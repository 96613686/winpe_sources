# ExtAPIoctlSetDefaultKey(_EXTAP_IOCTL_HANDLER_ENTRY const *,_EXTAP_VELAN *,_IRP *,uchar *,ulong)

- ea: `0x140073820`
- end: `0x140073ad9`
- name: `?ExtAPIoctlSetDefaultKey@@YAHPEBU_EXTAP_IOCTL_HANDLER_ENTRY@@PEAU_EXTAP_VELAN@@PEAU_IRP@@PEAEK@Z`
- size: `697`
- prototype: `__int64 __fastcall(const struct _EXTAP_IOCTL_HANDLER_ENTRY *, struct _EXTAP_VELAN *, struct _IRP *, unsigned __int8 *, unsigned int Size)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d21c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140073820`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140073915`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140073915`
- `ntoskrnl!ExAllocatePool2` at `0x14007392a`
- `ntoskrnl!ExAllocatePool2` at `0x14007392a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140073a11`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140073a11`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073a25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073a25`

## pseudocode

```c
__int64 __fastcall ExtAPIoctlSetDefaultKey(
        const struct _EXTAP_IOCTL_HANDLER_ENTRY *a1,
        struct _EXTAP_VELAN *a2,
        struct _IRP *a3,
        unsigned __int8 *a4,
        unsigned int Size)
{
  unsigned int v8; // eax
  unsigned int v9; // ecx
  unsigned int v10; // edi
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // ebp
  unsigned int v14; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rdi
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v17; // rbx
  _DWORD *v18; // r14
  size_t v19; // r8
  unsigned int v20; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
  v8 = *((_DWORD *)a1 + 6);
  v9 = *((_DWORD *)a4 + 6);
  if ( v8 + v9 < v8 )
  {
    v10 = -1073676267;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_32;
    v12 = 99;
LABEL_31:
    WPP_SF_(v11->AttachedDevice, v12, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
    goto LABEL_32;
  }
  if ( v9 > 0xFFFF || Size < v8 + v9 || (unsigned int)(*((_DWORD *)a4 + 1) - 1) > 7 )
  {
    v10 = -1073741811;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_32;
    v12 = 100;
    goto LABEL_31;
  }
  v13 = v9 + 22;
  v14 = v9 + 38;
  if ( v9 + 38 < 0x10 )
    goto LABEL_27;
  if ( v14 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_18:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_20;
  }
  if ( v14 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_18;
  }
  if ( v14 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_18;
  }
  if ( v14 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_18;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v14, 808464432);
LABEL_20:
  v17 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  if ( Pool2 )
  {
    Pool2[2] = 808464432;
    v18 = Pool2 + 4;
    *(_QWORD *)Pool2 = p_DeviceQueue;
    memset(Pool2 + 4, 0, v13);
    *v18 = 1573248;
    v18[1] = *((_DWORD *)a4 + 1) - 1;
    *((_BYTE *)v18 + 18) = *((_DWORD *)a4 + 5) != 1;
    *((_BYTE *)v18 + 19) = *(_DWORD *)a4 != 0;
    v18[2] = *((_DWORD *)a4 + 2);
    v19 = *((unsigned __int16 *)a4 + 12);
    *((_WORD *)v18 + 10) = *((_WORD *)a4 + 12);
    memmove((char *)v18 + 22, a4 + 28, v19);
    v20 = PtRequestAdapterSync(a2->pVElan->pAdapt, 1u, *((_DWORD *)a1 + 2), v18, v13);
    v10 = v20;
    if ( v20 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, v20);
    memset(v18, 0, v13);
    if ( *v17 )
      ExFreeToNPagedLookasideList(*v17, v17);
    else
      ExFreePoolWithTag(v17, *((_DWORD *)v17 + 2));
    goto LABEL_32;
  }
LABEL_27:
  v10 = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
LABEL_32:
  memset(a4, 0, Size);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x140073820  push    rbx
0x140073822  push    rbp
0x140073823  push    rsi
0x140073824  push    rdi
0x140073825  push    r12
0x140073827  push    r13
0x140073829  push    r14
0x14007382b  push    r15
0x14007382d  sub     rsp, 38h
0x140073831  mov     rsi, r9
0x140073834  mov     r13, rdx
0x140073837  mov     r15, rcx
0x14007383a  mov     rcx, cs:WPP_GLOBAL_Control
0x140073841  lea     r8, WPP_GLOBAL_Control
0x140073848  cmp     rcx, r8
0x14007384b  jz      short loc_140073869
0x14007384d  mov     rcx, [rcx+18h]
0x140073851  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140073858  mov     edx, 62h ; 'b'
0x14007385d  call    WPP_SF_
0x140073862  lea     r8, WPP_GLOBAL_Control
0x140073869  mov     eax, [r15+18h]
0x14007386d  mov     ecx, [rsi+18h]
0x140073870  lea     edx, [rax+rcx]
0x140073873  cmp     edx, eax
0x140073875  jnb     short loc_140073896
0x140073877  mov     edi, 0C0010015h
0x14007387c  mov     rcx, cs:WPP_GLOBAL_Control
0x140073883  cmp     rcx, r8
0x140073886  jz      loc_140073A88
0x14007388c  mov     edx, 63h ; 'c'
0x140073891  jmp     loc_140073A78
0x140073896  cmp     ecx, 0FFFFh
0x14007389c  ja      loc_140073A62
0x1400738a2  cmp     dword ptr [rsp+78h+Size], edx
0x1400738a9  jb      loc_140073A62
0x1400738af  mov     eax, [rsi+4]
0x1400738b2  dec     eax
0x1400738b4  cmp     eax, 7
0x1400738b7  ja      loc_140073A62
0x1400738bd  lea     ebp, [rcx+16h]
0x1400738c0  lea     eax, [rbp+10h]
0x1400738c3  cmp     eax, 10h
0x1400738c6  jb      loc_140073A33
0x1400738cc  mov     ecx, 40h ; '@'
0x1400738d1  mov     r14d, 30303030h
0x1400738d7  cmp     eax, ecx
0x1400738d9  ja      short loc_1400738E4
0x1400738db  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x1400738e2  jmp     short loc_140073912
0x1400738e4  cmp     eax, 100h
0x1400738e9  ja      short loc_1400738F4
0x1400738eb  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400738f2  jmp     short loc_140073912
0x1400738f4  cmp     eax, 400h
0x1400738f9  ja      short loc_140073904
0x1400738fb  lea     rdi, Lookaside
0x140073902  jmp     short loc_140073912
0x140073904  cmp     eax, 800h
0x140073909  ja      short loc_140073923
0x14007390b  lea     rdi, stru_1400B31C0
0x140073912  mov     rcx, rdi; Lookaside
0x140073915  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007391c  nop     dword ptr [rax+rax+00h]
0x140073921  jmp     short loc_140073936
0x140073923  xor     edi, edi
0x140073925  mov     edx, eax
0x140073927  mov     r8d, r14d
0x14007392a  call    cs:__imp_ExAllocatePool2
0x140073931  nop     dword ptr [rax+rax+00h]
0x140073936  mov     rbx, rax
0x140073939  test    rax, rax
0x14007393c  jz      loc_140073A33
0x140073942  mov     [rax+8], r14d
0x140073946  xor     edx, edx; Val
0x140073948  lea     r14, [rax+10h]
0x14007394c  mov     r8d, ebp; Size
0x14007394f  mov     rcx, r14; void *
0x140073952  mov     [rax], rdi
0x140073955  mov     r12d, ebp
0x140073958  call    memset
0x14007395d  mov     dword ptr [r14], 180180h
0x140073964  lea     rdx, [rsi+1Ch]; Src
0x140073968  mov     eax, [rsi+4]
0x14007396b  lea     rcx, [r14+16h]; void *
0x14007396f  dec     eax
0x140073971  mov     [r14+4], eax
0x140073975  cmp     dword ptr [rsi+14h], 1
0x140073979  setnz   al
0x14007397c  mov     [r14+12h], al
0x140073980  cmp     dword ptr [rsi], 0
0x140073983  setnz   al
0x140073986  mov     [r14+13h], al
0x14007398a  mov     eax, [rsi+8]
0x14007398d  mov     [r14+8], eax
0x140073991  movzx   eax, word ptr [rsi+18h]
0x140073995  mov     r8d, eax; Size
0x140073998  mov     [r14+14h], ax
0x14007399d  call    memmove
0x1400739a2  mov     rcx, [r13+0]
0x1400739a6  mov     r9, r14; void *
0x1400739a9  mov     r8d, [r15+8]; unsigned int
0x1400739ad  mov     edx, 1; unsigned int
0x1400739b2  mov     [rsp+78h+var_58], ebp; unsigned int
0x1400739b6  mov     rcx, [rcx+10h]; struct _ADAPT *
0x1400739ba  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x1400739bf  mov     edi, eax
0x1400739c1  test    eax, eax
0x1400739c3  jz      short loc_1400739F2
0x1400739c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400739cc  lea     rbp, WPP_GLOBAL_Control
0x1400739d3  cmp     rcx, rbp
0x1400739d6  jz      short loc_1400739F9
0x1400739d8  mov     rcx, [rcx+18h]
0x1400739dc  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x1400739e3  mov     edx, 66h ; 'f'
0x1400739e8  mov     r9d, eax
0x1400739eb  call    WPP_SF_d
0x1400739f0  jmp     short loc_1400739F9
0x1400739f2  lea     rbp, WPP_GLOBAL_Control
0x1400739f9  mov     r8, r12; Size
0x1400739fc  xor     edx, edx; Val
0x1400739fe  mov     rcx, r14; void *
0x140073a01  call    memset
0x140073a06  mov     rcx, [rbx]; Lookaside
0x140073a09  test    rcx, rcx
0x140073a0c  jz      short loc_140073A1F
0x140073a0e  mov     rdx, rbx; Entry
0x140073a11  call    cs:__imp_ExFreeToNPagedLookasideList
0x140073a18  nop     dword ptr [rax+rax+00h]
0x140073a1d  jmp     short loc_140073A8F
0x140073a1f  mov     edx, [rbx+8]; Tag
0x140073a22  mov     rcx, rbx; P
0x140073a25  call    cs:__imp_ExFreePoolWithTag
0x140073a2c  nop     dword ptr [rax+rax+00h]
0x140073a31  jmp     short loc_140073A8F
0x140073a33  mov     edi, 0C000009Ah
0x140073a38  mov     rcx, cs:WPP_GLOBAL_Control
0x140073a3f  lea     rbp, WPP_GLOBAL_Control
0x140073a46  cmp     rcx, rbp
0x140073a49  jz      short loc_140073A8F
0x140073a4b  mov     rcx, [rcx+18h]
0x140073a4f  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140073a56  mov     edx, 65h ; 'e'
0x140073a5b  call    WPP_SF_
0x140073a60  jmp     short loc_140073A8F
0x140073a62  mov     edi, 0C000000Dh
0x140073a67  mov     rcx, cs:WPP_GLOBAL_Control
0x140073a6e  cmp     rcx, r8
0x140073a71  jz      short loc_140073A88
0x140073a73  mov     edx, 64h ; 'd'
0x140073a78  mov     rcx, [rcx+18h]
0x140073a7c  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140073a83  call    WPP_SF_
0x140073a88  lea     rbp, WPP_GLOBAL_Control
0x140073a8f  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x140073a97  xor     edx, edx; Val
0x140073a99  mov     rcx, rsi; void *
0x140073a9c  call    memset
0x140073aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140073aa8  cmp     rcx, rbp
0x140073aab  jz      short loc_140073AC5
0x140073aad  mov     rcx, [rcx+18h]
0x140073ab1  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140073ab8  mov     edx, 67h ; 'g'
0x140073abd  mov     r9d, edi
0x140073ac0  call    WPP_SF_d
0x140073ac5  mov     eax, edi
0x140073ac7  add     rsp, 38h
0x140073acb  pop     r15
0x140073acd  pop     r14
0x140073acf  pop     r13
0x140073ad1  pop     r12
0x140073ad3  pop     rdi
0x140073ad4  pop     rsi
0x140073ad5  pop     rbp
0x140073ad6  pop     rbx
0x140073ad7  retn
```
