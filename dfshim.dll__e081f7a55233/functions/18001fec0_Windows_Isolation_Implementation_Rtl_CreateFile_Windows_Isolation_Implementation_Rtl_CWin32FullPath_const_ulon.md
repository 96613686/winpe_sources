# Windows::Isolation::Implementation::Rtl::CreateFile(Windows::Isolation::Implementation::Rtl::CWin32FullPath const &,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x18001fec0`
- end: `0x18001ffac`
- name: `?CreateFile@Rtl@Implementation@Isolation@Windows@@YA?AU_WIN32_FUNCTION_RETURN_STATUS@@AEBVCWin32FullPath@1234@KKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `236`
- prototype: `struct _WIN32_FUNCTION_RETURN_STATUS __high(const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020c10`
- `0x180021be0`
- `0x180022d40`

## callees

- `0x1800069e5`
- `0x18001fec0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18001ff32`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18001ff32`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ff89`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ff89`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fef9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ff50`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fef9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ff50`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::CreateFile(
        __int64 a1,
        __int64 a2,
        DWORD a3,
        DWORD a4,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes)
{
  __int64 v7; // rbx
  int v8; // eax
  HANDLE FileA; // rax

  v7 = a2 + 48;
  *(_OWORD *)a1 = 0;
  v8 = *(_DWORD *)(a2 + 56);
  if ( v8 == 1 )
  {
    if ( !*(_QWORD *)v7 )
      RaiseException(0xC00000E5, 1u, 0, 0);
    FileA = CreateFileA(
              *(LPCSTR *)(*(_QWORD *)v7 + 16LL),
              a3,
              a4,
              lpSecurityAttributes,
              dwCreationDisposition,
              dwFlagsAndAttributes,
              0);
  }
  else
  {
    if ( v8 != 2 || !*(_QWORD *)v7 )
      RaiseException(0xC00000E5, 1u, 0, 0);
    FileA = CreateFileW(
              *(LPCWSTR *)(*(_QWORD *)v7 + 16LL),
              a3,
              a4,
              lpSecurityAttributes,
              dwCreationDisposition,
              dwFlagsAndAttributes,
              0);
  }
  *(_QWORD *)(a1 + 8) = FileA;
  if ( FileA == (HANDLE)-1LL )
    *(_DWORD *)a1 = GetLastError_0();
  return a1;
}

```

## disassembly

```asm
0x18001fec0  push    rbx
0x18001fec2  push    rbp
0x18001fec3  push    rsi
0x18001fec4  push    rdi
0x18001fec5  sub     rsp, 48h
0x18001fec9  xorps   xmm0, xmm0
0x18001fecc  lea     rbx, [rdx+30h]
0x18001fed0  movups  xmmword ptr [rcx], xmm0
0x18001fed3  mov     eax, [rdx+38h]
0x18001fed6  mov     esi, r9d
0x18001fed9  mov     edx, 1; dwExceptionFlags
0x18001fede  mov     ebp, r8d
0x18001fee1  mov     rdi, rcx
0x18001fee4  cmp     eax, edx
0x18001fee6  jnz     short loc_18001FF3A
0x18001fee8  cmp     qword ptr [rbx], 0
0x18001feec  jnz     short loc_18001FEFF
0x18001feee  xor     r9d, r9d; lpArguments
0x18001fef1  xor     r8d, r8d; nNumberOfArguments
0x18001fef4  mov     ecx, 0C00000E5h; dwExceptionCode
0x18001fef9  call    cs:__imp_RaiseException
0x18001feff  mov     eax, [rsp+68h+arg_30]
0x18001ff06  mov     r8d, esi; dwShareMode
0x18001ff09  mov     rcx, [rbx]
0x18001ff0c  mov     edx, ebp; dwDesiredAccess
0x18001ff0e  mov     r9, [rsp+68h+lpSecurityAttributes]; lpSecurityAttributes
0x18001ff16  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18001ff1f  mov     [rsp+68h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18001ff23  mov     eax, [rsp+68h+arg_28]
0x18001ff2a  mov     rcx, [rcx+10h]; lpFileName
0x18001ff2e  mov     [rsp+68h+dwCreationDisposition], eax; dwCreationDisposition
0x18001ff32  call    cs:__imp_CreateFileA
0x18001ff38  jmp     short loc_18001FF8F
0x18001ff3a  cmp     eax, 2
0x18001ff3d  jnz     short loc_18001FF45
0x18001ff3f  cmp     qword ptr [rbx], 0
0x18001ff43  jnz     short loc_18001FF56
0x18001ff45  xor     r9d, r9d; lpArguments
0x18001ff48  xor     r8d, r8d; nNumberOfArguments
0x18001ff4b  mov     ecx, 0C00000E5h; dwExceptionCode
0x18001ff50  call    cs:__imp_RaiseException
0x18001ff56  mov     eax, [rsp+68h+arg_30]
0x18001ff5d  mov     r8d, esi; dwShareMode
0x18001ff60  mov     rcx, [rbx]
0x18001ff63  mov     edx, ebp; dwDesiredAccess
0x18001ff65  mov     r9, [rsp+68h+lpSecurityAttributes]; lpSecurityAttributes
0x18001ff6d  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18001ff76  mov     [rsp+68h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18001ff7a  mov     eax, [rsp+68h+arg_28]
0x18001ff81  mov     rcx, [rcx+10h]; lpFileName
0x18001ff85  mov     [rsp+68h+dwCreationDisposition], eax; dwCreationDisposition
0x18001ff89  call    cs:__imp_CreateFileW
0x18001ff8f  mov     [rdi+8], rax
0x18001ff93  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ff97  jnz     short loc_18001FFA0
0x18001ff99  call    GetLastError_0
0x18001ff9e  mov     [rdi], eax
0x18001ffa0  mov     rax, rdi
0x18001ffa3  add     rsp, 48h
0x18001ffa7  pop     rdi
0x18001ffa8  pop     rsi
0x18001ffa9  pop     rbp
0x18001ffaa  pop     rbx
0x18001ffab  retn
```
