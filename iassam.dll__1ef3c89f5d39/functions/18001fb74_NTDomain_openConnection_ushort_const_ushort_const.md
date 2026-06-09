# NTDomain::openConnection(ushort const *,ushort const *)

- ea: `0x18001fb74`
- end: `0x18001fe0a`
- name: `?openConnection@NTDomain@@IEAAKPEBG0@Z`
- size: `662`
- prototype: `unsigned int __fastcall(NTDomain *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18001f640`

## callees

- `0x180001c88`
- `0x1800033bc`
- `0x18000a760`
- `0x18000c4a4`
- `0x18000d49c`
- `0x18000e754`
- `0x18001eb48`
- `0x18001f458`
- `0x18001f48c`
- `0x18001f608`
- `0x18001fb74`
- `0x18001fe10`
- `0x1800254a0`
- `0x180026fdc`
- `0x180029fe4`
- `0x18002b4a0`
- `0x18002e010`

## string_xrefs

- `0x18001fd94`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x18001fbcd`: `Opening LDAP connection to %S.`
- `0x18001fc25`: `Access denied -- purging Kerberos ticket cache.`

## pseudocode

```c
__int64 __fastcall NTDomain::openConnection(struct _RTL_CRITICAL_SECTION **this, const unsigned __int16 *a2, WCHAR *a3)
{
  const unsigned __int16 *v5; // rcx
  int v6; // r9d
  ULONG Instance; // edi
  const unsigned __int16 *v8; // rcx
  int v9; // r9d
  AvoidanceEntry *v10; // rax
  __int64 v11; // r8
  struct CacheEntry *v12; // rbx
  bool v13; // r8
  unsigned int v14; // eax
  __int64 v15; // rcx
  struct CacheEntry *v17; // [rsp+30h] [rbp-148h] BYREF
  char Buffer[256]; // [rsp+40h] [rbp-138h] BYREF

  NTDomain::closeConnection((NTDomain *)this);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Opening LDAP connection to %S.");
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_3d17ec2a460a38aa7d49725326c61fb2_Traceguids,
      v6,
      (__int64)a3);
  }
  Instance = LDAPConnection::createInstance(v5, a3, this + 15);
  if ( Instance == 5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Access denied -- purging Kerberos ticket cache.");
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        Instance + 6,
        WPP_3d17ec2a460a38aa7d49725326c61fb2_Traceguids,
        "NPSSVC");
    }
    IASPurgeTicketCache();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Retrying LDAP connection to %S.");
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_3d17ec2a460a38aa7d49725326c61fb2_Traceguids,
        v9,
        (__int64)a3);
    }
    Instance = LDAPConnection::createInstance(v8, a3, this + 15);
  }
  if ( Instance || (Instance = NTDomain::readDomainMode((NTDomain *)this)) != 0 )
  {
    v10 = (AvoidanceEntry *)operator new(0x50u);
    if ( v10 )
      v10 = AvoidanceEntry::AvoidanceEntry(v10, a3);
    LOBYTE(v11) = 1;
    ObjectPointer<AvoidanceEntry>::ObjectPointer<AvoidanceEntry>(&v17, v10, v11);
    v12 = v17;
    CacheBase::insert((CacheBase *)(this + 18), v17, v13);
    v14 = IASFormatSysErr(Instance, Buffer);
    if ( v14 >= 0x100uLL )
      _report_rangecheckfailure(v15);
    Buffer[v14] = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
      WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"LDAP connect", (__int64)Buffer);
    }
    if ( v12 )
      (*(void (__fastcall **)(struct CacheEntry *))(*(_QWORD *)v12 + 8LL))(v12);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("LDAP connect succeeded.");
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      Instance + 13,
      WPP_3d17ec2a460a38aa7d49725326c61fb2_Traceguids,
      "NPSSVC");
  }
  return Instance;
}

