# ndisCreateThread

- ea: `0x1400c5ed0`
- end: `0x1400c600e`
- name: `ndisCreateThread`
- size: `318`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400c5e0c`
- `0x1400c6138`

## callees

- `0x14001cf60`
- `0x1400c5ed0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400c5ff3`
- `ntoskrnl!ZwClose` at `0x1400c5ff3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400c5fc8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400c5fc8`
- `ntoskrnl!PsCreateSystemThread` at `0x1400c5f44`
- `ntoskrnl!PsCreateSystemThread` at `0x1400c5f44`
- `ntoskrnl!PsThreadType` at `0x1400c5f98`
- `ntoskrnl!KeSetPriorityThread` at `0x1400c5fe3`
- `ntoskrnl!KeSetPriorityThread` at `0x1400c5fe3`

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
0x1400c5ed0  mov     r11, rsp
0x1400c5ed3  mov     [r11+8], rcx
0x1400c5ed7  push    rbp
0x1400c5ed8  push    rbx
0x1400c5ed9  push    rsi
0x1400c5eda  push    rdi
0x1400c5edb  lea     rbp, [r11-5Fh]
0x1400c5edf  sub     rsp, 88h
0x1400c5ee6  mov     [r11-78h], rdx
0x1400c5eea  lea     rax, ndisReceiveWorkerThread
0x1400c5ef1  mov     rsi, r9
0x1400c5ef4  mov     [r11-80h], rax
0x1400c5ef8  mov     edi, r8d
0x1400c5efb  mov     [rsp+0A0h+ClientId], 0; ClientId
0x1400c5f04  xorps   xmm0, xmm0
0x1400c5f07  mov     [rbp+57h+ThreadHandle], 0
0x1400c5f0f  xor     r9d, r9d; ProcessHandle
0x1400c5f12  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400c5f1a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400c5f1e  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x1400c5f26  mov     edx, 1FFFFFh; DesiredAccess
0x1400c5f2b  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400c5f33  lea     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x1400c5f37  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x1400c5f3f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400c5f44  call    cs:__imp_PsCreateSystemThread
0x1400c5f4b  nop     dword ptr [rax+rax+00h]
0x1400c5f50  mov     ebx, eax
0x1400c5f52  test    eax, eax
0x1400c5f54  jns     short loc_1400C5F98
0x1400c5f56  lea     rax, WPP_RECORDER_INITIALIZED
0x1400c5f5d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c5f64  jz      loc_1400C5FFF
0x1400c5f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c5f71  lea     rax, WPP_2fb632d9e69632cc5880b19a4ac60799_Traceguids
0x1400c5f78  mov     r9d, 0Ah; int
0x1400c5f7e  mov     [rsp+28h], ebx; char
0x1400c5f82  mov     dl, 2; int
0x1400c5f84  mov     [rsp+0A0h+ClientId], rax; struct _GUID *
0x1400c5f89  mov     rcx, [rcx+40h]; int
0x1400c5f8d  lea     r8d, [r9+2]; int
0x1400c5f91  call    WPP_RECORDER_SF_d
0x1400c5f96  jmp     short loc_1400C5FFF
0x1400c5f98  mov     r8, cs:__imp_PsThreadType
0x1400c5f9f  lea     rax, [rbp+57h+Object]
0x1400c5fa3  mov     rcx, [rbp+57h+ThreadHandle]; Handle
0x1400c5fa7  xor     r9d, r9d; AccessMode
0x1400c5faa  mov     qword ptr [rsp+28h], 0; HandleInformation
0x1400c5fb3  mov     edx, 1FFFFFh; DesiredAccess
0x1400c5fb8  mov     [rbp+57h+Object], 0
0x1400c5fc0  mov     r8, [r8]; ObjectType
0x1400c5fc3  mov     [rsp+0A0h+ClientId], rax; Object
0x1400c5fc8  call    cs:__imp_ObReferenceObjectByHandle
0x1400c5fcf  nop     dword ptr [rax+rax+00h]
0x1400c5fd4  mov     rcx, [rbp+57h+Object]; Thread
0x1400c5fd8  mov     ebx, eax
0x1400c5fda  mov     [rsi], rcx
0x1400c5fdd  test    edi, edi
0x1400c5fdf  jz      short loc_1400C5FEF
0x1400c5fe1  mov     edx, edi; Priority
0x1400c5fe3  call    cs:__imp_KeSetPriorityThread
0x1400c5fea  nop     dword ptr [rax+rax+00h]
0x1400c5fef  mov     rcx, [rbp+57h+ThreadHandle]; Handle
0x1400c5ff3  call    cs:__imp_ZwClose
0x1400c5ffa  nop     dword ptr [rax+rax+00h]
0x1400c5fff  mov     eax, ebx
0x1400c6001  add     rsp, 88h
0x1400c6008  pop     rdi
0x1400c6009  pop     rsi
0x1400c600a  pop     rbx
0x1400c600b  pop     rbp
0x1400c600c  retn
```
