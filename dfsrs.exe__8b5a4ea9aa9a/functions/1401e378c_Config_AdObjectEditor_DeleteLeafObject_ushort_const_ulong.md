# Config::AdObjectEditor::DeleteLeafObject(ushort const *,ulong)

- ea: `0x1401e378c`
- end: `0x1401e3a01`
- name: `?DeleteLeafObject@AdObjectEditor@Config@@QEAAPEAVFrsStatus@@PEBGK@Z`
- size: `629`
- prototype: `struct FrsStatus *(Config::AdObjectEditor *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1401f8f08`
- `0x140204f6c`

## callees

- `0x140019358`
- `0x1401b90b4`
- `0x1401b9494`
- `0x1401de240`
- `0x1401de7cc`
- `0x1401e378c`
- `0x1401f3320`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401e3833`
- `KERNEL32!GetCurrentThreadId` at `0x1401e390b`
- `KERNEL32!GetCurrentThreadId` at `0x1401e3957`
- `KERNEL32!GetCurrentThreadId` at `0x1401e399e`
- `KERNEL32!GetCurrentThreadId` at `0x1401e3833`
- `KERNEL32!GetCurrentThreadId` at `0x1401e390b`
- `KERNEL32!GetCurrentThreadId` at `0x1401e3957`
- `KERNEL32!GetCurrentThreadId` at `0x1401e399e`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1401e391c`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1401e391c`
- `WLDAP32!__imp_ldap_delete_sW` at `0x1401e386b`
- `WLDAP32!__imp_ldap_delete_sW` at `0x1401e386b`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1401e38c4`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1401e38c4`

## string_xrefs

- `0x1401e3817`: `Config::AdObjectEditor::DeleteLeafObject`
- `0x1401e3899`: `Config::AdObjectEditor::DeleteLeafObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct FrsStatus *__fastcall Config::AdObjectEditor::DeleteLeafObject(
        struct Config::AdSession **this,
        unsigned __int16 *a2)
{
  __int64 v4; // rdi
  struct FrsStatus *started; // rbx
  __int64 v6; // rcx
  __int64 v7; // rax
  ULONG v8; // r14d
  DWORD v9; // ebx
  ULONG v10; // eax
  __int64 v11; // rcx
  FrsStatus *v12; // rbx
  DWORD v13; // eax
  __int64 v14; // rcx
  struct FrsStatus *v15; // rax
  __int64 v16; // rcx
  DWORD CurrentThreadId; // [rsp+38h] [rbp-C8h]
  DWORD v19; // [rsp+38h] [rbp-C8h]
  const wchar_t *v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+58h] [rbp-A8h]
  int v22; // [rsp+5Ch] [rbp-A4h]
  const wchar_t *v23; // [rsp+60h] [rbp-A0h]
  _BYTE v24[88]; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v26; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 *v27; // [rsp+228h] [rbp+128h] BYREF

  Config::AdQuery::AdQuery((Config::AdQuery *)v24);
  v26 = L"distinguishedName";
  v4 = 0;
  started = Config::AdQuery::StartSearch(
              (Config::AdQuery *)v24,
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
    goto LABEL_12;
  if ( v25 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = FrsStatusList::PushNewError(
           v6,
           4307,
           0,
           1,
           "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
           "Config::AdObjectEditor::DeleteLeafObject",
           3061,
           CurrentThreadId,
           0);
LABEL_13:
    v4 = v7;
    goto LABEL_14;
  }
  v8 = ldap_delete_sW(*(LDAP **)this[1], a2);
  if ( v8 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v20 = L"Config::AdObjectEditor::DeleteLeafObject";
      v21 = 3066;
      v22 = 2;
      v23 = L"CFAD";
      v26 = ldap_err2stringW(v8);
      if ( !a2 )
        a2 = L"<null>";
      v27 = a2;
      dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
        &v20,
        L"Failed to ldap_add_s(). dn:%ws Error:%?",
        &v27,
        &v26);
    }
    v9 = GetCurrentThreadId();
    v10 = LdapMapErrorToWin32(v8);
    v12 = (FrsStatus *)FrsStatusList::PushNewError(
                         v11,
                         v10,
                         0,
                         1,
                         "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                         "Config::AdObjectEditor::DeleteLeafObject",
                         3072,
                         v9,
                         0);
    v13 = GetCurrentThreadId();
    v15 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v14,
                                v8,
                                0,
                                5,
                                "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                                "Config::AdObjectEditor::DeleteLeafObject",
                                3072,
                                v13,
                                0);
    started = FrsStatus::AppendError(v12, v15);
    if ( started )
    {
LABEL_12:
      v19 = GetCurrentThreadId();
      v7 = FrsStatusList::PushNewError(
             v16,
             *((unsigned int *)started + 1),
             *((unsigned int *)started + 2),
             *(unsigned int *)started,
             "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
             "Config::AdObjectEditor::DeleteLeafObject",
             3075,
             v19,
             started);
      goto LABEL_13;
    }
  }
