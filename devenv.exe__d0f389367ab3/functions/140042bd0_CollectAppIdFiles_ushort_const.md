# CollectAppIdFiles(ushort const *)

- ea: `0x140042bd0`
- end: `0x140042e72`
- name: `?CollectAppIdFiles@@YAXPEBG@Z`
- size: `674`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140042e74`

## callees

- `0x140001020`
- `0x140003070`
- `0x140003160`
- `0x140009b10`
- `0x14002a5b0`
- `0x14004281c`
- `0x1400429c4`
- `0x140042b28`
- `0x140042ba0`
- `0x140042bd0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x140042bfb`
- `KERNEL32!GetModuleFileNameW` at `0x140042bfb`
- `SHLWAPI!PathFindFileNameW` at `0x140042cab`
- `SHLWAPI!PathFindFileNameW` at `0x140042cab`

## string_xrefs

- `0x140042cbe`: `.exe.config`
- `0x140042d23`: `activitylog.setup.xml`
- `0x140042d5e`: `activitylog.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CollectAppIdFiles(const unsigned __int16 *a1)
{
  _QWORD *v2; // rdx
  LPWSTR FileNameW; // rax
  _QWORD *v4; // rdx
  _QWORD *v5; // rdx
  _QWORD *v6; // rdx
  _QWORD *v7; // rdx
  _QWORD *v8; // rdx
  _QWORD *v9; // rdx
  __int64 v10; // [rsp+20h] [rbp-268h] BYREF
  __int64 v11; // [rsp+28h] [rbp-260h] BYREF
  __int64 v12; // [rsp+30h] [rbp-258h] BYREF
  __int64 v13; // [rsp+38h] [rbp-250h] BYREF
  __int64 v14; // [rsp+40h] [rbp-248h] BYREF
  __int64 v15; // [rsp+48h] [rbp-240h] BYREF
  __int64 v16; // [rsp+50h] [rbp-238h] BYREF
  __int64 v17; // [rsp+58h] [rbp-230h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-228h] BYREF

  GetModuleFileNameW(0, Filename, 0x104u);
  v11 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v11,
    Filename);
  ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RenameExtension(
    &v11,
    L".isolation.ini");
  CollectFile(&v11);
  if ( a1 )
  {
    v15 = 0;
    ComputeAppIdSubPath(&v15, a1);
    v10 = 0;
    v17 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v15 - 24) + 24;
    ComputeAppIdDataPath(&v10, &v17, 28);
    FileNameW = PathFindFileNameW(Filename);
    ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
      &v10,
      FileNameW);
    ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RenameExtension(
      &v10,
      L".exe.config");
    CollectFile(&v10);
    v14 = 0;
    v16 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v15 - 24) + 24;
    ComputeAppIdDataPath(&v14, &v16, 26);
    v13 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v14 - 24) + 24;
    ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
      &v13,
      L"activitylog.setup.xml");
    CollectFile(&v13);
    if ( DumpActivityLog() )
    {
      v12 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v14 - 24) + 24;
      ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
        &v12,
        L"activitylog.xml");
      CollectFile(&v12);
      v4 = (_QWORD *)(v12 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v12 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 8LL))(*v4);
      }
    }
    v5 = (_QWORD *)(v13 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v13 - 24 + 16)) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
    }
    v6 = (_QWORD *)(v14 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v14 - 24 + 16)) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
    }
    v7 = (_QWORD *)(v10 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v10 - 24 + 16)) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 8LL))(*v7);
    }
    v8 = (_QWORD *)(v15 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v15 - 24 + 16)) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
    }
    v9 = (_QWORD *)(v11 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v11 - 24 + 16)) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
    }
  }
  else
  {
    v2 = (_QWORD *)(v11 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v11 - 24 + 16)) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 8LL))(*v2);
    }
  }
}

