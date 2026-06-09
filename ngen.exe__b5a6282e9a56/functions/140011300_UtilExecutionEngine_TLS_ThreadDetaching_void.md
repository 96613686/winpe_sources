# UtilExecutionEngine::TLS_ThreadDetaching(void)

- ea: `0x140011300`
- end: `0x140011381`
- name: `?TLS_ThreadDetaching@UtilExecutionEngine@@EEAAXXZ`
- size: `129`
- prototype: `void __fastcall(UtilExecutionEngine *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140011090`
- `0x140011300`
- `0x140013f30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140011366`
- `KERNEL32!HeapFree` at `0x140011366`
- `KERNEL32!GetProcessHeap` at `0x140011358`
- `KERNEL32!GetProcessHeap` at `0x140011358`

## pseudocode

```c
void __fastcall UtilExecutionEngine::TLS_ThreadDetaching(UtilExecutionEngine *this)
{
  __int64 v1; // rax
  void *v2; // rdi
  _QWORD *v3; // rbx
  char *v4; // rsi
  __int64 v5; // rbp
  void (*v6)(void); // rax
  HANDLE ProcessHeap; // rax

  v1 = CheckThreadState(0, 0);
  v2 = (void *)v1;
  if ( v1 )
  {
    v3 = (_QWORD *)v1;
    v4 = (char *)qword_140027A40 - v1;
    v5 = 22;
    do
    {
      v6 = *(void (**)(void))((char *)v3 + (_QWORD)v4);
      if ( v6 )
      {
        if ( *v3 )
          v6();
      }
      ++v3;
      --v5;
    }
    while ( v5 );
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
}

```

## disassembly

```asm
0x140011300  mov     [rsp+arg_0], rbx
0x140011305  mov     [rsp+arg_8], rbp
0x14001130a  mov     [rsp+arg_10], rsi
0x14001130f  push    rdi
0x140011310  sub     rsp, 20h
0x140011314  xor     edx, edx
0x140011316  xor     ecx, ecx
0x140011318  call    CheckThreadState
0x14001131d  mov     rdi, rax
0x140011320  test    rax, rax
0x140011323  jz      short loc_14001136C
0x140011325  lea     rsi, qword_140027A40
0x14001132c  mov     rbx, rax
0x14001132f  sub     rsi, rax
0x140011332  mov     ebp, 16h
0x140011337  mov     rax, [rsi+rbx]
0x14001133b  test    rax, rax
0x14001133e  jz      short loc_14001134E
0x140011340  mov     rcx, [rbx]
0x140011343  test    rcx, rcx
0x140011346  jz      short loc_14001134E
0x140011348  call    cs:__guard_dispatch_icall_fptr
0x14001134e  add     rbx, 8
0x140011352  sub     rbp, 1
0x140011356  jnz     short loc_140011337
0x140011358  call    cs:__imp_GetProcessHeap
0x14001135e  mov     r8, rdi; lpMem
0x140011361  xor     edx, edx; dwFlags
0x140011363  mov     rcx, rax; hHeap
0x140011366  call    cs:__imp_HeapFree
0x14001136c  mov     rbx, [rsp+28h+arg_0]
0x140011371  mov     rbp, [rsp+28h+arg_8]
0x140011376  mov     rsi, [rsp+28h+arg_10]
0x14001137b  add     rsp, 20h
0x14001137f  pop     rdi
0x140011380  retn
```
