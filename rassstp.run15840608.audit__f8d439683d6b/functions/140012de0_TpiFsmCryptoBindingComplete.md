# TpiFsmCryptoBindingComplete

- ea: `0x140012de0`
- end: `0x140012f39`
- name: `TpiFsmCryptoBindingComplete`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400133f0`

## callees

- `0x140002030`
- `0x140002bd8`
- `0x140005e10`
- `0x140006240`
- `0x140012de0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012e3d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012e3d`
- `ntoskrnl!KfRaiseIrql` at `0x140012ea7`
- `ntoskrnl!KfRaiseIrql` at `0x140012ea7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012e59`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012e59`
- `ntoskrnl!KeLowerIrql` at `0x140012eda`
- `ntoskrnl!KeLowerIrql` at `0x140012eda`
- `NDIS!NdisMCoIndicateStatusEx` at `0x140012ecc`
- `NDIS!NdisMCoIndicateStatusEx` at `0x140012ecc`

## pseudocode

```c
__int64 __fastcall TpiFsmCryptoBindingComplete(__int64 a1)
{
  KIRQL v2; // al
  KIRQL v3; // bl
  __int64 result; // rax
  _NDIS_STATUS_INDICATION StatusIndication; // [rsp+20h] [rbp-A8h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  _InterlockedIncrement((volatile signed __int32 *)a1);
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 32));
  *(_BYTE *)(a1 + 506) = 1;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), v2);
  memset(&StatusIndication.Header + 1, 0, 0x6Cu);
  StatusIndication.Header = (NDIS_OBJECT_HEADER)7340440;
  StatusIndication.SourceHandle = (NDIS_HANDLE)*((_QWORD *)SstpGlobals + 21);
  StatusIndication.StatusCode = 1073807378;
  StatusIndication.StatusBuffer = (PVOID)(a1 + 506);
  StatusIndication.StatusBufferSize = 1;
  v3 = KfRaiseIrql(2u);
  NdisMCoIndicateStatusEx(*((NDIS_HANDLE *)SstpGlobals + 21), *(NDIS_HANDLE *)(a1 + 40), &StatusIndication);
  KeLowerIrql(v3);
  result = DereferenceRefCount(a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer) & 0x82;
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 86, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140012de0  push    rbx
0x140012de2  push    rsi
0x140012de3  push    rdi
0x140012de4  push    r14
0x140012de6  sub     rsp, 0A8h
0x140012ded  mov     rax, cs:__security_cookie
0x140012df4  xor     rax, rsp
0x140012df7  mov     [rsp+0C8h+var_38], rax
0x140012dff  mov     rsi, rcx
0x140012e02  mov     rcx, cs:WPP_GLOBAL_Control
0x140012e09  lea     r14, WPP_GLOBAL_Control
0x140012e10  cmp     rcx, r14
0x140012e13  jz      short loc_140012E36
0x140012e15  mov     eax, [rcx+2Ch]
0x140012e18  and     eax, 82h
0x140012e1d  cmp     al, 82h
0x140012e1f  jnz     short loc_140012E36
0x140012e21  mov     rcx, [rcx+18h]
0x140012e25  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140012e2c  mov     edx, 55h ; 'U'
0x140012e31  call    WPP_SF_
0x140012e36  lock inc dword ptr [rsi]
0x140012e39  lea     rcx, [rsi+20h]; SpinLock
0x140012e3d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012e44  nop     dword ptr [rax+rax+00h]
0x140012e49  lea     rdi, [rsi+1FAh]
0x140012e50  mov     dl, al; NewIrql
0x140012e52  lea     rcx, [rsi+20h]; SpinLock
0x140012e56  mov     byte ptr [rdi], 1
0x140012e59  call    cs:__imp_KeReleaseSpinLock
0x140012e60  nop     dword ptr [rax+rax+00h]
0x140012e65  xor     edx, edx; Val
0x140012e67  lea     rcx, [rsp+0C8h+StatusIndication+4]; void *
0x140012e6c  lea     r8d, [rdx+6Ch]; Size
0x140012e70  call    memset
0x140012e75  mov     rax, cs:SstpGlobals
0x140012e7c  mov     cl, 2; NewIrql
0x140012e7e  mov     dword ptr [rsp+0C8h+StatusIndication.Header.Type], 700198h
0x140012e86  mov     rdx, [rax+0A8h]
0x140012e8d  mov     [rsp+0C8h+StatusIndication.SourceHandle], rdx
0x140012e92  mov     [rsp+0C8h+StatusIndication.StatusCode], 40010012h
0x140012e9a  mov     [rsp+0C8h+StatusIndication.StatusBuffer], rdi
0x140012e9f  mov     [rsp+0C8h+StatusIndication.StatusBufferSize], 1
0x140012ea7  call    cs:__imp_KfRaiseIrql
0x140012eae  nop     dword ptr [rax+rax+00h]
0x140012eb3  mov     rcx, cs:SstpGlobals
0x140012eba  lea     r8, [rsp+0C8h+StatusIndication]; StatusIndication
0x140012ebf  mov     rdx, [rsi+28h]; NdisVcHandle
0x140012ec3  mov     bl, al
0x140012ec5  mov     rcx, [rcx+0A8h]; MiniportAdapterHandle
0x140012ecc  call    cs:__imp_NdisMCoIndicateStatusEx
0x140012ed3  nop     dword ptr [rax+rax+00h]
0x140012ed8  mov     cl, bl; NewIrql
0x140012eda  call    cs:__imp_KeLowerIrql
0x140012ee1  nop     dword ptr [rax+rax+00h]
0x140012ee6  mov     rcx, rsi
0x140012ee9  call    DereferenceRefCount
0x140012eee  mov     rcx, cs:WPP_GLOBAL_Control
0x140012ef5  cmp     rcx, r14
0x140012ef8  jz      short loc_140012F1B
0x140012efa  mov     eax, [rcx+2Ch]
0x140012efd  and     eax, 82h
0x140012f02  cmp     al, 82h
0x140012f04  jnz     short loc_140012F1B
0x140012f06  mov     rcx, [rcx+18h]
0x140012f0a  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140012f11  mov     edx, 56h ; 'V'
0x140012f16  call    WPP_SF_
0x140012f1b  mov     rcx, [rsp+0C8h+var_38]
0x140012f23  xor     rcx, rsp; StackCookie
0x140012f26  call    __security_check_cookie
0x140012f2b  add     rsp, 0A8h
0x140012f32  pop     r14
0x140012f34  pop     rdi
0x140012f35  pop     rsi
0x140012f36  pop     rbx
0x140012f37  retn
```
