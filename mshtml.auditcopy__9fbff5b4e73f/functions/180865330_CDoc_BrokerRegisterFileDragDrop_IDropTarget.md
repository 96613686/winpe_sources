# CDoc::BrokerRegisterFileDragDrop(IDropTarget *)

- ea: `0x180865330`
- end: `0x180865517`
- name: `?BrokerRegisterFileDragDrop@CDoc@@AEAAJPEAUIDropTarget@@@Z`
- size: `487`
- prototype: `__int64 __fastcall(CDoc *__hidden this, LPUNKNOWN pUnk)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1806ecfb0`

## callees

- `0x180013efc`
- `0x1800c5000`
- `0x180865330`
- `0x180866244`
- `0x180866bb4`
- `0x181104010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18086543c`
- `msvcrt!memcpy_s` at `0x18086543c`
- `KERNEL32!GlobalSize` at `0x1808653e0`
- `KERNEL32!GlobalSize` at `0x1808653e0`
- `KERNEL32!GlobalLock` at `0x1808653f3`
- `KERNEL32!GlobalLock` at `0x1808653f3`
- `KERNEL32!GlobalUnlock` at `0x1808654d3`
- `KERNEL32!GlobalUnlock` at `0x1808654d3`
- `api-ms-win-downlevel-ole32-l1-1-0!GetHGlobalFromStream` at `0x1808653c6`
- `api-ms-win-downlevel-ole32-l1-1-0!GetHGlobalFromStream` at `0x1808653c6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoReleaseMarshalData` at `0x1808654e8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoReleaseMarshalData` at `0x1808654e8`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x18086536c`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x18086536c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180865410`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180865410`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1808654b6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1808654b6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterface` at `0x1808653a0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterface` at `0x1808653a0`

## pseudocode

