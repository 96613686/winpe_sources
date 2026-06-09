# CreateThreadAndAddRefDll(_SECURITY_ATTRIBUTES *,unsigned __int64,ulong (*)(void *),void *,ulong,ulong *)

- ea: `0x1800c6e58`
- end: `0x1800c6f1e`
- name: `?CreateThreadAndAddRefDll@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@_KP6AKPEAX@Z2KPEAK@Z`
- size: `198`
- prototype: `void *__fastcall(struct _SECURITY_ATTRIBUTES *, unsigned __int64, unsigned int (*)(void *), void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c6d8c`

## callees

- `0x1800c6e58`
- `0x1800c6f24`
- `0x1800e5e90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c6f10`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c6f10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c6e94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c6e94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c6e7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c6e7f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800c6edd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800c6edd`

## pseudocode

```c
HANDLE __fastcall CreateThreadAndAddRefDll(
        struct _SECURITY_ATTRIBUTES *a1,
        __int64 a2,
        unsigned int (*a3)(void *),
        void *a4)
{
  HANDLE Thread; // rdi
  HANDLE ProcessHeap; // rax
  wil::details *v6; // rax
  HMODULE v7; // rsi
  wil::details *v8; // rbx
  void *v9; // rdx
  HMODULE hLibModule; // [rsp+58h] [rbp+20h] BYREF

  Thread = 0;
  hLibModule = 0;
  if ( (unsigned int)AddRefModule(&hLibModule) )
  {
    ProcessHeap = GetProcessHeap();
    v6 = (wil::details *)HeapAlloc(ProcessHeap, 0, 0x18u);
    v7 = hLibModule;
    v8 = v6;
    if ( v6 )
    {
      *((_QWORD *)v6 + 1) = 0;
      *(_QWORD *)v6 = BackgroundThreadProc;
      *((_QWORD *)v6 + 2) = v7;
      Thread = CreateThread(0, 0, DllRefCountSafeThreadThunk, v6, 0, &Globals::ThreadId);
      if ( Thread )
        return Thread;
      wil::details::FreeProcessHeap(v8, v9);
    }
    FreeLibrary(v7);
  }
  return Thread;
}

```

## disassembly

```asm
0x1800c6e58  mov     rax, rsp
0x1800c6e5b  mov     [rax+8], rbx
0x1800c6e5f  mov     [rax+10h], rsi
0x1800c6e63  mov     [rax+20h], r9
0x1800c6e67  push    rdi
0x1800c6e68  sub     rsp, 30h
0x1800c6e6c  xor     edi, edi
0x1800c6e6e  lea     rcx, [rax+20h]; HINSTANCE *
0x1800c6e72  and     [rax+20h], rdi
0x1800c6e76  call    ?AddRefModule@@YAHPEAPEAUHINSTANCE__@@@Z; AddRefModule(HINSTANCE__ * *)
0x1800c6e7b  test    eax, eax
0x1800c6e7d  jz      short loc_1800C6EF1
0x1800c6e7f  call    cs:__imp_GetProcessHeap
0x1800c6e86  nop     dword ptr [rax+rax+00h]
0x1800c6e8b  xor     edx, edx; dwFlags
0x1800c6e8d  lea     r8d, [rdi+18h]; dwBytes
0x1800c6e91  mov     rcx, rax; hHeap
0x1800c6e94  call    cs:__imp_HeapAlloc
0x1800c6e9b  nop     dword ptr [rax+rax+00h]
0x1800c6ea0  mov     rsi, [rsp+38h+hLibModule]
0x1800c6ea5  mov     rbx, rax
0x1800c6ea8  test    rax, rax
0x1800c6eab  jz      short loc_1800C6F0D
0x1800c6ead  and     [rbx+8], rdi
0x1800c6eb1  lea     rax, ?BackgroundThreadProc@@YAKPEAX@Z; BackgroundThreadProc(void *)
0x1800c6eb8  mov     [rbx], rax
0x1800c6ebb  lea     r8, ?DllRefCountSafeThreadThunk@@YAKPEAX@Z; lpStartAddress
0x1800c6ec2  lea     rax, ?ThreadId@Globals@@3KA; ulong Globals::ThreadId
0x1800c6ec9  mov     [rbx+10h], rsi
0x1800c6ecd  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800c6ed2  mov     r9, rbx; lpParameter
0x1800c6ed5  and     [rsp+38h+var_18], edi
0x1800c6ed9  xor     edx, edx; dwStackSize
0x1800c6edb  xor     ecx, ecx; lpThreadAttributes
0x1800c6edd  call    cs:__imp_CreateThread
0x1800c6ee4  nop     dword ptr [rax+rax+00h]
0x1800c6ee9  mov     rdi, rax
0x1800c6eec  test    rax, rax
0x1800c6eef  jz      short loc_1800C6F05
0x1800c6ef1  mov     rbx, [rsp+38h+arg_0]
0x1800c6ef6  mov     rax, rdi
0x1800c6ef9  mov     rsi, [rsp+38h+arg_8]
0x1800c6efe  add     rsp, 30h
0x1800c6f02  pop     rdi
0x1800c6f03  retn
0x1800c6f05  mov     rcx, rbx; this
0x1800c6f08  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800c6f0d  mov     rcx, rsi; hLibModule
0x1800c6f10  call    cs:__imp_FreeLibrary
0x1800c6f17  nop     dword ptr [rax+rax+00h]
0x1800c6f1c  jmp     short loc_1800C6EF1
```
