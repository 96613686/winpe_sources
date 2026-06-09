# ServiceManager_EnsureInstance(void)

- ea: `0x18000a540`
- end: `0x18000a69e`
- name: `?ServiceManager_EnsureInstance@@YAJXZ`
- size: `350`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180007350`
- `0x1800082d0`
- `0x180008ce0`
- `0x180009250`
- `0x18000ac10`

## callees

- `0x18000a540`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a67c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a67c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a587`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a587`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a5db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a5db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a686`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a686`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a55e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a55e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a59a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a59a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5e6`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000a5c4`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000a610`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000a5c4`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000a610`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a661`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000a661`

## string_xrefs

- `0x18000a580`: `MosHostCore.dll`
- `0x18000a5bb`: `ServiceManager_EnsureInstance`
- `0x18000a609`: `ServiceManager_EnsureInstance`
- `0x18000a658`: `ServiceManager_EnsureInstance`
- `0x18000a5d1`: `MosHostCore_ServiceManagerInstance`

## pseudocode

```c
__int64 ServiceManager_EnsureInstance(void)
{
  unsigned int v0; // edi
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed int v3; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  int v6; // r8d
  int v7; // ecx
  unsigned int v8; // eax
  HMODULE v9; // rcx
  __int64 (__fastcall ***v10)(_QWORD); // rax
  int v11; // eax

  EnterCriticalSection(&stru_1800186B0);
  v0 = 0;
  if ( hLibModule )
    goto LABEL_22;
  Library = LoadLibraryExW(L"MosHostCore.dll", 0, 0x800u);
  v2 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "MosHostCore_ServiceManagerInstance");
    if ( ProcAddress )
    {
      v10 = (__int64 (__fastcall ***)(_QWORD))((__int64 (__fastcall *)(void ***))ProcAddress)(off_1800180A0);
      qword_1800185D0 = (__int64)v10;
      if ( v10 )
      {
        v11 = (**v10)(v10);
        if ( v11 >= 0 )
        {
          v9 = hLibModule;
          hLibModule = v2;
          if ( !v9 )
            goto LABEL_22;
LABEL_21:
          FreeLibrary(v9);
          goto LABEL_22;
        }
        v8 = ZTraceReportPropagationNoThis(v11, "ServiceManager_EnsureInstance", 66);
LABEL_15:
        v0 = v8;
        v9 = v2;
        goto LABEL_21;
      }
      v6 = 64;
      v7 = -2147418113;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2143748092;
      }
      v6 = 61;
      v7 = LastError;
    }
    v8 = ZTraceReportOriginationNoThis(v7, "ServiceManager_EnsureInstance", v6);
    goto LABEL_15;
  }
  v3 = GetLastError();
  if ( v3 )
  {
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    v3 = -2143748092;
  }
  v0 = ZTraceReportOriginationNoThis(v3, "ServiceManager_EnsureInstance", 58);
LABEL_22:
  LeaveCriticalSection(&stru_1800186B0);
  return v0;
}

```

## disassembly

```asm
0x18000a540  mov     [rsp+arg_8], rbx
0x18000a545  mov     [rsp+arg_10], rsi
0x18000a54a  push    rdi
0x18000a54b  sub     rsp, 30h
0x18000a54f  lea     rsi, stru_1800186B0
0x18000a556  mov     [rsp+38h+var_18], rsi
0x18000a55b  mov     rcx, rsi; lpCriticalSection
0x18000a55e  call    cs:__imp_EnterCriticalSection
0x18000a564  mov     [rsp+38h+var_10], 1
0x18000a569  xor     edi, edi
0x18000a56b  cmp     cs:hLibModule, rdi
0x18000a572  jnz     loc_18000A683
0x18000a578  xor     edx, edx; hFile
0x18000a57a  mov     r8d, 800h; dwFlags
0x18000a580  lea     rcx, LibFileName; "MosHostCore.dll"
0x18000a587  call    cs:__imp_LoadLibraryExW
0x18000a58d  mov     rbx, rax
0x18000a590  mov     [rsp+38h+arg_0], rax
0x18000a595  test    rax, rax
0x18000a598  jnz     short loc_18000A5D1
0x18000a59a  call    cs:__imp_GetLastError
0x18000a5a0  test    eax, eax
0x18000a5a2  jz      short loc_18000A5B0
0x18000a5a4  jle     short loc_18000A5B5
0x18000a5a6  movzx   eax, ax
0x18000a5a9  or      eax, 80070000h
0x18000a5ae  jmp     short loc_18000A5B5
0x18000a5b0  mov     eax, 80390004h
0x18000a5b5  mov     r8d, 3Ah ; ':'
0x18000a5bb  lea     rdx, aServicemanager_0; "ServiceManager_EnsureInstance"
0x18000a5c2  mov     ecx, eax
0x18000a5c4  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000a5ca  mov     edi, eax
0x18000a5cc  jmp     loc_18000A683
0x18000a5d1  lea     rdx, aMoshostcoreSer; "MosHostCore_ServiceManagerInstance"
0x18000a5d8  mov     rcx, rbx; hModule
0x18000a5db  call    cs:__imp_GetProcAddress
0x18000a5e1  test    rax, rax
0x18000a5e4  jnz     short loc_18000A61D
0x18000a5e6  call    cs:__imp_GetLastError
0x18000a5ec  test    eax, eax
0x18000a5ee  jz      short loc_18000A5FC
0x18000a5f0  jle     short loc_18000A601
0x18000a5f2  movzx   eax, ax
0x18000a5f5  or      eax, 80070000h
0x18000a5fa  jmp     short loc_18000A601
0x18000a5fc  mov     eax, 80390004h
0x18000a601  mov     r8d, 3Dh ; '='
0x18000a607  mov     ecx, eax
0x18000a609  lea     rdx, aServicemanager_0; "ServiceManager_EnsureInstance"
0x18000a610  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000a616  mov     edi, eax
0x18000a618  mov     rcx, rbx
0x18000a61b  jmp     short loc_18000A67C
0x18000a61d  lea     rcx, off_1800180A0
0x18000a624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a629  mov     rcx, rax
0x18000a62c  mov     cs:qword_1800185D0, rax
0x18000a633  test    rax, rax
0x18000a636  jnz     short loc_18000A643
0x18000a638  lea     r8d, [rax+40h]
0x18000a63c  mov     ecx, 8000FFFFh
0x18000a641  jmp     short loc_18000A609
0x18000a643  mov     rax, [rax]
0x18000a646  mov     rax, [rax]
0x18000a649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a64e  test    eax, eax
0x18000a650  jns     short loc_18000A669
0x18000a652  mov     r8d, 42h ; 'B'
0x18000a658  lea     rdx, aServicemanager_0; "ServiceManager_EnsureInstance"
0x18000a65f  mov     ecx, eax
0x18000a661  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000a667  jmp     short loc_18000A616
0x18000a669  mov     rcx, cs:hLibModule; hLibModule
0x18000a670  mov     cs:hLibModule, rbx
0x18000a677  test    rcx, rcx
0x18000a67a  jz      short loc_18000A683
0x18000a67c  call    cs:__imp_FreeLibrary
0x18000a682  nop
0x18000a683  mov     rcx, rsi; lpCriticalSection
0x18000a686  call    cs:__imp_LeaveCriticalSection
0x18000a68c  mov     eax, edi
0x18000a68e  mov     rbx, [rsp+38h+arg_8]
0x18000a693  mov     rsi, [rsp+38h+arg_10]
0x18000a698  add     rsp, 30h
0x18000a69c  pop     rdi
0x18000a69d  retn
```
