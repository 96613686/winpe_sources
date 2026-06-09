# CallFindAndLock

- ea: `0x14000360c`
- end: `0x140003881`
- name: `CallFindAndLock`
- size: `629`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400059b0`
- `0x14000f588`
- `0x14000fbac`

## callees

- `0x140002990`
- `0x140002a70`
- `0x140002b10`
- `0x14000360c`
- `0x14000398c`
- `0x140003e08`
- `0x140003e38`
- `0x1400077c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000383c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000383c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003770`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003770`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003660`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400037c1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003660`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400037c1`
- `cng!SystemPrng` at `0x1400036a6`
- `cng!SystemPrng` at `0x1400036a6`

## pseudocode

```c
__int64 __fastcall CallFindAndLock(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rbx
  int v5; // r13d
  const void **v6; // rsi
  int v7; // ebp
  __int64 v8; // r15
  int v9; // edi
  unsigned int v10; // edi
  __int64 v11; // rax
  void *v13; // rax
  const void *v14; // rbp
  int v15; // eax
  unsigned int v16; // [rsp+80h] [rbp+18h] BYREF

  v16 = a3;
  v3 = 0;
  v5 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
  }
  *(_BYTE *)(a1 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  v6 = (const void **)(a1 + 32);
  while ( 2 )
  {
    if ( PptpClientSide )
    {
      v7 = 1;
      LODWORD(v8) = -1;
      goto LABEL_12;
    }
    v7 = 0;
    v9 = 0;
    do
    {
      v16 = 0;
      SystemPrng(&v16, 4);
      v8 = v16 % PptpWanEndpoints;
      if ( !*((_QWORD *)*v6 + v8) )
      {
        v3 = CallAlloc(a1);
        if ( v3 )
        {
          *((_QWORD *)*v6 + v8) = v3;
          *(_QWORD *)(v3 + 200) = v8;
LABEL_22:
          CallSetFullCallId(v3);
LABEL_23:
          _InterlockedIncrement((volatile signed __int32 *)v3);
          goto LABEL_24;
        }
      }
      ++v9;
    }
    while ( v9 < PptpWanEndpoints / 2 );
LABEL_12:
    if ( v7 < 2 )
    {
      v10 = v8;
      while ( 1 )
      {
        if ( v7 )
        {
          if ( (int)++v10 >= PptpWanEndpoints )
          {
LABEL_16:
            ++v7;
            if ( v3 )
              goto LABEL_23;
            goto LABEL_12;
          }
        }
        else if ( (--v10 & 0x80000000) != 0 )
        {
          goto LABEL_16;
        }
        if ( !*((_QWORD *)*v6 + (int)v10) )
        {
          v11 = CallAlloc(a1);
          v3 = v11;
          if ( v11 )
          {
            *((_QWORD *)*v6 + (int)v10) = v11;
            *(_QWORD *)(v11 + 200) = v10;
            goto LABEL_22;
          }
        }
      }
    }
    if ( !v5 && (unsigned int)PptpWanEndpoints <= 0x3FF6 )
    {
      v13 = (void *)MyMemAlloc((unsigned int)(8 * PptpWanEndpoints + 80), 1666208848);
      v14 = v13;
      if ( v13 )
      {
        memmove(v13, *v6, 8LL * (unsigned int)PptpWanEndpoints);
        ExFreePoolWithTag((PVOID)*v6, 0);
        v15 = PptpWanEndpoints + 10;
        *v6 = v14;
        PptpWanEndpoints = v15;
        *(_DWORD *)(a1 + 72) = v15;
        InitCallLayer();
        v5 = 1;
        continue;
      }
    }
    break;
  }
LABEL_24:
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), *(_BYTE *)(a1 + 16));
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        37,
        WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
        *(unsigned int *)(v3 + 200));
    }
    *(_BYTE *)(v3 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 96));
    *(_DWORD *)(v3 + 112) = 2;
  }
  return v3;
}

