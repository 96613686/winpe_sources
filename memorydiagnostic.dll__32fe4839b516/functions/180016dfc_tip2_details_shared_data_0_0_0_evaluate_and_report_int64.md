# tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)

- ea: `0x180016dfc`
- end: `0x180017194`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `920`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180016740`

## callees

- `0x1800026b0`
- `0x180003374`
- `0x180016dfc`
- `0x18001719c`
- `0x180019820`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180017071`
- `KERNEL32!GetModuleHandleW` at `0x18001710d`
- `KERNEL32!GetModuleHandleW` at `0x180017071`
- `KERNEL32!GetModuleHandleW` at `0x18001710d`
- `KERNEL32!GetProcAddress` at `0x18001708e`
- `KERNEL32!GetProcAddress` at `0x18001712a`
- `KERNEL32!GetProcAddress` at `0x18001708e`
- `KERNEL32!GetProcAddress` at `0x18001712a`
- `ole32!CoTaskMemFree` at `0x180017164`
- `ole32!CoTaskMemFree` at `0x180017164`

## string_xrefs

- `0x18001706a`: `kernelbase.dll`
- `0x180017106`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64 a1, __int64 a2)
{
  void (__fastcall ***v4)(_QWORD); // rcx
  char v5; // cl
  unsigned __int8 v6; // al
  char v7; // dl
  unsigned int v8; // ecx
  __int64 v9; // r8
  __int64 v10; // rsi
  int v11; // ecx
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // eax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  void (__fastcall ***v19)(_QWORD); // rcx
  FARPROC v20; // rax
  HMODULE v21; // rax
  const struct tip2::test_requirement *v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h]
  int v25; // [rsp+40h] [rbp-C0h]
  __int128 v26; // [rsp+44h] [rbp-BCh]
  int v27; // [rsp+54h] [rbp-ACh]
  char v28; // [rsp+58h] [rbp-A8h]
  __int16 v29; // [rsp+5Ah] [rbp-A6h]
  __int64 v30; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+78h] [rbp-88h]
  int v33; // [rsp+80h] [rbp-80h]
  __int64 v34; // [rsp+88h] [rbp-78h]
  __int16 v35; // [rsp+90h] [rbp-70h]
  int v36; // [rsp+9Ch] [rbp-64h]
  int v37; // [rsp+A0h] [rbp-60h]
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  char v39; // [rsp+B8h] [rbp-48h]
  int v40; // [rsp+B9h] [rbp-47h] BYREF
  char v41; // [rsp+BDh] [rbp-43h]
  char v42; // [rsp+BEh] [rbp-42h] BYREF
  char v43; // [rsp+8B9h] [rbp+7B9h] BYREF
  int *v44; // [rsp+8C0h] [rbp+7C0h]
  char *v45; // [rsp+8C8h] [rbp+7C8h]
  char *v46; // [rsp+8D0h] [rbp+7D0h]

  if ( !*(_BYTE *)(a1 + 160)
    && tip2::details::evaluate_flags(
         (tip2::details *)(a1 + 8),
         *(const struct tip2::test_state **)(a1 + 40),
         *(const struct tip2::test_requirement **)(a1 + 56),
         *(const struct tip2::test_requirement **)(a1 + 48),
         v22) )
  {
    v4 = *(void (__fastcall ****)(_QWORD))a1;
    if ( tip2::details::g_test_interface_exception_guard )
    {
      if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v4, 0, 0, 0, 0) && !*(_BYTE *)(a1 + 160) )
      {
        *(_BYTE *)(a1 + 160) = 3;
        *(_WORD *)(a1 + 162) = 16395;
        *(_QWORD *)(a1 + 168) = 0;
      }
    }
    else
    {
      (**v4)(v4);
    }
  }
  v5 = *(_BYTE *)(a1 + 160);
  if ( v5 != 5 )
  {
    if ( v5 )
    {
      if ( (unsigned __int8)(v5 - 2) > 1u && ((*(_DWORD *)(a1 + 20) & 0x1000) == 0 || v5 == 4) )
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
      v6 = 1;
LABEL_17:
      v7 = v6;
      v8 = v6 | 2;
      if ( (*(_DWORD *)(a1 + 20) & 0x200) == 0 )
        v8 = v6;
      pv = 0;
      v39 = 0;
      v44 = &v40;
      v46 = &v43;
      v40 = -2143256512;
      v41 = 0;
      v45 = &v42;
      if ( (*(_DWORD *)(a1 + 20) & 0x200) != 0 )
        v7 = 1;
      v9 = v8 | 4;
      if ( !v7 )
        v9 = v8;
      v10 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, v9);
      memset_0(&v23, 0, 0x78u);
      v11 = *(_DWORD *)(a1 + 180);
      if ( v11 )
        v23 = *(_DWORD *)(a1 + 180);
      else
        v23 = *(_DWORD *)(a1 + 16);
      v24 = *(_QWORD *)(a1 + 24);
      v25 = *(_DWORD *)(a1 + 20);
      v26 = *(_OWORD *)(a1 + 144);
      v27 = *(_DWORD *)(a1 + 64) | 0x200000;
      v28 = *(_BYTE *)(a1 + 160);
      v29 = *(_WORD *)(a1 + 162);
      v30 = *(_QWORD *)(a1 + 168);
      v31 = a2;
      v32 = v10;
      v36 = *(_DWORD *)(a1 + 176);
      if ( v11 )
        v37 = *(_DWORD *)(a1 + 16);
      else
        v37 = 0;
      v12 = 0;
      v13 = 0;
      v14 = *(_QWORD *)(a1 + 72);
      v15 = v14 + 168LL * *(_QWORD *)(a1 + 88);
      if ( v14 != v15 )
      {
        do
        {
          v16 = *(_DWORD *)(v14 + 8);
          if ( (_DWORD)v12 != v16 )
            v13 = v14;
          v14 += 168;
          if ( (_DWORD)v12 == v16 )
            v16 = v12;
          v12 = v16;
        }
        while ( v14 != v15 );
        if ( v13 )
        {
          v33 = *(_DWORD *)(v13 + 8);
          v34 = *(_QWORD *)(v13 + 56);
          v35 = *(_WORD *)(v13 + 64);
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
        ((void (__fastcall *)(int *, __int64, __int64, __int64))ProcAddress)(&v23, v14, v15, v12);
      v19 = *(void (__fastcall ****)(_QWORD))a1;
      if ( tip2::details::g_test_interface_exception_guard )
      {
        if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v19, 0, 0, 0, &v23) )
        {
          v29 = 16398;
          v28 = 3;
          v20 = (FARPROC)`TestReport'::`2'::s_pfnTestReport;
          if ( `TestReport'::`2'::s_pfnTestReport )
            goto LABEL_48;
          v21 = g_tip_details_kernelbaseModuleHandle;
          if ( !g_tip_details_kernelbaseModuleHandle )
          {
            v21 = GetModuleHandleW(L"kernelbase.dll");
            g_tip_details_kernelbaseModuleHandle = v21;
          }
          v20 = GetProcAddress(v21, "TestReport");
          `TestReport'::`2'::s_pfnTestReport = (__int64)v20;
          if ( v20 )
LABEL_48:
            ((void (__fastcall *)(int *))v20)(&v23);
        }
      }
      else
      {
        ((void (__fastcall *)(void (__fastcall ***)(_QWORD), int *))(*v19)[3])(v19, &v23);
      }
      if ( pv )
        CoTaskMemFree(pv);
      return;
    }
LABEL_16:
    v6 = 0;
    goto LABEL_17;
  }
}

