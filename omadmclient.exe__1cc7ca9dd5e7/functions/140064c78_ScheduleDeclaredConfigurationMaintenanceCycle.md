# ScheduleDeclaredConfigurationMaintenanceCycle

- ea: `0x140064c78`
- end: `0x1400650aa`
- name: `ScheduleDeclaredConfigurationMaintenanceCycle`
- size: `1074`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140064af8`

## callees

- `0x1400564cc`
- `0x140056a5c`
- `0x14005fa64`
- `0x1400601fc`
- `0x1400649a8`
- `0x140064c78`
- `0x140065274`
- `0x14006572c`
- `0x1400659d8`
- `0x140069010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140064e79`
- `OLEAUT32!__imp_SysAllocString` at `0x140064e79`
- `OLEAUT32!__imp_VariantInit` at `0x140064e44`
- `OLEAUT32!__imp_VariantInit` at `0x140064e5e`
- `OLEAUT32!__imp_VariantInit` at `0x140064e44`
- `OLEAUT32!__imp_VariantInit` at `0x140064e5e`
- `OLEAUT32!__imp_VariantClear` at `0x140064f46`
- `OLEAUT32!__imp_VariantClear` at `0x140064f5e`
- `OLEAUT32!__imp_VariantClear` at `0x140064f76`
- `OLEAUT32!__imp_VariantClear` at `0x140064f46`
- `OLEAUT32!__imp_VariantClear` at `0x140064f5e`
- `OLEAUT32!__imp_VariantClear` at `0x140064f76`

## string_xrefs

- `0x140064df5`: `Refresh schedule created by Declared Configuration to refresh any settings changed on the device`
- `0x140064eb4`: `Refresh schedule created by Declared Configuration to refresh any settings changed on the device`
- `0x140064d48`: `%windir%\system32\deviceenroller.exe `

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall ScheduleDeclaredConfigurationMaintenanceCycle(
        __int64 a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        unsigned __int16 *a7,
        __int64 *a8)
{
  int v10; // ebx
  __int64 v11; // rdx
  __int64 *v12; // rbx
  __int64 (__fastcall *v13)(__int64 *, _QWORD *, __int64 *); // rdi
  _QWORD *v14; // rdx
  int v15; // ebx
  const unsigned __int16 *v16; // rcx
  __int64 *v17; // rbx
  __int64 v18; // rdi
  __int128 v19; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v21; // xmm8
  IRecordInfo *v22; // xmm9_8
  BSTR v23; // rax
  __int64 (__fastcall *v24)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // r14
  __int128 v25; // xmm10
  IRecordInfo *v26; // xmm11_8
  __int64 v27; // rdi
  _bstr_t *v28; // rax
  __int64 v29; // rdx
  HRESULT v30; // eax
  HRESULT v31; // eax
  HRESULT v32; // eax
  CDeclaredConfigurationLogger *Logger; // rax
  __int64 v35; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+70h] [rbp-98h] BYREF
  __int64 v37; // [rsp+78h] [rbp-90h] BYREF
  int v38[2]; // [rsp+80h] [rbp-88h] BYREF
  int v39[2]; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v40; // [rsp+90h] [rbp-78h] BYREF
  VARIANTARG v41; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v43; // [rsp+D8h] [rbp-30h]
  __int64 v44; // [rsp+E0h] [rbp-28h]
  __int64 v45; // [rsp+E8h] [rbp-20h]
  __int128 v46; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v47; // [rsp+108h] [rbp+0h]
  __int128 v48; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v49; // [rsp+128h] [rbp+20h]
  __int128 v50; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v51; // [rsp+148h] [rbp+40h]
  __int64 v52; // [rsp+1D8h] [rbp+D0h] BYREF

  *(_QWORD *)v39 = 0;
  a8 = 0;
  v52 = 0;
  *(_QWORD *)v38 = 0;
  a6 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v37 = 0;
  v36 = 0;
  v10 = CreateTask(
          (LPVOID *)v39,
          &a8,
          &v52,
          v38,
          a2,
          (__int64)L"%windir%\\system32\\deviceenroller.exe ",
          a7,
          (__int64 *)L"S-1-5-18",
          0,
          1,
          1);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v52 + 72LL))(v52, &a6);
    if ( v10 >= 0 )
    {
      v10 = AddTimeTaskTriggers(&a6, v11, a4, a5);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 80LL))(v52, a6);
        if ( v10 >= 0 )
        {
          v12 = a8;
          v13 = *(__int64 (__fastcall **)(__int64 *, _QWORD *, __int64 *))(*a8 + 104);
          v14 = *(_QWORD **)_bstr_t::_bstr_t(
                              (_bstr_t *)&v35,
                              L"Refresh schedule created by Declared Configuration to refresh any settings changed on the device");
          if ( v14 )
            v14 = (_QWORD *)*v14;
          v15 = v13(v12, v14, &v36);
          _bstr_t::~_bstr_t((_bstr_t *)&v35);
          if ( v15 >= 0 )
            goto LABEL_16;
          v17 = a8;
          v18 = *a8;
          VariantInit(&pvarg);
          v19 = *(_OWORD *)&pvarg.vt;
          pRecInfo = pvarg.pRecInfo;
          VariantInit(&v41);
          v21 = *(_OWORD *)&v41.vt;
          v22 = v41.pRecInfo;
          v23 = SysAllocString(L"S-1-5-18");
          if ( !v23 )
            _com_issue_error(-2147024882);
          v24 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v18 + 136);
          v40.vt = 8;
          v40.llVal = (LONGLONG)v23;
          v25 = *(_OWORD *)&v40.vt;
          v26 = v40.pRecInfo;
          v27 = v52;
          v28 = _bstr_t::_bstr_t(
                  (_bstr_t *)&v35,
                  L"Refresh schedule created by Declared Configuration to refresh any settings changed on the device");
          if ( *(_QWORD *)v28 )
            v29 = **(_QWORD **)v28;
          else
            v29 = 0;
          v46 = v19;
          v47 = pRecInfo;
          v48 = v21;
          v49 = v22;
          v50 = v25;
          v51 = v26;
          v10 = v24(v17, v29, v27, 6, &v50, &v48, 3, &v46, &v37);
          _bstr_t::~_bstr_t((_bstr_t *)&v35);
          v30 = VariantClear(&v40);
          if ( v30 < 0 )
            _com_issue_error(v30);
          v31 = VariantClear(&v41);
          if ( v31 < 0 )
            _com_issue_error(v31);
          v32 = VariantClear(&pvarg);
          if ( v32 < 0 )
            _com_issue_error(v32);
          Logger = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogDeclaredConfigurationTaskCreated(Logger, a2, v10);
          if ( v10 >= 0 )
LABEL_16:
            v10 = DeclaredConfigurationStore_PersistScheduleRecord(v16);
        }
      }
    }
  }
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( a6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
  if ( *(_QWORD *)v38 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v38 + 16LL))(*(_QWORD *)v38);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  if ( a8 )
    (*(void (__fastcall **)(__int64 *))(*a8 + 16))(a8);
  if ( *(_QWORD *)v39 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v39 + 16LL))(*(_QWORD *)v39);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140064c78  mov     rax, rsp
0x140064c7b  mov     [rax+10h], rbx
0x140064c7f  mov     [rax+18h], rsi
0x140064c83  mov     [rax+8], rcx
0x140064c87  push    rbp
0x140064c88  push    rdi
0x140064c89  push    r14
0x140064c8b  lea     rbp, [rax-0C8h]
0x140064c92  sub     rsp, 1B0h
0x140064c99  movaps  xmmword ptr [rax-28h], xmm6
0x140064c9d  movaps  xmmword ptr [rax-38h], xmm7
0x140064ca1  movaps  xmmword ptr [rax-48h], xmm8
0x140064ca6  movaps  xmmword ptr [rax-58h], xmm9
0x140064cab  movaps  xmmword ptr [rax-68h], xmm10
0x140064cb0  movaps  xmmword ptr [rax-78h], xmm11
0x140064cb5  mov     edi, r9d
0x140064cb8  mov     rsi, rdx
0x140064cbb  mov     qword ptr [rbp+0C0h+var_140], 0
0x140064cc3  mov     [rbp+0C0h+arg_38], 0
0x140064cce  mov     [rbp+0C0h+arg_0], 0
0x140064cd9  mov     qword ptr [rsp+1C0h+var_148], 0
0x140064ce2  mov     [rbp+0C0h+arg_28], 0
0x140064ced  mov     [rbp+0C0h+var_F0], 0
0x140064cf5  mov     [rbp+0C0h+var_E8], 0
0x140064cfd  mov     [rbp+0C0h+var_E0], 0
0x140064d05  mov     [rsp+1C0h+var_150], 0
0x140064d0e  mov     [rsp+1C0h+var_158], 0
0x140064d17  mov     eax, 1
0x140064d1c  mov     dword ptr [rsp+1C0h+var_168], eax
0x140064d20  mov     [rsp+1C0h+var_170], eax; int
0x140064d24  mov     [rsp+1C0h+var_178], eax; int
0x140064d28  mov     [rsp+1C0h+Data], 0; Data
0x140064d30  lea     r14, aS1518; "S-1-5-18"
0x140064d37  mov     [rsp+1C0h+var_188], r14; __int64
0x140064d3c  mov     rax, [rbp+0C0h+arg_30]
0x140064d43  mov     [rsp+1C0h+var_190], rax; unsigned __int16 *
0x140064d48  lea     rax, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe "
0x140064d4f  mov     [rsp+1C0h+var_198], rax; __int64
0x140064d54  mov     [rsp+1C0h+var_1A0], rdx; unsigned __int16 *
0x140064d59  lea     r9, [rsp+1C0h+var_148]; int
0x140064d5e  lea     r8, [rbp+0C0h+arg_0]; int
0x140064d65  lea     rdx, [rbp+0C0h+arg_38]; int
0x140064d6c  lea     rcx, [rbp+0C0h+var_140]; int
0x140064d70  call    CreateTask
0x140064d75  mov     ebx, eax
0x140064d77  test    eax, eax
0x140064d79  js      loc_140064FA8
0x140064d7f  mov     rcx, [rbp+0C0h+arg_0]
0x140064d86  mov     rax, [rcx]
0x140064d89  lea     rdx, [rbp+0C0h+arg_28]
0x140064d90  mov     rax, [rax+48h]
0x140064d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064d99  mov     ebx, eax
0x140064d9b  test    eax, eax
0x140064d9d  js      loc_140064FA8
0x140064da3  mov     r9d, [rbp+0C0h+arg_20]
0x140064daa  mov     r8d, edi
0x140064dad  lea     rcx, [rbp+0C0h+arg_28]
0x140064db4  call    AddTimeTaskTriggers
0x140064db9  mov     ebx, eax
0x140064dbb  test    eax, eax
0x140064dbd  js      loc_140064FA8
0x140064dc3  mov     rcx, [rbp+0C0h+arg_0]
0x140064dca  mov     rax, [rcx]
0x140064dcd  mov     rdx, [rbp+0C0h+arg_28]
0x140064dd4  mov     rax, [rax+50h]
0x140064dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064ddd  mov     ebx, eax
0x140064ddf  test    eax, eax
0x140064de1  js      loc_140064FA8
0x140064de7  mov     rbx, [rbp+0C0h+arg_38]
0x140064dee  mov     rax, [rbx]
0x140064df1  mov     rdi, [rax+68h]
0x140064df5  lea     rdx, aRefreshSchedul; "Refresh schedule created by Declared Co"...
0x140064dfc  lea     rcx, [rsp+1C0h+var_160]; this
0x140064e01  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140064e06  nop
0x140064e07  mov     rdx, [rax]
0x140064e0a  test    rdx, rdx
0x140064e0d  jz      short loc_140064E12
0x140064e0f  mov     rdx, [rdx]
0x140064e12  lea     r8, [rsp+1C0h+var_158]
0x140064e17  mov     rcx, rbx
0x140064e1a  mov     rax, rdi
0x140064e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064e22  mov     ebx, eax
0x140064e24  lea     rcx, [rsp+1C0h+var_160]; this
0x140064e29  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x140064e2e  test    ebx, ebx
0x140064e30  jns     loc_140064FA1
0x140064e36  mov     rbx, [rbp+0C0h+arg_38]
0x140064e3d  mov     rdi, [rbx]
0x140064e40  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x140064e44  call    cs:__imp_VariantInit
0x140064e4b  nop     dword ptr [rax+rax+00h]
0x140064e50  nop
0x140064e51  movups  xmm6, xmmword ptr [rbp+0C0h+pvarg]
0x140064e55  movsd   xmm7, qword ptr [rbp+0C0h+pvarg+10h]
0x140064e5a  lea     rcx, [rbp+0C0h+var_120]; pvarg
0x140064e5e  call    cs:__imp_VariantInit
0x140064e65  nop     dword ptr [rax+rax+00h]
0x140064e6a  nop
0x140064e6b  movups  xmm8, xmmword ptr [rbp+0C0h+var_120]
0x140064e70  movsd   xmm9, qword ptr [rbp+0C0h+var_120+10h]
0x140064e76  mov     rcx, r14; psz
0x140064e79  call    cs:__imp_SysAllocString
0x140064e80  nop     dword ptr [rax+rax+00h]
0x140064e85  test    rax, rax
0x140064e88  jz      loc_14006508F
0x140064e8e  mov     r14, [rdi+88h]
0x140064e95  mov     ecx, 8
0x140064e9a  mov     word ptr [rbp+0C0h+var_138], cx
0x140064e9e  mov     qword ptr [rbp+0C0h+var_138+8], rax
0x140064ea2  movups  xmm10, xmmword ptr [rbp+0C0h+var_138]
0x140064ea7  movsd   xmm11, qword ptr [rbp+0C0h+var_138+10h]
0x140064ead  mov     rdi, [rbp+0C0h+arg_0]
0x140064eb4  lea     rdx, aRefreshSchedul; "Refresh schedule created by Declared Co"...
0x140064ebb  lea     rcx, [rsp+1C0h+var_160]; this
0x140064ec0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140064ec5  nop
0x140064ec6  mov     rcx, [rax]
0x140064ec9  test    rcx, rcx
0x140064ecc  jz      short loc_140064ED3
0x140064ece  mov     rdx, [rcx]
0x140064ed1  jmp     short loc_140064ED5
0x140064ed3  xor     edx, edx
0x140064ed5  movaps  [rbp+0C0h+var_D0], xmm6
0x140064ed9  movsd   [rbp+0C0h+var_C0], xmm7
0x140064ede  movaps  [rbp+0C0h+var_B0], xmm8
0x140064ee3  movsd   [rbp+0C0h+var_A0], xmm9
0x140064ee9  movaps  [rbp+0C0h+var_90], xmm10
0x140064eee  movsd   [rbp+0C0h+var_80], xmm11
0x140064ef4  lea     rax, [rsp+1C0h+var_150]
0x140064ef9  mov     qword ptr [rsp+1C0h+Data], rax
0x140064efe  lea     rax, [rbp+0C0h+var_D0]
0x140064f02  mov     [rsp+1C0h+var_188], rax
0x140064f07  mov     dword ptr [rsp+1C0h+var_190], 3
0x140064f0f  lea     rax, [rbp+0C0h+var_B0]
0x140064f13  mov     [rsp+1C0h+var_198], rax
0x140064f18  lea     rax, [rbp+0C0h+var_90]
0x140064f1c  mov     [rsp+1C0h+var_1A0], rax
0x140064f21  mov     r9d, 6
0x140064f27  mov     r8, rdi
0x140064f2a  mov     rcx, rbx
0x140064f2d  mov     rax, r14
0x140064f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064f35  mov     ebx, eax
0x140064f37  lea     rcx, [rsp+1C0h+var_160]; this
0x140064f3c  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x140064f41  nop
0x140064f42  lea     rcx, [rbp+0C0h+var_138]; pvarg
0x140064f46  call    cs:__imp_VariantClear
0x140064f4d  nop     dword ptr [rax+rax+00h]
0x140064f52  test    eax, eax
0x140064f54  js      loc_14006509A
0x140064f5a  lea     rcx, [rbp+0C0h+var_120]; pvarg
0x140064f5e  call    cs:__imp_VariantClear
0x140064f65  nop     dword ptr [rax+rax+00h]
0x140064f6a  test    eax, eax
0x140064f6c  js      loc_1400650A2
0x140064f72  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x140064f76  call    cs:__imp_VariantClear
0x140064f7d  nop     dword ptr [rax+rax+00h]
0x140064f82  test    eax, eax
0x140064f84  js      loc_140065087
0x140064f8a  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x140064f8f  mov     r8d, ebx; int
0x140064f92  mov     rdx, rsi; unsigned __int16 *
0x140064f95  mov     rcx, rax; this
0x140064f98  call    ?LogDeclaredConfigurationTaskCreated@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogDeclaredConfigurationTaskCreated(ushort const *,long)
0x140064f9d  test    ebx, ebx
0x140064f9f  js      short loc_140064FA8
0x140064fa1  call    ?DeclaredConfigurationStore_PersistScheduleRecord@@YAJPEBG@Z; DeclaredConfigurationStore_PersistScheduleRecord(ushort const *)
0x140064fa6  mov     ebx, eax
0x140064fa8  mov     rcx, [rsp+1C0h+var_158]
0x140064fad  test    rcx, rcx
0x140064fb0  jz      short loc_140064FBF
0x140064fb2  mov     rax, [rcx]
0x140064fb5  mov     rax, [rax+10h]
0x140064fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064fbe  nop
0x140064fbf  mov     rcx, [rsp+1C0h+var_150]
0x140064fc4  test    rcx, rcx
0x140064fc7  jz      short loc_140064FD6
0x140064fc9  mov     rax, [rcx]
0x140064fcc  mov     rax, [rax+10h]
0x140064fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064fd5  nop
0x140064fd6  mov     rcx, [rbp+0C0h+arg_28]
0x140064fdd  test    rcx, rcx
0x140064fe0  jz      short loc_140064FEF
0x140064fe2  mov     rax, [rcx]
0x140064fe5  mov     rax, [rax+10h]
0x140064fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064fee  nop
0x140064fef  mov     rcx, qword ptr [rsp+1C0h+var_148]
0x140064ff4  test    rcx, rcx
0x140064ff7  jz      short loc_140065006
0x140064ff9  mov     rax, [rcx]
0x140064ffc  mov     rax, [rax+10h]
0x140065000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065005  nop
0x140065006  mov     rcx, [rbp+0C0h+arg_0]
0x14006500d  test    rcx, rcx
0x140065010  jz      short loc_14006501F
0x140065012  mov     rax, [rcx]
0x140065015  mov     rax, [rax+10h]
0x140065019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006501e  nop
0x14006501f  mov     rcx, [rbp+0C0h+arg_38]
0x140065026  test    rcx, rcx
0x140065029  jz      short loc_140065038
0x14006502b  mov     rax, [rcx]
0x14006502e  mov     rax, [rax+10h]
0x140065032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065037  nop
0x140065038  mov     rcx, qword ptr [rbp+0C0h+var_140]
0x14006503c  test    rcx, rcx
0x14006503f  jz      short loc_14006504E
0x140065041  mov     rax, [rcx]
0x140065044  mov     rax, [rax+10h]
0x140065048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006504d  nop
0x14006504e  mov     eax, ebx
0x140065050  lea     r11, [rsp+1C0h+var_10]
0x140065058  mov     rbx, [r11+28h]
0x14006505c  mov     rsi, [r11+30h]
0x140065060  movaps  xmm6, xmmword ptr [r11-10h]
0x140065065  movaps  xmm7, xmmword ptr [r11-20h]
0x14006506a  movaps  xmm8, xmmword ptr [r11-30h]
0x14006506f  movaps  xmm9, xmmword ptr [r11-40h]
0x140065074  movaps  xmm10, xmmword ptr [r11-50h]
0x140065079  movaps  xmm11, xmmword ptr [r11-60h]
0x14006507e  mov     rsp, r11
0x140065081  pop     r14
0x140065083  pop     rdi
0x140065084  pop     rbp
0x140065085  retn
0x140065087  mov     ecx, eax; int
0x140065089  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14006508f  mov     ecx, 8007000Eh; int
0x140065094  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14006509a  mov     ecx, eax; int
0x14006509c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400650a2  mov     ecx, eax; int
0x1400650a4  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
