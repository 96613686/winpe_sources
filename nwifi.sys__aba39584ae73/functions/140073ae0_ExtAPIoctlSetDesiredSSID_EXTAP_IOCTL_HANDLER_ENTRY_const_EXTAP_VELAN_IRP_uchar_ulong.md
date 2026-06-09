# ExtAPIoctlSetDesiredSSID(_EXTAP_IOCTL_HANDLER_ENTRY const *,_EXTAP_VELAN *,_IRP *,uchar *,ulong)

- ea: `0x140073ae0`
- end: `0x140073ec5`
- name: `?ExtAPIoctlSetDesiredSSID@@YAHPEBU_EXTAP_IOCTL_HANDLER_ENTRY@@PEAU_EXTAP_VELAN@@PEAU_IRP@@PEAEK@Z`
- size: `997`
- prototype: `__int64 __fastcall(const struct _EXTAP_IOCTL_HANDLER_ENTRY *, struct _EXTAP_VELAN *, struct _IRP *, unsigned __int8 *, size_t Size)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d21c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140020f20`
- `0x14002f44c`
- `0x14002f6c0`
- `0x140073ae0`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140073c12`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140073c12`
- `ntoskrnl!ExAllocatePool2` at `0x140073c2a`
- `ntoskrnl!ExAllocatePool2` at `0x140073c2a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140073def`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140073def`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073e06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073e06`

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
  unsigned int uDesiredSSIDListSize; // r9d
  unsigned int v9; // ebx
  unsigned int v10; // r15d
  unsigned int v11; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v14; // rsi
  _DWORD *v15; // r14
  unsigned int v16; // eax
  __int64 v17; // r9
  _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v19; // rax
  unsigned int v20; // edi
  _DEVICE_OBJECT *v21; // rcx
  PDEVICE_OBJECT v22; // rcx
  __int64 v23; // rdx
  __int128 v25; // [rsp+30h] [rbp-10h] BYREF

  pExtAPAttrs = a2->pExtAPAttrs;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
  v7 = (unsigned int)Size / 0x24uLL;
  if ( (unsigned int)Size != 36 * v7 || (unsigned int)Size < 0x24 )
  {
    v9 = -1073741811;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v9;
    v23 = 33;
    goto LABEL_43;
  }
  uDesiredSSIDListSize = 36;
  if ( pExtAPAttrs->uDesiredSSIDListSize < 0x24 )
    uDesiredSSIDListSize = pExtAPAttrs->uDesiredSSIDListSize;
  if ( (unsigned int)v7 <= uDesiredSSIDListSize )
  {
    v10 = Size + 12;
    if ( (int)Size + 12 >= (unsigned int)Size )
    {
      v11 = Size + 28;
      if ( v10 >= 0xFFFFFFF0 )
        goto LABEL_37;
      if ( v11 > 0x40 )
      {
        if ( v11 > 0x100 )
        {
          if ( v11 > 0x400 )
          {
            if ( v11 > 0x800 )
            {
              p_WaitListHead = 0;
              Pool2 = (_DWORD *)ExAllocatePool2(64, v11, 808464432);
LABEL_22:
              v14 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
              if ( Pool2 )
              {
                v15 = Pool2 + 4;
                *(_QWORD *)Pool2 = p_WaitListHead;
                Pool2[2] = 808464432;
                memset(Pool2 + 4, 0, v10);
                *v15 = 3146112;
                v15[1] = v7;
                v15[2] = v7;
                memmove(v15 + 3, a4, (unsigned int)Size);
                v16 = PtRequestAdapterSync(a2->pVElan->pAdapt, 1u, 0xE01017Cu, v15, v10);
                v9 = v16;
                if ( v16 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      37,
                      WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids,
                      v16);
                }
                else
                {
                  memmove(a2->DesiredSSIDList, a4, (unsigned int)Size);
                  a2->ulDesiredSSIDListSize = v7;
                  v17 = (unsigned int)v15[2];
                  if ( (_DWORD)v17 == 1 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    {
                      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
                      v25 = 0;
                      LOWORD(v25) = *((_WORD *)v15 + 6);
                      *((_QWORD *)&v25 + 1) = v15 + 4;
                      WPP_SF__HEX_(AttachedDevice, 38, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, &v25);
                    }
                  }
                  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      39,
                      WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids,
                      v17);
                    v19 = 0;
                    if ( v15[2] )
                    {
                      do
                      {
                        v20 = v19 + 1;
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        {
                          v21 = WPP_GLOBAL_Control->AttachedDevice;
                          *(_QWORD *)&v25 = LOWORD(v15[9 * v19 + 3]);
                          *((_QWORD *)&v25 + 1) = &v15[9 * v19 + 4];
                          WPP_SF_d_HEX_(
                            (_DWORD)v21,
                            40,
                            (unsigned int)WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids,
                            v20,
                            (__int64)&v25);
                        }
                        v19 = v20;
                      }
                      while ( v20 < v15[2] );
                    }
                  }
                }
                if ( *v14 )
                  ExFreeToNPagedLookasideList(*v14, v14);
                else
                  ExFreePoolWithTag(v14, *((_DWORD *)v14 + 2));
                goto LABEL_44;
              }
LABEL_37:
              v9 = -1073741670;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                return v9;
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
              goto LABEL_44;
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
      goto LABEL_22;
    }
    v9 = -1073676267;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v9;
    v23 = 35;
LABEL_43:
    WPP_SF_(v22->AttachedDevice, v23, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
    goto LABEL_44;
  }
  v9 = -1073741811;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return v9;
  WPP_SF_Dd(
    WPP_GLOBAL_Control->AttachedDevice,
    34,
    WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids,
    (unsigned int)v7,
    uDesiredSSIDListSize);
LABEL_44:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x140073ae0  mov     [rsp-38h+arg_0], rbx
0x140073ae5  mov     [rsp-38h+Src], r9
0x140073aea  push    rbp
0x140073aeb  push    rsi
0x140073aec  push    rdi
0x140073aed  push    r12
0x140073aef  push    r13
0x140073af1  push    r14
0x140073af3  push    r15
0x140073af5  mov     rbp, rsp
0x140073af8  sub     rsp, 40h
0x140073afc  mov     rbx, [rdx+18h]
0x140073b00  mov     r13, rdx
0x140073b03  mov     rcx, cs:WPP_GLOBAL_Control
0x140073b0a  lea     r10, WPP_GLOBAL_Control
0x140073b11  cmp     rcx, r10
0x140073b14  jz      short loc_140073B32
0x140073b16  mov     rcx, [rcx+18h]
0x140073b1a  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140073b21  mov     edx, 20h ; ' '
0x140073b26  call    WPP_SF_
0x140073b2b  lea     r10, WPP_GLOBAL_Control
0x140073b32  mov     r8d, dword ptr [rbp+Size]
0x140073b36  mov     rax, 0E38E38E38E38E38Fh
0x140073b40  mul     r8
0x140073b43  mov     r12d, r8d
0x140073b46  mov     rdi, rdx
0x140073b49  shr     rdi, 5
0x140073b4d  lea     rcx, [rdi+rdi*8]
0x140073b51  shl     rcx, 2
0x140073b55  cmp     r8, rcx
0x140073b58  jnz     loc_140073E59
0x140073b5e  mov     r14d, 24h ; '$'
0x140073b64  cmp     r8d, r14d
0x140073b67  jb      loc_140073E59
0x140073b6d  mov     eax, [rbx+8]
0x140073b70  mov     r9d, r14d
0x140073b73  cmp     eax, r14d
0x140073b76  cmovb   r9d, eax
0x140073b7a  cmp     edi, r9d
0x140073b7d  jbe     short loc_140073BB5
0x140073b7f  mov     ebx, 0C000000Dh
0x140073b84  mov     rcx, cs:WPP_GLOBAL_Control
0x140073b8b  cmp     rcx, r10
0x140073b8e  jz      loc_140073EAA
0x140073b94  mov     rcx, [rcx+18h]
0x140073b98  lea     edx, [r14-2]
0x140073b9c  mov     [rsp+40h+var_20], r9d
0x140073ba1  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140073ba8  mov     r9d, edi
0x140073bab  call    WPP_SF_Dd
0x140073bb0  jmp     loc_140073E7F
0x140073bb5  lea     r15d, [r8+0Ch]
0x140073bb9  cmp     r15d, r8d
0x140073bbc  jb      loc_140073E41
0x140073bc2  lea     eax, [r15+10h]
0x140073bc6  cmp     eax, 10h
0x140073bc9  jb      loc_140073E14
0x140073bcf  mov     ecx, 40h ; '@'
0x140073bd4  cmp     eax, ecx
0x140073bd6  ja      short loc_140073BE1
0x140073bd8  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140073bdf  jmp     short loc_140073C0F
0x140073be1  cmp     eax, 100h
0x140073be6  ja      short loc_140073BF1
0x140073be8  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140073bef  jmp     short loc_140073C0F
0x140073bf1  cmp     eax, 400h
0x140073bf6  ja      short loc_140073C01
0x140073bf8  lea     rbx, Lookaside
0x140073bff  jmp     short loc_140073C0F
0x140073c01  cmp     eax, 800h
0x140073c06  ja      short loc_140073C20
0x140073c08  lea     rbx, stru_1400B31C0
0x140073c0f  mov     rcx, rbx; Lookaside
0x140073c12  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140073c19  nop     dword ptr [rax+rax+00h]
0x140073c1e  jmp     short loc_140073C36
0x140073c20  xor     ebx, ebx
0x140073c22  mov     edx, eax
0x140073c24  mov     r8d, 30303030h
0x140073c2a  call    cs:__imp_ExAllocatePool2
0x140073c31  nop     dword ptr [rax+rax+00h]
0x140073c36  mov     rsi, rax
0x140073c39  test    rax, rax
0x140073c3c  jz      loc_140073E14
0x140073c42  lea     r14, [rax+10h]
0x140073c46  mov     r8d, r15d; Size
0x140073c49  mov     rcx, r14; void *
0x140073c4c  mov     [rax], rbx
0x140073c4f  xor     edx, edx; Val
0x140073c51  mov     dword ptr [rax+8], 30303030h
0x140073c58  call    memset
0x140073c5d  mov     rdx, [rbp+Src]; Src
0x140073c61  lea     rax, [r14+0Ch]
0x140073c65  mov     dword ptr [r14], 300180h
0x140073c6c  mov     rcx, rax; void *
0x140073c6f  mov     [r14+4], edi
0x140073c73  mov     r8, r12; Size
0x140073c76  mov     [r14+8], edi
0x140073c7a  mov     [rbp+arg_8], rax
0x140073c7e  call    memmove
0x140073c83  mov     rcx, [r13+0]
0x140073c87  mov     r9, r14; void *
0x140073c8a  mov     edx, 1; unsigned int
0x140073c8f  mov     [rsp+40h+var_20], r15d; unsigned int
0x140073c94  mov     r8d, 0E01017Ch; unsigned int
0x140073c9a  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140073c9e  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140073ca3  mov     ebx, eax
0x140073ca5  test    eax, eax
0x140073ca7  jz      short loc_140073CDD
0x140073ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x140073cb0  lea     r15, WPP_GLOBAL_Control
0x140073cb7  cmp     rcx, r15
0x140073cba  jz      loc_140073DE4
0x140073cc0  mov     rcx, [rcx+18h]
0x140073cc4  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140073ccb  mov     edx, 25h ; '%'
0x140073cd0  mov     r9d, eax
0x140073cd3  call    WPP_SF_d
0x140073cd8  jmp     loc_140073DE4
0x140073cdd  mov     rdx, [rbp+Src]; Src
0x140073ce1  lea     rcx, [r13+48h]; void *
0x140073ce5  mov     r8, r12; Size
0x140073ce8  call    memmove
0x140073ced  mov     [r13+6Ch], edi
0x140073cf1  mov     r9d, [r14+8]
0x140073cf5  cmp     r9d, 1
0x140073cf9  jnz     short loc_140073D52
0x140073cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140073d02  lea     r15, WPP_GLOBAL_Control
0x140073d09  cmp     rcx, r15
0x140073d0c  jz      loc_140073DE4
0x140073d12  mov     rdx, [rbp+arg_8]
0x140073d16  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140073d1d  mov     rcx, [rcx+18h]
0x140073d21  xorps   xmm0, xmm0
0x140073d24  movups  [rbp+var_10], xmm0
0x140073d28  movzx   eax, word ptr [rdx]
0x140073d2b  mov     word ptr [rbp+var_10], ax
0x140073d2f  lea     rax, [rdx+4]
0x140073d33  mov     qword ptr [rbp+var_10+8], rax
0x140073d37  lea     edx, [r9+25h]
0x140073d3b  movaps  xmm0, [rbp+var_10]
0x140073d3f  lea     r9, [rbp+var_10]
0x140073d43  movdqa  [rbp+var_10], xmm0
0x140073d48  call    WPP_SF__HEX_
0x140073d4d  jmp     loc_140073DE4
0x140073d52  mov     rcx, cs:WPP_GLOBAL_Control
0x140073d59  lea     r15, WPP_GLOBAL_Control
0x140073d60  cmp     rcx, r15
0x140073d63  jz      short loc_140073DE4
0x140073d65  mov     rcx, [rcx+18h]
0x140073d69  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140073d70  mov     edx, 27h ; '''
0x140073d75  call    WPP_SF_d
0x140073d7a  xor     eax, eax
0x140073d7c  cmp     [r14+8], eax
0x140073d80  jbe     short loc_140073DE4
0x140073d82  mov     rcx, cs:WPP_GLOBAL_Control
0x140073d89  lea     edi, [rax+1]
0x140073d8c  cmp     rcx, r15
0x140073d8f  jz      short loc_140073DDC
0x140073d91  mov     rcx, [rcx+18h]
0x140073d95  lea     rdx, [rax+rax*8]
0x140073d99  movzx   eax, word ptr [r14+rdx*4+0Ch]
0x140073d9f  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140073da6  xorps   xmm0, xmm0
0x140073da9  mov     r9d, edi
0x140073dac  movups  [rbp+var_10], xmm0
0x140073db0  mov     word ptr [rbp+var_10], ax
0x140073db4  lea     rax, [rdx+4]
0x140073db8  lea     rax, [r14+rax*4]
0x140073dbc  mov     edx, 28h ; '('
0x140073dc1  mov     qword ptr [rbp+var_10+8], rax
0x140073dc5  lea     rax, [rbp+var_10]
0x140073dc9  movaps  xmm0, [rbp+var_10]
0x140073dcd  movdqa  [rbp+var_10], xmm0
0x140073dd2  mov     qword ptr [rsp+40h+var_20], rax
0x140073dd7  call    WPP_SF_d_HEX_
0x140073ddc  mov     eax, edi
0x140073dde  cmp     eax, [r14+8]
0x140073de2  jb      short loc_140073D82
0x140073de4  mov     rcx, [rsi]; Lookaside
0x140073de7  test    rcx, rcx
0x140073dea  jz      short loc_140073E00
0x140073dec  mov     rdx, rsi; Entry
0x140073def  call    cs:__imp_ExFreeToNPagedLookasideList
0x140073df6  nop     dword ptr [rax+rax+00h]
0x140073dfb  jmp     loc_140073E86
0x140073e00  mov     edx, [rsi+8]; Tag
0x140073e03  mov     rcx, rsi; P
0x140073e06  call    cs:__imp_ExFreePoolWithTag
0x140073e0d  nop     dword ptr [rax+rax+00h]
0x140073e12  jmp     short loc_140073E86
0x140073e14  mov     ebx, 0C000009Ah
0x140073e19  mov     rcx, cs:WPP_GLOBAL_Control
0x140073e20  lea     r15, WPP_GLOBAL_Control
0x140073e27  cmp     rcx, r15
0x140073e2a  jz      short loc_140073EAA
0x140073e2c  mov     rcx, [rcx+18h]
0x140073e30  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140073e37  mov     edx, r14d
0x140073e3a  call    WPP_SF_
0x140073e3f  jmp     short loc_140073E86
0x140073e41  mov     ebx, 0C0010015h
0x140073e46  mov     rcx, cs:WPP_GLOBAL_Control
0x140073e4d  cmp     rcx, r10
0x140073e50  jz      short loc_140073EAA
0x140073e52  mov     edx, 23h ; '#'
0x140073e57  jmp     short loc_140073E6F
0x140073e59  mov     ebx, 0C000000Dh
0x140073e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140073e65  cmp     rcx, r10
0x140073e68  jz      short loc_140073EAA
0x140073e6a  mov     edx, 21h ; '!'
0x140073e6f  mov     rcx, [rcx+18h]
0x140073e73  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140073e7a  call    WPP_SF_
0x140073e7f  lea     r15, WPP_GLOBAL_Control
0x140073e86  mov     rcx, cs:WPP_GLOBAL_Control
0x140073e8d  cmp     rcx, r15
0x140073e90  jz      short loc_140073EAA
0x140073e92  mov     rcx, [rcx+18h]
0x140073e96  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140073e9d  mov     edx, 29h ; ')'
0x140073ea2  mov     r9d, ebx
0x140073ea5  call    WPP_SF_d
0x140073eaa  mov     eax, ebx
0x140073eac  mov     rbx, [rsp+40h+arg_0]
0x140073eb4  add     rsp, 40h
0x140073eb8  pop     r15
0x140073eba  pop     r14
0x140073ebc  pop     r13
0x140073ebe  pop     r12
0x140073ec0  pop     rdi
0x140073ec1  pop     rsi
0x140073ec2  pop     rbp
0x140073ec3  retn
```
