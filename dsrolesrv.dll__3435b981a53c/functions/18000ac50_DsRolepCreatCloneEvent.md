# DsRolepCreatCloneEvent

- ea: `0x18000ac50`
- end: `0x18000acd6`
- name: `DsRolepCreatCloneEvent`
- size: `134`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000bbd4`

## callees

- `0x18000ac50`
- `0x180020dbc`

## import_xrefs

- `ntdll!NtCreateEvent` at `0x18000ac8f`
- `ntdll!NtCreateEvent` at `0x18000ac8f`

## string_xrefs

- `0x18000aca5`: `vDC Cloning: Create %ws event failed with error: 0x%x (%lu)\n`
- `0x18000acb8`: `vDC Cloning: Created %ws event.\n`

## pseudocode

```c
__int64 __fastcall DsRolepCreatCloneEvent(void **a1, __int64 a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  __int64 InitialState; // [rsp+20h] [rbp-48h]
  struct _OBJECT_ATTRIBUTES v7; // [rsp+30h] [rbp-38h] BYREF

  *(_QWORD *)&v7.Length = 48;
  memset(&v7.RootDirectory, 0, 40);
  v3 = NtCreateEvent(a1, 0x1F0003u, &v7, SynchronizationEvent, 0);
  v4 = v3;
  if ( v3 )
  {
    LODWORD(InitialState) = v3;
    DsRolepLogPrintRoutine(1, "vDC Cloning: Create %ws event failed with error: 0x%x (%lu)\n", a2, v3, InitialState);
  }
  else
  {
    DsRolepLogPrintRoutine(4, "vDC Cloning: Created %ws event.\n", a2);
  }
  return v4;
}

```

## disassembly

```asm
0x18000ac50  mov     r11, rsp
0x18000ac53  mov     [r11+8], rbx
0x18000ac57  push    rdi
0x18000ac58  sub     rsp, 60h
0x18000ac5c  xor     eax, eax
0x18000ac5e  mov     qword ptr [r11-38h], 30h ; '0'
0x18000ac66  mov     rdi, rdx
0x18000ac69  mov     [r11-20h], rax
0x18000ac6d  xorps   xmm0, xmm0
0x18000ac70  mov     [r11-30h], rax
0x18000ac74  mov     [r11-28h], rax
0x18000ac78  lea     r8, [r11-38h]; ObjectAttributes
0x18000ac7c  lea     r9d, [rax+1]; EventType
0x18000ac80  mov     [rsp+68h+InitialState], al; InitialState
0x18000ac84  mov     edx, 1F0003h; DesiredAccess
0x18000ac89  movdqu  [rsp+68h+var_18], xmm0
0x18000ac8f  call    cs:__imp_NtCreateEvent
0x18000ac95  mov     ebx, eax
0x18000ac97  mov     r8, rdi
0x18000ac9a  test    eax, eax
0x18000ac9c  jz      short loc_18000ACB8
0x18000ac9e  mov     r9d, eax
0x18000aca1  mov     dword ptr [rsp+68h+InitialState], eax
0x18000aca5  lea     rdx, aVdcCloningCrea; "vDC Cloning: Create %ws event failed wi"...
0x18000acac  mov     ecx, 1
0x18000acb1  call    DsRolepLogPrintRoutine
0x18000acb6  jmp     short loc_18000ACC9
0x18000acb8  lea     rdx, aVdcCloningCrea_0; "vDC Cloning: Created %ws event.\n"
0x18000acbf  mov     ecx, 4
0x18000acc4  call    DsRolepLogPrintRoutine
0x18000acc9  mov     eax, ebx
0x18000accb  mov     rbx, [rsp+68h+arg_0]
0x18000acd0  add     rsp, 60h
0x18000acd4  pop     rdi
0x18000acd5  retn
```
