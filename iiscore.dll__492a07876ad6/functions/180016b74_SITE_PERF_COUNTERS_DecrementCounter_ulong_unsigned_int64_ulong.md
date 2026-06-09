# SITE_PERF_COUNTERS::DecrementCounter(ulong,unsigned __int64 *,ulong)

- ea: `0x180016b74`
- end: `0x180016bf3`
- name: `?DecrementCounter@SITE_PERF_COUNTERS@@QEAAXKPEA_KK@Z`
- size: `127`
- prototype: `void __fastcall(SITE_PERF_COUNTERS *__hidden this, unsigned int, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eb20`

## callees

- `0x180016b74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016bd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016bd0`

## pseudocode

```c
void __fastcall SITE_PERF_COUNTERS::DecrementCounter(SITE_PERF_COUNTERS *this, unsigned int a2, unsigned __int64 *a3)
{
  _QWORD *v3; // rdi
  unsigned __int64 *v4; // rbx
  __int64 v5; // rsi

  v3 = (_QWORD *)*((_QWORD *)this + 1);
  v4 = a3;
  v5 = a2;
  if ( v3 )
  {
    if ( a3 )
    {
      if ( *a3 == 0xFFFFFFFF )
      {
        LODWORD(a3) = (unsigned __int64)GetCurrentThreadId() % v3[2];
        *v4 = (unsigned int)a3;
      }
      else
      {
        LODWORD(a3) = *(_DWORD *)a3;
      }
    }
    _InterlockedDecrement((volatile signed __int32 *)(*v3
                                                    + v3[1] * (unsigned int)a3
                                                    + (unsigned int)dword_18004DCE4[3 * v5]));
  }
}

```

## disassembly

```asm
0x180016b74  mov     [rsp+arg_0], rbx
0x180016b79  mov     [rsp+arg_8], rsi
0x180016b7e  push    rdi
0x180016b7f  sub     rsp, 20h
0x180016b83  mov     rdi, [rcx+8]
0x180016b87  mov     rbx, r8
0x180016b8a  mov     esi, edx
0x180016b8c  test    rdi, rdi
0x180016b8f  jz      short loc_180016BB5
0x180016b91  test    rbx, rbx
0x180016b94  jnz     short loc_180016BC6
0x180016b96  lea     rax, dword_18004DCE4
0x180016b9d  lea     rcx, [rsi+rsi*2]
0x180016ba1  mov     edx, [rax+rcx*4]
0x180016ba4  mov     eax, r8d
0x180016ba7  imul    rax, [rdi+8]
0x180016bac  add     rdx, rax
0x180016baf  add     rdx, [rdi]
0x180016bb2  lock dec dword ptr [rdx]
0x180016bb5  mov     rbx, [rsp+28h+arg_0]
0x180016bba  mov     rsi, [rsp+28h+arg_8]
0x180016bbf  add     rsp, 20h
0x180016bc3  pop     rdi
0x180016bc4  retn
0x180016bc6  mov     eax, 0FFFFFFFFh
0x180016bcb  cmp     [r8], rax
0x180016bce  jnz     short loc_180016BEE
0x180016bd0  call    cs:__imp_GetCurrentThreadId
0x180016bd7  nop     dword ptr [rax+rax+00h]
0x180016bdc  mov     eax, eax
0x180016bde  xor     edx, edx
0x180016be0  div     qword ptr [rdi+10h]
0x180016be4  mov     eax, edx
0x180016be6  mov     r8, rdx
0x180016be9  mov     [rbx], rax
0x180016bec  jmp     short loc_180016B96
0x180016bee  mov     r8d, [r8]
0x180016bf1  jmp     short loc_180016B96
```
