# SecDetShutdownTimers

- ea: `0x140043f0c`
- end: `0x140043f79`
- name: `SecDetShutdownTimers`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140041cec`

## callees

- `0x140011650`
- `0x140043f0c`

## import_xrefs

- `ntoskrnl!ExDeleteTimer` at `0x140043f4b`
- `ntoskrnl!ExDeleteTimer` at `0x140043f4b`

## pseudocode

```c
void *__fastcall SecDetShutdownTimers(__int64 a1, __int64 a2, __int64 a3)
{
  void *result; // rax
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+30h] [rbp-18h]

  if ( *((_QWORD *)DetectionContext + 6) )
  {
    LOBYTE(a3) = 1;
    v4 = 0;
    v5 = 0;
    LOBYTE(a2) = 1;
    ExDeleteTimer(*((_QWORD *)DetectionContext + 6), a2, a3, &v4);
    result = DetectionContext;
    *((_QWORD *)DetectionContext + 6) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140043f0c  sub     rsp, 48h
0x140043f10  mov     rax, cs:__security_cookie
0x140043f17  xor     rax, rsp
0x140043f1a  mov     [rsp+48h+var_10], rax
0x140043f1f  mov     rcx, cs:DetectionContext
0x140043f26  cmp     qword ptr [rcx+30h], 0
0x140043f2b  jz      short loc_140043F66
0x140043f2d  xorps   xmm0, xmm0
0x140043f30  lea     r9, [rsp+48h+var_28]
0x140043f35  xor     eax, eax
0x140043f37  mov     r8b, 1
0x140043f3a  movups  [rsp+48h+var_28], xmm0
0x140043f3f  mov     [rsp+48h+var_18], rax
0x140043f44  mov     dl, r8b
0x140043f47  mov     rcx, [rcx+30h]
0x140043f4b  call    cs:__imp_ExDeleteTimer
0x140043f52  nop     dword ptr [rax+rax+00h]
0x140043f57  mov     rax, cs:DetectionContext
0x140043f5e  mov     qword ptr [rax+30h], 0
0x140043f66  mov     rcx, [rsp+48h+var_10]
0x140043f6b  xor     rcx, rsp; StackCookie
0x140043f6e  call    __security_check_cookie
0x140043f73  add     rsp, 48h
0x140043f77  retn
```
