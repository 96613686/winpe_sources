# KspReleaseDeviceBagEntry

- ea: `0x18005799c`
- end: `0x180057ae0`
- name: `KspReleaseDeviceBagEntry`
- size: `324`
- prototype: `__int64 __fastcall(__int64, _DWORD *, char)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18004efb0`
- `0x180057590`
- `0x180057874`

## callees

- `0x18000a2d4`
- `0x18000b7bc`
- `0x18000dddc`
- `0x180019cb0`
- `0x18005799c`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180057a64`
- `ntoskrnl!KeReleaseMutex` at `0x180057a64`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800579f1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800579f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180057a84`
- `ntoskrnl!ExFreePoolWithTag` at `0x180057a84`

## pseudocode

```c
__int64 __fastcall KspReleaseDeviceBagEntry(__int64 a1, _DWORD *a2, char a3)
{
  _DWORD *v4; // rbx
  int v6; // edx
  unsigned int v7; // edi
  void (__fastcall *v8)(void *); // rax
  void *v9; // rcx
  _QWORD *v10; // rax
  void **v11; // rcx

  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      60,
      (__int64)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids);
  }
  KeWaitForSingleObject((PVOID)(a1 + 16), Executive, 0, 0, 0);
  v7 = v4[8];
  v4[8] = v7 - 1;
  if ( v7 == 1 && a3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v6) = 5;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        1,
        61,
        (__int64)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids,
        *((_QWORD *)v4 + 2));
    }
    v8 = (void (__fastcall *)(void *))*((_QWORD *)v4 + 3);
    v9 = (void *)*((_QWORD *)v4 + 2);
    if ( v8 )
      v8(v9);
    else
      ExFreePoolWithTag(v9, 0);
    v10 = *(_QWORD **)v4;
    if ( *(_DWORD **)(*(_QWORD *)v4 + 8LL) != v4 || (v11 = (void **)*((_QWORD *)v4 + 1), *v11 != v4) )
      __fastfail(3u);
    *v11 = v10;
    v10[1] = v11;
    operator delete(v4);
  }
  KeReleaseMutex((PRKMUTEX)(a1 + 16), 0);
  return v7;
}

```

## disassembly

```asm
0x18005799c  push    rbx
0x18005799e  push    rbp
0x18005799f  push    rsi
0x1800579a0  push    rdi
0x1800579a1  push    r13
0x1800579a3  push    r14
0x1800579a5  push    r15
0x1800579a7  sub     rsp, 30h
0x1800579ab  mov     sil, r8b
0x1800579ae  mov     rbx, rdx
0x1800579b1  mov     rbp, rcx
0x1800579b4  lea     r15, WPP_RECORDER_INITIALIZED
0x1800579bb  xor     r14d, r14d
0x1800579be  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800579c5  lea     r13, WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids
0x1800579cc  jz      short loc_1800579E0
0x1800579ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800579d5  cmp     [rcx+48h], r14w
0x1800579da  jnz     loc_180057A99
0x1800579e0  xor     r9d, r9d; Alertable
0x1800579e3  mov     [rsp+68h+Timeout], r14; Timeout
0x1800579e8  xor     r8d, r8d; WaitMode
0x1800579eb  lea     rcx, [rbp+10h]; Object
0x1800579ef  xor     edx, edx; WaitReason
0x1800579f1  call    cs:__imp_KeWaitForSingleObject
0x1800579f8  nop     dword ptr [rax+rax+00h]
0x1800579fd  mov     edi, [rbx+20h]
0x180057a00  lea     eax, [rdi-1]
0x180057a03  mov     [rbx+20h], eax
0x180057a06  cmp     edi, 1
0x180057a09  jnz     short loc_180057A5E
0x180057a0b  test    sil, sil
0x180057a0e  jz      short loc_180057A5E
0x180057a10  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180057a17  jz      short loc_180057A2B
0x180057a19  mov     rcx, cs:WPP_GLOBAL_Control
0x180057a20  cmp     [rcx+48h], r14w
0x180057a25  jnz     loc_180057AB8
0x180057a2b  mov     rax, [rbx+18h]
0x180057a2f  mov     rcx, [rbx+10h]; P
0x180057a33  test    rax, rax
0x180057a36  jz      short loc_180057A82
0x180057a38  call    _guard_dispatch_icall
0x180057a3d  mov     rax, [rbx]
0x180057a40  cmp     [rax+8], rbx
0x180057a44  jnz     short loc_180057A92
0x180057a46  mov     rcx, [rbx+8]
0x180057a4a  cmp     [rcx], rbx
0x180057a4d  jnz     short loc_180057A92
0x180057a4f  mov     [rcx], rax
0x180057a52  mov     [rax+8], rcx
0x180057a56  mov     rcx, rbx; void *
0x180057a59  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180057a5e  xor     edx, edx; Wait
0x180057a60  lea     rcx, [rbp+10h]; Mutex
0x180057a64  call    cs:__imp_KeReleaseMutex
0x180057a6b  nop     dword ptr [rax+rax+00h]
0x180057a70  mov     eax, edi
0x180057a72  add     rsp, 30h
0x180057a76  pop     r15
0x180057a78  pop     r14
0x180057a7a  pop     r13
0x180057a7c  pop     rdi
0x180057a7d  pop     rsi
0x180057a7e  pop     rbp
0x180057a7f  pop     rbx
0x180057a80  retn
0x180057a82  xor     edx, edx; Tag
0x180057a84  call    cs:__imp_ExFreePoolWithTag
0x180057a8b  nop     dword ptr [rax+rax+00h]
0x180057a90  jmp     short loc_180057A3D
0x180057a92  mov     ecx, 3
0x180057a97  int     29h; Win8: RtlFailFast(ecx)
0x180057a99  mov     rcx, [rcx+40h]
0x180057a9d  mov     r9d, 3Ch ; '<'
0x180057aa3  mov     dl, 5
0x180057aa5  mov     [rsp+68h+Timeout], r13
0x180057aaa  lea     r8d, [r9-3Bh]
0x180057aae  call    WPP_RECORDER_SF_
0x180057ab3  jmp     loc_1800579E0
0x180057ab8  mov     rax, [rbx+10h]
0x180057abc  mov     r9d, 3Dh ; '='
0x180057ac2  mov     rcx, [rcx+40h]
0x180057ac6  mov     dl, 5
0x180057ac8  mov     [rsp+68h+var_40], rax
0x180057acd  mov     [rsp+68h+Timeout], r13
0x180057ad2  lea     r8d, [r9-3Ch]
0x180057ad6  call    WPP_RECORDER_SF_q
0x180057adb  jmp     loc_180057A2B
```
