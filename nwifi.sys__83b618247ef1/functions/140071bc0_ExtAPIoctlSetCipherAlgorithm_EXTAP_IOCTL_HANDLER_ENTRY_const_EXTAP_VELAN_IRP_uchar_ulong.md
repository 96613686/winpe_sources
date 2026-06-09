# ExtAPIoctlSetCipherAlgorithm(_EXTAP_IOCTL_HANDLER_ENTRY const *,_EXTAP_VELAN *,_IRP *,uchar *,ulong)

- ea: `0x140071bc0`
- end: `0x140071e83`
- name: `?ExtAPIoctlSetCipherAlgorithm@@YAHPEBU_EXTAP_IOCTL_HANDLER_ENTRY@@PEAU_EXTAP_VELAN@@PEAU_IRP@@PEAEK@Z`
- size: `707`
- prototype: `__int64 __fastcall(const struct _EXTAP_IOCTL_HANDLER_ENTRY *, struct _EXTAP_VELAN *, struct _IRP *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d22c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140020f20`
- `0x140071bc0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140071c9b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140071c9b`
- `ntoskrnl!ExAllocatePool2` at `0x140071cb3`
- `ntoskrnl!ExAllocatePool2` at `0x140071cb3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140071df6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140071df6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071e07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071e07`

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
            Pool2 = (_DWORD *)ExAllocatePool2(64, v10, 808464432, a4);
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
0x140071bc0  push    rbx
0x140071bc2  push    rbp
0x140071bc3  push    rsi
0x140071bc4  push    rdi
0x140071bc5  push    r12
0x140071bc7  push    r13
0x140071bc9  push    r14
0x140071bcb  push    r15
0x140071bcd  sub     rsp, 38h
0x140071bd1  mov     rdi, r9
0x140071bd4  mov     r14, rdx
0x140071bd7  mov     rbp, rcx
0x140071bda  mov     rcx, cs:WPP_GLOBAL_Control
0x140071be1  lea     r15, WPP_GLOBAL_Control
0x140071be8  lea     r12, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140071bef  cmp     rcx, r15
0x140071bf2  jz      short loc_140071C05
0x140071bf4  mov     rcx, [rcx+18h]
0x140071bf8  mov     edx, 47h ; 'G'
0x140071bfd  mov     r8, r12
0x140071c00  call    WPP_SF_
0x140071c05  mov     ecx, [rsp+78h+arg_20]
0x140071c0c  mov     rax, 0AAAAAAAAAAAAAAABh
0x140071c16  mov     r8d, [rdi]
0x140071c19  add     ecx, 0FFFFFFF8h
0x140071c1c  mul     rcx
0x140071c1f  shr     rdx, 3
0x140071c23  cmp     edx, r8d
0x140071c26  jb      loc_140071E2D
0x140071c2c  cmp     [rdi+4], r8d
0x140071c30  jnz     loc_140071E2D
0x140071c36  test    r8d, r8d
0x140071c39  jz      loc_140071E2D
0x140071c3f  lea     esi, ds:0Ch[r8*4]
0x140071c47  mov     r13d, 10h
0x140071c4d  lea     eax, [rsi+10h]
0x140071c50  cmp     eax, r13d
0x140071c53  jb      loc_140071E15
0x140071c59  lea     ecx, [r13+30h]
0x140071c5d  cmp     eax, ecx
0x140071c5f  ja      short loc_140071C6A
0x140071c61  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140071c68  jmp     short loc_140071C98
0x140071c6a  cmp     eax, 100h
0x140071c6f  ja      short loc_140071C7A
0x140071c71  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140071c78  jmp     short loc_140071C98
0x140071c7a  cmp     eax, 400h
0x140071c7f  ja      short loc_140071C8A
0x140071c81  lea     rbx, Lookaside
0x140071c88  jmp     short loc_140071C98
0x140071c8a  cmp     eax, 800h
0x140071c8f  ja      short loc_140071CA9
0x140071c91  lea     rbx, stru_1400B0180
0x140071c98  mov     rcx, rbx; Lookaside
0x140071c9b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140071ca2  nop     dword ptr [rax+rax+00h]
0x140071ca7  jmp     short loc_140071CBF
0x140071ca9  xor     ebx, ebx
0x140071cab  mov     edx, eax
0x140071cad  mov     r8d, 30303030h
0x140071cb3  call    cs:__imp_ExAllocatePool2
0x140071cba  nop     dword ptr [rax+rax+00h]
0x140071cbf  test    rax, rax
0x140071cc2  jz      loc_140071E15
0x140071cc8  mov     [rax], rbx
0x140071ccb  xor     edx, edx; Val
0x140071ccd  lea     rbx, [rax+10h]
0x140071cd1  mov     r8d, esi; Size
0x140071cd4  mov     rcx, rbx; void *
0x140071cd7  mov     dword ptr [rax+8], 30303030h
0x140071cde  call    memset
0x140071ce3  mov     dword ptr [rbx], 100180h
0x140071ce9  xor     r8d, r8d
0x140071cec  mov     eax, [rdi]
0x140071cee  mov     [rbx+4], eax
0x140071cf1  mov     eax, [rdi]
0x140071cf3  mov     [rbx+8], eax
0x140071cf6  cmp     [rdi], r8d
0x140071cf9  jbe     short loc_140071D10
0x140071cfb  lea     rax, [r8+r8*2]
0x140071cff  mov     ecx, [rdi+rax*4+0Ch]
0x140071d03  mov     [rbx+r8*4+0Ch], ecx
0x140071d08  inc     r8d
0x140071d0b  cmp     r8d, [rdi]
0x140071d0e  jb      short loc_140071CFB
0x140071d10  mov     rcx, [r14]
0x140071d13  mov     r9, rbx; void *
0x140071d16  mov     r8d, [rbp+8]; unsigned int
0x140071d1a  mov     edx, 1; unsigned int
0x140071d1f  mov     [rsp+78h+var_58], esi; unsigned int
0x140071d23  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140071d27  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140071d2c  mov     edi, eax
0x140071d2e  test    eax, eax
0x140071d30  jz      short loc_140071D5B
0x140071d32  mov     rcx, cs:WPP_GLOBAL_Control
0x140071d39  cmp     rcx, r15
0x140071d3c  jz      loc_140071DE4
0x140071d42  mov     rcx, [rcx+18h]
0x140071d46  mov     edx, 4Ah ; 'J'
0x140071d4b  mov     r9d, eax
0x140071d4e  mov     r8, r12
0x140071d51  call    WPP_SF_d
0x140071d56  jmp     loc_140071DE4
0x140071d5b  mov     r9d, [rbx+8]
0x140071d5f  cmp     r9d, 1
0x140071d63  jnz     short loc_140071D87
0x140071d65  mov     rcx, cs:WPP_GLOBAL_Control
0x140071d6c  cmp     rcx, r15
0x140071d6f  jz      short loc_140071DDD
0x140071d71  mov     rcx, [rcx+18h]
0x140071d75  lea     edx, [r9+4Ah]
0x140071d79  mov     r9d, [rbx+0Ch]
0x140071d7d  mov     r8, r12
0x140071d80  call    WPP_SF_d
0x140071d85  jmp     short loc_140071DDD
0x140071d87  mov     rcx, cs:WPP_GLOBAL_Control
0x140071d8e  cmp     rcx, r15
0x140071d91  jz      short loc_140071DDD
0x140071d93  mov     rcx, [rcx+18h]
0x140071d97  mov     edx, 4Ch ; 'L'
0x140071d9c  mov     r8, r12
0x140071d9f  call    WPP_SF_d
0x140071da4  xor     eax, eax
0x140071da6  cmp     [rbx+8], eax
0x140071da9  jbe     short loc_140071DDD
0x140071dab  mov     rcx, cs:WPP_GLOBAL_Control
0x140071db2  lea     esi, [rax+1]
0x140071db5  cmp     rcx, r15
0x140071db8  jz      short loc_140071DD6
0x140071dba  mov     eax, [rbx+rax*4+0Ch]
0x140071dbe  mov     edx, 4Dh ; 'M'
0x140071dc3  mov     rcx, [rcx+18h]
0x140071dc7  mov     r9d, esi
0x140071dca  mov     r8, r12
0x140071dcd  mov     [rsp+78h+var_58], eax
0x140071dd1  call    WPP_SF_Dd
0x140071dd6  mov     eax, esi
0x140071dd8  cmp     eax, [rbx+8]
0x140071ddb  jb      short loc_140071DAB
0x140071ddd  mov     eax, [rbx+0Ch]
0x140071de0  mov     [r14+74h], eax
0x140071de4  lea     rcx, [rbx-10h]; P
0x140071de8  mov     rax, [rcx]
0x140071deb  test    rax, rax
0x140071dee  jz      short loc_140071E04
0x140071df0  mov     rdx, rcx; Entry
0x140071df3  mov     rcx, rax; Lookaside
0x140071df6  call    cs:__imp_ExFreeToNPagedLookasideList
0x140071dfd  nop     dword ptr [rax+rax+00h]
0x140071e02  jmp     short loc_140071E4F
0x140071e04  mov     edx, [rcx+8]; Tag
0x140071e07  call    cs:__imp_ExFreePoolWithTag
0x140071e0e  nop     dword ptr [rax+rax+00h]
0x140071e13  jmp     short loc_140071E4F
0x140071e15  mov     edi, 0C000009Ah
0x140071e1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140071e21  cmp     rcx, r15
0x140071e24  jz      short loc_140071E6F
0x140071e26  mov     edx, 49h ; 'I'
0x140071e2b  jmp     short loc_140071E43
0x140071e2d  mov     edi, 0C000000Dh
0x140071e32  mov     rcx, cs:WPP_GLOBAL_Control
0x140071e39  cmp     rcx, r15
0x140071e3c  jz      short loc_140071E6F
0x140071e3e  mov     edx, 48h ; 'H'
0x140071e43  mov     rcx, [rcx+18h]
0x140071e47  mov     r8, r12
0x140071e4a  call    WPP_SF_
0x140071e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140071e56  cmp     rcx, r15
0x140071e59  jz      short loc_140071E6F
0x140071e5b  mov     rcx, [rcx+18h]
0x140071e5f  mov     edx, 4Eh ; 'N'
0x140071e64  mov     r9d, edi
0x140071e67  mov     r8, r12
0x140071e6a  call    WPP_SF_d
0x140071e6f  mov     eax, edi
0x140071e71  add     rsp, 38h
0x140071e75  pop     r15
0x140071e77  pop     r14
0x140071e79  pop     r13
0x140071e7b  pop     r12
0x140071e7d  pop     rdi
0x140071e7e  pop     rsi
0x140071e7f  pop     rbp
0x140071e80  pop     rbx
0x140071e81  retn
```
