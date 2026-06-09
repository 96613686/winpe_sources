# MinCrypK_FindPageHashesInSignedCert

- ea: `0x18008d7bc`
- end: `0x18008da0a`
- name: `MinCrypK_FindPageHashesInSignedCert`
- size: `590`
- prototype: `__int64 __usercall@<rax>(void *Source1@<rcx>, SIZE_T Length@<rdx>, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006157c`
- `0x180094f70`

## callees

- `0x180012d3e`
- `0x18002bef0`
- `0x18008d5e4`
- `0x18008d7bc`
- `0x18008da10`
- `0x18008dcac`
- `0x18008de28`
- `0x18008e91c`
- `0x1800905d0`
- `0x180090988`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x18008d96b`
- `ntoskrnl!RtlCompareMemory` at `0x18008d96b`

## pseudocode

```c
__int64 __fastcall MinCrypK_FindPageHashesInSignedCert(
        void *Source1,
        SIZE_T Length,
        unsigned int a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        __int64 a7)
{
  SIZE_T v8; // rbx
  __int64 *v11; // rax
  __int64 result; // rax
  int Values; // eax
  unsigned int v14; // edi
  int v15; // eax
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h]
  int v20; // [rsp+70h] [rbp-90h] BYREF
  void *Source2; // [rsp+78h] [rbp-88h]
  int v22; // [rsp+80h] [rbp-80h]
  __int64 v23; // [rsp+88h] [rbp-78h]
  _BYTE v24[16]; // [rsp+C0h] [rbp-40h] BYREF
  int v25; // [rsp+D0h] [rbp-30h]
  _BYTE v26[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v27[16]; // [rsp+100h] [rbp+0h] BYREF
  int v28; // [rsp+110h] [rbp+10h]

  v8 = (unsigned int)Length;
  LODWORD(v19) = 0;
  v18 = 0;
  v17 = 0;
  if ( I_MinCryptIsHashRevoked(a3, Source1, (unsigned int)Length) )
  {
    result = 3221227011LL;
    goto LABEL_19;
  }
  v11 = qword_18002E530;
  if ( (g_CiPolicyState & 0x10000) == 0 )
    v11 = (__int64 *)&qword_18002E5B0;
  result = MinCrypK_VerifySignedDataKModeEx(*(_QWORD *)a4, *(_DWORD *)(a4 + 8), 0, 0, (__int64)v11, a6, &v20, a7, 0);
  if ( (int)result < 0 )
    goto LABEL_19;
  if ( v20 != 10 || RtlCompareMemory_0(qword_1800F4968, Source2, 0xAu) != 10 )
    goto LABEL_20;
  v16 = 8;
  Values = MinAsn1ExtractValues(v23, v22, (unsigned int)&v16, (unsigned int)&qword_18002E7A0, 6, (__int64)v24);
  if ( Values > 0 )
    Values = v25;
  if ( Values < 0 )
    goto LABEL_20;
  v14 = MinCryptDecodeHashAlgorithmIdentifier(v27);
  switch ( v14 )
  {
    case 0x8004u:
      v15 = 20;
      break;
    case 0x800Cu:
      v15 = 32;
      break;
    case 0x800Du:
      v15 = 48;
      break;
    case 0x800Eu:
      v15 = 64;
      break;
    default:
LABEL_20:
      result = 3221226536LL;
      goto LABEL_19;
  }
  if ( v15 != (_DWORD)v8
    || v28 != (_DWORD)v8
    || a3 != v14
    || !(unsigned __int8)MinAsn1FindPageHashesAttribute(v26, &v20)
    || !I_ValidatePageHashesBlob((__int64)&v20, *(_QWORD *)a4, *(_DWORD *)(a4 + 8), v8, (__int64)&v18) )
  {
    goto LABEL_20;
  }
  if ( RtlCompareMemory(Source1, (const void *)(v19 + 4), v8) != v8 )
  {
    result = 3221226021LL;
    goto LABEL_19;
  }
  result = I_AllocatePageHashes(&v18, v14, 0, &v17);
  if ( (int)result < 0 )
  {
LABEL_19:
    *(_DWORD *)(a6 + 8) |= 0x100000u;
    return result;
  }
  *a5 = v17;
  return result;
}