LABEL_14:
  Config::AdQuery::~AdQuery((Config::AdQuery *)v24);
  return (struct FrsStatus *)v4;
}

```

## disassembly

```asm
0x1401e378c  mov     [rsp-8+arg_8], rbx
0x1401e3791  mov     [rsp-8+arg_10], rsi
0x1401e3796  push    rbp
0x1401e3797  push    rdi
0x1401e3798  push    r12
0x1401e379a  push    r13
0x1401e379c  push    r14
0x1401e379e  lea     rbp, [rsp-0E0h]
0x1401e37a6  sub     rsp, 1E0h
0x1401e37ad  mov     rsi, rdx
0x1401e37b0  mov     r14, rcx
0x1401e37b3  lea     rcx, [rsp+200h+var_190]; this
0x1401e37b8  call    ??0AdQuery@Config@@QEAA@XZ; Config::AdQuery::AdQuery(void)
0x1401e37bd  nop
0x1401e37be  lea     rax, aDistinguishedn_0; "distinguishedName"
0x1401e37c5  mov     [rbp+100h+arg_0], rax
0x1401e37cc  mov     [rsp+200h+var_1B8], 8CA0h; unsigned int
0x1401e37d4  lea     rax, aObjectcategory_6; "(objectCategory=*)"
0x1401e37db  mov     [rsp+200h+var_1C0], rax; unsigned __int16 *
0x1401e37e0  xor     edi, edi
0x1401e37e2  mov     [rsp+200h+var_1C8], edi; unsigned int
0x1401e37e6  mov     [rsp+200h+var_1D0], rdi; unsigned __int16 **
0x1401e37eb  mov     [rsp+200h+var_1D8], 1; unsigned int
0x1401e37f3  lea     rax, [rbp+100h+arg_0]
0x1401e37fa  mov     [rsp+200h+var_1E0], rax; unsigned __int16 **
0x1401e37ff  lea     r9d, [rdi+1]; unsigned int
0x1401e3803  mov     r8, rsi; unsigned __int16 *
0x1401e3806  mov     rdx, [r14+8]; struct Config::AdSession *
0x1401e380a  lea     rcx, [rsp+200h+var_190]; this
0x1401e380f  call    ?StartSearch@AdQuery@Config@@QEAAPEAVFrsStatus@@PEAVAdSession@2@PEBGKPEAPEBGK2K1K@Z; Config::AdQuery::StartSearch(Config::AdSession *,ushort const *,ulong,ushort const * *,ulong,ushort const * *,ulong,ushort const *,ulong)
0x1401e3814  mov     rbx, rax
0x1401e3817  lea     r12, aConfigAdobject_5; "Config::AdObjectEditor::DeleteLeafObjec"...
0x1401e381e  lea     r13, aBaseFsRemotefs_10; "base\\fs\\remotefs\\frs\\src\\ad\\ad.cp"...
0x1401e3825  test    rax, rax
0x1401e3828  jnz     loc_1401E399E
0x1401e382e  cmp     [rbp+100h+var_138], edi
0x1401e3831  jbe     short loc_1401E3861
0x1401e3833  call    cs:__imp_GetCurrentThreadId
0x1401e383a  nop     dword ptr [rax+rax+00h]
0x1401e383f  mov     [rsp+200h+var_1C0], rdi
0x1401e3844  mov     [rsp+200h+var_1C8], eax
0x1401e3848  mov     dword ptr [rsp+200h+var_1D0], 0BF5h
0x1401e3850  lea     r9d, [rdi+1]
0x1401e3854  xor     r8d, r8d
0x1401e3857  mov     edx, 10D3h
0x1401e385c  jmp     loc_1401E39C5
0x1401e3861  mov     rcx, [r14+8]
0x1401e3865  mov     rdx, rsi; dn
0x1401e3868  mov     rcx, [rcx]; ld
0x1401e386b  call    cs:__imp_ldap_delete_sW
0x1401e3872  nop     dword ptr [rax+rax+00h]
0x1401e3877  mov     r14d, eax
0x1401e387a  test    eax, eax
0x1401e387c  jz      loc_1401E39D7
0x1401e3882  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401e3889  test    rcx, rcx
0x1401e388c  jz      short loc_1401E390B
0x1401e388e  cmp     [rcx+40h], edi
0x1401e3891  jz      short loc_1401E390B
0x1401e3893  cmp     dword ptr [rcx+38h], 2
0x1401e3897  jl      short loc_1401E390B
0x1401e3899  lea     rax, aConfigAdobject_6; "Config::AdObjectEditor::DeleteLeafObjec"...
0x1401e38a0  mov     [rsp+200h+var_1B0], rax
0x1401e38a5  mov     [rsp+200h+var_1A8], 0BFAh
0x1401e38ad  mov     [rsp+200h+var_1A4], 2
0x1401e38b5  lea     rax, aCfad; "CFAD"
0x1401e38bc  mov     [rsp+200h+var_1A0], rax
0x1401e38c1  mov     ecx, r14d; err
0x1401e38c4  call    cs:__imp_ldap_err2stringW
0x1401e38cb  nop     dword ptr [rax+rax+00h]
0x1401e38d0  mov     [rbp+100h+arg_0], rax
0x1401e38d7  lea     rax, aNull; "<null>"
0x1401e38de  test    rsi, rsi
0x1401e38e1  cmovz   rsi, rax
0x1401e38e5  mov     [rbp+100h+arg_18], rsi
0x1401e38ec  lea     r9, [rbp+100h+arg_0]
0x1401e38f3  lea     r8, [rbp+100h+arg_18]
0x1401e38fa  lea     rdx, aFailedToLdapAd; "Failed to ldap_add_s(). dn:%ws Error:%?"
0x1401e3901  lea     rcx, [rsp+200h+var_1B0]
0x1401e3906  call    ??$DbgPrint@GPEBGPEAG@dbgobj@@QEAA_KPEBGAEBQEBGAEBQEAG@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort *>(ushort const *,ushort const * const &,ushort * const &)
0x1401e390b  call    cs:__imp_GetCurrentThreadId
0x1401e3912  nop     dword ptr [rax+rax+00h]
0x1401e3917  mov     ebx, eax
0x1401e3919  mov     ecx, r14d; LdapError
0x1401e391c  call    cs:__imp_LdapMapErrorToWin32
0x1401e3923  nop     dword ptr [rax+rax+00h]
0x1401e3928  mov     [rsp+200h+var_1C0], rdi
0x1401e392d  mov     [rsp+200h+var_1C8], ebx
0x1401e3931  mov     esi, 0C00h
0x1401e3936  mov     dword ptr [rsp+200h+var_1D0], esi
0x1401e393a  mov     qword ptr [rsp+200h+var_1D8], r12
0x1401e393f  mov     [rsp+200h+var_1E0], r13
0x1401e3944  mov     r9d, 1
0x1401e394a  xor     r8d, r8d
0x1401e394d  mov     edx, eax
0x1401e394f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401e3954  mov     rbx, rax
0x1401e3957  call    cs:__imp_GetCurrentThreadId
0x1401e395e  nop     dword ptr [rax+rax+00h]
0x1401e3963  mov     [rsp+200h+var_1C0], rdi
0x1401e3968  mov     [rsp+200h+var_1C8], eax
0x1401e396c  mov     dword ptr [rsp+200h+var_1D0], esi
0x1401e3970  mov     qword ptr [rsp+200h+var_1D8], r12
0x1401e3975  mov     [rsp+200h+var_1E0], r13
0x1401e397a  mov     r9d, 5
0x1401e3980  xor     r8d, r8d
0x1401e3983  mov     edx, r14d
0x1401e3986  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401e398b  mov     rdx, rax; struct FrsStatus *
0x1401e398e  mov     rcx, rbx; this
0x1401e3991  call    ?AppendError@FrsStatus@@QEAAPEAV1@PEAV1@@Z; FrsStatus::AppendError(FrsStatus *)
0x1401e3996  mov     rbx, rax
0x1401e3999  test    rax, rax
0x1401e399c  jz      short loc_1401E39D7
0x1401e399e  call    cs:__imp_GetCurrentThreadId
0x1401e39a5  nop     dword ptr [rax+rax+00h]
0x1401e39aa  mov     [rsp+200h+var_1C0], rbx
0x1401e39af  mov     [rsp+200h+var_1C8], eax
0x1401e39b3  mov     dword ptr [rsp+200h+var_1D0], 0C03h
0x1401e39bb  mov     r9d, [rbx]
0x1401e39be  mov     r8d, [rbx+8]
0x1401e39c2  mov     edx, [rbx+4]
0x1401e39c5  mov     qword ptr [rsp+200h+var_1D8], r12
0x1401e39ca  mov     [rsp+200h+var_1E0], r13
0x1401e39cf  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401e39d4  mov     rdi, rax
0x1401e39d7  lea     rcx, [rsp+200h+var_190]; this
0x1401e39dc  call    ??1AdQuery@Config@@UEAA@XZ; Config::AdQuery::~AdQuery(void)
0x1401e39e1  mov     rax, rdi
0x1401e39e4  lea     r11, [rsp+200h+var_20]
0x1401e39ec  mov     rbx, [r11+38h]
0x1401e39f0  mov     rsi, [r11+40h]
0x1401e39f4  mov     rsp, r11
0x1401e39f7  pop     r14
0x1401e39f9  pop     r13
0x1401e39fb  pop     r12
0x1401e39fd  pop     rdi
0x1401e39fe  pop     rbp
0x1401e39ff  retn
```
