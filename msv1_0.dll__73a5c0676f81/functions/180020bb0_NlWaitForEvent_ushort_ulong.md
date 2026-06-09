# NlWaitForEvent(ushort *,ulong)

- ea: `0x180020bb0`
- end: `0x180020cde`
- name: `?NlWaitForEvent@@YAJPEAGK@Z`
- size: `302`
- prototype: `__int64 __fastcall(PCWSTR SourceString, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800205b4`
- `0x18003ef28`

## callees

- `0x180020bb0`
- `0x18002ee7c`

## import_xrefs

- `ntdll!NtOpenEvent` at `0x180020c4f`
- `ntdll!NtOpenEvent` at `0x180020c4f`
- `ntdll!NtCreateEvent` at `0x180020c2f`
- `ntdll!NtCreateEvent` at `0x180020c2f`
- `ntdll!NtWaitForSingleObject` at `0x180020ca3`
- `ntdll!NtWaitForSingleObject` at `0x180020ca3`
- `ntdll!NtClose` at `0x180020caf`
- `ntdll!NtClose` at `0x180020caf`
- `ntdll!RtlInitUnicodeString` at `0x180020bee`
- `ntdll!RtlInitUnicodeString` at `0x180020bee`

## pseudocode

```c
__int64 __fastcall NlWaitForEvent(PCWSTR SourceString, unsigned int a2)
{
  __int64 v2; // rdi
  NTSTATUS v3; // eax
  NTSTATUS v4; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+90h] [rbp+20h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+98h] [rbp+28h] BYREF

  v2 = a2;
  EventHandle = 0;
  Timeout.QuadPart = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtCreateEvent(&EventHandle, 0x100000u, &ObjectAttributes, NotificationEvent, 0);
  v4 = v3;
  if ( v3 >= 0 || v3 == -1073741771 && (v4 = NtOpenEvent(&EventHandle, 0x100000u, &ObjectAttributes), v4 >= 0) )
  {
    Timeout.QuadPart = -10000000 * v2;
    v4 = NtWaitForSingleObject(EventHandle, 0, &Timeout);
    NtClose(EventHandle);
    if ( v4 >= 0 )
    {
      if ( v4 != 258 )
        return 0;
      return (unsigned int)-1073741422;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids, (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180020bb0  mov     [rsp-8+arg_0], rbx
0x180020bb5  mov     [rsp-8+arg_8], rdi
0x180020bba  push    rbp
0x180020bbb  mov     rbp, rsp
0x180020bbe  sub     rsp, 70h
0x180020bc2  xorps   xmm0, xmm0
0x180020bc5  mov     edi, edx
0x180020bc7  mov     rdx, rcx; SourceString
0x180020bca  mov     [rbp+EventHandle], 0
0x180020bd2  lea     rcx, [rbp+DestinationString]; DestinationString
0x180020bd6  mov     qword ptr [rbp+Timeout], 0
0x180020bde  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180020be2  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180020be6  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180020bea  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180020bee  call    cs:__imp_RtlInitUnicodeString
0x180020bf4  lea     rax, [rbp+DestinationString]
0x180020bf8  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180020bff  xorps   xmm0, xmm0
0x180020c02  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180020c06  xor     r9d, r9d; EventType
0x180020c09  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180020c11  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180020c15  mov     [rbp+ObjectAttributes.Attributes], 0
0x180020c1c  mov     edx, 100000h; DesiredAccess
0x180020c21  mov     [rsp+70h+InitialState], 0; InitialState
0x180020c26  lea     rcx, [rbp+EventHandle]; EventHandle
0x180020c2a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180020c2f  call    cs:__imp_NtCreateEvent
0x180020c35  mov     ebx, eax
0x180020c37  test    eax, eax
0x180020c39  jns     short loc_180020C8E
0x180020c3b  cmp     eax, 0C0000035h
0x180020c40  jnz     short loc_180020C5B
0x180020c42  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180020c46  mov     edx, 100000h; DesiredAccess
0x180020c4b  lea     rcx, [rbp+EventHandle]; EventHandle
0x180020c4f  call    cs:__imp_NtOpenEvent
0x180020c55  mov     ebx, eax
0x180020c57  test    eax, eax
0x180020c59  jns     short loc_180020C8E
0x180020c5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c62  lea     rax, WPP_GLOBAL_Control
0x180020c69  cmp     rcx, rax
0x180020c6c  jz      short loc_180020CCA
0x180020c6e  test    byte ptr [rcx+1Ch], 8
0x180020c72  jz      short loc_180020CCA
0x180020c74  mov     rcx, [rcx+10h]
0x180020c78  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x180020c7f  mov     edx, 0Dh
0x180020c84  mov     r9d, ebx
0x180020c87  call    WPP_SF_d
0x180020c8c  jmp     short loc_180020CCA
0x180020c8e  imul    rcx, rdi, 0FFFFFFFFFF676980h
0x180020c95  lea     r8, [rbp+Timeout]; Timeout
0x180020c99  xor     edx, edx; Alertable
0x180020c9b  mov     qword ptr [rbp+Timeout], rcx
0x180020c9f  mov     rcx, [rbp+EventHandle]; Handle
0x180020ca3  call    cs:__imp_NtWaitForSingleObject
0x180020ca9  mov     rcx, [rbp+EventHandle]; Handle
0x180020cad  mov     ebx, eax
0x180020caf  call    cs:__imp_NtClose
0x180020cb5  test    ebx, ebx
0x180020cb7  js      short loc_180020CCA
0x180020cb9  cmp     ebx, 102h
0x180020cbf  jz      short loc_180020CC5
0x180020cc1  xor     eax, eax
0x180020cc3  jmp     short loc_180020CCC
0x180020cc5  mov     ebx, 0C0000192h
0x180020cca  mov     eax, ebx
0x180020ccc  lea     r11, [rsp+70h+var_s0]
0x180020cd1  mov     rbx, [r11+10h]
0x180020cd5  mov     rdi, [r11+18h]
0x180020cd9  mov     rsp, r11
0x180020cdc  pop     rbp
0x180020cdd  retn
```
