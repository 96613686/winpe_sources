# UpdateCapabilityDerivedData

- ea: `0x1400670d0`
- end: `0x140067650`
- name: `UpdateCapabilityDerivedData`
- size: `1408`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140066b40`

## callees

- `0x14000d21c`
- `0x140030244`
- `0x1400670d0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140067160`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140067338`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006742a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140067537`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140067160`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140067338`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006742a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140067537`
- `ntoskrnl!ExAllocatePool2` at `0x140067178`
- `ntoskrnl!ExAllocatePool2` at `0x14006735a`
- `ntoskrnl!ExAllocatePool2` at `0x140067442`
- `ntoskrnl!ExAllocatePool2` at `0x140067550`
- `ntoskrnl!ExAllocatePool2` at `0x140067178`
- `ntoskrnl!ExAllocatePool2` at `0x14006735a`
- `ntoskrnl!ExAllocatePool2` at `0x140067442`
- `ntoskrnl!ExAllocatePool2` at `0x140067550`

## pseudocode

```c
__int64 __fastcall UpdateCapabilityDerivedData(__int64 *a1)
{
  __int64 v1; // rsi
  __int64 v3; // rbp
  unsigned int v4; // r14d
  unsigned int v5; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // r15
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  unsigned int i; // ebx
  __int64 v10; // r9
  unsigned int v11; // edx
  __int64 v12; // rcx
  __int64 j; // rdx
  unsigned int v14; // r10d
  __int64 v15; // r8
  unsigned int v16; // ebx
  __int64 k; // rcx
  unsigned int v18; // r8d
  __int64 v19; // rdx
  unsigned int v20; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v21; // rbx
  _DWORD *v22; // rax
  __int64 v23; // rax
  __int64 v24; // r9
  unsigned int v25; // edx
  __int64 m; // rcx
  unsigned int v27; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v28; // rbx
  _DWORD *v29; // rax
  PDEVICE_OBJECT v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // r9
  unsigned int v34; // edx
  __int64 n; // rcx
  __int64 v36; // rax
  unsigned int v37; // eax
  _DWORD *v38; // rax
  __int64 v39; // rax
  __int64 v40; // r9
  unsigned int v41; // edx
  __int64 ii; // rcx

  v1 = *a1;
  v3 = a1[1];
  if ( *(_DWORD *)(*a1 + 4) >= *(_DWORD *)(v3 + 4) )
  {
    v3 = *a1;
    v1 = a1[1];
  }
  v4 = *(_DWORD *)(v1 + 4);
  a1[4] = 0;
  v5 = 4 * v4 + 16;
  if ( 4 * v4 >= 0xFFFFFFF0 )
  {
LABEL_108:
    v16 = -1073741670;
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v31 = 38;
LABEL_110:
      WPP_SF_(v30->AttachedDevice, v31, WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids);
      return v16;
    }
    return v16;
  }
  p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  if ( v5 <= 0x40 )
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_12:
    Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_14;
  }
  if ( v5 <= 0x100 )
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_12;
  }
  if ( v5 <= 0x400 )
  {
    p_WaitListHead = &Lookaside;
    goto LABEL_12;
  }
  if ( v5 <= 0x800 )
  {
    p_WaitListHead = &stru_1400B31C0;
    goto LABEL_12;
  }
  p_WaitListHead = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v5, 878802035);
LABEL_14:
  if ( !Pool2 )
    goto LABEL_108;
  *(_QWORD *)Pool2 = p_WaitListHead;
  i = 0;
  Pool2[2] = 878802035;
  a1[4] = (__int64)(Pool2 + 4);
  *((_DWORD *)a1 + 6) = 0;
  if ( v4 )
  {
    v10 = 0;
    v11 = 0;
    do
    {
      v12 = 0;
      for ( i = v11; (unsigned int)v12 < v11; v12 = (unsigned int)(v12 + 1) )
      {
        if ( *(_DWORD *)(v1 + 8 * v10 + 12) == *(_DWORD *)(a1[4] + 4 * v12) )
          break;
      }
      if ( (_DWORD)v12 == v11 )
      {
        *(_DWORD *)(a1[4] + 4LL * (unsigned int)v12) = *(_DWORD *)(v1 + 8 * v10 + 12);
        i = ++*((_DWORD *)a1 + 6);
      }
      v10 = (unsigned int)(v10 + 1);
      v11 = i;
    }
    while ( (unsigned int)v10 < v4 );
  }
  for ( j = 0; ; j = (unsigned int)(j + 1) )
  {
    v14 = *(_DWORD *)(v3 + 4);
    if ( (unsigned int)j >= i )
      break;
    v15 = 0;
    if ( v14 )
    {
      while ( *(_DWORD *)(a1[4] + 4 * j) != *(_DWORD *)(v3 + 8 * v15 + 12) )
      {
        v15 = (unsigned int)(v15 + 1);
        if ( (unsigned int)v15 >= v14 )
          goto LABEL_28;
      }
    }
    else
    {
LABEL_28:
      if ( (unsigned int)v15 >= v14 )
      {
        v16 = -1073741823;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_lll(
            WPP_GLOBAL_Control->AttachedDevice,
            39,
            WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids,
            *(unsigned int *)(a1[4] + 4LL * (unsigned int)j),
            *((_DWORD *)a1 + 6),
            v14);
        return v16;
      }
    }
  }
  for ( k = 0; (unsigned int)k < v14; k = (unsigned int)(k + 1) )
  {
    v18 = *((_DWORD *)a1 + 6);
    if ( !v18 )
    {
LABEL_38:
      v16 = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_lll(
          WPP_GLOBAL_Control->AttachedDevice,
          40,
          WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids,
          *(unsigned int *)(v3 + 8LL * (unsigned int)k + 12),
          v14,
          v18);
      return v16;
    }
    v19 = 0;
    while ( *(_DWORD *)(v3 + 8 * k + 12) != *(_DWORD *)(a1[4] + 4 * v19) )
    {
      v19 = (unsigned int)(v19 + 1);
      if ( (unsigned int)v19 >= v18 )
        goto LABEL_38;
    }
  }
  v20 = 4 * *(_DWORD *)(*a1 + 4) + 16;
  a1[8] = 0;
  if ( v20 < 0x10 )
    goto LABEL_106;
  if ( v20 <= 0x40 )
  {
    v21 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_50:
    v22 = ExAllocateFromNPagedLookasideList(v21);
    goto LABEL_52;
  }
  if ( v20 <= 0x100 )
  {
    v21 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_50;
  }
  if ( v20 <= 0x400 )
  {
    v21 = &Lookaside;
    goto LABEL_50;
  }
  if ( v20 <= 0x800 )
  {
    v21 = &stru_1400B31C0;
    goto LABEL_50;
  }
  v21 = 0;
  v22 = (_DWORD *)ExAllocatePool2(64, v20, 878802035);
LABEL_52:
  if ( !v22 )
  {
LABEL_106:
    v16 = -1073741670;
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v16;
    v31 = 41;
    goto LABEL_110;
  }
  *(_QWORD *)v22 = v21;
  v22[2] = 878802035;
  a1[8] = (__int64)(v22 + 4);
  v23 = *a1;
  *((_DWORD *)a1 + 14) = 0;
  if ( *(_DWORD *)(v23 + 4) )
  {
    v24 = 0;
    v25 = 0;
    do
    {
      for ( m = 0; (unsigned int)m < v25; m = (unsigned int)(m + 1) )
      {
        if ( *(_DWORD *)(v23 + 8 * v24 + 16) == *(_DWORD *)(a1[8] + 4 * m) )
          break;
      }
      if ( (_DWORD)m == v25 )
      {
        *(_DWORD *)(a1[8] + 4LL * (unsigned int)m) = *(_DWORD *)(*a1 + 8 * v24 + 16);
        v25 = ++*((_DWORD *)a1 + 14);
      }
      v23 = *a1;
      v24 = (unsigned int)(v24 + 1);
    }
    while ( (unsigned int)v24 < *(_DWORD *)(*a1 + 4) );
  }
  v27 = 4 * *(_DWORD *)(a1[1] + 4) + 16;
  a1[6] = 0;
  if ( v27 < 0x10 )
    goto LABEL_73;
  if ( v27 <= 0x40 )
  {
    v28 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_70:
    v29 = ExAllocateFromNPagedLookasideList(v28);
    goto LABEL_72;
  }
  if ( v27 <= 0x100 )
  {
    v28 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_70;
  }
  if ( v27 <= 0x400 )
  {
    v28 = &Lookaside;
    goto LABEL_70;
  }
  if ( v27 <= 0x800 )
  {
    v28 = &stru_1400B31C0;
    goto LABEL_70;
  }
  v28 = 0;
  v29 = (_DWORD *)ExAllocatePool2(64, v27, 878802035);
LABEL_72:
  if ( !v29 )
  {
LABEL_73:
    v16 = -1073741670;
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v16;
    v31 = 42;
    goto LABEL_110;
  }
  *(_QWORD *)v29 = v28;
  v16 = 0;
  v29[2] = 878802035;
  a1[6] = (__int64)(v29 + 4);
  v32 = a1[1];
  *((_DWORD *)a1 + 10) = 0;
  if ( *(_DWORD *)(v32 + 4) )
  {
    v33 = 0;
    v34 = 0;
    do
    {
      for ( n = 0; (unsigned int)n < v34; n = (unsigned int)(n + 1) )
      {
        if ( *(_DWORD *)(v32 + 8 * v33 + 16) == *(_DWORD *)(a1[6] + 4 * n) )
          break;
      }
      if ( (_DWORD)n == v34 )
      {
        *(_DWORD *)(a1[6] + 4LL * (unsigned int)n) = *(_DWORD *)(a1[1] + 8 * v33 + 16);
        v34 = ++*((_DWORD *)a1 + 10);
      }
      v32 = a1[1];
      v33 = (unsigned int)(v33 + 1);
    }
    while ( (unsigned int)v33 < *(_DWORD *)(v32 + 4) );
  }
  v36 = a1[2];
  if ( !v36 )
    return v16;
  v37 = 4 * *(_DWORD *)(v36 + 4) + 16;
  a1[10] = 0;
  if ( v37 < 0x10 )
  {
LABEL_95:
    v16 = -1073741670;
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v16;
    v31 = 43;
    goto LABEL_110;
  }
  if ( v37 > 0x40 )
  {
    if ( v37 > 0x100 )
    {
      if ( v37 > 0x400 )
      {
        if ( v37 > 0x800 )
        {
          p_DeviceQueue = 0;
          v38 = (_DWORD *)ExAllocatePool2(64, v37, 878802035);
          goto LABEL_94;
        }
        p_DeviceQueue = &stru_1400B31C0;
      }
      else
      {
        p_DeviceQueue = &Lookaside;
      }
    }
    else
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    }
  }
  v38 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
LABEL_94:
  if ( !v38 )
    goto LABEL_95;
  *(_QWORD *)v38 = p_DeviceQueue;
  v38[2] = 878802035;
  a1[10] = (__int64)(v38 + 4);
  v39 = a1[2];
  *((_DWORD *)a1 + 18) = 0;
  if ( *(_DWORD *)(v39 + 4) )
  {
    v40 = 0;
    v41 = 0;
    do
    {
      for ( ii = 0; (unsigned int)ii < v41; ii = (unsigned int)(ii + 1) )
      {
        if ( *(_DWORD *)(v39 + 8 * v40 + 16) == *(_DWORD *)(a1[10] + 4 * ii) )
          break;
      }
      if ( (_DWORD)ii == v41 )
      {
        *(_DWORD *)(a1[10] + 4LL * (unsigned int)ii) = *(_DWORD *)(a1[2] + 8 * v40 + 16);
        v41 = ++*((_DWORD *)a1 + 18);
      }
      v39 = a1[2];
      v40 = (unsigned int)(v40 + 1);
    }
    while ( (unsigned int)v40 < *(_DWORD *)(v39 + 4) );
  }
  return v16;
}

```

