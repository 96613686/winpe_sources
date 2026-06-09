# CCscWmiCacheEnumThread::_DoWork(IWbemServices *,IWbemContext *,IWbemObjectSink *,CWmiAsyncCancelMonitor *,void *)

- ea: `0x180017a30`
- end: `0x180017bfe`
- name: `?_DoWork@CCscWmiCacheEnumThread@@EEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@PEAVCWmiAsyncCancelMonitor@@PEAX@Z`
- size: `462`
- prototype: `int(CCscWmiCacheEnumThread *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemObjectSink *, struct CWmiAsyncCancelMonitor *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800161b8`
- `0x180016280`
- `0x1800162b4`
- `0x180016f50`
- `0x1800173c0`
- `0x180017a30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180017a88`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180017a88`

## pseudocode

```c
__int64 __fastcall CCscWmiCacheEnumThread::_DoWork(
        CCscWmiCacheEnumThread *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemObjectSink *a4,
        struct CWmiAsyncCancelMonitor *a5,
        struct IWbemObjectSink *a6)
{
  struct IOfflineFilesCache *v7; // rcx
  HRESULT InterfaceAndReleaseStream; // ebx
  CWmiAsyncCancelMonitor *v11; // r15
  int v12; // eax
  CCscControlWmiEnum *v13; // r14
  CRefCounted *v14; // rsi
  unsigned int v15; // r13d
  struct IWbemObjectSink *v16; // r15
  int v17; // r12d
  HRESULT v18; // eax
  int v20; // [rsp+20h] [rbp-30h]
  LPVOID ppv; // [rsp+30h] [rbp-20h] BYREF
  struct IWbemClassObject *v22; // [rsp+38h] [rbp-18h] BYREF
  CRefCounted *v23; // [rsp+40h] [rbp-10h] BYREF
  struct CCscWmiCacheEnum *v24; // [rsp+90h] [rbp+40h] BYREF
  struct IWbemObjectSink *v25; // [rsp+A8h] [rbp+58h]

