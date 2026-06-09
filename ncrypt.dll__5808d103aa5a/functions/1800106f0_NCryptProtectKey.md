# NCryptProtectKey

- ea: `0x1800106f0`
- end: `0x180010881`
- name: `NCryptProtectKey`
- size: `401`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001550`
- `0x180003150`

## callees

- `0x18000d02c`
- `0x18000f098`
- `0x18000f8b8`
- `0x1800106f0`
- `0x1800109d0`
- `0x180020010`

## string_xrefs

- `0x1800107e7`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\router.c`
- `0x180010827`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\router.c`

## pseudocode

```c
__int64 __fastcall NCryptProtectKey(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        unsigned int a4,
        __int64 *a5,
        __int64 a6,
        __int64 a7,
        int a8)
{
  PVOID *v12; // rcx
  __int64 *v13; // r8
  int v14; // edx
  unsigned int v15; // esi
  int v16; // r8d
  __int64 v18; // rbx
  __int64 v19; // rdi
  __int64 ProcessName; // rax
  int v21; // edx
  int v22; // ecx

  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, a3, a1, a8);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 && *(_DWORD *)a1 == 72 && *(_QWORD *)(a1 + 56) )
  {
    v13 = &NCryptDefaultAllocPara;
    if ( a5 )
      v13 = a5;
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, _QWORD, __int64 *, __int64, __int64, int))(a1 + 40))(
            *(_QWORD *)(a1 + 56),
            a2,
            a3,
            a4,
            v13,
            a6,
            a7,
            a8);
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          v16,
          (unsigned int)"Status",
          v15,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\router.c",
          120);
      if ( (Microsoft_Windows_Crypto_NCryptEnableBits & 2) != 0 )
      {
        v18 = a2[1];
        v19 = *a2;
        ProcessName = I_GetProcessName();
        McTemplateU0zzddz_EventWriteTransfer(v22, v21, v19, v18, a8, v15, ProcessName);
      }
    }
  }
  else
  {
    v15 = -2146893786;
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        (unsigned int)v12[2],
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\router.c",
        99);
  }
  return v15;
}

```

## disassembly

```asm
0x1800106f0  push    rbx
0x1800106f2  push    rbp
0x1800106f3  push    rsi
0x1800106f4  push    rdi
0x1800106f5  push    r14
0x1800106f7  push    r15
0x1800106f9  sub     rsp, 58h
0x1800106fd  mov     esi, r9d
0x180010700  mov     r14, r8
0x180010703  mov     rdi, rdx
0x180010706  mov     rbx, rcx
0x180010709  mov     rcx, cs:WPP_GLOBAL_Control
0x180010710  lea     r15, WPP_GLOBAL_Control
0x180010717  mov     ebp, [rsp+88h+arg_38]
0x18001071e  cmp     rcx, r15
0x180010721  jnz     loc_1800107A8
0x180010727  test    rbx, rbx
0x18001072a  jz      loc_1800107D3
0x180010730  cmp     dword ptr [rbx], 48h ; 'H'
0x180010733  jnz     loc_1800107D3
0x180010739  cmp     qword ptr [rbx+38h], 0
0x18001073e  jz      loc_1800107D3
0x180010744  mov     rax, [rsp+88h+arg_20]
0x18001074c  lea     r8, NCryptDefaultAllocPara
0x180010753  mov     rdx, [rsp+88h+arg_30]
0x18001075b  test    rax, rax
0x18001075e  mov     rcx, [rbx+38h]
0x180010762  mov     r9d, esi
0x180010765  cmovnz  r8, rax
0x180010769  mov     [rsp+88h+var_50], ebp
0x18001076d  mov     rax, [rbx+28h]
0x180010771  mov     [rsp+88h+var_58], rdx
0x180010776  mov     rdx, [rsp+88h+arg_28]
0x18001077e  mov     [rsp+88h+var_60], rdx
0x180010783  mov     rdx, rdi
0x180010786  mov     [rsp+88h+var_68], r8
0x18001078b  mov     r8, r14
0x18001078e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010793  mov     esi, eax
0x180010795  test    eax, eax
0x180010797  jnz     short loc_180010811
0x180010799  mov     eax, esi
0x18001079b  add     rsp, 58h
0x18001079f  pop     r15
0x1800107a1  pop     r14
0x1800107a3  pop     rdi
0x1800107a4  pop     rsi
0x1800107a5  pop     rbp
0x1800107a6  pop     rbx
0x1800107a7  retn
0x1800107a8  test    byte ptr [rcx+1Ch], 4
0x1800107ac  jz      loc_180010727
0x1800107b2  mov     rcx, [rcx+10h]
0x1800107b6  mov     edx, 0Eh
0x1800107bb  mov     r9, rbx
0x1800107be  mov     dword ptr [rsp+88h+var_68], ebp
0x1800107c2  call    WPP_SF_qD
0x1800107c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107ce  jmp     loc_180010727
0x1800107d3  mov     esi, 80090026h
0x1800107d8  cmp     rcx, r15
0x1800107db  jz      short loc_180010799
0x1800107dd  test    byte ptr [rcx+1Ch], 1
0x1800107e1  jz      short loc_180010799
0x1800107e3  mov     rcx, [rcx+10h]
0x1800107e7  lea     rax, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800107ee  mov     dword ptr [rsp+88h+var_58], 163h
0x1800107f6  lea     r9, aStatus; "Status"
0x1800107fd  mov     [rsp+88h+var_60], rax
0x180010802  mov     dword ptr [rsp+88h+var_68], 80090026h
0x18001080a  call    WPP_SF_sDsd
0x18001080f  jmp     short loc_180010799
0x180010811  mov     rcx, cs:WPP_GLOBAL_Control
0x180010818  cmp     rcx, r15
0x18001081b  jz      short loc_18001084B
0x18001081d  test    byte ptr [rcx+1Ch], 1
0x180010821  jz      short loc_18001084B
0x180010823  mov     rcx, [rcx+10h]
0x180010827  lea     rax, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001082e  mov     dword ptr [rsp+88h+var_58], 178h
0x180010836  lea     r9, aStatus; "Status"
0x18001083d  mov     [rsp+88h+var_60], rax
0x180010842  mov     dword ptr [rsp+88h+var_68], esi
0x180010846  call    WPP_SF_sDsd
0x18001084b  test    cs:Microsoft_Windows_Crypto_NCryptEnableBits, 2
0x180010852  jz      loc_180010799
0x180010858  mov     rbx, [rdi+8]
0x18001085c  mov     rdi, [rdi]
0x18001085f  call    I_GetProcessName
0x180010864  mov     [rsp+88h+var_58], rax
0x180010869  mov     r9, rbx
0x18001086c  mov     dword ptr [rsp+88h+var_60], esi
0x180010870  mov     r8, rdi
0x180010873  mov     dword ptr [rsp+88h+var_68], ebp
0x180010877  call    McTemplateU0zzddz_EventWriteTransfer
0x18001087c  jmp     loc_180010799
```
