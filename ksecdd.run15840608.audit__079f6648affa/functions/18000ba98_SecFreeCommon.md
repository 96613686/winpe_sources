# SecFreeCommon

- ea: `0x18000ba98`
- end: `0x18000bbfd`
- name: `SecFreeCommon`
- size: `357`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002900`
- `0x1800029f0`
- `0x18000d574`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180005718`
- `0x180005b58`
- `0x18000ba98`
- `0x18000bc60`

## import_xrefs

- `ntoskrnl!ZwFreeVirtualMemory` at `0x18000bb77`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x18000bb77`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000bacf`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000bacf`
- `ntoskrnl!PsIsProtectedProcess` at `0x18000bb0e`
- `ntoskrnl!PsIsProtectedProcess` at `0x18000bb0e`
- `ntoskrnl!MmIsUserAddress` at `0x18000bb22`
- `ntoskrnl!MmIsUserAddress` at `0x18000bb56`
- `ntoskrnl!MmIsUserAddress` at `0x18000bb22`
- `ntoskrnl!MmIsUserAddress` at `0x18000bb56`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bb9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bb9e`
- `ntoskrnl!ZwClose` at `0x18000bb46`
- `ntoskrnl!ZwClose` at `0x18000bb46`

## pseudocode

```c
__int64 __fastcall SecFreeCommon(HANDLE ProcessHandle, void *a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // edi
  unsigned int v5; // esi
  struct _EPROCESS *CurrentProcess; // rbx
  void *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int v12; // ebx
  struct _EPROCESS **v13; // [rsp+30h] [rbp-10h] BYREF
  ULONG_PTR RegionSize; // [rsp+38h] [rbp-8h] BYREF
  PVOID BaseAddress; // [rsp+68h] [rbp+28h] BYREF

  BaseAddress = a2;
  RegionSize = 0;
  v4 = a4;
  v5 = a3;
  if ( !a2 )
    return 0;
  CurrentProcess = (struct _EPROCESS *)PsGetCurrentProcess(ProcessHandle, a2, a3, a4);
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v13);
  if ( v13
    && CurrentProcess != WPP_MAIN_CB.DeviceExtension
    && CurrentProcess != *v13
    && v4 == -3
    && (unsigned int)PsIsProtectedProcess(CurrentProcess)
    && (unsigned __int8)MmIsUserAddress(BaseAddress) )
  {
    v9 = (void *)KsecRemoveValidVm(CurrentProcess, (unsigned __int8 *)BaseAddress);
    if ( v9 )
    {
      ZwClose(v9);
LABEL_11:
      if ( (unsigned __int8)MmIsUserAddress(BaseAddress) )
        ZwFreeVirtualMemory(ProcessHandle, &BaseAddress, &RegionSize, 0x8000u);
      else
        ExFreePoolWithTag(BaseAddress, 0);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0 )
        WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 3), v10, v11, v4, BaseAddress);
      v12 = 1;
      goto LABEL_20;
    }
  }
  else if ( KsecRemoveValidAddressCommon((unsigned __int8 *)BaseAddress, v5) )
  {
    goto LABEL_11;
  }
  v12 = 0;
LABEL_20:
  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v13);
  return v12;
}

```

## disassembly

