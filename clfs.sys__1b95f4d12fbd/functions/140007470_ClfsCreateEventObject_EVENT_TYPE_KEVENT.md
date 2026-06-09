# ClfsCreateEventObject(_EVENT_TYPE,_KEVENT * &)

- ea: `0x140007470`
- end: `0x140007547`
- name: `?ClfsCreateEventObject@@YAJW4_EVENT_TYPE@@AEAPEAU_KEVENT@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(enum _EVENT_TYPE, struct _KEVENT **)`
- caller_count: `26`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x14000593c`
- `0x140005f1c`
- `0x1400119a0`
- `0x1400326b0`
- `0x140032bb8`
- `0x140032d88`
- `0x14003306c`
- `0x140033898`
- `0x140037f48`
- `0x14003dc6c`
- `0x14003f208`
- `0x140048404`
- `0x14004887c`
- `0x140048d30`
- `0x140055290`
- `0x140057f54`
- `0x14005b6d0`
- `0x14005c274`
- `0x14005cdc8`
- `0x140063844`
- `0x140070cd4`
- `0x140071248`
- `0x140073128`
- `0x140074410`
- `0x140076e00`
- `0x1400784e4`

## callees

- `0x140007470`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000751c`
- `ntoskrnl!ZwClose` at `0x14000751c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400074fe`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400074fe`
- `ntoskrnl!ZwCreateEvent` at `0x1400074bf`
- `ntoskrnl!ZwCreateEvent` at `0x1400074bf`

## pseudocode

```c
NTSTATUS __fastcall ClfsCreateEventObject(enum _EVENT_TYPE a1, PVOID *a2)
{
  NTSTATUS result; // eax
  NTSTATUS v4; // eax
  HANDLE v5; // rcx
  int v6; // ebx
  struct _OBJECT_ATTRIBUTES v7; // [rsp+30h] [rbp-38h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp+10h] BYREF
  PVOID Object; // [rsp+80h] [rbp+18h] BYREF

  *(_QWORD *)&v7.Length = 48;
  *a2 = 0;
  memset(&v7.ObjectName, 0, 32);
  Handle = 0;
  v7.RootDirectory = 0;
  v7.Attributes = 512;
  v7.ObjectName = 0;
  result = ZwCreateEvent(&Handle, 0x1F0003u, &v7, NotificationEvent, 0);
  if ( result >= 0 )
  {
    Object = 0;
    v4 = ObReferenceObjectByHandle(Handle, 2u, 0, 0, &Object, 0);
    v5 = Handle;
    v6 = v4;
    *a2 = Object;
    ZwClose(v5);
    result = v6;
    if ( v6 < 0 )
      *a2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140007470  mov     rax, rsp
0x140007473  mov     [rax+20h], rsi
0x140007477  push    rdi
0x140007478  sub     rsp, 60h
0x14000747c  xor     esi, esi
0x14000747e  mov     qword ptr [rax-38h], 30h ; '0'
0x140007486  xorps   xmm0, xmm0
0x140007489  mov     [rdx], rsi
0x14000748c  movups  xmmword ptr [rax-28h], xmm0
0x140007490  mov     rdi, rdx
0x140007493  mov     [rax+10h], rsi
0x140007497  mov     edx, 1F0003h; DesiredAccess
0x14000749c  mov     [rax-30h], rsi
0x1400074a0  xor     r9d, r9d; EventType
0x1400074a3  mov     dword ptr [rax-20h], 200h
0x1400074aa  lea     r8, [rax-38h]; ObjectAttributes
0x1400074ae  mov     [rax-28h], rsi
0x1400074b2  lea     rcx, [rax+10h]; EventHandle
0x1400074b6  mov     [rax-48h], sil
0x1400074ba  movdqu  xmmword ptr [rax-18h], xmm0
0x1400074bf  call    cs:__imp_ZwCreateEvent
0x1400074c6  nop     dword ptr [rax+rax+00h]
0x1400074cb  test    eax, eax
0x1400074cd  js      short loc_140007533
0x1400074cf  mov     rcx, [rsp+68h+Handle]; Handle
0x1400074d4  lea     rax, [rsp+68h+arg_10]
0x1400074dc  mov     [rsp+68h+HandleInformation], rsi; HandleInformation
0x1400074e1  xor     r9d, r9d; AccessMode
0x1400074e4  xor     r8d, r8d; ObjectType
0x1400074e7  mov     [rsp+68h+Object], rax; Object
0x1400074ec  mov     edx, 2; DesiredAccess
0x1400074f1  mov     [rsp+68h+arg_0], rbx
0x1400074f6  mov     [rsp+68h+arg_10], rsi
0x1400074fe  call    cs:__imp_ObReferenceObjectByHandle
0x140007505  nop     dword ptr [rax+rax+00h]
0x14000750a  mov     rcx, [rsp+68h+Handle]; Handle
0x14000750f  mov     ebx, eax
0x140007511  mov     rax, [rsp+68h+arg_10]
0x140007519  mov     [rdi], rax
0x14000751c  call    cs:__imp_ZwClose
0x140007523  nop     dword ptr [rax+rax+00h]
0x140007528  mov     eax, ebx
0x14000752a  test    ebx, ebx
0x14000752c  js      short loc_140007542
0x14000752e  mov     rbx, [rsp+68h+arg_0]
0x140007533  mov     rsi, [rsp+68h+arg_18]
0x14000753b  add     rsp, 60h
0x14000753f  pop     rdi
0x140007540  retn
0x140007542  mov     [rdi], rsi
0x140007545  jmp     short loc_14000752E
```
