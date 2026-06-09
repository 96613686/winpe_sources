# ConnectCallback(tagComCallData *)

- ea: `0x180001950`
- end: `0x180001d1c`
- name: `?ConnectCallback@@YAJPEAUtagComCallData@@@Z`
- size: `972`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001014`
- `0x180001950`
- `0x180001eb4`
- `0x18000284c`
- `0x1800028dc`
- `0x180002964`
- `0x180002a00`
- `0x180002c8c`
- `0x180002f84`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001a3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001a3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001a2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001a2a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800019f1`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800019f1`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180001c4b`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180001c4b`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180001ac2`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180001ac2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001b29`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001b96`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001b29`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001b96`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180001ae7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180001ae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001af1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001af1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bc1`

## string_xrefs

- `0x180001b22`: `FdphostSetComContext`
- `0x180001b8f`: `FdphostSetSharedService`

## pseudocode

```c
__int64 __fastcall ConnectCallback(struct tagComCallData *a1)
{
  unsigned int v1; // ebp
  int v2; // r14d
  void *v3; // rbx
  void *v4; // rdx
  CFdphostSharedService *v5; // rcx
  int ClassObject; // ebx
  int v7; // edx
  int v8; // r8d
  unsigned int v9; // r9d
  int v10; // edi
  __int64 v11; // rsi
  wchar_t *v12; // rax
  signed int v13; // eax
  FARPROC ProcAddress; // rax
  __int64 v15; // rbx
  FARPROC v16; // rax
  __int64 v17; // rbx
  signed int LastError; // eax
  const struct _EVENT_DESCRIPTOR *v19; // rcx
  LPVOID *ppv; // [rsp+20h] [rbp-38h]
  LPUNKNOWN pUnk; // [rsp+68h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids);
  v1 = 0;
  v2 = 0;
  pUnk = 0;
  v3 = operator new(0x20u);
  if ( v3 )
  {
    *((_DWORD *)v3 + 3) = 0;
    *(_QWORD *)v3 = &CFdphostSharedService::`vftable';
    *((_DWORD *)v3 + 2) = 1;
    *((_DWORD *)v3 + 6) = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 10);
    InitializeSRWLock((PSRWLOCK)v3 + 2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 11);
    g_pSharedService = (struct CFdphostSharedService *)v3;
    EnterCriticalSection(&g_hServiceStopEventLock);
    ClassObject = CFdphostSharedService::Initialize(v5, v4);
    LeaveCriticalSection(&g_hServiceStopEventLock);
    v10 = 0;
    if ( ClassObject >= 0 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            if ( v10 >= 2 )
              goto LABEL_45;
            v11 = 7LL * v10;
            v12 = (&off_180007010)[v11];
            if ( v12 )
              break;
            ++v10;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, v9, (__int64)v12);
          ClassObject = CoGetClassObject(
                          (const IID *const)((char *)&g_FdphostProviders + v11 * 8),
                          1u,
                          0,
                          &IID_IClassFactory,
                          (LPVOID *)&pUnk);
          if ( !ClassObject )
            break;
LABEL_39:
          v19 = (const struct _EVENT_DESCRIPTOR *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_sSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, v9, (__int64)(&off_180007010)[v11], ClassObject);
          LogError(v19, (const unsigned __int16 *)(&g_arysProviderDesc)[v10], ClassObject, v9, (const char *)ppv);
          v1 = ClassObject;
          ClassObject = 0;
          ++v10;
        }
        if ( GetModuleHandleExW(0, (&off_180007010)[v11], (HMODULE *)((char *)&g_FdphostProviders + v11 * 8 + 24)) )
        {
          ProcAddress = GetProcAddress((HMODULE)qword_180007018[v11], "FdphostSetComContext");
          v15 = (__int64)ProcAddress;
          if ( ProcAddress )
          {
            ((void (__fastcall *)(LPVOID))ProcAddress)(g_pIContextCallback);
            qword_180007018[v11 + 1] = v15;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids);
          }
          v16 = GetProcAddress((HMODULE)qword_180007018[v11], "FdphostSetSharedService");
          v17 = (__int64)v16;
          if ( v16 )
          {
            ((void (__fastcall *)(struct CFdphostSharedService *))v16)(g_pSharedService);
            qword_180007028[v11 + 1] = v17;
LABEL_35:
            qword_180007028[v11] = (__int64)GetProcAddress((HMODULE)qword_180007018[v11], "FdphostSessionChange");
LABEL_36:
            ClassObject = CoRegisterClassObject(
                            (const IID *const)((char *)&g_FdphostProviders + v11 * 8),
                            pUnk,
                            4u,
                            1u,
                            (LPDWORD)(0x180000000LL + 4LL * v10 + 30400));
            goto LABEL_37;
          }
          LastError = GetLastError();
          ClassObject = LastError;
          if ( LastError > 0 )
            ClassObject = (unsigned __int16)LastError | 0x80070000;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            LODWORD(ppv) = ClassObject;
            WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13);
          }
          if ( !ClassObject )
            goto LABEL_35;
        }
        else
        {
          v13 = GetLastError();
          ClassObject = v13;
          if ( v13 > 0 )
            ClassObject = (unsigned __int16)v13 | 0x80070000;
          if ( !ClassObject )
            goto LABEL_36;
        }
LABEL_37:
        ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
        pUnk = 0;
        if ( ClassObject )
          goto LABEL_39;
        ++v2;
        ++v10;
      }
    }
  }
  else
  {
    g_pSharedService = 0;
    ClassObject = -2147024882;
  }
LABEL_45:
  if ( v2 )
    return (unsigned int)ClassObject;
  return v1;
}

```

## disassembly

```asm
0x180001950  mov     [rsp+arg_0], rbx
0x180001955  mov     [rsp+arg_10], rbp
0x18000195a  push    rsi
0x18000195b  push    rdi
0x18000195c  push    r12
0x18000195e  push    r14
0x180001960  push    r15
0x180001962  sub     rsp, 30h
0x180001966  mov     rcx, cs:WPP_GLOBAL_Control
0x18000196d  lea     r15, WPP_GLOBAL_Control
0x180001974  mov     edi, 0Ah
0x180001979  cmp     rcx, r15
0x18000197c  jz      short loc_180001996
0x18000197e  cmp     byte ptr [rcx+19h], 4
0x180001982  jb      short loc_180001996
0x180001984  mov     rcx, [rcx+10h]
0x180001988  lea     r8, WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids
0x18000198f  mov     edx, edi
0x180001991  call    WPP_SF_s
0x180001996  xor     ebp, ebp
0x180001998  xor     r14d, r14d
0x18000199b  mov     [rsp+58h+pUnk], rbp
0x1800019a0  lea     ecx, [rbp+20h]; Size
0x1800019a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800019a8  mov     rbx, rax
0x1800019ab  test    rax, rax
0x1800019ae  jz      loc_180001CF1
0x1800019b4  lea     rax, ??_7CFdphostSharedService@@6B@; const CFdphostSharedService::`vftable'
0x1800019bb  mov     [rbx+0Ch], ebp
0x1800019be  mov     [rbx], rax
0x1800019c1  mov     dword ptr [rbx+8], 1
0x1800019c8  mov     [rbx+18h], ebp
0x1800019cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019d2  cmp     rcx, r15
0x1800019d5  jz      short loc_1800019ED
0x1800019d7  cmp     byte ptr [rcx+19h], 4
0x1800019db  jb      short loc_1800019ED
0x1800019dd  mov     rcx, [rcx+10h]
0x1800019e1  mov     edx, edi
0x1800019e3  mov     [rsp+58h+ppv], rbx
0x1800019e8  call    WPP_SF_sq
0x1800019ed  lea     rcx, [rbx+10h]; SRWLock
0x1800019f1  call    cs:__imp_InitializeSRWLock
0x1800019f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019fe  cmp     rcx, r15
0x180001a01  jz      short loc_180001A1C
0x180001a03  cmp     byte ptr [rcx+19h], 4
0x180001a07  jb      short loc_180001A1C
0x180001a09  mov     rcx, [rcx+10h]
0x180001a0d  mov     edx, 0Bh
0x180001a12  mov     [rsp+58h+ppv], rbx
0x180001a17  call    WPP_SF_sq
0x180001a1c  lea     rcx, ?g_hServiceStopEventLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001a23  mov     cs:?g_pSharedService@@3PEAVCFdphostSharedService@@EA, rbx; CFdphostSharedService * g_pSharedService
0x180001a2a  call    cs:__imp_EnterCriticalSection
0x180001a30  call    ?Initialize@CFdphostSharedService@@QEAAJPEAX@Z; CFdphostSharedService::Initialize(void *)
0x180001a35  lea     rcx, ?g_hServiceStopEventLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001a3c  mov     ebx, eax
0x180001a3e  call    cs:__imp_LeaveCriticalSection
0x180001a44  xor     edi, edi
0x180001a46  test    ebx, ebx
0x180001a48  js      loc_180001CFD
0x180001a4e  lea     rax, cs:180000000h
0x180001a55  cmp     edi, 2
0x180001a58  jge     loc_180001CFD
0x180001a5e  movsxd  r12, edi
0x180001a61  imul    rsi, r12, 38h ; '8'
0x180001a65  mov     rax, [rsi+rax+7010h]
0x180001a6d  test    rax, rax
0x180001a70  jz      loc_180001CDE
0x180001a76  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a7d  cmp     rcx, r15
0x180001a80  jz      short loc_180001A96
0x180001a82  cmp     byte ptr [rcx+19h], 4
0x180001a86  jb      short loc_180001A96
0x180001a88  mov     rcx, [rcx+10h]
0x180001a8c  mov     [rsp+58h+ppv], rax
0x180001a91  call    WPP_SF_sS
0x180001a96  lea     rax, cs:180000000h
0x180001a9d  xor     r8d, r8d; pvReserved
0x180001aa0  lea     r15, rva ?g_FdphostProviders@@3PAU_FDPHOST_PROVIDER_INFO@@A[rax]; _FDPHOST_PROVIDER_INFO near * g_FdphostProviders ...
0x180001aa7  lea     rax, [rsp+58h+pUnk]
0x180001aac  add     r15, rsi
0x180001aaf  mov     rcx, r15; rclsid
0x180001ab2  mov     [rsp+58h+ppv], rax; ppv
0x180001ab7  lea     r9, IID_IClassFactory; riid
0x180001abe  lea     edx, [r8+1]; dwClsContext
0x180001ac2  call    cs:__imp_CoGetClassObject
0x180001ac8  mov     ebx, eax
0x180001aca  test    eax, eax
0x180001acc  jnz     loc_180001C82
0x180001ad2  lea     rbx, cs:180000000h
0x180001ad9  xor     ecx, ecx; dwFlags
0x180001adb  mov     rdx, [rsi+rbx+7010h]; lpModuleName
0x180001ae3  lea     r8, [r15+18h]; phModule
0x180001ae7  call    cs:__imp_GetModuleHandleExW
0x180001aed  test    eax, eax
0x180001aef  jnz     short loc_180001B1A
0x180001af1  call    cs:__imp_GetLastError
0x180001af7  mov     ebx, eax
0x180001af9  test    eax, eax
0x180001afb  jle     short loc_180001B06
0x180001afd  movzx   ebx, ax
0x180001b00  or      ebx, 80070000h
0x180001b06  test    ebx, ebx
0x180001b08  jnz     loc_180001C53
0x180001b0e  lea     rbx, cs:180000000h
0x180001b15  jmp     loc_180001C29
0x180001b1a  mov     rcx, [rsi+rbx+7018h]; hModule
0x180001b22  lea     rdx, ProcName; "FdphostSetComContext"
0x180001b29  call    cs:__imp_GetProcAddress
0x180001b2f  mov     rbx, rax
0x180001b32  test    rax, rax
0x180001b35  jz      short loc_180001B80
0x180001b37  mov     rcx, cs:?g_pIContextCallback@@3PEAUIContextCallback@@EA; IContextCallback * g_pIContextCallback
0x180001b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b43  lea     rax, cs:180000000h
0x180001b4a  mov     [rsi+rax+7020h], rbx
0x180001b52  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b59  lea     rax, WPP_GLOBAL_Control
0x180001b60  cmp     rcx, rax
0x180001b63  jz      short loc_180001B80
0x180001b65  cmp     byte ptr [rcx+19h], 4
0x180001b69  jb      short loc_180001B80
0x180001b6b  mov     rcx, [rcx+10h]
0x180001b6f  lea     r8, WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids
0x180001b76  mov     edx, 0Ch
0x180001b7b  call    WPP_SF_s
0x180001b80  lea     rcx, cs:180000000h
0x180001b87  mov     rcx, [rsi+rcx+7018h]; hModule
0x180001b8f  lea     rdx, aFdphostsetshar; "FdphostSetSharedService"
0x180001b96  call    cs:__imp_GetProcAddress
0x180001b9c  mov     rbx, rax
0x180001b9f  test    rax, rax
0x180001ba2  jz      short loc_180001BC1
0x180001ba4  mov     rcx, cs:?g_pSharedService@@3PEAVCFdphostSharedService@@EA; CFdphostSharedService * g_pSharedService
0x180001bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bb0  lea     rax, cs:180000000h
0x180001bb7  mov     [rsi+rax+7030h], rbx
0x180001bbf  jmp     short loc_180001C05
0x180001bc1  call    cs:__imp_GetLastError
0x180001bc7  mov     ebx, eax
0x180001bc9  test    eax, eax
0x180001bcb  jle     short loc_180001BD6
0x180001bcd  movzx   ebx, ax
0x180001bd0  or      ebx, 80070000h
0x180001bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bdd  lea     rax, WPP_GLOBAL_Control
0x180001be4  cmp     rcx, rax
0x180001be7  jz      short loc_180001C01
0x180001be9  cmp     byte ptr [rcx+19h], 2
0x180001bed  jb      short loc_180001C01
0x180001bef  mov     rcx, [rcx+10h]
0x180001bf3  mov     edx, 0Dh
0x180001bf8  mov     dword ptr [rsp+58h+ppv], ebx
0x180001bfc  call    WPP_SF_sd
0x180001c01  test    ebx, ebx
0x180001c03  jnz     short loc_180001C53
0x180001c05  lea     rbx, cs:180000000h
0x180001c0c  mov     rcx, [rsi+rbx+7018h]; hModule
0x180001c14  lea     rdx, aFdphostsession; "FdphostSessionChange"
0x180001c1b  call    cs:__imp_GetProcAddress
0x180001c21  mov     [rsi+rbx+7028h], rax
0x180001c29  mov     rdx, [rsp+58h+pUnk]; pUnk
0x180001c2e  lea     rax, ds:76C0h[r12*4]
0x180001c36  mov     r9d, 1; flags
0x180001c3c  add     rax, rbx
0x180001c3f  mov     rcx, r15; rclsid
0x180001c42  mov     [rsp+58h+ppv], rax; lpdwRegister
0x180001c47  lea     r8d, [r9+3]; dwClsContext
0x180001c4b  call    cs:__imp_CoRegisterClassObject
0x180001c51  mov     ebx, eax
0x180001c53  mov     rcx, [rsp+58h+pUnk]
0x180001c58  mov     rax, [rcx]
0x180001c5b  mov     rax, [rax+10h]
0x180001c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c64  mov     [rsp+58h+pUnk], 0
0x180001c6d  test    ebx, ebx
0x180001c6f  jnz     short loc_180001C82
0x180001c71  inc     r14d
0x180001c74  lea     r15, WPP_GLOBAL_Control
0x180001c7b  inc     edi
0x180001c7d  jmp     loc_180001A4E
0x180001c82  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c89  lea     r15, WPP_GLOBAL_Control
0x180001c90  cmp     rcx, r15
0x180001c93  jz      short loc_180001CBC
0x180001c95  cmp     byte ptr [rcx+19h], 2
0x180001c99  jb      short loc_180001CBC
0x180001c9b  mov     rcx, [rcx+10h]
0x180001c9f  lea     rax, cs:180000000h
0x180001ca6  mov     rax, [rsi+rax+7010h]
0x180001cae  mov     [rsp+58h+var_30], ebx
0x180001cb2  mov     [rsp+58h+ppv], rax; char *
0x180001cb7  call    WPP_SF_sSd
0x180001cbc  lea     rax, cs:180000000h
0x180001cc3  mov     r8d, ebx; int
0x180001cc6  mov     rdx, ds:rva ?g_arysProviderDesc@@3PAPEBGA[rax+r12*8]; unsigned __int16 *
0x180001cce  call    ?LogError@@YAJPEBU_EVENT_DESCRIPTOR@@PEBGJKPEBD@Z; LogError(_EVENT_DESCRIPTOR const *,ushort const *,long,ulong,char const *)
0x180001cd3  mov     ebp, ebx
0x180001cd5  xor     ebx, ebx
0x180001cd7  inc     edi
0x180001cd9  jmp     loc_180001A4E
0x180001cde  inc     edi
0x180001ce0  lea     rax, cs:180000000h
0x180001ce7  test    ebx, ebx
0x180001ce9  jns     loc_180001A55
0x180001cef  jmp     short loc_180001CFD
0x180001cf1  mov     cs:?g_pSharedService@@3PEAVCFdphostSharedService@@EA, rbp; CFdphostSharedService * g_pSharedService
0x180001cf8  mov     ebx, 8007000Eh
0x180001cfd  test    r14d, r14d
0x180001d00  cmovnz  ebp, ebx
0x180001d03  mov     rbx, [rsp+58h+arg_0]
0x180001d08  mov     eax, ebp
0x180001d0a  mov     rbp, [rsp+58h+arg_10]
0x180001d0f  add     rsp, 30h
0x180001d13  pop     r15
0x180001d15  pop     r14
0x180001d17  pop     r12
0x180001d19  pop     rdi
0x180001d1a  pop     rsi
0x180001d1b  retn
```
