# RtlpNotOwnerCriticalSection

- ea: `0x1800538b0`
- end: `0x180053982`
- name: `RtlpNotOwnerCriticalSection`
- size: `210`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001f4e0`
- `0x1800535c0`

## callees

- `0x18001a080`
- `0x1800538b0`
- `0x180053990`
- `0x1800c1cd0`
- `0x18016f020`

## string_xrefs

- `0x180053949`: `NTDLL: Calling thread (%p) not owner of CritSect: %p  Owner ThreadId: %p\n`

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
0x1800538b0  sub     rsp, 38h
0x1800538b4  mov     rax, gs:60h
0x1800538bd  mov     rax, [rax+18h]
0x1800538c1  cmp     byte ptr [rax+48h], 0
0x1800538c5  jz      short loc_1800538EC
0x1800538c7  lea     rdx, LdrpLoaderLock
0x1800538ce  cmp     rcx, rdx
0x1800538d1  jnz     short loc_1800538E6
0x1800538d3  mov     rdx, gs:30h
0x1800538dc  mov     r8, [rdx+48h]
0x1800538e0  cmp     [rax+50h], r8
0x1800538e4  jnz     short loc_1800538EC
0x1800538e6  add     rsp, 38h
0x1800538ea  retn
0x1800538ec  cmp     cs:UseWOW64, 0
0x1800538f3  jz      short loc_18005391F
0x1800538f5  mov     rdx, gs:30h
0x1800538fe  movsxd  rax, dword ptr [rdx+180Ch]
0x180053905  test    eax, eax
0x180053907  jz      short loc_18005397E
0x180053909  js      short loc_18005390E
0x18005390b  add     rdx, rax
0x18005390e  mov     eax, [rdx+30h]
0x180053911  mov     edx, [rax+0Ch]
0x180053914  test    rdx, rdx
0x180053917  jz      short loc_18005391F
0x180053919  cmp     byte ptr [rdx+28h], 0
0x18005391d  jnz     short loc_1800538E6
0x18005391f  mov     rax, gs:60h
0x180053928  cmp     byte ptr [rax+2], 0
0x18005392c  jz      short loc_18005395D
0x18005392e  mov     r9, gs:30h
0x180053937  mov     rax, [rcx+10h]
0x18005393b  mov     [rsp+38h+var_10], rax
0x180053940  mov     [rsp+38h+var_18], rcx
0x180053945  mov     r9, [r9+48h]
0x180053949  lea     r8, aNtdllCallingTh; "NTDLL: Calling thread (%p) not owner of"...
0x180053950  xor     edx, edx
0x180053952  mov     ecx, 65h ; 'e'
0x180053957  call    DbgPrintEx
0x18005395c  int     3; Trap to Debugger
0x18005395d  mov     rcx, cs:RtlpUnhandledExceptionFilter
0x180053964  call    RtlDecodePointer
0x180053969  mov     [rsp+38h+arg_0], rax
0x18005396e  mov     ecx, 0C0000264h
0x180053973  call    RtlRaiseStatus
0x180053979  jmp     loc_1800538E6
0x18005397e  xor     edx, edx
0x180053980  jmp     short loc_18005390E
0x1801664c0  push    rbp
0x1801664c2  sub     rsp, 30h
0x1801664c6  mov     rbp, rdx
0x1801664c9  mov     rax, [rbp+40h]
0x1801664cd  test    rax, rax
0x1801664d0  jz      short loc_1801664D8
0x1801664d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801664d7  nop
0x1801664d8  add     rsp, 30h
0x1801664dc  pop     rbp
0x1801664dd  retn
```
