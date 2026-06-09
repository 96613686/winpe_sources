# UpdateCapabilityDerivedData

- ea: `0x1400658a0`
- end: `0x140065e20`
- name: `UpdateCapabilityDerivedData`
- size: `1408`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140065310`

## callees

- `0x14000d22c`
- `0x14002ffb4`
- `0x1400658a0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065930`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065b08`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065bfa`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065d07`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065930`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065b08`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065bfa`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140065d07`
- `ntoskrnl!ExAllocatePool2` at `0x140065948`
- `ntoskrnl!ExAllocatePool2` at `0x140065b2a`
- `ntoskrnl!ExAllocatePool2` at `0x140065c12`
- `ntoskrnl!ExAllocatePool2` at `0x140065d20`
- `ntoskrnl!ExAllocatePool2` at `0x140065948`
- `ntoskrnl!ExAllocatePool2` at `0x140065b2a`
- `ntoskrnl!ExAllocatePool2` at `0x140065c12`
- `ntoskrnl!ExAllocatePool2` at `0x140065d20`

## pseudocode

```c
__int64 __fastcall UpdateCapabilityDerivedData(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rsi
  __int64 v6; // rbp
  unsigned int v7; // r14d
  unsigned int v8; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // r15
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  __int64 v12; // r9
  unsigned int i; // ebx
  unsigned int v14; // edx
  __int64 v15; // rcx
  __int64 j; // rdx
  unsigned int v17; // r10d
  __int64 v18; // r8
  unsigned int v19; // ebx
  __int64 k; // rcx
  unsigned int v21; // r8d
  __int64 v22; // rdx
  unsigned int v23; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v24; // rbx
  _DWORD *v25; // rax
  __int64 v26; // r9
  __int64 v27; // rax
  unsigned int v28; // edx
  __int64 m; // rcx
  unsigned int v30; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v31; // rbx
  _DWORD *v32; // rax
  __int64 v33; // r9
  PDEVICE_OBJECT v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rax
  unsigned int v37; // edx
  __int64 n; // rcx
  __int64 v39; // rax
  unsigned int v40; // eax
  _DWORD *v41; // rax
  __int64 v42; // rax
  __int64 v43; // r9
  unsigned int v44; // edx
  __int64 ii; // rcx

  v4 = *a1;
  v6 = a1[1];
  if ( *(_DWORD *)(*a1 + 4) >= *(_DWORD *)(v6 + 4) )
  {
    v6 = *a1;
    v4 = a1[1];
  }
  v7 = *(_DWORD *)(v4 + 4);
  a1[4] = 0;
  v8 = 4 * v7 + 16;
  if ( 4 * v7 >= 0xFFFFFFF0 )
  {
LABEL_109:
    v19 = -1073741670;
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v35 = 38;
LABEL_111:
      WPP_SF_(v34->AttachedDevice, v35, WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids);
      return v19;
    }
    return v19;
  }
  p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  if ( v8 <= 0x40 )
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_12:
    Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_14;
  }
  if ( v8 <= 0x100 )
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_12;
  }
  if ( v8 <= 0x400 )
  {
    p_WaitListHead = &Lookaside;
    goto LABEL_12;
  }
  if ( v8 <= 0x800 )
  {
    p_WaitListHead = &stru_1400B0180;
    goto LABEL_12;
  }
  p_WaitListHead = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v8, 878802035, a4);
LABEL_14:
  if ( !Pool2 )
    goto LABEL_109;
  *(_QWORD *)Pool2 = p_WaitListHead;
  i = 0;
  Pool2[2] = 878802035;
  a1[4] = (__int64)(Pool2 + 4);
  *((_DWORD *)a1 + 6) = 0;
  if ( v7 )
  {
    v12 = 0;
    v14 = 0;
    do
    {
      v15 = 0;
      for ( i = v14; (unsigned int)v15 < v14; v15 = (unsigned int)(v15 + 1) )
      {
        if ( *(_DWORD *)(v4 + 8 * v12 + 12) == *(_DWORD *)(a1[4] + 4 * v15) )
          break;
      }
      if ( (_DWORD)v15 == v14 )
      {
        *(_DWORD *)(a1[4] + 4LL * (unsigned int)v15) = *(_DWORD *)(v4 + 8 * v12 + 12);
        i = ++*((_DWORD *)a1 + 6);
      }
      v12 = (unsigned int)(v12 + 1);
      v14 = i;
    }
    while ( (unsigned int)v12 < v7 );
  }
  for ( j = 0; ; j = (unsigned int)(j + 1) )
  {
    v17 = *(_DWORD *)(v6 + 4);
    if ( (unsigned int)j >= i )
      break;
    v18 = 0;
    if ( v17 )
    {
      v12 = *(unsigned int *)(a1[4] + 4 * j);
      while ( (_DWORD)v12 != *(_DWORD *)(v6 + 8 * v18 + 12) )
      {
        v18 = (unsigned int)(v18 + 1);
        if ( (unsigned int)v18 >= v17 )
          goto LABEL_29;
      }
    }
    else
    {
LABEL_29:
      if ( (unsigned int)v18 >= v17 )
      {
        v19 = -1073741823;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_lll(
            WPP_GLOBAL_Control->AttachedDevice,
            39,
            WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids,
            *(unsigned int *)(a1[4] + 4LL * (unsigned int)j),
            *((_DWORD *)a1 + 6),
            v17);
        return v19;
      }
    }
  }
  for ( k = 0; (unsigned int)k < v17; k = (unsigned int)(k + 1) )
  {
    v21 = *((_DWORD *)a1 + 6);
    v12 = (unsigned int)k;
    if ( !v21 )
    {
LABEL_39:
      v19 = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_lll(
          WPP_GLOBAL_Control->AttachedDevice,
          40,
          WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids,
          *(unsigned int *)(v6 + 8LL * (unsigned int)k + 12),
          v17,
          v21);
      return v19;
    }
    v22 = 0;
    while ( *(_DWORD *)(v6 + 8 * k + 12) != *(_DWORD *)(a1[4] + 4 * v22) )
    {
      v22 = (unsigned int)(v22 + 1);
      if ( (unsigned int)v22 >= v21 )
        goto LABEL_39;
    }
  }
  v23 = 4 * *(_DWORD *)(*a1 + 4) + 16;
  a1[8] = 0;
  if ( v23 < 0x10 )
    goto LABEL_107;
  if ( v23 <= 0x40 )
  {
    v24 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_51:
    v25 = ExAllocateFromNPagedLookasideList(v24);
    goto LABEL_53;
  }
  if ( v23 <= 0x100 )
  {
    v24 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_51;
  }
  if ( v23 <= 0x400 )
  {
    v24 = &Lookaside;
    goto LABEL_51;
  }
  if ( v23 <= 0x800 )
  {
    v24 = &stru_1400B0180;
    goto LABEL_51;
  }
  v24 = 0;
  v25 = (_DWORD *)ExAllocatePool2(64, v23, 878802035, v12);
LABEL_53:
  if ( !v25 )
  {
LABEL_107:
    v19 = -1073741670;
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v19;
    v35 = 41;
    goto LABEL_111;
  }
  *(_QWORD *)v25 = v24;
  v25[2] = 878802035;
  a1[8] = (__int64)(v25 + 4);
  v27 = *a1;
  *((_DWORD *)a1 + 14) = 0;
  if ( *(_DWORD *)(v27 + 4) )
  {
    v26 = 0;
    v28 = 0;
    do
    {
      for ( m = 0; (unsigned int)m < v28; m = (unsigned int)(m + 1) )
      {
        if ( *(_DWORD *)(v27 + 8 * v26 + 16) == *(_DWORD *)(a1[8] + 4 * m) )
          break;
      }
      if ( (_DWORD)m == v28 )
      {
        *(_DWORD *)(a1[8] + 4LL * (unsigned int)m) = *(_DWORD *)(*a1 + 8 * v26 + 16);
        v28 = ++*((_DWORD *)a1 + 14);
      }
      v27 = *a1;
      v26 = (unsigned int)(v26 + 1);
    }
    while ( (unsigned int)v26 < *(_DWORD *)(*a1 + 4) );
  }
  v30 = 4 * *(_DWORD *)(a1[1] + 4) + 16;
  a1[6] = 0;
  if ( v30 < 0x10 )
    goto LABEL_74;
  if ( v30 <= 0x40 )
  {
    v31 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_71:
    v32 = ExAllocateFromNPagedLookasideList(v31);
    goto LABEL_73;
  }
  if ( v30 <= 0x100 )
  {
    v31 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_71;
  }
  if ( v30 <= 0x400 )
  {
    v31 = &Lookaside;
    goto LABEL_71;
  }
  if ( v30 <= 0x800 )
  {
    v31 = &stru_1400B0180;
    goto LABEL_71;
  }
  v31 = 0;
  v32 = (_DWORD *)ExAllocatePool2(64, v30, 878802035, v26);
LABEL_73:
  if ( !v32 )
  {
LABEL_74:
    v19 = -1073741670;
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v19;
    v35 = 42;
    goto LABEL_111;
  }
  *(_QWORD *)v32 = v31;
  v19 = 0;
  v32[2] = 878802035;
  a1[6] = (__int64)(v32 + 4);
  v36 = a1[1];
  *((_DWORD *)a1 + 10) = 0;
  if ( *(_DWORD *)(v36 + 4) )
  {
    v33 = 0;
    v37 = 0;
    do
    {
      for ( n = 0; (unsigned int)n < v37; n = (unsigned int)(n + 1) )
      {
        if ( *(_DWORD *)(v36 + 8 * v33 + 16) == *(_DWORD *)(a1[6] + 4 * n) )
          break;
      }
      if ( (_DWORD)n == v37 )
      {
        *(_DWORD *)(a1[6] + 4LL * (unsigned int)n) = *(_DWORD *)(a1[1] + 8 * v33 + 16);
        v37 = ++*((_DWORD *)a1 + 10);
      }
      v36 = a1[1];
      v33 = (unsigned int)(v33 + 1);
    }
    while ( (unsigned int)v33 < *(_DWORD *)(v36 + 4) );
  }
  v39 = a1[2];
  if ( !v39 )
    return v19;
  v40 = 4 * *(_DWORD *)(v39 + 4) + 16;
  a1[10] = 0;
  if ( v40 < 0x10 )
  {
LABEL_96:
    v19 = -1073741670;
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v19;
    v35 = 43;
    goto LABEL_111;
  }
  if ( v40 > 0x40 )
  {
    if ( v40 > 0x100 )
    {
      if ( v40 > 0x400 )
      {
        if ( v40 > 0x800 )
        {
          p_DeviceQueue = 0;
          v41 = (_DWORD *)ExAllocatePool2(64, v40, 878802035, v33);
          goto LABEL_95;
        }
        p_DeviceQueue = &stru_1400B0180;
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
  v41 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
LABEL_95:
  if ( !v41 )
    goto LABEL_96;
  *(_QWORD *)v41 = p_DeviceQueue;
  v41[2] = 878802035;
  a1[10] = (__int64)(v41 + 4);
  v42 = a1[2];
  *((_DWORD *)a1 + 18) = 0;
  if ( *(_DWORD *)(v42 + 4) )
  {
    v43 = 0;
    v44 = 0;
    do
    {
      for ( ii = 0; (unsigned int)ii < v44; ii = (unsigned int)(ii + 1) )
      {
        if ( *(_DWORD *)(v42 + 8 * v43 + 16) == *(_DWORD *)(a1[10] + 4 * ii) )
          break;
      }
      if ( (_DWORD)ii == v44 )
      {
        *(_DWORD *)(a1[10] + 4LL * (unsigned int)ii) = *(_DWORD *)(a1[2] + 8 * v43 + 16);
        v44 = ++*((_DWORD *)a1 + 18);
      }
      v42 = a1[2];
      v43 = (unsigned int)(v43 + 1);
    }
    while ( (unsigned int)v43 < *(_DWORD *)(v42 + 4) );
  }
  return v19;
}

```

