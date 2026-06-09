# CWorkerThread::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18000c210`
- end: `0x18000c5cc`
- name: `?WorkCallback@CWorkerThread@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `956`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, unsigned int *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008f10`
- `0x18000c210`
- `0x18000c5d4`
- `0x18000ca14`
- `0x18000d910`
- `0x1800100b8`
- `0x1800107ac`
- `0x180013010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x18000c2dc`
- `ADVAPI32!SetThreadToken` at `0x18000c538`
- `ADVAPI32!SetThreadToken` at `0x18000c2dc`
- `ADVAPI32!SetThreadToken` at `0x18000c538`
- `KERNEL32!GetLastError` at `0x18000c2e6`
- `KERNEL32!GetLastError` at `0x18000c554`
- `KERNEL32!GetLastError` at `0x18000c2e6`
- `KERNEL32!GetLastError` at `0x18000c554`
- `KERNEL32!SetEventWhenCallbackReturns` at `0x18000c261`
- `KERNEL32!SetEventWhenCallbackReturns` at `0x18000c261`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c58c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c58c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c26b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c26b`

## pseudocode

```c
void __fastcall CWorkerThread::WorkCallback(PTP_CALLBACK_INSTANCE Instance, unsigned int *Context, PTP_WORK Work)
{
  int v5; // ebp
  HRESULT v6; // eax
  int v7; // esi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  signed int LastError; // eax
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rcx
  __int64 *v15; // rdx
  int v16; // eax
  __int64 v17; // rcx
  __int64 *v18; // rdx
  struct IUnknown **v19; // rdi
  __int64 v20; // rcx
  int v21; // eax
  struct IUnknown *v22; // rdx
  PVOID *v23; // rcx
  PVOID *v24; // rcx
  signed int v25; // eax

  v5 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
      *((_QWORD *)Context + 3));
  SetEventWhenCallbackReturns(Instance, *((HANDLE *)Context + 7));
  v6 = CoInitializeEx(0, 0);
  v7 = v6;
  if ( v6 == -2147417850 || v6 == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
        (unsigned int)v6);
LABEL_13:
    if ( !SetThreadToken(0, *((HANDLE *)Context + 4)) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_47;
      v9 = 51;
LABEL_19:
      v10 = (unsigned int)LastError;
      goto LABEL_46;
    }
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)Context + 2) + 32LL))(
            *((_QWORD *)Context + 2),
            Context[16]);
    v13 = v12;
    v5 = 1;
    if ( v12 < 0 )
    {
      v14 = (unsigned int)(v12 + 2147220991);
      if ( (v14 & 0xFFFFFDFF) != 0 )
      {
        if ( (Microsoft_Windows_FileHistory_CoreEnableBits & 2) != 0 )
        {
          v15 = CycleFailure_ScanAndBackup;
LABEL_26:
          McTemplateU0qz_EventWriteTransfer(v14, v15, (unsigned int)v12, *((_QWORD *)Context + 3));
        }
      }
      else if ( (Microsoft_Windows_FileHistory_CoreEnableBits & 4) != 0 )
      {
        v15 = CycleWarning_ScanAndBackup;
        goto LABEL_26;
      }
      if ( v13 == -2147220719 )
      {
        LastError = CWorkerThread::DuplicateConfiguration((CWorkerThread *)Context);
        if ( LastError >= 0 )
          goto LABEL_47;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_47;
        v9 = 52;
        goto LABEL_19;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_47;
      v9 = 53;
LABEL_45:
      v10 = v13;
      goto LABEL_46;
    }
    v16 = (*(__int64 (__fastcall **)(_QWORD, bool))(**((_QWORD **)Context + 2) + 64LL))(
            *((_QWORD *)Context + 2),
            Context[17] == 3);
    v13 = v16;
    if ( v16 >= 0 )
      goto LABEL_47;
    v17 = (unsigned int)(v16 + 2147220479);
    if ( (unsigned int)v17 <= 2 )
    {
      if ( (Microsoft_Windows_FileHistory_CoreEnableBits & 4) == 0 )
        goto LABEL_42;
      v18 = CycleWarning_Finalization;
    }
    else
    {
      if ( (Microsoft_Windows_FileHistory_CoreEnableBits & 2) == 0 )
        goto LABEL_42;
      v18 = CycleFailure_Finalization;
    }
    McTemplateU0qz_EventWriteTransfer(v17, v18, (unsigned int)v16, *((_QWORD *)Context + 3));
LABEL_42:
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_47;
    v9 = 54;
    goto LABEL_45;
  }
  if ( v6 >= 0 )
    goto LABEL_13;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 50;
    v10 = (unsigned int)v6;
