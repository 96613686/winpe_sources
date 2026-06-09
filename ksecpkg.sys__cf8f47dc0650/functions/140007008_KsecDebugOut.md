# KsecDebugOut

- ea: `0x140007008`
- end: `0x14000711b`
- name: `KsecDebugOut`
- size: `275`
- prototype: `__int64(_QWORD, const char *, ...)`
- caller_count: `35`
- callee_count: `2`
- tags: ``

## callers

- `0x14000db50`
- `0x1400206f8`
- `0x1400207ec`
- `0x140021d20`
- `0x140021db0`
- `0x140021ea0`
- `0x140022010`
- `0x140022150`
- `0x1400221e0`
- `0x140022280`
- `0x1400223a4`
- `0x140022510`
- `0x140022680`
- `0x140028fb0`
- `0x1400290b0`
- `0x1400291a0`
- `0x140029690`
- `0x140029780`
- `0x140029870`
- `0x1400299f8`
- `0x140029fe4`
- `0x14002a2e4`
- `0x14002a4d8`
- `0x14002ae10`
- `0x14002bc00`
- `0x14002bf1c`
- `0x14002c250`
- `0x14002c300`
- `0x14002c3b0`
- `0x14002c460`
- `0x14002c510`
- `0x14002c5c0`
- `0x14002c664`
- `0x14002c740`
- `0x140032078`

## callees

- `0x140007008`
- `0x140010160`

## import_xrefs

- `ntoskrnl!_vsnprintf_s` at `0x1400070c3`
- `ntoskrnl!_vsnprintf_s` at `0x1400070c3`
- `ntoskrnl!DbgPrintEx` at `0x14000709e`
- `ntoskrnl!DbgPrintEx` at `0x1400070de`
- `ntoskrnl!DbgPrintEx` at `0x1400070f3`
- `ntoskrnl!DbgPrintEx` at `0x14000709e`
- `ntoskrnl!DbgPrintEx` at `0x1400070de`
- `ntoskrnl!DbgPrintEx` at `0x1400070f3`
- `ntoskrnl!PsGetCurrentProcess` at `0x140007072`
- `ntoskrnl!PsGetCurrentProcess` at `0x140007072`

## pseudocode

```c
void KsecDebugOut(int a1, const char *a2, ...)
{
  ULONG v2; // edi
  struct _KTHREAD *CurrentThread; // rbx
  const void *CurrentProcess; // rax
  char DstBuf[256]; // [rsp+40h] [rbp-128h] BYREF
  va_list va; // [rsp+180h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( (a1 & KsecInfoLevel) != 0 )
  {
    v2 = 1;
    if ( (a1 & 1) != 0 )
    {
      v2 = 0;
    }
    else if ( (a1 & 2) == 0 )
    {
      v2 = (~(_BYTE)a1 & 4 | 8u) >> 2;
    }
    CurrentThread = KeGetCurrentThread();
    CurrentProcess = (const void *)PsGetCurrentProcess();
    DbgPrintEx(0x83u, v2, "%p.%p> KSec:  ", CurrentProcess, CurrentThread);
    if ( _vsnprintf_s(DstBuf, 0x100u, 0xFFu, a2, va) >= 0 )
      DbgPrintEx(0x83u, v2, DstBuf);
    else
      DbgPrintEx(0x83u, 0, "Error printing message\n");
  }
}

```

## disassembly

```asm
0x140007008  mov     [rsp+Format], rdx
0x14000700d  mov     qword ptr [rsp+arg_10], r8
0x140007012  mov     [rsp+arg_18], r9
0x140007017  push    rbx
0x140007018  push    rsi
0x140007019  push    rdi
0x14000701a  sub     rsp, 150h
0x140007021  mov     rax, cs:__security_cookie
0x140007028  xor     rax, rsp
0x14000702b  mov     [rsp+168h+var_28], rax
0x140007033  test    cs:KsecInfoLevel, ecx
0x140007039  mov     [rsp+168h+var_138], 0
0x140007042  jz      loc_1400070FF
0x140007048  mov     edi, 1
0x14000704d  test    dil, cl
0x140007050  jz      short loc_140007056
0x140007052  xor     edi, edi
0x140007054  jmp     short loc_140007069
0x140007056  test    cl, 2
0x140007059  jnz     short loc_140007069
0x14000705b  not     cl
0x14000705d  movzx   edi, cl
0x140007060  and     edi, 4
0x140007063  or      edi, 8
0x140007066  shr     edi, 2
0x140007069  mov     rbx, gs:188h
0x140007072  call    cs:__imp_PsGetCurrentProcess
0x140007079  nop     dword ptr [rax+rax+00h]
0x14000707e  mov     [rsp+168h+ArgList], rbx
0x140007083  lea     r8, Format; "%p.%p> KSec:  "
0x14000708a  mov     ebx, 83h
0x14000708f  lea     rsi, [rsp+168h+arg_10]
0x140007097  mov     ecx, ebx; ComponentId
0x140007099  mov     r9, rax
0x14000709c  mov     edx, edi; Level
0x14000709e  call    cs:__imp_DbgPrintEx
0x1400070a5  nop     dword ptr [rax+rax+00h]
0x1400070aa  mov     r9, [rsp+168h+Format]; Format
0x1400070b2  lea     edx, [rbx+7Dh]; SizeInBytes
0x1400070b5  lea     r8d, [rbx+7Ch]; MaxCount
0x1400070b9  mov     [rsp+168h+ArgList], rsi; ArgList
0x1400070be  lea     rcx, [rsp+168h+DstBuf]; DstBuf
0x1400070c3  call    cs:__imp__vsnprintf_s
0x1400070ca  nop     dword ptr [rax+rax+00h]
0x1400070cf  mov     ecx, ebx; ComponentId
0x1400070d1  test    eax, eax
0x1400070d3  jns     short loc_1400070EC
0x1400070d5  lea     r8, aErrorPrintingM; "Error printing message\n"
0x1400070dc  xor     edx, edx; Level
0x1400070de  call    cs:__imp_DbgPrintEx
0x1400070e5  nop     dword ptr [rax+rax+00h]
0x1400070ea  jmp     short loc_1400070FF
0x1400070ec  lea     r8, [rsp+168h+DstBuf]; Format
0x1400070f1  mov     edx, edi; Level
0x1400070f3  call    cs:__imp_DbgPrintEx
0x1400070fa  nop     dword ptr [rax+rax+00h]
0x1400070ff  mov     rcx, [rsp+168h+var_28]
0x140007107  xor     rcx, rsp; StackCookie
0x14000710a  call    __security_check_cookie
0x14000710f  add     rsp, 150h
0x140007116  pop     rdi
0x140007117  pop     rsi
0x140007118  pop     rbx
0x140007119  retn
```
