# FwReportReturnError

- ea: `0x1800047e0`
- end: `0x18000483a`
- name: `FwReportReturnError`
- size: `90`
- prototype: ``
- caller_count: `97`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001270`
- `0x180001344`
- `0x180001400`
- `0x1800014d0`
- `0x180001680`
- `0x180001720`
- `0x180001820`
- `0x180001a58`
- `0x180001b80`
- `0x180001eb0`
- `0x180002080`
- `0x1800020f0`
- `0x180002160`
- `0x180002280`
- `0x1800023c0`
- `0x180002440`
- `0x1800024a0`
- `0x180002610`
- `0x1800027a0`
- `0x180002910`
- `0x180002b30`
- `0x180002c10`
- `0x180002e70`
- `0x1800030b0`
- `0x1800031a0`
- `0x1800032e0`
- `0x1800037f0`
- `0x1800038e0`
- `0x180003b30`
- `0x180004100`
- `0x1800043a0`
- `0x1800045f0`
- `0x180004cd0`
- `0x180004f90`
- `0x1800050c0`
- `0x180005350`
- `0x1800053c0`
- `0x180006090`
- `0x1800068e4`
- `0x180006b68`
- `0x180007180`
- `0x1800114a0`
- `0x1800120e0`
- `0x180012220`
- `0x180012288`
- `0x180012508`
- `0x18001262c`
- `0x18001287c`
- `0x180012960`
- `0x180012a60`

## callees

- `0x1800047e0`
- `0x180017b58`
- `0x18002f38c`

## string_xrefs

- `0x18000482c`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwReportReturnError(int a1, __int64 a2, int a3)
{
  unsigned int v3; // ebx

  v3 = a2;
  if ( (int)a2 >= 0 )
    MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", a2, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, v3);
  return v3;
}

```

## disassembly

```asm
0x1800047e0  mov     [rsp+arg_0], rbx
0x1800047e5  push    rdi
0x1800047e6  sub     rsp, 30h
0x1800047ea  mov     ebx, edx
0x1800047ec  mov     rdi, rcx
0x1800047ef  test    edx, edx
0x1800047f1  jns     short loc_180004829
0x1800047f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047fa  lea     rax, WPP_GLOBAL_Control
0x180004801  cmp     rcx, rax
0x180004804  jz      short loc_18000481C
0x180004806  test    byte ptr [rcx+1Ch], 1
0x18000480a  jz      short loc_18000481C
0x18000480c  mov     rcx, [rcx+10h]
0x180004810  mov     r9, rdi
0x180004813  mov     [rsp+38h+var_18], ebx
0x180004817  call    WPP_SF_sD
0x18000481c  mov     eax, ebx
0x18000481e  mov     rbx, [rsp+38h+arg_0]
0x180004823  add     rsp, 30h
0x180004827  pop     rdi
0x180004828  retn
0x180004829  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "FAILED(hr)", "Function failure")
0x18000482c  lea     rcx, aMpssvcDll_0; "mpssvc.dll"
0x180004833  call    MicrosoftTelemetryAssertTriggeredArgs
0x180004838  jmp     short loc_1800047F3
```
