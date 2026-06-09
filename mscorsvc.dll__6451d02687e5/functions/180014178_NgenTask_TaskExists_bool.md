# NgenTask::TaskExists(bool &)

- ea: `0x180014178`
- end: `0x180014589`
- name: `?TaskExists@NgenTask@@YAJAEA_N@Z`
- size: `1041`
- prototype: `__int64 __fastcall(NgenTask *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180008500`
- `0x1800283d0`

## callees

- `0x180013f04`
- `0x180013f88`
- `0x18001406c`
- `0x180014178`
- `0x180030568`
- `0x180030d84`
- `0x18003f280`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180014248`
- `ole32!CoCreateInstance` at `0x180014248`
- `OLEAUT32!__imp_VariantInit` at `0x180014276`
- `OLEAUT32!__imp_VariantInit` at `0x180014296`
- `OLEAUT32!__imp_VariantInit` at `0x1800142b6`
- `OLEAUT32!__imp_VariantInit` at `0x1800142d6`
- `OLEAUT32!__imp_VariantInit` at `0x180014276`
- `OLEAUT32!__imp_VariantInit` at `0x180014296`
- `OLEAUT32!__imp_VariantInit` at `0x1800142b6`
- `OLEAUT32!__imp_VariantInit` at `0x1800142d6`
- `OLEAUT32!__imp_VariantClear` at `0x18001435c`
- `OLEAUT32!__imp_VariantClear` at `0x180014367`
- `OLEAUT32!__imp_VariantClear` at `0x180014372`
- `OLEAUT32!__imp_VariantClear` at `0x18001437d`
- `OLEAUT32!__imp_VariantClear` at `0x18001435c`
- `OLEAUT32!__imp_VariantClear` at `0x180014367`
- `OLEAUT32!__imp_VariantClear` at `0x180014372`
- `OLEAUT32!__imp_VariantClear` at `0x18001437d`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall NgenTask::TaskExists(NgenTask *this, bool *a2, bool a3)
{
  HRESULT v4; // eax
  int v5; // r12d
  int v6; // ecx
  LPVOID v7; // rbx
  _bstr_t *v8; // rax
  __int64 v9; // rdx
  bool v10; // bl
  int v11; // eax
  __int64 v12; // r14
  void *v13; // rsi
  _bstr_t *v14; // rax
  __int64 v15; // rdx
  bool v16; // bl
  int v17; // eax
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+40h] [rbp-C0h]
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+50h] [rbp-B0h]
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+60h] [rbp-A0h]
  _DWORD v25[2]; // [rsp+68h] [rbp-98h] BYREF
  int v26; // [rsp+70h] [rbp-90h]
  void *lpMem; // [rsp+78h] [rbp-88h]
  __int128 v28; // [rsp+80h] [rbp-80h] BYREF
  IRecordInfo *v29; // [rsp+90h] [rbp-70h]
  __int128 v30; // [rsp+A0h] [rbp-60h] BYREF
  IRecordInfo *v31; // [rsp+B0h] [rbp-50h]
  __int128 v32; // [rsp+C0h] [rbp-40h] BYREF
  IRecordInfo *v33; // [rsp+D0h] [rbp-30h]
  VARIANTARG v34; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG v35; // [rsp+F8h] [rbp-8h] BYREF
  VARIANTARG v36; // [rsp+110h] [rbp+10h] BYREF
  VARIANTARG pvarg; // [rsp+128h] [rbp+28h] BYREF
  VARIANTARG v38; // [rsp+140h] [rbp+40h] BYREF
  IRecordInfo *p_ppv; // [rsp+1A0h] [rbp+A0h] BYREF
  IRecordInfo *pRecInfo; // [rsp+1A8h] [rbp+A8h]
  IRecordInfo *v41; // [rsp+1B0h] [rbp+B0h]

  ppv = 0;
  v20 = 0;
  v23 = 0;
  v24 = 0;
  v21 = 0;
  v22 = 0;
  v25[0] = 2;
  v25[1] = 2;
  v26 = 16;
  lpMem = (void *)&SString::s_EmptyBuffer;
  NgenTask::GetTaskName((NgenTask *)v25, 0, a3);
  *(_BYTE *)this = 0;
  p_ppv = (IRecordInfo *)&ppv;
  if ( v20 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v20 = 0;
  }
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  v5 = v4;
  v6 = v20;
  if ( ppv )
    v6 = 1;
  v20 = v6;
  if ( v4 < 0 )
    goto LABEL_30;
  VariantInit(&pvarg);
  v28 = *(_OWORD *)&pvarg.vt;
  p_ppv = pvarg.pRecInfo;
  VariantInit(&v36);
  v30 = *(_OWORD *)&v36.vt;
  pRecInfo = v36.pRecInfo;
  VariantInit(&v35);
  v32 = *(_OWORD *)&v35.vt;
  v41 = v35.pRecInfo;
  VariantInit(&v34);
  v29 = p_ppv;
  v31 = pRecInfo;
  v33 = v41;
  v38 = v34;
  v5 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL))(
         ppv,
         &v38,
         &v32,
         &v30,
         &v28);
  VariantClear(&v34);
  VariantClear(&v35);
  VariantClear(&v36);
  VariantClear(&pvarg);
  if ( v5 < 0 )
    goto LABEL_30;
  v7 = ppv;
  pRecInfo = (IRecordInfo *)&v23;
  if ( v24 )
  {
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v24 = 0;
  }
  v23 = 0;
  v8 = _bstr_t::_bstr_t((_bstr_t *)&p_ppv, L"\\Microsoft\\Windows\\.NET Framework");
  if ( *(_QWORD *)v8 )
    v9 = **(_QWORD **)v8;
  else
    v9 = 0;
  v10 = (*(int (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v7 + 56LL))(v7, v9, &v23) < 0;
  _bstr_t::~_bstr_t((_bstr_t *)&p_ppv);
  v11 = v24;
  v12 = v23;
  if ( v23 )
    v11 = 1;
  v24 = v11;
  if ( v10 )
  {
LABEL_30:
    v13 = lpMem;
  }
  else
  {
    pRecInfo = (IRecordInfo *)&v21;
    if ( v22 )
    {
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v22 = 0;
    }
    v21 = 0;
    SString::ConvertToUnicode((SString *)v25);
    v13 = lpMem;
    v14 = _bstr_t::_bstr_t((_bstr_t *)&p_ppv, (const unsigned __int16 *)lpMem);
    if ( *(_QWORD *)v14 )
      v15 = **(_QWORD **)v14;
    else
      v15 = 0;
    v16 = (*(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v12 + 104LL))(v12, v15, &v21) < 0;
    _bstr_t::~_bstr_t((_bstr_t *)&p_ppv);
    v17 = v22;
    if ( v21 )
      v17 = 1;
    v22 = v17;
    if ( !v16 )
      *(_BYTE *)this = 1;
  }
  if ( (v26 & 8) != 0 )
    operator delete(v13);
  if ( v22 )
  {
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v22 = 0;
  }
  if ( v24 )
  {
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v24 = 0;
  }
  if ( v20 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v20 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180014178  mov     [rsp-8+arg_18], rbx
0x18001417d  push    rbp
0x18001417e  push    rsi
0x18001417f  push    rdi
0x180014180  push    r12
0x180014182  push    r13
0x180014184  push    r14
0x180014186  push    r15
0x180014188  lea     rbp, [rsp-60h]
0x18001418d  sub     rsp, 160h
0x180014194  mov     r15, rcx
0x180014197  xor     r13d, r13d
0x18001419a  mov     [rsp+190h+var_160], r13d
0x18001419f  mov     [rsp+190h+var_158], r13
0x1800141a4  mov     [rsp+190h+var_150], r13d
0x1800141a9  mov     [rsp+190h+var_138], r13
0x1800141ae  mov     [rsp+190h+var_130], r13d
0x1800141b3  mov     [rsp+190h+var_148], r13
0x1800141b8  mov     [rsp+190h+var_140], r13d
0x1800141bd  lea     r14d, [r13+2]
0x1800141c1  mov     [rsp+190h+var_128], r14d
0x1800141c6  mov     [rsp+190h+var_124], r14d
0x1800141cb  mov     [rsp+190h+var_120], 10h
0x1800141d3  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x1800141da  mov     [rsp+190h+lpMem], rax
0x1800141df  xor     edx, edx; struct SString *
0x1800141e1  lea     rcx, [rsp+190h+var_128]; this
0x1800141e6  call    ?GetTaskName@NgenTask@@YAXAEAVSString@@_N@Z; NgenTask::GetTaskName(SString &,bool)
0x1800141eb  mov     [r15], r13b
0x1800141ee  lea     rax, [rsp+190h+var_158]
0x1800141f3  mov     [rbp+90h+arg_0], rax
0x1800141fa  cmp     [rsp+190h+var_150], r13d
0x1800141ff  jz      short loc_18001421D
0x180014201  mov     rcx, [rsp+190h+var_158]
0x180014206  test    rcx, rcx
0x180014209  jz      short loc_180014218
0x18001420b  mov     rax, [rcx]
0x18001420e  mov     rax, [rax+10h]
0x180014212  call    cs:__guard_dispatch_icall_fptr
0x180014218  mov     [rsp+190h+var_150], r13d
0x18001421d  mov     [rsp+190h+var_158], r13
0x180014222  mov     esi, 1
0x180014227  mov     [rsp+190h+var_160], esi
0x18001422b  lea     rax, [rsp+190h+var_158]
0x180014230  mov     [rsp+190h+ppv], rax; ppv
0x180014235  lea     r9, IID_ITaskService; riid
0x18001423c  mov     r8d, esi; dwClsContext
0x18001423f  xor     edx, edx; pUnkOuter
0x180014241  lea     rcx, CLSID_TaskScheduler; rclsid
0x180014248  call    cs:__imp_CoCreateInstance
0x18001424e  mov     r12d, eax
0x180014251  mov     edi, esi
0x180014253  and     edi, 0FFFFFFFEh
0x180014256  mov     [rsp+190h+var_160], edi
0x18001425a  mov     ecx, [rsp+190h+var_150]
0x18001425e  cmp     [rsp+190h+var_158], r13
0x180014263  cmovnz  ecx, esi
0x180014266  mov     [rsp+190h+var_150], ecx
0x18001426a  test    eax, eax
0x18001426c  js      loc_1800144ED
0x180014272  lea     rcx, [rbp+90h+pvarg]; pvarg
0x180014276  call    cs:__imp_VariantInit
0x18001427c  nop
0x18001427d  movups  xmm0, xmmword ptr [rbp+90h+pvarg]
0x180014281  movups  [rbp+90h+var_110], xmm0
0x180014285  movsd   xmm0, qword ptr [rbp+90h+pvarg+10h]
0x18001428a  movsd   [rbp+90h+arg_0], xmm0
0x180014292  lea     rcx, [rbp+90h+var_80]; pvarg
0x180014296  call    cs:__imp_VariantInit
0x18001429c  nop
0x18001429d  movups  xmm0, xmmword ptr [rbp+90h+var_80]
0x1800142a1  movups  [rbp+90h+var_F0], xmm0
0x1800142a5  movsd   xmm0, qword ptr [rbp+90h+var_80+10h]
0x1800142aa  movsd   [rbp+90h+arg_8], xmm0
0x1800142b2  lea     rcx, [rbp+90h+var_98]; pvarg
0x1800142b6  call    cs:__imp_VariantInit
0x1800142bc  nop
0x1800142bd  movups  xmm0, xmmword ptr [rbp+90h+var_98]
0x1800142c1  movups  [rbp+90h+var_D0], xmm0
0x1800142c5  movsd   xmm0, qword ptr [rbp+90h+var_98+10h]
0x1800142ca  movsd   [rbp+90h+arg_10], xmm0
0x1800142d2  lea     rcx, [rbp+90h+var_B0]; pvarg
0x1800142d6  call    cs:__imp_VariantInit
0x1800142dc  nop
0x1800142dd  movups  xmm0, [rbp+90h+var_110]
0x1800142e1  movaps  [rbp+90h+var_110], xmm0
0x1800142e5  movsd   xmm0, [rbp+90h+arg_0]
0x1800142ed  movsd   [rbp+90h+var_100], xmm0
0x1800142f2  movups  xmm0, [rbp+90h+var_F0]
0x1800142f6  movaps  [rbp+90h+var_F0], xmm0
0x1800142fa  movsd   xmm0, [rbp+90h+arg_8]
0x180014302  movsd   [rbp+90h+var_E0], xmm0
0x180014307  movups  xmm0, [rbp+90h+var_D0]
0x18001430b  movaps  [rbp+90h+var_D0], xmm0
0x18001430f  movsd   xmm0, [rbp+90h+arg_10]
0x180014317  movsd   [rbp+90h+var_C0], xmm0
0x18001431c  movups  xmm0, xmmword ptr [rbp+90h+var_B0]
0x180014320  movaps  [rbp+90h+var_50], xmm0
0x180014324  movsd   xmm1, qword ptr [rbp+90h+var_B0+10h]
0x180014329  movsd   [rbp+90h+var_40], xmm1
0x18001432e  mov     rcx, [rsp+190h+var_158]
0x180014333  mov     rax, [rcx]
0x180014336  lea     rdx, [rbp+90h+var_110]
0x18001433a  mov     [rsp+190h+ppv], rdx
0x18001433f  lea     r9, [rbp+90h+var_F0]
0x180014343  lea     r8, [rbp+90h+var_D0]
0x180014347  lea     rdx, [rbp+90h+var_50]
0x18001434b  mov     rax, [rax+50h]
0x18001434f  call    cs:__guard_dispatch_icall_fptr
0x180014355  mov     r12d, eax
0x180014358  lea     rcx, [rbp+90h+var_B0]; pvarg
0x18001435c  call    cs:__imp_VariantClear
0x180014362  nop
0x180014363  lea     rcx, [rbp+90h+var_98]; pvarg
0x180014367  call    cs:__imp_VariantClear
0x18001436d  nop
0x18001436e  lea     rcx, [rbp+90h+var_80]; pvarg
0x180014372  call    cs:__imp_VariantClear
0x180014378  nop
0x180014379  lea     rcx, [rbp+90h+pvarg]; pvarg
0x18001437d  call    cs:__imp_VariantClear
0x180014383  test    r12d, r12d
0x180014386  js      loc_1800144ED
0x18001438c  mov     rbx, [rsp+190h+var_158]
0x180014391  lea     rax, [rsp+190h+var_138]
0x180014396  mov     [rbp+90h+arg_8], rax
0x18001439d  cmp     [rsp+190h+var_130], r13d
0x1800143a2  jz      short loc_1800143C0
0x1800143a4  mov     rcx, [rsp+190h+var_138]
0x1800143a9  test    rcx, rcx
0x1800143ac  jz      short loc_1800143BB
0x1800143ae  mov     rax, [rcx]
0x1800143b1  mov     rax, [rax+10h]
0x1800143b5  call    cs:__guard_dispatch_icall_fptr
0x1800143bb  mov     [rsp+190h+var_130], r13d
0x1800143c0  mov     [rsp+190h+var_138], r13
0x1800143c5  or      edi, r14d
0x1800143c8  mov     [rsp+190h+var_160], edi
0x1800143cc  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\.NET Framework"
0x1800143d3  lea     rcx, [rbp+90h+arg_0]; this
0x1800143da  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800143df  nop
0x1800143e0  mov     rcx, [rax]
0x1800143e3  test    rcx, rcx
0x1800143e6  jz      short loc_1800143ED
0x1800143e8  mov     rdx, [rcx]
0x1800143eb  jmp     short loc_1800143F0
0x1800143ed  mov     rdx, r13
0x1800143f0  mov     rax, [rbx]
0x1800143f3  lea     r8, [rsp+190h+var_138]
0x1800143f8  mov     rcx, rbx
0x1800143fb  mov     rax, [rax+38h]
0x1800143ff  call    cs:__guard_dispatch_icall_fptr
0x180014405  test    eax, eax
0x180014407  sets    bl
0x18001440a  lea     rcx, [rbp+90h+arg_0]; this
0x180014411  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180014416  and     edi, 0FFFFFFFDh
0x180014419  mov     [rsp+190h+var_160], edi
0x18001441d  mov     eax, [rsp+190h+var_130]
0x180014421  mov     r14, [rsp+190h+var_138]
0x180014426  test    r14, r14
0x180014429  cmovnz  eax, esi
0x18001442c  mov     [rsp+190h+var_130], eax
0x180014430  test    bl, bl
0x180014432  jnz     loc_1800144ED
0x180014438  lea     rax, [rsp+190h+var_148]
0x18001443d  mov     [rbp+90h+arg_8], rax
0x180014444  cmp     [rsp+190h+var_140], r13d
0x180014449  jz      short loc_180014467
0x18001444b  mov     rcx, [rsp+190h+var_148]
0x180014450  test    rcx, rcx
0x180014453  jz      short loc_180014462
0x180014455  mov     rax, [rcx]
0x180014458  mov     rax, [rax+10h]
0x18001445c  call    cs:__guard_dispatch_icall_fptr
0x180014462  mov     [rsp+190h+var_140], r13d
0x180014467  mov     [rsp+190h+var_148], r13
0x18001446c  or      edi, 4
0x18001446f  mov     [rsp+190h+var_160], edi
0x180014473  lea     rcx, [rsp+190h+var_128]; this
0x180014478  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001447d  mov     rsi, [rsp+190h+lpMem]
0x180014482  mov     rdx, rsi; unsigned __int16 *
0x180014485  lea     rcx, [rbp+90h+arg_0]; this
0x18001448c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180014491  nop
0x180014492  mov     rcx, [rax]
0x180014495  test    rcx, rcx
0x180014498  jz      short loc_18001449F
0x18001449a  mov     rdx, [rcx]
0x18001449d  jmp     short loc_1800144A2
0x18001449f  mov     rdx, r13
0x1800144a2  mov     rax, [r14]
0x1800144a5  lea     r8, [rsp+190h+var_148]
0x1800144aa  mov     rcx, r14
0x1800144ad  mov     rax, [rax+68h]
0x1800144b1  call    cs:__guard_dispatch_icall_fptr
0x1800144b7  test    eax, eax
0x1800144b9  sets    bl
0x1800144bc  lea     rcx, [rbp+90h+arg_0]; this
0x1800144c3  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800144c8  and     edi, 0FFFFFFFBh
0x1800144cb  mov     [rsp+190h+var_160], edi
0x1800144cf  mov     eax, [rsp+190h+var_140]
0x1800144d3  cmp     [rsp+190h+var_148], r13
0x1800144d8  mov     ecx, 1
0x1800144dd  cmovnz  eax, ecx
0x1800144e0  mov     [rsp+190h+var_140], eax
0x1800144e4  test    bl, bl
0x1800144e6  jnz     short loc_1800144F2
0x1800144e8  mov     [r15], cl
0x1800144eb  jmp     short loc_1800144F2
0x1800144ed  mov     rsi, [rsp+190h+lpMem]
0x1800144f2  test    byte ptr [rsp+190h+var_120], 8
0x1800144f7  jz      short loc_180014502
0x1800144f9  mov     rcx, rsi; lpMem
0x1800144fc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014501  nop
0x180014502  cmp     [rsp+190h+var_140], r13d
0x180014507  jz      short loc_180014525
0x180014509  mov     rcx, [rsp+190h+var_148]
0x18001450e  test    rcx, rcx
0x180014511  jz      short loc_180014520
0x180014513  mov     rax, [rcx]
0x180014516  mov     rax, [rax+10h]
0x18001451a  call    cs:__guard_dispatch_icall_fptr
0x180014520  mov     [rsp+190h+var_140], r13d
0x180014525  cmp     [rsp+190h+var_130], r13d
0x18001452a  jz      short loc_180014548
0x18001452c  mov     rcx, [rsp+190h+var_138]
0x180014531  test    rcx, rcx
0x180014534  jz      short loc_180014543
0x180014536  mov     rax, [rcx]
0x180014539  mov     rax, [rax+10h]
0x18001453d  call    cs:__guard_dispatch_icall_fptr
0x180014543  mov     [rsp+190h+var_130], r13d
0x180014548  cmp     [rsp+190h+var_150], r13d
0x18001454d  jz      short loc_18001456B
0x18001454f  mov     rcx, [rsp+190h+var_158]
0x180014554  test    rcx, rcx
0x180014557  jz      short loc_180014566
0x180014559  mov     rax, [rcx]
0x18001455c  mov     rax, [rax+10h]
0x180014560  call    cs:__guard_dispatch_icall_fptr
0x180014566  mov     [rsp+190h+var_150], r13d
0x18001456b  mov     eax, r12d
0x18001456e  mov     rbx, [rsp+190h+arg_18]
0x180014576  add     rsp, 160h
0x18001457d  pop     r15
0x18001457f  pop     r14
0x180014581  pop     r13
0x180014583  pop     r12
0x180014585  pop     rdi
0x180014586  pop     rsi
0x180014587  pop     rbp
0x180014588  retn
```
