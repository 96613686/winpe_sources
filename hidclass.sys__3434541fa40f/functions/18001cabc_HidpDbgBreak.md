# HidpDbgBreak

- ea: `0x18001cabc`
- end: `0x18001cb42`
- name: `HidpDbgBreak`
- size: `134`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800017d0`
- `0x180003900`
- `0x180003b70`
- `0x180003f40`
- `0x18000ef30`
- `0x180012090`
- `0x180025858`

## callees

- `0x18001cabc`
- `0x18002343c`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x18001cb14`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x18001cb14`
- `ntoskrnl!DbgPrint` at `0x18001cb2e`
- `ntoskrnl!DbgPrint` at `0x18001cb2e`

## pseudocode

```c
char __fastcall HidpDbgBreak(const char *a1, __int64 a2, __int64 a3, int a4)
{
  bool v5; // dl
  char result; // al

  v5 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      a4);
  result = KdRefreshDebuggerNotPresent();
  if ( !result )
  {
    result = DbgPrint("ERROR: HID ASSERT failed due to %s. For more details run: !rcdrlogdump hidclass\n", a1);
    __debugbreak();
  }
  return result;
}

```

## disassembly

```asm
0x18001cabc  push    rbx
0x18001cabe  sub     rsp, 50h
0x18001cac2  mov     rbx, rcx
0x18001cac5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001cacc  lea     rax, WPP_GLOBAL_Control
0x18001cad3  cmp     rcx, rax
0x18001cad6  jz      short loc_18001CAE9
0x18001cad8  mov     eax, [rcx+2Ch]
0x18001cadb  test    al, al
0x18001cadd  jns     short loc_18001CAE9
0x18001cadf  cmp     byte ptr [rcx+29h], 2
0x18001cae3  jb      short loc_18001CAE9
0x18001cae5  mov     dl, 1
0x18001cae7  jmp     short loc_18001CAEB
0x18001cae9  xor     dl, dl
0x18001caeb  lea     rax, WPP_RECORDER_INITIALIZED
0x18001caf2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001caf9  setnz   r8b
0x18001cafd  test    dl, dl
0x18001caff  jnz     short loc_18001CB06
0x18001cb01  test    r8b, r8b
0x18001cb04  jz      short loc_18001CB14
0x18001cb06  mov     rcx, [rcx+18h]
0x18001cb0a  mov     [rsp+58h+var_18], rbx
0x18001cb0f  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001cb14  call    cs:__imp_KdRefreshDebuggerNotPresent
0x18001cb1b  nop     dword ptr [rax+rax+00h]
0x18001cb20  test    al, al
0x18001cb22  jnz     short loc_18001CB3B
0x18001cb24  mov     rdx, rbx
0x18001cb27  lea     rcx, aErrorHidAssert; "ERROR: HID ASSERT failed due to %s. For"...
0x18001cb2e  call    cs:__imp_DbgPrint
0x18001cb35  nop     dword ptr [rax+rax+00h]
0x18001cb3a  int     3; Trap to Debugger
0x18001cb3b  add     rsp, 50h
0x18001cb3f  pop     rbx
0x18001cb40  retn
```
