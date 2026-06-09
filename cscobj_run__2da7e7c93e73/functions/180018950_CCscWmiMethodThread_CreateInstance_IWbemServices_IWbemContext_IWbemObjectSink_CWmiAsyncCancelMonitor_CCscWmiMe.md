# CCscWmiMethodThread::CreateInstance(IWbemServices *,IWbemContext *,IWbemObjectSink *,CWmiAsyncCancelMonitor *,CCscWmiMethod *,IWbemClassObject *,long,CCscWmiMethodThread * *)

- ea: `0x180018950`
- end: `0x180018a1f`
- name: `?CreateInstance@CCscWmiMethodThread@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@PEAVCWmiAsyncCancelMonitor@@PEAVCCscWmiMethod@@PEAUIWbemClassObject@@JPEAPEAV1@@Z`
- size: `207`
- prototype: `__int64 __fastcall(struct IWbemServices *, struct IWbemContext *, struct IWbemObjectSink *, struct CWmiAsyncCancelMonitor *, struct CCscWmiMethod *, LPUNKNOWN pUnk, int, struct CCscWmiMethodThread **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019934`

## callees

- `0x18000b390`
- `0x180018950`
- `0x18002660c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1800189d7`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1800189d7`

## pseudocode

```c
__int64 __fastcall CCscWmiMethodThread::CreateInstance(
        struct IWbemServices *a1,
        struct IWbemContext *a2,
        struct IWbemObjectSink *a3,
        struct CWmiAsyncCancelMonitor *a4,
        struct CCscWmiMethod *a5,
        LPUNKNOWN pUnk,
        int a7,
        struct CCscWmiMethodThread **a8)
{
  unsigned int v12; // edi
  CCscWmiAsyncThread *v13; // rax
  CCscWmiAsyncThread *v14; // rbx

  v12 = -2147024882;
  v13 = (CCscWmiAsyncThread *)operator new(0xC0u);
  v14 = v13;
  if ( v13 )
  {
    CCscWmiAsyncThread::CCscWmiAsyncThread(v13, a1, a2, a3, a4);
    *(_QWORD *)v14 = &CCscWmiMethodThread::`vftable';
    *((_QWORD *)v14 + 20) = 0;
    *((_DWORD *)v14 + 42) = 0;
    *((_QWORD *)v14 + 19) = pUnk;
    if ( pUnk )
      *((_DWORD *)v14 + 42) = CoMarshalInterThreadInterfaceInStream(
                                &GUID_dc12a681_737f_11cf_884d_00aa004b2e24,
                                pUnk,
                                (LPSTREAM *)v14 + 20);
    *((_QWORD *)v14 + 22) = a5;
    *((_DWORD *)v14 + 46) = a7;
    _InterlockedIncrement((volatile signed __int32 *)a5 + 2);
    v12 = 0;
    *a8 = v14;
  }
  return v12;
}

```

## disassembly

```asm
0x180018950  push    rbx
0x180018952  push    rbp
0x180018953  push    rsi
0x180018954  push    rdi
0x180018955  push    r14
0x180018957  push    r15
0x180018959  sub     rsp, 38h
0x18001895d  mov     r15, rcx
0x180018960  mov     rsi, r9
0x180018963  mov     ecx, 0C0h; Size
0x180018968  mov     rbp, r8
0x18001896b  mov     r14, rdx
0x18001896e  mov     edi, 8007000Eh
0x180018973  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018978  mov     rbx, rax
0x18001897b  test    rax, rax
0x18001897e  jz      loc_180018A10
0x180018984  mov     r9, rbp; struct IWbemObjectSink *
0x180018987  mov     [rsp+68h+var_48], rsi; struct CWmiAsyncCancelMonitor *
0x18001898c  mov     r8, r14; struct IWbemContext *
0x18001898f  mov     rdx, r15; struct IWbemServices *
0x180018992  mov     rcx, rax; this
0x180018995  call    ??0CCscWmiAsyncThread@@QEAA@PEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@PEAVCWmiAsyncCancelMonitor@@@Z; CCscWmiAsyncThread::CCscWmiAsyncThread(IWbemServices *,IWbemContext *,IWbemObjectSink *,CWmiAsyncCancelMonitor *)
0x18001899a  mov     rdx, [rsp+68h+pUnk]; pUnk
0x1800189a2  lea     rax, ??_7CCscWmiMethodThread@@6B@; const CCscWmiMethodThread::`vftable'
0x1800189a9  mov     [rbx], rax
0x1800189ac  lea     r8, [rbx+0A0h]; ppStm
0x1800189b3  mov     qword ptr [r8], 0
0x1800189ba  mov     dword ptr [rbx+0A8h], 0
0x1800189c4  mov     [rbx+98h], rdx
0x1800189cb  test    rdx, rdx
0x1800189ce  jz      short loc_1800189E3
0x1800189d0  lea     rcx, _GUID_dc12a681_737f_11cf_884d_00aa004b2e24; riid
0x1800189d7  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1800189dd  mov     [rbx+0A8h], eax
0x1800189e3  mov     rcx, [rsp+68h+arg_20]
0x1800189eb  mov     eax, [rsp+68h+arg_30]
0x1800189f2  mov     [rbx+0B0h], rcx
0x1800189f9  mov     [rbx+0B8h], eax
0x1800189ff  lock inc dword ptr [rcx+8]
0x180018a03  mov     rax, [rsp+68h+arg_38]
0x180018a0b  xor     edi, edi
0x180018a0d  mov     [rax], rbx
0x180018a10  mov     eax, edi
0x180018a12  add     rsp, 38h
0x180018a16  pop     r15
0x180018a18  pop     r14
0x180018a1a  pop     rdi
0x180018a1b  pop     rsi
0x180018a1c  pop     rbp
0x180018a1d  pop     rbx
0x180018a1e  retn
```