## disassembly

```asm
0x1400658a0  push    rbx
0x1400658a2  push    rbp
0x1400658a3  push    rsi
0x1400658a4  push    rdi
0x1400658a5  push    r13
0x1400658a7  push    r14
0x1400658a9  push    r15
0x1400658ab  sub     rsp, 30h
0x1400658af  mov     rsi, [rcx]
0x1400658b2  mov     rdi, rcx
0x1400658b5  mov     r8, [rcx+8]
0x1400658b9  mov     rbp, r8
0x1400658bc  mov     edx, [rsi+4]
0x1400658bf  cmp     edx, [r8+4]
0x1400658c3  cmovnb  rbp, rsi
0x1400658c7  cmovnb  rsi, r8
0x1400658cb  mov     r14d, [rsi+4]
0x1400658cf  mov     qword ptr [rcx+20h], 0
0x1400658d7  lea     eax, ds:10h[r14*4]
0x1400658df  cmp     eax, 10h
0x1400658e2  jb      loc_140065DE1
0x1400658e8  lea     r15, WPP_MAIN_CB.DeviceQueue
0x1400658ef  mov     r13d, 34617473h
0x1400658f5  cmp     eax, 40h ; '@'
0x1400658f8  ja      short loc_1400658FF
0x1400658fa  mov     rbx, r15
0x1400658fd  jmp     short loc_14006592D
0x1400658ff  cmp     eax, 100h
0x140065904  ja      short loc_14006590F
0x140065906  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006590d  jmp     short loc_14006592D
0x14006590f  cmp     eax, 400h
0x140065914  ja      short loc_14006591F
0x140065916  lea     rbx, Lookaside
0x14006591d  jmp     short loc_14006592D
0x14006591f  cmp     eax, 800h
0x140065924  ja      short loc_14006593E
0x140065926  lea     rbx, stru_1400B0180
0x14006592d  mov     rcx, rbx; Lookaside
0x140065930  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140065937  nop     dword ptr [rax+rax+00h]
0x14006593c  jmp     short loc_140065954
0x14006593e  xor     ebx, ebx
0x140065940  mov     edx, eax
0x140065942  mov     r8d, r13d
0x140065945  lea     ecx, [rbx+40h]
0x140065948  call    cs:__imp_ExAllocatePool2
0x14006594f  nop     dword ptr [rax+rax+00h]
0x140065954  test    rax, rax
0x140065957  jz      loc_140065DE1
0x14006595d  mov     [rax], rbx
0x140065960  xor     ebx, ebx
0x140065962  mov     [rax+8], r13d
0x140065966  add     rax, 10h
0x14006596a  mov     [rdi+20h], rax
0x14006596e  mov     dword ptr [rdi+18h], 0
0x140065975  lea     r13d, [rbx+1]
0x140065979  test    r14d, r14d
0x14006597c  jz      short loc_1400659C4
0x14006597e  xor     r9d, r9d
0x140065981  xor     edx, edx
0x140065983  xor     ecx, ecx
0x140065985  mov     ebx, edx
0x140065987  test    edx, edx
0x140065989  jz      short loc_1400659A1
0x14006598b  mov     r10, [rdi+20h]
0x14006598f  mov     r11d, [rsi+r9*8+0Ch]
0x140065994  cmp     r11d, [r10+rcx*4]
0x140065998  jz      short loc_1400659A1
0x14006599a  add     ecx, r13d
0x14006599d  cmp     ecx, edx
0x14006599f  jb      short loc_140065994
0x1400659a1  cmp     ecx, edx
0x1400659a3  jnz     short loc_1400659BA
0x1400659a5  mov     eax, [rsi+r9*8+0Ch]
0x1400659aa  mov     edx, ecx
0x1400659ac  mov     rcx, [rdi+20h]
0x1400659b0  mov     [rcx+rdx*4], eax
0x1400659b3  add     [rdi+18h], r13d
0x1400659b7  mov     ebx, [rdi+18h]
0x1400659ba  add     r9d, r13d
0x1400659bd  mov     edx, ebx
0x1400659bf  cmp     r9d, r14d
0x1400659c2  jb      short loc_140065983
0x1400659c4  xor     edx, edx
0x1400659c6  mov     r10d, [rbp+4]
0x1400659ca  cmp     edx, ebx
0x1400659cc  jnb     short loc_140065A44
0x1400659ce  xor     r8d, r8d
0x1400659d1  test    r10d, r10d
0x1400659d4  jz      short loc_1400659ED
0x1400659d6  mov     rax, [rdi+20h]
0x1400659da  mov     r9d, [rax+rdx*4]
0x1400659de  cmp     r9d, [rbp+r8*8+0Ch]
0x1400659e3  jz      short loc_1400659F2
0x1400659e5  add     r8d, r13d
0x1400659e8  cmp     r8d, r10d
0x1400659eb  jb      short loc_1400659DE
0x1400659ed  cmp     r8d, r10d
0x1400659f0  jnb     short loc_1400659F7
0x1400659f2  add     edx, r13d
0x1400659f5  jmp     short loc_1400659C6
0x1400659f7  mov     ebx, 0C0000001h
0x1400659fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140065a03  lea     rax, WPP_GLOBAL_Control
0x140065a0a  cmp     rcx, rax
0x140065a0d  jz      loc_140065E0E
0x140065a13  mov     r9, [rdi+20h]
0x140065a17  mov     eax, [rdi+18h]
0x140065a1a  mov     r8d, edx
0x140065a1d  mov     edx, 27h ; '''
0x140065a22  mov     [rsp+68h+var_40], r10d
0x140065a27  mov     [rsp+68h+var_48], eax
0x140065a2b  mov     r9d, [r9+r8*4]
0x140065a2f  mov     rcx, [rcx+18h]
0x140065a33  lea     r8, WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids
0x140065a3a  call    WPP_SF_lll
0x140065a3f  jmp     loc_140065E0E
0x140065a44  xor     ecx, ecx
0x140065a46  cmp     ecx, r10d
0x140065a49  jnb     short loc_140065AA6
0x140065a4b  mov     r8d, [rdi+18h]
0x140065a4f  mov     r9d, ecx
0x140065a52  test    r8d, r8d
0x140065a55  jz      short loc_140065A6F
0x140065a57  mov     r11, [rdi+20h]
0x140065a5b  xor     edx, edx
0x140065a5d  mov     ebx, [rbp+rcx*8+0Ch]
0x140065a61  cmp     ebx, [r11+rdx*4]
0x140065a65  jz      short loc_140065AA1
0x140065a67  add     edx, r13d
0x140065a6a  cmp     edx, r8d
0x140065a6d  jb      short loc_140065A61
0x140065a6f  mov     ebx, 0C0000001h
0x140065a74  mov     rcx, cs:WPP_GLOBAL_Control
0x140065a7b  lea     rax, WPP_GLOBAL_Control
0x140065a82  cmp     rcx, rax
0x140065a85  jz      loc_140065E0E
0x140065a8b  mov     r9d, [rbp+r9*8+0Ch]
0x140065a90  mov     edx, 28h ; '('
0x140065a95  mov     [rsp+68h+var_40], r8d
0x140065a9a  mov     [rsp+68h+var_48], r10d
0x140065a9f  jmp     short loc_140065A2F
0x140065aa1  add     ecx, r13d
0x140065aa4  jmp     short loc_140065A46
0x140065aa6  mov     rax, [rdi]
0x140065aa9  mov     ecx, [rax+4]
0x140065aac  shl     ecx, 2
0x140065aaf  add     ecx, 10h
0x140065ab2  mov     qword ptr [rdi+40h], 0
0x140065aba  cmp     ecx, 10h
0x140065abd  jb      loc_140065DC2
0x140065ac3  mov     esi, 40h ; '@'
0x140065ac8  mov     r14d, 100h
0x140065ace  cmp     ecx, esi
0x140065ad0  ja      short loc_140065AD7
0x140065ad2  mov     rbx, r15
0x140065ad5  jmp     short loc_140065B05
0x140065ad7  cmp     ecx, r14d
0x140065ada  ja      short loc_140065AE5
0x140065adc  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140065ae3  jmp     short loc_140065B05
0x140065ae5  cmp     ecx, 400h
0x140065aeb  ja      short loc_140065AF6
0x140065aed  lea     rbx, Lookaside
0x140065af4  jmp     short loc_140065B05
0x140065af6  cmp     ecx, 800h
0x140065afc  ja      short loc_140065B1B
0x140065afe  lea     rbx, stru_1400B0180
0x140065b05  mov     rcx, rbx; Lookaside
0x140065b08  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140065b0f  nop     dword ptr [rax+rax+00h]
0x140065b14  mov     ebp, 34617473h
0x140065b19  jmp     short loc_140065B36
0x140065b1b  mov     edx, ecx
0x140065b1d  mov     ebp, 34617473h
0x140065b22  mov     r8d, ebp
0x140065b25  xor     ebx, ebx
0x140065b27  mov     rcx, rsi
0x140065b2a  call    cs:__imp_ExAllocatePool2
0x140065b31  nop     dword ptr [rax+rax+00h]
0x140065b36  test    rax, rax
0x140065b39  jz      loc_140065DC2
0x140065b3f  mov     [rax], rbx
0x140065b42  mov     [rax+8], ebp
0x140065b45  add     rax, 10h
0x140065b49  mov     [rdi+40h], rax
0x140065b4d  mov     rax, [rdi]
0x140065b50  mov     dword ptr [rdi+38h], 0
0x140065b57  cmp     dword ptr [rax+4], 0
0x140065b5b  jbe     short loc_140065BA6
0x140065b5d  xor     r9d, r9d
0x140065b60  xor     edx, edx
0x140065b62  xor     ecx, ecx
0x140065b64  test    edx, edx
0x140065b66  jz      short loc_140065B7E
0x140065b68  mov     r11, [rdi+40h]
0x140065b6c  mov     ebx, [rax+r9*8+10h]
0x140065b71  cmp     ebx, [r11+rcx*4]
0x140065b75  jz      short loc_140065B7E
0x140065b77  add     ecx, r13d
0x140065b7a  cmp     ecx, edx
0x140065b7c  jb      short loc_140065B71
0x140065b7e  cmp     ecx, edx
0x140065b80  jnz     short loc_140065B9A
0x140065b82  mov     rax, [rdi]
0x140065b85  mov     edx, ecx
0x140065b87  mov     rcx, [rdi+40h]
0x140065b8b  mov     eax, [rax+r9*8+10h]
0x140065b90  mov     [rcx+rdx*4], eax
0x140065b93  add     [rdi+38h], r13d
0x140065b97  mov     edx, [rdi+38h]
0x140065b9a  mov     rax, [rdi]
0x140065b9d  add     r9d, r13d
0x140065ba0  cmp     r9d, [rax+4]
0x140065ba4  jb      short loc_140065B62
0x140065ba6  mov     rax, [rdi+8]
0x140065baa  mov     ecx, [rax+4]
0x140065bad  shl     ecx, 2
0x140065bb0  add     ecx, 10h
0x140065bb3  mov     qword ptr [rdi+30h], 0
0x140065bbb  cmp     ecx, 10h
0x140065bbe  jb      short loc_140065C23
0x140065bc0  cmp     ecx, esi
0x140065bc2  ja      short loc_140065BC9
0x140065bc4  mov     rbx, r15
0x140065bc7  jmp     short loc_140065BF7
0x140065bc9  cmp     ecx, r14d
0x140065bcc  ja      short loc_140065BD7
0x140065bce  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140065bd5  jmp     short loc_140065BF7
0x140065bd7  cmp     ecx, 400h
0x140065bdd  ja      short loc_140065BE8
0x140065bdf  lea     rbx, Lookaside
0x140065be6  jmp     short loc_140065BF7
0x140065be8  cmp     ecx, 800h
0x140065bee  ja      short loc_140065C08
0x140065bf0  lea     rbx, stru_1400B0180
0x140065bf7  mov     rcx, rbx; Lookaside
0x140065bfa  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140065c01  nop     dword ptr [rax+rax+00h]
0x140065c06  jmp     short loc_140065C1E
0x140065c08  mov     edx, ecx
0x140065c0a  xor     ebx, ebx
0x140065c0c  mov     rcx, rsi
0x140065c0f  mov     r8d, ebp
0x140065c12  call    cs:__imp_ExAllocatePool2
0x140065c19  nop     dword ptr [rax+rax+00h]
0x140065c1e  test    rax, rax
0x140065c21  jnz     short loc_140065C49
0x140065c23  mov     ebx, 0C000009Ah
0x140065c28  mov     rcx, cs:WPP_GLOBAL_Control
0x140065c2f  lea     rax, WPP_GLOBAL_Control
0x140065c36  cmp     rcx, rax
0x140065c39  jz      loc_140065E0E
0x140065c3f  mov     edx, 2Ah ; '*'
0x140065c44  jmp     loc_140065DFE
0x140065c49  mov     [rax], rbx
0x140065c4c  xor     ebx, ebx
0x140065c4e  mov     [rax+8], ebp
0x140065c51  add     rax, 10h
0x140065c55  mov     [rdi+30h], rax
0x140065c59  mov     rax, [rdi+8]
0x140065c5d  mov     [rdi+28h], ebx
0x140065c60  cmp     [rax+4], ebx
0x140065c63  jbe     short loc_140065CB5
0x140065c65  xor     r9d, r9d
0x140065c68  xor     edx, edx
0x140065c6a  xor     ecx, ecx
0x140065c6c  test    edx, edx
0x140065c6e  jz      short loc_140065C86
0x140065c70  mov     r11, [rdi+30h]
0x140065c74  mov     esi, [rax+r9*8+10h]
0x140065c79  cmp     esi, [r11+rcx*4]
0x140065c7d  jz      short loc_140065C86
0x140065c7f  add     ecx, r13d
0x140065c82  cmp     ecx, edx
0x140065c84  jb      short loc_140065C79
0x140065c86  cmp     ecx, edx
0x140065c88  jnz     short loc_140065CA3
0x140065c8a  mov     rax, [rdi+8]
0x140065c8e  mov     edx, ecx
0x140065c90  mov     rcx, [rdi+30h]
0x140065c94  mov     eax, [rax+r9*8+10h]
0x140065c99  mov     [rcx+rdx*4], eax
0x140065c9c  add     [rdi+28h], r13d
0x140065ca0  mov     edx, [rdi+28h]
0x140065ca3  mov     rax, [rdi+8]
0x140065ca7  add     r9d, r13d
0x140065caa  cmp     r9d, [rax+4]
0x140065cae  jb      short loc_140065C6A
0x140065cb0  mov     esi, 40h ; '@'
0x140065cb5  mov     rax, [rdi+10h]
0x140065cb9  test    rax, rax
0x140065cbc  jz      loc_140065E0E
0x140065cc2  mov     eax, [rax+4]
0x140065cc5  shl     eax, 2
0x140065cc8  add     eax, 10h
0x140065ccb  mov     [rdi+50h], rbx
0x140065ccf  cmp     eax, 10h
  ... truncated ...
```
