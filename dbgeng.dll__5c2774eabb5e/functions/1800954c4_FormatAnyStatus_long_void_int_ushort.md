# FormatAnyStatus(long,void *,int *,ushort * *)

- ea: `0x1800954c4`
- end: `0x1800957dd`
- name: `?FormatAnyStatus@@YAPEBGJPEAXPEAHPEAPEAG@Z`
- size: `793`
- prototype: `const unsigned __int16 *__fastcall(DWORD dwMessageId, va_list *Arguments, int *, unsigned __int16 **)`
- caller_count: `33`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180096068`
- `0x180096320`
- `0x1800a3a00`
- `0x1800da60c`
- `0x1800e770c`
- `0x1800e846c`
- `0x1800eb6bc`
- `0x180186b00`
- `0x180186cc0`
- `0x180186eb0`
- `0x180188e20`
- `0x180189020`
- `0x180189190`
- `0x1801a46ac`
- `0x1801a5544`
- `0x1801ad2f8`
- `0x1801e9fd0`
- `0x1801ea1d0`
- `0x1801f0830`
- `0x1801f09e0`
- `0x1801f2610`
- `0x1801f2c10`
- `0x1801f3380`
- `0x1801f5210`
- `0x1801f7bd0`
- `0x1801fc824`
- `0x1801fcd2c`
- `0x18021ca70`
- `0x180247e88`
- `0x180281460`
- `0x1802d0bd0`
- `0x1803a9170`
- `0x1803a9350`

## callees

- `0x180073230`
- `0x1800954c4`
- `0x1800986ec`
- `0x1800c3810`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!iswprint` at `0x180095778`
- `api-ms-win-crt-string-l1-1-0!iswprint` at `0x180095778`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18009579f`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18009579f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18009575a`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18009575a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800955a0`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800955a0`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180095584`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180095584`
- `api-ms-win-core-misc-l1-1-0!FormatMessageW` at `0x180095601`
- `api-ms-win-core-misc-l1-1-0!FormatMessageW` at `0x18009573f`
- `api-ms-win-core-misc-l1-1-0!FormatMessageW` at `0x180095601`
- `api-ms-win-core-misc-l1-1-0!FormatMessageW` at `0x18009573f`
- `ntdll!RtlUTF8ToUnicodeN` at `0x1800956e5`
- `ntdll!RtlUTF8ToUnicodeN` at `0x1800956e5`

## string_xrefs

- `0x180095554`: `The process that you are attempting to attach to is already being debugged. Only one debugger can be invasively attached to a process at a time. A non-invasive attach is still possible when another debugger is attached.`
- `0x180095547`: `ntdll.dll`
- `0x180095522`: `netmsg.dll`

## pseudocode

