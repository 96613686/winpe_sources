# COutputQueue::InitialThreadProc(void *)

- ea: `0x18001c360`
- end: `0x18001c395`
- name: `?InitialThreadProc@COutputQueue@@KAKPEAX@Z`
- size: `53`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180007758`
- `0x18001c360`
- `0x18001c730`

## import_xrefs

- `ole32!CoUninitialize` at `0x18001c382`
- `ole32!CoUninitialize` at `0x18001c382`

## pseudocode

```c
__int64 __fastcall COutputQueue::InitialThreadProc(COutputQueue *lpThreadParameter)
{
  int v2; // edi
  unsigned int v3; // ebx

  v2 = CAMThread::CoInitializeHelper();
  v3 = COutputQueue::ThreadProc(lpThreadParameter);
  if ( !v2 )
    CoUninitialize();
  return v3;
}

```

## disassembly

```asm
0x18001c360  mov     [rsp+arg_0], rbx
0x18001c365  push    rdi
0x18001c366  sub     rsp, 20h
0x18001c36a  mov     rbx, rcx
0x18001c36d  call    ?CoInitializeHelper@CAMThread@@SAJXZ; CAMThread::CoInitializeHelper(void)
0x18001c372  mov     rcx, rbx; this
0x18001c375  mov     edi, eax
0x18001c377  call    ?ThreadProc@COutputQueue@@IEAAKXZ; COutputQueue::ThreadProc(void)
0x18001c37c  mov     ebx, eax
0x18001c37e  test    edi, edi
0x18001c380  jnz     short loc_18001C388
0x18001c382  call    cs:__imp_CoUninitialize
0x18001c388  mov     eax, ebx
0x18001c38a  mov     rbx, [rsp+28h+arg_0]
0x18001c38f  add     rsp, 20h
0x18001c393  pop     rdi
0x18001c394  retn
```
