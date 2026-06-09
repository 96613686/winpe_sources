# CTSSessionSecurityDescriptor::CreateAppContainerSD(void)

- ea: `0x180019dc8`
- end: `0x180019f1f`
- name: `?CreateAppContainerSD@CTSSessionSecurityDescriptor@@IEAAJXZ`
- size: `343`
- prototype: `__int64 __fastcall(CTSSessionSecurityDescriptor *__hidden this)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800189d4`
- `0x180019838`
- `0x180066040`
- `0x1800660e8`
- `0x18006aaa0`

## callees

- `0x1800074c0`
- `0x180018d40`
- `0x180018e68`
- `0x180019dc8`
- `0x180019f28`
- `0x18001a088`
- `0x1800473dc`
- `0x18004bd84`
- `0x18007e5e4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019eed`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019efc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019eed`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019efc`

## string_xrefs

- `0x180019e16`: `CUtils::CreateAppContainerSid() failed: 0x%x in %s`
- `0x180019ed0`: `CTSSessionSecurityDescriptor::CreateAppContainerSD`
- `0x180019e31`: `CUtils::CreateLPACCapabilitySid() failed: 0x%x in %s`
- `0x180019e4c`: `CUtils::CreateUserSignInCapabilitySID() failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSessionSecurityDescriptor::CreateAppContainerSD(CTSSessionSecurityDescriptor *this)
{
  char *v1; // rdi
  void *v3; // rcx
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  PSID pSid; // [rsp+40h] [rbp+20h] BYREF
  PSID Sid; // [rsp+48h] [rbp+28h] BYREF
  void *Block; // [rsp+50h] [rbp+30h] BYREF

  v1 = (char *)this + 8;
  pSid = 0;
  Sid = 0;
  v3 = (void *)*((_QWORD *)this + 2);
  Block = 0;
  CUtils::CleanupSD(v3);
  *((_QWORD *)v1 + 1) = 0;
  v4 = CUtils::CreateAppContainerSid(&pSid);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = CUtils::CreateLPACCapabilitySid(&Sid);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v7 = CUtils::CreateUserSignInCapabilitySID(&Block);
      v5 = v7;
      if ( v7 >= 0 )
      {
        v8 = CTSSecurityDescriptor::InitializeFromBlob((HLOCAL *)v1, *((void **)this + 5));
        v5 = v8;
        if ( v8 >= 0 )
        {
          v9 = CTSSecurityDescriptor::AddUserAce((CTSSecurityDescriptor *)v1, pSid, 1u);
          v5 = v9;
          if ( v9 >= 0 )
          {
            v10 = CTSSecurityDescriptor::AddUserAce((CTSSecurityDescriptor *)v1, Sid, 1u);
            v5 = v10;
            if ( v10 >= 0 )
            {
              v11 = CTSSecurityDescriptor::AddUserAce((CTSSecurityDescriptor *)v1, Block, 9u);
              v5 = v11;
              if ( v11 < 0 )
                _DbgPrintMessage(
                  8,
                  "m_AppContainerSD.AddUserAce() - UserSignIn failed: 0x%x in %s",
                  (unsigned int)v11,
                  "CTSSessionSecurityDescriptor::CreateAppContainerSD");
            }
            else
            {
              _DbgPrintMessage(
                8,
                "m_AppContainerSD.AddUserAce() - LPAC failed: 0x%x in %s",
                (unsigned int)v10,
                "CTSSessionSecurityDescriptor::CreateAppContainerSD");
            }
          }
          else
          {
            _DbgPrintMessage(
              8,
              "m_AppContainerSD.AddUserAce() - AnyPackage failed: 0x%x in %s",
              (unsigned int)v9,
              "CTSSessionSecurityDescriptor::CreateAppContainerSD");
          }
        }
        else
        {
          _DbgPrintMessage(
            8,
            "m_AppContainerSD.Initialize() failed: 0x%x in %s",
            (unsigned int)v8,
            "CTSSessionSecurityDescriptor::CreateAppContainerSD");
        }
      }
      else
      {
        _DbgPrintMessage(
          8,
          "CUtils::CreateUserSignInCapabilitySID() failed: 0x%x in %s",
          (unsigned int)v7,
          "CTSSessionSecurityDescriptor::CreateAppContainerSD");
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "CUtils::CreateLPACCapabilitySid() failed: 0x%x in %s",
        (unsigned int)v6,
        "CTSSessionSecurityDescriptor::CreateAppContainerSD");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "CUtils::CreateAppContainerSid() failed: 0x%x in %s",
      (unsigned int)v4,
      "CTSSessionSecurityDescriptor::CreateAppContainerSD");
  }
  if ( pSid )
    FreeSid(pSid);
  if ( Sid )
    FreeSid(Sid);
  if ( Block )
    operator delete(Block);
  return v5;
}

```

## disassembly

