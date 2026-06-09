# StartAddress

- ea: `0x1801b5ba0`
- end: `0x1801b5c05`
- name: `StartAddress`
- size: `101`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1801b5ba0`
- `0x1801b5dc0`
- `0x1801c838c`
- `0x1801c9974`
- `0x1801cc92c`
- `0x1801cccc8`
- `0x18037b570`

## import_xrefs

- `KERNEL32!ExitThread` at `0x1801b5bb6`
- `KERNEL32!ExitThread` at `0x1801b5bb6`
- `KERNEL32!GetLastError` at `0x1801b5bae`
- `KERNEL32!GetLastError` at `0x1801b5bae`

## pseudocode

```c
void __fastcall __noreturn StartAddress(_BYTE *lpThreadParameter)
{
  DWORD LastError; // eax
  unsigned int v3; // eax

  if ( !lpThreadParameter )
  {
    LastError = GetLastError();
    ExitThread(LastError);
  }
  *(_QWORD *)(sub_1801C9974() + 960) = lpThreadParameter;
  if ( (unsigned int)sub_1801CCCC8() == 2 )
    lpThreadParameter[32] = (unsigned int)sub_1801CC92C(1) == 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD))lpThreadParameter)(*((_QWORD *)lpThreadParameter + 1));
  sub_1801B5DC0(v3);
}

```

## disassembly

```asm
0x1801b5ba0  push    rbx
0x1801b5ba2  sub     rsp, 20h
0x1801b5ba6  mov     rbx, rcx
0x1801b5ba9  test    rcx, rcx
0x1801b5bac  jnz     short loc_1801B5BBD
0x1801b5bae  call    cs:__imp_GetLastError
0x1801b5bb4  mov     ecx, eax; dwExitCode
0x1801b5bb6  call    cs:ExitThread
0x1801b5bbd  call    sub_1801C9974
0x1801b5bc2  mov     [rax+3C0h], rbx
0x1801b5bc9  call    sub_1801CCCC8
0x1801b5bce  cmp     eax, 2
0x1801b5bd1  jnz     short loc_1801B5BE3
0x1801b5bd3  lea     ecx, [rax-1]
0x1801b5bd6  call    sub_1801CC92C
0x1801b5bdb  test    eax, eax
0x1801b5bdd  setz    al
0x1801b5be0  mov     [rbx+20h], al
0x1801b5be3  mov     rcx, [rbx+8]
0x1801b5be7  mov     rax, [rbx]
0x1801b5bea  call    j__guard_dispatch_icall_nop
0x1801b5bef  mov     ecx, eax
0x1801b5bf1  call    sub_1801B5DC0
0x1801b5bf7  mov     ecx, eax
0x1801b5bf9  call    sub_1801C838C
0x1801b5bfe  nop
0x1801b5bff  add     rsp, 20h
0x1801b5c03  pop     rbx
0x1801b5c04  retn
```
