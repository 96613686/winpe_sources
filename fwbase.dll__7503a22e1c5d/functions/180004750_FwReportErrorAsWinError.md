# FwReportErrorAsWinError

- ea: `0x180004750`
- end: `0x1800047cf`
- name: `FwReportErrorAsWinError`
- size: `127`
- prototype: ``
- caller_count: `52`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001720`
- `0x180001a58`
- `0x180001b80`
- `0x180001eb0`
- `0x180002160`
- `0x180002280`
- `0x1800023c0`
- `0x1800024a0`
- `0x180002610`
- `0x1800027a0`
- `0x180002910`
- `0x180002c10`
- `0x1800030b0`
- `0x1800031a0`
- `0x1800032e0`
- `0x180003b30`
- `0x180004100`
- `0x1800043a0`
- `0x1800045f0`
- `0x180004cd0`
- `0x180004f90`
- `0x1800050c0`
- `0x180005350`
- `0x1800053c0`
- `0x1800068e4`
- `0x180006b68`
- `0x180007180`
- `0x180012220`
- `0x18001262c`
- `0x180012960`
- `0x180012a60`
- `0x180012de4`
- `0x1800138f0`
- `0x180013a20`
- `0x18001f260`
- `0x18001f3a0`
- `0x18001f530`
- `0x18001f88c`
- `0x18001fb90`
- `0x18001ff80`
- `0x180020470`
- `0x1800205fc`
- `0x180020b10`
- `0x180020e90`
- `0x180020f80`
- `0x1800210b0`
- `0x180021270`
- `0x180029d10`
- `0x18002b410`
- `0x18002b7a4`

## callees

- `0x180004750`
- `0x180014268`
- `0x18002f38c`

## string_xrefs

- `0x1800047a8`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwReportErrorAsWinError(int a1, __int64 a2, int a3)
{
  int v3; // ebx

  v3 = a3;
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", 0, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_ssL(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a2, v3);
  if ( v3 > 0 )
    return (unsigned __int16)v3 | 0x80070000;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180004750  mov     [rsp+arg_0], rbx
0x180004755  mov     [rsp+arg_8], rsi
0x18000475a  push    rdi
0x18000475b  sub     rsp, 30h
0x18000475f  mov     ebx, r8d
0x180004762  mov     rdi, rdx
0x180004765  mov     rsi, rcx
0x180004768  test    r8d, r8d
0x18000476b  jz      short loc_1800047A5
0x18000476d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004774  lea     rax, WPP_GLOBAL_Control
0x18000477b  cmp     rcx, rax
0x18000477e  jz      short loc_180004786
0x180004780  test    byte ptr [rcx+1Ch], 1
0x180004784  jnz     short loc_1800047B8
0x180004786  test    ebx, ebx
0x180004788  jle     short loc_180004793
0x18000478a  movzx   ebx, bx
0x18000478d  or      ebx, 80070000h
0x180004793  mov     rsi, [rsp+38h+arg_8]
0x180004798  mov     eax, ebx
0x18000479a  mov     rbx, [rsp+38h+arg_0]
0x18000479f  add     rsp, 30h
0x1800047a3  pop     rdi
0x1800047a4  retn
0x1800047a5  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "error != NO_ERROR", "Function failure")
0x1800047a8  lea     rcx, aMpssvcDll_0; "mpssvc.dll"
0x1800047af  xor     edx, edx
0x1800047b1  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800047b6  jmp     short loc_18000476D
0x1800047b8  mov     rcx, [rcx+10h]
0x1800047bc  mov     r9, rsi
0x1800047bf  mov     [rsp+38h+var_10], ebx
0x1800047c3  mov     [rsp+38h+var_18], rdi
0x1800047c8  call    WPP_SF_ssL
0x1800047cd  jmp     short loc_180004786
```
