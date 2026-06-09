# CicBridge::OnSysKeyboardProc(unsigned __int64,__int64)

- ea: `0x1800447a0`
- end: `0x180044e13`
- name: `?OnSysKeyboardProc@CicBridge@@UEAAJ_K_J@Z`
- size: `1651`
- prototype: `int(CicBridge *__hidden this, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800185f0`
- `0x180018640`
- `0x18001a460`
- `0x18001b210`
- `0x18001cc80`
- `0x1800447a0`
- `0x180045040`
- `0x180045074`
- `0x1800454c0`
- `0x180045520`
- `0x180065884`
- `0x1800e1468`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x180044ac7`
- `ntdll!RtlDllShutdownInProgress` at `0x180044ac7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180044b07`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180044b07`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800447e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800447e3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044aec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044d66`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044aec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044d66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044b25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044bf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044c4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044c58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044b25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044bf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044c4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044c58`
- `USER32!PostMessageW` at `0x180044cd1`
- `USER32!PostMessageW` at `0x180044cd1`
- `USER32!ToUnicode` at `0x180044d3b`
- `USER32!ToUnicode` at `0x180044d3b`
- `USER32!GetKeyboardState` at `0x180044a0d`
- `USER32!GetKeyboardState` at `0x180044a0d`
- `USER32!GetFocus` at `0x180044868`
- `USER32!GetFocus` at `0x180044c29`
- `USER32!GetFocus` at `0x180044dd6`
- `USER32!GetFocus` at `0x180044868`
- `USER32!GetFocus` at `0x180044c29`
- `USER32!GetFocus` at `0x180044dd6`
- `USER32!GetKeyboardLayout` at `0x180044a1d`
- `USER32!GetKeyboardLayout` at `0x180044a1d`
- `IMM32!ImmGetContext` at `0x1800449df`
- `IMM32!ImmGetContext` at `0x1800449df`
- `IMM32!ImmGetAppCompatFlags` at `0x1800449cb`
- `IMM32!ImmGetAppCompatFlags` at `0x1800449cb`
- `ext-ms-win-imm-l1-1-0!ImmGetProperty` at `0x180044a2b`
- `ext-ms-win-imm-l1-1-0!ImmGetProperty` at `0x180044a2b`

## pseudocode

