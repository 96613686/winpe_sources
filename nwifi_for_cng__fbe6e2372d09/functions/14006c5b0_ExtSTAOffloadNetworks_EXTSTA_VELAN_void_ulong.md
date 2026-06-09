# ExtSTAOffloadNetworks(EXTSTA_VELAN *,void *,ulong)

- ea: `0x14006c5b0`
- end: `0x14006c829`
- name: `?ExtSTAOffloadNetworks@@YAJPEAUEXTSTA_VELAN@@PEAXK@Z`
- size: `633`
- prototype: `int(struct EXTSTA_VELAN *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140019bbc`
- `0x140020dc0`
- `0x14006c5b0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006c675`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006c675`
- `ntoskrnl!ExAllocatePool2` at `0x14006c68a`
- `ntoskrnl!ExAllocatePool2` at `0x14006c68a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006c7f7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006c7f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c808`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c808`

## pseudocode

```c
__int64 __fastcall ExtSTAOffloadNetworks(struct EXTSTA_VELAN *a1, _BYTE *a2, unsigned int a3)
{
  __int64 v5; // rax
  __int64 v6; // rdx
  _ADAPT *pAdapt; // rcx
  unsigned int v8; // ebp
  unsigned int v9; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rdi
  _DWORD *Pool2; // rax
  _WORD *v12; // rsi
  __int64 v13; // r9
  __int64 v14; // r10
  __int64 v15; // r8
  char *v16; // rdi
  int v17; // eax
  unsigned int v18; // edi
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9

  if ( a3 < 0x18 )
    return (unsigned int)-1073741811;
  if ( *a2 != 0x80 )
    return (unsigned int)-1073741811;
  if ( a2[1] != 2 )
    return (unsigned int)-1073741811;
  v5 = *((unsigned __int16 *)a2 + 1);
  if ( (unsigned int)v5 > a3 )
    return (unsigned int)-1073741811;
  v6 = *((unsigned int *)a2 + 5);
  if ( v5 != 96 * v6 + 24 )
    return (unsigned int)-1073741811;
  pAdapt = a1->pGenVElan->pAdapt;
  if ( pAdapt->AdapterEnhancedCapabilities.uIhvWdiVersion )
  {
    v12 = 0;
    v17 = PtRequestAdapterSync(pAdapt, 1u, 0xE070103u, a2, a3);
    goto LABEL_26;
  }
  v8 = 76 * v6 + 24;
  v9 = 76 * v6 + 40;
  if ( v9 < 0x10 )
    return (unsigned int)-1073741670;
  if ( v9 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_16:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_18;
  }
  if ( v9 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_16;
  }
  if ( v9 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_16;
  }
  if ( v9 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_16;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v9, 845771639);
LABEL_18:
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  Pool2[2] = 845771639;
  v12 = Pool2 + 4;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  memset(Pool2 + 4, 0, v8);
  *v12 = 384;
  v13 = 0;
  v12[1] = v8;
  *((_DWORD *)v12 + 1) = *((_DWORD *)a2 + 1);
  *((_DWORD *)v12 + 2) = *((_DWORD *)a2 + 2);
  *((_DWORD *)v12 + 3) = *((_DWORD *)a2 + 3);
  *((_DWORD *)v12 + 4) = *((_DWORD *)a2 + 4);
  for ( *((_DWORD *)v12 + 5) = *((_DWORD *)a2 + 5); (unsigned int)v13 < *((_DWORD *)a2 + 5); v13 = (unsigned int)(v13 + 1) )
  {
    v14 = 38LL * (unsigned int)v13;
    v15 = 0;
    *(_OWORD *)&v12[v14 + 12] = *(_OWORD *)&a2[96 * v13 + 24];
    v16 = (char *)&v12[v14];
    *(_OWORD *)&v12[v14 + 20] = *(_OWORD *)&a2[96 * v13 + 40];
    *(_DWORD *)&v12[v14 + 28] = *(_DWORD *)&a2[96 * v13 + 56];
    *((_DWORD *)v16 + 15) = *(_DWORD *)&a2[96 * v13 + 60];
    *((_DWORD *)v16 + 16) = *(_DWORD *)&a2[96 * v13 + 64];
    do
    {
      *(_DWORD *)&v12[4 * v15 + 34 + v14] = *(_DWORD *)&a2[96 * v13 + 68 + 12 * v15];
      *(_DWORD *)&v16[8 * v15 + 72] = *(_DWORD *)&a2[96 * v13 + 76 + 12 * v15];
      ++v15;
    }
    while ( v15 != 4 );
  }
  v17 = PtRequestAdapterSync(a1->pGenVElan->pAdapt, 1u, 0xE070103u, v12, v8);
LABEL_26:
  v18 = v17;
  if ( v17 >= 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_32;
    v21 = *((unsigned int *)a2 + 5);
    v20 = 71;
  }
  else
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_32;
    v20 = 70;
    v21 = (unsigned int)v17;
  }
  WPP_SF_d(v19->AttachedDevice, v20, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, v21);
LABEL_32:
  if ( v12 )
  {
    if ( *((_QWORD *)v12 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v12 - 2), v12 - 8);
    else
      ExFreePoolWithTag(v12 - 8, *((_DWORD *)v12 - 2));
  }
  return v18;
}

```