```

## disassembly

```asm
0x140042bd0  push    rbx
0x140042bd2  sub     rsp, 280h
0x140042bd9  mov     rax, cs:__security_cookie
0x140042be0  xor     rax, rsp
0x140042be3  mov     [rsp+288h+var_18], rax
0x140042beb  mov     rbx, rcx
0x140042bee  mov     r8d, 104h; nSize
0x140042bf4  lea     rdx, [rsp+288h+Filename]; lpFilename
0x140042bf9  xor     ecx, ecx; hModule
0x140042bfb  call    cs:__imp_GetModuleFileNameW
0x140042c01  and     [rsp+288h+var_260], 0
0x140042c07  lea     rdx, [rsp+288h+Filename]
0x140042c0c  lea     rcx, [rsp+288h+var_260]
0x140042c11  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140042c16  lea     rdx, aIsolationIni; ".isolation.ini"
0x140042c1d  lea     rcx, [rsp+288h+var_260]
0x140042c22  call    ?RenameExtension@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::RenameExtension(ushort const *)
0x140042c27  lea     rcx, [rsp+288h+var_260]
0x140042c2c  call    ?CollectFile@@YAXAEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@@Z; CollectFile(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &)
0x140042c31  test    rbx, rbx
0x140042c34  jnz     short loc_140042C60
0x140042c36  mov     rdx, [rsp+288h+var_260]
0x140042c3b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140042c3f  or      ebx, 0FFFFFFFFh
0x140042c42  mov     eax, ebx
0x140042c44  lock xadd [rdx+10h], eax
0x140042c49  add     eax, ebx
0x140042c4b  test    eax, eax
0x140042c4d  jg      short loc_140042C5B
0x140042c4f  lfence
0x140042c52  mov     rcx, [rdx]
0x140042c55  mov     rax, [rcx]
0x140042c58  call    qword ptr [rax+8]
0x140042c5b  jmp     loc_140042E59
0x140042c60  and     [rsp+288h+var_240], 0
0x140042c66  mov     rdx, rbx
0x140042c69  lea     rcx, [rsp+288h+var_240]
0x140042c6e  call    ?ComputeAppIdSubPath@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; ComputeAppIdSubPath(ushort const *)
0x140042c73  and     [rsp+288h+var_268], 0
0x140042c79  mov     rcx, [rsp+288h+var_240]
0x140042c7e  add     rcx, 0FFFFFFFFFFFFFFE8h
0x140042c82  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140042c87  add     rax, 18h
0x140042c8b  mov     [rsp+288h+var_230], rax
0x140042c90  mov     r8d, 1Ch
0x140042c96  lea     rdx, [rsp+288h+var_230]
0x140042c9b  lea     rcx, [rsp+288h+var_268]
0x140042ca0  call    ?ComputeAppIdDataPath@@YA?AV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@H@Z; ComputeAppIdDataPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int)
0x140042ca5  nop
0x140042ca6  lea     rcx, [rsp+288h+Filename]; pszPath
0x140042cab  call    cs:__imp_PathFindFileNameW
0x140042cb1  mov     rdx, rax
0x140042cb4  lea     rcx, [rsp+288h+var_268]
0x140042cb9  call    ?Append@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Append(ushort const *)
0x140042cbe  lea     rdx, aExeConfig; ".exe.config"
0x140042cc5  lea     rcx, [rsp+288h+var_268]
0x140042cca  call    ?RenameExtension@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::RenameExtension(ushort const *)
0x140042ccf  lea     rcx, [rsp+288h+var_268]
0x140042cd4  call    ?CollectFile@@YAXAEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@@Z; CollectFile(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &)
0x140042cd9  and     [rsp+288h+var_248], 0
0x140042cdf  mov     rcx, [rsp+288h+var_240]
0x140042ce4  add     rcx, 0FFFFFFFFFFFFFFE8h
0x140042ce8  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140042ced  add     rax, 18h
0x140042cf1  mov     [rsp+288h+var_238], rax
0x140042cf6  mov     r8d, 1Ah
0x140042cfc  lea     rdx, [rsp+288h+var_238]
0x140042d01  lea     rcx, [rsp+288h+var_248]
0x140042d06  call    ?ComputeAppIdDataPath@@YA?AV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@H@Z; ComputeAppIdDataPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int)
0x140042d0b  nop
0x140042d0c  mov     rcx, [rsp+288h+var_248]
0x140042d11  add     rcx, 0FFFFFFFFFFFFFFE8h
0x140042d15  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140042d1a  add     rax, 18h
0x140042d1e  mov     [rsp+288h+var_250], rax
0x140042d23  lea     rdx, aActivitylogSet; "activitylog.setup.xml"
0x140042d2a  lea     rcx, [rsp+288h+var_250]
0x140042d2f  call    ?Append@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Append(ushort const *)
0x140042d34  lea     rcx, [rsp+288h+var_250]
0x140042d39  call    ?CollectFile@@YAXAEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@@Z; CollectFile(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &)
0x140042d3e  call    ?DumpActivityLog@@YA_NXZ; DumpActivityLog(void)
0x140042d43  test    al, al
0x140042d45  jz      short loc_140042DA7
0x140042d47  mov     rcx, [rsp+288h+var_248]
0x140042d4c  add     rcx, 0FFFFFFFFFFFFFFE8h
0x140042d50  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140042d55  add     rax, 18h
0x140042d59  mov     [rsp+288h+var_258], rax
0x140042d5e  lea     rdx, aActivitylogXml_0; "activitylog.xml"
0x140042d65  lea     rcx, [rsp+288h+var_258]
0x140042d6a  call    ?Append@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Append(ushort const *)
0x140042d6f  lea     rcx, [rsp+288h+var_258]
0x140042d74  call    ?CollectFile@@YAXAEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@@Z; CollectFile(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &)
0x140042d79  nop
0x140042d7a  nop     word ptr [rax+rax+00h]
0x140042d80  mov     rdx, [rsp+288h+var_258]
0x140042d85  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140042d89  or      ebx, 0FFFFFFFFh
0x140042d8c  mov     eax, ebx
0x140042d8e  lock xadd [rdx+10h], eax
0x140042d93  add     eax, ebx
0x140042d95  test    eax, eax
0x140042d97  jg      short loc_140042DAA
0x140042d99  lfence
0x140042d9c  mov     rcx, [rdx]
0x140042d9f  mov     rax, [rcx]
0x140042da2  call    qword ptr [rax+8]
0x140042da5  jmp     short loc_140042DAA
0x140042da7  or      ebx, 0FFFFFFFFh
0x140042daa  mov     rdx, [rsp+288h+var_250]
0x140042daf  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140042db3  mov     eax, ebx
0x140042db5  lock xadd [rdx+10h], eax
0x140042dba  add     eax, ebx
0x140042dbc  test    eax, eax
0x140042dbe  jg      short loc_140042DCD
0x140042dc0  lfence
0x140042dc3  mov     rcx, [rdx]
0x140042dc6  mov     rax, [rcx]
0x140042dc9  call    qword ptr [rax+8]
0x140042dcc  nop
0x140042dcd  mov     rdx, [rsp+288h+var_248]
0x140042dd2  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140042dd6  mov     eax, ebx
0x140042dd8  lock xadd [rdx+10h], eax
0x140042ddd  add     eax, ebx
0x140042ddf  test    eax, eax
0x140042de1  jg      short loc_140042DF0
0x140042de3  lfence
0x140042de6  mov     rcx, [rdx]
0x140042de9  mov     rax, [rcx]
0x140042dec  call    qword ptr [rax+8]
0x140042def  nop
0x140042df0  mov     rdx, [rsp+288h+var_268]
0x140042df5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140042df9  mov     eax, ebx
0x140042dfb  lock xadd [rdx+10h], eax
0x140042e00  add     eax, ebx
0x140042e02  test    eax, eax
0x140042e04  jg      short loc_140042E13
0x140042e06  lfence
0x140042e09  mov     rcx, [rdx]
0x140042e0c  mov     rax, [rcx]
0x140042e0f  call    qword ptr [rax+8]
0x140042e12  nop
0x140042e13  mov     rdx, [rsp+288h+var_240]
0x140042e18  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140042e1c  mov     eax, ebx
0x140042e1e  lock xadd [rdx+10h], eax
0x140042e23  add     eax, ebx
0x140042e25  test    eax, eax
0x140042e27  jg      short loc_140042E36
0x140042e29  lfence
0x140042e2c  mov     rcx, [rdx]
0x140042e2f  mov     rax, [rcx]
0x140042e32  call    qword ptr [rax+8]
0x140042e35  nop
0x140042e36  mov     rdx, [rsp+288h+var_260]
0x140042e3b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140042e3f  mov     eax, ebx
0x140042e41  lock xadd [rdx+10h], eax
0x140042e46  add     eax, ebx
0x140042e48  test    eax, eax
0x140042e4a  jg      short loc_140042E59
0x140042e4c  lfence
0x140042e4f  mov     rcx, [rdx]
0x140042e52  mov     rax, [rcx]
0x140042e55  call    qword ptr [rax+8]
0x140042e58  nop
0x140042e59  mov     rcx, [rsp+288h+var_18]
0x140042e61  xor     rcx, rsp; StackCookie
0x140042e64  call    __security_check_cookie
0x140042e69  add     rsp, 280h
0x140042e70  pop     rbx
0x140042e71  retn
```
