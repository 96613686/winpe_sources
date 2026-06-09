# CheckDirectory(void *,ushort const *)

- ea: `0x18004cc94`
- end: `0x18004cd9d`
- name: `?CheckDirectory@@YAJPEAXPEBG@Z`
- size: `265`
- prototype: `__int64 __fastcall(void *, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180007aa8`

## callees

- `0x180008200`
- `0x18000a320`
- `0x18002d2d8`
- `0x18002f8e0`
- `0x180032228`
- `0x18003a730`
- `0x18004cc94`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18004cd0c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18004cd0c`

## string_xrefs

- `0x18004ccd6`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18004cd22`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18004cd61`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18004cd1b`: `Failed to get attributes of the directory <%ls>.`
- `0x18004cd48`: `Directory <%ls> is not a directory!`

## pseudocode

```c
__int64 __fastcall CheckDirectory(void *a1, char *a2)
{
  int v3; // eax
  unsigned int LastErrorMsg; // ebx
  int v6; // [rsp+20h] [rbp-58h]
  __int64 v7; // [rsp+30h] [rbp-48h] BYREF
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
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v7);
  return LastErrorMsg;
}

```

## disassembly

```asm
0x18004cc94  mov     [rsp+arg_10], rbx
0x18004cc99  push    rdi
0x18004cc9a  sub     rsp, 70h
0x18004cc9e  mov     rax, cs:__security_cookie
0x18004cca5  xor     rax, rsp
0x18004cca8  mov     [rsp+78h+var_10], rax
0x18004ccad  mov     rdi, rdx
0x18004ccb0  mov     [rsp+78h+var_48], 0
0x18004ccb9  mov     rdx, rcx; void *
0x18004ccbc  mov     [rsp+78h+var_40], 0
0x18004ccc1  lea     rcx, [rsp+78h+var_48]; this
0x18004ccc6  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x18004cccb  mov     ebx, eax
0x18004cccd  test    eax, eax
0x18004cccf  jns     short loc_18004CCEF
0x18004ccd1  mov     rcx, [rsp+78h]; this
0x18004ccd6  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004ccdd  mov     r9d, eax; char *
0x18004cce0  mov     edx, 4F4h; void *
0x18004cce5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ccea  jmp     loc_18004CD76
0x18004ccef  xorps   xmm0, xmm0
0x18004ccf2  lea     r8, [rsp+78h+FileInformation]; lpFileInformation
0x18004ccf7  xor     eax, eax
0x18004ccf9  xor     edx, edx; fInfoLevelId
0x18004ccfb  mov     rcx, rdi; lpFileName
0x18004ccfe  mov     [rsp+78h+var_18], eax
0x18004cd02  movups  [rsp+78h+FileInformation], xmm0
0x18004cd07  movups  [rsp+78h+var_28], xmm0
0x18004cd0c  call    cs:__imp_GetFileAttributesExW
0x18004cd12  test    eax, eax
0x18004cd14  jnz     short loc_18004CD3C
0x18004cd16  mov     rcx, [rsp+78h]; this
0x18004cd1b  lea     r9, aFailedToGetAtt; "Failed to get attributes of the directo"...
0x18004cd22  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004cd29  mov     [rsp+78h+var_58], rdi; char *
0x18004cd2e  mov     edx, 4F9h; void *
0x18004cd33  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18004cd38  mov     ebx, eax
0x18004cd3a  jmp     short loc_18004CD76
0x18004cd3c  test    byte ptr [rsp+78h+FileInformation], 10h
0x18004cd41  jnz     short loc_18004CD74
0x18004cd43  mov     rcx, [rsp+78h]; this
0x18004cd48  lea     rax, aDirectoryLsIsN; "Directory <%ls> is not a directory!"
0x18004cd4f  mov     ebx, 80070003h
0x18004cd54  mov     [rsp+78h+var_50], rdi; char *
0x18004cd59  mov     r9d, ebx; char *
0x18004cd5c  mov     [rsp+78h+var_58], rax; int
0x18004cd61  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004cd68  mov     edx, 4FCh; void *
0x18004cd6d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004cd72  jmp     short loc_18004CD76
0x18004cd74  xor     ebx, ebx
0x18004cd76  lea     rcx, [rsp+78h+var_48]; this
0x18004cd7b  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18004cd80  mov     eax, ebx
0x18004cd82  mov     rcx, [rsp+78h+var_10]
0x18004cd87  xor     rcx, rsp; StackCookie
0x18004cd8a  call    __security_check_cookie
0x18004cd8f  mov     rbx, [rsp+78h+arg_10]
0x18004cd97  add     rsp, 70h
0x18004cd9b  pop     rdi
0x18004cd9c  retn
```