## disassembly

```asm
0x14006c5b0  push    rbx
0x14006c5b2  push    rbp
0x14006c5b3  push    rsi
0x14006c5b4  push    rdi
0x14006c5b5  push    r14
0x14006c5b7  sub     rsp, 30h
0x14006c5bb  mov     rbx, rdx
0x14006c5be  mov     r14, rcx
0x14006c5c1  cmp     r8d, 18h
0x14006c5c5  jb      loc_14006C816
0x14006c5cb  cmp     byte ptr [rdx], 80h
0x14006c5ce  jnz     loc_14006C816
0x14006c5d4  cmp     byte ptr [rdx+1], 2
0x14006c5d8  jnz     loc_14006C816
0x14006c5de  movzx   eax, word ptr [rdx+2]
0x14006c5e2  cmp     eax, r8d
0x14006c5e5  ja      loc_14006C816
0x14006c5eb  mov     edx, [rdx+14h]
0x14006c5ee  lea     rcx, [rdx+rdx*2]
0x14006c5f2  shl     rcx, 5
0x14006c5f6  add     rcx, 18h
0x14006c5fa  cmp     rax, rcx
0x14006c5fd  jnz     loc_14006C816
0x14006c603  mov     rax, [r14+0A38h]
0x14006c60a  mov     rcx, [rax+10h]; struct _ADAPT *
0x14006c60e  cmp     dword ptr [rcx+53Ch], 0
0x14006c615  ja      loc_14006C777
0x14006c61b  imul    ebp, edx, 4Ch ; 'L'
0x14006c61e  add     ebp, 18h
0x14006c621  lea     eax, [rbp+10h]
0x14006c624  cmp     eax, 10h
0x14006c627  jb      loc_14006C76D
0x14006c62d  mov     ecx, 40h ; '@'
0x14006c632  mov     esi, 32697377h
0x14006c637  cmp     eax, ecx
0x14006c639  ja      short loc_14006C644
0x14006c63b  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14006c642  jmp     short loc_14006C672
0x14006c644  cmp     eax, 100h
0x14006c649  ja      short loc_14006C654
0x14006c64b  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006c652  jmp     short loc_14006C672
0x14006c654  cmp     eax, 400h
0x14006c659  ja      short loc_14006C664
0x14006c65b  lea     rdi, Lookaside
0x14006c662  jmp     short loc_14006C672
0x14006c664  cmp     eax, 800h
0x14006c669  ja      short loc_14006C683
0x14006c66b  lea     rdi, stru_1400B31C0
0x14006c672  mov     rcx, rdi; Lookaside
0x14006c675  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006c67c  nop     dword ptr [rax+rax+00h]
0x14006c681  jmp     short loc_14006C696
0x14006c683  xor     edi, edi
0x14006c685  mov     edx, eax
0x14006c687  mov     r8d, esi
0x14006c68a  call    cs:__imp_ExAllocatePool2
0x14006c691  nop     dword ptr [rax+rax+00h]
0x14006c696  test    rax, rax
0x14006c699  jz      loc_14006C76D
0x14006c69f  mov     [rax+8], esi
0x14006c6a2  xor     edx, edx; Val
0x14006c6a4  lea     rsi, [rax+10h]
0x14006c6a8  mov     r8d, ebp; Size
0x14006c6ab  mov     rcx, rsi; void *
0x14006c6ae  mov     [rax], rdi
0x14006c6b1  call    memset
0x14006c6b6  mov     word ptr [rsi], 180h
0x14006c6bb  xor     r9d, r9d
0x14006c6be  mov     [rsi+2], bp
0x14006c6c2  mov     eax, [rbx+4]
0x14006c6c5  mov     [rsi+4], eax
0x14006c6c8  mov     eax, [rbx+8]
0x14006c6cb  mov     [rsi+8], eax
0x14006c6ce  mov     eax, [rbx+0Ch]
0x14006c6d1  mov     [rsi+0Ch], eax
0x14006c6d4  mov     eax, [rbx+10h]
0x14006c6d7  mov     [rsi+10h], eax
0x14006c6da  mov     eax, [rbx+14h]
0x14006c6dd  mov     [rsi+14h], eax
0x14006c6e0  cmp     [rbx+14h], r9d
0x14006c6e4  jbe     short loc_14006C759
0x14006c6e6  mov     r11d, r9d
0x14006c6e9  lea     rcx, [r9+r9*2]
0x14006c6ed  shl     rcx, 5
0x14006c6f1  imul    r10, r11, 4Ch ; 'L'
0x14006c6f5  movups  xmm0, xmmword ptr [rcx+rbx+18h]
0x14006c6fa  xor     r8d, r8d
0x14006c6fd  movups  xmmword ptr [r10+rsi+18h], xmm0
0x14006c703  lea     rdi, [r10+rsi]
0x14006c707  movups  xmm1, xmmword ptr [rcx+rbx+28h]
0x14006c70c  movups  xmmword ptr [r10+rsi+28h], xmm1
0x14006c712  mov     eax, [rcx+rbx+38h]
0x14006c716  mov     [r10+rsi+38h], eax
0x14006c71b  mov     eax, [rcx+rbx+3Ch]
0x14006c71f  mov     [rdi+3Ch], eax
0x14006c722  mov     eax, [rcx+rbx+40h]
0x14006c726  mov     [rdi+40h], eax
0x14006c729  lea     rax, [r8+r9*8]
0x14006c72d  lea     rdx, [rax+rax*2]
0x14006c731  mov     eax, [rbx+rdx*4+44h]
0x14006c735  lea     rcx, [rsi+r8*8]
0x14006c739  mov     [rcx+r10+44h], eax
0x14006c73e  mov     eax, [rbx+rdx*4+4Ch]
0x14006c742  mov     [rdi+r8*8+48h], eax
0x14006c747  inc     r8
0x14006c74a  cmp     r8, 4
0x14006c74e  jnz     short loc_14006C729
0x14006c750  inc     r9d
0x14006c753  cmp     r9d, [rbx+14h]
0x14006c757  jb      short loc_14006C6E6
0x14006c759  mov     rcx, [r14+0A38h]
0x14006c760  mov     r9, rsi
0x14006c763  mov     [rsp+58h+var_38], ebp
0x14006c767  mov     rcx, [rcx+10h]
0x14006c76b  jmp     short loc_14006C781
0x14006c76d  mov     edi, 0C000009Ah
0x14006c772  jmp     loc_14006C81B
0x14006c777  xor     esi, esi
0x14006c779  mov     [rsp+58h+var_38], r8d; unsigned int
0x14006c77e  mov     r9, rbx; void *
0x14006c781  mov     r8d, 0E070103h; unsigned int
0x14006c787  mov     edx, 1; unsigned int
0x14006c78c  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006c791  mov     edi, eax
0x14006c793  test    eax, eax
0x14006c795  jns     short loc_14006C7B4
0x14006c797  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c79e  lea     rax, WPP_GLOBAL_Control
0x14006c7a5  cmp     rcx, rax
0x14006c7a8  jz      short loc_14006C7E0
0x14006c7aa  mov     edx, 46h ; 'F'
0x14006c7af  mov     r9d, edi
0x14006c7b2  jmp     short loc_14006C7D0
0x14006c7b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c7bb  lea     rax, WPP_GLOBAL_Control
0x14006c7c2  cmp     rcx, rax
0x14006c7c5  jz      short loc_14006C7E0
0x14006c7c7  mov     r9d, [rbx+14h]
0x14006c7cb  mov     edx, 47h ; 'G'
0x14006c7d0  mov     rcx, [rcx+18h]
0x14006c7d4  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006c7db  call    WPP_SF_d
0x14006c7e0  test    rsi, rsi
0x14006c7e3  jz      short loc_14006C81B
0x14006c7e5  lea     rcx, [rsi-10h]; P
0x14006c7e9  mov     rax, [rcx]
0x14006c7ec  test    rax, rax
0x14006c7ef  jz      short loc_14006C805
0x14006c7f1  mov     rdx, rcx; Entry
0x14006c7f4  mov     rcx, rax; Lookaside
0x14006c7f7  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006c7fe  nop     dword ptr [rax+rax+00h]
0x14006c803  jmp     short loc_14006C81B
0x14006c805  mov     edx, [rcx+8]; Tag
0x14006c808  call    cs:__imp_ExFreePoolWithTag
0x14006c80f  nop     dword ptr [rax+rax+00h]
0x14006c814  jmp     short loc_14006C81B
0x14006c816  mov     edi, 0C000000Dh
0x14006c81b  mov     eax, edi
0x14006c81d  add     rsp, 30h
0x14006c821  pop     r14
0x14006c823  pop     rdi
0x14006c824  pop     rsi
0x14006c825  pop     rbp
0x14006c826  pop     rbx
0x14006c827  retn
```
