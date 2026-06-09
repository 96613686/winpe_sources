# CLRWTSEnumerateSessions(void *,ulong,ulong,_WTS_SESSION_INFOW * *,ulong *)

- ea: `0x180007e94`
- end: `0x180007f20`
- name: `?CLRWTSEnumerateSessions@@YAHPEAXKKPEAPEAU_WTS_SESSION_INFOW@@PEAK@Z`
- size: `140`
- prototype: `__int64 __fastcall(void *, __int64, __int64, struct _WTS_SESSION_INFOW **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007130`

## callees

- `0x180007e94`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180007ebe`
- `KERNEL32!LoadLibraryExW` at `0x180007ebe`
- `KERNEL32!GetProcAddress` at `0x180007ed3`
- `KERNEL32!GetProcAddress` at `0x180007ed3`

## string_xrefs

- `0x180007eb5`: `Wtsapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=49
__int64 __fastcall CLRWTSEnumerateSessions(
        void *a1,
        __int64 a2,
        __int64 a3,
        struct _WTS_SESSION_INFOW **a4,
        unsigned int *a5)
{
  FARPROC ProcAddress; // r10
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FF80;
  if ( qword_18006FF80 )
    return ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, struct _WTS_SESSION_INFOW **, unsigned int *))ProcAddress)(
             0,
             0,
             1,
             a4,
             a5);
  if ( !bWTSEnumerateSessionsProbed
    && ((Library = LoadLibraryExW(L"Wtsapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FF80)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "WTSEnumerateSessionsW"), qword_18006FF80 = (__int64)ProcAddress),
        bWTSEnumerateSessionsProbed = 1,
        ProcAddress) )
  {
    return ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, struct _WTS_SESSION_INFOW **, unsigned int *))ProcAddress)(
             0,
             0,
             1,
             a4,
             a5);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180007e94  push    rbx
0x180007e96  sub     rsp, 30h
0x180007e9a  mov     r10, cs:qword_18006FF80
0x180007ea1  mov     rbx, r9
0x180007ea4  test    r10, r10
0x180007ea7  jnz     short loc_180007EFC
0x180007ea9  cmp     cs:?bWTSEnumerateSessionsProbed@@3_NA, r10b; bool bWTSEnumerateSessionsProbed
0x180007eb0  jnz     short loc_180007EF8
0x180007eb2  xor     r8d, r8d; dwFlags
0x180007eb5  lea     rcx, aWtsapi32Dll; "Wtsapi32.dll"
0x180007ebc  xor     edx, edx; hFile
0x180007ebe  call    cs:__imp_LoadLibraryExW
0x180007ec4  test    rax, rax
0x180007ec7  jz      short loc_180007EE5
0x180007ec9  lea     rdx, aWtsenumeratese; "WTSEnumerateSessionsW"
0x180007ed0  mov     rcx, rax; hModule
0x180007ed3  call    cs:__imp_GetProcAddress
0x180007ed9  mov     r10, rax
0x180007edc  mov     cs:qword_18006FF80, rax
0x180007ee3  jmp     short loc_180007EEC
0x180007ee5  mov     r10, cs:qword_18006FF80
0x180007eec  mov     cs:?bWTSEnumerateSessionsProbed@@3_NA, 1; bool bWTSEnumerateSessionsProbed
0x180007ef3  test    r10, r10
0x180007ef6  jnz     short loc_180007EFC
0x180007ef8  xor     eax, eax
0x180007efa  jmp     short loc_180007F1A
0x180007efc  mov     rax, [rsp+38h+arg_20]
0x180007f01  xor     edx, edx
0x180007f03  mov     [rsp+38h+var_18], rax
0x180007f08  mov     r9, rbx
0x180007f0b  xor     ecx, ecx
0x180007f0d  mov     rax, r10
0x180007f10  lea     r8d, [rdx+1]
0x180007f14  call    cs:__guard_dispatch_icall_fptr
0x180007f1a  add     rsp, 30h
0x180007f1e  pop     rbx
0x180007f1f  retn
```
