# HidpInterruptWriteComplete

- ea: `0x18000ef30`
- end: `0x18000f172`
- name: `HidpInterruptWriteComplete`
- size: `578`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180003f40`
- `0x18000ef30`
- `0x18000f178`
- `0x180010830`
- `0x18001cabc`
- `0x180021bb0`

## import_xrefs

- `ntoskrnl!IoDecrementKeepAliveCount` at `0x18000f102`
- `ntoskrnl!IoDecrementKeepAliveCount` at `0x18000f102`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ef74`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ef74`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000efcd`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000f13d`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000efcd`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000f13d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000ef8f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000ef8f`

## pseudocode

```c
__int64 __fastcall HidpInterruptWriteComplete(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdi
  int v6; // esi
  __int64 v7; // rcx
  __int64 v8; // rbp
  KIRQL v9; // r14
  bool v10; // zf
  __int64 i; // rdx
  __int64 v12; // r8
  __int64 v13; // r10
  unsigned int v14; // r11d
  __int64 v15; // rax
  __int64 result; // rax

  v4 = *(_QWORD *)(a3 + 64);
  v6 = *(_DWORD *)(a2 + 48);
  v7 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 48LL);
  if ( v7 )
  {
    v8 = *(_QWORD *)(v7 + 24);
    if ( *(_QWORD *)(v8 + 136) )
    {
      IoDecrementKeepAliveCount(*(_QWORD *)(v8 + 96));
      _InterlockedDecrement((volatile signed __int32 *)(v8 + 144));
    }
  }
  ExFreePoolWithTag(*(PVOID *)(a2 + 112), 0);
  *(_QWORD *)(a2 + 112) = 0;
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 416));
  if ( *(int *)(v4 + 1892) <= 0 )
    HidpDbgBreak("Invalid InFlightIoCount");
  v10 = (*(_DWORD *)(v4 + 1892))-- == 1;
  if ( v10 && *(_BYTE *)(v4 + 1756) )
  {
    *(_BYTE *)(v4 + 1756) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 416), v9);
    HIDSM_AddEvent((KSPIN_LOCK *)(v4 + 736), 2022);
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 416), v9);
  }
  HidpFdoReleasePoFxPowerReferenceWithTag(v4 + 32, 8);
  if ( v6 >= 0 )
  {
    v13 = *(_QWORD *)(v4 + 192);
    v14 = *(_DWORD *)(a3 + 8);
    if ( v13 )
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)(v4 + 200); i = (unsigned int)(i + 1) )
      {
        v12 = v13 + 40 * i;
        if ( *(unsigned __int8 *)(v12 + 4) == v14 )
        {
          if ( !v12 )
            break;
          v15 = *(unsigned __int16 *)(v12 + 22);
          goto LABEL_16;
        }
      }
    }
    TraceLoggingGetCollectionDescFailed(v4 + 32, v14);
    v15 = 0;
LABEL_16:
    *(_QWORD *)(a2 + 56) = v15;
  }
  LOBYTE(i) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)i || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qdqqdI(WPP_GLOBAL_Control->AttachedDevice, i, v12, *(_QWORD *)(v4 + 704));
  }
  result = (unsigned int)v6;
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  return result;
}