```asm
0x180019dc8  mov     [rsp-18h+arg_18], rbx
0x180019dcd  push    rbp
0x180019dce  push    rsi
0x180019dcf  push    rdi
0x180019dd0  mov     rbp, rsp
0x180019dd3  sub     rsp, 20h
0x180019dd7  lea     rdi, [rcx+8]
0x180019ddb  mov     [rbp+pSid], 0
0x180019de3  mov     rsi, rcx
0x180019de6  mov     [rbp+Sid], 0
0x180019dee  mov     rcx, [rdi+8]; hMem
0x180019df2  mov     [rbp+Block], 0
0x180019dfa  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x180019dff  lea     rcx, [rbp+pSid]; pSid
0x180019e03  mov     qword ptr [rdi+8], 0
0x180019e0b  call    ?CreateAppContainerSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAppContainerSid(void * *)
0x180019e10  mov     ebx, eax
0x180019e12  test    eax, eax
0x180019e14  jns     short loc_180019E22
0x180019e16  lea     rdx, aCutilsCreateap_0; "CUtils::CreateAppContainerSid() failed:"...
0x180019e1d  jmp     loc_180019ED0
0x180019e22  lea     rcx, [rbp+Sid]; Sid
0x180019e26  call    ?CreateLPACCapabilitySid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateLPACCapabilitySid(void * *)
0x180019e2b  mov     ebx, eax
0x180019e2d  test    eax, eax
0x180019e2f  jns     short loc_180019E3D
0x180019e31  lea     rdx, aCutilsCreatelp_1; "CUtils::CreateLPACCapabilitySid() faile"...
0x180019e38  jmp     loc_180019ED0
0x180019e3d  lea     rcx, [rbp+Block]; void **
0x180019e41  call    ?CreateUserSignInCapabilitySID@CUtils@@SAJPEAPEAX@Z; CUtils::CreateUserSignInCapabilitySID(void * *)
0x180019e46  mov     ebx, eax
0x180019e48  test    eax, eax
0x180019e4a  jns     short loc_180019E55
0x180019e4c  lea     rdx, aCutilsCreateus_0; "CUtils::CreateUserSignInCapabilitySID()"...
0x180019e53  jmp     short loc_180019ED0
0x180019e55  mov     rdx, [rsi+28h]; void *
0x180019e59  mov     rcx, rdi; this
0x180019e5c  call    ?InitializeFromBlob@CTSSecurityDescriptor@@QEAAJPEAX@Z; CTSSecurityDescriptor::InitializeFromBlob(void *)
0x180019e61  mov     ebx, eax
0x180019e63  test    eax, eax
0x180019e65  jns     short loc_180019E70
0x180019e67  lea     rdx, aMAppcontainers_2; "m_AppContainerSD.Initialize() failed: 0"...
0x180019e6e  jmp     short loc_180019ED0
0x180019e70  mov     rdx, [rbp+pSid]; void *
0x180019e74  mov     esi, 1
0x180019e79  mov     r8d, esi; unsigned int
0x180019e7c  mov     rcx, rdi; this
0x180019e7f  call    ?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z; CTSSecurityDescriptor::AddUserAce(void *,ulong)
0x180019e84  mov     ebx, eax
0x180019e86  test    eax, eax
0x180019e88  jns     short loc_180019E93
0x180019e8a  lea     rdx, aMAppcontainers_1; "m_AppContainerSD.AddUserAce() - AnyPack"...
0x180019e91  jmp     short loc_180019ED0
0x180019e93  mov     rdx, [rbp+Sid]; void *
0x180019e97  mov     r8d, esi; unsigned int
0x180019e9a  mov     rcx, rdi; this
0x180019e9d  call    ?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z; CTSSecurityDescriptor::AddUserAce(void *,ulong)
0x180019ea2  mov     ebx, eax
0x180019ea4  test    eax, eax
0x180019ea6  jns     short loc_180019EB1
0x180019ea8  lea     rdx, aMAppcontainers_0; "m_AppContainerSD.AddUserAce() - LPAC fa"...
0x180019eaf  jmp     short loc_180019ED0
0x180019eb1  mov     rdx, [rbp+Block]; void *
0x180019eb5  mov     r8d, 9; unsigned int
0x180019ebb  mov     rcx, rdi; this
0x180019ebe  call    ?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z; CTSSecurityDescriptor::AddUserAce(void *,ulong)
0x180019ec3  mov     ebx, eax
0x180019ec5  test    eax, eax
0x180019ec7  jns     short loc_180019EE4
0x180019ec9  lea     rdx, aMAppcontainers; "m_AppContainerSD.AddUserAce() - UserSig"...
0x180019ed0  lea     r9, aCtssessionsecu_0; "CTSSessionSecurityDescriptor::CreateApp"...
0x180019ed7  mov     r8d, eax
0x180019eda  mov     ecx, 8; int
0x180019edf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019ee4  mov     rcx, [rbp+pSid]; pSid
0x180019ee8  test    rcx, rcx
0x180019eeb  jz      short loc_180019EF3
0x180019eed  call    cs:__imp_FreeSid
0x180019ef3  mov     rcx, [rbp+Sid]; pSid
0x180019ef7  test    rcx, rcx
0x180019efa  jz      short loc_180019F02
0x180019efc  call    cs:__imp_FreeSid
0x180019f02  mov     rcx, [rbp+Block]; Block
0x180019f06  test    rcx, rcx
0x180019f09  jz      short loc_180019F10
0x180019f0b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019f10  mov     eax, ebx
0x180019f12  mov     rbx, [rsp+20h+arg_18]
0x180019f17  add     rsp, 20h
0x180019f1b  pop     rdi
0x180019f1c  pop     rsi
0x180019f1d  pop     rbp
0x180019f1e  retn
```
