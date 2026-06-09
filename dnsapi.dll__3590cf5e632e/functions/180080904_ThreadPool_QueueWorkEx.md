# ThreadPool_QueueWorkEx

- ea: `0x180080904`
- end: `0x180080991`
- name: `ThreadPool_QueueWorkEx`
- size: `141`
- prototype: `__int64 __fastcall(PTP_WORK_CALLBACK pfnwk, PVOID pv)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180056600`
- `0x180062450`
- `0x180097d50`
- `0x1800aa81c`

## callees

- `0x180080904`
- `0x1800ddfa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080953`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080953`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008093f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008093f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180080968`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180080968`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180080977`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180080977`

## pseudocode

```c
__int64 __fastcall ThreadPool_QueueWorkEx(PTP_WORK_CALLBACK pfnwk, PVOID pv)
{
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v5; // rdi
  unsigned int v6; // ebx

  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_q(1035, 15, WPP_0ee542721a7b375122a881c30985be4a_Traceguids, pv);
  ThreadpoolWork = CreateThreadpoolWork(pfnwk, pv, 0);
  v5 = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    v6 = 0;
    SubmitThreadpoolWork(ThreadpoolWork);
    CloseThreadpoolWork(v5);
  }
  else
  {
    return GetLastError();
  }
  return v6;
}

```

## disassembly

```asm
0x180080904  mov     [rsp+arg_0], rbx
0x180080909  push    rdi
0x18008090a  sub     rsp, 20h
0x18008090e  mov     rbx, rdx
0x180080911  mov     rdi, rcx
0x180080914  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18008091b  jz      short loc_180080936
0x18008091d  mov     edx, 0Fh
0x180080922  lea     r8, WPP_0ee542721a7b375122a881c30985be4a_Traceguids
0x180080929  mov     ecx, 40Bh
0x18008092e  mov     r9, rbx
0x180080931  call    WPP_SF_q
0x180080936  xor     r8d, r8d; pcbe
0x180080939  mov     rdx, rbx; pv
0x18008093c  mov     rcx, rdi; pfnwk
0x18008093f  call    cs:__imp_CreateThreadpoolWork
0x180080946  nop     dword ptr [rax+rax+00h]
0x18008094b  mov     rdi, rax
0x18008094e  test    rax, rax
0x180080951  jnz     short loc_180080963
0x180080953  call    cs:__imp_GetLastError
0x18008095a  nop     dword ptr [rax+rax+00h]
0x18008095f  mov     ebx, eax
0x180080961  jmp     short loc_180080983
0x180080963  mov     rcx, rdi; pwk
0x180080966  xor     ebx, ebx
0x180080968  call    cs:__imp_SubmitThreadpoolWork
0x18008096f  nop     dword ptr [rax+rax+00h]
0x180080974  mov     rcx, rdi; pwk
0x180080977  call    cs:__imp_CloseThreadpoolWork
0x18008097e  nop     dword ptr [rax+rax+00h]
0x180080983  mov     eax, ebx
0x180080985  mov     rbx, [rsp+28h+arg_0]
0x18008098a  add     rsp, 20h
0x18008098e  pop     rdi
0x18008098f  retn
```
