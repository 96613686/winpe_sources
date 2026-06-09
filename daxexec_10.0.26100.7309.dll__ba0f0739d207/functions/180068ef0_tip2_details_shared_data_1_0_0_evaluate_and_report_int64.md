# tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)

- ea: `0x180068ef0`
- end: `0x180069288`
- name: `?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z`
- size: `920`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800686ec`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x180068ef0`
- `0x180069290`
- `0x18006b194`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180069182`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006921e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180069182`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006921e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180069165`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180069201`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180069165`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180069201`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069258`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069258`

## string_xrefs

- `0x18006915e`: `kernelbase.dll`
- `0x1800691fa`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64 a1, __int64 a2)
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
      v10 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &pv, v9);
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
0x180068ef0  mov     [rsp-8+arg_10], rbx
0x180068ef5  push    rbp
0x180068ef6  push    rsi
0x180068ef7  push    rdi
0x180068ef8  lea     rbp, [rsp-7F0h]
0x180068f00  sub     rsp, 8F0h
0x180068f07  mov     rax, cs:__security_cookie
0x180068f0e  xor     rax, rsp
0x180068f11  mov     [rbp+800h+var_20], rax
0x180068f18  mov     rdi, rdx
0x180068f1b  mov     rbx, rcx
0x180068f1e  cmp     byte ptr [rcx+0A0h], 0
0x180068f25  jnz     short loc_180068F94
0x180068f27  add     rcx, 8; this
0x180068f2b  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x180068f2f  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x180068f33  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x180068f37  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x180068f3c  test    al, al
0x180068f3e  jz      short loc_180068F94
0x180068f40  mov     rcx, [rbx]
0x180068f43  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180068f4a  test    rax, rax
0x180068f4d  jz      short loc_180068F88
0x180068f4f  and     [rsp+900h+var_8E0], 0
0x180068f55  xor     r9d, r9d
0x180068f58  xor     r8d, r8d
0x180068f5b  xor     edx, edx
0x180068f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f62  test    al, al
0x180068f64  jnz     short loc_180068F94
0x180068f66  cmp     [rbx+0A0h], al
0x180068f6c  jnz     short loc_180068F94
0x180068f6e  mov     byte ptr [rbx+0A0h], 3
0x180068f75  mov     word ptr [rbx+0A2h], 400Bh
0x180068f7e  and     qword ptr [rbx+0A8h], 0
0x180068f86  jmp     short loc_180068F94
0x180068f88  mov     rax, [rcx]
0x180068f8b  mov     rax, [rax]
0x180068f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f93  nop
0x180068f94  mov     cl, [rbx+0A0h]
0x180068f9a  cmp     cl, 5
0x180068f9d  jz      loc_180069265
0x180068fa3  mov     r9d, 1
0x180068fa9  test    cl, cl
0x180068fab  jnz     short loc_180068FC7
0x180068fad  mov     byte ptr [rbx+0A0h], 3
0x180068fb4  mov     word ptr [rbx+0A2h], 400Ah
0x180068fbd  and     qword ptr [rbx+0A8h], 0
0x180068fc5  jmp     short loc_180068FDD
0x180068fc7  lea     eax, [rcx-2]
0x180068fca  cmp     al, r9b
0x180068fcd  jbe     short loc_180068FDD
0x180068fcf  test    dword ptr [rbx+14h], 1000h
0x180068fd6  jz      short loc_180068FEB
0x180068fd8  cmp     cl, 4
0x180068fdb  jz      short loc_180068FEB
0x180068fdd  test    dword ptr [rbx+40h], 800h
0x180068fe4  jz      short loc_180068FEB
0x180068fe6  mov     al, r9b
0x180068fe9  jmp     short loc_180068FED
0x180068feb  xor     al, al
0x180068fed  movzx   edx, al
0x180068ff0  mov     ecx, edx
0x180068ff2  or      ecx, 2
0x180068ff5  test    dword ptr [rbx+14h], 200h
0x180068ffc  cmovz   ecx, edx
0x180068fff  and     [rbp+800h+pv], 0
0x180069004  mov     [rbp+800h+var_848], 0
0x180069008  lea     r8, [rbp+800h+var_847]
0x18006900c  mov     [rbp+800h+var_40], r8
0x180069013  lea     r8, [rbp+800h+var_47]
0x18006901a  mov     [rbp+800h+var_30], r8
0x180069021  mov     [rbp+800h+var_847], 80408040h
0x180069028  mov     [rbp+800h+var_843], 0
0x18006902c  lea     r8, [rbp+800h+var_842]
0x180069030  mov     [rbp+800h+var_38], r8
0x180069037  test    dword ptr [rbx+14h], 200h
0x18006903e  cmovnz  edx, r9d
0x180069042  mov     r8d, ecx
0x180069045  or      r8d, 4
0x180069049  test    dl, dl
0x18006904b  cmovz   r8d, ecx
0x18006904f  lea     rdx, [rbp+800h+pv]
0x180069053  mov     rcx, rbx
0x180069056  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18006905b  mov     rsi, rax
0x18006905e  xor     edx, edx; Val
0x180069060  lea     r8d, [rdx+78h]; Size
0x180069064  lea     rcx, [rsp+900h+var_8D0]; void *
0x180069069  call    memset_0
0x18006906e  mov     ecx, [rbx+0B4h]
0x180069074  test    ecx, ecx
0x180069076  jz      short loc_18006907E
0x180069078  mov     [rsp+900h+var_8D0], ecx
0x18006907c  jmp     short loc_180069085
0x18006907e  mov     eax, [rbx+10h]
0x180069081  mov     [rsp+900h+var_8D0], eax
0x180069085  mov     rax, [rbx+18h]
0x180069089  mov     [rsp+900h+var_8C8], rax
0x18006908e  mov     eax, [rbx+14h]
0x180069091  mov     [rsp+900h+var_8C0], eax
0x180069095  movups  xmm0, xmmword ptr [rbx+90h]
0x18006909c  movdqu  [rsp+900h+var_8BC], xmm0
0x1800690a2  mov     eax, [rbx+40h]
0x1800690a5  bts     eax, 15h
0x1800690a9  mov     [rsp+900h+var_8AC], eax
0x1800690ad  mov     al, [rbx+0A0h]
0x1800690b3  mov     [rsp+900h+var_8A8], al
0x1800690b7  movzx   eax, word ptr [rbx+0A2h]
0x1800690be  mov     [rsp+900h+var_8A6], ax
0x1800690c3  mov     rax, [rbx+0A8h]
0x1800690ca  mov     [rsp+900h+var_8A0], rax
0x1800690cf  mov     [rsp+900h+var_898], rdi
0x1800690d4  mov     [rsp+900h+var_888], rsi
0x1800690d9  mov     eax, [rbx+0B0h]
0x1800690df  mov     [rbp+800h+var_864], eax
0x1800690e2  test    ecx, ecx
0x1800690e4  jz      short loc_1800690EE
0x1800690e6  mov     eax, [rbx+10h]
0x1800690e9  mov     [rbp+800h+var_860], eax
0x1800690ec  jmp     short loc_1800690F2
0x1800690ee  and     [rbp+800h+var_860], 0
0x1800690f2  xor     r9d, r9d
0x1800690f5  xor     ecx, ecx
0x1800690f7  mov     rdx, [rbx+48h]
0x1800690fb  imul    r8, [rbx+58h], 0A8h
0x180069103  add     r8, rdx
0x180069106  cmp     rdx, r8
0x180069109  jz      short loc_180069146
0x18006910b  mov     eax, [rdx+8]
0x18006910e  cmp     r9d, eax
0x180069111  cmovnz  rcx, rdx
0x180069115  add     rdx, 0A8h
0x18006911c  cmp     r9d, eax
0x18006911f  cmovz   eax, r9d
0x180069123  mov     r9d, eax
0x180069126  cmp     rdx, r8
0x180069129  jnz     short loc_18006910B
0x18006912b  test    rcx, rcx
0x18006912e  jz      short loc_180069146
0x180069130  mov     eax, [rcx+8]
0x180069133  mov     [rbp+800h+var_880], eax
0x180069136  mov     rax, [rcx+38h]
0x18006913a  mov     [rbp+800h+var_878], rax
0x18006913e  movzx   eax, word ptr [rcx+40h]
0x180069142  mov     [rbp+800h+var_870], ax
0x180069146  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x18006914d  test    rax, rax
0x180069150  jnz     short loc_18006919A
0x180069152  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180069159  test    rax, rax
0x18006915c  jnz     short loc_180069178
0x18006915e  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180069165  call    cs:__imp_GetModuleHandleW
0x18006916c  nop     dword ptr [rax+rax+00h]
0x180069171  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180069178  lea     rdx, aTestreport; "TestReport"
0x18006917f  mov     rcx, rax; hModule
0x180069182  call    cs:__imp_GetProcAddress
0x180069189  nop     dword ptr [rax+rax+00h]
0x18006918e  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180069195  test    rax, rax
0x180069198  jz      short loc_1800691A5
0x18006919a  lea     rcx, [rsp+900h+var_8D0]
0x18006919f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800691a4  nop
0x1800691a5  mov     rcx, [rbx]
0x1800691a8  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x1800691af  lea     rdx, [rsp+900h+var_8D0]
0x1800691b4  test    rax, rax
0x1800691b7  jz      loc_180069242
0x1800691bd  mov     [rsp+900h+var_8E0], rdx
0x1800691c2  xor     r9d, r9d
0x1800691c5  xor     r8d, r8d
0x1800691c8  xor     edx, edx
0x1800691ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800691cf  test    al, al
0x1800691d1  jnz     short loc_18006924F
0x1800691d3  mov     eax, 400Eh
0x1800691d8  mov     [rsp+900h+var_8A6], ax
0x1800691dd  mov     [rsp+900h+var_8A8], 3
0x1800691e2  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800691e9  test    rax, rax
0x1800691ec  jnz     short loc_180069236
0x1800691ee  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800691f5  test    rax, rax
0x1800691f8  jnz     short loc_180069214
0x1800691fa  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180069201  call    cs:__imp_GetModuleHandleW
0x180069208  nop     dword ptr [rax+rax+00h]
0x18006920d  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180069214  lea     rdx, aTestreport; "TestReport"
0x18006921b  mov     rcx, rax; hModule
0x18006921e  call    cs:__imp_GetProcAddress
0x180069225  nop     dword ptr [rax+rax+00h]
0x18006922a  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180069231  test    rax, rax
0x180069234  jz      short loc_18006924F
0x180069236  lea     rcx, [rsp+900h+var_8D0]
0x18006923b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069240  jmp     short loc_18006924F
0x180069242  mov     rax, [rcx]
0x180069245  mov     rax, [rax+18h]
0x180069249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006924e  nop
0x18006924f  mov     rcx, [rbp+800h+pv]; pv
0x180069253  test    rcx, rcx
0x180069256  jz      short loc_180069265
0x180069258  call    cs:__imp_CoTaskMemFree
0x18006925f  nop     dword ptr [rax+rax+00h]
0x180069264  nop
0x180069265  mov     rcx, [rbp+800h+var_20]
0x18006926c  xor     rcx, rsp; StackCookie
0x18006926f  call    __security_check_cookie
0x180069274  mov     rbx, [rsp+900h+arg_10]
0x18006927c  add     rsp, 8F0h
0x180069283  pop     rdi
0x180069284  pop     rsi
0x180069285  pop     rbp
0x180069286  retn
```
