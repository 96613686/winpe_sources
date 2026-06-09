# CThreadInputMgr::Deactivate(void)

- ea: `0x18000c720`
- end: `0x18000cb35`
- name: `?Deactivate@CThreadInputMgr@@UEAAJXZ`
- size: `1045`
- prototype: `__int64 __fastcall(CThreadInputMgr *__hidden this)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800751e0`
- `0x1800aa9a0`
- `0x1800aa9b0`

## callees

- `0x1800071e0`
- `0x18000b5e4`
- `0x18000b750`
- `0x18000ba24`
- `0x18000c720`
- `0x18000cb3c`
- `0x18008ced0`
- `0x1800926fc`
- `0x1800a18d4`
- `0x1800b8adc`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c856`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c856`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c869`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c869`
- `USER32!KillTimer` at `0x18000c88f`
- `USER32!KillTimer` at `0x18000c8aa`
- `USER32!KillTimer` at `0x18000c8c5`
- `USER32!KillTimer` at `0x18000c8e0`
- `USER32!KillTimer` at `0x18000c8fb`
- `USER32!KillTimer` at `0x18000c916`
- `USER32!KillTimer` at `0x18000c931`
- `USER32!KillTimer` at `0x18000c94c`
- `USER32!KillTimer` at `0x18000c88f`
- `USER32!KillTimer` at `0x18000c8aa`
- `USER32!KillTimer` at `0x18000c8c5`
- `USER32!KillTimer` at `0x18000c8e0`
- `USER32!KillTimer` at `0x18000c8fb`
- `USER32!KillTimer` at `0x18000c916`
- `USER32!KillTimer` at `0x18000c931`
- `USER32!KillTimer` at `0x18000c94c`
- `IMM32!CtfImmSetCiceroStartInThread` at `0x18000c7aa`
- `IMM32!CtfImmSetCiceroStartInThread` at `0x18000c7aa`

## pseudocode

