# CTSSessionSecurityDescriptor::CreateAppContainerSD(void)

- ea: `0x18000ab80`
- end: `0x18000ace4`
- name: `?CreateAppContainerSD@CTSSessionSecurityDescriptor@@IEAAJXZ`
- size: `356`
- prototype: `__int64 __fastcall(CTSSessionSecurityDescriptor *__hidden this)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800095f8`
- `0x18000a5e0`
- `0x180069d00`
- `0x180069da8`
- `0x18006e8f0`

## callees

- `0x1800077a0`
- `0x180009490`
- `0x180009998`
- `0x180009ad4`
- `0x18000ab80`
- `0x18000acec`
- `0x180049dbc`
- `0x18004f174`
- `0x180083060`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000aca5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000acba`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000aca5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000acba`

## string_xrefs

- `0x18000abce`: `CUtils::CreateAppContainerSid() failed: 0x%x in %s`
- `0x18000ac88`: `CTSSessionSecurityDescriptor::CreateAppContainerSD`
- `0x18000ac04`: `CUtils::CreateUserSignInCapabilitySID() failed: 0x%x in %s`
- `0x18000abe9`: `CUtils::CreateLPACCapabilitySid() failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSessionSecurityDescriptor::CreateAppContainerSD(CTSSessionSecurityDescriptor *this)
{
  CTSSecurityDescriptor *v1; // rdi
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

  v1 = (CTSSessionSecurityDescriptor *)((char *)this + 8);
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
        v8 = CTSSecurityDescriptor::InitializeFromBlob(v1, *((void **)this + 5));
        v5 = v8;
        if ( v8 >= 0 )
        {
          v9 = CTSSecurityDescriptor::AddUserAce(v1, pSid, 1u);
          v5 = v9;
          if ( v9 >= 0 )
          {
            v10 = CTSSecurityDescriptor::AddUserAce(v1, Sid, 1u);
            v5 = v10;
            if ( v10 >= 0 )
            {
              v11 = CTSSecurityDescriptor::AddUserAce(v1, Block, 9u);
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
0x18000ab80  mov     [rsp-18h+arg_18], rbx
0x18000ab85  push    rbp
0x18000ab86  push    rsi
0x18000ab87  push    rdi
0x18000ab88  mov     rbp, rsp
0x18000ab8b  sub     rsp, 20h
0x18000ab8f  lea     rdi, [rcx+8]
0x18000ab93  mov     [rbp+pSid], 0
0x18000ab9b  mov     rsi, rcx
0x18000ab9e  mov     [rbp+Sid], 0
0x18000aba6  mov     rcx, [rdi+8]; hMem
0x18000abaa  mov     [rbp+Block], 0
0x18000abb2  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x18000abb7  lea     rcx, [rbp+pSid]; pSid
0x18000abbb  mov     qword ptr [rdi+8], 0
0x18000abc3  call    ?CreateAppContainerSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAppContainerSid(void * *)
0x18000abc8  mov     ebx, eax
0x18000abca  test    eax, eax
0x18000abcc  jns     short loc_18000ABDA
0x18000abce  lea     rdx, aCutilsCreateap_0; "CUtils::CreateAppContainerSid() failed:"...
0x18000abd5  jmp     loc_18000AC88
0x18000abda  lea     rcx, [rbp+Sid]; Sid
0x18000abde  call    ?CreateLPACCapabilitySid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateLPACCapabilitySid(void * *)
0x18000abe3  mov     ebx, eax
0x18000abe5  test    eax, eax
0x18000abe7  jns     short loc_18000ABF5
0x18000abe9  lea     rdx, aCutilsCreatelp_1; "CUtils::CreateLPACCapabilitySid() faile"...
0x18000abf0  jmp     loc_18000AC88
0x18000abf5  lea     rcx, [rbp+Block]; void **
0x18000abf9  call    ?CreateUserSignInCapabilitySID@CUtils@@SAJPEAPEAX@Z; CUtils::CreateUserSignInCapabilitySID(void * *)
0x18000abfe  mov     ebx, eax
0x18000ac00  test    eax, eax
0x18000ac02  jns     short loc_18000AC0D
0x18000ac04  lea     rdx, aCutilsCreateus_0; "CUtils::CreateUserSignInCapabilitySID()"...
0x18000ac0b  jmp     short loc_18000AC88
0x18000ac0d  mov     rdx, [rsi+28h]; void *
0x18000ac11  mov     rcx, rdi; this
0x18000ac14  call    ?InitializeFromBlob@CTSSecurityDescriptor@@QEAAJPEAX@Z; CTSSecurityDescriptor::InitializeFromBlob(void *)
0x18000ac19  mov     ebx, eax
0x18000ac1b  test    eax, eax
0x18000ac1d  jns     short loc_18000AC28
0x18000ac1f  lea     rdx, aMAppcontainers_2; "m_AppContainerSD.Initialize() failed: 0"...
0x18000ac26  jmp     short loc_18000AC88
0x18000ac28  mov     rdx, [rbp+pSid]; void *
0x18000ac2c  mov     esi, 1
0x18000ac31  mov     r8d, esi; unsigned int
0x18000ac34  mov     rcx, rdi; this
0x18000ac37  call    ?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z; CTSSecurityDescriptor::AddUserAce(void *,ulong)
0x18000ac3c  mov     ebx, eax
0x18000ac3e  test    eax, eax
0x18000ac40  jns     short loc_18000AC4B
0x18000ac42  lea     rdx, aMAppcontainers_1; "m_AppContainerSD.AddUserAce() - AnyPack"...
0x18000ac49  jmp     short loc_18000AC88
0x18000ac4b  mov     rdx, [rbp+Sid]; void *
0x18000ac4f  mov     r8d, esi; unsigned int
0x18000ac52  mov     rcx, rdi; this
0x18000ac55  call    ?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z; CTSSecurityDescriptor::AddUserAce(void *,ulong)
0x18000ac5a  mov     ebx, eax
0x18000ac5c  test    eax, eax
0x18000ac5e  jns     short loc_18000AC69
0x18000ac60  lea     rdx, aMAppcontainers_0; "m_AppContainerSD.AddUserAce() - LPAC fa"...
0x18000ac67  jmp     short loc_18000AC88
0x18000ac69  mov     rdx, [rbp+Block]; void *
0x18000ac6d  mov     r8d, 9; unsigned int
0x18000ac73  mov     rcx, rdi; this
0x18000ac76  call    ?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z; CTSSecurityDescriptor::AddUserAce(void *,ulong)
0x18000ac7b  mov     ebx, eax
0x18000ac7d  test    eax, eax
0x18000ac7f  jns     short loc_18000AC9C
0x18000ac81  lea     rdx, aMAppcontainers; "m_AppContainerSD.AddUserAce() - UserSig"...
0x18000ac88  lea     r9, aCtssessionsecu_0; "CTSSessionSecurityDescriptor::CreateApp"...
0x18000ac8f  mov     r8d, eax
0x18000ac92  mov     ecx, 8; int
0x18000ac97  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ac9c  mov     rcx, [rbp+pSid]; pSid
0x18000aca0  test    rcx, rcx
0x18000aca3  jz      short loc_18000ACB1
0x18000aca5  call    cs:__imp_FreeSid
0x18000acac  nop     dword ptr [rax+rax+00h]
0x18000acb1  mov     rcx, [rbp+Sid]; pSid
0x18000acb5  test    rcx, rcx
0x18000acb8  jz      short loc_18000ACC6
0x18000acba  call    cs:__imp_FreeSid
0x18000acc1  nop     dword ptr [rax+rax+00h]
0x18000acc6  mov     rcx, [rbp+Block]; Block
0x18000acca  test    rcx, rcx
0x18000accd  jz      short loc_18000ACD4
0x18000accf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000acd4  mov     eax, ebx
0x18000acd6  mov     rbx, [rsp+20h+arg_18]
0x18000acdb  add     rsp, 20h
0x18000acdf  pop     rdi
0x18000ace0  pop     rsi
0x18000ace1  pop     rbp
0x18000ace2  retn
```