```

## disassembly

```asm
0x180016dfc  mov     [rsp-8+arg_10], rbx
0x180016e01  push    rbp
0x180016e02  push    rsi
0x180016e03  push    rdi
0x180016e04  lea     rbp, [rsp-7F0h]
0x180016e0c  sub     rsp, 8F0h
0x180016e13  mov     rax, cs:__security_cookie
0x180016e1a  xor     rax, rsp
0x180016e1d  mov     [rbp+800h+var_20], rax
0x180016e24  mov     rdi, rdx
0x180016e27  mov     rbx, rcx
0x180016e2a  cmp     byte ptr [rcx+0A0h], 0
0x180016e31  jnz     short loc_180016EA0
0x180016e33  add     rcx, 8; this
0x180016e37  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x180016e3b  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x180016e3f  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x180016e43  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x180016e48  test    al, al
0x180016e4a  jz      short loc_180016EA0
0x180016e4c  mov     rcx, [rbx]
0x180016e4f  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180016e56  test    rax, rax
0x180016e59  jz      short loc_180016E94
0x180016e5b  and     [rsp+900h+var_8E0], 0
0x180016e61  xor     r9d, r9d
0x180016e64  xor     r8d, r8d
0x180016e67  xor     edx, edx
0x180016e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e6e  test    al, al
0x180016e70  jnz     short loc_180016EA0
0x180016e72  cmp     [rbx+0A0h], al
0x180016e78  jnz     short loc_180016EA0
0x180016e7a  mov     byte ptr [rbx+0A0h], 3
0x180016e81  mov     word ptr [rbx+0A2h], 400Bh
0x180016e8a  and     qword ptr [rbx+0A8h], 0
0x180016e92  jmp     short loc_180016EA0
0x180016e94  mov     rax, [rcx]
0x180016e97  mov     rax, [rax]
0x180016e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e9f  nop
0x180016ea0  mov     cl, [rbx+0A0h]
0x180016ea6  cmp     cl, 5
0x180016ea9  jz      loc_180017171
0x180016eaf  mov     r9d, 1
0x180016eb5  test    cl, cl
0x180016eb7  jnz     short loc_180016ED3
0x180016eb9  mov     byte ptr [rbx+0A0h], 3
0x180016ec0  mov     word ptr [rbx+0A2h], 400Ah
0x180016ec9  and     qword ptr [rbx+0A8h], 0
0x180016ed1  jmp     short loc_180016EE9
0x180016ed3  lea     eax, [rcx-2]
0x180016ed6  cmp     al, r9b
0x180016ed9  jbe     short loc_180016EE9
0x180016edb  test    dword ptr [rbx+14h], 1000h
0x180016ee2  jz      short loc_180016EF7
0x180016ee4  cmp     cl, 4
0x180016ee7  jz      short loc_180016EF7
0x180016ee9  test    dword ptr [rbx+40h], 800h
0x180016ef0  jz      short loc_180016EF7
0x180016ef2  mov     al, r9b
0x180016ef5  jmp     short loc_180016EF9
0x180016ef7  xor     al, al
0x180016ef9  movzx   edx, al
0x180016efc  mov     ecx, edx
0x180016efe  or      ecx, 2
0x180016f01  test    dword ptr [rbx+14h], 200h
0x180016f08  cmovz   ecx, edx
0x180016f0b  and     [rbp+800h+pv], 0
0x180016f10  mov     [rbp+800h+var_848], 0
0x180016f14  lea     r8, [rbp+800h+var_847]
0x180016f18  mov     [rbp+800h+var_40], r8
0x180016f1f  lea     r8, [rbp+800h+var_47]
0x180016f26  mov     [rbp+800h+var_30], r8
0x180016f2d  mov     [rbp+800h+var_847], 80408040h
0x180016f34  mov     [rbp+800h+var_843], 0
0x180016f38  lea     r8, [rbp+800h+var_842]
0x180016f3c  mov     [rbp+800h+var_38], r8
0x180016f43  test    dword ptr [rbx+14h], 200h
0x180016f4a  cmovnz  edx, r9d
0x180016f4e  mov     r8d, ecx
0x180016f51  or      r8d, 4
0x180016f55  test    dl, dl
0x180016f57  cmovz   r8d, ecx
0x180016f5b  lea     rdx, [rbp+800h+pv]
0x180016f5f  mov     rcx, rbx
0x180016f62  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180016f67  mov     rsi, rax
0x180016f6a  xor     edx, edx; Val
0x180016f6c  lea     r8d, [rdx+78h]; Size
0x180016f70  lea     rcx, [rsp+900h+var_8D0]; void *
0x180016f75  call    memset_0
0x180016f7a  mov     ecx, [rbx+0B4h]
0x180016f80  test    ecx, ecx
0x180016f82  jz      short loc_180016F8A
0x180016f84  mov     [rsp+900h+var_8D0], ecx
0x180016f88  jmp     short loc_180016F91
0x180016f8a  mov     eax, [rbx+10h]
0x180016f8d  mov     [rsp+900h+var_8D0], eax
0x180016f91  mov     rax, [rbx+18h]
0x180016f95  mov     [rsp+900h+var_8C8], rax
0x180016f9a  mov     eax, [rbx+14h]
0x180016f9d  mov     [rsp+900h+var_8C0], eax
0x180016fa1  movups  xmm0, xmmword ptr [rbx+90h]
0x180016fa8  movdqu  [rsp+900h+var_8BC], xmm0
0x180016fae  mov     eax, [rbx+40h]
0x180016fb1  bts     eax, 15h
0x180016fb5  mov     [rsp+900h+var_8AC], eax
0x180016fb9  mov     al, [rbx+0A0h]
0x180016fbf  mov     [rsp+900h+var_8A8], al
0x180016fc3  movzx   eax, word ptr [rbx+0A2h]
0x180016fca  mov     [rsp+900h+var_8A6], ax
0x180016fcf  mov     rax, [rbx+0A8h]
0x180016fd6  mov     [rsp+900h+var_8A0], rax
0x180016fdb  mov     [rsp+900h+var_898], rdi
0x180016fe0  mov     [rsp+900h+var_888], rsi
0x180016fe5  mov     eax, [rbx+0B0h]
0x180016feb  mov     [rbp+800h+var_864], eax
0x180016fee  test    ecx, ecx
0x180016ff0  jz      short loc_180016FFA
0x180016ff2  mov     eax, [rbx+10h]
0x180016ff5  mov     [rbp+800h+var_860], eax
0x180016ff8  jmp     short loc_180016FFE
0x180016ffa  and     [rbp+800h+var_860], 0
0x180016ffe  xor     r9d, r9d
0x180017001  xor     ecx, ecx
0x180017003  mov     rdx, [rbx+48h]
0x180017007  imul    r8, [rbx+58h], 0A8h
0x18001700f  add     r8, rdx
0x180017012  cmp     rdx, r8
0x180017015  jz      short loc_180017052
0x180017017  mov     eax, [rdx+8]
0x18001701a  cmp     r9d, eax
0x18001701d  cmovnz  rcx, rdx
0x180017021  add     rdx, 0A8h
0x180017028  cmp     r9d, eax
0x18001702b  cmovz   eax, r9d
0x18001702f  mov     r9d, eax
0x180017032  cmp     rdx, r8
0x180017035  jnz     short loc_180017017
0x180017037  test    rcx, rcx
0x18001703a  jz      short loc_180017052
0x18001703c  mov     eax, [rcx+8]
0x18001703f  mov     [rbp+800h+var_880], eax
0x180017042  mov     rax, [rcx+38h]
0x180017046  mov     [rbp+800h+var_878], rax
0x18001704a  movzx   eax, word ptr [rcx+40h]
0x18001704e  mov     [rbp+800h+var_870], ax
0x180017052  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180017059  test    rax, rax
0x18001705c  jnz     short loc_1800170A6
0x18001705e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180017065  test    rax, rax
0x180017068  jnz     short loc_180017084
0x18001706a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180017071  call    cs:__imp_GetModuleHandleW
0x180017078  nop     dword ptr [rax+rax+00h]
0x18001707d  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180017084  lea     rdx, aTestreport; "TestReport"
0x18001708b  mov     rcx, rax; hModule
0x18001708e  call    cs:__imp_GetProcAddress
0x180017095  nop     dword ptr [rax+rax+00h]
0x18001709a  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800170a1  test    rax, rax
0x1800170a4  jz      short loc_1800170B1
0x1800170a6  lea     rcx, [rsp+900h+var_8D0]
0x1800170ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170b0  nop
0x1800170b1  mov     rcx, [rbx]
0x1800170b4  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x1800170bb  lea     rdx, [rsp+900h+var_8D0]
0x1800170c0  test    rax, rax
0x1800170c3  jz      loc_18001714E
0x1800170c9  mov     [rsp+900h+var_8E0], rdx
0x1800170ce  xor     r9d, r9d
0x1800170d1  xor     r8d, r8d
0x1800170d4  xor     edx, edx
0x1800170d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170db  test    al, al
0x1800170dd  jnz     short loc_18001715B
0x1800170df  mov     eax, 400Eh
0x1800170e4  mov     [rsp+900h+var_8A6], ax
0x1800170e9  mov     [rsp+900h+var_8A8], 3
0x1800170ee  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800170f5  test    rax, rax
0x1800170f8  jnz     short loc_180017142
0x1800170fa  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180017101  test    rax, rax
0x180017104  jnz     short loc_180017120
0x180017106  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001710d  call    cs:__imp_GetModuleHandleW
0x180017114  nop     dword ptr [rax+rax+00h]
0x180017119  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180017120  lea     rdx, aTestreport; "TestReport"
0x180017127  mov     rcx, rax; hModule
0x18001712a  call    cs:__imp_GetProcAddress
0x180017131  nop     dword ptr [rax+rax+00h]
0x180017136  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18001713d  test    rax, rax
0x180017140  jz      short loc_18001715B
0x180017142  lea     rcx, [rsp+900h+var_8D0]
0x180017147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001714c  jmp     short loc_18001715B
0x18001714e  mov     rax, [rcx]
0x180017151  mov     rax, [rax+18h]
0x180017155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001715a  nop
0x18001715b  mov     rcx, [rbp+800h+pv]; pv
0x18001715f  test    rcx, rcx
0x180017162  jz      short loc_180017171
0x180017164  call    cs:__imp_CoTaskMemFree
0x18001716b  nop     dword ptr [rax+rax+00h]
0x180017170  nop
0x180017171  mov     rcx, [rbp+800h+var_20]
0x180017178  xor     rcx, rsp; StackCookie
0x18001717b  call    __security_check_cookie
0x180017180  mov     rbx, [rsp+900h+arg_10]
0x180017188  add     rsp, 8F0h
0x18001718f  pop     rdi
0x180017190  pop     rsi
0x180017191  pop     rbp
0x180017192  retn
```
