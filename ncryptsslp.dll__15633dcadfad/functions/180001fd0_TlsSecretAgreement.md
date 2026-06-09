# TlsSecretAgreement

- ea: `0x180001fd0`
- end: `0x18000228c`
- name: `TlsSecretAgreement`
- size: `700`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013f08`

## callees

- `0x180001fd0`
- `0x180003ef0`
- `0x18000b594`

## import_xrefs

- `ncrypt!NCryptDeriveKey` at `0x18000206a`
- `ncrypt!NCryptDeriveKey` at `0x1800020c9`
- `ncrypt!NCryptDeriveKey` at `0x18000206a`
- `ncrypt!NCryptDeriveKey` at `0x1800020c9`
- `ncrypt!NCryptSecretAgreement` at `0x180002034`
- `ncrypt!NCryptSecretAgreement` at `0x180002034`
- `ncrypt!NCryptFreeObject` at `0x18000211f`
- `ncrypt!NCryptFreeObject` at `0x18000211f`
- `ntdll!RtlAllocateHeap` at `0x18000208e`
- `ntdll!RtlAllocateHeap` at `0x18000208e`

## string_xrefs

- `0x18000215b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000222c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180002273`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsSecretAgreement(NCRYPT_KEY_HANDLE a1, NCRYPT_KEY_HANDLE a2, int a3, BYTE **a4, DWORD *a5)
{
  DWORD *v6; // rsi
  int v7; // edx
  SECURITY_STATUS v8; // ebx
  int v9; // r8d
  BYTE *Heap; // rax
  int v11; // edx
  int v12; // r8d
  BYTE *v13; // rbp
  DWORD v14; // r8d
  BYTE *v15; // rcx
  BYTE *v16; // rdx
  char v17; // al
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  BYTE *v21; // rax
  char dwFlags; // [rsp+30h] [rbp-28h]
  NCRYPT_SECRET_HANDLE phAgreedSecret; // [rsp+60h] [rbp+8h] BYREF
  DWORD pcbResult; // [rsp+70h] [rbp+18h] BYREF

  phAgreedSecret = 0;
  pcbResult = 0;
  if ( a1 && a2 && a4 && !*a4 && (v6 = a5) != 0 )
  {
    v8 = NCryptSecretAgreement(a1, a2, &phAgreedSecret, 0);
    if ( v8 < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        dwFlags = 121;
        goto LABEL_20;
      }
    }
    else
    {
      v8 = NCryptDeriveKey(phAgreedSecret, L"TRUNCATE", 0, 0, 0, &pcbResult, 0);
      if ( v8 >= 0 )
      {
        Heap = (BYTE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, pcbResult);
        v13 = Heap;
        if ( !Heap )
        {
          v8 = -1073741801;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v11,
              v12,
              (unsigned int)"Status",
              23,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              146);
          goto LABEL_14;
        }
        v8 = NCryptDeriveKey(phAgreedSecret, L"TRUNCATE", 0, Heap, pcbResult, &pcbResult, 0);
        if ( v8 >= 0 )
        {
          v14 = pcbResult;
          v15 = v13;
          v16 = &v13[pcbResult - 1];
          if ( v13 < v16 )
          {
            do
            {
              *v15 ^= *v16;
              *v16 ^= *v15;
              v17 = *v16--;
              *v15++ ^= v17;
            }
            while ( v15 < v16 );
            v14 = pcbResult;
          }
          *a4 = v13;
          *v6 = v14;
          goto LABEL_14;
        }
        v20 = pcbResult;
        v21 = v13;
        if ( pcbResult )
        {
          do
          {
            *v21++ = 0;
            --v20;
          }
          while ( v20 );
        }
        MSCryptFree(v13);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_14;
        dwFlags = -95;
        goto LABEL_20;
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        dwFlags = -117;
LABEL_20:
        WPP_SF_sDsd(
          v19[2],
          v7,
          v9,
          (unsigned int)"Status",
          v8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          dwFlags);
      }
    }
  }
  else
  {
    v8 = -1073741811;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v8;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      106);
  }
LABEL_14:
  if ( phAgreedSecret )
    NCryptFreeObject(phAgreedSecret);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180001fd0  mov     [rsp+arg_8], rbx
0x180001fd5  mov     [rsp+arg_18], rbp
0x180001fda  mov     [rsp+arg_10], r8d
0x180001fdf  push    rsi
0x180001fe0  push    rdi
0x180001fe1  push    r14
0x180001fe3  sub     rsp, 40h
0x180001fe7  xor     r14d, r14d
0x180001fea  mov     rdi, r9
0x180001fed  mov     [rsp+58h+phAgreedSecret], r14
0x180001ff2  mov     [rsp+58h+arg_10], r14d
0x180001ff7  test    rcx, rcx
0x180001ffa  jz      loc_180002245
0x180002000  test    rdx, rdx
0x180002003  jz      loc_180002245
0x180002009  test    r9, r9
0x18000200c  jz      loc_180002245
0x180002012  cmp     [r9], r14
0x180002015  jnz     loc_180002245
0x18000201b  mov     rsi, [rsp+58h+arg_20]
0x180002023  test    rsi, rsi
0x180002026  jz      loc_180002245
0x18000202c  xor     r9d, r9d; dwFlags
0x18000202f  lea     r8, [rsp+58h+phAgreedSecret]; phAgreedSecret
0x180002034  call    cs:__imp_NCryptSecretAgreement
0x18000203a  mov     ebx, eax
0x18000203c  test    eax, eax
0x18000203e  js      loc_1800021D0
0x180002044  mov     rcx, [rsp+58h+phAgreedSecret]; hSharedSecret
0x180002049  lea     rax, [rsp+58h+arg_10]
0x18000204e  mov     dword ptr [rsp+58h+dwFlags], r14d; dwFlags
0x180002053  lea     rdx, pwszKDF; "TRUNCATE"
0x18000205a  mov     [rsp+58h+pcbResult], rax; pcbResult
0x18000205f  xor     r9d, r9d; pbDerivedKey
0x180002062  xor     r8d, r8d; pParameterList
0x180002065  mov     [rsp+58h+cbDerivedKey], r14d; cbDerivedKey
0x18000206a  call    cs:__imp_NCryptDeriveKey
0x180002070  mov     ebx, eax
0x180002072  test    eax, eax
0x180002074  js      loc_18000213A
0x18000207a  mov     rcx, gs:60h
0x180002083  xor     edx, edx; Flags
0x180002085  mov     r8d, [rsp+58h+arg_10]; Size
0x18000208a  mov     rcx, [rcx+30h]; HeapHandle
0x18000208e  call    cs:__imp_RtlAllocateHeap
0x180002094  mov     rbp, rax
0x180002097  test    rax, rax
0x18000209a  jz      loc_1800021FE
0x1800020a0  mov     rcx, [rsp+58h+phAgreedSecret]; hSharedSecret
0x1800020a5  lea     rax, [rsp+58h+arg_10]
0x1800020aa  mov     dword ptr [rsp+58h+dwFlags], r14d; dwFlags
0x1800020af  lea     rdx, pwszKDF; "TRUNCATE"
0x1800020b6  mov     [rsp+58h+pcbResult], rax; pcbResult
0x1800020bb  mov     r9, rbp; pbDerivedKey
0x1800020be  mov     eax, [rsp+58h+arg_10]
0x1800020c2  xor     r8d, r8d; pParameterList
0x1800020c5  mov     [rsp+58h+cbDerivedKey], eax; cbDerivedKey
0x1800020c9  call    cs:__imp_NCryptDeriveKey
0x1800020cf  mov     ebx, eax
0x1800020d1  test    eax, eax
0x1800020d3  js      loc_18000217D
0x1800020d9  mov     r8d, [rsp+58h+arg_10]
0x1800020de  mov     rcx, rbp
0x1800020e1  lea     rdx, [r8-1]
0x1800020e5  add     rdx, rbp
0x1800020e8  cmp     rbp, rdx
0x1800020eb  jnb     short loc_18000210F
0x1800020ed  nop     dword ptr [rax]
0x1800020f0  movzx   eax, byte ptr [rdx]
0x1800020f3  xor     [rcx], al
0x1800020f5  movzx   eax, byte ptr [rcx]
0x1800020f8  xor     [rdx], al
0x1800020fa  movzx   eax, byte ptr [rdx]
0x1800020fd  dec     rdx
0x180002100  xor     [rcx], al
0x180002102  inc     rcx
0x180002105  cmp     rcx, rdx
0x180002108  jb      short loc_1800020F0
0x18000210a  mov     r8d, [rsp+58h+arg_10]
0x18000210f  mov     [rdi], rbp
0x180002112  mov     [rsi], r8d
0x180002115  mov     rcx, [rsp+58h+phAgreedSecret]; hObject
0x18000211a  test    rcx, rcx
0x18000211d  jz      short loc_180002125
0x18000211f  call    cs:__imp_NCryptFreeObject
0x180002125  mov     rbp, [rsp+58h+arg_18]
0x18000212a  mov     eax, ebx
0x18000212c  mov     rbx, [rsp+58h+arg_8]
0x180002131  add     rsp, 40h
0x180002135  pop     r14
0x180002137  pop     rdi
0x180002138  pop     rsi
0x180002139  retn
0x18000213a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002141  lea     rax, WPP_GLOBAL_Control
0x180002148  cmp     rcx, rax
0x18000214b  jz      short loc_180002115
0x18000214d  test    byte ptr [rcx+1Ch], 1
0x180002151  jz      short loc_180002115
0x180002153  mov     dword ptr [rsp+58h+dwFlags], 0E8Bh
0x18000215b  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002162  mov     [rsp+58h+pcbResult], rax
0x180002167  mov     [rsp+58h+cbDerivedKey], ebx
0x18000216b  mov     rcx, [rcx+10h]
0x18000216f  lea     r9, aStatus; "Status"
0x180002176  call    WPP_SF_sDsd
0x18000217b  jmp     short loc_180002115
0x18000217d  mov     edx, [rsp+58h+arg_10]
0x180002181  mov     rax, rbp
0x180002184  test    rdx, rdx
0x180002187  jz      short loc_18000219D
0x180002189  nop     dword ptr [rax+00000000h]
0x180002190  mov     [rax], r14b
0x180002193  lea     rax, [rax+1]
0x180002197  sub     rdx, 1
0x18000219b  jnz     short loc_180002190
0x18000219d  mov     rcx, rbp
0x1800021a0  call    MSCryptFree
0x1800021a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021ac  lea     rax, WPP_GLOBAL_Control
0x1800021b3  cmp     rcx, rax
0x1800021b6  jz      loc_180002115
0x1800021bc  test    byte ptr [rcx+1Ch], 1
0x1800021c0  jz      loc_180002115
0x1800021c6  mov     dword ptr [rsp+58h+dwFlags], 0EA1h
0x1800021ce  jmp     short loc_18000215B
0x1800021d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021d7  lea     rax, WPP_GLOBAL_Control
0x1800021de  cmp     rcx, rax
0x1800021e1  jz      loc_180002115
0x1800021e7  test    byte ptr [rcx+1Ch], 1
0x1800021eb  jz      loc_180002115
0x1800021f1  mov     dword ptr [rsp+58h+dwFlags], 0E79h
0x1800021f9  jmp     loc_18000215B
0x1800021fe  mov     ebx, 0C0000017h
0x180002203  mov     rcx, cs:WPP_GLOBAL_Control
0x18000220a  lea     rax, WPP_GLOBAL_Control
0x180002211  cmp     rcx, rax
0x180002214  jz      loc_180002115
0x18000221a  test    byte ptr [rcx+1Ch], 1
0x18000221e  jz      loc_180002115
0x180002224  mov     dword ptr [rsp+58h+dwFlags], 0E92h
0x18000222c  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002233  mov     [rsp+58h+pcbResult], rax
0x180002238  mov     [rsp+58h+cbDerivedKey], 0C0000017h
0x180002240  jmp     loc_18000216B
0x180002245  mov     ebx, 0C000000Dh
0x18000224a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002251  lea     rax, WPP_GLOBAL_Control
0x180002258  cmp     rcx, rax
0x18000225b  jz      loc_180002125
0x180002261  test    byte ptr [rcx+1Ch], 1
0x180002265  jz      loc_180002125
0x18000226b  mov     dword ptr [rsp+58h+dwFlags], 0E6Ah
0x180002273  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000227a  mov     [rsp+58h+pcbResult], rax
0x18000227f  mov     [rsp+58h+cbDerivedKey], 0C000000Dh
0x180002287  jmp     loc_18000216B
```