```

## disassembly

```asm
0x18000ef30  push    rbx
0x18000ef32  push    rbp
0x18000ef33  push    rsi
0x18000ef34  push    rdi
0x18000ef35  push    r14
0x18000ef37  push    r15
0x18000ef39  sub     rsp, 78h
0x18000ef3d  mov     rax, [rdx+0B8h]
0x18000ef44  mov     r15, r8
0x18000ef47  mov     rdi, [r8+40h]
0x18000ef4b  mov     rbx, rdx
0x18000ef4e  mov     esi, [rdx+30h]
0x18000ef51  mov     rcx, [rax+30h]
0x18000ef55  test    rcx, rcx
0x18000ef58  jz      short loc_18000EF6E
0x18000ef5a  mov     rbp, [rcx+18h]
0x18000ef5e  mov     rdx, [rbp+88h]
0x18000ef65  test    rdx, rdx
0x18000ef68  jnz     loc_18000F0FE
0x18000ef6e  mov     rcx, [rbx+70h]; P
0x18000ef72  xor     edx, edx; Tag
0x18000ef74  call    cs:__imp_ExFreePoolWithTag
0x18000ef7b  nop     dword ptr [rax+rax+00h]
0x18000ef80  lea     rcx, [rdi+1A0h]; SpinLock
0x18000ef87  mov     qword ptr [rbx+70h], 0
0x18000ef8f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18000ef96  nop     dword ptr [rax+rax+00h]
0x18000ef9b  cmp     dword ptr [rdi+764h], 0
0x18000efa2  movzx   r14d, al
0x18000efa6  jle     loc_18000F11A
0x18000efac  sub     dword ptr [rdi+764h], 1
0x18000efb3  jnz     short loc_18000EFC2
0x18000efb5  cmp     byte ptr [rdi+6DCh], 0
0x18000efbc  jnz     loc_18000F12B
0x18000efc2  movzx   edx, r14b; NewIrql
0x18000efc6  lea     rcx, [rdi+1A0h]; SpinLock
0x18000efcd  call    cs:__imp_KeReleaseSpinLock
0x18000efd4  nop     dword ptr [rax+rax+00h]
0x18000efd9  mov     r8, rbx
0x18000efdc  lea     rcx, [rdi+20h]
0x18000efe0  mov     edx, 8
0x18000efe5  call    HidpFdoReleasePoFxPowerReferenceWithTag
0x18000efea  test    esi, esi
0x18000efec  js      short loc_18000F03D
0x18000efee  mov     r10, [rdi+0C0h]
0x18000eff5  mov     r11d, [r15+8]
0x18000eff9  test    r10, r10
0x18000effc  jz      loc_18000F15F
0x18000f002  mov     r9d, [rdi+0C8h]
0x18000f009  xor     edx, edx
0x18000f00b  cmp     edx, r9d
0x18000f00e  jnb     loc_18000F15F
0x18000f014  lea     rcx, [rdx+rdx*4]
0x18000f018  movzx   eax, byte ptr [r10+rcx*8+4]
0x18000f01e  lea     r8, [r10+rcx*8]
0x18000f022  cmp     eax, r11d
0x18000f025  jnz     loc_18000F0D1
0x18000f02b  test    r8, r8
0x18000f02e  jz      loc_18000F15F
0x18000f034  movzx   eax, word ptr [r8+16h]
0x18000f039  mov     [rbx+38h], rax
0x18000f03d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f044  lea     rax, WPP_GLOBAL_Control
0x18000f04b  cmp     rcx, rax
0x18000f04e  jnz     loc_18000F0D8
0x18000f054  xor     dl, dl
0x18000f056  lea     rax, WPP_RECORDER_INITIALIZED
0x18000f05d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000f064  setnz   r8b
0x18000f068  test    dl, dl
0x18000f06a  jz      loc_18000F0F4
0x18000f070  mov     rax, [rbx+38h]
0x18000f074  mov     r10, [r15+40h]
0x18000f078  mov     r9, [rdi+2C0h]
0x18000f07f  mov     rcx, [rcx+18h]
0x18000f083  mov     [rsp+0A8h+var_40], rax
0x18000f088  mov     rax, [r15+30h]
0x18000f08c  mov     r10, [r10+20h]
0x18000f090  mov     [rsp+0A8h+var_48], esi
0x18000f094  mov     [rsp+0A8h+var_50], rbx
0x18000f099  mov     [rsp+0A8h+var_58], rax
0x18000f09e  mov     eax, [r15+8]
0x18000f0a2  mov     [rsp+0A8h+var_60], eax
0x18000f0a6  mov     [rsp+0A8h+var_68], r10
0x18000f0ab  call    WPP_RECORDER_AND_TRACE_SF_qdqqdI
0x18000f0b0  cmp     byte ptr [rbx+41h], 0
0x18000f0b4  mov     eax, esi
0x18000f0b6  jz      short loc_18000F0C3
0x18000f0b8  mov     rcx, [rbx+0B8h]
0x18000f0bf  or      byte ptr [rcx+3], 1
0x18000f0c3  add     rsp, 78h
0x18000f0c7  pop     r15
0x18000f0c9  pop     r14
0x18000f0cb  pop     rdi
0x18000f0cc  pop     rsi
0x18000f0cd  pop     rbp
0x18000f0ce  pop     rbx
0x18000f0cf  retn
0x18000f0d1  inc     edx
0x18000f0d3  jmp     loc_18000F00B
0x18000f0d8  mov     eax, [rcx+2Ch]
0x18000f0db  test    al, 20h
0x18000f0dd  jz      loc_18000F054
0x18000f0e3  cmp     byte ptr [rcx+29h], 4
0x18000f0e7  jb      loc_18000F054
0x18000f0ed  mov     dl, 1
0x18000f0ef  jmp     loc_18000F056
0x18000f0f4  test    r8b, r8b
0x18000f0f7  jz      short loc_18000F0B0
0x18000f0f9  jmp     loc_18000F070
0x18000f0fe  mov     rcx, [rbp+60h]
0x18000f102  call    cs:__imp_IoDecrementKeepAliveCount
0x18000f109  nop     dword ptr [rax+rax+00h]
0x18000f10e  lock dec dword ptr [rbp+90h]
0x18000f115  jmp     loc_18000EF6E
0x18000f11a  lea     rcx, aInvalidInfligh; "Invalid InFlightIoCount"
0x18000f121  call    HidpDbgBreak
0x18000f126  jmp     loc_18000EFAC
0x18000f12b  movzx   edx, r14b; NewIrql
0x18000f12f  mov     byte ptr [rdi+6DCh], 0
0x18000f136  lea     rcx, [rdi+1A0h]; SpinLock
0x18000f13d  call    cs:__imp_KeReleaseSpinLock
0x18000f144  nop     dword ptr [rax+rax+00h]
0x18000f149  lea     rcx, [rdi+2E0h]; Context
0x18000f150  mov     edx, 7E6h
0x18000f155  call    HIDSM_AddEvent
0x18000f15a  jmp     loc_18000EFD9
0x18000f15f  mov     edx, r11d
0x18000f162  lea     rcx, [rdi+20h]
0x18000f166  call    TraceLoggingGetCollectionDescFailed
0x18000f16b  xor     eax, eax
0x18000f16d  jmp     loc_18000F039
```
