# ExtSTAOffloadNetworks(EXTSTA_VELAN *,void *,ulong)

- ea: `0x14006ad80`
- end: `0x14006aff9`
- name: `?ExtSTAOffloadNetworks@@YAJPEAUEXTSTA_VELAN@@PEAXK@Z`
- size: `633`
- prototype: `int(struct EXTSTA_VELAN *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140019bbc`
- `0x140020dc0`
- `0x14006ad80`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006ae45`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006ae45`
- `ntoskrnl!ExAllocatePool2` at `0x14006ae5a`
- `ntoskrnl!ExAllocatePool2` at `0x14006ae5a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006afc7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006afc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006afd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006afd8`

## pseudocode

```c
__int64 __fastcall ExtSTAOffloadNetworks(struct EXTSTA_VELAN *a1, _BYTE *a2, unsigned int a3, __int64 a4)
{
  __int64 v6; // rax
  __int64 v7; // rdx
  _ADAPT *pAdapt; // rcx
  unsigned int v9; // ebp
  unsigned int v10; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rdi
  _DWORD *Pool2; // rax
  _WORD *v13; // rsi
  __int64 v14; // r9
  __int64 v15; // r10
  __int64 v16; // r8
  char *v17; // rdi
  int v18; // eax
  unsigned int v19; // edi
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9

  if ( a3 < 0x18 )
    return (unsigned int)-1073741811;
  if ( *a2 != 0x80 )
    return (unsigned int)-1073741811;
  if ( a2[1] != 2 )
    return (unsigned int)-1073741811;
  v6 = *((unsigned __int16 *)a2 + 1);
  if ( (unsigned int)v6 > a3 )
    return (unsigned int)-1073741811;
  v7 = *((unsigned int *)a2 + 5);
  if ( v6 != 96 * v7 + 24 )
    return (unsigned int)-1073741811;
  pAdapt = a1->pGenVElan->pAdapt;
  if ( pAdapt->AdapterEnhancedCapabilities.uIhvWdiVersion )
  {
    v13 = 0;
    v18 = PtRequestAdapterSync(pAdapt, 1u, 0xE070103u, a2, a3);
    goto LABEL_26;
  }
  v9 = 76 * v7 + 24;
  v10 = 76 * v7 + 40;
  if ( v10 < 0x10 )
    return (unsigned int)-1073741670;
  if ( v10 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_16:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_18;
  }
  if ( v10 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_16;
  }
  if ( v10 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_16;
  }
  if ( v10 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_16;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v10, 845771639, a4);
LABEL_18:
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  Pool2[2] = 845771639;
  v13 = Pool2 + 4;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  memset(Pool2 + 4, 0, v9);
  *v13 = 384;
  v14 = 0;
  v13[1] = v9;
  *((_DWORD *)v13 + 1) = *((_DWORD *)a2 + 1);
  *((_DWORD *)v13 + 2) = *((_DWORD *)a2 + 2);
  *((_DWORD *)v13 + 3) = *((_DWORD *)a2 + 3);
  *((_DWORD *)v13 + 4) = *((_DWORD *)a2 + 4);
  for ( *((_DWORD *)v13 + 5) = *((_DWORD *)a2 + 5); (unsigned int)v14 < *((_DWORD *)a2 + 5); v14 = (unsigned int)(v14 + 1) )
  {
    v15 = 38LL * (unsigned int)v14;
    v16 = 0;
    *(_OWORD *)&v13[v15 + 12] = *(_OWORD *)&a2[96 * v14 + 24];
    v17 = (char *)&v13[v15];
    *(_OWORD *)&v13[v15 + 20] = *(_OWORD *)&a2[96 * v14 + 40];
    *(_DWORD *)&v13[v15 + 28] = *(_DWORD *)&a2[96 * v14 + 56];
    *((_DWORD *)v17 + 15) = *(_DWORD *)&a2[96 * v14 + 60];
    *((_DWORD *)v17 + 16) = *(_DWORD *)&a2[96 * v14 + 64];
    do
    {
      *(_DWORD *)&v13[4 * v16 + 34 + v15] = *(_DWORD *)&a2[96 * v14 + 68 + 12 * v16];
      *(_DWORD *)&v17[8 * v16 + 72] = *(_DWORD *)&a2[96 * v14 + 76 + 12 * v16];
      ++v16;
    }
    while ( v16 != 4 );
  }
  v18 = PtRequestAdapterSync(a1->pGenVElan->pAdapt, 1u, 0xE070103u, v13, v9);
LABEL_26:
  v19 = v18;
  if ( v18 >= 0 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_32;
    v22 = *((unsigned int *)a2 + 5);
    v21 = 71;
  }
  else
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_32;
    v21 = 70;
    v22 = (unsigned int)v18;
  }
  WPP_SF_d(v20->AttachedDevice, v21, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, v22);
LABEL_32:
  if ( v13 )
  {
    if ( *((_QWORD *)v13 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 - 2), v13 - 8);
    else
      ExFreePoolWithTag(v13 - 8, *((_DWORD *)v13 - 2));
  }
  return v19;
}

```

