# tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)

- ea: `0x18001625c`
- end: `0x1800165e1`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `901`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180015a4c`

## callees

- `0x180002e50`
- `0x180003940`
- `0x18001625c`
- `0x1800165e8`
- `0x180018844`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800164e1`
- `KERNEL32!GetModuleHandleW` at `0x18001656d`
- `KERNEL32!GetModuleHandleW` at `0x1800164e1`
- `KERNEL32!GetModuleHandleW` at `0x18001656d`
- `KERNEL32!GetProcAddress` at `0x1800164f8`
- `KERNEL32!GetProcAddress` at `0x180016584`
- `KERNEL32!GetProcAddress` at `0x1800164f8`
- `KERNEL32!GetProcAddress` at `0x180016584`
- `ole32!CoTaskMemFree` at `0x1800165b8`
- `ole32!CoTaskMemFree` at `0x1800165b8`

## string_xrefs

- `0x1800164da`: `kernelbase.dll`
- `0x180016566`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64 a1, __int64 a2)
{
  tip2::details *v4; // rcx
  void (__fastcall ***v5)(_QWORD); // rcx
  char v6; // cl
  unsigned __int8 v7; // r8
  unsigned int v8; // edx
  bool v9; // zf
  char v10; // al
  __int64 v11; // r8
  __int64 v12; // rsi
  int v13; // edx
  int *v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned int v19; // eax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  void (__fastcall ***v22)(_QWORD); // rcx
  FARPROC v23; // rax
  HMODULE v24; // rax
  const struct tip2::test_requirement *v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h]
  int v28; // [rsp+40h] [rbp-C0h]
  __int128 v29; // [rsp+44h] [rbp-BCh]
  int v30; // [rsp+54h] [rbp-ACh]
  char v31; // [rsp+58h] [rbp-A8h]
  __int16 v32; // [rsp+5Ah] [rbp-A6h]
  __int64 v33; // [rsp+60h] [rbp-A0h]
  __int64 v34; // [rsp+68h] [rbp-98h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  int v36; // [rsp+80h] [rbp-80h]
  __int64 v37; // [rsp+88h] [rbp-78h]
  __int16 v38; // [rsp+90h] [rbp-70h]
  int v39; // [rsp+9Ch] [rbp-64h]
  int v40; // [rsp+A0h] [rbp-60h]
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  char v42; // [rsp+B8h] [rbp-48h]
  int v43; // [rsp+B9h] [rbp-47h] BYREF
  char v44; // [rsp+BDh] [rbp-43h]
  char v45; // [rsp+BEh] [rbp-42h] BYREF
  char v46; // [rsp+8B9h] [rbp+7B9h] BYREF
  int *v47; // [rsp+8C0h] [rbp+7C0h]
  char *v48; // [rsp+8C8h] [rbp+7C8h]
  char *v49; // [rsp+8D0h] [rbp+7D0h]

  v4 = (tip2::details *)(a1 + 8);
  if ( !*((_BYTE *)v4 + 152)
    && tip2::details::evaluate_flags(
         v4,
         *(const struct tip2::test_state **)(a1 + 40),
         *(const struct tip2::test_requirement **)(a1 + 56),
         *(const struct tip2::test_requirement **)(a1 + 48),
         v25) )
  {
    v5 = *(void (__fastcall ****)(_QWORD))a1;
    if ( tip2::details::g_test_interface_exception_guard )
    {
      if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v5, 0, 0, 0, 0) && !*(_BYTE *)(a1 + 160) )
      {
        *(_BYTE *)(a1 + 160) = 3;
        *(_WORD *)(a1 + 162) = 16395;
        *(_QWORD *)(a1 + 168) = 0;
      }
    }
    else
    {
      (**v5)(v5);
    }
  }
  v6 = *(_BYTE *)(a1 + 160);
  if ( v6 != 5 )
  {
    if ( v6 )
    {
      if ( (unsigned __int8)(v6 - 2) > 1u && ((*(_DWORD *)(a1 + 20) & 0x1000) == 0 || v6 == 4) )
        goto LABEL_16;
    }
    else
    {
      *(_BYTE *)(a1 + 160) = 3;
      *(_WORD *)(a1 + 162) = 16394;
      *(_QWORD *)(a1 + 168) = 0;
    }
    if ( (*(_DWORD *)(a1 + 64) & 0x800) != 0 )
    {
      v7 = 1;
LABEL_17:
      v8 = v7 | 2;
      v9 = (*(_DWORD *)(a1 + 20) & 0x200) == 0;
      if ( (*(_DWORD *)(a1 + 20) & 0x200) == 0 )
        v8 = v7;
      pv = 0;
      v42 = 0;
      v47 = &v43;
      v49 = &v46;
      v43 = -2143256512;
      v44 = 0;
      v48 = &v45;
      v10 = v7;
      if ( !v9 )
        v10 = 1;
      v11 = v8 | 4;
      if ( !v10 )
        v11 = v8;
      v12 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, v11, 1);
      memset_0(&v26, 0, 0x78u);
      v13 = *(_DWORD *)(a1 + 180);
      v14 = (int *)(a1 + 16);
      if ( v13 )
        v26 = *(_DWORD *)(a1 + 180);
      else
        v26 = *v14;
      v27 = *(_QWORD *)(a1 + 24);
      v28 = *(_DWORD *)(a1 + 20);
      v29 = *(_OWORD *)(a1 + 144);
      v30 = *(_DWORD *)(a1 + 64) | 0x200000;
      v31 = *(_BYTE *)(a1 + 160);
      v32 = *(_WORD *)(a1 + 162);
      v33 = *(_QWORD *)(a1 + 168);
      v34 = a2;
      v35 = v12;
      v39 = *(_DWORD *)(a1 + 176);
      if ( v13 )
        v40 = *v14;
      else
        v40 = 0;
      v15 = 0;
      v16 = 0;
      v17 = *(_QWORD *)(a1 + 72);
      v18 = v17 + 168LL * *(_QWORD *)(a1 + 88);
      if ( v17 != v18 )
      {
        do
        {
          v19 = *(_DWORD *)(v17 + 8);
          if ( (_DWORD)v15 != v19 )
            v16 = v17;
          v17 += 168;
          if ( (_DWORD)v15 == v19 )
            v19 = v15;
          v15 = v19;
        }
        while ( v17 != v18 );
        if ( v16 )
        {
          v36 = *(_DWORD *)(v16 + 8);
          v37 = *(_QWORD *)(v16 + 56);
          v38 = *(_WORD *)(v16 + 64);
        }
      }
      ProcAddress = (FARPROC)`TestReport'::`2'::s_pfnTestReport;
      if ( `TestReport'::`2'::s_pfnTestReport )
        goto LABEL_41;
      ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
      if ( !g_tip_details_kernelbaseModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
        g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "TestReport");
      `TestReport'::`2'::s_pfnTestReport = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_41:
        ((void (__fastcall *)(int *, __int64, __int64, __int64))ProcAddress)(&v26, v17, v18, v15);
      v22 = *(void (__fastcall ****)(_QWORD))a1;
      if ( tip2::details::g_test_interface_exception_guard )
      {
        if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v22, 0, 0, 0, &v26) )
        {
          v32 = 16398;
          v31 = 3;
          v23 = (FARPROC)`TestReport'::`2'::s_pfnTestReport;
          if ( `TestReport'::`2'::s_pfnTestReport )
            goto LABEL_48;
          v24 = g_tip_details_kernelbaseModuleHandle;
          if ( !g_tip_details_kernelbaseModuleHandle )
          {
            v24 = GetModuleHandleW(L"kernelbase.dll");
            g_tip_details_kernelbaseModuleHandle = v24;
          }
          v23 = GetProcAddress(v24, "TestReport");
          `TestReport'::`2'::s_pfnTestReport = (__int64)v23;
          if ( v23 )
LABEL_48:
            ((void (__fastcall *)(int *))v23)(&v26);
        }
      }
      else
      {
        ((void (__fastcall *)(void (__fastcall ***)(_QWORD), int *))(*v22)[3])(v22, &v26);
      }
      if ( pv )
        CoTaskMemFree(pv);
      return;
    }
