# PtQueryFipsCapabilities(_ADAPT * const)

- ea: `0x14003d2bc`
- end: `0x14003d52b`
- name: `?PtQueryFipsCapabilities@@YAXQEAU_ADAPT@@@Z`
- size: `623`
- prototype: `void __fastcall(struct _ADAPT *const)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14003d11c`

## callees

- `0x14000d21c`
- `0x140015b0c`
- `0x140020dc0`
- `0x14003d058`
- `0x14003d2bc`
- `0x14009bbb0`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003d3dc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003d3dc`
- `ntoskrnl!ExAllocatePool2` at `0x14003d3f4`
- `ntoskrnl!ExAllocatePool2` at `0x14003d3f4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003d4b7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003d4b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d4c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d4c8`

## pseudocode

```c
void __fastcall PtQueryFipsCapabilities(struct _ADAPT *const a1)
{
  bool v1; // zf
  unsigned int v3; // eax
  unsigned int v4; // esi
  unsigned int v5; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  DOT11_FIPS_CAPABILITIES *v8; // rbx
  unsigned int v9; // eax
  unsigned int v10; // [rsp+30h] [rbp-28h] BYREF
  unsigned int Size[3]; // [rsp+34h] [rbp-24h] BYREF

  v1 = a1->AdapterEnhancedCapabilities.uWindowsWifiCxVersion == 0;
  memset(Size, 0, sizeof(Size));
  v10 = 0;
  if ( v1 )
  {
    PtGenerateFipsCapabilities(a1);
    return;
  }
  v3 = PtQueryAdapterSyncEx(a1, 0xE0101A8u, &Size[1], 8, Size, &v10);
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
  v4 = v10;
  v5 = v10 + 16;
  if ( v10 >= 0xFFFFFFF0 )
    goto LABEL_33;
  if ( v5 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_18:
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_20;
  }
  if ( v5 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_18;
  }
  if ( v5 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_18;
  }
  if ( v5 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_18;
  }
  p_DeviceQueue = 0;
  Pool2 = (char *)ExAllocatePool2(64, v5, 1718186871);
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
  v8 = (DOT11_FIPS_CAPABILITIES *)(Pool2 + 16);
  *((_DWORD *)Pool2 + 2) = 1718186871;
  if ( Size[0] )
  {
    memmove(v8, &Size[1], Size[0]);
LABEL_23:
    a1->fipsCapabilities = v8;
    return;
  }
  v9 = PtQueryAdapterSyncEx(a1, 0xE0101A8u, v8, v4, Size, &v10);
  if ( !v9 )
    goto LABEL_23;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer)
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids, v9);
  }
  if ( v8 )
  {
    if ( *(_QWORD *)v8[-2].FIPSCertifiedCipherAlgorithmsList )
      ExFreeToNPagedLookasideList(
        *(PNPAGED_LOOKASIDE_LIST *)v8[-2].FIPSCertifiedCipherAlgorithmsList,
        v8[-2].FIPSCertifiedCipherAlgorithmsList);
    else
      ExFreePoolWithTag(v8[-2].FIPSCertifiedCipherAlgorithmsList, *(_DWORD *)&v8[-1].NumFIPSCertifiedCipherAlgorithms);
  }
}

