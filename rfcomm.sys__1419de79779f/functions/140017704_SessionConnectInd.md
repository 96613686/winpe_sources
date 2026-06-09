# SessionConnectInd

- ea: `0x140017704`
- end: `0x1400178b1`
- name: `SessionConnectInd`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d4b0`

## callees

- `0x140003868`
- `0x140003bf4`
- `0x140003cb4`
- `0x14000e4e0`
- `0x1400157dc`
- `0x140017704`
- `0x1400178b8`
- `0x14001812c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017766`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017766`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017791`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017803`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001782c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017791`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017803`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001782c`

## string_xrefs

- `0x1400177a6`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\session.c`

## pseudocode

```c
__int64 __fastcall SessionConnectInd(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 Locked; // rax
  __int64 v7; // rdi
  unsigned __int16 v8; // bx
  __int64 v9; // rax
  int v10; // edx
  char v12; // [rsp+60h] [rbp+8h] BYREF
  __int64 v13; // [rsp+70h] [rbp+18h] BYREF

  v13 = a3;
  v12 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      19,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids);
  *(_BYTE *)(a1 + 32) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 24));
  Locked = SessionFindLocked(a1, &v13);
  v7 = Locked;
  if ( Locked )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(Locked + 56), *(_BYTE *)(Locked + 64));
    RefObj_ReleaseEx(v7 + 24, 1145981254, 306, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\session.c");
    v8 = 4;
  }
  else
  {
    v9 = SessionCreateLocked(a1, a3, 0, &v12);
    v7 = v9;
    if ( v9 )
    {
      if ( (unsigned __int8)RfcommSetState(v9, 1) )
      {
        *(_QWORD *)(v7 + 280) = a2;
        v8 = 0;
      }
      else
      {
        v8 = 4;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 56), *(_BYTE *)(v7 + 64));
    }
    else
    {
      v8 = 4;
    }
    if ( v12 )
      RfcommStartTimerLocked(a1);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 24), *(_BYTE *)(a1 + 32));
  if ( !v8 )
  {
    LOBYTE(v10) = 1;
    BrbpConnect(v7, v10, *(_QWORD *)(v7 + 264), 1, a2, 0);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      3,
      20,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids,
      v8);
  return v8;
}

```

## disassembly

```asm
0x140017704  mov     r11, rsp
0x140017707  mov     [r11+10h], rbx
0x14001770b  mov     [r11+20h], rbp
0x14001770f  mov     [r11+18h], r8
0x140017713  push    rsi
0x140017714  push    rdi
0x140017715  push    r12
0x140017717  push    r14
0x140017719  push    r15
0x14001771b  sub     rsp, 30h
0x14001771f  xor     r15d, r15d
0x140017722  mov     rbx, r8
0x140017725  mov     [r11+8], r15b
0x140017729  mov     rbp, rdx
0x14001772c  mov     rsi, rcx
0x14001772f  lea     r12, WPP_RECORDER_INITIALIZED
0x140017736  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001773d  lea     rax, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x140017744  jz      short loc_140017762
0x140017746  mov     rcx, cs:WPP_GLOBAL_Control
0x14001774d  lea     r9d, [r15+13h]
0x140017751  lea     r8d, [r15+3]
0x140017755  mov     [r11-38h], rax
0x140017759  mov     rcx, [rcx+40h]
0x14001775d  call    WPP_RECORDER_SF_
0x140017762  lea     rcx, [rsi+18h]; SpinLock
0x140017766  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001776d  nop     dword ptr [rax+rax+00h]
0x140017772  lea     rdx, [rsp+58h+arg_10]
0x140017777  mov     rcx, rsi
0x14001777a  mov     [rsi+20h], al
0x14001777d  call    SessionFindLocked
0x140017782  mov     rdi, rax
0x140017785  test    rax, rax
0x140017788  jz      short loc_1400177BF
0x14001778a  mov     dl, [rax+40h]; NewIrql
0x14001778d  lea     rcx, [rax+38h]; SpinLock
0x140017791  call    cs:__imp_KeReleaseSpinLock
0x140017798  nop     dword ptr [rax+rax+00h]
0x14001779d  lea     rcx, [rdi+18h]
0x1400177a1  mov     edx, 444E4946h
0x1400177a6  lea     r9, aOnecoreDrivers; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400177ad  mov     r8d, 132h
0x1400177b3  call    RefObj_ReleaseEx
0x1400177b8  mov     ebx, 4
0x1400177bd  jmp     short loc_140017825
0x1400177bf  lea     r9, [rsp+58h+arg_0]
0x1400177c4  xor     r8d, r8d
0x1400177c7  mov     rdx, rbx
0x1400177ca  mov     rcx, rsi
0x1400177cd  call    SessionCreateLocked
0x1400177d2  mov     rdi, rax
0x1400177d5  test    rax, rax
0x1400177d8  jz      short loc_140017811
0x1400177da  mov     edx, 1
0x1400177df  mov     rcx, rax
0x1400177e2  call    RfcommSetState
0x1400177e7  test    al, al
0x1400177e9  jz      short loc_1400177F7
0x1400177eb  mov     [rdi+118h], rbp
0x1400177f2  mov     ebx, r15d
0x1400177f5  jmp     short loc_1400177FC
0x1400177f7  mov     ebx, 4
0x1400177fc  mov     dl, [rdi+40h]; NewIrql
0x1400177ff  lea     rcx, [rdi+38h]; SpinLock
0x140017803  call    cs:__imp_KeReleaseSpinLock
0x14001780a  nop     dword ptr [rax+rax+00h]
0x14001780f  jmp     short loc_140017816
0x140017811  mov     ebx, 4
0x140017816  cmp     [rsp+58h+arg_0], r15b
0x14001781b  jz      short loc_140017825
0x14001781d  mov     rcx, rsi
0x140017820  call    RfcommStartTimerLocked
0x140017825  mov     dl, [rsi+20h]; NewIrql
0x140017828  lea     rcx, [rsi+18h]; SpinLock
0x14001782c  call    cs:__imp_KeReleaseSpinLock
0x140017833  nop     dword ptr [rax+rax+00h]
0x140017838  test    bx, bx
0x14001783b  jnz     short loc_140017860
0x14001783d  mov     r8, [rdi+108h]
0x140017844  mov     r9d, 1
0x14001784a  mov     dl, r9b
0x14001784d  mov     word ptr [rsp+58h+var_30], r15w
0x140017853  mov     rcx, rdi
0x140017856  mov     [rsp+58h+var_38], rbp
0x14001785b  call    BrbpConnect
0x140017860  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140017867  jz      short loc_140017896
0x140017869  movzx   ecx, bx
0x14001786c  lea     rax, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x140017873  mov     [rsp+58h+var_30], ecx
0x140017877  mov     r9d, 14h
0x14001787d  mov     rcx, cs:WPP_GLOBAL_Control
0x140017884  mov     [rsp+58h+var_38], rax
0x140017889  lea     r8d, [r9-11h]
0x14001788d  mov     rcx, [rcx+40h]
0x140017891  call    WPP_RECORDER_SF_d
0x140017896  mov     rbp, [rsp+58h+arg_18]
0x14001789b  movzx   eax, bx
0x14001789e  mov     rbx, [rsp+58h+arg_8]
0x1400178a3  add     rsp, 30h
0x1400178a7  pop     r15
0x1400178a9  pop     r14
0x1400178ab  pop     r12
0x1400178ad  pop     rdi
0x1400178ae  pop     rsi
0x1400178af  retn
```
