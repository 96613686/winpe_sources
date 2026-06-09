# wil::details::ScopeExitFnGuard__lambda_47272fddd909adeb429bad6d42265b19___::operator()

- ea: `0x18002627c`
- end: `0x1800262be`
- name: `wil::details::ScopeExitFnGuard__lambda_47272fddd909adeb429bad6d42265b19___::operator()`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026270`
- `0x1800263f4`

## callees

- `0x18002627c`
- `0x180026560`

## import_xrefs

- `IPHLPAPI!DeleteCompartment` at `0x180026295`
- `IPHLPAPI!DeleteCompartment` at `0x180026295`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFnGuard__lambda_47272fddd909adeb429bad6d42265b19___::operator()(_BYTE *a1)
{
  unsigned int v1; // eax
  unsigned int v2; // r8d
  unsigned int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a1[9] )
  {
    a1[9] = 0;
    v1 = DeleteCompartment(*(unsigned int *)(*(_QWORD *)a1 + 16LL));
    if ( v1 )
      wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x59, v2, (const char *)v1, v3);
  }
}

```

## disassembly

```asm
0x18002627c  mov     [rsp+arg_0], rcx
0x180026281  sub     rsp, 28h
0x180026285  cmp     byte ptr [rcx+9], 0
0x180026289  jz      short loc_1800262B8
0x18002628b  mov     byte ptr [rcx+9], 0
0x18002628f  mov     rcx, [rcx]
0x180026292  mov     ecx, [rcx+10h]
0x180026295  call    cs:__imp_DeleteCompartment
0x18002629c  nop     dword ptr [rax+rax+00h]
0x1800262a1  mov     rcx, [rsp+28h]; this
0x1800262a6  test    eax, eax
0x1800262a8  jz      short loc_1800262B8
0x1800262aa  mov     r9d, eax; char *
0x1800262ad  mov     edx, 59h ; 'Y'; void *
0x1800262b2  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800262b7  nop
0x1800262b8  add     rsp, 28h
0x1800262bc  retn
```
