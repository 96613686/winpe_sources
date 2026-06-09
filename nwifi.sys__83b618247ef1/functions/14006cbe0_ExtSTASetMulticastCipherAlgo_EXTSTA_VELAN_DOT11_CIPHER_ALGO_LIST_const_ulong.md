# ExtSTASetMulticastCipherAlgo(EXTSTA_VELAN *,_DOT11_CIPHER_ALGO_LIST const *,ulong)

- ea: `0x14006cbe0`
- end: `0x14006ced2`
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
- `0x14006cbe0`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006cd3e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006cd3e`
- `ntoskrnl!ExAllocatePool2` at `0x14006cd53`
- `ntoskrnl!ExAllocatePool2` at `0x14006cd53`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006ce97`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006ce97`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cea8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cea8`

## pseudocode

```c
__int64 __fastcall ExtSTASetMulticastCipherAlgo(
        struct EXTSTA_VELAN *a1,
        const struct _DOT11_CIPHER_ALGO_LIST *a2,
        int a3)
{
  __int64 v3; // r9
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

  v3 = *(unsigned int *)a2;
  if ( (a3 - 8) / 0xCu < (unsigned int)v3 )
    return (unsigned int)-1073741789;
  if ( (_DWORD)v3 != *((_DWORD *)a2 + 1) )
    return (unsigned int)-1073741811;
  if ( (_DWORD)v3 )
  {
    for ( i = 0; (unsigned int)i < (int)v3 - 1; i = (unsigned int)(i + 1) )
    {
      v7 = i + 1;
      if ( (int)i + 1 < (unsigned int)v3 )
      {
        while ( *((_DWORD *)a2 + 3 * i + 3) != *((_DWORD *)a2 + 3 * v7 + 3) )
        {
          if ( ++v7 >= (unsigned int)v3 )
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
  if ( v9 < (unsigned int)v3 )
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
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_33;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v17, 808464432, v3);
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
0x14006cbe0  push    rbx
0x14006cbe2  push    rbp
0x14006cbe3  push    rsi
0x14006cbe4  push    rdi
0x14006cbe5  push    r13
0x14006cbe7  push    r14
0x14006cbe9  sub     rsp, 38h
0x14006cbed  mov     r9d, [rdx]
0x14006cbf0  add     r8d, 0FFFFFFF8h
0x14006cbf4  mov     rsi, rdx
0x14006cbf7  mov     rax, 0AAAAAAAAAAAAAAABh
0x14006cc01  mul     r8
0x14006cc04  mov     r14, rcx
0x14006cc07  shr     rdx, 3
0x14006cc0b  cmp     edx, r9d
0x14006cc0e  jb      loc_14006CEBD
0x14006cc14  cmp     r9d, [rsi+4]
0x14006cc18  jnz     loc_14006CCD0
0x14006cc1e  test    r9d, r9d
0x14006cc21  jz      short loc_14006CC5D
0x14006cc23  xor     eax, eax
0x14006cc25  lea     r8d, [r9-1]
0x14006cc29  cmp     eax, r8d
0x14006cc2c  jnb     short loc_14006CC5D
0x14006cc2e  lea     edx, [rax+1]
0x14006cc31  mov     ecx, edx
0x14006cc33  cmp     edx, r9d
0x14006cc36  jnb     short loc_14006CC59
0x14006cc38  inc     rax
0x14006cc3b  lea     rax, [rax+rax*2]
0x14006cc3f  mov     r10d, [rsi+rax*4]
0x14006cc43  mov     eax, ecx
0x14006cc45  inc     rax
0x14006cc48  lea     rax, [rax+rax*2]
0x14006cc4c  cmp     r10d, [rsi+rax*4]
0x14006cc50  jz      short loc_14006CCD0
0x14006cc52  inc     ecx
0x14006cc54  cmp     ecx, r9d
0x14006cc57  jb      short loc_14006CC43
0x14006cc59  mov     eax, edx
0x14006cc5b  jmp     short loc_14006CC29
0x14006cc5d  mov     ebx, 798h
0x14006cc62  xor     r8d, r8d
0x14006cc65  cmp     dword ptr [r14+6BCh], 1
0x14006cc6d  lea     ecx, [rbx+70h]
0x14006cc70  lea     edi, [rcx-68h]
0x14006cc73  cmovnz  ebx, ecx
0x14006cc76  lea     ecx, [rdi+70h]
0x14006cc79  cmovnz  edi, ecx
0x14006cc7c  cmp     r8d, r9d
0x14006cc7f  jnb     short loc_14006CCDA
0x14006cc81  mov     r11d, [rbx+r14]
0x14006cc85  mov     eax, r8d
0x14006cc88  inc     rax
0x14006cc8b  xor     edx, edx
0x14006cc8d  lea     rax, [rax+rax*2]
0x14006cc91  mov     r10d, [rsi+rax*4]
0x14006cc95  cmp     edx, r11d
0x14006cc98  jnb     short loc_14006CCA8
0x14006cc9a  mov     rax, [rdi+r14]
0x14006cc9e  cmp     [rax+rdx*4], r10d
0x14006cca2  jz      short loc_14006CCCB
0x14006cca4  inc     edx
0x14006cca6  jmp     short loc_14006CC95
0x14006cca8  lea     eax, [r10-1]
0x14006ccac  test    eax, 0FFFFFFFBh
0x14006ccb1  jnz     short loc_14006CCD0
0x14006ccb3  xor     edx, edx
0x14006ccb5  cmp     edx, r11d
0x14006ccb8  jnb     short loc_14006CCD0
0x14006ccba  mov     rax, [rdi+r14]
0x14006ccbe  cmp     dword ptr [rax+rdx*4], 101h
0x14006ccc5  jz      short loc_14006CCCB
0x14006ccc7  inc     edx
0x14006ccc9  jmp     short loc_14006CCB5
0x14006cccb  inc     r8d
0x14006ccce  jmp     short loc_14006CC7C
0x14006ccd0  mov     ebx, 0C000000Dh
0x14006ccd5  jmp     loc_14006CEC2
0x14006ccda  mov     eax, [rbx+r14]
0x14006ccde  mov     r13d, 10h
0x14006cce4  lea     ebp, ds:0Ch[rax*4]
0x14006cceb  lea     eax, [rbp+10h]
0x14006ccee  cmp     eax, r13d
0x14006ccf1  jb      loc_14006CEB6
0x14006ccf7  lea     ecx, [r13+30h]
0x14006ccfb  mov     edi, 30303030h
0x14006cd00  cmp     eax, ecx
0x14006cd02  ja      short loc_14006CD0D
0x14006cd04  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14006cd0b  jmp     short loc_14006CD3B
0x14006cd0d  cmp     eax, 100h
0x14006cd12  ja      short loc_14006CD1D
0x14006cd14  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006cd1b  jmp     short loc_14006CD3B
0x14006cd1d  cmp     eax, 400h
0x14006cd22  ja      short loc_14006CD2D
0x14006cd24  lea     rbx, Lookaside
0x14006cd2b  jmp     short loc_14006CD3B
0x14006cd2d  cmp     eax, 800h
0x14006cd32  ja      short loc_14006CD4C
0x14006cd34  lea     rbx, stru_1400B0180
0x14006cd3b  mov     rcx, rbx; Lookaside
0x14006cd3e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006cd45  nop     dword ptr [rax+rax+00h]
0x14006cd4a  jmp     short loc_14006CD5F
0x14006cd4c  xor     ebx, ebx
0x14006cd4e  mov     edx, eax
0x14006cd50  mov     r8d, edi
0x14006cd53  call    cs:__imp_ExAllocatePool2
0x14006cd5a  nop     dword ptr [rax+rax+00h]
0x14006cd5f  test    rax, rax
0x14006cd62  jz      loc_14006CEB6
0x14006cd68  mov     [rax+8], edi
0x14006cd6b  xor     r8d, r8d
0x14006cd6e  xor     edx, edx
0x14006cd70  mov     [rax], rbx
0x14006cd73  lea     rdi, [rax+10h]
0x14006cd77  cmp     [rsi], edx
0x14006cd79  jbe     short loc_14006CD98
0x14006cd7b  lea     rax, [rdx+rdx*2]
0x14006cd7f  cmp     dword ptr [rsi+rax*4+10h], 0
0x14006cd84  jz      short loc_14006CD92
0x14006cd86  mov     eax, [rsi+rax*4+0Ch]
0x14006cd8a  mov     [rdi+r8*4+0Ch], eax
0x14006cd8f  inc     r8d
0x14006cd92  inc     edx
0x14006cd94  cmp     edx, [rsi]
0x14006cd96  jb      short loc_14006CD7B
0x14006cd98  mov     dword ptr [rdi], 100180h
0x14006cd9e  mov     r9, rdi; void *
0x14006cda1  mov     [rdi+8], r8d
0x14006cda5  mov     edx, 1; unsigned int
0x14006cdaa  mov     [rdi+4], r8d
0x14006cdae  mov     r8d, 0E010189h; unsigned int
0x14006cdb4  mov     rcx, [r14+0A38h]
0x14006cdbb  mov     [rsp+68h+var_48], ebp; unsigned int
0x14006cdbf  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006cdc3  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006cdc8  mov     ebx, eax
0x14006cdca  test    eax, eax
0x14006cdcc  js      loc_14006CE80
0x14006cdd2  mov     rcx, [r14+6D0h]; void *
0x14006cdd9  mov     rdx, rdi; Src
0x14006cddc  mov     r8d, ebp; Size
0x14006cddf  call    memmove
0x14006cde4  mov     r9d, [rdi+8]
0x14006cde8  cmp     r9d, 1
0x14006cdec  jnz     short loc_14006CE1B
0x14006cdee  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cdf5  lea     rsi, WPP_GLOBAL_Control
0x14006cdfc  cmp     rcx, rsi
0x14006cdff  jz      short loc_14006CE80
0x14006ce01  mov     rcx, [rcx+18h]
0x14006ce05  lea     edx, [r9+22h]
0x14006ce09  mov     r9d, [rdi+0Ch]
0x14006ce0d  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006ce14  call    WPP_SF_d
0x14006ce19  jmp     short loc_14006CE80
0x14006ce1b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ce22  lea     rsi, WPP_GLOBAL_Control
0x14006ce29  cmp     rcx, rsi
0x14006ce2c  jz      short loc_14006CE80
0x14006ce2e  mov     rcx, [rcx+18h]
0x14006ce32  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006ce39  mov     edx, 24h ; '$'
0x14006ce3e  call    WPP_SF_d
0x14006ce43  xor     eax, eax
0x14006ce45  cmp     [rdi+8], eax
0x14006ce48  jbe     short loc_14006CE80
0x14006ce4a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ce51  lea     ebp, [rax+1]
0x14006ce54  cmp     rcx, rsi
0x14006ce57  jz      short loc_14006CE79
0x14006ce59  mov     eax, [rdi+rax*4+0Ch]
0x14006ce5d  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006ce64  mov     rcx, [rcx+18h]
0x14006ce68  mov     edx, 25h ; '%'
0x14006ce6d  mov     r9d, ebp
0x14006ce70  mov     [rsp+68h+var_48], eax
0x14006ce74  call    WPP_SF_Dd
0x14006ce79  mov     eax, ebp
0x14006ce7b  cmp     eax, [rdi+8]
0x14006ce7e  jb      short loc_14006CE4A
0x14006ce80  test    rdi, rdi
0x14006ce83  jz      short loc_14006CEC2
0x14006ce85  lea     rcx, [rdi-10h]; P
0x14006ce89  mov     rax, [rcx]
0x14006ce8c  test    rax, rax
0x14006ce8f  jz      short loc_14006CEA5
0x14006ce91  mov     rdx, rcx; Entry
0x14006ce94  mov     rcx, rax; Lookaside
0x14006ce97  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006ce9e  nop     dword ptr [rax+rax+00h]
0x14006cea3  jmp     short loc_14006CEC2
0x14006cea5  mov     edx, [rcx+8]; Tag
0x14006cea8  call    cs:__imp_ExFreePoolWithTag
0x14006ceaf  nop     dword ptr [rax+rax+00h]
0x14006ceb4  jmp     short loc_14006CEC2
0x14006ceb6  mov     ebx, 0C000009Ah
0x14006cebb  jmp     short loc_14006CEC2
0x14006cebd  mov     ebx, 0C0000023h
0x14006cec2  mov     eax, ebx
0x14006cec4  add     rsp, 38h
0x14006cec8  pop     r14
0x14006ceca  pop     r13
0x14006cecc  pop     rdi
0x14006cecd  pop     rsi
0x14006cece  pop     rbp
0x14006cecf  pop     rbx
0x14006ced0  retn
```
