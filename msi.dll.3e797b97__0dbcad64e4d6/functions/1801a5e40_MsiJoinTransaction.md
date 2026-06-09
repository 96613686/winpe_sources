# MsiJoinTransaction

- ea: `0x1801a5e40`
- end: `0x1801a6457`
- name: `MsiJoinTransaction`
- size: `1559`
- prototype: `UINT __stdcall(MSIHANDLE hTransactionHandle, DWORD dwTransactionAttributes, HANDLE *phChangeOfOwnerEvent)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005af8`
- `0x18000c4bc`
- `0x18000ca3c`
- `0x18000d6d8`
- `0x180010ac0`
- `0x1800141e0`
- `0x180018ee0`
- `0x180019cc0`
- `0x1800e22e0`
- `0x18012b2c0`
- `0x180148a10`
- `0x180178ad0`
- `0x1801a5e40`
- `0x1801d6748`
- `0x180209c0c`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1801a624b`
- `KERNEL32!WaitForSingleObject` at `0x1801a624b`
- `KERNEL32!OpenEventW` at `0x1801a6062`
- `KERNEL32!OpenEventW` at `0x1801a6105`
- `KERNEL32!OpenEventW` at `0x1801a61de`
- `KERNEL32!OpenEventW` at `0x1801a6062`
- `KERNEL32!OpenEventW` at `0x1801a6105`
- `KERNEL32!OpenEventW` at `0x1801a61de`
- `KERNEL32!CreateEventW` at `0x1801a6262`
- `KERNEL32!CreateEventW` at `0x1801a6284`
- `KERNEL32!CreateEventW` at `0x1801a6262`
- `KERNEL32!CreateEventW` at `0x1801a6284`
- `KERNEL32!CreateThread` at `0x1801a62e2`
- `KERNEL32!CreateThread` at `0x1801a62e2`

## string_xrefs

- `0x1801a60c4`: `Error occurred in string function, unable to create end transaction event.`
- `0x1801a613e`: `Error occured opening event: %s`
- `0x1801a63ae`: `Error occured opening event: %s`
- `0x1801a619b`: `Error occurred in string function, unable to create ack event.`
- `0x1801a6332`: `Error occurred creating cleanup EEUI on change of owner thread.`
- `0x1801a5e8f`: `Entering MsiJoinTransaction. hTransactionHandle: %d, dwTransactionAttributes: %d`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
UINT __stdcall MsiJoinTransaction(
        MSIHANDLE hTransactionHandle,
        DWORD dwTransactionAttributes,
        HANDLE *phChangeOfOwnerEvent)
{
  const bool *v6; // r8
  int v7; // eax
  struct IMsiServer *MsiServer; // rax
  struct IMsiServer *v10; // rbx
  char v11; // al
  char v12; // r12
  CMsiAPIMessage *v13; // rcx
  UINT v14; // edi
  unsigned int v15; // edx
  _QWORD *v16; // rax
  void *v17; // rax
  void *v18; // rdi
  __int64 v19; // rcx
  HANDLE v20; // r14
  WCHAR *v21; // rax
  const unsigned __int16 *v22; // r9
  HANDLE EventW; // rdi
  HANDLE v24; // rsi
  _QWORD *v25; // rax
  void *v26; // rbx
  HANDLE Thread; // rax
  int v28; // ebx
  _BYTE v29[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v30; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v31; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v32; // [rsp+6Ch] [rbp-94h] BYREF
  _QWORD v33[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v35[264]; // [rsp+290h] [rbp+190h] BYREF

  v6 = L"(NULL)";
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"Entering MsiJoinTransaction. hTransactionHandle: %d, dwTransactionAttributes: %d",
      (const unsigned __int16 *)hTransactionHandle,
      (const unsigned __int16 *)dwTransactionAttributes,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  if ( !phChangeOfOwnerEvent || dwTransactionAttributes > 2 )
    return 87;
  v7 = ((__int64 (__fastcall *)(_QWORD, _QWORD, const bool *))OLE32::CoInitialize)(
         0,
         *(_QWORD *)&dwTransactionAttributes,
         v6);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147417850 )
    return 1603;
  v29[0] = v7 >= 0;
  MsiServer = CreateMsiServer();
  v33[0] = MsiServer;
  v10 = MsiServer;
  if ( MsiServer )
  {
    v11 = (*(__int64 (__fastcall **)(struct IMsiServer *))(*(_QWORD *)MsiServer + 224LL))(MsiServer);
    v30 = 1;
    v12 = v11;
    v14 = (*(__int64 (__fastcall **)(struct IMsiServer *, _QWORD, _QWORD, unsigned int *, WCHAR *))(*(_QWORD *)v10
                                                                                                  + 176LL))(
            v10,
            hTransactionHandle,
            dwTransactionAttributes,
            &v30,
            Name);
    if ( v14 )
    {
LABEL_48:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v33);
      CCoUninitialize::~CCoUninitialize((CCoUninitialize *)v29);
      return v14;
    }
    CMsiAPIMessage::SetInternalHandler(v13, v30, 0);
    if ( dwTransactionAttributes != 2 )
      goto LABEL_16;
    if ( g_pEmbeddedUI )
      CMsiEmbeddedUIManager::`scalar deleting destructor'((CMsiEmbeddedUIManager *)g_pEmbeddedUI, v15);
    v16 = operator new(0x448u);
    if ( v16 )
    {
      v16[65] = 0;
      v16[66] = 0;
      *((_WORD *)v16 + 274) = 0;
      *((_DWORD *)v16 + 136) = 0;
      *(_QWORD *)((char *)v16 + 1068) = 0;
      v16[135] = 0;
      v16[67] = &MsiUIMessageHandler::`vftable';
      *((_DWORD *)v16 + 272) = 0;
      *((_BYTE *)v16 + 1092) = 0;
      *(_WORD *)v16 = 0;
      v32 = 0;
      g_pEmbeddedUI = (LPCWSTR)v16;
      v17 = operator new(0x208u);
      v18 = v17;
      if ( v17 )
      {
        v31 = 0;
        (*(void (__fastcall **)(struct IMsiServer *, void *, unsigned int *, unsigned int *))(*(_QWORD *)v10 + 208LL))(
          v10,
          v17,
          &v32,
          &v31);
        CMsiEmbeddedUIManager::JoinExistingEEUI(v19, v18, v32, v31);
        operator delete(v18);
LABEL_16:
        v20 = OpenEventW(0x100000u, 0, Name);
        if ( !v20 )
        {
          if ( g_dmDiagnosticMode )
          {
            v22 = L"Error occured opening event: %s";
            v21 = Name;
            goto LABEL_46;
          }
          goto LABEL_47;
        }
        if ( (int)StringCchPrintfW(v35, 0x105u, L"%s%s", Name, L"ET") < 0 )
        {
          if ( g_dmDiagnosticMode )
          {
            v21 = (WCHAR *)L"(NULL)";
            v22 = L"Error occurred in string function, unable to create end transaction event.";
LABEL_46:
            DebugString(9, 0, 0, v22, v21, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
            goto LABEL_47;
          }
          goto LABEL_47;
        }
        g_hEndTransactionEvent = OpenEventW(0x100000u, 0, v35);
        if ( !g_hEndTransactionEvent && g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"Error occured opening event: %s",
            v35,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        if ( (int)StringCchCatW(Name, 0x105u, L"Reset") < 0 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              L"Error occurred in string function, unable to create ack event.",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          goto LABEL_47;
        }
        if ( v12 )
        {
          EventW = OpenEventW(0x100002u, 0, Name);
          if ( !EventW )
            goto LABEL_30;
          (*(void (__fastcall **)(struct IMsiServer *))(*(_QWORD *)v10 + 192LL))(v10);
          WaitForSingleObject(EventW, 0xFFFFFFFF);
        }
        else
        {
          EventW = CreateEventW(0, 0, 0, Name);
          if ( !EventW )
          {
LABEL_30:
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                L"Error occured creating event",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            goto LABEL_47;
          }
        }
        v24 = CreateEventW(0, 0, 0, 0);
        if ( !v24 )
        {
          if ( g_dmDiagnosticMode )
          {
            v21 = (WCHAR *)L"(NULL)";
            v22 = L"Error occured creating event";
            goto LABEL_46;
          }
LABEL_47:
          v14 = 0;
          goto LABEL_48;
        }
        if ( LoadServices() )
        {
          *phChangeOfOwnerEvent = v24;
          v25 = operator new(0x18u);
          v26 = v25;
          if ( v25 )
          {
            *v25 = v20;
            v25[2] = v24;
            v25[1] = EventW;
            Thread = CreateThread(0, 0, CleanupEEUIOnChangeOfOwnerThread, v25, 0, 0);
            g_hCleanupEEUIThread = Thread;
          }
          else
          {
            Thread = g_hCleanupEEUIThread;
          }
          if ( Thread )
            goto LABEL_47;
          operator delete(v26);
          FreeServices();
          if ( !g_dmDiagnosticMode )
            goto LABEL_47;
          v21 = (WCHAR *)L"(NULL)";
          v22 = L"Error occurred creating cleanup EEUI on change of owner thread.";
          goto LABEL_46;
        }
      }
    }
    else
    {
      g_pEmbeddedUI = 0;
    }
    v14 = 14;
    goto LABEL_48;
  }
  v28 = InSafeMode() ? 0x33 : 0;
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v33);
  CCoUninitialize::~CCoUninitialize((CCoUninitialize *)v29);
  return v28 + 1601;
}

```

## disassembly

```asm
0x1801a5e40  mov     [rsp-8+arg_18], rbx
0x1801a5e45  push    rbp
0x1801a5e46  push    rsi
0x1801a5e47  push    rdi
0x1801a5e48  push    r12
0x1801a5e4a  push    r13
0x1801a5e4c  push    r14
0x1801a5e4e  push    r15
0x1801a5e50  lea     rbp, [rsp-3B0h]
0x1801a5e58  sub     rsp, 4B0h
0x1801a5e5f  mov     rax, cs:__security_cookie
0x1801a5e66  xor     rax, rsp
0x1801a5e69  mov     [rbp+3E0h+var_40], rax
0x1801a5e70  xor     r13d, r13d
0x1801a5e73  mov     esi, edx
0x1801a5e75  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801a5e7c  mov     r15, r8
0x1801a5e7f  mov     edi, ecx
0x1801a5e81  lea     r8, aNull; "(NULL)"
0x1801a5e88  jz      short loc_1801A5EC6
0x1801a5e8a  mov     [rsp+4E0h+var_488], r13; void *
0x1801a5e8f  lea     r9, aEnteringMsijoi; "Entering MsiJoinTransaction. hTransacti"...
0x1801a5e96  mov     [rsp+4E0h+var_490], r13d; unsigned int
0x1801a5e9b  xor     edx, edx; unsigned __int16
0x1801a5e9d  mov     [rsp+4E0h+var_498], r8; unsigned __int16 *
0x1801a5ea2  mov     [rsp+4E0h+var_4A0], r8; unsigned __int16 *
0x1801a5ea7  mov     [rsp+4E0h+var_4A8], r8; unsigned __int16 *
0x1801a5eac  mov     [rsp+4E0h+var_4B0], r8; unsigned __int16 *
0x1801a5eb1  lea     ecx, [rdx+9]; int
0x1801a5eb4  mov     [rsp+4E0h+lpThreadId], rsi; unsigned __int16 *
0x1801a5eb9  xor     r8d, r8d; int
0x1801a5ebc  mov     qword ptr [rsp+4E0h+dwCreationFlags], rdi; unsigned __int16 *
0x1801a5ec1  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801a5ec6  test    r15, r15
0x1801a5ec9  jz      loc_1801A6427
0x1801a5ecf  cmp     esi, 2
0x1801a5ed2  ja      loc_1801A6427
0x1801a5ed8  mov     rax, cs:?CoInitialize@OLE32@@3P6AJPEAX@ZEA; long (*OLE32::CoInitialize)(void *)
0x1801a5edf  xor     ecx, ecx
0x1801a5ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a5ee6  mov     edx, 80000000h
0x1801a5eeb  lea     ecx, [rax+rdx]
0x1801a5eee  test    edx, ecx
0x1801a5ef0  jnz     short loc_1801A5F03
0x1801a5ef2  cmp     eax, 80010106h
0x1801a5ef7  jz      short loc_1801A5F03
0x1801a5ef9  mov     eax, 643h
0x1801a5efe  jmp     loc_1801A642C
0x1801a5f03  shr     eax, 1Fh
0x1801a5f06  xor     al, 1
0x1801a5f08  mov     [rsp+4E0h+var_480], al
0x1801a5f0c  call    ?CreateMsiServer@@YAPEAUIMsiServer@@XZ; CreateMsiServer(void)
0x1801a5f11  mov     [rsp+4E0h+var_470], rax
0x1801a5f16  mov     rbx, rax
0x1801a5f19  test    rax, rax
0x1801a5f1c  jz      loc_1801A63FF
0x1801a5f22  mov     rax, [rax]
0x1801a5f25  mov     rcx, rbx
0x1801a5f28  mov     rax, [rax+0E0h]
0x1801a5f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a5f34  mov     [rsp+4E0h+var_47C], 1
0x1801a5f3c  lea     r9, [rsp+4E0h+var_47C]
0x1801a5f41  mov     rcx, [rbx]
0x1801a5f44  mov     r12b, al
0x1801a5f47  mov     r8d, esi
0x1801a5f4a  mov     edx, edi
0x1801a5f4c  mov     rax, [rcx+0B0h]
0x1801a5f53  lea     rcx, [rbp+3E0h+Name]
0x1801a5f57  mov     qword ptr [rsp+4E0h+dwCreationFlags], rcx
0x1801a5f5c  mov     rcx, rbx
0x1801a5f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a5f64  mov     edi, eax
0x1801a5f66  test    eax, eax
0x1801a5f68  jnz     loc_1801A63E7
0x1801a5f6e  mov     edx, [rsp+4E0h+var_47C]; unsigned int
0x1801a5f72  xor     r8d, r8d; HWND *
0x1801a5f75  call    ?SetInternalHandler@CMsiAPIMessage@@QEAA?AW4tagINSTALLUILEVEL@@IPEAPEAUHWND__@@@Z; CMsiAPIMessage::SetInternalHandler(uint,HWND__ * *)
0x1801a5f7a  cmp     esi, 2
0x1801a5f7d  jnz     loc_1801A6055
0x1801a5f83  mov     rcx, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; this
0x1801a5f8a  test    rcx, rcx
0x1801a5f8d  jz      short loc_1801A5F94
0x1801a5f8f  call    ??_GCMsiEmbeddedUIManager@@QEAAPEAXI@Z; CMsiEmbeddedUIManager::`scalar deleting destructor'(uint)
0x1801a5f94  mov     ecx, 448h; unsigned __int64
0x1801a5f99  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801a5f9e  mov     rdx, rax
0x1801a5fa1  test    rax, rax
0x1801a5fa4  jz      loc_1801A60E9
0x1801a5faa  mov     [rax+208h], r13
0x1801a5fb1  mov     ecx, 208h; unsigned __int64
0x1801a5fb6  mov     [rax+210h], r13
0x1801a5fbd  mov     [rax+224h], r13w
0x1801a5fc5  mov     [rax+220h], r13d
0x1801a5fcc  mov     [rax+42Ch], r13
0x1801a5fd3  mov     [rax+438h], r13
0x1801a5fda  lea     rax, ??_7MsiUIMessageHandler@@6B@; const MsiUIMessageHandler::`vftable'
0x1801a5fe1  mov     [rdx+218h], rax
0x1801a5fe8  mov     [rdx+440h], r13d
0x1801a5fef  mov     [rdx+444h], r13b
0x1801a5ff6  mov     [rdx], r13w
0x1801a5ffa  mov     [rsp+4E0h+var_474], r13d
0x1801a5fff  mov     cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA, rdx; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x1801a6006  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801a600b  mov     rdi, rax
0x1801a600e  test    rax, rax
0x1801a6011  jz      loc_1801A60F0
0x1801a6017  mov     [rsp+4E0h+var_478], r13d
0x1801a601c  lea     r9, [rsp+4E0h+var_478]
0x1801a6021  mov     rcx, [rbx]
0x1801a6024  lea     r8, [rsp+4E0h+var_474]
0x1801a6029  mov     rdx, rdi
0x1801a602c  mov     rax, [rcx+0D0h]
0x1801a6033  mov     rcx, rbx
0x1801a6036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a603b  mov     r9d, [rsp+4E0h+var_478]
0x1801a6040  mov     rdx, rdi
0x1801a6043  mov     r8d, [rsp+4E0h+var_474]
0x1801a6048  call    ?JoinExistingEEUI@CMsiEmbeddedUIManager@@QEAAKPEAGKW4icacCustomActionContext@@@Z; CMsiEmbeddedUIManager::JoinExistingEEUI(ushort *,ulong,icacCustomActionContext)
0x1801a604d  mov     rcx, rdi; void *
0x1801a6050  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801a6055  mov     edi, 100000h
0x1801a605a  lea     r8, [rbp+3E0h+Name]; lpName
0x1801a605e  mov     ecx, edi; dwDesiredAccess
0x1801a6060  xor     edx, edx; bInheritHandle
0x1801a6062  call    cs:__imp_OpenEventW
0x1801a6069  nop     dword ptr [rax+rax+00h]
0x1801a606e  mov     r14, rax
0x1801a6071  test    rax, rax
0x1801a6074  jz      loc_1801A6394
0x1801a607a  lea     rax, aEt; "ET"
0x1801a6081  mov     edx, 105h; unsigned __int64
0x1801a6086  lea     r9, [rbp+3E0h+Name]
0x1801a608a  mov     qword ptr [rsp+4E0h+dwCreationFlags], rax
0x1801a608f  lea     r8, aSS_1; "%s%s"
0x1801a6096  lea     rcx, [rbp+3E0h+var_250]; unsigned __int16 *
0x1801a609d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801a60a2  test    eax, eax
0x1801a60a4  jns     short loc_1801A60FA
0x1801a60a6  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801a60ad  jz      loc_1801A63E4
0x1801a60b3  mov     [rsp+4E0h+var_488], r13
0x1801a60b8  lea     rax, aNull; "(NULL)"
0x1801a60bf  mov     [rsp+4E0h+var_490], r13d
0x1801a60c4  lea     r9, aErrorOccurredI; "Error occurred in string function, unab"...
0x1801a60cb  mov     [rsp+4E0h+var_498], rax
0x1801a60d0  mov     [rsp+4E0h+var_4A0], rax
0x1801a60d5  mov     [rsp+4E0h+var_4A8], rax
0x1801a60da  mov     [rsp+4E0h+var_4B0], rax
0x1801a60df  mov     [rsp+4E0h+lpThreadId], rax
0x1801a60e4  jmp     loc_1801A63D2
0x1801a60e9  mov     cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA, r13; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x1801a60f0  mov     edi, 0Eh
0x1801a60f5  jmp     loc_1801A63E7
0x1801a60fa  lea     r8, [rbp+3E0h+var_250]; lpName
0x1801a6101  xor     edx, edx; bInheritHandle
0x1801a6103  mov     ecx, edi; dwDesiredAccess
0x1801a6105  call    cs:__imp_OpenEventW
0x1801a610c  nop     dword ptr [rax+rax+00h]
0x1801a6111  mov     cs:?g_hEndTransactionEvent@@3PEAXEA, rax; void * g_hEndTransactionEvent
0x1801a6118  lea     rsi, aNull; "(NULL)"
0x1801a611f  test    rax, rax
0x1801a6122  jnz     short loc_1801A6170
0x1801a6124  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801a612b  jz      short loc_1801A6170
0x1801a612d  mov     [rsp+4E0h+var_488], r13; void *
0x1801a6132  lea     rax, [rbp+3E0h+var_250]
0x1801a6139  mov     [rsp+4E0h+var_490], r13d; unsigned int
0x1801a613e  lea     r9, aErrorOccuredOp; "Error occured opening event: %s"
0x1801a6145  mov     [rsp+4E0h+var_498], rsi; unsigned __int16 *
0x1801a614a  xor     edx, edx; unsigned __int16
0x1801a614c  mov     [rsp+4E0h+var_4A0], rsi; unsigned __int16 *
0x1801a6151  xor     r8d, r8d; int
0x1801a6154  mov     [rsp+4E0h+var_4A8], rsi; unsigned __int16 *
0x1801a6159  mov     [rsp+4E0h+var_4B0], rsi; unsigned __int16 *
0x1801a615e  mov     [rsp+4E0h+lpThreadId], rsi; unsigned __int16 *
0x1801a6163  lea     ecx, [rdx+9]; int
0x1801a6166  mov     qword ptr [rsp+4E0h+dwCreationFlags], rax; unsigned __int16 *
0x1801a616b  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801a6170  lea     r8, aReset; "Reset"
0x1801a6177  mov     edx, 105h; unsigned __int64
0x1801a617c  lea     rcx, [rbp+3E0h+Name]; unsigned __int16 *
0x1801a6180  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801a6185  test    eax, eax
0x1801a6187  jns     short loc_1801A61CA
0x1801a6189  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801a6190  jz      loc_1801A63E4
0x1801a6196  mov     [rsp+4E0h+var_488], r13
0x1801a619b  lea     r9, aErrorOccurredI_0; "Error occurred in string function, unab"...
0x1801a61a2  mov     [rsp+4E0h+var_490], r13d
0x1801a61a7  mov     [rsp+4E0h+var_498], rsi
0x1801a61ac  mov     [rsp+4E0h+var_4A0], rsi
0x1801a61b1  mov     [rsp+4E0h+var_4A8], rsi
0x1801a61b6  mov     [rsp+4E0h+var_4B0], rsi
0x1801a61bb  mov     [rsp+4E0h+lpThreadId], rsi
0x1801a61c0  mov     qword ptr [rsp+4E0h+dwCreationFlags], rsi
0x1801a61c5  jmp     loc_1801A63D7
0x1801a61ca  xor     edx, edx; bManualReset
0x1801a61cc  test    r12b, r12b
0x1801a61cf  jz      loc_1801A6259
0x1801a61d5  lea     r8, [rbp+3E0h+Name]; lpName
0x1801a61d9  mov     ecx, 100002h; dwDesiredAccess
0x1801a61de  call    cs:__imp_OpenEventW
0x1801a61e5  nop     dword ptr [rax+rax+00h]
0x1801a61ea  mov     rdi, rax
0x1801a61ed  test    rax, rax
0x1801a61f0  jnz     short loc_1801A6233
0x1801a61f2  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801a61f9  jz      loc_1801A63E4
0x1801a61ff  mov     [rsp+4E0h+var_488], r13
0x1801a6204  lea     r9, aErrorOccuredCr_1; "Error occured creating event"
0x1801a620b  mov     [rsp+4E0h+var_490], r13d
0x1801a6210  mov     [rsp+4E0h+var_498], rsi
0x1801a6215  mov     [rsp+4E0h+var_4A0], rsi
0x1801a621a  mov     [rsp+4E0h+var_4A8], rsi
0x1801a621f  mov     [rsp+4E0h+var_4B0], rsi
0x1801a6224  mov     [rsp+4E0h+lpThreadId], rsi
0x1801a6229  mov     qword ptr [rsp+4E0h+dwCreationFlags], rsi
0x1801a622e  jmp     loc_1801A63D7
0x1801a6233  mov     rax, [rbx]
0x1801a6236  mov     rcx, rbx
0x1801a6239  mov     rax, [rax+0C0h]
0x1801a6240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a6245  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801a6248  mov     rcx, rdi; hHandle
0x1801a624b  call    cs:__imp_WaitForSingleObject
0x1801a6252  nop     dword ptr [rax+rax+00h]
0x1801a6257  jmp     short loc_1801A627A
0x1801a6259  lea     r9, [rbp+3E0h+Name]; lpName
0x1801a625d  xor     r8d, r8d; bInitialState
0x1801a6260  xor     ecx, ecx; lpEventAttributes
0x1801a6262  call    cs:__imp_CreateEventW
0x1801a6269  nop     dword ptr [rax+rax+00h]
0x1801a626e  mov     rdi, rax
0x1801a6271  test    rax, rax
0x1801a6274  jz      loc_1801A61F2
0x1801a627a  xor     r9d, r9d; lpName
0x1801a627d  xor     r8d, r8d; bInitialState
0x1801a6280  xor     edx, edx; bManualReset
0x1801a6282  xor     ecx, ecx; lpEventAttributes
0x1801a6284  call    cs:__imp_CreateEventW
0x1801a628b  nop     dword ptr [rax+rax+00h]
0x1801a6290  mov     rsi, rax
0x1801a6293  test    rax, rax
0x1801a6296  jz      loc_1801A6354
0x1801a629c  call    ?LoadServices@@YAPEAVIMsiServices@@XZ; LoadServices(void)
0x1801a62a1  test    rax, rax
0x1801a62a4  jz      loc_1801A60F0
0x1801a62aa  mov     ecx, 18h; unsigned __int64
0x1801a62af  mov     [r15], rsi
0x1801a62b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801a62b7  mov     rbx, rax
0x1801a62ba  test    rax, rax
0x1801a62bd  jz      short loc_1801A62F7
0x1801a62bf  mov     [rsp+4E0h+lpThreadId], r13; lpThreadId
0x1801a62c4  lea     r8, ?CleanupEEUIOnChangeOfOwnerThread@@YAKPEAX@Z; lpStartAddress
0x1801a62cb  mov     r9, rax; lpParameter
0x1801a62ce  mov     [rsp+4E0h+dwCreationFlags], r13d; dwCreationFlags
0x1801a62d3  xor     edx, edx; dwStackSize
0x1801a62d5  mov     [rax], r14
0x1801a62d8  xor     ecx, ecx; lpThreadAttributes
0x1801a62da  mov     [rax+10h], rsi
0x1801a62de  mov     [rax+8], rdi
0x1801a62e2  call    cs:__imp_CreateThread
0x1801a62e9  nop     dword ptr [rax+rax+00h]
0x1801a62ee  mov     cs:?g_hCleanupEEUIThread@@3PEAXEA, rax; void * g_hCleanupEEUIThread
0x1801a62f5  jmp     short loc_1801A62FE
0x1801a62f7  mov     rax, cs:?g_hCleanupEEUIThread@@3PEAXEA; void * g_hCleanupEEUIThread
0x1801a62fe  test    rax, rax
0x1801a6301  jnz     loc_1801A63E4
0x1801a6307  mov     rcx, rbx; void *
0x1801a630a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801a630f  call    ?FreeServices@@YAHXZ; FreeServices(void)
0x1801a6314  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801a631b  jz      loc_1801A63E4
0x1801a6321  mov     [rsp+4E0h+var_488], r13
0x1801a6326  lea     rax, aNull; "(NULL)"
0x1801a632d  mov     [rsp+4E0h+var_490], r13d
0x1801a6332  lea     r9, aErrorOccurredC; "Error occurred creating cleanup EEUI on"...
0x1801a6339  mov     [rsp+4E0h+var_498], rax
0x1801a633e  mov     [rsp+4E0h+var_4A0], rax
0x1801a6343  mov     [rsp+4E0h+var_4A8], rax
0x1801a6348  mov     [rsp+4E0h+var_4B0], rax
0x1801a634d  mov     [rsp+4E0h+lpThreadId], rax
0x1801a6352  jmp     short loc_1801A63D2
0x1801a6354  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801a635b  jz      loc_1801A63E4
0x1801a6361  mov     [rsp+4E0h+var_488], r13
0x1801a6366  lea     rax, aNull; "(NULL)"
0x1801a636d  mov     [rsp+4E0h+var_490], r13d
0x1801a6372  lea     r9, aErrorOccuredCr_1; "Error occured creating event"
0x1801a6379  mov     [rsp+4E0h+var_498], rax
0x1801a637e  mov     [rsp+4E0h+var_4A0], rax
0x1801a6383  mov     [rsp+4E0h+var_4A8], rax
0x1801a6388  mov     [rsp+4E0h+var_4B0], rax
0x1801a638d  mov     [rsp+4E0h+lpThreadId], rax
0x1801a6392  jmp     short loc_1801A63D2
0x1801a6394  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801a639b  jz      short loc_1801A63E4
0x1801a639d  mov     [rsp+4E0h+var_488], r13; void *
0x1801a63a2  lea     rax, aNull; "(NULL)"
  ... truncated ...
```
