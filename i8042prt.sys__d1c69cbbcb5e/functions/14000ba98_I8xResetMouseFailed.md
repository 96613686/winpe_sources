# I8xResetMouseFailed

- ea: `0x14000ba98`
- end: `0x14000baf9`
- name: `I8xResetMouseFailed`
- size: `97`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000b8a8`
- `0x14000c190`
- `0x14000c83c`
- `0x14001be20`

## callees

- `0x140004530`
- `0x14000b5f4`
- `0x14000ba98`

## pseudocode

```c
void __fastcall I8xResetMouseFailed(__int64 a1, __int64 a2)
{
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      a2,
      0x11u,
      0x59u,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
  *(_DWORD *)(a1 + 928) = 1101;
  I8xFinishResetRequest(a1, 1, 1, 1);
}

```

## disassembly

```asm
0x14000ba98  push    rbx
0x14000ba9a  sub     rsp, 30h
0x14000ba9e  mov     rbx, rcx
0x14000baa1  lea     rax, WPP_RECORDER_INITIALIZED
0x14000baa8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000baaf  jz      short loc_14000BAD7
0x14000bab1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bab8  lea     rax, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14000babf  mov     r9d, 59h ; 'Y'
0x14000bac5  mov     [rsp+38h+var_18], rax
0x14000baca  mov     rcx, [rcx+40h]
0x14000bace  lea     r8d, [r9-48h]
0x14000bad2  call    WPP_RECORDER_SF_
0x14000bad7  mov     r9b, 1
0x14000bada  mov     dword ptr [rbx+3A0h], 44Dh
0x14000bae4  mov     r8b, r9b
0x14000bae7  mov     dl, r9b
0x14000baea  mov     rcx, rbx
0x14000baed  call    I8xFinishResetRequest
0x14000baf2  add     rsp, 30h
0x14000baf6  pop     rbx
0x14000baf7  retn
```