## disassembly

```asm
0x1400670d0  push    rbx
0x1400670d2  push    rbp
0x1400670d3  push    rsi
0x1400670d4  push    rdi
0x1400670d5  push    r13
0x1400670d7  push    r14
0x1400670d9  push    r15
0x1400670db  sub     rsp, 30h
0x1400670df  mov     rsi, [rcx]
0x1400670e2  mov     rdi, rcx
0x1400670e5  mov     r8, [rcx+8]
0x1400670e9  mov     rbp, r8
0x1400670ec  mov     edx, [rsi+4]
0x1400670ef  cmp     edx, [r8+4]
0x1400670f3  cmovnb  rbp, rsi
0x1400670f7  cmovnb  rsi, r8
0x1400670fb  mov     r14d, [rsi+4]
0x1400670ff  mov     qword ptr [rcx+20h], 0
0x140067107  lea     eax, ds:10h[r14*4]
0x14006710f  cmp     eax, 10h
0x140067112  jb      loc_140067611
0x140067118  lea     r15, WPP_MAIN_CB.DeviceQueue
0x14006711f  mov     r13d, 34617473h
0x140067125  cmp     eax, 40h ; '@'
0x140067128  ja      short loc_14006712F
0x14006712a  mov     rbx, r15
0x14006712d  jmp     short loc_14006715D
0x14006712f  cmp     eax, 100h
0x140067134  ja      short loc_14006713F
0x140067136  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006713d  jmp     short loc_14006715D
0x14006713f  cmp     eax, 400h
0x140067144  ja      short loc_14006714F
0x140067146  lea     rbx, Lookaside
0x14006714d  jmp     short loc_14006715D
0x14006714f  cmp     eax, 800h
0x140067154  ja      short loc_14006716E
0x140067156  lea     rbx, stru_1400B31C0
0x14006715d  mov     rcx, rbx; Lookaside
0x140067160  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140067167  nop     dword ptr [rax+rax+00h]
0x14006716c  jmp     short loc_140067184
0x14006716e  xor     ebx, ebx
0x140067170  mov     edx, eax
0x140067172  mov     r8d, r13d
0x140067175  lea     ecx, [rbx+40h]
0x140067178  call    cs:__imp_ExAllocatePool2
0x14006717f  nop     dword ptr [rax+rax+00h]
0x140067184  test    rax, rax
0x140067187  jz      loc_140067611
0x14006718d  mov     [rax], rbx
0x140067190  xor     ebx, ebx
0x140067192  mov     [rax+8], r13d
0x140067196  add     rax, 10h
0x14006719a  mov     [rdi+20h], rax
0x14006719e  mov     dword ptr [rdi+18h], 0
0x1400671a5  lea     r13d, [rbx+1]
0x1400671a9  test    r14d, r14d
0x1400671ac  jz      short loc_1400671F4
0x1400671ae  xor     r9d, r9d
0x1400671b1  xor     edx, edx
0x1400671b3  xor     ecx, ecx
0x1400671b5  mov     ebx, edx
0x1400671b7  test    edx, edx
0x1400671b9  jz      short loc_1400671D1
0x1400671bb  mov     r10, [rdi+20h]
0x1400671bf  mov     r11d, [rsi+r9*8+0Ch]
0x1400671c4  cmp     r11d, [r10+rcx*4]
0x1400671c8  jz      short loc_1400671D1
0x1400671ca  add     ecx, r13d
0x1400671cd  cmp     ecx, edx
0x1400671cf  jb      short loc_1400671C4
0x1400671d1  cmp     ecx, edx
0x1400671d3  jnz     short loc_1400671EA
0x1400671d5  mov     eax, [rsi+r9*8+0Ch]
0x1400671da  mov     edx, ecx
0x1400671dc  mov     rcx, [rdi+20h]
0x1400671e0  mov     [rcx+rdx*4], eax
0x1400671e3  add     [rdi+18h], r13d
0x1400671e7  mov     ebx, [rdi+18h]
0x1400671ea  add     r9d, r13d
0x1400671ed  mov     edx, ebx
0x1400671ef  cmp     r9d, r14d
0x1400671f2  jb      short loc_1400671B3
0x1400671f4  xor     edx, edx
0x1400671f6  mov     r10d, [rbp+4]
0x1400671fa  cmp     edx, ebx
0x1400671fc  jnb     short loc_140067274
0x1400671fe  xor     r8d, r8d
0x140067201  test    r10d, r10d
0x140067204  jz      short loc_14006721D
0x140067206  mov     rax, [rdi+20h]
0x14006720a  mov     r9d, [rax+rdx*4]
0x14006720e  cmp     r9d, [rbp+r8*8+0Ch]
0x140067213  jz      short loc_140067222
0x140067215  add     r8d, r13d
0x140067218  cmp     r8d, r10d
0x14006721b  jb      short loc_14006720E
0x14006721d  cmp     r8d, r10d
0x140067220  jnb     short loc_140067227
0x140067222  add     edx, r13d
0x140067225  jmp     short loc_1400671F6
0x140067227  mov     ebx, 0C0000001h
0x14006722c  mov     rcx, cs:WPP_GLOBAL_Control
0x140067233  lea     rax, WPP_GLOBAL_Control
0x14006723a  cmp     rcx, rax
0x14006723d  jz      loc_14006763E
0x140067243  mov     r9, [rdi+20h]
0x140067247  mov     eax, [rdi+18h]
0x14006724a  mov     r8d, edx
0x14006724d  mov     edx, 27h ; '''
0x140067252  mov     [rsp+68h+var_40], r10d
0x140067257  mov     [rsp+68h+var_48], eax
0x14006725b  mov     r9d, [r9+r8*4]
0x14006725f  mov     rcx, [rcx+18h]
0x140067263  lea     r8, WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids
0x14006726a  call    WPP_SF_lll
0x14006726f  jmp     loc_14006763E
0x140067274  xor     ecx, ecx
0x140067276  cmp     ecx, r10d
0x140067279  jnb     short loc_1400672D6
0x14006727b  mov     r8d, [rdi+18h]
0x14006727f  mov     r9d, ecx
0x140067282  test    r8d, r8d
0x140067285  jz      short loc_14006729F
0x140067287  mov     r11, [rdi+20h]
0x14006728b  xor     edx, edx
0x14006728d  mov     ebx, [rbp+rcx*8+0Ch]
0x140067291  cmp     ebx, [r11+rdx*4]
0x140067295  jz      short loc_1400672D1
0x140067297  add     edx, r13d
0x14006729a  cmp     edx, r8d
0x14006729d  jb      short loc_140067291
0x14006729f  mov     ebx, 0C0000001h
0x1400672a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400672ab  lea     rax, WPP_GLOBAL_Control
0x1400672b2  cmp     rcx, rax
0x1400672b5  jz      loc_14006763E
0x1400672bb  mov     r9d, [rbp+r9*8+0Ch]
0x1400672c0  mov     edx, 28h ; '('
0x1400672c5  mov     [rsp+68h+var_40], r8d
0x1400672ca  mov     [rsp+68h+var_48], r10d
0x1400672cf  jmp     short loc_14006725F
0x1400672d1  add     ecx, r13d
0x1400672d4  jmp     short loc_140067276
0x1400672d6  mov     rax, [rdi]
0x1400672d9  mov     ecx, [rax+4]
0x1400672dc  shl     ecx, 2
0x1400672df  add     ecx, 10h
0x1400672e2  mov     qword ptr [rdi+40h], 0
0x1400672ea  cmp     ecx, 10h
0x1400672ed  jb      loc_1400675F2
0x1400672f3  mov     esi, 40h ; '@'
0x1400672f8  mov     r14d, 100h
0x1400672fe  cmp     ecx, esi
0x140067300  ja      short loc_140067307
0x140067302  mov     rbx, r15
0x140067305  jmp     short loc_140067335
0x140067307  cmp     ecx, r14d
0x14006730a  ja      short loc_140067315
0x14006730c  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140067313  jmp     short loc_140067335
0x140067315  cmp     ecx, 400h
0x14006731b  ja      short loc_140067326
0x14006731d  lea     rbx, Lookaside
0x140067324  jmp     short loc_140067335
0x140067326  cmp     ecx, 800h
0x14006732c  ja      short loc_14006734B
0x14006732e  lea     rbx, stru_1400B31C0
0x140067335  mov     rcx, rbx; Lookaside
0x140067338  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006733f  nop     dword ptr [rax+rax+00h]
0x140067344  mov     ebp, 34617473h
0x140067349  jmp     short loc_140067366
0x14006734b  mov     edx, ecx
0x14006734d  mov     ebp, 34617473h
0x140067352  mov     r8d, ebp
0x140067355  xor     ebx, ebx
0x140067357  mov     rcx, rsi
0x14006735a  call    cs:__imp_ExAllocatePool2
0x140067361  nop     dword ptr [rax+rax+00h]
0x140067366  test    rax, rax
0x140067369  jz      loc_1400675F2
0x14006736f  mov     [rax], rbx
0x140067372  mov     [rax+8], ebp
0x140067375  add     rax, 10h
0x140067379  mov     [rdi+40h], rax
0x14006737d  mov     rax, [rdi]
0x140067380  mov     dword ptr [rdi+38h], 0
0x140067387  cmp     dword ptr [rax+4], 0
0x14006738b  jbe     short loc_1400673D6
0x14006738d  xor     r9d, r9d
0x140067390  xor     edx, edx
0x140067392  xor     ecx, ecx
0x140067394  test    edx, edx
0x140067396  jz      short loc_1400673AE
0x140067398  mov     r11, [rdi+40h]
0x14006739c  mov     ebx, [rax+r9*8+10h]
0x1400673a1  cmp     ebx, [r11+rcx*4]
0x1400673a5  jz      short loc_1400673AE
0x1400673a7  add     ecx, r13d
0x1400673aa  cmp     ecx, edx
0x1400673ac  jb      short loc_1400673A1
0x1400673ae  cmp     ecx, edx
0x1400673b0  jnz     short loc_1400673CA
0x1400673b2  mov     rax, [rdi]
0x1400673b5  mov     edx, ecx
0x1400673b7  mov     rcx, [rdi+40h]
0x1400673bb  mov     eax, [rax+r9*8+10h]
0x1400673c0  mov     [rcx+rdx*4], eax
0x1400673c3  add     [rdi+38h], r13d
0x1400673c7  mov     edx, [rdi+38h]
0x1400673ca  mov     rax, [rdi]
0x1400673cd  add     r9d, r13d
0x1400673d0  cmp     r9d, [rax+4]
0x1400673d4  jb      short loc_140067392
0x1400673d6  mov     rax, [rdi+8]
0x1400673da  mov     ecx, [rax+4]
0x1400673dd  shl     ecx, 2
0x1400673e0  add     ecx, 10h
0x1400673e3  mov     qword ptr [rdi+30h], 0
0x1400673eb  cmp     ecx, 10h
0x1400673ee  jb      short loc_140067453
0x1400673f0  cmp     ecx, esi
0x1400673f2  ja      short loc_1400673F9
0x1400673f4  mov     rbx, r15
0x1400673f7  jmp     short loc_140067427
0x1400673f9  cmp     ecx, r14d
0x1400673fc  ja      short loc_140067407
0x1400673fe  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140067405  jmp     short loc_140067427
0x140067407  cmp     ecx, 400h
0x14006740d  ja      short loc_140067418
0x14006740f  lea     rbx, Lookaside
0x140067416  jmp     short loc_140067427
0x140067418  cmp     ecx, 800h
0x14006741e  ja      short loc_140067438
0x140067420  lea     rbx, stru_1400B31C0
0x140067427  mov     rcx, rbx; Lookaside
0x14006742a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140067431  nop     dword ptr [rax+rax+00h]
0x140067436  jmp     short loc_14006744E
0x140067438  mov     edx, ecx
0x14006743a  xor     ebx, ebx
0x14006743c  mov     rcx, rsi
0x14006743f  mov     r8d, ebp
0x140067442  call    cs:__imp_ExAllocatePool2
0x140067449  nop     dword ptr [rax+rax+00h]
0x14006744e  test    rax, rax
0x140067451  jnz     short loc_140067479
0x140067453  mov     ebx, 0C000009Ah
0x140067458  mov     rcx, cs:WPP_GLOBAL_Control
0x14006745f  lea     rax, WPP_GLOBAL_Control
0x140067466  cmp     rcx, rax
0x140067469  jz      loc_14006763E
0x14006746f  mov     edx, 2Ah ; '*'
0x140067474  jmp     loc_14006762E
0x140067479  mov     [rax], rbx
0x14006747c  xor     ebx, ebx
0x14006747e  mov     [rax+8], ebp
0x140067481  add     rax, 10h
0x140067485  mov     [rdi+30h], rax
0x140067489  mov     rax, [rdi+8]
0x14006748d  mov     [rdi+28h], ebx
0x140067490  cmp     [rax+4], ebx
0x140067493  jbe     short loc_1400674E5
0x140067495  xor     r9d, r9d
0x140067498  xor     edx, edx
0x14006749a  xor     ecx, ecx
0x14006749c  test    edx, edx
0x14006749e  jz      short loc_1400674B6
0x1400674a0  mov     r11, [rdi+30h]
0x1400674a4  mov     esi, [rax+r9*8+10h]
0x1400674a9  cmp     esi, [r11+rcx*4]
0x1400674ad  jz      short loc_1400674B6
0x1400674af  add     ecx, r13d
0x1400674b2  cmp     ecx, edx
0x1400674b4  jb      short loc_1400674A9
0x1400674b6  cmp     ecx, edx
0x1400674b8  jnz     short loc_1400674D3
0x1400674ba  mov     rax, [rdi+8]
0x1400674be  mov     edx, ecx
0x1400674c0  mov     rcx, [rdi+30h]
0x1400674c4  mov     eax, [rax+r9*8+10h]
0x1400674c9  mov     [rcx+rdx*4], eax
0x1400674cc  add     [rdi+28h], r13d
0x1400674d0  mov     edx, [rdi+28h]
0x1400674d3  mov     rax, [rdi+8]
0x1400674d7  add     r9d, r13d
0x1400674da  cmp     r9d, [rax+4]
0x1400674de  jb      short loc_14006749A
0x1400674e0  mov     esi, 40h ; '@'
0x1400674e5  mov     rax, [rdi+10h]
0x1400674e9  test    rax, rax
0x1400674ec  jz      loc_14006763E
0x1400674f2  mov     eax, [rax+4]
0x1400674f5  shl     eax, 2
0x1400674f8  add     eax, 10h
0x1400674fb  mov     [rdi+50h], rbx
0x1400674ff  cmp     eax, 10h
  ... truncated ...
```
