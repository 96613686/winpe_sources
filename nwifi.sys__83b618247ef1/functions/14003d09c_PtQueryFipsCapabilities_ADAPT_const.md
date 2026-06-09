# PtQueryFipsCapabilities(_ADAPT * const)

- ea: `0x14003d09c`
- end: `0x14003d30b`
- name: `?PtQueryFipsCapabilities@@YAXQEAU_ADAPT@@@Z`
- size: `623`
- prototype: `void __fastcall(struct _ADAPT *const)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14003cefc`

## callees

- `0x14000d22c`
- `0x140015b1c`
- `0x140020dc0`
- `0x14003ce38`
- `0x14003d09c`
- `0x14009a3d0`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003d1bc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003d1bc`
- `ntoskrnl!ExAllocatePool2` at `0x14003d1d4`
- `ntoskrnl!ExAllocatePool2` at `0x14003d1d4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003d297`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003d297`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d2a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d2a8`

## pseudocode

```c
void __fastcall PtQueryFipsCapabilities(struct _ADAPT *const a1)
{
  bool v1; // zf
  unsigned int v3; // eax
  __int64 v4; // r9
  unsigned int v5; // esi
  unsigned int v6; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  DOT11_FIPS_CAPABILITIES *v9; // rbx
  unsigned int v10; // eax
  unsigned int v11; // [rsp+30h] [rbp-28h] BYREF
  unsigned int Size[3]; // [rsp+34h] [rbp-24h] BYREF

  v1 = a1->AdapterEnhancedCapabilities.uWindowsWifiCxVersion == 0;
  memset(Size, 0, sizeof(Size));
  v11 = 0;
  if ( v1 )
  {
    PtGenerateFipsCapabilities(a1);
    return;
  }
  v3 = PtQueryAdapterSyncEx(a1, 0xE0101A8u, &Size[1], 8, Size, &v11);
  v4 = v3;
  if ( v3 && v3 != -2147483643 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids, v3);
    }
    return;
  }
  v5 = v11;
  v6 = v11 + 16;
  if ( v11 >= 0xFFFFFFF0 )
    goto LABEL_33;
  if ( v6 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_18:
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_20;
  }
  if ( v6 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_18;
  }
  if ( v6 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_18;
  }
  if ( v6 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_18;
  }
  p_DeviceQueue = 0;
  Pool2 = (char *)ExAllocatePool2(64, v6, 1718186871, v4);
LABEL_20:
  if ( !Pool2 )
  {
LABEL_33:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids);
    }
    return;
  }
  *(_QWORD *)Pool2 = p_DeviceQueue;
  v9 = (DOT11_FIPS_CAPABILITIES *)(Pool2 + 16);
  *((_DWORD *)Pool2 + 2) = 1718186871;
  if ( Size[0] )
  {
    memmove(v9, &Size[1], Size[0]);
LABEL_23:
    a1->fipsCapabilities = v9;
    return;
  }
  v10 = PtQueryAdapterSyncEx(a1, 0xE0101A8u, v9, v5, Size, &v11);
  if ( !v10 )
    goto LABEL_23;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer)
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids, v10);
  }
  if ( v9 )
  {
    if ( *(_QWORD *)v9[-2].FIPSCertifiedCipherAlgorithmsList )
      ExFreeToNPagedLookasideList(
        *(PNPAGED_LOOKASIDE_LIST *)v9[-2].FIPSCertifiedCipherAlgorithmsList,
        v9[-2].FIPSCertifiedCipherAlgorithmsList);
    else
      ExFreePoolWithTag(v9[-2].FIPSCertifiedCipherAlgorithmsList, *(_DWORD *)&v9[-1].NumFIPSCertifiedCipherAlgorithms);
  }
}

