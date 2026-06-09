# MRxDAVGetFullDirectoryPath

- ea: `0x140002138`
- end: `0x1400022c0`
- name: `MRxDAVGetFullDirectoryPath`
- size: `392`
- prototype: `__int64 __fastcall(__int64, const void **, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140011eec`
- `0x14001e6a0`
- `0x140022a80`

## callees

- `0x140001680`
- `0x140002138`
- `0x140006900`
- `0x140006c00`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140002239`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140002239`
- `ntoskrnl!ExAllocatePool2` at `0x1400021fb`
- `ntoskrnl!ExAllocatePool2` at `0x1400021fb`

## pseudocode

```c
__int64 __fastcall MRxDAVGetFullDirectoryPath(__int64 a1, const void **a2, __int64 a3)
{
  unsigned int v5; // esi
  __int64 v6; // rax
  unsigned __int16 v7; // cx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int16 v10; // ax
  __int16 v11; // dx
  __int64 v12; // rbp
  unsigned __int16 v13; // dx
  size_t v14; // r14
  void *Pool2; // rax
  __int64 v16; // rbx
  HANDLE CurrentThreadId; // rax

  *(_QWORD *)(a3 + 8) = 0;
  *(_DWORD *)a3 = 0;
  v5 = 0;
  if ( a2 )
  {
    v11 = *(_WORD *)a2;
    if ( v11 )
    {
      v12 = *(_QWORD *)(a1 + 56);
      v13 = **(_WORD **)(*(_QWORD *)(v12 + 120) + 88LL) + v11;
      *(_WORD *)(a3 + 2) = v13;
      *(_WORD *)a3 = v13;
      v14 = v13 + 2LL;
      Pool2 = (void *)ExAllocatePool2(258, v14, 1766217284);
      *(_QWORD *)(a3 + 8) = Pool2;
      if ( Pool2 )
      {
        memset(Pool2, 0, v14);
        memmove(
          *(void **)(a3 + 8),
          *(const void **)(*(_QWORD *)(*(_QWORD *)(v12 + 120) + 88LL) + 8LL),
          **(unsigned __int16 **)(*(_QWORD *)(v12 + 120) + 88LL));
        memmove(
          (void *)(*(_QWORD *)(a3 + 8)
                 + 2 * ((unsigned __int64)**(unsigned __int16 **)(*(_QWORD *)(v12 + 120) + 88LL) >> 1)),
          a2[1],
          *(unsigned __int16 *)a2);
      }
      else
      {
        v5 = -1073741670;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v16 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          CurrentThreadId = PsGetCurrentThreadId();
          WPP_SF_qD(v16, 133, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, CurrentThreadId, -1073741670);
        }
      }
    }
  }
  else
  {
    v6 = *(_QWORD *)(a1 + 48);
    v7 = 1;
    v8 = *(_QWORD *)(v6 + 48);
    v9 = *(_WORD *)(v8 + 88) >> 1;
    if ( (unsigned __int16)v9 > 1u )
    {
      do
      {
        if ( *(_WORD *)(*(_QWORD *)(v8 + 96) + 2LL * v7) == 92 )
          break;
        ++v7;
      }
      while ( v7 < (unsigned __int16)v9 );
    }
    if ( v7 < (unsigned __int16)v9 )
    {
      *(_QWORD *)(a3 + 8) = 2LL * v7 + *(_QWORD *)(v8 + 96);
      v10 = *(_WORD *)(v8 + 88) - 2 * v7;
      *(_WORD *)(a3 + 2) = v10;
      *(_WORD *)a3 = v10;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140002138  push    rbx
0x14000213a  push    rbp
0x14000213b  push    rsi
0x14000213c  push    rdi
0x14000213d  push    r14
0x14000213f  push    r15
0x140002141  sub     rsp, 38h
0x140002145  xor     r15d, r15d
0x140002148  mov     rbx, r8
0x14000214b  mov     [r8+8], r15
0x14000214f  mov     rdi, rdx
0x140002152  mov     [r8], r15d
0x140002155  mov     esi, r15d
0x140002158  test    rdx, rdx
0x14000215b  jnz     short loc_1400021C2
0x14000215d  mov     rax, [rcx+30h]
0x140002161  lea     r11d, [rdx+1]
0x140002165  movzx   ecx, r11w
0x140002169  mov     r8, [rax+30h]
0x14000216d  movzx   edx, word ptr [r8+58h]
0x140002172  shr     dx, 1
0x140002175  cmp     r11w, dx
0x140002179  jnb     short loc_140002193
0x14000217b  mov     r9, [r8+60h]
0x14000217f  movzx   eax, cx
0x140002182  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x140002188  jz      short loc_140002193
0x14000218a  add     cx, r11w
0x14000218e  cmp     cx, dx
0x140002191  jb      short loc_14000217F
0x140002193  cmp     cx, dx
0x140002196  jnb     loc_1400022B0
0x14000219c  movzx   eax, cx
0x14000219f  mov     rcx, [r8+60h]
0x1400021a3  lea     rdx, [rax+rax]
0x1400021a7  add     rcx, rdx
0x1400021aa  mov     [rbx+8], rcx
0x1400021ae  movzx   eax, word ptr [r8+58h]
0x1400021b3  sub     ax, dx
0x1400021b6  mov     [rbx+2], ax
0x1400021ba  mov     [rbx], ax
0x1400021bd  jmp     loc_1400022B0
0x1400021c2  movzx   edx, word ptr [rdx]
0x1400021c5  test    dx, dx
0x1400021c8  jz      loc_1400022B0
0x1400021ce  mov     rbp, [rcx+38h]
0x1400021d2  mov     rax, [rbp+78h]
0x1400021d6  mov     rcx, [rax+58h]
0x1400021da  add     dx, [rcx]
0x1400021dd  mov     ecx, 102h
0x1400021e2  movzx   eax, dx
0x1400021e5  mov     [r8+2], ax
0x1400021ea  mov     [r8], ax
0x1400021ee  mov     r8d, 69465644h
0x1400021f4  lea     r14, [rax+2]
0x1400021f8  mov     rdx, r14
0x1400021fb  call    cs:__imp_ExAllocatePool2
0x140002202  nop     dword ptr [rax+rax+00h]
0x140002207  mov     [rbx+8], rax
0x14000220b  test    rax, rax
0x14000220e  jnz     short loc_140002266
0x140002210  mov     esi, 0C000009Ah
0x140002215  mov     rbx, cs:WPP_GLOBAL_Control
0x14000221c  lea     rax, WPP_GLOBAL_Control
0x140002223  cmp     rbx, rax
0x140002226  jz      loc_1400022B0
0x14000222c  test    dword ptr [rbx+2Ch], 2000h
0x140002233  jz      short loc_1400022B0
0x140002235  mov     rbx, [rbx+18h]
0x140002239  call    cs:__imp_PsGetCurrentThreadId
0x140002240  nop     dword ptr [rax+rax+00h]
0x140002245  mov     edx, 85h
0x14000224a  mov     [rsp+68h+var_48], 0C000009Ah
0x140002252  mov     r9, rax
0x140002255  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x14000225c  mov     rcx, rbx
0x14000225f  call    WPP_SF_qD
0x140002264  jmp     short loc_1400022B0
0x140002266  mov     r8, r14; Size
0x140002269  xor     edx, edx; Val
0x14000226b  mov     rcx, rax; void *
0x14000226e  call    memset
0x140002273  mov     rax, [rbp+78h]
0x140002277  mov     rcx, [rbx+8]; void *
0x14000227b  mov     rdx, [rax+58h]
0x14000227f  movzx   r8d, word ptr [rdx]; Size
0x140002283  mov     rdx, [rdx+8]; Src
0x140002287  call    memmove
0x14000228c  mov     rcx, [rbp+78h]
0x140002290  movzx   r8d, word ptr [rdi]; Size
0x140002294  mov     rdx, [rcx+58h]
0x140002298  mov     rcx, [rbx+8]
0x14000229c  movzx   r9d, word ptr [rdx]
0x1400022a0  mov     rdx, [rdi+8]; Src
0x1400022a4  shr     r9, 1
0x1400022a7  lea     rcx, [rcx+r9*2]; void *
0x1400022ab  call    memmove
0x1400022b0  mov     eax, esi
0x1400022b2  add     rsp, 38h
0x1400022b6  pop     r15
0x1400022b8  pop     r14
0x1400022ba  pop     rdi
0x1400022bb  pop     rsi
0x1400022bc  pop     rbp
0x1400022bd  pop     rbx
0x1400022be  retn
```
