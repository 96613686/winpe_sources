# CertPropCreateThreadpoolWait

- ea: `0x180002610`
- end: `0x18000267e`
- name: `CertPropCreateThreadpoolWait`
- size: `110`
- prototype: `DWORD __fastcall(__int64, void *, void *, struct _TP_CALLBACK_ENVIRON_V3 *, PTP_WAIT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002ee0`

## callees

- `0x180002610`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180002651`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180002651`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000266b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000266b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180002634`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180002634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002642`

## pseudocode

```c
DWORD __fastcall CertPropCreateThreadpoolWait(
        __int64 a1,
        void *a2,
        void *a3,
        struct _TP_CALLBACK_ENVIRON_V3 *a4,
        PTP_WAIT *a5)
{
  struct _TP_WAIT *ThreadpoolWait; // rax
  DWORD result; // eax
  DWORD v8; // ebx

  ThreadpoolWait = *a5;
  if ( *a5 || (ThreadpoolWait = CreateThreadpoolWait(CertPropHandleReaderAction, a2, a4), (*a5 = ThreadpoolWait) != 0) )
  {
    SetThreadpoolWait(ThreadpoolWait, a3, 0);
    return 0;
  }
  else
  {
    result = GetLastError();
    v8 = result;
    if ( result )
    {
      CloseThreadpoolWait(*a5);
      result = v8;
      *a5 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002610  mov     [rsp+arg_0], rbx
0x180002615  push    rdi
0x180002616  sub     rsp, 20h
0x18000261a  mov     rdi, [rsp+28h+arg_20]
0x18000261f  mov     rbx, r8
0x180002622  mov     rax, [rdi]
0x180002625  test    rax, rax
0x180002628  jnz     short loc_180002662
0x18000262a  mov     r8, r9; pcbe
0x18000262d  lea     rcx, CertPropHandleReaderAction; pfnwa
0x180002634  call    cs:__imp_CreateThreadpoolWait
0x18000263a  mov     [rdi], rax
0x18000263d  test    rax, rax
0x180002640  jnz     short loc_180002662
0x180002642  call    cs:__imp_GetLastError
0x180002648  mov     ebx, eax
0x18000264a  test    eax, eax
0x18000264c  jz      short loc_180002673
0x18000264e  mov     rcx, [rdi]; pwa
0x180002651  call    cs:__imp_CloseThreadpoolWait
0x180002657  mov     eax, ebx
0x180002659  mov     qword ptr [rdi], 0
0x180002660  jmp     short loc_180002673
0x180002662  xor     r8d, r8d; pftTimeout
0x180002665  mov     rdx, rbx; h
0x180002668  mov     rcx, rax; pwa
0x18000266b  call    cs:__imp_SetThreadpoolWait
0x180002671  xor     eax, eax
0x180002673  mov     rbx, [rsp+28h+arg_0]
0x180002678  add     rsp, 20h
0x18000267c  pop     rdi
0x18000267d  retn
```