LABEL_16:
    v7 = 0;
    goto LABEL_17;
  }
}

```

## disassembly

```asm
0x18001625c  mov     [rsp-8+arg_10], rbx
0x180016261  push    rbp
0x180016262  push    rsi
0x180016263  push    rdi
0x180016264  lea     rbp, [rsp-7F0h]
0x18001626c  sub     rsp, 8F0h
0x180016273  mov     rax, cs:__security_cookie
0x18001627a  xor     rax, rsp
0x18001627d  mov     [rbp+800h+var_20], rax
0x180016284  mov     rdi, rdx
0x180016287  mov     rbx, rcx
0x18001628a  add     rcx, 8; this
0x18001628e  cmp     byte ptr [rcx+98h], 0
0x180016295  jnz     short loc_180016306
0x180016297  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x18001629b  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x18001629f  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x1800162a3  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x1800162a8  test    al, al
0x1800162aa  jz      short loc_180016306
0x1800162ac  mov     rcx, [rbx]
0x1800162af  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x1800162b6  test    rax, rax
0x1800162b9  jz      short loc_1800162FA
0x1800162bb  mov     [rsp+900h+var_8E0], 0
0x1800162c4  xor     r9d, r9d
0x1800162c7  xor     r8d, r8d
0x1800162ca  xor     edx, edx
0x1800162cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162d1  test    al, al
0x1800162d3  jnz     short loc_180016306
0x1800162d5  cmp     [rbx+0A0h], al
0x1800162db  jnz     short loc_180016306
0x1800162dd  mov     byte ptr [rbx+0A0h], 3
0x1800162e4  mov     word ptr [rbx+0A2h], 400Bh
0x1800162ed  mov     qword ptr [rbx+0A8h], 0
0x1800162f8  jmp     short loc_180016306
0x1800162fa  mov     rax, [rcx]
0x1800162fd  mov     rax, [rax]
0x180016300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016305  nop
0x180016306  mov     cl, [rbx+0A0h]
0x18001630c  cmp     cl, 5
0x18001630f  jz      loc_1800165BF
0x180016315  mov     r9d, 1
0x18001631b  test    cl, cl
0x18001631d  jnz     short loc_18001633C
0x18001631f  mov     byte ptr [rbx+0A0h], 3
0x180016326  mov     word ptr [rbx+0A2h], 400Ah
0x18001632f  mov     qword ptr [rbx+0A8h], 0
0x18001633a  jmp     short loc_180016352
0x18001633c  lea     eax, [rcx-2]
0x18001633f  cmp     al, r9b
0x180016342  jbe     short loc_180016352
0x180016344  test    dword ptr [rbx+14h], 1000h
0x18001634b  jz      short loc_180016360
0x18001634d  cmp     cl, 4
0x180016350  jz      short loc_180016360
0x180016352  test    dword ptr [rbx+40h], 800h
0x180016359  jz      short loc_180016360
0x18001635b  mov     r8b, r9b
0x18001635e  jmp     short loc_180016363
0x180016360  xor     r8b, r8b
0x180016363  movzx   eax, r8b
0x180016367  mov     edx, eax
0x180016369  or      edx, 2
0x18001636c  test    dword ptr [rbx+14h], 200h
0x180016373  cmovz   edx, eax
0x180016376  mov     [rbp+800h+pv], 0
0x18001637e  mov     [rbp+800h+var_848], 0
0x180016382  lea     rax, [rbp+800h+var_847]
0x180016386  mov     [rbp+800h+var_40], rax
0x18001638d  lea     rax, [rbp+800h+var_47]
0x180016394  mov     [rbp+800h+var_30], rax
0x18001639b  mov     [rbp+800h+var_847], 80408040h
0x1800163a2  mov     [rbp+800h+var_843], 0
0x1800163a6  lea     rax, [rbp+800h+var_842]
0x1800163aa  mov     [rbp+800h+var_38], rax
0x1800163b1  movzx   eax, r8b
0x1800163b5  cmovnz  eax, r9d
0x1800163b9  mov     r8d, edx
0x1800163bc  or      r8d, 4
0x1800163c0  test    al, al
0x1800163c2  cmovz   r8d, edx
0x1800163c6  lea     rdx, [rbp+800h+pv]
0x1800163ca  mov     rcx, rbx
0x1800163cd  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800163d2  mov     rsi, rax
0x1800163d5  xor     edx, edx; Val
0x1800163d7  lea     r8d, [rdx+78h]; Size
0x1800163db  lea     rcx, [rsp+900h+var_8D0]; void *
0x1800163e0  call    memset_0
0x1800163e5  mov     edx, [rbx+0B4h]
0x1800163eb  lea     rcx, [rbx+10h]
0x1800163ef  test    edx, edx
0x1800163f1  jz      short loc_1800163F9
0x1800163f3  mov     [rsp+900h+var_8D0], edx
0x1800163f7  jmp     short loc_1800163FF
0x1800163f9  mov     eax, [rcx]
0x1800163fb  mov     [rsp+900h+var_8D0], eax
0x1800163ff  mov     rax, [rbx+18h]
0x180016403  mov     [rsp+900h+var_8C8], rax
0x180016408  mov     eax, [rbx+14h]
0x18001640b  mov     [rsp+900h+var_8C0], eax
0x18001640f  movups  xmm0, xmmword ptr [rbx+90h]
0x180016416  movdqu  [rsp+900h+var_8BC], xmm0
0x18001641c  mov     eax, [rbx+40h]
0x18001641f  bts     eax, 15h
0x180016423  mov     [rsp+900h+var_8AC], eax
0x180016427  mov     al, [rbx+0A0h]
0x18001642d  mov     [rsp+900h+var_8A8], al
0x180016431  movzx   eax, word ptr [rbx+0A2h]
0x180016438  mov     [rsp+900h+var_8A6], ax
0x18001643d  mov     rax, [rbx+0A8h]
0x180016444  mov     [rsp+900h+var_8A0], rax
0x180016449  mov     [rsp+900h+var_898], rdi
0x18001644e  mov     [rsp+900h+var_888], rsi
0x180016453  mov     eax, [rbx+0B0h]
0x180016459  mov     [rbp+800h+var_864], eax
0x18001645c  test    edx, edx
0x18001645e  jz      short loc_180016467
0x180016460  mov     eax, [rcx]
0x180016462  mov     [rbp+800h+var_860], eax
0x180016465  jmp     short loc_18001646E
0x180016467  mov     [rbp+800h+var_860], 0
0x18001646e  xor     r9d, r9d
0x180016471  xor     ecx, ecx
0x180016473  mov     rdx, [rbx+48h]
0x180016477  imul    r8, [rbx+58h], 0A8h
0x18001647f  add     r8, rdx
0x180016482  cmp     rdx, r8
0x180016485  jz      short loc_1800164C2
0x180016487  mov     eax, [rdx+8]
0x18001648a  cmp     r9d, eax
0x18001648d  cmovnz  rcx, rdx
0x180016491  add     rdx, 0A8h
0x180016498  cmp     r9d, eax
0x18001649b  cmovz   eax, r9d
0x18001649f  mov     r9d, eax
0x1800164a2  cmp     rdx, r8
0x1800164a5  jnz     short loc_180016487
0x1800164a7  test    rcx, rcx
0x1800164aa  jz      short loc_1800164C2
0x1800164ac  mov     eax, [rcx+8]
0x1800164af  mov     [rbp+800h+var_880], eax
0x1800164b2  mov     rax, [rcx+38h]
0x1800164b6  mov     [rbp+800h+var_878], rax
0x1800164ba  movzx   eax, word ptr [rcx+40h]
0x1800164be  mov     [rbp+800h+var_870], ax
0x1800164c2  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800164c9  test    rax, rax
0x1800164cc  jnz     short loc_18001650A
0x1800164ce  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800164d5  test    rax, rax
0x1800164d8  jnz     short loc_1800164EE
0x1800164da  lea     rcx, ModuleName; "kernelbase.dll"
0x1800164e1  call    cs:__imp_GetModuleHandleW
0x1800164e7  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800164ee  lea     rdx, aTestreport; "TestReport"
0x1800164f5  mov     rcx, rax; hModule
0x1800164f8  call    cs:__imp_GetProcAddress
0x1800164fe  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180016505  test    rax, rax
0x180016508  jz      short loc_180016515
0x18001650a  lea     rcx, [rsp+900h+var_8D0]
0x18001650f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016514  nop
0x180016515  mov     rcx, [rbx]
0x180016518  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18001651f  lea     rdx, [rsp+900h+var_8D0]
0x180016524  test    rax, rax
0x180016527  jz      short loc_1800165A2
0x180016529  mov     [rsp+900h+var_8E0], rdx
0x18001652e  xor     r9d, r9d
0x180016531  xor     r8d, r8d
0x180016534  xor     edx, edx
0x180016536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001653b  test    al, al
0x18001653d  jnz     short loc_1800165AF
0x18001653f  mov     eax, 400Eh
0x180016544  mov     [rsp+900h+var_8A6], ax
0x180016549  mov     [rsp+900h+var_8A8], 3
0x18001654e  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180016555  test    rax, rax
0x180016558  jnz     short loc_180016596
0x18001655a  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180016561  test    rax, rax
0x180016564  jnz     short loc_18001657A
0x180016566  lea     rcx, ModuleName; "kernelbase.dll"
0x18001656d  call    cs:__imp_GetModuleHandleW
0x180016573  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18001657a  lea     rdx, aTestreport; "TestReport"
0x180016581  mov     rcx, rax; hModule
0x180016584  call    cs:__imp_GetProcAddress
0x18001658a  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180016591  test    rax, rax
0x180016594  jz      short loc_1800165AF
0x180016596  lea     rcx, [rsp+900h+var_8D0]
0x18001659b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165a0  jmp     short loc_1800165AF
0x1800165a2  mov     rax, [rcx]
0x1800165a5  mov     rax, [rax+18h]
0x1800165a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165ae  nop
0x1800165af  mov     rcx, [rbp+800h+pv]; pv
0x1800165b3  test    rcx, rcx
0x1800165b6  jz      short loc_1800165BF
0x1800165b8  call    cs:__imp_CoTaskMemFree
0x1800165be  nop
0x1800165bf  mov     rcx, [rbp+800h+var_20]
0x1800165c6  xor     rcx, rsp; StackCookie
0x1800165c9  call    __security_check_cookie
0x1800165ce  mov     rbx, [rsp+900h+arg_10]
0x1800165d6  add     rsp, 8F0h
0x1800165dd  pop     rdi
0x1800165de  pop     rsi
0x1800165df  pop     rbp
0x1800165e0  retn
```
