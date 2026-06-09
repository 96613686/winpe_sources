# NCryptCloseKeyProtector

- ea: `0x180007b80`
- end: `0x180007c98`
- name: `NCryptCloseKeyProtector`
- size: `280`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180008cfc`
- `0x180008da0`

## callees

- `0x180007234`
- `0x180007b80`
- `0x180007ca0`
- `0x18000a770`
- `0x18000d02c`
- `0x1800109d0`
- `0x180020010`

## string_xrefs

- `0x180007c0c`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\router.c`

## pseudocode

```c
__int64 __fastcall NCryptCloseKeyProtector(__int64 a1, int a2, __int64 a3)
{
  PVOID *v4; // rcx
  signed __int32 v5; // eax
  bool v6; // cc
  signed __int32 v7; // eax
  unsigned int v8; // ebx

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a7f478cd9c5e3193055148dad9f0cbe0_Traceguids, a1);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 && *(_DWORD *)a1 == 72 )
  {
    v5 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 4), 0xFFFFFFFF);
    v6 = v5 <= 1;
    v7 = v5 - 1;
    if ( v6 )
    {
      if ( *(_QWORD *)(a1 + 8) )
      {
        if ( *(_QWORD *)(a1 + 56) )
          (*(void (**)(void))(a1 + 32))();
        UnloadProvider(*(_QWORD *)(a1 + 8));
      }
      MSCryptFree(a1);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, a3, a1, v7);
    }
    return 0;
  }
  else
  {
    v8 = -2146893786;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        (unsigned int)v4[2],
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\router.c",
        37);
  }
  return v8;
}

```

## disassembly

```asm
0x180007b80  mov     [rsp+arg_0], rbx
0x180007b85  push    rdi
0x180007b86  sub     rsp, 40h
0x180007b8a  mov     rbx, rcx
0x180007b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b94  lea     rdi, WPP_GLOBAL_Control
0x180007b9b  cmp     rcx, rdi
0x180007b9e  jnz     loc_180007C36
0x180007ba4  test    rbx, rbx
0x180007ba7  jz      short loc_180007BF8
0x180007ba9  cmp     dword ptr [rbx], 48h ; 'H'
0x180007bac  jnz     short loc_180007BF8
0x180007bae  or      eax, 0FFFFFFFFh
0x180007bb1  lock xadd [rbx+4], eax
0x180007bb6  sub     eax, 1
0x180007bb9  jg      loc_180007C64
0x180007bbf  cmp     qword ptr [rbx+8], 0
0x180007bc4  jz      short loc_180007BE1
0x180007bc6  mov     rcx, [rbx+38h]
0x180007bca  test    rcx, rcx
0x180007bcd  jz      short loc_180007BD8
0x180007bcf  mov     rax, [rbx+20h]
0x180007bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bd8  mov     rcx, [rbx+8]
0x180007bdc  call    UnloadProvider
0x180007be1  mov     rcx, rbx
0x180007be4  call    MSCryptFree
0x180007be9  xor     ebx, ebx
0x180007beb  mov     eax, ebx
0x180007bed  mov     rbx, [rsp+48h+arg_0]
0x180007bf2  add     rsp, 40h
0x180007bf6  pop     rdi
0x180007bf7  retn
0x180007bf8  mov     ebx, 80090026h
0x180007bfd  cmp     rcx, rdi
0x180007c00  jz      short loc_180007BEB
0x180007c02  test    byte ptr [rcx+1Ch], 1
0x180007c06  jz      short loc_180007BEB
0x180007c08  mov     rcx, [rcx+10h]
0x180007c0c  lea     rax, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007c13  mov     [rsp+48h+var_18], 125h
0x180007c1b  lea     r9, aStatus; "Status"
0x180007c22  mov     [rsp+48h+var_20], rax
0x180007c27  mov     [rsp+48h+var_28], 80090026h
0x180007c2f  call    WPP_SF_sDsd
0x180007c34  jmp     short loc_180007BEB
0x180007c36  test    byte ptr [rcx+1Ch], 4
0x180007c3a  jz      loc_180007BA4
0x180007c40  mov     rcx, [rcx+10h]
0x180007c44  lea     r8, WPP_a7f478cd9c5e3193055148dad9f0cbe0_Traceguids
0x180007c4b  mov     edx, 0Ch
0x180007c50  mov     r9, rbx
0x180007c53  call    WPP_SF_q
0x180007c58  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c5f  jmp     loc_180007BA4
0x180007c64  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c6b  cmp     rcx, rdi
0x180007c6e  jz      loc_180007BE9
0x180007c74  test    byte ptr [rcx+1Ch], 20h
0x180007c78  jz      loc_180007BE9
0x180007c7e  mov     rcx, [rcx+10h]
0x180007c82  mov     edx, 0Dh
0x180007c87  mov     r9, rbx
0x180007c8a  mov     [rsp+48h+var_28], eax
0x180007c8e  call    WPP_SF_qD
0x180007c93  jmp     loc_180007BE9
```
