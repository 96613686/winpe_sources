# NtfsFileSystem::InitializeSids(void * &,void * &)

- ea: `0x1400aff78`
- end: `0x1400b00f9`
- name: `?InitializeSids@NtfsFileSystem@@AEAAPEAVFrsStatus@@AEAPEAX0@Z`
- size: `385`
- prototype: `struct FrsStatus *(NtfsFileSystem *__hidden this, void **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400b0b20`

## callees

- `0x1400036a0`
- `0x1400aff78`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400b0036`
- `KERNEL32!GetLastError` at `0x1400b0036`
- `KERNEL32!GetCurrentThreadId` at `0x1400b0028`
- `KERNEL32!GetCurrentThreadId` at `0x1400b009a`
- `KERNEL32!GetCurrentThreadId` at `0x1400b0028`
- `KERNEL32!GetCurrentThreadId` at `0x1400b009a`
- `ADVAPI32!FreeSid` at `0x1400b0086`
- `ADVAPI32!FreeSid` at `0x1400b0086`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400affd6`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400b0014`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400affd6`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400b0014`

## string_xrefs

- `0x1400b0047`: `NtfsFileSystem::InitializeSids`

## pseudocode

```c
struct FrsStatus *__fastcall NtfsFileSystem::InitializeSids(NtfsFileSystem *this, void **pSid, void **a3)
{
  __int64 v3; // rdi
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  __int64 v8; // rcx
  unsigned int *v9; // rbx
  DWORD v10; // eax
  __int64 v11; // rcx
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-28h] BYREF

  v3 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, pSid)
    || !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, a3) )
  {
    CurrentThreadId = GetCurrentThreadId();
    LastError = GetLastError();
    v9 = (unsigned int *)FrsStatusList::PushNewError(
                           v8,
                           LastError,
                           0,
                           3,
                           "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
                           "NtfsFileSystem::InitializeSids",
                           1741,
                           CurrentThreadId,
                           0);
    if ( *pSid )
    {
      FreeSid(*pSid);
      *pSid = 0;
    }
    if ( v9 )
    {
      v10 = GetCurrentThreadId();
      return (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v11,
                                   v9[1],
                                   v9[2],
                                   *v9,
                                   "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
                                   "NtfsFileSystem::InitializeSids",
                                   1747,
                                   v10,
                                   v9);
    }
  }
  return (struct FrsStatus *)v3;
}

