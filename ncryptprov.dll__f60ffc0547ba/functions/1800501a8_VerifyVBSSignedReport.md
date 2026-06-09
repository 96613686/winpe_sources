# VerifyVBSSignedReport

- ea: `0x1800501a8`
- end: `0x180050384`
- name: `VerifyVBSSignedReport`
- size: `476`
- prototype: `__int64 __usercall@<rax>(BCRYPT_KEY_HANDLE hKey@<rcx>, ULONG, void *Source2, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004ff08`

## callees

- `0x18000af80`
- `0x1800501a8`
- `0x180062310`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x18005023c`
- `ntdll!RtlCompareMemory` at `0x18005023c`
- `bcrypt!BCryptHash` at `0x1800502cd`
- `bcrypt!BCryptHash` at `0x1800502cd`
- `bcrypt!BCryptVerifySignature` at `0x180050314`
- `bcrypt!BCryptVerifySignature` at `0x180050314`

## string_xrefs

- `0x180050353`: `onecore\ds\security\cryptoapi\ncrypt\storage\verifyclaim.c`

## pseudocode

```c
__int64 __fastcall VerifyVBSSignedReport(
        BCRYPT_KEY_HANDLE hKey,
        __int64 a2,
        unsigned int a3,
        UCHAR *a4,
        ULONG cbSignature,
        void *Source2,
        int a7,
        _QWORD *a8,
        _DWORD *a9,
        bool *a10)
{
  unsigned int *v13; // rdi
  __int64 v14; // r9
  int v15; // r9d
  char *v16; // rcx
  unsigned __int64 v17; // r8
  char *v18; // rdx
  unsigned __int64 v19; // rax
  int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // rcx
  NTSTATUS v23; // eax
  _QWORD pPaddingInfo[2]; // [rsp+40h] [rbp-68h] BYREF
  UCHAR pbHash[32]; // [rsp+50h] [rbp-58h] BYREF

  pPaddingInfo[0] = L"SHA256";
  pPaddingInfo[1] = 32;
  if ( a3 < 0x2C || a3 != *(_DWORD *)(a2 + 4) || a3 < *(_DWORD *)(a2 + 8) )
  {
    v14 = 644;
    goto LABEL_20;
  }
  *a8 = *(_QWORD *)(a2 + 28);
  *a9 = *(_DWORD *)(a2 + 36);
  v13 = (unsigned int *)(a2 + *(unsigned int *)(a2 + 8));
  if ( a7 != RtlCompareMemory(v13 + 5, Source2, v13[4]) )
  {
    v14 = 680;
LABEL_20:
    v21 = -1073741271;
    v22 = 3221226025LL;
    goto LABEL_21;
  }
  v15 = 1;
  v16 = (char *)v13 + *v13;
  v17 = (unsigned __int64)&v16[*((unsigned int *)v16 + 3) + 32];
  v18 = v16 + 32;
  if ( (unsigned __int64)(v16 + 32) < v17 )
  {
    do
    {
      v19 = (unsigned __int64)(v18 + 16);
      if ( (unsigned __int64)(v18 + 16) > v17 || !*((_DWORD *)v18 + 1) )
        break;
      if ( *((_DWORD *)v18 + 1) == 2 )
        v15 = *((_DWORD *)v18 + 2);
      v18 += 16;
    }
    while ( v19 < v17 );
  }
  *a10 = v15 != 0;
  v20 = BCryptHash(65, 0, 0, a2, *(_DWORD *)(a2 + 4), pbHash, 32);
  v21 = v20;
  if ( v20 < 0 )
  {
    v14 = 732;
    v22 = (unsigned int)v20;
LABEL_21:
    DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\verifyclaim.c", v14);
    return v21;
  }
  v23 = BCryptVerifySignature(hKey, pPaddingInfo, pbHash, 0x20u, a4, cbSignature, 8u);
  v21 = v23;
  if ( v23 < 0 )
  {
    if ( v23 == -1073700864 || v23 == -1073741811 )
      v21 = -1073741271;
    v14 = 752;
    v22 = v21;
    goto LABEL_21;
  }
  return v21;
}

