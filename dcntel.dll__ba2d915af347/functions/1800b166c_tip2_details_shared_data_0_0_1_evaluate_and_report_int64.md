# tip2::details::shared_data<0,0,1>::evaluate_and_report(__int64)

- ea: `0x1800b166c`
- end: `0x1800b1923`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAX_J@Z`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b1418`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x1800b166c`
- `0x1800b192c`
- `0x1800b33c0`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b18bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b18bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b18a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b18a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b18fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b18fa`

## string_xrefs

- `0x1800b18a1`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::shared_data<0,0,1>::evaluate_and_report(_DWORD *a1, __int64 a2)
{
  tip2::details *v4; // rcx
  char v5; // cl
  unsigned __int8 v6; // r8
  unsigned int v7; // edx
  bool v8; // zf
  char v9; // al
  __int64 v10; // r8
  __int64 v11; // rsi
  int v12; // edx
  _DWORD *v13; // rcx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // eax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  const struct tip2::test_requirement *v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+30h] [rbp-D0h]
  __int128 v23; // [rsp+34h] [rbp-CCh]
  int v24; // [rsp+44h] [rbp-BCh]
  char v25; // [rsp+48h] [rbp-B8h]
  __int16 v26; // [rsp+4Ah] [rbp-B6h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+78h] [rbp-88h]
  __int16 v32; // [rsp+80h] [rbp-80h]
  int v33; // [rsp+8Ch] [rbp-74h]
  int v34; // [rsp+90h] [rbp-70h]
  LPVOID pv; // [rsp+A0h] [rbp-60h] BYREF
  char v36; // [rsp+A8h] [rbp-58h]
  int v37; // [rsp+A9h] [rbp-57h] BYREF
  char v38; // [rsp+ADh] [rbp-53h]
  char v39; // [rsp+AEh] [rbp-52h] BYREF
  char v40; // [rsp+8A9h] [rbp+7A9h] BYREF
  int *v41; // [rsp+8B0h] [rbp+7B0h]
  char *v42; // [rsp+8B8h] [rbp+7B8h]
  char *v43; // [rsp+8C0h] [rbp+7C0h]

  v4 = (tip2::details *)(a1 + 2);
  if ( !*((_BYTE *)v4 + 152)
    && tip2::details::evaluate_flags(
         v4,
         *((const struct tip2::test_state **)a1 + 5),
         *((const struct tip2::test_requirement **)a1 + 7),
         *((const struct tip2::test_requirement **)a1 + 6),
         v21[0]) )
  {
    (***(void (__fastcall ****)(_QWORD))a1)(*(_QWORD *)a1);
  }
  v5 = *((_BYTE *)a1 + 160);
  if ( v5 != 5 )
  {
    if ( v5 )
    {
      if ( (unsigned __int8)(v5 - 2) > 1u && ((a1[5] & 0x1000) == 0 || v5 == 4) )
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
      v6 = 1;
LABEL_13:
      v7 = v6 | 2;
      v8 = (a1[5] & 0x200) == 0;
      if ( (a1[5] & 0x200) == 0 )
        v7 = v6;
      pv = 0;
      v36 = 0;
      v41 = &v37;
      v43 = &v40;
      v37 = -2143256512;
      v38 = 0;
      v42 = &v39;
      v9 = v6;
      if ( !v8 )
        v9 = 1;
      v10 = v7 | 4;
      if ( !v9 )
        v10 = v7;
      v11 = tip2::details::shared_data<0,0,1>::serialize_data(a1, &pv, v10);
      memset_0(v21, 0, 0x78u);
      v12 = a1[45];
      v13 = a1 + 4;
      if ( v12 )
        LODWORD(v21[0]) = a1[45];
      else
        LODWORD(v21[0]) = *v13;
      v21[1] = *((const struct tip2::test_requirement **)a1 + 3);
      v22 = a1[5];
      v23 = *((_OWORD *)a1 + 9);
      v24 = a1[16] | 0x200000;
      v25 = *((_BYTE *)a1 + 160);
      v26 = *((_WORD *)a1 + 81);
      v27 = *((_QWORD *)a1 + 21);
      v28 = a2;
      v29 = v11;
      v33 = a1[44];
      if ( v12 )
        v34 = *v13;
      else
        v34 = 0;
      v14 = 0;
      v15 = 0;
      v16 = *((_QWORD *)a1 + 9);
      v17 = v16 + 168LL * *((_QWORD *)a1 + 11);
      if ( v16 != v17 )
      {
        do
        {
          v18 = *(_DWORD *)(v16 + 8);
          if ( (_DWORD)v14 != v18 )
            v15 = v16;
          v16 += 168;
          if ( (_DWORD)v14 == v18 )
            v18 = v14;
          v14 = v18;
        }
        while ( v16 != v17 );
        if ( v15 )
        {
          v30 = *(_DWORD *)(v15 + 8);
          v31 = *(_QWORD *)(v15 + 56);
          v32 = *(_WORD *)(v15 + 64);
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
          v21,
          v16,
          v17,
          v14);
      (*(void (__fastcall **)(_QWORD, const struct tip2::test_requirement **))(**(_QWORD **)a1 + 24LL))(
        *(_QWORD *)a1,
        v21);
      if ( pv )
        CoTaskMemFree(pv);
      return;
    }
LABEL_12:
    v6 = 0;
    goto LABEL_13;
  }
}

```

## disassembly

```asm
0x1800b166c  mov     [rsp-8+arg_10], rbx
0x1800b1671  push    rbp
0x1800b1672  push    rsi
0x1800b1673  push    rdi
0x1800b1674  lea     rbp, [rsp-7E0h]
0x1800b167c  sub     rsp, 8E0h
0x1800b1683  mov     rax, cs:__security_cookie
0x1800b168a  xor     rax, rsp
0x1800b168d  mov     [rbp+7F0h+var_20], rax
0x1800b1694  mov     rdi, rdx
0x1800b1697  mov     rbx, rcx
0x1800b169a  add     rcx, 8; this
0x1800b169e  cmp     byte ptr [rcx+98h], 0
0x1800b16a5  jnz     short loc_1800B16CB
0x1800b16a7  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x1800b16ab  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x1800b16af  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x1800b16b3  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x1800b16b8  test    al, al
0x1800b16ba  jz      short loc_1800B16CB
0x1800b16bc  mov     rcx, [rbx]
0x1800b16bf  mov     rax, [rcx]
0x1800b16c2  mov     rax, [rax]
0x1800b16c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b16ca  nop
0x1800b16cb  mov     cl, [rbx+0A0h]
0x1800b16d1  cmp     cl, 5
0x1800b16d4  jz      loc_1800B1901
0x1800b16da  mov     r9d, 1
0x1800b16e0  test    cl, cl
0x1800b16e2  jnz     short loc_1800B1701
0x1800b16e4  mov     byte ptr [rbx+0A0h], 3
0x1800b16eb  mov     word ptr [rbx+0A2h], 400Ah
0x1800b16f4  mov     qword ptr [rbx+0A8h], 0
0x1800b16ff  jmp     short loc_1800B1717
0x1800b1701  lea     eax, [rcx-2]
0x1800b1704  cmp     al, r9b
0x1800b1707  jbe     short loc_1800B1717
0x1800b1709  test    dword ptr [rbx+14h], 1000h
0x1800b1710  jz      short loc_1800B1725
0x1800b1712  cmp     cl, 4
0x1800b1715  jz      short loc_1800B1725
0x1800b1717  test    dword ptr [rbx+40h], 800h
0x1800b171e  jz      short loc_1800B1725
0x1800b1720  mov     r8b, r9b
0x1800b1723  jmp     short loc_1800B1728
0x1800b1725  xor     r8b, r8b
0x1800b1728  movzx   eax, r8b
0x1800b172c  mov     edx, eax
0x1800b172e  or      edx, 2
0x1800b1731  test    dword ptr [rbx+14h], 200h
0x1800b1738  cmovz   edx, eax
0x1800b173b  mov     [rbp+7F0h+pv], 0
0x1800b1743  mov     [rbp+7F0h+var_848], 0
0x1800b1747  lea     rax, [rbp+7F0h+var_847]
0x1800b174b  mov     [rbp+7F0h+var_40], rax
0x1800b1752  lea     rax, [rbp+7F0h+var_47]
0x1800b1759  mov     [rbp+7F0h+var_30], rax
0x1800b1760  mov     [rbp+7F0h+var_847], 80408040h
0x1800b1767  mov     [rbp+7F0h+var_843], 0
0x1800b176b  lea     rax, [rbp+7F0h+var_842]
0x1800b176f  mov     [rbp+7F0h+var_38], rax
0x1800b1776  movzx   eax, r8b
0x1800b177a  cmovnz  eax, r9d
0x1800b177e  mov     r8d, edx
0x1800b1781  or      r8d, 4
0x1800b1785  test    al, al
0x1800b1787  cmovz   r8d, edx
0x1800b178b  lea     rdx, [rbp+7F0h+pv]
0x1800b178f  mov     rcx, rbx
0x1800b1792  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800b1797  mov     rsi, rax
0x1800b179a  xor     edx, edx; Val
0x1800b179c  lea     r8d, [rdx+78h]; Size
0x1800b17a0  lea     rcx, [rsp+8F0h+var_8D0]; void *
0x1800b17a5  call    memset_0
0x1800b17aa  mov     edx, [rbx+0B4h]
0x1800b17b0  lea     rcx, [rbx+10h]
0x1800b17b4  test    edx, edx
0x1800b17b6  jz      short loc_1800B17BE
0x1800b17b8  mov     [rsp+8F0h+var_8D0], edx
0x1800b17bc  jmp     short loc_1800B17C4
0x1800b17be  mov     eax, [rcx]
0x1800b17c0  mov     [rsp+8F0h+var_8D0], eax
0x1800b17c4  mov     rax, [rbx+18h]
0x1800b17c8  mov     [rsp+8F0h+var_8C8], rax
0x1800b17cd  mov     eax, [rbx+14h]
0x1800b17d0  mov     [rsp+8F0h+var_8C0], eax
0x1800b17d4  movups  xmm0, xmmword ptr [rbx+90h]
0x1800b17db  movdqu  [rsp+8F0h+var_8BC], xmm0
0x1800b17e1  mov     eax, [rbx+40h]
0x1800b17e4  bts     eax, 15h
0x1800b17e8  mov     [rsp+8F0h+var_8AC], eax
0x1800b17ec  mov     al, [rbx+0A0h]
0x1800b17f2  mov     [rsp+8F0h+var_8A8], al
0x1800b17f6  movzx   eax, word ptr [rbx+0A2h]
0x1800b17fd  mov     [rsp+8F0h+var_8A6], ax
0x1800b1802  mov     rax, [rbx+0A8h]
0x1800b1809  mov     [rsp+8F0h+var_8A0], rax
0x1800b180e  mov     [rsp+8F0h+var_898], rdi
0x1800b1813  mov     [rsp+8F0h+var_888], rsi
0x1800b1818  mov     eax, [rbx+0B0h]
0x1800b181e  mov     [rbp+7F0h+var_864], eax
0x1800b1821  test    edx, edx
0x1800b1823  jz      short loc_1800B182C
0x1800b1825  mov     eax, [rcx]
0x1800b1827  mov     [rbp+7F0h+var_860], eax
0x1800b182a  jmp     short loc_1800B1833
0x1800b182c  mov     [rbp+7F0h+var_860], 0
0x1800b1833  xor     r9d, r9d
0x1800b1836  xor     ecx, ecx
0x1800b1838  mov     rdx, [rbx+48h]
0x1800b183c  imul    r8, [rbx+58h], 0A8h
0x1800b1844  add     r8, rdx
0x1800b1847  cmp     rdx, r8
0x1800b184a  jz      short loc_1800B1889
0x1800b184c  mov     eax, [rdx+8]
0x1800b184f  cmp     r9d, eax
0x1800b1852  cmovnz  rcx, rdx
0x1800b1856  add     rdx, 0A8h
0x1800b185d  cmp     r9d, eax
0x1800b1860  cmovz   eax, r9d
0x1800b1864  mov     r9d, eax
0x1800b1867  cmp     rdx, r8
0x1800b186a  jnz     short loc_1800B184C
0x1800b186c  test    rcx, rcx
0x1800b186f  jz      short loc_1800B1889
0x1800b1871  mov     eax, [rcx+8]
0x1800b1874  mov     [rsp+8F0h+var_880], eax
0x1800b1878  mov     rax, [rcx+38h]
0x1800b187c  mov     [rsp+8F0h+var_878], rax
0x1800b1881  movzx   eax, word ptr [rcx+40h]
0x1800b1885  mov     [rbp+7F0h+var_870], ax
0x1800b1889  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800b1890  test    rax, rax
0x1800b1893  jnz     short loc_1800B18D1
0x1800b1895  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800b189c  test    rax, rax
0x1800b189f  jnz     short loc_1800B18B5
0x1800b18a1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800b18a8  call    cs:__imp_GetModuleHandleW
0x1800b18ae  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800b18b5  lea     rdx, aTestreport; "TestReport"
0x1800b18bc  mov     rcx, rax; hModule
0x1800b18bf  call    cs:__imp_GetProcAddress
0x1800b18c5  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800b18cc  test    rax, rax
0x1800b18cf  jz      short loc_1800B18DC
0x1800b18d1  lea     rcx, [rsp+8F0h+var_8D0]
0x1800b18d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b18db  nop
0x1800b18dc  mov     rcx, [rbx]
0x1800b18df  mov     rax, [rcx]
0x1800b18e2  lea     rdx, [rsp+8F0h+var_8D0]
0x1800b18e7  mov     rax, [rax+18h]
0x1800b18eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b18f0  nop
0x1800b18f1  mov     rcx, [rbp+7F0h+pv]; pv
0x1800b18f5  test    rcx, rcx
0x1800b18f8  jz      short loc_1800B1901
0x1800b18fa  call    cs:__imp_CoTaskMemFree
0x1800b1900  nop
0x1800b1901  mov     rcx, [rbp+7F0h+var_20]
0x1800b1908  xor     rcx, rsp; StackCookie
0x1800b190b  call    __security_check_cookie
0x1800b1910  mov     rbx, [rsp+8F0h+arg_10]
0x1800b1918  add     rsp, 8E0h
0x1800b191f  pop     rdi
0x1800b1920  pop     rsi
0x1800b1921  pop     rbp
0x1800b1922  retn
```