LABEL_46:
    WPP_SF_d(v8[2], v9, &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids, v10);
  }
LABEL_47:
  if ( !Context[23] )
  {
    if ( v5 )
    {
      (*(void (__fastcall **)(_QWORD, char *, char *))(**((_QWORD **)Context + 2) + 80LL))(
        *((_QWORD *)Context + 2),
        (char *)Context + 80,
        (char *)Context + 84);
      Context[19] = 1;
    }
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)Context + 2) + 88LL))(
      *((_QWORD *)Context + 2),
      Context[17],
      Context[18]);
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)Context + 2) + 96LL))(
      *((_QWORD *)Context + 2),
      Context[17],
      Context[18]);
  }
  v19 = (struct IUnknown **)(Context + 2);
  v20 = *((_QWORD *)Context + 1);
  if ( v20 )
  {
    v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 40LL))(v20);
    if ( v21 < 0 )
    {
      v23 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            55,
            &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
            (unsigned int)v21);
          v23 = (PVOID *)WPP_GLOBAL_Control;
          v19 = (struct IUnknown **)(Context + 2);
        }
        if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 4) != 0 )
          WPP_SF_ss(
            (unsigned int)v23[2],
            56,
            (unsigned int)&WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
            (unsigned int)"FALSE",
            (__int64)"IFhCatalog::Detach has failed");
      }
    }
    if ( *v19 )
      ATL::AtlComPtrAssign(v19, v22);
  }
  if ( SetThreadToken(0, 0) )
    goto LABEL_67;
  v24 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v25 = GetLastError();
    if ( v25 > 0 )
      v25 = (unsigned __int16)v25 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
      (unsigned int)v25);
LABEL_67:
    v24 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 >= 0 )
  {
    CoUninitialize();
    v24 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 8) != 0 )
    WPP_SF_S(v24[2], 58, &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids, *((_QWORD *)Context + 3));
  Context[12] = 1;
}

