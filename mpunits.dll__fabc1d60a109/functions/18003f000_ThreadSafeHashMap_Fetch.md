# ThreadSafeHashMap_Fetch

- ea: `0x18003f000`
- end: `0x18003f0d4`
- name: `ThreadSafeHashMap_Fetch`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18003dbe0`
- `0x18003dd00`

## callees

- `0x18003f000`
- `0x180043d40`
- `0x180044464`
- `0x18004449c`
- `0x1800444f4`
- `0x18004462c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f021`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f09f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f021`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f09f`

## pseudocode

```c
__int64 __fastcall ThreadSafeHashMap_Fetch(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall *a3)(__int64, _QWORD *),
        __int64 a4)
{
  __int64 v5; // rdi
  __int64 v9; // rax
  _QWORD *v10; // rdx
  _QWORD *v11; // rsi
  unsigned int v12; // ebx

  v5 = a1 + 48;
  if ( *(_QWORD *)(a1 + 88) != GetCurrentThreadId() && (unsigned int)_Pump_BeginDeferringHelper(v5) )
    _Pump_BeginDeferring(v5);
  v9 = HashMap_Find(a1, a2);
  if ( v9 )
  {
    v10 = (_QWORD *)v9;
LABEL_13:
    v12 = a3(a4, v10);
  }
  else
  {
    v11 = *(_QWORD **)(a1 + 64);
    v12 = 6;
    while ( v11 )
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD *, __int64))(a1 + 112))(v11 - 1, a2) )
      {
        _m_prefetchw(v11 + 1);
        if ( v11[1] )
          break;
        v10 = v11 - 1;
        goto LABEL_13;
      }
      v11 = (_QWORD *)*v11;
    }
  }
  if ( *(_QWORD *)(v5 + 40) != GetCurrentThreadId() && (unsigned int)_Pump_EndDeferringHelper(v5) )
    _Pump_EndDeferring(v5);
  return v12;
}

```

## disassembly

```asm
0x18003f000  push    rbx
0x18003f002  push    rbp
0x18003f003  push    rsi
0x18003f004  push    rdi
0x18003f005  push    r12
0x18003f007  push    r13
0x18003f009  push    r14
0x18003f00b  push    r15
0x18003f00d  sub     rsp, 28h
0x18003f011  mov     r12, r9
0x18003f014  lea     rdi, [rcx+30h]
0x18003f018  mov     r13, r8
0x18003f01b  mov     r15, rdx
0x18003f01e  mov     r14, rcx
0x18003f021  call    cs:__imp_GetCurrentThreadId
0x18003f027  mov     eax, eax
0x18003f029  cmp     [rdi+28h], rax
0x18003f02d  jz      short loc_18003F043
0x18003f02f  mov     rcx, rdi
0x18003f032  call    __Pump_BeginDeferringHelper
0x18003f037  test    eax, eax
0x18003f039  jz      short loc_18003F043
0x18003f03b  mov     rcx, rdi
0x18003f03e  call    __Pump_BeginDeferring
0x18003f043  mov     rdx, r15
0x18003f046  mov     rcx, r14
0x18003f049  call    HashMap_Find
0x18003f04e  test    rax, rax
0x18003f051  jz      short loc_18003F058
0x18003f053  mov     rdx, rax
0x18003f056  jmp     short loc_18003F092
0x18003f058  mov     rsi, [r14+40h]
0x18003f05c  mov     ebx, 6
0x18003f061  jmp     short loc_18003F07A
0x18003f063  mov     rax, [r14+70h]
0x18003f067  lea     rcx, [rsi-8]
0x18003f06b  mov     rdx, r15
0x18003f06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f073  test    eax, eax
0x18003f075  jnz     short loc_18003F081
0x18003f077  mov     rsi, [rsi]
0x18003f07a  test    rsi, rsi
0x18003f07d  jnz     short loc_18003F063
0x18003f07f  jmp     short loc_18003F09F
0x18003f081  prefetchw byte ptr [rsi+8]
0x18003f085  mov     rax, [rsi+8]
0x18003f089  test    rax, rax
0x18003f08c  jnz     short loc_18003F09F
0x18003f08e  lea     rdx, [rsi-8]
0x18003f092  mov     rcx, r12
0x18003f095  mov     rax, r13
0x18003f098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f09d  mov     ebx, eax
0x18003f09f  call    cs:__imp_GetCurrentThreadId
0x18003f0a5  mov     eax, eax
0x18003f0a7  cmp     [rdi+28h], rax
0x18003f0ab  jz      short loc_18003F0C1
0x18003f0ad  mov     rcx, rdi
0x18003f0b0  call    __Pump_EndDeferringHelper
0x18003f0b5  test    eax, eax
0x18003f0b7  jz      short loc_18003F0C1
0x18003f0b9  mov     rcx, rdi
0x18003f0bc  call    __Pump_EndDeferring
0x18003f0c1  mov     eax, ebx
0x18003f0c3  add     rsp, 28h
0x18003f0c7  pop     r15
0x18003f0c9  pop     r14
0x18003f0cb  pop     r13
0x18003f0cd  pop     r12
0x18003f0cf  pop     rdi
0x18003f0d0  pop     rsi
0x18003f0d1  pop     rbp
0x18003f0d2  pop     rbx
0x18003f0d3  retn
```
