# Config::AdObjectEditor::DeleteSubTree(ushort const *,ulong)

- ea: `0x1401e3aec`
- end: `0x1401e3dd3`
- name: `?DeleteSubTree@AdObjectEditor@Config@@IEAAPEAVFrsStatus@@PEBGK@Z`
- size: `743`
- prototype: `struct FrsStatus *__fastcall(Config::AdObjectEditor *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1401e3a08`
- `0x1401e3aec`

## callees

- `0x140019358`
- `0x14002179c`
- `0x1401b90b4`
- `0x1401b9494`
- `0x1401de184`
- `0x1401de240`
- `0x1401de77c`
- `0x1401de7cc`
- `0x1401e3aec`
- `0x1401e684c`
- `0x1401e7efc`
- `0x1401f2054`
- `0x1401f3320`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401e3bda`
- `KERNEL32!GetCurrentThreadId` at `0x1401e3cce`
- `KERNEL32!GetCurrentThreadId` at `0x1401e3d1b`
- `KERNEL32!GetCurrentThreadId` at `0x1401e3d71`
- `KERNEL32!GetCurrentThreadId` at `0x1401e3bda`
- `KERNEL32!GetCurrentThreadId` at `0x1401e3cce`
- `KERNEL32!GetCurrentThreadId` at `0x1401e3d1b`
- `KERNEL32!GetCurrentThreadId` at `0x1401e3d71`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1401e3cde`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1401e3cde`
- `WLDAP32!__imp_ldap_delete_sW` at `0x1401e3c45`
- `WLDAP32!__imp_ldap_delete_sW` at `0x1401e3c45`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1401e3c9c`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1401e3c9c`

## string_xrefs

- `0x1401e3b79`: `Config::AdObjectEditor::DeleteSubTree`
- `0x1401e3c72`: `Config::AdObjectEditor::DeleteSubTree`
- `0x1401e3cbd`: `Failed to ldap_delete_s(). dn:%ws Error:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct FrsStatus *__fastcall Config::AdObjectEditor::DeleteSubTree(
        struct Config::AdSession **this,
        unsigned __int16 *a2)
{
  __int64 v4; // rdi
  struct FrsStatus *started; // rbx
  int i; // eax
  const unsigned __int16 *Value; // rax
  struct FrsStatus *v8; // rax
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  ULONG v11; // esi
  DWORD v12; // ebx
  ULONG v13; // eax
  __int64 v14; // rcx
  FrsStatus *v15; // rbx
  DWORD v16; // eax
  __int64 v17; // rcx
  struct FrsStatus *v18; // rax
  DWORD v19; // eax
  __int64 v20; // rcx
  _QWORD v22[4]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v23[40]; // [rsp+78h] [rbp-90h] BYREF
  Config::AdStrAttr *v24; // [rsp+A0h] [rbp-68h]
  _BYTE v25[368]; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int16 *v26; // [rsp+278h] [rbp+170h] BYREF
  unsigned __int16 *v27; // [rsp+280h] [rbp+178h] BYREF

  v27 = a2;
  Config::AdQuery::AdQuery((Config::AdQuery *)v25);
  v26 = L"distinguishedName";
  v4 = 0;
  started = Config::AdQuery::StartSearch(
              (Config::AdQuery *)v25,
              this[1],
              a2,
              1u,
              (const unsigned __int16 **)&v26,
              1u,
              0,
              0,
              L"(objectCategory=*)",
              0x8CA0u);
  if ( started )
    goto LABEL_18;
  Config::AdObject::AdObject((Config::AdObject *)v23);
  for ( i = Config::AdQuery::GetFirstObject((Config::AdQuery *)v25, (struct Config::AdObject *)v23);
        i && !started;
        i = Config::AdQuery::GetNextObject((Config::AdQuery *)v25, (struct Config::AdObject *)v23) )
  {
    if ( Config::AdStrAttr::GetValue(v24) )
    {
      Value = Config::AdStrAttr::GetValue(v24);
      v8 = Config::AdObjectEditor::DeleteSubTree((Config::AdObjectEditor *)this, Value, 0x8CA0u);
    }
    else
    {
      CurrentThreadId = GetCurrentThreadId();
      v8 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v10,
                                 13,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                                 "Config::AdObjectEditor::DeleteSubTree",
                                 2801,
                                 CurrentThreadId,
                                 0);
    }
    started = v8;
  }
  Config::AdObject::Release((Config::AdObject *)v23);
  if ( !started )
  {
    v11 = ldap_delete_sW(*(LDAP **)this[1], a2);
    if ( v11 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v22[0] = L"Config::AdObjectEditor::DeleteSubTree";
        v22[1] = 0x200000AFBLL;
        v22[2] = L"CFAD";
        v26 = ldap_err2stringW(v11);
        dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
          v22,
          L"Failed to ldap_delete_s(). dn:%ws Error:%?",
          &v27,
          &v26);
      }
      v12 = GetCurrentThreadId();
      v13 = LdapMapErrorToWin32(v11);
      v15 = (FrsStatus *)FrsStatusList::PushNewError(
                           v14,
                           v13,
                           0,
                           1,
                           "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                           "Config::AdObjectEditor::DeleteSubTree",
                           2818,
                           v12,
                           0);
      v16 = GetCurrentThreadId();
      v18 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  v17,
                                  v11,
                                  0,
                                  5,
                                  "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                                  "Config::AdObjectEditor::DeleteSubTree",
                                  2818,
                                  v16,
                                  0);
      started = FrsStatus::AppendError(v15, v18);
    }
    else
    {
      started = 0;
    }
  }
  Config::AdObject::~AdObject((Config::AdObject *)v23);
  if ( started )
  {
LABEL_18:
    v19 = GetCurrentThreadId();
    v4 = FrsStatusList::PushNewError(
           v20,
           *((unsigned int *)started + 1),
           *((unsigned int *)started + 2),
           *(unsigned int *)started,
           "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
           "Config::AdObjectEditor::DeleteSubTree",
           2822,
           v19,
           started);
  }
  Config::AdQuery::~AdQuery((Config::AdQuery *)v25);
  return (struct FrsStatus *)v4;
}

