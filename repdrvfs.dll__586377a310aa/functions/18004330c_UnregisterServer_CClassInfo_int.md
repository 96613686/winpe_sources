# UnregisterServer(CClassInfo *,int)

- ea: `0x18004330c`
- end: `0x1800435c5`
- name: `?UnregisterServer@@YAJPEAUCClassInfo@@H@Z`
- size: `697`
- prototype: `__int64 __fastcall(struct CClassInfo *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800439f0`

## callees

- `0x1800013c8`
- `0x180024ca0`
- `0x180029fbc`
- `0x1800429e4`
- `0x18004330c`
- `0x180043b78`
- `0x1800440a4`
- `0x180044420`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18004335f`
- `wbemcomn!GetMemLogObject` at `0x180043426`
- `wbemcomn!GetMemLogObject` at `0x180043476`
- `wbemcomn!GetMemLogObject` at `0x180043513`
- `wbemcomn!GetMemLogObject` at `0x180043564`
- `wbemcomn!GetMemLogObject` at `0x18004335f`
- `wbemcomn!GetMemLogObject` at `0x180043426`
- `wbemcomn!GetMemLogObject` at `0x180043476`
- `wbemcomn!GetMemLogObject` at `0x180043513`
- `wbemcomn!GetMemLogObject` at `0x180043564`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004336a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043432`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043482`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004351f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043570`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004336a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043432`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043482`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004351f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180043570`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180043345`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180043345`

## string_xrefs

- `0x1800434cd`: `SOFTWARE\Classes\CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UnregisterServer(const GUID *const *a1)
{
  __int64 v1; // rdx
  unsigned __int16 *v2; // r9
  int PathString; // ebx
  int v4; // r8d
  CMemoryLog *v5; // rax
  int v7; // r14d
  int v8; // r14d
  CMemoryLog *v9; // rax
  int v10; // r8d
  int v11; // r8d
  CMemoryLog *MemLogObject; // rax
  int v13; // r14d
  int v14; // r14d
  CMemoryLog *v15; // rax
  int v16; // r8d
  CMemoryLog *v17; // rax
  int v18; // r8d
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[8]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 (__fastcall *v21)(_QWORD); // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+48h] [rbp-B8h]
  OLECHAR sz[128]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v24[256]; // [rsp+150h] [rbp+50h] BYREF

  StringFromGUID2(a1[3], sz, 128);
  PathString = CreatePathString(v24, v1, sz, v2);
  if ( PathString >= 0 )
  {
    v19 = 0;
    v7 = DLRegOpenKeyExW(-2147483646, (unsigned int)v24, v4, 0x2000000, (__int64)&v19);
    if ( v7 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v7);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v11, v7, (__int64)v24);
      }
    }
    else
    {
      v20[0] = 0;
      v21 = DLRegCloseKey;
      v22 = v19;
      v8 = DLRegDeleteKeyW(v19, L"InProcServer32");
      if ( v8 )
      {
        v9 = GetMemLogObject();
        CMemoryLog::Write(v9, v8);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v10, v8, (__int64)v24);
        }
      }
      ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v20);
    }
    v13 = DLRegOpenKeyExW(-2147483646, (unsigned int)L"SOFTWARE\\Classes\\CLSID", v11, 0x2000000, (__int64)&v19);
    if ( v13 )
    {
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, v13);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v18, v13, (__int64)L"SOFTWARE\\Classes\\CLSID");
      }
    }
    else
    {
      v20[0] = 0;
      v21 = DLRegCloseKey;
      v22 = v19;
      v14 = DLRegDeleteKeyW(v19, sz);
      if ( v14 )
      {
        v15 = GetMemLogObject();
        CMemoryLog::Write(v15, v14);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v16, v14, (__int64)sz);
        }
      }
      ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v20);
    }
    return 0;
  }
  else
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, PathString);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids, sz);
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18004330c  push    rbp
0x18004330e  push    rbx
0x18004330f  push    rsi
0x180043310  push    r12
0x180043312  push    r13
0x180043314  push    r14
0x180043316  lea     rbp, [rsp-268h]
0x18004331e  sub     rsp, 368h
0x180043325  mov     rax, cs:__security_cookie
0x18004332c  xor     rax, rsp
0x18004332f  mov     [rbp+290h+var_40], rax
0x180043336  mov     r8d, 80h; cchMax
0x18004333c  lea     rdx, [rsp+390h+sz]; lpsz
0x180043341  mov     rcx, [rcx+18h]; rguid
0x180043345  call    cs:__imp_StringFromGUID2
0x18004334b  lea     r8, [rsp+390h+sz]; unsigned __int16 *
0x180043350  lea     rcx, [rbp+290h+var_240]; unsigned __int16 *
0x180043354  call    ?CreatePathString@@YAJPEAGH00@Z; CreatePathString(ushort *,int,ushort *,ushort *)
0x180043359  mov     ebx, eax
0x18004335b  test    eax, eax
0x18004335d  jns     short loc_1800433B4
0x18004335f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180043365  mov     edx, ebx
0x180043367  mov     rcx, rax
0x18004336a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180043370  lea     rsi, WPP_GLOBAL_Control
0x180043377  mov     rcx, cs:WPP_GLOBAL_Control
0x18004337e  cmp     rcx, rsi
0x180043381  jz      short loc_1800433AA
0x180043383  test    byte ptr [rcx+1Ch], 1
0x180043387  jz      short loc_1800433AA
0x180043389  mov     bl, 2
0x18004338b  cmp     [rcx+19h], bl
0x18004338e  jb      short loc_1800433AA
0x180043390  mov     edx, 16h
0x180043395  lea     r9, [rsp+390h+sz]
0x18004339a  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x1800433a1  mov     rcx, [rcx+10h]
0x1800433a5  call    WPP_SF_S
0x1800433aa  mov     eax, 80004005h
0x1800433af  jmp     loc_1800435A5
0x1800433b4  mov     [rsp+390h+var_360], 0
0x1800433bd  lea     rax, [rsp+390h+var_360]
0x1800433c2  mov     [rsp+390h+var_370], rax
0x1800433c7  mov     r12d, 2000000h
0x1800433cd  mov     r9d, r12d
0x1800433d0  lea     rdx, [rbp+290h+var_240]
0x1800433d4  mov     rcx, 0FFFFFFFF80000002h
0x1800433db  call    DLRegOpenKeyExW
0x1800433e0  mov     r14d, eax
0x1800433e3  mov     bl, 2
0x1800433e5  lea     r13, DLRegCloseKey
0x1800433ec  test    eax, eax
0x1800433ee  jnz     loc_180043476
0x1800433f4  mov     [rsp+390h+var_358], al
0x1800433f8  mov     [rsp+390h+var_350], r13
0x1800433fd  mov     rax, [rsp+390h+var_360]
0x180043402  mov     [rsp+390h+var_348], rax
0x180043407  lea     rdx, aInprocserver32_0; "InProcServer32"
0x18004340e  mov     rcx, [rsp+390h+var_360]
0x180043413  call    DLRegDeleteKeyW
0x180043418  mov     r14d, eax
0x18004341b  lea     rsi, WPP_GLOBAL_Control
0x180043422  test    eax, eax
0x180043424  jz      short loc_18004346A
0x180043426  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004342c  mov     edx, r14d
0x18004342f  mov     rcx, rax
0x180043432  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180043438  mov     rcx, cs:WPP_GLOBAL_Control
0x18004343f  cmp     rcx, rsi
0x180043442  jz      short loc_18004346A
0x180043444  test    byte ptr [rcx+1Ch], 1
0x180043448  jz      short loc_18004346A
0x18004344a  cmp     [rcx+19h], bl
0x18004344d  jb      short loc_18004346A
0x18004344f  mov     edx, 17h
0x180043454  lea     rax, [rbp+290h+var_240]
0x180043458  mov     [rsp+390h+var_370], rax
0x18004345d  mov     r9d, r14d
0x180043460  mov     rcx, [rcx+10h]
0x180043464  call    WPP_SF_LS
0x180043469  nop
0x18004346a  lea     rcx, [rsp+390h+var_358]
0x18004346f  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x180043474  jmp     short loc_1800434C0
0x180043476  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004347c  mov     edx, r14d
0x18004347f  mov     rcx, rax
0x180043482  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180043488  lea     rsi, WPP_GLOBAL_Control
0x18004348f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043496  cmp     rcx, rsi
0x180043499  jz      short loc_1800434C0
0x18004349b  test    byte ptr [rcx+1Ch], 1
0x18004349f  jz      short loc_1800434C0
0x1800434a1  cmp     [rcx+19h], bl
0x1800434a4  jb      short loc_1800434C0
0x1800434a6  mov     edx, 18h
0x1800434ab  lea     rax, [rbp+290h+var_240]
0x1800434af  mov     [rsp+390h+var_370], rax
0x1800434b4  mov     r9d, r14d
0x1800434b7  mov     rcx, [rcx+10h]
0x1800434bb  call    WPP_SF_LS
0x1800434c0  lea     rax, [rsp+390h+var_360]
0x1800434c5  mov     [rsp+390h+var_370], rax
0x1800434ca  mov     r9d, r12d
0x1800434cd  lea     r12, aSoftwareClasse; "SOFTWARE\\Classes\\CLSID"
0x1800434d4  mov     rdx, r12
0x1800434d7  mov     rcx, 0FFFFFFFF80000002h
0x1800434de  call    DLRegOpenKeyExW
0x1800434e3  mov     r14d, eax
0x1800434e6  test    eax, eax
0x1800434e8  jnz     short loc_180043564
0x1800434ea  mov     [rsp+390h+var_358], al
0x1800434ee  mov     [rsp+390h+var_350], r13
0x1800434f3  mov     rax, [rsp+390h+var_360]
0x1800434f8  mov     [rsp+390h+var_348], rax
0x1800434fd  lea     rdx, [rsp+390h+sz]
0x180043502  mov     rcx, [rsp+390h+var_360]
0x180043507  call    DLRegDeleteKeyW
0x18004350c  mov     r14d, eax
0x18004350f  test    eax, eax
0x180043511  jz      short loc_180043558
0x180043513  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180043519  mov     edx, r14d
0x18004351c  mov     rcx, rax
0x18004351f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180043525  mov     rcx, cs:WPP_GLOBAL_Control
0x18004352c  cmp     rcx, rsi
0x18004352f  jz      short loc_180043558
0x180043531  test    byte ptr [rcx+1Ch], 1
0x180043535  jz      short loc_180043558
0x180043537  cmp     [rcx+19h], bl
0x18004353a  jb      short loc_180043558
0x18004353c  mov     edx, 19h
0x180043541  lea     rax, [rsp+390h+sz]
0x180043546  mov     [rsp+390h+var_370], rax
0x18004354b  mov     r9d, r14d
0x18004354e  mov     rcx, [rcx+10h]
0x180043552  call    WPP_SF_LS
0x180043557  nop
0x180043558  lea     rcx, [rsp+390h+var_358]
0x18004355d  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x180043562  jmp     short loc_1800435A3
0x180043564  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004356a  mov     edx, r14d
0x18004356d  mov     rcx, rax
0x180043570  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180043576  mov     rcx, cs:WPP_GLOBAL_Control
0x18004357d  cmp     rcx, rsi
0x180043580  jz      short loc_1800435A3
0x180043582  test    byte ptr [rcx+1Ch], 1
0x180043586  jz      short loc_1800435A3
0x180043588  cmp     [rcx+19h], bl
0x18004358b  jb      short loc_1800435A3
0x18004358d  mov     edx, 1Ah
0x180043592  mov     [rsp+390h+var_370], r12
0x180043597  mov     r9d, r14d
0x18004359a  mov     rcx, [rcx+10h]
0x18004359e  call    WPP_SF_LS
0x1800435a3  xor     eax, eax
0x1800435a5  mov     rcx, [rbp+290h+var_40]
0x1800435ac  xor     rcx, rsp; StackCookie
0x1800435af  call    __security_check_cookie
0x1800435b4  add     rsp, 368h
0x1800435bb  pop     r14
0x1800435bd  pop     r13
0x1800435bf  pop     r12
0x1800435c1  pop     rsi
0x1800435c2  pop     rbx
0x1800435c3  pop     rbp
0x1800435c4  retn
```
