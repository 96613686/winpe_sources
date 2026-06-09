# HidpFdoCancelPdoDevicePresenceNotifications

- ea: `0x18001be48`
- end: `0x18001bff8`
- name: `HidpFdoCancelPdoDevicePresenceNotifications`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003e5b0`

## callees

- `0x18000a15c`
- `0x18001be48`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18001bfd6`
- `ntoskrnl!IofCompleteRequest` at `0x18001bfd6`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001befa`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001befa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001be6b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001be6b`

## pseudocode

```c
__int64 __fastcall HidpFdoCancelPdoDevicePresenceNotifications(_QWORD *a1, __int64 a2)
{
  KSPIN_LOCK *v2; // rbx
  KIRQL v5; // r11
  _QWORD *v6; // r8
  __int64 v7; // rcx
  _QWORD *v8; // rax
  _QWORD *v9; // r9
  _QWORD *v10; // rdx
  int v11; // r8d
  __int64 result; // rax
  __int64 v13; // rcx
  __int128 *v14; // rdx
  IRP *v15; // rbx
  __int128 v16; // [rsp+60h] [rbp-18h] BYREF

  v2 = a1 + 243;
  v16 = 0;
  v5 = KeAcquireSpinLockRaiseToDpc(a1 + 243);
  v6 = (_QWORD *)a1[245];
  *((_QWORD *)&v16 + 1) = &v16;
  *(_QWORD *)&v16 = &v16;
  while ( v6 != a1 + 245 )
  {
    if ( *(v6 - 6) == a2 )
    {
      v7 = *v6;
      if ( *(_QWORD **)(*v6 + 8LL) != v6
        || (v8 = (_QWORD *)v6[1], (_QWORD *)*v8 != v6)
        || (*v8 = v7, *(_QWORD *)(v7 + 8) = v8, v9 = (_QWORD *)*((_QWORD *)&v16 + 1), **((__int128 ***)&v16 + 1) != &v16) )
      {
LABEL_22:
        __fastfail(3u);
      }
      v6[1] = *((_QWORD *)&v16 + 1);
      *v6 = &v16;
      v10 = v6;
      *v9 = v6;
      *((_QWORD *)&v16 + 1) = v6;
      v6 = v8;
      _InterlockedExchange64(v10 - 8, 0);
    }
    v6 = (_QWORD *)*v6;
  }
  KeReleaseSpinLock(v2, v5);
  while ( 1 )
  {
    result = v16;
    if ( (__int128 *)v16 == &v16 )
      return result;
    if ( *(__int128 **)(v16 + 8) != &v16 )
      goto LABEL_22;
    v13 = *(_QWORD *)v16;
    if ( *(_QWORD *)(*(_QWORD *)v16 + 8LL) != (_QWORD)v16 )
      goto LABEL_22;
    *(_QWORD *)&v16 = *(_QWORD *)v16;
    v14 = &v16;
    v15 = (IRP *)(result - 168);
    *(_QWORD *)(v13 + 8) = &v16;
    *(_DWORD *)(result - 168 + 48) = -1073741536;
    LOBYTE(v14) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v14,
        v11,
        a1[84],
        4,
        12,
        10,
        (__int64)WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids,
        *a1,
        result + 88,
        32);
    }
    IofCompleteRequest(v15, 0);
  }
}

```

## disassembly

