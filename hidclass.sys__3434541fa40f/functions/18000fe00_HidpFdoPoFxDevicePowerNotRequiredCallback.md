# HidpFdoPoFxDevicePowerNotRequiredCallback

- ea: `0x18000fe00`
- end: `0x18000ff3e`
- name: `HidpFdoPoFxDevicePowerNotRequiredCallback`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000fe00`
- `0x18000ff44`
- `0x180010830`

## import_xrefs

- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x18000ff2d`
- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x18000ff2d`

## pseudocode

```c
void __fastcall HidpFdoPoFxDevicePowerNotRequiredCallback(volatile signed __int32 *a1, __int64 a2, __int64 a3)
{
  char v4; // di

  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      *((_QWORD *)a1 + 84),
      4,
      9,
      31,
      (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
      *(_QWORD *)a1);
  }
  if ( _InterlockedCompareExchange(a1 + 546, 1, 0) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v4 = 0;
    }
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = v4;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        a2,
        a3,
        *((_QWORD *)a1 + 84),
        4,
        9,
        32,
        (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
        *(_QWORD *)a1);
    }
    PoFxCompleteDevicePowerNotRequired(*((_QWORD *)a1 + 87), a2, a3);
  }
  else
  {
    HIDSM_AddEvent((KSPIN_LOCK *)a1 + 88, 2019);
  }
}

```

## disassembly

```asm
0x18000fe00  push    rbx
0x18000fe02  push    rbp
0x18000fe03  push    rdi
0x18000fe04  push    r12
0x18000fe06  push    r14
0x18000fe08  sub     rsp, 50h
0x18000fe0c  mov     rbx, rcx
0x18000fe0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe16  lea     rbp, WPP_GLOBAL_Control
0x18000fe1d  mov     edi, 1
0x18000fe22  cmp     rcx, rbp
0x18000fe25  jz      short loc_18000FE30
0x18000fe27  test    dword ptr [rcx+2Ch], 100h
0x18000fe2e  jnz     short loc_18000FEAA
0x18000fe30  xor     dl, dl
0x18000fe32  lea     r14, WPP_RECORDER_INITIALIZED
0x18000fe39  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000fe40  lea     r12, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x18000fe47  setnz   r8b
0x18000fe4b  test    dl, dl
0x18000fe4d  jz      short loc_18000FEB8
0x18000fe4f  mov     rax, [rbx]
0x18000fe52  mov     r9, [rbx+2A0h]
0x18000fe59  mov     rcx, [rcx+18h]
0x18000fe5d  mov     [rsp+78h+var_38], rax
0x18000fe62  mov     [rsp+78h+var_40], r12
0x18000fe67  mov     [rsp+78h+var_48], 1Fh
0x18000fe6e  mov     [rsp+78h+var_50], 9
0x18000fe76  mov     [rsp+78h+var_58], 4
0x18000fe7b  call    WPP_RECORDER_AND_TRACE_SF_q
0x18000fe80  xor     eax, eax
0x18000fe82  lock cmpxchg [rbx+888h], edi
0x18000fe8a  jnz     short loc_18000FEBF
0x18000fe8c  lea     rcx, [rbx+2C0h]; Context
0x18000fe93  mov     edx, 7E3h
0x18000fe98  call    HIDSM_AddEvent
0x18000fe9d  add     rsp, 50h
0x18000fea1  pop     r14
0x18000fea3  pop     r12
0x18000fea5  pop     rdi
0x18000fea6  pop     rbp
0x18000fea7  pop     rbx
0x18000fea8  retn
0x18000feaa  cmp     byte ptr [rcx+29h], 4
0x18000feae  jb      short loc_18000FE30
0x18000feb0  mov     dl, dil
0x18000feb3  jmp     loc_18000FE32
0x18000feb8  test    r8b, r8b
0x18000febb  jz      short loc_18000FE80
0x18000febd  jmp     short loc_18000FE4F
0x18000febf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fec6  cmp     rcx, rbp
0x18000fec9  jz      short loc_18000FEDA
0x18000fecb  test    dword ptr [rcx+2Ch], 100h
0x18000fed2  jz      short loc_18000FEDA
0x18000fed4  cmp     byte ptr [rcx+29h], 4
0x18000fed8  jnb     short loc_18000FEDD
0x18000feda  xor     dil, dil
0x18000fedd  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000fee4  setnz   r8b
0x18000fee8  test    dil, dil
0x18000feeb  jnz     short loc_18000FEF2
0x18000feed  test    r8b, r8b
0x18000fef0  jz      short loc_18000FF26
0x18000fef2  mov     rax, [rbx]
0x18000fef5  mov     dl, dil
0x18000fef8  mov     r9, [rbx+2A0h]
0x18000feff  mov     rcx, [rcx+18h]
0x18000ff03  mov     [rsp+78h+var_38], rax
0x18000ff08  mov     [rsp+78h+var_40], r12
0x18000ff0d  mov     [rsp+78h+var_48], 20h ; ' '
0x18000ff14  mov     [rsp+78h+var_50], 9
0x18000ff1c  mov     [rsp+78h+var_58], 4
0x18000ff21  call    WPP_RECORDER_AND_TRACE_SF_q
0x18000ff26  mov     rcx, [rbx+2B8h]
0x18000ff2d  call    cs:__imp_PoFxCompleteDevicePowerNotRequired
0x18000ff34  nop     dword ptr [rax+rax+00h]
0x18000ff39  jmp     loc_18000FE9D
```
