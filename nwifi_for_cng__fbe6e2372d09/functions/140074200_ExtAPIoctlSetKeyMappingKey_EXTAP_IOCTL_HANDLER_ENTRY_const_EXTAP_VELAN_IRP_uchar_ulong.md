# ExtAPIoctlSetKeyMappingKey(_EXTAP_IOCTL_HANDLER_ENTRY const *,_EXTAP_VELAN *,_IRP *,uchar *,ulong)

- ea: `0x140074200`
- end: `0x1400744e9`
- name: `?ExtAPIoctlSetKeyMappingKey@@YAHPEBU_EXTAP_IOCTL_HANDLER_ENTRY@@PEAU_EXTAP_VELAN@@PEAU_IRP@@PEAEK@Z`
- size: `745`
- prototype: `__int64 __fastcall(const struct _EXTAP_IOCTL_HANDLER_ENTRY *, struct _EXTAP_VELAN *, struct _IRP *, unsigned __int8 *, unsigned int Size)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d21c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140074200`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007436b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007436b`
- `ntoskrnl!ExAllocatePool2` at `0x140074380`
- `ntoskrnl!ExAllocatePool2` at `0x140074380`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007448b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007448b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400744a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400744a2`

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
            Pool2 = (_DWORD *)ExAllocatePool2(64, v13, 808464432);
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
0x140074200  mov     [rsp+arg_0], rcx
0x140074205  push    rbx
0x140074206  push    rbp
0x140074207  push    rsi
0x140074208  push    rdi
0x140074209  push    r12
0x14007420b  push    r13
0x14007420d  push    r14
0x14007420f  push    r15
0x140074211  sub     rsp, 38h
0x140074215  mov     rsi, r9
0x140074218  mov     r13, rdx
0x14007421b  mov     rcx, cs:WPP_GLOBAL_Control
0x140074222  lea     rdx, WPP_GLOBAL_Control
0x140074229  cmp     rcx, rdx
0x14007422c  jz      short loc_14007424A
0x14007422e  mov     rcx, [rcx+18h]
0x140074232  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140074239  mov     edx, 68h ; 'h'
0x14007423e  call    WPP_SF_
0x140074243  lea     rdx, WPP_GLOBAL_Control
0x14007424a  cmp     dword ptr [rsi], 1
0x14007424d  mov     ebp, dword ptr [rsp+78h+Size]
0x140074254  jz      short loc_1400742C8
0x140074256  mov     ebx, 0C000000Dh
0x14007425b  mov     rcx, cs:WPP_GLOBAL_Control
0x140074262  cmp     rcx, rdx
0x140074265  jz      short loc_14007427C
0x140074267  mov     edx, 69h ; 'i'
0x14007426c  mov     rcx, [rcx+18h]
0x140074270  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140074277  call    WPP_SF_
0x14007427c  lea     r15, WPP_GLOBAL_Control
0x140074283  mov     r8, rbp; Size
0x140074286  xor     edx, edx; Val
0x140074288  mov     rcx, rsi; void *
0x14007428b  call    memset
0x140074290  mov     rcx, cs:WPP_GLOBAL_Control
0x140074297  cmp     rcx, r15
0x14007429a  jz      short loc_1400742B4
0x14007429c  mov     rcx, [rcx+18h]
0x1400742a0  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x1400742a7  mov     edx, 6Eh ; 'n'
0x1400742ac  mov     r9d, ebx
0x1400742af  call    WPP_SF_d
0x1400742b4  mov     eax, ebx
0x1400742b6  add     rsp, 38h
0x1400742ba  pop     r15
0x1400742bc  pop     r14
0x1400742be  pop     r13
0x1400742c0  pop     r12
0x1400742c2  pop     rdi
0x1400742c3  pop     rsi
0x1400742c4  pop     rbp
0x1400742c5  pop     rbx
0x1400742c6  retn
0x1400742c8  mov     ecx, [rsi+24h]
0x1400742cb  lea     eax, [rbp-28h]
0x1400742ce  cmp     eax, ecx
0x1400742d0  jnb     short loc_1400742EA
0x1400742d2  mov     ebx, 0C000000Dh
0x1400742d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400742de  cmp     rcx, rdx
0x1400742e1  jz      short loc_14007427C
0x1400742e3  mov     edx, 6Ah ; 'j'
0x1400742e8  jmp     short loc_14007426C
0x1400742ea  cmp     ecx, 0FFFFh
0x1400742f0  jbe     short loc_140074311
0x1400742f2  mov     ebx, 0C000000Dh
0x1400742f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400742fe  cmp     rcx, rdx
0x140074301  jz      loc_14007427C
0x140074307  mov     edx, 6Bh ; 'k'
0x14007430c  jmp     loc_14007426C
0x140074311  lea     r15d, [rcx+20h]
0x140074315  lea     eax, [r15+10h]
0x140074319  cmp     eax, 10h
0x14007431c  jb      loc_1400744B3
0x140074322  mov     ecx, 40h ; '@'
0x140074327  mov     r14d, 30303030h
0x14007432d  cmp     eax, ecx
0x14007432f  ja      short loc_14007433A
0x140074331  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140074338  jmp     short loc_140074368
0x14007433a  cmp     eax, 100h
0x14007433f  ja      short loc_14007434A
0x140074341  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140074348  jmp     short loc_140074368
0x14007434a  cmp     eax, 400h
0x14007434f  ja      short loc_14007435A
0x140074351  lea     rbx, Lookaside
0x140074358  jmp     short loc_140074368
0x14007435a  cmp     eax, 800h
0x14007435f  ja      short loc_140074379
0x140074361  lea     rbx, stru_1400B31C0
0x140074368  mov     rcx, rbx; Lookaside
0x14007436b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140074372  nop     dword ptr [rax+rax+00h]
0x140074377  jmp     short loc_14007438C
0x140074379  xor     ebx, ebx
0x14007437b  mov     edx, eax
0x14007437d  mov     r8d, r14d
0x140074380  call    cs:__imp_ExAllocatePool2
0x140074387  nop     dword ptr [rax+rax+00h]
0x14007438c  mov     rdi, rax
0x14007438f  test    rax, rax
0x140074392  jz      loc_1400744B3
0x140074398  mov     [rax+8], r14d
0x14007439c  xor     edx, edx; Val
0x14007439e  lea     r14, [rax+10h]
0x1400743a2  mov     r8d, r15d; Size
0x1400743a5  mov     rcx, r14; void *
0x1400743a8  mov     [rax], rbx
0x1400743ab  mov     r12d, r15d
0x1400743ae  call    memset
0x1400743b3  mov     dword ptr [r14], 100180h
0x1400743ba  lea     eax, [r15-0Ch]
0x1400743be  mov     [r14+4], eax
0x1400743c2  lea     rdx, [rsi+28h]; Src
0x1400743c6  mov     [r14+8], eax
0x1400743ca  lea     rcx, [r14+20h]; void *
0x1400743ce  mov     eax, [rsi+0Ch]
0x1400743d1  mov     [r14+0Ch], eax
0x1400743d5  movzx   eax, word ptr [rsi+10h]
0x1400743d9  mov     [r14+10h], ax
0x1400743de  cmp     dword ptr [rsi+20h], 1
0x1400743e2  setnz   al
0x1400743e5  mov     [r14+1Ch], al
0x1400743e9  mov     eax, [rsi+14h]
0x1400743ec  mov     [r14+14h], eax
0x1400743f0  mov     eax, [rsi+18h]
0x1400743f3  mov     [r14+18h], eax
0x1400743f7  cmp     dword ptr [rsi+1Ch], 0
0x1400743fb  setnz   al
0x1400743fe  mov     [r14+1Dh], al
0x140074402  movzx   eax, word ptr [rsi+24h]
0x140074406  mov     r8d, eax; Size
0x140074409  mov     [r14+1Eh], ax
0x14007440e  call    memmove
0x140074413  mov     rcx, [r13+0]
0x140074417  mov     r9, r14; void *
0x14007441a  mov     r8, [rsp+78h+arg_0]
0x140074422  mov     edx, 1; unsigned int
0x140074427  mov     [rsp+78h+var_58], r15d; unsigned int
0x14007442c  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140074430  mov     r8d, [r8+8]; unsigned int
0x140074434  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140074439  mov     ebx, eax
0x14007443b  test    eax, eax
0x14007443d  jz      short loc_14007446C
0x14007443f  mov     rcx, cs:WPP_GLOBAL_Control
0x140074446  lea     r15, WPP_GLOBAL_Control
0x14007444d  cmp     rcx, r15
0x140074450  jz      short loc_140074473
0x140074452  mov     rcx, [rcx+18h]
0x140074456  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x14007445d  mov     edx, 6Dh ; 'm'
0x140074462  mov     r9d, eax
0x140074465  call    WPP_SF_d
0x14007446a  jmp     short loc_140074473
0x14007446c  lea     r15, WPP_GLOBAL_Control
0x140074473  mov     r8, r12; Size
0x140074476  xor     edx, edx; Val
0x140074478  mov     rcx, r14; void *
0x14007447b  call    memset
0x140074480  mov     rcx, [rdi]; Lookaside
0x140074483  test    rcx, rcx
0x140074486  jz      short loc_14007449C
0x140074488  mov     rdx, rdi; Entry
0x14007448b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140074492  nop     dword ptr [rax+rax+00h]
0x140074497  jmp     loc_140074283
0x14007449c  mov     edx, [rdi+8]; Tag
0x14007449f  mov     rcx, rdi; P
0x1400744a2  call    cs:__imp_ExFreePoolWithTag
0x1400744a9  nop     dword ptr [rax+rax+00h]
0x1400744ae  jmp     loc_140074283
0x1400744b3  mov     ebx, 0C000009Ah
0x1400744b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400744bf  lea     r15, WPP_GLOBAL_Control
0x1400744c6  cmp     rcx, r15
0x1400744c9  jz      loc_140074283
0x1400744cf  mov     rcx, [rcx+18h]
0x1400744d3  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x1400744da  mov     edx, 6Ch ; 'l'
0x1400744df  call    WPP_SF_
0x1400744e4  jmp     loc_140074283
```
