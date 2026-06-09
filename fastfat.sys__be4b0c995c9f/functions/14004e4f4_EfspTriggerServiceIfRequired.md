# EfspTriggerServiceIfRequired

- ea: `0x14004e4f4`
- end: `0x14004e55a`
- name: `EfspTriggerServiceIfRequired`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x14004da14`

## callees

- `0x14004e4f4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14004e545`
- `ntoskrnl!ZwClose` at `0x14004e545`
- `ntoskrnl!PsCreateSystemThread` at `0x14004e52e`
- `ntoskrnl!PsCreateSystemThread` at `0x14004e52e`

## pseudocode

```c
__int64 EfspTriggerServiceIfRequired()
{
  NTSTATUS v0; // ebx
  HANDLE Handle; // [rsp+50h] [rbp+8h] BYREF

  Handle = 0;
  v0 = PsCreateSystemThread(&Handle, 0x1FFFFFu, 0, 0, 0, (PKSTART_ROUTINE)EfspCheckEfsPolicy, 0);
  if ( v0 >= 0 )
    ZwClose(Handle);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14004e4f4  mov     r11, rsp
0x14004e4f7  push    rbx
0x14004e4f8  sub     rsp, 40h
0x14004e4fc  mov     qword ptr [r11-18h], 0
0x14004e504  lea     rax, EfspCheckEfsPolicy
0x14004e50b  mov     [r11-20h], rax
0x14004e50f  lea     rcx, [r11+8]; ThreadHandle
0x14004e513  xor     r9d, r9d; ProcessHandle
0x14004e516  mov     qword ptr [r11-28h], 0
0x14004e51e  xor     r8d, r8d; ObjectAttributes
0x14004e521  mov     qword ptr [r11+8], 0
0x14004e529  mov     edx, 1FFFFFh; DesiredAccess
0x14004e52e  call    cs:__imp_PsCreateSystemThread
0x14004e535  nop     dword ptr [rax+rax+00h]
0x14004e53a  mov     ebx, eax
0x14004e53c  test    eax, eax
0x14004e53e  js      short loc_14004E551
0x14004e540  mov     rcx, [rsp+48h+Handle]; Handle
0x14004e545  call    cs:__imp_ZwClose
0x14004e54c  nop     dword ptr [rax+rax+00h]
0x14004e551  mov     eax, ebx
0x14004e553  add     rsp, 40h
0x14004e557  pop     rbx
0x14004e558  retn
```
