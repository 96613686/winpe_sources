# GetDesktopUniqueName(ushort const *,ushort *,ulong)

- ea: `0x18000f900`
- end: `0x18000faad`
- name: `?GetDesktopUniqueName@@YAXPEBGPEAGK@Z`
- size: `429`
- prototype: `void __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `10`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002053c`
- `0x180020b3c`
- `0x180021890`
- `0x180022c48`
- `0x180052ff8`
- `0x18005c7ac`
- `0x18005c8c0`
- `0x180075940`
- `0x1800b4e9c`
- `0x1800bd150`

## callees

- `0x18000f900`
- `0x18000fac0`
- `0x180106a60`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x18000f9fc`
- `ntdll!NtQueryInformationProcess` at `0x18000f9fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f93d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f93d`
- `USER32!GetUserObjectInformationW` at `0x18000f972`
- `USER32!GetUserObjectInformationW` at `0x18000f972`
- `USER32!GetThreadDesktop` at `0x18000f945`
- `USER32!GetThreadDesktop` at `0x18000f945`

## pseudocode

```c
void __fastcall GetDesktopUniqueName(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  __int64 v6; // rax
  _WORD *v7; // rcx
  __int64 v8; // r8
  _WORD *v9; // rdx
  _WORD *v10; // rcx
  int v11; // ecx
  __int64 v12; // rax
  const OLECHAR *v13; // rcx
  __int64 nLengthNeeded; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+38h] [rbp-C8h] BYREF
  _WORD v16[264]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pvInfo[528]; // [rsp+280h] [rbp+180h] BYREF

  v16[0] = 0;
  LODWORD(nLengthNeeded) = 0;
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  if ( ThreadDesktop && GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x208u, (LPDWORD)&nLengthNeeded) )
  {
    v6 = 2147483646;
    v7 = pvInfo;
    v8 = 260;
    v9 = v16;
    do
    {
      if ( !v6 )
        break;
      if ( !*v7 )
        break;
      *v9++ = *v7++;
      --v6;
      --v8;
    }
    while ( v8 );
  }
  else
  {
    v12 = 2147483646;
    v13 = &lParam;
    v8 = 260;
    v9 = v16;
    do
    {
      if ( !v12 )
        break;
      if ( !*v13 )
        break;
      *v9++ = *v13++;
      --v12;
      --v8;
    }
    while ( v8 );
  }
  LODWORD(nLengthNeeded) = 0;
  v10 = v9 - 1;
  if ( v8 )
    v10 = v9;
  ProcessInformation[0] = 0;
  *v10 = 0;
  memset(&ProcessInformation[1], 0, 32);
  if ( NtQueryInformationProcess(
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         ProcessBasicInformation,
         ProcessInformation,
         0x30u,
         (PULONG)&nLengthNeeded) )
  {
    v11 = -1;
  }
  else
  {
    v11 = *(_DWORD *)(*((_QWORD *)&ProcessInformation[0] + 1) + 704LL);
  }
  StringCchPrintfW(a2, 0x104u, L"%s%s%d", a1, v16, v11, nLengthNeeded);
}