```asm
0x18001be48  push    rbp
0x18001be4a  push    rbx
0x18001be4b  push    rsi
0x18001be4c  push    rdi
0x18001be4d  mov     rbp, rsp
0x18001be50  sub     rsp, 78h
0x18001be54  lea     rbx, [rcx+798h]
0x18001be5b  mov     rsi, rcx
0x18001be5e  xorps   xmm0, xmm0
0x18001be61  mov     rcx, rbx; SpinLock
0x18001be64  mov     rdi, rdx
0x18001be67  movups  [rbp+var_18], xmm0
0x18001be6b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18001be72  nop     dword ptr [rax+rax+00h]
0x18001be77  mov     r11b, al
0x18001be7a  lea     r10, [rsi+7A8h]
0x18001be81  mov     r8, [r10]
0x18001be84  lea     rax, [rbp+var_18]
0x18001be88  mov     qword ptr [rbp+var_18+8], rax
0x18001be8c  lea     rax, [rbp+var_18]
0x18001be90  mov     qword ptr [rbp+var_18], rax
0x18001be94  jmp     short loc_18001BEEF
0x18001be96  cmp     [r8-30h], rdi
0x18001be9a  jnz     short loc_18001BEEC
0x18001be9c  mov     rcx, [r8]
0x18001be9f  cmp     [rcx+8], r8
0x18001bea3  jnz     loc_18001BFE7
0x18001bea9  mov     rax, [r8+8]
0x18001bead  cmp     [rax], r8
0x18001beb0  jnz     loc_18001BFE7
0x18001beb6  mov     [rax], rcx
0x18001beb9  mov     [rcx+8], rax
0x18001bebd  lea     rcx, [rbp+var_18]
0x18001bec1  mov     r9, qword ptr [rbp+var_18+8]
0x18001bec5  cmp     [r9], rcx
0x18001bec8  jnz     loc_18001BFE7
0x18001bece  mov     [r8+8], r9
0x18001bed2  lea     rcx, [rbp+var_18]
0x18001bed6  mov     [r8], rcx
0x18001bed9  mov     rdx, r8
0x18001bedc  mov     [r9], r8
0x18001bedf  mov     qword ptr [rbp+var_18+8], r8
0x18001bee3  mov     r8, rax
0x18001bee6  xor     eax, eax
0x18001bee8  xchg    rax, [rdx-40h]
0x18001beec  mov     r8, [r8]
0x18001beef  cmp     r8, r10
0x18001bef2  jnz     short loc_18001BE96
0x18001bef4  mov     dl, r11b; NewIrql
0x18001bef7  mov     rcx, rbx; SpinLock
0x18001befa  call    cs:__imp_KeReleaseSpinLock
0x18001bf01  nop     dword ptr [rax+rax+00h]
0x18001bf06  mov     edi, 0C0000120h
0x18001bf0b  mov     rax, qword ptr [rbp+var_18]
0x18001bf0f  lea     rcx, [rbp+var_18]
0x18001bf13  cmp     rax, rcx
0x18001bf16  jz      loc_18001BFEE
0x18001bf1c  lea     rcx, [rbp+var_18]
0x18001bf20  cmp     [rax+8], rcx
0x18001bf24  jnz     loc_18001BFE7
0x18001bf2a  mov     rcx, [rax]
0x18001bf2d  cmp     [rcx+8], rax
0x18001bf31  jnz     loc_18001BFE7
0x18001bf37  mov     qword ptr [rbp+var_18], rcx
0x18001bf3b  lea     rdx, [rbp+var_18]
0x18001bf3f  lea     rbx, [rax-0A8h]
0x18001bf46  mov     [rcx+8], rdx
0x18001bf4a  mov     [rbx+30h], edi
0x18001bf4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf54  lea     rax, WPP_GLOBAL_Control
0x18001bf5b  cmp     rcx, rax
0x18001bf5e  jz      short loc_18001BF73
0x18001bf60  test    dword ptr [rcx+2Ch], 800h
0x18001bf67  jz      short loc_18001BF73
0x18001bf69  cmp     byte ptr [rcx+29h], 4
0x18001bf6d  jb      short loc_18001BF73
0x18001bf6f  mov     dl, 1
0x18001bf71  jmp     short loc_18001BF75
0x18001bf73  xor     dl, dl
0x18001bf75  lea     rax, WPP_RECORDER_INITIALIZED
0x18001bf7c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001bf83  setnz   r8b
0x18001bf87  test    dl, dl
0x18001bf89  jnz     short loc_18001BF90
0x18001bf8b  test    r8b, r8b
0x18001bf8e  jz      short loc_18001BFD1
0x18001bf90  mov     rax, [rsi]
0x18001bf93  mov     r9, [rsi+2A0h]
0x18001bf9a  mov     rcx, [rcx+18h]
0x18001bf9e  mov     [rsp+78h+var_28], edi
0x18001bfa2  mov     [rsp+78h+var_30], rbx
0x18001bfa7  mov     [rsp+78h+var_38], rax
0x18001bfac  lea     rax, WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids
0x18001bfb3  mov     [rsp+78h+var_40], rax
0x18001bfb8  mov     [rsp+78h+var_48], 0Ah
0x18001bfbf  mov     [rsp+78h+var_50], 0Ch
0x18001bfc7  mov     [rsp+78h+var_58], 4
0x18001bfcc  call    WPP_RECORDER_AND_TRACE_SF_qqd
0x18001bfd1  xor     edx, edx; PriorityBoost
0x18001bfd3  mov     rcx, rbx; Irp
0x18001bfd6  call    cs:__imp_IofCompleteRequest
0x18001bfdd  nop     dword ptr [rax+rax+00h]
0x18001bfe2  jmp     loc_18001BF0B
0x18001bfe7  mov     ecx, 3
0x18001bfec  int     29h; Win8: RtlFailFast(ecx)
0x18001bfee  add     rsp, 78h
0x18001bff2  pop     rdi
0x18001bff3  pop     rsi
0x18001bff4  pop     rbx
0x18001bff5  pop     rbp
0x18001bff6  retn
```
