# NgenTask::GetTaskIfRunning(bool &,IRegisteredTask * *,bool)

- ea: `0x180016218`
- end: `0x180016646`
- name: `?GetTaskIfRunning@NgenTask@@YAJAEA_NPEAPEAUIRegisteredTask@@_N@Z`
- size: `1070`
- prototype: `int(NgenTask *__hidden this, bool *, struct IRegisteredTask **, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016648`
- `0x180016708`

## callees

- `0x180013f04`
- `0x180013f88`
- `0x18001406c`
- `0x180016218`
- `0x180030568`
- `0x180030d84`
- `0x18003f280`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800162eb`
- `ole32!CoCreateInstance` at `0x1800162eb`
- `OLEAUT32!__imp_VariantInit` at `0x180016318`
- `OLEAUT32!__imp_VariantInit` at `0x180016338`
- `OLEAUT32!__imp_VariantInit` at `0x180016355`
- `OLEAUT32!__imp_VariantInit` at `0x180016373`
- `OLEAUT32!__imp_VariantInit` at `0x180016318`
- `OLEAUT32!__imp_VariantInit` at `0x180016338`
- `OLEAUT32!__imp_VariantInit` at `0x180016355`
- `OLEAUT32!__imp_VariantInit` at `0x180016373`
- `OLEAUT32!__imp_VariantClear` at `0x1800163f3`
- `OLEAUT32!__imp_VariantClear` at `0x1800163fe`
- `OLEAUT32!__imp_VariantClear` at `0x180016409`
- `OLEAUT32!__imp_VariantClear` at `0x180016414`
- `OLEAUT32!__imp_VariantClear` at `0x1800163f3`
- `OLEAUT32!__imp_VariantClear` at `0x1800163fe`
- `OLEAUT32!__imp_VariantClear` at `0x180016409`
- `OLEAUT32!__imp_VariantClear` at `0x180016414`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall NgenTask::GetTaskIfRunning(NgenTask *this, struct SString *a2, struct IRegisteredTask **a3)
{
  struct SString *v3; // r12
  HRESULT v5; // eax
  int v6; // edi
  int v7; // ecx
  LPVOID v8; // rdi
  _bstr_t *v9; // rax
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // r14
  void *v13; // rsi
  _bstr_t *v14; // rax
  __int64 v15; // rdx
  int v16; // eax
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+40h] [rbp-C0h]
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  int v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+60h] [rbp-A0h]
  IRecordInfo *v24; // [rsp+68h] [rbp-98h]
  _DWORD v25[2]; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+78h] [rbp-88h]
  void *lpMem; // [rsp+80h] [rbp-80h]
  IRecordInfo *pRecInfo; // [rsp+88h] [rbp-78h]
  __int128 v29; // [rsp+90h] [rbp-70h] BYREF
  IRecordInfo *v30; // [rsp+A0h] [rbp-60h]
  __int128 v31; // [rsp+B0h] [rbp-50h] BYREF
  IRecordInfo *v32; // [rsp+C0h] [rbp-40h]
  __int128 v33; // [rsp+D0h] [rbp-30h] BYREF
  IRecordInfo *v34; // [rsp+E0h] [rbp-20h]
  VARIANTARG v35; // [rsp+F0h] [rbp-10h] BYREF
  VARIANTARG v36; // [rsp+108h] [rbp+8h] BYREF
  VARIANTARG v37; // [rsp+120h] [rbp+20h] BYREF
  VARIANTARG pvarg; // [rsp+138h] [rbp+38h] BYREF
  VARIANTARG v39; // [rsp+150h] [rbp+50h] BYREF
  int v40; // [rsp+1B0h] [rbp+B0h] BYREF
  IRecordInfo *p_ppv; // [rsp+1C8h] [rbp+C8h] BYREF

  v3 = a2;
  ppv = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v18 = 0;
  v19 = 0;
  v25[0] = 2;
  v25[1] = 2;
  v26 = 16;
  lpMem = (void *)&SString::s_EmptyBuffer;
  LOBYTE(a2) = (_BYTE)a3;
  NgenTask::GetTaskName((NgenTask *)v25, a2, (bool)a3);
  *(_BYTE *)this = 0;
  p_ppv = (IRecordInfo *)&ppv;
  if ( v21 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v21 = 0;
  }
  ppv = 0;
  v5 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  v6 = v5;
  v7 = v21;
  if ( ppv )
    v7 = 1;
  v21 = v7;
  if ( v5 < 0 )
    goto LABEL_32;
  VariantInit(&pvarg);
  v29 = *(_OWORD *)&pvarg.vt;
  p_ppv = pvarg.pRecInfo;
  VariantInit(&v37);
  v31 = *(_OWORD *)&v37.vt;
  pRecInfo = v37.pRecInfo;
  VariantInit(&v36);
  v33 = *(_OWORD *)&v36.vt;
  v24 = v36.pRecInfo;
  VariantInit(&v35);
  v30 = p_ppv;
  v32 = pRecInfo;
  v34 = v24;
  v39 = v35;
  v6 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL))(
         ppv,
         &v39,
         &v33,
         &v31,
         &v29);
  VariantClear(&v35);
  VariantClear(&v36);
  VariantClear(&v37);
  VariantClear(&pvarg);
  if ( v6 < 0 )
    goto LABEL_32;
  v8 = ppv;
  v24 = (IRecordInfo *)&v22;
  if ( v23 )
  {
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v23 = 0;
  }
  v22 = 0;
  v9 = _bstr_t::_bstr_t((_bstr_t *)&p_ppv, L"\\Microsoft\\Windows\\.NET Framework");
  if ( *(_QWORD *)v9 )
    v10 = **(_QWORD **)v9;
  else
    v10 = 0;
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v8 + 56LL))(v8, v10, &v22);
  _bstr_t::~_bstr_t((_bstr_t *)&p_ppv);
  v11 = v23;
  v12 = v22;
  if ( v22 )
    v11 = 1;
  v23 = v11;
  if ( v6 < 0 )
  {
LABEL_32:
    v13 = lpMem;
  }
  else
  {
    v24 = (IRecordInfo *)&v18;
    if ( v19 )
    {
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v19 = 0;
    }
    v18 = 0;
    SString::ConvertToUnicode((SString *)v25);
    v13 = lpMem;
    v14 = _bstr_t::_bstr_t((_bstr_t *)&p_ppv, (const unsigned __int16 *)lpMem);
    if ( *(_QWORD *)v14 )
      v15 = **(_QWORD **)v14;
    else
      v15 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v12 + 104LL))(v12, v15, &v18);
    _bstr_t::~_bstr_t((_bstr_t *)&p_ppv);
    v16 = v19;
    if ( v18 )
      v16 = 1;
    v19 = v16;
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 72LL))(v18, &v40);
      if ( v6 >= 0 && v40 == 4 )
      {
        v19 = 0;
        *(_QWORD *)v3 = v18;
        *(_BYTE *)this = 1;
      }
    }
  }
  if ( (v26 & 8) != 0 )
    operator delete(v13);
  if ( v19 )
  {
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v19 = 0;
  }
  if ( v23 )
  {
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v23 = 0;
  }
  if ( v21 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v21 = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016218  mov     [rsp-8+arg_8], rbx
0x18001621d  push    rbp
0x18001621e  push    rsi
0x18001621f  push    rdi
0x180016220  push    r12
0x180016222  push    r13
0x180016224  push    r14
0x180016226  push    r15
0x180016228  lea     rbp, [rsp-70h]
0x18001622d  sub     rsp, 170h
0x180016234  mov     r12, rdx
0x180016237  mov     r15, rcx
0x18001623a  xor     r13d, r13d
0x18001623d  mov     [rsp+1A0h+var_170], r13d
0x180016242  mov     [rsp+1A0h+var_158], r13
0x180016247  mov     [rsp+1A0h+var_150], r13d
0x18001624c  mov     [rsp+1A0h+var_148], r13
0x180016251  mov     [rsp+1A0h+var_140], r13d
0x180016256  mov     [rsp+1A0h+var_168], r13
0x18001625b  mov     [rsp+1A0h+var_160], r13d
0x180016260  lea     r14d, [r13+2]
0x180016264  mov     [rsp+1A0h+var_130], r14d
0x180016269  mov     [rsp+1A0h+var_12C], r14d
0x18001626e  mov     [rsp+1A0h+var_128], 10h
0x180016276  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x18001627d  mov     [rbp+0A0h+lpMem], rax
0x180016281  mov     dl, r8b; struct SString *
0x180016284  lea     rcx, [rsp+1A0h+var_130]; this
0x180016289  call    ?GetTaskName@NgenTask@@YAXAEAVSString@@_N@Z; NgenTask::GetTaskName(SString &,bool)
0x18001628e  mov     [r15], r13b
0x180016291  lea     rax, [rsp+1A0h+var_158]
0x180016296  mov     [rbp+0A0h+arg_18], rax
0x18001629d  cmp     [rsp+1A0h+var_150], r13d
0x1800162a2  jz      short loc_1800162C0
0x1800162a4  mov     rcx, [rsp+1A0h+var_158]
0x1800162a9  test    rcx, rcx
0x1800162ac  jz      short loc_1800162BB
0x1800162ae  mov     rax, [rcx]
0x1800162b1  mov     rax, [rax+10h]
0x1800162b5  call    cs:__guard_dispatch_icall_fptr
0x1800162bb  mov     [rsp+1A0h+var_150], r13d
0x1800162c0  mov     [rsp+1A0h+var_158], r13
0x1800162c5  mov     esi, 1
0x1800162ca  mov     [rsp+1A0h+var_170], esi
0x1800162ce  lea     rax, [rsp+1A0h+var_158]
0x1800162d3  mov     [rsp+1A0h+ppv], rax; ppv
0x1800162d8  lea     r9, IID_ITaskService; riid
0x1800162df  mov     r8d, esi; dwClsContext
0x1800162e2  xor     edx, edx; pUnkOuter
0x1800162e4  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800162eb  call    cs:__imp_CoCreateInstance
0x1800162f1  mov     edi, eax
0x1800162f3  mov     ebx, esi
0x1800162f5  and     ebx, 0FFFFFFFEh
0x1800162f8  mov     [rsp+1A0h+var_170], ebx
0x1800162fc  mov     ecx, [rsp+1A0h+var_150]
0x180016300  cmp     [rsp+1A0h+var_158], r13
0x180016305  cmovnz  ecx, esi
0x180016308  mov     [rsp+1A0h+var_150], ecx
0x18001630c  test    eax, eax
0x18001630e  js      loc_1800165AC
0x180016314  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x180016318  call    cs:__imp_VariantInit
0x18001631e  nop
0x18001631f  movups  xmm0, xmmword ptr [rbp+0A0h+pvarg]
0x180016323  movups  [rbp+0A0h+var_110], xmm0
0x180016327  movsd   xmm0, qword ptr [rbp+0A0h+pvarg+10h]
0x18001632c  movsd   [rbp+0A0h+arg_18], xmm0
0x180016334  lea     rcx, [rbp+0A0h+var_80]; pvarg
0x180016338  call    cs:__imp_VariantInit
0x18001633e  nop
0x18001633f  movups  xmm0, xmmword ptr [rbp+0A0h+var_80]
0x180016343  movups  [rbp+0A0h+var_F0], xmm0
0x180016347  movsd   xmm0, qword ptr [rbp+0A0h+var_80+10h]
0x18001634c  movsd   [rbp+0A0h+var_118], xmm0
0x180016351  lea     rcx, [rbp+0A0h+var_98]; pvarg
0x180016355  call    cs:__imp_VariantInit
0x18001635b  nop
0x18001635c  movups  xmm0, xmmword ptr [rbp+0A0h+var_98]
0x180016360  movups  [rbp+0A0h+var_D0], xmm0
0x180016364  movsd   xmm0, qword ptr [rbp+0A0h+var_98+10h]
0x180016369  movsd   [rsp+1A0h+var_138], xmm0
0x18001636f  lea     rcx, [rbp+0A0h+var_B0]; pvarg
0x180016373  call    cs:__imp_VariantInit
0x180016379  nop
0x18001637a  movups  xmm0, [rbp+0A0h+var_110]
0x18001637e  movaps  [rbp+0A0h+var_110], xmm0
0x180016382  movsd   xmm0, [rbp+0A0h+arg_18]
0x18001638a  movsd   [rbp+0A0h+var_100], xmm0
0x18001638f  movups  xmm0, [rbp+0A0h+var_F0]
0x180016393  movaps  [rbp+0A0h+var_F0], xmm0
0x180016397  movsd   xmm0, [rbp+0A0h+var_118]
0x18001639c  movsd   [rbp+0A0h+var_E0], xmm0
0x1800163a1  movups  xmm0, [rbp+0A0h+var_D0]
0x1800163a5  movaps  [rbp+0A0h+var_D0], xmm0
0x1800163a9  movsd   xmm0, [rsp+1A0h+var_138]
0x1800163af  movsd   [rbp+0A0h+var_C0], xmm0
0x1800163b4  movups  xmm0, xmmword ptr [rbp+0A0h+var_B0]
0x1800163b8  movaps  [rbp+0A0h+var_50], xmm0
0x1800163bc  movsd   xmm1, qword ptr [rbp+0A0h+var_B0+10h]
0x1800163c1  movsd   [rbp+0A0h+var_40], xmm1
0x1800163c6  mov     rcx, [rsp+1A0h+var_158]
0x1800163cb  mov     rax, [rcx]
0x1800163ce  lea     rdx, [rbp+0A0h+var_110]
0x1800163d2  mov     [rsp+1A0h+ppv], rdx
0x1800163d7  lea     r9, [rbp+0A0h+var_F0]
0x1800163db  lea     r8, [rbp+0A0h+var_D0]
0x1800163df  lea     rdx, [rbp+0A0h+var_50]
0x1800163e3  mov     rax, [rax+50h]
0x1800163e7  call    cs:__guard_dispatch_icall_fptr
0x1800163ed  mov     edi, eax
0x1800163ef  lea     rcx, [rbp+0A0h+var_B0]; pvarg
0x1800163f3  call    cs:__imp_VariantClear
0x1800163f9  nop
0x1800163fa  lea     rcx, [rbp+0A0h+var_98]; pvarg
0x1800163fe  call    cs:__imp_VariantClear
0x180016404  nop
0x180016405  lea     rcx, [rbp+0A0h+var_80]; pvarg
0x180016409  call    cs:__imp_VariantClear
0x18001640f  nop
0x180016410  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x180016414  call    cs:__imp_VariantClear
0x18001641a  test    edi, edi
0x18001641c  js      loc_1800165AC
0x180016422  mov     rdi, [rsp+1A0h+var_158]
0x180016427  lea     rax, [rsp+1A0h+var_148]
0x18001642c  mov     [rsp+1A0h+var_138], rax
0x180016431  cmp     [rsp+1A0h+var_140], r13d
0x180016436  jz      short loc_180016454
0x180016438  mov     rcx, [rsp+1A0h+var_148]
0x18001643d  test    rcx, rcx
0x180016440  jz      short loc_18001644F
0x180016442  mov     rax, [rcx]
0x180016445  mov     rax, [rax+10h]
0x180016449  call    cs:__guard_dispatch_icall_fptr
0x18001644f  mov     [rsp+1A0h+var_140], r13d
0x180016454  mov     [rsp+1A0h+var_148], r13
0x180016459  or      ebx, r14d
0x18001645c  mov     [rsp+1A0h+var_170], ebx
0x180016460  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\.NET Framework"
0x180016467  lea     rcx, [rbp+0A0h+arg_18]; this
0x18001646e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180016473  nop
0x180016474  mov     rcx, [rax]
0x180016477  test    rcx, rcx
0x18001647a  jz      short loc_180016481
0x18001647c  mov     rdx, [rcx]
0x18001647f  jmp     short loc_180016484
0x180016481  mov     rdx, r13
0x180016484  mov     rax, [rdi]
0x180016487  lea     r8, [rsp+1A0h+var_148]
0x18001648c  mov     rcx, rdi
0x18001648f  mov     rax, [rax+38h]
0x180016493  call    cs:__guard_dispatch_icall_fptr
0x180016499  mov     edi, eax
0x18001649b  lea     rcx, [rbp+0A0h+arg_18]; this
0x1800164a2  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800164a7  and     ebx, 0FFFFFFFDh
0x1800164aa  mov     [rsp+1A0h+var_170], ebx
0x1800164ae  mov     eax, [rsp+1A0h+var_140]
0x1800164b2  mov     r14, [rsp+1A0h+var_148]
0x1800164b7  test    r14, r14
0x1800164ba  cmovnz  eax, esi
0x1800164bd  mov     [rsp+1A0h+var_140], eax
0x1800164c1  test    edi, edi
0x1800164c3  js      loc_1800165AC
0x1800164c9  lea     rax, [rsp+1A0h+var_168]
0x1800164ce  mov     [rsp+1A0h+var_138], rax
0x1800164d3  cmp     [rsp+1A0h+var_160], r13d
0x1800164d8  jz      short loc_1800164F6
0x1800164da  mov     rcx, [rsp+1A0h+var_168]
0x1800164df  test    rcx, rcx
0x1800164e2  jz      short loc_1800164F1
0x1800164e4  mov     rax, [rcx]
0x1800164e7  mov     rax, [rax+10h]
0x1800164eb  call    cs:__guard_dispatch_icall_fptr
0x1800164f1  mov     [rsp+1A0h+var_160], r13d
0x1800164f6  mov     [rsp+1A0h+var_168], r13
0x1800164fb  or      ebx, 4
0x1800164fe  mov     [rsp+1A0h+var_170], ebx
0x180016502  lea     rcx, [rsp+1A0h+var_130]; this
0x180016507  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001650c  mov     rsi, [rbp+0A0h+lpMem]
0x180016510  mov     rdx, rsi; unsigned __int16 *
0x180016513  lea     rcx, [rbp+0A0h+arg_18]; this
0x18001651a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001651f  nop
0x180016520  mov     rcx, [rax]
0x180016523  test    rcx, rcx
0x180016526  jz      short loc_18001652D
0x180016528  mov     rdx, [rcx]
0x18001652b  jmp     short loc_180016530
0x18001652d  mov     rdx, r13
0x180016530  mov     rax, [r14]
0x180016533  lea     r8, [rsp+1A0h+var_168]
0x180016538  mov     rcx, r14
0x18001653b  mov     rax, [rax+68h]
0x18001653f  call    cs:__guard_dispatch_icall_fptr
0x180016545  mov     edi, eax
0x180016547  lea     rcx, [rbp+0A0h+arg_18]; this
0x18001654e  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180016553  and     ebx, 0FFFFFFFBh
0x180016556  mov     [rsp+1A0h+var_170], ebx
0x18001655a  mov     eax, [rsp+1A0h+var_160]
0x18001655e  mov     rcx, [rsp+1A0h+var_168]
0x180016563  test    rcx, rcx
0x180016566  mov     ebx, 1
0x18001656b  cmovnz  eax, ebx
0x18001656e  mov     [rsp+1A0h+var_160], eax
0x180016572  test    edi, edi
0x180016574  js      short loc_1800165B0
0x180016576  mov     rax, [rcx]
0x180016579  lea     rdx, [rbp+0A0h+arg_0]
0x180016580  mov     rax, [rax+48h]
0x180016584  call    cs:__guard_dispatch_icall_fptr
0x18001658a  mov     edi, eax
0x18001658c  test    eax, eax
0x18001658e  js      short loc_1800165B0
0x180016590  cmp     [rbp+0A0h+arg_0], 4
0x180016597  jnz     short loc_1800165B0
0x180016599  mov     [rsp+1A0h+var_160], r13d
0x18001659e  mov     rax, [rsp+1A0h+var_168]
0x1800165a3  mov     [r12], rax
0x1800165a7  mov     [r15], bl
0x1800165aa  jmp     short loc_1800165B0
0x1800165ac  mov     rsi, [rbp+0A0h+lpMem]
0x1800165b0  test    byte ptr [rsp+1A0h+var_128], 8
0x1800165b5  jz      short loc_1800165C0
0x1800165b7  mov     rcx, rsi; lpMem
0x1800165ba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800165bf  nop
0x1800165c0  cmp     [rsp+1A0h+var_160], r13d
0x1800165c5  jz      short loc_1800165E3
0x1800165c7  mov     rcx, [rsp+1A0h+var_168]
0x1800165cc  test    rcx, rcx
0x1800165cf  jz      short loc_1800165DE
0x1800165d1  mov     rax, [rcx]
0x1800165d4  mov     rax, [rax+10h]
0x1800165d8  call    cs:__guard_dispatch_icall_fptr
0x1800165de  mov     [rsp+1A0h+var_160], r13d
0x1800165e3  cmp     [rsp+1A0h+var_140], r13d
0x1800165e8  jz      short loc_180016606
0x1800165ea  mov     rcx, [rsp+1A0h+var_148]
0x1800165ef  test    rcx, rcx
0x1800165f2  jz      short loc_180016601
0x1800165f4  mov     rax, [rcx]
0x1800165f7  mov     rax, [rax+10h]
0x1800165fb  call    cs:__guard_dispatch_icall_fptr
0x180016601  mov     [rsp+1A0h+var_140], r13d
0x180016606  cmp     [rsp+1A0h+var_150], r13d
0x18001660b  jz      short loc_180016629
0x18001660d  mov     rcx, [rsp+1A0h+var_158]
0x180016612  test    rcx, rcx
0x180016615  jz      short loc_180016624
0x180016617  mov     rax, [rcx]
0x18001661a  mov     rax, [rax+10h]
0x18001661e  call    cs:__guard_dispatch_icall_fptr
0x180016624  mov     [rsp+1A0h+var_150], r13d
0x180016629  mov     eax, edi
0x18001662b  mov     rbx, [rsp+1A0h+arg_8]
0x180016633  add     rsp, 170h
0x18001663a  pop     r15
0x18001663c  pop     r14
0x18001663e  pop     r13
0x180016640  pop     r12
0x180016642  pop     rdi
0x180016643  pop     rsi
0x180016644  pop     rbp
0x180016645  retn
```
