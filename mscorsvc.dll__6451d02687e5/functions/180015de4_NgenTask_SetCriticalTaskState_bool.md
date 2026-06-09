# NgenTask::SetCriticalTaskState(bool)

- ea: `0x180015de4`
- end: `0x180016210`
- name: `?SetCriticalTaskState@NgenTask@@YAJ_N@Z`
- size: `1068`
- prototype: `__int64 __fastcall(NgenTask *__hidden this, bool)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180008500`
- `0x180016210`
- `0x180016fd4`

## callees

- `0x180013f04`
- `0x180013f88`
- `0x18001406c`
- `0x180015de4`
- `0x180016a9c`
- `0x180030568`
- `0x180030d84`
- `0x18003f280`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180015ec8`
- `ole32!CoCreateInstance` at `0x180015ec8`
- `OLEAUT32!__imp_VariantInit` at `0x180015ef7`
- `OLEAUT32!__imp_VariantInit` at `0x180015f17`
- `OLEAUT32!__imp_VariantInit` at `0x180015f37`
- `OLEAUT32!__imp_VariantInit` at `0x180015f57`
- `OLEAUT32!__imp_VariantInit` at `0x180015ef7`
- `OLEAUT32!__imp_VariantInit` at `0x180015f17`
- `OLEAUT32!__imp_VariantInit` at `0x180015f37`
- `OLEAUT32!__imp_VariantInit` at `0x180015f57`
- `OLEAUT32!__imp_VariantClear` at `0x180015fdc`
- `OLEAUT32!__imp_VariantClear` at `0x180015fe7`
- `OLEAUT32!__imp_VariantClear` at `0x180015ff2`
- `OLEAUT32!__imp_VariantClear` at `0x180015ffd`
- `OLEAUT32!__imp_VariantClear` at `0x180015fdc`
- `OLEAUT32!__imp_VariantClear` at `0x180015fe7`
- `OLEAUT32!__imp_VariantClear` at `0x180015ff2`
- `OLEAUT32!__imp_VariantClear` at `0x180015ffd`

## pseudocode

```c
// Hidden C++ exception states: #wind=38
__int64 __fastcall NgenTask::SetCriticalTaskState(NgenTask *this, struct SString *a2, bool a3)
{
  unsigned __int16 v3; // r15
  HRESULT v4; // edi
  int v5; // eax
  LPVOID v6; // rdi
  _bstr_t *v7; // rax
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // r14
  void *v11; // rsi
  _bstr_t *v12; // rax
  __int64 v13; // rdx
  int v14; // eax
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  int v17; // [rsp+40h] [rbp-C0h]
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  int v19; // [rsp+50h] [rbp-B0h]
  __int64 v20; // [rsp+58h] [rbp-A8h] BYREF
  int v21; // [rsp+60h] [rbp-A0h]
  _DWORD v22[2]; // [rsp+68h] [rbp-98h] BYREF
  int v23; // [rsp+70h] [rbp-90h]
  void *lpMem; // [rsp+78h] [rbp-88h]
  __int128 v25; // [rsp+80h] [rbp-80h] BYREF
  IRecordInfo *v26; // [rsp+90h] [rbp-70h]
  __int128 v27; // [rsp+A0h] [rbp-60h] BYREF
  IRecordInfo *v28; // [rsp+B0h] [rbp-50h]
  __int128 v29; // [rsp+C0h] [rbp-40h] BYREF
  IRecordInfo *v30; // [rsp+D0h] [rbp-30h]
  VARIANTARG v31; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG v32; // [rsp+F8h] [rbp-8h] BYREF
  VARIANTARG v33; // [rsp+110h] [rbp+10h] BYREF
  VARIANTARG pvarg; // [rsp+128h] [rbp+28h] BYREF
  VARIANTARG v35; // [rsp+140h] [rbp+40h] BYREF
  IRecordInfo *p_ppv; // [rsp+1A8h] [rbp+A8h] BYREF
  IRecordInfo *pRecInfo; // [rsp+1B0h] [rbp+B0h]
  IRecordInfo *v38; // [rsp+1B8h] [rbp+B8h]

  v3 = (unsigned __int8)this;
  ppv = 0;
  v17 = 0;
  v20 = 0;
  v21 = 0;
  v18 = 0;
  v19 = 0;
  if ( (_BYTE)this && NgenTask::IsTaskPaused(this) )
  {
    v4 = 0;
  }
  else
  {
    v22[0] = 2;
    v22[1] = 2;
    v23 = 16;
    lpMem = (void *)&SString::s_EmptyBuffer;
    LOBYTE(a2) = 1;
    NgenTask::GetTaskName((NgenTask *)v22, a2, a3);
    p_ppv = (IRecordInfo *)&ppv;
    ppv = 0;
    v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
    v5 = v17;
    if ( ppv )
      v5 = 1;
    v17 = v5;
    if ( v4 < 0 )
      goto LABEL_29;
    VariantInit(&pvarg);
    v25 = *(_OWORD *)&pvarg.vt;
    p_ppv = pvarg.pRecInfo;
    VariantInit(&v33);
    v27 = *(_OWORD *)&v33.vt;
    pRecInfo = v33.pRecInfo;
    VariantInit(&v32);
    v29 = *(_OWORD *)&v32.vt;
    v38 = v32.pRecInfo;
    VariantInit(&v31);
    v26 = p_ppv;
    v28 = pRecInfo;
    v30 = v38;
    v35 = v31;
    v4 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL))(
           ppv,
           &v35,
           &v29,
           &v27,
           &v25);
    VariantClear(&v31);
    VariantClear(&v32);
    VariantClear(&v33);
    VariantClear(&pvarg);
    if ( v4 < 0 )
      goto LABEL_29;
    v6 = ppv;
    pRecInfo = (IRecordInfo *)&v20;
    if ( v21 )
    {
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v21 = 0;
    }
    v20 = 0;
    v7 = _bstr_t::_bstr_t((_bstr_t *)&p_ppv, L"\\Microsoft\\Windows\\.NET Framework");
    if ( *(_QWORD *)v7 )
      v8 = **(_QWORD **)v7;
    else
      v8 = 0;
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v6 + 56LL))(v6, v8, &v20);
    _bstr_t::~_bstr_t((_bstr_t *)&p_ppv);
    v9 = v21;
    v10 = v20;
    if ( v20 )
      v9 = 1;
    v21 = v9;
    if ( v4 < 0 )
    {
LABEL_29:
      v11 = lpMem;
    }
    else
    {
      pRecInfo = (IRecordInfo *)&v18;
      if ( v19 )
      {
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        v19 = 0;
      }
      v18 = 0;
      SString::ConvertToUnicode((SString *)v22);
      v11 = lpMem;
      v12 = _bstr_t::_bstr_t((_bstr_t *)&p_ppv, (const unsigned __int16 *)lpMem);
      if ( *(_QWORD *)v12 )
        v13 = **(_QWORD **)v12;
      else
        v13 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v10 + 104LL))(v10, v13, &v18);
      _bstr_t::~_bstr_t((_bstr_t *)&p_ppv);
      v14 = v19;
      if ( v18 )
        v14 = 1;
      v19 = v14;
      if ( v4 >= 0 )
        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 88LL))(v18, v3);
    }
    if ( (v23 & 8) != 0 )
      operator delete(v11);
  }
  if ( v19 )
  {
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v19 = 0;
  }
  if ( v21 )
  {
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v21 = 0;
  }
  if ( v17 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v17 = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015de4  mov     [rsp-8+arg_0], rbx
0x180015de9  push    rbp
0x180015dea  push    rsi
0x180015deb  push    rdi
0x180015dec  push    r12
0x180015dee  push    r13
0x180015df0  push    r14
0x180015df2  push    r15
0x180015df4  lea     rbp, [rsp-60h]
0x180015df9  sub     rsp, 160h
0x180015e00  movzx   r15d, cl
0x180015e04  xor     r12d, r12d
0x180015e07  mov     [rsp+190h+var_160], r12d
0x180015e0c  mov     [rsp+190h+var_158], r12
0x180015e11  mov     [rsp+190h+var_150], r12d
0x180015e16  mov     [rsp+190h+var_138], r12
0x180015e1b  mov     [rsp+190h+var_130], r12d
0x180015e20  mov     [rsp+190h+var_148], r12
0x180015e25  mov     [rsp+190h+var_140], r12d
0x180015e2a  test    cl, cl
0x180015e2c  jz      short loc_180015E3F
0x180015e2e  call    ?IsTaskPaused@NgenTask@@YA_NXZ; NgenTask::IsTaskPaused(void)
0x180015e33  test    al, al
0x180015e35  jz      short loc_180015E3F
0x180015e37  mov     edi, r12d
0x180015e3a  jmp     loc_18001618A
0x180015e3f  mov     esi, 2
0x180015e44  mov     [rsp+190h+var_128], esi
0x180015e48  mov     [rsp+190h+var_124], esi
0x180015e4c  mov     [rsp+190h+var_120], 10h
0x180015e54  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180015e5b  mov     [rsp+190h+lpMem], rax
0x180015e60  lea     r13d, [rsi-1]
0x180015e64  mov     dl, r13b; struct SString *
0x180015e67  lea     rcx, [rsp+190h+var_128]; this
0x180015e6c  call    ?GetTaskName@NgenTask@@YAXAEAVSString@@_N@Z; NgenTask::GetTaskName(SString &,bool)
0x180015e71  nop
0x180015e72  lea     rax, [rsp+190h+var_158]
0x180015e77  mov     [rbp+90h+arg_8], rax
0x180015e7e  cmp     [rsp+190h+var_150], r12d
0x180015e83  jz      short loc_180015EA1
0x180015e85  mov     rcx, [rsp+190h+var_158]
0x180015e8a  test    rcx, rcx
0x180015e8d  jz      short loc_180015E9C
0x180015e8f  mov     rax, [rcx]
0x180015e92  mov     rax, [rax+10h]
0x180015e96  call    cs:__guard_dispatch_icall_fptr
0x180015e9c  mov     [rsp+190h+var_150], r12d
0x180015ea1  mov     [rsp+190h+var_158], r12
0x180015ea6  mov     [rsp+190h+var_160], r13d
0x180015eab  lea     rax, [rsp+190h+var_158]
0x180015eb0  mov     [rsp+190h+ppv], rax; ppv
0x180015eb5  lea     r9, IID_ITaskService; riid
0x180015ebc  mov     r8d, r13d; dwClsContext
0x180015ebf  xor     edx, edx; pUnkOuter
0x180015ec1  lea     rcx, CLSID_TaskScheduler; rclsid
0x180015ec8  call    cs:__imp_CoCreateInstance
0x180015ece  mov     edi, eax
0x180015ed0  mov     ebx, r13d
0x180015ed3  and     ebx, 0FFFFFFFEh
0x180015ed6  mov     [rsp+190h+var_160], ebx
0x180015eda  mov     eax, [rsp+190h+var_150]
0x180015ede  cmp     [rsp+190h+var_158], r12
0x180015ee3  cmovnz  eax, r13d
0x180015ee7  mov     [rsp+190h+var_150], eax
0x180015eeb  test    edi, edi
0x180015eed  js      loc_180016175
0x180015ef3  lea     rcx, [rbp+90h+pvarg]; pvarg
0x180015ef7  call    cs:__imp_VariantInit
0x180015efd  nop
0x180015efe  movups  xmm0, xmmword ptr [rbp+90h+pvarg]
0x180015f02  movups  [rbp+90h+var_110], xmm0
0x180015f06  movsd   xmm0, qword ptr [rbp+90h+pvarg+10h]
0x180015f0b  movsd   [rbp+90h+arg_8], xmm0
0x180015f13  lea     rcx, [rbp+90h+var_80]; pvarg
0x180015f17  call    cs:__imp_VariantInit
0x180015f1d  nop
0x180015f1e  movups  xmm0, xmmword ptr [rbp+90h+var_80]
0x180015f22  movups  [rbp+90h+var_F0], xmm0
0x180015f26  movsd   xmm0, qword ptr [rbp+90h+var_80+10h]
0x180015f2b  movsd   [rbp+90h+arg_10], xmm0
0x180015f33  lea     rcx, [rbp+90h+var_98]; pvarg
0x180015f37  call    cs:__imp_VariantInit
0x180015f3d  nop
0x180015f3e  movups  xmm0, xmmword ptr [rbp+90h+var_98]
0x180015f42  movups  [rbp+90h+var_D0], xmm0
0x180015f46  movsd   xmm0, qword ptr [rbp+90h+var_98+10h]
0x180015f4b  movsd   [rbp+90h+arg_18], xmm0
0x180015f53  lea     rcx, [rbp+90h+var_B0]; pvarg
0x180015f57  call    cs:__imp_VariantInit
0x180015f5d  nop
0x180015f5e  movups  xmm0, [rbp+90h+var_110]
0x180015f62  movaps  [rbp+90h+var_110], xmm0
0x180015f66  movsd   xmm0, [rbp+90h+arg_8]
0x180015f6e  movsd   [rbp+90h+var_100], xmm0
0x180015f73  movups  xmm0, [rbp+90h+var_F0]
0x180015f77  movaps  [rbp+90h+var_F0], xmm0
0x180015f7b  movsd   xmm0, [rbp+90h+arg_10]
0x180015f83  movsd   [rbp+90h+var_E0], xmm0
0x180015f88  movups  xmm0, [rbp+90h+var_D0]
0x180015f8c  movaps  [rbp+90h+var_D0], xmm0
0x180015f90  movsd   xmm0, [rbp+90h+arg_18]
0x180015f98  movsd   [rbp+90h+var_C0], xmm0
0x180015f9d  movups  xmm0, xmmword ptr [rbp+90h+var_B0]
0x180015fa1  movaps  [rbp+90h+var_50], xmm0
0x180015fa5  movsd   xmm1, qword ptr [rbp+90h+var_B0+10h]
0x180015faa  movsd   [rbp+90h+var_40], xmm1
0x180015faf  mov     rcx, [rsp+190h+var_158]
0x180015fb4  mov     rax, [rcx]
0x180015fb7  lea     rdx, [rbp+90h+var_110]
0x180015fbb  mov     [rsp+190h+ppv], rdx
0x180015fc0  lea     r9, [rbp+90h+var_F0]
0x180015fc4  lea     r8, [rbp+90h+var_D0]
0x180015fc8  lea     rdx, [rbp+90h+var_50]
0x180015fcc  mov     rax, [rax+50h]
0x180015fd0  call    cs:__guard_dispatch_icall_fptr
0x180015fd6  mov     edi, eax
0x180015fd8  lea     rcx, [rbp+90h+var_B0]; pvarg
0x180015fdc  call    cs:__imp_VariantClear
0x180015fe2  nop
0x180015fe3  lea     rcx, [rbp+90h+var_98]; pvarg
0x180015fe7  call    cs:__imp_VariantClear
0x180015fed  nop
0x180015fee  lea     rcx, [rbp+90h+var_80]; pvarg
0x180015ff2  call    cs:__imp_VariantClear
0x180015ff8  nop
0x180015ff9  lea     rcx, [rbp+90h+pvarg]; pvarg
0x180015ffd  call    cs:__imp_VariantClear
0x180016003  test    edi, edi
0x180016005  js      loc_180016175
0x18001600b  mov     rdi, [rsp+190h+var_158]
0x180016010  lea     rax, [rsp+190h+var_138]
0x180016015  mov     [rbp+90h+arg_10], rax
0x18001601c  cmp     [rsp+190h+var_130], r12d
0x180016021  jz      short loc_18001603F
0x180016023  mov     rcx, [rsp+190h+var_138]
0x180016028  test    rcx, rcx
0x18001602b  jz      short loc_18001603A
0x18001602d  mov     rax, [rcx]
0x180016030  mov     rax, [rax+10h]
0x180016034  call    cs:__guard_dispatch_icall_fptr
0x18001603a  mov     [rsp+190h+var_130], r12d
0x18001603f  mov     [rsp+190h+var_138], r12
0x180016044  or      ebx, esi
0x180016046  mov     [rsp+190h+var_160], ebx
0x18001604a  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\.NET Framework"
0x180016051  lea     rcx, [rbp+90h+arg_8]; this
0x180016058  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001605d  nop
0x18001605e  mov     rcx, [rax]
0x180016061  test    rcx, rcx
0x180016064  jz      short loc_18001606B
0x180016066  mov     rdx, [rcx]
0x180016069  jmp     short loc_18001606E
0x18001606b  mov     rdx, r12
0x18001606e  mov     rax, [rdi]
0x180016071  lea     r8, [rsp+190h+var_138]
0x180016076  mov     rcx, rdi
0x180016079  mov     rax, [rax+38h]
0x18001607d  call    cs:__guard_dispatch_icall_fptr
0x180016083  mov     edi, eax
0x180016085  lea     rcx, [rbp+90h+arg_8]; this
0x18001608c  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180016091  and     ebx, 0FFFFFFFDh
0x180016094  mov     [rsp+190h+var_160], ebx
0x180016098  mov     eax, [rsp+190h+var_130]
0x18001609c  mov     r14, [rsp+190h+var_138]
0x1800160a1  test    r14, r14
0x1800160a4  cmovnz  eax, r13d
0x1800160a8  mov     [rsp+190h+var_130], eax
0x1800160ac  test    edi, edi
0x1800160ae  js      loc_180016175
0x1800160b4  lea     rax, [rsp+190h+var_148]
0x1800160b9  mov     [rbp+90h+arg_10], rax
0x1800160c0  cmp     [rsp+190h+var_140], r12d
0x1800160c5  jz      short loc_1800160E3
0x1800160c7  mov     rcx, [rsp+190h+var_148]
0x1800160cc  test    rcx, rcx
0x1800160cf  jz      short loc_1800160DE
0x1800160d1  mov     rax, [rcx]
0x1800160d4  mov     rax, [rax+10h]
0x1800160d8  call    cs:__guard_dispatch_icall_fptr
0x1800160de  mov     [rsp+190h+var_140], r12d
0x1800160e3  mov     [rsp+190h+var_148], r12
0x1800160e8  or      ebx, 4
0x1800160eb  mov     [rsp+190h+var_160], ebx
0x1800160ef  lea     rcx, [rsp+190h+var_128]; this
0x1800160f4  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800160f9  mov     rsi, [rsp+190h+lpMem]
0x1800160fe  mov     rdx, rsi; unsigned __int16 *
0x180016101  lea     rcx, [rbp+90h+arg_8]; this
0x180016108  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001610d  nop
0x18001610e  mov     rcx, [rax]
0x180016111  test    rcx, rcx
0x180016114  jz      short loc_18001611B
0x180016116  mov     rdx, [rcx]
0x180016119  jmp     short loc_18001611E
0x18001611b  mov     rdx, r12
0x18001611e  mov     rax, [r14]
0x180016121  lea     r8, [rsp+190h+var_148]
0x180016126  mov     rcx, r14
0x180016129  mov     rax, [rax+68h]
0x18001612d  call    cs:__guard_dispatch_icall_fptr
0x180016133  mov     edi, eax
0x180016135  lea     rcx, [rbp+90h+arg_8]; this
0x18001613c  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180016141  and     ebx, 0FFFFFFFBh
0x180016144  mov     [rsp+190h+var_160], ebx
0x180016148  mov     eax, [rsp+190h+var_140]
0x18001614c  mov     rcx, [rsp+190h+var_148]
0x180016151  test    rcx, rcx
0x180016154  cmovnz  eax, r13d
0x180016158  mov     [rsp+190h+var_140], eax
0x18001615c  test    edi, edi
0x18001615e  js      short loc_18001617A
0x180016160  mov     rax, [rcx]
0x180016163  movzx   edx, r15w
0x180016167  mov     rax, [rax+58h]
0x18001616b  call    cs:__guard_dispatch_icall_fptr
0x180016171  mov     edi, eax
0x180016173  jmp     short loc_18001617A
0x180016175  mov     rsi, [rsp+190h+lpMem]
0x18001617a  test    byte ptr [rsp+190h+var_120], 8
0x18001617f  jz      short loc_18001618A
0x180016181  mov     rcx, rsi; lpMem
0x180016184  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016189  nop
0x18001618a  cmp     [rsp+190h+var_140], r12d
0x18001618f  jz      short loc_1800161AD
0x180016191  mov     rcx, [rsp+190h+var_148]
0x180016196  test    rcx, rcx
0x180016199  jz      short loc_1800161A8
0x18001619b  mov     rax, [rcx]
0x18001619e  mov     rax, [rax+10h]
0x1800161a2  call    cs:__guard_dispatch_icall_fptr
0x1800161a8  mov     [rsp+190h+var_140], r12d
0x1800161ad  cmp     [rsp+190h+var_130], r12d
0x1800161b2  jz      short loc_1800161D0
0x1800161b4  mov     rcx, [rsp+190h+var_138]
0x1800161b9  test    rcx, rcx
0x1800161bc  jz      short loc_1800161CB
0x1800161be  mov     rax, [rcx]
0x1800161c1  mov     rax, [rax+10h]
0x1800161c5  call    cs:__guard_dispatch_icall_fptr
0x1800161cb  mov     [rsp+190h+var_130], r12d
0x1800161d0  cmp     [rsp+190h+var_150], r12d
0x1800161d5  jz      short loc_1800161F3
0x1800161d7  mov     rcx, [rsp+190h+var_158]
0x1800161dc  test    rcx, rcx
0x1800161df  jz      short loc_1800161EE
0x1800161e1  mov     rdx, [rcx]
0x1800161e4  mov     rax, [rdx+10h]
0x1800161e8  call    cs:__guard_dispatch_icall_fptr
0x1800161ee  mov     [rsp+190h+var_150], r12d
0x1800161f3  mov     eax, edi
0x1800161f5  mov     rbx, [rsp+190h+arg_0]
0x1800161fd  add     rsp, 160h
0x180016204  pop     r15
0x180016206  pop     r14
0x180016208  pop     r13
0x18001620a  pop     r12
0x18001620c  pop     rdi
0x18001620d  pop     rsi
0x18001620e  pop     rbp
0x18001620f  retn
```
