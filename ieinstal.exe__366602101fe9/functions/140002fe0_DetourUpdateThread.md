# DetourUpdateThread

- ea: `0x140002fe0`
- end: `0x14000308b`
- name: `DetourUpdateThread`
- size: `171`
- prototype: `__int64 __fastcall(HANDLE hThread)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x14000d36c`
- `0x14000d4f0`

## callees

- `0x140002fe0`
- `0x1400038cc`
- `0x140003978`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x140002ff7`
- `KERNEL32!GetCurrentThread` at `0x140002ff7`
- `KERNEL32!GetLastError` at `0x140003036`
- `KERNEL32!GetLastError` at `0x140003036`
- `KERNEL32!SuspendThread` at `0x14000302b`
- `KERNEL32!SuspendThread` at `0x14000302b`

## pseudocode

```c
__int64 __fastcall DetourUpdateThread(HANDLE hThread)
{
  __int64 result; // rax
  _QWORD *v3; // rbx
  DWORD LastError; // edi

  result = (unsigned int)dword_14001772C;
  if ( !dword_14001772C )
  {
    if ( hThread == GetCurrentThread() )
      return 0;
    v3 = operator new(0x10u);
    if ( !v3 )
    {
      LastError = 8;
LABEL_8:
      result = LastError;
      dword_14001772C = LastError;
      qword_140017730 = 0;
      return result;
    }
    if ( SuspendThread(hThread) == -1 )
    {
      LastError = GetLastError();
      operator delete(v3, 0x10u);
      goto LABEL_8;
    }
    *v3 = qword_140017738;
    result = 0;
    v3[1] = hThread;
    qword_140017738 = v3;
  }
  return result;
}

```

## disassembly

```asm
0x140002fe0  push    rdi
0x140002fe2  sub     rsp, 20h
0x140002fe6  mov     eax, cs:dword_14001772C
0x140002fec  mov     rdi, rcx
0x140002fef  test    eax, eax
0x140002ff1  jnz     loc_140003085
0x140002ff7  call    cs:__imp_GetCurrentThread
0x140002ffd  cmp     rdi, rax
0x140003000  jnz     short loc_14000300A
0x140003002  xor     eax, eax
0x140003004  add     rsp, 20h
0x140003008  pop     rdi
0x140003009  retn
0x14000300a  mov     ecx, 10h; dwBytes
0x14000300f  mov     [rsp+28h+arg_0], rbx
0x140003014  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003019  mov     rbx, rax
0x14000301c  test    rax, rax
0x14000301f  jnz     short loc_140003028
0x140003021  mov     edi, 8
0x140003026  jmp     short loc_14000304B
0x140003028  mov     rcx, rdi; hThread
0x14000302b  call    cs:__imp_SuspendThread
0x140003031  cmp     eax, 0FFFFFFFFh
0x140003034  jnz     short loc_140003069
0x140003036  call    cs:__imp_GetLastError
0x14000303c  mov     edi, eax
0x14000303e  mov     edx, 10h; unsigned __int64
0x140003043  mov     rcx, rbx; void *
0x140003046  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000304b  mov     rbx, [rsp+28h+arg_0]
0x140003050  mov     eax, edi
0x140003052  mov     cs:dword_14001772C, edi
0x140003058  mov     cs:qword_140017730, 0
0x140003063  add     rsp, 20h
0x140003067  pop     rdi
0x140003068  retn
0x140003069  mov     rax, cs:qword_140017738
0x140003070  mov     [rbx], rax
0x140003073  xor     eax, eax
0x140003075  mov     [rbx+8], rdi
0x140003079  mov     cs:qword_140017738, rbx
0x140003080  mov     rbx, [rsp+28h+arg_0]
0x140003085  add     rsp, 20h
0x140003089  pop     rdi
0x14000308a  retn
```
