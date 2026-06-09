# ExtAPIoctlSetAuthenticationAlgorithm(_EXTAP_IOCTL_HANDLER_ENTRY const *,_EXTAP_VELAN *,_IRP *,uchar *,ulong)

- ea: `0x1400718f0`
- end: `0x140071bae`
- name: `?ExtAPIoctlSetAuthenticationAlgorithm@@YAHPEBU_EXTAP_IOCTL_HANDLER_ENTRY@@PEAU_EXTAP_VELAN@@PEAU_IRP@@PEAEK@Z`
- size: `702`
- prototype: `__int64 __fastcall(const struct _EXTAP_IOCTL_HANDLER_ENTRY *, struct _EXTAP_VELAN *, struct _IRP *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d22c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140020f20`
- `0x1400718f0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400719c3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400719c3`
- `ntoskrnl!ExAllocatePool2` at `0x1400719de`
- `ntoskrnl!ExAllocatePool2` at `0x1400719de`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140071b23`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140071b23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071b34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071b34`

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
            Pool2 = (_DWORD *)ExAllocatePool2(64, v9, 808464432, a4);
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
0x1400718f0  push    rbx
0x1400718f2  push    rbp
0x1400718f3  push    rsi
0x1400718f4  push    rdi
0x1400718f5  push    r13
0x1400718f7  push    r14
0x1400718f9  push    r15
0x1400718fb  sub     rsp, 30h
0x1400718ff  mov     rdi, r9
0x140071902  mov     r14, rdx
0x140071905  mov     rcx, cs:WPP_GLOBAL_Control
0x14007190c  lea     rbp, WPP_GLOBAL_Control
0x140071913  lea     r15, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x14007191a  cmp     rcx, rbp
0x14007191d  jz      short loc_140071930
0x14007191f  mov     rcx, [rcx+18h]
0x140071923  mov     edx, 3Ch ; '<'
0x140071928  mov     r8, r15
0x14007192b  call    WPP_SF_
0x140071930  mov     ecx, [rsp+68h+arg_20]
0x140071937  mov     rax, 0AAAAAAAAAAAAAAABh
0x140071941  mov     r8d, [rdi]
0x140071944  add     ecx, 0FFFFFFF8h
0x140071947  mul     rcx
0x14007194a  shr     rdx, 3
0x14007194e  cmp     edx, r8d
0x140071951  jb      loc_140071B5A
0x140071957  cmp     [rdi+4], r8d
0x14007195b  jnz     loc_140071B5A
0x140071961  test    r8d, r8d
0x140071964  jz      loc_140071B5A
0x14007196a  lea     esi, ds:0Ch[r8*4]
0x140071972  mov     r13d, 10h
0x140071978  lea     eax, [rsi+10h]
0x14007197b  cmp     eax, r13d
0x14007197e  jb      loc_140071B42
0x140071984  cmp     eax, 40h ; '@'
0x140071987  ja      short loc_140071992
0x140071989  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140071990  jmp     short loc_1400719C0
0x140071992  cmp     eax, 100h
0x140071997  ja      short loc_1400719A2
0x140071999  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400719a0  jmp     short loc_1400719C0
0x1400719a2  cmp     eax, 400h
0x1400719a7  ja      short loc_1400719B2
0x1400719a9  lea     rbx, Lookaside
0x1400719b0  jmp     short loc_1400719C0
0x1400719b2  cmp     eax, 800h
0x1400719b7  ja      short loc_1400719D1
0x1400719b9  lea     rbx, stru_1400B0180
0x1400719c0  mov     rcx, rbx; Lookaside
0x1400719c3  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400719ca  nop     dword ptr [rax+rax+00h]
0x1400719cf  jmp     short loc_1400719EA
0x1400719d1  xor     ebx, ebx
0x1400719d3  mov     edx, eax
0x1400719d5  mov     r8d, 30303030h
0x1400719db  lea     ecx, [rbx+40h]
0x1400719de  call    cs:__imp_ExAllocatePool2
0x1400719e5  nop     dword ptr [rax+rax+00h]
0x1400719ea  test    rax, rax
0x1400719ed  jz      loc_140071B42
0x1400719f3  mov     [rax], rbx
0x1400719f6  xor     edx, edx; Val
0x1400719f8  lea     rbx, [rax+10h]
0x1400719fc  mov     r8d, esi; Size
0x1400719ff  mov     rcx, rbx; void *
0x140071a02  mov     dword ptr [rax+8], 30303030h
0x140071a09  call    memset
0x140071a0e  mov     dword ptr [rbx], 100180h
0x140071a14  xor     r8d, r8d
0x140071a17  mov     eax, [rdi]
0x140071a19  mov     [rbx+4], eax
0x140071a1c  mov     eax, [rdi]
0x140071a1e  mov     [rbx+8], eax
0x140071a21  cmp     [rdi], r8d
0x140071a24  jbe     short loc_140071A3B
0x140071a26  lea     rax, [r8+r8*2]
0x140071a2a  mov     ecx, [rdi+rax*4+0Ch]
0x140071a2e  mov     [rbx+r8*4+0Ch], ecx
0x140071a33  inc     r8d
0x140071a36  cmp     r8d, [rdi]
0x140071a39  jb      short loc_140071A26
0x140071a3b  mov     rcx, [r14]
0x140071a3e  mov     r9, rbx; void *
0x140071a41  mov     edx, 1; unsigned int
0x140071a46  mov     [rsp+68h+var_48], esi; unsigned int
0x140071a4a  mov     r8d, 0E010185h; unsigned int
0x140071a50  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140071a54  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140071a59  mov     edi, eax
0x140071a5b  test    eax, eax
0x140071a5d  jz      short loc_140071A88
0x140071a5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140071a66  cmp     rcx, rbp
0x140071a69  jz      loc_140071B11
0x140071a6f  mov     rcx, [rcx+18h]
0x140071a73  mov     edx, 3Fh ; '?'
0x140071a78  mov     r9d, eax
0x140071a7b  mov     r8, r15
0x140071a7e  call    WPP_SF_d
0x140071a83  jmp     loc_140071B11
0x140071a88  mov     r9d, [rbx+8]
0x140071a8c  cmp     r9d, 1
0x140071a90  jnz     short loc_140071AB4
0x140071a92  mov     rcx, cs:WPP_GLOBAL_Control
0x140071a99  cmp     rcx, rbp
0x140071a9c  jz      short loc_140071B0A
0x140071a9e  mov     rcx, [rcx+18h]
0x140071aa2  lea     edx, [r9+3Fh]
0x140071aa6  mov     r9d, [rbx+0Ch]
0x140071aaa  mov     r8, r15
0x140071aad  call    WPP_SF_d
0x140071ab2  jmp     short loc_140071B0A
0x140071ab4  mov     rcx, cs:WPP_GLOBAL_Control
0x140071abb  cmp     rcx, rbp
0x140071abe  jz      short loc_140071B0A
0x140071ac0  mov     rcx, [rcx+18h]
0x140071ac4  mov     edx, 41h ; 'A'
0x140071ac9  mov     r8, r15
0x140071acc  call    WPP_SF_d
0x140071ad1  xor     eax, eax
0x140071ad3  cmp     [rbx+8], eax
0x140071ad6  jbe     short loc_140071B0A
0x140071ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x140071adf  lea     esi, [rax+1]
0x140071ae2  cmp     rcx, rbp
0x140071ae5  jz      short loc_140071B03
0x140071ae7  mov     eax, [rbx+rax*4+0Ch]
0x140071aeb  mov     edx, 42h ; 'B'
0x140071af0  mov     rcx, [rcx+18h]
0x140071af4  mov     r9d, esi
0x140071af7  mov     r8, r15
0x140071afa  mov     [rsp+68h+var_48], eax
0x140071afe  call    WPP_SF_Dd
0x140071b03  mov     eax, esi
0x140071b05  cmp     eax, [rbx+8]
0x140071b08  jb      short loc_140071AD8
0x140071b0a  mov     eax, [rbx+0Ch]
0x140071b0d  mov     [r14+70h], eax
0x140071b11  lea     rcx, [rbx-10h]; P
0x140071b15  mov     rax, [rcx]
0x140071b18  test    rax, rax
0x140071b1b  jz      short loc_140071B31
0x140071b1d  mov     rdx, rcx; Entry
0x140071b20  mov     rcx, rax; Lookaside
0x140071b23  call    cs:__imp_ExFreeToNPagedLookasideList
0x140071b2a  nop     dword ptr [rax+rax+00h]
0x140071b2f  jmp     short loc_140071B7C
0x140071b31  mov     edx, [rcx+8]; Tag
0x140071b34  call    cs:__imp_ExFreePoolWithTag
0x140071b3b  nop     dword ptr [rax+rax+00h]
0x140071b40  jmp     short loc_140071B7C
0x140071b42  mov     edi, 0C000009Ah
0x140071b47  mov     rcx, cs:WPP_GLOBAL_Control
0x140071b4e  cmp     rcx, rbp
0x140071b51  jz      short loc_140071B9C
0x140071b53  mov     edx, 3Eh ; '>'
0x140071b58  jmp     short loc_140071B70
0x140071b5a  mov     edi, 0C000000Dh
0x140071b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140071b66  cmp     rcx, rbp
0x140071b69  jz      short loc_140071B9C
0x140071b6b  mov     edx, 3Dh ; '='
0x140071b70  mov     rcx, [rcx+18h]
0x140071b74  mov     r8, r15
0x140071b77  call    WPP_SF_
0x140071b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140071b83  cmp     rcx, rbp
0x140071b86  jz      short loc_140071B9C
0x140071b88  mov     rcx, [rcx+18h]
0x140071b8c  mov     edx, 43h ; 'C'
0x140071b91  mov     r9d, edi
0x140071b94  mov     r8, r15
0x140071b97  call    WPP_SF_d
0x140071b9c  mov     eax, edi
0x140071b9e  add     rsp, 30h
0x140071ba2  pop     r15
0x140071ba4  pop     r14
0x140071ba6  pop     r13
0x140071ba8  pop     rdi
0x140071ba9  pop     rsi
0x140071baa  pop     rbp
0x140071bab  pop     rbx
0x140071bac  retn
```
