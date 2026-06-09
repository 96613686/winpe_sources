# BrbpDisconnect

- ea: `0x14000e700`
- end: `0x14000e835`
- name: `BrbpDisconnect`
- size: `309`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400157dc`
- `0x140017db4`

## callees

- `0x140004a68`
- `0x1400051b4`
- `0x14000e094`
- `0x14000e700`
- `0x14001bfa8`
- `0x14001e74c`
- `0x14001fc70`

## string_xrefs

- `0x14000e7a7`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\brb.c`

## pseudocode

```c
__int64 __fastcall BrbpDisconnect(_QWORD *a1)
{
  __int64 v1; // rsi
  unsigned int v3; // edi
  __int64 v4; // r14
  __int64 v5; // r15
  int v6; // edx
  __int64 v7; // rbp
  void *DeviceExtension; // rbx
  const char *v9; // rax
  int v10; // edx

  v1 = a1[35];
  if ( v1 )
  {
    v4 = a1[9];
    v5 = a1[33];
    v7 = (*(__int64 (__fastcall **)(__int64, __int64))(v4 + 312))(260, 1111647826);
    if ( v7 )
    {
      v3 = 259;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          3,
          33,
          (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids,
          v1);
      *(_QWORD *)(v7 + 112) = v5;
      *(_QWORD *)(v7 + 120) = v1;
      RefObj_AddRefEx(a1 + 3, BrbpDisconnect, 734, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\brb.c");
      BrbpCallDriverAsync(
        v4,
        (_DWORD *)v7,
        (void (__fastcall *)(__int64, _DWORD *, __int64))BrbDisconnectCompletion,
        (__int64)a1,
        (__int64)(a1 + 30));
    }
    else
    {
      v3 = -1073741670;
    }
  }
  else
  {
    v3 = -1073741816;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    v9 = NtStatusTxt(v3);
    WPP_RECORDER_SF_s(
      (_DWORD)DeviceExtension,
      v10,
      3,
      34,
      (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids,
      (__int64)v9);
  }
  return v3;
}

```

## disassembly

```asm
0x14000e700  push    rbx
0x14000e702  push    rbp
0x14000e703  push    rsi
0x14000e704  push    rdi
0x14000e705  push    r12
0x14000e707  push    r14
0x14000e709  push    r15
0x14000e70b  sub     rsp, 30h
0x14000e70f  mov     rsi, [rcx+118h]
0x14000e716  lea     r12, WPP_RECORDER_INITIALIZED
0x14000e71d  lea     rbp, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000e724  mov     rbx, rcx
0x14000e727  test    rsi, rsi
0x14000e72a  jnz     short loc_14000E736
0x14000e72c  mov     edi, 0C0000008h
0x14000e731  jmp     loc_14000E7EC
0x14000e736  mov     r14, [rcx+48h]
0x14000e73a  mov     edx, 42426652h
0x14000e73f  mov     r15, [rcx+108h]
0x14000e746  mov     ecx, 104h
0x14000e74b  mov     rax, [r14+138h]
0x14000e752  call    _guard_dispatch_icall
0x14000e757  mov     rbp, rax
0x14000e75a  test    rax, rax
0x14000e75d  jnz     short loc_14000E766
0x14000e75f  mov     edi, 0C000009Ah
0x14000e764  jmp     short loc_14000E7E5
0x14000e766  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000e76d  mov     edi, 103h
0x14000e772  jz      short loc_14000E79F
0x14000e774  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e77b  lea     rax, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000e782  mov     r9d, 21h ; '!'
0x14000e788  mov     [rsp+68h+var_40], rsi
0x14000e78d  mov     [rsp+68h+var_48], rax
0x14000e792  mov     rcx, [rcx+40h]
0x14000e796  lea     r8d, [r9-1Eh]
0x14000e79a  call    WPP_RECORDER_SF_q
0x14000e79f  lea     rcx, [rbx+18h]
0x14000e7a3  mov     [rbp+70h], r15
0x14000e7a7  lea     r9, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000e7ae  mov     [rbp+78h], rsi
0x14000e7b2  mov     r8d, 2DEh
0x14000e7b8  lea     rdx, BrbpDisconnect
0x14000e7bf  call    RefObj_AddRefEx
0x14000e7c4  lea     rax, [rbx+0F0h]
0x14000e7cb  mov     r9, rbx
0x14000e7ce  lea     r8, BrbDisconnectCompletion
0x14000e7d5  mov     [rsp+68h+var_48], rax
0x14000e7da  mov     rdx, rbp
0x14000e7dd  mov     rcx, r14
0x14000e7e0  call    BrbpCallDriverAsync
0x14000e7e5  lea     rbp, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000e7ec  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000e7f3  jz      short loc_14000E823
0x14000e7f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e7fc  mov     rbx, [rcx+40h]
0x14000e800  mov     ecx, edi
0x14000e802  call    NtStatusTxt
0x14000e807  mov     r9d, 22h ; '"'
0x14000e80d  mov     [rsp+68h+var_40], rax
0x14000e812  mov     rcx, rbx
0x14000e815  mov     [rsp+68h+var_48], rbp
0x14000e81a  lea     r8d, [r9-1Fh]
0x14000e81e  call    WPP_RECORDER_SF_s
0x14000e823  mov     eax, edi
0x14000e825  add     rsp, 30h
0x14000e829  pop     r15
0x14000e82b  pop     r14
0x14000e82d  pop     r12
0x14000e82f  pop     rdi
0x14000e830  pop     rsi
0x14000e831  pop     rbp
0x14000e832  pop     rbx
0x14000e833  retn
```
