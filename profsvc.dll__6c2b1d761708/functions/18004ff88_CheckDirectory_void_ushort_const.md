# CheckDirectory(void *,ushort const *)

- ea: `0x18004ff88`
- end: `0x180050098`
- name: `?CheckDirectory@@YAJPEAXPEBG@Z`
- size: `272`
- prototype: `__int64 __fastcall(void *, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800054cc`

## callees

- `0x180005dd0`
- `0x180007b58`
- `0x180030ad0`
- `0x180032e94`
- `0x180035860`
- `0x18003bc70`
- `0x18004ff88`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180050000`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180050000`

## string_xrefs

- `0x18004ffca`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18005001c`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18005005b`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180050015`: `Failed to get attributes of the directory <%ls>.`
- `0x180050042`: `Directory <%ls> is not a directory!`

## pseudocode

```c
__int64 __fastcall CheckDirectory(void *a1, char *a2)
{
  int v3; // eax
  unsigned int LastErrorMsg; // ebx
  int v6; // [rsp+20h] [rbp-58h]
  HANDLE v7; // [rsp+30h] [rbp-48h] BYREF
  char v8; // [rsp+38h] [rbp-40h]
  _OWORD FileInformation[2]; // [rsp+40h] [rbp-38h] BYREF
  int v10; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v7 = 0;
  v8 = 0;
  v3 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v7, a1);
  LastErrorMsg = v3;
  if ( v3 >= 0 )
  {
    v10 = 0;
    memset(FileInformation, 0, sizeof(FileInformation));
    if ( GetFileAttributesExW((LPCWSTR)a2, GetFileExInfoStandard, FileInformation) )
    {
      if ( (FileInformation[0] & 0x10) != 0 )
      {
        LastErrorMsg = 0;
      }
      else
      {
        LastErrorMsg = -2147024893;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x4FC,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)0x80070003LL,
          (int)"Directory <%ls> is not a directory!",
          a2);
      }
    }
    else
    {
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x4F9,
                       (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                       "Failed to get attributes of the directory <%ls>.",
                       a2);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)(unsigned int)v3,
      v6);
  }
  CAutoImpersonate::ResetImpersonation(&v7);
  return LastErrorMsg;
}

```

## disassembly

```asm
0x18004ff88  mov     [rsp+arg_10], rbx
0x18004ff8d  push    rdi
0x18004ff8e  sub     rsp, 70h
0x18004ff92  mov     rax, cs:__security_cookie
0x18004ff99  xor     rax, rsp
0x18004ff9c  mov     [rsp+78h+var_10], rax
0x18004ffa1  mov     rdi, rdx
0x18004ffa4  mov     [rsp+78h+var_48], 0
0x18004ffad  mov     rdx, rcx; void *
0x18004ffb0  mov     [rsp+78h+var_40], 0
0x18004ffb5  lea     rcx, [rsp+78h+var_48]; this
0x18004ffba  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x18004ffbf  mov     ebx, eax
0x18004ffc1  test    eax, eax
0x18004ffc3  jns     short loc_18004FFE3
0x18004ffc5  mov     rcx, [rsp+78h]; this
0x18004ffca  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004ffd1  mov     r9d, eax; char *
0x18004ffd4  mov     edx, 4F4h; void *
0x18004ffd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ffde  jmp     loc_180050070
0x18004ffe3  xorps   xmm0, xmm0
0x18004ffe6  lea     r8, [rsp+78h+FileInformation]; lpFileInformation
0x18004ffeb  xor     eax, eax
0x18004ffed  xor     edx, edx; fInfoLevelId
0x18004ffef  mov     rcx, rdi; lpFileName
0x18004fff2  mov     [rsp+78h+var_18], eax
0x18004fff6  movups  [rsp+78h+FileInformation], xmm0
0x18004fffb  movups  [rsp+78h+var_28], xmm0
0x180050000  call    cs:__imp_GetFileAttributesExW
0x180050007  nop     dword ptr [rax+rax+00h]
0x18005000c  test    eax, eax
0x18005000e  jnz     short loc_180050036
0x180050010  mov     rcx, [rsp+78h]; this
0x180050015  lea     r9, aFailedToGetAtt; "Failed to get attributes of the directo"...
0x18005001c  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180050023  mov     [rsp+78h+var_58], rdi; char *
0x180050028  mov     edx, 4F9h; void *
0x18005002d  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180050032  mov     ebx, eax
0x180050034  jmp     short loc_180050070
0x180050036  test    byte ptr [rsp+78h+FileInformation], 10h
0x18005003b  jnz     short loc_18005006E
0x18005003d  mov     rcx, [rsp+78h]; this
0x180050042  lea     rax, aDirectoryLsIsN; "Directory <%ls> is not a directory!"
0x180050049  mov     ebx, 80070003h
0x18005004e  mov     [rsp+78h+var_50], rdi; char *
0x180050053  mov     r9d, ebx; char *
0x180050056  mov     [rsp+78h+var_58], rax; int
0x18005005b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180050062  mov     edx, 4FCh; void *
0x180050067  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005006c  jmp     short loc_180050070
0x18005006e  xor     ebx, ebx
0x180050070  lea     rcx, [rsp+78h+var_48]; this
0x180050075  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18005007a  mov     eax, ebx
0x18005007c  mov     rcx, [rsp+78h+var_10]
0x180050081  xor     rcx, rsp; StackCookie
0x180050084  call    __security_check_cookie
0x180050089  mov     rbx, [rsp+78h+arg_10]
0x180050091  add     rsp, 70h
0x180050095  pop     rdi
0x180050096  retn
```
