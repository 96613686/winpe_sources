# PsmpDuplicateHandleForClientProcess

- ea: `0x180024070`
- end: `0x180024148`
- name: `PsmpDuplicateHandleForClientProcess`
- size: `216`
- prototype: `__int64 __fastcall(unsigned int, void *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000dbd0`

## callees

- `0x180024070`

## import_xrefs

- `ntdll!NtDuplicateObject` at `0x180024113`
- `ntdll!NtDuplicateObject` at `0x180024113`
- `ntdll!NtClose` at `0x180024134`
- `ntdll!NtClose` at `0x180024134`
- `ntdll!NtOpenProcess` at `0x1800240d8`
- `ntdll!NtOpenProcess` at `0x1800240d8`

## pseudocode

```c
__int64 __fastcall PsmpDuplicateHandleForClientProcess(unsigned int a1, void *a2, void **a3)
{
  NTSTATUS v5; // ebx
  void *ProcessHandle; // [rsp+40h] [rbp-19h] BYREF
  _CLIENT_ID ClientId; // [rsp+48h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-1h] BYREF
  void *TargetHandle; // [rsp+D8h] [rbp+7Fh] BYREF

  TargetHandle = 0;
  ClientId.UniqueThread = 0;
  ClientId.UniqueProcess = (HANDLE)a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  ProcessHandle = 0;
  v5 = NtOpenProcess(&ProcessHandle, 0x40u, &ObjectAttributes, &ClientId);
  if ( v5 >= 0 )
  {
    TargetHandle = 0;
    v5 = NtDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, a2, ProcessHandle, &TargetHandle, 0, 0, 2u);
    if ( v5 >= 0 )
      *a3 = TargetHandle;
  }
  if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    NtClose(ProcessHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180024070  push    rbp
0x180024072  push    rbx
0x180024073  push    rsi
0x180024074  push    rdi
0x180024075  lea     rbp, [rsp-3Fh]
0x18002407a  sub     rsp, 98h
0x180024081  xor     eax, eax
0x180024083  mov     [rbp+57h+TargetHandle], 0
0x18002408b  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], rax
0x18002408f  lea     r9, [rbp+57h+ClientId]; ClientId
0x180024093  mov     [rbp+57h+ClientId.UniqueThread], rax
0x180024097  mov     rdi, r8
0x18002409a  mov     eax, ecx
0x18002409c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800240a0  mov     rsi, rdx
0x1800240a3  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x1800240a7  xorps   xmm0, xmm0
0x1800240aa  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800240b2  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1800240b6  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800240be  mov     edx, 40h ; '@'; DesiredAccess
0x1800240c3  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x1800240cb  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800240d0  mov     [rbp+57h+ProcessHandle], 0
0x1800240d8  call    cs:__imp_NtOpenProcess
0x1800240de  mov     ebx, eax
0x1800240e0  test    eax, eax
0x1800240e2  js      short loc_180024126
0x1800240e4  mov     r8, [rbp+57h+ProcessHandle]; TargetProcessHandle
0x1800240e8  lea     r9, [rbp+57h+TargetHandle]; TargetHandle
0x1800240ec  mov     [rsp+0B0h+Options], 2; Options
0x1800240f4  mov     rdx, rsi; SourceHandle
0x1800240f7  mov     [rsp+0B0h+HandleAttributes], 0; HandleAttributes
0x1800240ff  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x180024103  mov     [rsp+0B0h+DesiredAccess], 0; DesiredAccess
0x18002410b  mov     [rbp+57h+TargetHandle], 0
0x180024113  call    cs:__imp_NtDuplicateObject
0x180024119  mov     ebx, eax
0x18002411b  test    eax, eax
0x18002411d  js      short loc_180024126
0x18002411f  mov     rax, [rbp+57h+TargetHandle]
0x180024123  mov     [rdi], rax
0x180024126  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x18002412a  lea     rax, [rcx-1]
0x18002412e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024132  ja      short loc_18002413A
0x180024134  call    cs:__imp_NtClose
0x18002413a  mov     eax, ebx
0x18002413c  add     rsp, 98h
0x180024143  pop     rdi
0x180024144  pop     rsi
0x180024145  pop     rbx
0x180024146  pop     rbp
0x180024147  retn
```
