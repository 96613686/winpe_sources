# KclSetWmiObjectSecurity

- ea: `0x140040528`
- end: `0x14004060e`
- name: `KclSetWmiObjectSecurity`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002b33c`

## callees

- `0x140011650`
- `0x140040528`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14004059d`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14004059d`
- `ntoskrnl!IoWMIOpenBlock` at `0x140040560`
- `ntoskrnl!IoWMIOpenBlock` at `0x140040560`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400405b3`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400405b3`
- `ntoskrnl!ZwClose` at `0x1400405cb`
- `ntoskrnl!ZwClose` at `0x1400405cb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400405ea`
- `ntoskrnl!ObfDereferenceObject` at `0x1400405ea`

## pseudocode

```c
__int64 __fastcall KclSetWmiObjectSecurity(const GUID *a1, SECURITY_INFORMATION a2, void *a3)
{
  NTSTATUS v5; // ebx
  HANDLE Handle; // [rsp+40h] [rbp-38h] BYREF
  PVOID DataBlockObject; // [rsp+48h] [rbp-30h] BYREF

  DataBlockObject = 0;
  Handle = 0;
  v5 = IoWMIOpenBlock(a1, 0x40000u, &DataBlockObject);
  if ( v5 >= 0 )
  {
    ObOpenObjectByPointer(DataBlockObject, 0x200u, 0, 0x40000u, 0, 0, &Handle);
    v5 = ZwSetSecurityObject(Handle, a2, a3);
  }
  if ( Handle )
  {
    ZwClose(Handle);
    Handle = 0;
  }
  if ( DataBlockObject )
    ObfDereferenceObject(DataBlockObject);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140040528  push    rbx
0x14004052a  push    rsi
0x14004052b  push    rdi
0x14004052c  sub     rsp, 60h
0x140040530  mov     rax, cs:__security_cookie
0x140040537  xor     rax, rsp
0x14004053a  mov     [rsp+78h+var_28], rax
0x14004053f  mov     rsi, r8
0x140040542  mov     [rsp+78h+DataBlockObject], 0
0x14004054b  mov     edi, edx
0x14004054d  mov     [rsp+78h+var_38], 0
0x140040556  lea     r8, [rsp+78h+DataBlockObject]; DataBlockObject
0x14004055b  mov     edx, 40000h; DesiredAccess
0x140040560  call    cs:__imp_IoWMIOpenBlock
0x140040567  nop     dword ptr [rax+rax+00h]
0x14004056c  mov     ebx, eax
0x14004056e  test    eax, eax
0x140040570  js      short loc_1400405C1
0x140040572  mov     rcx, [rsp+78h+DataBlockObject]; Object
0x140040577  lea     rax, [rsp+78h+var_38]
0x14004057c  mov     [rsp+78h+Handle], rax; Handle
0x140040581  mov     r9d, 40000h; DesiredAccess
0x140040587  mov     [rsp+78h+AccessMode], 0; AccessMode
0x14004058c  xor     r8d, r8d; PassedAccessState
0x14004058f  mov     edx, 200h; HandleAttributes
0x140040594  mov     [rsp+78h+ObjectType], 0; ObjectType
0x14004059d  call    cs:__imp_ObOpenObjectByPointer
0x1400405a4  nop     dword ptr [rax+rax+00h]
0x1400405a9  mov     rcx, [rsp+78h+var_38]; Handle
0x1400405ae  mov     r8, rsi; SecurityDescriptor
0x1400405b1  mov     edx, edi; SecurityInformation
0x1400405b3  call    cs:__imp_ZwSetSecurityObject
0x1400405ba  nop     dword ptr [rax+rax+00h]
0x1400405bf  mov     ebx, eax
0x1400405c1  mov     rcx, [rsp+78h+var_38]; Handle
0x1400405c6  test    rcx, rcx
0x1400405c9  jz      short loc_1400405E0
0x1400405cb  call    cs:__imp_ZwClose
0x1400405d2  nop     dword ptr [rax+rax+00h]
0x1400405d7  mov     [rsp+78h+var_38], 0
0x1400405e0  mov     rcx, [rsp+78h+DataBlockObject]; Object
0x1400405e5  test    rcx, rcx
0x1400405e8  jz      short loc_1400405F6
0x1400405ea  call    cs:__imp_ObfDereferenceObject
0x1400405f1  nop     dword ptr [rax+rax+00h]
0x1400405f6  mov     eax, ebx
0x1400405f8  mov     rcx, [rsp+78h+var_28]
0x1400405fd  xor     rcx, rsp; StackCookie
0x140040600  call    __security_check_cookie
0x140040605  add     rsp, 60h
0x140040609  pop     rdi
0x14004060a  pop     rsi
0x14004060b  pop     rbx
0x14004060c  retn
```
