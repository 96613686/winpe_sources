# FormatAnyStatus(long,void *,int *,ushort * *)

- ea: `0x1801bf65c`
- end: `0x1801bf917`
- name: `?FormatAnyStatus@@YAPEBGJPEAXPEAHPEAPEAG@Z`
- size: `699`
- prototype: `const unsigned __int16 *__fastcall(DWORD dwMessageId, void *, int *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18019eee0`
- `0x18019f818`
- `0x18019f8e4`
- `0x1801af304`

## callees

- `0x1800084a0`
- `0x180169420`
- `0x1801bf65c`
- `0x1801bf920`
- `0x180205010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswprint` at `0x1801bf8c5`
- `api-ms-win-crt-private-l1-1-0!_o_iswprint` at `0x1801bf8c5`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1801bf8e7`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1801bf8e7`
- `api-ms-win-core-misc-l1-1-0!FormatMessageW` at `0x1801bf898`
- `api-ms-win-core-misc-l1-1-0!FormatMessageW` at `0x1801bf898`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1801bf8ac`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1801bf8ac`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801bf72d`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801bf72d`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1801bf717`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1801bf717`
- `ntdll!RtlUTF8ToUnicodeN` at `0x1801bf831`
- `ntdll!RtlUTF8ToUnicodeN` at `0x1801bf831`

## string_xrefs

- `0x1801bf6e3`: `The process that you are attempting to attach to is already being debugged. Only one debugger can be invasively attached to a process at a time. A non-invasive attach is still possible when another debugger is attached.`
- `0x1801bf6d6`: `ntdll.dll`
- `0x1801bf6b1`: `netmsg.dll`

## pseudocode

```c
WCHAR *__fastcall FormatAnyStatus(DWORD dwMessageId, void *a2, int *a3, unsigned __int16 **a4)
{
  DWORD v4; // ebp
  unsigned int v5; // r8d
  const WCHAR *v6; // rbx
  WCHAR *result; // rax
  int v8; // esi
  WCHAR *lpBuffer; // r14
  HMODULE ModuleHandleW; // rdi
  int v11; // ebx
  DWORD v12; // ebp
  wint_t v13; // ax
  WCHAR *v14; // rbx

  v4 = dwMessageId;
  v5 = ((_BYTE)g_NextFormatStatusBuffer - 1) & 1;
  g_NextFormatStatusBuffer = v5;
  if ( (dwMessageId & 0xC0000000) != -1073741824 && (dwMessageId & 0x10000000) == 0 )
  {
    if ( dwMessageId - 2100 > 0x383 )
      v6 = 0;
    else
      v6 = L"netmsg.dll";
  }
  else
  {
    v4 = dwMessageId & 0xEFFFFFFF;
    v6 = L"ntdll.dll";
  }
  result = L"The process that you are attempting to attach to is already being debugged. Only one debugger can be invasive"
            "ly attached to a process at a time. A non-invasive attach is still possible when another debugger is attached.";
  if ( v4 != -1073741752 )
    result = 0;
  if ( !result )
  {
    v8 = 0;
    lpBuffer = (WCHAR *)&(&g_FormatStatusBuffer)[256 * (unsigned __int64)v5];
    if ( v6 )
    {
      ModuleHandleW = GetModuleHandleW(v6);
      if ( !ModuleHandleW )
      {
        ModuleHandleW = LoadLibraryExW(v6, 0, 0);
        v8 = 1;
      }
      v11 = ModuleHandleW != 0 ? 6144 : 4096;
      if ( ModuleHandleW )
        LoadDynamicCalls(&g_NtDllCallsDesc);
    }
    else
    {
      v11 = 4096;
      ModuleHandleW = 0;
    }
    v12 = FormatMessageW(v11 | 0x200, ModuleHandleW, v4, 0, lpBuffer, 0x400u, 0);
    if ( ModuleHandleW && v8 )
      FreeLibrary(ModuleHandleW);
    if ( v12 )
    {
      v13 = *lpBuffer;
      if ( *lpBuffer )
      {
        v14 = lpBuffer;
        do
        {
          if ( !iswprint(v13) )
            *v14 = 32;
          v13 = *++v14;
        }
        while ( *v14 );
      }
      while ( (unsigned int)_o_iswspace(lpBuffer[--v12]) )
      {
        lpBuffer[v12] = 0;
        if ( !v12 )
          return L"<Unable to get error code text>";
      }
      return lpBuffer;
    }
    else
    {
      return L"<Unable to get error code text>";
    }
  }
  return result;
}

```

## disassembly

