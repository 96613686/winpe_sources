# DllMain(x,x,x)

- ea: `0x1000f260`
- end: `0x1000f48f`
- name: `_DllMain@12`
- size: `559`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1004d142`

## callees

- `0x1000ba90`
- `0x1000be60`
- `0x1000f260`
- `0x1001c530`
- `0x1001c570`
- `0x1001c6d0`
- `0x1004ce5d`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1000f3d8`
- `KERNEL32!LeaveCriticalSection` at `0x1000f475`
- `KERNEL32!LeaveCriticalSection` at `0x1000f3d8`
- `KERNEL32!LeaveCriticalSection` at `0x1000f475`
- `KERNEL32!EnterCriticalSection` at `0x1000f2ca`
- `KERNEL32!EnterCriticalSection` at `0x1000f40d`
- `KERNEL32!EnterCriticalSection` at `0x1000f2ca`
- `KERNEL32!EnterCriticalSection` at `0x1000f40d`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000f2a4`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000f41e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000f2a4`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000f41e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1000f37e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1000f37e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1000f332`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1000f332`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1000f35b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1000f35b`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1000f2ea`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1000f2ea`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  HRESULT Malloc; // eax
  int v5; // esi
  HKEY v6; // eax
  CExtBuffer *v7; // eax
  CExtBuffer *v8; // [esp+0h] [ebp-20h]
  unsigned int v9; // [esp+4h] [ebp-1Ch]
  LPMALLOC ppMalloc; // [esp+Ch] [ebp-14h] BYREF
  HKEY phkResult; // [esp+10h] [ebp-10h] BYREF
  int v12; // [esp+1Ch] [ebp-4h]

  if ( !fdwReason )
  {
    EnterCriticalSection(&g_CriticalSection);
    v12 = 1;
    SetErrorInfo(0, 0);
    if ( g_cAttachedProcesses <= 1 )
    {
      if ( Sys )
      {
        (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)Sys + 8))(*(_DWORD *)(*(_DWORD *)Sys + 8), Sys);
        Sys = 0;
      }
      if ( g_pSessionList )
        CExtBuffer::`scalar deleting destructor'(g_pSessionList, (unsigned int)g_pSessionList);
    }
    if ( g_cAttachedProcesses > 0 )
      _InterlockedDecrement(&g_cAttachedProcesses);
    goto LABEL_29;
  }
  if ( fdwReason != 1 )
  {
    if ( fdwReason == 3 )
    {
      SetErrorInfo(0, 0);
      return 0;
    }
    return 0;
  }
  EnterCriticalSection(&g_CriticalSection);
  v12 = 0;
  if ( g_cAttachedProcesses )
  {
LABEL_20:
    _InterlockedIncrement(&g_cAttachedProcesses);
    LeaveCriticalSection(&g_CriticalSection);
    return 1;
  }
  Malloc = CoGetMalloc(1u, &ppMalloc);
  if ( !ppMalloc || Malloc < 0 )
    goto LABEL_29;
  v5 = 1;
  g_hinstance = hinstDLL;
  Sys = (int)ppMalloc;
  phkResult = HKEY_CURRENT_USER;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE", 0, 0x20019u, &phkResult) )
    goto LABEL_13;
  v6 = phkResult;
  if ( phkResult == HKEY_CURRENT_USER )
  {
    if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SOFTWARE", 0, 0x20019u, &phkResult) )
    {
      v6 = phkResult;
      if ( phkResult == HKEY_CURRENT_USER )
        goto LABEL_16;
      v5 = 0;
LABEL_14:
      if ( v6 == HKEY_CURRENT_USER )
        goto LABEL_16;
      goto LABEL_15;
    }
LABEL_13:
    v6 = phkResult;
    goto LABEL_14;
  }
LABEL_15:
  RegCloseKey(v6);
LABEL_16:
  g_fUnicodeRegistry = v5;
  if ( g_pSessionList )
    goto LABEL_20;
  v7 = (CExtBuffer *)operator new(0x28u);
  if ( v7 )
  {
    g_pSessionList = CExtBuffer::CExtBuffer(v7);
    if ( g_pSessionList && CExtBuffer::FInit(v8, v9) >= 0 )
      goto LABEL_20;
  }
  else
  {
    g_pSessionList = 0;
  }
LABEL_29:
  LeaveCriticalSection(&g_CriticalSection);
  return 0;
}

