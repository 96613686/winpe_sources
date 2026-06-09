# NgenTask::StartTask(void)

- ea: `0x1800171a8`
- end: `0x180017696`
- name: `?StartTask@NgenTask@@YAJXZ`
- size: `1262`
- prototype: `__int64 __fastcall(NgenTask *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180008500`
- `0x180015208`
- `0x180016fd4`

## callees

- `0x180013f04`
- `0x180013f88`
- `0x18001406c`
- `0x18001458c`
- `0x180016920`
- `0x180016a9c`
- `0x1800171a8`
- `0x180030568`
- `0x180030d84`
- `0x18003f280`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180017297`
- `ole32!CoCreateInstance` at `0x180017297`
- `OLEAUT32!__imp_VariantInit` at `0x1800172c6`
- `OLEAUT32!__imp_VariantInit` at `0x1800172e6`
- `OLEAUT32!__imp_VariantInit` at `0x180017306`
- `OLEAUT32!__imp_VariantInit` at `0x180017326`
- `OLEAUT32!__imp_VariantInit` at `0x180017533`
- `OLEAUT32!__imp_VariantInit` at `0x1800172c6`
- `OLEAUT32!__imp_VariantInit` at `0x1800172e6`
- `OLEAUT32!__imp_VariantInit` at `0x180017306`
- `OLEAUT32!__imp_VariantInit` at `0x180017326`
- `OLEAUT32!__imp_VariantInit` at `0x180017533`
- `OLEAUT32!__imp_VariantClear` at `0x1800173ab`
- `OLEAUT32!__imp_VariantClear` at `0x1800173b6`
- `OLEAUT32!__imp_VariantClear` at `0x1800173c1`
- `OLEAUT32!__imp_VariantClear` at `0x1800173cc`
- `OLEAUT32!__imp_VariantClear` at `0x1800175db`
- `OLEAUT32!__imp_VariantClear` at `0x1800173ab`
- `OLEAUT32!__imp_VariantClear` at `0x1800173b6`
- `OLEAUT32!__imp_VariantClear` at `0x1800173c1`
- `OLEAUT32!__imp_VariantClear` at `0x1800173cc`
- `OLEAUT32!__imp_VariantClear` at `0x1800175db`

## pseudocode

```c
// Hidden C++ exception states: #wind=49
__int64 __fastcall NgenTask::StartTask(NgenTask *this, __int64 a2, bool a3)
{
  bool v3; // dl
  NgenTask *v4; // rcx
  NgenTask *v5; // rcx
  __int64 v6; // rdx
  bool v7; // r8
  NgenTask *v8; // rcx
  int v9; // edi
  int v10; // eax
  LPVOID v11; // rdi
  _bstr_t *v12; // rax
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // r14
  void *v16; // rsi
  _bstr_t *v17; // rax
  __int64 v18; // rdx
  int v19; // eax
  __int128 v20; // xmm0
  IRecordInfo *v21; // xmm1_8
  __int64 v22; // rdi
  int v23; // eax
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  int v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  int v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h] BYREF
  int v30; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h] BYREF
  int v32; // [rsp+70h] [rbp-90h]
  _DWORD v33[2]; // [rsp+78h] [rbp-88h] BYREF
  int v34; // [rsp+80h] [rbp-80h]
  void *lpMem; // [rsp+88h] [rbp-78h]
  VARIANTARG pvarg; // [rsp+90h] [rbp-70h] BYREF
  __int128 v37; // [rsp+B0h] [rbp-50h] BYREF
  IRecordInfo *v38; // [rsp+C0h] [rbp-40h]
  VARIANTARG v39; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v40; // [rsp+F0h] [rbp-10h] BYREF
  IRecordInfo *v41; // [rsp+100h] [rbp+0h]
  __int128 v42; // [rsp+110h] [rbp+10h] BYREF
  IRecordInfo *v43; // [rsp+120h] [rbp+20h]
  VARIANTARG v44; // [rsp+130h] [rbp+30h] BYREF
  VARIANTARG v45; // [rsp+148h] [rbp+48h] BYREF
  VARIANTARG v46; // [rsp+160h] [rbp+60h] BYREF
  IRecordInfo *p_ppv; // [rsp+1C0h] [rbp+C0h] BYREF
  IRecordInfo *pRecInfo; // [rsp+1C8h] [rbp+C8h]
  IRecordInfo *v49; // [rsp+1D0h] [rbp+D0h]

  ppv = 0;
  v26 = 0;
  v31 = 0;
  v32 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v33[0] = 2;
  v33[1] = 2;
  v34 = 16;
  lpMem = (void *)&SString::s_EmptyBuffer;
  NgenTask::GetTaskName((NgenTask *)v33, 0, a3);
  NgenTask::SetTaskHighPriority(v4, v3);
  LOBYTE(v5) = 1;
  v9 = NgenTask::SetTaskBootTrigger(v5, v6, v7);
  if ( v9 < 0 || NgenTask::IsTaskPaused(v8) )
    goto LABEL_34;
  p_ppv = (IRecordInfo *)&ppv;
  ppv = 0;
  v9 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  v10 = v26;
  if ( ppv )
    v10 = 1;
  v26 = v10;
  if ( v9 < 0 )
    goto LABEL_34;
  VariantInit(&pvarg);
  v40 = *(_OWORD *)&pvarg.vt;
  p_ppv = pvarg.pRecInfo;
  VariantInit(&v46);
  v42 = *(_OWORD *)&v46.vt;
  pRecInfo = v46.pRecInfo;
  VariantInit(&v45);
  v37 = *(_OWORD *)&v45.vt;
  v49 = v45.pRecInfo;
  VariantInit(&v44);
  v41 = p_ppv;
  v43 = pRecInfo;
  v38 = v49;
  v39 = v44;
  v9 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL))(
         ppv,
         &v39,
         &v37,
         &v42,
         &v40);
  VariantClear(&v44);
  VariantClear(&v45);
  VariantClear(&v46);
  VariantClear(&pvarg);
  if ( v9 < 0 )
    goto LABEL_34;
  v11 = ppv;
  pRecInfo = (IRecordInfo *)&v31;
  if ( v32 )
  {
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v32 = 0;
  }
  v31 = 0;
  v12 = _bstr_t::_bstr_t((_bstr_t *)&p_ppv, L"\\Microsoft\\Windows\\.NET Framework");
  if ( *(_QWORD *)v12 )
    v13 = **(_QWORD **)v12;
  else
    v13 = 0;
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v11 + 56LL))(v11, v13, &v31);
  _bstr_t::~_bstr_t((_bstr_t *)&p_ppv);
  v14 = v32;
  v15 = v31;
  if ( v31 )
    v14 = 1;
  v32 = v14;
  if ( v9 < 0 )
  {
LABEL_34:
    v16 = lpMem;
  }
  else
  {
    pRecInfo = (IRecordInfo *)&v27;
    if ( v28 )
    {
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      v28 = 0;
    }
    v27 = 0;
    SString::ConvertToUnicode((SString *)v33);
    v16 = lpMem;
    v17 = _bstr_t::_bstr_t((_bstr_t *)&p_ppv, (const unsigned __int16 *)lpMem);
    if ( *(_QWORD *)v17 )
      v18 = **(_QWORD **)v17;
    else
      v18 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v15 + 104LL))(v15, v18, &v27);
    _bstr_t::~_bstr_t((_bstr_t *)&p_ppv);
    v19 = v28;
    if ( v27 )
      v19 = 1;
    v28 = v19;
    if ( v9 >= 0 )
    {
      VariantInit(&pvarg);
      v20 = *(_OWORD *)&pvarg.vt;
      v37 = *(_OWORD *)&pvarg.vt;
      v21 = pvarg.pRecInfo;
      p_ppv = pvarg.pRecInfo;
      v22 = v27;
      pRecInfo = (IRecordInfo *)&v29;
      if ( v30 )
      {
        if ( v29 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          v20 = v37;
          v21 = p_ppv;
        }
        v30 = 0;
      }
      v29 = 0;
      *(_OWORD *)&v39.vt = v20;
      v39.pRecInfo = v21;
      v9 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64 *))(*(_QWORD *)v22 + 96LL))(v22, &v39, &v29);
      v23 = v30;
      if ( v29 )
        v23 = 1;
      v30 = v23;
      VariantClear(&pvarg);
    }
  }
  if ( (v34 & 8) != 0 )
    operator delete(v16);
  if ( v30 )
  {
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v30 = 0;
  }
  if ( v28 )
  {
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v28 = 0;
  }
  if ( v32 )
  {
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v32 = 0;
  }
  if ( v26 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v26 = 0;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800171a8  push    rbp
0x1800171aa  push    rbx
0x1800171ab  push    rsi
0x1800171ac  push    rdi
0x1800171ad  push    r12
0x1800171af  push    r14
0x1800171b1  push    r15
0x1800171b3  lea     rbp, [rsp-80h]
0x1800171b8  sub     rsp, 180h
0x1800171bf  xor     r15d, r15d
0x1800171c2  mov     [rsp+1B0h+var_180], r15d
0x1800171c7  mov     [rsp+1B0h+var_178], r15
0x1800171cc  mov     [rsp+1B0h+var_170], r15d
0x1800171d1  mov     [rsp+1B0h+var_148], r15
0x1800171d6  mov     [rsp+1B0h+var_140], r15d
0x1800171db  mov     [rsp+1B0h+var_168], r15
0x1800171e0  mov     [rsp+1B0h+var_160], r15d
0x1800171e5  mov     [rsp+1B0h+var_158], r15
0x1800171ea  mov     [rsp+1B0h+var_150], r15d
0x1800171ef  lea     esi, [r15+2]
0x1800171f3  mov     [rsp+1B0h+var_138], esi
0x1800171f7  mov     [rsp+1B0h+var_134], esi
0x1800171fb  mov     [rbp+0B0h+var_130], 10h
0x180017202  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180017209  mov     [rbp+0B0h+lpMem], rax
0x18001720d  xor     edx, edx; struct SString *
0x18001720f  lea     rcx, [rsp+1B0h+var_138]; this
0x180017214  call    ?GetTaskName@NgenTask@@YAXAEAVSString@@_N@Z; NgenTask::GetTaskName(SString &,bool)
0x180017219  call    ?SetTaskHighPriority@NgenTask@@YAX_N@Z; NgenTask::SetTaskHighPriority(bool)
0x18001721e  lea     r12d, [r15+1]
0x180017222  mov     cl, r12b; this
0x180017225  call    ?SetTaskBootTrigger@NgenTask@@YAJ_N@Z; NgenTask::SetTaskBootTrigger(bool)
0x18001722a  mov     edi, eax
0x18001722c  test    eax, eax
0x18001722e  js      loc_1800175E3
0x180017234  call    ?IsTaskPaused@NgenTask@@YA_NXZ; NgenTask::IsTaskPaused(void)
0x180017239  test    al, al
0x18001723b  jnz     loc_1800175E3
0x180017241  lea     rax, [rsp+1B0h+var_178]
0x180017246  mov     [rbp+0B0h+arg_0], rax
0x18001724d  cmp     [rsp+1B0h+var_170], r15d
0x180017252  jz      short loc_180017270
0x180017254  mov     rcx, [rsp+1B0h+var_178]
0x180017259  test    rcx, rcx
0x18001725c  jz      short loc_18001726B
0x18001725e  mov     rax, [rcx]
0x180017261  mov     rax, [rax+10h]
0x180017265  call    cs:__guard_dispatch_icall_fptr
0x18001726b  mov     [rsp+1B0h+var_170], r15d
0x180017270  mov     [rsp+1B0h+var_178], r15
0x180017275  mov     [rsp+1B0h+var_180], r12d
0x18001727a  lea     rax, [rsp+1B0h+var_178]
0x18001727f  mov     [rsp+1B0h+ppv], rax; ppv
0x180017284  lea     r9, IID_ITaskService; riid
0x18001728b  mov     r8d, r12d; dwClsContext
0x18001728e  xor     edx, edx; pUnkOuter
0x180017290  lea     rcx, CLSID_TaskScheduler; rclsid
0x180017297  call    cs:__imp_CoCreateInstance
0x18001729d  mov     edi, eax
0x18001729f  mov     ebx, r12d
0x1800172a2  and     ebx, 0FFFFFFFEh
0x1800172a5  mov     [rsp+1B0h+var_180], ebx
0x1800172a9  mov     eax, [rsp+1B0h+var_170]
0x1800172ad  cmp     [rsp+1B0h+var_178], r15
0x1800172b2  cmovnz  eax, r12d
0x1800172b6  mov     [rsp+1B0h+var_170], eax
0x1800172ba  test    edi, edi
0x1800172bc  js      loc_1800175E3
0x1800172c2  lea     rcx, [rbp+0B0h+pvarg]; pvarg
0x1800172c6  call    cs:__imp_VariantInit
0x1800172cc  nop
0x1800172cd  movups  xmm0, xmmword ptr [rbp+0B0h+pvarg]
0x1800172d1  movups  [rbp+0B0h+var_C0], xmm0
0x1800172d5  movsd   xmm0, qword ptr [rbp+0B0h+pvarg+10h]
0x1800172da  movsd   [rbp+0B0h+arg_0], xmm0
0x1800172e2  lea     rcx, [rbp+0B0h+var_50]; pvarg
0x1800172e6  call    cs:__imp_VariantInit
0x1800172ec  nop
0x1800172ed  movups  xmm0, xmmword ptr [rbp+0B0h+var_50]
0x1800172f1  movups  [rbp+0B0h+var_A0], xmm0
0x1800172f5  movsd   xmm0, qword ptr [rbp+0B0h+var_50+10h]
0x1800172fa  movsd   [rbp+0B0h+arg_8], xmm0
0x180017302  lea     rcx, [rbp+0B0h+var_68]; pvarg
0x180017306  call    cs:__imp_VariantInit
0x18001730c  nop
0x18001730d  movups  xmm0, xmmword ptr [rbp+0B0h+var_68]
0x180017311  movups  [rbp+0B0h+var_100], xmm0
0x180017315  movsd   xmm0, qword ptr [rbp+0B0h+var_68+10h]
0x18001731a  movsd   [rbp+0B0h+arg_10], xmm0
0x180017322  lea     rcx, [rbp+0B0h+var_80]; pvarg
0x180017326  call    cs:__imp_VariantInit
0x18001732c  nop
0x18001732d  movups  xmm0, [rbp+0B0h+var_C0]
0x180017331  movaps  [rbp+0B0h+var_C0], xmm0
0x180017335  movsd   xmm0, [rbp+0B0h+arg_0]
0x18001733d  movsd   [rbp+0B0h+var_B0], xmm0
0x180017342  movups  xmm0, [rbp+0B0h+var_A0]
0x180017346  movaps  [rbp+0B0h+var_A0], xmm0
0x18001734a  movsd   xmm0, [rbp+0B0h+arg_8]
0x180017352  movsd   [rbp+0B0h+var_90], xmm0
0x180017357  movups  xmm0, [rbp+0B0h+var_100]
0x18001735b  movaps  [rbp+0B0h+var_100], xmm0
0x18001735f  movsd   xmm0, [rbp+0B0h+arg_10]
0x180017367  movsd   [rbp+0B0h+var_F0], xmm0
0x18001736c  movups  xmm0, xmmword ptr [rbp+0B0h+var_80]
0x180017370  movaps  [rbp+0B0h+var_E0], xmm0
0x180017374  movsd   xmm1, qword ptr [rbp+0B0h+var_80+10h]
0x180017379  movsd   [rbp+0B0h+var_D0], xmm1
0x18001737e  mov     rcx, [rsp+1B0h+var_178]
0x180017383  mov     rax, [rcx]
0x180017386  lea     rdx, [rbp+0B0h+var_C0]
0x18001738a  mov     [rsp+1B0h+ppv], rdx
0x18001738f  lea     r9, [rbp+0B0h+var_A0]
0x180017393  lea     r8, [rbp+0B0h+var_100]
0x180017397  lea     rdx, [rbp+0B0h+var_E0]
0x18001739b  mov     rax, [rax+50h]
0x18001739f  call    cs:__guard_dispatch_icall_fptr
0x1800173a5  mov     edi, eax
0x1800173a7  lea     rcx, [rbp+0B0h+var_80]; pvarg
0x1800173ab  call    cs:__imp_VariantClear
0x1800173b1  nop
0x1800173b2  lea     rcx, [rbp+0B0h+var_68]; pvarg
0x1800173b6  call    cs:__imp_VariantClear
0x1800173bc  nop
0x1800173bd  lea     rcx, [rbp+0B0h+var_50]; pvarg
0x1800173c1  call    cs:__imp_VariantClear
0x1800173c7  nop
0x1800173c8  lea     rcx, [rbp+0B0h+pvarg]; pvarg
0x1800173cc  call    cs:__imp_VariantClear
0x1800173d2  test    edi, edi
0x1800173d4  js      loc_1800175E3
0x1800173da  mov     rdi, [rsp+1B0h+var_178]
0x1800173df  lea     rax, [rsp+1B0h+var_148]
0x1800173e4  mov     [rbp+0B0h+arg_8], rax
0x1800173eb  cmp     [rsp+1B0h+var_140], r15d
0x1800173f0  jz      short loc_18001740E
0x1800173f2  mov     rcx, [rsp+1B0h+var_148]
0x1800173f7  test    rcx, rcx
0x1800173fa  jz      short loc_180017409
0x1800173fc  mov     rax, [rcx]
0x1800173ff  mov     rax, [rax+10h]
0x180017403  call    cs:__guard_dispatch_icall_fptr
0x180017409  mov     [rsp+1B0h+var_140], r15d
0x18001740e  mov     [rsp+1B0h+var_148], r15
0x180017413  or      ebx, esi
0x180017415  mov     [rsp+1B0h+var_180], ebx
0x180017419  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\.NET Framework"
0x180017420  lea     rcx, [rbp+0B0h+arg_0]; this
0x180017427  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001742c  nop
0x18001742d  mov     rcx, [rax]
0x180017430  test    rcx, rcx
0x180017433  jz      short loc_18001743A
0x180017435  mov     rdx, [rcx]
0x180017438  jmp     short loc_18001743D
0x18001743a  mov     rdx, r15
0x18001743d  mov     rax, [rdi]
0x180017440  lea     r8, [rsp+1B0h+var_148]
0x180017445  mov     rcx, rdi
0x180017448  mov     rax, [rax+38h]
0x18001744c  call    cs:__guard_dispatch_icall_fptr
0x180017452  mov     edi, eax
0x180017454  lea     rcx, [rbp+0B0h+arg_0]; this
0x18001745b  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180017460  and     ebx, 0FFFFFFFDh
0x180017463  mov     [rsp+1B0h+var_180], ebx
0x180017467  mov     eax, [rsp+1B0h+var_140]
0x18001746b  mov     r14, [rsp+1B0h+var_148]
0x180017470  test    r14, r14
0x180017473  cmovnz  eax, r12d
0x180017477  mov     [rsp+1B0h+var_140], eax
0x18001747b  test    edi, edi
0x18001747d  js      loc_1800175E3
0x180017483  lea     rax, [rsp+1B0h+var_168]
0x180017488  mov     [rbp+0B0h+arg_8], rax
0x18001748f  cmp     [rsp+1B0h+var_160], r15d
0x180017494  jz      short loc_1800174B2
0x180017496  mov     rcx, [rsp+1B0h+var_168]
0x18001749b  test    rcx, rcx
0x18001749e  jz      short loc_1800174AD
0x1800174a0  mov     rax, [rcx]
0x1800174a3  mov     rax, [rax+10h]
0x1800174a7  call    cs:__guard_dispatch_icall_fptr
0x1800174ad  mov     [rsp+1B0h+var_160], r15d
0x1800174b2  mov     [rsp+1B0h+var_168], r15
0x1800174b7  or      ebx, 4
0x1800174ba  mov     [rsp+1B0h+var_180], ebx
0x1800174be  lea     rcx, [rsp+1B0h+var_138]; this
0x1800174c3  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800174c8  mov     rsi, [rbp+0B0h+lpMem]
0x1800174cc  mov     rdx, rsi; unsigned __int16 *
0x1800174cf  lea     rcx, [rbp+0B0h+arg_0]; this
0x1800174d6  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800174db  nop
0x1800174dc  mov     rcx, [rax]
0x1800174df  test    rcx, rcx
0x1800174e2  jz      short loc_1800174E9
0x1800174e4  mov     rdx, [rcx]
0x1800174e7  jmp     short loc_1800174EC
0x1800174e9  mov     rdx, r15
0x1800174ec  mov     rax, [r14]
0x1800174ef  lea     r8, [rsp+1B0h+var_168]
0x1800174f4  mov     rcx, r14
0x1800174f7  mov     rax, [rax+68h]
0x1800174fb  call    cs:__guard_dispatch_icall_fptr
0x180017501  mov     edi, eax
0x180017503  lea     rcx, [rbp+0B0h+arg_0]; this
0x18001750a  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001750f  and     ebx, 0FFFFFFFBh
0x180017512  mov     [rsp+1B0h+var_180], ebx
0x180017516  mov     eax, [rsp+1B0h+var_160]
0x18001751a  cmp     [rsp+1B0h+var_168], r15
0x18001751f  cmovnz  eax, r12d
0x180017523  mov     [rsp+1B0h+var_160], eax
0x180017527  test    edi, edi
0x180017529  js      loc_1800175E7
0x18001752f  lea     rcx, [rbp+0B0h+pvarg]; pvarg
0x180017533  call    cs:__imp_VariantInit
0x180017539  nop
0x18001753a  movups  xmm0, xmmword ptr [rbp+0B0h+pvarg]
0x18001753e  movups  [rbp+0B0h+var_100], xmm0
0x180017542  movsd   xmm1, qword ptr [rbp+0B0h+pvarg+10h]
0x180017547  movsd   [rbp+0B0h+arg_0], xmm1
0x18001754f  mov     rdi, [rsp+1B0h+var_168]
0x180017554  lea     rax, [rsp+1B0h+var_158]
0x180017559  mov     [rbp+0B0h+arg_8], rax
0x180017560  cmp     [rsp+1B0h+var_150], r15d
0x180017565  jz      short loc_18001758F
0x180017567  mov     rcx, [rsp+1B0h+var_158]
0x18001756c  test    rcx, rcx
0x18001756f  jz      short loc_18001758A
0x180017571  mov     rax, [rcx]
0x180017574  mov     rax, [rax+10h]
0x180017578  call    cs:__guard_dispatch_icall_fptr
0x18001757e  movups  xmm0, [rbp+0B0h+var_100]
0x180017582  movsd   xmm1, [rbp+0B0h+arg_0]
0x18001758a  mov     [rsp+1B0h+var_150], r15d
0x18001758f  mov     [rsp+1B0h+var_158], r15
0x180017594  or      ebx, 8
0x180017597  mov     [rsp+1B0h+var_180], ebx
0x18001759b  movaps  [rbp+0B0h+var_E0], xmm0
0x18001759f  movsd   [rbp+0B0h+var_D0], xmm1
0x1800175a4  mov     rax, [rdi]
0x1800175a7  lea     r8, [rsp+1B0h+var_158]
0x1800175ac  lea     rdx, [rbp+0B0h+var_E0]
0x1800175b0  mov     rcx, rdi
0x1800175b3  mov     rax, [rax+60h]
0x1800175b7  call    cs:__guard_dispatch_icall_fptr
0x1800175bd  mov     edi, eax
0x1800175bf  and     ebx, 0FFFFFFF7h
0x1800175c2  mov     [rsp+1B0h+var_180], ebx
0x1800175c6  mov     eax, [rsp+1B0h+var_150]
0x1800175ca  cmp     [rsp+1B0h+var_158], r15
0x1800175cf  cmovnz  eax, r12d
0x1800175d3  mov     [rsp+1B0h+var_150], eax
0x1800175d7  lea     rcx, [rbp+0B0h+pvarg]; pvarg
0x1800175db  call    cs:__imp_VariantClear
0x1800175e1  jmp     short loc_1800175E7
0x1800175e3  mov     rsi, [rbp+0B0h+lpMem]
0x1800175e7  test    byte ptr [rbp+0B0h+var_130], 8
0x1800175eb  jz      short loc_1800175F6
0x1800175ed  mov     rcx, rsi; lpMem
0x1800175f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800175f5  nop
0x1800175f6  cmp     [rsp+1B0h+var_150], r15d
0x1800175fb  jz      short loc_180017619
0x1800175fd  mov     rcx, [rsp+1B0h+var_158]
0x180017602  test    rcx, rcx
0x180017605  jz      short loc_180017614
0x180017607  mov     rax, [rcx]
0x18001760a  mov     rax, [rax+10h]
0x18001760e  call    cs:__guard_dispatch_icall_fptr
0x180017614  mov     [rsp+1B0h+var_150], r15d
0x180017619  cmp     [rsp+1B0h+var_160], r15d
0x18001761e  jz      short loc_18001763C
0x180017620  mov     rcx, [rsp+1B0h+var_168]
0x180017625  test    rcx, rcx
0x180017628  jz      short loc_180017637
0x18001762a  mov     rax, [rcx]
0x18001762d  mov     rax, [rax+10h]
0x180017631  call    cs:__guard_dispatch_icall_fptr
0x180017637  mov     [rsp+1B0h+var_160], r15d
0x18001763c  cmp     [rsp+1B0h+var_140], r15d
0x180017641  jz      short loc_18001765F
0x180017643  mov     rcx, [rsp+1B0h+var_148]
0x180017648  test    rcx, rcx
0x18001764b  jz      short loc_18001765A
0x18001764d  mov     rax, [rcx]
0x180017650  mov     rax, [rax+10h]
0x180017654  call    cs:__guard_dispatch_icall_fptr
0x18001765a  mov     [rsp+1B0h+var_140], r15d
0x18001765f  cmp     [rsp+1B0h+var_170], r15d
0x180017664  jz      short loc_180017682
0x180017666  mov     rcx, [rsp+1B0h+var_178]
0x18001766b  test    rcx, rcx
0x18001766e  jz      short loc_18001767D
0x180017670  mov     rax, [rcx]
0x180017673  mov     rax, [rax+10h]
0x180017677  call    cs:__guard_dispatch_icall_fptr
0x18001767d  mov     [rsp+1B0h+var_170], r15d
  ... truncated ...
```
