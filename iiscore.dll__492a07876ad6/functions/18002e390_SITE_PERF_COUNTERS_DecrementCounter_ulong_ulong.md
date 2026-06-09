# SITE_PERF_COUNTERS::DecrementCounter(ulong,ulong)

- ea: `0x18002e390`
- end: `0x18002e3ea`
- name: `?DecrementCounter@SITE_PERF_COUNTERS@@UEAAXKK@Z`
- size: `90`
- prototype: `void __fastcall(SITE_PERF_COUNTERS *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002e390`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e3aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e3aa`

## pseudocode

```c
void __fastcall SITE_PERF_COUNTERS::DecrementCounter(SITE_PERF_COUNTERS *this, unsigned int a2)
{
  _QWORD *v2; // rbx

  if ( a2 < 0x22 )
  {
    v2 = (_QWORD *)*((_QWORD *)this + 1);
    if ( v2 )
      _InterlockedDecrement((volatile signed __int32 *)(*v2
                                                      + (unsigned int)dword_18004DCE4[3 * a2]
                                                      + v2[1] * ((unsigned __int64)GetCurrentThreadId() % v2[2])));
  }
}

```

## disassembly

```asm
0x18002e390  cmp     edx, 22h ; '"'
0x18002e393  jnb     short locret_18002E3E8
0x18002e395  mov     [rsp+arg_0], rbx
0x18002e39a  push    rdi
0x18002e39b  sub     rsp, 20h
0x18002e39f  mov     rbx, [rcx+8]
0x18002e3a3  mov     edi, edx
0x18002e3a5  test    rbx, rbx
0x18002e3a8  jz      short loc_18002E3DE
0x18002e3aa  call    cs:__imp_GetCurrentThreadId
0x18002e3b1  nop     dword ptr [rax+rax+00h]
0x18002e3b6  mov     eax, eax
0x18002e3b8  xor     edx, edx
0x18002e3ba  lea     rcx, [rdi+rdi*2]
0x18002e3be  div     qword ptr [rbx+10h]
0x18002e3c2  lea     rax, dword_18004DCE4
0x18002e3c9  mov     eax, [rax+rcx*4]
0x18002e3cc  mov     r8d, edx
0x18002e3cf  imul    r8, [rbx+8]
0x18002e3d4  add     r8, rax
0x18002e3d7  add     r8, [rbx]
0x18002e3da  lock dec dword ptr [r8]
0x18002e3de  mov     rbx, [rsp+28h+arg_0]
0x18002e3e3  add     rsp, 20h
0x18002e3e7  pop     rdi
0x18002e3e8  retn
```
