# RtlpNotOwnerCriticalSection

- ea: `0x180070290`
- end: `0x180070362`
- name: `RtlpNotOwnerCriticalSection`
- size: `210`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001f4d0`
- `0x18006ffa0`

## callees

- `0x18001a080`
- `0x180070290`
- `0x180070370`
- `0x1800c5fb0`
- `0x18016f020`

## string_xrefs

- `0x180070329`: `NTDLL: Calling thread (%p) not owner of CritSect: %p  Owner ThreadId: %p\n`

## pseudocode

```c
_PEB_LDR_DATA *__fastcall RtlpNotOwnerCriticalSection(const void **a1)
{
  _PEB_LDR_DATA *result; // rax
  struct _TEB *v2; // rdx
  __int64 WowTebOffset; // rax

  result = NtCurrentPeb()->Ldr;
  if ( !result->ShutdownInProgress
    || a1 == (const void **)&LdrpLoaderLock && result->ShutdownThreadId != NtCurrentTeb()->ClientId.UniqueThread )
  {
    if ( !UseWOW64 )
      goto LABEL_17;
    v2 = NtCurrentTeb();
    WowTebOffset = v2->WowTebOffset;
    if ( (_DWORD)WowTebOffset )
    {
      if ( (int)WowTebOffset >= 0 )
        v2 = (struct _TEB *)((char *)v2 + WowTebOffset);
    }
    else
    {
      v2 = 0;
    }
    result = (_PEB_LDR_DATA *)LODWORD(v2->NtTib.Self);
    if ( !HIDWORD(result->SsHandle) || !*(_BYTE *)(HIDWORD(result->SsHandle) + 0x28LL) )
    {
LABEL_17:
      if ( NtCurrentPeb()->BeingDebugged )
      {
        DbgPrintEx(
          101,
          0,
          "NTDLL: Calling thread (%p) not owner of CritSect: %p  Owner ThreadId: %p\n",
          NtCurrentTeb()->ClientId.UniqueThread,
          a1,
          a1[2]);
        __debugbreak();
      }
      RtlDecodePointer(RtlpUnhandledExceptionFilter);
      RtlRaiseStatus(3221226084LL);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180070290  sub     rsp, 38h
0x180070294  mov     rax, gs:60h
0x18007029d  mov     rax, [rax+18h]
0x1800702a1  cmp     byte ptr [rax+48h], 0
0x1800702a5  jz      short loc_1800702CC
0x1800702a7  lea     rdx, LdrpLoaderLock
0x1800702ae  cmp     rcx, rdx
0x1800702b1  jnz     short loc_1800702C6
0x1800702b3  mov     rdx, gs:30h
0x1800702bc  mov     r8, [rdx+48h]
0x1800702c0  cmp     [rax+50h], r8
0x1800702c4  jnz     short loc_1800702CC
0x1800702c6  add     rsp, 38h
0x1800702ca  retn
0x1800702cc  cmp     cs:UseWOW64, 0
0x1800702d3  jz      short loc_1800702FF
0x1800702d5  mov     rdx, gs:30h
0x1800702de  movsxd  rax, dword ptr [rdx+180Ch]
0x1800702e5  test    eax, eax
0x1800702e7  jz      short loc_18007035E
0x1800702e9  js      short loc_1800702EE
0x1800702eb  add     rdx, rax
0x1800702ee  mov     eax, [rdx+30h]
0x1800702f1  mov     edx, [rax+0Ch]
0x1800702f4  test    rdx, rdx
0x1800702f7  jz      short loc_1800702FF
0x1800702f9  cmp     byte ptr [rdx+28h], 0
0x1800702fd  jnz     short loc_1800702C6
0x1800702ff  mov     rax, gs:60h
0x180070308  cmp     byte ptr [rax+2], 0
0x18007030c  jz      short loc_18007033D
0x18007030e  mov     r9, gs:30h
0x180070317  mov     rax, [rcx+10h]
0x18007031b  mov     [rsp+38h+var_10], rax
0x180070320  mov     [rsp+38h+var_18], rcx
0x180070325  mov     r9, [r9+48h]
0x180070329  lea     r8, aNtdllCallingTh; "NTDLL: Calling thread (%p) not owner of"...
0x180070330  xor     edx, edx
0x180070332  mov     ecx, 65h ; 'e'
0x180070337  call    DbgPrintEx
0x18007033c  int     3; Trap to Debugger
0x18007033d  mov     rcx, cs:RtlpUnhandledExceptionFilter
0x180070344  call    RtlDecodePointer
0x180070349  mov     [rsp+38h+arg_0], rax
0x18007034e  mov     ecx, 0C0000264h
0x180070353  call    RtlRaiseStatus
0x180070359  jmp     loc_1800702C6
0x18007035e  xor     edx, edx
0x180070360  jmp     short loc_1800702EE
0x180166fd0  push    rbp
0x180166fd2  sub     rsp, 30h
0x180166fd6  mov     rbp, rdx
0x180166fd9  mov     rax, [rbp+40h]
0x180166fdd  test    rax, rax
0x180166fe0  jz      short loc_180166FE8
0x180166fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180166fe7  nop
0x180166fe8  add     rsp, 30h
0x180166fec  pop     rbp
0x180166fed  retn
```