```c
__int64 __fastcall CicBridge::OnSysKeyboardProc(CicBridge *this, __int64 a2, unsigned __int64 a3)
{
  struct ITfThreadMgr_P **Value; // rsi
  struct ITfThreadMgr_P *v5; // rbx
  HWND Focus; // r15
  __int64 (__fastcall **v7)(__int64, GUID *, unsigned int *); // rax
  int v8; // edi
  char v9; // di
  int v10; // r14d
  HIMC Context; // rax
  HIMC v13; // rdi
  HKL KeyboardLayout; // rax
  DWORD Property; // r14d
  unsigned __int64 v16; // r12
  CicBridge *v17; // r13
  unsigned int v18; // r15d
  struct ITfThreadMgr_P **v19; // rax
  __int64 v20; // r13
  struct tagTRANSMSG *v21; // rdi
  HWND v22; // rax
  CicBridge *v23; // rcx
  unsigned int v24; // r15d
  struct tagTRANSMSGLIST *v25; // rax
  struct tagTRANSMSGLIST *v26; // r14
  unsigned int v27; // eax
  int v28; // ebx
  HWND v29; // rax
  CicBridge *v30; // rcx
  __int64 wFlagsa; // [rsp+28h] [rbp-D8h]
  unsigned __int8 *wFlags; // [rsp+28h] [rbp-D8h]
  unsigned __int8 *v33; // [rsp+30h] [rbp-D0h]
  unsigned int v34; // [rsp+38h] [rbp-C8h]
  WCHAR pwszBuff; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v36)(__int64, GUID *, unsigned int *); // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v37[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v38[2]; // [rsp+68h] [rbp-98h] BYREF
  struct ITfThreadMgr_P *v39; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+78h] [rbp-88h] BYREF
  char v41[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v42; // [rsp+88h] [rbp-78h]
  int v43; // [rsp+98h] [rbp-68h]
  CicBridge *v44; // [rsp+A0h] [rbp-60h]
  unsigned int v45[2]; // [rsp+A8h] [rbp-58h]
  struct tagTRANSMSG *v46[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v47; // [rsp+C0h] [rbp-40h]
  int v48; // [rsp+C8h] [rbp-38h]
  LPARAM lParam; // [rsp+D0h] [rbp-30h]
  BYTE KeyState[256]; // [rsp+E0h] [rbp-20h] BYREF

  v44 = this;
  lParam = a3;
  *(_QWORD *)v45 = a2;
  if ( TLS::dwTLSIndex == -1 )
    goto LABEL_52;
  Value = (struct ITfThreadMgr_P **)TlsGetValue(TLS::dwTLSIndex);
  if ( Value )
    goto LABEL_3;
  if ( RtlDllShutdownInProgress()
    || !(unsigned int)_IsFlsCallbackNotCalled()
    || (v19 = (struct ITfThreadMgr_P **)LocalAlloc(0x40u, 0x38u), (Value = v19) == 0) )
  {
LABEL_52:
    CicTrace(2u, "CicBridge::OnSysKeyboardProc. ptls==NULL.");
    return 1;
  }
  if ( !TlsSetValue(TLS::dwTLSIndex, v19) )
  {
    LocalFree(Value);
    goto LABEL_52;
  }
  *((_DWORD *)Value + 6) |= 1u;
  *((_DWORD *)Value + 8) |= 1u;
LABEL_3:
  v5 = Value[2];
  v39 = v5;
  if ( !v5 )
  {
    CicTrace(2u, "CicBridge::OnSysKeyboardProc. ptim_P==NULL");
    return 1;
  }
  (*(void (__fastcall **)(struct ITfThreadMgr_P *))(*(_QWORD *)v5 + 8LL))(v5);
  v40 = 0;
  if ( (*(int (__fastcall **)(struct ITfThreadMgr_P *, int *))(*(_QWORD *)v5 + 136LL))(v5, &v40) < 0 )
  {
    CicTrace(2u, "CicBridge::OnSysKeyboardProc. IsKeystrokeFeedEnabled return error.");
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
    return 1;
  }
  if ( !v40 )
  {
    (*(void (__fastcall **)(struct ITfThreadMgr_P *))(*(_QWORD *)v5 + 16LL))(v5);
    return 1;
  }
  Focus = GetFocus();
  if ( Focus )
  {
    v36 = 0;
    (*(void (__fastcall **)(struct ITfThreadMgr_P *, __int64 (__fastcall ****)(__int64, GUID *, unsigned int *)))(*(_QWORD *)v5 + 56LL))(
      v5,
      &v36);
    if ( v36 )
    {
      *(_QWORD *)v38 = 0;
      v47 = 0;
      v7 = *v36;
      *(_QWORD *)v37 = 0;
      *(_OWORD *)v46 = 0;
      v8 = (*v7)((__int64)v36, &IID_ITfCompartmentMgr, v38);
      if ( v8 >= 0 )
      {
        if ( !*(_QWORD *)v38 )
        {
LABEL_16:
          if ( v36 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, unsigned int *)))(*v36)[2])(v36);
          goto LABEL_18;
        }
        v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, unsigned int *))(**(_QWORD **)v38 + 24LL))(
               *(_QWORD *)v38,
               &GUID_COMPARTMENT_CTFIME_DIMFLAGS,
               v37);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v38 + 16LL))(*(_QWORD *)v38);
      }
      if ( v8 >= 0 )
      {
        v9 = 0;
        v10 = (*(__int64 (__fastcall **)(_QWORD, struct tagTRANSMSG **))(**(_QWORD **)v37 + 32LL))(*(_QWORD *)v37, v46);
        if ( !v10 )
          v9 = (char)v46[1];
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v37 + 16LL))(*(_QWORD *)v37);
        if ( v10 >= 0 && (v9 & 1) != 0 && (ImmGetAppCompatFlags(0) & 0xD000000) != 0 )
        {
          Context = ImmGetContext(Focus);
          v13 = Context;
          if ( Context )
          {
            if ( (unsigned int)MsimtfIsGuidMapEnable(Context) )
            {
              if ( !GetKeyboardState(KeyState) )
                goto LABEL_38;
              KeyboardLayout = GetKeyboardLayout(0);
              Property = ImmGetProperty(KeyboardLayout, 4u);
              v16 = a3 >> 16;
              if ( (a3 & 0x10000000) != 0 )
                goto LABEL_38;
              LOWORD(v37[0]) = WORD1(a3) & 0x8000;
              if ( (a3 & 0x80000000) != 0 && (Property & 4) != 0 )
                goto LABEL_38;
              if ( (a3 & 0x20000000) != 0 && (Property & 8) == 0 )
                goto LABEL_38;
              v38[0] = 0;
              wFlagsa = a3;
              v17 = v44;
              if ( !CicBridge::ProcessKey(v44, (struct TLS *)Value, v5, v13, v45[0], wFlagsa, v33, (int *)v38) )
              {
                v18 = 1;
LABEL_41:
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
                return v18;
              }
              if ( v38[0] )
              {
                IMCLock::IMCLock((IMCLock *)v41, v13);
                v20 = v42;
                if ( !v42 )
                {
                  v18 = -2147467259;
                  IMCLock::~IMCLock((IMCLock *)v41);
                  goto LABEL_41;
                }
                v18 = v43;
                if ( v43 >= 0 )
                {
                  PostMessageW(*(HWND *)v42, (LOWORD(v37[0]) != 0) + 256, 0xE5u, lParam);
                  *(_DWORD *)(v20 + 352) = 0;
                }
                IMCLock::~IMCLock((IMCLock *)v41);
                if ( v18 )
                  goto LABEL_41;
                v17 = v44;
              }
              v24 = LOWORD(v45[0]);
              v37[0] = 0;
              if ( (Property & 0x80002) == 0x80002 )
              {
                pwszBuff = 0;
                v37[0] = ToUnicode(LOWORD(v45[0]), (unsigned __int16)v16, KeyState, &pwszBuff, 1, 0);
                if ( v37[0] == 1 )
                  v24 = (unsigned __int8)v24 | (pwszBuff << 16);
              }
              v25 = (struct tagTRANSMSGLIST *)LocalAlloc(0x40u, 0x1808u);
              v26 = v25;
              if ( !v25 )
              {
LABEL_38:
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
                return 1;
              }
              v25->uMsgCount = 256;
              v27 = CicBridge::ToAsciiEx(
                      v17,
                      (struct TLS *)Value,
                      v5,
                      v24,
                      (unsigned __int16)v16,
                      wFlags,
                      v25,
                      v34,
                      v13,
                      v37);
              v28 = v37[0];
              v18 = v27;
              if ( v37[0] > 0x100 )
              {
                IMCLock::IMCLock((IMCLock *)v41, v13);
                if ( v42 && v43 >= 0 )
                {
                  InternalIMCCLock::InternalIMCCLock((InternalIMCCLock *)v46, *(HIMCC *)(v42 + 328));
                  v21 = v46[1];
                  v46[0] = (struct tagTRANSMSG *)&IMCCLock<tagCANDIDATEINFO>::`vftable';
                  if ( v46[1] && v48 >= 0 )
                  {
                    v29 = GetFocus();
                    CicBridge::PostTransMsg(v30, v29, v28, v21);
                    InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)v46);
                    goto LABEL_49;
                  }
                  LocalFree(v26);
                  InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)v46);
                  goto LABEL_37;
                }
              }
              else
              {
                if ( (int)v37[0] <= 0 )
                  goto LABEL_50;
                IMCLock::IMCLock((IMCLock *)v41, v13);
                if ( v42 && v43 >= 0 )
                {
                  v22 = GetFocus();
                  CicBridge::PostTransMsg(v23, v22, v28, v26->TransMsg);
LABEL_49:
                  IMCLock::~IMCLock((IMCLock *)v41);
LABEL_50:
                  LocalFree(v26);
                  goto LABEL_41;
                }
              }
              LocalFree(v26);
