# CDllHost::MTAInitializeActivators(void)

- ea: `0x18013dcac`
- end: `0x18013de7f`
- name: `?MTAInitializeActivators@CDllHost@@AEAAJXZ`
- size: `467`
- prototype: `HRESULT __fastcall(CDllHost *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001186c`

## callees

- `0x18000be10`
- `0x1800188a0`
- `0x18008ce34`
- `0x180126b1c`
- `0x18013dcac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013dd59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013de6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013dd59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013de6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013ddb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013ddb7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18013dd82`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18013dd82`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013dd27`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013dd27`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18013dd4b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18013dd4b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18013dd96`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18013dd96`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18013dd75`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18013dd75`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18013dd8d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18013dd8d`

## pseudocode

```c
__int64 __fastcall CDllHost::MTAInitializeActivators(CDllHost *this)
{
  char v1; // r14
  tagSOleTlsData *ReservedForOle; // rbx
  int v4; // ebp
  unsigned int dwFlags; // eax
  HANDLE EventW; // rax
  _TP_WORK *ThreadpoolWork; // rbx
  signed int v8; // eax
  int hr; // edi
  void *hEvent; // rcx
  signed int LastError; // eax
  COleTls tls; // [rsp+40h] [rbp+8h] BYREF

  v1 = 0;
  ReservedForOle = (tagSOleTlsData *)NtCurrentTeb()->ReservedForOle;
  tls._pData = ReservedForOle;
  if ( !ReservedForOle )
  {
    hr = COleTls::TLSAllocData(&tls);
    if ( hr < 0 )
      goto LABEL_28;
    ReservedForOle = tls._pData;
  }
  v4 = 1;
  if ( (this->_dwType & 0x40) == 0 )
  {
    hr = IncrementMTAUsageHelper(0, 0);
    if ( hr < 0 )
      goto LABEL_28;
    this->_dwType |= 0x40u;
    _InterlockedAdd((volatile signed __int32 *)&gcActivationHostThreadInits, 1u);
    g_fMTAHostUsageFlags |= 1u;
    v1 = 1;
  }
  if ( ReservedForOle )
  {
    dwFlags = ReservedForOle->dwFlags;
    if ( (dwFlags & 0x800) != 0 )
    {
      v4 = 3;
      goto LABEL_7;
    }
    if ( (dwFlags & 0x80u) != 0 )
    {
      if ( (dwFlags & 0x400000) == 0 )
        v4 = (dwFlags >> 28) & 4;
      goto LABEL_7;
    }
  }
  v4 = 2;
LABEL_7:
  this->_dwType |= 0x20u;
  if ( v4 == 2 )
  {
    CDllHost::MTAInitializeActivatorsInMTAImpl(this);
  }
  else
  {
    EventW = CreateEventW(0, 0, 0, 0);
    this->_hEvent = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      hr = LastError;
      if ( LastError > 0 )
        hr = (unsigned __int16)LastError | 0x80070000;
      if ( hr < 0 )
        goto LABEL_28;
    }
    ThreadpoolWork = CreateThreadpoolWork(CDllHost::MTAInitializeActivatorsInMTA, 0, 0);
    if ( !ThreadpoolWork )
    {
      v8 = GetLastError();
      hr = v8;
      if ( v8 > 0 )
        hr = (unsigned __int16)v8 | 0x80070000;
      if ( hr < 0 )
        goto LABEL_28;
    }
    SubmitThreadpoolWork(ThreadpoolWork);
    WaitForSingleObject(this->_hEvent, 0xFFFFFFFF);
    WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 0);
    CloseThreadpoolWork(ThreadpoolWork);
  }
  hr = this->_hr;
  if ( hr >= 0 )
  {
    g_fMTAHostUsageFlags |= 2u;
    goto LABEL_16;
  }
LABEL_28:
  this->_dwType &= ~0x20u;
  if ( v1 )
    CDllHost::MTAUninitializeApartmentOnly(this);
LABEL_16:
  hEvent = this->_hEvent;
  if ( hEvent )
  {
    CloseHandle(hEvent);
    this->_hEvent = 0;
  }
  return (unsigned int)hr;
}

```

