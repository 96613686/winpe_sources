# CreateThreadAndAddRefDll(_SECURITY_ATTRIBUTES *,unsigned __int64,ulong (*)(void *),void *,ulong,ulong *)

- ea: `0x1800cdd14`
- end: `0x1800cdddc`
- name: `?CreateThreadAndAddRefDll@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@_KP6AKPEAX@Z2KPEAK@Z`
- size: `200`
- prototype: `void *__fastcall(struct _SECURITY_ATTRIBUTES *, unsigned __int64, unsigned int (*)(void *), void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800cdc48`

## callees

- `0x1800cdd14`
- `0x1800cdde4`
- `0x1800e8864`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cddc4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cddc4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cdd50`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cdd50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cdd3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cdd3b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800cdd99`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800cdd99`

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
0x1800cdd14  mov     rax, rsp
0x1800cdd17  mov     [rax+8], rbx
0x1800cdd1b  mov     [rax+10h], rsi
0x1800cdd1f  mov     [rax+20h], r9
0x1800cdd23  push    rdi
0x1800cdd24  sub     rsp, 30h
0x1800cdd28  xor     edi, edi
0x1800cdd2a  lea     rcx, [rax+20h]; HINSTANCE *
0x1800cdd2e  mov     [rax+20h], rdi
0x1800cdd32  call    ?AddRefModule@@YAHPEAPEAUHINSTANCE__@@@Z; AddRefModule(HINSTANCE__ * *)
0x1800cdd37  test    eax, eax
0x1800cdd39  jz      short loc_1800CDDAD
0x1800cdd3b  call    cs:__imp_GetProcessHeap
0x1800cdd42  nop     dword ptr [rax+rax+00h]
0x1800cdd47  xor     edx, edx; dwFlags
0x1800cdd49  lea     r8d, [rdi+18h]; dwBytes
0x1800cdd4d  mov     rcx, rax; hHeap
0x1800cdd50  call    cs:__imp_HeapAlloc
0x1800cdd57  nop     dword ptr [rax+rax+00h]
0x1800cdd5c  mov     rsi, [rsp+38h+hLibModule]
0x1800cdd61  mov     rbx, rax
0x1800cdd64  test    rax, rax
0x1800cdd67  jz      short loc_1800CDDC1
0x1800cdd69  lea     rax, ?BackgroundThreadProc@@YAKPEAX@Z; BackgroundThreadProc(void *)
0x1800cdd70  mov     [rbx+8], rdi
0x1800cdd74  mov     [rbx], rax
0x1800cdd77  lea     r8, ?DllRefCountSafeThreadThunk@@YAKPEAX@Z; lpStartAddress
0x1800cdd7e  lea     rax, ?ThreadId@Globals@@3KA; ulong Globals::ThreadId
0x1800cdd85  mov     [rbx+10h], rsi
0x1800cdd89  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800cdd8e  mov     r9, rbx; lpParameter
0x1800cdd91  xor     edx, edx; dwStackSize
0x1800cdd93  mov     [rsp+38h+dwCreationFlags], edi; dwCreationFlags
0x1800cdd97  xor     ecx, ecx; lpThreadAttributes
0x1800cdd99  call    cs:__imp_CreateThread
0x1800cdda0  nop     dword ptr [rax+rax+00h]
0x1800cdda5  mov     rdi, rax
0x1800cdda8  test    rax, rax
0x1800cddab  jz      short loc_1800CDDD2
0x1800cddad  mov     rbx, [rsp+38h+arg_0]
0x1800cddb2  mov     rax, rdi
0x1800cddb5  mov     rsi, [rsp+38h+arg_8]
0x1800cddba  add     rsp, 30h
0x1800cddbe  pop     rdi
0x1800cddbf  retn
0x1800cddc1  mov     rcx, rsi; hLibModule
0x1800cddc4  call    cs:__imp_FreeLibrary
0x1800cddcb  nop     dword ptr [rax+rax+00h]
0x1800cddd0  jmp     short loc_1800CDDAD
0x1800cddd2  mov     rcx, rbx; this
0x1800cddd5  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800cddda  jmp     short loc_1800CDDC1
```
