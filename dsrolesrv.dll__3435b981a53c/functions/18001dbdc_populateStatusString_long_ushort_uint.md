# populateStatusString(long,ushort *,uint)

- ea: `0x18001dbdc`
- end: `0x18001dd75`
- name: `?populateStatusString@@YAXJPEAGI@Z`
- size: `409`
- prototype: `void __fastcall(int dwMessageId, wchar_t *Buffer)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180019b34`

## callees

- `0x18001dbdc`
- `0x18002c050`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x18001dd32`
- `msvcrt!_snwprintf_s` at `0x18001dd4e`
- `msvcrt!_snwprintf_s` at `0x18001dd32`
- `msvcrt!_snwprintf_s` at `0x18001dd4e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001dcaa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001dcaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001dc2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001dc5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001dcc5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001dc2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001dc5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001dcc5`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001dcfb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001dcfb`

## string_xrefs

- `0x18001dc25`: `NTDLL.DLL`
- `0x18001dc58`: `NTDLL.DLL`
- `0x18001dcbe`: `KERNEL32.DLL`
- `0x18001dc85`: `ws2_32.dll`
- `0x18001dc9b`: `netmsg.dll`

## pseudocode

```c
void __fastcall populateStatusString(int dwMessageId, wchar_t *Buffer)
{
  signed int v2; // ebx
  HMODULE ModuleHandleW; // rax
  const WCHAR *v5; // rcx
  __int64 nSize; // [rsp+28h] [rbp-240h]
  va_list *Arguments; // [rsp+30h] [rbp-238h]
  WCHAR Buffera[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( !dwMessageId )
    return;
  v2 = dwMessageId;
  if ( (dwMessageId & 0xC0000000) == 0xC0000000 )
  {
    ModuleHandleW = (HMODULE)qword_18004DF00;
    if ( !qword_18004DF00 )
    {
      ModuleHandleW = GetModuleHandleW(L"NTDLL.DLL");
      qword_18004DF00 = ModuleHandleW;
    }
    goto LABEL_17;
  }
  if ( (dwMessageId & 0xF0000000) == 0xD0000000 )
  {
    ModuleHandleW = (HMODULE)qword_18004DF00;
    if ( !qword_18004DF00 )
    {
      ModuleHandleW = GetModuleHandleW(L"NTDLL.DLL");
      qword_18004DF00 = ModuleHandleW;
    }
    v2 &= 0xCFFFFFFF;
    goto LABEL_17;
  }
  if ( dwMessageId < 0 )
    goto LABEL_15;
  if ( (unsigned int)(dwMessageId - 10000) > 0x3E8 )
  {
    if ( (unsigned int)(dwMessageId - 2100) <= 0x383 )
    {
      v5 = L"netmsg.dll";
      goto LABEL_14;
    }
LABEL_15:
    ModuleHandleW = (HMODULE)qword_18004DF08;
    if ( !qword_18004DF08 )
    {
      ModuleHandleW = GetModuleHandleW(L"KERNEL32.DLL");
      qword_18004DF08 = (__int64)ModuleHandleW;
    }
    goto LABEL_17;
  }
  v5 = L"ws2_32.dll";
LABEL_14:
  ModuleHandleW = LoadLibraryExW(v5, 0, 2u);
LABEL_17:
  if ( !FormatMessageW(0xA00u, ModuleHandleW, v2, 0, Buffera, 0x104u, 0) )
    wcscpy(Buffera, L" ");
  if ( v2 >= 0 )
  {
    LODWORD(Arguments) = v2;
    LODWORD(nSize) = v2;
    _snwprintf_s(Buffer, 0x105u, 0x104u, L"\"%ws (%#x, %d)\"", Buffera, nSize, Arguments);
  }
  else
  {
    LODWORD(nSize) = v2;
    _snwprintf_s(Buffer, 0x105u, 0x104u, L"\"%ws (%#x)\"", Buffera, nSize);
  }
}

```

## disassembly

