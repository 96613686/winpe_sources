# TdiDeleteDevice

- ea: `0x140008460`
- end: `0x14000858d`
- name: `TdiDeleteDevice`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140003bf4`
- `0x140004a68`
- `0x140008460`
- `0x14001fd40`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x14000854d`
- `ntoskrnl!IoDeleteDevice` at `0x14000854d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400084b6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400084b6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400084d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400084d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008506`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008506`
- `TDI!TdiDeregisterDeviceObject` at `0x14000853d`
- `TDI!TdiDeregisterDeviceObject` at `0x14000853d`

## pseudocode

```c
void __fastcall TdiDeleteDevice(__int64 a1, int a2)
{
  __int64 v3; // rbx
  KIRQL v4; // al
  __int64 v5; // rbx
  void *v6; // rcx
  int v7; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      32,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      *(_QWORD *)(a1 + 40));
  v3 = *(_QWORD *)(a1 + 56);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v3);
  *(_QWORD *)(v3 + 16) = 0;
  *(_BYTE *)(v3 + 8) = v4;
  KeReleaseSpinLock((PKSPIN_LOCK)v3, v4);
  v5 = 0;
  *(_BYTE *)(a1 + 105) = 0;
  do
  {
    if ( *(_BYTE *)(a1 + 16 * (v5 + 7)) )
    {
      v6 = *(void **)(a1 + 16 * v5 + 120);
      if ( v6 )
      {
        ExFreePoolWithTag(v6, 0x6C687442u);
        *(_QWORD *)(a1 + 16 * v5 + 120) = 0;
      }
      *(_BYTE *)(a1 + 16 * (v5 + 7)) = 0;
    }
    ++v5;
  }
  while ( v5 != 32 );
  memset((void *)(a1 + 112), 0, 0x200u);
  TdiDeregisterDeviceObject(*(HANDLE *)(a1 + 48));
  IoDeleteDevice(*(PDEVICE_OBJECT *)(a1 + 40));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      15,
      33,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
}

```

## disassembly

```asm
0x140008460  push    rbx
0x140008462  push    rbp
0x140008463  push    rsi
0x140008464  push    rdi
0x140008465  push    r13
0x140008467  push    r15
0x140008469  sub     rsp, 38h
0x14000846d  mov     rdi, rcx
0x140008470  lea     r15, WPP_RECORDER_INITIALIZED
0x140008477  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000847e  lea     r13, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140008485  jz      short loc_1400084AF
0x140008487  mov     rax, [rcx+28h]
0x14000848b  mov     r9d, 20h ; ' '
0x140008491  mov     rcx, cs:WPP_GLOBAL_Control
0x140008498  mov     [rsp+68h+var_40], rax
0x14000849d  mov     [rsp+68h+var_48], r13
0x1400084a2  lea     r8d, [r9-11h]
0x1400084a6  mov     rcx, [rcx+40h]
0x1400084aa  call    WPP_RECORDER_SF_q
0x1400084af  mov     rbx, [rdi+38h]
0x1400084b3  mov     rcx, rbx; SpinLock
0x1400084b6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400084bd  nop     dword ptr [rax+rax+00h]
0x1400084c2  mov     rcx, rbx; SpinLock
0x1400084c5  mov     qword ptr [rbx+10h], 0
0x1400084cd  mov     dl, al; NewIrql
0x1400084cf  mov     [rbx+8], al
0x1400084d2  call    cs:__imp_KeReleaseSpinLock
0x1400084d9  nop     dword ptr [rax+rax+00h]
0x1400084de  xor     ebx, ebx
0x1400084e0  mov     byte ptr [rdi+69h], 0
0x1400084e4  lea     rsi, [rbx+7]
0x1400084e8  add     rsi, rsi
0x1400084eb  cmp     byte ptr [rdi+rsi*8], 0
0x1400084ef  jz      short loc_14000851F
0x1400084f1  mov     rbp, rbx
0x1400084f4  add     rbp, rbp
0x1400084f7  mov     rcx, [rdi+rbp*8+78h]; P
0x1400084fc  test    rcx, rcx
0x1400084ff  jz      short loc_14000851B
0x140008501  mov     edx, 6C687442h; Tag
0x140008506  call    cs:__imp_ExFreePoolWithTag
0x14000850d  nop     dword ptr [rax+rax+00h]
0x140008512  mov     qword ptr [rdi+rbp*8+78h], 0
0x14000851b  mov     byte ptr [rdi+rsi*8], 0
0x14000851f  inc     rbx
0x140008522  cmp     rbx, 20h ; ' '
0x140008526  jnz     short loc_1400084E4
0x140008528  lea     rcx, [rdi+70h]; void *
0x14000852c  xor     edx, edx; Val
0x14000852e  mov     r8d, 200h; Size
0x140008534  call    memset
0x140008539  mov     rcx, [rdi+30h]; RegistrationHandle
0x14000853d  call    cs:__imp_TdiDeregisterDeviceObject
0x140008544  nop     dword ptr [rax+rax+00h]
0x140008549  mov     rcx, [rdi+28h]; DeviceObject
0x14000854d  call    cs:__imp_IoDeleteDevice
0x140008554  nop     dword ptr [rax+rax+00h]
0x140008559  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140008560  jz      short loc_14000857F
0x140008562  mov     rcx, cs:WPP_GLOBAL_Control
0x140008569  lea     r9d, [rbx+1]
0x14000856d  lea     r8d, [rbx-11h]
0x140008571  mov     [rsp+68h+var_48], r13
0x140008576  mov     rcx, [rcx+40h]
0x14000857a  call    WPP_RECORDER_SF_
0x14000857f  add     rsp, 38h
0x140008583  pop     r15
0x140008585  pop     r13
0x140008587  pop     rdi
0x140008588  pop     rsi
0x140008589  pop     rbp
0x14000858a  pop     rbx
0x14000858b  retn
```