```

## disassembly

```asm
0x18000c210  push    rbx
0x18000c212  push    rbp
0x18000c213  push    rsi
0x18000c214  push    rdi
0x18000c215  push    r12
0x18000c217  push    r14
0x18000c219  push    r15
0x18000c21b  sub     rsp, 30h
0x18000c21f  mov     rbx, rdx
0x18000c222  mov     rdi, rcx
0x18000c225  xor     ebp, ebp
0x18000c227  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c22e  lea     r14, WPP_GLOBAL_Control
0x18000c235  lea     r15, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x18000c23c  cmp     rcx, r14
0x18000c23f  jz      short loc_18000C25A
0x18000c241  test    byte ptr [rcx+1Ch], 8
0x18000c245  jz      short loc_18000C25A
0x18000c247  mov     r9, [rbx+18h]
0x18000c24b  lea     edx, [rbp+30h]
0x18000c24e  mov     rcx, [rcx+10h]
0x18000c252  mov     r8, r15
0x18000c255  call    WPP_SF_S
0x18000c25a  mov     rdx, [rbx+38h]; evt
0x18000c25e  mov     rcx, rdi; pci
0x18000c261  call    cs:__imp_SetEventWhenCallbackReturns
0x18000c267  xor     edx, edx; dwCoInit
0x18000c269  xor     ecx, ecx; pvReserved
0x18000c26b  call    cs:__imp_CoInitializeEx
0x18000c271  mov     esi, eax
0x18000c273  mov     r12d, 1
0x18000c279  cmp     eax, 80010106h
0x18000c27e  jz      short loc_18000C2B0
0x18000c280  cmp     eax, r12d
0x18000c283  jz      short loc_18000C2B0
0x18000c285  test    eax, eax
0x18000c287  jns     short loc_18000C2D6
0x18000c289  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c290  cmp     rcx, r14
0x18000c293  jz      loc_18000C456
0x18000c299  test    [rcx+1Ch], r12b
0x18000c29d  jz      loc_18000C456
0x18000c2a3  lea     edx, [r12+31h]
0x18000c2a8  mov     r9d, eax
0x18000c2ab  jmp     loc_18000C44A
0x18000c2b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2b7  cmp     rcx, r14
0x18000c2ba  jz      short loc_18000C2D6
0x18000c2bc  test    byte ptr [rcx+1Ch], 2
0x18000c2c0  jz      short loc_18000C2D6
0x18000c2c2  mov     rcx, [rcx+10h]
0x18000c2c6  mov     edx, 31h ; '1'
0x18000c2cb  mov     r9d, esi
0x18000c2ce  mov     r8, r15
0x18000c2d1  call    WPP_SF_d
0x18000c2d6  mov     rdx, [rbx+20h]; Token
0x18000c2da  xor     ecx, ecx; Thread
0x18000c2dc  call    cs:__imp_SetThreadToken
0x18000c2e2  test    eax, eax
0x18000c2e4  jnz     short loc_18000C31F
0x18000c2e6  call    cs:__imp_GetLastError
0x18000c2ec  test    eax, eax
0x18000c2ee  jle     short loc_18000C2F8
0x18000c2f0  movzx   eax, ax
0x18000c2f3  or      eax, 80070000h
0x18000c2f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2ff  cmp     rcx, r14
0x18000c302  jz      loc_18000C456
0x18000c308  test    [rcx+1Ch], r12b
0x18000c30c  jz      loc_18000C456
0x18000c312  mov     edx, 33h ; '3'
0x18000c317  mov     r9d, eax
0x18000c31a  jmp     loc_18000C44A
0x18000c31f  mov     rcx, [rbx+10h]
0x18000c323  mov     edx, [rbx+40h]
0x18000c326  mov     rax, [rcx]
0x18000c329  mov     rax, [rax+20h]
0x18000c32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c332  mov     edi, eax
0x18000c334  mov     ebp, r12d
0x18000c337  test    eax, eax
0x18000c339  jns     loc_18000C3D8
0x18000c33f  lea     ecx, [rax+7FFBFDFFh]
0x18000c345  test    ecx, 0FFFFFDFFh
0x18000c34b  jz      short loc_18000C35F
0x18000c34d  test    cs:Microsoft_Windows_FileHistory_CoreEnableBits, 2
0x18000c354  jz      short loc_18000C37B
0x18000c356  lea     rdx, CycleFailure_ScanAndBackup
0x18000c35d  jmp     short loc_18000C36F
0x18000c35f  test    cs:Microsoft_Windows_FileHistory_CoreEnableBits, 4
0x18000c366  jz      short loc_18000C37B
0x18000c368  lea     rdx, CycleWarning_ScanAndBackup
0x18000c36f  mov     r9, [rbx+18h]
0x18000c373  mov     r8d, edi
0x18000c376  call    McTemplateU0qz_EventWriteTransfer
0x18000c37b  cmp     edi, 80040311h
0x18000c381  jnz     short loc_18000C3B7
0x18000c383  mov     rcx, rbx; this
0x18000c386  call    ?DuplicateConfiguration@CWorkerThread@@AEAAJXZ; CWorkerThread::DuplicateConfiguration(void)
0x18000c38b  test    eax, eax
0x18000c38d  jns     loc_18000C456
0x18000c393  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c39a  cmp     rcx, r14
0x18000c39d  jz      loc_18000C456
0x18000c3a3  test    [rcx+1Ch], r12b
0x18000c3a7  jz      loc_18000C456
0x18000c3ad  mov     edx, 34h ; '4'
0x18000c3b2  jmp     loc_18000C317
0x18000c3b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3be  cmp     rcx, r14
0x18000c3c1  jz      loc_18000C456
0x18000c3c7  test    [rcx+1Ch], r12b
0x18000c3cb  jz      loc_18000C456
0x18000c3d1  mov     edx, 35h ; '5'
0x18000c3d6  jmp     short loc_18000C447
0x18000c3d8  mov     rcx, [rbx+10h]
0x18000c3dc  xor     edx, edx
0x18000c3de  cmp     dword ptr [rbx+44h], 3
0x18000c3e2  setz    dl
0x18000c3e5  mov     rax, [rcx]
0x18000c3e8  mov     rax, [rax+40h]
0x18000c3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3f1  mov     edi, eax
0x18000c3f3  test    eax, eax
0x18000c3f5  jns     short loc_18000C456
0x18000c3f7  lea     ecx, [rax+7FFBFBFFh]
0x18000c3fd  cmp     ecx, 2
0x18000c400  jbe     short loc_18000C414
0x18000c402  test    cs:Microsoft_Windows_FileHistory_CoreEnableBits, 2
0x18000c409  jz      short loc_18000C430
0x18000c40b  lea     rdx, CycleFailure_Finalization
0x18000c412  jmp     short loc_18000C424
0x18000c414  test    cs:Microsoft_Windows_FileHistory_CoreEnableBits, 4
0x18000c41b  jz      short loc_18000C430
0x18000c41d  lea     rdx, CycleWarning_Finalization
0x18000c424  mov     r9, [rbx+18h]
0x18000c428  mov     r8d, edi
0x18000c42b  call    McTemplateU0qz_EventWriteTransfer
0x18000c430  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c437  cmp     rcx, r14
0x18000c43a  jz      short loc_18000C456
0x18000c43c  test    [rcx+1Ch], r12b
0x18000c440  jz      short loc_18000C456
0x18000c442  mov     edx, 36h ; '6'
0x18000c447  mov     r9d, edi
0x18000c44a  mov     rcx, [rcx+10h]
0x18000c44e  mov     r8, r15
0x18000c451  call    WPP_SF_d
0x18000c456  cmp     dword ptr [rbx+5Ch], 0
0x18000c45a  jnz     short loc_18000C4AA
0x18000c45c  test    ebp, ebp
0x18000c45e  jz      short loc_18000C47C
0x18000c460  mov     rcx, [rbx+10h]
0x18000c464  lea     r8, [rbx+54h]
0x18000c468  lea     rdx, [rbx+50h]
0x18000c46c  mov     rax, [rcx]
0x18000c46f  mov     rax, [rax+50h]
0x18000c473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c478  mov     [rbx+4Ch], r12d
0x18000c47c  mov     rcx, [rbx+10h]
0x18000c480  mov     r8d, [rbx+48h]
0x18000c484  mov     edx, [rbx+44h]
0x18000c487  mov     rax, [rcx]
0x18000c48a  mov     rax, [rax+58h]
0x18000c48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c493  mov     rcx, [rbx+10h]
0x18000c497  mov     r8d, [rbx+48h]
0x18000c49b  mov     edx, [rbx+44h]
0x18000c49e  mov     rax, [rcx]
0x18000c4a1  mov     rax, [rax+60h]
0x18000c4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4aa  lea     rdi, [rbx+8]
0x18000c4ae  mov     rcx, [rdi]
0x18000c4b1  test    rcx, rcx
0x18000c4b4  jz      short loc_18000C534
0x18000c4b6  mov     rax, [rcx]
0x18000c4b9  mov     rax, [rax+28h]
0x18000c4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4c2  test    eax, eax
0x18000c4c4  jns     short loc_18000C526
0x18000c4c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4cd  cmp     rcx, r14
0x18000c4d0  jz      short loc_18000C526
0x18000c4d2  test    byte ptr [rcx+1Ch], 2
0x18000c4d6  jz      short loc_18000C4F7
0x18000c4d8  mov     rcx, [rcx+10h]
0x18000c4dc  mov     edx, 37h ; '7'
0x18000c4e1  mov     r9d, eax
0x18000c4e4  mov     r8, r15
0x18000c4e7  call    WPP_SF_d
0x18000c4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4f3  lea     rdi, [rbx+8]
0x18000c4f7  cmp     rcx, r14
0x18000c4fa  jz      short loc_18000C526
0x18000c4fc  test    byte ptr [rcx+1Ch], 4
0x18000c500  jz      short loc_18000C526
0x18000c502  mov     rcx, [rcx+10h]
0x18000c506  lea     rax, aIfhcatalogDeta; "IFhCatalog::Detach has failed"
0x18000c50d  mov     edx, 38h ; '8'
0x18000c512  mov     [rsp+68h+var_48], rax
0x18000c517  lea     r9, aFalse; "FALSE"
0x18000c51e  mov     r8, r15
0x18000c521  call    WPP_SF_ss
0x18000c526  cmp     qword ptr [rdi], 0
0x18000c52a  jz      short loc_18000C534
0x18000c52c  mov     rcx, rdi; struct IUnknown **
0x18000c52f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000c534  xor     edx, edx; Token
0x18000c536  xor     ecx, ecx; Thread
0x18000c538  call    cs:__imp_SetThreadToken
0x18000c53e  test    eax, eax
0x18000c540  jnz     short loc_18000C581
0x18000c542  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c549  cmp     rcx, r14
0x18000c54c  jz      short loc_18000C588
0x18000c54e  test    [rcx+1Ch], r12b
0x18000c552  jz      short loc_18000C588
0x18000c554  call    cs:__imp_GetLastError
0x18000c55a  test    eax, eax
0x18000c55c  jle     short loc_18000C566
0x18000c55e  movzx   eax, ax
0x18000c561  or      eax, 80070000h
0x18000c566  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c56d  mov     edx, 39h ; '9'
0x18000c572  mov     r9d, eax
0x18000c575  mov     r8, r15
0x18000c578  mov     rcx, [rcx+10h]
0x18000c57c  call    WPP_SF_d
0x18000c581  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c588  test    esi, esi
0x18000c58a  js      short loc_18000C599
0x18000c58c  call    cs:__imp_CoUninitialize
0x18000c592  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c599  cmp     rcx, r14
0x18000c59c  jz      short loc_18000C5B9
0x18000c59e  test    byte ptr [rcx+1Ch], 8
0x18000c5a2  jz      short loc_18000C5B9
0x18000c5a4  mov     r9, [rbx+18h]
0x18000c5a8  mov     edx, 3Ah ; ':'
0x18000c5ad  mov     rcx, [rcx+10h]
0x18000c5b1  mov     r8, r15
0x18000c5b4  call    WPP_SF_S
0x18000c5b9  mov     [rbx+30h], r12d
0x18000c5bd  add     rsp, 30h
0x18000c5c1  pop     r15
0x18000c5c3  pop     r14
0x18000c5c5  pop     r12
0x18000c5c7  pop     rdi
0x18000c5c8  pop     rsi
0x18000c5c9  pop     rbp
0x18000c5ca  pop     rbx
0x18000c5cb  retn
```