```

## disassembly

```asm
0x14000360c  mov     [rsp+arg_10], r8d
0x140003611  push    rbx
0x140003612  push    rbp
0x140003613  push    rsi
0x140003614  push    rdi
0x140003615  push    r12
0x140003617  push    r13
0x140003619  push    r14
0x14000361b  push    r15
0x14000361d  sub     rsp, 28h
0x140003621  xor     ebx, ebx
0x140003623  mov     r14, rcx
0x140003626  xor     r13d, r13d
0x140003629  mov     rcx, cs:WPP_GLOBAL_Control
0x140003630  lea     rax, WPP_GLOBAL_Control
0x140003637  cmp     rcx, rax
0x14000363a  jz      short loc_14000365C
0x14000363c  mov     eax, [rcx+2Ch]
0x14000363f  test    al, 10h
0x140003641  jz      short loc_14000365C
0x140003643  cmp     byte ptr [rcx+29h], 2
0x140003647  jb      short loc_14000365C
0x140003649  mov     rcx, [rcx+18h]
0x14000364d  lea     edx, [rbx+24h]
0x140003650  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140003657  call    WPP_SF_
0x14000365c  lea     rcx, [r14+8]; SpinLock
0x140003660  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003667  nop     dword ptr [rax+rax+00h]
0x14000366c  mov     [r14+10h], al
0x140003670  lea     rsi, [r14+20h]
0x140003674  mov     r12d, 2
0x14000367a  cmp     cs:PptpClientSide, 0
0x140003681  jz      short loc_14000368E
0x140003683  mov     ebp, 1
0x140003688  or      r15d, 0FFFFFFFFh
0x14000368c  jmp     short loc_1400036F1
0x14000368e  xor     ebp, ebp
0x140003690  xor     edi, edi
0x140003692  mov     edx, 4
0x140003697  mov     [rsp+68h+arg_10], ebp
0x14000369e  lea     rcx, [rsp+68h+arg_10]
0x1400036a6  call    cs:__imp_SystemPrng
0x1400036ad  nop     dword ptr [rax+rax+00h]
0x1400036b2  mov     eax, [rsp+68h+arg_10]
0x1400036b9  xor     edx, edx
0x1400036bb  div     cs:PptpWanEndpoints
0x1400036c1  mov     rax, [rsi]
0x1400036c4  mov     r15d, edx
0x1400036c7  cmp     [rax+rdx*8], rbp
0x1400036cb  jnz     short loc_1400036E1
0x1400036cd  mov     rcx, r14
0x1400036d0  call    CallAlloc
0x1400036d5  mov     rbx, rax
0x1400036d8  test    rax, rax
0x1400036db  jnz     loc_14000386E
0x1400036e1  mov     eax, cs:PptpWanEndpoints
0x1400036e7  inc     edi
0x1400036e9  cdq
0x1400036ea  idiv    r12d
0x1400036ed  cmp     edi, eax
0x1400036ef  jl      short loc_140003692
0x1400036f1  test    rbx, rbx
0x1400036f4  jnz     short loc_14000375F
0x1400036f6  cmp     ebp, r12d
0x1400036f9  jge     loc_1400037E9
0x1400036ff  mov     edi, r15d
0x140003702  test    ebp, ebp
0x140003704  jnz     short loc_140003720
0x140003706  dec     edi
0x140003708  mov     eax, edi
0x14000370a  not     eax
0x14000370c  shr     eax, 1Fh
0x14000370f  test    eax, eax
0x140003711  jnz     short loc_14000372A
0x140003713  inc     ebp
0x140003715  test    rbx, rbx
0x140003718  jnz     short loc_14000375F
0x14000371a  lea     r12d, [rbx+2]
0x14000371e  jmp     short loc_1400036F6
0x140003720  inc     edi
0x140003722  cmp     edi, cs:PptpWanEndpoints
0x140003728  jge     short loc_140003713
0x14000372a  mov     rax, [rsi]
0x14000372d  movsxd  r12, edi
0x140003730  cmp     qword ptr [rax+r12*8], 0
0x140003735  jnz     short loc_140003702
0x140003737  mov     rcx, r14
0x14000373a  call    CallAlloc
0x14000373f  mov     rbx, rax
0x140003742  test    rax, rax
0x140003745  jz      short loc_140003702
0x140003747  mov     rax, [rsi]
0x14000374a  mov     [rax+r12*8], rbx
0x14000374e  mov     eax, edi
0x140003750  mov     [rbx+0C8h], rax
0x140003757  mov     rcx, rbx
0x14000375a  call    CallSetFullCallId
0x14000375f  lock inc dword ptr [rbx]
0x140003762  mov     r12d, 2
0x140003768  mov     dl, [r14+10h]; NewIrql
0x14000376c  lea     rcx, [r14+8]; SpinLock
0x140003770  call    cs:__imp_KeReleaseSpinLock
0x140003777  nop     dword ptr [rax+rax+00h]
0x14000377c  test    rbx, rbx
0x14000377f  jz      short loc_1400037D4
0x140003781  mov     rcx, cs:WPP_GLOBAL_Control
0x140003788  lea     rax, WPP_GLOBAL_Control
0x14000378f  cmp     rcx, rax
0x140003792  jz      short loc_1400037BD
0x140003794  mov     eax, [rcx+2Ch]
0x140003797  test    al, 10h
0x140003799  jz      short loc_1400037BD
0x14000379b  cmp     [rcx+29h], r12b
0x14000379f  jb      short loc_1400037BD
0x1400037a1  mov     r9d, [rbx+0C8h]
0x1400037a8  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x1400037af  mov     rcx, [rcx+18h]
0x1400037b3  mov     edx, 25h ; '%'
0x1400037b8  call    WPP_SF_d
0x1400037bd  lea     rcx, [rbx+60h]; SpinLock
0x1400037c1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400037c8  nop     dword ptr [rax+rax+00h]
0x1400037cd  mov     [rbx+68h], al
0x1400037d0  mov     [rbx+70h], r12d
0x1400037d4  mov     rax, rbx
0x1400037d7  add     rsp, 28h
0x1400037db  pop     r15
0x1400037dd  pop     r14
0x1400037df  pop     r13
0x1400037e1  pop     r12
0x1400037e3  pop     rdi
0x1400037e4  pop     rsi
0x1400037e5  pop     rbp
0x1400037e6  pop     rbx
0x1400037e7  retn
0x1400037e9  test    r13d, r13d
0x1400037ec  jnz     loc_140003768
0x1400037f2  mov     ecx, cs:PptpWanEndpoints
0x1400037f8  cmp     ecx, 3FF6h
0x1400037fe  ja      loc_140003768
0x140003804  lea     ecx, ds:50h[rcx*8]
0x14000380b  mov     edx, 63505450h
0x140003810  call    MyMemAlloc
0x140003815  mov     rbp, rax
0x140003818  test    rax, rax
0x14000381b  jz      loc_140003768
0x140003821  mov     r8d, cs:PptpWanEndpoints
0x140003828  mov     rcx, rax; void *
0x14000382b  mov     rdx, [rsi]; Src
0x14000382e  shl     r8, 3; Size
0x140003832  call    memmove
0x140003837  mov     rcx, [rsi]; P
0x14000383a  xor     edx, edx; Tag
0x14000383c  call    cs:__imp_ExFreePoolWithTag
0x140003843  nop     dword ptr [rax+rax+00h]
0x140003848  mov     eax, cs:PptpWanEndpoints
0x14000384e  add     eax, 0Ah
0x140003851  mov     [rsi], rbp
0x140003854  mov     cs:PptpWanEndpoints, eax
0x14000385a  mov     [r14+48h], eax
0x14000385e  call    InitCallLayer
0x140003863  mov     r13d, 1
0x140003869  jmp     loc_14000367A
0x14000386e  mov     rax, [rsi]
0x140003871  mov     [rax+r15*8], rbx
0x140003875  mov     [rbx+0C8h], r15
0x14000387c  jmp     loc_140003757
```
