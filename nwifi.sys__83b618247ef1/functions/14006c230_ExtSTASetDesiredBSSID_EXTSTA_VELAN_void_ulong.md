# ExtSTASetDesiredBSSID(EXTSTA_VELAN *,void *,ulong)

- ea: `0x14006c230`
- end: `0x14006c482`
- name: `?ExtSTASetDesiredBSSID@@YAJPEAUEXTSTA_VELAN@@PEAXK@Z`
- size: `594`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x14000a54c`
- `0x140019bbc`
- `0x140020dc0`
- `0x14003ae2c`
- `0x140053288`
- `0x14006c230`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006c2d9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006c2d9`
- `ntoskrnl!ExAllocatePool2` at `0x14006c2ee`
- `ntoskrnl!ExAllocatePool2` at `0x14006c2ee`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006c443`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006c443`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c454`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c454`

## pseudocode

```c
__int64 __fastcall ExtSTASetDesiredBSSID(struct EXTSTA_VELAN *a1, void *a2, unsigned int a3)
{
  size_t v3; // r14
  unsigned __int64 v6; // rsi
  unsigned int v7; // ebp
  unsigned int v8; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  _DWORD *v11; // rdi
  __int64 v12; // r15
  int v13; // edx
  int v14; // ebx
  __int64 v15; // r9
  int v16; // ecx
  __int64 v17; // rax
  unsigned int v18; // ebp

  v3 = a3;
  v6 = a3 / 6uLL;
  if ( a3 != 6 * v6 )
    return (unsigned int)-1073741811;
  if ( a3 < 6 )
    return (unsigned int)-1073741811;
  v7 = a3 + 12;
  if ( a3 + 12 < a3 )
    return (unsigned int)-1073741811;
  v8 = a3 + 28;
  if ( v7 >= 0xFFFFFFF0 )
    return (unsigned int)-1073741670;
  if ( v8 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_13:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_15;
  }
  if ( v8 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_13;
  }
  if ( v8 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_13;
  }
  if ( v8 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_13;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v8, 808464432, 6 * v6);
LABEL_15:
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  Pool2[2] = 808464432;
  v11 = Pool2 + 4;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  Pool2[4] = 1311104;
  v12 = (__int64)(Pool2 + 7);
  Pool2[5] = v6;
  Pool2[6] = v6;
  memmove(Pool2 + 7, a2, v3);
  v14 = PtRequestAdapterSync(a1->pGenVElan->pAdapt, 1u, 0xE01017Eu, v11, v7);
  if ( v14 >= 0 )
  {
    v15 = (unsigned int)v11[2];
    if ( (_DWORD)v15 == 1 )
    {
      v16 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, v12);
    }
    else
    {
      v16 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, v15);
        v17 = 0;
        if ( v11[2] )
        {
          do
          {
            v16 = (int)WPP_GLOBAL_Control;
            v18 = v17 + 1;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              WPP_SF_d_MAC_(
                WPP_GLOBAL_Control->AttachedDevice,
                47,
                (unsigned int)WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids,
                v18,
                (__int64)v11 + 6 * v17 + 12);
            v17 = v18;
          }
          while ( v18 < v11[2] );
        }
      }
    }
    if ( (byte_1400AF801 & 1) != 0 )
      McTemplateK0pjqB6r2_EtwWriteTransfer(
        v16,
        v13,
        &a1->pGenVElan->gDeviceId,
        a1->pGenVElan,
        (__int64)&a1->pGenVElan->gDeviceId,
        v11[1],
        v12);
  }
  if ( v11 )
  {
    if ( *((_QWORD *)v11 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v11 - 2), v11 - 4);
    else
      ExFreePoolWithTag(v11 - 4, *(v11 - 2));
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14006c230  push    rbx
0x14006c232  push    rbp
0x14006c233  push    rsi
0x14006c234  push    rdi
0x14006c235  push    r12
0x14006c237  push    r13
0x14006c239  push    r14
0x14006c23b  push    r15
0x14006c23d  sub     rsp, 48h
0x14006c241  mov     r14d, r8d
0x14006c244  mov     rax, 0AAAAAAAAAAAAAAABh
0x14006c24e  mov     r12, rdx
0x14006c251  mov     r13, rcx
0x14006c254  mul     r14
0x14006c257  mov     rsi, rdx
0x14006c25a  shr     rsi, 2
0x14006c25e  lea     r9, [rsi+rsi*2]
0x14006c262  add     r9, r9
0x14006c265  cmp     r14, r9
0x14006c268  jnz     loc_14006C469
0x14006c26e  cmp     r8d, 6
0x14006c272  jb      loc_14006C469
0x14006c278  lea     ebp, [r8+0Ch]
0x14006c27c  cmp     ebp, r8d
0x14006c27f  jb      loc_14006C469
0x14006c285  lea     eax, [rbp+10h]
0x14006c288  cmp     eax, 10h
0x14006c28b  jb      loc_14006C462
0x14006c291  mov     ecx, 40h ; '@'
0x14006c296  mov     edi, 30303030h
0x14006c29b  cmp     eax, ecx
0x14006c29d  ja      short loc_14006C2A8
0x14006c29f  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14006c2a6  jmp     short loc_14006C2D6
0x14006c2a8  cmp     eax, 100h
0x14006c2ad  ja      short loc_14006C2B8
0x14006c2af  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006c2b6  jmp     short loc_14006C2D6
0x14006c2b8  cmp     eax, 400h
0x14006c2bd  ja      short loc_14006C2C8
0x14006c2bf  lea     rbx, Lookaside
0x14006c2c6  jmp     short loc_14006C2D6
0x14006c2c8  cmp     eax, 800h
0x14006c2cd  ja      short loc_14006C2E7
0x14006c2cf  lea     rbx, stru_1400B0180
0x14006c2d6  mov     rcx, rbx; Lookaside
0x14006c2d9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006c2e0  nop     dword ptr [rax+rax+00h]
0x14006c2e5  jmp     short loc_14006C2FA
0x14006c2e7  xor     ebx, ebx
0x14006c2e9  mov     edx, eax
0x14006c2eb  mov     r8d, edi
0x14006c2ee  call    cs:__imp_ExAllocatePool2
0x14006c2f5  nop     dword ptr [rax+rax+00h]
0x14006c2fa  test    rax, rax
0x14006c2fd  jz      loc_14006C462
0x14006c303  mov     [rax+8], edi
0x14006c306  mov     r8, r14; Size
0x14006c309  lea     rdi, [rax+10h]
0x14006c30d  mov     [rax], rbx
0x14006c310  mov     dword ptr [rdi], 140180h
0x14006c316  lea     r15, [rdi+0Ch]
0x14006c31a  mov     [rdi+4], esi
0x14006c31d  mov     rcx, r15; void *
0x14006c320  mov     rdx, r12; Src
0x14006c323  mov     [rdi+8], esi
0x14006c326  call    memmove
0x14006c32b  mov     rcx, [r13+0A38h]
0x14006c332  mov     r9, rdi; void *
0x14006c335  mov     edx, 1; unsigned int
0x14006c33a  mov     [rsp+88h+var_68], ebp; unsigned int
0x14006c33e  mov     r8d, 0E01017Eh; unsigned int
0x14006c344  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006c348  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006c34d  mov     ebx, eax
0x14006c34f  test    eax, eax
0x14006c351  js      loc_14006C42C
0x14006c357  mov     r9d, [rdi+8]
0x14006c35b  cmp     r9d, 1
0x14006c35f  jnz     short loc_14006C391
0x14006c361  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c368  lea     rsi, WPP_GLOBAL_Control
0x14006c36f  cmp     rcx, rsi
0x14006c372  jz      loc_14006C3FF
0x14006c378  mov     rcx, [rcx+18h]
0x14006c37c  lea     edx, [r9+2Ch]
0x14006c380  mov     r9, r15
0x14006c383  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006c38a  call    WPP_SF__MAC_
0x14006c38f  jmp     short loc_14006C3FF
0x14006c391  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c398  lea     rsi, WPP_GLOBAL_Control
0x14006c39f  cmp     rcx, rsi
0x14006c3a2  jz      short loc_14006C3FF
0x14006c3a4  mov     rcx, [rcx+18h]
0x14006c3a8  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006c3af  mov     edx, 2Eh ; '.'
0x14006c3b4  call    WPP_SF_d
0x14006c3b9  xor     eax, eax
0x14006c3bb  cmp     [rdi+8], eax
0x14006c3be  jbe     short loc_14006C3FF
0x14006c3c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c3c7  lea     ebp, [rax+1]
0x14006c3ca  cmp     rcx, rsi
0x14006c3cd  jz      short loc_14006C3F8
0x14006c3cf  mov     rcx, [rcx+18h]
0x14006c3d3  add     rax, 2
0x14006c3d7  mov     edx, 2Fh ; '/'
0x14006c3dc  mov     r9d, ebp
0x14006c3df  lea     rax, [rax+rax*2]
0x14006c3e3  lea     r8, [rdi+rax*2]
0x14006c3e7  mov     qword ptr [rsp+88h+var_68], r8
0x14006c3ec  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006c3f3  call    WPP_SF_d_MAC_
0x14006c3f8  mov     eax, ebp
0x14006c3fa  cmp     eax, [rdi+8]
0x14006c3fd  jb      short loc_14006C3C0
0x14006c3ff  test    cs:byte_1400AF801, 1
0x14006c406  jz      short loc_14006C42C
0x14006c408  mov     r9, [r13+0A38h]
0x14006c40f  mov     eax, [rdi+4]
0x14006c412  mov     [rsp+88h+var_58], r15
0x14006c417  mov     [rsp+88h+var_60], eax
0x14006c41b  lea     r8, [r9+1338h]
0x14006c422  mov     qword ptr [rsp+88h+var_68], r8
0x14006c427  call    McTemplateK0pjqB6r2_EtwWriteTransfer
0x14006c42c  test    rdi, rdi
0x14006c42f  jz      short loc_14006C46E
0x14006c431  lea     rcx, [rdi-10h]; P
0x14006c435  mov     rax, [rcx]
0x14006c438  test    rax, rax
0x14006c43b  jz      short loc_14006C451
0x14006c43d  mov     rdx, rcx; Entry
0x14006c440  mov     rcx, rax; Lookaside
0x14006c443  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006c44a  nop     dword ptr [rax+rax+00h]
0x14006c44f  jmp     short loc_14006C46E
0x14006c451  mov     edx, [rcx+8]; Tag
0x14006c454  call    cs:__imp_ExFreePoolWithTag
0x14006c45b  nop     dword ptr [rax+rax+00h]
0x14006c460  jmp     short loc_14006C46E
0x14006c462  mov     ebx, 0C000009Ah
0x14006c467  jmp     short loc_14006C46E
0x14006c469  mov     ebx, 0C000000Dh
0x14006c46e  mov     eax, ebx
0x14006c470  add     rsp, 48h
0x14006c474  pop     r15
0x14006c476  pop     r14
0x14006c478  pop     r13
0x14006c47a  pop     r12
0x14006c47c  pop     rdi
0x14006c47d  pop     rsi
0x14006c47e  pop     rbp
0x14006c47f  pop     rbx
0x14006c480  retn
```