```

## disassembly

```asm
0x1800501a8  push    rbx
0x1800501aa  push    rbp
0x1800501ab  push    rsi
0x1800501ac  push    rdi
0x1800501ad  push    r14
0x1800501af  sub     rsp, 80h
0x1800501b6  mov     rax, cs:__security_cookie
0x1800501bd  xor     rax, rsp
0x1800501c0  mov     [rsp+0A8h+var_38], rax
0x1800501c5  mov     r14, [rsp+0A8h+arg_48]
0x1800501cd  lea     rax, aSha256; "SHA256"
0x1800501d4  mov     [rsp+0A8h+pPaddingInfo], rax
0x1800501d9  mov     rbp, r9
0x1800501dc  mov     r9, [rsp+0A8h+arg_40]
0x1800501e4  mov     rbx, rdx
0x1800501e7  mov     rdx, [rsp+0A8h+Source2]; Source2
0x1800501ef  mov     rsi, rcx
0x1800501f2  mov     rcx, [rsp+0A8h+arg_38]
0x1800501fa  mov     [rsp+0A8h+var_60], 20h ; ' '
0x180050203  cmp     r8d, 2Ch ; ','
0x180050207  jb      loc_180050343
0x18005020d  cmp     r8d, [rbx+4]
0x180050211  jnz     loc_180050343
0x180050217  cmp     r8d, [rbx+8]
0x18005021b  jb      loc_180050343
0x180050221  mov     rax, [rbx+1Ch]
0x180050225  mov     [rcx], rax
0x180050228  mov     eax, [rbx+24h]
0x18005022b  mov     [r9], eax
0x18005022e  mov     edi, [rbx+8]
0x180050231  add     rdi, rbx
0x180050234  mov     r8d, [rdi+10h]; Length
0x180050238  lea     rcx, [rdi+14h]; Source1
0x18005023c  call    cs:__imp_RtlCompareMemory
0x180050243  nop     dword ptr [rax+rax+00h]
0x180050248  mov     ecx, [rsp+0A8h+arg_30]
0x18005024f  cmp     rcx, rax
0x180050252  jz      short loc_18005025F
0x180050254  mov     r9d, 2A8h
0x18005025a  jmp     loc_180050349
0x18005025f  mov     eax, [rdi]
0x180050261  mov     r9d, 1
0x180050267  lea     rcx, [rax+rdi]
0x18005026b  mov     eax, [rax+rdi+0Ch]
0x18005026f  lea     r8, [rcx+20h]
0x180050273  add     r8, rax
0x180050276  lea     rdx, [rcx+20h]
0x18005027a  cmp     rdx, r8
0x18005027d  jnb     short loc_1800502A0
0x18005027f  lea     rax, [rdx+10h]
0x180050283  cmp     rax, r8
0x180050286  ja      short loc_1800502A0
0x180050288  cmp     dword ptr [rdx+4], 0
0x18005028c  jz      short loc_1800502A0
0x18005028e  cmp     dword ptr [rdx+4], 2
0x180050292  jnz     short loc_180050298
0x180050294  mov     r9d, [rdx+8]
0x180050298  mov     rdx, rax
0x18005029b  cmp     rax, r8
0x18005029e  jb      short loc_18005027F
0x1800502a0  test    r9d, r9d
0x1800502a3  mov     [rsp+0A8h+dwFlags], 20h ; ' '
0x1800502ab  mov     r9, rbx
0x1800502ae  setnz   al
0x1800502b1  xor     edx, edx
0x1800502b3  mov     [r14], al
0x1800502b6  xor     r8d, r8d
0x1800502b9  lea     rax, [rsp+0A8h+pbHash]
0x1800502be  mov     qword ptr [rsp+0A8h+cbSignature], rax
0x1800502c3  mov     eax, [rbx+4]
0x1800502c6  lea     ecx, [rdx+41h]
0x1800502c9  mov     dword ptr [rsp+0A8h+pbSignature], eax
0x1800502cd  call    cs:__imp_BCryptHash
0x1800502d4  nop     dword ptr [rax+rax+00h]
0x1800502d9  mov     ebx, eax
0x1800502db  test    eax, eax
0x1800502dd  jns     short loc_1800502E9
0x1800502df  mov     r9d, 2DCh
0x1800502e5  mov     ecx, eax
0x1800502e7  jmp     short loc_180050353
0x1800502e9  mov     eax, [rsp+0A8h+arg_20]
0x1800502f0  lea     r8, [rsp+0A8h+pbHash]; pbHash
0x1800502f5  mov     [rsp+0A8h+dwFlags], 8; dwFlags
0x1800502fd  lea     rdx, [rsp+0A8h+pPaddingInfo]; pPaddingInfo
0x180050302  mov     [rsp+0A8h+cbSignature], eax; cbSignature
0x180050306  mov     r9d, 20h ; ' '; cbHash
0x18005030c  mov     rcx, rsi; hKey
0x18005030f  mov     [rsp+0A8h+pbSignature], rbp; pbSignature
0x180050314  call    cs:__imp_BCryptVerifySignature
0x18005031b  nop     dword ptr [rax+rax+00h]
0x180050320  mov     ebx, eax
0x180050322  test    eax, eax
0x180050324  jns     short loc_180050366
0x180050326  cmp     eax, 0C000A000h
0x18005032b  jz      short loc_180050334
0x18005032d  cmp     eax, 0C000000Dh
0x180050332  jnz     short loc_180050339
0x180050334  mov     ebx, 0C0000229h
0x180050339  mov     r9d, 2F0h
0x18005033f  mov     ecx, ebx
0x180050341  jmp     short loc_180050353
0x180050343  mov     r9d, 284h
0x180050349  mov     ebx, 0C0000229h
0x18005034e  mov     ecx, 0C0000229h
0x180050353  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005035a  lea     rdx, aStatus; "Status"
0x180050361  call    DebugTraceError
0x180050366  mov     eax, ebx
0x180050368  mov     rcx, [rsp+0A8h+var_38]
0x18005036d  xor     rcx, rsp; StackCookie
0x180050370  call    __security_check_cookie
0x180050375  add     rsp, 80h
0x18005037c  pop     r14
0x18005037e  pop     rdi
0x18005037f  pop     rsi
0x180050380  pop     rbp
0x180050381  pop     rbx
0x180050382  retn
```