```

## disassembly

```asm
0x18001fb74  mov     [rsp+arg_8], rbx
0x18001fb79  push    rbp
0x18001fb7a  push    rsi
0x18001fb7b  push    rdi
0x18001fb7c  push    r12
0x18001fb7e  push    r15
0x18001fb80  sub     rsp, 150h
0x18001fb87  mov     rax, cs:__security_cookie
0x18001fb8e  xor     rax, rsp
0x18001fb91  mov     [rsp+178h+var_38], rax
0x18001fb99  mov     rbx, r8
0x18001fb9c  mov     rsi, rcx
0x18001fb9f  call    ?closeConnection@NTDomain@@IEAAXXZ; NTDomain::closeConnection(void)
0x18001fba4  lea     r15, WPP_GLOBAL_Control
0x18001fbab  lea     r12, WPP_3d17ec2a460a38aa7d49725326c61fb2_Traceguids
0x18001fbb2  mov     rax, cs:WPP_GLOBAL_Control
0x18001fbb9  cmp     rax, r15
0x18001fbbc  jz      short loc_18001FBF6
0x18001fbbe  cmp     byte ptr [rax+19h], 4
0x18001fbc2  jb      short loc_18001FBF6
0x18001fbc4  test    byte ptr [rax+1Ch], 4
0x18001fbc8  jz      short loc_18001FBF6
0x18001fbca  mov     rdx, rbx
0x18001fbcd  lea     rcx, aOpeningLdapCon; "Opening LDAP connection to %S."
0x18001fbd4  call    WppDbgPrint
0x18001fbd9  mov     edx, 0Ah
0x18001fbde  mov     [rsp+178h+var_158], rbx
0x18001fbe3  mov     r8, r12
0x18001fbe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fbed  mov     rcx, [rcx+10h]
0x18001fbf1  call    WPP_SF_sS
0x18001fbf6  lea     r8, [rsi+78h]; struct LDAPConnection **
0x18001fbfa  mov     rdx, rbx; unsigned __int16 *
0x18001fbfd  call    ?createInstance@LDAPConnection@@SAKPEBG0PEAPEAV1@@Z; LDAPConnection::createInstance(ushort const *,ushort const *,LDAPConnection * *)
0x18001fc02  mov     edi, eax
0x18001fc04  cmp     eax, 5
0x18001fc07  jnz     loc_18001FCA5
0x18001fc0d  mov     rax, cs:WPP_GLOBAL_Control
0x18001fc14  cmp     rax, r15
0x18001fc17  jz      short loc_18001FC4E
0x18001fc19  cmp     byte ptr [rax+19h], 2
0x18001fc1d  jb      short loc_18001FC4E
0x18001fc1f  test    byte ptr [rax+1Ch], 4
0x18001fc23  jz      short loc_18001FC4E
0x18001fc25  lea     rcx, aAccessDeniedPu; "Access denied -- purging Kerberos ticke"...
0x18001fc2c  call    WppDbgPrint
0x18001fc31  lea     edx, [rdi+6]
0x18001fc34  lea     r9, aNpssvc; "NPSSVC"
0x18001fc3b  mov     r8, r12
0x18001fc3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc45  mov     rcx, [rcx+10h]
0x18001fc49  call    WPP_SF_s
0x18001fc4e  call    IASPurgeTicketCache
0x18001fc53  mov     rax, cs:WPP_GLOBAL_Control
0x18001fc5a  cmp     rax, r15
0x18001fc5d  jz      short loc_18001FC97
0x18001fc5f  cmp     byte ptr [rax+19h], 4
0x18001fc63  jb      short loc_18001FC97
0x18001fc65  test    byte ptr [rax+1Ch], 4
0x18001fc69  jz      short loc_18001FC97
0x18001fc6b  mov     rdx, rbx
0x18001fc6e  lea     rcx, aRetryingLdapCo; "Retrying LDAP connection to %S."
0x18001fc75  call    WppDbgPrint
0x18001fc7a  mov     edx, 0Ch
0x18001fc7f  mov     [rsp+178h+var_158], rbx
0x18001fc84  mov     r8, r12
0x18001fc87  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc8e  mov     rcx, [rcx+10h]
0x18001fc92  call    WPP_SF_sS
0x18001fc97  lea     r8, [rsi+78h]; struct LDAPConnection **
0x18001fc9b  mov     rdx, rbx; unsigned __int16 *
0x18001fc9e  call    ?createInstance@LDAPConnection@@SAKPEBG0PEAPEAV1@@Z; LDAPConnection::createInstance(ushort const *,ushort const *,LDAPConnection * *)
0x18001fca3  mov     edi, eax
0x18001fca5  test    edi, edi
0x18001fca7  jnz     short loc_18001FD09
0x18001fca9  mov     rcx, rsi; this
0x18001fcac  call    ?readDomainMode@NTDomain@@IEAAKXZ; NTDomain::readDomainMode(void)
0x18001fcb1  mov     edi, eax
0x18001fcb3  test    eax, eax
0x18001fcb5  jnz     short loc_18001FD09
0x18001fcb7  mov     rax, cs:WPP_GLOBAL_Control
0x18001fcbe  cmp     rax, r15
0x18001fcc1  jz      loc_18001FDDB
0x18001fcc7  cmp     byte ptr [rax+19h], 4
0x18001fccb  jb      loc_18001FDDB
0x18001fcd1  test    byte ptr [rax+1Ch], 4
0x18001fcd5  jz      loc_18001FDDB
0x18001fcdb  lea     rcx, aLdapConnectSuc; "LDAP connect succeeded."
0x18001fce2  call    WppDbgPrint
0x18001fce7  lea     edx, [rdi+0Dh]
0x18001fcea  lea     r9, aNpssvc; "NPSSVC"
0x18001fcf1  mov     r8, r12
0x18001fcf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fcfb  mov     rcx, [rcx+10h]
0x18001fcff  call    WPP_SF_s
0x18001fd04  jmp     loc_18001FDDB
0x18001fd09  mov     ecx, 50h ; 'P'; Size
0x18001fd0e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fd13  test    rax, rax
0x18001fd16  jz      short loc_18001FD23
0x18001fd18  mov     rdx, rbx; unsigned __int16 *
0x18001fd1b  mov     rcx, rax; this
0x18001fd1e  call    ??0AvoidanceEntry@@QEAA@PEBG@Z; AvoidanceEntry::AvoidanceEntry(ushort const *)
0x18001fd23  mov     r8b, 1
0x18001fd26  mov     rdx, rax
0x18001fd29  lea     rcx, [rsp+178h+var_148]
0x18001fd2e  call    ??0?$ObjectPointer@VAvoidanceEntry@@@@QEAA@PEAVAvoidanceEntry@@_N@Z; ObjectPointer<AvoidanceEntry>::ObjectPointer<AvoidanceEntry>(AvoidanceEntry *,bool)
0x18001fd33  lea     rcx, [rsi+90h]; this
0x18001fd3a  mov     rbx, [rsp+178h+var_148]
0x18001fd3f  mov     rdx, rbx; struct CacheEntry *
0x18001fd42  call    ?insert@CacheBase@@QEAA_NAEAVCacheEntry@@_N@Z; CacheBase::insert(CacheEntry &,bool)
0x18001fd47  lea     rdx, [rsp+178h+Buffer]; Buffer
0x18001fd4c  mov     ecx, edi; dwMessageId
0x18001fd4e  call    IASFormatSysErr
0x18001fd53  mov     eax, eax
0x18001fd55  cmp     rax, 100h
0x18001fd5b  jnb     loc_18001FE04
0x18001fd61  mov     [rsp+rax+178h+Buffer], 0
0x18001fd66  mov     rax, cs:WPP_GLOBAL_Control
0x18001fd6d  cmp     rax, r15
0x18001fd70  jz      short loc_18001FDC7
0x18001fd72  cmp     byte ptr [rax+19h], 2
0x18001fd76  jb      short loc_18001FDC7
0x18001fd78  test    byte ptr [rax+1Ch], 4
0x18001fd7c  jz      short loc_18001FDC7
0x18001fd7e  lea     r9, [rsp+178h+Buffer]
0x18001fd83  lea     rsi, aLdapConnect_0; "LDAP connect"
0x18001fd8a  mov     r8, rsi
0x18001fd8d  lea     rdx, aNpssvc; "NPSSVC"
0x18001fd94  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18001fd9b  call    WppDbgPrint
0x18001fda0  mov     edx, 0Eh
0x18001fda5  lea     rax, [rsp+178h+Buffer]
0x18001fdaa  mov     [rsp+178h+var_150], rax; __int64
0x18001fdaf  mov     [rsp+178h+var_158], rsi; __int64
0x18001fdb4  mov     r8, r12
0x18001fdb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fdbe  mov     rcx, [rcx+10h]; LoggerHandle
0x18001fdc2  call    WPP_SF_sss
0x18001fdc7  test    rbx, rbx
0x18001fdca  jz      short loc_18001FDDB
0x18001fdcc  mov     rax, [rbx]
0x18001fdcf  mov     rcx, rbx
0x18001fdd2  mov     rax, [rax+8]
0x18001fdd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fddb  mov     eax, edi
0x18001fddd  mov     rcx, [rsp+178h+var_38]
0x18001fde5  xor     rcx, rsp; StackCookie
0x18001fde8  call    __security_check_cookie
0x18001fded  mov     rbx, [rsp+178h+arg_8]
0x18001fdf5  add     rsp, 150h
0x18001fdfc  pop     r15
0x18001fdfe  pop     r12
0x18001fe00  pop     rdi
0x18001fe01  pop     rsi
0x18001fe02  pop     rbp
0x18001fe03  retn
0x18001fe04  call    __report_rangecheckfailure
```
