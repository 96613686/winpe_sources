# NegoExtsInitKernelContext

- ea: `0x140022510`
- end: `0x14002264e`
- name: `NegoExtsInitKernelContext`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140007008`
- `0x14000e344`
- `0x140010240`
- `0x140022510`
- `0x14002c664`

## string_xrefs

- `0x14002257b`: `Failed to create kernel mode context: 0x%x\n`
- `0x1400225d5`: `NegoExtsInitKernelContext package failed to create kernel mode context: %#x\n`

## pseudocode

```c
__int64 __fastcall NegoExtsInitKernelContext(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rbx
  int v7; // eax
  unsigned int v8; // edi
  PVOID v9; // rbx
  __int64 v10; // rax
  int v11; // eax
  __int128 v13; // [rsp+20h] [rbp-28h] BYREF
  PVOID P; // [rsp+58h] [rbp+10h] BYREF

  v3 = *(_QWORD *)(a2 + 8);
  v13 = 0;
  P = 0;
  if ( KsecInfoLevel )
    KsecDebugOut(4, "NegoExtsInitUserModeContex called\n");
  v7 = NegoExtsCreateKernelModeContext(a1, a2, &P);
  v8 = v7;
  if ( v7 >= 0 )
  {
    LODWORD(v13) = *(_DWORD *)(v3 + 16);
    v10 = v3 + *(unsigned int *)(v3 + 12);
    v9 = P;
    *((_QWORD *)&v13 + 1) = v10;
    v11 = (*(__int64 (__fastcall **)(__int64, __int128 *, char *))(*((_QWORD *)P + 3) + 16LL))(a1, &v13, (char *)P + 32);
    v8 = v11;
    if ( v11 >= 0 )
    {
      *a3 = v9;
      v9 = 0;
    }
    else if ( KsecInfoLevel )
    {
      KsecDebugOut(1, "NegoExtsInitKernelContext package failed to create kernel mode context: %#x\n", v11);
    }
  }
  else
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "Failed to create kernel mode context: 0x%x\n", v7);
    v9 = P;
  }
  if ( v9 )
    NegoExtsFreeContext(v9);
  if ( *(_QWORD *)(a2 + 8) )
  {
    (*(void (**)(void))(NegoExtsKernelFunctions + 8))();
    *(_QWORD *)(a2 + 8) = 0;
  }
  if ( KsecInfoLevel )
    KsecDebugOut(4, "NegoExtsInitUserModeContex returned %#x\n", v8);
  return v8;
}

```

## disassembly

```asm
0x140022510  mov     rax, rsp
0x140022513  mov     [rax+8], rbx
0x140022517  mov     [rax+18h], rbp
0x14002251b  push    rsi
0x14002251c  push    rdi
0x14002251d  push    r14
0x14002251f  sub     rsp, 30h
0x140022523  cmp     cs:KsecInfoLevel, 0
0x14002252a  xorps   xmm0, xmm0
0x14002252d  mov     rbx, [rdx+8]
0x140022531  mov     r14, r8
0x140022534  movups  xmmword ptr [rax-28h], xmm0
0x140022538  mov     rsi, rdx
0x14002253b  mov     qword ptr [rax+10h], 0
0x140022543  mov     rbp, rcx
0x140022546  jz      short loc_140022559
0x140022548  lea     rdx, aNegoextsinitus; "NegoExtsInitUserModeContex called\n"
0x14002254f  mov     ecx, 4
0x140022554  call    KsecDebugOut
0x140022559  lea     r8, [rsp+48h+P]
0x14002255e  mov     rdx, rsi
0x140022561  mov     rcx, rbp
0x140022564  call    NegoExtsCreateKernelModeContext
0x140022569  mov     edi, eax
0x14002256b  test    eax, eax
0x14002256d  jns     short loc_140022593
0x14002256f  cmp     cs:KsecInfoLevel, 0
0x140022576  jz      short loc_14002258C
0x140022578  mov     r8d, eax
0x14002257b  lea     rdx, aFailedToCreate_0; "Failed to create kernel mode context: 0"...
0x140022582  mov     ecx, 1
0x140022587  call    KsecDebugOut
0x14002258c  mov     rbx, [rsp+48h+P]
0x140022591  jmp     short loc_1400225ED
0x140022593  mov     eax, [rbx+10h]
0x140022596  lea     rdx, [rsp+48h+var_28]
0x14002259b  mov     [rsp+48h+var_28], eax
0x14002259f  mov     rcx, rbp
0x1400225a2  mov     eax, [rbx+0Ch]
0x1400225a5  add     rax, rbx
0x1400225a8  mov     rbx, [rsp+48h+P]
0x1400225ad  mov     [rsp+48h+var_20], rax
0x1400225b2  mov     rax, [rbx+18h]
0x1400225b6  lea     r8, [rbx+20h]
0x1400225ba  mov     rax, [rax+10h]
0x1400225be  call    _guard_dispatch_icall
0x1400225c3  mov     edi, eax
0x1400225c5  test    eax, eax
0x1400225c7  jns     short loc_1400225E8
0x1400225c9  cmp     cs:KsecInfoLevel, 0
0x1400225d0  jz      short loc_1400225ED
0x1400225d2  mov     r8d, eax
0x1400225d5  lea     rdx, aNegoextsinitke; "NegoExtsInitKernelContext package faile"...
0x1400225dc  mov     ecx, 1
0x1400225e1  call    KsecDebugOut
0x1400225e6  jmp     short loc_1400225ED
0x1400225e8  mov     [r14], rbx
0x1400225eb  xor     ebx, ebx
0x1400225ed  test    rbx, rbx
0x1400225f0  jz      short loc_1400225FA
0x1400225f2  mov     rcx, rbx; P
0x1400225f5  call    NegoExtsFreeContext
0x1400225fa  mov     rcx, [rsi+8]
0x1400225fe  test    rcx, rcx
0x140022601  jz      short loc_14002261B
0x140022603  mov     rax, cs:NegoExtsKernelFunctions
0x14002260a  mov     rax, [rax+8]
0x14002260e  call    _guard_dispatch_icall
0x140022613  mov     qword ptr [rsi+8], 0
0x14002261b  cmp     cs:KsecInfoLevel, 0
0x140022622  jz      short loc_140022638
0x140022624  mov     r8d, edi
0x140022627  lea     rdx, aNegoextsinitus_0; "NegoExtsInitUserModeContex returned %#x"...
0x14002262e  mov     ecx, 4
0x140022633  call    KsecDebugOut
0x140022638  mov     rbx, [rsp+48h+arg_0]
0x14002263d  mov     eax, edi
0x14002263f  mov     rbp, [rsp+48h+arg_10]
0x140022644  add     rsp, 30h
0x140022648  pop     r14
0x14002264a  pop     rdi
0x14002264b  pop     rsi
0x14002264c  retn
```
