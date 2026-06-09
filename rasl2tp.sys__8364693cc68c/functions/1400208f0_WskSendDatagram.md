# WskSendDatagram

- ea: `0x1400208f0`
- end: `0x140020c12`
- name: `WskSendDatagram`
- size: `802`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001b1e0`
- `0x14001c1b0`

## callees

- `0x140004830`
- `0x1400208f0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400209b4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400209b4`
- `ntoskrnl!ExAllocatePool3` at `0x140020a1b`
- `ntoskrnl!ExAllocatePool3` at `0x140020b4f`
- `ntoskrnl!ExAllocatePool3` at `0x140020a1b`
- `ntoskrnl!ExAllocatePool3` at `0x140020b4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020c01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020c01`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140020bd0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140020bd0`
- `ntoskrnl!IoFreeIrp` at `0x140020be4`
- `ntoskrnl!IoFreeIrp` at `0x140020be4`
- `ntoskrnl!IoAllocateIrp` at `0x140020995`
- `ntoskrnl!IoAllocateIrp` at `0x140020995`

## pseudocode

```c
__int64 __fastcall WskSendDatagram(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7)
{
  PIRP Irp; // rsi
  _QWORD *v12; // rdi
  __int64 v13; // r12
  void *v14; // r14
  _OWORD *v15; // rax
  int v16; // r13d
  __int64 Pool3; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int v19; // ebp
  __int64 v21; // rax
  __int64 v22; // [rsp+40h] [rbp-68h]
  _QWORD v23[2]; // [rsp+48h] [rbp-60h] BYREF
  __int128 v24; // [rsp+58h] [rbp-50h] BYREF
  __int64 v25; // [rsp+68h] [rbp-40h]
  int v26; // [rsp+B0h] [rbp+8h]
  unsigned int v28; // [rsp+E0h] [rbp+38h]

  v23[1] = 16;
  v24 = 0;
  v25 = 0;
  v23[0] = 1;
  if ( *(_QWORD *)(a1 + 64) )
  {
    Irp = 0;
    v12 = 0;
    v13 = *(_QWORD *)(a7 + 8);
    v14 = 0;
    if ( (*(_DWORD *)(a1 + 392) & 0x20) != 0 )
    {
      if ( !a2 )
      {
        v19 = -1073741811;
LABEL_18:
        (*(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64, unsigned int))(a1 + 64))(
          *(_QWORD *)(a1 + 8),
          a4,
          a5,
          a6,
          v13,
          v19);
        if ( v12 )
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 256), v12);
        if ( Irp )
          IoFreeIrp(Irp);
        if ( v14 )
          ExFreePoolWithTag(v14, 0x6D636177u);
        return v19;
      }
      v28 = *(_DWORD *)(a7 + 24);
      v26 = *(_DWORD *)(a7 + 16);
      v22 = *(_QWORD *)(a1 + 384);
      Irp = IoAllocateIrp(1, 0);
      if ( Irp )
      {
        v15 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 256));
        v12 = v15;
        if ( v15 )
        {
          v16 = 0;
          *v15 = 0;
          v15[1] = 0;
          v15[2] = 0;
          v15[3] = 0;
          if ( !a3 )
            goto LABEL_11;
          if ( *(_WORD *)a3 != 23 )
          {
            if ( *(_WORD *)a3 == 2 )
            {
              v16 = 24;
              Pool3 = ExAllocatePool3(64, 24, 1835229559, v23, 1);
              v14 = (void *)Pool3;
              if ( Pool3 )
              {
                *(_QWORD *)Pool3 = 24;
                *(_DWORD *)(Pool3 + 8) = 0;
                *(_DWORD *)(Pool3 + 12) = 19;
                *(_DWORD *)(Pool3 + 16) = *(_DWORD *)(a3 + 4);
                *(_DWORD *)(Pool3 + 20) = *(_DWORD *)(a3 + 28);
                goto LABEL_11;
              }
              goto LABEL_17;
            }
LABEL_11:
            v12[2] = a5;
            *((_DWORD *)v12 + 6) = a6;
            *v12 = a1;
            v12[4] = v13;
            v12[1] = a4;
            v12[5] = v14;
            *((_DWORD *)v12 + 12) = v16;
            _InterlockedIncrement((volatile signed __int32 *)(a1 + 512));
            CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
            CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskSendCompletion;
            CurrentStackLocation[-1].Context = v12;
            CurrentStackLocation[-1].Control = -32;
            v25 = v28;
            DWORD2(v24) = v26;
            *(_QWORD *)&v24 = v13;
            return (*(unsigned int (__fastcall **)(__int64, __int128 *, _QWORD, __int64, int, void *, PIRP))(*(_QWORD *)v22 + 24LL))(
                     v22,
                     &v24,
                     0,
                     a2,
                     v16,
                     v14,
                     Irp);
          }
          v16 = 40;
          v21 = ExAllocatePool3(64, 40, 1835229559, v23, 1);
          v14 = (void *)v21;
          if ( v21 )
          {
            *(_QWORD *)v21 = 36;
            *(_DWORD *)(v21 + 8) = 41;
            *(_DWORD *)(v21 + 12) = 19;
            *(_OWORD *)(v21 + 16) = *(_OWORD *)(a3 + 8);
            *(_DWORD *)(v21 + 32) = *(_DWORD *)(a3 + 28);
            goto LABEL_11;
          }
        }
      }
    }
LABEL_17:
    v19 = -1073741670;
    goto LABEL_18;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400208f0  mov     r11, rsp
0x1400208f3  mov     [r11+20h], r9
0x1400208f7  push    rbx
0x1400208f8  push    rbp
0x1400208f9  push    r15
0x1400208fb  sub     rsp, 90h
0x140020902  xor     eax, eax
0x140020904  mov     qword ptr [r11-58h], 10h
0x14002090c  xorps   xmm0, xmm0
0x14002090f  mov     r15, r8
0x140020912  mov     rbp, rdx
0x140020915  mov     rbx, rcx
0x140020918  movups  [rsp+0A8h+var_50], xmm0
0x14002091d  mov     [r11-40h], rax
0x140020921  mov     qword ptr [r11-60h], 1
0x140020929  cmp     [rcx+40h], rax
0x14002092d  jz      loc_140020B20
0x140020933  mov     rcx, [rsp+0A8h+arg_30]
0x14002093b  mov     eax, [rbx+188h]
0x140020941  mov     [r11+10h], rsi
0x140020945  xor     esi, esi
0x140020947  mov     [r11-20h], rdi
0x14002094b  xor     edi, edi
0x14002094d  mov     [r11-28h], r12
0x140020951  mov     r12, [rcx+8]
0x140020955  mov     [r11-30h], r13
0x140020959  mov     [r11-38h], r14
0x14002095d  xor     r14d, r14d
0x140020960  test    al, 20h
0x140020962  jz      loc_140020B8E
0x140020968  test    rdx, rdx
0x14002096b  jz      loc_140020B27
0x140020971  mov     eax, [rcx+18h]
0x140020974  xor     edx, edx; ChargeQuota
0x140020976  mov     dword ptr [rsp+0A8h+arg_30], eax
0x14002097d  mov     eax, [rcx+10h]
0x140020980  mov     cl, 1; StackSize
0x140020982  mov     [rsp+0A8h+arg_0], eax
0x140020989  mov     rax, [rbx+180h]
0x140020990  mov     [rsp+0A8h+var_68], rax
0x140020995  call    cs:__imp_IoAllocateIrp
0x14002099c  nop     dword ptr [rax+rax+00h]
0x1400209a1  mov     rsi, rax
0x1400209a4  test    rax, rax
0x1400209a7  jz      loc_140020B8E
0x1400209ad  lea     rcx, [rbx+100h]; Lookaside
0x1400209b4  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400209bb  nop     dword ptr [rax+rax+00h]
0x1400209c0  mov     rdi, rax
0x1400209c3  test    rax, rax
0x1400209c6  jz      loc_140020B8E
0x1400209cc  xorps   xmm0, xmm0
0x1400209cf  xor     r13d, r13d
0x1400209d2  movups  xmmword ptr [rax], xmm0
0x1400209d5  movups  xmmword ptr [rax+10h], xmm0
0x1400209d9  movups  xmmword ptr [rax+20h], xmm0
0x1400209dd  movups  xmmword ptr [rax+30h], xmm0
0x1400209e1  test    r15, r15
0x1400209e4  jz      short loc_140020A54
0x1400209e6  movzx   eax, word ptr [r15]
0x1400209ea  cmp     ax, 17h
0x1400209ee  jz      loc_140020B2E
0x1400209f4  cmp     ax, 2
0x1400209f8  jnz     short loc_140020A54
0x1400209fa  mov     r13d, 18h
0x140020a00  mov     dword ptr [rsp+0A8h+var_88], 1
0x140020a08  mov     edx, r13d
0x140020a0b  lea     r9, [rsp+0A8h+var_60]
0x140020a10  mov     r8d, 6D636177h
0x140020a16  mov     ecx, 40h ; '@'
0x140020a1b  call    cs:__imp_ExAllocatePool3
0x140020a22  nop     dword ptr [rax+rax+00h]
0x140020a27  mov     r14, rax
0x140020a2a  test    rax, rax
0x140020a2d  jz      loc_140020B8E
0x140020a33  mov     [rax], r13
0x140020a36  mov     dword ptr [rax+8], 0
0x140020a3d  mov     dword ptr [rax+0Ch], 13h
0x140020a44  mov     eax, [r15+4]
0x140020a48  mov     [r14+10h], eax
0x140020a4c  mov     eax, [r15+1Ch]
0x140020a50  mov     [r14+14h], eax
0x140020a54  mov     rax, [rsp+0A8h+arg_20]
0x140020a5c  mov     rcx, [rsp+0A8h+arg_18]
0x140020a64  mov     [rdi+10h], rax
0x140020a68  mov     eax, [rsp+0A8h+arg_28]
0x140020a6f  mov     [rdi+18h], eax
0x140020a72  mov     [rdi], rbx
0x140020a75  mov     [rdi+20h], r12
0x140020a79  mov     [rdi+8], rcx
0x140020a7d  mov     [rdi+28h], r14
0x140020a81  mov     [rdi+30h], r13d
0x140020a85  lock inc dword ptr [rbx+200h]
0x140020a8c  mov     rax, [rsi+0B8h]
0x140020a93  lea     rcx, WskSendCompletion
0x140020a9a  mov     [rsp+0A8h+var_78], rsi
0x140020a9f  lea     rdx, [rsp+0A8h+var_50]
0x140020aa4  mov     [rsp+0A8h+var_80], r14
0x140020aa9  mov     r9, rbp
0x140020aac  xor     r8d, r8d
0x140020aaf  mov     dword ptr [rsp+0A8h+var_88], r13d
0x140020ab4  mov     [rax-10h], rcx
0x140020ab8  mov     rcx, [rsp+0A8h+var_68]
0x140020abd  mov     [rax-8], rdi
0x140020ac1  mov     byte ptr [rax-45h], 0E0h
0x140020ac5  mov     eax, dword ptr [rsp+0A8h+arg_30]
0x140020acc  mov     [rsp+0A8h+var_40], rax
0x140020ad1  mov     eax, [rsp+0A8h+arg_0]
0x140020ad8  mov     dword ptr [rsp+0A8h+var_50+8], eax
0x140020adc  mov     qword ptr [rsp+0A8h+var_50], r12
0x140020ae1  mov     rax, [rcx]
0x140020ae4  mov     rax, [rax+18h]
0x140020ae8  call    _guard_dispatch_icall
0x140020aed  mov     ebp, eax
0x140020aef  mov     r14, [rsp+0A8h+var_38]
0x140020af4  mov     eax, ebp
0x140020af6  mov     r13, [rsp+0A8h+var_30]
0x140020afb  mov     r12, [rsp+0A8h+var_28]
0x140020b03  mov     rdi, [rsp+0A8h+var_20]
0x140020b0b  mov     rsi, [rsp+0A8h+arg_8]
0x140020b13  add     rsp, 90h
0x140020b1a  pop     r15
0x140020b1c  pop     rbp
0x140020b1d  pop     rbx
0x140020b1e  retn
0x140020b20  mov     eax, 0C000000Dh
0x140020b25  jmp     short loc_140020B13
0x140020b27  mov     ebp, 0C000000Dh
0x140020b2c  jmp     short loc_140020B93
0x140020b2e  mov     r13d, 28h ; '('
0x140020b34  mov     dword ptr [rsp+0A8h+var_88], 1
0x140020b3c  mov     edx, r13d
0x140020b3f  lea     r9, [rsp+0A8h+var_60]
0x140020b44  mov     r8d, 6D636177h
0x140020b4a  mov     ecx, 40h ; '@'
0x140020b4f  call    cs:__imp_ExAllocatePool3
0x140020b56  nop     dword ptr [rax+rax+00h]
0x140020b5b  mov     r14, rax
0x140020b5e  test    rax, rax
0x140020b61  jz      short loc_140020B8E
0x140020b63  mov     qword ptr [rax], 24h ; '$'
0x140020b6a  mov     dword ptr [rax+8], 29h ; ')'
0x140020b71  mov     dword ptr [rax+0Ch], 13h
0x140020b78  movups  xmm0, xmmword ptr [r15+8]
0x140020b7d  movups  xmmword ptr [rax+10h], xmm0
0x140020b81  mov     eax, [r15+1Ch]
0x140020b85  mov     [r14+20h], eax
0x140020b89  jmp     loc_140020A54
0x140020b8e  mov     ebp, 0C000009Ah
0x140020b93  mov     rax, [rbx+40h]
0x140020b97  mov     r9d, [rsp+0A8h+arg_28]
0x140020b9f  mov     r8, [rsp+0A8h+arg_20]
0x140020ba7  mov     rdx, [rsp+0A8h+arg_18]
0x140020baf  mov     rcx, [rbx+8]
0x140020bb3  mov     dword ptr [rsp+0A8h+var_80], ebp
0x140020bb7  mov     [rsp+0A8h+var_88], r12
0x140020bbc  call    _guard_dispatch_icall
0x140020bc1  test    rdi, rdi
0x140020bc4  jz      short loc_140020BDC
0x140020bc6  lea     rcx, [rbx+100h]; Lookaside
0x140020bcd  mov     rdx, rdi; Entry
0x140020bd0  call    cs:__imp_ExFreeToNPagedLookasideList
0x140020bd7  nop     dword ptr [rax+rax+00h]
0x140020bdc  test    rsi, rsi
0x140020bdf  jz      short loc_140020BF0
0x140020be1  mov     rcx, rsi; Irp
0x140020be4  call    cs:__imp_IoFreeIrp
0x140020beb  nop     dword ptr [rax+rax+00h]
0x140020bf0  test    r14, r14
0x140020bf3  jz      loc_140020AEF
0x140020bf9  mov     edx, 6D636177h; Tag
0x140020bfe  mov     rcx, r14; P
0x140020c01  call    cs:__imp_ExFreePoolWithTag
0x140020c08  nop     dword ptr [rax+rax+00h]
0x140020c0d  jmp     loc_140020AEF
```
