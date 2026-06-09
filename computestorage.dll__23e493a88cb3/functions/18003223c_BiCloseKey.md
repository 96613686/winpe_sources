# BiCloseKey

- ea: `0x18003223c`
- end: `0x1800322de`
- name: `BiCloseKey`
- size: `162`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `16`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002c3ec`
- `0x18002c6b4`
- `0x18002d374`
- `0x18002d9b0`
- `0x18002dcec`
- `0x18002e0a0`
- `0x18002e3dc`
- `0x18002e4a8`
- `0x18002e4fc`
- `0x18002e808`
- `0x18003290c`
- `0x180033c68`
- `0x180033dd0`
- `0x180034c64`
- `0x180034f24`
- `0x1800358b8`

## callees

- `0x18003223c`
- `0x180032604`
- `0x180039298`
- `0x18003b918`

## import_xrefs

- `ntdll!ZwSetSecurityObject` at `0x180032281`
- `ntdll!ZwSetSecurityObject` at `0x180032281`
- `ntdll!ZwClose` at `0x1800322c1`
- `ntdll!ZwClose` at `0x1800322c1`
- `ntdll!RtlFreeHeap` at `0x18003229f`
- `ntdll!RtlFreeHeap` at `0x18003229f`

## pseudocode

```c
NTSTATUS __fastcall BiCloseKey(unsigned __int64 Handle)
{
  struct _ACL *KeySecurityDescriptor; // rax
  struct _ACL *v3; // rsi

  KeySecurityDescriptor = BiCreateKeySecurityDescriptor(0x60019u);
  v3 = KeySecurityDescriptor;
  if ( KeySecurityDescriptor )
  {
    if ( (Handle & 1) != 0 )
      ORSetKeySecurity(Handle & 0xFFFFFFFFFFFFFFFEuLL, 4u, KeySecurityDescriptor);
    else
      ZwSetSecurityObject((HANDLE)Handle, 4u, KeySecurityDescriptor);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  }
  if ( (Handle & 1) != 0 )
    return ORCloseKey(Handle & 0xFFFFFFFFFFFFFFFEuLL);
  else
    return ZwClose((HANDLE)Handle);
}

```

## disassembly

```asm
0x18003223c  mov     [rsp+arg_0], rbx
0x180032241  mov     [rsp+arg_8], rsi
0x180032246  push    rdi
0x180032247  sub     rsp, 20h
0x18003224b  mov     rbx, rcx
0x18003224e  mov     ecx, 60019h; AccessMask
0x180032253  call    BiCreateKeySecurityDescriptor
0x180032258  mov     rdi, rbx
0x18003225b  mov     rsi, rax
0x18003225e  and     edi, 1
0x180032261  test    rax, rax
0x180032264  jz      short loc_1800322AB
0x180032266  mov     rcx, rbx; Handle
0x180032269  mov     r8, rax; SecurityDescriptor
0x18003226c  mov     edx, 4; SecurityInformation
0x180032271  test    rdi, rdi
0x180032274  jz      short loc_180032281
0x180032276  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18003227a  call    ORSetKeySecurity
0x18003227f  jmp     short loc_18003228D
0x180032281  call    cs:__imp_ZwSetSecurityObject
0x180032288  nop     dword ptr [rax+rax+00h]
0x18003228d  mov     rcx, gs:60h
0x180032296  mov     r8, rsi; P
0x180032299  xor     edx, edx; Flags
0x18003229b  mov     rcx, [rcx+30h]; HeapHandle
0x18003229f  call    cs:__imp_RtlFreeHeap
0x1800322a6  nop     dword ptr [rax+rax+00h]
0x1800322ab  test    rdi, rdi
0x1800322ae  jz      short loc_1800322BE
0x1800322b0  and     rbx, 0FFFFFFFFFFFFFFFEh
0x1800322b4  mov     rcx, rbx
0x1800322b7  call    ORCloseKey
0x1800322bc  jmp     short loc_1800322CD
0x1800322be  mov     rcx, rbx; Handle
0x1800322c1  call    cs:__imp_ZwClose
0x1800322c8  nop     dword ptr [rax+rax+00h]
0x1800322cd  mov     rbx, [rsp+28h+arg_0]
0x1800322d2  mov     rsi, [rsp+28h+arg_8]
0x1800322d7  add     rsp, 20h
0x1800322db  pop     rdi
0x1800322dc  retn
```
