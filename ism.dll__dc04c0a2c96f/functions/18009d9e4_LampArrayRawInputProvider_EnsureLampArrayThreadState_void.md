# LampArrayRawInputProvider::EnsureLampArrayThreadState(void)

- ea: `0x18009d9e4`
- end: `0x18009daf1`
- name: `?EnsureLampArrayThreadState@LampArrayRawInputProvider@@AEAAJXZ`
- size: `269`
- prototype: `__int64 __fastcall(ULONG_PTR dwData)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18009d920`

## callees

- `0x18002fb90`
- `0x18008daac`
- `0x18009d9e4`
- `0x18009daf8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009da8c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009da8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18009da49`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18009da49`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009dabe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009dabe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009daa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009daa6`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18009d9fb`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18009da08`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18009d9fb`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18009da08`

## pseudocode

```c
__int64 __fastcall LampArrayRawInputProvider::EnsureLampArrayThreadState(ULONG_PTR dwData)
{
  int SystemMetrics; // edi
  HMODULE *v3; // rsi
  const char *v4; // r9
  signed int LastError; // eax
  unsigned int v7; // edi
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  SystemMetrics = GetSystemMetrics(4096);
  if ( GetSystemMetrics(67) || SystemMetrics )
  {
    LampArrayRawInputProvider::Shutdown(dwData);
    return 0;
  }
  if ( *(_QWORD *)(dwData + 176) )
    LampArrayRawInputProvider::Shutdown(dwData);
  v3 = (HMODULE *)(dwData + 168);
  if ( !GetModuleHandleExW(4u, (LPCWSTR)LampArrayRawInputProvider::WorkerThreadProcThunk, (HMODULE *)(dwData + 168)) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x5B,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\lamparrayrawinputprovider.cpp",
             v4);
  _InterlockedIncrement((volatile signed __int32 *)(dwData + 32));
  _InterlockedExchange64(
    (volatile __int64 *)(dwData + 176),
    (__int64)CreateThread(0, 0, LampArrayRawInputProvider::WorkerThreadProcThunk, (LPVOID)dwData, 0, 0));
  if ( *(_QWORD *)(dwData + 176) )
    return 0;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  FreeLibrary(*v3);
  *v3 = 0;
  LampArrayRawInputProvider::Release(dwData);
  return v7;
}

```

## disassembly

```asm
0x18009d9e4  mov     [rsp+arg_0], rbx
0x18009d9e9  mov     [rsp+arg_8], rsi
0x18009d9ee  push    rdi
0x18009d9ef  sub     rsp, 30h
0x18009d9f3  mov     rbx, rcx
0x18009d9f6  mov     ecx, 1000h; nIndex
0x18009d9fb  call    cs:__imp_GetSystemMetrics
0x18009da01  mov     edi, eax
0x18009da03  mov     ecx, 43h ; 'C'; nIndex
0x18009da08  call    cs:__imp_GetSystemMetrics
0x18009da0e  test    eax, eax
0x18009da10  jnz     loc_18009DAD7
0x18009da16  test    edi, edi
0x18009da18  jnz     loc_18009DAD7
0x18009da1e  mov     rax, [rbx+0B0h]
0x18009da25  nop
0x18009da26  test    rax, rax
0x18009da29  jz      short loc_18009DA33
0x18009da2b  mov     rcx, rbx; dwData
0x18009da2e  call    ?Shutdown@LampArrayRawInputProvider@@AEAAXXZ; LampArrayRawInputProvider::Shutdown(void)
0x18009da33  lea     rsi, [rbx+0A8h]
0x18009da3a  mov     r8, rsi; phModule
0x18009da3d  lea     rdx, ?WorkerThreadProcThunk@LampArrayRawInputProvider@@CAKPEAX@Z; lpModuleName
0x18009da44  mov     ecx, 4; dwFlags
0x18009da49  call    cs:__imp_GetModuleHandleExW
0x18009da4f  test    eax, eax
0x18009da51  jnz     short loc_18009DA69
0x18009da53  mov     rcx, [rsp+38h]; this
0x18009da58  lea     r8, aOnecoreuapWind_201; "onecoreuap\\windows\\moderncore\\inputv"...
0x18009da5f  lea     edx, [rax+5Bh]; void *
0x18009da62  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009da67  jmp     short loc_18009DAE1
0x18009da69  lock inc dword ptr [rbx+20h]
0x18009da6d  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18009da76  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18009da7e  mov     r9, rbx; lpParameter
0x18009da81  lea     r8, ?WorkerThreadProcThunk@LampArrayRawInputProvider@@CAKPEAX@Z; lpStartAddress
0x18009da88  xor     edx, edx; dwStackSize
0x18009da8a  xor     ecx, ecx; lpThreadAttributes
0x18009da8c  call    cs:__imp_CreateThread
0x18009da92  xchg    rax, [rbx+0B0h]
0x18009da99  mov     rax, [rbx+0B0h]
0x18009daa0  nop
0x18009daa1  test    rax, rax
0x18009daa4  jnz     short loc_18009DADF
0x18009daa6  call    cs:__imp_GetLastError
0x18009daac  mov     edi, eax
0x18009daae  test    eax, eax
0x18009dab0  jle     short loc_18009DABB
0x18009dab2  movzx   edi, ax
0x18009dab5  or      edi, 80070000h
0x18009dabb  mov     rcx, [rsi]; hLibModule
0x18009dabe  call    cs:__imp_FreeLibrary
0x18009dac4  mov     qword ptr [rsi], 0
0x18009dacb  mov     rcx, rbx; dwData
0x18009dace  call    ?Release@LampArrayRawInputProvider@@UEAAKXZ; LampArrayRawInputProvider::Release(void)
0x18009dad3  mov     eax, edi
0x18009dad5  jmp     short loc_18009DAE1
0x18009dad7  mov     rcx, rbx; dwData
0x18009dada  call    ?Shutdown@LampArrayRawInputProvider@@AEAAXXZ; LampArrayRawInputProvider::Shutdown(void)
0x18009dadf  xor     eax, eax
0x18009dae1  mov     rbx, [rsp+38h+arg_0]
0x18009dae6  mov     rsi, [rsp+38h+arg_8]
0x18009daeb  add     rsp, 30h
0x18009daef  pop     rdi
0x18009daf0  retn
```
