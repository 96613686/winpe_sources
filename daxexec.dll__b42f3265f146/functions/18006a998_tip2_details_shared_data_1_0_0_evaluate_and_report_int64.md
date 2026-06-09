# tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)

- ea: `0x18006a998`
- end: `0x18006ad40`
- name: `?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `936`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18006a114`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18006a998`
- `0x18006ad48`
- `0x18006cacc`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006ac1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006acb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006ac1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006acb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ac3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006acd6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ac3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006acd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ad10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ad10`

## string_xrefs

- `0x18006ac16`: `kernelbase.dll`
- `0x18006acb2`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64 a1, __int64 a2)
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
      v12 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &pv, v11);
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
0x18006a998  mov     [rsp-8+arg_10], rbx
0x18006a99d  push    rbp
0x18006a99e  push    rsi
0x18006a99f  push    rdi
0x18006a9a0  lea     rbp, [rsp-7F0h]
0x18006a9a8  sub     rsp, 8F0h
0x18006a9af  mov     rax, cs:__security_cookie
0x18006a9b6  xor     rax, rsp
0x18006a9b9  mov     [rbp+800h+var_20], rax
0x18006a9c0  mov     rdi, rdx
0x18006a9c3  mov     rbx, rcx
0x18006a9c6  add     rcx, 8; this
0x18006a9ca  cmp     byte ptr [rcx+98h], 0
0x18006a9d1  jnz     short loc_18006AA42
0x18006a9d3  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x18006a9d7  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x18006a9db  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x18006a9df  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x18006a9e4  test    al, al
0x18006a9e6  jz      short loc_18006AA42
0x18006a9e8  mov     rcx, [rbx]
0x18006a9eb  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18006a9f2  test    rax, rax
0x18006a9f5  jz      short loc_18006AA36
0x18006a9f7  mov     [rsp+900h+var_8E0], 0
0x18006aa00  xor     r9d, r9d
0x18006aa03  xor     r8d, r8d
0x18006aa06  xor     edx, edx
0x18006aa08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa0d  test    al, al
0x18006aa0f  jnz     short loc_18006AA42
0x18006aa11  cmp     [rbx+0A0h], al
0x18006aa17  jnz     short loc_18006AA42
0x18006aa19  mov     byte ptr [rbx+0A0h], 3
0x18006aa20  mov     word ptr [rbx+0A2h], 400Bh
0x18006aa29  mov     qword ptr [rbx+0A8h], 0
0x18006aa34  jmp     short loc_18006AA42
0x18006aa36  mov     rax, [rcx]
0x18006aa39  mov     rax, [rax]
0x18006aa3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa41  nop
0x18006aa42  mov     cl, [rbx+0A0h]
0x18006aa48  cmp     cl, 5
0x18006aa4b  jz      loc_18006AD1D
0x18006aa51  mov     r9d, 1
0x18006aa57  test    cl, cl
0x18006aa59  jnz     short loc_18006AA78
0x18006aa5b  mov     byte ptr [rbx+0A0h], 3
0x18006aa62  mov     word ptr [rbx+0A2h], 400Ah
0x18006aa6b  mov     qword ptr [rbx+0A8h], 0
0x18006aa76  jmp     short loc_18006AA8E
0x18006aa78  lea     eax, [rcx-2]
0x18006aa7b  cmp     al, r9b
0x18006aa7e  jbe     short loc_18006AA8E
0x18006aa80  test    dword ptr [rbx+14h], 1000h
0x18006aa87  jz      short loc_18006AA9C
0x18006aa89  cmp     cl, 4
0x18006aa8c  jz      short loc_18006AA9C
0x18006aa8e  test    dword ptr [rbx+40h], 800h
0x18006aa95  jz      short loc_18006AA9C
0x18006aa97  mov     r8b, r9b
0x18006aa9a  jmp     short loc_18006AA9F
0x18006aa9c  xor     r8b, r8b
0x18006aa9f  movzx   eax, r8b
0x18006aaa3  mov     edx, eax
0x18006aaa5  or      edx, 2
0x18006aaa8  test    dword ptr [rbx+14h], 200h
0x18006aaaf  cmovz   edx, eax
0x18006aab2  mov     [rbp+800h+pv], 0
0x18006aaba  mov     [rbp+800h+var_848], 0
0x18006aabe  lea     rax, [rbp+800h+var_847]
0x18006aac2  mov     [rbp+800h+var_40], rax
0x18006aac9  lea     rax, [rbp+800h+var_47]
0x18006aad0  mov     [rbp+800h+var_30], rax
0x18006aad7  mov     [rbp+800h+var_847], 80408040h
0x18006aade  mov     [rbp+800h+var_843], 0
0x18006aae2  lea     rax, [rbp+800h+var_842]
0x18006aae6  mov     [rbp+800h+var_38], rax
0x18006aaed  movzx   eax, r8b
0x18006aaf1  cmovnz  eax, r9d
0x18006aaf5  mov     r8d, edx
0x18006aaf8  or      r8d, 4
0x18006aafc  test    al, al
0x18006aafe  cmovz   r8d, edx
0x18006ab02  lea     rdx, [rbp+800h+pv]
0x18006ab06  mov     rcx, rbx
0x18006ab09  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18006ab0e  mov     rsi, rax
0x18006ab11  xor     edx, edx; Val
0x18006ab13  lea     r8d, [rdx+78h]; Size
0x18006ab17  lea     rcx, [rsp+900h+var_8D0]; void *
0x18006ab1c  call    memset_0
0x18006ab21  mov     edx, [rbx+0B4h]
0x18006ab27  lea     rcx, [rbx+10h]
0x18006ab2b  test    edx, edx
0x18006ab2d  jz      short loc_18006AB35
0x18006ab2f  mov     [rsp+900h+var_8D0], edx
0x18006ab33  jmp     short loc_18006AB3B
0x18006ab35  mov     eax, [rcx]
0x18006ab37  mov     [rsp+900h+var_8D0], eax
0x18006ab3b  mov     rax, [rbx+18h]
0x18006ab3f  mov     [rsp+900h+var_8C8], rax
0x18006ab44  mov     eax, [rbx+14h]
0x18006ab47  mov     [rsp+900h+var_8C0], eax
0x18006ab4b  movups  xmm0, xmmword ptr [rbx+90h]
0x18006ab52  movdqu  [rsp+900h+var_8BC], xmm0
0x18006ab58  mov     eax, [rbx+40h]
0x18006ab5b  bts     eax, 15h
0x18006ab5f  mov     [rsp+900h+var_8AC], eax
0x18006ab63  mov     al, [rbx+0A0h]
0x18006ab69  mov     [rsp+900h+var_8A8], al
0x18006ab6d  movzx   eax, word ptr [rbx+0A2h]
0x18006ab74  mov     [rsp+900h+var_8A6], ax
0x18006ab79  mov     rax, [rbx+0A8h]
0x18006ab80  mov     [rsp+900h+var_8A0], rax
0x18006ab85  mov     [rsp+900h+var_898], rdi
0x18006ab8a  mov     [rsp+900h+var_888], rsi
0x18006ab8f  mov     eax, [rbx+0B0h]
0x18006ab95  mov     [rbp+800h+var_864], eax
0x18006ab98  test    edx, edx
0x18006ab9a  jz      short loc_18006ABA3
0x18006ab9c  mov     eax, [rcx]
0x18006ab9e  mov     [rbp+800h+var_860], eax
0x18006aba1  jmp     short loc_18006ABAA
0x18006aba3  mov     [rbp+800h+var_860], 0
0x18006abaa  xor     r9d, r9d
0x18006abad  xor     ecx, ecx
0x18006abaf  mov     rdx, [rbx+48h]
0x18006abb3  imul    r8, [rbx+58h], 0A8h
0x18006abbb  add     r8, rdx
0x18006abbe  cmp     rdx, r8
0x18006abc1  jz      short loc_18006ABFE
0x18006abc3  mov     eax, [rdx+8]
0x18006abc6  cmp     r9d, eax
0x18006abc9  cmovnz  rcx, rdx
0x18006abcd  add     rdx, 0A8h
0x18006abd4  cmp     r9d, eax
0x18006abd7  cmovz   eax, r9d
0x18006abdb  mov     r9d, eax
0x18006abde  cmp     rdx, r8
0x18006abe1  jnz     short loc_18006ABC3
0x18006abe3  test    rcx, rcx
0x18006abe6  jz      short loc_18006ABFE
0x18006abe8  mov     eax, [rcx+8]
0x18006abeb  mov     [rbp+800h+var_880], eax
0x18006abee  mov     rax, [rcx+38h]
0x18006abf2  mov     [rbp+800h+var_878], rax
0x18006abf6  movzx   eax, word ptr [rcx+40h]
0x18006abfa  mov     [rbp+800h+var_870], ax
0x18006abfe  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18006ac05  test    rax, rax
0x18006ac08  jnz     short loc_18006AC52
0x18006ac0a  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18006ac11  test    rax, rax
0x18006ac14  jnz     short loc_18006AC30
0x18006ac16  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18006ac1d  call    cs:__imp_GetModuleHandleW
0x18006ac24  nop     dword ptr [rax+rax+00h]
0x18006ac29  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18006ac30  lea     rdx, aTestreport; "TestReport"
0x18006ac37  mov     rcx, rax; hModule
0x18006ac3a  call    cs:__imp_GetProcAddress
0x18006ac41  nop     dword ptr [rax+rax+00h]
0x18006ac46  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18006ac4d  test    rax, rax
0x18006ac50  jz      short loc_18006AC5D
0x18006ac52  lea     rcx, [rsp+900h+var_8D0]
0x18006ac57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac5c  nop
0x18006ac5d  mov     rcx, [rbx]
0x18006ac60  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18006ac67  lea     rdx, [rsp+900h+var_8D0]
0x18006ac6c  test    rax, rax
0x18006ac6f  jz      loc_18006ACFA
0x18006ac75  mov     [rsp+900h+var_8E0], rdx
0x18006ac7a  xor     r9d, r9d
0x18006ac7d  xor     r8d, r8d
0x18006ac80  xor     edx, edx
0x18006ac82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac87  test    al, al
0x18006ac89  jnz     short loc_18006AD07
0x18006ac8b  mov     eax, 400Eh
0x18006ac90  mov     [rsp+900h+var_8A6], ax
0x18006ac95  mov     [rsp+900h+var_8A8], 3
0x18006ac9a  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18006aca1  test    rax, rax
0x18006aca4  jnz     short loc_18006ACEE
0x18006aca6  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18006acad  test    rax, rax
0x18006acb0  jnz     short loc_18006ACCC
0x18006acb2  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18006acb9  call    cs:__imp_GetModuleHandleW
0x18006acc0  nop     dword ptr [rax+rax+00h]
0x18006acc5  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18006accc  lea     rdx, aTestreport; "TestReport"
0x18006acd3  mov     rcx, rax; hModule
0x18006acd6  call    cs:__imp_GetProcAddress
0x18006acdd  nop     dword ptr [rax+rax+00h]
0x18006ace2  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18006ace9  test    rax, rax
0x18006acec  jz      short loc_18006AD07
0x18006acee  lea     rcx, [rsp+900h+var_8D0]
0x18006acf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006acf8  jmp     short loc_18006AD07
0x18006acfa  mov     rax, [rcx]
0x18006acfd  mov     rax, [rax+18h]
0x18006ad01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad06  nop
0x18006ad07  mov     rcx, [rbp+800h+pv]; pv
0x18006ad0b  test    rcx, rcx
0x18006ad0e  jz      short loc_18006AD1D
0x18006ad10  call    cs:__imp_CoTaskMemFree
0x18006ad17  nop     dword ptr [rax+rax+00h]
0x18006ad1c  nop
0x18006ad1d  mov     rcx, [rbp+800h+var_20]
0x18006ad24  xor     rcx, rsp; StackCookie
0x18006ad27  call    __security_check_cookie
0x18006ad2c  mov     rbx, [rsp+900h+arg_10]
0x18006ad34  add     rsp, 8F0h
0x18006ad3b  pop     rdi
0x18006ad3c  pop     rsi
0x18006ad3d  pop     rbp
0x18006ad3e  retn
```
