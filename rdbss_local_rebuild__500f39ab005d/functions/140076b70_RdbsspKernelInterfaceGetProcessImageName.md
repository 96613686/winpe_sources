# RdbsspKernelInterfaceGetProcessImageName

- ea: `0x140076b70`
- end: `0x140076bc3`
- name: `RdbsspKernelInterfaceGetProcessImageName`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140076b70`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14007fb2a`
- `ntoskrnl!ExAllocatePool2` at `0x14007fb2a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14007fb64`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14007fb64`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b92a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fb93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b92a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fb93`
- `ntoskrnl!PsIsSystemProcess` at `0x140076b88`
- `ntoskrnl!PsIsSystemProcess` at `0x140076b88`
- `ntoskrnl!SeLocateProcessImageName` at `0x140076ba2`
- `ntoskrnl!SeLocateProcessImageName` at `0x140076ba2`

## pseudocode

```c
__int64 __fastcall RdbsspKernelInterfaceGetProcessImageName(__int64 a1, struct _KPROCESS *a2, PUNICODE_STRING *a3)
{
  NTSTATUS appended; // ebx
  UNICODE_STRING *Pool2; // rax
  UNICODE_STRING *v8; // rsi

  if ( (unsigned __int8)PsIsSystemProcess(a2) )
  {
    Pool2 = (UNICODE_STRING *)ExAllocatePool2(256, 28, 1229677650);
    v8 = Pool2;
    if ( Pool2 )
    {
      Pool2->MaximumLength = 12;
      Pool2->Buffer = &Pool2[1].Length;
      appended = RtlAppendUnicodeToString(Pool2, L"System");
      if ( appended >= 0 )
        *a3 = v8;
    }
    else
    {
      appended = -1073741670;
    }
    if ( appended < 0 && v8 )
      ExFreePoolWithTag(v8, 0);
  }
  else
  {
    return (unsigned int)SeLocateProcessImageName(a2, a3);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140076b70  mov     [rsp+arg_0], rbx
0x140076b75  mov     [rsp+arg_8], rsi
0x140076b7a  push    rdi
0x140076b7b  sub     rsp, 30h
0x140076b7f  mov     rdi, r8
0x140076b82  mov     rbx, rdx
0x140076b85  mov     rcx, rdx
0x140076b88  call    cs:__imp_PsIsSystemProcess
0x140076b8f  nop     dword ptr [rax+rax+00h]
0x140076b94  test    al, al
0x140076b96  jnz     loc_14007FB06
0x140076b9c  mov     rdx, rdi; pImageFileName
0x140076b9f  mov     rcx, rbx; Process
0x140076ba2  call    cs:__imp_SeLocateProcessImageName
0x140076ba9  nop     dword ptr [rax+rax+00h]
0x140076bae  mov     ebx, eax
0x140076bb0  mov     eax, ebx
0x140076bb2  mov     rbx, [rsp+38h+arg_0]
0x140076bb7  mov     rsi, [rsp+38h+arg_8]
0x140076bbc  add     rsp, 30h
0x140076bc0  pop     rdi
0x140076bc1  retn
0x14007b910  push    rbp
0x14007b912  sub     rsp, 20h
0x14007b916  mov     rbp, rdx
0x14007b919  cmp     dword ptr [rbp+20h], 0
0x14007b91d  jge     short loc_14007B93E
0x14007b91f  mov     rcx, [rbp+28h]; P
0x14007b923  test    rcx, rcx
0x14007b926  jz      short loc_14007B93E
0x14007b928  xor     edx, edx; Tag
0x14007b92a  call    cs:__imp_ExFreePoolWithTag
0x14007b931  nop     dword ptr [rax+rax+00h]
0x14007b936  mov     qword ptr [rbp+28h], 0
0x14007b93e  add     rsp, 20h
0x14007b942  pop     rbp
0x14007b943  retn
0x14007fb06  xor     eax, eax
0x14007fb08  mov     [rsp+38h+var_18], eax
0x14007fb0c  mov     [rsp+38h+var_10], rax
0x14007fb11  mov     ebx, 0Ch
0x14007fb16  mov     [rsp+38h+arg_18], ebx
0x14007fb1a  mov     edx, 1Ch
0x14007fb1f  mov     ecx, 100h
0x14007fb24  mov     r8d, 494B6452h
0x14007fb2a  call    cs:__imp_ExAllocatePool2
0x14007fb31  nop     dword ptr [rax+rax+00h]
0x14007fb36  mov     rsi, rax
0x14007fb39  mov     [rsp+38h+var_10], rax
0x14007fb3e  test    rax, rax
0x14007fb41  jnz     short loc_14007FB4E
0x14007fb43  mov     ebx, 0C000009Ah
0x14007fb48  mov     [rsp+38h+var_18], ebx
0x14007fb4c  jmp     short loc_14007FB7D
0x14007fb4e  mov     [rax+2], bx
0x14007fb52  add     rax, 10h
0x14007fb56  mov     [rsi+8], rax
0x14007fb5a  lea     rdx, aSystem; "System"
0x14007fb61  mov     rcx, rsi; Destination
0x14007fb64  call    cs:__imp_RtlAppendUnicodeToString
0x14007fb6b  nop     dword ptr [rax+rax+00h]
0x14007fb70  mov     ebx, eax
0x14007fb72  mov     [rsp+38h+var_18], eax
0x14007fb76  test    eax, eax
0x14007fb78  js      short loc_14007FB7D
0x14007fb7a  mov     [rdi], rsi
0x14007fb7d  test    ebx, ebx
0x14007fb7f  jns     loc_140076BB0
0x14007fb85  test    rsi, rsi
0x14007fb88  jz      loc_140076BB0
0x14007fb8e  xor     edx, edx; Tag
0x14007fb90  mov     rcx, rsi; P
0x14007fb93  call    cs:__imp_ExFreePoolWithTag
0x14007fb9a  nop     dword ptr [rax+rax+00h]
0x14007fb9f  nop
0x14007fba0  jmp     loc_140076BB0
```
