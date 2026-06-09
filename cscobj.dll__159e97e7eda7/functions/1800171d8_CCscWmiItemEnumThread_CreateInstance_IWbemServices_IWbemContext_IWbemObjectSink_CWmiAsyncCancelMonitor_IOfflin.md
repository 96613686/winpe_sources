# CCscWmiItemEnumThread::CreateInstance(IWbemServices *,IWbemContext *,IWbemObjectSink *,CWmiAsyncCancelMonitor *,IOfflineFilesItemContainer *,IOfflineFilesItem *,ulong,long,CCscWmiItemEnumThread * *)

- ea: `0x1800171d8`
- end: `0x1800172e0`
- name: `?CreateInstance@CCscWmiItemEnumThread@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@PEAVCWmiAsyncCancelMonitor@@PEAUIOfflineFilesItemContainer@@PEAUIOfflineFilesItem@@KJPEAPEAV1@@Z`
- size: `264`
- prototype: `__int64 __fastcall(struct IWbemServices *, struct IWbemContext *, struct IWbemObjectSink *, struct CWmiAsyncCancelMonitor *, LPUNKNOWN pUnk, LPUNKNOWN, unsigned int, int, struct CCscWmiItemEnumThread **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017784`

## callees

- `0x18000b390`
- `0x1800171d8`
- `0x18002660c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18001725f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18001729e`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18001725f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18001729e`

## pseudocode

```c
__int64 __fastcall CCscWmiItemEnumThread::CreateInstance(
        IUnknown *a1,
        IUnknown *a2,
        IUnknown *a3,
        struct CWmiAsyncCancelMonitor *a4,
        LPUNKNOWN pUnk,
        LPUNKNOWN a6,
        unsigned int a7,
        int a8,
        struct CCscWmiItemEnumThread **a9)
{
  unsigned int v13; // edi
  CCscWmiAsyncThread *v14; // rax
  CCscWmiAsyncThread *v15; // rbx

  v13 = -2147024882;
  v14 = (CCscWmiAsyncThread *)operator new(0xD0u);
  v15 = v14;
  if ( v14 )
  {
    CCscWmiAsyncThread::CCscWmiAsyncThread(v14, a1, a2, a3, a4);
    *(_QWORD *)v15 = &CCscWmiItemEnumThread::`vftable';
    *((_QWORD *)v15 + 20) = 0;
    *((_DWORD *)v15 + 42) = 0;
    *((_QWORD *)v15 + 19) = pUnk;
    if ( pUnk )
      *((_DWORD *)v15 + 42) = CoMarshalInterThreadInterfaceInStream(
                                &GUID_3836f049_9413_45dd_bf46_b5aaa82dc310,
                                pUnk,
                                (LPSTREAM *)v15 + 20);
    *((_QWORD *)v15 + 23) = 0;
    *((_DWORD *)v15 + 48) = 0;
    *((_QWORD *)v15 + 22) = a6;
    if ( a6 )
      *((_DWORD *)v15 + 48) = CoMarshalInterThreadInterfaceInStream(
                                &GUID_4a753da6_e044_4f12_a718_5d14d079a906,
                                a6,
                                (LPSTREAM *)v15 + 23);
    v13 = 0;
    *((_DWORD *)v15 + 50) = a7;
    *((_DWORD *)v15 + 51) = a8;
    *a9 = v15;
  }
  return v13;
}

```

## disassembly

```asm
0x1800171d8  push    rbx
0x1800171da  push    rbp
0x1800171db  push    rsi
0x1800171dc  push    rdi
0x1800171dd  push    r14
0x1800171df  push    r15
0x1800171e1  sub     rsp, 38h
0x1800171e5  mov     r15, rcx
0x1800171e8  mov     rsi, r9
0x1800171eb  mov     ecx, 0D0h; Size
0x1800171f0  mov     rbp, r8
0x1800171f3  mov     r14, rdx
0x1800171f6  mov     edi, 8007000Eh
0x1800171fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017200  mov     rbx, rax
0x180017203  test    rax, rax
0x180017206  jz      loc_1800172D1
0x18001720c  mov     r9, rbp; struct IWbemObjectSink *
0x18001720f  mov     [rsp+68h+var_48], rsi; struct CWmiAsyncCancelMonitor *
0x180017214  mov     r8, r14; struct IWbemContext *
0x180017217  mov     rdx, r15; struct IWbemServices *
0x18001721a  mov     rcx, rax; this
0x18001721d  call    ??0CCscWmiAsyncThread@@QEAA@PEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@PEAVCWmiAsyncCancelMonitor@@@Z; CCscWmiAsyncThread::CCscWmiAsyncThread(IWbemServices *,IWbemContext *,IWbemObjectSink *,CWmiAsyncCancelMonitor *)
0x180017222  mov     rdx, [rsp+68h+pUnk]; pUnk
0x18001722a  lea     rax, ??_7CCscWmiItemEnumThread@@6B@; const CCscWmiItemEnumThread::`vftable'
0x180017231  mov     [rbx], rax
0x180017234  lea     r8, [rbx+0A0h]; ppStm
0x18001723b  mov     qword ptr [r8], 0
0x180017242  mov     dword ptr [rbx+0A8h], 0
0x18001724c  mov     [rbx+98h], rdx
0x180017253  test    rdx, rdx
0x180017256  jz      short loc_18001726B
0x180017258  lea     rcx, _GUID_3836f049_9413_45dd_bf46_b5aaa82dc310; riid
0x18001725f  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180017265  mov     [rbx+0A8h], eax
0x18001726b  mov     rdx, [rsp+68h+arg_28]; pUnk
0x180017273  lea     r8, [rbx+0B8h]; ppStm
0x18001727a  mov     qword ptr [r8], 0
0x180017281  mov     dword ptr [rbx+0C0h], 0
0x18001728b  mov     [rbx+0B0h], rdx
0x180017292  test    rdx, rdx
0x180017295  jz      short loc_1800172AA
0x180017297  lea     rcx, _GUID_4a753da6_e044_4f12_a718_5d14d079a906; riid
0x18001729e  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1800172a4  mov     [rbx+0C0h], eax
0x1800172aa  mov     eax, [rsp+68h+arg_30]
0x1800172b1  xor     edi, edi
0x1800172b3  mov     [rbx+0C8h], eax
0x1800172b9  mov     eax, [rsp+68h+arg_38]
0x1800172c0  mov     [rbx+0CCh], eax
0x1800172c6  mov     rax, [rsp+68h+arg_40]
0x1800172ce  mov     [rax], rbx
0x1800172d1  mov     eax, edi
0x1800172d3  add     rsp, 38h
0x1800172d7  pop     r15
0x1800172d9  pop     r14
0x1800172db  pop     rdi
0x1800172dc  pop     rsi
0x1800172dd  pop     rbp
0x1800172de  pop     rbx
0x1800172df  retn
```
