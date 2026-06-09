# CWin32StartupCommand::EnumRunKeyItems(MethodContext *,CInstance *,ushort const *,ushort const *)

- ea: `0x180031d4c`
- end: `0x18003221d`
- name: `?EnumRunKeyItems@CWin32StartupCommand@@IEAAJPEAVMethodContext@@PEAVCInstance@@PEBG2@Z`
- size: `1233`
- prototype: `int(CWin32StartupCommand *__hidden this, struct MethodContext *, struct CInstance *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180031b4c`
- `0x1800d38f0`

## callees

- `0x18000ab30`
- `0x180014c58`
- `0x180015c80`
- `0x180031d4c`
- `0x180032224`
- `0x18003a82c`
- `0x18003d7b0`
- `0x18007c6d8`
- `0x1800fc980`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003203d`
- `msvcrt!_wcsicmp` at `0x180032116`
- `msvcrt!_wcsicmp` at `0x18003203d`
- `msvcrt!_wcsicmp` at `0x180032116`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180031db1`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180031dbd`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180031dc9`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180031dd5`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180031de1`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180031ea5`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800320dd`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180031db1`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180031dbd`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180031dc9`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180031dd5`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180031de1`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180031ea5`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800320dd`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180031ede`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180032015`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180032069`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800320fc`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003210a`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180031ede`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180032015`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180032069`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800320fc`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003210a`
- `framedynos!?CreateNewInstance@Provider@@IEAAPEAVCInstance@@PEAVMethodContext@@@Z` at `0x180031f86`
- `framedynos!?CreateNewInstance@Provider@@IEAAPEAVCInstance@@PEAVMethodContext@@@Z` at `0x180031f86`
- `framedynos!?Commit@CInstance@@QEAAJXZ` at `0x1800320af`
- `framedynos!?Commit@CInstance@@QEAAJXZ` at `0x1800320af`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x180031f1f`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x180031f1f`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x180031ecb`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x180031ecb`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180031e19`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180031e99`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180031e19`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180031e99`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003217e`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800321a9`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800321b7`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003217e`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800321a9`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800321b7`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x180031ef4`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x180031ef4`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x1800320cd`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x18003212f`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x1800320cd`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x18003212f`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180031fcb`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180031fe0`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180031ff5`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18003200a`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180032028`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18003205e`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18003207c`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180031fcb`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180031fe0`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180031ff5`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18003200a`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180032028`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18003205e`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18003207c`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180031f10`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180031f10`
- `framedynos!?GetValueCount@CRegistry@@QEAAKXZ` at `0x180031f34`
- `framedynos!?GetValueCount@CRegistry@@QEAAKXZ` at `0x180031f34`
- `framedynos!?EnumerateAndGetValues@CRegistry@@QEAAJAEAKAEAPEAGAEAPEAE@Z` at `0x180031f63`
- `framedynos!?EnumerateAndGetValues@CRegistry@@QEAAJAEAKAEAPEAGAEAPEAE@Z` at `0x180031f63`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180031e0c`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180031e79`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180031ed3`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180031e0c`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180031e79`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180031ed3`
- `framedynos!?GetLocalInstancePath@Provider@@IEAA_NPEBVCInstance@@AEAVCHString@@@Z` at `0x180031e42`
- `framedynos!?GetLocalInstancePath@Provider@@IEAA_NPEBVCInstance@@AEAVCHString@@@Z` at `0x1800320f1`
- `framedynos!?GetLocalInstancePath@Provider@@IEAA_NPEBVCInstance@@AEAVCHString@@@Z` at `0x180031e42`
- `framedynos!?GetLocalInstancePath@Provider@@IEAA_NPEBVCInstance@@AEAVCHString@@@Z` at `0x1800320f1`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180031f2a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180032125`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180032158`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180032173`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003219e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800321c3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800321cf`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800321db`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800321e7`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800321f2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180031f2a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180032125`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180032158`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180032173`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003219e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800321c3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800321cf`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800321db`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800321e7`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800321f2`

## string_xrefs

