# NtfsFileSystem::ValidateSecurity(ushort const *,void * const,void * const)

- ea: `0x1400b334c`
- end: `0x1400b3630`
- name: `?ValidateSecurity@NtfsFileSystem@@AEAAPEAVFrsStatus@@PEBGQEAX1@Z`
- size: `740`
- prototype: `struct FrsStatus *(NtfsFileSystem *__hidden this, const unsigned __int16 *, void *const, void *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b0b20`

## callees

- `0x1400ae800`
- `0x1400b334c`
- `0x1400c1460`
- `0x1400c1e90`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400b3586`
- `KERNEL32!GetLastError` at `0x1400b3586`
- `KERNEL32!GetCurrentThreadId` at `0x1400b3410`
- `KERNEL32!GetCurrentThreadId` at `0x1400b347f`
- `KERNEL32!GetCurrentThreadId` at `0x1400b3532`
- `KERNEL32!GetCurrentThreadId` at `0x1400b3578`
- `KERNEL32!GetCurrentThreadId` at `0x1400b35bf`
- `KERNEL32!GetCurrentThreadId` at `0x1400b3410`
- `KERNEL32!GetCurrentThreadId` at `0x1400b347f`
- `KERNEL32!GetCurrentThreadId` at `0x1400b3532`
- `KERNEL32!GetCurrentThreadId` at `0x1400b3578`
- `KERNEL32!GetCurrentThreadId` at `0x1400b35bf`
- `ADVAPI32!GetAce` at `0x1400b34dd`
- `ADVAPI32!GetAce` at `0x1400b34dd`
- `ADVAPI32!EqualSid` at `0x1400b3458`
- `ADVAPI32!EqualSid` at `0x1400b346f`
- `ADVAPI32!EqualSid` at `0x1400b3508`
- `ADVAPI32!EqualSid` at `0x1400b3522`
- `ADVAPI32!EqualSid` at `0x1400b3458`
- `ADVAPI32!EqualSid` at `0x1400b346f`
- `ADVAPI32!EqualSid` at `0x1400b3508`
- `ADVAPI32!EqualSid` at `0x1400b3522`
- `ADVAPI32!GetSecurityInfo` at `0x1400b3402`
- `ADVAPI32!GetSecurityInfo` at `0x1400b3402`

## string_xrefs

- `0x1400b33c1`: `NtfsFileSystem::ValidateSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct FrsStatus *__fastcall NtfsFileSystem::ValidateSecurity(
        NtfsFileSystem *this,
        const unsigned __int16 *a2,
        void *const a3,
        void *const a4)
{
  __int64 v6; // rdi
  struct FrsStatus *v7; // rbx
  DWORD SecurityInfo; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  DWORD v11; // eax
  __int64 v12; // rcx
  DWORD v13; // esi
  char *v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rax
  DWORD v17; // ebx
  DWORD LastError; // eax
  __int64 v19; // rcx
  DWORD v20; // eax
  __int64 v21; // rcx
  DWORD ppSecurityDescriptor; // [rsp+38h] [rbp-48h]
  PACL pAcl; // [rsp+50h] [rbp-30h] BYREF
  LPVOID pAce; // [rsp+58h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR v26; // [rsp+60h] [rbp-20h] BYREF
  void **v27; // [rsp+68h] [rbp-18h] BYREF
  HANDLE handle; // [rsp+70h] [rbp-10h]
  int v29; // [rsp+78h] [rbp-8h]
  PSID ppsidOwner; // [rsp+B0h] [rbp+30h] BYREF

  v27 = &FileHandle::`vftable';
  handle = (HANDLE)-1LL;
  v6 = 0;
  v29 = 0;
  ppsidOwner = 0;
  pAcl = 0;
  v26 = 0;
  v7 = FileHandle::OpenPath((FileHandle *)&v27, a2, 0x20000u, 0, 7u, 0x204000u);
  if ( !v7 )
  {
    SecurityInfo = GetSecurityInfo(handle, SE_FILE_OBJECT, 5u, &ppsidOwner, 0, &pAcl, 0, &v26);
    CurrentThreadId = GetCurrentThreadId();
    v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v10,
                               SecurityInfo,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
                               "NtfsFileSystem::ValidateSecurity",
                               1871,
                               CurrentThreadId,
                               0);
    if ( !v7 && (!ppsidOwner || !EqualSid(ppsidOwner, a4) && !EqualSid(ppsidOwner, a3)) )
    {
      v11 = GetCurrentThreadId();
      v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v12,
                                 9058,
                                 0,
                                 3,
                                 "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
                                 "NtfsFileSystem::ValidateSecurity",
                                 1875,
                                 v11,
                                 0);
    }
  }
  pAce = 0;
  v13 = 0;
  while ( !v7 )
  {
    if ( v13 >= pAcl->AceCount )
      goto LABEL_19;
    if ( !GetAce(pAcl, v13, &pAce) )
    {
      v17 = GetCurrentThreadId();
      LastError = GetLastError();
      v16 = FrsStatusList::PushNewError(
              v19,
              LastError,
              0,
              1,
              "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
              "NtfsFileSystem::ValidateSecurity",
              1892,
              v17,
              0);
      goto LABEL_14;
    }
    if ( !*(_BYTE *)pAce )
    {
      v14 = (char *)pAce + 8;
      if ( !EqualSid((char *)pAce + 8, a4) && !EqualSid(v14, a3) )
      {
        ppSecurityDescriptor = GetCurrentThreadId();
        v16 = FrsStatusList::PushNewError(
                v15,
                9058,
                0,
                3,
                "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
                "NtfsFileSystem::ValidateSecurity",
                1887,
                ppSecurityDescriptor,
                0);
LABEL_14:
        v7 = (struct FrsStatus *)v16;
      }
    }
    ++v13;
  }
  v20 = GetCurrentThreadId();
  v6 = FrsStatusList::PushNewError(
         v21,
         *((unsigned int *)v7 + 1),
         *((unsigned int *)v7 + 2),
         *(unsigned int *)v7,
         "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
         "NtfsFileSystem::ValidateSecurity",
         1897,
         v20,
         v7);
LABEL_19:
  scoped_any<void *,close_fun<void * (*)(void *),&void * LocalFree(void *)>,null_t,0>::~scoped_any<void *,close_fun<void * (*)(void *),&void * LocalFree(void *)>,null_t,0>(&v26);
  FileHandle::~FileHandle((FileHandle *)&v27);
  return (struct FrsStatus *)v6;
}

```

## disassembly

```asm
0x1400b334c  mov     rax, rsp
0x1400b334f  mov     [rax+10h], rbx
0x1400b3353  mov     [rax+18h], rsi
0x1400b3357  mov     [rax+20h], rdi
0x1400b335b  mov     [rax+8], rcx
0x1400b335f  push    rbp
0x1400b3360  push    r12
0x1400b3362  push    r13
0x1400b3364  push    r14
0x1400b3366  push    r15
0x1400b3368  mov     rbp, rsp
0x1400b336b  sub     rsp, 80h
0x1400b3372  mov     r12, r9
0x1400b3375  mov     r15, r8
0x1400b3378  lea     rax, ??_7FileHandle@@6B@; const FileHandle::`vftable'
0x1400b337f  mov     [rbp+var_18], rax
0x1400b3383  or      [rbp+handle], 0FFFFFFFFFFFFFFFFh
0x1400b3388  xor     edi, edi
0x1400b338a  mov     [rbp+var_8], edi
0x1400b338d  mov     [rbp+ppsidOwner], rdi
0x1400b3391  mov     [rbp+pAcl], rdi
0x1400b3395  mov     [rbp+var_20], rdi
0x1400b3399  mov     dword ptr [rsp+80h+ppDacl], 204000h; unsigned int
0x1400b33a1  mov     dword ptr [rsp+80h+ppsidGroup], 7; unsigned int
0x1400b33a9  xor     r9d, r9d; int
0x1400b33ac  mov     r8d, 20000h; unsigned int
0x1400b33b2  lea     rcx, [rbp+var_18]; this
0x1400b33b6  call    ?OpenPath@FileHandle@@UEAAPEAVFrsStatus@@PEBGKHKK@Z; FileHandle::OpenPath(ushort const *,ulong,int,ulong,ulong)
0x1400b33bb  mov     rbx, rax
0x1400b33be  lea     esi, [rdi+1]
0x1400b33c1  lea     r13, aNtfsfilesystem_4; "NtfsFileSystem::ValidateSecurity"
0x1400b33c8  lea     r14, aBaseFsRemotefs_106; "base\\fs\\remotefs\\frs\\src\\fs\\ntfsf"...
0x1400b33cf  test    rax, rax
0x1400b33d2  jnz     loc_1400B34BC
0x1400b33d8  lea     rax, [rbp+var_20]
0x1400b33dc  mov     [rsp+80h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1400b33e1  mov     [rsp+80h+ppSacl], rdi; ppSacl
0x1400b33e6  lea     rax, [rbp+pAcl]
0x1400b33ea  mov     [rsp+80h+ppDacl], rax; ppDacl
0x1400b33ef  mov     [rsp+80h+ppsidGroup], rdi; ppsidGroup
0x1400b33f4  lea     r9, [rbp+ppsidOwner]; ppsidOwner
0x1400b33f8  lea     r8d, [rdi+5]; SecurityInfo
0x1400b33fc  mov     edx, esi; ObjectType
0x1400b33fe  mov     rcx, [rbp+handle]; handle
0x1400b3402  call    cs:__imp_GetSecurityInfo
0x1400b3409  nop     dword ptr [rax+rax+00h]
0x1400b340e  mov     ebx, eax
0x1400b3410  call    cs:__imp_GetCurrentThreadId
0x1400b3417  nop     dword ptr [rax+rax+00h]
0x1400b341c  mov     [rsp+80h+var_40], rdi
0x1400b3421  mov     dword ptr [rsp+80h+ppSecurityDescriptor], eax
0x1400b3425  mov     dword ptr [rsp+80h+ppSacl], 74Fh
0x1400b342d  mov     [rsp+80h+ppDacl], r13
0x1400b3432  mov     [rsp+80h+ppsidGroup], r14
0x1400b3437  mov     r9d, esi
0x1400b343a  xor     r8d, r8d
0x1400b343d  mov     edx, ebx
0x1400b343f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400b3444  mov     rbx, rax
0x1400b3447  test    rax, rax
0x1400b344a  jnz     short loc_1400B34BC
0x1400b344c  mov     rcx, [rbp+ppsidOwner]; pSid1
0x1400b3450  test    rcx, rcx
0x1400b3453  jz      short loc_1400B347F
0x1400b3455  mov     rdx, r12; pSid2
0x1400b3458  call    cs:__imp_EqualSid
0x1400b345f  nop     dword ptr [rax+rax+00h]
0x1400b3464  test    eax, eax
0x1400b3466  jnz     short loc_1400B34BC
0x1400b3468  mov     rdx, r15; pSid2
0x1400b346b  mov     rcx, [rbp+ppsidOwner]; pSid1
0x1400b346f  call    cs:__imp_EqualSid
0x1400b3476  nop     dword ptr [rax+rax+00h]
0x1400b347b  test    eax, eax
0x1400b347d  jnz     short loc_1400B34BC
0x1400b347f  call    cs:__imp_GetCurrentThreadId
0x1400b3486  nop     dword ptr [rax+rax+00h]
0x1400b348b  mov     [rsp+80h+var_40], rdi
0x1400b3490  mov     dword ptr [rsp+80h+ppSecurityDescriptor], eax
0x1400b3494  mov     dword ptr [rsp+80h+ppSacl], 753h
0x1400b349c  mov     [rsp+80h+ppDacl], r13
0x1400b34a1  mov     [rsp+80h+ppsidGroup], r14
0x1400b34a6  mov     r9d, 3
0x1400b34ac  xor     r8d, r8d
0x1400b34af  mov     edx, 2362h
0x1400b34b4  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400b34b9  mov     rbx, rax
0x1400b34bc  mov     [rbp+pAce], rdi
0x1400b34c0  mov     esi, edi
0x1400b34c2  jmp     loc_1400B35B6
0x1400b34c7  mov     rcx, [rbp+pAcl]; pAcl
0x1400b34cb  movzx   eax, word ptr [rcx+4]
0x1400b34cf  cmp     esi, eax
0x1400b34d1  jnb     loc_1400B35F8
0x1400b34d7  lea     r8, [rbp+pAce]; pAce
0x1400b34db  mov     edx, esi; dwAceIndex
0x1400b34dd  call    cs:__imp_GetAce
0x1400b34e4  nop     dword ptr [rax+rax+00h]
0x1400b34e9  test    eax, eax
0x1400b34eb  jz      loc_1400B3578
0x1400b34f1  mov     rax, [rbp+pAce]
0x1400b34f5  cmp     [rax], dil
0x1400b34f8  jnz     loc_1400B35B4
0x1400b34fe  lea     r14, [rax+8]
0x1400b3502  mov     rdx, r12; pSid2
0x1400b3505  mov     rcx, r14; pSid1
0x1400b3508  call    cs:__imp_EqualSid
0x1400b350f  nop     dword ptr [rax+rax+00h]
0x1400b3514  test    eax, eax
0x1400b3516  jnz     loc_1400B35AD
0x1400b351c  mov     rdx, r15; pSid2
0x1400b351f  mov     rcx, r14; pSid1
0x1400b3522  call    cs:__imp_EqualSid
0x1400b3529  nop     dword ptr [rax+rax+00h]
0x1400b352e  test    eax, eax
0x1400b3530  jnz     short loc_1400B35AD
0x1400b3532  call    cs:__imp_GetCurrentThreadId
0x1400b3539  nop     dword ptr [rax+rax+00h]
0x1400b353e  mov     [rsp+80h+var_40], rdi
0x1400b3543  mov     dword ptr [rsp+80h+ppSecurityDescriptor], eax
0x1400b3547  mov     dword ptr [rsp+80h+ppSacl], 75Fh
0x1400b354f  lea     r14, aBaseFsRemotefs_106; "base\\fs\\remotefs\\frs\\src\\fs\\ntfsf"...
0x1400b3556  mov     r9d, 3
0x1400b355c  mov     edx, 2362h
0x1400b3561  mov     [rsp+80h+ppDacl], r13
0x1400b3566  xor     r8d, r8d
0x1400b3569  mov     [rsp+80h+ppsidGroup], r14
0x1400b356e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400b3573  mov     rbx, rax
0x1400b3576  jmp     short loc_1400B35B4
0x1400b3578  call    cs:__imp_GetCurrentThreadId
0x1400b357f  nop     dword ptr [rax+rax+00h]
0x1400b3584  mov     ebx, eax
0x1400b3586  call    cs:__imp_GetLastError
0x1400b358d  nop     dword ptr [rax+rax+00h]
0x1400b3592  mov     [rsp+80h+var_40], rdi
0x1400b3597  mov     dword ptr [rsp+80h+ppSecurityDescriptor], ebx
0x1400b359b  mov     dword ptr [rsp+80h+ppSacl], 764h
0x1400b35a3  mov     r9d, 1
0x1400b35a9  mov     edx, eax
0x1400b35ab  jmp     short loc_1400B3561
0x1400b35ad  lea     r14, aBaseFsRemotefs_106; "base\\fs\\remotefs\\frs\\src\\fs\\ntfsf"...
0x1400b35b4  inc     esi
0x1400b35b6  test    rbx, rbx
0x1400b35b9  jz      loc_1400B34C7
0x1400b35bf  call    cs:__imp_GetCurrentThreadId
0x1400b35c6  nop     dword ptr [rax+rax+00h]
0x1400b35cb  mov     [rsp+80h+var_40], rbx
0x1400b35d0  mov     dword ptr [rsp+80h+ppSecurityDescriptor], eax
0x1400b35d4  mov     dword ptr [rsp+80h+ppSacl], 769h
0x1400b35dc  mov     [rsp+80h+ppDacl], r13
0x1400b35e1  mov     [rsp+80h+ppsidGroup], r14
0x1400b35e6  mov     r9d, [rbx]
0x1400b35e9  mov     r8d, [rbx+8]
0x1400b35ed  mov     edx, [rbx+4]
0x1400b35f0  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400b35f5  mov     rdi, rax
0x1400b35f8  lea     rcx, [rbp+var_20]
0x1400b35fc  call    ??1?$scoped_any@PEAXU?$close_fun@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<void *,close_fun<void * (*)(void *),&LocalFree(void *)>,null_t,0>::~scoped_any<void *,close_fun<void * (*)(void *),&LocalFree(void *)>,null_t,0>(void)
0x1400b3601  nop
0x1400b3602  lea     rcx, [rbp+var_18]; this
0x1400b3606  call    ??1FileHandle@@UEAA@XZ; FileHandle::~FileHandle(void)
0x1400b360b  mov     rax, rdi
0x1400b360e  lea     r11, [rsp+80h+var_s0]
0x1400b3616  mov     rbx, [r11+38h]
0x1400b361a  mov     rsi, [r11+40h]
0x1400b361e  mov     rdi, [r11+48h]
0x1400b3622  mov     rsp, r11
0x1400b3625  pop     r15
0x1400b3627  pop     r14
0x1400b3629  pop     r13
0x1400b362b  pop     r12
0x1400b362d  pop     rbp
0x1400b362e  retn
```
