# HidpFdoUnRegisterWithPoFx

- ea: `0x180017d98`
- end: `0x180017e73`
- name: `HidpFdoUnRegisterWithPoFx`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003b444`

## callees

- `0x18000ff44`
- `0x180017d98`

## import_xrefs

- `ntoskrnl!PoFxUnregisterDevice` at `0x180017e55`
- `ntoskrnl!PoFxUnregisterDevice` at `0x180017e55`
- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x180017e42`
- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x180017e42`

## pseudocode

```c
__int64 __fastcall HidpFdoUnRegisterWithPoFx(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 696) )
  {
    v4 = 1;
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 2184), 1, 0) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        LOBYTE(v4) = 0;
      }
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          v4,
          a3,
          *(_QWORD *)(a1 + 672),
          4,
          9,
          53,
          (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
          *(_QWORD *)a1);
      PoFxCompleteDevicePowerNotRequired(*(_QWORD *)(a1 + 696), v4, a3);
    }
    result = PoFxUnregisterDevice(*(_QWORD *)(a1 + 696));
    *(_QWORD *)(a1 + 696) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180017d98  push    rbx
0x180017d9a  sub     rsp, 50h
0x180017d9e  cmp     qword ptr [rcx+2B8h], 0
0x180017da6  mov     rbx, rcx
0x180017da9  jz      loc_180017E6C
0x180017daf  mov     edx, 1
0x180017db4  xor     eax, eax
0x180017db6  lock cmpxchg [rcx+888h], edx
0x180017dbe  jz      loc_180017E4E
0x180017dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180017dcb  lea     rax, WPP_GLOBAL_Control
0x180017dd2  cmp     rcx, rax
0x180017dd5  jz      short loc_180017DE6
0x180017dd7  test    dword ptr [rcx+2Ch], 100h
0x180017dde  jz      short loc_180017DE6
0x180017de0  cmp     byte ptr [rcx+29h], 4
0x180017de4  jnb     short loc_180017DE8
0x180017de6  xor     dl, dl
0x180017de8  lea     rax, WPP_RECORDER_INITIALIZED
0x180017def  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180017df6  setnz   r8b
0x180017dfa  test    dl, dl
0x180017dfc  jnz     short loc_180017E03
0x180017dfe  test    r8b, r8b
0x180017e01  jz      short loc_180017E3B
0x180017e03  mov     rax, [rbx]
0x180017e06  mov     r9, [rbx+2A0h]
0x180017e0d  mov     rcx, [rcx+18h]
0x180017e11  mov     [rsp+58h+var_18], rax
0x180017e16  lea     rax, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x180017e1d  mov     [rsp+58h+var_20], rax
0x180017e22  mov     [rsp+58h+var_28], 35h ; '5'
0x180017e29  mov     [rsp+58h+var_30], 9
0x180017e31  mov     [rsp+58h+var_38], 4
0x180017e36  call    WPP_RECORDER_AND_TRACE_SF_q
0x180017e3b  mov     rcx, [rbx+2B8h]
0x180017e42  call    cs:__imp_PoFxCompleteDevicePowerNotRequired
0x180017e49  nop     dword ptr [rax+rax+00h]
0x180017e4e  mov     rcx, [rbx+2B8h]
0x180017e55  call    cs:__imp_PoFxUnregisterDevice
0x180017e5c  nop     dword ptr [rax+rax+00h]
0x180017e61  mov     qword ptr [rbx+2B8h], 0
0x180017e6c  add     rsp, 50h
0x180017e70  pop     rbx
0x180017e71  retn
```
