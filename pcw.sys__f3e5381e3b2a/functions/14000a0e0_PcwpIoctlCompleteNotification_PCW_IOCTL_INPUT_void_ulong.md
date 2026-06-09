# PcwpIoctlCompleteNotification(PCW_IOCTL_INPUT *,void *,ulong *)

- ea: `0x14000a0e0`
- end: `0x14000a1d6`
- name: `?PcwpIoctlCompleteNotification@@YAJPEATPCW_IOCTL_INPUT@@PEAXPEAK@Z`
- size: `246`
- prototype: `__int64 __fastcall(union PCW_IOCTL_INPUT *, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000806c`
- `0x1400098b8`
- `0x14000a0e0`
- `0x14000b820`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000a145`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a19b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a1b7`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a145`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a19b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a1b7`
- `ntoskrnl!ProbeForRead` at `0x14000a115`
- `ntoskrnl!ProbeForRead` at `0x14000a115`

## pseudocode

```c
__int64 __fastcall PcwpIoctlCompleteNotification(union PCW_IOCTL_INPUT *a1, void *a2, unsigned int *a3)
{
  unsigned int v5; // eax
  int v6; // edi
  PVOID v7; // rcx
  const void *v9; // r9
  unsigned int v10; // r8d
  PVOID v11; // rbx
  __int64 v12; // rdx
  unsigned int v13; // [rsp+20h] [rbp-18h]
  bool v14; // [rsp+40h] [rbp+8h] BYREF
  PVOID Object; // [rsp+58h] [rbp+20h] BYREF

  v14 = 0;
  Object = 0;
  v5 = *((_DWORD *)a1 + 4);
  if ( v5 )
    ProbeForRead(*((volatile void **)a1 + 1), v5, 1u);
  v6 = PcwpReferenceObjectByHandle_PCW_USER_REGISTRATION_(&Object, *(_QWORD *)a1, a3);
  if ( v6 < 0 )
  {
    v7 = Object;
    if ( !Object )
      return (unsigned int)v6;
LABEL_5:
    ObfDereferenceObject(v7);
    return (unsigned int)v6;
  }
  v13 = *((_DWORD *)a1 + 4);
  v9 = (const void *)*((_QWORD *)a1 + 1);
  v10 = *((_DWORD *)a1 + 5);
  v11 = Object;
  v6 = PCW_USER_REGISTRATION::CompleteInFlightNotification((PCW_USER_REGISTRATION *)Object, &v14, v10, v9, v13);
  if ( v6 < 0 )
  {
    if ( !v11 )
      return (unsigned int)v6;
    v7 = v11;
    goto LABEL_5;
  }
  LOBYTE(v12) = v14;
  RtlWriteUCharToUser(a2, v12);
  if ( v11 )
    ObfDereferenceObject(v11);
  return 0;
}

```

## disassembly

```asm
0x14000a0e0  mov     rax, rsp
0x14000a0e3  mov     [rax+10h], rbx
0x14000a0e7  mov     [rax+18h], rsi
0x14000a0eb  push    rdi
0x14000a0ec  sub     rsp, 30h
0x14000a0f0  mov     rsi, rdx
0x14000a0f3  mov     rbx, rcx
0x14000a0f6  mov     byte ptr [rax+8], 0
0x14000a0fa  mov     qword ptr [rax+20h], 0
0x14000a102  mov     eax, [rcx+10h]
0x14000a105  test    eax, eax
0x14000a107  jz      short loc_14000A128
0x14000a109  mov     edx, eax; Length
0x14000a10b  mov     r8d, 1; Alignment
0x14000a111  mov     rcx, [rcx+8]; Address
0x14000a115  call    cs:__imp_ProbeForRead
0x14000a11c  nop     dword ptr [rax+rax+00h]
0x14000a121  jmp     short loc_14000A128
0x14000a123  jmp     loc_14000A1C5
0x14000a128  mov     rdx, [rbx]
0x14000a12b  lea     rcx, [rsp+38h+Object]
0x14000a130  call    PcwpReferenceObjectByHandle_PCW_USER_REGISTRATION_
0x14000a135  mov     edi, eax
0x14000a137  test    eax, eax
0x14000a139  jns     short loc_14000A155
0x14000a13b  mov     rcx, [rsp+38h+Object]; Object
0x14000a140  test    rcx, rcx
0x14000a143  jz      short loc_14000A151
0x14000a145  call    cs:__imp_ObfDereferenceObject
0x14000a14c  nop     dword ptr [rax+rax+00h]
0x14000a151  mov     eax, edi
0x14000a153  jmp     short loc_14000A1C5
0x14000a155  mov     eax, [rbx+10h]
0x14000a158  mov     [rsp+38h+var_18], eax; unsigned int
0x14000a15c  mov     r9, [rbx+8]; void *
0x14000a160  mov     r8d, [rbx+14h]; unsigned int
0x14000a164  lea     rdx, [rsp+38h+arg_0]; bool *
0x14000a169  mov     rbx, [rsp+38h+Object]
0x14000a16e  mov     rcx, rbx; this
0x14000a171  call    ?CompleteInFlightNotification@PCW_USER_REGISTRATION@@QEAAJPEA_NKPEBXK@Z; PCW_USER_REGISTRATION::CompleteInFlightNotification(bool *,ulong,void const *,ulong)
0x14000a176  mov     edi, eax
0x14000a178  test    eax, eax
0x14000a17a  jns     short loc_14000A186
0x14000a17c  test    rbx, rbx
0x14000a17f  jz      short loc_14000A151
0x14000a181  mov     rcx, rbx
0x14000a184  jmp     short loc_14000A145
0x14000a186  mov     dl, [rsp+38h+arg_0]
0x14000a18a  mov     rcx, rsi
0x14000a18d  call    RtlWriteUCharToUser
0x14000a192  nop
0x14000a193  test    rbx, rbx
0x14000a196  jz      short loc_14000A1A7
0x14000a198  mov     rcx, rbx; Object
0x14000a19b  call    cs:__imp_ObfDereferenceObject
0x14000a1a2  nop     dword ptr [rax+rax+00h]
0x14000a1a7  xor     eax, eax
0x14000a1a9  jmp     short loc_14000A1C5
0x14000a1ab  mov     ebx, eax
0x14000a1ad  mov     rcx, [rsp+38h+Object]; Object
0x14000a1b2  test    rcx, rcx
0x14000a1b5  jz      short loc_14000A1C3
0x14000a1b7  call    cs:__imp_ObfDereferenceObject
0x14000a1be  nop     dword ptr [rax+rax+00h]
0x14000a1c3  mov     eax, ebx
0x14000a1c5  mov     rbx, [rsp+38h+arg_8]
0x14000a1ca  mov     rsi, [rsp+38h+arg_10]
0x14000a1cf  add     rsp, 30h
0x14000a1d3  pop     rdi
0x14000a1d4  retn
```
