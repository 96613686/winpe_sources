# Win32LiveSystemProvider::ResumeThread(void *,void * *)

- ea: `0x180015a40`
- end: `0x180015add`
- name: `?ResumeThread@Win32LiveSystemProvider@@UEAAKPEAXPEAPEAX@Z`
- size: `157`
- prototype: `unsigned int __fastcall(Win32LiveSystemProvider *__hidden this, void *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180015a40`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180015ad6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ab6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ab6`

## pseudocode

```c
DWORD __fastcall Win32LiveSystemProvider::ResumeThread(Win32LiveSystemProvider *this, void *a2, void **a3)
{
  void (__fastcall *v4)(_QWORD, void *, __int64); // r10
  DWORD result; // eax
  _QWORD v6[3]; // [rsp+40h] [rbp-18h] BYREF

  if ( !a3 || !*a3 )
    return ResumeThread(a2);
  v4 = (void (__fastcall *)(_QWORD, void *, __int64))*((_QWORD *)this + 51);
  if ( v4 )
  {
    v4(*a3, a2, 1);
  }
  else
  {
    v6[0] = *a3;
    v6[1] = 1;
    (*((void (__fastcall **)(void *, __int64, _QWORD *, __int64))this + 52))(a2, 52, v6, 16);
  }
  CloseHandle(*a3);
  result = 1;
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x180015a40  push    rbx
0x180015a42  sub     rsp, 50h
0x180015a46  mov     rbx, r8
0x180015a49  mov     rax, rdx
0x180015a4c  mov     r11, rcx
0x180015a4f  test    r8, r8
0x180015a52  jz      short loc_180015ACE
0x180015a54  mov     rcx, [r8]
0x180015a57  test    rcx, rcx
0x180015a5a  jz      short loc_180015ACE
0x180015a5c  mov     r10, [r11+198h]
0x180015a63  test    r10, r10
0x180015a66  jnz     short loc_180015A94
0x180015a68  mov     [rsp+58h+var_18], rcx
0x180015a6d  lea     r9d, [r10+10h]
0x180015a71  mov     rcx, rax
0x180015a74  mov     [rsp+58h+var_10], 1
0x180015a7d  mov     rax, [r11+1A0h]
0x180015a84  lea     r8, [rsp+58h+var_18]
0x180015a89  lea     edx, [r10+34h]
0x180015a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a92  jmp     short loc_180015AB3
0x180015a94  xor     r9d, r9d
0x180015a97  mov     [rsp+58h+var_30], 0
0x180015a9f  mov     rax, r10
0x180015aa2  mov     [rsp+58h+var_38], 0
0x180015aaa  lea     r8d, [r9+1]
0x180015aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ab3  mov     rcx, [rbx]; hObject
0x180015ab6  call    cs:__imp_CloseHandle
0x180015abc  mov     eax, 1
0x180015ac1  mov     qword ptr [rbx], 0
0x180015ac8  add     rsp, 50h
0x180015acc  pop     rbx
0x180015acd  retn
0x180015ace  mov     rcx, rax
0x180015ad1  add     rsp, 50h
0x180015ad5  pop     rbx
0x180015ad6  jmp     cs:__imp_ResumeThread
```
