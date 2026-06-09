# ResolveNetAliasFromRegistry<tagDBC>(tagDBC *,CDlgATTRs &,int)

- ea: `0x1004e45cc`
- end: `0x1004e4c3a`
- name: `??$ResolveNetAliasFromRegistry@UtagDBC@@@@YAJPEAUtagDBC@@AEAVCDlgATTRs@@H@Z`
- size: `1646`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1004e4c40`
- `0x1004e7ee8`
- `0x1004e889c`

## callees

- `0x100468e74`
- `0x10046cf68`
- `0x10046d140`
- `0x1004e45cc`
- `0x1004e88a8`
- `0x100545d74`
- `0x100546a24`
- `0x100548140`
- `0x100548210`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e49a2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e4ac7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e49a2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e4ac7`

## pseudocode

```c
__int64 __fastcall ResolveNetAliasFromRegistry<tagDBC>(__int64 a1, CDlgATTRs *a2, int a3)
{
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // r14
  int NetLibAddr; // eax
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned __int16 *v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  _WORD *v16; // rcx
  char *v17; // r8
  __int64 v18; // rdx
  __int16 v19; // ax
  _WORD *v20; // rax
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  int v24; // eax
  unsigned __int16 *v25; // r8
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  const wchar_t *v30; // rcx
  int v31; // eax
  int v32; // eax
  int v33; // eax
  __int64 v34; // rdx
  const wchar_t *v35; // rcx
  int v36; // eax
  int v37; // eax
  char v38; // al
  int v39; // eax
  _WORD *v40; // rdx
  _WORD *v41; // rsi
  _WORD *v42; // rax
  unsigned __int16 *v44; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v45; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v46[1056]; // [rsp+40h] [rbp-C0h] BYREF

  v45 = 0;
  v44 = 0;
  v6 = 0;
  memset_0(v46, 0, 0x416u);
  v8 = 261;
  if ( (unsigned int)IsEmbeddedSNAC() )
    goto LABEL_46;
  if ( !a1 || (*(_BYTE *)(*((_QWORD *)a2 + 1) + 312LL) & 1) != 0 && !a3 )
    goto LABEL_28;
  NetLibAddr = GetNetLibAddr(a2, 18, v46, 523, &v45, &v44);
  v6 = NetLibAddr;
  if ( NetLibAddr < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v10 = (unsigned int)NetLibAddr;
      v11 = 529417;
LABEL_96:
      _mm_lfence();
      bidTraceHR(0, v11, v10, v7);
      return v6;
    }
    return v6;
  }
  if ( NetLibAddr )
  {
LABEL_28:
    v22 = *((_QWORD *)a2 + 1);
    if ( (*(_BYTE *)(v22 + 312) & 1) == 0 && (*(_BYTE *)(v22 + 336) & 1) == 0 || a3 )
    {
      v23 = GetNetLibAddr(a2, 5, v46, 523, &v45, &v44);
      v6 = v23;
      if ( v23 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v10 = (unsigned int)v23;
          v11 = 576521;
          goto LABEL_96;
        }
        return v6;
      }
      _mm_lfence();
      if ( v23 )
      {
        if ( (*(_BYTE *)(*((_QWORD *)a2 + 1) + 336LL) & 1) == 0 )
        {
          _mm_lfence();
          v31 = CDlgATTRs::CopyATTRValue(a2, 14, 5);
          v6 = v31;
          if ( v31 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              v10 = (unsigned int)v31;
              v11 = 619529;
              goto LABEL_96;
            }
            return v6;
          }
        }
        _mm_lfence();
        if ( (*(_BYTE *)(*((_QWORD *)a2 + 1) + 312LL) & 1) == 0 )
        {
          _mm_lfence();
          v32 = CDlgATTRs::SetATTRValue(a2, 13, L"DBNETLIB");
          v6 = v32;
          if ( v32 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              v10 = (unsigned int)v32;
              v11 = 625673;
              goto LABEL_96;
            }
            return v6;
          }
        }
      }
      else
      {
        v24 = CDlgATTRs::SetATTRValue(a2, 13, v45);
        v6 = v24;
        if ( v24 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v10 = (unsigned int)v24;
            v11 = 583689;
            goto LABEL_96;
          }
          return v6;
        }
        _mm_lfence();
        v25 = v44;
        *(_WORD *)(*((_QWORD *)a2 + 1) + 312LL) |= 1u;
        *(_WORD *)(*((_QWORD *)a2 + 1) + 312LL) |= 8u;
        *(_WORD *)(*((_QWORD *)a2 + 1) + 312LL) &= ~2u;
        *(_WORD *)(*((_QWORD *)a2 + 1) + 312LL) &= ~0x20u;
        v26 = CDlgATTRs::SetATTRValue(a2, 14, v25);
        v6 = v26;
        if ( v26 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v10 = (unsigned int)v26;
            v11 = 591881;
            goto LABEL_96;
          }
          return v6;
        }
        _mm_lfence();
        *(_WORD *)(*((_QWORD *)a2 + 1) + 336LL) |= 1u;
        *(_WORD *)(*((_QWORD *)a2 + 1) + 336LL) |= 8u;
        *(_WORD *)(*((_QWORD *)a2 + 1) + 336LL) &= ~2u;
        *(_WORD *)(*((_QWORD *)a2 + 1) + 336LL) &= ~0x20u;
        if ( a1 )
        {
          _mm_lfence();
          *(_BYTE *)(a1 + 9174) &= ~4u;
          v27 = MapNetworkPrefixEnum(*(_QWORD *)(*((_QWORD *)a2 + 1) + 320LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL));
          if ( v27 == 4 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              v14 = 606217;
              goto LABEL_12;
            }
            return (unsigned int)-2147418113;
          }
          *(_DWORD *)(a1 + 9160) = v27;
        }
      }
    }
LABEL_46:
    v28 = *((_QWORD *)a2 + 1);
    v29 = *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL);
    v30 = (const wchar_t *)(v29 + *(_QWORD *)(v28 + 344));
    if ( *v30 )
    {
      if ( (*(_BYTE *)(v28 + 336) & 0x20) != 0 || _wcsicmp(v30, (const wchar_t *)(v29 + *(_QWORD *)(v28 + 128))) )
      {
LABEL_66:
        v34 = *((_QWORD *)a2 + 1);
        v35 = (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + *(_QWORD *)(v34 + 320));
        if ( *v35 )
        {
          if ( (*(_BYTE *)(v34 + 312) & 0x20) != 0 || _wcsicmp(v35, L"DBNETLIB") )
            goto LABEL_75;
        }
        else
        {
          v36 = CDlgATTRs::SetATTRValue(a2, 13, L"DBNETLIB");
          v6 = v36;
          if ( v36 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              v10 = (unsigned int)v36;
              v11 = 672777;
              goto LABEL_96;
            }
            return v6;
          }
          _mm_lfence();
        }
        *(_WORD *)(*((_QWORD *)a2 + 1) + 312LL) |= 0x20u;
LABEL_75:
        if ( !a1 )
          return v6;
        if ( (*(_BYTE *)(a1 + 9174) & 4) != 0 )
        {
          v37 = MapNetworkPrefixEnum(*(_QWORD *)(*((_QWORD *)a2 + 1) + 320LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL));
          if ( v37 == 4 )
          {
            if ( (bidGblFlags & 2) == 0 )
              return (unsigned int)-2147467259;
            v14 = 688137;
            v15 = 2147500037LL;
            return (unsigned int)bidTraceHR(0, v14, v15, v7);
          }
          *(_DWORD *)(a1 + 9160) = v37;
        }
        v38 = *(_BYTE *)(a1 + 9174);
        if ( (v38 & 8) != 0 )
          return v6;
        v39 = (v38 & 4) != 0 ? *(_DWORD *)(a1 + 9160) : 0;
        *(_DWORD *)(a1 + 9164) = v39;
        v40 = (_WORD *)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 440LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL));
        v41 = (_WORD *)(a1 + 7592);
        do
        {
          if ( v8 == -2147483385 )
            break;
          if ( !*v40 )
            break;
          *v41++ = *v40++;
          --v8;
        }
        while ( v8 );
        v42 = v41 - 1;
        if ( v8 )
          v42 = v41;
        *v42 = 0;
        v6 = v8 == 0 ? 0x8007007A : 0;
        if ( v8 || (bidGblFlags & 2) == 0 )
          return v6;
        v11 = 717833;
LABEL_95:
        v10 = v6;
        goto LABEL_96;
      }
    }
    else
    {
      if ( *(_WORD *)(v29 + *(_QWORD *)(v28 + 128)) )
        v33 = CDlgATTRs::CopyATTRValue(a2, 14, 5);
      else
        v33 = CDlgATTRs::SetATTRValue(a2, 14, &g_szComputerName);
      v6 = v33;
      if ( v33 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v6;
        v11 = 654345;
        goto LABEL_95;
      }
      _mm_lfence();
    }
    *(_WORD *)(*((_QWORD *)a2 + 1) + 336LL) |= 0x20u;
    goto LABEL_66;
  }
  v12 = v45;
  *(_BYTE *)(a1 + 9174) |= 8u;
  v13 = MapNetworkPrefixEnum(v12);
  if ( v13 == 4 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v14 = 540681;
LABEL_12:
      v15 = 2147549183LL;
      return (unsigned int)bidTraceHR(0, v14, v15, v7);
    }
    return (unsigned int)-2147418113;
  }
  v16 = (_WORD *)(a1 + 7592);
  v17 = (char *)v44 - a1 - 7592;
  *(_DWORD *)(a1 + 9164) = v13;
  v18 = 261;
  do
  {
    if ( v18 == -2147483385 )
      break;
    v19 = *(_WORD *)((char *)v16 + (_QWORD)v17);
    if ( !v19 )
      break;
    *v16++ = v19;
    --v18;
  }
  while ( v18 );
  v20 = v16 - 1;
  if ( v18 )
    v20 = v16;
  *v20 = 0;
  v6 = v18 == 0 ? 0x8007007A : 0;
  if ( !v18 )
  {
    if ( (bidGblFlags & 2) == 0 )
      return v6;
    v11 = 549897;
    goto LABEL_95;
  }
  _mm_lfence();
  v21 = CDlgATTRs::SetATTRValue(a2, 18, v44);
  v6 = v21;
  if ( v21 >= 0 )
  {
    _mm_lfence();
    *(_WORD *)(*((_QWORD *)a2 + 1) + 432LL) |= 1u;
    *(_WORD *)(*((_QWORD *)a2 + 1) + 432LL) |= 8u;
    *(_WORD *)(*((_QWORD *)a2 + 1) + 432LL) &= ~2u;
    *(_WORD *)(*((_QWORD *)a2 + 1) + 432LL) &= ~0x20u;
    goto LABEL_28;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    v10 = (unsigned int)v21;
    v11 = 552969;
    goto LABEL_96;
  }
  return v6;
}

```