LABEL_37:
              IMCLock::~IMCLock((IMCLock *)v41);
              goto LABEL_38;
            }
          }
        }
      }
      goto LABEL_16;
    }
  }
LABEL_18:
  (*(void (__fastcall **)(struct ITfThreadMgr_P *))(*(_QWORD *)v5 + 16LL))(v5);
  return 1;
}

```

## disassembly

```asm
0x1800447a0  push    rbp
0x1800447a2  push    rsi
0x1800447a3  push    r13
0x1800447a5  lea     rbp, [rsp-110h]
0x1800447ad  sub     rsp, 210h
0x1800447b4  mov     rax, cs:__security_cookie
0x1800447bb  xor     rax, rsp
0x1800447be  mov     [rbp+120h+var_40], rax
0x1800447c5  mov     [rbp+120h+var_180], rcx
0x1800447c9  mov     r13, r8
0x1800447cc  mov     ecx, cs:?dwTLSIndex@TLS@@0KA; dwTlsIndex
0x1800447d2  mov     [rbp+120h+lParam], r8
0x1800447d6  mov     qword ptr [rbp+120h+var_178], rdx
0x1800447da  cmp     ecx, 0FFFFFFFFh
0x1800447dd  jz      loc_180044C5E
0x1800447e3  call    cs:__imp_TlsGetValue
0x1800447e9  mov     rsi, rax
0x1800447ec  test    rax, rax
0x1800447ef  jz      loc_180044AC7
0x1800447f5  mov     [rsp+220h+arg_18], rbx
0x1800447fd  mov     rbx, [rsi+10h]
0x180044801  mov     [rsp+220h+var_1B0], rbx
0x180044806  test    rbx, rbx
0x180044809  jz      loc_180044DF8
0x18004480f  mov     rax, [rbx]
0x180044812  mov     rcx, rbx
0x180044815  mov     [rsp+220h+var_28], r14
0x18004481d  mov     rax, [rax+8]
0x180044821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044826  xor     r14d, r14d
0x180044829  lea     rdx, [rsp+220h+var_1A8]
0x18004482e  mov     [rsp+220h+var_1A8], r14d
0x180044833  mov     rcx, rbx
0x180044836  mov     rax, [rbx]
0x180044839  mov     rax, [rax+88h]
0x180044840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044845  test    eax, eax
0x180044847  js      loc_180044C79
0x18004484d  cmp     [rsp+220h+var_1A8], r14d
0x180044852  jz      loc_1800449B3
0x180044858  mov     [rsp+220h+var_18], rdi
0x180044860  mov     [rsp+220h+var_30], r15
0x180044868  call    cs:__imp_GetFocus
0x18004486e  mov     r15, rax
0x180044871  test    rax, rax
0x180044874  jz      loc_180044964
0x18004487a  mov     [rsp+220h+var_1C8], r14
0x18004487f  lea     rdx, [rsp+220h+var_1C8]
0x180044884  mov     rcx, [rbx]
0x180044887  mov     rax, [rcx+38h]
0x18004488b  mov     rcx, rbx
0x18004488e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044893  mov     rcx, [rsp+220h+var_1C8]
0x180044898  test    rcx, rcx
0x18004489b  jz      loc_180044964
0x1800448a1  xor     eax, eax
0x1800448a3  mov     qword ptr [rsp+220h+var_1B8], r14
0x1800448a8  mov     [rbp+120h+var_160], rax
0x1800448ac  lea     r8, [rsp+220h+var_1B8]
0x1800448b1  mov     rax, [rcx]
0x1800448b4  lea     rdx, IID_ITfCompartmentMgr
0x1800448bb  xorps   xmm0, xmm0
0x1800448be  mov     qword ptr [rsp+220h+var_1C0], r14
0x1800448c3  movups  xmmword ptr [rbp+120h+var_170], xmm0
0x1800448c7  mov     rax, [rax]
0x1800448ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448cf  mov     edi, eax
0x1800448d1  test    eax, eax
0x1800448d3  js      short loc_18004490A
0x1800448d5  mov     rcx, qword ptr [rsp+220h+var_1B8]
0x1800448da  test    rcx, rcx
0x1800448dd  jz      short loc_18004494E
0x1800448df  mov     rax, [rcx]
0x1800448e2  lea     r8, [rsp+220h+var_1C0]
0x1800448e7  lea     rdx, ?GUID_COMPARTMENT_CTFIME_DIMFLAGS@@3U_GUID@@B; _GUID const GUID_COMPARTMENT_CTFIME_DIMFLAGS
0x1800448ee  mov     rax, [rax+18h]
0x1800448f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448f7  mov     rcx, qword ptr [rsp+220h+var_1B8]
0x1800448fc  mov     edi, eax
0x1800448fe  mov     rax, [rcx]
0x180044901  mov     rax, [rax+10h]
0x180044905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004490a  test    edi, edi
0x18004490c  js      short loc_18004494E
0x18004490e  mov     rcx, qword ptr [rsp+220h+var_1C0]
0x180044913  lea     rdx, [rbp+120h+var_170]
0x180044917  mov     edi, r14d
0x18004491a  mov     rax, [rcx]
0x18004491d  mov     rax, [rax+20h]
0x180044921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044926  mov     r14d, eax
0x180044929  test    eax, eax
0x18004492b  jnz     short loc_180044930
0x18004492d  mov     edi, dword ptr [rbp+120h+var_170+8]
0x180044930  mov     rdx, qword ptr [rsp+220h+var_1C0]
0x180044935  mov     rcx, [rdx]
0x180044938  mov     rax, [rcx+10h]
0x18004493c  mov     rcx, rdx
0x18004493f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044944  test    r14d, r14d
0x180044947  js      short loc_18004494E
0x180044949  and     edi, 1
0x18004494c  jnz     short loc_1800449C9
0x18004494e  mov     rcx, [rsp+220h+var_1C8]
0x180044953  test    rcx, rcx
0x180044956  jz      short loc_180044964
0x180044958  mov     rax, [rcx]
0x18004495b  mov     rax, [rax+10h]
0x18004495f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044964  mov     rax, [rbx]
0x180044967  mov     rcx, rbx
0x18004496a  mov     rax, [rax+10h]
0x18004496e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044973  mov     eax, 1
0x180044978  mov     rdi, [rsp+220h+var_18]
0x180044980  mov     r15, [rsp+220h+var_30]
0x180044988  mov     r14, [rsp+220h+var_28]
0x180044990  mov     rbx, [rsp+220h+arg_18]
0x180044998  mov     rcx, [rbp+120h+var_40]
0x18004499f  xor     rcx, rsp; StackCookie
0x1800449a2  call    __security_check_cookie
0x1800449a7  add     rsp, 210h
0x1800449ae  pop     r13
0x1800449b0  pop     rsi
0x1800449b1  pop     rbp
0x1800449b2  retn
0x1800449b3  mov     rax, [rbx]
0x1800449b6  mov     rcx, rbx
0x1800449b9  mov     rax, [rax+10h]
0x1800449bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800449c2  mov     eax, 1
0x1800449c7  jmp     short loc_180044988
0x1800449c9  xor     ecx, ecx
0x1800449cb  call    cs:__imp_ImmGetAppCompatFlags
0x1800449d1  test    eax, 0D000000h
0x1800449d6  jz      loc_18004494E
0x1800449dc  mov     rcx, r15; HWND
0x1800449df  call    cs:__imp_ImmGetContext
0x1800449e5  mov     rdi, rax
0x1800449e8  test    rax, rax
0x1800449eb  jz      loc_18004494E
0x1800449f1  mov     rcx, rax
0x1800449f4  call    MsimtfIsGuidMapEnable
0x1800449f9  test    eax, eax
0x1800449fb  jz      loc_18004494E
0x180044a01  lea     rcx, [rbp+120h+KeyState]; lpKeyState
0x180044a05  mov     [rsp+220h+var_20], r12
0x180044a0d  call    cs:__imp_GetKeyboardState
0x180044a13  test    eax, eax
0x180044a15  jz      loc_180044B34
0x180044a1b  xor     ecx, ecx; idThread
0x180044a1d  call    cs:__imp_GetKeyboardLayout
0x180044a23  mov     rcx, rax; HKL
0x180044a26  mov     edx, 4; DWORD
0x180044a2b  call    cs:__imp_ImmGetProperty
0x180044a31  mov     r12, r13
0x180044a34  mov     r14d, eax
0x180044a37  shr     r12, 10h
0x180044a3b  bt      r12w, 0Ch
0x180044a41  jb      loc_180044B34
0x180044a47  mov     eax, 8000h
0x180044a4c  movzx   ecx, r12w
0x180044a50  and     cx, ax
0x180044a53  mov     word ptr [rsp+220h+var_1C0], cx
0x180044a58  jz      short loc_180044A64
0x180044a5a  test    r14b, 4
0x180044a5e  jnz     loc_180044B34
0x180044a64  mov     eax, 0Dh
0x180044a69  bt      r12w, ax
0x180044a6e  setb    cl
0x180044a71  test    r14b, 8
0x180044a75  setz    al
0x180044a78  test    al, cl
0x180044a7a  jnz     loc_180044B34
0x180044a80  lea     rax, [rsp+220h+var_1B8]
0x180044a85  mov     [rsp+220h+var_1B8], 0
0x180044a8d  mov     [rsp+220h+var_1E8], rax; unsigned int
0x180044a92  mov     r9, rdi; HIMC
0x180044a95  mov     rax, qword ptr [rbp+120h+var_178]
0x180044a99  mov     r8, rbx; struct ITfThreadMgr_P *
0x180044a9c  mov     qword ptr [rsp+220h+wFlags], r13; __int64
0x180044aa1  mov     rdx, rsi; struct TLS *
0x180044aa4  mov     r13, [rbp+120h+var_180]
0x180044aa8  mov     rcx, r13; this
0x180044aab  mov     [rsp+220h+cchBuff], eax; unsigned int
0x180044aaf  call    ?ProcessKey@CicBridge@@QEAAHPEAVTLS@@PEAUITfThreadMgr_P@@PEAUHIMC__@@I_JQEAEPEAH@Z; CicBridge::ProcessKey(TLS *,ITfThreadMgr_P *,HIMC__ *,uint,__int64,uchar * const,int *)
0x180044ab4  test    eax, eax
0x180044ab6  jnz     loc_180044C9E
0x180044abc  mov     r15d, 1
0x180044ac2  jmp     loc_180044B82
0x180044ac7  call    cs:__imp_RtlDllShutdownInProgress
0x180044acd  test    al, al
0x180044acf  jnz     loc_180044C5E
0x180044ad5  call    ?_IsFlsCallbackNotCalled@@YAHXZ; _IsFlsCallbackNotCalled(void)
0x180044ada  test    eax, eax
0x180044adc  jz      loc_180044C5E
0x180044ae2  mov     edx, 38h ; '8'; uBytes
0x180044ae7  mov     ecx, 40h ; '@'; uFlags
0x180044aec  call    cs:__imp_LocalAlloc
0x180044af2  mov     rsi, rax
0x180044af5  test    rax, rax
0x180044af8  jz      loc_180044C5E
0x180044afe  mov     ecx, cs:?dwTLSIndex@TLS@@0KA; dwTlsIndex
0x180044b04  mov     rdx, rax; lpTlsValue
0x180044b07  call    cs:__imp_TlsSetValue
0x180044b0d  test    eax, eax
0x180044b0f  jz      loc_180044C55
0x180044b15  or      dword ptr [rsi+18h], 1
0x180044b19  or      dword ptr [rsi+20h], 1
0x180044b1d  jmp     loc_1800447F5
0x180044b22  mov     rcx, r14; hMem
0x180044b25  call    cs:__imp_LocalFree
0x180044b2b  lea     rcx, [rbp+120h+var_1A0]; this
0x180044b2f  call    ??1IMCLock@@UEAA@XZ; IMCLock::~IMCLock(void)
0x180044b34  lea     rcx, [rsp+220h+var_1C8]
0x180044b39  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180044b3e  lea     rcx, [rsp+220h+var_1B0]
0x180044b43  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180044b48  mov     r12, [rsp+220h+var_20]
0x180044b50  mov     eax, 1
0x180044b55  jmp     loc_180044978
0x180044b5a  mov     rdx, rdi; HIMC
0x180044b5d  lea     rcx, [rbp+120h+var_1A0]; this
0x180044b61  call    ??0IMCLock@@QEAA@PEAUHIMC__@@@Z; IMCLock::IMCLock(HIMC__ *)
0x180044b66  mov     r13, [rbp+120h+var_198]
0x180044b6a  test    r13, r13
0x180044b6d  jnz     loc_180044CAA
0x180044b73  lea     rcx, [rbp+120h+var_1A0]; this
0x180044b77  mov     r15d, 80004005h
0x180044b7d  call    ??1IMCLock@@UEAA@XZ; IMCLock::~IMCLock(void)
0x180044b82  lea     rcx, [rsp+220h+var_1C8]
0x180044b87  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180044b8c  lea     rcx, [rsp+220h+var_1B0]
0x180044b91  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180044b96  mov     r12, [rsp+220h+var_20]
0x180044b9e  mov     eax, r15d
0x180044ba1  jmp     loc_180044978
0x180044ba6  mov     rdx, rdi; HIMC
0x180044ba9  lea     rcx, [rbp+120h+var_1A0]; this
0x180044bad  call    ??0IMCLock@@QEAA@PEAUHIMC__@@@Z; IMCLock::IMCLock(HIMC__ *)
0x180044bb2  mov     rdx, [rbp+120h+var_198]
0x180044bb6  test    rdx, rdx
0x180044bb9  jz      loc_180044B22
0x180044bbf  cmp     [rbp+120h+var_188], 0
0x180044bc3  jl      loc_180044B22
0x180044bc9  mov     rdx, [rdx+148h]; HIMCC
0x180044bd0  lea     rcx, [rbp+120h+var_170]; this
0x180044bd4  call    ??0InternalIMCCLock@@QEAA@PEAUHIMCC__@@@Z; InternalIMCCLock::InternalIMCCLock(HIMCC__ *)
0x180044bd9  mov     rdi, [rbp+120h+var_170+8]
0x180044bdd  lea     rax, ??_7?$IMCCLock@UtagCANDIDATEINFO@@@@6B@; const IMCCLock<tagCANDIDATEINFO>::`vftable'
0x180044be4  mov     [rbp+120h+var_170], rax
0x180044be8  test    rdi, rdi
0x180044beb  jnz     loc_180044DCC
0x180044bf1  mov     rcx, r14; hMem
0x180044bf4  call    cs:__imp_LocalFree
0x180044bfa  lea     rcx, [rbp+120h+var_170]; this
0x180044bfe  call    ??1InternalIMCCLock@@UEAA@XZ; InternalIMCCLock::~InternalIMCCLock(void)
0x180044c03  jmp     loc_180044B2B
0x180044c08  mov     rdx, rdi; HIMC
0x180044c0b  lea     rcx, [rbp+120h+var_1A0]; this
0x180044c0f  call    ??0IMCLock@@QEAA@PEAUHIMC__@@@Z; IMCLock::IMCLock(HIMC__ *)
0x180044c14  cmp     [rbp+120h+var_198], 0
0x180044c19  jz      loc_180044B22
0x180044c1f  cmp     [rbp+120h+var_188], 0
0x180044c23  jl      loc_180044B22
0x180044c29  call    cs:__imp_GetFocus
0x180044c2f  lea     r9, [r14+8]; struct tagTRANSMSG *
0x180044c33  mov     r8d, ebx; int
0x180044c36  mov     rdx, rax; HWND
0x180044c39  call    ?PostTransMsg@CicBridge@@AEAAXPEAUHWND__@@HPEAUtagTRANSMSG@@@Z; CicBridge::PostTransMsg(HWND__ *,int,tagTRANSMSG *)
0x180044c3e  lea     rcx, [rbp+120h+var_1A0]; this
0x180044c42  call    ??1IMCLock@@UEAA@XZ; IMCLock::~IMCLock(void)
0x180044c47  mov     rcx, r14; hMem
0x180044c4a  call    cs:__imp_LocalFree
0x180044c50  jmp     loc_180044B82
0x180044c55  mov     rcx, rsi; hMem
0x180044c58  call    cs:__imp_LocalFree
0x180044c5e  lea     rdx, aCicbridgeOnsys; "CicBridge::OnSysKeyboardProc. ptls==NUL"...
0x180044c65  mov     ecx, 2; unsigned int
0x180044c6a  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180044c6f  mov     eax, 1
0x180044c74  jmp     loc_180044998
0x180044c79  lea     rdx, aCicbridgeOnsys_0; "CicBridge::OnSysKeyboardProc. IsKeystro"...
0x180044c80  mov     ecx, 2; unsigned int
0x180044c85  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180044c8a  lea     rcx, [rsp+220h+var_1B0]
0x180044c8f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180044c94  mov     eax, 1
0x180044c99  jmp     loc_180044988
0x180044c9e  cmp     [rsp+220h+var_1B8], 0
0x180044ca3  jz      short loc_180044CFB
0x180044ca5  jmp     loc_180044B5A
0x180044caa  mov     r15d, [rbp+120h+var_188]
0x180044cae  test    r15d, r15d
0x180044cb1  js      short loc_180044CE2
0x180044cb3  mov     r9, [rbp+120h+lParam]; lParam
0x180044cb7  xor     edx, edx
0x180044cb9  cmp     word ptr [rsp+220h+var_1C0], dx
0x180044cbe  mov     r8d, 0E5h; wParam
0x180044cc4  mov     rcx, [r13+0]; hWnd
  ... truncated ...
```