```asm
0x18001dbdc  test    ecx, ecx
0x18001dbde  jz      locret_18001DD74
0x18001dbe4  mov     [rsp+arg_10], rbx
0x18001dbe9  push    rdi
0x18001dbea  sub     rsp, 260h
0x18001dbf1  mov     rax, cs:__security_cookie
0x18001dbf8  xor     rax, rsp
0x18001dbfb  mov     [rsp+268h+var_18], rax
0x18001dc03  mov     eax, ecx
0x18001dc05  mov     ebx, ecx
0x18001dc07  mov     ecx, 0C0000000h
0x18001dc0c  mov     rdi, rdx
0x18001dc0f  and     eax, ecx
0x18001dc11  cmp     eax, ecx
0x18001dc13  jnz     short loc_18001DC3E
0x18001dc15  mov     rax, cs:qword_18004DF00
0x18001dc1c  test    rax, rax
0x18001dc1f  jnz     loc_18001DCD2
0x18001dc25  lea     rcx, aNtdllDll_0; "NTDLL.DLL"
0x18001dc2c  call    cs:__imp_GetModuleHandleW
0x18001dc32  mov     cs:qword_18004DF00, rax
0x18001dc39  jmp     loc_18001DCD2
0x18001dc3e  mov     eax, ebx
0x18001dc40  and     eax, 0F0000000h
0x18001dc45  cmp     eax, 0D0000000h
0x18001dc4a  jnz     short loc_18001DC74
0x18001dc4c  mov     rax, cs:qword_18004DF00
0x18001dc53  test    rax, rax
0x18001dc56  jnz     short loc_18001DC6C
0x18001dc58  lea     rcx, aNtdllDll_0; "NTDLL.DLL"
0x18001dc5f  call    cs:__imp_GetModuleHandleW
0x18001dc65  mov     cs:qword_18004DF00, rax
0x18001dc6c  and     ebx, 0CFFFFFFFh
0x18001dc72  jmp     short loc_18001DCD2
0x18001dc74  test    ebx, ebx
0x18001dc76  js      short loc_18001DCB2
0x18001dc78  lea     eax, [rbx-2710h]
0x18001dc7e  cmp     eax, 3E8h
0x18001dc83  ja      short loc_18001DC8E
0x18001dc85  lea     rcx, aWs232Dll_0; "ws2_32.dll"
0x18001dc8c  jmp     short loc_18001DCA2
0x18001dc8e  lea     eax, [rbx-834h]
0x18001dc94  cmp     eax, 383h
0x18001dc99  ja      short loc_18001DCB2
0x18001dc9b  lea     rcx, LibFileName; "netmsg.dll"
0x18001dca2  mov     r8d, 2; dwFlags
0x18001dca8  xor     edx, edx; hFile
0x18001dcaa  call    cs:__imp_LoadLibraryExW
0x18001dcb0  jmp     short loc_18001DCD2
0x18001dcb2  mov     rax, cs:qword_18004DF08
0x18001dcb9  test    rax, rax
0x18001dcbc  jnz     short loc_18001DCD2
0x18001dcbe  lea     rcx, aKernel32Dll_0; "KERNEL32.DLL"
0x18001dcc5  call    cs:__imp_GetModuleHandleW
0x18001dccb  mov     cs:qword_18004DF08, rax
0x18001dcd2  lea     rcx, [rsp+268h+Buffer]
0x18001dcd7  mov     [rsp+268h+Arguments], 0; Arguments
0x18001dce0  mov     dword ptr [rsp+268h+nSize], 104h; nSize
0x18001dce8  xor     r9d, r9d; dwLanguageId
0x18001dceb  mov     [rsp+268h+lpBuffer], rcx; lpBuffer
0x18001dcf0  mov     r8d, ebx; dwMessageId
0x18001dcf3  mov     ecx, 0A00h; dwFlags
0x18001dcf8  mov     rdx, rax; lpSource
0x18001dcfb  call    cs:__imp_FormatMessageW
0x18001dd01  test    eax, eax
0x18001dd03  jnz     short loc_18001DD0D
0x18001dd05  mov     dword ptr [rsp+268h+Buffer], 20h ; ' '
0x18001dd0d  lea     rax, [rsp+268h+Buffer]
0x18001dd12  mov     edx, 105h; BufferCount
0x18001dd17  mov     rcx, rdi; Buffer
0x18001dd1a  lea     r8d, [rdx-1]; MaxCount
0x18001dd1e  test    ebx, ebx
0x18001dd20  jns     short loc_18001DD3A
0x18001dd22  mov     dword ptr [rsp+268h+nSize], ebx
0x18001dd26  lea     r9, aWsX; "\"%ws (%#x)\""
0x18001dd2d  mov     [rsp+268h+lpBuffer], rax
0x18001dd32  call    cs:__imp__snwprintf_s
0x18001dd38  jmp     short loc_18001DD54
0x18001dd3a  mov     dword ptr [rsp+268h+Arguments], ebx
0x18001dd3e  lea     r9, aWsXD; "\"%ws (%#x, %d)\""
0x18001dd45  mov     dword ptr [rsp+268h+nSize], ebx
0x18001dd49  mov     [rsp+268h+lpBuffer], rax
0x18001dd4e  call    cs:__imp__snwprintf_s
0x18001dd54  mov     rcx, [rsp+268h+var_18]
0x18001dd5c  xor     rcx, rsp; StackCookie
0x18001dd5f  call    __security_check_cookie
0x18001dd64  mov     rbx, [rsp+268h+arg_10]
0x18001dd6c  add     rsp, 260h
0x18001dd73  pop     rdi
0x18001dd74  retn
```