## disassembly

```asm
0x1004e45cc  mov     [rsp-8+arg_10], rbx
0x1004e45d1  push    rbp
0x1004e45d2  push    rsi
0x1004e45d3  push    rdi
0x1004e45d4  push    r12
0x1004e45d6  push    r13
0x1004e45d8  push    r14
0x1004e45da  push    r15
0x1004e45dc  lea     rbp, [rsp-370h]
0x1004e45e4  sub     rsp, 470h
0x1004e45eb  mov     rax, cs:__security_cookie
0x1004e45f2  xor     rax, rsp
0x1004e45f5  mov     [rbp+3A0h+var_40], rax
0x1004e45fc  xor     r12d, r12d
0x1004e45ff  mov     r15d, r8d
0x1004e4602  mov     rdi, rdx
0x1004e4605  mov     [rsp+4A0h+var_468], r12
0x1004e460a  mov     rsi, rcx
0x1004e460d  mov     [rsp+4A0h+var_470], r12
0x1004e4612  xor     edx, edx; Val
0x1004e4614  lea     rcx, [rsp+4A0h+var_460]; void *
0x1004e4619  mov     r8d, 416h; Size
0x1004e461f  mov     ebx, r12d
0x1004e4622  call    memset_0
0x1004e4627  call    ?IsEmbeddedSNAC@@YAHXZ; IsEmbeddedSNAC(void)
0x1004e462c  lea     r13d, [r12+1]
0x1004e4631  mov     r14d, 105h
0x1004e4637  test    eax, eax
0x1004e4639  jnz     loc_1004E496B
0x1004e463f  test    rsi, rsi
0x1004e4642  jz      loc_1004E47D7
0x1004e4648  mov     rax, [rdi+8]
0x1004e464c  test    [rax+138h], r13b
0x1004e4653  jz      short loc_1004E465E
0x1004e4655  test    r15d, r15d
0x1004e4658  jz      loc_1004E47D7
0x1004e465e  lea     rax, [rsp+4A0h+var_470]
0x1004e4663  mov     r9d, 20Bh
0x1004e4669  mov     [rsp+4A0h+var_478], rax
0x1004e466e  lea     r8, [rsp+4A0h+var_460]
0x1004e4673  lea     rax, [rsp+4A0h+var_468]
0x1004e4678  mov     edx, 12h
0x1004e467d  mov     rcx, rdi
0x1004e4680  mov     [rsp+4A0h+var_480], rax
0x1004e4685  call    ?GetNetLibAddr@@YAJAEAVCDlgATTRs@@W4_ATTR_KEY@@PEAG_KPEAPEAG4@Z; GetNetLibAddr(CDlgATTRs &,_ATTR_KEY,ushort *,unsigned __int64,ushort * *,ushort * *)
0x1004e468a  mov     ebx, eax
0x1004e468c  test    eax, eax
0x1004e468e  jns     short loc_1004E46AA
0x1004e4690  test    byte ptr cs:_bidGblFlags, 2
0x1004e4697  jz      loc_1004E4C0E
0x1004e469d  mov     r8d, eax
0x1004e46a0  mov     edx, 81409h
0x1004e46a5  jmp     loc_1004E4C04
0x1004e46aa  jnz     loc_1004E47D7
0x1004e46b0  mov     rcx, [rsp+4A0h+var_468]
0x1004e46b5  or      byte ptr [rsi+23D6h], 8
0x1004e46bc  call    ?MapNetworkPrefixEnum@@YA?AW4PrefixEnum@@PEBG@Z; MapNetworkPrefixEnum(ushort const *)
0x1004e46c1  cmp     eax, 4
0x1004e46c4  jnz     short loc_1004E46F2
0x1004e46c6  test    byte ptr cs:_bidGblFlags, 2
0x1004e46cd  jz      short loc_1004E46E8
0x1004e46cf  mov     edx, 84009h
0x1004e46d4  mov     r8d, 8000FFFFh
0x1004e46da  xor     ecx, ecx
0x1004e46dc  call    _bidTraceHR
0x1004e46e1  mov     ebx, eax
0x1004e46e3  jmp     loc_1004E4C0E
0x1004e46e8  mov     ebx, 8000FFFFh
0x1004e46ed  jmp     loc_1004E4C0E
0x1004e46f2  mov     r8, [rsp+4A0h+var_470]
0x1004e46f7  lea     rcx, [rsi+1DA8h]
0x1004e46fe  sub     r8, rcx
0x1004e4701  mov     [rsi+23CCh], eax
0x1004e4707  mov     rdx, r14
0x1004e470a  lea     rax, [rdx+7FFFFEF9h]
0x1004e4711  test    rax, rax
0x1004e4714  jz      short loc_1004E472C
0x1004e4716  movzx   eax, word ptr [r8+rcx]
0x1004e471b  test    ax, ax
0x1004e471e  jz      short loc_1004E472C
0x1004e4720  mov     [rcx], ax
0x1004e4723  add     rcx, 2
0x1004e4727  sub     rdx, r13
0x1004e472a  jnz     short loc_1004E470A
0x1004e472c  test    rdx, rdx
0x1004e472f  lea     rax, [rcx-2]
0x1004e4733  cmovnz  rax, rcx
0x1004e4737  mov     [rax], r12w
0x1004e473b  mov     rax, rdx
0x1004e473e  neg     rax
0x1004e4741  sbb     ebx, ebx
0x1004e4743  not     ebx
0x1004e4745  and     ebx, 8007007Ah
0x1004e474b  test    rdx, rdx
0x1004e474e  jnz     short loc_1004E4767
0x1004e4750  test    byte ptr cs:_bidGblFlags, 2
0x1004e4757  jz      loc_1004E4C0E
0x1004e475d  mov     edx, 86409h
0x1004e4762  jmp     loc_1004E4C01
0x1004e4767  lfence
0x1004e476a  mov     r8, [rsp+4A0h+var_470]; unsigned __int16 *
0x1004e476f  mov     edx, 12h; int
0x1004e4774  mov     rcx, rdi; this
0x1004e4777  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x1004e477c  mov     ebx, eax
0x1004e477e  test    eax, eax
0x1004e4780  jns     short loc_1004E479C
0x1004e4782  test    byte ptr cs:_bidGblFlags, 2
0x1004e4789  jz      loc_1004E4C0E
0x1004e478f  mov     r8d, eax
0x1004e4792  mov     edx, 87009h
0x1004e4797  jmp     loc_1004E4C04
0x1004e479c  lfence
0x1004e479f  mov     rax, [rdi+8]
0x1004e47a3  mov     ecx, 0FFFDh
0x1004e47a8  or      [rax+1B0h], r13w
0x1004e47b0  mov     rax, [rdi+8]
0x1004e47b4  or      word ptr [rax+1B0h], 8
0x1004e47bc  mov     rax, [rdi+8]
0x1004e47c0  and     [rax+1B0h], cx
0x1004e47c7  mov     ecx, 0FFDFh
0x1004e47cc  mov     rax, [rdi+8]
0x1004e47d0  and     [rax+1B0h], cx
0x1004e47d7  mov     rax, [rdi+8]
0x1004e47db  test    [rax+138h], r13b
0x1004e47e2  jnz     short loc_1004E47ED
0x1004e47e4  test    [rax+150h], r13b
0x1004e47eb  jz      short loc_1004E47F6
0x1004e47ed  test    r15d, r15d
0x1004e47f0  jz      loc_1004E496B
0x1004e47f6  lea     rax, [rsp+4A0h+var_470]
0x1004e47fb  mov     r9d, 20Bh
0x1004e4801  mov     [rsp+4A0h+var_478], rax
0x1004e4806  lea     r8, [rsp+4A0h+var_460]
0x1004e480b  lea     rax, [rsp+4A0h+var_468]
0x1004e4810  mov     edx, 5
0x1004e4815  mov     rcx, rdi
0x1004e4818  mov     [rsp+4A0h+var_480], rax
0x1004e481d  call    ?GetNetLibAddr@@YAJAEAVCDlgATTRs@@W4_ATTR_KEY@@PEAG_KPEAPEAG4@Z; GetNetLibAddr(CDlgATTRs &,_ATTR_KEY,ushort *,unsigned __int64,ushort * *,ushort * *)
0x1004e4822  mov     ebx, eax
0x1004e4824  test    eax, eax
0x1004e4826  jns     short loc_1004E4842
0x1004e4828  test    byte ptr cs:_bidGblFlags, 2
0x1004e482f  jz      loc_1004E4C0E
0x1004e4835  mov     r8d, eax
0x1004e4838  mov     edx, 8CC09h
0x1004e483d  jmp     loc_1004E4C04
0x1004e4842  lfence
0x1004e4845  jnz     loc_1004E49B5
0x1004e484b  mov     r8, [rsp+4A0h+var_468]; unsigned __int16 *
0x1004e4850  mov     edx, 0Dh; int
0x1004e4855  mov     rcx, rdi; this
0x1004e4858  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x1004e485d  mov     ebx, eax
0x1004e485f  test    eax, eax
0x1004e4861  jns     short loc_1004E487D
0x1004e4863  test    byte ptr cs:_bidGblFlags, 2
0x1004e486a  jz      loc_1004E4C0E
0x1004e4870  mov     r8d, eax
0x1004e4873  mov     edx, 8E809h
0x1004e4878  jmp     loc_1004E4C04
0x1004e487d  lfence
0x1004e4880  mov     rax, [rdi+8]
0x1004e4884  mov     r15d, 0FFFDh
0x1004e488a  mov     r8, [rsp+4A0h+var_470]; unsigned __int16 *
0x1004e488f  mov     edx, 0Eh; int
0x1004e4894  or      [rax+138h], r13w
0x1004e489c  lea     ecx, [r15-1Eh]
0x1004e48a0  mov     rax, [rdi+8]
0x1004e48a4  or      word ptr [rax+138h], 8
0x1004e48ac  mov     rax, [rdi+8]
0x1004e48b0  and     [rax+138h], r15w
0x1004e48b8  mov     rax, [rdi+8]
0x1004e48bc  and     [rax+138h], cx
0x1004e48c3  mov     rcx, rdi; this
0x1004e48c6  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x1004e48cb  mov     ebx, eax
0x1004e48cd  test    eax, eax
0x1004e48cf  jns     short loc_1004E48EB
0x1004e48d1  test    byte ptr cs:_bidGblFlags, 2
0x1004e48d8  jz      loc_1004E4C0E
0x1004e48de  mov     r8d, eax
0x1004e48e1  mov     edx, 90809h
0x1004e48e6  jmp     loc_1004E4C04
0x1004e48eb  lfence
0x1004e48ee  mov     rax, [rdi+8]
0x1004e48f2  mov     ecx, 0FFDFh
0x1004e48f7  or      [rax+150h], r13w
0x1004e48ff  mov     rax, [rdi+8]
0x1004e4903  or      word ptr [rax+150h], 8
0x1004e490b  mov     rax, [rdi+8]
0x1004e490f  and     [rax+150h], r15w
0x1004e4917  mov     rax, [rdi+8]
0x1004e491b  and     [rax+150h], cx
0x1004e4922  test    rsi, rsi
0x1004e4925  jz      short loc_1004E496B
0x1004e4927  lfence
0x1004e492a  and     byte ptr [rsi+23D6h], 0FBh
0x1004e4931  mov     rax, [rdi+10h]
0x1004e4935  mov     rdx, [rdi+8]
0x1004e4939  mov     rcx, [rax+20h]
0x1004e493d  add     rcx, [rdx+140h]
0x1004e4944  call    ?MapNetworkPrefixEnum@@YA?AW4PrefixEnum@@PEBG@Z; MapNetworkPrefixEnum(ushort const *)
0x1004e4949  cmp     eax, 4
0x1004e494c  jnz     short loc_1004E4965
0x1004e494e  test    byte ptr cs:_bidGblFlags, 2
0x1004e4955  jz      loc_1004E46E8
0x1004e495b  mov     edx, 94009h
0x1004e4960  jmp     loc_1004E46D4
0x1004e4965  mov     [rsi+23C8h], eax
0x1004e496b  mov     rdx, [rdi+8]
0x1004e496f  mov     rax, [rdi+10h]
0x1004e4973  mov     rcx, [rdx+158h]
0x1004e497a  mov     r8, [rax+20h]
0x1004e497e  add     rcx, r8; String1
0x1004e4981  cmp     [rcx], r12w
0x1004e4985  jz      loc_1004E4A45
0x1004e498b  test    byte ptr [rdx+150h], 20h
0x1004e4992  jnz     loc_1004E4A9E
0x1004e4998  mov     rdx, [rdx+80h]
0x1004e499f  add     rdx, r8; String2
0x1004e49a2  call    cs:__imp__wcsicmp
0x1004e49a8  test    eax, eax
0x1004e49aa  jnz     loc_1004E4A9E
0x1004e49b0  jmp     loc_1004E4A92
0x1004e49b5  mov     rax, [rdi+8]
0x1004e49b9  test    [rax+150h], r13b
0x1004e49c0  jnz     short loc_1004E49F6
0x1004e49c2  lfence
0x1004e49c5  mov     edx, 0Eh; int
0x1004e49ca  mov     rcx, rdi; this
0x1004e49cd  lea     r8d, [rdx-9]; int
0x1004e49d1  call    ?CopyATTRValue@CDlgATTRs@@QEAAJHH@Z; CDlgATTRs::CopyATTRValue(int,int)
0x1004e49d6  mov     ebx, eax
0x1004e49d8  test    eax, eax
0x1004e49da  jns     short loc_1004E49F6
0x1004e49dc  test    byte ptr cs:_bidGblFlags, 2
0x1004e49e3  jz      loc_1004E4C0E
0x1004e49e9  mov     r8d, eax
0x1004e49ec  mov     edx, 97409h
0x1004e49f1  jmp     loc_1004E4C04
0x1004e49f6  lfence
0x1004e49f9  mov     rax, [rdi+8]
0x1004e49fd  test    [rax+138h], r13b
0x1004e4a04  jnz     loc_1004E496B
0x1004e4a0a  lfence
0x1004e4a0d  lea     r8, aDbnetlib; "DBNETLIB"
0x1004e4a14  mov     edx, 0Dh; int
0x1004e4a19  mov     rcx, rdi; this
0x1004e4a1c  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x1004e4a21  mov     ebx, eax
0x1004e4a23  test    eax, eax
0x1004e4a25  jns     loc_1004E496B
0x1004e4a2b  test    byte ptr cs:_bidGblFlags, 2
0x1004e4a32  jz      loc_1004E4C0E
0x1004e4a38  mov     r8d, eax
0x1004e4a3b  mov     edx, 98C09h
0x1004e4a40  jmp     loc_1004E4C04
0x1004e4a45  mov     rax, [rdx+80h]
0x1004e4a4c  mov     rcx, rdi; this
0x1004e4a4f  mov     edx, 0Eh; int
0x1004e4a54  cmp     [r8+rax], r12w
0x1004e4a59  jz      short loc_1004E4A66
0x1004e4a5b  lea     r8d, [rdx-9]; int
0x1004e4a5f  call    ?CopyATTRValue@CDlgATTRs@@QEAAJHH@Z; CDlgATTRs::CopyATTRValue(int,int)
0x1004e4a64  jmp     short loc_1004E4A72
0x1004e4a66  lea     r8, ?g_szComputerName@@3PAGA; unsigned __int16 *
0x1004e4a6d  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x1004e4a72  mov     ebx, eax
0x1004e4a74  test    eax, eax
0x1004e4a76  jns     short loc_1004E4A8F
0x1004e4a78  test    byte ptr cs:_bidGblFlags, 2
0x1004e4a7f  jz      loc_1004E4C0E
0x1004e4a85  mov     edx, 9FC09h
0x1004e4a8a  jmp     loc_1004E4C01
0x1004e4a8f  lfence
0x1004e4a92  mov     rax, [rdi+8]
0x1004e4a96  or      word ptr [rax+150h], 20h
0x1004e4a9e  mov     rdx, [rdi+8]
0x1004e4aa2  mov     rax, [rdi+10h]
0x1004e4aa6  mov     rcx, [rdx+140h]
0x1004e4aad  add     rcx, [rax+20h]; String1
0x1004e4ab1  cmp     [rcx], r12w
0x1004e4ab5  jz      short loc_1004E4AD3
0x1004e4ab7  test    byte ptr [rdx+138h], 20h
0x1004e4abe  jnz     short loc_1004E4B16
0x1004e4ac0  lea     rdx, aDbnetlib; "DBNETLIB"
0x1004e4ac7  call    cs:__imp__wcsicmp
0x1004e4acd  test    eax, eax
0x1004e4acf  jnz     short loc_1004E4B16
0x1004e4ad1  jmp     short loc_1004E4B0A
0x1004e4ad3  lea     r8, aDbnetlib; "DBNETLIB"
0x1004e4ada  mov     edx, 0Dh; int
0x1004e4adf  mov     rcx, rdi; this
0x1004e4ae2  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x1004e4ae7  mov     ebx, eax
0x1004e4ae9  test    eax, eax
0x1004e4aeb  jns     short loc_1004E4B07
0x1004e4aed  test    byte ptr cs:_bidGblFlags, 2
0x1004e4af4  jz      loc_1004E4C0E
  ... truncated ...
```
