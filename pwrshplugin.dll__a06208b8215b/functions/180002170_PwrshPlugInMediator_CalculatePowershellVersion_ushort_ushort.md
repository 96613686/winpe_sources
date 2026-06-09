# PwrshPlugInMediator::CalculatePowershellVersion(ushort *,ushort *)

- ea: `0x180002170`
- end: `0x18000255a`
- name: `?CalculatePowershellVersion@PwrshPlugInMediator@@QEAAPEAGPEAG0@Z`
- size: `1002`
- prototype: `unsigned __int16 *__fastcall(PwrshPlugInMediator *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003a68`

## callees

- `0x180001098`
- `0x180001318`
- `0x180001dfc`
- `0x180002058`
- `0x180002170`
- `0x180002e80`
- `0x1800042ec`
- `0x180008b88`
- `0x18000b010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800021b9`
- `msvcrt!wcschr` at `0x1800021c7`
- `msvcrt!wcschr` at `0x180002222`
- `msvcrt!wcschr` at `0x180002230`
- `msvcrt!wcschr` at `0x180002279`
- `msvcrt!wcschr` at `0x180002287`
- `msvcrt!wcschr` at `0x1800022e2`
- `msvcrt!wcschr` at `0x1800022f0`
- `msvcrt!wcschr` at `0x1800021b9`
- `msvcrt!wcschr` at `0x1800021c7`
- `msvcrt!wcschr` at `0x180002222`
- `msvcrt!wcschr` at `0x180002230`
- `msvcrt!wcschr` at `0x180002279`
- `msvcrt!wcschr` at `0x180002287`
- `msvcrt!wcschr` at `0x1800022e2`
- `msvcrt!wcschr` at `0x1800022f0`

## pseudocode

