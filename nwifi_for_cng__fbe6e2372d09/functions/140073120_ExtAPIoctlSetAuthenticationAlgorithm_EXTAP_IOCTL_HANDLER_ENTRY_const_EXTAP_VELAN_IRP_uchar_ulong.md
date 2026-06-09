# ExtAPIoctlSetAuthenticationAlgorithm(_EXTAP_IOCTL_HANDLER_ENTRY const *,_EXTAP_VELAN *,_IRP *,uchar *,ulong)

- ea: `0x140073120`
- end: `0x1400733de`
- name: `?ExtAPIoctlSetAuthenticationAlgorithm@@YAHPEBU_EXTAP_IOCTL_HANDLER_ENTRY@@PEAU_EXTAP_VELAN@@PEAU_IRP@@PEAEK@Z`
- size: `702`
- prototype: `__int64 __fastcall(const struct _EXTAP_IOCTL_HANDLER_ENTRY *, struct _EXTAP_VELAN *, struct _IRP *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d21c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140020f20`
- `0x140073120`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400731f3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400731f3`
- `ntoskrnl!ExAllocatePool2` at `0x14007320e`
- `ntoskrnl!ExAllocatePool2` at `0x14007320e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140073353`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140073353`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073364`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073364`

## pseudocode

```c
__int64 __fastcall ExtAPIoctlSetAuthenticationAlgorithm(
        const struct _EXTAP_IOCTL_HANDLER_ENTRY *a1,
        struct _EXTAP_VELAN *a2,
        struct _IRP *a3,
        unsigned __int8 *a4,
        unsigned int a5)
{
  int v7; // r8d
  unsigned int v8; // esi
  unsigned int v9; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  _DWORD *v12; // rbx
  __int64 v13; // r8
  unsigned int v14; // eax
  unsigned int v15; // edi
  __int64 v16; // r9
  __int64 v17; // rax
  unsigned int v18; // esi
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
  v7 = *(_DWORD *)a4;
  if ( (a5 - 8) / 0xC >= *(_DWORD *)a4 && *((_DWORD *)a4 + 1) == v7 && v7 )
  {
    v8 = 4 * v7 + 12;
    v9 = 4 * v7 + 28;
    if ( v9 < 0x10 )
    {
LABEL_35:
      v15 = -1073741670;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v15;
      v20 = 62;
      goto LABEL_39;
    }
    if ( v9 > 0x40 )
    {
      if ( v9 > 0x100 )
      {
        if ( v9 > 0x400 )
        {
          if ( v9 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v9, 808464432);
LABEL_17:
            if ( Pool2 )
            {
              *(_QWORD *)Pool2 = p_WaitListHead;
              v12 = Pool2 + 4;
              Pool2[2] = 808464432;
              memset(Pool2 + 4, 0, v8);
              *v12 = 1048960;
              v13 = 0;
              v12[1] = *(_DWORD *)a4;
              for ( v12[2] = *(_DWORD *)a4; (unsigned int)v13 < *(_DWORD *)a4; v13 = (unsigned int)(v13 + 1) )
                v12[v13 + 3] = *(_DWORD *)&a4[12 * v13 + 12];
              v14 = PtRequestAdapterSync(a2->pVElan->pAdapt, 1u, 0xE010185u, v12, v8);
              v15 = v14;
              if ( v14 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, v14);
              }
              else
              {
                v16 = (unsigned int)v12[2];
                if ( (_DWORD)v16 == 1 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      64,
                      WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids,
                      (unsigned int)v12[3]);
                }
                else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, v16);
                  v17 = 0;
                  if ( v12[2] )
                  {
                    do
                    {
                      v18 = v17 + 1;
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        WPP_SF_Dd(
                          WPP_GLOBAL_Control->AttachedDevice,
                          66,
                          WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids,
                          v18,
                          v12[v17 + 3]);
                      v17 = v18;
                    }
                    while ( v18 < v12[2] );
                  }
                }
                a2->LastSetAuthAlgo = v12[3];
              }
              if ( *((_QWORD *)v12 - 2) )
                ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v12 - 2), v12 - 4);
              else
                ExFreePoolWithTag(v12 - 4, *(v12 - 2));
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
  v15 = -1073741811;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return v15;
  v20 = 61;
LABEL_39:
  WPP_SF_(v19->AttachedDevice, v20, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
LABEL_40:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x140073120  push    rbx
0x140073122  push    rbp
0x140073123  push    rsi
0x140073124  push    rdi
0x140073125  push    r13
0x140073127  push    r14
0x140073129  push    r15
0x14007312b  sub     rsp, 30h
0x14007312f  mov     rdi, r9
0x140073132  mov     r14, rdx
0x140073135  mov     rcx, cs:WPP_GLOBAL_Control
0x14007313c  lea     rbp, WPP_GLOBAL_Control
0x140073143  lea     r15, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x14007314a  cmp     rcx, rbp
0x14007314d  jz      short loc_140073160
0x14007314f  mov     rcx, [rcx+18h]
0x140073153  mov     edx, 3Ch ; '<'
0x140073158  mov     r8, r15
0x14007315b  call    WPP_SF_
0x140073160  mov     ecx, [rsp+68h+arg_20]
0x140073167  mov     rax, 0AAAAAAAAAAAAAAABh
0x140073171  mov     r8d, [rdi]
0x140073174  add     ecx, 0FFFFFFF8h
0x140073177  mul     rcx
0x14007317a  shr     rdx, 3
0x14007317e  cmp     edx, r8d
0x140073181  jb      loc_14007338A
0x140073187  cmp     [rdi+4], r8d
0x14007318b  jnz     loc_14007338A
0x140073191  test    r8d, r8d
0x140073194  jz      loc_14007338A
0x14007319a  lea     esi, ds:0Ch[r8*4]
0x1400731a2  mov     r13d, 10h
0x1400731a8  lea     eax, [rsi+10h]
0x1400731ab  cmp     eax, r13d
0x1400731ae  jb      loc_140073372
0x1400731b4  cmp     eax, 40h ; '@'
0x1400731b7  ja      short loc_1400731C2
0x1400731b9  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400731c0  jmp     short loc_1400731F0
0x1400731c2  cmp     eax, 100h
0x1400731c7  ja      short loc_1400731D2
0x1400731c9  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400731d0  jmp     short loc_1400731F0
0x1400731d2  cmp     eax, 400h
0x1400731d7  ja      short loc_1400731E2
0x1400731d9  lea     rbx, Lookaside
0x1400731e0  jmp     short loc_1400731F0
0x1400731e2  cmp     eax, 800h
0x1400731e7  ja      short loc_140073201
0x1400731e9  lea     rbx, stru_1400B31C0
0x1400731f0  mov     rcx, rbx; Lookaside
0x1400731f3  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400731fa  nop     dword ptr [rax+rax+00h]
0x1400731ff  jmp     short loc_14007321A
0x140073201  xor     ebx, ebx
0x140073203  mov     edx, eax
0x140073205  mov     r8d, 30303030h
0x14007320b  lea     ecx, [rbx+40h]
0x14007320e  call    cs:__imp_ExAllocatePool2
0x140073215  nop     dword ptr [rax+rax+00h]
0x14007321a  test    rax, rax
0x14007321d  jz      loc_140073372
0x140073223  mov     [rax], rbx
0x140073226  xor     edx, edx; Val
0x140073228  lea     rbx, [rax+10h]
0x14007322c  mov     r8d, esi; Size
0x14007322f  mov     rcx, rbx; void *
0x140073232  mov     dword ptr [rax+8], 30303030h
0x140073239  call    memset
0x14007323e  mov     dword ptr [rbx], 100180h
0x140073244  xor     r8d, r8d
0x140073247  mov     eax, [rdi]
0x140073249  mov     [rbx+4], eax
0x14007324c  mov     eax, [rdi]
0x14007324e  mov     [rbx+8], eax
0x140073251  cmp     [rdi], r8d
0x140073254  jbe     short loc_14007326B
0x140073256  lea     rax, [r8+r8*2]
0x14007325a  mov     ecx, [rdi+rax*4+0Ch]
0x14007325e  mov     [rbx+r8*4+0Ch], ecx
0x140073263  inc     r8d
0x140073266  cmp     r8d, [rdi]
0x140073269  jb      short loc_140073256
0x14007326b  mov     rcx, [r14]
0x14007326e  mov     r9, rbx; void *
0x140073271  mov     edx, 1; unsigned int
0x140073276  mov     [rsp+68h+var_48], esi; unsigned int
0x14007327a  mov     r8d, 0E010185h; unsigned int
0x140073280  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140073284  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140073289  mov     edi, eax
0x14007328b  test    eax, eax
0x14007328d  jz      short loc_1400732B8
0x14007328f  mov     rcx, cs:WPP_GLOBAL_Control
0x140073296  cmp     rcx, rbp
0x140073299  jz      loc_140073341
0x14007329f  mov     rcx, [rcx+18h]
0x1400732a3  mov     edx, 3Fh ; '?'
0x1400732a8  mov     r9d, eax
0x1400732ab  mov     r8, r15
0x1400732ae  call    WPP_SF_d
0x1400732b3  jmp     loc_140073341
0x1400732b8  mov     r9d, [rbx+8]
0x1400732bc  cmp     r9d, 1
0x1400732c0  jnz     short loc_1400732E4
0x1400732c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400732c9  cmp     rcx, rbp
0x1400732cc  jz      short loc_14007333A
0x1400732ce  mov     rcx, [rcx+18h]
0x1400732d2  lea     edx, [r9+3Fh]
0x1400732d6  mov     r9d, [rbx+0Ch]
0x1400732da  mov     r8, r15
0x1400732dd  call    WPP_SF_d
0x1400732e2  jmp     short loc_14007333A
0x1400732e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400732eb  cmp     rcx, rbp
0x1400732ee  jz      short loc_14007333A
0x1400732f0  mov     rcx, [rcx+18h]
0x1400732f4  mov     edx, 41h ; 'A'
0x1400732f9  mov     r8, r15
0x1400732fc  call    WPP_SF_d
0x140073301  xor     eax, eax
0x140073303  cmp     [rbx+8], eax
0x140073306  jbe     short loc_14007333A
0x140073308  mov     rcx, cs:WPP_GLOBAL_Control
0x14007330f  lea     esi, [rax+1]
0x140073312  cmp     rcx, rbp
0x140073315  jz      short loc_140073333
0x140073317  mov     eax, [rbx+rax*4+0Ch]
0x14007331b  mov     edx, 42h ; 'B'
0x140073320  mov     rcx, [rcx+18h]
0x140073324  mov     r9d, esi
0x140073327  mov     r8, r15
0x14007332a  mov     [rsp+68h+var_48], eax
0x14007332e  call    WPP_SF_Dd
0x140073333  mov     eax, esi
0x140073335  cmp     eax, [rbx+8]
0x140073338  jb      short loc_140073308
0x14007333a  mov     eax, [rbx+0Ch]
0x14007333d  mov     [r14+70h], eax
0x140073341  lea     rcx, [rbx-10h]; P
0x140073345  mov     rax, [rcx]
0x140073348  test    rax, rax
0x14007334b  jz      short loc_140073361
0x14007334d  mov     rdx, rcx; Entry
0x140073350  mov     rcx, rax; Lookaside
0x140073353  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007335a  nop     dword ptr [rax+rax+00h]
0x14007335f  jmp     short loc_1400733AC
0x140073361  mov     edx, [rcx+8]; Tag
0x140073364  call    cs:__imp_ExFreePoolWithTag
0x14007336b  nop     dword ptr [rax+rax+00h]
0x140073370  jmp     short loc_1400733AC
0x140073372  mov     edi, 0C000009Ah
0x140073377  mov     rcx, cs:WPP_GLOBAL_Control
0x14007337e  cmp     rcx, rbp
0x140073381  jz      short loc_1400733CC
0x140073383  mov     edx, 3Eh ; '>'
0x140073388  jmp     short loc_1400733A0
0x14007338a  mov     edi, 0C000000Dh
0x14007338f  mov     rcx, cs:WPP_GLOBAL_Control
0x140073396  cmp     rcx, rbp
0x140073399  jz      short loc_1400733CC
0x14007339b  mov     edx, 3Dh ; '='
0x1400733a0  mov     rcx, [rcx+18h]
0x1400733a4  mov     r8, r15
0x1400733a7  call    WPP_SF_
0x1400733ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400733b3  cmp     rcx, rbp
0x1400733b6  jz      short loc_1400733CC
0x1400733b8  mov     rcx, [rcx+18h]
0x1400733bc  mov     edx, 43h ; 'C'
0x1400733c1  mov     r9d, edi
0x1400733c4  mov     r8, r15
0x1400733c7  call    WPP_SF_d
0x1400733cc  mov     eax, edi
0x1400733ce  add     rsp, 30h
0x1400733d2  pop     r15
0x1400733d4  pop     r14
0x1400733d6  pop     r13
0x1400733d8  pop     rdi
0x1400733d9  pop     rsi
0x1400733da  pop     rbp
0x1400733db  pop     rbx
0x1400733dc  retn
```
