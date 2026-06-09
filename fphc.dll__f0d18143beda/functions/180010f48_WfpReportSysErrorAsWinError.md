# WfpReportSysErrorAsWinError

- ea: `0x180010f48`
- end: `0x180010f96`
- name: `WfpReportSysErrorAsWinError`
- size: `78`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180006970`
- `0x18000bad0`
- `0x18000c63c`
- `0x18000c868`
- `0x180010a00`

## callees

- `0x180010d4c`
- `0x180010f48`

## pseudocode

```c
__int64 __fastcall WfpReportSysErrorAsWinError(__int64 a1, int a2, int a3)
{
  int v3; // ebx

  v3 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2, a3);
  }
  if ( v3 > 0 )
    return (int)((unsigned __int16)v3 | 0x80070000);
  return v3;
}

```

## disassembly

```asm
0x180010f48  push    rbx
0x180010f4a  sub     rsp, 30h
0x180010f4e  mov     ebx, r8d
0x180010f51  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f58  lea     rax, WPP_GLOBAL_Control
0x180010f5f  cmp     rcx, rax
0x180010f62  jz      short loc_180010F80
0x180010f64  cmp     byte ptr [rcx+19h], 2
0x180010f68  jb      short loc_180010F80
0x180010f6a  test    byte ptr [rcx+1Ch], 1
0x180010f6e  jz      short loc_180010F80
0x180010f70  mov     rcx, [rcx+10h]
0x180010f74  mov     r9, rdx
0x180010f77  mov     [rsp+38h+var_18], ebx
0x180010f7b  call    WPP_SF_sD
0x180010f80  test    ebx, ebx
0x180010f82  jle     short loc_180010F8D
0x180010f84  movzx   ebx, bx
0x180010f87  or      ebx, 80070000h
0x180010f8d  movsxd  rax, ebx
0x180010f90  add     rsp, 30h
0x180010f94  pop     rbx
0x180010f95  retn
```
