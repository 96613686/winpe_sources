# CtfImeProcessCicHotkey

- ea: `0x180044e20`
- end: `0x180045030`
- name: `CtfImeProcessCicHotkey`
- size: `528`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180018640`
- `0x18001cc80`
- `0x180044e20`
- `0x180045040`
- `0x1800831b8`
- `0x18010a010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x180044f80`
- `ntdll!RtlDllShutdownInProgress` at `0x180044f80`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180044fb8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180044fb8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044e43`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044e43`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044fa1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044fa1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045009`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045009`
- `IMM32!CtfImmIsCiceroStartedInThread` at `0x180044ecc`
- `IMM32!CtfImmIsCiceroStartedInThread` at `0x180044ecc`

## string_xrefs

- `0x180044f47`: `CtfImeProcessCicHotkey. TF_GetThreadMgr failed`
- `0x180044fcf`: `CtfImeProcessCicHotkey. IID_ITfThreadMgr_P==NULL`

## pseudocode

```c
__int64 __fastcall CtfImeProcessCicHotkey(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v4; // rsi
  unsigned int v5; // ebx
  struct tagSYSTHREAD *SYSTHREAD; // rax
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  __int64 v10; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v11[2]; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v12; // [rsp+68h] [rbp+20h] BYREF

  v4 = a2;
  if ( TLS::dwTLSIndex == -1 )
    goto LABEL_25;
  if ( !TlsGetValue(TLS::dwTLSIndex) )
  {
    if ( !RtlDllShutdownInProgress() )
    {
      if ( (unsigned int)_IsFlsCallbackNotCalled() )
      {
        v8 = LocalAlloc(0x40u, 0x38u);
        v9 = v8;
        if ( v8 )
        {
          if ( TlsSetValue(TLS::dwTLSIndex, v8) )
          {
            v9[6] |= 1u;
            v9[8] |= 1u;
            goto LABEL_3;
          }
          LocalFree(v9);
        }
      }
    }
LABEL_25:
    CicTrace(1u, "CtfImeProcessCicHotkey. ptls==NULL.");
    return 0;
  }
LABEL_3:
  v5 = 0;
  SYSTHREAD = GetSYSTHREAD();
  v10 = 0;
  if ( !SYSTHREAD
    || !*(_QWORD *)SYSTHREAD
    || (***(unsigned int (__fastcall ****)(_QWORD, GUID *, __int64 *))SYSTHREAD)(
         *(_QWORD *)SYSTHREAD,
         &IID_ITfThreadMgr,
         &v10) )
  {
    CicTrace(2u, "CtfImeProcessCicHotkey. TF_GetThreadMgr failed");
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      return 0;
    }
    return v5;
  }
  v11[0] = 0;
  if ( v10
    && ((**(void (__fastcall ***)(__int64, GUID *, _QWORD *))v10)(v10, &GUID_7c6247a1_2884_4b7c_af24_f198047aa728, v11),
        v11[0]) )
  {
    if ( (unsigned int)CtfImmIsCiceroStartedInThread() )
    {
      v12 = 0;
      if ( (*(int (__fastcall **)(_QWORD, __int64, __int64, unsigned int *))(*(_QWORD *)v11[0] + 144LL))(
             v11[0],
             v4,
             a3,
             &v12) >= 0 )
      {
        v5 = v12;
        if ( v11[0] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v11[0] + 16LL))(v11[0]);
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        return v5;
      }
      CicTrace(2u, "CtfImeProcessCicHotkey. CallImm32HotkeyHandler returns Error.");
    }
  }
  else
  {
    CicTrace(2u, "CtfImeProcessCicHotkey. IID_ITfThreadMgr_P==NULL");
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v11);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  return 0;
}

