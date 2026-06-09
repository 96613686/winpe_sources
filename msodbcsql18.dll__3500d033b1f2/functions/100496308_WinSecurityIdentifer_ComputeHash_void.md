# WinSecurityIdentifer::ComputeHash(void)

- ea: `0x100496308`
- end: `0x1004964cd`
- name: `?ComputeHash@WinSecurityIdentifer@@AEAAJXZ`
- size: `453`
- prototype: `__int64 __fastcall(WinSecurityIdentifer *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1004966d0`

## callees

- `0x100496308`
- `0x100546a24`
- `0x100546d91`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x100496498`
- `KERNEL32!LocalFree` at `0x100496498`
- `KERNEL32!GetLastError` at `0x100496352`
- `KERNEL32!GetLastError` at `0x1004963fc`
- `KERNEL32!GetLastError` at `0x10049641d`
- `KERNEL32!GetLastError` at `0x10049644d`
- `KERNEL32!GetLastError` at `0x100496352`
- `KERNEL32!GetLastError` at `0x1004963fc`
- `KERNEL32!GetLastError` at `0x10049641d`
- `KERNEL32!GetLastError` at `0x10049644d`
- `ADVAPI32!GetTokenInformation` at `0x100496348`
- `ADVAPI32!GetTokenInformation` at `0x1004963e9`
- `ADVAPI32!GetTokenInformation` at `0x100496348`
- `ADVAPI32!GetTokenInformation` at `0x1004963e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinSecurityIdentifer::ComputeHash(HANDLE *this)
{
  unsigned int v2; // edi
  PSID *v3; // rbx
  signed int LastError; // eax
  __int64 v5; // r9
  __int64 v6; // r8
  __int64 v7; // rdx
  signed int v8; // eax
  signed int v9; // eax
  int v10; // edx
  LPWSTR i; // rcx
  DWORD TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+10h] BYREF
  __int64 v15; // [rsp+70h] [rbp+18h]

  v2 = 0;
  TokenInformationLength = 0;
  StringSid = 0;
  v3 = 0;
  v15 = 0;
  if ( !GetTokenInformation(this[3], TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      v2 = (unsigned __int16)LastError | 0x80070000;
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( LastError <= 0 )
          v2 = LastError;
        v6 = v2;
        v7 = 109577;
        goto LABEL_7;
      }
LABEL_18:
      if ( LastError <= 0 )
        v2 = LastError;
      goto LABEL_30;
    }
  }
  v3 = (PSID *)((__int64 (__fastcall *)(struct IMalloc *, _QWORD))g_pMO->lpVtbl[1].Free)(g_pMO, TokenInformationLength);
  if ( v3 )
  {
    if ( GetTokenInformation(this[3], TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
    {
      if ( ConvertSidToStringSidW_0(*v3, &StringSid) )
      {
        v10 = 0;
        for ( i = StringSid; *i; ++i )
          v10 = *i + 101 * v10;
        *((_DWORD *)this + 4) = v10;
        goto LABEL_30;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        v9 = GetLastError();
        v6 = (unsigned __int16)v9 | 0x80070000;
        if ( v9 <= 0 )
          v6 = (unsigned int)v9;
        v7 = 142345;
        goto LABEL_7;
      }
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      v8 = GetLastError();
      v6 = (unsigned __int16)v8 | 0x80070000;
      if ( v8 <= 0 )
        v6 = (unsigned int)v8;
      v7 = 133129;
      goto LABEL_7;
    }
    LastError = GetLastError();
    v2 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_18;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    v7 = 119817;
    v6 = 2147942414LL;
LABEL_7:
    v2 = bidTraceHR(0, v7, v6, v5);
    goto LABEL_30;
  }
  v2 = -2147024882;
LABEL_30:
  if ( StringSid )
    LocalFree(StringSid);
  if ( v3 )
    ((void (__fastcall *)(struct IMalloc *, PSID *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v3);
  return v2;
}

```

## disassembly

```asm
0x100496308  mov     rax, rsp
0x10049630b  push    rbp
0x10049630c  push    rsi
0x10049630d  push    rdi
0x10049630e  sub     rsp, 40h
0x100496312  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x10049631a  mov     [rax+20h], rbx
0x10049631e  mov     rsi, rcx
0x100496321  xor     ebp, ebp
0x100496323  mov     edi, ebp
0x100496325  mov     [rax+8], ebp
0x100496328  mov     [rax+10h], rbp
0x10049632c  mov     ebx, ebp
0x10049632e  mov     [rax+18h], rbx
0x100496332  lea     rax, [rax+8]
0x100496336  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x10049633b  xor     r9d, r9d; TokenInformationLength
0x10049633e  xor     r8d, r8d; TokenInformation
0x100496341  lea     edx, [rbp+1]; TokenInformationClass
0x100496344  mov     rcx, [rcx+18h]; TokenHandle
0x100496348  call    cs:__imp_GetTokenInformation
0x10049634e  test    eax, eax
0x100496350  jnz     short loc_10049638E
0x100496352  call    cs:__imp_GetLastError
0x100496358  cmp     eax, 7Ah ; 'z'
0x10049635b  jz      short loc_10049638E
0x10049635d  movzx   edi, ax
0x100496360  or      edi, 80070000h
0x100496366  test    byte ptr cs:_bidGblFlags, 2
0x10049636d  jz      loc_10049642C
0x100496373  test    eax, eax
0x100496375  cmovle  edi, eax
0x100496378  mov     r8d, edi
0x10049637b  mov     edx, 1AC09h
0x100496380  xor     ecx, ecx
0x100496382  call    _bidTraceHR
0x100496387  mov     edi, eax
0x100496389  jmp     loc_10049648E
0x10049638e  mov     edx, [rsp+58h+TokenInformationLength]
0x100496392  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100496399  mov     rax, [rcx]
0x10049639c  mov     rax, [rax+70h]
0x1004963a0  call    cs:__guard_dispatch_icall_fptr
0x1004963a6  mov     rbx, rax
0x1004963a9  test    rax, rax
0x1004963ac  jnz     short loc_1004963CE
0x1004963ae  test    byte ptr cs:_bidGblFlags, 2
0x1004963b5  jz      short loc_1004963C4
0x1004963b7  mov     edx, 1D409h
0x1004963bc  mov     r8d, 8007000Eh
0x1004963c2  jmp     short loc_100496380
0x1004963c4  mov     edi, 8007000Eh
0x1004963c9  jmp     loc_10049648E
0x1004963ce  lea     rax, [rsp+58h+TokenInformationLength]
0x1004963d3  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1004963d8  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1004963dd  mov     r8, rbx; TokenInformation
0x1004963e0  mov     edx, 1; TokenInformationClass
0x1004963e5  mov     rcx, [rsi+18h]; TokenHandle
0x1004963e9  call    cs:__imp_GetTokenInformation
0x1004963ef  test    eax, eax
0x1004963f1  jnz     short loc_100496433
0x1004963f3  test    byte ptr cs:_bidGblFlags, 2
0x1004963fa  jz      short loc_10049641D
0x1004963fc  call    cs:__imp_GetLastError
0x100496402  movzx   r8d, ax
0x100496406  or      r8d, 80070000h
0x10049640d  test    eax, eax
0x10049640f  cmovle  r8d, eax
0x100496413  mov     edx, 20809h
0x100496418  jmp     loc_100496380
0x10049641d  call    cs:__imp_GetLastError
0x100496423  movzx   edi, ax
0x100496426  or      edi, 80070000h
0x10049642c  test    eax, eax
0x10049642e  cmovle  edi, eax
0x100496431  jmp     short loc_10049648E
0x100496433  lea     rdx, [rsp+58h+StringSid]; StringSid
0x100496438  mov     rcx, [rbx]; Sid
0x10049643b  call    ConvertSidToStringSidW_0
0x100496440  test    eax, eax
0x100496442  jnz     short loc_10049646E
0x100496444  test    byte ptr cs:_bidGblFlags, 2
0x10049644b  jz      short loc_10049641D
0x10049644d  call    cs:__imp_GetLastError
0x100496453  movzx   r8d, ax
0x100496457  or      r8d, 80070000h
0x10049645e  test    eax, eax
0x100496460  cmovle  r8d, eax
0x100496464  mov     edx, 22C09h
0x100496469  jmp     loc_100496380
0x10049646e  mov     edx, ebp
0x100496470  mov     rcx, [rsp+58h+StringSid]
0x100496475  jmp     short loc_100496483
0x100496477  imul    edx, 65h ; 'e'
0x10049647a  movzx   eax, ax
0x10049647d  add     edx, eax
0x10049647f  lea     rcx, [rcx+2]
0x100496483  movzx   eax, word ptr [rcx]
0x100496486  test    ax, ax
0x100496489  jnz     short loc_100496477
0x10049648b  mov     [rsi+10h], edx
0x10049648e  mov     rcx, [rsp+58h+StringSid]; hMem
0x100496493  test    rcx, rcx
0x100496496  jz      short loc_10049649F
0x100496498  call    cs:__imp_LocalFree
0x10049649e  nop
0x10049649f  test    rbx, rbx
0x1004964a2  jz      short loc_1004964BE
0x1004964a4  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1004964ab  mov     rax, [rcx]
0x1004964ae  mov     rdx, rbx
0x1004964b1  mov     rax, [rax+80h]
0x1004964b8  call    cs:__guard_dispatch_icall_fptr
0x1004964be  mov     eax, edi
0x1004964c0  mov     rbx, [rsp+58h+arg_18]
0x1004964c5  add     rsp, 40h
0x1004964c9  pop     rdi
0x1004964ca  pop     rsi
0x1004964cb  pop     rbp
0x1004964cc  retn
```