```c
WCHAR *__fastcall FormatAnyStatus(DWORD dwMessageId, va_list *Arguments, int *a3, unsigned __int16 **a4)
{
  DWORD v4; // esi
  unsigned int v5; // r9d
  const WCHAR *v7; // rdi
  WCHAR *result; // rax
  int v9; // r12d
  WCHAR *lpBuffer; // rbx
  HMODULE ModuleHandleW; // rbp
  int v12; // r14d
  DWORD v13; // edi
  wint_t v14; // ax
  WCHAR *v15; // rsi

  v4 = dwMessageId;
  v5 = ((_BYTE)g_NextFormatStatusBuffer - 1) & 1;
  g_NextFormatStatusBuffer = v5;
  if ( (dwMessageId & 0xC0000000) != -1073741824 && (dwMessageId & 0x10000000) == 0 )
  {
    if ( dwMessageId - 2100 > 0x383 )
      v7 = 0;
    else
      v7 = L"netmsg.dll";
  }
  else
  {
    v4 = dwMessageId & 0xEFFFFFFF;
    v7 = L"ntdll.dll";
  }
  result = L"The process that you are attempting to attach to is already being debugged. Only one debugger can be invasive"
            "ly attached to a process at a time. A non-invasive attach is still possible when another debugger is attached.";
  if ( v4 != -1073741752 )
    result = 0;
  if ( !result )
  {
    v9 = 0;
    lpBuffer = (WCHAR *)&(&g_FormatStatusBuffer)[256 * (unsigned __int64)v5];
    if ( v7 )
    {
      ModuleHandleW = GetModuleHandleW(v7);
      if ( !ModuleHandleW )
      {
        ModuleHandleW = LoadLibraryExW(v7, 0, 0);
        v9 = 1;
      }
      v12 = ModuleHandleW != 0 ? 6144 : 4096;
    }
    else
    {
      v12 = 4096;
      ModuleHandleW = 0;
    }
    if ( !Arguments || (v13 = FormatMessageW(v12 | 0x2000, ModuleHandleW, v4, 0, lpBuffer, 0x400u, Arguments)) == 0 )
    {
      if ( ModuleHandleW )
        LoadDynamicCalls(&g_NtDllCallsDesc);
      v13 = FormatMessageW(v12 | 0x200, ModuleHandleW, v4, 0, lpBuffer, 0x400u, 0);
    }
    if ( ModuleHandleW && v9 )
      FreeLibrary(ModuleHandleW);
    if ( v13 )
    {
      v14 = *lpBuffer;
      if ( *lpBuffer )
      {
        v15 = lpBuffer;
        do
        {
          if ( !iswprint(v14) )
            *v15 = 32;
          v14 = *++v15;
        }
        while ( *v15 );
      }
      while ( iswspace(lpBuffer[--v13]) )
      {
        lpBuffer[v13] = 0;
        if ( !v13 )
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
0x1800954c4  mov     [rsp+arg_8], rbx
0x1800954c9  mov     [rsp+arg_18], r9
0x1800954ce  push    rbp
0x1800954cf  push    rsi
0x1800954d0  push    rdi
0x1800954d1  push    r12
0x1800954d3  push    r13
0x1800954d5  push    r14
0x1800954d7  push    r15
0x1800954d9  sub     rsp, 40h
0x1800954dd  mov     r9d, cs:?g_NextFormatStatusBuffer@@3KA; ulong g_NextFormatStatusBuffer
0x1800954e4  mov     esi, ecx
0x1800954e6  dec     r9d
0x1800954e9  mov     eax, ecx
0x1800954eb  and     r9d, 1
0x1800954ef  mov     ecx, 0C0000000h
0x1800954f4  and     eax, ecx
0x1800954f6  mov     cs:?g_NextFormatStatusBuffer@@3KA, r9d; ulong g_NextFormatStatusBuffer
0x1800954fd  cmp     eax, ecx
0x1800954ff  mov     r15, rdx
0x180095502  setnz   r8b
0x180095506  bt      esi, 1Ch
0x18009550a  setnb   al
0x18009550d  xor     r13d, r13d
0x180095510  test    al, r8b
0x180095513  jz      short loc_180095543
0x180095515  lea     eax, [rsi-834h]
0x18009551b  cmp     eax, 383h
0x180095520  ja      short loc_18009552B
0x180095522  lea     rdi, LibFileName; "netmsg.dll"
0x180095529  jmp     short loc_18009554E
0x18009552b  lea     eax, [rsi-2710h]
0x180095531  cmp     eax, 96h
0x180095536  jbe     short loc_18009553E
0x180095538  lea     eax, [rsi-2AF8h]
0x18009553e  mov     rdi, r13
0x180095541  jmp     short loc_18009554E
0x180095543  btr     esi, 1Ch
0x180095547  lea     rdi, aNtdllDll_1; "ntdll.dll"
0x18009554e  cmp     esi, 0C0000048h
0x180095554  lea     rax, aTheProcessThat; "The process that you are attempting to "...
0x18009555b  cmovnz  rax, r13
0x18009555f  test    rax, rax
0x180095562  jnz     loc_1800957BF
0x180095568  mov     ebx, r9d
0x18009556b  lea     rcx, ?g_FormatStatusBuffer@@3PAY0EAA@GA; ushort (near * g_FormatStatusBuffer)[1024]
0x180095572  shl     rbx, 0Bh
0x180095576  mov     r12d, r13d
0x180095579  add     rbx, rcx
0x18009557c  test    rdi, rdi
0x18009557f  jz      short loc_1800955CE
0x180095581  mov     rcx, rdi; lpModuleName
0x180095584  call    cs:__imp_GetModuleHandleW
0x18009558b  nop     dword ptr [rax+rax+00h]
0x180095590  mov     rbp, rax
0x180095593  test    rax, rax
0x180095596  jnz     short loc_1800955B5
0x180095598  xor     r8d, r8d; dwFlags
0x18009559b  xor     edx, edx; hFile
0x18009559d  mov     rcx, rdi; lpLibFileName
0x1800955a0  call    cs:__imp_LoadLibraryExW
0x1800955a7  nop     dword ptr [rax+rax+00h]
0x1800955ac  mov     rbp, rax
0x1800955af  mov     r12d, 1
0x1800955b5  mov     rax, rbp
0x1800955b8  neg     rax
0x1800955bb  sbb     r14d, r14d
0x1800955be  and     r14d, 800h
0x1800955c5  add     r14d, 1000h
0x1800955cc  jmp     short loc_1800955D7
0x1800955ce  mov     r14d, 1000h
0x1800955d4  mov     rbp, r13
0x1800955d7  test    r15, r15
0x1800955da  jz      short loc_180095618
0x1800955dc  mov     [rsp+78h+Arguments], r15; Arguments
0x1800955e1  mov     ecx, r14d
0x1800955e4  mov     r15d, 400h
0x1800955ea  bts     ecx, 0Dh; dwFlags
0x1800955ee  mov     [rsp+78h+nSize], r15d; nSize
0x1800955f3  xor     r9d, r9d; dwLanguageId
0x1800955f6  mov     r8d, esi; dwMessageId
0x1800955f9  mov     [rsp+78h+lpBuffer], rbx; lpBuffer
0x1800955fe  mov     rdx, rbp; lpSource
0x180095601  call    cs:__imp_FormatMessageW
0x180095608  nop     dword ptr [rax+rax+00h]
0x18009560d  mov     edi, eax
0x18009560f  test    eax, eax
0x180095611  jz      short loc_18009561E
0x180095613  jmp     loc_18009574D
0x180095618  mov     r15d, 400h
0x18009561e  mov     [rsp+78h+arg_18], r13
0x180095626  test    rbp, rbp
0x180095629  jz      loc_18009571F
0x18009562f  lea     rcx, ?g_NtDllCallsDesc@@3U_DYNAMIC_CALLS_DESC@@C; _DYNAMIC_CALLS_DESC volatile g_NtDllCallsDesc
0x180095636  call    LoadDynamicCalls
0x18009563b  test    eax, eax
0x18009563d  jnz     loc_18009571F
0x180095643  mov     rax, cs:qword_18082DD00
0x18009564a  test    rax, rax
0x18009564d  jz      loc_18009571F
0x180095653  mov     rax, cs:qword_18082DD00
0x18009565a  lea     rcx, [rsp+78h+arg_18]
0x180095662  xor     r8d, r8d
0x180095665  mov     [rsp+78h+lpBuffer], rcx
0x18009566a  mov     r9d, esi
0x18009566d  mov     rcx, rbp
0x180095670  lea     edx, [r8+0Bh]
0x180095674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095679  test    eax, eax
0x18009567b  js      loc_18009571F
0x180095681  mov     r9, [rsp+78h+arg_18]
0x180095689  test    r9, r9
0x18009568c  jz      loc_18009571F
0x180095692  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180095696  test    byte ptr [r9+2], 1
0x18009569b  jz      short loc_1800956B2
0x18009569d  lea     rdx, [r9+4]
0x1800956a1  or      r8d, 0FFFFFFFFh
0x1800956a5  mov     r9d, r15d
0x1800956a8  mov     rcx, rbx; void *
0x1800956ab  call    CopyNStringW
0x1800956b0  jmp     short loc_180095713
0x1800956b2  test    byte ptr [r9+2], 2
0x1800956b7  jz      short loc_1800956FD
0x1800956b9  mov     [rsp+78h+arg_0], r13d
0x1800956c1  add     r9, 4
0x1800956c5  mov     rax, rdi
0x1800956c8  inc     rax
0x1800956cb  cmp     [r9+rax], r13b
0x1800956cf  jnz     short loc_1800956C8
0x1800956d1  inc     eax
0x1800956d3  lea     r8, [rsp+78h+arg_0]
0x1800956db  mov     edx, r15d
0x1800956de  mov     dword ptr [rsp+78h+lpBuffer], eax
0x1800956e2  mov     rcx, rbx
0x1800956e5  call    cs:__imp_RtlUTF8ToUnicodeN
0x1800956ec  nop     dword ptr [rax+rax+00h]
0x1800956f1  test    eax, eax
0x1800956f3  jns     short loc_180095713
0x1800956f5  mov     r9, [rsp+78h+arg_18]
0x1800956fd  add     r9, 4
0x180095701  lea     r8, aS_43; "%S"
0x180095708  mov     edx, r15d; BufferCount
0x18009570b  mov     rcx, rbx; Buffer
0x18009570e  call    PrintStringW
0x180095713  inc     rdi
0x180095716  cmp     [rbx+rdi*2], r13w
0x18009571b  jnz     short loc_180095713
0x18009571d  jmp     short loc_180095752
0x18009571f  bts     r14d, 9
0x180095724  mov     [rsp+78h+Arguments], r13; Arguments
0x180095729  mov     ecx, r14d; dwFlags
0x18009572c  mov     [rsp+78h+nSize], r15d; nSize
0x180095731  xor     r9d, r9d; dwLanguageId
0x180095734  mov     [rsp+78h+lpBuffer], rbx; lpBuffer
0x180095739  mov     r8d, esi; dwMessageId
0x18009573c  mov     rdx, rbp; lpSource
0x18009573f  call    cs:__imp_FormatMessageW
0x180095746  nop     dword ptr [rax+rax+00h]
0x18009574b  mov     edi, eax
0x18009574d  test    rbp, rbp
0x180095750  jz      short loc_180095766
0x180095752  test    r12d, r12d
0x180095755  jz      short loc_180095766
0x180095757  mov     rcx, rbp; hLibModule
0x18009575a  call    cs:__imp_FreeLibrary
0x180095761  nop     dword ptr [rax+rax+00h]
0x180095766  test    edi, edi
0x180095768  jz      short loc_1800957B8
0x18009576a  movzx   eax, word ptr [rbx]
0x18009576d  test    ax, ax
0x180095770  jz      short loc_180095799
0x180095772  mov     rsi, rbx
0x180095775  movzx   ecx, ax; C
0x180095778  call    cs:__imp_iswprint
0x18009577f  nop     dword ptr [rax+rax+00h]
0x180095784  test    eax, eax
0x180095786  jnz     short loc_18009578D
0x180095788  mov     word ptr [rsi], 20h ; ' '
0x18009578d  add     rsi, 2
0x180095791  movzx   eax, word ptr [rsi]
0x180095794  test    ax, ax
0x180095797  jnz     short loc_180095775
0x180095799  dec     edi
0x18009579b  movzx   ecx, word ptr [rbx+rdi*2]; C
0x18009579f  call    cs:__imp_iswspace
0x1800957a6  nop     dword ptr [rax+rax+00h]
0x1800957ab  test    eax, eax
0x1800957ad  jz      short loc_1800957D8
0x1800957af  mov     [rbx+rdi*2], r13w
0x1800957b4  test    edi, edi
0x1800957b6  jnz     short loc_180095799
0x1800957b8  lea     rax, aUnableToGetErr; "<Unable to get error code text>"
0x1800957bf  mov     rbx, [rsp+78h+arg_8]
0x1800957c7  add     rsp, 40h
0x1800957cb  pop     r15
0x1800957cd  pop     r14
0x1800957cf  pop     r13
0x1800957d1  pop     r12
0x1800957d3  pop     rdi
0x1800957d4  pop     rsi
0x1800957d5  pop     rbp
0x1800957d6  retn
0x1800957d8  mov     rax, rbx
0x1800957db  jmp     short loc_1800957BF
```
