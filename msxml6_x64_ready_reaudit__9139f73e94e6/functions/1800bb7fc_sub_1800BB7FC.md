# sub_1800BB7FC

- ea: `0x1800bb7fc`
- end: `0x1800bb83e`
- name: `sub_1800BB7FC`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800bb608`
- `0x1800bb700`
- `0x18011fcb0`

## callees

- `0x1800bb7fc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800bb828`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800bb828`

## pseudocode

```c
void __fastcall sub_1800BB7FC(struct _TP_TIMER **a1, _BYTE *a2, __int64 a3)
{
  struct _TP_TIMER *v3; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v3 = *a1;
  if ( v3 )
  {
    pftDueTime = (struct _FILETIME)(-10000 * a3);
    SetThreadpoolTimer(v3, &pftDueTime, 0, (unsigned int)a3 >> 2);
    *a2 = 1;
  }
}

```

## disassembly

```asm
0x1800bb7fc  push    rbx
0x1800bb7fe  sub     rsp, 20h
0x1800bb802  mov     rcx, [rcx]; pti
0x1800bb805  mov     rbx, rdx
0x1800bb808  test    rcx, rcx
0x1800bb80b  jz      short loc_1800BB837
0x1800bb80d  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x1800bb814  shr     r8d, 2
0x1800bb818  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800bb81d  mov     r9d, r8d; msWindowLength
0x1800bb820  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x1800bb825  xor     r8d, r8d; msPeriod
0x1800bb828  call    cs:SetThreadpoolTimer
0x1800bb82f  nop     dword ptr [rax+rax+00h]
0x1800bb834  mov     byte ptr [rbx], 1
0x1800bb837  add     rsp, 20h
0x1800bb83b  pop     rbx
0x1800bb83c  retn
```
