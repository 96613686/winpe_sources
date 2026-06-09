# CDoc::BrokerRegisterFileDragDrop(IDropTarget *)

- ea: `0x180860340`
- end: `0x1808604ea`
- name: `?BrokerRegisterFileDragDrop@CDoc@@AEAAJPEAUIDropTarget@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(CDoc *__hidden this, LPUNKNOWN pUnk)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1806e9ec0`

## callees

- `0x1801af6e0`
- `0x1801b0510`
- `0x180860340`
- `0x180861174`
- `0x180861a7c`
- `0x1810d1010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180860428`
- `msvcrt!memcpy_s` at `0x180860428`
- `KERNEL32!GlobalSize` at `0x1808603de`
- `KERNEL32!GlobalSize` at `0x1808603de`
- `KERNEL32!GlobalLock` at `0x1808603eb`
- `KERNEL32!GlobalLock` at `0x1808603eb`
- `KERNEL32!GlobalUnlock` at `0x1808604b3`
- `KERNEL32!GlobalUnlock` at `0x1808604b3`
- `api-ms-win-downlevel-ole32-l1-1-0!GetHGlobalFromStream` at `0x1808603ca`
- `api-ms-win-downlevel-ole32-l1-1-0!GetHGlobalFromStream` at `0x1808603ca`
- `api-ms-win-downlevel-ole32-l1-1-0!CoReleaseMarshalData` at `0x1808604c2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoReleaseMarshalData` at `0x1808604c2`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x18086037c`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x18086037c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180860402`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180860402`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18086049c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18086049c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterface` at `0x1808603aa`
- `api-ms-win-downlevel-ole32-l1-1-0!CoMarshalInterface` at `0x1808603aa`

## pseudocode

