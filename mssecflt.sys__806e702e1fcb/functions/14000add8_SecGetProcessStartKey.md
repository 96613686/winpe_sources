# SecGetProcessStartKey

- ea: `0x14000add8`
- end: `0x14000aec0`
- name: `SecGetProcessStartKey`
- size: `232`
- prototype: `__int64 __fastcall(PEPROCESS Process)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140006754`
- `0x14000ac80`
- `0x140021ca0`
- `0x140027278`
- `0x14002c580`
- `0x14002c6b0`
- `0x140040f3c`

## callees

- `0x1400088d4`
- `0x14000add8`
- `0x140011610`
- `0x140011650`
- `0x140040874`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000ae82`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000ae82`
- `ntoskrnl!PsGetProcessId` at `0x14000ae41`
- `ntoskrnl!PsGetProcessId` at `0x14000ae41`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14000ae2f`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14000ae2f`

## pseudocode

```c
__int64 __fastcall SecGetProcessStartKey(PEPROCESS Process, _QWORD *a2)
{
  __int64 v4; // rax
  NTSTATUS v5; // ecx
  LONGLONG TimeQuadPart; // rbx
  unsigned int MinimumRequiredStackSizeQueryProcessStartKey; // eax
  PEPROCESS Parameter; // [rsp+30h] [rbp-28h] BYREF
  __int64 v10; // [rsp+38h] [rbp-20h]
  __int64 v11; // [rsp+40h] [rbp-18h]

  v10 = 0;
  v11 = 0;
  if ( qword_140020020 )
  {
    v4 = qword_140020020();
    v5 = 0;
LABEL_7:
    *a2 = v4;
    return (unsigned int)v5;
  }
  if ( (unsigned __int8)KclIsWindows8() )
  {
    TimeQuadPart = PsGetProcessCreateTimeQuadPart(Process);
    *a2 = TimeQuadPart ^ ((unsigned __int64)(unsigned int)PsGetProcessId(Process) << 32);
    return 0;
  }
  else
  {
    Parameter = Process;
    MinimumRequiredStackSizeQueryProcessStartKey = SecGetMinimumRequiredStackSizeQueryProcessStartKey();
    v5 = KeExpandKernelStackAndCalloutEx(
           SecQueryProcessStartKeyCallout,
           &Parameter,
           MinimumRequiredStackSizeQueryProcessStartKey,
           0,
           0);
    if ( v5 >= 0 )
    {
      v5 = v11;
      v4 = v10;
      goto LABEL_7;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000add8  mov     r11, rsp
0x14000addb  mov     [r11+18h], rbx
0x14000addf  mov     [r11+20h], rsi
0x14000ade3  push    rdi
0x14000ade4  sub     rsp, 50h
0x14000ade8  mov     rax, cs:__security_cookie
0x14000adef  xor     rax, rsp
0x14000adf2  mov     [rsp+58h+var_10], rax
0x14000adf7  mov     rax, cs:qword_140020020
0x14000adfe  mov     rdi, rdx
0x14000ae01  mov     qword ptr [r11-20h], 0
0x14000ae09  mov     rsi, rcx
0x14000ae0c  mov     qword ptr [r11-18h], 0
0x14000ae14  test    rax, rax
0x14000ae17  jz      short loc_14000AE23
0x14000ae19  call    cs:__guard_dispatch_icall_fptr
0x14000ae1f  xor     ecx, ecx
0x14000ae21  jmp     short loc_14000AE9D
0x14000ae23  call    KclIsWindows8
0x14000ae28  test    al, al
0x14000ae2a  jz      short loc_14000AE5D
0x14000ae2c  mov     rcx, rsi; Process
0x14000ae2f  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14000ae36  nop     dword ptr [rax+rax+00h]
0x14000ae3b  mov     rcx, rsi; Process
0x14000ae3e  mov     rbx, rax
0x14000ae41  call    cs:__imp_PsGetProcessId
0x14000ae48  nop     dword ptr [rax+rax+00h]
0x14000ae4d  mov     ecx, eax
0x14000ae4f  shl     rcx, 20h
0x14000ae53  xor     rcx, rbx
0x14000ae56  mov     [rdi], rcx
0x14000ae59  xor     ecx, ecx
0x14000ae5b  jmp     short loc_14000AEA0
0x14000ae5d  mov     [rsp+58h+Parameter], rsi
0x14000ae62  call    SecGetMinimumRequiredStackSizeQueryProcessStartKey
0x14000ae67  mov     r8d, eax; Size
0x14000ae6a  lea     rdx, [rsp+58h+Parameter]; Parameter
0x14000ae6f  xor     r9d, r9d; Wait
0x14000ae72  mov     [rsp+58h+Context], 0; Context
0x14000ae7b  lea     rcx, SecQueryProcessStartKeyCallout; Callout
0x14000ae82  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14000ae89  nop     dword ptr [rax+rax+00h]
0x14000ae8e  mov     ecx, eax
0x14000ae90  test    eax, eax
0x14000ae92  js      short loc_14000AEA0
0x14000ae94  mov     ecx, dword ptr [rsp+58h+var_18]
0x14000ae98  mov     rax, [rsp+58h+var_20]
0x14000ae9d  mov     [rdi], rax
0x14000aea0  mov     eax, ecx
0x14000aea2  mov     rcx, [rsp+58h+var_10]
0x14000aea7  xor     rcx, rsp; StackCookie
0x14000aeaa  call    __security_check_cookie
0x14000aeaf  mov     rbx, [rsp+58h+arg_10]
0x14000aeb4  mov     rsi, [rsp+58h+arg_18]
0x14000aeb9  add     rsp, 50h
0x14000aebd  pop     rdi
0x14000aebe  retn
```
