# ProvSetKeyProperty

- ea: `0x140002510`
- end: `0x14000265e`
- name: `ProvSetKeyProperty`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140002670`

## callees

- `0x140001170`
- `0x140002510`
- `0x1400028e8`
- `0x140003cf6`
- `0x140003e00`

## import_xrefs

- `cng!BCryptSetProperty` at `0x140002546`
- `cng!BCryptSetProperty` at `0x1400025fe`
- `cng!BCryptSetProperty` at `0x140002546`
- `cng!BCryptSetProperty` at `0x1400025fe`

## pseudocode

```c
int __fastcall ProvSetKeyProperty(__int64 a1, __int64 a2, UCHAR *a3, ULONG a4, ULONG dwFlags)
{
  int result; // eax
  char v10; // r15
  int v11; // eax
  int v12; // edi
  int v13; // edi
  __int64 v14; // rcx

  if ( *(_BYTE *)(a1 + 12) )
    return BCryptSetProperty(*(BCRYPT_HANDLE *)(a1 + 16), (LPCWSTR)a2, a3, a4, dwFlags);
  v10 = 0;
  if ( !wcscmp_0((const wchar_t *)a2, L"ChainingMode") )
  {
    v11 = ConvertToInternalChainingMode((wchar_t *)a3);
    v12 = v11;
    if ( *(_BYTE *)(a1 + 13) || !v11 )
      SwitchKeyToSoftwareOnly(a1);
    else
      v10 = 1;
    *(_DWORD *)(a1 + 8) = v12;
    v13 = v12 - 1;
    if ( v13 )
    {
      if ( v13 == 1 )
      {
        *(_QWORD *)(a1 + 96) = 0;
        *(_DWORD *)(a1 + 104) = 0;
      }
    }
    else
    {
      *(_DWORD *)(a1 + 104) = 16;
      *(_QWORD *)(a1 + 96) = a1 + 40;
    }
  }
  else
  {
    if ( *(_WORD *)a2 == 73 && *(_WORD *)(a2 + 2) == 86 && !*(_WORD *)(a2 + 4) && a4 == 16 )
    {
      *(_OWORD *)(a1 + 40) = *(_OWORD *)a3;
      return 0;
    }
    SwitchKeyToSoftwareOnly(a1);
  }
  result = BCryptSetProperty(*(BCRYPT_HANDLE *)(a1 + 16), (LPCWSTR)a2, a3, a4, dwFlags);
  if ( result >= 0 && !*(_BYTE *)(a1 + 12) )
  {
    if ( v10 )
    {
      v14 = *(_QWORD *)(a1 + 24);
      if ( v14 )
      {
        if ( (*(int (__fastcall **)(__int64, __int64, UCHAR *, _QWORD, ULONG))(g_pHwCipherFunctionTable + 24))(
               v14,
               a2,
               a3,
               a4,
               dwFlags) < 0 )
          SwitchKeyToSoftwareOnly(a1);
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002510  push    rbx
0x140002512  push    rbp
0x140002513  push    rsi
0x140002514  push    rdi
0x140002515  push    r12
0x140002517  push    r14
0x140002519  push    r15
0x14000251b  sub     rsp, 30h
0x14000251f  xor     r12d, r12d
0x140002522  mov     r14d, r9d
0x140002525  mov     rbp, r8
0x140002528  mov     rsi, rdx
0x14000252b  mov     rbx, rcx
0x14000252e  cmp     [rcx+0Ch], r12b
0x140002532  jz      short loc_140002557
0x140002534  mov     eax, [rsp+68h+arg_20]
0x14000253b  mov     r9d, r14d; cbInput
0x14000253e  mov     rcx, [rcx+10h]; hObject
0x140002542  mov     [rsp+68h+dwFlags], eax; dwFlags
0x140002546  call    cs:__imp_BCryptSetProperty
0x14000254d  nop     dword ptr [rax+rax+00h]
0x140002552  jmp     loc_14000264E
0x140002557  lea     rdx, aChainingmode; "ChainingMode"
0x14000255e  mov     rcx, rsi; Str1
0x140002561  mov     r15b, r12b
0x140002564  call    wcscmp_0
0x140002569  test    eax, eax
0x14000256b  jnz     short loc_1400025B9
0x14000256d  mov     rdx, r14
0x140002570  mov     rcx, rbp; Str1
0x140002573  call    ConvertToInternalChainingMode
0x140002578  mov     edi, eax
0x14000257a  cmp     [rbx+0Dh], r12b
0x14000257e  jnz     short loc_140002589
0x140002580  test    eax, eax
0x140002582  jz      short loc_140002589
0x140002584  mov     r15b, 1
0x140002587  jmp     short loc_140002591
0x140002589  mov     rcx, rbx
0x14000258c  call    SwitchKeyToSoftwareOnly
0x140002591  mov     [rbx+8], edi
0x140002594  sub     edi, 1
0x140002597  jz      short loc_1400025A8
0x140002599  cmp     edi, 1
0x14000259c  jnz     short loc_1400025E6
0x14000259e  mov     [rbx+60h], r12
0x1400025a2  mov     [rbx+68h], r12d
0x1400025a6  jmp     short loc_1400025E6
0x1400025a8  lea     rax, [rbx+28h]
0x1400025ac  mov     dword ptr [rbx+68h], 10h
0x1400025b3  mov     [rbx+60h], rax
0x1400025b7  jmp     short loc_1400025E6
0x1400025b9  cmp     word ptr [rsi], 49h ; 'I'
0x1400025bd  jnz     short loc_1400025DE
0x1400025bf  cmp     word ptr [rsi+2], 56h ; 'V'
0x1400025c4  jnz     short loc_1400025DE
0x1400025c6  cmp     [rsi+4], r12w
0x1400025cb  jnz     short loc_1400025DE
0x1400025cd  cmp     r14d, 10h
0x1400025d1  jnz     short loc_1400025DE
0x1400025d3  movups  xmm0, xmmword ptr [rbp+0]
0x1400025d7  movdqu  xmmword ptr [rbx+28h], xmm0
0x1400025dc  jmp     short loc_14000264B
0x1400025de  mov     rcx, rbx
0x1400025e1  call    SwitchKeyToSoftwareOnly
0x1400025e6  mov     edi, [rsp+68h+arg_20]
0x1400025ed  mov     r9d, r14d; cbInput
0x1400025f0  mov     rcx, [rbx+10h]; hObject
0x1400025f4  mov     r8, rbp; pbInput
0x1400025f7  mov     rdx, rsi; pszProperty
0x1400025fa  mov     [rsp+68h+dwFlags], edi; dwFlags
0x1400025fe  call    cs:__imp_BCryptSetProperty
0x140002605  nop     dword ptr [rax+rax+00h]
0x14000260a  test    eax, eax
0x14000260c  js      short loc_14000264E
0x14000260e  cmp     [rbx+0Ch], r12b
0x140002612  jnz     short loc_14000264E
0x140002614  test    r15b, r15b
0x140002617  jz      short loc_14000264E
0x140002619  mov     rcx, [rbx+18h]
0x14000261d  test    rcx, rcx
0x140002620  jz      short loc_14000264E
0x140002622  mov     rax, cs:g_pHwCipherFunctionTable
0x140002629  mov     r9d, r14d
0x14000262c  mov     r8, rbp
0x14000262f  mov     [rsp+68h+dwFlags], edi
0x140002633  mov     rdx, rsi
0x140002636  mov     rax, [rax+18h]
0x14000263a  call    _guard_dispatch_icall
0x14000263f  test    eax, eax
0x140002641  jns     short loc_14000264B
0x140002643  mov     rcx, rbx
0x140002646  call    SwitchKeyToSoftwareOnly
0x14000264b  mov     eax, r12d
0x14000264e  add     rsp, 30h
0x140002652  pop     r15
0x140002654  pop     r14
0x140002656  pop     r12
0x140002658  pop     rdi
0x140002659  pop     rsi
0x14000265a  pop     rbp
0x14000265b  pop     rbx
0x14000265c  retn
```