```

## disassembly

```asm
0x14003d2bc  mov     [rsp+arg_8], rbx
0x14003d2c1  mov     [rsp+arg_10], rsi
0x14003d2c6  push    rdi
0x14003d2c7  sub     rsp, 50h
0x14003d2cb  mov     rax, cs:__security_cookie
0x14003d2d2  xor     rax, rsp
0x14003d2d5  mov     [rsp+58h+var_18], rax
0x14003d2da  cmp     qword ptr [rcx+610h], 0
0x14003d2e2  mov     rdi, rcx
0x14003d2e5  mov     dword ptr [rsp+58h+Size], 0
0x14003d2ed  mov     [rsp+58h+var_28], 0
0x14003d2f5  mov     qword ptr [rsp+58h+Size+4], 0
0x14003d2fe  jnz     short loc_14003D30A
0x14003d300  call    ?PtGenerateFipsCapabilities@@YAXQEAU_ADAPT@@@Z; PtGenerateFipsCapabilities(_ADAPT * const)
0x14003d305  jmp     loc_14003D50D
0x14003d30a  lea     rax, [rsp+58h+var_28]
0x14003d30f  mov     r9d, 8; unsigned int
0x14003d315  mov     [rsp+58h+var_30], rax; unsigned int *
0x14003d31a  lea     r8, [rsp+58h+Size+4]; void *
0x14003d31f  lea     rax, [rsp+58h+Size]
0x14003d324  mov     edx, 0E0101A8h; unsigned int
0x14003d329  mov     [rsp+58h+var_38], rax; unsigned int *
0x14003d32e  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x14003d333  mov     r9d, eax
0x14003d336  test    eax, eax
0x14003d338  jz      short loc_14003D389
0x14003d33a  cmp     eax, 80000005h
0x14003d33f  jz      short loc_14003D389
0x14003d341  mov     r10, cs:WPP_GLOBAL_Control
0x14003d348  lea     rcx, WPP_GLOBAL_Control
0x14003d34f  cmp     r10, rcx
0x14003d352  jz      loc_14003D50D
0x14003d358  cmp     byte ptr [r10+29h], 1
0x14003d35d  jb      loc_14003D50D
0x14003d363  mov     eax, [r10+2Ch]
0x14003d367  test    al, 8
0x14003d369  jz      loc_14003D50D
0x14003d36f  mov     rcx, [r10+18h]
0x14003d373  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x14003d37a  mov     edx, 17h
0x14003d37f  call    WPP_SF_d
0x14003d384  jmp     loc_14003D50D
0x14003d389  mov     esi, [rsp+58h+var_28]
0x14003d38d  lea     eax, [rsi+10h]
0x14003d390  cmp     eax, 10h
0x14003d393  jb      loc_14003D4D6
0x14003d399  mov     ecx, 40h ; '@'
0x14003d39e  cmp     eax, ecx
0x14003d3a0  ja      short loc_14003D3AB
0x14003d3a2  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14003d3a9  jmp     short loc_14003D3D9
0x14003d3ab  cmp     eax, 100h
0x14003d3b0  ja      short loc_14003D3BB
0x14003d3b2  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14003d3b9  jmp     short loc_14003D3D9
0x14003d3bb  cmp     eax, 400h
0x14003d3c0  ja      short loc_14003D3CB
0x14003d3c2  lea     rbx, Lookaside
0x14003d3c9  jmp     short loc_14003D3D9
0x14003d3cb  cmp     eax, 800h
0x14003d3d0  ja      short loc_14003D3EA
0x14003d3d2  lea     rbx, stru_1400B31C0
0x14003d3d9  mov     rcx, rbx; Lookaside
0x14003d3dc  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003d3e3  nop     dword ptr [rax+rax+00h]
0x14003d3e8  jmp     short loc_14003D400
0x14003d3ea  xor     ebx, ebx
0x14003d3ec  mov     edx, eax
0x14003d3ee  mov     r8d, 66697377h
0x14003d3f4  call    cs:__imp_ExAllocatePool2
0x14003d3fb  nop     dword ptr [rax+rax+00h]
0x14003d400  test    rax, rax
0x14003d403  jz      loc_14003D4D6
0x14003d409  mov     [rax], rbx
0x14003d40c  lea     rbx, [rax+10h]
0x14003d410  mov     dword ptr [rax+8], 66697377h
0x14003d417  mov     eax, dword ptr [rsp+58h+Size]
0x14003d41b  test    eax, eax
0x14003d41d  jz      short loc_14003D43B
0x14003d41f  mov     r8d, eax; Size
0x14003d422  lea     rdx, [rsp+58h+Size+4]; Src
0x14003d427  mov     rcx, rbx; void *
0x14003d42a  call    memmove
0x14003d42f  mov     [rdi+698h], rbx
0x14003d436  jmp     loc_14003D50D
0x14003d43b  lea     rax, [rsp+58h+var_28]
0x14003d440  mov     r9d, esi; unsigned int
0x14003d443  mov     [rsp+58h+var_30], rax; unsigned int *
0x14003d448  mov     r8, rbx; void *
0x14003d44b  lea     rax, [rsp+58h+Size]
0x14003d450  mov     edx, 0E0101A8h; unsigned int
0x14003d455  mov     rcx, rdi; struct _ADAPT *
0x14003d458  mov     [rsp+58h+var_38], rax; unsigned int *
0x14003d45d  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x14003d462  mov     r9d, eax
0x14003d465  test    eax, eax
0x14003d467  jz      short loc_14003D42F
0x14003d469  mov     r10, cs:WPP_GLOBAL_Control
0x14003d470  lea     rcx, WPP_GLOBAL_Control
0x14003d477  cmp     r10, rcx
0x14003d47a  jz      short loc_14003D4A0
0x14003d47c  cmp     byte ptr [r10+29h], 1
0x14003d481  jb      short loc_14003D4A0
0x14003d483  mov     eax, [r10+2Ch]
0x14003d487  test    al, 8
0x14003d489  jz      short loc_14003D4A0
0x14003d48b  mov     rcx, [r10+18h]
0x14003d48f  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x14003d496  mov     edx, 19h
0x14003d49b  call    WPP_SF_d
0x14003d4a0  test    rbx, rbx
0x14003d4a3  jz      short loc_14003D50D
0x14003d4a5  lea     rcx, [rbx-10h]; P
0x14003d4a9  mov     rax, [rcx]
0x14003d4ac  test    rax, rax
0x14003d4af  jz      short loc_14003D4C5
0x14003d4b1  mov     rdx, rcx; Entry
0x14003d4b4  mov     rcx, rax; Lookaside
0x14003d4b7  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003d4be  nop     dword ptr [rax+rax+00h]
0x14003d4c3  jmp     short loc_14003D50D
0x14003d4c5  mov     edx, [rcx+8]; Tag
0x14003d4c8  call    cs:__imp_ExFreePoolWithTag
0x14003d4cf  nop     dword ptr [rax+rax+00h]
0x14003d4d4  jmp     short loc_14003D50D
0x14003d4d6  mov     r9, cs:WPP_GLOBAL_Control
0x14003d4dd  lea     rcx, WPP_GLOBAL_Control
0x14003d4e4  cmp     r9, rcx
0x14003d4e7  jz      short loc_14003D50D
0x14003d4e9  cmp     byte ptr [r9+29h], 1
0x14003d4ee  jb      short loc_14003D50D
0x14003d4f0  mov     eax, [r9+2Ch]
0x14003d4f4  test    al, 8
0x14003d4f6  jz      short loc_14003D50D
0x14003d4f8  mov     rcx, [r9+18h]
0x14003d4fc  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x14003d503  mov     edx, 18h
0x14003d508  call    WPP_SF_
0x14003d50d  mov     rcx, [rsp+58h+var_18]
0x14003d512  xor     rcx, rsp; StackCookie
0x14003d515  call    __security_check_cookie
0x14003d51a  mov     rbx, [rsp+58h+arg_8]
0x14003d51f  mov     rsi, [rsp+58h+arg_10]
0x14003d524  add     rsp, 50h
0x14003d528  pop     rdi
0x14003d529  retn
```
