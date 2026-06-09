# WfpReportError

- ea: `0x180010e48`
- end: `0x180010e8e`
- name: `WfpReportError`
- size: `70`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c868`
- `0x18000ca08`
- `0x18000ee60`
- `0x180010a00`

## callees

- `0x180010dcc`
- `0x180010e48`

## pseudocode

```c
__int64 __fastcall WfpReportError(__int64 a1, int a2, int a3)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, a3, a2, a1);
  }
  return a1;
}

```

## disassembly

```asm
0x180010e48  push    rbx
0x180010e4a  sub     rsp, 30h
0x180010e4e  mov     r9, rdx
0x180010e51  mov     rbx, rcx
0x180010e54  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e5b  lea     rax, WPP_GLOBAL_Control
0x180010e62  cmp     rcx, rax
0x180010e65  jz      short loc_180010E85
0x180010e67  cmp     byte ptr [rcx+19h], 2
0x180010e6b  jb      short loc_180010E85
0x180010e6d  test    byte ptr [rcx+1Ch], 1
0x180010e71  jz      short loc_180010E85
0x180010e73  mov     rcx, [rcx+10h]
0x180010e77  mov     edx, 0Eh
0x180010e7c  mov     [rsp+38h+var_18], ebx
0x180010e80  call    WPP_SF_sd
0x180010e85  mov     rax, rbx
0x180010e88  add     rsp, 30h
0x180010e8c  pop     rbx
0x180010e8d  retn
```
