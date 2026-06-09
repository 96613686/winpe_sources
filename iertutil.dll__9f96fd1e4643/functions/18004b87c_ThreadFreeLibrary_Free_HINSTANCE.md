# ThreadFreeLibrary::Free(HINSTANCE__ *)

- ea: `0x18004b87c`
- end: `0x18004b917`
- name: `?Free@ThreadFreeLibrary@@SAXPEAUHINSTANCE__@@@Z`
- size: `155`
- prototype: `void __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004b870`

## callees

- `0x18004b87c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b8ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b8ac`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18004b906`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18004b906`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004b8f3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004b8f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18004b8bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18004b8bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b89b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b89b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b889`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b889`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18004b8e7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18004b8e7`

## pseudocode

```c
void __fastcall ThreadFreeLibrary::Free(HINSTANCE a1)
{
  HANDLE ProcessHeap; // rax
  void **v3; // rax
  void **v4; // rbx
  DWORD CurrentThreadId; // eax
  HANDLE v6; // rax
  LPVOID Value; // rax
  DWORD v8; // ecx

  ProcessHeap = GetProcessHeap();
  v3 = (void **)HeapAlloc(ProcessHeap, 8u, 0x20u);
  v4 = v3;
  if ( v3 )
  {
    *v3 = a1;
    CurrentThreadId = GetCurrentThreadId();
    v6 = OpenThread(0x100000u, 0, CurrentThreadId);
    v4[1] = v6;
    RegisterWaitForSingleObject(v4 + 2, v6, ThreadFreeLibrary::WaitCallback, v4, 0xFFFFFFFF, 0x18u);
    Value = TlsGetValue(ThreadFreeLibrary::TLS);
    v8 = ThreadFreeLibrary::TLS;
    v4[3] = Value;
    TlsSetValue(v8, v4);
  }
}

```

## disassembly

```asm
0x18004b87c  mov     [rsp+arg_0], rbx
0x18004b881  push    rdi
0x18004b882  sub     rsp, 30h
0x18004b886  mov     rdi, rcx
0x18004b889  call    cs:__imp_GetProcessHeap
0x18004b88f  mov     edx, 8; dwFlags
0x18004b894  mov     rcx, rax; hHeap
0x18004b897  lea     r8d, [rdx+18h]; dwBytes
0x18004b89b  call    cs:__imp_HeapAlloc
0x18004b8a1  mov     rbx, rax
0x18004b8a4  test    rax, rax
0x18004b8a7  jz      short loc_18004B90C
0x18004b8a9  mov     [rax], rdi
0x18004b8ac  call    cs:__imp_GetCurrentThreadId
0x18004b8b2  xor     edx, edx; bInheritHandle
0x18004b8b4  mov     ecx, 100000h; dwDesiredAccess
0x18004b8b9  mov     r8d, eax; dwThreadId
0x18004b8bc  call    cs:__imp_OpenThread
0x18004b8c2  lea     rcx, [rbx+10h]; phNewWaitObject
0x18004b8c6  mov     [rsp+38h+dwFlags], 18h; dwFlags
0x18004b8ce  mov     rdx, rax; hObject
0x18004b8d1  mov     [rbx+8], rax
0x18004b8d5  mov     r9, rbx; Context
0x18004b8d8  mov     [rsp+38h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18004b8e0  lea     r8, ?WaitCallback@ThreadFreeLibrary@@CAXPEAXE@Z; Callback
0x18004b8e7  call    cs:__imp_RegisterWaitForSingleObject
0x18004b8ed  mov     ecx, cs:?TLS@ThreadFreeLibrary@@0KA; dwTlsIndex
0x18004b8f3  call    cs:__imp_TlsGetValue
0x18004b8f9  mov     ecx, cs:?TLS@ThreadFreeLibrary@@0KA; dwTlsIndex
0x18004b8ff  mov     rdx, rbx; lpTlsValue
0x18004b902  mov     [rbx+18h], rax
0x18004b906  call    cs:__imp_TlsSetValue
0x18004b90c  mov     rbx, [rsp+38h+arg_0]
0x18004b911  add     rsp, 30h
0x18004b915  pop     rdi
0x18004b916  retn
```