```asm
0x1801bf65c  mov     [rsp+arg_8], rbx
0x1801bf661  mov     [rsp+arg_18], r9
0x1801bf666  push    rbp
0x1801bf667  push    rsi
0x1801bf668  push    rdi
0x1801bf669  push    r14
0x1801bf66b  push    r15
0x1801bf66d  sub     rsp, 40h
0x1801bf671  mov     r8d, cs:?g_NextFormatStatusBuffer@@3KA; ulong g_NextFormatStatusBuffer
0x1801bf678  mov     ebp, ecx
0x1801bf67a  dec     r8d
0x1801bf67d  mov     eax, ecx
0x1801bf67f  and     r8d, 1
0x1801bf683  mov     ecx, 0C0000000h
0x1801bf688  and     eax, ecx
0x1801bf68a  mov     cs:?g_NextFormatStatusBuffer@@3KA, r8d; ulong g_NextFormatStatusBuffer
0x1801bf691  cmp     eax, ecx
0x1801bf693  setnz   dl
0x1801bf696  bt      ebp, 1Ch
0x1801bf69a  setnb   al
0x1801bf69d  xor     r15d, r15d
0x1801bf6a0  test    al, dl
0x1801bf6a2  jz      short loc_1801BF6D2
0x1801bf6a4  lea     eax, [rbp-834h]
0x1801bf6aa  cmp     eax, 383h
0x1801bf6af  ja      short loc_1801BF6BA
0x1801bf6b1  lea     rbx, aNetmsgDll; "netmsg.dll"
0x1801bf6b8  jmp     short loc_1801BF6DD
0x1801bf6ba  lea     eax, [rbp-2710h]
0x1801bf6c0  cmp     eax, 96h
0x1801bf6c5  jbe     short loc_1801BF6CD
0x1801bf6c7  lea     eax, [rbp-2AF8h]
0x1801bf6cd  mov     rbx, r15
0x1801bf6d0  jmp     short loc_1801BF6DD
0x1801bf6d2  btr     ebp, 1Ch
0x1801bf6d6  lea     rbx, aNtdllDll_1; "ntdll.dll"
0x1801bf6dd  cmp     ebp, 0C0000048h
0x1801bf6e3  lea     rax, aTheProcessThat; "The process that you are attempting to "...
0x1801bf6ea  cmovnz  rax, r15
0x1801bf6ee  test    rax, rax
0x1801bf6f1  jnz     loc_1801BF901
0x1801bf6f7  mov     r14d, r8d
0x1801bf6fa  lea     rcx, ?g_FormatStatusBuffer@@3PAY0EAA@GA; ushort (near * g_FormatStatusBuffer)[1024]
0x1801bf701  shl     r14, 0Bh
0x1801bf705  mov     esi, r15d
0x1801bf708  add     r14, rcx
0x1801bf70b  test    rbx, rbx
0x1801bf70e  jz      loc_1801BF867
0x1801bf714  mov     rcx, rbx; lpModuleName
0x1801bf717  call    cs:__imp_GetModuleHandleW
0x1801bf71d  mov     rdi, rax
0x1801bf720  test    rax, rax
0x1801bf723  jnz     short loc_1801BF73B
0x1801bf725  xor     r8d, r8d; dwFlags
0x1801bf728  xor     edx, edx; hFile
0x1801bf72a  mov     rcx, rbx; lpLibFileName
0x1801bf72d  call    cs:__imp_LoadLibraryExW
0x1801bf733  mov     rdi, rax
0x1801bf736  mov     esi, 1
0x1801bf73b  mov     rax, rdi
0x1801bf73e  mov     [rsp+68h+arg_18], r15
0x1801bf746  neg     rax
0x1801bf749  sbb     ebx, ebx
0x1801bf74b  and     ebx, 800h
0x1801bf751  add     ebx, 1000h
0x1801bf757  test    rdi, rdi
0x1801bf75a  jz      loc_1801BF877
0x1801bf760  lea     rcx, ?g_NtDllCallsDesc@@3U_DYNAMIC_CALLS_DESC@@C; _DYNAMIC_CALLS_DESC volatile g_NtDllCallsDesc
0x1801bf767  call    LoadDynamicCalls
0x1801bf76c  test    eax, eax
0x1801bf76e  jnz     loc_1801BF877
0x1801bf774  mov     rax, cs:qword_1802ECC40
0x1801bf77b  test    rax, rax
0x1801bf77e  jz      loc_1801BF877
0x1801bf784  mov     rax, cs:qword_1802ECC40
0x1801bf78b  lea     rcx, [rsp+68h+arg_18]
0x1801bf793  xor     r8d, r8d
0x1801bf796  mov     [rsp+68h+lpBuffer], rcx
0x1801bf79b  mov     r9d, ebp
0x1801bf79e  mov     rcx, rdi
0x1801bf7a1  lea     edx, [r8+0Bh]
0x1801bf7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bf7aa  test    eax, eax
0x1801bf7ac  js      loc_1801BF877
0x1801bf7b2  mov     r9, [rsp+68h+arg_18]
0x1801bf7ba  test    r9, r9
0x1801bf7bd  jz      loc_1801BF877
0x1801bf7c3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1801bf7c7  test    byte ptr [r9+2], 1
0x1801bf7cc  jz      short loc_1801BF802
0x1801bf7ce  lea     rdx, [r9+4]; Src
0x1801bf7d2  mov     rax, rbp
0x1801bf7d5  inc     rax
0x1801bf7d8  cmp     [rdx+rax*2], r15w
0x1801bf7dd  jnz     short loc_1801BF7D5
0x1801bf7df  cmp     eax, 400h
0x1801bf7e4  mov     ecx, 3FFh
0x1801bf7e9  cmovnb  eax, ecx
0x1801bf7ec  mov     rcx, r14; void *
0x1801bf7ef  lea     rbx, [rax+rax]
0x1801bf7f3  mov     r8, rbx; Size
0x1801bf7f6  call    memcpy_0
0x1801bf7fb  mov     [rbx+r14], r15w
0x1801bf800  jmp     short loc_1801BF85B
0x1801bf802  test    byte ptr [r9+2], 2
0x1801bf807  jz      short loc_1801BF843
0x1801bf809  mov     [rsp+68h+arg_0], r15d
0x1801bf80e  add     r9, 4
0x1801bf812  mov     rax, rbp
0x1801bf815  inc     rax
0x1801bf818  cmp     [r9+rax], r15b
0x1801bf81c  jnz     short loc_1801BF815
0x1801bf81e  inc     eax
0x1801bf820  lea     r8, [rsp+68h+arg_0]
0x1801bf825  mov     edx, 400h
0x1801bf82a  mov     dword ptr [rsp+68h+lpBuffer], eax
0x1801bf82e  mov     rcx, r14
0x1801bf831  call    cs:__imp_RtlUTF8ToUnicodeN
0x1801bf837  test    eax, eax
0x1801bf839  jns     short loc_1801BF85B
0x1801bf83b  mov     r9, [rsp+68h+arg_18]
0x1801bf843  add     r9, 4
0x1801bf847  lea     r8, aS_14; "%S"
0x1801bf84e  mov     edx, 400h
0x1801bf853  mov     rcx, r14
0x1801bf856  call    PrintStringW
0x1801bf85b  inc     rbp
0x1801bf85e  cmp     [r14+rbp*2], r15w
0x1801bf863  jnz     short loc_1801BF85B
0x1801bf865  jmp     short loc_1801BF8A5
0x1801bf867  mov     ebx, 1000h
0x1801bf86c  mov     [rsp+68h+arg_18], r15
0x1801bf874  mov     rdi, r15
0x1801bf877  mov     [rsp+68h+Arguments], r15; Arguments
0x1801bf87c  bts     ebx, 9
0x1801bf880  mov     ecx, ebx; dwFlags
0x1801bf882  mov     [rsp+68h+nSize], 400h; nSize
0x1801bf88a  xor     r9d, r9d; dwLanguageId
0x1801bf88d  mov     [rsp+68h+lpBuffer], r14; lpBuffer
0x1801bf892  mov     r8d, ebp; dwMessageId
0x1801bf895  mov     rdx, rdi; lpSource
0x1801bf898  call    cs:__imp_FormatMessageW
0x1801bf89e  mov     ebp, eax
0x1801bf8a0  test    rdi, rdi
0x1801bf8a3  jz      short loc_1801BF8B2
0x1801bf8a5  test    esi, esi
0x1801bf8a7  jz      short loc_1801BF8B2
0x1801bf8a9  mov     rcx, rdi; hLibModule
0x1801bf8ac  call    cs:__imp_FreeLibrary
0x1801bf8b2  test    ebp, ebp
0x1801bf8b4  jz      short loc_1801BF8FA
0x1801bf8b6  movzx   eax, word ptr [r14]
0x1801bf8ba  test    ax, ax
0x1801bf8bd  jz      short loc_1801BF8E0
0x1801bf8bf  mov     rbx, r14
0x1801bf8c2  movzx   ecx, ax; C
0x1801bf8c5  call    cs:__imp_iswprint
0x1801bf8cb  test    eax, eax
0x1801bf8cd  jnz     short loc_1801BF8D4
0x1801bf8cf  mov     word ptr [rbx], 20h ; ' '
0x1801bf8d4  add     rbx, 2
0x1801bf8d8  movzx   eax, word ptr [rbx]
0x1801bf8db  test    ax, ax
0x1801bf8de  jnz     short loc_1801BF8C2
0x1801bf8e0  dec     ebp
0x1801bf8e2  movzx   ecx, word ptr [r14+rbp*2]
0x1801bf8e7  call    cs:__imp__o_iswspace
0x1801bf8ed  test    eax, eax
0x1801bf8ef  jz      short loc_1801BF912
0x1801bf8f1  mov     [r14+rbp*2], r15w
0x1801bf8f6  test    ebp, ebp
0x1801bf8f8  jnz     short loc_1801BF8E0
0x1801bf8fa  lea     rax, aUnableToGetErr; "<Unable to get error code text>"
0x1801bf901  mov     rbx, [rsp+68h+arg_8]
0x1801bf906  add     rsp, 40h
0x1801bf90a  pop     r15
0x1801bf90c  pop     r14
0x1801bf90e  pop     rdi
0x1801bf90f  pop     rsi
0x1801bf910  pop     rbp
0x1801bf911  retn
0x1801bf912  mov     rax, r14
0x1801bf915  jmp     short loc_1801BF901
```
