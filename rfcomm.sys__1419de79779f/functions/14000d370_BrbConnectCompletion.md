# BrbConnectCompletion

- ea: `0x14000d370`
- end: `0x14000d4a7`
- name: `BrbConnectCompletion`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003bf4`
- `0x14000d370`
- `0x14000fa84`
- `0x1400174a8`
- `0x140017ab8`
- `0x140017db4`
- `0x14001bfa8`
- `0x14001ea34`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000d39b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d39b`

## string_xrefs

- `0x14000d449`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\brb.c`

## pseudocode

```c
__int64 __fastcall BrbConnectCompletion(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  void *DeviceExtension; // rdi
  int v9; // edx
  int v10; // r8d
  __int64 v11; // r8
  __int64 result; // rax
  int v13; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    KeGetCurrentIrql();
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    NtStatusTxt(a4);
    WPP_RECORDER_SF_sqqd((_DWORD)DeviceExtension, v9, v10, 27);
  }
  if ( a4 || *(_DWORD *)(a2 + 28) )
  {
    v11 = *(unsigned int *)(a2 + 28);
    if ( (int)v11 >= 0 )
      v11 = a4;
    if ( (_DWORD)v11 != -1073741643 )
      v11 = 3221226044LL;
    _InterlockedExchange64((volatile __int64 *)(a3 + 280), 0);
    SessionDisconnectInd(a3, 0, v11);
    if ( *(_DWORD *)(a3 + 48) != 6 )
      SessionDisconnect(a3);
  }
  else
  {
    SessionConnectComplete(a3, a2);
  }
  if ( *(_WORD *)(a2 + 22) != 531 )
    RefObj_ReleaseEx(a3 + 24, 1413697091, 545, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\brb.c");
  result = (*(__int64 (__fastcall **)(__int64))(a1 + 320))(a2);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_(
             WPP_GLOBAL_Control->DeviceExtension,
             v13,
             3,
             28,
             (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids);
  return result;
}

```

## disassembly

```asm
0x14000d370  push    rbx
0x14000d372  push    rbp
0x14000d373  push    rsi
0x14000d374  push    rdi
0x14000d375  push    r12
0x14000d377  push    r14
0x14000d379  push    r15
0x14000d37b  sub     rsp, 50h
0x14000d37f  mov     r14d, r9d
0x14000d382  mov     rbp, r8
0x14000d385  mov     rsi, rdx
0x14000d388  mov     r15, rcx
0x14000d38b  lea     r12, WPP_RECORDER_INITIALIZED
0x14000d392  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000d399  jz      short loc_14000D3DE
0x14000d39b  call    cs:__imp_KeGetCurrentIrql
0x14000d3a2  nop     dword ptr [rax+rax+00h]
0x14000d3a7  movzx   ebx, al
0x14000d3aa  mov     ecx, r14d
0x14000d3ad  mov     rax, cs:WPP_GLOBAL_Control
0x14000d3b4  mov     rdi, [rax+40h]
0x14000d3b8  call    NtStatusTxt
0x14000d3bd  mov     [rsp+88h+var_48], ebx
0x14000d3c1  mov     r9d, 1Bh
0x14000d3c7  mov     [rsp+88h+var_50], rsi
0x14000d3cc  mov     rcx, rdi
0x14000d3cf  mov     [rsp+88h+var_58], rbp
0x14000d3d4  mov     [rsp+88h+var_60], rax
0x14000d3d9  call    WPP_RECORDER_SF_sqqd
0x14000d3de  test    r14d, r14d
0x14000d3e1  jnz     short loc_14000D3F6
0x14000d3e3  cmp     [rsi+1Ch], r14d
0x14000d3e7  jnz     short loc_14000D3F6
0x14000d3e9  mov     rdx, rsi
0x14000d3ec  mov     rcx, rbp
0x14000d3ef  call    SessionConnectComplete
0x14000d3f4  jmp     short loc_14000D435
0x14000d3f6  mov     r8d, [rsi+1Ch]
0x14000d3fa  mov     eax, 0C000023Ch
0x14000d3ff  test    r8d, r8d
0x14000d402  mov     rcx, rbp
0x14000d405  cmovns  r8d, r14d
0x14000d409  cmp     r8d, 0C00000B5h
0x14000d410  cmovnz  r8d, eax
0x14000d414  xor     eax, eax
0x14000d416  xchg    rax, [rbp+118h]
0x14000d41d  xor     r9d, r9d
0x14000d420  xor     edx, edx
0x14000d422  call    SessionDisconnectInd
0x14000d427  cmp     dword ptr [rbp+30h], 6
0x14000d42b  jz      short loc_14000D435
0x14000d42d  mov     rcx, rbp
0x14000d430  call    SessionDisconnect
0x14000d435  mov     eax, 213h
0x14000d43a  cmp     [rsi+16h], ax
0x14000d43e  jz      short loc_14000D459
0x14000d440  lea     rcx, [rbp+18h]
0x14000d444  mov     edx, 54434E43h
0x14000d449  lea     r9, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000d450  lea     r8d, [rax+0Eh]
0x14000d454  call    RefObj_ReleaseEx
0x14000d459  mov     rax, [r15+140h]
0x14000d460  mov     rcx, rsi
0x14000d463  call    _guard_dispatch_icall
0x14000d468  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000d46f  jz      short loc_14000D497
0x14000d471  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d478  lea     rax, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000d47f  mov     r9d, 1Ch
0x14000d485  mov     [rsp+88h+var_68], rax
0x14000d48a  mov     rcx, [rcx+40h]
0x14000d48e  lea     r8d, [r9-19h]
0x14000d492  call    WPP_RECORDER_SF_
0x14000d497  add     rsp, 50h
0x14000d49b  pop     r15
0x14000d49d  pop     r14
0x14000d49f  pop     r12
0x14000d4a1  pop     rdi
0x14000d4a2  pop     rsi
0x14000d4a3  pop     rbp
0x14000d4a4  pop     rbx
0x14000d4a5  retn
```
