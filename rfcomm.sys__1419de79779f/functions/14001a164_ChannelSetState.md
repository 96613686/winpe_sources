# ChannelSetState

- ea: `0x14001a164`
- end: `0x14001a204`
- name: `ChannelSetState`
- size: `160`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000fc00`
- `0x140011634`
- `0x14001190c`
- `0x140012590`
- `0x14001291c`
- `0x140012c60`
- `0x140014210`
- `0x140018e9c`
- `0x1400197ec`
- `0x140019b64`
- `0x140019cd0`

## callees

- `0x1400105ec`
- `0x140016ebc`
- `0x14001a164`

## pseudocode

```c
__int64 __fastcall ChannelSetState(__int64 a1, int a2)
{
  unsigned int v2; // esi
  const char *v5; // rax
  int v6; // edx
  __int64 v7; // r8

  v2 = *(_DWORD *)(a1 + 48);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    ChannelStateTxt(a2);
    v5 = ChannelStateTxt(v2);
    WPP_RECORDER_SF_qss(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      17,
      33,
      (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
      a1,
      (__int64)v5,
      v7);
  }
  *(_DWORD *)(a1 + 48) = a2;
  if ( a2 == 4 )
  {
    _InterlockedExchange((volatile __int32 *)(a1 + 148), 11);
  }
  else if ( a2 != 6 )
  {
    _InterlockedExchange((volatile __int32 *)(a1 + 148), 0);
  }
  return v2;
}

```

## disassembly

```asm
0x14001a164  mov     [rsp+arg_0], rbx
0x14001a169  mov     [rsp+arg_8], rsi
0x14001a16e  push    rdi
0x14001a16f  sub     rsp, 40h
0x14001a173  mov     esi, [rcx+30h]
0x14001a176  mov     edi, edx
0x14001a178  mov     rbx, rcx
0x14001a17b  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a182  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a189  jz      short loc_14001A1D1
0x14001a18b  mov     ecx, edx
0x14001a18d  call    ChannelStateTxt
0x14001a192  mov     ecx, esi
0x14001a194  mov     r8, rax
0x14001a197  call    ChannelStateTxt
0x14001a19c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a1a3  mov     r9d, 21h ; '!'
0x14001a1a9  mov     [rsp+48h+var_10], r8
0x14001a1ae  mov     [rsp+48h+var_18], rax
0x14001a1b3  lea     rax, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x14001a1ba  mov     [rsp+48h+var_20], rbx
0x14001a1bf  mov     rcx, [rcx+40h]
0x14001a1c3  lea     r8d, [r9-10h]
0x14001a1c7  mov     [rsp+48h+var_28], rax
0x14001a1cc  call    WPP_RECORDER_SF_qss
0x14001a1d1  mov     [rbx+30h], edi
0x14001a1d4  cmp     edi, 4
0x14001a1d7  jnz     short loc_14001A1E4
0x14001a1d9  lea     eax, [rdi+7]
0x14001a1dc  xchg    eax, [rbx+94h]
0x14001a1e2  jmp     short loc_14001A1F1
0x14001a1e4  cmp     edi, 6
0x14001a1e7  jz      short loc_14001A1F1
0x14001a1e9  xor     ecx, ecx
0x14001a1eb  xchg    ecx, [rbx+94h]
0x14001a1f1  mov     rbx, [rsp+48h+arg_0]
0x14001a1f6  mov     eax, esi
0x14001a1f8  mov     rsi, [rsp+48h+arg_8]
0x14001a1fd  add     rsp, 40h
0x14001a201  pop     rdi
0x14001a202  retn
```
