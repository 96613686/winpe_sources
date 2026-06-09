# DiskSetInfoExceptionInformation

- ea: `0x14000e200`
- end: `0x14000e291`
- name: `DiskSetInfoExceptionInformation`
- size: `145`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140010490`
- `0x140010a70`

## callees

- `0x1400043dc`
- `0x14000e200`
- `0x140015760`

## pseudocode

```c
__int64 __fastcall DiskSetInfoExceptionInformation(__int64 a1, void *a2)
{
  int v4; // ebx
  int v5; // edi
  const char *v6; // r9

  v4 = 2;
  do
  {
    v5 = DiskModeSelect(*(PDEVICE_OBJECT *)(a1 + 8), a2, 0xCu, 1);
    --v4;
  }
  while ( v4 );
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v6 = "succeeded";
    if ( v5 < 0 )
      v6 = "failed";
    WPP_SF_sq(
      WPP_GLOBAL_Control->AttachedDevice,
      49,
      (unsigned int)WPP_0d021951613e35be7880fae860fb7f50_Traceguids,
      (_DWORD)v6,
      *(_QWORD *)(a1 + 8));
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000e200  push    rbx
0x14000e202  push    rbp
0x14000e203  push    rsi
0x14000e204  push    rdi
0x14000e205  sub     rsp, 38h
0x14000e209  mov     rsi, rdx
0x14000e20c  mov     rbp, rcx
0x14000e20f  mov     ebx, 2
0x14000e214  mov     rcx, [rbp+8]; DeviceObject
0x14000e218  mov     r9b, 1
0x14000e21b  mov     r8d, 0Ch; Size
0x14000e221  mov     rdx, rsi; Src
0x14000e224  call    DiskModeSelect
0x14000e229  mov     edi, eax
0x14000e22b  add     ebx, 0FFFFFFFFh
0x14000e22e  jnz     short loc_14000E214
0x14000e230  mov     r10, cs:WPP_GLOBAL_Control
0x14000e237  lea     rax, WPP_GLOBAL_Control
0x14000e23e  cmp     r10, rax
0x14000e241  jz      short loc_14000E285
0x14000e243  mov     ecx, [r10+2Ch]
0x14000e247  test    cl, 40h
0x14000e24a  jz      short loc_14000E285
0x14000e24c  cmp     byte ptr [r10+29h], 4
0x14000e251  jb      short loc_14000E285
0x14000e253  mov     rcx, [r10+18h]
0x14000e257  lea     rax, aFailed; "failed"
0x14000e25e  test    edi, edi
0x14000e260  lea     r9, aSucceeded; "succeeded"
0x14000e267  mov     edx, 31h ; '1'
0x14000e26c  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000e273  cmovs   r9, rax
0x14000e277  mov     rax, [rbp+8]
0x14000e27b  mov     [rsp+58h+var_38], rax
0x14000e280  call    WPP_SF_sq
0x14000e285  mov     eax, edi
0x14000e287  add     rsp, 38h
0x14000e28b  pop     rdi
0x14000e28c  pop     rsi
0x14000e28d  pop     rbp
0x14000e28e  pop     rbx
0x14000e28f  retn
```
