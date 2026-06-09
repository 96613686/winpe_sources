# MountMgrTraceDeviceExtension

- ea: `0x14000d0bc`
- end: `0x14000d142`
- name: `MountMgrTraceDeviceExtension`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000d3ac`

## callees

- `0x1400029f8`
- `0x14000d0bc`

## pseudocode

```c
__int64 __fastcall MountMgrTraceDeviceExtension(__int64 a1)
{
  const char *v1; // r9
  const char *v2; // r8
  const char *v3; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v1 = "TRUE";
    v2 = "TRUE";
    if ( !*(_DWORD *)(a1 + 280) )
      v2 = "FALSE";
    v3 = "TRUE";
    if ( !*(_BYTE *)(a1 + 192) )
      v3 = "FALSE";
    if ( !*(_BYTE *)(a1 + 144) )
      v1 = "FALSE";
    WPP_SF_sssi(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v3,
      (_DWORD)v2,
      (_DWORD)v1,
      (__int64)v3,
      (__int64)v2,
      *(_QWORD *)(a1 + 336));
  }
  return 0;
}

```

## disassembly

```asm
0x14000d0bc  sub     rsp, 48h
0x14000d0c0  mov     r10, rcx
0x14000d0c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d0ca  lea     rax, WPP_GLOBAL_Control
0x14000d0d1  cmp     rcx, rax
0x14000d0d4  jz      short loc_14000D13A
0x14000d0d6  mov     eax, [rcx+2Ch]
0x14000d0d9  test    al, 8
0x14000d0db  jz      short loc_14000D13A
0x14000d0dd  cmp     byte ptr [rcx+29h], 2
0x14000d0e1  jb      short loc_14000D13A
0x14000d0e3  cmp     dword ptr [r10+118h], 0
0x14000d0eb  lea     r11, aFalse; "FALSE"
0x14000d0f2  mov     rax, [r10+150h]
0x14000d0f9  lea     r9, aTrue; "TRUE"
0x14000d100  mov     rcx, [rcx+18h]
0x14000d104  mov     r8, r9
0x14000d107  cmovz   r8, r11
0x14000d10b  mov     [rsp+48h+var_18], rax
0x14000d110  cmp     byte ptr [r10+0C0h], 0
0x14000d118  mov     rdx, r9
0x14000d11b  mov     [rsp+48h+var_20], r8
0x14000d120  cmovz   rdx, r11
0x14000d124  cmp     byte ptr [r10+90h], 0
0x14000d12c  mov     [rsp+48h+var_28], rdx
0x14000d131  cmovz   r9, r11
0x14000d135  call    WPP_SF_sssi
0x14000d13a  xor     eax, eax
0x14000d13c  add     rsp, 48h
0x14000d140  retn
```
