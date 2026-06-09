# tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)

- ea: `0x18000c990`
- end: `0x18000cd15`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `901`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c568`

## callees

- `0x180001cf0`
- `0x1800026c8`
- `0x18000c990`
- `0x18000cd1c`
- `0x18000dce4`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cc2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ccb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cc2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ccb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cc15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cca1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cc15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cca1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccec`

## string_xrefs

- `0x18000cc0e`: `kernelbase.dll`
- `0x18000cc9a`: `kernelbase.dll`

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
      v12 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, v11);
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
0x18000c990  mov     [rsp-8+arg_10], rbx
0x18000c995  push    rbp
0x18000c996  push    rsi
0x18000c997  push    rdi
0x18000c998  lea     rbp, [rsp-7F0h]
0x18000c9a0  sub     rsp, 8F0h
0x18000c9a7  mov     rax, cs:__security_cookie
0x18000c9ae  xor     rax, rsp
0x18000c9b1  mov     [rbp+800h+var_20], rax
0x18000c9b8  mov     rdi, rdx
0x18000c9bb  mov     rbx, rcx
0x18000c9be  add     rcx, 8; this
0x18000c9c2  cmp     byte ptr [rcx+98h], 0
0x18000c9c9  jnz     short loc_18000CA3A
0x18000c9cb  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x18000c9cf  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x18000c9d3  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x18000c9d7  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x18000c9dc  test    al, al
0x18000c9de  jz      short loc_18000CA3A
0x18000c9e0  mov     rcx, [rbx]
0x18000c9e3  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18000c9ea  test    rax, rax
0x18000c9ed  jz      short loc_18000CA2E
0x18000c9ef  mov     [rsp+900h+var_8E0], 0
0x18000c9f8  xor     r9d, r9d
0x18000c9fb  xor     r8d, r8d
0x18000c9fe  xor     edx, edx
0x18000ca00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca05  test    al, al
0x18000ca07  jnz     short loc_18000CA3A
0x18000ca09  cmp     [rbx+0A0h], al
0x18000ca0f  jnz     short loc_18000CA3A
0x18000ca11  mov     byte ptr [rbx+0A0h], 3
0x18000ca18  mov     word ptr [rbx+0A2h], 400Bh
0x18000ca21  mov     qword ptr [rbx+0A8h], 0
0x18000ca2c  jmp     short loc_18000CA3A
0x18000ca2e  mov     rax, [rcx]
0x18000ca31  mov     rax, [rax]
0x18000ca34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca39  nop
0x18000ca3a  mov     cl, [rbx+0A0h]
0x18000ca40  cmp     cl, 5
0x18000ca43  jz      loc_18000CCF3
0x18000ca49  mov     r9d, 1
0x18000ca4f  test    cl, cl
0x18000ca51  jnz     short loc_18000CA70
0x18000ca53  mov     byte ptr [rbx+0A0h], 3
0x18000ca5a  mov     word ptr [rbx+0A2h], 400Ah
0x18000ca63  mov     qword ptr [rbx+0A8h], 0
0x18000ca6e  jmp     short loc_18000CA86
0x18000ca70  lea     eax, [rcx-2]
0x18000ca73  cmp     al, r9b
0x18000ca76  jbe     short loc_18000CA86
0x18000ca78  test    dword ptr [rbx+14h], 1000h
0x18000ca7f  jz      short loc_18000CA94
0x18000ca81  cmp     cl, 4
0x18000ca84  jz      short loc_18000CA94
0x18000ca86  test    dword ptr [rbx+40h], 800h
0x18000ca8d  jz      short loc_18000CA94
0x18000ca8f  mov     r8b, r9b
0x18000ca92  jmp     short loc_18000CA97
0x18000ca94  xor     r8b, r8b
0x18000ca97  movzx   eax, r8b
0x18000ca9b  mov     edx, eax
0x18000ca9d  or      edx, 2
0x18000caa0  test    dword ptr [rbx+14h], 200h
0x18000caa7  cmovz   edx, eax
0x18000caaa  mov     [rbp+800h+pv], 0
0x18000cab2  mov     [rbp+800h+var_848], 0
0x18000cab6  lea     rax, [rbp+800h+var_847]
0x18000caba  mov     [rbp+800h+var_40], rax
0x18000cac1  lea     rax, [rbp+800h+var_47]
0x18000cac8  mov     [rbp+800h+var_30], rax
0x18000cacf  mov     [rbp+800h+var_847], 80408040h
0x18000cad6  mov     [rbp+800h+var_843], 0
0x18000cada  lea     rax, [rbp+800h+var_842]
0x18000cade  mov     [rbp+800h+var_38], rax
0x18000cae5  movzx   eax, r8b
0x18000cae9  cmovnz  eax, r9d
0x18000caed  mov     r8d, edx
0x18000caf0  or      r8d, 4
0x18000caf4  test    al, al
0x18000caf6  cmovz   r8d, edx
0x18000cafa  lea     rdx, [rbp+800h+pv]
0x18000cafe  mov     rcx, rbx
0x18000cb01  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18000cb06  mov     rsi, rax
0x18000cb09  xor     edx, edx; Val
0x18000cb0b  lea     r8d, [rdx+78h]; Size
0x18000cb0f  lea     rcx, [rsp+900h+var_8D0]; void *
0x18000cb14  call    memset_0
0x18000cb19  mov     edx, [rbx+0B4h]
0x18000cb1f  lea     rcx, [rbx+10h]
0x18000cb23  test    edx, edx
0x18000cb25  jz      short loc_18000CB2D
0x18000cb27  mov     [rsp+900h+var_8D0], edx
0x18000cb2b  jmp     short loc_18000CB33
0x18000cb2d  mov     eax, [rcx]
0x18000cb2f  mov     [rsp+900h+var_8D0], eax
0x18000cb33  mov     rax, [rbx+18h]
0x18000cb37  mov     [rsp+900h+var_8C8], rax
0x18000cb3c  mov     eax, [rbx+14h]
0x18000cb3f  mov     [rsp+900h+var_8C0], eax
0x18000cb43  movups  xmm0, xmmword ptr [rbx+90h]
0x18000cb4a  movdqu  [rsp+900h+var_8BC], xmm0
0x18000cb50  mov     eax, [rbx+40h]
0x18000cb53  bts     eax, 15h
0x18000cb57  mov     [rsp+900h+var_8AC], eax
0x18000cb5b  mov     al, [rbx+0A0h]
0x18000cb61  mov     [rsp+900h+var_8A8], al
0x18000cb65  movzx   eax, word ptr [rbx+0A2h]
0x18000cb6c  mov     [rsp+900h+var_8A6], ax
0x18000cb71  mov     rax, [rbx+0A8h]
0x18000cb78  mov     [rsp+900h+var_8A0], rax
0x18000cb7d  mov     [rsp+900h+var_898], rdi
0x18000cb82  mov     [rsp+900h+var_888], rsi
0x18000cb87  mov     eax, [rbx+0B0h]
0x18000cb8d  mov     [rbp+800h+var_864], eax
0x18000cb90  test    edx, edx
0x18000cb92  jz      short loc_18000CB9B
0x18000cb94  mov     eax, [rcx]
0x18000cb96  mov     [rbp+800h+var_860], eax
0x18000cb99  jmp     short loc_18000CBA2
0x18000cb9b  mov     [rbp+800h+var_860], 0
0x18000cba2  xor     r9d, r9d
0x18000cba5  xor     ecx, ecx
0x18000cba7  mov     rdx, [rbx+48h]
0x18000cbab  imul    r8, [rbx+58h], 0A8h
0x18000cbb3  add     r8, rdx
0x18000cbb6  cmp     rdx, r8
0x18000cbb9  jz      short loc_18000CBF6
0x18000cbbb  mov     eax, [rdx+8]
0x18000cbbe  cmp     r9d, eax
0x18000cbc1  cmovnz  rcx, rdx
0x18000cbc5  add     rdx, 0A8h
0x18000cbcc  cmp     r9d, eax
0x18000cbcf  cmovz   eax, r9d
0x18000cbd3  mov     r9d, eax
0x18000cbd6  cmp     rdx, r8
0x18000cbd9  jnz     short loc_18000CBBB
0x18000cbdb  test    rcx, rcx
0x18000cbde  jz      short loc_18000CBF6
0x18000cbe0  mov     eax, [rcx+8]
0x18000cbe3  mov     [rbp+800h+var_880], eax
0x18000cbe6  mov     rax, [rcx+38h]
0x18000cbea  mov     [rbp+800h+var_878], rax
0x18000cbee  movzx   eax, word ptr [rcx+40h]
0x18000cbf2  mov     [rbp+800h+var_870], ax
0x18000cbf6  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18000cbfd  test    rax, rax
0x18000cc00  jnz     short loc_18000CC3E
0x18000cc02  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000cc09  test    rax, rax
0x18000cc0c  jnz     short loc_18000CC22
0x18000cc0e  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000cc15  call    cs:__imp_GetModuleHandleW
0x18000cc1b  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000cc22  lea     rdx, aTestreport; "TestReport"
0x18000cc29  mov     rcx, rax; hModule
0x18000cc2c  call    cs:__imp_GetProcAddress
0x18000cc32  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18000cc39  test    rax, rax
0x18000cc3c  jz      short loc_18000CC49
0x18000cc3e  lea     rcx, [rsp+900h+var_8D0]
0x18000cc43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc48  nop
0x18000cc49  mov     rcx, [rbx]
0x18000cc4c  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18000cc53  lea     rdx, [rsp+900h+var_8D0]
0x18000cc58  test    rax, rax
0x18000cc5b  jz      short loc_18000CCD6
0x18000cc5d  mov     [rsp+900h+var_8E0], rdx
0x18000cc62  xor     r9d, r9d
0x18000cc65  xor     r8d, r8d
0x18000cc68  xor     edx, edx
0x18000cc6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc6f  test    al, al
0x18000cc71  jnz     short loc_18000CCE3
0x18000cc73  mov     eax, 400Eh
0x18000cc78  mov     [rsp+900h+var_8A6], ax
0x18000cc7d  mov     [rsp+900h+var_8A8], 3
0x18000cc82  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18000cc89  test    rax, rax
0x18000cc8c  jnz     short loc_18000CCCA
0x18000cc8e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000cc95  test    rax, rax
0x18000cc98  jnz     short loc_18000CCAE
0x18000cc9a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000cca1  call    cs:__imp_GetModuleHandleW
0x18000cca7  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000ccae  lea     rdx, aTestreport; "TestReport"
0x18000ccb5  mov     rcx, rax; hModule
0x18000ccb8  call    cs:__imp_GetProcAddress
0x18000ccbe  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18000ccc5  test    rax, rax
0x18000ccc8  jz      short loc_18000CCE3
0x18000ccca  lea     rcx, [rsp+900h+var_8D0]
0x18000cccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccd4  jmp     short loc_18000CCE3
0x18000ccd6  mov     rax, [rcx]
0x18000ccd9  mov     rax, [rax+18h]
0x18000ccdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cce2  nop
0x18000cce3  mov     rcx, [rbp+800h+pv]; pv
0x18000cce7  test    rcx, rcx
0x18000ccea  jz      short loc_18000CCF3
0x18000ccec  call    cs:__imp_CoTaskMemFree
0x18000ccf2  nop
0x18000ccf3  mov     rcx, [rbp+800h+var_20]
0x18000ccfa  xor     rcx, rsp; StackCookie
0x18000ccfd  call    __security_check_cookie
0x18000cd02  mov     rbx, [rsp+900h+arg_10]
0x18000cd0a  add     rsp, 8F0h
0x18000cd11  pop     rdi
0x18000cd12  pop     rsi
0x18000cd13  pop     rbp
0x18000cd14  retn
```