```c
__int64 __fastcall CThreadInputMgr::Deactivate(CThreadInputMgr *this)
{
  int v2; // eax
  int *v3; // r15
  int v4; // eax
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rcx
  CInputProfileManager *v8; // rbx
  char v9; // al
  char v10; // dl
  int v11; // r14d
  DWORD CurrentThreadId; // ebx
  __int64 v13; // r8
  LPVOID Value; // rax
  __int64 v15; // r9
  CLangBarMgr *v16; // rcx
  UINT_PTR v17; // rdx
  UINT_PTR v18; // rdx
  UINT_PTR v19; // rdx
  UINT_PTR v20; // rdx
  UINT_PTR v21; // rdx
  UINT_PTR v22; // rdx
  UINT_PTR v23; // rdx
  UINT_PTR v24; // rdx
  __int64 v25; // rax
  int (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // rdi
  int (__fastcall *v27)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v28; // rbx
  int (__fastcall *v29)(__int64, GUID *, _QWORD *); // rdi
  __int64 v31; // [rsp+30h] [rbp-88h] BYREF
  int v32; // [rsp+38h] [rbp-80h]
  char *v33; // [rsp+40h] [rbp-78h]
  __int128 v34; // [rsp+48h] [rbp-70h] BYREF
  __int64 v35; // [rsp+58h] [rbp-60h]
  _QWORD v36[2]; // [rsp+60h] [rbp-58h] BYREF

  v2 = *((_DWORD *)this + 910);
  if ( v2 )
  {
    *((_DWORD *)this + 910) = v2 - 1;
    v3 = (int *)((char *)this + 3668);
    v4 = *((_DWORD *)this + 917);
    if ( (v4 & 8) != 0 )
      return 0;
    v33 = (char *)this + 3668;
    if ( (v4 & 4) == 0 && (v4 & 0x80u) == 0 )
    {
      *v3 = v4 | 8;
      CThreadInputMgr::OnActivationChange(this);
      if ( !*((_DWORD *)this + 910) )
      {
        if ( (Microsoft_Windows_TSF_msctfEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(
            &Microsoft_Windows_TSF_msctf_Context,
            DeactivateCiceroForThread_Start,
            v5,
            1,
            v36);
        CtfImmSetCiceroStartInThread(0);
        *(_DWORD *)(*((_QWORD *)this + 26) + 192LL) &= ~0x20u;
        CThreadInputMgr::UninitDefaultHotkeys(this);
        v6 = *((_QWORD *)this + 368);
        if ( v6 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
          *((_QWORD *)this + 368) = 0;
        }
        v7 = *((_QWORD *)this + 369);
        if ( v7 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          *((_QWORD *)this + 369) = 0;
        }
        v8 = (CInputProfileManager *)*((_QWORD *)this + 390);
        if ( v8 )
        {
          if ( !*((_QWORD *)v8 + 11)
            || (v9 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 8LL))(*((_QWORD *)this + 390)), v10 = 1, !v9) )
          {
            v10 = 0;
          }
          CInputProfileManager::UpdateLocalEventHook(v8, v10, 0);
          *((_QWORD *)v8 + 10) = 0;
          CInputProfileManager::Release(*((CInputProfileManager **)this + 390));
          *((_QWORD *)this + 390) = 0;
        }
        v11 = *((_DWORD *)this + 58);
        while ( 1 )
        {
          v32 = --v11;
          if ( v11 < 0 )
            break;
          v25 = *((_QWORD *)this + 28);
          v26 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))(v25 + 8LL * v11);
          if ( v26 && ((__int64 (__fastcall *)(_QWORD))(*v26)[11])(*(_QWORD *)(v25 + 8LL * v11)) )
          {
            v36[0] = 0;
            v31 = 0;
            v27 = **v26;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
            if ( v27(v26, &GUID_7dcf57ac_18ad_438b_824d_979bffb74b7c, &v31) >= 0 )
            {
              v28 = v31;
              v29 = *(int (__fastcall **)(__int64, GUID *, _QWORD *))(*(_QWORD *)v31 + 24LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v36);
              if ( v29(v28, &GUID_COMPARTMENT_TRANSITORYEXTENSION, v36) >= 0 )
              {
                v34 = 0;
                v35 = 0;
                LOWORD(v34) = 3;
                DWORD2(v34) = 0;
                (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)v36[0] + 24LL))(
                  v36[0],
                  g_gaSystem,
                  &v34);
              }
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v36);
          }
        }
        *((_DWORD *)this + 942) = 0;
        CurrentThreadId = GetCurrentThreadId();
        if ( g_dwTLSIndex != -1 )
        {
          Value = TlsGetValue(g_dwTLSIndex);
          if ( Value )
          {
            v16 = (CLangBarMgr *)*((_QWORD *)Value + 5);
            if ( v16 )
              CLangBarMgr::OnLanguageBarEvent(v16, 5, CurrentThreadId, v15);
          }
        }
        v17 = *((_QWORD *)this + 461);
        if ( v17 )
        {
          KillTimer(0, v17);
          *((_QWORD *)this + 461) = 0;
        }
        v18 = *((_QWORD *)this + 462);
        if ( v18 )
        {
          KillTimer(0, v18);
          *((_QWORD *)this + 462) = 0;
        }
        v19 = *((_QWORD *)this + 463);
        if ( v19 )
        {
          KillTimer(0, v19);
          *((_QWORD *)this + 463) = 0;
        }
        v20 = *((_QWORD *)this + 464);
        if ( v20 )
        {
          KillTimer(0, v20);
          *((_QWORD *)this + 464) = 0;
        }
        v21 = *((_QWORD *)this + 465);
        if ( v21 )
        {
          KillTimer(0, v21);
          *((_QWORD *)this + 465) = 0;
        }
        v22 = *((_QWORD *)this + 466);
        if ( v22 )
        {
          KillTimer(0, v22);
          *((_QWORD *)this + 466) = 0;
        }
        v23 = *((_QWORD *)this + 467);
        if ( v23 )
        {
          KillTimer(0, v23);
          *((_QWORD *)this + 467) = 0;
        }
        v24 = *((_QWORD *)this + 468);
        if ( v24 )
        {
          KillTimer(0, v24);
          *((_QWORD *)this + 468) = 0;
        }
        if ( (*v3 & 0x100000) != 0 )
        {
          *v3 &= ~0x100000u;
          Internal_UninitLocalMsCtfMonitor();
        }
        if ( (Microsoft_Windows_TSF_msctfEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(
            &Microsoft_Windows_TSF_msctf_Context,
            DeactivateCiceroForThread_End,
            v13,
            1,
            v36);
      }
      *v3 &= ~8u;
      return 0;
    }
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18000c720  push    rbx
0x18000c722  push    rsi
0x18000c723  push    rdi
0x18000c724  push    r12
0x18000c726  push    r14
0x18000c728  push    r15
0x18000c72a  sub     rsp, 88h
0x18000c731  mov     rax, cs:__security_cookie
0x18000c738  xor     rax, rsp
0x18000c73b  mov     [rsp+0B8h+var_48], rax
0x18000c740  mov     rsi, rcx
0x18000c743  mov     eax, [rcx+0E38h]
0x18000c749  xor     r12d, r12d
0x18000c74c  test    eax, eax
0x18000c74e  jz      loc_18000CB2E
0x18000c754  dec     eax
0x18000c756  mov     [rcx+0E38h], eax
0x18000c75c  lea     r15, [rcx+0E54h]
0x18000c763  mov     eax, [r15]
0x18000c766  test    al, 8
0x18000c768  jnz     loc_18000CB0E
0x18000c76e  mov     [rsp+0B8h+var_78], r15
0x18000c773  test    al, 4
0x18000c775  jnz     loc_18000CB2E
0x18000c77b  test    al, al
0x18000c77d  js      loc_18000CB2E
0x18000c783  or      eax, 8
0x18000c786  mov     [r15], eax
0x18000c789  call    ?OnActivationChange@CThreadInputMgr@@AEAAXXZ; CThreadInputMgr::OnActivationChange(void)
0x18000c78e  cmp     [rsi+0E38h], r12d
0x18000c795  jnz     loc_18000CB03
0x18000c79b  test    cs:Microsoft_Windows_TSF_msctfEnableBits, 1
0x18000c7a2  jnz     loc_18000C9D9
0x18000c7a8  xor     ecx, ecx
0x18000c7aa  call    cs:__imp_CtfImmSetCiceroStartInThread
0x18000c7b0  mov     rax, [rsi+0D0h]
0x18000c7b7  and     dword ptr [rax+0C0h], 0FFFFFFDFh
0x18000c7be  mov     rcx, rsi; this
0x18000c7c1  call    ?UninitDefaultHotkeys@CThreadInputMgr@@AEAAJXZ; CThreadInputMgr::UninitDefaultHotkeys(void)
0x18000c7c6  mov     rcx, [rsi+0B80h]
0x18000c7cd  test    rcx, rcx
0x18000c7d0  jnz     loc_18000CA01
0x18000c7d6  mov     rcx, [rsi+0B88h]
0x18000c7dd  test    rcx, rcx
0x18000c7e0  jnz     loc_18000CA19
0x18000c7e6  mov     rbx, [rsi+0C30h]
0x18000c7ed  test    rbx, rbx
0x18000c7f0  jz      short loc_18000C837
0x18000c7f2  cmp     [rbx+58h], r12
0x18000c7f6  jz      loc_18000CA31
0x18000c7fc  mov     rax, [rbx]
0x18000c7ff  mov     rcx, rbx
0x18000c802  mov     rax, [rax+8]
0x18000c806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c80b  test    al, al
0x18000c80d  mov     dl, 1; bool
0x18000c80f  jz      loc_18000CA31
0x18000c815  xor     r8d, r8d; bool
0x18000c818  mov     rcx, rbx; this
0x18000c81b  call    ?UpdateLocalEventHook@CInputProfileManager@@QEAAX_N0@Z; CInputProfileManager::UpdateLocalEventHook(bool,bool)
0x18000c820  mov     [rbx+50h], r12
0x18000c824  mov     rcx, [rsi+0C30h]; this
0x18000c82b  call    ?Release@CInputProfileManager@@QEAAJXZ; CInputProfileManager::Release(void)
0x18000c830  mov     [rsi+0C30h], r12
0x18000c837  mov     r14d, [rsi+0E8h]
0x18000c83e  dec     r14d
0x18000c841  mov     [rsp+0B8h+var_80], r14d
0x18000c846  test    r14d, r14d
0x18000c849  jns     loc_18000C9AD
0x18000c84f  mov     [rsi+0EB8h], r12d
0x18000c856  call    cs:__imp_GetCurrentThreadId
0x18000c85c  mov     ebx, eax
0x18000c85e  mov     ecx, cs:?g_dwTLSIndex@@3KA; dwTlsIndex
0x18000c864  cmp     ecx, 0FFFFFFFFh
0x18000c867  jz      short loc_18000C881
0x18000c869  call    cs:__imp_TlsGetValue
0x18000c86f  test    rax, rax
0x18000c872  jz      short loc_18000C881
0x18000c874  mov     rcx, [rax+28h]; this
0x18000c878  test    rcx, rcx
0x18000c87b  jnz     loc_18000C99B
0x18000c881  mov     rdx, [rsi+0E68h]; uIDEvent
0x18000c888  test    rdx, rdx
0x18000c88b  jz      short loc_18000C89C
0x18000c88d  xor     ecx, ecx; hWnd
0x18000c88f  call    cs:__imp_KillTimer
0x18000c895  mov     [rsi+0E68h], r12
0x18000c89c  mov     rdx, [rsi+0E70h]; uIDEvent
0x18000c8a3  test    rdx, rdx
0x18000c8a6  jz      short loc_18000C8B7
0x18000c8a8  xor     ecx, ecx; hWnd
0x18000c8aa  call    cs:__imp_KillTimer
0x18000c8b0  mov     [rsi+0E70h], r12
0x18000c8b7  mov     rdx, [rsi+0E78h]; uIDEvent
0x18000c8be  test    rdx, rdx
0x18000c8c1  jz      short loc_18000C8D2
0x18000c8c3  xor     ecx, ecx; hWnd
0x18000c8c5  call    cs:__imp_KillTimer
0x18000c8cb  mov     [rsi+0E78h], r12
0x18000c8d2  mov     rdx, [rsi+0E80h]; uIDEvent
0x18000c8d9  test    rdx, rdx
0x18000c8dc  jz      short loc_18000C8ED
0x18000c8de  xor     ecx, ecx; hWnd
0x18000c8e0  call    cs:__imp_KillTimer
0x18000c8e6  mov     [rsi+0E80h], r12
0x18000c8ed  mov     rdx, [rsi+0E88h]; uIDEvent
0x18000c8f4  test    rdx, rdx
0x18000c8f7  jz      short loc_18000C908
0x18000c8f9  xor     ecx, ecx; hWnd
0x18000c8fb  call    cs:__imp_KillTimer
0x18000c901  mov     [rsi+0E88h], r12
0x18000c908  mov     rdx, [rsi+0E90h]; uIDEvent
0x18000c90f  test    rdx, rdx
0x18000c912  jz      short loc_18000C923
0x18000c914  xor     ecx, ecx; hWnd
0x18000c916  call    cs:__imp_KillTimer
0x18000c91c  mov     [rsi+0E90h], r12
0x18000c923  mov     rdx, [rsi+0E98h]; uIDEvent
0x18000c92a  test    rdx, rdx
0x18000c92d  jz      short loc_18000C93E
0x18000c92f  xor     ecx, ecx; hWnd
0x18000c931  call    cs:__imp_KillTimer
0x18000c937  mov     [rsi+0E98h], r12
0x18000c93e  mov     rdx, [rsi+0EA0h]; uIDEvent
0x18000c945  test    rdx, rdx
0x18000c948  jz      short loc_18000C959
0x18000c94a  xor     ecx, ecx; hWnd
0x18000c94c  call    cs:__imp_KillTimer
0x18000c952  mov     [rsi+0EA0h], r12
0x18000c959  mov     eax, [r15]
0x18000c95c  bt      eax, 14h
0x18000c960  jb      loc_18000CAF2
0x18000c966  test    cs:Microsoft_Windows_TSF_msctfEnableBits, 1
0x18000c96d  jz      loc_18000CB03
0x18000c973  lea     rax, [rsp+0B8h+var_58]
0x18000c978  mov     [rsp+0B8h+var_98], rax
0x18000c97d  mov     r9d, 1
0x18000c983  lea     rdx, DeactivateCiceroForThread_End
0x18000c98a  lea     rcx, Microsoft_Windows_TSF_msctf_Context
0x18000c991  call    McGenEventWrite_EventWriteTransfer
0x18000c996  jmp     loc_18000CB03
0x18000c99b  mov     r8d, ebx; unsigned int
0x18000c99e  mov     edx, 5; int
0x18000c9a3  call    ?OnLanguageBarEvent@CLangBarMgr@@AEAAXHK_J@Z; CLangBarMgr::OnLanguageBarEvent(int,ulong,__int64)
0x18000c9a8  jmp     loc_18000C881
0x18000c9ad  movsxd  rcx, r14d
0x18000c9b0  mov     rax, [rsi+0E0h]
0x18000c9b7  mov     rdi, [rax+rcx*8]
0x18000c9bb  test    rdi, rdi
0x18000c9be  jz      short loc_18000C9D4
0x18000c9c0  mov     rax, [rdi]
0x18000c9c3  mov     rcx, rdi
0x18000c9c6  mov     rax, [rax+58h]
0x18000c9ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9cf  test    rax, rax
0x18000c9d2  jnz     short loc_18000CA39
0x18000c9d4  jmp     loc_18000C83E
0x18000c9d9  lea     rax, [rsp+0B8h+var_58]
0x18000c9de  mov     [rsp+0B8h+var_98], rax
0x18000c9e3  mov     r9d, 1
0x18000c9e9  lea     rdx, DeactivateCiceroForThread_Start
0x18000c9f0  lea     rcx, Microsoft_Windows_TSF_msctf_Context
0x18000c9f7  call    McGenEventWrite_EventWriteTransfer
0x18000c9fc  jmp     loc_18000C7A8
0x18000ca01  mov     rax, [rcx]
0x18000ca04  mov     rax, [rax+10h]
0x18000ca08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca0d  mov     [rsi+0B80h], r12
0x18000ca14  jmp     loc_18000C7D6
0x18000ca19  mov     rax, [rcx]
0x18000ca1c  mov     rax, [rax+10h]
0x18000ca20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca25  mov     [rsi+0B88h], r12
0x18000ca2c  jmp     loc_18000C7E6
0x18000ca31  mov     dl, r12b
0x18000ca34  jmp     loc_18000C815
0x18000ca39  mov     [rsp+0B8h+var_58], r12
0x18000ca3e  mov     [rsp+0B8h+var_88], r12
0x18000ca43  mov     rax, [rdi]
0x18000ca46  mov     rbx, [rax]
0x18000ca49  lea     rcx, [rsp+0B8h+var_88]
0x18000ca4e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ca53  lea     r8, [rsp+0B8h+var_88]
0x18000ca58  lea     rdx, _GUID_7dcf57ac_18ad_438b_824d_979bffb74b7c
0x18000ca5f  mov     rcx, rdi
0x18000ca62  mov     rax, rbx
0x18000ca65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca6a  test    eax, eax
0x18000ca6c  js      short loc_18000CAD9
0x18000ca6e  mov     rbx, [rsp+0B8h+var_88]
0x18000ca73  mov     rax, [rbx]
0x18000ca76  mov     rdi, [rax+18h]
0x18000ca7a  lea     rcx, [rsp+0B8h+var_58]
0x18000ca7f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ca84  lea     r8, [rsp+0B8h+var_58]
0x18000ca89  lea     rdx, GUID_COMPARTMENT_TRANSITORYEXTENSION
0x18000ca90  mov     rcx, rbx
0x18000ca93  mov     rax, rdi
0x18000ca96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca9b  test    eax, eax
0x18000ca9d  js      short loc_18000CAD9
0x18000ca9f  xorps   xmm0, xmm0
0x18000caa2  xor     eax, eax
0x18000caa4  movups  [rsp+0B8h+var_70], xmm0
0x18000caa9  mov     [rsp+0B8h+var_60], rax
0x18000caae  mov     eax, 3
0x18000cab3  mov     word ptr [rsp+0B8h+var_70], ax
0x18000cab8  mov     dword ptr [rsp+0B8h+var_70+8], r12d
0x18000cabd  mov     rcx, [rsp+0B8h+var_58]
0x18000cac2  mov     rax, [rcx]
0x18000cac5  lea     r8, [rsp+0B8h+var_70]
0x18000caca  mov     edx, cs:?g_gaSystem@@3KA; ulong g_gaSystem
0x18000cad0  mov     rax, [rax+18h]
0x18000cad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cad9  lea     rcx, [rsp+0B8h+var_88]
0x18000cade  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cae3  lea     rcx, [rsp+0B8h+var_58]
0x18000cae8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000caed  jmp     loc_18000C9D4
0x18000caf2  btr     eax, 14h
0x18000caf6  mov     [r15], eax
0x18000caf9  call    ?Internal_UninitLocalMsCtfMonitor@@YAJXZ; Internal_UninitLocalMsCtfMonitor(void)
0x18000cafe  jmp     loc_18000C966
0x18000cb03  jmp     short loc_18000CB0A
0x18000cb05  mov     r15, [rsp+0B8h+var_78]
0x18000cb0a  and     dword ptr [r15], 0FFFFFFF7h
0x18000cb0e  xor     eax, eax
0x18000cb10  mov     rcx, [rsp+0B8h+var_48]
0x18000cb15  xor     rcx, rsp; StackCookie
0x18000cb18  call    __security_check_cookie
0x18000cb1d  add     rsp, 88h
0x18000cb24  pop     r15
0x18000cb26  pop     r14
0x18000cb28  pop     r12
0x18000cb2a  pop     rdi
0x18000cb2b  pop     rsi
0x18000cb2c  pop     rbx
0x18000cb2d  retn
0x18000cb2e  mov     eax, 8000FFFFh
0x18000cb33  jmp     short loc_18000CB10
0x1801073ef  push    rbp
0x1801073f1  sub     rsp, 30h
0x1801073f5  mov     rbp, rdx
0x1801073f8  mov     dl, cs:?g_fEnableFailFast@@3_NA; bool
0x1801073fe  call    ?CicExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@_N@Z; CicExceptionFilter(_EXCEPTION_POINTERS *,bool)
0x180107403  nop
0x180107404  add     rsp, 30h
0x180107408  pop     rbp
0x180107409  retn
```