```c
__int64 __fastcall CDoc::BrokerRegisterFileDragDrop(struct IEUserBroker **this, LPUNKNOWN pUnk)
{
  __int64 *v4; // rax
  bool v5; // di
  int StreamOnHGlobal; // ebx
  unsigned int v7; // esi
  const void *v8; // r15
  unsigned int v9; // r14d
  void *v10; // rax
  void *v11; // rsi
  HWND v13; // [rsp+30h] [rbp-10h] BYREF
  LPSTREAM pStm; // [rsp+80h] [rbp+40h] BYREF
  HGLOBAL phglobal; // [rsp+88h] [rbp+48h] BYREF

  pStm = 0;
  v4 = TSmartPointer<ID3D11Device>::operator&((__int64 *)&pStm);
  v5 = 1;
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, (LPSTREAM *)v4);
  if ( !StreamOnHGlobal )
  {
    StreamOnHGlobal = CoMarshalInterface(pStm, &IID_IDropTarget, pUnk, 0, 0, 1u);
    if ( StreamOnHGlobal )
      goto LABEL_13;
    phglobal = 0;
    StreamOnHGlobal = GetHGlobalFromStream(pStm, &phglobal);
    if ( StreamOnHGlobal )
      goto LABEL_13;
    v7 = GlobalSize(phglobal);
    v8 = GlobalLock(phglobal);
    if ( !v8 )
      goto LABEL_13;
    v9 = v7;
    v10 = CoTaskMemAlloc(v7);
    v11 = v10;
    if ( v10 )
    {
      v13 = 0;
      memcpy_s(v10, v9, v8, v9);
      StreamOnHGlobal = CDoc::PrepareBrokerCall(this, 0, &v13);
      if ( !StreamOnHGlobal )
      {
        StreamOnHGlobal = (*(__int64 (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, void *))(*(_QWORD *)this[80] + 1976LL))(
                            this[80],
                            *((_QWORD *)this[12] + 21),
                            v9,
                            v11);
        if ( StreamOnHGlobal >= 0 )
        {
          StreamOnHGlobal = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete((__int64)(this + 77));
          if ( StreamOnHGlobal >= 0 )
            StreamOnHGlobal = (*(__int64 (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)this[80] + 1984LL))(this[80]);
        }
      }
      CoTaskMemFree(v11);
      v5 = StreamOnHGlobal != 0;
    }
    else
    {
      StreamOnHGlobal = -2147024882;
    }
    GlobalUnlock(phglobal);
    if ( v5 )
LABEL_13:
      CoReleaseMarshalData(pStm);
  }
  TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>((__int64 *)&pStm);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x180865330  mov     [rsp-28h+arg_0], rbx
0x180865335  mov     [rsp-28h+arg_8], rsi
0x18086533a  push    rbp
0x18086533b  push    rdi
0x18086533c  push    r13
0x18086533e  push    r14
0x180865340  push    r15
0x180865342  mov     rbp, rsp
0x180865345  sub     rsp, 40h
0x180865349  mov     r13, rcx
0x18086534c  mov     [rbp+pStm], 0
0x180865354  lea     rcx, [rbp+pStm]
0x180865358  mov     rsi, rdx
0x18086535b  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x180865360  mov     edi, 1
0x180865365  mov     r8, rax; ppstm
0x180865368  mov     edx, edi; fDeleteOnRelease
0x18086536a  xor     ecx, ecx; hGlobal
0x18086536c  call    cs:__imp_CreateStreamOnHGlobal
0x180865373  nop     dword ptr [rax+rax+00h]
0x180865378  mov     ebx, eax
0x18086537a  test    eax, eax
0x18086537c  jnz     loc_1808654F4
0x180865382  mov     rcx, [rbp+pStm]; pStm
0x180865386  lea     rdx, IID_IDropTarget; riid
0x18086538d  mov     [rsp+40h+mshlflags], edi; mshlflags
0x180865391  xor     r9d, r9d; dwDestContext
0x180865394  mov     r8, rsi; pUnk
0x180865397  mov     [rsp+40h+pvDestContext], 0; pvDestContext
0x1808653a0  call    cs:__imp_CoMarshalInterface
0x1808653a7  nop     dword ptr [rax+rax+00h]
0x1808653ac  mov     ebx, eax
0x1808653ae  test    eax, eax
0x1808653b0  jnz     loc_1808654E4
0x1808653b6  mov     rcx, [rbp+pStm]; pstm
0x1808653ba  lea     rdx, [rbp+phglobal]; phglobal
0x1808653be  mov     [rbp+phglobal], 0
0x1808653c6  call    cs:__imp_GetHGlobalFromStream
0x1808653cd  nop     dword ptr [rax+rax+00h]
0x1808653d2  mov     ebx, eax
0x1808653d4  test    eax, eax
0x1808653d6  jnz     loc_1808654E4
0x1808653dc  mov     rcx, [rbp+phglobal]; hMem
0x1808653e0  call    cs:__imp_GlobalSize
0x1808653e7  nop     dword ptr [rax+rax+00h]
0x1808653ec  mov     rcx, [rbp+phglobal]; hMem
0x1808653f0  mov     rsi, rax
0x1808653f3  call    cs:__imp_GlobalLock
0x1808653fa  nop     dword ptr [rax+rax+00h]
0x1808653ff  mov     r15, rax
0x180865402  test    rax, rax
0x180865405  jz      loc_1808654E4
0x18086540b  mov     ecx, esi; cb
0x18086540d  mov     r14d, esi
0x180865410  call    cs:__imp_CoTaskMemAlloc
0x180865417  nop     dword ptr [rax+rax+00h]
0x18086541c  mov     rsi, rax
0x18086541f  test    rax, rax
0x180865422  jz      loc_1808654CA
0x180865428  mov     r9d, r14d; SourceSize
0x18086542b  mov     [rbp+var_10], 0
0x180865433  mov     r8, r15; Source
0x180865436  mov     edx, r14d; DestinationSize
0x180865439  mov     rcx, rax; Destination
0x18086543c  call    cs:__imp_memcpy_s
0x180865443  nop     dword ptr [rax+rax+00h]
0x180865448  lea     r8, [rbp+var_10]; HWND *
0x18086544c  xor     edx, edx; bool
0x18086544e  mov     rcx, r13; this
0x180865451  call    ?PrepareBrokerCall@CDoc@@AEAAJ_NPEAPEAUHWND__@@@Z; CDoc::PrepareBrokerCall(bool,HWND__ * *)
0x180865456  mov     ebx, eax
0x180865458  test    eax, eax
0x18086545a  jnz     short loc_1808654B3
0x18086545c  mov     rdx, [r13+60h]
0x180865460  lea     rdi, [r13+268h]
0x180865467  mov     rcx, [rdi+18h]
0x18086546b  mov     r9, rsi
0x18086546e  mov     r8d, r14d
0x180865471  mov     rdx, [rdx+0A8h]
0x180865478  mov     rax, [rcx]
0x18086547b  mov     rax, [rax+7B8h]
0x180865482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180865487  mov     ebx, eax
0x180865489  test    eax, eax
0x18086548b  js      short loc_1808654B3
0x18086548d  mov     rcx, rdi
0x180865490  call    ?WaitForCallComplete@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJPEAUHWND__@@I@Z; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(HWND__ *,uint)
0x180865495  mov     ebx, eax
0x180865497  test    eax, eax
0x180865499  js      short loc_1808654B3
0x18086549b  mov     rcx, [r13+280h]
0x1808654a2  mov     rax, [rcx]
0x1808654a5  mov     rax, [rax+7C0h]
0x1808654ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808654b1  mov     ebx, eax
0x1808654b3  mov     rcx, rsi; pv
0x1808654b6  call    cs:__imp_CoTaskMemFree
0x1808654bd  nop     dword ptr [rax+rax+00h]
0x1808654c2  test    ebx, ebx
0x1808654c4  setnz   dil
0x1808654c8  jmp     short loc_1808654CF
0x1808654ca  mov     ebx, 8007000Eh
0x1808654cf  mov     rcx, [rbp+phglobal]; hMem
0x1808654d3  call    cs:__imp_GlobalUnlock
0x1808654da  nop     dword ptr [rax+rax+00h]
0x1808654df  test    dil, dil
0x1808654e2  jz      short loc_1808654F4
0x1808654e4  mov     rcx, [rbp+pStm]; pStm
0x1808654e8  call    cs:__imp_CoReleaseMarshalData
0x1808654ef  nop     dword ptr [rax+rax+00h]
0x1808654f4  lea     rcx, [rbp+pStm]; void *
0x1808654f8  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1808654fd  mov     rsi, [rsp+40h+arg_8]
0x180865502  mov     eax, ebx
0x180865504  mov     rbx, [rsp+40h+arg_0]
0x180865509  add     rsp, 40h
0x18086550d  pop     r15
0x18086550f  pop     r14
0x180865511  pop     r13
0x180865513  pop     rdi
0x180865514  pop     rbp
0x180865515  retn
```
