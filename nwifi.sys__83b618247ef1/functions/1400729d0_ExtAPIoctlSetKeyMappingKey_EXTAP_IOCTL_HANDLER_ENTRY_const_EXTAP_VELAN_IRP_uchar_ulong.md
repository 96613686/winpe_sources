# ExtAPIoctlSetKeyMappingKey(_EXTAP_IOCTL_HANDLER_ENTRY const *,_EXTAP_VELAN *,_IRP *,uchar *,ulong)

- ea: `0x1400729d0`
- end: `0x140072cb9`
- name: `?ExtAPIoctlSetKeyMappingKey@@YAHPEBU_EXTAP_IOCTL_HANDLER_ENTRY@@PEAU_EXTAP_VELAN@@PEAU_IRP@@PEAEK@Z`
- size: `745`
- prototype: `__int64 __fastcall(const struct _EXTAP_IOCTL_HANDLER_ENTRY *, struct _EXTAP_VELAN *, struct _IRP *, unsigned __int8 *, unsigned int Size)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d22c`
- `0x140019bbc`
- `0x140020dc0`
- `0x1400729d0`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140072b3b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140072b3b`
- `ntoskrnl!ExAllocatePool2` at `0x140072b50`
- `ntoskrnl!ExAllocatePool2` at `0x140072b50`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140072c5b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140072c5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072c72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072c72`

## pseudocode

