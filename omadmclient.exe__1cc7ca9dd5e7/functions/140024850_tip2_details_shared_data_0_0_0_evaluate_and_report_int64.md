# tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)

- ea: `0x140024850`
- end: `0x140024bf8`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `936`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14002409c`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x140024850`
- `0x140024c00`
- `0x140025a50`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140024af2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140024b8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140024af2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140024b8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140024ad5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140024b71`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140024ad5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140024b71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024bc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024bc8`

## string_xrefs

- `0x140024ace`: `kernelbase.dll`
- `0x140024b6a`: `kernelbase.dll`

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
0x140024850  mov     [rsp-8+arg_10], rbx
0x140024855  push    rbp
0x140024856  push    rsi
0x140024857  push    rdi
0x140024858  lea     rbp, [rsp-7F0h]
0x140024860  sub     rsp, 8F0h
0x140024867  mov     rax, cs:__security_cookie
0x14002486e  xor     rax, rsp
0x140024871  mov     [rbp+800h+var_20], rax
0x140024878  mov     rdi, rdx
0x14002487b  mov     rbx, rcx
0x14002487e  add     rcx, 8; this
0x140024882  cmp     byte ptr [rcx+98h], 0
0x140024889  jnz     short loc_1400248FA
0x14002488b  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x14002488f  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x140024893  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x140024897  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x14002489c  test    al, al
0x14002489e  jz      short loc_1400248FA
0x1400248a0  mov     rcx, [rbx]
0x1400248a3  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x1400248aa  test    rax, rax
0x1400248ad  jz      short loc_1400248EE
0x1400248af  mov     [rsp+900h+var_8E0], 0
0x1400248b8  xor     r9d, r9d
0x1400248bb  xor     r8d, r8d
0x1400248be  xor     edx, edx
0x1400248c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400248c5  test    al, al
0x1400248c7  jnz     short loc_1400248FA
0x1400248c9  cmp     [rbx+0A0h], al
0x1400248cf  jnz     short loc_1400248FA
0x1400248d1  mov     byte ptr [rbx+0A0h], 3
0x1400248d8  mov     word ptr [rbx+0A2h], 400Bh
0x1400248e1  mov     qword ptr [rbx+0A8h], 0
0x1400248ec  jmp     short loc_1400248FA
0x1400248ee  mov     rax, [rcx]
0x1400248f1  mov     rax, [rax]
0x1400248f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400248f9  nop
0x1400248fa  mov     cl, [rbx+0A0h]
0x140024900  cmp     cl, 5
0x140024903  jz      loc_140024BD5
0x140024909  mov     r9d, 1
0x14002490f  test    cl, cl
0x140024911  jnz     short loc_140024930
0x140024913  mov     byte ptr [rbx+0A0h], 3
0x14002491a  mov     word ptr [rbx+0A2h], 400Ah
0x140024923  mov     qword ptr [rbx+0A8h], 0
0x14002492e  jmp     short loc_140024946
0x140024930  lea     eax, [rcx-2]
0x140024933  cmp     al, r9b
0x140024936  jbe     short loc_140024946
0x140024938  test    dword ptr [rbx+14h], 1000h
0x14002493f  jz      short loc_140024954
0x140024941  cmp     cl, 4
0x140024944  jz      short loc_140024954
0x140024946  test    dword ptr [rbx+40h], 800h
0x14002494d  jz      short loc_140024954
0x14002494f  mov     r8b, r9b
0x140024952  jmp     short loc_140024957
0x140024954  xor     r8b, r8b
0x140024957  movzx   eax, r8b
0x14002495b  mov     edx, eax
0x14002495d  or      edx, 2
0x140024960  test    dword ptr [rbx+14h], 200h
0x140024967  cmovz   edx, eax
0x14002496a  mov     [rbp+800h+pv], 0
0x140024972  mov     [rbp+800h+var_848], 0
0x140024976  lea     rax, [rbp+800h+var_847]
0x14002497a  mov     [rbp+800h+var_40], rax
0x140024981  lea     rax, [rbp+800h+var_47]
0x140024988  mov     [rbp+800h+var_30], rax
0x14002498f  mov     [rbp+800h+var_847], 80408040h
0x140024996  mov     [rbp+800h+var_843], 0
0x14002499a  lea     rax, [rbp+800h+var_842]
0x14002499e  mov     [rbp+800h+var_38], rax
0x1400249a5  movzx   eax, r8b
0x1400249a9  cmovnz  eax, r9d
0x1400249ad  mov     r8d, edx
0x1400249b0  or      r8d, 4
0x1400249b4  test    al, al
0x1400249b6  cmovz   r8d, edx
0x1400249ba  lea     rdx, [rbp+800h+pv]
0x1400249be  mov     rcx, rbx
0x1400249c1  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1400249c6  mov     rsi, rax
0x1400249c9  xor     edx, edx; Val
0x1400249cb  lea     r8d, [rdx+78h]; Size
0x1400249cf  lea     rcx, [rsp+900h+var_8D0]; void *
0x1400249d4  call    memset_0
0x1400249d9  mov     edx, [rbx+0B4h]
0x1400249df  lea     rcx, [rbx+10h]
0x1400249e3  test    edx, edx
0x1400249e5  jz      short loc_1400249ED
0x1400249e7  mov     [rsp+900h+var_8D0], edx
0x1400249eb  jmp     short loc_1400249F3
0x1400249ed  mov     eax, [rcx]
0x1400249ef  mov     [rsp+900h+var_8D0], eax
0x1400249f3  mov     rax, [rbx+18h]
0x1400249f7  mov     [rsp+900h+var_8C8], rax
0x1400249fc  mov     eax, [rbx+14h]
0x1400249ff  mov     [rsp+900h+var_8C0], eax
0x140024a03  movups  xmm0, xmmword ptr [rbx+90h]
0x140024a0a  movdqu  [rsp+900h+var_8BC], xmm0
0x140024a10  mov     eax, [rbx+40h]
0x140024a13  bts     eax, 15h
0x140024a17  mov     [rsp+900h+var_8AC], eax
0x140024a1b  mov     al, [rbx+0A0h]
0x140024a21  mov     [rsp+900h+var_8A8], al
0x140024a25  movzx   eax, word ptr [rbx+0A2h]
0x140024a2c  mov     [rsp+900h+var_8A6], ax
0x140024a31  mov     rax, [rbx+0A8h]
0x140024a38  mov     [rsp+900h+var_8A0], rax
0x140024a3d  mov     [rsp+900h+var_898], rdi
0x140024a42  mov     [rsp+900h+var_888], rsi
0x140024a47  mov     eax, [rbx+0B0h]
0x140024a4d  mov     [rbp+800h+var_864], eax
0x140024a50  test    edx, edx
0x140024a52  jz      short loc_140024A5B
0x140024a54  mov     eax, [rcx]
0x140024a56  mov     [rbp+800h+var_860], eax
0x140024a59  jmp     short loc_140024A62
0x140024a5b  mov     [rbp+800h+var_860], 0
0x140024a62  xor     r9d, r9d
0x140024a65  xor     ecx, ecx
0x140024a67  mov     rdx, [rbx+48h]
0x140024a6b  imul    r8, [rbx+58h], 0A8h
0x140024a73  add     r8, rdx
0x140024a76  cmp     rdx, r8
0x140024a79  jz      short loc_140024AB6
0x140024a7b  mov     eax, [rdx+8]
0x140024a7e  cmp     r9d, eax
0x140024a81  cmovnz  rcx, rdx
0x140024a85  add     rdx, 0A8h
0x140024a8c  cmp     r9d, eax
0x140024a8f  cmovz   eax, r9d
0x140024a93  mov     r9d, eax
0x140024a96  cmp     rdx, r8
0x140024a99  jnz     short loc_140024A7B
0x140024a9b  test    rcx, rcx
0x140024a9e  jz      short loc_140024AB6
0x140024aa0  mov     eax, [rcx+8]
0x140024aa3  mov     [rbp+800h+var_880], eax
0x140024aa6  mov     rax, [rcx+38h]
0x140024aaa  mov     [rbp+800h+var_878], rax
0x140024aae  movzx   eax, word ptr [rcx+40h]
0x140024ab2  mov     [rbp+800h+var_870], ax
0x140024ab6  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x140024abd  test    rax, rax
0x140024ac0  jnz     short loc_140024B0A
0x140024ac2  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x140024ac9  test    rax, rax
0x140024acc  jnz     short loc_140024AE8
0x140024ace  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140024ad5  call    cs:__imp_GetModuleHandleW
0x140024adc  nop     dword ptr [rax+rax+00h]
0x140024ae1  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x140024ae8  lea     rdx, aTestreport; "TestReport"
0x140024aef  mov     rcx, rax; hModule
0x140024af2  call    cs:__imp_GetProcAddress
0x140024af9  nop     dword ptr [rax+rax+00h]
0x140024afe  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x140024b05  test    rax, rax
0x140024b08  jz      short loc_140024B15
0x140024b0a  lea     rcx, [rsp+900h+var_8D0]
0x140024b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024b14  nop
0x140024b15  mov     rcx, [rbx]
0x140024b18  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x140024b1f  lea     rdx, [rsp+900h+var_8D0]
0x140024b24  test    rax, rax
0x140024b27  jz      loc_140024BB2
0x140024b2d  mov     [rsp+900h+var_8E0], rdx
0x140024b32  xor     r9d, r9d
0x140024b35  xor     r8d, r8d
0x140024b38  xor     edx, edx
0x140024b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024b3f  test    al, al
0x140024b41  jnz     short loc_140024BBF
0x140024b43  mov     eax, 400Eh
0x140024b48  mov     [rsp+900h+var_8A6], ax
0x140024b4d  mov     [rsp+900h+var_8A8], 3
0x140024b52  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x140024b59  test    rax, rax
0x140024b5c  jnz     short loc_140024BA6
0x140024b5e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x140024b65  test    rax, rax
0x140024b68  jnz     short loc_140024B84
0x140024b6a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140024b71  call    cs:__imp_GetModuleHandleW
0x140024b78  nop     dword ptr [rax+rax+00h]
0x140024b7d  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x140024b84  lea     rdx, aTestreport; "TestReport"
0x140024b8b  mov     rcx, rax; hModule
0x140024b8e  call    cs:__imp_GetProcAddress
0x140024b95  nop     dword ptr [rax+rax+00h]
0x140024b9a  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x140024ba1  test    rax, rax
0x140024ba4  jz      short loc_140024BBF
0x140024ba6  lea     rcx, [rsp+900h+var_8D0]
0x140024bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024bb0  jmp     short loc_140024BBF
0x140024bb2  mov     rax, [rcx]
0x140024bb5  mov     rax, [rax+18h]
0x140024bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024bbe  nop
0x140024bbf  mov     rcx, [rbp+800h+pv]; pv
0x140024bc3  test    rcx, rcx
0x140024bc6  jz      short loc_140024BD5
0x140024bc8  call    cs:__imp_CoTaskMemFree
0x140024bcf  nop     dword ptr [rax+rax+00h]
0x140024bd4  nop
0x140024bd5  mov     rcx, [rbp+800h+var_20]
0x140024bdc  xor     rcx, rsp; StackCookie
0x140024bdf  call    __security_check_cookie
0x140024be4  mov     rbx, [rsp+900h+arg_10]
0x140024bec  add     rsp, 8F0h
0x140024bf3  pop     rdi
0x140024bf4  pop     rsi
0x140024bf5  pop     rbp
0x140024bf6  retn
```
