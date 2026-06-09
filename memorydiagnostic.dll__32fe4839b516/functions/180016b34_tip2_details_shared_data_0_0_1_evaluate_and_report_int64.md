# tip2::details::shared_data<0,0,1>::evaluate_and_report(__int64)

- ea: `0x180016b34`
- end: `0x180016df4`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAX_J@Z`
- size: `704`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180016694`

## callees

- `0x1800026b0`
- `0x180003374`
- `0x180016b34`
- `0x18001719c`
- `0x180019660`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180016d66`
- `KERNEL32!GetModuleHandleW` at `0x180016d66`
- `KERNEL32!GetProcAddress` at `0x180016d83`
- `KERNEL32!GetProcAddress` at `0x180016d83`
- `ole32!CoTaskMemFree` at `0x180016dc4`
- `ole32!CoTaskMemFree` at `0x180016dc4`

## string_xrefs

- `0x180016d5f`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::shared_data<0,0,1>::evaluate_and_report(_DWORD *a1, __int64 a2)
{
  char v4; // cl
  unsigned __int8 v5; // al
  char v6; // dl
  unsigned int v7; // ecx
  __int64 v8; // r8
  __int64 v9; // rsi
  int v10; // ecx
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // eax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  const struct tip2::test_requirement *v18[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+30h] [rbp-D0h]
  __int128 v20; // [rsp+34h] [rbp-CCh]
  int v21; // [rsp+44h] [rbp-BCh]
  char v22; // [rsp+48h] [rbp-B8h]
  __int16 v23; // [rsp+4Ah] [rbp-B6h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  __int64 v25; // [rsp+58h] [rbp-A8h]
  __int64 v26; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+70h] [rbp-90h]
  __int64 v28; // [rsp+78h] [rbp-88h]
  __int16 v29; // [rsp+80h] [rbp-80h]
  int v30; // [rsp+8Ch] [rbp-74h]
  int v31; // [rsp+90h] [rbp-70h]
  LPVOID pv; // [rsp+A0h] [rbp-60h] BYREF
  char v33; // [rsp+A8h] [rbp-58h]
  int v34; // [rsp+A9h] [rbp-57h] BYREF
  char v35; // [rsp+ADh] [rbp-53h]
  char v36; // [rsp+AEh] [rbp-52h] BYREF
  char v37; // [rsp+8A9h] [rbp+7A9h] BYREF
  int *v38; // [rsp+8B0h] [rbp+7B0h]
  char *v39; // [rsp+8B8h] [rbp+7B8h]
  char *v40; // [rsp+8C0h] [rbp+7C0h]

  if ( !*((_BYTE *)a1 + 160)
    && tip2::details::evaluate_flags(
         (tip2::details *)(a1 + 2),
         *((const struct tip2::test_state **)a1 + 5),
         *((const struct tip2::test_requirement **)a1 + 7),
         *((const struct tip2::test_requirement **)a1 + 6),
         v18[0]) )
  {
    (***(void (__fastcall ****)(_QWORD))a1)(*(_QWORD *)a1);
  }
  v4 = *((_BYTE *)a1 + 160);
  if ( v4 != 5 )
  {
    if ( v4 )
    {
      if ( (unsigned __int8)(v4 - 2) > 1u && ((a1[5] & 0x1000) == 0 || v4 == 4) )
        goto LABEL_12;
    }
    else
    {
      *((_BYTE *)a1 + 160) = 3;
      *((_WORD *)a1 + 81) = 16394;
      *((_QWORD *)a1 + 21) = 0;
    }
    if ( (a1[16] & 0x800) != 0 )
    {
      v5 = 1;
LABEL_13:
      v6 = v5;
      v7 = v5 | 2;
      if ( (a1[5] & 0x200) == 0 )
        v7 = v5;
      pv = 0;
      v33 = 0;
      v38 = &v34;
      v40 = &v37;
      v34 = -2143256512;
      v35 = 0;
      v39 = &v36;
      if ( (a1[5] & 0x200) != 0 )
        v6 = 1;
      v8 = v7 | 4;
      if ( !v6 )
        v8 = v7;
      v9 = tip2::details::shared_data<0,0,1>::serialize_data(a1, &pv, v8);
      memset_0(v18, 0, 0x78u);
      v10 = a1[45];
      if ( v10 )
        LODWORD(v18[0]) = a1[45];
      else
        LODWORD(v18[0]) = a1[4];
      v18[1] = *((const struct tip2::test_requirement **)a1 + 3);
      v19 = a1[5];
      v20 = *((_OWORD *)a1 + 9);
      v21 = a1[16] | 0x200000;
      v22 = *((_BYTE *)a1 + 160);
      v23 = *((_WORD *)a1 + 81);
      v24 = *((_QWORD *)a1 + 21);
      v25 = a2;
      v26 = v9;
      v30 = a1[44];
      if ( v10 )
        v31 = a1[4];
      else
        v31 = 0;
      v11 = 0;
      v12 = 0;
      v13 = *((_QWORD *)a1 + 9);
      v14 = v13 + 168LL * *((_QWORD *)a1 + 11);
      if ( v13 != v14 )
      {
        do
        {
          v15 = *(_DWORD *)(v13 + 8);
          if ( (_DWORD)v11 != v15 )
            v12 = v13;
          v13 += 168;
          if ( (_DWORD)v11 == v15 )
            v15 = v11;
          v11 = v15;
        }
        while ( v13 != v14 );
        if ( v12 )
        {
          v27 = *(_DWORD *)(v12 + 8);
          v28 = *(_QWORD *)(v12 + 56);
          v29 = *(_WORD *)(v12 + 64);
        }
      }
      ProcAddress = (FARPROC)`TestReport'::`2'::s_pfnTestReport;
      if ( `TestReport'::`2'::s_pfnTestReport )
        goto LABEL_37;
      ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
      if ( !g_tip_details_kernelbaseModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
        g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "TestReport");
      `TestReport'::`2'::s_pfnTestReport = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_37:
        ((void (__fastcall *)(const struct tip2::test_requirement **, __int64, __int64, __int64))ProcAddress)(
          v18,
          v13,
          v14,
          v11);
      (*(void (__fastcall **)(_QWORD, const struct tip2::test_requirement **))(**(_QWORD **)a1 + 24LL))(
        *(_QWORD *)a1,
        v18);
      if ( pv )
        CoTaskMemFree(pv);
      return;
    }