  v25 = a4;
  v7 = 0;
  ppv = 0;
  InterfaceAndReleaseStream = *((_DWORD *)this + 42);
  if ( InterfaceAndReleaseStream >= 0 )
  {
    if ( *((_QWORD *)this + 20) )
    {
      InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(
                                    *((LPSTREAM *)this + 20),
                                    &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5,
                                    &ppv);
      if ( InterfaceAndReleaseStream < 0 )
      {
LABEL_17:
        v7 = (struct IOfflineFilesCache *)ppv;
        goto LABEL_18;
      }
      v7 = (struct IOfflineFilesCache *)ppv;
      *((_QWORD *)this + 20) = 0;
    }
    v11 = a5;
    v20 = *((_DWORD *)this + 45);
    v24 = 0;
    InterfaceAndReleaseStream = CCscWmiCacheEnum::CreateInstance(a2, a3, a5, v7, v20, &v24);
    if ( InterfaceAndReleaseStream >= 0 )
    {
      v23 = 0;
      v12 = CWmiAsyncCancelMonitor::Register(v11, a6, &v23);
      v13 = v24;
      InterfaceAndReleaseStream = v12;
      if ( v12 >= 0 )
      {
        v14 = v23;
        v15 = 0;
        v16 = v25;
        v22 = 0;
        v17 = *((_DWORD *)this + 45) & 0x80;
        do
        {
          if ( v15 >= *((_DWORD *)this + 44) )
            break;
          InterfaceAndReleaseStream = CCscControlWmiEnum::NextAlreadyImpersonating(
                                        v13,
                                        -1,
                                        1u,
                                        &v22,
                                        (unsigned int *)&v24);
          if ( InterfaceAndReleaseStream )
            break;
          ++v15;
          ((void (__fastcall *)(struct IWbemObjectSink *, __int64, struct IWbemClassObject **))v16->lpVtbl->Indicate)(
            v16,
            1,
            &v22);
          ((void (__fastcall *)(struct IWbemClassObject *))v22->lpVtbl->Release)(v22);
          if ( v17 )
            ((void (__fastcall *)(struct IWbemObjectSink *, _QWORD, _QWORD, _QWORD, _QWORD))v16->lpVtbl->SetStatus)(
              v16,
              (unsigned int)(InterfaceAndReleaseStream + 2),
              0,
              0,
              0);
        }
        while ( !*((_DWORD *)v14 + 4) );
        CWmiAsyncCancelMonitor::Unregister(a5, v14);
        CRefCounted::ReleaseReference(v14);
        v18 = 0;
        if ( InterfaceAndReleaseStream != 1 )
          v18 = InterfaceAndReleaseStream;
        InterfaceAndReleaseStream = v18;
      }
      (*(void (__fastcall **)(CCscControlWmiEnum *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    goto LABEL_17;
  }
LABEL_18:
  if ( v7 )
    ((void (__fastcall *)(struct IOfflineFilesCache *))v7->lpVtbl->Release)(v7);
  return (unsigned int)InterfaceAndReleaseStream;
}

```

## disassembly

```asm
0x180017a30  mov     [rsp-38h+arg_8], rbx
0x180017a35  mov     [rsp-38h+arg_18], r9
0x180017a3a  push    rbp
0x180017a3b  push    rsi
0x180017a3c  push    rdi
0x180017a3d  push    r12
0x180017a3f  push    r13
0x180017a41  push    r14
0x180017a43  push    r15
0x180017a45  mov     rbp, rsp
0x180017a48  sub     rsp, 50h
0x180017a4c  mov     rdi, rcx
0x180017a4f  xor     r12d, r12d
0x180017a52  mov     ecx, r12d
0x180017a55  mov     rsi, r8
0x180017a58  mov     r14, rdx
0x180017a5b  mov     [rbp+ppv], rcx
0x180017a5f  mov     ebx, [rdi+0A8h]
0x180017a65  test    ebx, ebx
0x180017a67  js      loc_180017BD3
0x180017a6d  cmp     [rdi+0A0h], r12
0x180017a74  jz      short loc_180017AA3
0x180017a76  mov     rcx, [rdi+0A0h]; pStm
0x180017a7d  lea     r8, [rbp+ppv]; ppv
0x180017a81  lea     rdx, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; iid
0x180017a88  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180017a8e  mov     ebx, eax
0x180017a90  test    eax, eax
0x180017a92  js      loc_180017BCF
0x180017a98  mov     rcx, [rbp+ppv]
0x180017a9c  mov     [rdi+0A0h], r12
0x180017aa3  mov     r15, [rbp+arg_20]
0x180017aa7  lea     rax, [rbp+arg_0]
0x180017aab  mov     [rsp+50h+var_28], rax; struct CCscWmiCacheEnum **
0x180017ab0  mov     r9, rcx; struct IOfflineFilesCache *
0x180017ab3  mov     eax, [rdi+0B4h]
0x180017ab9  mov     r8, r15; struct CWmiAsyncCancelMonitor *
0x180017abc  mov     rdx, rsi; struct IWbemContext *
0x180017abf  mov     dword ptr [rsp+50h+var_30], eax; int
0x180017ac3  mov     rcx, r14; struct IWbemServices *
0x180017ac6  mov     [rbp+arg_0], r12
0x180017aca  call    ?CreateInstance@CCscWmiCacheEnum@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAVCWmiAsyncCancelMonitor@@PEAUIOfflineFilesCache@@JPEAPEAV1@@Z; CCscWmiCacheEnum::CreateInstance(IWbemServices *,IWbemContext *,CWmiAsyncCancelMonitor *,IOfflineFilesCache *,long,CCscWmiCacheEnum * *)
0x180017acf  mov     ebx, eax
0x180017ad1  test    eax, eax
0x180017ad3  js      loc_180017BCF
0x180017ad9  mov     rdx, [rbp+arg_28]; struct IWbemObjectSink *
0x180017add  lea     r8, [rbp+var_10]; struct CWmiAsyncCancelState **
0x180017ae1  mov     rcx, r15; this
0x180017ae4  mov     [rbp+var_10], r12
0x180017ae8  call    ?Register@CWmiAsyncCancelMonitor@@QEAAJPEAUIWbemObjectSink@@PEAPEAVCWmiAsyncCancelState@@@Z; CWmiAsyncCancelMonitor::Register(IWbemObjectSink *,CWmiAsyncCancelState * *)
0x180017aed  mov     r14, [rbp+arg_0]
0x180017af1  mov     ebx, eax
0x180017af3  test    eax, eax
0x180017af5  js      loc_180017BC0
0x180017afb  mov     rsi, [rbp+var_10]
0x180017aff  mov     r13d, r12d
0x180017b02  mov     r15, [rbp+arg_18]
0x180017b06  mov     [rbp+var_18], r12
0x180017b0a  mov     r12d, [rdi+0B4h]
0x180017b11  and     r12d, 80h
0x180017b18  cmp     r13d, [rdi+0B0h]
0x180017b1f  jnb     short loc_180017B9E
0x180017b21  lea     rax, [rbp+arg_0]
0x180017b25  mov     r8d, 1; unsigned int
0x180017b2b  lea     r9, [rbp+var_18]; struct IWbemClassObject **
0x180017b2f  mov     [rsp+50h+var_30], rax; unsigned int *
0x180017b34  or      edx, 0FFFFFFFFh; int
0x180017b37  mov     rcx, r14; this
0x180017b3a  call    ?NextAlreadyImpersonating@CCscControlWmiEnum@@QEAAJJKPEAPEAUIWbemClassObject@@PEAK@Z; CCscControlWmiEnum::NextAlreadyImpersonating(long,ulong,IWbemClassObject * *,ulong *)
0x180017b3f  mov     ebx, eax
0x180017b41  test    eax, eax
0x180017b43  jnz     short loc_180017B9E
0x180017b45  mov     rax, [r15]
0x180017b48  lea     r8, [rbp+var_18]
0x180017b4c  lea     edx, [rbx+1]
0x180017b4f  mov     rcx, r15
0x180017b52  inc     r13d
0x180017b55  mov     rax, [rax+18h]
0x180017b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b5e  mov     rcx, [rbp+var_18]
0x180017b62  mov     rax, [rcx]
0x180017b65  mov     rax, [rax+10h]
0x180017b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b6e  test    r12d, r12d
0x180017b71  jz      short loc_180017B94
0x180017b73  mov     rax, [r15]
0x180017b76  lea     edx, [rbx+2]
0x180017b79  xor     r9d, r9d
0x180017b7c  mov     [rsp+50h+var_30], 0
0x180017b85  xor     r8d, r8d
0x180017b88  mov     rcx, r15
0x180017b8b  mov     rax, [rax+20h]
0x180017b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b94  cmp     dword ptr [rsi+10h], 0
0x180017b98  jz      loc_180017B18
0x180017b9e  mov     rcx, [rbp+arg_20]; this
0x180017ba2  mov     rdx, rsi; struct CWmiAsyncCancelState *
0x180017ba5  call    ?Unregister@CWmiAsyncCancelMonitor@@QEAAXPEAVCWmiAsyncCancelState@@@Z; CWmiAsyncCancelMonitor::Unregister(CWmiAsyncCancelState *)
0x180017baa  mov     rcx, rsi; this
0x180017bad  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x180017bb2  xor     r12d, r12d
0x180017bb5  cmp     ebx, 1
0x180017bb8  mov     eax, r12d
0x180017bbb  cmovnz  eax, ebx
0x180017bbe  mov     ebx, eax
0x180017bc0  mov     rax, [r14]
0x180017bc3  mov     rcx, r14
0x180017bc6  mov     rax, [rax+10h]
0x180017bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bcf  mov     rcx, [rbp+ppv]
0x180017bd3  test    rcx, rcx
0x180017bd6  jz      short loc_180017BE4
0x180017bd8  mov     rax, [rcx]
0x180017bdb  mov     rax, [rax+10h]
0x180017bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017be4  mov     eax, ebx
0x180017be6  mov     rbx, [rsp+50h+arg_8]
0x180017bee  add     rsp, 50h
0x180017bf2  pop     r15
0x180017bf4  pop     r14
0x180017bf6  pop     r13
0x180017bf8  pop     r12
0x180017bfa  pop     rdi
0x180017bfb  pop     rsi
0x180017bfc  pop     rbp
0x180017bfd  retn
```
