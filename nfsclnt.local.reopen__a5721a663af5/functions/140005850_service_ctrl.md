# service_ctrl

- ea: `0x140005850`
- end: `0x14000587e`
- name: `service_ctrl`
- size: `46`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400053e0`
- `0x140005850`
- `0x140007124`

## pseudocode

```c
void __fastcall service_ctrl(DWORD dwControl)
{
  if ( dwControl == 1 )
  {
    ssStatus.dwCurrentState = 3;
    ServiceStop(0);
  }
  ReportStatusToSCMgr(ssStatus.dwCurrentState, 0, 0);
}

```

## disassembly

```asm
0x140005850  sub     rsp, 28h
0x140005854  cmp     ecx, 1
0x140005857  jnz     short loc_14000586A
0x140005859  xor     ecx, ecx
0x14000585b  mov     cs:ssStatus.dwCurrentState, 3
0x140005865  call    ServiceStop
0x14000586a  mov     ecx, cs:ssStatus.dwCurrentState
0x140005870  xor     r8d, r8d
0x140005873  xor     edx, edx
0x140005875  add     rsp, 28h
0x140005879  jmp     ReportStatusToSCMgr
```
