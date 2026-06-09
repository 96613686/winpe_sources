# CCscWmiAsyncThread::CCscWmiAsyncThread(IWbemServices *,IWbemContext *,IWbemObjectSink *,CWmiAsyncCancelMonitor *)

- ea: `0x18002660c`
- end: `0x180026700`
- name: `??0CCscWmiAsyncThread@@QEAA@PEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@PEAVCWmiAsyncCancelMonitor@@@Z`
- size: `244`
- prototype: `CCscWmiAsyncThread *(CCscWmiAsyncThread *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemObjectSink *, struct CWmiAsyncCancelMonitor *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800171d8`
- `0x1800176e0`
- `0x180018950`

## callees

- `0x18002660c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180026661`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180026687`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1800266b0`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180026661`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180026687`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1800266b0`

## pseudocode

```c
CCscWmiAsyncThread *__fastcall CCscWmiAsyncThread::CCscWmiAsyncThread(
        CCscWmiAsyncThread *this,
        IUnknown *a2,
        IUnknown *a3,
        IUnknown *a4,
        struct CWmiAsyncCancelMonitor *a5)
{
  *((_DWORD *)this + 2) = 1;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 3) = 0;
  *(_QWORD *)this = &CCscWmiAsyncThread::`vftable';
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 8) = a2;
  if ( a2 )
    *((_DWORD *)this + 20) = CoMarshalInterThreadInterfaceInStream(
                               &GUID_9556dc99_828c_11cf_a37e_00aa003240c7,
                               a2,
                               (LPSTREAM *)this + 9);
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 11) = a3;
  if ( a3 )
    *((_DWORD *)this + 26) = CoMarshalInterThreadInterfaceInStream(
                               &GUID_44aca674_e8fc_11d0_a07c_00c04fb68820,
                               a3,
                               (LPSTREAM *)this + 12);
  *((_DWORD *)this + 32) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 14) = a4;
  if ( a4 )
    *((_DWORD *)this + 32) = CoMarshalInterThreadInterfaceInStream(
                               &GUID_7c857801_7381_11cf_884d_00aa004b2e24,
                               a4,
                               (LPSTREAM *)this + 15);
  *((_QWORD *)this + 18) = a5;
  *((_QWORD *)this + 17) = a4;
  _InterlockedIncrement(&g_cRefDll);
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 18) + 8LL));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 8LL))(*((_QWORD *)this + 17));
  return this;
}

```

## disassembly

```asm
0x18002660c  push    rbx
0x18002660e  push    rbp
0x18002660f  push    rsi
0x180026610  push    rdi
0x180026611  sub     rsp, 28h
0x180026615  xor     ebp, ebp
0x180026617  mov     dword ptr [rcx+8], 1
0x18002661e  mov     [rcx+10h], ebp
0x180026621  mov     rsi, r8
0x180026624  mov     [rcx+18h], rbp
0x180026628  lea     rax, ??_7CCscWmiAsyncThread@@6B@; const CCscWmiAsyncThread::`vftable'
0x18002662f  mov     [rcx], rax
0x180026632  lea     r8, [rcx+48h]; ppStm
0x180026636  mov     [rcx+20h], rbp
0x18002663a  mov     rdi, r9
0x18002663d  mov     [rcx+28h], rbp
0x180026641  mov     rbx, rcx
0x180026644  mov     [rcx+30h], rbp
0x180026648  mov     [rcx+38h], ebp
0x18002664b  mov     [r8], rbp
0x18002664e  mov     [rcx+50h], ebp
0x180026651  mov     [rcx+40h], rdx
0x180026655  test    rdx, rdx
0x180026658  jz      short loc_18002666A
0x18002665a  lea     rcx, _GUID_9556dc99_828c_11cf_a37e_00aa003240c7; riid
0x180026661  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180026667  mov     [rbx+50h], eax
0x18002666a  mov     [rbx+68h], ebp
0x18002666d  lea     r8, [rbx+60h]; ppStm
0x180026671  mov     [r8], rbp
0x180026674  mov     [rbx+58h], rsi
0x180026678  test    rsi, rsi
0x18002667b  jz      short loc_180026690
0x18002667d  mov     rdx, rsi; pUnk
0x180026680  lea     rcx, _GUID_44aca674_e8fc_11d0_a07c_00c04fb68820; riid
0x180026687  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18002668d  mov     [rbx+68h], eax
0x180026690  mov     [rbx+80h], ebp
0x180026696  lea     r8, [rbx+78h]; ppStm
0x18002669a  mov     [r8], rbp
0x18002669d  mov     [rbx+70h], rdi
0x1800266a1  test    rdi, rdi
0x1800266a4  jz      short loc_1800266BC
0x1800266a6  mov     rdx, rdi; pUnk
0x1800266a9  lea     rcx, _GUID_7c857801_7381_11cf_884d_00aa004b2e24; riid
0x1800266b0  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1800266b6  mov     [rbx+80h], eax
0x1800266bc  mov     rax, [rsp+48h+arg_20]
0x1800266c1  mov     [rbx+90h], rax
0x1800266c8  mov     [rbx+88h], rdi
0x1800266cf  lock inc cs:?g_cRefDll@@3JA; long g_cRefDll
0x1800266d6  mov     rax, [rbx+90h]
0x1800266dd  lock inc dword ptr [rax+8]
0x1800266e1  mov     rcx, [rbx+88h]
0x1800266e8  mov     rax, [rcx]
0x1800266eb  mov     rax, [rax+8]
0x1800266ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266f4  mov     rax, rbx
0x1800266f7  add     rsp, 28h
0x1800266fb  pop     rdi
0x1800266fc  pop     rsi
0x1800266fd  pop     rbp
0x1800266fe  pop     rbx
0x1800266ff  retn
```
