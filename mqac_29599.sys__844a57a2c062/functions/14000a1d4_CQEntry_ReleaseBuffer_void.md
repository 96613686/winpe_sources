# CQEntry::ReleaseBuffer(void)

- ea: `0x14000a1d4`
- end: `0x14000a21e`
- name: `?ReleaseBuffer@CQEntry@@QEBAXXZ`
- size: `74`
- prototype: `void __fastcall(CQEntry *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x1400041ac`
- `0x140005e1c`
- `0x140005f08`
- `0x1400061fc`
- `0x140006334`
- `0x14000648c`
- `0x140007a88`
- `0x140007cb8`
- `0x140007e3c`
- `0x14000a2b8`
- `0x140012368`
- `0x140014980`
- `0x14001569c`
- `0x140020ebc`
- `0x140020f9c`

## callees

- `0x140001c34`
- `0x14000a1d4`

## pseudocode

```c
void __fastcall CQEntry::ReleaseBuffer(CQEntry *this)
{
  __int64 v1; // rax

  v1 = *((_QWORD *)this + 3);
  --*(_DWORD *)(v1 + 148);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      0x1Eu,
      (__int64)&WPP_664e97eed756311217f592c2f10907d7_Traceguids,
      *(_DWORD *)(v1 + 148));
  }
}

```

## disassembly

```asm
0x14000a1d4  sub     rsp, 28h
0x14000a1d8  mov     rax, [rcx+18h]
0x14000a1dc  dec     dword ptr [rax+94h]
0x14000a1e2  mov     r9d, [rax+94h]
0x14000a1e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a1f0  lea     rax, WPP_GLOBAL_Control
0x14000a1f7  cmp     rcx, rax
0x14000a1fa  jz      short loc_14000A218
0x14000a1fc  mov     eax, [rcx+6Ch]
0x14000a1ff  test    al, 4
0x14000a201  jz      short loc_14000A218
0x14000a203  mov     rcx, [rcx+58h]
0x14000a207  lea     r8, WPP_664e97eed756311217f592c2f10907d7_Traceguids
0x14000a20e  mov     edx, 1Eh
0x14000a213  call    WPP_SF_d
0x14000a218  add     rsp, 28h
0x14000a21c  retn
```
