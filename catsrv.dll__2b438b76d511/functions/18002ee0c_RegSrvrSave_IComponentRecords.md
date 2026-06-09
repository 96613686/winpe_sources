# RegSrvrSave(IComponentRecords * *)

- ea: `0x18002ee0c`
- end: `0x18002f152`
- name: `?RegSrvrSave@@YAJPEAPEAUIComponentRecords@@@Z`
- size: `838`
- prototype: `__int64 __fastcall(struct IComponentRecords **)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180017380`
- `0x180027320`
- `0x180039b60`

## callees

- `0x180007c2c`
- `0x18000997c`
- `0x180009ee0`
- `0x18000af70`
- `0x1800235ec`
- `0x18002ea9c`
- `0x18002ed84`
- `0x18002ee0c`
- `0x18002f324`
- `0x18002f82c`
- `0x180055502`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002eed3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f0e3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f0f0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002eed3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f0e3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f0f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ef0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f116`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ef0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f116`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002eef1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f0fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002eef1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f0fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002efcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002efcb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002f023`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002f023`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002f069`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002f069`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002efc1`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002efc1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002effa`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002effa`

## pseudocode

```c
__int64 __fastcall RegSrvrSave(struct IComponentRecords **a1)
{
  int TransactionID; // eax
  int v3; // ebx
  int v5; // esi
  unsigned int v6; // r14d
  __int64 v7; // rbp
  signed int LastError; // eax
  struct DELVERSION *Entry; // rbx
  struct BOID Buf1; // [rsp+30h] [rbp-458h] BYREF
  WCHAR NewFileName[264]; // [rsp+40h] [rbp-448h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+250h] [rbp-238h] BYREF

  Buf1 = 0;
  TransactionID = _GetTransactionID(&Buf1);
  v3 = TransactionID;
  if ( TransactionID >= 0 )
  {
    if ( !TransactionID )
    {
      if ( !(unsigned int)IsCallFromMsi() )
      {
        if ( memcmp_0(&Buf1, &g_txUOW, (unsigned int)(v3 + 16)) )
          v3 = -2147168238;
      }
      if ( !a1 )
        return (unsigned int)v3;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
      goto LABEL_37;
    }
    if ( g_pICrmLogControl )
    {
      ((void (__fastcall *)(struct ICrmLogControl *))g_pICrmLogControl->lpVtbl->Release)(g_pICrmLogControl);
      g_pICrmLogControl = 0;
    }
    if ( !dword_180072D18 )
    {
      if ( !a1 )
      {
        SetEvent(g_hTxInProgressEvent);
        return 0;
      }
      v3 = -2146368397;
      goto LABEL_37;
    }
    EnterCriticalSection(&stru_180073228);
    g_txUOW = (struct BOID)GUID_NULL;
    LeaveCriticalSection(&stru_180073228);
    if ( a1 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
      *a1 = 0;
      v3 = RegSrvrPrepareSave();
      if ( v3 < 0 )
      {
LABEL_37:
        *a1 = 0;
        return (unsigned int)v3;
      }
    }
    v5 = 0;
    dword_180072D18 = 0;
    v6 = 1;
    StringCchPrintfW(ExistingFileName, 0x104u, L"%s\\%s", &dword_180072FEC, L"_RegDBWrt.clb");
    while ( 1 )
    {
      v7 = 2;
      if ( qword_180072D20 + v6 < 0xFFFFFFFFFFFFLL )
        v7 = qword_180072D20 + v6;
      GetDBName(NewFileName, 0x105u, &dword_180072FEC, v7);
      if ( MoveFileExW(ExistingFileName, NewFileName, 8u) )
        break;
      LastError = GetLastError();
      v3 = LastError;
      if ( v6 == 1 && LastError == 183 )
      {
        v6 = 2;
      }
      else
      {
        if ( v5 >= 10 || LastError != 32 )
        {
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
          return (unsigned int)v3;
        }
        ++v5;
        Sleep(500 * v5);
      }
    }
    DeleteFileW(ExistingFileName);
    if ( !_SetUpdateEvent(v7) )
    {
      v3 = -2147418113;
      goto LABEL_36;
    }
    GetDBName(NewFileName, 0x105u, &dword_180072FEC, qword_180072D20 - *(unsigned int *)&Data);
    if ( GetFileAttributesW(NewFileName) != -1 )
    {
      Entry = _RegAllocateEntry(NewFileName);
      if ( !Entry )
      {
        v3 = -2147024882;
        goto LABEL_36;
      }
      ((void (__fastcall *)(void *))*Globals)(&Globals);
      *(_QWORD *)Entry = qword_180072D38;
      qword_180072D38 = Entry;
      (*(void (__fastcall **)(void *))(Globals + 8LL))(&Globals);
    }
    v3 = SetRegDbVersionInRegistry(v7);
    if ( v3 >= 0 )
    {
      SetEvent(g_hCommitEvent);
      SetEvent(g_hTxInProgressEvent);
      EnterCriticalSection(&CriticalSection);
      _RegReleaseReference((struct REGAPI_STATE *)&qword_180072DA0);
      LeaveCriticalSection(&CriticalSection);
    }
  }
LABEL_36:
  if ( a1 )
    goto LABEL_37;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002ee0c  mov     [rsp+arg_8], rbx
0x18002ee11  mov     [rsp+arg_10], rbp
0x18002ee16  push    rsi
0x18002ee17  push    rdi
0x18002ee18  push    r14
0x18002ee1a  sub     rsp, 470h
0x18002ee21  mov     rax, cs:__security_cookie
0x18002ee28  xor     rax, rsp
0x18002ee2b  mov     [rsp+488h+var_28], rax
0x18002ee33  mov     rdi, rcx
0x18002ee36  xorps   xmm0, xmm0
0x18002ee39  lea     rcx, [rsp+488h+Buf1]; struct BOID *
0x18002ee3e  movups  [rsp+488h+Buf1], xmm0
0x18002ee43  call    ?_GetTransactionID@@YAJPEAUBOID@@@Z; _GetTransactionID(BOID *)
0x18002ee48  mov     ebx, eax
0x18002ee4a  test    eax, eax
0x18002ee4c  js      loc_18002F11C
0x18002ee52  test    eax, eax
0x18002ee54  jnz     short loc_18002EE9B
0x18002ee56  call    ?IsCallFromMsi@@YAHXZ; IsCallFromMsi(void)
0x18002ee5b  test    eax, eax
0x18002ee5d  jnz     short loc_18002EE7E
0x18002ee5f  lea     r8d, [rbx+10h]; Size
0x18002ee63  lea     rdx, ?g_txUOW@@3UBOID@@A; Buf2
0x18002ee6a  lea     rcx, [rsp+488h+Buf1]; Buf1
0x18002ee6f  call    memcmp_0
0x18002ee74  test    eax, eax
0x18002ee76  mov     ecx, 8004D012h
0x18002ee7b  cmovnz  ebx, ecx
0x18002ee7e  test    rdi, rdi
0x18002ee81  jz      loc_18002F128
0x18002ee87  mov     rcx, [rdi]
0x18002ee8a  mov     rax, [rcx]
0x18002ee8d  mov     rax, [rax+10h]
0x18002ee91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee96  jmp     loc_18002F121
0x18002ee9b  mov     rcx, cs:?g_pICrmLogControl@@3PEAUICrmLogControl@@EA; ICrmLogControl * g_pICrmLogControl
0x18002eea2  test    rcx, rcx
0x18002eea5  jz      short loc_18002EEBE
0x18002eea7  mov     rax, [rcx]
0x18002eeaa  mov     rax, [rax+10h]
0x18002eeae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eeb3  mov     cs:?g_pICrmLogControl@@3PEAUICrmLogControl@@EA, 0; ICrmLogControl * g_pICrmLogControl
0x18002eebe  cmp     cs:dword_180072D18, 0
0x18002eec5  jnz     short loc_18002EEEA
0x18002eec7  test    rdi, rdi
0x18002eeca  jnz     short loc_18002EEE0
0x18002eecc  mov     rcx, cs:?g_hTxInProgressEvent@@3PEAXEA; hEvent
0x18002eed3  call    cs:__imp_SetEvent
0x18002eed9  xor     eax, eax
0x18002eedb  jmp     loc_18002F12A
0x18002eee0  mov     ebx, 80110473h
0x18002eee5  jmp     loc_18002F121
0x18002eeea  lea     rcx, stru_180073228; lpCriticalSection
0x18002eef1  call    cs:__imp_EnterCriticalSection
0x18002eef7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002eefe  lea     rcx, stru_180073228; lpCriticalSection
0x18002ef05  movdqu  cs:?g_txUOW@@3UBOID@@A, xmm0; BOID g_txUOW
0x18002ef0d  call    cs:__imp_LeaveCriticalSection
0x18002ef13  test    rdi, rdi
0x18002ef16  jz      short loc_18002EF3D
0x18002ef18  mov     rcx, [rdi]
0x18002ef1b  mov     rax, [rcx]
0x18002ef1e  mov     rax, [rax+10h]
0x18002ef22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef27  mov     qword ptr [rdi], 0
0x18002ef2e  call    ?RegSrvrPrepareSave@@YAJXZ; RegSrvrPrepareSave(void)
0x18002ef33  mov     ebx, eax
0x18002ef35  test    eax, eax
0x18002ef37  js      loc_18002F121
0x18002ef3d  xor     esi, esi
0x18002ef3f  lea     rax, aRegdbwrtClb; "_RegDBWrt.clb"
0x18002ef46  lea     r9, dword_180072FEC
0x18002ef4d  mov     cs:dword_180072D18, esi
0x18002ef53  lea     r8, aSS; "%s\\%s"
0x18002ef5a  mov     [rsp+488h+var_468], rax
0x18002ef5f  mov     edx, 104h; unsigned __int64
0x18002ef64  lea     rcx, [rsp+488h+ExistingFileName]; unsigned __int16 *
0x18002ef6c  lea     r14d, [rsi+1]
0x18002ef70  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ef75  mov     rax, 0FFFFFFFFFFFFh
0x18002ef7f  mov     edx, r14d
0x18002ef82  add     rdx, cs:qword_180072D20
0x18002ef89  lea     r8, dword_180072FEC; unsigned __int16 *
0x18002ef90  cmp     rdx, rax
0x18002ef93  lea     rcx, [rsp+488h+NewFileName]; unsigned __int16 *
0x18002ef98  mov     ebp, 2
0x18002ef9d  cmovl   rbp, rdx
0x18002efa1  mov     edx, 105h; unsigned __int64
0x18002efa6  mov     r9, rbp; __int64
0x18002efa9  call    ?GetDBName@@YA_KPEAG_KPEBG_J@Z; GetDBName(ushort *,unsigned __int64,ushort const *,__int64)
0x18002efae  mov     r8d, 8; dwFlags
0x18002efb4  lea     rdx, [rsp+488h+NewFileName]; lpNewFileName
0x18002efb9  lea     rcx, [rsp+488h+ExistingFileName]; lpExistingFileName
0x18002efc1  call    cs:__imp_MoveFileExW
0x18002efc7  test    eax, eax
0x18002efc9  jnz     short loc_18002F01B
0x18002efcb  call    cs:__imp_GetLastError
0x18002efd1  mov     ebx, eax
0x18002efd3  cmp     r14d, 1
0x18002efd7  jnz     short loc_18002EFE8
0x18002efd9  cmp     eax, 0B7h
0x18002efde  jnz     short loc_18002EFE8
0x18002efe0  mov     r14d, 2
0x18002efe6  jmp     short loc_18002EF75
0x18002efe8  cmp     esi, 0Ah
0x18002efeb  jge     short loc_18002F005
0x18002efed  cmp     eax, 20h ; ' '
0x18002eff0  jnz     short loc_18002F005
0x18002eff2  inc     esi
0x18002eff4  imul    ecx, esi, 1F4h; dwMilliseconds
0x18002effa  call    cs:__imp_Sleep
0x18002f000  jmp     loc_18002EF75
0x18002f005  test    eax, eax
0x18002f007  jle     loc_18002F128
0x18002f00d  movzx   ebx, ax
0x18002f010  or      ebx, 80070000h
0x18002f016  jmp     loc_18002F128
0x18002f01b  lea     rcx, [rsp+488h+ExistingFileName]; lpFileName
0x18002f023  call    cs:__imp_DeleteFileW
0x18002f029  mov     ecx, ebp; int
0x18002f02b  call    ?_SetUpdateEvent@@YAHH@Z; _SetUpdateEvent(int)
0x18002f030  test    eax, eax
0x18002f032  jnz     short loc_18002F03E
0x18002f034  mov     ebx, 8000FFFFh
0x18002f039  jmp     loc_18002F11C
0x18002f03e  mov     eax, cs:Data
0x18002f044  lea     r8, dword_180072FEC; unsigned __int16 *
0x18002f04b  mov     r9, cs:qword_180072D20
0x18002f052  lea     rcx, [rsp+488h+NewFileName]; unsigned __int16 *
0x18002f057  sub     r9, rax; __int64
0x18002f05a  mov     edx, 105h; unsigned __int64
0x18002f05f  call    ?GetDBName@@YA_KPEAG_KPEBG_J@Z; GetDBName(ushort *,unsigned __int64,ushort const *,__int64)
0x18002f064  lea     rcx, [rsp+488h+NewFileName]; lpFileName
0x18002f069  call    cs:__imp_GetFileAttributesW
0x18002f06f  cmp     eax, 0FFFFFFFFh
0x18002f072  jz      short loc_18002F0CE
0x18002f074  lea     rcx, [rsp+488h+NewFileName]; unsigned __int16 *
0x18002f079  call    ?_RegAllocateEntry@@YAPEAUDELVERSION@@PEBG@Z; _RegAllocateEntry(ushort const *)
0x18002f07e  mov     rbx, rax
0x18002f081  test    rax, rax
0x18002f084  jnz     short loc_18002F090
0x18002f086  mov     ebx, 8007000Eh
0x18002f08b  jmp     loc_18002F11C
0x18002f090  mov     rax, cs:?Globals@@3UGLOBALDATA@@A; GLOBALDATA Globals
0x18002f097  lea     rcx, ?Globals@@3UGLOBALDATA@@A; GLOBALDATA Globals
0x18002f09e  mov     rax, [rax]
0x18002f0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0a6  mov     rax, cs:qword_180072D38
0x18002f0ad  lea     rcx, ?Globals@@3UGLOBALDATA@@A; GLOBALDATA Globals
0x18002f0b4  mov     [rbx], rax
0x18002f0b7  mov     rax, cs:?Globals@@3UGLOBALDATA@@A; GLOBALDATA Globals
0x18002f0be  mov     cs:qword_180072D38, rbx
0x18002f0c5  mov     rax, [rax+8]
0x18002f0c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0ce  mov     rcx, rbp; __int64
0x18002f0d1  call    ?SetRegDbVersionInRegistry@@YAJ_J@Z; SetRegDbVersionInRegistry(__int64)
0x18002f0d6  mov     ebx, eax
0x18002f0d8  test    eax, eax
0x18002f0da  js      short loc_18002F11C
0x18002f0dc  mov     rcx, cs:?g_hCommitEvent@@3PEAXEA; hEvent
0x18002f0e3  call    cs:__imp_SetEvent
0x18002f0e9  mov     rcx, cs:?g_hTxInProgressEvent@@3PEAXEA; hEvent
0x18002f0f0  call    cs:__imp_SetEvent
0x18002f0f6  lea     rcx, CriticalSection; lpCriticalSection
0x18002f0fd  call    cs:__imp_EnterCriticalSection
0x18002f103  lea     rcx, qword_180072DA0; struct REGAPI_STATE *
0x18002f10a  call    ?_RegReleaseReference@@YAXPEAUREGAPI_STATE@@@Z; _RegReleaseReference(REGAPI_STATE *)
0x18002f10f  lea     rcx, CriticalSection; lpCriticalSection
0x18002f116  call    cs:__imp_LeaveCriticalSection
0x18002f11c  test    rdi, rdi
0x18002f11f  jz      short loc_18002F128
0x18002f121  mov     qword ptr [rdi], 0
0x18002f128  mov     eax, ebx
0x18002f12a  mov     rcx, [rsp+488h+var_28]
0x18002f132  xor     rcx, rsp; StackCookie
0x18002f135  call    __security_check_cookie
0x18002f13a  lea     r11, [rsp+488h+var_18]
0x18002f142  mov     rbx, [r11+28h]
0x18002f146  mov     rbp, [r11+30h]
0x18002f14a  mov     rsp, r11
0x18002f14d  pop     r14
0x18002f14f  pop     rdi
0x18002f150  pop     rsi
0x18002f151  retn
```
