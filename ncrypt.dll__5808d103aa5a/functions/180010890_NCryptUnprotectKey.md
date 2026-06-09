# NCryptUnprotectKey

- ea: `0x180010890`
- end: `0x1800109c7`
- name: `NCryptUnprotectKey`
- size: `311`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800122c4`
- `0x180016e90`

## callees

- `0x18000d02c`
- `0x18000e120`
- `0x180010890`
- `0x1800109d0`
- `0x18001b784`
- `0x180020010`

## string_xrefs

- `0x18001096b`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\router.c`
- `0x18001099b`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\router.c`

## pseudocode

```c
__int64 __fastcall NCryptUnprotectKey(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7)
{
  PVOID *v11; // rcx
  __int64 *v12; // r8
  unsigned int v13; // eax
  unsigned int v14; // ebx

  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, a3, a1, a7);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 && *(_DWORD *)a1 == 72 && *(_QWORD *)(a1 + 56) )
  {
    v12 = &NCryptDefaultAllocPara;
    if ( a3 )
      v12 = a3;
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, __int64, __int64, __int64, unsigned int))(a1 + 48))(
            *(_QWORD *)(a1 + 56),
            a2,
            v12,
            a4,
            a5,
            a6,
            a7);
    v14 = v13;
    if ( v13 )
    {
      DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\router.c", 442);
      EtwLogNCryptUnprotectKeyFailed(*(_QWORD *)(a1 + 64), a2, a7, v14);
    }
  }
  else
  {
    v14 = -2146893786;
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        (unsigned int)v11[2],
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\router.c",
        166);
  }
  return v14;
}

```

## disassembly

```asm
0x180010890  push    rbx
0x180010892  push    rbp
0x180010893  push    rsi
0x180010894  push    rdi
0x180010895  push    r14
0x180010897  push    r15
0x180010899  sub     rsp, 48h
0x18001089d  mov     r14, r9
0x1800108a0  mov     rbx, r8
0x1800108a3  mov     rbp, rdx
0x1800108a6  mov     rdi, rcx
0x1800108a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108b0  lea     r15, WPP_GLOBAL_Control
0x1800108b7  mov     esi, [rsp+78h+arg_30]
0x1800108be  cmp     rcx, r15
0x1800108c1  jnz     short loc_180010930
0x1800108c3  test    rdi, rdi
0x1800108c6  jz      loc_180010957
0x1800108cc  cmp     dword ptr [rdi], 48h ; 'H'
0x1800108cf  jnz     loc_180010957
0x1800108d5  cmp     qword ptr [rdi+38h], 0
0x1800108da  jz      short loc_180010957
0x1800108dc  mov     rdx, [rsp+78h+arg_28]
0x1800108e4  lea     r8, NCryptDefaultAllocPara
0x1800108eb  mov     rcx, [rdi+38h]
0x1800108ef  test    rbx, rbx
0x1800108f2  mov     rax, [rdi+30h]
0x1800108f6  mov     r9, r14
0x1800108f9  mov     [rsp+78h+var_48], esi
0x1800108fd  cmovnz  r8, rbx
0x180010901  mov     [rsp+78h+var_50], rdx
0x180010906  mov     rdx, [rsp+78h+arg_20]
0x18001090e  mov     [rsp+78h+var_58], rdx
0x180010913  mov     rdx, rbp
0x180010916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001091b  mov     ebx, eax
0x18001091d  test    eax, eax
0x18001091f  jnz     short loc_180010995
0x180010921  mov     eax, ebx
0x180010923  add     rsp, 48h
0x180010927  pop     r15
0x180010929  pop     r14
0x18001092b  pop     rdi
0x18001092c  pop     rsi
0x18001092d  pop     rbp
0x18001092e  pop     rbx
0x18001092f  retn
0x180010930  test    byte ptr [rcx+1Ch], 4
0x180010934  jz      short loc_1800108C3
0x180010936  mov     rcx, [rcx+10h]
0x18001093a  mov     edx, 0Fh
0x18001093f  mov     r9, rdi
0x180010942  mov     dword ptr [rsp+78h+var_58], esi
0x180010946  call    WPP_SF_qD
0x18001094b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010952  jmp     loc_1800108C3
0x180010957  mov     ebx, 80090026h
0x18001095c  cmp     rcx, r15
0x18001095f  jz      short loc_180010921
0x180010961  test    byte ptr [rcx+1Ch], 1
0x180010965  jz      short loc_180010921
0x180010967  mov     rcx, [rcx+10h]
0x18001096b  lea     rax, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010972  mov     [rsp+78h+var_48], 1A6h
0x18001097a  lea     r9, aStatus; "Status"
0x180010981  mov     [rsp+78h+var_50], rax
0x180010986  mov     dword ptr [rsp+78h+var_58], 80090026h
0x18001098e  call    WPP_SF_sDsd
0x180010993  jmp     short loc_180010921
0x180010995  mov     r9d, 1BAh
0x18001099b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800109a2  lea     rdx, aStatus; "Status"
0x1800109a9  mov     ecx, ebx
0x1800109ab  call    DebugTraceError
0x1800109b0  mov     rcx, [rdi+40h]
0x1800109b4  mov     r9d, ebx
0x1800109b7  mov     r8d, esi
0x1800109ba  mov     rdx, rbp
0x1800109bd  call    EtwLogNCryptUnprotectKeyFailed
0x1800109c2  jmp     loc_180010921
```