- `0x180032000`: `Command`
- `0x180031d9f`: `Software\Microsoft\Windows\CurrentVersion\RunServices`
- `0x180032054`: `UserSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CWin32StartupCommand::EnumRunKeyItems(
        CWin32StartupCommand *this,
        struct MethodContext *a2,
        struct CInstance *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  Provider *v7; // rdi
  int v8; // esi
  int v9; // r13d
  __int64 v10; // rbx
  const wchar_t *v11; // rdx
  int i; // r14d
  const unsigned __int16 *v13; // rax
  int v14; // eax
  __int64 v15; // rax
  unsigned int ValueCount; // eax
  unsigned int v17; // ecx
  CInstance *NewInstance; // rbx
  int v19; // edi
  const unsigned __int16 *v20; // rax
  CInstance *v21; // rax
  const unsigned __int16 *v22; // rax
  const wchar_t *v23; // rdi
  const wchar_t *v24; // rax
  unsigned int v26; // [rsp+20h] [rbp-E0h] BYREF
  void *v27; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v28[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct CInstance *v29; // [rsp+38h] [rbp-C8h] BYREF
  Provider *v30; // [rsp+40h] [rbp-C0h]
  _BYTE v31[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *v32; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v33[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v34[8]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v35; // [rsp+68h] [rbp-98h]
  _BYTE v36[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v37[8]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v38; // [rsp+80h] [rbp-80h]
  _BYTE v39[8]; // [rsp+88h] [rbp-78h] BYREF
  struct MethodContext *v40; // [rsp+90h] [rbp-70h]
  _BYTE v41[8]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v42[2]; // [rsp+A0h] [rbp-60h]
  _BYTE v43[608]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v44[608]; // [rsp+310h] [rbp+210h] BYREF

  v40 = a2;
  v7 = this;
  v30 = this;
  v8 = 0;
  v42[0] = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Run";
  v42[1] = L"Software\\Microsoft\\Windows\\CurrentVersion\\RunServices";
  v9 = 0;
  CHString::CHString((CHString *)v41);
  CHString::CHString((CHString *)v34);
  CHString::CHString((CHString *)v37);
  CHString::CHString((CHString *)v36);
  CHString::CHString((CHString *)v31);
  if ( a5 )
  {
    CHString::operator=(v31, a5);
  }
  else if ( !GetAllUsersName((struct CHString *)v31) )
  {
    CHString::operator=(v31, L"Public");
  }
  CRegistry::CRegistry((CRegistry *)v44);
  v27 = 0;
  v32 = 0;
  if ( a3 )
  {
    Provider::GetLocalInstancePath(v7, a3, (struct CHString *)v36);
    v8 = -2147217406;
  }
  if ( a5 )
  {
    v10 = -2147483645;
    v11 = L"HKU\\";
  }
  else
  {
    v10 = -2147483646;
    v11 = L"HKLM\\";
  }
  v38 = v10;
  CHString::operator=(v34, v11);
  for ( i = 0; i < 1 && !v9; ++i )
  {
    CRegistry::CRegistry((CRegistry *)v43);
    CHString::CHString((CHString *)v28);
    if ( a4 )
      CHString::Format((CHString *)v28, L"%s\\%s", a4, v42[i]);
    else
      CHString::operator=(v28, v42[i]);
    v13 = (const unsigned __int16 *)CHString::operator unsigned short const *(v28);
    v14 = CRegistry::Open((CRegistry *)v43, (HKEY)v10, v13, 0x20019u);
    if ( v14 )
    {
      v8 = WinErrorToWBEMhResult(v14);
      CHString::~CHString((CHString *)v28);
      CRegistry::~CRegistry((CRegistry *)v43);
      break;
    }
    v15 = operator+(v39, v34, v28);
    CHString::operator=(v37, v15);
    CHString::~CHString((CHString *)v39);
    ValueCount = CRegistry::GetValueCount((CRegistry *)v43);
    v35 = ValueCount;
    v26 = 0;
    v17 = 0;
    while ( v17 < ValueCount )
    {
      if ( !CRegistry::EnumerateAndGetValues(
              (CRegistry *)v43,
              &v26,
              (unsigned __int16 **)&v27,
              (unsigned __int8 **)&v32) )
      {
        v29 = 0;
        if ( a3 )
        {
          v19 = 0;
          NewInstance = a3;
          v29 = a3;
          _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_AddRef(&v29);
        }
        else
        {
          NewInstance = Provider::CreateNewInstance(v7, v40);
          v29 = NewInstance;
          v19 = 1;
          if ( !NewInstance )
            _com_issue_error(-2147467261);
        }
        CInstance::SetCharSplat(NewInstance, L"Name", (const unsigned __int16 *)v27);
        CInstance::SetCharSplat(NewInstance, L"Description", (const unsigned __int16 *)v27);
        CInstance::SetCharSplat(NewInstance, L"Caption", (const unsigned __int16 *)v27);
        CInstance::SetCharSplat(NewInstance, L"Command", (const unsigned __int16 *)v32);
        v20 = (const unsigned __int16 *)CHString::operator unsigned short const *(v37);
        CInstance::SetCharSplat(NewInstance, L"Location", v20);
        if ( a4 && _wcsicmp(a4, L".DEFAULT") )
        {
          v21 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v29);
          CInstance::SetCharSplat(v21, L"UserSID", a4);
        }
        v22 = (const unsigned __int16 *)CHString::operator unsigned short const *(v31);
        CInstance::SetCharSplat(NewInstance, L"User", v22);
        operator delete(v27);
        v27 = 0;
        operator delete(v32);
        v32 = 0;
        if ( v19 )
        {
          v8 = CInstance::Commit(NewInstance);
          if ( v8 < 0 )
          {
            v9 = 1;
            CInstance::Release(NewInstance);
            goto LABEL_36;
          }
        }
        else
        {
          CHString::CHString((CHString *)v33);
          Provider::GetLocalInstancePath(v30, NewInstance, (struct CHString *)v33);
          v23 = (const wchar_t *)CHString::operator unsigned short const *(v36);
          v24 = (const wchar_t *)CHString::operator unsigned short const *(v33);
          if ( !_wcsicmp(v24, v23) )
          {
            v8 = 0;
            v9 = 1;
            CHString::~CHString((CHString *)v33);
            _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v29);
LABEL_36:
            v7 = v30;
            break;
          }
          CHString::~CHString((CHString *)v33);
        }
        CInstance::Release(NewInstance);
        v7 = v30;
      }
      v17 = ++v26;
      ValueCount = v35;
    }
    CHString::~CHString((CHString *)v28);
    CRegistry::~CRegistry((CRegistry *)v43);
    v10 = v38;
  }
  CRegistry::~CRegistry((CRegistry *)v44);
  CHString::~CHString((CHString *)v31);
  CHString::~CHString((CHString *)v36);
  CHString::~CHString((CHString *)v37);
  CHString::~CHString((CHString *)v34);
  CHString::~CHString((CHString *)v41);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180031d4c  push    rbp
0x180031d4e  push    rbx
0x180031d4f  push    rsi
0x180031d50  push    rdi
0x180031d51  push    r12
0x180031d53  push    r13
0x180031d55  push    r14
0x180031d57  push    r15
0x180031d59  lea     rbp, [rsp-488h]
0x180031d61  sub     rsp, 588h
0x180031d68  mov     rax, cs:__security_cookie
0x180031d6f  xor     rax, rsp
0x180031d72  mov     [rbp+4C0h+var_50], rax
0x180031d79  mov     r12, r9
0x180031d7c  mov     r15, r8
0x180031d7f  mov     [rbp+4C0h+var_530], rdx
0x180031d83  mov     rdi, rcx
0x180031d86  mov     [rsp+5C0h+var_580], rcx
0x180031d8b  mov     rbx, [rbp+4C0h+arg_20]
0x180031d92  xor     esi, esi
0x180031d94  lea     rax, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180031d9b  mov     [rbp+4C0h+var_520], rax
0x180031d9f  lea     rax, aSoftwareMicros_19; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180031da6  mov     [rbp+4C0h+var_518], rax
0x180031daa  xor     r13d, r13d
0x180031dad  lea     rcx, [rbp+4C0h+var_528]
0x180031db1  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180031db7  nop
0x180031db8  lea     rcx, [rsp+5C0h+var_560]
0x180031dbd  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180031dc3  nop
0x180031dc4  lea     rcx, [rsp+5C0h+var_548]
0x180031dc9  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180031dcf  nop
0x180031dd0  lea     rcx, [rsp+5C0h+var_550]
0x180031dd5  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180031ddb  nop
0x180031ddc  lea     rcx, [rsp+5C0h+var_578]
0x180031de1  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180031de7  nop
0x180031de8  lea     rcx, [rsp+5C0h+var_578]; struct CHString *
0x180031ded  test    rbx, rbx
0x180031df0  jz      short loc_180031DF7
0x180031df2  mov     rdx, rbx
0x180031df5  jmp     short loc_180031E0C
0x180031df7  call    ?GetAllUsersName@@YA_NAEAVCHString@@@Z; GetAllUsersName(CHString &)
0x180031dfc  test    al, al
0x180031dfe  jnz     short loc_180031E12
0x180031e00  lea     rdx, aPublic_1; "Public"
0x180031e07  lea     rcx, [rsp+5C0h+var_578]
0x180031e0c  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x180031e12  lea     rcx, [rbp+4C0h+var_2B0]
0x180031e19  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x180031e1f  nop
0x180031e20  mov     [rsp+5C0h+var_598], 0
0x180031e29  mov     [rsp+5C0h+var_570], 0
0x180031e32  test    r15, r15
0x180031e35  jz      short loc_180031E4D
0x180031e37  lea     r8, [rsp+5C0h+var_550]
0x180031e3c  mov     rdx, r15
0x180031e3f  mov     rcx, rdi
0x180031e42  call    cs:__imp_?GetLocalInstancePath@Provider@@IEAA_NPEBVCInstance@@AEAVCHString@@@Z; Provider::GetLocalInstancePath(CInstance const *,CHString &)
0x180031e48  mov     esi, 80041002h
0x180031e4d  lea     rcx, [rsp+5C0h+var_560]
0x180031e52  test    rbx, rbx
0x180031e55  jnz     short loc_180031E67
0x180031e57  mov     rbx, 0FFFFFFFF80000002h
0x180031e5e  lea     rdx, aHklm; "HKLM\\"
0x180031e65  jmp     short loc_180031E75
0x180031e67  mov     rbx, 0FFFFFFFF80000003h
0x180031e6e  lea     rdx, aHku_0; "HKU\\"
0x180031e75  mov     [rbp+4C0h+var_540], rbx
0x180031e79  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x180031e7f  xor     r14d, r14d
0x180031e82  cmp     r14d, 1
0x180031e86  jge     loc_1800321B0
0x180031e8c  test    r13d, r13d
0x180031e8f  jnz     loc_1800321B0
0x180031e95  lea     rcx, [rbp+4C0h+var_510]
0x180031e99  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x180031e9f  nop
0x180031ea0  lea     rcx, [rsp+5C0h+var_590]
0x180031ea5  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180031eab  nop
0x180031eac  movsxd  rax, r14d
0x180031eaf  mov     rdx, [rbp+rax*8+4C0h+var_520]
0x180031eb4  lea     rcx, [rsp+5C0h+var_590]
0x180031eb9  test    r12, r12
0x180031ebc  jz      short loc_180031ED3
0x180031ebe  mov     r9, rdx
0x180031ec1  mov     r8, r12
0x180031ec4  lea     rdx, aSS_0; "%s\\%s"
0x180031ecb  call    cs:__imp_?Format@CHString@@QEAAXPEBGZZ; CHString::Format(ushort const *,...)
0x180031ed1  jmp     short loc_180031ED9
0x180031ed3  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x180031ed9  lea     rcx, [rsp+5C0h+var_590]
0x180031ede  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180031ee4  mov     r8, rax
0x180031ee7  mov     r9d, 20019h
0x180031eed  mov     rdx, rbx
0x180031ef0  lea     rcx, [rbp+4C0h+var_510]
0x180031ef4  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x180031efa  test    eax, eax
0x180031efc  jnz     loc_180032190
0x180031f02  lea     r8, [rsp+5C0h+var_590]
0x180031f07  lea     rdx, [rsp+5C0h+var_560]
0x180031f0c  lea     rcx, [rbp+4C0h+var_538]
0x180031f10  call    cs:__imp_??H@YA?AVCHString@@AEBV0@0@Z; operator+(CHString const &,CHString const &)
0x180031f16  nop
0x180031f17  mov     rdx, rax
0x180031f1a  lea     rcx, [rsp+5C0h+var_548]
0x180031f1f  call    cs:__imp_??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x180031f25  nop
0x180031f26  lea     rcx, [rbp+4C0h+var_538]
0x180031f2a  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180031f30  lea     rcx, [rbp+4C0h+var_510]
0x180031f34  call    cs:__imp_?GetValueCount@CRegistry@@QEAAKXZ; CRegistry::GetValueCount(void)
0x180031f3a  mov     [rsp+5C0h+var_558], eax
0x180031f3e  mov     [rsp+5C0h+var_5A0], 0
0x180031f46  xor     ecx, ecx
0x180031f48  cmp     ecx, eax
0x180031f4a  jnb     loc_18003216E
0x180031f50  lea     r9, [rsp+5C0h+var_570]
0x180031f55  lea     r8, [rsp+5C0h+var_598]
0x180031f5a  lea     rdx, [rsp+5C0h+var_5A0]
0x180031f5f  lea     rcx, [rbp+4C0h+var_510]
0x180031f63  call    cs:__imp_?EnumerateAndGetValues@CRegistry@@QEAAJAEAKAEAPEAGAEAPEAE@Z; CRegistry::EnumerateAndGetValues(ulong &,ushort * &,uchar * &)
0x180031f69  test    eax, eax
0x180031f6b  jnz     loc_18003213A
0x180031f71  mov     [rsp+5C0h+var_588], 0
0x180031f7a  test    r15, r15
0x180031f7d  jnz     short loc_180031FA8
0x180031f7f  mov     rdx, [rbp+4C0h+var_530]
0x180031f83  mov     rcx, rdi
0x180031f86  call    cs:__imp_?CreateNewInstance@Provider@@IEAAPEAVCInstance@@PEAVMethodContext@@@Z; Provider::CreateNewInstance(MethodContext *)
0x180031f8c  mov     rbx, rax
0x180031f8f  mov     [rsp+5C0h+var_588], rax
0x180031f94  lea     edi, [r15+1]
0x180031f98  test    rax, rax
0x180031f9b  jnz     short loc_180031FBC
0x180031f9d  mov     ecx, 80004003h; int
0x180031fa2  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180031fa8  xor     edi, edi
0x180031faa  mov     rbx, r15
0x180031fad  mov     [rsp+5C0h+var_588], rbx
0x180031fb2  lea     rcx, [rsp+5C0h+var_588]
0x180031fb7  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_AddRef(void)
0x180031fbc  mov     r8, [rsp+5C0h+var_598]
0x180031fc1  lea     rdx, aName; "Name"
0x180031fc8  mov     rcx, rbx
0x180031fcb  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180031fd1  mov     r8, [rsp+5C0h+var_598]
0x180031fd6  lea     rdx, aDescription; "Description"
0x180031fdd  mov     rcx, rbx
0x180031fe0  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180031fe6  mov     r8, [rsp+5C0h+var_598]
0x180031feb  lea     rdx, aCaption; "Caption"
0x180031ff2  mov     rcx, rbx
0x180031ff5  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180031ffb  mov     r8, [rsp+5C0h+var_570]
0x180032000  lea     rdx, aCommand; "Command"
0x180032007  mov     rcx, rbx
0x18003200a  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180032010  lea     rcx, [rsp+5C0h+var_548]
0x180032015  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18003201b  mov     r8, rax
0x18003201e  lea     rdx, aLocation; "Location"
0x180032025  mov     rcx, rbx
0x180032028  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18003202e  test    r12, r12
0x180032031  jz      short loc_180032064
0x180032033  lea     rdx, aDefault; ".DEFAULT"
0x18003203a  mov     rcx, r12; String1
0x18003203d  call    cs:__imp__wcsicmp
0x180032043  test    eax, eax
0x180032045  jz      short loc_180032064
0x180032047  lea     rcx, [rsp+5C0h+var_588]
0x18003204c  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x180032051  mov     r8, r12
0x180032054  lea     rdx, aUsersid; "UserSID"
0x18003205b  mov     rcx, rax
0x18003205e  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180032064  lea     rcx, [rsp+5C0h+var_578]
0x180032069  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18003206f  mov     r8, rax
0x180032072  lea     rdx, aUser; "User"
0x180032079  mov     rcx, rbx
0x18003207c  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180032082  mov     rcx, [rsp+5C0h+var_598]; void *
0x180032087  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003208c  mov     [rsp+5C0h+var_598], 0
0x180032095  mov     rcx, [rsp+5C0h+var_570]; void *
0x18003209a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003209f  mov     [rsp+5C0h+var_570], 0
0x1800320a8  test    edi, edi
0x1800320aa  jz      short loc_1800320D8
0x1800320ac  mov     rcx, rbx
0x1800320af  call    cs:__imp_?Commit@CInstance@@QEAAJXZ; CInstance::Commit(void)
0x1800320b5  mov     esi, eax
0x1800320b7  test    eax, eax
0x1800320b9  jns     short loc_18003212C
0x1800320bb  mov     r13d, 1
0x1800320c1  test    rbx, rbx
0x1800320c4  jz      loc_180032169
0x1800320ca  mov     rcx, rbx
0x1800320cd  call    cs:__imp_?Release@CInstance@@QEAAJXZ; CInstance::Release(void)
0x1800320d3  jmp     loc_180032169
0x1800320d8  lea     rcx, [rsp+5C0h+var_568]
0x1800320dd  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800320e3  nop
0x1800320e4  lea     r8, [rsp+5C0h+var_568]
0x1800320e9  mov     rdx, rbx
0x1800320ec  mov     rcx, [rsp+5C0h+var_580]
0x1800320f1  call    cs:__imp_?GetLocalInstancePath@Provider@@IEAA_NPEBVCInstance@@AEAVCHString@@@Z; Provider::GetLocalInstancePath(CInstance const *,CHString &)
0x1800320f7  lea     rcx, [rsp+5C0h+var_550]
0x1800320fc  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180032102  mov     rdi, rax
0x180032105  lea     rcx, [rsp+5C0h+var_568]
0x18003210a  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180032110  mov     rdx, rdi; String2
0x180032113  mov     rcx, rax; String1
0x180032116  call    cs:__imp__wcsicmp
0x18003211c  test    eax, eax
0x18003211e  jz      short loc_18003214D
0x180032120  lea     rcx, [rsp+5C0h+var_568]
0x180032125  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18003212b  nop
0x18003212c  mov     rcx, rbx
0x18003212f  call    cs:__imp_?Release@CInstance@@QEAAJXZ; CInstance::Release(void)
0x180032135  mov     rdi, [rsp+5C0h+var_580]
0x18003213a  mov     ecx, [rsp+5C0h+var_5A0]
0x18003213e  inc     ecx
0x180032140  mov     [rsp+5C0h+var_5A0], ecx
0x180032144  mov     eax, [rsp+5C0h+var_558]
0x180032148  jmp     loc_180031F48
0x18003214d  xor     esi, esi
0x18003214f  lea     r13d, [rsi+1]
0x180032153  lea     rcx, [rsp+5C0h+var_568]
0x180032158  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18003215e  nop
0x18003215f  lea     rcx, [rsp+5C0h+var_588]
0x180032164  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x180032169  mov     rdi, [rsp+5C0h+var_580]
0x18003216e  lea     rcx, [rsp+5C0h+var_590]
0x180032173  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180032179  nop
0x18003217a  lea     rcx, [rbp+4C0h+var_510]
0x18003217e  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x180032184  inc     r14d
0x180032187  mov     rbx, [rbp+4C0h+var_540]
0x18003218b  jmp     loc_180031E82
0x180032190  mov     ecx, eax; int
0x180032192  call    ?WinErrorToWBEMhResult@@YAJJ@Z; WinErrorToWBEMhResult(long)
0x180032197  mov     esi, eax
0x180032199  lea     rcx, [rsp+5C0h+var_590]
0x18003219e  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800321a4  nop
0x1800321a5  lea     rcx, [rbp+4C0h+var_510]
0x1800321a9  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x1800321af  nop
0x1800321b0  lea     rcx, [rbp+4C0h+var_2B0]
0x1800321b7  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x1800321bd  nop
0x1800321be  lea     rcx, [rsp+5C0h+var_578]
0x1800321c3  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800321c9  nop
0x1800321ca  lea     rcx, [rsp+5C0h+var_550]
0x1800321cf  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800321d5  nop
0x1800321d6  lea     rcx, [rsp+5C0h+var_548]
0x1800321db  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800321e1  nop
0x1800321e2  lea     rcx, [rsp+5C0h+var_560]
0x1800321e7  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800321ed  nop
0x1800321ee  lea     rcx, [rbp+4C0h+var_528]
0x1800321f2  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800321f8  mov     eax, esi
0x1800321fa  mov     rcx, [rbp+4C0h+var_50]
0x180032201  xor     rcx, rsp; StackCookie
0x180032204  call    __security_check_cookie
0x180032209  add     rsp, 588h
0x180032210  pop     r15
0x180032212  pop     r14
0x180032214  pop     r13
0x180032216  pop     r12
0x180032218  pop     rdi
0x180032219  pop     rsi
0x18003221a  pop     rbx
0x18003221b  pop     rbp
0x18003221c  retn
```