## disassembly

```asm
0x14006ad80  push    rbx
0x14006ad82  push    rbp
0x14006ad83  push    rsi
0x14006ad84  push    rdi
0x14006ad85  push    r14
0x14006ad87  sub     rsp, 30h
0x14006ad8b  mov     rbx, rdx
0x14006ad8e  mov     r14, rcx
0x14006ad91  cmp     r8d, 18h
0x14006ad95  jb      loc_14006AFE6
0x14006ad9b  cmp     byte ptr [rdx], 80h
0x14006ad9e  jnz     loc_14006AFE6
0x14006ada4  cmp     byte ptr [rdx+1], 2
0x14006ada8  jnz     loc_14006AFE6
0x14006adae  movzx   eax, word ptr [rdx+2]
0x14006adb2  cmp     eax, r8d
0x14006adb5  ja      loc_14006AFE6
0x14006adbb  mov     edx, [rdx+14h]
0x14006adbe  lea     rcx, [rdx+rdx*2]
0x14006adc2  shl     rcx, 5
0x14006adc6  add     rcx, 18h
0x14006adca  cmp     rax, rcx
0x14006adcd  jnz     loc_14006AFE6
0x14006add3  mov     rax, [r14+0A38h]
0x14006adda  mov     rcx, [rax+10h]; struct _ADAPT *
0x14006adde  cmp     dword ptr [rcx+53Ch], 0
0x14006ade5  ja      loc_14006AF47
0x14006adeb  imul    ebp, edx, 4Ch ; 'L'
0x14006adee  add     ebp, 18h
0x14006adf1  lea     eax, [rbp+10h]
0x14006adf4  cmp     eax, 10h
0x14006adf7  jb      loc_14006AF3D
0x14006adfd  mov     ecx, 40h ; '@'
0x14006ae02  mov     esi, 32697377h
0x14006ae07  cmp     eax, ecx
0x14006ae09  ja      short loc_14006AE14
0x14006ae0b  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14006ae12  jmp     short loc_14006AE42
0x14006ae14  cmp     eax, 100h
0x14006ae19  ja      short loc_14006AE24
0x14006ae1b  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006ae22  jmp     short loc_14006AE42
0x14006ae24  cmp     eax, 400h
0x14006ae29  ja      short loc_14006AE34
0x14006ae2b  lea     rdi, Lookaside
0x14006ae32  jmp     short loc_14006AE42
0x14006ae34  cmp     eax, 800h
0x14006ae39  ja      short loc_14006AE53
0x14006ae3b  lea     rdi, stru_1400B0180
0x14006ae42  mov     rcx, rdi; Lookaside
0x14006ae45  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006ae4c  nop     dword ptr [rax+rax+00h]
0x14006ae51  jmp     short loc_14006AE66
0x14006ae53  xor     edi, edi
0x14006ae55  mov     edx, eax
0x14006ae57  mov     r8d, esi
0x14006ae5a  call    cs:__imp_ExAllocatePool2
0x14006ae61  nop     dword ptr [rax+rax+00h]
0x14006ae66  test    rax, rax
0x14006ae69  jz      loc_14006AF3D
0x14006ae6f  mov     [rax+8], esi
0x14006ae72  xor     edx, edx; Val
0x14006ae74  lea     rsi, [rax+10h]
0x14006ae78  mov     r8d, ebp; Size
0x14006ae7b  mov     rcx, rsi; void *
0x14006ae7e  mov     [rax], rdi
0x14006ae81  call    memset
0x14006ae86  mov     word ptr [rsi], 180h
0x14006ae8b  xor     r9d, r9d
0x14006ae8e  mov     [rsi+2], bp
0x14006ae92  mov     eax, [rbx+4]
0x14006ae95  mov     [rsi+4], eax
0x14006ae98  mov     eax, [rbx+8]
0x14006ae9b  mov     [rsi+8], eax
0x14006ae9e  mov     eax, [rbx+0Ch]
0x14006aea1  mov     [rsi+0Ch], eax
0x14006aea4  mov     eax, [rbx+10h]
0x14006aea7  mov     [rsi+10h], eax
0x14006aeaa  mov     eax, [rbx+14h]
0x14006aead  mov     [rsi+14h], eax
0x14006aeb0  cmp     [rbx+14h], r9d
0x14006aeb4  jbe     short loc_14006AF29
0x14006aeb6  mov     r11d, r9d
0x14006aeb9  lea     rcx, [r9+r9*2]
0x14006aebd  shl     rcx, 5
0x14006aec1  imul    r10, r11, 4Ch ; 'L'
0x14006aec5  movups  xmm0, xmmword ptr [rcx+rbx+18h]
0x14006aeca  xor     r8d, r8d
0x14006aecd  movups  xmmword ptr [r10+rsi+18h], xmm0
0x14006aed3  lea     rdi, [r10+rsi]
0x14006aed7  movups  xmm1, xmmword ptr [rcx+rbx+28h]
0x14006aedc  movups  xmmword ptr [r10+rsi+28h], xmm1
0x14006aee2  mov     eax, [rcx+rbx+38h]
0x14006aee6  mov     [r10+rsi+38h], eax
0x14006aeeb  mov     eax, [rcx+rbx+3Ch]
0x14006aeef  mov     [rdi+3Ch], eax
0x14006aef2  mov     eax, [rcx+rbx+40h]
0x14006aef6  mov     [rdi+40h], eax
0x14006aef9  lea     rax, [r8+r9*8]
0x14006aefd  lea     rdx, [rax+rax*2]
0x14006af01  mov     eax, [rbx+rdx*4+44h]
0x14006af05  lea     rcx, [rsi+r8*8]
0x14006af09  mov     [rcx+r10+44h], eax
0x14006af0e  mov     eax, [rbx+rdx*4+4Ch]
0x14006af12  mov     [rdi+r8*8+48h], eax
0x14006af17  inc     r8
0x14006af1a  cmp     r8, 4
0x14006af1e  jnz     short loc_14006AEF9
0x14006af20  inc     r9d
0x14006af23  cmp     r9d, [rbx+14h]
0x14006af27  jb      short loc_14006AEB6
0x14006af29  mov     rcx, [r14+0A38h]
0x14006af30  mov     r9, rsi
0x14006af33  mov     [rsp+58h+var_38], ebp
0x14006af37  mov     rcx, [rcx+10h]
0x14006af3b  jmp     short loc_14006AF51
0x14006af3d  mov     edi, 0C000009Ah
0x14006af42  jmp     loc_14006AFEB
0x14006af47  xor     esi, esi
0x14006af49  mov     [rsp+58h+var_38], r8d; unsigned int
0x14006af4e  mov     r9, rbx; void *
0x14006af51  mov     r8d, 0E070103h; unsigned int
0x14006af57  mov     edx, 1; unsigned int
0x14006af5c  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006af61  mov     edi, eax
0x14006af63  test    eax, eax
0x14006af65  jns     short loc_14006AF84
0x14006af67  mov     rcx, cs:WPP_GLOBAL_Control
0x14006af6e  lea     rax, WPP_GLOBAL_Control
0x14006af75  cmp     rcx, rax
0x14006af78  jz      short loc_14006AFB0
0x14006af7a  mov     edx, 46h ; 'F'
0x14006af7f  mov     r9d, edi
0x14006af82  jmp     short loc_14006AFA0
0x14006af84  mov     rcx, cs:WPP_GLOBAL_Control
0x14006af8b  lea     rax, WPP_GLOBAL_Control
0x14006af92  cmp     rcx, rax
0x14006af95  jz      short loc_14006AFB0
0x14006af97  mov     r9d, [rbx+14h]
0x14006af9b  mov     edx, 47h ; 'G'
0x14006afa0  mov     rcx, [rcx+18h]
0x14006afa4  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006afab  call    WPP_SF_d
0x14006afb0  test    rsi, rsi
0x14006afb3  jz      short loc_14006AFEB
0x14006afb5  lea     rcx, [rsi-10h]; P
0x14006afb9  mov     rax, [rcx]
0x14006afbc  test    rax, rax
0x14006afbf  jz      short loc_14006AFD5
0x14006afc1  mov     rdx, rcx; Entry
0x14006afc4  mov     rcx, rax; Lookaside
0x14006afc7  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006afce  nop     dword ptr [rax+rax+00h]
0x14006afd3  jmp     short loc_14006AFEB
0x14006afd5  mov     edx, [rcx+8]; Tag
0x14006afd8  call    cs:__imp_ExFreePoolWithTag
0x14006afdf  nop     dword ptr [rax+rax+00h]
0x14006afe4  jmp     short loc_14006AFEB
0x14006afe6  mov     edi, 0C000000Dh
0x14006afeb  mov     eax, edi
0x14006afed  add     rsp, 30h
0x14006aff1  pop     r14
0x14006aff3  pop     rdi
0x14006aff4  pop     rsi
0x14006aff5  pop     rbp
0x14006aff6  pop     rbx
0x14006aff7  retn
```
