# CKsNotification::s_WnfTriggerCheckCAMAccess(void)

- ea: `0x180045b78`
- end: `0x180045c94`
- name: `?s_WnfTriggerCheckCAMAccess@CKsNotification@@KAJXZ`
- size: `284`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180045b60`

## callees

- `0x18000c630`
- `0x180019cb0`
- `0x180045b78`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180045c34`
- `ntoskrnl!KeReleaseMutex` at `0x180045c34`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180045c7f`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180045c7f`
- `ntoskrnl!KeWaitForSingleObject` at `0x180045b9a`
- `ntoskrnl!KeWaitForSingleObject` at `0x180045b9a`
- `HAL!KeQueryPerformanceCounter` at `0x180045c42`
- `HAL!KeQueryPerformanceCounter` at `0x180045c42`

## pseudocode

```c
__int64 CKsNotification::s_WnfTriggerCheckCAMAccess(void)
{
  __int64 v0; // rcx
  __int64 *i; // rbx
  __int64 v2; // rax
  int v3; // eax
  int v4; // edx
  __int64 v6; // [rsp+28h] [rbp-20h]
  LARGE_INTEGER PerformanceCounter; // [rsp+50h] [rbp+8h] BYREF

  KeWaitForSingleObject((PVOID)(*((_QWORD *)&WPP_MAIN_CB.Reserved + 1) + 16LL), Executive, 0, 0, 0);
  v0 = *((_QWORD *)&WPP_MAIN_CB.Reserved + 1);
  for ( i = *(__int64 **)(*((_QWORD *)&WPP_MAIN_CB.Reserved + 1) + 120LL);
        i && i != (__int64 *)(v0 + 120);
        i = (__int64 *)*i )
  {
    v2 = i[3];
    if ( *(_BYTE *)(v2 + 80) != 1 && *((_DWORD *)i + 26) )
    {
      v3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 72) + 136LL))(*(_QWORD *)(v2 - 72));
      if ( v3 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v6) = v3;
        LOBYTE(v4) = 2;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v4,
          1,
          53,
          (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids,
          v6);
      }
      v0 = *((_QWORD *)&WPP_MAIN_CB.Reserved + 1);
    }
  }
  KeReleaseMutex((PRKMUTEX)(v0 + 16), 0);
  PerformanceCounter = KeQueryPerformanceCounter(0);
  ZwUpdateWnfStateData(&WNF_KSV_DEVICESTATE, &PerformanceCounter, 8);
  return 0;
}

```

## disassembly

```asm
0x180045b78  push    rbx
0x180045b7a  sub     rsp, 40h
0x180045b7e  mov     rcx, qword ptr cs:WPP_MAIN_CB+148h
0x180045b85  xor     r9d, r9d; Alertable
0x180045b88  add     rcx, 10h; Object
0x180045b8c  mov     [rsp+48h+Timeout], 0; Timeout
0x180045b95  xor     r8d, r8d; WaitMode
0x180045b98  xor     edx, edx; WaitReason
0x180045b9a  call    cs:__imp_KeWaitForSingleObject
0x180045ba1  nop     dword ptr [rax+rax+00h]
0x180045ba6  mov     rcx, qword ptr cs:WPP_MAIN_CB+148h
0x180045bad  mov     rbx, [rcx+78h]
0x180045bb1  jmp     short loc_180045C29
0x180045bb3  lea     rax, [rcx+78h]
0x180045bb7  cmp     rbx, rax
0x180045bba  jz      short loc_180045C2E
0x180045bbc  mov     rax, [rbx+18h]
0x180045bc0  cmp     byte ptr [rax+50h], 1
0x180045bc4  jz      short loc_180045C26
0x180045bc6  cmp     dword ptr [rbx+68h], 0
0x180045bca  jz      short loc_180045C26
0x180045bcc  mov     rcx, [rax-48h]
0x180045bd0  mov     rax, [rcx]
0x180045bd3  mov     rax, [rax+88h]
0x180045bda  call    _guard_dispatch_icall
0x180045bdf  test    eax, eax
0x180045be1  jns     short loc_180045C1F
0x180045be3  lea     rcx, WPP_RECORDER_INITIALIZED
0x180045bea  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180045bf1  jz      short loc_180045C1F
0x180045bf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180045bfa  mov     r9d, 35h ; '5'
0x180045c00  mov     dword ptr [rsp+48h+var_20], eax
0x180045c04  mov     dl, 2
0x180045c06  lea     rax, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x180045c0d  mov     [rsp+48h+Timeout], rax
0x180045c12  mov     rcx, [rcx+40h]
0x180045c16  lea     r8d, [r9-34h]
0x180045c1a  call    WPP_RECORDER_SF_D
0x180045c1f  mov     rcx, qword ptr cs:WPP_MAIN_CB+148h
0x180045c26  mov     rbx, [rbx]
0x180045c29  test    rbx, rbx
0x180045c2c  jnz     short loc_180045BB3
0x180045c2e  add     rcx, 10h; Mutex
0x180045c32  xor     edx, edx; Wait
0x180045c34  call    cs:__imp_KeReleaseMutex
0x180045c3b  nop     dword ptr [rax+rax+00h]
0x180045c40  xor     ecx, ecx; PerformanceFrequency
0x180045c42  call    cs:__imp_KeQueryPerformanceCounter
0x180045c49  nop     dword ptr [rax+rax+00h]
0x180045c4e  xor     r9d, r9d
0x180045c51  mov     [rsp+48h+var_18], 0
0x180045c59  mov     dword ptr [rsp+48h+var_20], 0
0x180045c61  lea     rdx, [rsp+48h+arg_0]
0x180045c66  lea     rcx, WNF_KSV_DEVICESTATE
0x180045c6d  mov     [rsp+48h+arg_0], rax
0x180045c72  mov     [rsp+48h+Timeout], 0
0x180045c7b  lea     r8d, [r9+8]
0x180045c7f  call    cs:__imp_ZwUpdateWnfStateData
0x180045c86  nop     dword ptr [rax+rax+00h]
0x180045c8b  xor     eax, eax
0x180045c8d  add     rsp, 40h
0x180045c91  pop     rbx
0x180045c92  retn
```