```

## disassembly

```asm
0x18000f900  mov     [rsp-8+arg_10], rsi
0x18000f905  push    rbp
0x18000f906  push    rdi
0x18000f907  push    r14
0x18000f909  lea     rbp, [rsp-3A0h]
0x18000f911  sub     rsp, 4A0h
0x18000f918  mov     rax, cs:__security_cookie
0x18000f91f  xor     rax, rsp
0x18000f922  mov     [rbp+3B0h+var_20], rax
0x18000f929  xor     r14d, r14d
0x18000f92c  mov     rsi, rdx
0x18000f92f  mov     [rsp+4B0h+var_440], r14w
0x18000f935  mov     rdi, rcx
0x18000f938  mov     dword ptr [rsp+4B0h+nLengthNeeded], r14d
0x18000f93d  call    cs:__imp_GetCurrentThreadId
0x18000f943  mov     ecx, eax; dwThreadId
0x18000f945  call    cs:__imp_GetThreadDesktop
0x18000f94b  test    rax, rax
0x18000f94e  jz      loc_18000FA5D
0x18000f954  lea     rcx, [rsp+4B0h+nLengthNeeded]
0x18000f959  mov     r9d, 208h; nLength
0x18000f95f  mov     [rsp+4B0h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x18000f964  lea     r8, [rbp+3B0h+pvInfo]; pvInfo
0x18000f96b  mov     rcx, rax; hObj
0x18000f96e  lea     edx, [r14+2]; nIndex
0x18000f972  call    cs:__imp_GetUserObjectInformationW
0x18000f978  test    eax, eax
0x18000f97a  jz      loc_18000FA5D
0x18000f980  mov     eax, 7FFFFFFEh
0x18000f985  lea     rcx, [rbp+3B0h+pvInfo]
0x18000f98c  mov     r8d, 104h
0x18000f992  lea     rdx, [rsp+4B0h+var_440]
0x18000f997  test    rax, rax
0x18000f99a  jz      short loc_18000F9BB
0x18000f99c  movzx   r9d, word ptr [rcx]
0x18000f9a0  test    r9w, r9w
0x18000f9a4  jz      short loc_18000F9BB
0x18000f9a6  mov     [rdx], r9w
0x18000f9aa  add     rcx, 2
0x18000f9ae  add     rdx, 2
0x18000f9b2  dec     rax
0x18000f9b5  sub     r8, 1
0x18000f9b9  jnz     short loc_18000F997
0x18000f9bb  xorps   xmm0, xmm0
0x18000f9be  mov     dword ptr [rsp+4B0h+nLengthNeeded], r14d
0x18000f9c3  test    r8, r8
0x18000f9c6  lea     rcx, [rdx-2]
0x18000f9ca  lea     rax, [rsp+4B0h+nLengthNeeded]
0x18000f9cf  mov     r9d, 30h ; '0'; ProcessInformationLength
0x18000f9d5  cmovnz  rcx, rdx
0x18000f9d9  mov     [rsp+4B0h+lpnLengthNeeded], rax; ReturnLength
0x18000f9de  lea     r8, [rsp+4B0h+ProcessInformation]; ProcessInformation
0x18000f9e3  xor     edx, edx; ProcessInformationClass
0x18000f9e5  movups  [rsp+4B0h+ProcessInformation], xmm0
0x18000f9ea  mov     [rcx], r14w
0x18000f9ee  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000f9f2  movups  [rsp+4B0h+var_468], xmm0
0x18000f9f7  movups  [rsp+4B0h+var_458], xmm0
0x18000f9fc  call    cs:__imp_NtQueryInformationProcess
0x18000fa02  test    eax, eax
0x18000fa04  jnz     loc_18000FAA5
0x18000fa0a  mov     rax, qword ptr [rsp+4B0h+ProcessInformation+8]
0x18000fa0f  mov     ecx, [rax+2C0h]
0x18000fa15  mov     [rsp+4B0h+var_488], ecx
0x18000fa19  lea     rax, [rsp+4B0h+var_440]
0x18000fa1e  mov     rcx, rsi; unsigned __int16 *
0x18000fa21  mov     [rsp+4B0h+lpnLengthNeeded], rax
0x18000fa26  mov     r9, rdi
0x18000fa29  lea     r8, aSSD; "%s%s%d"
0x18000fa30  mov     edx, 104h; unsigned __int64
0x18000fa35  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fa3a  mov     rcx, [rbp+3B0h+var_20]
0x18000fa41  xor     rcx, rsp; StackCookie
0x18000fa44  call    __security_check_cookie
0x18000fa49  mov     rsi, [rsp+4B0h+arg_10]
0x18000fa51  add     rsp, 4A0h
0x18000fa58  pop     r14
0x18000fa5a  pop     rdi
0x18000fa5b  pop     rbp
0x18000fa5c  retn
0x18000fa5d  mov     eax, 7FFFFFFEh
0x18000fa62  lea     rcx, lParam
0x18000fa69  mov     r8d, 104h
0x18000fa6f  lea     rdx, [rsp+4B0h+var_440]
0x18000fa74  test    rax, rax
0x18000fa77  jz      loc_18000F9BB
0x18000fa7d  movzx   r9d, word ptr [rcx]
0x18000fa81  test    r9w, r9w
0x18000fa85  jz      loc_18000F9BB
0x18000fa8b  mov     [rdx], r9w
0x18000fa8f  add     rcx, 2
0x18000fa93  add     rdx, 2
0x18000fa97  dec     rax
0x18000fa9a  sub     r8, 1
0x18000fa9e  jnz     short loc_18000FA74
0x18000faa0  jmp     loc_18000F9BB
0x18000faa5  or      ecx, 0FFFFFFFFh
0x18000faa8  jmp     loc_18000FA15
```