```

## disassembly

```asm
0x14003d09c  mov     [rsp+arg_8], rbx
0x14003d0a1  mov     [rsp+arg_10], rsi
0x14003d0a6  push    rdi
0x14003d0a7  sub     rsp, 50h
0x14003d0ab  mov     rax, cs:__security_cookie
0x14003d0b2  xor     rax, rsp
0x14003d0b5  mov     [rsp+58h+var_18], rax
0x14003d0ba  cmp     qword ptr [rcx+610h], 0
0x14003d0c2  mov     rdi, rcx
0x14003d0c5  mov     dword ptr [rsp+58h+Size], 0
0x14003d0cd  mov     [rsp+58h+var_28], 0
0x14003d0d5  mov     qword ptr [rsp+58h+Size+4], 0
0x14003d0de  jnz     short loc_14003D0EA
0x14003d0e0  call    ?PtGenerateFipsCapabilities@@YAXQEAU_ADAPT@@@Z; PtGenerateFipsCapabilities(_ADAPT * const)
0x14003d0e5  jmp     loc_14003D2ED
0x14003d0ea  lea     rax, [rsp+58h+var_28]
0x14003d0ef  mov     r9d, 8; unsigned int
0x14003d0f5  mov     [rsp+58h+var_30], rax; unsigned int *
0x14003d0fa  lea     r8, [rsp+58h+Size+4]; void *
0x14003d0ff  lea     rax, [rsp+58h+Size]
0x14003d104  mov     edx, 0E0101A8h; unsigned int
0x14003d109  mov     [rsp+58h+var_38], rax; unsigned int *
0x14003d10e  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x14003d113  mov     r9d, eax
0x14003d116  test    eax, eax
0x14003d118  jz      short loc_14003D169
0x14003d11a  cmp     eax, 80000005h
0x14003d11f  jz      short loc_14003D169
0x14003d121  mov     r10, cs:WPP_GLOBAL_Control
0x14003d128  lea     rcx, WPP_GLOBAL_Control
0x14003d12f  cmp     r10, rcx
0x14003d132  jz      loc_14003D2ED
0x14003d138  cmp     byte ptr [r10+29h], 1
0x14003d13d  jb      loc_14003D2ED
0x14003d143  mov     eax, [r10+2Ch]
0x14003d147  test    al, 8
0x14003d149  jz      loc_14003D2ED
0x14003d14f  mov     rcx, [r10+18h]
0x14003d153  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x14003d15a  mov     edx, 17h
0x14003d15f  call    WPP_SF_d
0x14003d164  jmp     loc_14003D2ED
0x14003d169  mov     esi, [rsp+58h+var_28]
0x14003d16d  lea     eax, [rsi+10h]
0x14003d170  cmp     eax, 10h
0x14003d173  jb      loc_14003D2B6
0x14003d179  mov     ecx, 40h ; '@'
0x14003d17e  cmp     eax, ecx
0x14003d180  ja      short loc_14003D18B
0x14003d182  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14003d189  jmp     short loc_14003D1B9
0x14003d18b  cmp     eax, 100h
0x14003d190  ja      short loc_14003D19B
0x14003d192  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14003d199  jmp     short loc_14003D1B9
0x14003d19b  cmp     eax, 400h
0x14003d1a0  ja      short loc_14003D1AB
0x14003d1a2  lea     rbx, Lookaside
0x14003d1a9  jmp     short loc_14003D1B9
0x14003d1ab  cmp     eax, 800h
0x14003d1b0  ja      short loc_14003D1CA
0x14003d1b2  lea     rbx, stru_1400B0180
0x14003d1b9  mov     rcx, rbx; Lookaside
0x14003d1bc  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003d1c3  nop     dword ptr [rax+rax+00h]
0x14003d1c8  jmp     short loc_14003D1E0
0x14003d1ca  xor     ebx, ebx
0x14003d1cc  mov     edx, eax
0x14003d1ce  mov     r8d, 66697377h
0x14003d1d4  call    cs:__imp_ExAllocatePool2
0x14003d1db  nop     dword ptr [rax+rax+00h]
0x14003d1e0  test    rax, rax
0x14003d1e3  jz      loc_14003D2B6
0x14003d1e9  mov     [rax], rbx
0x14003d1ec  lea     rbx, [rax+10h]
0x14003d1f0  mov     dword ptr [rax+8], 66697377h
0x14003d1f7  mov     eax, dword ptr [rsp+58h+Size]
0x14003d1fb  test    eax, eax
0x14003d1fd  jz      short loc_14003D21B
0x14003d1ff  mov     r8d, eax; Size
0x14003d202  lea     rdx, [rsp+58h+Size+4]; Src
0x14003d207  mov     rcx, rbx; void *
0x14003d20a  call    memmove
0x14003d20f  mov     [rdi+698h], rbx
0x14003d216  jmp     loc_14003D2ED
0x14003d21b  lea     rax, [rsp+58h+var_28]
0x14003d220  mov     r9d, esi; unsigned int
0x14003d223  mov     [rsp+58h+var_30], rax; unsigned int *
0x14003d228  mov     r8, rbx; void *
0x14003d22b  lea     rax, [rsp+58h+Size]
0x14003d230  mov     edx, 0E0101A8h; unsigned int
0x14003d235  mov     rcx, rdi; struct _ADAPT *
0x14003d238  mov     [rsp+58h+var_38], rax; unsigned int *
0x14003d23d  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x14003d242  mov     r9d, eax
0x14003d245  test    eax, eax
0x14003d247  jz      short loc_14003D20F
0x14003d249  mov     r10, cs:WPP_GLOBAL_Control
0x14003d250  lea     rcx, WPP_GLOBAL_Control
0x14003d257  cmp     r10, rcx
0x14003d25a  jz      short loc_14003D280
0x14003d25c  cmp     byte ptr [r10+29h], 1
0x14003d261  jb      short loc_14003D280
0x14003d263  mov     eax, [r10+2Ch]
0x14003d267  test    al, 8
0x14003d269  jz      short loc_14003D280
0x14003d26b  mov     rcx, [r10+18h]
0x14003d26f  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x14003d276  mov     edx, 19h
0x14003d27b  call    WPP_SF_d
0x14003d280  test    rbx, rbx
0x14003d283  jz      short loc_14003D2ED
0x14003d285  lea     rcx, [rbx-10h]; P
0x14003d289  mov     rax, [rcx]
0x14003d28c  test    rax, rax
0x14003d28f  jz      short loc_14003D2A5
0x14003d291  mov     rdx, rcx; Entry
0x14003d294  mov     rcx, rax; Lookaside
0x14003d297  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003d29e  nop     dword ptr [rax+rax+00h]
0x14003d2a3  jmp     short loc_14003D2ED
0x14003d2a5  mov     edx, [rcx+8]; Tag
0x14003d2a8  call    cs:__imp_ExFreePoolWithTag
0x14003d2af  nop     dword ptr [rax+rax+00h]
0x14003d2b4  jmp     short loc_14003D2ED
0x14003d2b6  mov     r9, cs:WPP_GLOBAL_Control
0x14003d2bd  lea     rcx, WPP_GLOBAL_Control
0x14003d2c4  cmp     r9, rcx
0x14003d2c7  jz      short loc_14003D2ED
0x14003d2c9  cmp     byte ptr [r9+29h], 1
0x14003d2ce  jb      short loc_14003D2ED
0x14003d2d0  mov     eax, [r9+2Ch]
0x14003d2d4  test    al, 8
0x14003d2d6  jz      short loc_14003D2ED
0x14003d2d8  mov     rcx, [r9+18h]
0x14003d2dc  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x14003d2e3  mov     edx, 18h
0x14003d2e8  call    WPP_SF_
0x14003d2ed  mov     rcx, [rsp+58h+var_18]
0x14003d2f2  xor     rcx, rsp; StackCookie
0x14003d2f5  call    __security_check_cookie
0x14003d2fa  mov     rbx, [rsp+58h+arg_8]
0x14003d2ff  mov     rsi, [rsp+58h+arg_10]
0x14003d304  add     rsp, 50h
0x14003d308  pop     rdi
0x14003d309  retn
```
