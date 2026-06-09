# ExtSTASetUnicastCipherAlgo(EXTSTA_VELAN *,_DOT11_CIPHER_ALGO_LIST const *,ulong)

- ea: `0x1400197b0`
- end: `0x140019ac3`
- name: `?ExtSTASetUnicastCipherAlgo@@YAJPEAUEXTSTA_VELAN@@PEBU_DOT11_CIPHER_ALGO_LIST@@K@Z`
- size: `787`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, const struct _DOT11_CIPHER_ALGO_LIST *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x1400197b0`
- `0x140019bbc`
- `0x140020dc0`
- `0x140020f20`
- `0x1400391a4`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001992f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001992f`
- `ntoskrnl!ExAllocatePool2` at `0x140019944`
- `ntoskrnl!ExAllocatePool2` at `0x140019944`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019a88`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019a88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019a99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019a99`

## pseudocode

```c
__int64 __fastcall ExtSTASetUnicastCipherAlgo(
        struct EXTSTA_VELAN *a1,
        const struct _DOT11_CIPHER_ALGO_LIST *a2,
        int a3)
{
  unsigned int v3; // r9d
  __int64 i; // rax
  unsigned int v7; // ecx
  __int64 v8; // rdi
  unsigned int v9; // r8d
  __int64 v10; // rbx
  unsigned int v11; // r11d
  __int64 v12; // rdx
  int v13; // r10d
  __int64 j; // rdx
  int v15; // ebx
  _VELAN *pGenVElan; // rcx
  bool v17; // zf
  unsigned int v18; // ebp
  unsigned int v19; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  __int64 v22; // r8
  __int64 v23; // rdx
  unsigned int *k; // rdi
  __int64 v25; // r9
  __int64 v26; // rax
  unsigned int v27; // ebp

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
  v8 = 1960;
  v9 = 0;
  v10 = 1968;
  if ( a1->Rw.DesiredBSSType != dot11_BSS_type_infrastructure )
  {
    v8 = 2072;
    v10 = 2080;
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
  pGenVElan = a1->pGenVElan;
  v17 = pGenVElan->KeyContext.AuthAlgo == DOT11_AUTH_ALGO_OWE;
  pGenVElan->KeyContext.UcastCipher = *((_DWORD *)a2 + 3);
  if ( v17 )
    Dot11InitializeOWEAuthParams(pGenVElan, *((enum _DOT11_CIPHER_ALGORITHM *)a2 + 3));
  v18 = 4 * *(unsigned int *)((char *)&a1->ModuleStatus.uValue + v8) + 12;
  v19 = 4 * *(unsigned int *)((char *)&a1->ModuleStatus.uValue + v8) + 28;
  if ( v19 < 0x10 )
    return (unsigned int)-1073741670;
  if ( v19 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_35:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_37;
  }
  if ( v19 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_35;
  }
  if ( v19 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_35;
  }
  if ( v19 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_35;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v19, 808464432);
LABEL_37:
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  Pool2[2] = 808464432;
  v22 = 0;
  v23 = 0;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  for ( k = Pool2 + 4; (unsigned int)v23 < *(_DWORD *)a2; v23 = (unsigned int)(v23 + 1) )
  {
    if ( *((_DWORD *)a2 + 3 * v23 + 4) )
    {
      k[v22 + 3] = *((_DWORD *)a2 + 3 * v23 + 3);
      v22 = (unsigned int)(v22 + 1);
    }
  }
  *k = 1048960;
  Pool2[6] = v22;
  Pool2[5] = v22;
  v15 = PtRequestAdapterSync(a1->pGenVElan->pAdapt, 1u, 0xE010187u, k, v18);
  if ( v15 >= 0 )
  {
    memmove(a1->Rw.pEnabledUcastCiphers, k, v18);
    v25 = k[2];
    if ( (_DWORD)v25 == 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, k[3]);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, v25);
      v26 = 0;
      if ( k[2] )
      {
        do
        {
          v27 = v26 + 1;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              34,
              WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids,
              v27,
              k[v26 + 3]);
          v26 = v27;
        }
        while ( v27 < k[2] );
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
0x1400197b0  push    rbx
0x1400197b2  push    rbp
0x1400197b3  push    rsi
0x1400197b4  push    rdi
0x1400197b5  push    r13
0x1400197b7  push    r14
0x1400197b9  sub     rsp, 38h
0x1400197bd  mov     r9d, [rdx]
0x1400197c0  add     r8d, 0FFFFFFF8h
0x1400197c4  mov     rsi, rdx
0x1400197c7  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400197d1  mul     r8
0x1400197d4  mov     r14, rcx
0x1400197d7  shr     rdx, 3
0x1400197db  cmp     edx, r9d
0x1400197de  jb      loc_140019AAE
0x1400197e4  cmp     r9d, [rsi+4]
0x1400197e8  jnz     loc_1400198A0
0x1400197ee  test    r9d, r9d
0x1400197f1  jz      short loc_14001982D
0x1400197f3  xor     eax, eax
0x1400197f5  lea     r8d, [r9-1]
0x1400197f9  cmp     eax, r8d
0x1400197fc  jnb     short loc_14001982D
0x1400197fe  lea     edx, [rax+1]
0x140019801  mov     ecx, edx
0x140019803  cmp     edx, r9d
0x140019806  jnb     short loc_140019829
0x140019808  inc     rax
0x14001980b  lea     rax, [rax+rax*2]
0x14001980f  mov     r10d, [rsi+rax*4]
0x140019813  mov     eax, ecx
0x140019815  inc     rax
0x140019818  lea     rax, [rax+rax*2]
0x14001981c  cmp     r10d, [rsi+rax*4]
0x140019820  jz      short loc_1400198A0
0x140019822  inc     ecx
0x140019824  cmp     ecx, r9d
0x140019827  jb      short loc_140019813
0x140019829  mov     eax, edx
0x14001982b  jmp     short loc_1400197F9
0x14001982d  mov     edi, 7A8h
0x140019832  xor     r8d, r8d
0x140019835  cmp     dword ptr [r14+6BCh], 1
0x14001983d  lea     ecx, [rdi+70h]
0x140019840  lea     ebx, [rcx-68h]
0x140019843  cmovnz  edi, ecx
0x140019846  lea     ecx, [rbx+70h]
0x140019849  cmovnz  ebx, ecx
0x14001984c  cmp     r8d, r9d
0x14001984f  jnb     short loc_1400198AA
0x140019851  mov     r11d, [rdi+r14]
0x140019855  mov     eax, r8d
0x140019858  inc     rax
0x14001985b  xor     edx, edx
0x14001985d  lea     rax, [rax+rax*2]
0x140019861  mov     r10d, [rsi+rax*4]
0x140019865  cmp     edx, r11d
0x140019868  jnb     short loc_140019878
0x14001986a  mov     rax, [rbx+r14]
0x14001986e  cmp     [rax+rdx*4], r10d
0x140019872  jz      short loc_14001989B
0x140019874  inc     edx
0x140019876  jmp     short loc_140019865
0x140019878  lea     eax, [r10-1]
0x14001987c  test    eax, 0FFFFFFFBh
0x140019881  jnz     short loc_1400198A0
0x140019883  xor     edx, edx
0x140019885  cmp     edx, r11d
0x140019888  jnb     short loc_1400198A0
0x14001988a  mov     rax, [rbx+r14]
0x14001988e  cmp     dword ptr [rax+rdx*4], 101h
0x140019895  jz      short loc_14001989B
0x140019897  inc     edx
0x140019899  jmp     short loc_140019885
0x14001989b  inc     r8d
0x14001989e  jmp     short loc_14001984C
0x1400198a0  mov     ebx, 0C000000Dh
0x1400198a5  jmp     loc_140019AB3
0x1400198aa  mov     rcx, [r14+0A38h]; struct _VELAN *
0x1400198b1  mov     eax, [rsi+0Ch]
0x1400198b4  cmp     dword ptr [rcx+171Ch], 0Ah
0x1400198bb  mov     [rcx+1720h], eax
0x1400198c1  jnz     short loc_1400198CB
0x1400198c3  mov     edx, [rsi+0Ch]; enum _DOT11_CIPHER_ALGORITHM
0x1400198c6  call    ?Dot11InitializeOWEAuthParams@@YAJPEAU_VELAN@@W4_DOT11_CIPHER_ALGORITHM@@@Z; Dot11InitializeOWEAuthParams(_VELAN *,_DOT11_CIPHER_ALGORITHM)
0x1400198cb  mov     eax, [rdi+r14]
0x1400198cf  mov     r13d, 10h
0x1400198d5  lea     ebp, ds:0Ch[rax*4]
0x1400198dc  lea     eax, [rbp+10h]
0x1400198df  cmp     eax, r13d
0x1400198e2  jb      loc_140019AA7
0x1400198e8  lea     ecx, [r13+30h]
0x1400198ec  mov     edi, 30303030h
0x1400198f1  cmp     eax, ecx
0x1400198f3  ja      short loc_1400198FE
0x1400198f5  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400198fc  jmp     short loc_14001992C
0x1400198fe  cmp     eax, 100h
0x140019903  ja      short loc_14001990E
0x140019905  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14001990c  jmp     short loc_14001992C
0x14001990e  cmp     eax, 400h
0x140019913  ja      short loc_14001991E
0x140019915  lea     rbx, Lookaside
0x14001991c  jmp     short loc_14001992C
0x14001991e  cmp     eax, 800h
0x140019923  ja      short loc_14001993D
0x140019925  lea     rbx, stru_1400B31C0
0x14001992c  mov     rcx, rbx; Lookaside
0x14001992f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140019936  nop     dword ptr [rax+rax+00h]
0x14001993b  jmp     short loc_140019950
0x14001993d  xor     ebx, ebx
0x14001993f  mov     edx, eax
0x140019941  mov     r8d, edi
0x140019944  call    cs:__imp_ExAllocatePool2
0x14001994b  nop     dword ptr [rax+rax+00h]
0x140019950  test    rax, rax
0x140019953  jz      loc_140019AA7
0x140019959  mov     [rax+8], edi
0x14001995c  xor     r8d, r8d
0x14001995f  xor     edx, edx
0x140019961  mov     [rax], rbx
0x140019964  lea     rdi, [rax+10h]
0x140019968  cmp     [rsi], edx
0x14001996a  jbe     short loc_140019989
0x14001996c  lea     rax, [rdx+rdx*2]
0x140019970  cmp     dword ptr [rsi+rax*4+10h], 0
0x140019975  jz      short loc_140019983
0x140019977  mov     eax, [rsi+rax*4+0Ch]
0x14001997b  mov     [rdi+r8*4+0Ch], eax
0x140019980  inc     r8d
0x140019983  inc     edx
0x140019985  cmp     edx, [rsi]
0x140019987  jb      short loc_14001996C
0x140019989  mov     dword ptr [rdi], 100180h
0x14001998f  mov     r9, rdi; void *
0x140019992  mov     [rdi+8], r8d
0x140019996  mov     edx, 1; unsigned int
0x14001999b  mov     [rdi+4], r8d
0x14001999f  mov     r8d, 0E010187h; unsigned int
0x1400199a5  mov     rcx, [r14+0A38h]
0x1400199ac  mov     [rsp+68h+var_48], ebp; unsigned int
0x1400199b0  mov     rcx, [rcx+10h]; struct _ADAPT *
0x1400199b4  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x1400199b9  mov     ebx, eax
0x1400199bb  test    eax, eax
0x1400199bd  js      loc_140019A71
0x1400199c3  mov     rcx, [r14+6C8h]; void *
0x1400199ca  mov     rdx, rdi; Src
0x1400199cd  mov     r8d, ebp; Size
0x1400199d0  call    memmove
0x1400199d5  mov     r9d, [rdi+8]
0x1400199d9  cmp     r9d, 1
0x1400199dd  jnz     short loc_140019A0C
0x1400199df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400199e6  lea     rsi, WPP_GLOBAL_Control
0x1400199ed  cmp     rcx, rsi
0x1400199f0  jz      short loc_140019A71
0x1400199f2  mov     rcx, [rcx+18h]
0x1400199f6  lea     edx, [r9+1Fh]
0x1400199fa  mov     r9d, [rdi+0Ch]
0x1400199fe  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x140019a05  call    WPP_SF_d
0x140019a0a  jmp     short loc_140019A71
0x140019a0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140019a13  lea     rsi, WPP_GLOBAL_Control
0x140019a1a  cmp     rcx, rsi
0x140019a1d  jz      short loc_140019A71
0x140019a1f  mov     rcx, [rcx+18h]
0x140019a23  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x140019a2a  mov     edx, 21h ; '!'
0x140019a2f  call    WPP_SF_d
0x140019a34  xor     eax, eax
0x140019a36  cmp     [rdi+8], eax
0x140019a39  jbe     short loc_140019A71
0x140019a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140019a42  lea     ebp, [rax+1]
0x140019a45  cmp     rcx, rsi
0x140019a48  jz      short loc_140019A6A
0x140019a4a  mov     eax, [rdi+rax*4+0Ch]
0x140019a4e  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x140019a55  mov     rcx, [rcx+18h]
0x140019a59  mov     edx, 22h ; '"'
0x140019a5e  mov     r9d, ebp
0x140019a61  mov     [rsp+68h+var_48], eax
0x140019a65  call    WPP_SF_Dd
0x140019a6a  mov     eax, ebp
0x140019a6c  cmp     eax, [rdi+8]
0x140019a6f  jb      short loc_140019A3B
0x140019a71  test    rdi, rdi
0x140019a74  jz      short loc_140019AB3
0x140019a76  lea     rcx, [rdi-10h]; P
0x140019a7a  mov     rax, [rcx]
0x140019a7d  test    rax, rax
0x140019a80  jz      short loc_140019A96
0x140019a82  mov     rdx, rcx; Entry
0x140019a85  mov     rcx, rax; Lookaside
0x140019a88  call    cs:__imp_ExFreeToNPagedLookasideList
0x140019a8f  nop     dword ptr [rax+rax+00h]
0x140019a94  jmp     short loc_140019AB3
0x140019a96  mov     edx, [rcx+8]; Tag
0x140019a99  call    cs:__imp_ExFreePoolWithTag
0x140019aa0  nop     dword ptr [rax+rax+00h]
0x140019aa5  jmp     short loc_140019AB3
0x140019aa7  mov     ebx, 0C000009Ah
0x140019aac  jmp     short loc_140019AB3
0x140019aae  mov     ebx, 0C0000023h
0x140019ab3  mov     eax, ebx
0x140019ab5  add     rsp, 38h
0x140019ab9  pop     r14
0x140019abb  pop     r13
0x140019abd  pop     rdi
0x140019abe  pop     rsi
0x140019abf  pop     rbp
0x140019ac0  pop     rbx
0x140019ac1  retn
```