LABEL_12:
    v5 = 0;
    goto LABEL_13;
  }
}

```

## disassembly

```asm
0x180016b34  mov     [rsp-8+arg_10], rbx
0x180016b39  push    rbp
0x180016b3a  push    rsi
0x180016b3b  push    rdi
0x180016b3c  lea     rbp, [rsp-7E0h]
0x180016b44  sub     rsp, 8E0h
0x180016b4b  mov     rax, cs:__security_cookie
0x180016b52  xor     rax, rsp
0x180016b55  mov     [rbp+7F0h+var_20], rax
0x180016b5c  mov     rdi, rdx
0x180016b5f  mov     rbx, rcx
0x180016b62  cmp     byte ptr [rcx+0A0h], 0
0x180016b69  jnz     short loc_180016B93
0x180016b6b  add     rcx, 8; this
0x180016b6f  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x180016b73  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x180016b77  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x180016b7b  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x180016b80  test    al, al
0x180016b82  jz      short loc_180016B93
0x180016b84  mov     rcx, [rbx]
0x180016b87  mov     rax, [rcx]
0x180016b8a  mov     rax, [rax]
0x180016b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b92  nop
0x180016b93  mov     cl, [rbx+0A0h]
0x180016b99  cmp     cl, 5
0x180016b9c  jz      loc_180016DD1
0x180016ba2  mov     r9d, 1
0x180016ba8  test    cl, cl
0x180016baa  jnz     short loc_180016BC6
0x180016bac  mov     byte ptr [rbx+0A0h], 3
0x180016bb3  mov     word ptr [rbx+0A2h], 400Ah
0x180016bbc  and     qword ptr [rbx+0A8h], 0
0x180016bc4  jmp     short loc_180016BDC
0x180016bc6  lea     eax, [rcx-2]
0x180016bc9  cmp     al, r9b
0x180016bcc  jbe     short loc_180016BDC
0x180016bce  test    dword ptr [rbx+14h], 1000h
0x180016bd5  jz      short loc_180016BEA
0x180016bd7  cmp     cl, 4
0x180016bda  jz      short loc_180016BEA
0x180016bdc  test    dword ptr [rbx+40h], 800h
0x180016be3  jz      short loc_180016BEA
0x180016be5  mov     al, r9b
0x180016be8  jmp     short loc_180016BEC
0x180016bea  xor     al, al
0x180016bec  movzx   edx, al
0x180016bef  mov     ecx, edx
0x180016bf1  or      ecx, 2
0x180016bf4  test    dword ptr [rbx+14h], 200h
0x180016bfb  cmovz   ecx, edx
0x180016bfe  and     [rbp+7F0h+pv], 0
0x180016c03  mov     [rbp+7F0h+var_848], 0
0x180016c07  lea     r8, [rbp+7F0h+var_847]
0x180016c0b  mov     [rbp+7F0h+var_40], r8
0x180016c12  lea     r8, [rbp+7F0h+var_47]
0x180016c19  mov     [rbp+7F0h+var_30], r8
0x180016c20  mov     [rbp+7F0h+var_847], 80408040h
0x180016c27  mov     [rbp+7F0h+var_843], 0
0x180016c2b  lea     r8, [rbp+7F0h+var_842]
0x180016c2f  mov     [rbp+7F0h+var_38], r8
0x180016c36  test    dword ptr [rbx+14h], 200h
0x180016c3d  cmovnz  edx, r9d
0x180016c41  mov     r8d, ecx
0x180016c44  or      r8d, 4
0x180016c48  test    dl, dl
0x180016c4a  cmovz   r8d, ecx
0x180016c4e  lea     rdx, [rbp+7F0h+pv]
0x180016c52  mov     rcx, rbx
0x180016c55  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180016c5a  mov     rsi, rax
0x180016c5d  xor     edx, edx; Val
0x180016c5f  lea     r8d, [rdx+78h]; Size
0x180016c63  lea     rcx, [rsp+8F0h+var_8D0]; void *
0x180016c68  call    memset_0
0x180016c6d  mov     ecx, [rbx+0B4h]
0x180016c73  test    ecx, ecx
0x180016c75  jz      short loc_180016C7D
0x180016c77  mov     [rsp+8F0h+var_8D0], ecx
0x180016c7b  jmp     short loc_180016C84
0x180016c7d  mov     eax, [rbx+10h]
0x180016c80  mov     [rsp+8F0h+var_8D0], eax
0x180016c84  mov     rax, [rbx+18h]
0x180016c88  mov     [rsp+8F0h+var_8C8], rax
0x180016c8d  mov     eax, [rbx+14h]
0x180016c90  mov     [rsp+8F0h+var_8C0], eax
0x180016c94  movups  xmm0, xmmword ptr [rbx+90h]
0x180016c9b  movdqu  [rsp+8F0h+var_8BC], xmm0
0x180016ca1  mov     eax, [rbx+40h]
0x180016ca4  bts     eax, 15h
0x180016ca8  mov     [rsp+8F0h+var_8AC], eax
0x180016cac  mov     al, [rbx+0A0h]
0x180016cb2  mov     [rsp+8F0h+var_8A8], al
0x180016cb6  movzx   eax, word ptr [rbx+0A2h]
0x180016cbd  mov     [rsp+8F0h+var_8A6], ax
0x180016cc2  mov     rax, [rbx+0A8h]
0x180016cc9  mov     [rsp+8F0h+var_8A0], rax
0x180016cce  mov     [rsp+8F0h+var_898], rdi
0x180016cd3  mov     [rsp+8F0h+var_888], rsi
0x180016cd8  mov     eax, [rbx+0B0h]
0x180016cde  mov     [rbp+7F0h+var_864], eax
0x180016ce1  test    ecx, ecx
0x180016ce3  jz      short loc_180016CED
0x180016ce5  mov     eax, [rbx+10h]
0x180016ce8  mov     [rbp+7F0h+var_860], eax
0x180016ceb  jmp     short loc_180016CF1
0x180016ced  and     [rbp+7F0h+var_860], 0
0x180016cf1  xor     r9d, r9d
0x180016cf4  xor     ecx, ecx
0x180016cf6  mov     rdx, [rbx+48h]
0x180016cfa  imul    r8, [rbx+58h], 0A8h
0x180016d02  add     r8, rdx
0x180016d05  cmp     rdx, r8
0x180016d08  jz      short loc_180016D47
0x180016d0a  mov     eax, [rdx+8]
0x180016d0d  cmp     r9d, eax
0x180016d10  cmovnz  rcx, rdx
0x180016d14  add     rdx, 0A8h
0x180016d1b  cmp     r9d, eax
0x180016d1e  cmovz   eax, r9d
0x180016d22  mov     r9d, eax
0x180016d25  cmp     rdx, r8
0x180016d28  jnz     short loc_180016D0A
0x180016d2a  test    rcx, rcx
0x180016d2d  jz      short loc_180016D47
0x180016d2f  mov     eax, [rcx+8]
0x180016d32  mov     [rsp+8F0h+var_880], eax
0x180016d36  mov     rax, [rcx+38h]
0x180016d3a  mov     [rsp+8F0h+var_878], rax
0x180016d3f  movzx   eax, word ptr [rcx+40h]
0x180016d43  mov     [rbp+7F0h+var_870], ax
0x180016d47  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180016d4e  test    rax, rax
0x180016d51  jnz     short loc_180016D9B
0x180016d53  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180016d5a  test    rax, rax
0x180016d5d  jnz     short loc_180016D79
0x180016d5f  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180016d66  call    cs:__imp_GetModuleHandleW
0x180016d6d  nop     dword ptr [rax+rax+00h]
0x180016d72  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180016d79  lea     rdx, aTestreport; "TestReport"
0x180016d80  mov     rcx, rax; hModule
0x180016d83  call    cs:__imp_GetProcAddress
0x180016d8a  nop     dword ptr [rax+rax+00h]
0x180016d8f  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x180016d96  test    rax, rax
0x180016d99  jz      short loc_180016DA6
0x180016d9b  lea     rcx, [rsp+8F0h+var_8D0]
0x180016da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016da5  nop
0x180016da6  mov     rcx, [rbx]
0x180016da9  mov     rax, [rcx]
0x180016dac  lea     rdx, [rsp+8F0h+var_8D0]
0x180016db1  mov     rax, [rax+18h]
0x180016db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dba  nop
0x180016dbb  mov     rcx, [rbp+7F0h+pv]; pv
0x180016dbf  test    rcx, rcx
0x180016dc2  jz      short loc_180016DD1
0x180016dc4  call    cs:__imp_CoTaskMemFree
0x180016dcb  nop     dword ptr [rax+rax+00h]
0x180016dd0  nop
0x180016dd1  mov     rcx, [rbp+7F0h+var_20]
0x180016dd8  xor     rcx, rsp; StackCookie
0x180016ddb  call    __security_check_cookie
0x180016de0  mov     rbx, [rsp+8F0h+arg_10]
0x180016de8  add     rsp, 8E0h
0x180016def  pop     rdi
0x180016df0  pop     rsi
0x180016df1  pop     rbp
0x180016df2  retn
```
