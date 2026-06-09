# DasHostStartExport

- ea: `0x14000d1f0`
- end: `0x14000d57e`
- name: `DasHostStartExport`
- size: `910`
- prototype: `__int64 __fastcall(__int64, __int64 *, _WORD *, __int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x140009060`
- `0x14000ceec`
- `0x14000d1f0`
- `0x14001211c`
- `0x140014d74`
- `0x140018634`
- `0x14001a83c`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d4d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d4d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d4ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d4ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d30f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d30f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d4bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d4bf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000d262`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000d262`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14000d305`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14000d305`

## pseudocode

```c
__int64 __fastcall DasHostStartExport(__int64 a1, __int64 *a2, _WORD *a3, __int64 a4, __int64 a5)
{
  __int64 v5; // r14
  __int64 v9; // rdx
  int v10; // r8d
  void *v11; // rdi
  ProviderContext *v12; // rsi
  void *v13; // rcx
  signed int LastError; // eax
  __int64 v15; // rcx
  _WORD *v16; // rax
  unsigned __int64 v17; // r9
  unsigned __int64 v18; // r9
  __int64 v19; // rax
  _WORD *v20; // r15
  _WORD *v21; // rax
  __int64 v22; // rbx
  void *v23; // rax
  signed int ProviderFromAepId; // ebx
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  volatile signed __int32 *v27; // rbx
  signed __int32 v28; // eax
  bool v29; // zf
  int v30; // [rsp+28h] [rbp-38h]
  __int64 v31; // [rsp+40h] [rbp-20h] BYREF
  ProviderContext *v32[2]; // [rsp+48h] [rbp-18h] BYREF
  void *DuplicateTokenHandle; // [rsp+A0h] [rbp+40h] BYREF
  struct IClassFactory *v34; // [rsp+A8h] [rbp+48h] BYREF

  v5 = *a2;
  v34 = 0;
  *(_OWORD *)v32 = 0;
  v31 = 0;
  DuplicateTokenHandle = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      (int)a3,
      14,
      &WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids);
  EventActivityIdControl(2u, (LPGUID)v5);
  *(_QWORD *)(v5 + 16) = a1;
  if ( !a3 )
    goto LABEL_4;
  v16 = a3;
  v9 = 768;
  do
  {
    if ( !*v16 )
      break;
    ++v16;
    --v9;
  }
  while ( v9 );
  v10 = v9 == 0 ? 0x80070057 : 0;
  v17 = (768 - v9) & -(__int64)(v9 != 0);
  if ( !v9 || v17 < 3 || (v18 = v17 - 1, v19 = 1, v18 <= 1) )
  {
LABEL_4:
    v11 = 0;
    ProviderFromAepId = -2147024809;
    goto LABEL_35;
  }
  while ( a3[v19] != 35 )
  {
    if ( ++v19 >= v18 )
      goto LABEL_4;
  }
  v20 = &a3[v19 + 1];
  if ( !v20 )
  {
    ProviderFromAepId = -2147024809;
LABEL_34:
    v11 = 0;
    goto LABEL_35;
  }
  v10 = 512;
  v21 = &a3[v19 + 1];
  v9 = 512;
  do
  {
    if ( !*v21 )
      break;
    ++v21;
    --v9;
  }
  while ( v9 );
  ProviderFromAepId = v9 == 0 ? 0x80070057 : 0;
  if ( !v9 )
    goto LABEL_34;
  v22 = -(__int64)(v9 != 0) & (2 * (512 - v9));
  v23 = DAF_user_alloc(v22 + 2);
  v11 = v23;
  if ( v23 )
  {
    memcpy_0(v23, v20, v22 + 2);
    ProviderFromAepId = DAS::ProviderManagement::ProviderManager::GetProviderFromAepId(g_providerManager, a3, v32);
    if ( ProviderFromAepId >= 0 )
    {
      v12 = v32[0];
      ProviderFromAepId = ProviderContext::GetClassFactory((RTL_SRWLOCK *)v32[0], &v34);
      if ( ProviderFromAepId >= 0 )
      {
        ProviderFromAepId = ((__int64 (__fastcall *)(struct IClassFactory *, _QWORD, GUID *, __int64))v34->lpVtbl->CreateInstance)(
                              v34,
                              0,
                              &IID_IAepImportExport,
                              v5 + 24);
        if ( ProviderFromAepId >= 0 )
        {
          ((void (__fastcall *)(struct IClassFactory *))v34->lpVtbl->Release)(v34);
          v13 = *(void **)(v5 + 88);
          if ( !v13 || DuplicateToken(v13, SecurityImpersonation, &DuplicateTokenHandle) )
            goto LABEL_13;
          LastError = GetLastError();
          ProviderFromAepId = LastError;
          if ( LastError > 0 )
            ProviderFromAepId = (unsigned __int16)LastError | 0x80070000;
          if ( ProviderFromAepId >= 0 )
          {
LABEL_13:
            ProviderFromAepId = CImportExportCallback::Create(
                                  *(const unsigned __int16 **)v12,
                                  (void *)v5,
                                  *((_DWORD *)v12 + 19),
                                  DuplicateTokenHandle,
                                  (struct CImportExportCallback **)(v5 + 32));
            if ( ProviderFromAepId >= 0 )
            {
              DuplicateTokenHandle = 0;
              ProviderFromAepId = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v5 + 32))(
                                    *(_QWORD *)(v5 + 32),
                                    &GUID_0c512544_e485_46b6_b339_7a301e1e412d,
                                    &v31);
              if ( ProviderFromAepId >= 0 )
              {
                v15 = *(_QWORD *)(v5 + 24);
                *(_QWORD *)(v5 + 104) = a5;
                *(_QWORD *)(v5 + 96) = a4;
                ProviderFromAepId = (*(__int64 (__fastcall **)(__int64, void *, __int64))(*(_QWORD *)v15 + 32LL))(
                                      v15,
                                      v11,
                                      v31);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
              }
            }
          }
        }
      }
    }
  }
  else
  {
    ProviderFromAepId = -2147024882;
  }
LABEL_35:
  if ( DuplicateTokenHandle )
    CloseHandle(DuplicateTokenHandle);
  if ( v11 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v11);
  }
  if ( ProviderFromAepId < 0 )
    OnAepImportCompleteStub(0, 0, ProviderFromAepId, (void *)v5);
  result = (__int64)&WPP_RECORDER_INITIALIZED;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    result = WPP_RECORDER_SF_sd(
               *((_QWORD *)WPP_GLOBAL_Control + 5),
               v9,
               v10,
               15,
               &WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids,
               v30,
               ProviderFromAepId);
  v27 = (volatile signed __int32 *)v32[1];
  if ( v32[1] )
  {
    v28 = _InterlockedExchangeAdd((volatile signed __int32 *)v32[1] + 2, 0xFFFFFFFF);
    v29 = v28 == 1;
    result = (unsigned int)(v28 - 1);
    if ( v29 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
      result = (unsigned int)_InterlockedDecrement(v27 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d1f0  mov     [rsp-38h+arg_10], rbx
0x14000d1f5  push    rbp
0x14000d1f6  push    rsi
0x14000d1f7  push    rdi
0x14000d1f8  push    r12
0x14000d1fa  push    r13
0x14000d1fc  push    r14
0x14000d1fe  push    r15
0x14000d200  mov     rbp, rsp
0x14000d203  sub     rsp, 60h
0x14000d207  mov     r14, [rdx]
0x14000d20a  xor     r15d, r15d
0x14000d20d  xorps   xmm0, xmm0
0x14000d210  mov     [rbp+arg_8], r15
0x14000d214  movdqu  xmmword ptr [rbp+var_18], xmm0
0x14000d219  mov     [rbp+var_20], r15
0x14000d21d  mov     r13, r9
0x14000d220  mov     [rbp+DuplicateTokenHandle], r15
0x14000d224  mov     rsi, r8
0x14000d227  mov     rbx, rcx
0x14000d22a  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000d231  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000d238  lea     rax, WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids
0x14000d23f  jz      short loc_14000D25A
0x14000d241  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d248  lea     r9d, [r15+0Eh]; int
0x14000d24c  mov     [rsp+60h+MessageGuid], rax; MessageGuid
0x14000d251  mov     rcx, [rcx+28h]; int
0x14000d255  call    WPP_RECORDER_SF_s
0x14000d25a  mov     rdx, r14; ActivityId
0x14000d25d  mov     ecx, 2; ControlCode
0x14000d262  call    cs:__imp_EventActivityIdControl
0x14000d268  mov     [r14+10h], rbx
0x14000d26c  test    rsi, rsi
0x14000d26f  jnz     loc_14000D3B7
0x14000d275  mov     ecx, 80070057h
0x14000d27a  mov     rdi, r15
0x14000d27d  test    ecx, ecx
0x14000d27f  js      loc_14000D4B4
0x14000d285  mov     rcx, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x14000d28c  lea     r8, [rbp+var_18]
0x14000d290  mov     rdx, rsi
0x14000d293  call    ?GetProviderFromAepId@ProviderManager@ProviderManagement@DAS@@QEAAJPEBGAEAV?$shared_ptr@VProviderContext@@@std@@@Z; DAS::ProviderManagement::ProviderManager::GetProviderFromAepId(ushort const *,std::shared_ptr<ProviderContext> &)
0x14000d298  mov     ebx, eax
0x14000d29a  test    eax, eax
0x14000d29c  js      loc_14000D4B6
0x14000d2a2  mov     rsi, [rbp+var_18]
0x14000d2a6  lea     rdx, [rbp+arg_8]; struct IClassFactory **
0x14000d2aa  mov     rcx, rsi; this
0x14000d2ad  call    ?GetClassFactory@ProviderContext@@QEAAJPEAPEAUIClassFactory@@@Z; ProviderContext::GetClassFactory(IClassFactory * *)
0x14000d2b2  mov     ebx, eax
0x14000d2b4  test    eax, eax
0x14000d2b6  js      loc_14000D4B6
0x14000d2bc  mov     rcx, [rbp+arg_8]
0x14000d2c0  lea     r9, [r14+18h]
0x14000d2c4  lea     r8, IID_IAepImportExport
0x14000d2cb  xor     edx, edx
0x14000d2cd  mov     rax, [rcx]
0x14000d2d0  mov     rax, [rax+18h]
0x14000d2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d2d9  mov     ebx, eax
0x14000d2db  test    eax, eax
0x14000d2dd  js      loc_14000D4B6
0x14000d2e3  mov     rcx, [rbp+arg_8]
0x14000d2e7  mov     rax, [rcx]
0x14000d2ea  mov     rax, [rax+10h]
0x14000d2ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d2f3  mov     rcx, [r14+58h]; ExistingTokenHandle
0x14000d2f7  test    rcx, rcx
0x14000d2fa  jz      short loc_14000D32C
0x14000d2fc  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x14000d300  mov     edx, 2; ImpersonationLevel
0x14000d305  call    cs:__imp_DuplicateToken
0x14000d30b  test    eax, eax
0x14000d30d  jnz     short loc_14000D32C
0x14000d30f  call    cs:__imp_GetLastError
0x14000d315  mov     ebx, eax
0x14000d317  test    eax, eax
0x14000d319  jle     short loc_14000D324
0x14000d31b  movzx   ebx, ax
0x14000d31e  or      ebx, 80070000h
0x14000d324  test    ebx, ebx
0x14000d326  js      loc_14000D4B6
0x14000d32c  mov     r9, [rbp+DuplicateTokenHandle]; void *
0x14000d330  lea     r15, [r14+20h]
0x14000d334  mov     r8d, [rsi+4Ch]; int
0x14000d338  mov     rdx, r14; void *
0x14000d33b  mov     rcx, [rsi]; Src
0x14000d33e  mov     [rsp+60h+MessageGuid], r15; struct CImportExportCallback **
0x14000d343  call    ?Create@CImportExportCallback@@SAJPEBGPEAXH1PEAPEAV1@@Z; CImportExportCallback::Create(ushort const *,void *,int,void *,CImportExportCallback * *)
0x14000d348  mov     ebx, eax
0x14000d34a  test    eax, eax
0x14000d34c  js      loc_14000D4B6
0x14000d352  mov     [rbp+DuplicateTokenHandle], 0
0x14000d35a  lea     r8, [rbp+var_20]
0x14000d35e  mov     rcx, [r15]
0x14000d361  lea     rdx, _GUID_0c512544_e485_46b6_b339_7a301e1e412d
0x14000d368  mov     rax, [rcx]
0x14000d36b  mov     rax, [rax]
0x14000d36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d373  mov     ebx, eax
0x14000d375  test    eax, eax
0x14000d377  js      loc_14000D4B6
0x14000d37d  mov     rcx, [r14+18h]
0x14000d381  mov     rdx, rdi
0x14000d384  mov     rax, [rbp+arg_20]
0x14000d388  mov     [r14+68h], rax
0x14000d38c  mov     [r14+60h], r13
0x14000d390  mov     rax, [rcx]
0x14000d393  mov     r8, [rbp+var_20]
0x14000d397  mov     rax, [rax+20h]
0x14000d39b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d3a0  mov     rcx, [rbp+var_20]
0x14000d3a4  mov     ebx, eax
0x14000d3a6  mov     rax, [rcx]
0x14000d3a9  mov     rax, [rax+10h]
0x14000d3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d3b2  jmp     loc_14000D4B6
0x14000d3b7  mov     r10d, 300h
0x14000d3bd  mov     rax, rsi
0x14000d3c0  mov     edx, r10d
0x14000d3c3  mov     r11d, 1
0x14000d3c9  cmp     [rax], r15w
0x14000d3cd  jz      short loc_14000D3D8
0x14000d3cf  add     rax, 2
0x14000d3d3  sub     rdx, r11
0x14000d3d6  jnz     short loc_14000D3C9
0x14000d3d8  mov     rax, rdx
0x14000d3db  mov     ecx, 80070057h
0x14000d3e0  neg     rax
0x14000d3e3  mov     rax, rdx
0x14000d3e6  sbb     r8d, r8d
0x14000d3e9  sub     r10, rdx
0x14000d3ec  not     r8d
0x14000d3ef  and     r8d, ecx
0x14000d3f2  neg     rax
0x14000d3f5  sbb     r9, r9
0x14000d3f8  and     r9, r10
0x14000d3fb  test    rdx, rdx
0x14000d3fe  jnz     short loc_14000D408
0x14000d400  mov     ecx, r8d
0x14000d403  jmp     loc_14000D27A
0x14000d408  cmp     r9, 3
0x14000d40c  jb      loc_14000D27A
0x14000d412  dec     r9
0x14000d415  mov     rax, r11
0x14000d418  cmp     r9, r11
0x14000d41b  jbe     loc_14000D27A
0x14000d421  cmp     word ptr [rsi+rax*2], 23h ; '#'
0x14000d426  jz      short loc_14000D435
0x14000d428  add     rax, r11
0x14000d42b  cmp     rax, r9
0x14000d42e  jb      short loc_14000D421
0x14000d430  jmp     loc_14000D27A
0x14000d435  lea     r15, [rsi+2]
0x14000d439  xor     r12d, r12d
0x14000d43c  lea     r15, [r15+rax*2]
0x14000d440  test    r15, r15
0x14000d443  jz      short loc_14000D4AD
0x14000d445  mov     r8d, 200h
0x14000d44b  mov     rax, r15
0x14000d44e  mov     edx, r8d
0x14000d451  cmp     [rax], r12w
0x14000d455  jz      short loc_14000D460
0x14000d457  add     rax, 2
0x14000d45b  sub     rdx, r11
0x14000d45e  jnz     short loc_14000D451
0x14000d460  mov     rax, rdx
0x14000d463  neg     rax
0x14000d466  sbb     ebx, ebx
0x14000d468  not     ebx
0x14000d46a  and     ebx, ecx
0x14000d46c  test    rdx, rdx
0x14000d46f  jz      short loc_14000D4AF
0x14000d471  sub     r8, rdx
0x14000d474  neg     rdx
0x14000d477  sbb     rax, rax
0x14000d47a  lea     rbx, [r8+r8]
0x14000d47e  and     rbx, rax
0x14000d481  lea     rcx, [rbx+2]
0x14000d485  call    DAF_user_alloc
0x14000d48a  mov     rdi, rax
0x14000d48d  test    rax, rax
0x14000d490  jnz     short loc_14000D499
0x14000d492  mov     ebx, 8007000Eh
0x14000d497  jmp     short loc_14000D4B6
0x14000d499  lea     r8, [rbx+2]; Size
0x14000d49d  mov     rdx, r15; Src
0x14000d4a0  mov     rcx, rax; void *
0x14000d4a3  call    memcpy_0
0x14000d4a8  jmp     loc_14000D285
0x14000d4ad  mov     ebx, ecx
0x14000d4af  mov     rdi, r12
0x14000d4b2  jmp     short loc_14000D4B6
0x14000d4b4  mov     ebx, ecx
0x14000d4b6  mov     rcx, [rbp+DuplicateTokenHandle]; hObject
0x14000d4ba  test    rcx, rcx
0x14000d4bd  jz      short loc_14000D4C5
0x14000d4bf  call    cs:__imp_CloseHandle
0x14000d4c5  test    rdi, rdi
0x14000d4c8  jz      short loc_14000D4DE
0x14000d4ca  call    cs:__imp_GetProcessHeap
0x14000d4d0  mov     r8, rdi; lpMem
0x14000d4d3  xor     edx, edx; dwFlags
0x14000d4d5  mov     rcx, rax; hHeap
0x14000d4d8  call    cs:__imp_HeapFree
0x14000d4de  test    ebx, ebx
0x14000d4e0  jns     short loc_14000D4F1
0x14000d4e2  mov     r9, r14; void *
0x14000d4e5  mov     r8d, ebx; int
0x14000d4e8  xor     edx, edx; struct _DEVPROPERTY *
0x14000d4ea  xor     ecx, ecx; unsigned int
0x14000d4ec  call    ?OnAepImportCompleteStub@@YAJKQEAU_DEVPROPERTY@@JPEAX@Z; OnAepImportCompleteStub(ulong,_DEVPROPERTY * const,long,void *)
0x14000d4f1  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d4f8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d4ff  jz      short loc_14000D527
0x14000d501  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d508  lea     rax, WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids
0x14000d50f  mov     r9d, 0Fh; int
0x14000d515  mov     dword ptr [rsp+60h+var_30], ebx; char
0x14000d519  mov     [rsp+60h+MessageGuid], rax; MessageGuid
0x14000d51e  mov     rcx, [rcx+28h]; int
0x14000d522  call    WPP_RECORDER_SF_sd
0x14000d527  mov     rbx, [rbp+var_18+8]
0x14000d52b  test    rbx, rbx
0x14000d52e  jz      short loc_14000D566
0x14000d530  or      edi, 0FFFFFFFFh
0x14000d533  mov     eax, edi
0x14000d535  lock xadd [rbx+8], eax
0x14000d53a  add     eax, edi
0x14000d53c  jnz     short loc_14000D566
0x14000d53e  mov     rax, [rbx]
0x14000d541  mov     rcx, rbx
0x14000d544  mov     rax, [rax]
0x14000d547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d54c  mov     eax, edi
0x14000d54e  lock xadd [rbx+0Ch], eax
0x14000d553  add     eax, edi
0x14000d555  jnz     short loc_14000D566
0x14000d557  mov     rax, [rbx]
0x14000d55a  mov     rcx, rbx
0x14000d55d  mov     rax, [rax+8]
0x14000d561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d566  mov     rbx, [rsp+60h+arg_10]
0x14000d56e  add     rsp, 60h
0x14000d572  pop     r15
0x14000d574  pop     r14
0x14000d576  pop     r13
0x14000d578  pop     r12
0x14000d57a  pop     rdi
0x14000d57b  pop     rsi
0x14000d57c  pop     rbp
0x14000d57d  retn
```
