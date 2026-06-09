# CCscWmiMethodThread::_DoWork(IWbemServices *,IWbemContext *,IWbemObjectSink *,CWmiAsyncCancelMonitor *,void *)

- ea: `0x180019c00`
- end: `0x180019d4f`
- name: `?_DoWork@CCscWmiMethodThread@@EEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@PEAVCWmiAsyncCancelMonitor@@PEAX@Z`
- size: `335`
- prototype: `int(CCscWmiMethodThread *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemObjectSink *, struct CWmiAsyncCancelMonitor *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x180019140`
- `0x180019c00`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180019cc0`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180019cc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c5f`

## pseudocode

```c
__int64 __fastcall CCscWmiMethodThread::_DoWork(
        CCscWmiMethodThread *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemObjectSink *a4)
{
  __int64 v8; // rcx
  DWORD CurrentThreadId; // eax
  HRESULT InterfaceAndReleaseStream; // ebx
  struct IWbemClassObject *v12; // [rsp+28h] [rbp-40h]
  LPVOID ppv; // [rsp+70h] [rbp+8h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 40, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v8 != &WPP_GLOBAL_Control && (*(_DWORD *)(v8 + 28) & 0x4000000) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        41,
        WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
        CurrentThreadId);
      v8 = WPP_GLOBAL_Control;
    }
  }
  InterfaceAndReleaseStream = *((_DWORD *)this + 42);
  ppv = 0;
  if ( InterfaceAndReleaseStream >= 0 )
  {
    if ( *((_QWORD *)this + 20) )
    {
      InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(
                                    *((LPSTREAM *)this + 20),
                                    &GUID_dc12a681_737f_11cf_884d_00aa004b2e24,
                                    &ppv);
      if ( InterfaceAndReleaseStream >= 0 )
      {
        v12 = (struct IWbemClassObject *)ppv;
        *((_QWORD *)this + 20) = 0;
        InterfaceAndReleaseStream = CCscWmiMethod::Execute(
                                      *((CCscWmiMethod **)this + 22),
                                      a2,
                                      a3,
                                      a4,
                                      *((_DWORD *)this + 46),
                                      v12);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      v8 = WPP_GLOBAL_Control;
    }
    else
    {
      InterfaceAndReleaseStream = -2147467259;
    }
  }
  if ( (_UNKNOWN *)v8 != &WPP_GLOBAL_Control && (*(_DWORD *)(v8 + 28) & 0x4000000) != 0 )
    WPP_SF_d(
      *(_QWORD *)(v8 + 16),
      42,
      WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
      (unsigned int)InterfaceAndReleaseStream);
  return (unsigned int)InterfaceAndReleaseStream;
}

```

## disassembly

```asm
0x180019c00  push    rbx
0x180019c02  push    rbp
0x180019c03  push    rsi
0x180019c04  push    rdi
0x180019c05  push    r12
0x180019c07  push    r14
0x180019c09  sub     rsp, 38h
0x180019c0d  mov     rsi, r9
0x180019c10  mov     rbp, r8
0x180019c13  mov     r14, rdx
0x180019c16  mov     rdi, rcx
0x180019c19  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c20  lea     r12, WPP_GLOBAL_Control
0x180019c27  cmp     rcx, r12
0x180019c2a  jz      short loc_180019C8B
0x180019c2c  test    dword ptr [rcx+1Ch], 4000000h
0x180019c33  jz      short loc_180019C51
0x180019c35  mov     rcx, [rcx+10h]
0x180019c39  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x180019c40  mov     edx, 28h ; '('
0x180019c45  call    WPP_SF_
0x180019c4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c51  cmp     rcx, r12
0x180019c54  jz      short loc_180019C8B
0x180019c56  test    dword ptr [rcx+1Ch], 4000000h
0x180019c5d  jz      short loc_180019C8B
0x180019c5f  call    cs:__imp_GetCurrentThreadId
0x180019c65  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c6c  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x180019c73  mov     edx, 29h ; ')'
0x180019c78  mov     r9d, eax
0x180019c7b  mov     rcx, [rcx+10h]
0x180019c7f  call    WPP_SF_d
0x180019c84  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c8b  mov     ebx, [rdi+0A8h]
0x180019c91  mov     [rsp+68h+ppv], 0
0x180019c9a  test    ebx, ebx
0x180019c9c  js      short loc_180019D1A
0x180019c9e  mov     rax, [rdi+0A0h]
0x180019ca5  test    rax, rax
0x180019ca8  jnz     short loc_180019CB1
0x180019caa  mov     ebx, 80004005h
0x180019caf  jmp     short loc_180019D1A
0x180019cb1  lea     r8, [rsp+68h+ppv]; ppv
0x180019cb6  mov     rcx, rax; pStm
0x180019cb9  lea     rdx, _GUID_dc12a681_737f_11cf_884d_00aa004b2e24; iid
0x180019cc0  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180019cc6  mov     ebx, eax
0x180019cc8  test    eax, eax
0x180019cca  js      short loc_180019D13
0x180019ccc  mov     rax, [rsp+68h+ppv]
0x180019cd1  mov     r9, rsi; struct IWbemObjectSink *
0x180019cd4  mov     [rsp+68h+var_40], rax; struct IWbemClassObject *
0x180019cd9  mov     r8, rbp; struct IWbemContext *
0x180019cdc  mov     qword ptr [rdi+0A0h], 0
0x180019ce7  mov     rdx, r14; struct IWbemServices *
0x180019cea  mov     eax, [rdi+0B8h]
0x180019cf0  mov     rcx, [rdi+0B0h]; this
0x180019cf7  mov     [rsp+68h+var_48], eax; int
0x180019cfb  call    ?Execute@CCscWmiMethod@@QEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@JPEAUIWbemClassObject@@@Z; CCscWmiMethod::Execute(IWbemServices *,IWbemContext *,IWbemObjectSink *,long,IWbemClassObject *)
0x180019d00  mov     rcx, [rsp+68h+ppv]
0x180019d05  mov     ebx, eax
0x180019d07  mov     rdx, [rcx]
0x180019d0a  mov     rax, [rdx+10h]
0x180019d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d13  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d1a  cmp     rcx, r12
0x180019d1d  jz      short loc_180019D40
0x180019d1f  test    dword ptr [rcx+1Ch], 4000000h
0x180019d26  jz      short loc_180019D40
0x180019d28  mov     rcx, [rcx+10h]
0x180019d2c  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x180019d33  mov     edx, 2Ah ; '*'
0x180019d38  mov     r9d, ebx
0x180019d3b  call    WPP_SF_d
0x180019d40  mov     eax, ebx
0x180019d42  add     rsp, 38h
0x180019d46  pop     r14
0x180019d48  pop     r12
0x180019d4a  pop     rdi
0x180019d4b  pop     rsi
0x180019d4c  pop     rbp
0x180019d4d  pop     rbx
0x180019d4e  retn
```
