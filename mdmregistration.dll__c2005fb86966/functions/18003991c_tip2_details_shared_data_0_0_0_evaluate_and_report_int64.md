# tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)

- ea: `0x18003991c`
- end: `0x180039cc4`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `936`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180039428`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x18003991c`
- `0x180039ccc`
- `0x18003ab98`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039ba1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039c3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039ba1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039c3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039bbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039c5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039bbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039c5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039c94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039c94`

## string_xrefs

- `0x180039b9a`: `kernelbase.dll`
- `0x180039c36`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18003991c  mov     [rsp-8+arg_10], rbx
0x180039921  push    rbp
0x180039922  push    rsi
0x180039923  push    rdi
0x180039924  lea     rbp, [rsp-7F0h]
0x18003992c  sub     rsp, 8F0h
0x180039933  mov     rax, cs:__security_cookie
0x18003993a  xor     rax, rsp
0x18003993d  mov     [rbp+800h+var_20], rax
0x180039944  mov     rdi, rdx
0x180039947  mov     rbx, rcx
0x18003994a  add     rcx, 8; this
0x18003994e  cmp     byte ptr [rcx+98h], 0
0x180039955  jnz     short loc_1800399C6
0x180039957  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x18003995b  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x18003995f  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x180039963  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x180039968  test    al, al
0x18003996a  jz      short loc_1800399C6
0x18003996c  mov     rcx, [rbx]
0x18003996f  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180039976  test    rax, rax
0x180039979  jz      short loc_1800399BA
0x18003997b  mov     [rsp+900h+var_8E0], 0
0x180039984  xor     r9d, r9d
0x180039987  xor     r8d, r8d
0x18003998a  xor     edx, edx
0x18003998c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039991  test    al, al
0x180039993  jnz     short loc_1800399C6
0x180039995  cmp     [rbx+0A0h], al
0x18003999b  jnz     short loc_1800399C6
0x18003999d  mov     byte ptr [rbx+0A0h], 3
0x1800399a4  mov     word ptr [rbx+0A2h], 400Bh
0x1800399ad  mov     qword ptr [rbx+0A8h], 0
0x1800399b8  jmp     short loc_1800399C6
0x1800399ba  mov     rax, [rcx]
0x1800399bd  mov     rax, [rax]
0x1800399c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399c5  nop
0x1800399c6  mov     cl, [rbx+0A0h]
0x1800399cc  cmp     cl, 5
0x1800399cf  jz      loc_180039CA1
0x1800399d5  mov     r9d, 1
0x1800399db  test    cl, cl
0x1800399dd  jnz     short loc_1800399FC
0x1800399df  mov     byte ptr [rbx+0A0h], 3
0x1800399e6  mov     word ptr [rbx+0A2h], 400Ah
0x1800399ef  mov     qword ptr [rbx+0A8h], 0
0x1800399fa  jmp     short loc_180039A12
0x1800399fc  lea     eax, [rcx-2]
0x1800399ff  cmp     al, r9b
0x180039a02  jbe     short loc_180039A12
0x180039a04  test    dword ptr [rbx+14h], 1000h
0x180039a0b  jz      short loc_180039A20
0x180039a0d  cmp     cl, 4
0x180039a10  jz      short loc_180039A20
0x180039a12  test    dword ptr [rbx+40h], 800h
0x180039a19  jz      short loc_180039A20
0x180039a1b  mov     r8b, r9b
0x180039a1e  jmp     short loc_180039A23
0x180039a20  xor     r8b, r8b
0x180039a23  movzx   eax, r8b
0x180039a27  mov     edx, eax
0x180039a29  or      edx, 2
0x180039a2c  test    dword ptr [rbx+14h], 200h
0x180039a33  cmovz   edx, eax
0x180039a36  mov     [rbp+800h+pv], 0
0x180039a3e  mov     [rbp+800h+var_848], 0
0x180039a42  lea     rax, [rbp+800h+var_847]
0x180039a46  mov     [rbp+800h+var_40], rax
0x180039a4d  lea     rax, [rbp+800h+var_47]
0x180039a54  mov     [rbp+800h+var_30], rax
0x180039a5b  mov     [rbp+800h+var_847], 80408040h
0x180039a62  mov     [rbp+800h+var_843], 0
0x180039a66  lea     rax, [rbp+800h+var_842]
0x180039a6a  mov     [rbp+800h+var_38], rax
0x180039a71  movzx   eax, r8b
0x180039a75  cmovnz  eax, r9d
0x180039a79  mov     r8d, edx
0x180039a7c  or      r8d, 4
0x180039a80  test    al, al
0x180039a82  cmovz   r8d, edx
0x180039a86  lea     rdx, [rbp+800h+pv]
0x180039a8a  mov     rcx, rbx
0x180039a8d  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180039a92  mov     rsi, rax
0x180039a95  xor     edx, edx; Val
0x180039a97  lea     r8d, [rdx+78h]; Size
0x180039a9b  lea     rcx, [rsp+900h+var_8D0]; void *
0x180039aa0  call    memset_0
0x180039aa5  mov     edx, [rbx+0B4h]
0x180039aab  lea     rcx, [rbx+10h]
0x180039aaf  test    edx, edx
0x180039ab1  jz      short loc_180039AB9
0x180039ab3  mov     [rsp+900h+var_8D0], edx
0x180039ab7  jmp     short loc_180039ABF
0x180039ab9  mov     eax, [rcx]
0x180039abb  mov     [rsp+900h+var_8D0], eax
0x180039abf  mov     rax, [rbx+18h]
0x180039ac3  mov     [rsp+900h+var_8C8], rax
0x180039ac8  mov     eax, [rbx+14h]
0x180039acb  mov     [rsp+900h+var_8C0], eax
0x180039acf  movups  xmm0, xmmword ptr [rbx+90h]
0x180039ad6  movdqu  [rsp+900h+var_8BC], xmm0
0x180039adc  mov     eax, [rbx+40h]
0x180039adf  bts     eax, 15h
0x180039ae3  mov     [rsp+900h+var_8AC], eax
0x180039ae7  mov     al, [rbx+0A0h]
0x180039aed  mov     [rsp+900h+var_8A8], al
0x180039af1  movzx   eax, word ptr [rbx+0A2h]
0x180039af8  mov     [rsp+900h+var_8A6], ax
0x180039afd  mov     rax, [rbx+0A8h]
0x180039b04  mov     [rsp+900h+var_8A0], rax
0x180039b09  mov     [rsp+900h+var_898], rdi
0x180039b0e  mov     [rsp+900h+var_888], rsi
0x180039b13  mov     eax, [rbx+0B0h]
0x180039b19  mov     [rbp+800h+var_864], eax
0x180039b1c  test    edx, edx
0x180039b1e  jz      short loc_180039B27
0x180039b20  mov     eax, [rcx]
0x180039b22  mov     [rbp+800h+var_860], eax
0x180039b25  jmp     short loc_180039B2E
0x180039b27  mov     [rbp+800h+var_860], 0
0x180039b2e  xor     r9d, r9d
0x180039b31  xor     ecx, ecx
0x180039b33  mov     rdx, [rbx+48h]
0x180039b37  imul    r8, [rbx+58h], 0A8h
0x180039b3f  add     r8, rdx
0x180039b42  cmp     rdx, r8
0x180039b45  jz      short loc_180039B82
0x180039b47  mov     eax, [rdx+8]
0x180039b4a  cmp     r9d, eax
0x180039b4d  cmovnz  rcx, rdx
0x180039b51  add     rdx, 0A8h
0x180039b58  cmp     r9d, eax
0x180039b5b  cmovz   eax, r9d
0x180039b5f  mov     r9d, eax
0x180039b62  cmp     rdx, r8
0x180039b65  jnz     short loc_180039B47
0x180039b67  test    rcx, rcx
0x180039b6a  jz      short loc_180039B82
0x180039b6c  mov     eax, [rcx+8]
0x180039b6f  mov     [rbp+800h+var_880], eax
0x180039b72  mov     rax, [rcx+38h]
0x180039b76  mov     [rbp+800h+var_878], rax
0x180039b7a  movzx   eax, word ptr [rcx+40h]
0x180039b7e  mov     [rbp+800h+var_870], ax
0x180039b82  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180039b89  test    rax, rax
0x180039b8c  jnz     short loc_180039BD6
0x180039b8e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180039b95  test    rax, rax
0x180039b98  jnz     short loc_180039BB4
0x180039b9a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180039ba1  call    cs:__imp_GetModuleHandleW
0x180039ba8  nop     dword ptr [rax+rax+00h]
0x180039bad  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180039bb4  lea     rdx, aTestreport; "TestReport"
0x180039bbb  mov     rcx, rax; hModule
0x180039bbe  call    cs:__imp_GetProcAddress
0x180039bc5  nop     dword ptr [rax+rax+00h]
0x180039bca  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180039bd1  test    rax, rax
0x180039bd4  jz      short loc_180039BE1
0x180039bd6  lea     rcx, [rsp+900h+var_8D0]
0x180039bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039be0  nop
0x180039be1  mov     rcx, [rbx]
0x180039be4  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180039beb  lea     rdx, [rsp+900h+var_8D0]
0x180039bf0  test    rax, rax
0x180039bf3  jz      loc_180039C7E
0x180039bf9  mov     [rsp+900h+var_8E0], rdx
0x180039bfe  xor     r9d, r9d
0x180039c01  xor     r8d, r8d
0x180039c04  xor     edx, edx
0x180039c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c0b  test    al, al
0x180039c0d  jnz     short loc_180039C8B
0x180039c0f  mov     eax, 400Eh
0x180039c14  mov     [rsp+900h+var_8A6], ax
0x180039c19  mov     [rsp+900h+var_8A8], 3
0x180039c1e  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180039c25  test    rax, rax
0x180039c28  jnz     short loc_180039C72
0x180039c2a  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180039c31  test    rax, rax
0x180039c34  jnz     short loc_180039C50
0x180039c36  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180039c3d  call    cs:__imp_GetModuleHandleW
0x180039c44  nop     dword ptr [rax+rax+00h]
0x180039c49  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180039c50  lea     rdx, aTestreport; "TestReport"
0x180039c57  mov     rcx, rax; hModule
0x180039c5a  call    cs:__imp_GetProcAddress
0x180039c61  nop     dword ptr [rax+rax+00h]
0x180039c66  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180039c6d  test    rax, rax
0x180039c70  jz      short loc_180039C8B
0x180039c72  lea     rcx, [rsp+900h+var_8D0]
0x180039c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c7c  jmp     short loc_180039C8B
0x180039c7e  mov     rax, [rcx]
0x180039c81  mov     rax, [rax+18h]
0x180039c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c8a  nop
0x180039c8b  mov     rcx, [rbp+800h+pv]; pv
0x180039c8f  test    rcx, rcx
0x180039c92  jz      short loc_180039CA1
0x180039c94  call    cs:__imp_CoTaskMemFree
0x180039c9b  nop     dword ptr [rax+rax+00h]
0x180039ca0  nop
0x180039ca1  mov     rcx, [rbp+800h+var_20]
0x180039ca8  xor     rcx, rsp; StackCookie
0x180039cab  call    __security_check_cookie
0x180039cb0  mov     rbx, [rsp+900h+arg_10]
0x180039cb8  add     rsp, 8F0h
0x180039cbf  pop     rdi
0x180039cc0  pop     rsi
0x180039cc1  pop     rbp
0x180039cc2  retn
```