```

## disassembly

```asm
0x18008d7bc  mov     [rsp-8+arg_10], rbx
0x18008d7c1  push    rbp
0x18008d7c2  push    rsi
0x18008d7c3  push    rdi
0x18008d7c4  push    r12
0x18008d7c6  push    r13
0x18008d7c8  push    r14
0x18008d7ca  push    r15
0x18008d7cc  lea     rbp, [rsp-30h]
0x18008d7d1  sub     rsp, 130h
0x18008d7d8  mov     rax, cs:__security_cookie
0x18008d7df  xor     rax, rsp
0x18008d7e2  mov     [rbp+60h+var_40], rax
0x18008d7e6  mov     r12, [rbp+60h+arg_20]
0x18008d7ed  xor     eax, eax
0x18008d7ef  mov     rsi, [rbp+60h+arg_28]
0x18008d7f6  mov     r15d, r8d
0x18008d7f9  mov     rdi, [rbp+60h+arg_30]
0x18008d800  mov     r8d, edx
0x18008d803  mov     ebx, edx
0x18008d805  mov     r13, rcx
0x18008d808  mov     rdx, rcx
0x18008d80b  mov     qword ptr [rsp+160h+var_FC], rax
0x18008d810  mov     ecx, r15d
0x18008d813  mov     [rsp+60h], rax
0x18008d818  mov     r14, r9
0x18008d81b  mov     [rsp+160h+var_108], rax
0x18008d820  call    I_MinCryptIsHashRevoked
0x18008d825  test    rax, rax
0x18008d828  jnz     loc_18008DA03
0x18008d82e  test    byte ptr cs:g_CiPolicyState+2, 1
0x18008d835  lea     rcx, qword_18002E5B0
0x18008d83c  mov     edx, [r14+8]; int
0x18008d840  lea     rax, qword_18002E530
0x18008d847  cmovz   rax, rcx
0x18008d84b  mov     [rsp+160h+var_120], 0; __int64
0x18008d854  mov     [rsp+160h+var_128], rdi; __int64
0x18008d859  lea     rcx, [rsp+160h+var_F0]
0x18008d85e  mov     [rsp+160h+var_130], rcx; void *
0x18008d863  xor     r9d, r9d; int
0x18008d866  mov     rcx, [r14]; int
0x18008d869  xor     r8d, r8d; int
0x18008d86c  mov     qword ptr [rsp+160h+var_138], rsi; int
0x18008d871  mov     [rsp+160h+var_140], rax; __int64
0x18008d876  call    MinCrypK_VerifySignedDataKModeEx
0x18008d87b  test    eax, eax
0x18008d87d  js      loc_18008D994
0x18008d883  cmp     [rsp+160h+var_F0], 0Ah
0x18008d888  jnz     loc_18008D9C1
0x18008d88e  mov     rdx, [rsp+160h+Source2]; Source2
0x18008d893  lea     rcx, qword_1800F4968; Source1
0x18008d89a  mov     r8d, 0Ah; Length
0x18008d8a0  call    RtlCompareMemory_0
0x18008d8a5  cmp     rax, 0Ah
0x18008d8a9  jnz     loc_18008D9C1
0x18008d8af  mov     edx, [rbp+60h+var_E0]
0x18008d8b2  lea     rax, [rbp+60h+var_A0]
0x18008d8b6  mov     rcx, [rbp+60h+var_D8]
0x18008d8ba  lea     r9, qword_18002E7A0
0x18008d8c1  mov     qword ptr [rsp+160h+var_138], rax
0x18008d8c6  lea     r8, [rsp+160h+var_110]
0x18008d8cb  mov     dword ptr [rsp+160h+var_140], 6
0x18008d8d3  mov     [rsp+160h+var_110], 8
0x18008d8db  call    MinAsn1ExtractValues
0x18008d8e0  test    eax, eax
0x18008d8e2  cmovg   eax, [rbp+60h+var_90]
0x18008d8e6  test    eax, eax
0x18008d8e8  js      loc_18008D9C1
0x18008d8ee  lea     rcx, [rbp+60h+var_60]
0x18008d8f2  call    MinCryptDecodeHashAlgorithmIdentifier
0x18008d8f7  mov     ecx, eax
0x18008d8f9  mov     edi, eax
0x18008d8fb  sub     ecx, 8004h
0x18008d901  jnz     loc_18008D9C8
0x18008d907  lea     eax, [rcx+14h]
0x18008d90a  cmp     eax, ebx
0x18008d90c  jnz     loc_18008D9C1
0x18008d912  cmp     [rbp+60h+var_50], ebx
0x18008d915  jnz     loc_18008D9C1
0x18008d91b  cmp     r15d, edi
0x18008d91e  jnz     loc_18008D9C1
0x18008d924  lea     rdx, [rsp+160h+var_F0]
0x18008d929  lea     rcx, [rbp+60h+var_70]
0x18008d92d  call    MinAsn1FindPageHashesAttribute
0x18008d932  test    al, al
0x18008d934  jz      loc_18008D9C1
0x18008d93a  mov     r8d, [r14+8]
0x18008d93e  lea     rax, [rsp+160h+var_100]
0x18008d943  mov     rdx, [r14]
0x18008d946  lea     rcx, [rsp+160h+var_F0]
0x18008d94b  mov     r9d, ebx
0x18008d94e  mov     [rsp+160h+var_140], rax
0x18008d953  call    I_ValidatePageHashesBlob
0x18008d958  test    eax, eax
0x18008d95a  jz      short loc_18008D9C1
0x18008d95c  mov     rdx, qword ptr [rsp+160h+var_FC+4]
0x18008d961  mov     r8, rbx; Length
0x18008d964  add     rdx, 4; Source2
0x18008d968  mov     rcx, r13; Source1
0x18008d96b  call    cs:__imp_RtlCompareMemory
0x18008d972  nop     dword ptr [rax+rax+00h]
0x18008d977  cmp     rax, rbx
0x18008d97a  jnz     short loc_18008D9F1
0x18008d97c  lea     r9, [rsp+160h+var_108]
0x18008d981  xor     r8d, r8d
0x18008d984  mov     edx, edi
0x18008d986  lea     rcx, [rsp+160h+var_100]
0x18008d98b  call    I_AllocatePageHashes
0x18008d990  test    eax, eax
0x18008d992  jns     short loc_18008D9F8
0x18008d994  bts     dword ptr [rsi+8], 14h
0x18008d999  mov     rcx, [rbp+60h+var_40]
0x18008d99d  xor     rcx, rsp; StackCookie
0x18008d9a0  call    __security_check_cookie
0x18008d9a5  mov     rbx, [rsp+160h+arg_10]
0x18008d9ad  add     rsp, 130h
0x18008d9b4  pop     r15
0x18008d9b6  pop     r14
0x18008d9b8  pop     r13
0x18008d9ba  pop     r12
0x18008d9bc  pop     rdi
0x18008d9bd  pop     rsi
0x18008d9be  pop     rbp
0x18008d9bf  retn
0x18008d9c1  mov     eax, 0C0000428h
0x18008d9c6  jmp     short loc_18008D994
0x18008d9c8  sub     ecx, 8
0x18008d9cb  jnz     short loc_18008D9D5
0x18008d9cd  lea     eax, [rcx+20h]
0x18008d9d0  jmp     loc_18008D90A
0x18008d9d5  sub     ecx, 1
0x18008d9d8  jz      short loc_18008D9E7
0x18008d9da  cmp     ecx, 1
0x18008d9dd  jnz     short loc_18008D9C1
0x18008d9df  lea     eax, [rcx+3Fh]
0x18008d9e2  jmp     loc_18008D90A
0x18008d9e7  mov     eax, 30h ; '0'
0x18008d9ec  jmp     loc_18008D90A
0x18008d9f1  mov     eax, 0C0000225h
0x18008d9f6  jmp     short loc_18008D994
0x18008d9f8  mov     rcx, [rsp+160h+var_108]
0x18008d9fd  mov     [r12], rcx
0x18008da01  jmp     short loc_18008D999
0x18008da03  mov     eax, 0C0000603h
0x18008da08  jmp     short loc_18008D994
```