```c
unsigned __int16 *__fastcall PwrshPlugInMediator::CalculatePowershellVersion(
        PwrshPlugInMediator *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  unsigned __int16 *v6; // r15
  wchar_t *v7; // rbx
  wchar_t *v8; // rax
  NativeMsh::PwrshCommon *v9; // rcx
  const wchar_t *v10; // rbx
  wchar_t *v11; // r14
  wchar_t *v12; // rax
  NativeMsh::PwrshCommon *v13; // rcx
  const unsigned __int16 *v14; // r8
  wchar_t *v15; // rbx
  wchar_t *v16; // rax
  NativeMsh::PwrshCommon *v17; // rcx
  const wchar_t *v18; // rbx
  wchar_t *v19; // r14
  wchar_t *v20; // rax
  NativeMsh::PwrshCommon *v21; // rcx
  const unsigned __int16 *v22; // r8
  PlugInException *v23; // rax
  PlugInException *v24; // rax
  unsigned __int16 *v25; // rax
  __int64 v26; // rcx
  unsigned __int64 v27; // rsi
  PlugInException *v28; // rax
  PlugInException *v29; // rax
  unsigned __int16 *v30; // r9
  PlugInException *v32; // rax
  PlugInException *v33; // rax
  PlugInException *v34; // rax
  PlugInException *v35; // rax
  unsigned __int16 *v36; // [rsp+70h] [rbp+40h] BYREF
  PlugInException *pExceptionObject; // [rsp+78h] [rbp+48h] BYREF
  int v38; // [rsp+88h] [rbp+58h] BYREF

  LODWORD(pExceptionObject) = -1;
  LODWORD(v36) = -1;
  v6 = 0;
  if ( !a2 )
    goto LABEL_45;
  if ( !*a2 )
    goto LABEL_45;
  v7 = wcschr(a2, 0x2Eu);
  v8 = wcschr(a2, 0);
  if ( !v8 )
    goto LABEL_45;
  if ( !v7 )
  {
    if ( NativeMsh::PwrshCommon::ParseInt(v9, a2, v8, (int *)&pExceptionObject) )
    {
      v10 = 0;
      goto LABEL_9;
    }
LABEL_45:
    v30 = a2;
    goto LABEL_46;
  }
  if ( !NativeMsh::PwrshCommon::ParseInt(v9, a2, v7, (int *)&pExceptionObject) )
    goto LABEL_45;
  v10 = v7 + 1;
LABEL_9:
  if ( v10 )
  {
    if ( !*v10 )
      goto LABEL_45;
    v11 = wcschr(v10, 0x2Eu);
    v12 = wcschr(v10, 0);
    if ( !v12 )
      goto LABEL_45;
    v14 = v11;
    if ( !v11 )
      v14 = v12;
    if ( !NativeMsh::PwrshCommon::ParseInt(v13, v10, v14, &v38) )
      goto LABEL_45;
  }
  if ( !a3 )
    return L"3.0";
  if ( !*a3 )
    goto LABEL_43;
  v15 = wcschr(a3, 0x2Eu);
  v16 = wcschr(a3, 0);
  if ( !v16 )
    goto LABEL_43;
  if ( !v15 )
  {
    if ( NativeMsh::PwrshCommon::ParseInt(v17, a3, v16, (int *)&v36) )
    {
      v18 = 0;
      goto LABEL_23;
    }
LABEL_43:
    v30 = a3;
LABEL_46:
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int16 *))(**((_QWORD **)this + 21) + 8LL))(
      *((_QWORD *)this + 21),
      0,
      17,
      v30);
    return v6;
  }
  if ( !NativeMsh::PwrshCommon::ParseInt(v17, a3, v15, (int *)&v36) )
    goto LABEL_43;
  v18 = v15 + 1;
LABEL_23:
  if ( v18 )
  {
    if ( !*v18 )
      goto LABEL_43;
    v19 = wcschr(v18, 0x2Eu);
    v20 = wcschr(v18, 0);
    if ( !v20 )
      goto LABEL_43;
    v22 = v19;
    if ( !v19 )
      v22 = v20;
    if ( !NativeMsh::PwrshCommon::ParseInt(v21, v18, v22, &v38) )
      goto LABEL_43;
  }
  if ( (int)v36 > (int)pExceptionObject )
  {
    v36 = 0;
    GetFormattedErrorMessage(&v36, 0x805403EE, L"InitializationParameters");
    v32 = (PlugInException *)operator new(0x10u);
    pExceptionObject = v32;
    if ( v32 )
      v33 = PlugInException::PlugInException(v32, -2141977618, v36);
    else
      v33 = 0;
    pExceptionObject = v33;
    throw (PlugInException **)&pExceptionObject;
  }
  if ( (_DWORD)pExceptionObject == 3 )
  {
    if ( (_DWORD)v36 == 2 )
    {
      v36 = 0;
      GetFormattedErrorMessage(&v36, 0x805403EE, L"InitializationParameters");
      v23 = (PlugInException *)operator new(0x10u);
      pExceptionObject = v23;
      if ( v23 )
        v24 = PlugInException::PlugInException(v23, -2141977618, v36);
      else
        v24 = 0;
      pExceptionObject = v24;
      throw (PlugInException **)&pExceptionObject;
    }
  }
  else if ( (_DWORD)pExceptionObject == 2 && (_DWORD)v36 == 2 )
  {
    v25 = a2;
    v26 = 0x7FFFFFFF;
    do
    {
      if ( !*v25 )
        break;
      ++v25;
      --v26;
    }
    while ( v26 );
    v27 = (0x7FFFFFFF - v26) & -(__int64)(v26 != 0);
    if ( !v26 )
    {
      v36 = 0;
      GetFormattedErrorMessage(&v36, 0x805403EE, L"InitializationParameters");
      v34 = (PlugInException *)operator new(0x10u);
      pExceptionObject = v34;
      if ( v34 )
        v35 = PlugInException::PlugInException(v34, -2141977618, v36);
      else
        v35 = 0;
      pExceptionObject = v35;
      throw (PlugInException **)&pExceptionObject;
    }
    v6 = (unsigned __int16 *)operator new[](saturated_mul(v27 + 1, 2u));
    if ( (int)StringCchCopyNW(v6, v27 + 1, a2, v27) < 0 )
    {
      v36 = 0;
      GetFormattedErrorMessage(&v36, 0x805403EE, L"InitializationParameters");
      v28 = (PlugInException *)operator new(0x10u);
      pExceptionObject = v28;
      if ( v28 )
        v29 = PlugInException::PlugInException(v28, -2141977618, v36);
      else
        v29 = 0;
      pExceptionObject = v29;
      throw (PlugInException **)&pExceptionObject;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180002170  mov     [rsp-38h+arg_10], rbx
0x180002175  push    rbp
0x180002176  push    rsi
0x180002177  push    rdi
0x180002178  push    r12
0x18000217a  push    r13
0x18000217c  push    r14
0x18000217e  push    r15
0x180002180  mov     rbp, rsp
0x180002183  sub     rsp, 30h
0x180002187  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000218b  xor     r12d, r12d
0x18000218e  mov     dword ptr [rbp+pExceptionObject], eax
0x180002191  mov     rsi, r8
0x180002194  mov     dword ptr [rbp+arg_0], eax
0x180002197  mov     rdi, rdx
0x18000219a  mov     r13, rcx
0x18000219d  mov     r15d, r12d
0x1800021a0  test    rdx, rdx
0x1800021a3  jz      loc_180002445
0x1800021a9  cmp     r12w, [rdx]
0x1800021ad  jz      loc_180002445
0x1800021b3  lea     edx, [rax+2Fh]; Ch
0x1800021b6  mov     rcx, rdi; Str
0x1800021b9  call    cs:__imp_wcschr
0x1800021bf  xor     edx, edx; Ch
0x1800021c1  mov     rcx, rdi; Str
0x1800021c4  mov     rbx, rax
0x1800021c7  call    cs:__imp_wcschr
0x1800021cd  test    rax, rax
0x1800021d0  jz      loc_180002445
0x1800021d6  lea     r9, [rbp+pExceptionObject]; int *
0x1800021da  mov     rdx, rdi; unsigned __int16 *
0x1800021dd  test    rbx, rbx
0x1800021e0  jz      short loc_1800021F8
0x1800021e2  mov     r8, rbx; unsigned __int16 *
0x1800021e5  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x1800021ea  test    al, al
0x1800021ec  jz      loc_180002445
0x1800021f2  add     rbx, 2
0x1800021f6  jmp     short loc_18000220B
0x1800021f8  mov     r8, rax; unsigned __int16 *
0x1800021fb  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x180002200  test    al, al
0x180002202  jz      loc_180002445
0x180002208  mov     rbx, r12
0x18000220b  test    rbx, rbx
0x18000220e  jz      short loc_18000225E
0x180002210  cmp     r12w, [rbx]
0x180002214  jz      loc_180002445
0x18000221a  mov     edx, 2Eh ; '.'; Ch
0x18000221f  mov     rcx, rbx; Str
0x180002222  call    cs:__imp_wcschr
0x180002228  xor     edx, edx; Ch
0x18000222a  mov     rcx, rbx; Str
0x18000222d  mov     r14, rax
0x180002230  call    cs:__imp_wcschr
0x180002236  test    rax, rax
0x180002239  jz      loc_180002445
0x18000223f  lea     r9, [rbp+arg_18]; int *
0x180002243  mov     rdx, rbx; unsigned __int16 *
0x180002246  mov     r8, r14
0x180002249  test    r14, r14
0x18000224c  jnz     short loc_180002251
0x18000224e  mov     r8, rax; unsigned __int16 *
0x180002251  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x180002256  test    al, al
0x180002258  jz      loc_180002445
0x18000225e  test    rsi, rsi
0x180002261  jz      loc_18000243C
0x180002267  cmp     r12w, [rsi]
0x18000226b  jz      loc_180002437
0x180002271  mov     edx, 2Eh ; '.'; Ch
0x180002276  mov     rcx, rsi; Str
0x180002279  call    cs:__imp_wcschr
0x18000227f  xor     edx, edx; Ch
0x180002281  mov     rcx, rsi; Str
0x180002284  mov     rbx, rax
0x180002287  call    cs:__imp_wcschr
0x18000228d  test    rax, rax
0x180002290  jz      loc_180002437
0x180002296  lea     r9, [rbp+arg_0]; int *
0x18000229a  mov     rdx, rsi; unsigned __int16 *
0x18000229d  test    rbx, rbx
0x1800022a0  jz      short loc_1800022B8
0x1800022a2  mov     r8, rbx; unsigned __int16 *
0x1800022a5  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x1800022aa  test    al, al
0x1800022ac  jz      loc_180002437
0x1800022b2  add     rbx, 2
0x1800022b6  jmp     short loc_1800022CB
0x1800022b8  mov     r8, rax; unsigned __int16 *
0x1800022bb  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x1800022c0  test    al, al
0x1800022c2  jz      loc_180002437
0x1800022c8  mov     rbx, r12
0x1800022cb  test    rbx, rbx
0x1800022ce  jz      short loc_18000231E
0x1800022d0  cmp     r12w, [rbx]
0x1800022d4  jz      loc_180002437
0x1800022da  mov     edx, 2Eh ; '.'; Ch
0x1800022df  mov     rcx, rbx; Str
0x1800022e2  call    cs:__imp_wcschr
0x1800022e8  xor     edx, edx; Ch
0x1800022ea  mov     rcx, rbx; Str
0x1800022ed  mov     r14, rax
0x1800022f0  call    cs:__imp_wcschr
0x1800022f6  test    rax, rax
0x1800022f9  jz      loc_180002437
0x1800022ff  lea     r9, [rbp+arg_18]; int *
0x180002303  mov     rdx, rbx; unsigned __int16 *
0x180002306  mov     r8, r14
0x180002309  test    r14, r14
0x18000230c  jnz     short loc_180002311
0x18000230e  mov     r8, rax; unsigned __int16 *
0x180002311  call    ?ParseInt@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAH@Z; NativeMsh::PwrshCommon::ParseInt(ushort const *,ushort const *,int *)
0x180002316  test    al, al
0x180002318  jz      loc_180002437
0x18000231e  mov     eax, dword ptr [rbp+arg_0]
0x180002321  mov     ecx, dword ptr [rbp+pExceptionObject]
0x180002324  cmp     eax, ecx
0x180002326  jg      loc_180002496
0x18000232c  cmp     ecx, 3
0x18000232f  jnz     short loc_18000237F
0x180002331  cmp     eax, 2
0x180002334  jnz     loc_180002463
0x18000233a  mov     ebx, 805403EEh
0x18000233f  mov     [rbp+arg_0], r12
0x180002343  mov     edx, ebx; unsigned int
0x180002345  lea     r8, aInitialization; "InitializationParameters"
0x18000234c  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x180002350  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x180002355  mov     ecx, 10h; Size
0x18000235a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000235f  mov     [rbp+pExceptionObject], rax
0x180002363  test    rax, rax
0x180002366  jz      loc_1800024EC
0x18000236c  mov     r8, [rbp+arg_0]; unsigned __int16 *
0x180002370  mov     edx, ebx; unsigned int
0x180002372  mov     rcx, rax; this
0x180002375  call    ??0PlugInException@@QEAA@KPEAG@Z; PlugInException::PlugInException(ulong,ushort *)
0x18000237a  jmp     loc_1800024EF
0x18000237f  cmp     ecx, 2
0x180002382  jnz     loc_180002463
0x180002388  cmp     eax, ecx
0x18000238a  jnz     loc_180002463
0x180002390  mov     edx, 7FFFFFFFh
0x180002395  mov     rax, rdi
0x180002398  mov     ecx, edx
0x18000239a  cmp     [rax], r12w
0x18000239e  jz      short loc_1800023AA
0x1800023a0  add     rax, 2
0x1800023a4  sub     rcx, 1
0x1800023a8  jnz     short loc_18000239A
0x1800023aa  sub     rdx, rcx
0x1800023ad  mov     rax, rcx
0x1800023b0  neg     rax
0x1800023b3  sbb     rsi, rsi
0x1800023b6  and     rsi, rdx
0x1800023b9  test    rcx, rcx
0x1800023bc  jz      loc_180002504
0x1800023c2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800023c9  lea     rbx, [rsi+1]
0x1800023cd  mov     eax, 2
0x1800023d2  mul     rbx
0x1800023d5  cmovb   rax, rcx
0x1800023d9  mov     rcx, rax; unsigned __int64
0x1800023dc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800023e1  mov     r9, rsi; unsigned __int64
0x1800023e4  mov     r8, rdi; unsigned __int16 *
0x1800023e7  mov     rdx, rbx; unsigned __int64
0x1800023ea  mov     rcx, rax; unsigned __int16 *
0x1800023ed  mov     r15, rax
0x1800023f0  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800023f5  test    eax, eax
0x1800023f7  jns     short loc_180002463
0x1800023f9  mov     ebx, 805403EEh
0x1800023fe  mov     [rbp+arg_0], r12
0x180002402  mov     edx, ebx; unsigned int
0x180002404  lea     r8, aInitialization; "InitializationParameters"
0x18000240b  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x18000240f  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x180002414  mov     ecx, 10h; Size
0x180002419  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000241e  mov     [rbp+pExceptionObject], rax
0x180002422  test    rax, rax
0x180002425  jz      short loc_18000247E
0x180002427  mov     r8, [rbp+arg_0]; unsigned __int16 *
0x18000242b  mov     edx, ebx; unsigned int
0x18000242d  mov     rcx, rax; this
0x180002430  call    ??0PlugInException@@QEAA@KPEAG@Z; PlugInException::PlugInException(ulong,ushort *)
0x180002435  jmp     short loc_180002481
0x180002437  mov     r9, rsi
0x18000243a  jmp     short loc_180002448
0x18000243c  lea     r15, a30; "3.0"
0x180002443  jmp     short loc_180002463
0x180002445  mov     r9, rdi
0x180002448  mov     rcx, [r13+0A8h]
0x18000244f  mov     r8d, 11h
0x180002455  xor     edx, edx
0x180002457  mov     rax, [rcx]
0x18000245a  mov     rax, [rax+8]
0x18000245e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002463  mov     rbx, [rsp+30h+arg_10]
0x18000246b  mov     rax, r15
0x18000246e  add     rsp, 30h
0x180002472  pop     r15
0x180002474  pop     r14
0x180002476  pop     r13
0x180002478  pop     r12
0x18000247a  pop     rdi
0x18000247b  pop     rsi
0x18000247c  pop     rbp
0x18000247d  retn
0x18000247e  mov     rax, r12
0x180002481  lea     rdx, _TI2PEAVPlugInException@@; pThrowInfo
0x180002488  mov     [rbp+pExceptionObject], rax
0x18000248c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180002490  call    _CxxThrowException_0
0x180002496  mov     ebx, 805403EEh
0x18000249b  mov     [rbp+arg_0], r12
0x18000249f  mov     edx, ebx; unsigned int
0x1800024a1  lea     r8, aInitialization; "InitializationParameters"
0x1800024a8  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x1800024ac  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x1800024b1  mov     ecx, 10h; Size
0x1800024b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800024bb  mov     [rbp+pExceptionObject], rax
0x1800024bf  test    rax, rax
0x1800024c2  jz      short loc_1800024D4
0x1800024c4  mov     r8, [rbp+arg_0]; unsigned __int16 *
0x1800024c8  mov     edx, ebx; unsigned int
0x1800024ca  mov     rcx, rax; this
0x1800024cd  call    ??0PlugInException@@QEAA@KPEAG@Z; PlugInException::PlugInException(ulong,ushort *)
0x1800024d2  jmp     short loc_1800024D7
0x1800024d4  mov     rax, r12
0x1800024d7  lea     rdx, _TI2PEAVPlugInException@@; pThrowInfo
0x1800024de  mov     [rbp+pExceptionObject], rax
0x1800024e2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800024e6  call    _CxxThrowException_0
0x1800024ec  mov     rax, r12
0x1800024ef  lea     rdx, _TI2PEAVPlugInException@@; pThrowInfo
0x1800024f6  mov     [rbp+pExceptionObject], rax
0x1800024fa  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800024fe  call    _CxxThrowException_0
0x180002504  mov     ebx, 805403EEh
0x180002509  mov     [rbp+arg_0], r12
0x18000250d  mov     edx, ebx; unsigned int
0x18000250f  lea     r8, aInitialization; "InitializationParameters"
0x180002516  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x18000251a  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x18000251f  mov     ecx, 10h; Size
0x180002524  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002529  mov     [rbp+pExceptionObject], rax
0x18000252d  test    rax, rax
0x180002530  jz      short loc_180002542
0x180002532  mov     r8, [rbp+arg_0]; unsigned __int16 *
0x180002536  mov     edx, ebx; unsigned int
0x180002538  mov     rcx, rax; this
0x18000253b  call    ??0PlugInException@@QEAA@KPEAG@Z; PlugInException::PlugInException(ulong,ushort *)
0x180002540  jmp     short loc_180002545
0x180002542  mov     rax, r12
0x180002545  lea     rdx, _TI2PEAVPlugInException@@; pThrowInfo
0x18000254c  mov     [rbp+pExceptionObject], rax
0x180002550  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180002554  call    _CxxThrowException_0
```
