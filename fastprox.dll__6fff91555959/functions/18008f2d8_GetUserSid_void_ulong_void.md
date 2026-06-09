# GetUserSid(void *,ulong *,void *)

- ea: `0x18008f2d8`
- end: `0x18008f42e`
- name: `?GetUserSid@@YAJPEAXPEAK0@Z`
- size: `342`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int *, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008f440`
- `0x18008f550`

## callees

- `0x180037120`
- `0x18006fa66`
- `0x18008f2d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f333`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008f386`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008f386`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008f325`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008f379`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008f325`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008f379`
- `wbemcomn!GetMemLogObject` at `0x18008f3d1`
- `wbemcomn!GetMemLogObject` at `0x18008f3d1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f3dc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f3dc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18008f3a1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18008f3a1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008f351`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008f351`

## pseudocode

```c
__int64 __fastcall GetUserSid(HANDLE TokenHandle, unsigned int *a2, void *a3)
{
  int v6; // ebx
  PSID *v7; // rsi
  DWORD LengthSid; // eax
  CMemoryLog *MemLogObject; // rax
  DWORD TokenInformationLength; // [rsp+50h] [rbp+8h] BYREF

  if ( !TokenHandle )
  {
    v6 = -2147024890;
    goto LABEL_18;
  }
  if ( a2 )
  {
    TokenInformationLength = 0;
    v6 = -2147217407;
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
      goto LABEL_18;
    if ( a3 )
    {
      if ( *a2 < TokenInformationLength )
      {
        v6 = -2147217348;
      }
      else
      {
        v7 = (PSID *)CWin32DefaultArena::WbemMemAlloc(TokenInformationLength);
        if ( v7 )
        {
          if ( GetTokenInformation(TokenHandle, TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
          {
            LengthSid = GetLengthSid(*v7);
            *a2 = LengthSid;
            memcpy_0(a3, *v7, LengthSid);
            v6 = 0;
          }
          CWin32DefaultArena::WbemMemFree(v7);
        }
        else
        {
          v6 = -2147217402;
        }
      }
    }
    else
    {
      v6 = 0;
      *a2 = TokenInformationLength;
    }
  }
  else
  {
    v6 = -2147217400;
  }
  if ( v6 < 0 )
  {
LABEL_18:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v6);
  }
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a3414c62bfc43c14b650084b64f85981_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18008f2d8  mov     rax, rsp
0x18008f2db  mov     [rax+10h], rbx
0x18008f2df  mov     [rax+18h], rbp
0x18008f2e3  push    rsi
0x18008f2e4  push    rdi
0x18008f2e5  push    r14
0x18008f2e7  sub     rsp, 30h
0x18008f2eb  mov     r14, r8
0x18008f2ee  mov     rdi, rdx
0x18008f2f1  mov     rbp, rcx
0x18008f2f4  test    rcx, rcx
0x18008f2f7  jz      loc_18008F3CC
0x18008f2fd  test    rdx, rdx
0x18008f300  jz      loc_18008F3C1
0x18008f306  xor     r9d, r9d; TokenInformationLength
0x18008f309  mov     dword ptr [rax+8], 0
0x18008f310  lea     rax, [rax+8]
0x18008f314  xor     r8d, r8d; TokenInformation
0x18008f317  mov     ebx, 80041001h
0x18008f31c  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18008f321  lea     edx, [r9+1]; TokenInformationClass
0x18008f325  call    cs:__imp_GetTokenInformation
0x18008f32b  test    eax, eax
0x18008f32d  jnz     loc_18008F3D1
0x18008f333  call    cs:__imp_GetLastError
0x18008f339  cmp     eax, 7Ah ; 'z'
0x18008f33c  jnz     loc_18008F3D1
0x18008f342  test    r14, r14
0x18008f345  jz      short loc_18008F3B7
0x18008f347  mov     eax, [rsp+48h+TokenInformationLength]
0x18008f34b  cmp     [rdi], eax
0x18008f34d  jb      short loc_18008F3B0
0x18008f34f  mov     ecx, eax
0x18008f351  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18008f357  mov     rsi, rax
0x18008f35a  test    rax, rax
0x18008f35d  jz      short loc_18008F3A9
0x18008f35f  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18008f364  lea     rax, [rsp+48h+TokenInformationLength]
0x18008f369  mov     r8, rsi; TokenInformation
0x18008f36c  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18008f371  mov     edx, 1; TokenInformationClass
0x18008f376  mov     rcx, rbp; TokenHandle
0x18008f379  call    cs:__imp_GetTokenInformation
0x18008f37f  test    eax, eax
0x18008f381  jz      short loc_18008F39E
0x18008f383  mov     rcx, [rsi]; pSid
0x18008f386  call    cs:__imp_GetLengthSid
0x18008f38c  mov     [rdi], eax
0x18008f38e  mov     rcx, r14; void *
0x18008f391  mov     rdx, [rsi]; Src
0x18008f394  mov     r8d, eax; Size
0x18008f397  call    memcpy_0
0x18008f39c  xor     ebx, ebx
0x18008f39e  mov     rcx, rsi
0x18008f3a1  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18008f3a7  jmp     short loc_18008F3C6
0x18008f3a9  mov     ebx, 80041006h
0x18008f3ae  jmp     short loc_18008F3C6
0x18008f3b0  mov     ebx, 8004103Ch
0x18008f3b5  jmp     short loc_18008F3C6
0x18008f3b7  mov     eax, [rsp+48h+TokenInformationLength]
0x18008f3bb  xor     ebx, ebx
0x18008f3bd  mov     [rdi], eax
0x18008f3bf  jmp     short loc_18008F3C6
0x18008f3c1  mov     ebx, 80041008h
0x18008f3c6  test    ebx, ebx
0x18008f3c8  jns     short loc_18008F3E2
0x18008f3ca  jmp     short loc_18008F3D1
0x18008f3cc  mov     ebx, 80070006h
0x18008f3d1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008f3d7  mov     rcx, rax
0x18008f3da  mov     edx, ebx
0x18008f3dc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008f3e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f3e9  lea     rax, WPP_GLOBAL_Control
0x18008f3f0  cmp     rcx, rax
0x18008f3f3  jz      short loc_18008F419
0x18008f3f5  test    byte ptr [rcx+1Ch], 1
0x18008f3f9  jz      short loc_18008F419
0x18008f3fb  cmp     byte ptr [rcx+19h], 2
0x18008f3ff  jb      short loc_18008F419
0x18008f401  mov     rcx, [rcx+10h]
0x18008f405  lea     r8, WPP_a3414c62bfc43c14b650084b64f85981_Traceguids
0x18008f40c  mov     edx, 0Ch
0x18008f411  mov     r9d, ebx
0x18008f414  call    WPP_SF_d
0x18008f419  mov     rbp, [rsp+48h+arg_10]
0x18008f41e  mov     eax, ebx
0x18008f420  mov     rbx, [rsp+48h+arg_8]
0x18008f425  add     rsp, 30h
0x18008f429  pop     r14
0x18008f42b  pop     rdi
0x18008f42c  pop     rsi
0x18008f42d  retn
```