```c
__int64 __fastcall ExtAPIoctlSetKeyMappingKey(
        const struct _EXTAP_IOCTL_HANDLER_ENTRY *a1,
        struct _EXTAP_VELAN *a2,
        struct _IRP *a3,
        unsigned __int8 *a4,
        unsigned int Size)
{
  unsigned int v7; // ebx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  unsigned int v11; // ecx
  unsigned int v12; // r15d
  unsigned int v13; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v16; // rdi
  _DWORD *v17; // r14
  size_t v18; // r8
  unsigned int v19; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
  if ( *(_DWORD *)a4 != 1 )
  {
    v7 = -1073741811;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_7;
    v9 = 105;
    goto LABEL_6;
  }
  v11 = *((_DWORD *)a4 + 9);
  if ( Size - 40 < v11 )
  {
    v7 = -1073741811;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v9 = 106;
LABEL_6:
      WPP_SF_(v8->AttachedDevice, v9, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
      goto LABEL_7;
    }
    goto LABEL_7;
  }
  if ( v11 <= 0xFFFF )
  {
    v12 = v11 + 32;
    v13 = v11 + 48;
    if ( v11 + 48 < 0x10 )
    {
LABEL_34:
      v7 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
      goto LABEL_7;
    }
    if ( v13 > 0x40 )
    {
      if ( v13 > 0x100 )
      {
        if ( v13 > 0x400 )
        {
          if ( v13 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v13, 808464432, a4);
LABEL_27:
            v16 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
            if ( Pool2 )
            {
              Pool2[2] = 808464432;
              v17 = Pool2 + 4;
              *(_QWORD *)Pool2 = p_WaitListHead;
              memset(Pool2 + 4, 0, v12);
              *v17 = 1048960;
              v17[1] = v12 - 12;
              v17[2] = v12 - 12;
              v17[3] = *((_DWORD *)a4 + 3);
              *((_WORD *)v17 + 8) = *((_WORD *)a4 + 8);
              *((_BYTE *)v17 + 28) = *((_DWORD *)a4 + 8) != 1;
              v17[5] = *((_DWORD *)a4 + 5);
              v17[6] = *((_DWORD *)a4 + 6);
              *((_BYTE *)v17 + 29) = *((_DWORD *)a4 + 7) != 0;
              v18 = *((unsigned __int16 *)a4 + 18);
              *((_WORD *)v17 + 15) = *((_WORD *)a4 + 18);
              memmove(v17 + 8, a4 + 40, v18);
              v19 = PtRequestAdapterSync(a2->pVElan->pAdapt, 1u, *((_DWORD *)a1 + 2), v17, v12);
              v7 = v19;
              if ( v19 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 109, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, v19);
              memset(v17, 0, v12);
              if ( *v16 )
                ExFreeToNPagedLookasideList(*v16, v16);
              else
                ExFreePoolWithTag(v16, *((_DWORD *)v16 + 2));
              goto LABEL_7;
            }
            goto LABEL_34;
          }
          p_WaitListHead = &stru_1400B0180;
        }
        else
        {
          p_WaitListHead = &Lookaside;
        }
      }
      else
      {
        p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_27;
  }
  v7 = -1073741811;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    v9 = 107;
    goto LABEL_6;
  }
LABEL_7:
  memset(a4, 0, Size);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 110, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x1400729d0  mov     [rsp+arg_0], rcx
0x1400729d5  push    rbx
0x1400729d6  push    rbp
0x1400729d7  push    rsi
0x1400729d8  push    rdi
0x1400729d9  push    r12
0x1400729db  push    r13
0x1400729dd  push    r14
0x1400729df  push    r15
0x1400729e1  sub     rsp, 38h
0x1400729e5  mov     rsi, r9
0x1400729e8  mov     r13, rdx
0x1400729eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400729f2  lea     rdx, WPP_GLOBAL_Control
0x1400729f9  cmp     rcx, rdx
0x1400729fc  jz      short loc_140072A1A
0x1400729fe  mov     rcx, [rcx+18h]
0x140072a02  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140072a09  mov     edx, 68h ; 'h'
0x140072a0e  call    WPP_SF_
0x140072a13  lea     rdx, WPP_GLOBAL_Control
0x140072a1a  cmp     dword ptr [rsi], 1
0x140072a1d  mov     ebp, dword ptr [rsp+78h+Size]
0x140072a24  jz      short loc_140072A98
0x140072a26  mov     ebx, 0C000000Dh
0x140072a2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140072a32  cmp     rcx, rdx
0x140072a35  jz      short loc_140072A4C
0x140072a37  mov     edx, 69h ; 'i'
0x140072a3c  mov     rcx, [rcx+18h]
0x140072a40  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140072a47  call    WPP_SF_
0x140072a4c  lea     r15, WPP_GLOBAL_Control
0x140072a53  mov     r8, rbp; Size
0x140072a56  xor     edx, edx; Val
0x140072a58  mov     rcx, rsi; void *
0x140072a5b  call    memset
0x140072a60  mov     rcx, cs:WPP_GLOBAL_Control
0x140072a67  cmp     rcx, r15
0x140072a6a  jz      short loc_140072A84
0x140072a6c  mov     rcx, [rcx+18h]
0x140072a70  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140072a77  mov     edx, 6Eh ; 'n'
0x140072a7c  mov     r9d, ebx
0x140072a7f  call    WPP_SF_d
0x140072a84  mov     eax, ebx
0x140072a86  add     rsp, 38h
0x140072a8a  pop     r15
0x140072a8c  pop     r14
0x140072a8e  pop     r13
0x140072a90  pop     r12
0x140072a92  pop     rdi
0x140072a93  pop     rsi
0x140072a94  pop     rbp
0x140072a95  pop     rbx
0x140072a96  retn
0x140072a98  mov     ecx, [rsi+24h]
0x140072a9b  lea     eax, [rbp-28h]
0x140072a9e  cmp     eax, ecx
0x140072aa0  jnb     short loc_140072ABA
0x140072aa2  mov     ebx, 0C000000Dh
0x140072aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x140072aae  cmp     rcx, rdx
0x140072ab1  jz      short loc_140072A4C
0x140072ab3  mov     edx, 6Ah ; 'j'
0x140072ab8  jmp     short loc_140072A3C
0x140072aba  cmp     ecx, 0FFFFh
0x140072ac0  jbe     short loc_140072AE1
0x140072ac2  mov     ebx, 0C000000Dh
0x140072ac7  mov     rcx, cs:WPP_GLOBAL_Control
0x140072ace  cmp     rcx, rdx
0x140072ad1  jz      loc_140072A4C
0x140072ad7  mov     edx, 6Bh ; 'k'
0x140072adc  jmp     loc_140072A3C
0x140072ae1  lea     r15d, [rcx+20h]
0x140072ae5  lea     eax, [r15+10h]
0x140072ae9  cmp     eax, 10h
0x140072aec  jb      loc_140072C83
0x140072af2  mov     ecx, 40h ; '@'
0x140072af7  mov     r14d, 30303030h
0x140072afd  cmp     eax, ecx
0x140072aff  ja      short loc_140072B0A
0x140072b01  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140072b08  jmp     short loc_140072B38
0x140072b0a  cmp     eax, 100h
0x140072b0f  ja      short loc_140072B1A
0x140072b11  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140072b18  jmp     short loc_140072B38
0x140072b1a  cmp     eax, 400h
0x140072b1f  ja      short loc_140072B2A
0x140072b21  lea     rbx, Lookaside
0x140072b28  jmp     short loc_140072B38
0x140072b2a  cmp     eax, 800h
0x140072b2f  ja      short loc_140072B49
0x140072b31  lea     rbx, stru_1400B0180
0x140072b38  mov     rcx, rbx; Lookaside
0x140072b3b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140072b42  nop     dword ptr [rax+rax+00h]
0x140072b47  jmp     short loc_140072B5C
0x140072b49  xor     ebx, ebx
0x140072b4b  mov     edx, eax
0x140072b4d  mov     r8d, r14d
0x140072b50  call    cs:__imp_ExAllocatePool2
0x140072b57  nop     dword ptr [rax+rax+00h]
0x140072b5c  mov     rdi, rax
0x140072b5f  test    rax, rax
0x140072b62  jz      loc_140072C83
0x140072b68  mov     [rax+8], r14d
0x140072b6c  xor     edx, edx; Val
0x140072b6e  lea     r14, [rax+10h]
0x140072b72  mov     r8d, r15d; Size
0x140072b75  mov     rcx, r14; void *
0x140072b78  mov     [rax], rbx
0x140072b7b  mov     r12d, r15d
0x140072b7e  call    memset
0x140072b83  mov     dword ptr [r14], 100180h
0x140072b8a  lea     eax, [r15-0Ch]
0x140072b8e  mov     [r14+4], eax
0x140072b92  lea     rdx, [rsi+28h]; Src
0x140072b96  mov     [r14+8], eax
0x140072b9a  lea     rcx, [r14+20h]; void *
0x140072b9e  mov     eax, [rsi+0Ch]
0x140072ba1  mov     [r14+0Ch], eax
0x140072ba5  movzx   eax, word ptr [rsi+10h]
0x140072ba9  mov     [r14+10h], ax
0x140072bae  cmp     dword ptr [rsi+20h], 1
0x140072bb2  setnz   al
0x140072bb5  mov     [r14+1Ch], al
0x140072bb9  mov     eax, [rsi+14h]
0x140072bbc  mov     [r14+14h], eax
0x140072bc0  mov     eax, [rsi+18h]
0x140072bc3  mov     [r14+18h], eax
0x140072bc7  cmp     dword ptr [rsi+1Ch], 0
0x140072bcb  setnz   al
0x140072bce  mov     [r14+1Dh], al
0x140072bd2  movzx   eax, word ptr [rsi+24h]
0x140072bd6  mov     r8d, eax; Size
0x140072bd9  mov     [r14+1Eh], ax
0x140072bde  call    memmove
0x140072be3  mov     rcx, [r13+0]
0x140072be7  mov     r9, r14; void *
0x140072bea  mov     r8, [rsp+78h+arg_0]
0x140072bf2  mov     edx, 1; unsigned int
0x140072bf7  mov     [rsp+78h+var_58], r15d; unsigned int
0x140072bfc  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140072c00  mov     r8d, [r8+8]; unsigned int
0x140072c04  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140072c09  mov     ebx, eax
0x140072c0b  test    eax, eax
0x140072c0d  jz      short loc_140072C3C
0x140072c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140072c16  lea     r15, WPP_GLOBAL_Control
0x140072c1d  cmp     rcx, r15
0x140072c20  jz      short loc_140072C43
0x140072c22  mov     rcx, [rcx+18h]
0x140072c26  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140072c2d  mov     edx, 6Dh ; 'm'
0x140072c32  mov     r9d, eax
0x140072c35  call    WPP_SF_d
0x140072c3a  jmp     short loc_140072C43
0x140072c3c  lea     r15, WPP_GLOBAL_Control
0x140072c43  mov     r8, r12; Size
0x140072c46  xor     edx, edx; Val
0x140072c48  mov     rcx, r14; void *
0x140072c4b  call    memset
0x140072c50  mov     rcx, [rdi]; Lookaside
0x140072c53  test    rcx, rcx
0x140072c56  jz      short loc_140072C6C
0x140072c58  mov     rdx, rdi; Entry
0x140072c5b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140072c62  nop     dword ptr [rax+rax+00h]
0x140072c67  jmp     loc_140072A53
0x140072c6c  mov     edx, [rdi+8]; Tag
0x140072c6f  mov     rcx, rdi; P
0x140072c72  call    cs:__imp_ExFreePoolWithTag
0x140072c79  nop     dword ptr [rax+rax+00h]
0x140072c7e  jmp     loc_140072A53
0x140072c83  mov     ebx, 0C000009Ah
0x140072c88  mov     rcx, cs:WPP_GLOBAL_Control
0x140072c8f  lea     r15, WPP_GLOBAL_Control
0x140072c96  cmp     rcx, r15
0x140072c99  jz      loc_140072A53
0x140072c9f  mov     rcx, [rcx+18h]
0x140072ca3  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140072caa  mov     edx, 6Ch ; 'l'
0x140072caf  call    WPP_SF_
0x140072cb4  jmp     loc_140072A53
```
