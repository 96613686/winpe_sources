# ndisCreateThread

- ea: `0x1400c0aa0`
- end: `0x1400c0bde`
- name: `ndisCreateThread`
- size: `318`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400c09dc`
- `0x1400c0d08`

## callees

- `0x140028e00`
- `0x1400c0aa0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400c0bc3`
- `ntoskrnl!ZwClose` at `0x1400c0bc3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400c0b98`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400c0b98`
- `ntoskrnl!PsCreateSystemThread` at `0x1400c0b14`
- `ntoskrnl!PsCreateSystemThread` at `0x1400c0b14`
- `ntoskrnl!PsThreadType` at `0x1400c0b68`
- `ntoskrnl!KeSetPriorityThread` at `0x1400c0bb3`
- `ntoskrnl!KeSetPriorityThread` at `0x1400c0bb3`

## pseudocode

```c
__int64 __fastcall ndisCreateThread(__int64 a1, void *a2, KPRIORITY a3, PVOID *a4)
{
  int v6; // edx
  NTSTATUS v7; // ebx
  NTSTATUS v8; // eax
  struct _KTHREAD *v9; // rcx
  PVOID Object; // [rsp+48h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-1h] BYREF
  void *ThreadHandle; // [rsp+B8h] [rbp+67h] BYREF

  ThreadHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = PsCreateSystemThread(
         &ThreadHandle,
         0x1FFFFFu,
         &ObjectAttributes,
         0,
         0,
         (PKSTART_ROUTINE)ndisReceiveWorkerThread,
         a2);
  if ( v7 >= 0 )
  {
    Object = 0;
    v8 = ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, (POBJECT_TYPE)PsThreadType, 0, &Object, 0);
    v9 = (struct _KTHREAD *)Object;
    v7 = v8;
    *a4 = Object;
    if ( a3 )
      KeSetPriorityThread(v9, a3);
    ZwClose(ThreadHandle);
  }
  else if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v6,
      12,
      10,
      (struct _GUID *)&WPP_2fb632d9e69632cc5880b19a4ac60799_Traceguids,
      v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400c0aa0  mov     r11, rsp
0x1400c0aa3  mov     [r11+8], rcx
0x1400c0aa7  push    rbp
0x1400c0aa8  push    rbx
0x1400c0aa9  push    rsi
0x1400c0aaa  push    rdi
0x1400c0aab  lea     rbp, [r11-5Fh]
0x1400c0aaf  sub     rsp, 88h
0x1400c0ab6  mov     [r11-78h], rdx
0x1400c0aba  lea     rax, ndisReceiveWorkerThread
0x1400c0ac1  mov     rsi, r9
0x1400c0ac4  mov     [r11-80h], rax
0x1400c0ac8  mov     edi, r8d
0x1400c0acb  mov     [rsp+0A0h+ClientId], 0; ClientId
0x1400c0ad4  xorps   xmm0, xmm0
0x1400c0ad7  mov     [rbp+57h+ThreadHandle], 0
0x1400c0adf  xor     r9d, r9d; ProcessHandle
0x1400c0ae2  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400c0aea  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400c0aee  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x1400c0af6  mov     edx, 1FFFFFh; DesiredAccess
0x1400c0afb  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400c0b03  lea     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x1400c0b07  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x1400c0b0f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400c0b14  call    cs:__imp_PsCreateSystemThread
0x1400c0b1b  nop     dword ptr [rax+rax+00h]
0x1400c0b20  mov     ebx, eax
0x1400c0b22  test    eax, eax
0x1400c0b24  jns     short loc_1400C0B68
0x1400c0b26  lea     rax, WPP_RECORDER_INITIALIZED
0x1400c0b2d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c0b34  jz      loc_1400C0BCF
0x1400c0b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c0b41  lea     rax, WPP_2fb632d9e69632cc5880b19a4ac60799_Traceguids
0x1400c0b48  mov     r9d, 0Ah; int
0x1400c0b4e  mov     [rsp+28h], ebx; char
0x1400c0b52  mov     dl, 2; int
0x1400c0b54  mov     [rsp+0A0h+ClientId], rax; struct _GUID *
0x1400c0b59  mov     rcx, [rcx+40h]; int
0x1400c0b5d  lea     r8d, [r9+2]; int
0x1400c0b61  call    WPP_RECORDER_SF_d
0x1400c0b66  jmp     short loc_1400C0BCF
0x1400c0b68  mov     r8, cs:__imp_PsThreadType
0x1400c0b6f  lea     rax, [rbp+57h+Object]
0x1400c0b73  mov     rcx, [rbp+57h+ThreadHandle]; Handle
0x1400c0b77  xor     r9d, r9d; AccessMode
0x1400c0b7a  mov     qword ptr [rsp+28h], 0; HandleInformation
0x1400c0b83  mov     edx, 1FFFFFh; DesiredAccess
0x1400c0b88  mov     [rbp+57h+Object], 0
0x1400c0b90  mov     r8, [r8]; ObjectType
0x1400c0b93  mov     [rsp+0A0h+ClientId], rax; Object
0x1400c0b98  call    cs:__imp_ObReferenceObjectByHandle
0x1400c0b9f  nop     dword ptr [rax+rax+00h]
0x1400c0ba4  mov     rcx, [rbp+57h+Object]; Thread
0x1400c0ba8  mov     ebx, eax
0x1400c0baa  mov     [rsi], rcx
0x1400c0bad  test    edi, edi
0x1400c0baf  jz      short loc_1400C0BBF
0x1400c0bb1  mov     edx, edi; Priority
0x1400c0bb3  call    cs:__imp_KeSetPriorityThread
0x1400c0bba  nop     dword ptr [rax+rax+00h]
0x1400c0bbf  mov     rcx, [rbp+57h+ThreadHandle]; Handle
0x1400c0bc3  call    cs:__imp_ZwClose
0x1400c0bca  nop     dword ptr [rax+rax+00h]
0x1400c0bcf  mov     eax, ebx
0x1400c0bd1  add     rsp, 88h
0x1400c0bd8  pop     rdi
0x1400c0bd9  pop     rsi
0x1400c0bda  pop     rbx
0x1400c0bdb  pop     rbp
0x1400c0bdc  retn
```
