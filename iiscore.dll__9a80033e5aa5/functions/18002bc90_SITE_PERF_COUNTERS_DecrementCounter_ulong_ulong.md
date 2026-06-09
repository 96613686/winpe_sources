# SITE_PERF_COUNTERS::DecrementCounter(ulong,ulong)

- ea: `0x18002bc90`
- end: `0x18002bce3`
- name: `?DecrementCounter@SITE_PERF_COUNTERS@@UEAAXKK@Z`
- size: `83`
- prototype: `void __fastcall(SITE_PERF_COUNTERS *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002bc90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bcaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bcaa`

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
                                                      + (unsigned int)dword_18004ACE4[3 * a2]
                                                      + v2[1] * ((unsigned __int64)GetCurrentThreadId() % v2[2])));
  }
}

```

## disassembly

```asm
0x18002bc90  cmp     edx, 22h ; '"'
0x18002bc93  jnb     short locret_18002BCE2
0x18002bc95  mov     [rsp+arg_0], rbx
0x18002bc9a  push    rdi
0x18002bc9b  sub     rsp, 20h
0x18002bc9f  mov     rbx, [rcx+8]
0x18002bca3  mov     edi, edx
0x18002bca5  test    rbx, rbx
0x18002bca8  jz      short loc_18002BCD8
0x18002bcaa  call    cs:__imp_GetCurrentThreadId
0x18002bcb0  mov     eax, eax
0x18002bcb2  xor     edx, edx
0x18002bcb4  lea     rcx, [rdi+rdi*2]
0x18002bcb8  div     qword ptr [rbx+10h]
0x18002bcbc  lea     rax, dword_18004ACE4
0x18002bcc3  mov     eax, [rax+rcx*4]
0x18002bcc6  mov     r8d, edx
0x18002bcc9  imul    r8, [rbx+8]
0x18002bcce  add     r8, rax
0x18002bcd1  add     r8, [rbx]
0x18002bcd4  lock dec dword ptr [r8]
0x18002bcd8  mov     rbx, [rsp+28h+arg_0]
0x18002bcdd  add     rsp, 20h
0x18002bce1  pop     rdi
0x18002bce2  retn
```