```

## disassembly

```asm
0x1000f260  mov     edi, edi
0x1000f262  push    ebp
0x1000f263  mov     ebp, esp
0x1000f265  push    0FFFFFFFFh
0x1000f267  push    offset _DllMain@12_SEH
0x1000f26c  mov     eax, large fs:0
0x1000f272  push    eax
0x1000f273  sub     esp, 0Ch
0x1000f276  push    esi; unsigned int
0x1000f277  mov     eax, ___security_cookie
0x1000f27c  xor     eax, ebp
0x1000f27e  push    eax; this
0x1000f27f  lea     eax, [ebp+var_C]
0x1000f282  mov     large fs:0, eax
0x1000f288  mov     ecx, [ebp+fdwReason]
0x1000f28b  sub     ecx, 0
0x1000f28e  jz      loc_1000F401
0x1000f294  sub     ecx, 1
0x1000f297  jz      short loc_1000F2BE
0x1000f299  sub     ecx, 2
0x1000f29c  jnz     loc_1000F47B
0x1000f2a2  push    ecx; perrinfo
0x1000f2a3  push    ecx; dwReserved
0x1000f2a4  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1000f2aa  xor     eax, eax
0x1000f2ac  mov     ecx, [ebp+var_C]
0x1000f2af  mov     large fs:0, ecx
0x1000f2b6  pop     ecx
0x1000f2b7  pop     esi
0x1000f2b8  mov     esp, ebp
0x1000f2ba  pop     ebp
0x1000f2bb  retn    0Ch
0x1000f2be  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000f2c3  mov     [ebp+var_18], offset ?g_CriticalSection@@3VCriticalSection@@A; CriticalSection g_CriticalSection
0x1000f2ca  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000f2d0  mov     [ebp+var_4], 0
0x1000f2d7  cmp     ?g_cAttachedProcesses@@3JA, 0; long g_cAttachedProcesses
0x1000f2de  jnz     loc_1000F3CC
0x1000f2e4  lea     eax, [ebp+ppMalloc]
0x1000f2e7  push    eax; ppMalloc
0x1000f2e8  push    1; dwMemContext
0x1000f2ea  call    ds:__imp__CoGetMalloc@8; CoGetMalloc(x,x)
0x1000f2f0  mov     ecx, [ebp+ppMalloc]
0x1000f2f3  test    ecx, ecx
0x1000f2f5  jz      loc_1000F470
0x1000f2fb  test    eax, eax
0x1000f2fd  js      loc_1000F470
0x1000f303  mov     eax, [ebp+hinstDLL]
0x1000f306  mov     esi, 1
0x1000f30b  mov     ?g_hinstance@@3PAUHINSTANCE__@@A, eax; HINSTANCE__ * g_hinstance
0x1000f310  lea     eax, [ebp+phkResult]
0x1000f313  push    eax; phkResult
0x1000f314  push    20019h; samDesired
0x1000f319  push    0; ulOptions
0x1000f31b  push    offset SubKey; "SOFTWARE"
0x1000f320  push    80000002h; hKey
0x1000f325  mov     ?Sys@@3VSystem@@A, ecx; System Sys
0x1000f32b  mov     [ebp+phkResult], 80000001h
0x1000f332  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x1000f338  test    eax, eax
0x1000f33a  jnz     short loc_1000F373
0x1000f33c  mov     eax, [ebp+phkResult]
0x1000f33f  cmp     eax, 80000001h
0x1000f344  jnz     short loc_1000F37D
0x1000f346  lea     eax, [ebp+phkResult]
0x1000f349  push    eax; phkResult
0x1000f34a  push    20019h; samDesired
0x1000f34f  push    0; ulOptions
0x1000f351  push    offset aSoftware_0; "SOFTWARE"
0x1000f356  push    80000002h; hKey
0x1000f35b  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x1000f361  test    eax, eax
0x1000f363  jnz     short loc_1000F373
0x1000f365  mov     eax, [ebp+phkResult]
0x1000f368  cmp     eax, 80000001h
0x1000f36d  jz      short loc_1000F384
0x1000f36f  xor     esi, esi
0x1000f371  jmp     short loc_1000F376
0x1000f373  mov     eax, [ebp+phkResult]
0x1000f376  cmp     eax, 80000001h
0x1000f37b  jz      short loc_1000F384
0x1000f37d  push    eax; hKey
0x1000f37e  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1000f384  cmp     ?g_pSessionList@@3PAVCExtBuffer@@A, 0; CExtBuffer * g_pSessionList
0x1000f38b  mov     ?g_fUnicodeRegistry@@3HA, esi; int g_fUnicodeRegistry
0x1000f391  jnz     short loc_1000F3CC
0x1000f393  push    28h ; '('; Size
0x1000f395  call    ??2@YAPAXI@Z; operator new(uint)
0x1000f39a  add     esp, 4
0x1000f39d  mov     [ebp+var_18], eax
0x1000f3a0  test    eax, eax
0x1000f3a2  jz      short loc_1000F3F5
0x1000f3a4  mov     ecx, eax; this
0x1000f3a6  call    ??0CExtBuffer@@QAE@XZ; CExtBuffer::CExtBuffer(void)
0x1000f3ab  mov     ?g_pSessionList@@3PAVCExtBuffer@@A, eax; CExtBuffer * g_pSessionList
0x1000f3b0  test    eax, eax
0x1000f3b2  jz      loc_1000F470
0x1000f3b8  mov     edx, 4
0x1000f3bd  mov     ecx, eax
0x1000f3bf  call    ?FInit@CExtBuffer@@QAGJK@Z; CExtBuffer::FInit(ulong)
0x1000f3c4  test    eax, eax
0x1000f3c6  js      loc_1000F470
0x1000f3cc  lock inc ?g_cAttachedProcesses@@3JA; long g_cAttachedProcesses
0x1000f3d3  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000f3d8  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000f3de  mov     eax, 1
0x1000f3e3  mov     ecx, [ebp+var_C]
0x1000f3e6  mov     large fs:0, ecx
0x1000f3ed  pop     ecx
0x1000f3ee  pop     esi
0x1000f3ef  mov     esp, ebp
0x1000f3f1  pop     ebp
0x1000f3f2  retn    0Ch
0x1000f3f5  mov     ?g_pSessionList@@3PAVCExtBuffer@@A, 0; CExtBuffer * g_pSessionList
0x1000f3ff  jmp     short loc_1000F470
0x1000f401  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000f406  mov     [ebp+var_18], offset ?g_CriticalSection@@3VCriticalSection@@A; CriticalSection g_CriticalSection
0x1000f40d  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000f413  push    0; perrinfo
0x1000f415  push    0; dwReserved
0x1000f417  mov     [ebp+var_4], 1
0x1000f41e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1000f424  cmp     ?g_cAttachedProcesses@@3JA, 1; long g_cAttachedProcesses
0x1000f42b  jg      short loc_1000F460
0x1000f42d  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x1000f432  test    eax, eax
0x1000f434  jz      short loc_1000F450
0x1000f436  mov     ecx, [eax]
0x1000f438  push    eax
0x1000f439  mov     esi, [ecx+8]
0x1000f43c  mov     ecx, esi
0x1000f43e  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000f444  call    esi
0x1000f446  mov     ?Sys@@3VSystem@@A, 0; System Sys
0x1000f450  mov     ecx, ?g_pSessionList@@3PAVCExtBuffer@@A; this
0x1000f456  test    ecx, ecx
0x1000f458  jz      short loc_1000F460
0x1000f45a  push    ecx; unsigned int
0x1000f45b  call    ??_GCExtBuffer@@QAEPAXI@Z; CExtBuffer::`scalar deleting destructor'(uint)
0x1000f460  cmp     ?g_cAttachedProcesses@@3JA, 0; long g_cAttachedProcesses
0x1000f467  jle     short loc_1000F470
0x1000f469  lock dec ?g_cAttachedProcesses@@3JA; long g_cAttachedProcesses
0x1000f470  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000f475  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000f47b  xor     eax, eax
0x1000f47d  mov     ecx, [ebp+var_C]
0x1000f480  mov     large fs:0, ecx
0x1000f487  pop     ecx
0x1000f488  pop     esi
0x1000f489  mov     esp, ebp
0x1000f48b  pop     ebp
0x1000f48c  retn    0Ch
0x1004ded0  lea     ecx, [ebp+var_18]; this
0x1004ded3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004ded8  lea     ecx, [ebp+var_18]; this
0x1004dedb  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dee5  nop
0x1004dee6  nop
0x1004dee7  mov     edx, [esp-4+fdwReason]
0x1004deeb  lea     eax, [edx+0Ch]
0x1004deee  mov     ecx, [edx-14h]
0x1004def1  xor     ecx, eax; StackCookie
0x1004def3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004def8  mov     eax, offset stru_1004F490
0x1004defd  jmp     ___CxxFrameHandler3
```