```

## disassembly

```asm
0x1400aff78  mov     r11, rsp
0x1400aff7b  mov     [r11+8], rbx
0x1400aff7f  mov     [r11+20h], rbp
0x1400aff83  push    rsi
0x1400aff84  push    rdi
0x1400aff85  push    r14
0x1400aff87  sub     rsp, 70h
0x1400aff8b  mov     rax, cs:__security_cookie
0x1400aff92  xor     rax, rsp
0x1400aff95  mov     [rsp+88h+var_20], rax
0x1400aff9a  xor     edi, edi
0x1400aff9c  mov     [r11-38h], rdx
0x1400affa0  mov     [rsp+88h+nSubAuthority7], edi; nSubAuthority7
0x1400affa4  lea     rcx, [r11-28h]; pIdentifierAuthority
0x1400affa8  mov     [rsp+88h+nSubAuthority6], edi; nSubAuthority6
0x1400affac  mov     rbx, r8
0x1400affaf  mov     [rsp+88h+nSubAuthority5], edi; nSubAuthority5
0x1400affb3  mov     rsi, rdx
0x1400affb6  mov     [rsp+88h+nSubAuthority4], edi; nSubAuthority4
0x1400affba  lea     r8d, [rdi+12h]; nSubAuthority0
0x1400affbe  mov     [rsp+88h+nSubAuthority3], edi; nSubAuthority3
0x1400affc2  xor     r9d, r9d; nSubAuthority1
0x1400affc5  mov     dl, 1; nSubAuthorityCount
0x1400affc7  mov     [rsp+88h+nSubAuthority2], edi; nSubAuthority2
0x1400affcb  mov     dword ptr [rsp+88h+pIdentifierAuthority.Value], edi
0x1400affcf  mov     word ptr [rsp+88h+pIdentifierAuthority.Value+4], 500h
0x1400affd6  call    cs:__imp_AllocateAndInitializeSid
0x1400affdd  nop     dword ptr [rax+rax+00h]
0x1400affe2  test    eax, eax
0x1400affe4  jz      short loc_1400B0028
0x1400affe6  mov     [rsp+88h+pSid], rbx; pSid
0x1400affeb  lea     r8d, [rdi+20h]; nSubAuthority0
0x1400affef  mov     [rsp+88h+nSubAuthority7], edi; nSubAuthority7
0x1400afff3  lea     rcx, [rsp+88h+pIdentifierAuthority]; pIdentifierAuthority
0x1400afff8  mov     [rsp+88h+nSubAuthority6], edi; nSubAuthority6
0x1400afffc  mov     r9d, 220h; nSubAuthority1
0x1400b0002  mov     [rsp+88h+nSubAuthority5], edi; nSubAuthority5
0x1400b0006  mov     dl, 2; nSubAuthorityCount
0x1400b0008  mov     [rsp+88h+nSubAuthority4], edi; nSubAuthority4
0x1400b000c  mov     [rsp+88h+nSubAuthority3], edi; nSubAuthority3
0x1400b0010  mov     [rsp+88h+nSubAuthority2], edi; nSubAuthority2
0x1400b0014  call    cs:__imp_AllocateAndInitializeSid
0x1400b001b  nop     dword ptr [rax+rax+00h]
0x1400b0020  test    eax, eax
0x1400b0022  jnz     loc_1400B00D3
0x1400b0028  call    cs:__imp_GetCurrentThreadId
0x1400b002f  nop     dword ptr [rax+rax+00h]
0x1400b0034  mov     ebx, eax
0x1400b0036  call    cs:__imp_GetLastError
0x1400b003d  nop     dword ptr [rax+rax+00h]
0x1400b0042  mov     qword ptr [rsp+88h+nSubAuthority6], rdi
0x1400b0047  lea     rbp, aNtfsfilesystem_18; "NtfsFileSystem::InitializeSids"
0x1400b004e  mov     [rsp+88h+nSubAuthority5], ebx
0x1400b0052  lea     r14, aBaseFsRemotefs_106; "base\\fs\\remotefs\\frs\\src\\fs\\ntfsf"...
0x1400b0059  mov     [rsp+88h+nSubAuthority4], 6CDh
0x1400b0061  mov     r9d, 3
0x1400b0067  mov     qword ptr [rsp+88h+nSubAuthority3], rbp
0x1400b006c  xor     r8d, r8d
0x1400b006f  mov     edx, eax
0x1400b0071  mov     qword ptr [rsp+88h+nSubAuthority2], r14
0x1400b0076  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400b007b  mov     rbx, rax
0x1400b007e  cmp     [rsi], rdi
0x1400b0081  jz      short loc_1400B0095
0x1400b0083  mov     rcx, [rsi]; pSid
0x1400b0086  call    cs:__imp_FreeSid
0x1400b008d  nop     dword ptr [rax+rax+00h]
0x1400b0092  mov     [rsi], rdi
0x1400b0095  test    rbx, rbx
0x1400b0098  jz      short loc_1400B00D3
0x1400b009a  call    cs:__imp_GetCurrentThreadId
0x1400b00a1  nop     dword ptr [rax+rax+00h]
0x1400b00a6  mov     r9d, [rbx]
0x1400b00a9  mov     r8d, [rbx+8]
0x1400b00ad  mov     edx, [rbx+4]
0x1400b00b0  mov     qword ptr [rsp+88h+nSubAuthority6], rbx
0x1400b00b5  mov     [rsp+88h+nSubAuthority5], eax
0x1400b00b9  mov     [rsp+88h+nSubAuthority4], 6D3h
0x1400b00c1  mov     qword ptr [rsp+88h+nSubAuthority3], rbp
0x1400b00c6  mov     qword ptr [rsp+88h+nSubAuthority2], r14
0x1400b00cb  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400b00d0  mov     rdi, rax
0x1400b00d3  mov     rax, rdi
0x1400b00d6  mov     rcx, [rsp+88h+var_20]
0x1400b00db  xor     rcx, rsp; StackCookie
0x1400b00de  call    __security_check_cookie
0x1400b00e3  lea     r11, [rsp+88h+var_18]
0x1400b00e8  mov     rbx, [r11+20h]
0x1400b00ec  mov     rbp, [r11+38h]
0x1400b00f0  mov     rsp, r11
0x1400b00f3  pop     r14
0x1400b00f5  pop     rdi
0x1400b00f6  pop     rsi
0x1400b00f7  retn
```