```

## disassembly

```asm
0x1401e3aec  mov     rax, rsp
0x1401e3aef  mov     [rax+18h], rbx
0x1401e3af3  mov     [rax+20h], rsi
0x1401e3af7  mov     [rax+10h], rdx
0x1401e3afb  push    rbp
0x1401e3afc  push    rdi
0x1401e3afd  push    r12
0x1401e3aff  push    r13
0x1401e3b01  push    r14
0x1401e3b03  lea     rbp, [rax-168h]
0x1401e3b0a  sub     rsp, 240h
0x1401e3b11  mov     r14, rdx
0x1401e3b14  mov     rsi, rcx
0x1401e3b17  lea     rcx, [rbp+160h+var_190]; this
0x1401e3b1b  call    ??0AdQuery@Config@@QEAA@XZ; Config::AdQuery::AdQuery(void)
0x1401e3b20  nop
0x1401e3b21  lea     rax, aDistinguishedn_0; "distinguishedName"
0x1401e3b28  mov     [rbp+160h+arg_0], rax
0x1401e3b2f  mov     [rsp+260h+var_218], 8CA0h; unsigned int
0x1401e3b37  lea     rax, aObjectcategory_6; "(objectCategory=*)"
0x1401e3b3e  mov     [rsp+260h+var_220], rax; unsigned __int16 *
0x1401e3b43  xor     edi, edi
0x1401e3b45  mov     [rsp+260h+var_228], edi; unsigned int
0x1401e3b49  mov     [rsp+260h+var_230], rdi; unsigned __int16 **
0x1401e3b4e  mov     [rsp+260h+var_238], 1; unsigned int
0x1401e3b56  lea     rax, [rbp+160h+arg_0]
0x1401e3b5d  mov     [rsp+260h+var_240], rax; unsigned __int16 **
0x1401e3b62  lea     r9d, [rdi+1]; unsigned int
0x1401e3b66  mov     r8, r14; unsigned __int16 *
0x1401e3b69  mov     rdx, [rsi+8]; struct Config::AdSession *
0x1401e3b6d  lea     rcx, [rbp+160h+var_190]; this
0x1401e3b71  call    ?StartSearch@AdQuery@Config@@QEAAPEAVFrsStatus@@PEAVAdSession@2@PEBGKPEAPEBGK2K1K@Z; Config::AdQuery::StartSearch(Config::AdSession *,ushort const *,ulong,ushort const * *,ulong,ushort const * *,ulong,ushort const *,ulong)
0x1401e3b76  mov     rbx, rax
0x1401e3b79  lea     r12, aConfigAdobject; "Config::AdObjectEditor::DeleteSubTree"
0x1401e3b80  lea     r13, aBaseFsRemotefs_10; "base\\fs\\remotefs\\frs\\src\\ad\\ad.cp"...
0x1401e3b87  test    rax, rax
0x1401e3b8a  jnz     loc_1401E3D71
0x1401e3b90  lea     rcx, [rsp+260h+var_1F0]; this
0x1401e3b95  call    ??0AdObject@Config@@QEAA@XZ; Config::AdObject::AdObject(void)
0x1401e3b9a  nop
0x1401e3b9b  lea     rdx, [rsp+260h+var_1F0]; struct Config::AdObject *
0x1401e3ba0  lea     rcx, [rbp+160h+var_190]; this
0x1401e3ba4  call    ?GetFirstObject@AdQuery@Config@@QEAAHPEAVAdObject@2@@Z; Config::AdQuery::GetFirstObject(Config::AdObject *)
0x1401e3ba9  jmp     short loc_1401E3C24
0x1401e3bab  test    rbx, rbx
0x1401e3bae  jnz     short loc_1401E3C28
0x1401e3bb0  mov     rcx, [rbp+160h+var_1C8]; this
0x1401e3bb4  call    ?GetValue@AdStrAttr@Config@@QEBAPEBGXZ; Config::AdStrAttr::GetValue(void)
0x1401e3bb9  test    rax, rax
0x1401e3bbc  jz      short loc_1401E3BDA
0x1401e3bbe  mov     rcx, [rbp+160h+var_1C8]; this
0x1401e3bc2  call    ?GetValue@AdStrAttr@Config@@QEBAPEBGXZ; Config::AdStrAttr::GetValue(void)
0x1401e3bc7  mov     rdx, rax; unsigned __int16 *
0x1401e3bca  mov     r8d, 8CA0h; unsigned int
0x1401e3bd0  mov     rcx, rsi; this
0x1401e3bd3  call    ?DeleteSubTree@AdObjectEditor@Config@@IEAAPEAVFrsStatus@@PEBGK@Z; Config::AdObjectEditor::DeleteSubTree(ushort const *,ulong)
0x1401e3bd8  jmp     short loc_1401E3C13
0x1401e3bda  call    cs:__imp_GetCurrentThreadId
0x1401e3be1  nop     dword ptr [rax+rax+00h]
0x1401e3be6  mov     [rsp+260h+var_220], rdi
0x1401e3beb  mov     [rsp+260h+var_228], eax
0x1401e3bef  mov     dword ptr [rsp+260h+var_230], 0AF1h
0x1401e3bf7  mov     qword ptr [rsp+260h+var_238], r12
0x1401e3bfc  mov     [rsp+260h+var_240], r13
0x1401e3c01  mov     r9d, 1
0x1401e3c07  xor     r8d, r8d
0x1401e3c0a  lea     edx, [r9+0Ch]
0x1401e3c0e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401e3c13  mov     rbx, rax
0x1401e3c16  lea     rdx, [rsp+260h+var_1F0]; struct Config::AdObject *
0x1401e3c1b  lea     rcx, [rbp+160h+var_190]; this
0x1401e3c1f  call    ?GetNextObject@AdQuery@Config@@QEAAHPEAVAdObject@2@@Z; Config::AdQuery::GetNextObject(Config::AdObject *)
0x1401e3c24  test    eax, eax
0x1401e3c26  jnz     short loc_1401E3BAB
0x1401e3c28  lea     rcx, [rsp+260h+var_1F0]; this
0x1401e3c2d  call    ?Release@AdObject@Config@@QEAAXXZ; Config::AdObject::Release(void)
0x1401e3c32  test    rbx, rbx
0x1401e3c35  jnz     loc_1401E3D62
0x1401e3c3b  mov     rax, [rsi+8]
0x1401e3c3f  mov     rdx, r14; dn
0x1401e3c42  mov     rcx, [rax]; ld
0x1401e3c45  call    cs:__imp_ldap_delete_sW
0x1401e3c4c  nop     dword ptr [rax+rax+00h]
0x1401e3c51  mov     esi, eax
0x1401e3c53  test    eax, eax
0x1401e3c55  jz      loc_1401E3D5F
0x1401e3c5b  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401e3c62  test    rcx, rcx
0x1401e3c65  jz      short loc_1401E3CCE
0x1401e3c67  cmp     [rcx+40h], edi
0x1401e3c6a  jz      short loc_1401E3CCE
0x1401e3c6c  cmp     dword ptr [rcx+38h], 2
0x1401e3c70  jl      short loc_1401E3CCE
0x1401e3c72  lea     rax, aConfigAdobject_2; "Config::AdObjectEditor::DeleteSubTree"
0x1401e3c79  mov     qword ptr [rsp+260h+var_210], rax
0x1401e3c7e  mov     dword ptr [rsp+260h+var_208], 0AFBh
0x1401e3c86  mov     dword ptr [rsp+260h+var_208+4], 2
0x1401e3c8e  lea     rax, aCfad; "CFAD"
0x1401e3c95  mov     [rsp+260h+var_200], rax
0x1401e3c9a  mov     ecx, esi; err
0x1401e3c9c  call    cs:__imp_ldap_err2stringW
0x1401e3ca3  nop     dword ptr [rax+rax+00h]
0x1401e3ca8  mov     [rbp+160h+arg_0], rax
0x1401e3caf  lea     r9, [rbp+160h+arg_0]
0x1401e3cb6  lea     r8, [rbp+160h+arg_8]
0x1401e3cbd  lea     rdx, aFailedToLdapDe; "Failed to ldap_delete_s(). dn:%ws Error"...
0x1401e3cc4  lea     rcx, [rsp+260h+var_210]
0x1401e3cc9  call    ??$DbgPrint@GPEBGPEAG@dbgobj@@QEAA_KPEBGAEBQEBGAEBQEAG@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort *>(ushort const *,ushort const * const &,ushort * const &)
0x1401e3cce  call    cs:__imp_GetCurrentThreadId
0x1401e3cd5  nop     dword ptr [rax+rax+00h]
0x1401e3cda  mov     ebx, eax
0x1401e3cdc  mov     ecx, esi; LdapError
0x1401e3cde  call    cs:__imp_LdapMapErrorToWin32
0x1401e3ce5  nop     dword ptr [rax+rax+00h]
0x1401e3cea  mov     [rsp+260h+var_220], rdi
0x1401e3cef  mov     [rsp+260h+var_228], ebx
0x1401e3cf3  mov     r14d, 0B02h
0x1401e3cf9  mov     dword ptr [rsp+260h+var_230], r14d
0x1401e3cfe  mov     qword ptr [rsp+260h+var_238], r12
0x1401e3d03  mov     [rsp+260h+var_240], r13
0x1401e3d08  mov     r9d, 1
0x1401e3d0e  xor     r8d, r8d
0x1401e3d11  mov     edx, eax
0x1401e3d13  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401e3d18  mov     rbx, rax
0x1401e3d1b  call    cs:__imp_GetCurrentThreadId
0x1401e3d22  nop     dword ptr [rax+rax+00h]
0x1401e3d27  mov     [rsp+260h+var_220], rdi
0x1401e3d2c  mov     [rsp+260h+var_228], eax
0x1401e3d30  mov     dword ptr [rsp+260h+var_230], r14d
0x1401e3d35  mov     qword ptr [rsp+260h+var_238], r12
0x1401e3d3a  mov     [rsp+260h+var_240], r13
0x1401e3d3f  mov     r9d, 5
0x1401e3d45  xor     r8d, r8d
0x1401e3d48  mov     edx, esi
0x1401e3d4a  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401e3d4f  mov     rdx, rax; struct FrsStatus *
0x1401e3d52  mov     rcx, rbx; this
0x1401e3d55  call    ?AppendError@FrsStatus@@QEAAPEAV1@PEAV1@@Z; FrsStatus::AppendError(FrsStatus *)
0x1401e3d5a  mov     rbx, rax
0x1401e3d5d  jmp     short loc_1401E3D62
0x1401e3d5f  mov     rbx, rdi
0x1401e3d62  lea     rcx, [rsp+260h+var_1F0]; this
0x1401e3d67  call    ??1AdObject@Config@@QEAA@XZ; Config::AdObject::~AdObject(void)
0x1401e3d6c  test    rbx, rbx
0x1401e3d6f  jz      short loc_1401E3DAA
0x1401e3d71  call    cs:__imp_GetCurrentThreadId
0x1401e3d78  nop     dword ptr [rax+rax+00h]
0x1401e3d7d  mov     [rsp+260h+var_220], rbx
0x1401e3d82  mov     [rsp+260h+var_228], eax
0x1401e3d86  mov     dword ptr [rsp+260h+var_230], 0B06h
0x1401e3d8e  mov     qword ptr [rsp+260h+var_238], r12
0x1401e3d93  mov     [rsp+260h+var_240], r13
0x1401e3d98  mov     r9d, [rbx]
0x1401e3d9b  mov     r8d, [rbx+8]
0x1401e3d9f  mov     edx, [rbx+4]
0x1401e3da2  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401e3da7  mov     rdi, rax
0x1401e3daa  lea     rcx, [rbp+160h+var_190]; this
0x1401e3dae  call    ??1AdQuery@Config@@UEAA@XZ; Config::AdQuery::~AdQuery(void)
0x1401e3db3  mov     rax, rdi
0x1401e3db6  lea     r11, [rsp+260h+var_20]
0x1401e3dbe  mov     rbx, [r11+40h]
0x1401e3dc2  mov     rsi, [r11+48h]
0x1401e3dc6  mov     rsp, r11
0x1401e3dc9  pop     r14
0x1401e3dcb  pop     r13
0x1401e3dcd  pop     r12
0x1401e3dcf  pop     rdi
0x1401e3dd0  pop     rbp
0x1401e3dd1  retn
```
