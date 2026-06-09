# ExtSTASetMulticastCipherAlgo(EXTSTA_VELAN *,_DOT11_CIPHER_ALGO_LIST const *,ulong)

- ea: `0x14006e410`
- end: `0x14006e702`
- name: `?ExtSTASetMulticastCipherAlgo@@YAJPEAUEXTSTA_VELAN@@PEBU_DOT11_CIPHER_ALGO_LIST@@K@Z`
- size: `754`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, const struct _DOT11_CIPHER_ALGO_LIST *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x140019bbc`
- `0x140020dc0`
- `0x140020f20`
- `0x14006e410`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006e56e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006e56e`
- `ntoskrnl!ExAllocatePool2` at `0x14006e583`
- `ntoskrnl!ExAllocatePool2` at `0x14006e583`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006e6c7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006e6c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e6d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e6d8`

## pseudocode

```c
__int64 __fastcall ExtSTASetMulticastCipherAlgo(
        struct EXTSTA_VELAN *a1,
        const struct _DOT11_CIPHER_ALGO_LIST *a2,
        int a3)
{
  unsigned int v3; // r9d
  __int64 i; // rax
  unsigned int v7; // ecx
  __int64 v8; // rbx
  unsigned int v9; // r8d
  __int64 v10; // rdi
  unsigned int v11; // r11d
  __int64 v12; // rdx
  int v13; // r10d
  __int64 j; // rdx
  int v15; // ebx
  unsigned int v16; // ebp
  unsigned int v17; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  __int64 v20; // r8
  __int64 v21; // rdx
  unsigned int *k; // rdi
  __int64 v23; // r9
  __int64 v24; // rax
  unsigned int v25; // ebp

  v3 = *(_DWORD *)a2;
  if ( (a3 - 8) / 0xCu < *(_DWORD *)a2 )
    return (unsigned int)-1073741789;
  if ( v3 != *((_DWORD *)a2 + 1) )
    return (unsigned int)-1073741811;
  if ( v3 )
  {
    for ( i = 0; (unsigned int)i < v3 - 1; i = (unsigned int)(i + 1) )
    {
      v7 = i + 1;
      if ( (int)i + 1 < v3 )
      {
        while ( *((_DWORD *)a2 + 3 * i + 3) != *((_DWORD *)a2 + 3 * v7 + 3) )
        {
          if ( ++v7 >= v3 )
            goto LABEL_9;
        }
        return (unsigned int)-1073741811;
      }
LABEL_9:
      ;
    }
  }
  v8 = 1944;
  v9 = 0;
  v10 = 1952;
  if ( a1->Rw.DesiredBSSType != dot11_BSS_type_infrastructure )
  {
    v8 = 2056;
    v10 = 2064;
  }
LABEL_12:
  if ( v9 < v3 )
  {
    v11 = *(unsigned int *)((char *)&a1->ModuleStatus.uValue + v8);
    v12 = 0;
    v13 = *((_DWORD *)a2 + 3 * v9 + 3);
    while ( (unsigned int)v12 < v11 )
    {
      if ( *(_DWORD *)(*(_QWORD *)((char *)&a1->ModuleStatus.0 + v10) + 4 * v12) == v13 )
      {
LABEL_22:
        ++v9;
        goto LABEL_12;
      }
      v12 = (unsigned int)(v12 + 1);
    }
    if ( ((v13 - 1) & 0xFFFFFFFB) == 0 )
    {
      for ( j = 0; (unsigned int)j < v11; j = (unsigned int)(j + 1) )
      {
        if ( *(_DWORD *)(*(_QWORD *)((char *)&a1->ModuleStatus.0 + v10) + 4 * j) == 257 )
          goto LABEL_22;
      }
    }
    return (unsigned int)-1073741811;
  }
  v16 = 4 * *(unsigned int *)((char *)&a1->ModuleStatus.uValue + v8) + 12;
  v17 = 4 * *(unsigned int *)((char *)&a1->ModuleStatus.uValue + v8) + 28;
  if ( v17 < 0x10 )
    return (unsigned int)-1073741670;
  if ( v17 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_33:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_35;
  }
  if ( v17 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_33;
  }
  if ( v17 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_33;
  }
  if ( v17 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_33;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v17, 808464432);
LABEL_35:
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  Pool2[2] = 808464432;
  v20 = 0;
  v21 = 0;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  for ( k = Pool2 + 4; (unsigned int)v21 < *(_DWORD *)a2; v21 = (unsigned int)(v21 + 1) )
  {
    if ( *((_DWORD *)a2 + 3 * v21 + 4) )
    {
      k[v20 + 3] = *((_DWORD *)a2 + 3 * v21 + 3);
      v20 = (unsigned int)(v20 + 1);
    }
  }
  *k = 1048960;
  Pool2[6] = v20;
  Pool2[5] = v20;
  v15 = PtRequestAdapterSync(a1->pGenVElan->pAdapt, 1u, 0xE010189u, k, v16);
  if ( v15 >= 0 )
  {
    memmove(a1->Rw.pEnabledMcastCiphers, k, v16);
    v23 = k[2];
    if ( (_DWORD)v23 == 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, k[3]);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, v23);
      v24 = 0;
      if ( k[2] )
      {
        do
        {
          v25 = v24 + 1;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              37,
              WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids,
              v25,
              k[v24 + 3]);
          v24 = v25;
        }
        while ( v25 < k[2] );
      }
    }
  }
  if ( k )
  {
    if ( *((_QWORD *)k - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)k - 2), k - 4);
    else
      ExFreePoolWithTag(k - 4, *(k - 2));
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14006e410  push    rbx
0x14006e412  push    rbp
0x14006e413  push    rsi
0x14006e414  push    rdi
0x14006e415  push    r13
0x14006e417  push    r14
0x14006e419  sub     rsp, 38h
0x14006e41d  mov     r9d, [rdx]
0x14006e420  add     r8d, 0FFFFFFF8h
0x14006e424  mov     rsi, rdx
0x14006e427  mov     rax, 0AAAAAAAAAAAAAAABh
0x14006e431  mul     r8
0x14006e434  mov     r14, rcx
0x14006e437  shr     rdx, 3
0x14006e43b  cmp     edx, r9d
0x14006e43e  jb      loc_14006E6ED
0x14006e444  cmp     r9d, [rsi+4]
0x14006e448  jnz     loc_14006E500
0x14006e44e  test    r9d, r9d
0x14006e451  jz      short loc_14006E48D
0x14006e453  xor     eax, eax
0x14006e455  lea     r8d, [r9-1]
0x14006e459  cmp     eax, r8d
0x14006e45c  jnb     short loc_14006E48D
0x14006e45e  lea     edx, [rax+1]
0x14006e461  mov     ecx, edx
0x14006e463  cmp     edx, r9d
0x14006e466  jnb     short loc_14006E489
0x14006e468  inc     rax
0x14006e46b  lea     rax, [rax+rax*2]
0x14006e46f  mov     r10d, [rsi+rax*4]
0x14006e473  mov     eax, ecx
0x14006e475  inc     rax
0x14006e478  lea     rax, [rax+rax*2]
0x14006e47c  cmp     r10d, [rsi+rax*4]
0x14006e480  jz      short loc_14006E500
0x14006e482  inc     ecx
0x14006e484  cmp     ecx, r9d
0x14006e487  jb      short loc_14006E473
0x14006e489  mov     eax, edx
0x14006e48b  jmp     short loc_14006E459
0x14006e48d  mov     ebx, 798h
0x14006e492  xor     r8d, r8d
0x14006e495  cmp     dword ptr [r14+6BCh], 1
0x14006e49d  lea     ecx, [rbx+70h]
0x14006e4a0  lea     edi, [rcx-68h]
0x14006e4a3  cmovnz  ebx, ecx
0x14006e4a6  lea     ecx, [rdi+70h]
0x14006e4a9  cmovnz  edi, ecx
0x14006e4ac  cmp     r8d, r9d
0x14006e4af  jnb     short loc_14006E50A
0x14006e4b1  mov     r11d, [rbx+r14]
0x14006e4b5  mov     eax, r8d
0x14006e4b8  inc     rax
0x14006e4bb  xor     edx, edx
0x14006e4bd  lea     rax, [rax+rax*2]
0x14006e4c1  mov     r10d, [rsi+rax*4]
0x14006e4c5  cmp     edx, r11d
0x14006e4c8  jnb     short loc_14006E4D8
0x14006e4ca  mov     rax, [rdi+r14]
0x14006e4ce  cmp     [rax+rdx*4], r10d
0x14006e4d2  jz      short loc_14006E4FB
0x14006e4d4  inc     edx
0x14006e4d6  jmp     short loc_14006E4C5
0x14006e4d8  lea     eax, [r10-1]
0x14006e4dc  test    eax, 0FFFFFFFBh
0x14006e4e1  jnz     short loc_14006E500
0x14006e4e3  xor     edx, edx
0x14006e4e5  cmp     edx, r11d
0x14006e4e8  jnb     short loc_14006E500
0x14006e4ea  mov     rax, [rdi+r14]
0x14006e4ee  cmp     dword ptr [rax+rdx*4], 101h
0x14006e4f5  jz      short loc_14006E4FB
0x14006e4f7  inc     edx
0x14006e4f9  jmp     short loc_14006E4E5
0x14006e4fb  inc     r8d
0x14006e4fe  jmp     short loc_14006E4AC
0x14006e500  mov     ebx, 0C000000Dh
0x14006e505  jmp     loc_14006E6F2
0x14006e50a  mov     eax, [rbx+r14]
0x14006e50e  mov     r13d, 10h
0x14006e514  lea     ebp, ds:0Ch[rax*4]
0x14006e51b  lea     eax, [rbp+10h]
0x14006e51e  cmp     eax, r13d
0x14006e521  jb      loc_14006E6E6
0x14006e527  lea     ecx, [r13+30h]
0x14006e52b  mov     edi, 30303030h
0x14006e530  cmp     eax, ecx
0x14006e532  ja      short loc_14006E53D
0x14006e534  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14006e53b  jmp     short loc_14006E56B
0x14006e53d  cmp     eax, 100h
0x14006e542  ja      short loc_14006E54D
0x14006e544  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006e54b  jmp     short loc_14006E56B
0x14006e54d  cmp     eax, 400h
0x14006e552  ja      short loc_14006E55D
0x14006e554  lea     rbx, Lookaside
0x14006e55b  jmp     short loc_14006E56B
0x14006e55d  cmp     eax, 800h
0x14006e562  ja      short loc_14006E57C
0x14006e564  lea     rbx, stru_1400B31C0
0x14006e56b  mov     rcx, rbx; Lookaside
0x14006e56e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006e575  nop     dword ptr [rax+rax+00h]
0x14006e57a  jmp     short loc_14006E58F
0x14006e57c  xor     ebx, ebx
0x14006e57e  mov     edx, eax
0x14006e580  mov     r8d, edi
0x14006e583  call    cs:__imp_ExAllocatePool2
0x14006e58a  nop     dword ptr [rax+rax+00h]
0x14006e58f  test    rax, rax
0x14006e592  jz      loc_14006E6E6
0x14006e598  mov     [rax+8], edi
0x14006e59b  xor     r8d, r8d
0x14006e59e  xor     edx, edx
0x14006e5a0  mov     [rax], rbx
0x14006e5a3  lea     rdi, [rax+10h]
0x14006e5a7  cmp     [rsi], edx
0x14006e5a9  jbe     short loc_14006E5C8
0x14006e5ab  lea     rax, [rdx+rdx*2]
0x14006e5af  cmp     dword ptr [rsi+rax*4+10h], 0
0x14006e5b4  jz      short loc_14006E5C2
0x14006e5b6  mov     eax, [rsi+rax*4+0Ch]
0x14006e5ba  mov     [rdi+r8*4+0Ch], eax
0x14006e5bf  inc     r8d
0x14006e5c2  inc     edx
0x14006e5c4  cmp     edx, [rsi]
0x14006e5c6  jb      short loc_14006E5AB
0x14006e5c8  mov     dword ptr [rdi], 100180h
0x14006e5ce  mov     r9, rdi; void *
0x14006e5d1  mov     [rdi+8], r8d
0x14006e5d5  mov     edx, 1; unsigned int
0x14006e5da  mov     [rdi+4], r8d
0x14006e5de  mov     r8d, 0E010189h; unsigned int
0x14006e5e4  mov     rcx, [r14+0A38h]
0x14006e5eb  mov     [rsp+68h+var_48], ebp; unsigned int
0x14006e5ef  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006e5f3  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006e5f8  mov     ebx, eax
0x14006e5fa  test    eax, eax
0x14006e5fc  js      loc_14006E6B0
0x14006e602  mov     rcx, [r14+6D0h]; void *
0x14006e609  mov     rdx, rdi; Src
0x14006e60c  mov     r8d, ebp; Size
0x14006e60f  call    memmove
0x14006e614  mov     r9d, [rdi+8]
0x14006e618  cmp     r9d, 1
0x14006e61c  jnz     short loc_14006E64B
0x14006e61e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e625  lea     rsi, WPP_GLOBAL_Control
0x14006e62c  cmp     rcx, rsi
0x14006e62f  jz      short loc_14006E6B0
0x14006e631  mov     rcx, [rcx+18h]
0x14006e635  lea     edx, [r9+22h]
0x14006e639  mov     r9d, [rdi+0Ch]
0x14006e63d  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006e644  call    WPP_SF_d
0x14006e649  jmp     short loc_14006E6B0
0x14006e64b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e652  lea     rsi, WPP_GLOBAL_Control
0x14006e659  cmp     rcx, rsi
0x14006e65c  jz      short loc_14006E6B0
0x14006e65e  mov     rcx, [rcx+18h]
0x14006e662  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006e669  mov     edx, 24h ; '$'
0x14006e66e  call    WPP_SF_d
0x14006e673  xor     eax, eax
0x14006e675  cmp     [rdi+8], eax
0x14006e678  jbe     short loc_14006E6B0
0x14006e67a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e681  lea     ebp, [rax+1]
0x14006e684  cmp     rcx, rsi
0x14006e687  jz      short loc_14006E6A9
0x14006e689  mov     eax, [rdi+rax*4+0Ch]
0x14006e68d  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006e694  mov     rcx, [rcx+18h]
0x14006e698  mov     edx, 25h ; '%'
0x14006e69d  mov     r9d, ebp
0x14006e6a0  mov     [rsp+68h+var_48], eax
0x14006e6a4  call    WPP_SF_Dd
0x14006e6a9  mov     eax, ebp
0x14006e6ab  cmp     eax, [rdi+8]
0x14006e6ae  jb      short loc_14006E67A
0x14006e6b0  test    rdi, rdi
0x14006e6b3  jz      short loc_14006E6F2
0x14006e6b5  lea     rcx, [rdi-10h]; P
0x14006e6b9  mov     rax, [rcx]
0x14006e6bc  test    rax, rax
0x14006e6bf  jz      short loc_14006E6D5
0x14006e6c1  mov     rdx, rcx; Entry
0x14006e6c4  mov     rcx, rax; Lookaside
0x14006e6c7  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006e6ce  nop     dword ptr [rax+rax+00h]
0x14006e6d3  jmp     short loc_14006E6F2
0x14006e6d5  mov     edx, [rcx+8]; Tag
0x14006e6d8  call    cs:__imp_ExFreePoolWithTag
0x14006e6df  nop     dword ptr [rax+rax+00h]
0x14006e6e4  jmp     short loc_14006E6F2
0x14006e6e6  mov     ebx, 0C000009Ah
0x14006e6eb  jmp     short loc_14006E6F2
0x14006e6ed  mov     ebx, 0C0000023h
0x14006e6f2  mov     eax, ebx
0x14006e6f4  add     rsp, 38h
0x14006e6f8  pop     r14
0x14006e6fa  pop     r13
0x14006e6fc  pop     rdi
0x14006e6fd  pop     rsi
0x14006e6fe  pop     rbp
0x14006e6ff  pop     rbx
0x14006e700  retn
```
