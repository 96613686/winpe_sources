# LoadDll(_DLL_ELEMENT *)

- ea: `0x1800258c4`
- end: `0x1800259a6`
- name: `?LoadDll@@YAHPEAU_DLL_ELEMENT@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(struct _DLL_ELEMENT *)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008720`
- `0x180012d00`
- `0x180026220`
- `0x180026d50`
- `0x1800275a0`
- `0x180028d9c`
- `0x180029500`
- `0x180029b00`
- `0x1800466a0`

## callees

- `0x1800258c4`
- `0x180027cb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002597a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002597a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002598d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002598d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800258f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025918`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800258f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025918`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800258d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002594f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800258d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002594f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025985`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025985`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002593f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002593f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025927`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025927`

## string_xrefs

- `0x180025935`: `DllCanUnloadNow`

## pseudocode

```c
__int64 __fastcall LoadDll(struct _DLL_ELEMENT *a1)
{
  unsigned int v2; // esi
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rbp
  HMODULE Library; // rax
  DWORD LastError; // ebx

  EnterCriticalSection(&CriticalSection);
  v2 = 1;
  if ( *((_DWORD *)a1 + 9) )
  {
    v3 = 0;
    AddRefDll(a1);
  }
  else
  {
    ProcAddress = 0;
    LeaveCriticalSection(&CriticalSection);
    Library = LoadLibraryExW(*((LPCWSTR *)a1 + 2), 0, 0);
    v3 = Library;
    if ( Library )
      ProcAddress = GetProcAddress(Library, "DllCanUnloadNow");
    EnterCriticalSection(&CriticalSection);
    AddRefDll(a1);
    if ( !*((_DWORD *)a1 + 9) )
    {
      *((_QWORD *)a1 + 3) = v3;
      if ( v3 )
      {
        v3 = 0;
        *((_DWORD *)a1 + 9) = 1;
        *((_QWORD *)a1 + 6) = ProcAddress;
      }
      else
      {
        *((_DWORD *)a1 + 8) = 0;
        v2 = 0;
      }
    }
  }
  LeaveCriticalSection(&CriticalSection);
  if ( v3 )
  {
    LastError = GetLastError();
    FreeLibrary(v3);
    SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x1800258c4  push    rbx
0x1800258c6  push    rbp
0x1800258c7  push    rsi
0x1800258c8  push    rdi
0x1800258c9  sub     rsp, 28h
0x1800258cd  mov     rbx, rcx
0x1800258d0  lea     rcx, CriticalSection; lpCriticalSection
0x1800258d7  call    cs:__imp_EnterCriticalSection
0x1800258dd  cmp     dword ptr [rbx+24h], 0
0x1800258e1  mov     esi, 1
0x1800258e6  jz      short loc_18002590F
0x1800258e8  xor     edi, edi
0x1800258ea  mov     rcx, rbx; struct _DLL_ELEMENT *
0x1800258ed  call    ?AddRefDll@@YAXPEAU_DLL_ELEMENT@@@Z; AddRefDll(_DLL_ELEMENT *)
0x1800258f2  lea     rcx, CriticalSection; lpCriticalSection
0x1800258f9  call    cs:__imp_LeaveCriticalSection
0x1800258ff  test    rdi, rdi
0x180025902  jnz     short loc_18002597A
0x180025904  mov     eax, esi
0x180025906  add     rsp, 28h
0x18002590a  pop     rdi
0x18002590b  pop     rsi
0x18002590c  pop     rbp
0x18002590d  pop     rbx
0x18002590e  retn
0x18002590f  lea     rcx, CriticalSection; lpCriticalSection
0x180025916  xor     ebp, ebp
0x180025918  call    cs:__imp_LeaveCriticalSection
0x18002591e  mov     rcx, [rbx+10h]; lpLibFileName
0x180025922  xor     r8d, r8d; dwFlags
0x180025925  xor     edx, edx; hFile
0x180025927  call    cs:__imp_LoadLibraryExW
0x18002592d  mov     rdi, rax
0x180025930  test    rax, rax
0x180025933  jz      short loc_180025948
0x180025935  lea     rdx, ProcName; "DllCanUnloadNow"
0x18002593c  mov     rcx, rax; hModule
0x18002593f  call    cs:__imp_GetProcAddress
0x180025945  mov     rbp, rax
0x180025948  lea     rcx, CriticalSection; lpCriticalSection
0x18002594f  call    cs:__imp_EnterCriticalSection
0x180025955  mov     rcx, rbx; struct _DLL_ELEMENT *
0x180025958  call    ?AddRefDll@@YAXPEAU_DLL_ELEMENT@@@Z; AddRefDll(_DLL_ELEMENT *)
0x18002595d  cmp     dword ptr [rbx+24h], 0
0x180025961  jnz     short loc_1800258F2
0x180025963  mov     [rbx+18h], rdi
0x180025967  test    rdi, rdi
0x18002596a  jz      short loc_180025998
0x18002596c  xor     edi, edi
0x18002596e  mov     [rbx+24h], esi
0x180025971  mov     [rbx+30h], rbp
0x180025975  jmp     loc_1800258F2
0x18002597a  call    cs:__imp_GetLastError
0x180025980  mov     rcx, rdi; hLibModule
0x180025983  mov     ebx, eax
0x180025985  call    cs:__imp_FreeLibrary
0x18002598b  mov     ecx, ebx; dwErrCode
0x18002598d  call    cs:__imp_SetLastError
0x180025993  jmp     loc_180025904
0x180025998  mov     dword ptr [rbx+20h], 0
0x18002599f  xor     esi, esi
0x1800259a1  jmp     loc_1800258F2
```
