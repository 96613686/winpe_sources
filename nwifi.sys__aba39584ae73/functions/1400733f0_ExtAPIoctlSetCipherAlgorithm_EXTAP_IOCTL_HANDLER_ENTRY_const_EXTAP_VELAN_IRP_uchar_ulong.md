# ExtAPIoctlSetCipherAlgorithm(_EXTAP_IOCTL_HANDLER_ENTRY const *,_EXTAP_VELAN *,_IRP *,uchar *,ulong)

- ea: `0x1400733f0`
- end: `0x1400736b3`
- name: `?ExtAPIoctlSetCipherAlgorithm@@YAHPEBU_EXTAP_IOCTL_HANDLER_ENTRY@@PEAU_EXTAP_VELAN@@PEAU_IRP@@PEAEK@Z`
- size: `707`
- prototype: `__int64 __fastcall(const struct _EXTAP_IOCTL_HANDLER_ENTRY *, struct _EXTAP_VELAN *, struct _IRP *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d21c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140020f20`
- `0x1400733f0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400734cb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400734cb`
- `ntoskrnl!ExAllocatePool2` at `0x1400734e3`
- `ntoskrnl!ExAllocatePool2` at `0x1400734e3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140073626`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140073626`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073637`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073637`

## pseudocode

```c
__int64 __fastcall ExtAPIoctlSetCipherAlgorithm(
        const struct _EXTAP_IOCTL_HANDLER_ENTRY *a1,
        struct _EXTAP_VELAN *a2,
        struct _IRP *a3,
        unsigned __int8 *a4,
        unsigned int a5)
{
  int v8; // r8d
  unsigned int v9; // esi
  unsigned int v10; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  _DWORD *v13; // rbx
  __int64 v14; // r8
  unsigned int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // r9
  __int64 v18; // rax
  unsigned int v19; // esi
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
  v8 = *(_DWORD *)a4;
  if ( (a5 - 8) / 0xC >= *(_DWORD *)a4 && *((_DWORD *)a4 + 1) == v8 && v8 )
  {
    v9 = 4 * v8 + 12;
    v10 = 4 * v8 + 28;
    if ( v10 < 0x10 )
    {
LABEL_35:
      v16 = -1073741670;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v16;
      v21 = 73;
      goto LABEL_39;
    }
    if ( v10 > 0x40 )
    {
      if ( v10 > 0x100 )
      {
        if ( v10 > 0x400 )
        {
          if ( v10 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v10, 808464432);
LABEL_17:
            if ( Pool2 )
            {
              *(_QWORD *)Pool2 = p_WaitListHead;
              v13 = Pool2 + 4;
              Pool2[2] = 808464432;
              memset(Pool2 + 4, 0, v9);
              *v13 = 1048960;
              v14 = 0;
              v13[1] = *(_DWORD *)a4;
              for ( v13[2] = *(_DWORD *)a4; (unsigned int)v14 < *(_DWORD *)a4; v14 = (unsigned int)(v14 + 1) )
                v13[v14 + 3] = *(_DWORD *)&a4[12 * v14 + 12];
              v15 = PtRequestAdapterSync(a2->pVElan->pAdapt, 1u, *((_DWORD *)a1 + 2), v13, v9);
              v16 = v15;
              if ( v15 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, v15);
              }
              else
              {
                v17 = (unsigned int)v13[2];
                if ( (_DWORD)v17 == 1 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      75,
                      WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids,
                      (unsigned int)v13[3]);
                }
                else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, v17);
                  v18 = 0;
                  if ( v13[2] )
                  {
                    do
                    {
                      v19 = v18 + 1;
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        WPP_SF_Dd(
                          WPP_GLOBAL_Control->AttachedDevice,
                          77,
                          WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids,
                          v19,
                          v13[v18 + 3]);
                      v18 = v19;
                    }
                    while ( v19 < v13[2] );
                  }
                }
                a2->LastSetUcastCipher = v13[3];
              }
              if ( *((_QWORD *)v13 - 2) )
                ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 - 2), v13 - 4);
              else
                ExFreePoolWithTag(v13 - 4, *(v13 - 2));
              goto LABEL_40;
            }
            goto LABEL_35;
          }
          p_WaitListHead = &stru_1400B31C0;
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
    goto LABEL_17;
  }
  v16 = -1073741811;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return v16;
  v21 = 72;
LABEL_39:
  WPP_SF_(v20->AttachedDevice, v21, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
LABEL_40:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, v16);
  return v16;
}