```asm
0x18000ba98  mov     [rsp-18h+arg_0], rbx
0x18000ba9d  mov     [rsp-18h+arg_10], rsi
0x18000baa2  mov     [rsp-18h+BaseAddress], rdx
0x18000baa7  push    rbp
0x18000baa8  push    rdi
0x18000baa9  push    r14
0x18000baab  mov     rbp, rsp
0x18000baae  sub     rsp, 40h
0x18000bab2  mov     [rbp+RegionSize], 0
0x18000baba  mov     edi, r9d
0x18000babd  mov     esi, r8d
0x18000bac0  mov     r14, rcx
0x18000bac3  test    rdx, rdx
0x18000bac6  jnz     short loc_18000BACF
0x18000bac8  xor     eax, eax
0x18000baca  jmp     loc_18000BBE9
0x18000bacf  call    cs:__imp_PsGetCurrentProcess
0x18000bad6  nop     dword ptr [rax+rax+00h]
0x18000badb  lea     rcx, [rbp+var_10]; this
0x18000badf  mov     rbx, rax
0x18000bae2  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x18000bae7  mov     rcx, [rbp+var_10]
0x18000baeb  test    rcx, rcx
0x18000baee  jz      loc_18000BB85
0x18000baf4  cmp     rbx, cs:WPP_MAIN_CB.DeviceExtension
0x18000bafb  jz      loc_18000BB85
0x18000bb01  cmp     rbx, [rcx]
0x18000bb04  jz      short loc_18000BB85
0x18000bb06  cmp     edi, 0FFFFFFFDh
0x18000bb09  jnz     short loc_18000BB85
0x18000bb0b  mov     rcx, rbx
0x18000bb0e  call    cs:__imp_PsIsProtectedProcess
0x18000bb15  nop     dword ptr [rax+rax+00h]
0x18000bb1a  test    eax, eax
0x18000bb1c  jz      short loc_18000BB85
0x18000bb1e  mov     rcx, [rbp+BaseAddress]
0x18000bb22  call    cs:__imp_MmIsUserAddress
0x18000bb29  nop     dword ptr [rax+rax+00h]
0x18000bb2e  test    al, al
0x18000bb30  jz      short loc_18000BB85
0x18000bb32  mov     rdx, [rbp+BaseAddress]; unsigned __int8 *
0x18000bb36  mov     rcx, rbx; struct _EPROCESS *
0x18000bb39  call    KsecRemoveValidVm
0x18000bb3e  test    rax, rax
0x18000bb41  jz      short loc_18000BB94
0x18000bb43  mov     rcx, rax; Handle
0x18000bb46  call    cs:__imp_ZwClose
0x18000bb4d  nop     dword ptr [rax+rax+00h]
0x18000bb52  mov     rcx, [rbp+BaseAddress]
0x18000bb56  call    cs:__imp_MmIsUserAddress
0x18000bb5d  nop     dword ptr [rax+rax+00h]
0x18000bb62  test    al, al
0x18000bb64  jz      short loc_18000BB98
0x18000bb66  mov     r9d, 8000h; FreeType
0x18000bb6c  lea     r8, [rbp+RegionSize]; RegionSize
0x18000bb70  lea     rdx, [rbp+BaseAddress]; BaseAddress
0x18000bb74  mov     rcx, r14; ProcessHandle
0x18000bb77  call    cs:__imp_ZwFreeVirtualMemory
0x18000bb7e  nop     dword ptr [rax+rax+00h]
0x18000bb83  jmp     short loc_18000BBAA
0x18000bb85  mov     rcx, [rbp+BaseAddress]; unsigned __int8 *
0x18000bb89  mov     edx, esi
0x18000bb8b  call    KsecRemoveValidAddressCommon
0x18000bb90  test    eax, eax
0x18000bb92  jnz     short loc_18000BB52
0x18000bb94  xor     ebx, ebx
0x18000bb96  jmp     short loc_18000BBDE
0x18000bb98  mov     rcx, [rbp+BaseAddress]; P
0x18000bb9c  xor     edx, edx; Tag
0x18000bb9e  call    cs:__imp_ExFreePoolWithTag
0x18000bba5  nop     dword ptr [rax+rax+00h]
0x18000bbaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbb1  lea     rax, WPP_GLOBAL_Control
0x18000bbb8  cmp     rcx, rax
0x18000bbbb  jz      short loc_18000BBD9
0x18000bbbd  mov     eax, [rcx+2Ch]
0x18000bbc0  test    al, 10h
0x18000bbc2  jz      short loc_18000BBD9
0x18000bbc4  mov     rax, [rbp+BaseAddress]
0x18000bbc8  mov     r9d, edi
0x18000bbcb  mov     rcx, [rcx+18h]
0x18000bbcf  mov     [rsp+40h+var_20], rax
0x18000bbd4  call    WPP_SF_dq
0x18000bbd9  mov     ebx, 1
0x18000bbde  lea     rcx, [rbp+var_10]; this
0x18000bbe2  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000bbe7  mov     eax, ebx
0x18000bbe9  mov     rbx, [rsp+40h+arg_0]
0x18000bbee  mov     rsi, [rsp+40h+arg_10]
0x18000bbf3  add     rsp, 40h
0x18000bbf7  pop     r14
0x18000bbf9  pop     rdi
0x18000bbfa  pop     rbp
0x18000bbfb  retn
```