```

## disassembly

```asm
0x180044e20  mov     [rsp+arg_0], rbx
0x180044e25  mov     [rsp+arg_8], rsi
0x180044e2a  push    rdi
0x180044e2b  sub     rsp, 40h
0x180044e2f  mov     ecx, cs:?dwTLSIndex@TLS@@0KA; dwTlsIndex
0x180044e35  mov     rdi, r8
0x180044e38  mov     esi, edx
0x180044e3a  cmp     ecx, 0FFFFFFFFh
0x180044e3d  jz      loc_18004500F
0x180044e43  call    cs:__imp_TlsGetValue
0x180044e49  test    rax, rax
0x180044e4c  jz      loc_180044F80
0x180044e52  xor     ebx, ebx
0x180044e54  mov     [rsp+48h+var_18], rbx
0x180044e59  call    ?GetSYSTHREAD@@YAPEAUtagSYSTHREAD@@XZ; GetSYSTHREAD(void)
0x180044e5e  mov     [rsp+48h+var_18], rbx
0x180044e63  test    rax, rax
0x180044e66  jz      loc_180044F47
0x180044e6c  mov     rcx, [rax]
0x180044e6f  test    rcx, rcx
0x180044e72  jz      loc_180044F47
0x180044e78  mov     rax, [rcx]
0x180044e7b  lea     r8, [rsp+48h+var_18]
0x180044e80  lea     rdx, IID_ITfThreadMgr
0x180044e87  mov     rax, [rax]
0x180044e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e8f  test    eax, eax
0x180044e91  jnz     loc_180044F47
0x180044e97  mov     rcx, [rsp+48h+var_18]
0x180044e9c  mov     [rsp+48h+var_10], rbx
0x180044ea1  test    rcx, rcx
0x180044ea4  jz      loc_180044FCF
0x180044eaa  mov     rax, [rcx]
0x180044ead  lea     r8, [rsp+48h+var_10]
0x180044eb2  lea     rdx, _GUID_7c6247a1_2884_4b7c_af24_f198047aa728
0x180044eb9  mov     rax, [rax]
0x180044ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ec1  cmp     [rsp+48h+var_10], rbx
0x180044ec6  jz      loc_180044FCF
0x180044ecc  call    cs:__imp_CtfImmIsCiceroStartedInThread
0x180044ed2  test    eax, eax
0x180044ed4  jz      loc_180044FE0
0x180044eda  mov     rcx, [rsp+48h+var_10]
0x180044edf  lea     r9, [rsp+48h+arg_18]
0x180044ee4  mov     [rsp+48h+arg_18], ebx
0x180044ee8  mov     rdx, rsi
0x180044eeb  mov     r8, rdi
0x180044eee  mov     rax, [rcx]
0x180044ef1  mov     rax, [rax+90h]
0x180044ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044efd  test    eax, eax
0x180044eff  js      loc_180045027
0x180044f05  mov     rcx, [rsp+48h+var_10]
0x180044f0a  mov     ebx, [rsp+48h+arg_18]
0x180044f0e  test    rcx, rcx
0x180044f11  jz      short loc_180044F1F
0x180044f13  mov     rax, [rcx]
0x180044f16  mov     rax, [rax+10h]
0x180044f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f1f  mov     rcx, [rsp+48h+var_18]
0x180044f24  test    rcx, rcx
0x180044f27  jz      short loc_180044F35
0x180044f29  mov     rdx, [rcx]
0x180044f2c  mov     rax, [rdx+10h]
0x180044f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f35  mov     eax, ebx
0x180044f37  mov     rbx, [rsp+48h+arg_0]
0x180044f3c  mov     rsi, [rsp+48h+arg_8]
0x180044f41  add     rsp, 40h
0x180044f45  pop     rdi
0x180044f46  retn
0x180044f47  lea     rdx, aCtfimeprocessc_1; "CtfImeProcessCicHotkey. TF_GetThreadMgr"...
0x180044f4e  mov     ecx, 2; unsigned int
0x180044f53  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180044f58  mov     rcx, [rsp+48h+var_18]
0x180044f5d  test    rcx, rcx
0x180044f60  jz      short loc_180044F35
0x180044f62  mov     rax, [rcx]
0x180044f65  mov     rax, [rax+10h]
0x180044f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f6e  mov     eax, ebx
0x180044f70  mov     rbx, [rsp+48h+arg_0]
0x180044f75  mov     rsi, [rsp+48h+arg_8]
0x180044f7a  add     rsp, 40h
0x180044f7e  pop     rdi
0x180044f7f  retn
0x180044f80  call    cs:__imp_RtlDllShutdownInProgress
0x180044f86  test    al, al
0x180044f88  jnz     loc_18004500F
0x180044f8e  call    ?_IsFlsCallbackNotCalled@@YAHXZ; _IsFlsCallbackNotCalled(void)
0x180044f93  test    eax, eax
0x180044f95  jz      short loc_18004500F
0x180044f97  mov     edx, 38h ; '8'; uBytes
0x180044f9c  mov     ecx, 40h ; '@'; uFlags
0x180044fa1  call    cs:__imp_LocalAlloc
0x180044fa7  mov     rbx, rax
0x180044faa  test    rax, rax
0x180044fad  jz      short loc_18004500F
0x180044faf  mov     ecx, cs:?dwTLSIndex@TLS@@0KA; dwTlsIndex
0x180044fb5  mov     rdx, rax; lpTlsValue
0x180044fb8  call    cs:__imp_TlsSetValue
0x180044fbe  test    eax, eax
0x180044fc0  jz      short loc_180045006
0x180044fc2  or      dword ptr [rbx+18h], 1
0x180044fc6  or      dword ptr [rbx+20h], 1
0x180044fca  jmp     loc_180044E52
0x180044fcf  lea     rdx, aCtfimeprocessc_0; "CtfImeProcessCicHotkey. IID_ITfThreadMg"...
0x180044fd6  mov     ecx, 2; unsigned int
0x180044fdb  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180044fe0  lea     rcx, [rsp+48h+var_10]
0x180044fe5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180044fea  lea     rcx, [rsp+48h+var_18]
0x180044fef  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180044ff4  mov     rsi, [rsp+48h+arg_8]
0x180044ff9  mov     eax, ebx
0x180044ffb  mov     rbx, [rsp+48h+arg_0]
0x180045000  add     rsp, 40h
0x180045004  pop     rdi
0x180045005  retn
0x180045006  mov     rcx, rbx; hMem
0x180045009  call    cs:__imp_LocalFree
0x18004500f  lea     rdx, aCtfimeprocessc_2; "CtfImeProcessCicHotkey. ptls==NULL."
0x180045016  mov     ecx, 1; unsigned int
0x18004501b  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180045020  xor     ebx, ebx
0x180045022  jmp     loc_180044F35
0x180045027  lea     rdx, aCtfimeprocessc_3; "CtfImeProcessCicHotkey. CallImm32Hotkey"...
0x18004502e  jmp     short loc_180044FD6
```