```

## disassembly

```asm
0x1400733f0  push    rbx
0x1400733f2  push    rbp
0x1400733f3  push    rsi
0x1400733f4  push    rdi
0x1400733f5  push    r12
0x1400733f7  push    r13
0x1400733f9  push    r14
0x1400733fb  push    r15
0x1400733fd  sub     rsp, 38h
0x140073401  mov     rdi, r9
0x140073404  mov     r14, rdx
0x140073407  mov     rbp, rcx
0x14007340a  mov     rcx, cs:WPP_GLOBAL_Control
0x140073411  lea     r15, WPP_GLOBAL_Control
0x140073418  lea     r12, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x14007341f  cmp     rcx, r15
0x140073422  jz      short loc_140073435
0x140073424  mov     rcx, [rcx+18h]
0x140073428  mov     edx, 47h ; 'G'
0x14007342d  mov     r8, r12
0x140073430  call    WPP_SF_
0x140073435  mov     ecx, [rsp+78h+arg_20]
0x14007343c  mov     rax, 0AAAAAAAAAAAAAAABh
0x140073446  mov     r8d, [rdi]
0x140073449  add     ecx, 0FFFFFFF8h
0x14007344c  mul     rcx
0x14007344f  shr     rdx, 3
0x140073453  cmp     edx, r8d
0x140073456  jb      loc_14007365D
0x14007345c  cmp     [rdi+4], r8d
0x140073460  jnz     loc_14007365D
0x140073466  test    r8d, r8d
0x140073469  jz      loc_14007365D
0x14007346f  lea     esi, ds:0Ch[r8*4]
0x140073477  mov     r13d, 10h
0x14007347d  lea     eax, [rsi+10h]
0x140073480  cmp     eax, r13d
0x140073483  jb      loc_140073645
0x140073489  lea     ecx, [r13+30h]
0x14007348d  cmp     eax, ecx
0x14007348f  ja      short loc_14007349A
0x140073491  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140073498  jmp     short loc_1400734C8
0x14007349a  cmp     eax, 100h
0x14007349f  ja      short loc_1400734AA
0x1400734a1  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400734a8  jmp     short loc_1400734C8
0x1400734aa  cmp     eax, 400h
0x1400734af  ja      short loc_1400734BA
0x1400734b1  lea     rbx, Lookaside
0x1400734b8  jmp     short loc_1400734C8
0x1400734ba  cmp     eax, 800h
0x1400734bf  ja      short loc_1400734D9
0x1400734c1  lea     rbx, stru_1400B31C0
0x1400734c8  mov     rcx, rbx; Lookaside
0x1400734cb  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400734d2  nop     dword ptr [rax+rax+00h]
0x1400734d7  jmp     short loc_1400734EF
0x1400734d9  xor     ebx, ebx
0x1400734db  mov     edx, eax
0x1400734dd  mov     r8d, 30303030h
0x1400734e3  call    cs:__imp_ExAllocatePool2
0x1400734ea  nop     dword ptr [rax+rax+00h]
0x1400734ef  test    rax, rax
0x1400734f2  jz      loc_140073645
0x1400734f8  mov     [rax], rbx
0x1400734fb  xor     edx, edx; Val
0x1400734fd  lea     rbx, [rax+10h]
0x140073501  mov     r8d, esi; Size
0x140073504  mov     rcx, rbx; void *
0x140073507  mov     dword ptr [rax+8], 30303030h
0x14007350e  call    memset
0x140073513  mov     dword ptr [rbx], 100180h
0x140073519  xor     r8d, r8d
0x14007351c  mov     eax, [rdi]
0x14007351e  mov     [rbx+4], eax
0x140073521  mov     eax, [rdi]
0x140073523  mov     [rbx+8], eax
0x140073526  cmp     [rdi], r8d
0x140073529  jbe     short loc_140073540
0x14007352b  lea     rax, [r8+r8*2]
0x14007352f  mov     ecx, [rdi+rax*4+0Ch]
0x140073533  mov     [rbx+r8*4+0Ch], ecx
0x140073538  inc     r8d
0x14007353b  cmp     r8d, [rdi]
0x14007353e  jb      short loc_14007352B
0x140073540  mov     rcx, [r14]
0x140073543  mov     r9, rbx; void *
0x140073546  mov     r8d, [rbp+8]; unsigned int
0x14007354a  mov     edx, 1; unsigned int
0x14007354f  mov     [rsp+78h+var_58], esi; unsigned int
0x140073553  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140073557  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14007355c  mov     edi, eax
0x14007355e  test    eax, eax
0x140073560  jz      short loc_14007358B
0x140073562  mov     rcx, cs:WPP_GLOBAL_Control
0x140073569  cmp     rcx, r15
0x14007356c  jz      loc_140073614
0x140073572  mov     rcx, [rcx+18h]
0x140073576  mov     edx, 4Ah ; 'J'
0x14007357b  mov     r9d, eax
0x14007357e  mov     r8, r12
0x140073581  call    WPP_SF_d
0x140073586  jmp     loc_140073614
0x14007358b  mov     r9d, [rbx+8]
0x14007358f  cmp     r9d, 1
0x140073593  jnz     short loc_1400735B7
0x140073595  mov     rcx, cs:WPP_GLOBAL_Control
0x14007359c  cmp     rcx, r15
0x14007359f  jz      short loc_14007360D
0x1400735a1  mov     rcx, [rcx+18h]
0x1400735a5  lea     edx, [r9+4Ah]
0x1400735a9  mov     r9d, [rbx+0Ch]
0x1400735ad  mov     r8, r12
0x1400735b0  call    WPP_SF_d
0x1400735b5  jmp     short loc_14007360D
0x1400735b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400735be  cmp     rcx, r15
0x1400735c1  jz      short loc_14007360D
0x1400735c3  mov     rcx, [rcx+18h]
0x1400735c7  mov     edx, 4Ch ; 'L'
0x1400735cc  mov     r8, r12
0x1400735cf  call    WPP_SF_d
0x1400735d4  xor     eax, eax
0x1400735d6  cmp     [rbx+8], eax
0x1400735d9  jbe     short loc_14007360D
0x1400735db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400735e2  lea     esi, [rax+1]
0x1400735e5  cmp     rcx, r15
0x1400735e8  jz      short loc_140073606
0x1400735ea  mov     eax, [rbx+rax*4+0Ch]
0x1400735ee  mov     edx, 4Dh ; 'M'
0x1400735f3  mov     rcx, [rcx+18h]
0x1400735f7  mov     r9d, esi
0x1400735fa  mov     r8, r12
0x1400735fd  mov     [rsp+78h+var_58], eax
0x140073601  call    WPP_SF_Dd
0x140073606  mov     eax, esi
0x140073608  cmp     eax, [rbx+8]
0x14007360b  jb      short loc_1400735DB
0x14007360d  mov     eax, [rbx+0Ch]
0x140073610  mov     [r14+74h], eax
0x140073614  lea     rcx, [rbx-10h]; P
0x140073618  mov     rax, [rcx]
0x14007361b  test    rax, rax
0x14007361e  jz      short loc_140073634
0x140073620  mov     rdx, rcx; Entry
0x140073623  mov     rcx, rax; Lookaside
0x140073626  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007362d  nop     dword ptr [rax+rax+00h]
0x140073632  jmp     short loc_14007367F
0x140073634  mov     edx, [rcx+8]; Tag
0x140073637  call    cs:__imp_ExFreePoolWithTag
0x14007363e  nop     dword ptr [rax+rax+00h]
0x140073643  jmp     short loc_14007367F
0x140073645  mov     edi, 0C000009Ah
0x14007364a  mov     rcx, cs:WPP_GLOBAL_Control
0x140073651  cmp     rcx, r15
0x140073654  jz      short loc_14007369F
0x140073656  mov     edx, 49h ; 'I'
0x14007365b  jmp     short loc_140073673
0x14007365d  mov     edi, 0C000000Dh
0x140073662  mov     rcx, cs:WPP_GLOBAL_Control
0x140073669  cmp     rcx, r15
0x14007366c  jz      short loc_14007369F
0x14007366e  mov     edx, 48h ; 'H'
0x140073673  mov     rcx, [rcx+18h]
0x140073677  mov     r8, r12
0x14007367a  call    WPP_SF_
0x14007367f  mov     rcx, cs:WPP_GLOBAL_Control
0x140073686  cmp     rcx, r15
0x140073689  jz      short loc_14007369F
0x14007368b  mov     rcx, [rcx+18h]
0x14007368f  mov     edx, 4Eh ; 'N'
0x140073694  mov     r9d, edi
0x140073697  mov     r8, r12
0x14007369a  call    WPP_SF_d
0x14007369f  mov     eax, edi
0x1400736a1  add     rsp, 38h
0x1400736a5  pop     r15
0x1400736a7  pop     r14
0x1400736a9  pop     r13
0x1400736ab  pop     r12
0x1400736ad  pop     rdi
0x1400736ae  pop     rsi
0x1400736af  pop     rbp
0x1400736b0  pop     rbx
0x1400736b1  retn
```