## disassembly

```asm
0x18013dcac  mov     [rsp+arg_8], rbx
0x18013dcb1  mov     [rsp+arg_10], rbp
0x18013dcb6  push    rsi
0x18013dcb7  push    rdi
0x18013dcb8  push    r14
0x18013dcba  sub     rsp, 20h
0x18013dcbe  mov     rbx, gs:30h
0x18013dcc7  xor     r14b, r14b
0x18013dcca  mov     rsi, this
0x18013dccd  mov     rbx, [rbx+1758h]
0x18013dcd4  mov     [rsp+38h+tls._pData], rbx
0x18013dcd9  test    rbx, rbx
0x18013dcdc  jz      loc_18013DE0C
0x18013dce2  test    byte ptr [rsi+30h], 40h
0x18013dce6  mov     ebp, 1
0x18013dceb  jz      loc_18013DDDA
0x18013dcf1  test    rbx, rbx
0x18013dcf4  jz      short loc_18013DD0B
0x18013dcf6  mov     eax, [rbx+14h]
0x18013dcf9  bt      eax, 0Bh
0x18013dcfd  jb      loc_18013DE02
0x18013dd03  test    al, al
0x18013dd05  js      loc_18013DE26
0x18013dd0b  mov     ebp, 2
0x18013dd10  or      dword ptr [rsi+30h], 20h
0x18013dd14  cmp     ebp, 2
0x18013dd17  jz      loc_18013DE3D
0x18013dd1d  xor     r9d, r9d; lpName
0x18013dd20  xor     r8d, r8d; bInitialState
0x18013dd23  xor     edx, edx; bManualReset
0x18013dd25  xor     ecx, ecx; lpEventAttributes
0x18013dd27  call    cs:__imp_CreateEventW
0x18013dd2d  mov     [rsi+48h], rax
0x18013dd31  mov     ebp, 80070000h
0x18013dd36  test    rax, rax
0x18013dd39  jz      loc_18013DE6C
0x18013dd3f  xor     r8d, r8d; pcbe
0x18013dd42  lea     this, ?MTAInitializeActivatorsInMTA@CDllHost@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18013dd49  xor     edx, edx; pv
0x18013dd4b  call    cs:__imp_CreateThreadpoolWork
0x18013dd51  mov     rbx, rax
0x18013dd54  test    rax, rax
0x18013dd57  jnz     short loc_18013DD72
0x18013dd59  call    cs:__imp_GetLastError
0x18013dd5f  mov     edi, eax
0x18013dd61  test    eax, eax
0x18013dd63  jle     short loc_18013DD6A
0x18013dd65  movzx   edi, ax
0x18013dd68  or      edi, ebp
0x18013dd6a  test    edi, edi
0x18013dd6c  js      loc_18013DE52
0x18013dd72  mov     this, rbx; pwk
0x18013dd75  call    cs:__imp_SubmitThreadpoolWork
0x18013dd7b  mov     this, [rsi+48h]; hHandle
0x18013dd7f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18013dd82  call    cs:__imp_WaitForSingleObject
0x18013dd88  xor     edx, edx; fCancelPendingCallbacks
0x18013dd8a  mov     this, rbx; pwk
0x18013dd8d  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18013dd93  mov     this, rbx; pwk
0x18013dd96  call    cs:__imp_CloseThreadpoolWork
0x18013dd9c  mov     edi, [rsi+58h]
0x18013dd9f  test    edi, edi
0x18013dda1  js      loc_18013DE52
0x18013dda7  or      cs:?g_fMTAHostUsageFlags@@3W4MTA_HOST_USAGE_FLAGS@@A, 2; MTA_HOST_USAGE_FLAGS g_fMTAHostUsageFlags
0x18013ddae  mov     this, [rsi+48h]; hObject
0x18013ddb2  test    this, this
0x18013ddb5  jz      short loc_18013DDC5
0x18013ddb7  call    cs:__imp_CloseHandle
0x18013ddbd  mov     qword ptr [rsi+48h], 0
0x18013ddc5  mov     rbx, [rsp+38h+arg_8]
0x18013ddca  mov     eax, edi
0x18013ddcc  mov     rbp, [rsp+38h+arg_10]
0x18013ddd1  add     rsp, 20h
0x18013ddd5  pop     r14
0x18013ddd7  pop     rdi
0x18013ddd8  pop     rsi
0x18013ddd9  retn
0x18013ddda  xor     edx, edx; ppMtaUsageIncrementor
0x18013dddc  xor     ecx, ecx; bFailIfNotInitialized
0x18013ddde  call    ?IncrementMTAUsageHelper@@YAJ_NPEAPEAU_MTA_USAGE_INCREMENTOR@@@Z; IncrementMTAUsageHelper(bool,_MTA_USAGE_INCREMENTOR * *)
0x18013dde3  mov     edi, eax
0x18013dde5  test    eax, eax
0x18013dde7  js      short loc_18013DE52
0x18013dde9  or      dword ptr [rsi+30h], 40h
0x18013dded  lock add cs:?gcActivationHostThreadInits@@3KA, ebp; ulong gcActivationHostThreadInits
0x18013ddf4  or      cs:?g_fMTAHostUsageFlags@@3W4MTA_HOST_USAGE_FLAGS@@A, ebp; MTA_HOST_USAGE_FLAGS g_fMTAHostUsageFlags
0x18013ddfa  mov     r14b, bpl
0x18013ddfd  jmp     loc_18013DCF1
0x18013de02  mov     ebp, 3
0x18013de07  jmp     loc_18013DD10
0x18013de0c  lea     this, [rsp+38h+tls]; this
0x18013de11  call    ?TLSAllocData@COleTls@@QEAAJXZ; COleTls::TLSAllocData(void)
0x18013de16  mov     edi, eax
0x18013de18  test    eax, eax
0x18013de1a  js      short loc_18013DE52
0x18013de1c  mov     rbx, [rsp+38h+tls._pData]
0x18013de21  jmp     loc_18013DCE2
0x18013de26  bt      eax, 16h
0x18013de2a  jb      loc_18013DD10
0x18013de30  mov     ebp, eax
0x18013de32  shr     ebp, 1Ch
0x18013de35  and     ebp, 4
0x18013de38  jmp     loc_18013DD10
0x18013de3d  mov     this, rsi; this
0x18013de40  call    ?MTAInitializeActivatorsInMTAImpl@CDllHost@@AEAAXXZ; CDllHost::MTAInitializeActivatorsInMTAImpl(void)
0x18013de45  jmp     loc_18013DD9C
0x18013de4a  test    edi, edi
0x18013de4c  jns     loc_18013DD3F
0x18013de52  and     dword ptr [rsi+30h], 0FFFFFFDFh
0x18013de56  test    r14b, r14b
0x18013de59  jz      loc_18013DDAE
0x18013de5f  mov     this, rsi; this
0x18013de62  call    ?MTAUninitializeApartmentOnly@CDllHost@@AEAAXXZ; CDllHost::MTAUninitializeApartmentOnly(void)
0x18013de67  jmp     loc_18013DDAE
0x18013de6c  call    cs:__imp_GetLastError
0x18013de72  mov     edi, eax
0x18013de74  test    eax, eax
0x18013de76  jle     short loc_18013DE4A
0x18013de78  movzx   edi, ax
0x18013de7b  or      edi, ebp
0x18013de7d  jmp     short loc_18013DE4A
```
