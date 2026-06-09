# HandleQueryNetworkConnectivity(wchar_t const *,wchar_t * *,ulong,ulong,ulong,void const *,int *)

- ea: `0x18002bc80`
- end: `0x18002bdc4`
- name: `?HandleQueryNetworkConnectivity@@YAKPEB_WPEAPEA_WKKKPEBXPEAH@Z`
- size: `324`
- prototype: `__int64 __fastcall(const wchar_t *, wchar_t **, unsigned int, int, unsigned int, const void *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callees

- `0x18000f888`
- `0x18002b860`
- `0x18002bc80`
- `0x180043010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bcbf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bcbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd2b`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18002bd13`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18002bd13`

## pseudocode

```c
__int64 __fastcall HandleQueryNetworkConnectivity(
        const wchar_t *a1,
        wchar_t **a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        const void *a6,
        int *a7)
{
  __int64 v8; // rbx
  unsigned int v9; // eax
  unsigned int v10; // ebx
  __int64 result; // rax
  void *File2; // rax
  __int64 LastError; // rbx
  unsigned int v14; // eax
  unsigned int v15; // ebx
  _QWORD v16[3]; // [rsp+30h] [rbp-18h] BYREF

  try
  {
    *a7 = 0;
    if ( a4 && a3 == a4 - 1 )
    {
      v8 = a3;
      if ( (unsigned int)_o__wcsicmp(a2[a3], L"stdout") )
      {
        File2 = (void *)CreateFile2(a2[v8], 0x40000000, 0, 2, 0);
        v16[0] = File2;
        if ( (((unsigned __int64)File2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        {
          v14 = NetshQuery(File2);
          v15 = v14;
          if ( v14 )
            g_netshPrintMessageFromModule(g_moduleHandle, 10001u, v14);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v16);
          result = v15;
        }
        else
        {
          LastError = GetLastError();
          g_netshPrintMessageFromModule(g_moduleHandle, 0x2711u, LastError);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v16);
          result = (unsigned int)LastError;
        }
      }
      else
      {
        v9 = NetshQuery(0);
        v10 = v9;
        if ( v9 )
          g_netshPrintMessageFromModule(g_moduleHandle, 0x2711u, v9);
        result = v10;
      }
    }
    else
    {
      g_netshPrintMessageFromModule(g_moduleHandle, 10000u);
      result = 87;
    }
  }
  catch ( ... )
  {
    return Win32ErrorFromCaughtException();
  }
  return result;
}

```

## disassembly

```asm
0x18002bc80  mov     [rsp+arg_0], rbx
0x18002bc85  push    rdi
0x18002bc86  sub     rsp, 40h
0x18002bc8a  mov     rdi, rdx
0x18002bc8d  mov     rax, [rsp+48h+arg_30]
0x18002bc95  mov     dword ptr [rax], 0
0x18002bc9b  test    r9d, r9d
0x18002bc9e  jz      loc_18002BD95
0x18002bca4  lea     eax, [r9-1]
0x18002bca8  cmp     r8d, eax
0x18002bcab  jnz     loc_18002BD95
0x18002bcb1  mov     ebx, r8d
0x18002bcb4  lea     rdx, aStdout; "stdout"
0x18002bcbb  mov     rcx, [rdi+rbx*8]
0x18002bcbf  call    cs:__imp__o__wcsicmp
0x18002bcc5  test    eax, eax
0x18002bcc7  jnz     short loc_18002BCF8
0x18002bcc9  xor     ecx, ecx; void *
0x18002bccb  call    ?NetshQuery@@YAKPEAX@Z; NetshQuery(void *)
0x18002bcd0  mov     ebx, eax
0x18002bcd2  test    eax, eax
0x18002bcd4  jz      short loc_18002BCF1
0x18002bcd6  mov     r8d, eax
0x18002bcd9  mov     edx, 2711h
0x18002bcde  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x18002bce5  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x18002bcec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcf1  mov     eax, ebx
0x18002bcf3  jmp     loc_18002BDB8
0x18002bcf8  mov     [rsp+48h+var_28], 0
0x18002bd01  mov     r9d, 2
0x18002bd07  xor     r8d, r8d
0x18002bd0a  mov     edx, 40000000h
0x18002bd0f  mov     rcx, [rdi+rbx*8]
0x18002bd13  call    cs:__imp_CreateFile2
0x18002bd19  mov     [rsp+48h+var_18], rax
0x18002bd1e  lea     rcx, [rax+1]
0x18002bd22  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18002bd29  jnz     short loc_18002BD5D
0x18002bd2b  call    cs:__imp_GetLastError
0x18002bd31  mov     ebx, eax
0x18002bd33  mov     r8d, eax
0x18002bd36  mov     edx, 2711h
0x18002bd3b  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x18002bd42  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x18002bd49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd4e  nop
0x18002bd4f  lea     rcx, [rsp+48h+var_18]
0x18002bd54  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002bd59  mov     eax, ebx
0x18002bd5b  jmp     short loc_18002BDB8
0x18002bd5d  mov     rcx, rax; void *
0x18002bd60  call    ?NetshQuery@@YAKPEAX@Z; NetshQuery(void *)
0x18002bd65  mov     ebx, eax
0x18002bd67  test    eax, eax
0x18002bd69  jz      short loc_18002BD87
0x18002bd6b  mov     r8d, eax
0x18002bd6e  mov     edx, 2711h
0x18002bd73  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x18002bd7a  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x18002bd81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd86  nop
0x18002bd87  lea     rcx, [rsp+48h+var_18]
0x18002bd8c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002bd91  mov     eax, ebx
0x18002bd93  jmp     short loc_18002BDB8
0x18002bd95  mov     edx, 2710h
0x18002bd9a  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x18002bda1  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x18002bda8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdad  mov     eax, 57h ; 'W'
0x18002bdb2  jmp     short loc_18002BDB8
0x18002bdb4  mov     eax, dword ptr [rsp+48h+var_18]
0x18002bdb8  mov     rbx, [rsp+48h+arg_0]
0x18002bdbd  add     rsp, 40h
0x18002bdc1  pop     rdi
0x18002bdc2  retn
```