```c
__int64 __fastcall CDoc::BrokerRegisterFileDragDrop(CDoc *this, LPUNKNOWN pUnk)
{
  LPSTREAM *v4; // rax
  bool v5; // di
  HRESULT StreamOnHGlobal; // ebx
  unsigned int v7; // esi
  const void *v8; // r15
  unsigned int v9; // r14d
  void *v10; // rax
  void *v11; // rsi
  HWND v13; // [rsp+30h] [rbp-10h] BYREF
  LPSTREAM pStm; // [rsp+80h] [rbp+40h] BYREF
  HGLOBAL phglobal; // [rsp+88h] [rbp+48h] BYREF

  pStm = 0;
  v4 = (LPSTREAM *)TSmartPointer<ID3D11Device>::operator&(&pStm);
  v5 = 1;
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, v4);
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
        StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, void *))(**((_QWORD **)this + 80) + 1976LL))(
                            *((_QWORD *)this + 80),
                            *(_QWORD *)(*((_QWORD *)this + 12) + 168LL),
                            v9,
                            v11);
        if ( StreamOnHGlobal >= 0 )
        {
          StreamOnHGlobal = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete((char *)this + 616);
          if ( StreamOnHGlobal >= 0 )
            StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 80) + 1984LL))(*((_QWORD *)this + 80));
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
  TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&pStm);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x180860340  mov     [rsp-28h+arg_0], rbx
0x180860345  mov     [rsp-28h+arg_8], rsi
0x18086034a  push    rbp
0x18086034b  push    rdi
0x18086034c  push    r13
0x18086034e  push    r14
0x180860350  push    r15
0x180860352  mov     rbp, rsp
0x180860355  sub     rsp, 40h
0x180860359  mov     r13, rcx
0x18086035c  mov     [rbp+pStm], 0
0x180860364  lea     rcx, [rbp+pStm]
0x180860368  mov     rsi, rdx
0x18086036b  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x180860370  mov     edi, 1
0x180860375  mov     r8, rax; ppstm
0x180860378  mov     edx, edi; fDeleteOnRelease
0x18086037a  xor     ecx, ecx; hGlobal
0x18086037c  call    cs:__imp_CreateStreamOnHGlobal
0x180860382  mov     ebx, eax
0x180860384  test    eax, eax
0x180860386  jnz     loc_1808604C8
0x18086038c  mov     rcx, [rbp+pStm]; pStm
0x180860390  lea     rdx, IID_IDropTarget; riid
0x180860397  mov     [rsp+40h+mshlflags], edi; mshlflags
0x18086039b  xor     r9d, r9d; dwDestContext
0x18086039e  mov     r8, rsi; pUnk
0x1808603a1  mov     [rsp+40h+pvDestContext], 0; pvDestContext
0x1808603aa  call    cs:__imp_CoMarshalInterface
0x1808603b0  mov     ebx, eax
0x1808603b2  test    eax, eax
0x1808603b4  jnz     loc_1808604BE
0x1808603ba  mov     rcx, [rbp+pStm]; pstm
0x1808603be  lea     rdx, [rbp+phglobal]; phglobal
0x1808603c2  mov     [rbp+phglobal], 0
0x1808603ca  call    cs:__imp_GetHGlobalFromStream
0x1808603d0  mov     ebx, eax
0x1808603d2  test    eax, eax
0x1808603d4  jnz     loc_1808604BE
0x1808603da  mov     rcx, [rbp+phglobal]; hMem
0x1808603de  call    cs:__imp_GlobalSize
0x1808603e4  mov     rcx, [rbp+phglobal]; hMem
0x1808603e8  mov     rsi, rax
0x1808603eb  call    cs:__imp_GlobalLock
0x1808603f1  mov     r15, rax
0x1808603f4  test    rax, rax
0x1808603f7  jz      loc_1808604BE
0x1808603fd  mov     ecx, esi; cb
0x1808603ff  mov     r14d, esi
0x180860402  call    cs:__imp_CoTaskMemAlloc
0x180860408  mov     rsi, rax
0x18086040b  test    rax, rax
0x18086040e  jz      loc_1808604AA
0x180860414  mov     r9d, r14d; SourceSize
0x180860417  mov     [rbp+var_10], 0
0x18086041f  mov     r8, r15; Source
0x180860422  mov     edx, r14d; DestinationSize
0x180860425  mov     rcx, rax; Destination
0x180860428  call    cs:__imp_memcpy_s
0x18086042e  lea     r8, [rbp+var_10]; HWND *
0x180860432  xor     edx, edx; bool
0x180860434  mov     rcx, r13; this
0x180860437  call    ?PrepareBrokerCall@CDoc@@AEAAJ_NPEAPEAUHWND__@@@Z; CDoc::PrepareBrokerCall(bool,HWND__ * *)
0x18086043c  mov     ebx, eax
0x18086043e  test    eax, eax
0x180860440  jnz     short loc_180860499
0x180860442  mov     rdx, [r13+60h]
0x180860446  lea     rdi, [r13+268h]
0x18086044d  mov     rcx, [rdi+18h]
0x180860451  mov     r9, rsi
0x180860454  mov     r8d, r14d
0x180860457  mov     rdx, [rdx+0A8h]
0x18086045e  mov     rax, [rcx]
0x180860461  mov     rax, [rax+7B8h]
0x180860468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18086046d  mov     ebx, eax
0x18086046f  test    eax, eax
0x180860471  js      short loc_180860499
0x180860473  mov     rcx, rdi
0x180860476  call    ?WaitForCallComplete@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJPEAUHWND__@@I@Z; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(HWND__ *,uint)
0x18086047b  mov     ebx, eax
0x18086047d  test    eax, eax
0x18086047f  js      short loc_180860499
0x180860481  mov     rcx, [r13+280h]
0x180860488  mov     rax, [rcx]
0x18086048b  mov     rax, [rax+7C0h]
0x180860492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180860497  mov     ebx, eax
0x180860499  mov     rcx, rsi; pv
0x18086049c  call    cs:__imp_CoTaskMemFree
0x1808604a2  test    ebx, ebx
0x1808604a4  setnz   dil
0x1808604a8  jmp     short loc_1808604AF
0x1808604aa  mov     ebx, 8007000Eh
0x1808604af  mov     rcx, [rbp+phglobal]; hMem
0x1808604b3  call    cs:__imp_GlobalUnlock
0x1808604b9  test    dil, dil
0x1808604bc  jz      short loc_1808604C8
0x1808604be  mov     rcx, [rbp+pStm]; pStm
0x1808604c2  call    cs:__imp_CoReleaseMarshalData
0x1808604c8  lea     rcx, [rbp+pStm]; void *
0x1808604cc  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1808604d1  mov     rsi, [rsp+40h+arg_8]
0x1808604d6  mov     eax, ebx
0x1808604d8  mov     rbx, [rsp+40h+arg_0]
0x1808604dd  add     rsp, 40h
0x1808604e1  pop     r15
0x1808604e3  pop     r14
0x1808604e5  pop     r13
0x1808604e7  pop     rdi
0x1808604e8  pop     rbp
0x1808604e9  retn
```
