# tip2::details::shared_data<0,0,1>::evaluate_and_report(__int64)

- ea: `0x180015f9c`
- end: `0x180016253`
- name: `?evaluate_and_report@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAX_J@Z`
- size: `695`
- prototype: `void __fastcall(_DWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180015928`

## callees

- `0x180002e50`
- `0x180003940`
- `0x180015f9c`
- `0x1800165e8`
- `0x180018680`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800161d8`
- `KERNEL32!GetModuleHandleW` at `0x1800161d8`
- `KERNEL32!GetProcAddress` at `0x1800161ef`
- `KERNEL32!GetProcAddress` at `0x1800161ef`
- `ole32!CoTaskMemFree` at `0x18001622a`
- `ole32!CoTaskMemFree` at `0x18001622a`

## string_xrefs

- `0x1800161d1`: `kernelbase.dll`

## pseudocode

```c
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
      v11 = tip2::details::shared_data<0,0,1>::serialize_data(a1, &pv, v10, 1);
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
0x180015f9c  mov     [rsp-8+arg_10], rbx
0x180015fa1  push    rbp
0x180015fa2  push    rsi
0x180015fa3  push    rdi
0x180015fa4  lea     rbp, [rsp-7E0h]
0x180015fac  sub     rsp, 8E0h
0x180015fb3  mov     rax, cs:__security_cookie
0x180015fba  xor     rax, rsp
0x180015fbd  mov     [rbp+7F0h+var_20], rax
0x180015fc4  mov     rdi, rdx
0x180015fc7  mov     rbx, rcx
0x180015fca  add     rcx, 8; this
0x180015fce  cmp     byte ptr [rcx+98h], 0
0x180015fd5  jnz     short loc_180015FFB
0x180015fd7  mov     r9, [rbx+30h]; struct tip2::test_requirement *
0x180015fdb  mov     r8, [rbx+38h]; struct tip2::test_requirement *
0x180015fdf  mov     rdx, [rbx+28h]; struct tip2::test_state *
0x180015fe3  call    ?evaluate_flags@details@tip2@@YA_NAEBVtest_state@2@PEBUtest_requirement@2@11@Z; tip2::details::evaluate_flags(tip2::test_state const &,tip2::test_requirement const *,tip2::test_requirement const *,tip2::test_requirement const *)
0x180015fe8  test    al, al
0x180015fea  jz      short loc_180015FFB
0x180015fec  mov     rcx, [rbx]
0x180015fef  mov     rax, [rcx]
0x180015ff2  mov     rax, [rax]
0x180015ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ffa  nop
0x180015ffb  mov     cl, [rbx+0A0h]
0x180016001  cmp     cl, 5
0x180016004  jz      loc_180016231
0x18001600a  mov     r9d, 1
0x180016010  test    cl, cl
0x180016012  jnz     short loc_180016031
0x180016014  mov     byte ptr [rbx+0A0h], 3
0x18001601b  mov     word ptr [rbx+0A2h], 400Ah
0x180016024  mov     qword ptr [rbx+0A8h], 0
0x18001602f  jmp     short loc_180016047
0x180016031  lea     eax, [rcx-2]
0x180016034  cmp     al, r9b
0x180016037  jbe     short loc_180016047
0x180016039  test    dword ptr [rbx+14h], 1000h
0x180016040  jz      short loc_180016055
0x180016042  cmp     cl, 4
0x180016045  jz      short loc_180016055
0x180016047  test    dword ptr [rbx+40h], 800h
0x18001604e  jz      short loc_180016055
0x180016050  mov     r8b, r9b
0x180016053  jmp     short loc_180016058
0x180016055  xor     r8b, r8b
0x180016058  movzx   eax, r8b
0x18001605c  mov     edx, eax
0x18001605e  or      edx, 2
0x180016061  test    dword ptr [rbx+14h], 200h
0x180016068  cmovz   edx, eax
0x18001606b  mov     [rbp+7F0h+pv], 0
0x180016073  mov     [rbp+7F0h+var_848], 0
0x180016077  lea     rax, [rbp+7F0h+var_847]
0x18001607b  mov     [rbp+7F0h+var_40], rax
0x180016082  lea     rax, [rbp+7F0h+var_47]
0x180016089  mov     [rbp+7F0h+var_30], rax
0x180016090  mov     [rbp+7F0h+var_847], 80408040h
0x180016097  mov     [rbp+7F0h+var_843], 0
0x18001609b  lea     rax, [rbp+7F0h+var_842]
0x18001609f  mov     [rbp+7F0h+var_38], rax
0x1800160a6  movzx   eax, r8b
0x1800160aa  cmovnz  eax, r9d
0x1800160ae  mov     r8d, edx
0x1800160b1  or      r8d, 4
0x1800160b5  test    al, al
0x1800160b7  cmovz   r8d, edx
0x1800160bb  lea     rdx, [rbp+7F0h+pv]
0x1800160bf  mov     rcx, rbx
0x1800160c2  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800160c7  mov     rsi, rax
0x1800160ca  xor     edx, edx; Val
0x1800160cc  lea     r8d, [rdx+78h]; Size
0x1800160d0  lea     rcx, [rsp+8F0h+var_8D0]; void *
0x1800160d5  call    memset_0
0x1800160da  mov     edx, [rbx+0B4h]
0x1800160e0  lea     rcx, [rbx+10h]
0x1800160e4  test    edx, edx
0x1800160e6  jz      short loc_1800160EE
0x1800160e8  mov     [rsp+8F0h+var_8D0], edx
0x1800160ec  jmp     short loc_1800160F4
0x1800160ee  mov     eax, [rcx]
0x1800160f0  mov     [rsp+8F0h+var_8D0], eax
0x1800160f4  mov     rax, [rbx+18h]
0x1800160f8  mov     [rsp+8F0h+var_8C8], rax
0x1800160fd  mov     eax, [rbx+14h]
0x180016100  mov     [rsp+8F0h+var_8C0], eax
0x180016104  movups  xmm0, xmmword ptr [rbx+90h]
0x18001610b  movdqu  [rsp+8F0h+var_8BC], xmm0
0x180016111  mov     eax, [rbx+40h]
0x180016114  bts     eax, 15h
0x180016118  mov     [rsp+8F0h+var_8AC], eax
0x18001611c  mov     al, [rbx+0A0h]
0x180016122  mov     [rsp+8F0h+var_8A8], al
0x180016126  movzx   eax, word ptr [rbx+0A2h]
0x18001612d  mov     [rsp+8F0h+var_8A6], ax
0x180016132  mov     rax, [rbx+0A8h]
0x180016139  mov     [rsp+8F0h+var_8A0], rax
0x18001613e  mov     [rsp+8F0h+var_898], rdi
0x180016143  mov     [rsp+8F0h+var_888], rsi
0x180016148  mov     eax, [rbx+0B0h]
0x18001614e  mov     [rbp+7F0h+var_864], eax
0x180016151  test    edx, edx
0x180016153  jz      short loc_18001615C
0x180016155  mov     eax, [rcx]
0x180016157  mov     [rbp+7F0h+var_860], eax
0x18001615a  jmp     short loc_180016163
0x18001615c  mov     [rbp+7F0h+var_860], 0
0x180016163  xor     r9d, r9d
0x180016166  xor     ecx, ecx
0x180016168  mov     rdx, [rbx+48h]
0x18001616c  imul    r8, [rbx+58h], 0A8h
0x180016174  add     r8, rdx
0x180016177  cmp     rdx, r8
0x18001617a  jz      short loc_1800161B9
0x18001617c  mov     eax, [rdx+8]
0x18001617f  cmp     r9d, eax
0x180016182  cmovnz  rcx, rdx
0x180016186  add     rdx, 0A8h
0x18001618d  cmp     r9d, eax
0x180016190  cmovz   eax, r9d
0x180016194  mov     r9d, eax
0x180016197  cmp     rdx, r8
0x18001619a  jnz     short loc_18001617C
0x18001619c  test    rcx, rcx
0x18001619f  jz      short loc_1800161B9
0x1800161a1  mov     eax, [rcx+8]
0x1800161a4  mov     [rsp+8F0h+var_880], eax
0x1800161a8  mov     rax, [rcx+38h]
0x1800161ac  mov     [rsp+8F0h+var_878], rax
0x1800161b1  movzx   eax, word ptr [rcx+40h]
0x1800161b5  mov     [rbp+7F0h+var_870], ax
0x1800161b9  mov     rax, cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800161c0  test    rax, rax
0x1800161c3  jnz     short loc_180016201
0x1800161c5  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800161cc  test    rax, rax
0x1800161cf  jnz     short loc_1800161E5
0x1800161d1  lea     rcx, ModuleName; "kernelbase.dll"
0x1800161d8  call    cs:__imp_GetModuleHandleW
0x1800161de  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800161e5  lea     rdx, aTestreport; "TestReport"
0x1800161ec  mov     rcx, rax; hModule
0x1800161ef  call    cs:__imp_GetProcAddress
0x1800161f5  mov     cs:?s_pfnTestReport@?1??TestReport@@9@4P6AXPEAUTipReportingInfo@@@ZEA, rax; void (*`TestReport'::`2'::s_pfnTestReport)(TipReportingInfo *)
0x1800161fc  test    rax, rax
0x1800161ff  jz      short loc_18001620C
0x180016201  lea     rcx, [rsp+8F0h+var_8D0]
0x180016206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001620b  nop
0x18001620c  mov     rcx, [rbx]
0x18001620f  mov     rax, [rcx]
0x180016212  lea     rdx, [rsp+8F0h+var_8D0]
0x180016217  mov     rax, [rax+18h]
0x18001621b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016220  nop
0x180016221  mov     rcx, [rbp+7F0h+pv]; pv
0x180016225  test    rcx, rcx
0x180016228  jz      short loc_180016231
0x18001622a  call    cs:__imp_CoTaskMemFree
0x180016230  nop
0x180016231  mov     rcx, [rbp+7F0h+var_20]
0x180016238  xor     rcx, rsp; StackCookie
0x18001623b  call    __security_check_cookie
0x180016240  mov     rbx, [rsp+8F0h+arg_10]
0x180016248  add     rsp, 8E0h
0x18001624f  pop     rdi
0x180016250  pop     rsi
0x180016251  pop     rbp
0x180016252  retn
```
