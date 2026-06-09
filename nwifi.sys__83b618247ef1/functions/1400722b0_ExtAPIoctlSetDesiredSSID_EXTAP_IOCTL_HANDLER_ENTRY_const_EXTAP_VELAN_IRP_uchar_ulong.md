# ExtAPIoctlSetDesiredSSID(_EXTAP_IOCTL_HANDLER_ENTRY const *,_EXTAP_VELAN *,_IRP *,uchar *,ulong)

- ea: `0x1400722b0`
- end: `0x140072695`
- name: `?ExtAPIoctlSetDesiredSSID@@YAHPEBU_EXTAP_IOCTL_HANDLER_ENTRY@@PEAU_EXTAP_VELAN@@PEAU_IRP@@PEAEK@Z`
- size: `997`
- prototype: `__int64 __fastcall(const struct _EXTAP_IOCTL_HANDLER_ENTRY *, struct _EXTAP_VELAN *, struct _IRP *, unsigned __int8 *, size_t Size)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d22c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140020f20`
- `0x14002f1bc`
- `0x14002f430`
- `0x1400722b0`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400723e2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400723e2`
- `ntoskrnl!ExAllocatePool2` at `0x1400723fa`
- `ntoskrnl!ExAllocatePool2` at `0x1400723fa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400725bf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400725bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400725d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400725d6`

## pseudocode

```c
__int64 __fastcall ExtAPIoctlSetDesiredSSID(
        const struct _EXTAP_IOCTL_HANDLER_ENTRY *a1,
        struct _EXTAP_VELAN *a2,
        struct _IRP *a3,
        unsigned __int8 *a4,
        size_t Size)
{
  _DOT11_EXTAP_ATTRIBUTES *pExtAPAttrs; // rbx
  unsigned __int64 v7; // rdi
  unsigned int uDesiredSSIDListSize; // eax
  __int64 v9; // r9
  unsigned int v10; // ebx
  unsigned int v11; // r15d
  unsigned int v12; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v15; // rsi
  _DWORD *v16; // r14
  unsigned int v17; // eax
  __int64 v18; // r9
  _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v20; // rax
  unsigned int v21; // edi
  _DEVICE_OBJECT *v22; // rcx
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  __int128 v26; // [rsp+30h] [rbp-10h] BYREF

  pExtAPAttrs = a2->pExtAPAttrs;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
  v7 = (unsigned int)Size / 0x24uLL;
  if ( (unsigned int)Size != 36 * v7 || (unsigned int)Size < 0x24 )
  {
    v10 = -1073741811;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v10;
    v24 = 33;
    goto LABEL_43;
  }
  uDesiredSSIDListSize = pExtAPAttrs->uDesiredSSIDListSize;
  v9 = 36;
  if ( uDesiredSSIDListSize < 0x24 )
    v9 = uDesiredSSIDListSize;
  if ( (unsigned int)v7 <= (unsigned int)v9 )
  {
    v11 = Size + 12;
    if ( (int)Size + 12 >= (unsigned int)Size )
    {
      v12 = Size + 28;
      if ( v11 >= 0xFFFFFFF0 )
        goto LABEL_37;
      if ( v12 > 0x40 )
      {
        if ( v12 > 0x100 )
        {
          if ( v12 > 0x400 )
          {
            if ( v12 > 0x800 )
            {
              p_WaitListHead = 0;
              Pool2 = (_DWORD *)ExAllocatePool2(64, v12, 808464432, v9);
LABEL_22:
              v15 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
              if ( Pool2 )
              {
                v16 = Pool2 + 4;
                *(_QWORD *)Pool2 = p_WaitListHead;
                Pool2[2] = 808464432;
                memset(Pool2 + 4, 0, v11);
                *v16 = 3146112;
                v16[1] = v7;
                v16[2] = v7;
                memmove(v16 + 3, a4, (unsigned int)Size);
                v17 = PtRequestAdapterSync(a2->pVElan->pAdapt, 1u, 0xE01017Cu, v16, v11);
                v10 = v17;
                if ( v17 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      37,
                      WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids,
                      v17);
                }
                else
                {
                  memmove(a2->DesiredSSIDList, a4, (unsigned int)Size);
                  a2->ulDesiredSSIDListSize = v7;
                  v18 = (unsigned int)v16[2];
                  if ( (_DWORD)v18 == 1 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    {
                      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
                      v26 = 0;
                      LOWORD(v26) = *((_WORD *)v16 + 6);
                      *((_QWORD *)&v26 + 1) = v16 + 4;
                      WPP_SF__HEX_(AttachedDevice, 38, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, &v26);
                    }
                  }
                  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      39,
                      WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids,
                      v18);
                    v20 = 0;
                    if ( v16[2] )
                    {
                      do
                      {
                        v21 = v20 + 1;
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        {
                          v22 = WPP_GLOBAL_Control->AttachedDevice;
                          *(_QWORD *)&v26 = LOWORD(v16[9 * v20 + 3]);
                          *((_QWORD *)&v26 + 1) = &v16[9 * v20 + 4];
                          WPP_SF_d_HEX_(
                            (_DWORD)v22,
                            40,
                            (unsigned int)WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids,
                            v21,
                            (__int64)&v26);
                        }
                        v20 = v21;
                      }
                      while ( v21 < v16[2] );
                    }
                  }
                }
                if ( *v15 )
                  ExFreeToNPagedLookasideList(*v15, v15);
                else
                  ExFreePoolWithTag(v15, *((_DWORD *)v15 + 2));
                goto LABEL_44;
              }
LABEL_37:
              v10 = -1073741670;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                return v10;
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
              goto LABEL_44;
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
      goto LABEL_22;
    }
    v10 = -1073676267;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v10;
    v24 = 35;
LABEL_43:
    WPP_SF_(v23->AttachedDevice, v24, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
    goto LABEL_44;
  }
  v10 = -1073741811;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return v10;
  WPP_SF_Dd(
    WPP_GLOBAL_Control->AttachedDevice,
    34,
    WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids,
    (unsigned int)v7,
    v9);
LABEL_44:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x1400722b0  mov     [rsp-38h+arg_0], rbx
0x1400722b5  mov     [rsp-38h+Src], r9
0x1400722ba  push    rbp
0x1400722bb  push    rsi
0x1400722bc  push    rdi
0x1400722bd  push    r12
0x1400722bf  push    r13
0x1400722c1  push    r14
0x1400722c3  push    r15
0x1400722c5  mov     rbp, rsp
0x1400722c8  sub     rsp, 40h
0x1400722cc  mov     rbx, [rdx+18h]
0x1400722d0  mov     r13, rdx
0x1400722d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400722da  lea     r10, WPP_GLOBAL_Control
0x1400722e1  cmp     rcx, r10
0x1400722e4  jz      short loc_140072302
0x1400722e6  mov     rcx, [rcx+18h]
0x1400722ea  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x1400722f1  mov     edx, 20h ; ' '
0x1400722f6  call    WPP_SF_
0x1400722fb  lea     r10, WPP_GLOBAL_Control
0x140072302  mov     r8d, dword ptr [rbp+Size]
0x140072306  mov     rax, 0E38E38E38E38E38Fh
0x140072310  mul     r8
0x140072313  mov     r12d, r8d
0x140072316  mov     rdi, rdx
0x140072319  shr     rdi, 5
0x14007231d  lea     rcx, [rdi+rdi*8]
0x140072321  shl     rcx, 2
0x140072325  cmp     r8, rcx
0x140072328  jnz     loc_140072629
0x14007232e  mov     r14d, 24h ; '$'
0x140072334  cmp     r8d, r14d
0x140072337  jb      loc_140072629
0x14007233d  mov     eax, [rbx+8]
0x140072340  mov     r9d, r14d
0x140072343  cmp     eax, r14d
0x140072346  cmovb   r9d, eax
0x14007234a  cmp     edi, r9d
0x14007234d  jbe     short loc_140072385
0x14007234f  mov     ebx, 0C000000Dh
0x140072354  mov     rcx, cs:WPP_GLOBAL_Control
0x14007235b  cmp     rcx, r10
0x14007235e  jz      loc_14007267A
0x140072364  mov     rcx, [rcx+18h]
0x140072368  lea     edx, [r14-2]
0x14007236c  mov     [rsp+40h+var_20], r9d
0x140072371  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140072378  mov     r9d, edi
0x14007237b  call    WPP_SF_Dd
0x140072380  jmp     loc_14007264F
0x140072385  lea     r15d, [r8+0Ch]
0x140072389  cmp     r15d, r8d
0x14007238c  jb      loc_140072611
0x140072392  lea     eax, [r15+10h]
0x140072396  cmp     eax, 10h
0x140072399  jb      loc_1400725E4
0x14007239f  mov     ecx, 40h ; '@'
0x1400723a4  cmp     eax, ecx
0x1400723a6  ja      short loc_1400723B1
0x1400723a8  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400723af  jmp     short loc_1400723DF
0x1400723b1  cmp     eax, 100h
0x1400723b6  ja      short loc_1400723C1
0x1400723b8  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400723bf  jmp     short loc_1400723DF
0x1400723c1  cmp     eax, 400h
0x1400723c6  ja      short loc_1400723D1
0x1400723c8  lea     rbx, Lookaside
0x1400723cf  jmp     short loc_1400723DF
0x1400723d1  cmp     eax, 800h
0x1400723d6  ja      short loc_1400723F0
0x1400723d8  lea     rbx, stru_1400B0180
0x1400723df  mov     rcx, rbx; Lookaside
0x1400723e2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400723e9  nop     dword ptr [rax+rax+00h]
0x1400723ee  jmp     short loc_140072406
0x1400723f0  xor     ebx, ebx
0x1400723f2  mov     edx, eax
0x1400723f4  mov     r8d, 30303030h
0x1400723fa  call    cs:__imp_ExAllocatePool2
0x140072401  nop     dword ptr [rax+rax+00h]
0x140072406  mov     rsi, rax
0x140072409  test    rax, rax
0x14007240c  jz      loc_1400725E4
0x140072412  lea     r14, [rax+10h]
0x140072416  mov     r8d, r15d; Size
0x140072419  mov     rcx, r14; void *
0x14007241c  mov     [rax], rbx
0x14007241f  xor     edx, edx; Val
0x140072421  mov     dword ptr [rax+8], 30303030h
0x140072428  call    memset
0x14007242d  mov     rdx, [rbp+Src]; Src
0x140072431  lea     rax, [r14+0Ch]
0x140072435  mov     dword ptr [r14], 300180h
0x14007243c  mov     rcx, rax; void *
0x14007243f  mov     [r14+4], edi
0x140072443  mov     r8, r12; Size
0x140072446  mov     [r14+8], edi
0x14007244a  mov     [rbp+arg_8], rax
0x14007244e  call    memmove
0x140072453  mov     rcx, [r13+0]
0x140072457  mov     r9, r14; void *
0x14007245a  mov     edx, 1; unsigned int
0x14007245f  mov     [rsp+40h+var_20], r15d; unsigned int
0x140072464  mov     r8d, 0E01017Ch; unsigned int
0x14007246a  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14007246e  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140072473  mov     ebx, eax
0x140072475  test    eax, eax
0x140072477  jz      short loc_1400724AD
0x140072479  mov     rcx, cs:WPP_GLOBAL_Control
0x140072480  lea     r15, WPP_GLOBAL_Control
0x140072487  cmp     rcx, r15
0x14007248a  jz      loc_1400725B4
0x140072490  mov     rcx, [rcx+18h]
0x140072494  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x14007249b  mov     edx, 25h ; '%'
0x1400724a0  mov     r9d, eax
0x1400724a3  call    WPP_SF_d
0x1400724a8  jmp     loc_1400725B4
0x1400724ad  mov     rdx, [rbp+Src]; Src
0x1400724b1  lea     rcx, [r13+48h]; void *
0x1400724b5  mov     r8, r12; Size
0x1400724b8  call    memmove
0x1400724bd  mov     [r13+6Ch], edi
0x1400724c1  mov     r9d, [r14+8]
0x1400724c5  cmp     r9d, 1
0x1400724c9  jnz     short loc_140072522
0x1400724cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400724d2  lea     r15, WPP_GLOBAL_Control
0x1400724d9  cmp     rcx, r15
0x1400724dc  jz      loc_1400725B4
0x1400724e2  mov     rdx, [rbp+arg_8]
0x1400724e6  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x1400724ed  mov     rcx, [rcx+18h]
0x1400724f1  xorps   xmm0, xmm0
0x1400724f4  movups  [rbp+var_10], xmm0
0x1400724f8  movzx   eax, word ptr [rdx]
0x1400724fb  mov     word ptr [rbp+var_10], ax
0x1400724ff  lea     rax, [rdx+4]
0x140072503  mov     qword ptr [rbp+var_10+8], rax
0x140072507  lea     edx, [r9+25h]
0x14007250b  movaps  xmm0, [rbp+var_10]
0x14007250f  lea     r9, [rbp+var_10]
0x140072513  movdqa  [rbp+var_10], xmm0
0x140072518  call    WPP_SF__HEX_
0x14007251d  jmp     loc_1400725B4
0x140072522  mov     rcx, cs:WPP_GLOBAL_Control
0x140072529  lea     r15, WPP_GLOBAL_Control
0x140072530  cmp     rcx, r15
0x140072533  jz      short loc_1400725B4
0x140072535  mov     rcx, [rcx+18h]
0x140072539  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140072540  mov     edx, 27h ; '''
0x140072545  call    WPP_SF_d
0x14007254a  xor     eax, eax
0x14007254c  cmp     [r14+8], eax
0x140072550  jbe     short loc_1400725B4
0x140072552  mov     rcx, cs:WPP_GLOBAL_Control
0x140072559  lea     edi, [rax+1]
0x14007255c  cmp     rcx, r15
0x14007255f  jz      short loc_1400725AC
0x140072561  mov     rcx, [rcx+18h]
0x140072565  lea     rdx, [rax+rax*8]
0x140072569  movzx   eax, word ptr [r14+rdx*4+0Ch]
0x14007256f  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140072576  xorps   xmm0, xmm0
0x140072579  mov     r9d, edi
0x14007257c  movups  [rbp+var_10], xmm0
0x140072580  mov     word ptr [rbp+var_10], ax
0x140072584  lea     rax, [rdx+4]
0x140072588  lea     rax, [r14+rax*4]
0x14007258c  mov     edx, 28h ; '('
0x140072591  mov     qword ptr [rbp+var_10+8], rax
0x140072595  lea     rax, [rbp+var_10]
0x140072599  movaps  xmm0, [rbp+var_10]
0x14007259d  movdqa  [rbp+var_10], xmm0
0x1400725a2  mov     qword ptr [rsp+40h+var_20], rax
0x1400725a7  call    WPP_SF_d_HEX_
0x1400725ac  mov     eax, edi
0x1400725ae  cmp     eax, [r14+8]
0x1400725b2  jb      short loc_140072552
0x1400725b4  mov     rcx, [rsi]; Lookaside
0x1400725b7  test    rcx, rcx
0x1400725ba  jz      short loc_1400725D0
0x1400725bc  mov     rdx, rsi; Entry
0x1400725bf  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400725c6  nop     dword ptr [rax+rax+00h]
0x1400725cb  jmp     loc_140072656
0x1400725d0  mov     edx, [rsi+8]; Tag
0x1400725d3  mov     rcx, rsi; P
0x1400725d6  call    cs:__imp_ExFreePoolWithTag
0x1400725dd  nop     dword ptr [rax+rax+00h]
0x1400725e2  jmp     short loc_140072656
0x1400725e4  mov     ebx, 0C000009Ah
0x1400725e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400725f0  lea     r15, WPP_GLOBAL_Control
0x1400725f7  cmp     rcx, r15
0x1400725fa  jz      short loc_14007267A
0x1400725fc  mov     rcx, [rcx+18h]
0x140072600  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140072607  mov     edx, r14d
0x14007260a  call    WPP_SF_
0x14007260f  jmp     short loc_140072656
0x140072611  mov     ebx, 0C0010015h
0x140072616  mov     rcx, cs:WPP_GLOBAL_Control
0x14007261d  cmp     rcx, r10
0x140072620  jz      short loc_14007267A
0x140072622  mov     edx, 23h ; '#'
0x140072627  jmp     short loc_14007263F
0x140072629  mov     ebx, 0C000000Dh
0x14007262e  mov     rcx, cs:WPP_GLOBAL_Control
0x140072635  cmp     rcx, r10
0x140072638  jz      short loc_14007267A
0x14007263a  mov     edx, 21h ; '!'
0x14007263f  mov     rcx, [rcx+18h]
0x140072643  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x14007264a  call    WPP_SF_
0x14007264f  lea     r15, WPP_GLOBAL_Control
0x140072656  mov     rcx, cs:WPP_GLOBAL_Control
0x14007265d  cmp     rcx, r15
0x140072660  jz      short loc_14007267A
0x140072662  mov     rcx, [rcx+18h]
0x140072666  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x14007266d  mov     edx, 29h ; ')'
0x140072672  mov     r9d, ebx
0x140072675  call    WPP_SF_d
0x14007267a  mov     eax, ebx
0x14007267c  mov     rbx, [rsp+40h+arg_0]
0x140072684  add     rsp, 40h
0x140072688  pop     r15
0x14007268a  pop     r14
0x14007268c  pop     r13
0x14007268e  pop     r12
0x140072690  pop     rdi
0x140072691  pop     rsi
0x140072692  pop     rbp
0x140072693  retn
```
