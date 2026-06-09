# UtilIsNamedEventSet

- ea: `0x18003b3a8`
- end: `0x18003b453`
- name: `UtilIsNamedEventSet`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x180014598`

## callees

- `0x18003b3a8`

## import_xrefs

- `ntdll!NtOpenEvent` at `0x18003b3f6`
- `ntdll!NtOpenEvent` at `0x18003b3f6`
- `ntdll!NtClose` at `0x18003b42b`
- `ntdll!NtClose` at `0x18003b42b`
- `ntdll!NtQueryEvent` at `0x18003b41f`
- `ntdll!NtQueryEvent` at `0x18003b41f`

## pseudocode

```c
int __fastcall UtilIsNamedEventSet(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // eax
  NTSTATUS v3; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+70h] [rbp+10h] BYREF
  __int64 EventInformation; // [rsp+78h] [rbp+18h] BYREF

  ObjectAttributes.ObjectName = a1;
  EventHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  memset(&ObjectAttributes.Attributes, 0, 24);
  EventInformation = 0;
  v1 = NtOpenEvent(&EventHandle, 1u, &ObjectAttributes);
  if ( v1 < 0 )
    return v1 | 0x10000000;
  v3 = NtQueryEvent(EventHandle, EventBasicInformation, &EventInformation, 8u, 0);
  NtClose(EventHandle);
  if ( v3 >= 0 )
    return HIDWORD(EventInformation) == 0;
  else
    return v3 | 0x10000000;
}

```

## disassembly

```asm
0x18003b3a8  mov     [rsp-8+arg_10], rbx
0x18003b3ad  push    rbp
0x18003b3ae  mov     rbp, rsp
0x18003b3b1  sub     rsp, 60h
0x18003b3b5  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x18003b3b9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003b3bd  xorps   xmm0, xmm0
0x18003b3c0  mov     [rbp+EventHandle], 0
0x18003b3c8  lea     rcx, [rbp+EventHandle]; EventHandle
0x18003b3cc  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18003b3d4  mov     edx, 1; DesiredAccess
0x18003b3d9  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18003b3e1  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18003b3e6  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x18003b3ee  mov     [rbp+EventInformation], 0
0x18003b3f6  call    cs:__imp_NtOpenEvent
0x18003b3fc  test    eax, eax
0x18003b3fe  jns     short loc_18003B406
0x18003b400  bts     eax, 1Ch
0x18003b404  jmp     short loc_18003B445
0x18003b406  mov     rcx, [rbp+EventHandle]; EventHandle
0x18003b40a  lea     r8, [rbp+EventInformation]; EventInformation
0x18003b40e  mov     r9d, 8; EventInformationLength
0x18003b414  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x18003b41d  xor     edx, edx; EventInformationClass
0x18003b41f  call    cs:__imp_NtQueryEvent
0x18003b425  mov     rcx, [rbp+EventHandle]; Handle
0x18003b429  mov     ebx, eax
0x18003b42b  call    cs:__imp_NtClose
0x18003b431  test    ebx, ebx
0x18003b433  jns     short loc_18003B43D
0x18003b435  bts     ebx, 1Ch
0x18003b439  mov     eax, ebx
0x18003b43b  jmp     short loc_18003B445
0x18003b43d  xor     eax, eax
0x18003b43f  cmp     dword ptr [rbp+EventInformation+4], eax
0x18003b442  setz    al
0x18003b445  mov     rbx, [rsp+60h+arg_10]
0x18003b44d  add     rsp, 60h
0x18003b451  pop     rbp
0x18003b452  retn
```
