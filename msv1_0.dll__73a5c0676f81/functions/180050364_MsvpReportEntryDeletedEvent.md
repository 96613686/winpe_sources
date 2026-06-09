# MsvpReportEntryDeletedEvent

- ea: `0x180050364`
- end: `0x18005064e`
- name: `MsvpReportEntryDeletedEvent`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180041bb8`

## callees

- `0x18002ee7c`
- `0x18002fb50`
- `0x180030914`
- `0x18005021c`
- `0x180050364`
- `0x180050b08`
- `0x180050d08`
- `0x18006b7f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800504e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800504e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050542`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800504bb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800504bb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180050526`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180050526`

## string_xrefs

- `0x1800504b2`: `ntdll.dll`

## pseudocode

```c
void *__fastcall MsvpReportEntryDeletedEvent(__int64 a1, __int64 a2, int a3, __int64 a4, int a5, __int64 a6)
{
  _QWORD *v10; // rcx
  void *result; // rax
  HMODULE Library; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  DWORD LastError; // eax
  int nSize; // [rsp+28h] [rbp-D8h]
  int Arguments; // [rsp+30h] [rbp-D0h]
  size_t Size; // [rsp+50h] [rbp-B0h]
  _QWORD v19[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v20[2]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v21; // [rsp+80h] [rbp-80h]
  wchar_t lpBuffer[264]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v23[296]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wchar_t Buffer[280]; // [rsp+4F0h] [rbp+3F0h] BYREF

  *(_OWORD *)v20 = 0;
  v21 = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
    {
      WPP_SF_ZZDZ(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a2, a3, a4);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x4000) != 0 )
    {
      v19[0] = a6;
      v19[1] = (unsigned __int16)a5;
      WPP_SF_dD_HEX_(v10[2], a2, a3, a5, a5, (__int64)v19);
    }
  }
  if ( *(_QWORD *)&MsvpGlobalEventLogHandle || (result = (void *)MsvpInitializeEventLogHandle(), (int)result >= 0) )
  {
    lpBuffer[259] = 0;
    v23[291] = 0;
    Buffer[275] = 0;
    snwprintf_s(Buffer, 0x114u, 0x113u, L"%wZ@%wZ", a1, a2);
    v20[0] = (__int64)Buffer;
    v20[1] = *(_QWORD *)(a4 + 8);
    Library = (HMODULE)lpSource;
    if ( lpSource || (Library = LoadLibraryExW(L"ntdll.dll", 0, 0), (lpSource = Library) != 0) )
    {
      if ( !FormatMessageW(0x1A00u, Library, a3, 0, lpBuffer, 0x103u, 0) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_f868da5819ea3f687010c6986c962ee6_Traceguids, LastError);
        }
        wcscpy(lpBuffer, L" ");
      }
      if ( a3 >= 0 )
      {
        Arguments = a3;
        nSize = a3;
        snwprintf_s(v23, 0x124u, 0x123u, L"\"%ws (%#x, %d)\"");
      }
      else
      {
        nSize = a3;
        snwprintf_s(v23, 0x124u, 0x123u, L"\"%ws (%#x)\"");
      }
      LODWORD(Size) = a5;
      v21 = v23;
      result = (void *)NetpEventlogWriteEx3(
                         MsvpGlobalEventLogHandle,
                         4,
                         4,
                         45057,
                         (int)lpBuffer,
                         nSize,
                         Arguments,
                         (__int64)v20,
                         3u,
                         a6,
                         Size);
      if ( (_DWORD)result )
      {
        if ( (_DWORD)result != 183 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v14 = 17;
            return (void *)WPP_SF_d(v13[2], v14, WPP_f868da5819ea3f687010c6986c962ee6_Traceguids, (unsigned int)result);
          }
        }
      }
    }
    else
    {
      result = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LODWORD(result) = GetLastError();
        v13 = WPP_GLOBAL_Control;
        v14 = 15;
        return (void *)WPP_SF_d(v13[2], v14, WPP_f868da5819ea3f687010c6986c962ee6_Traceguids, (unsigned int)result);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180050364  push    rbp
0x180050366  push    rbx
0x180050367  push    rsi
0x180050368  push    rdi
0x180050369  push    r12
0x18005036b  push    r13
0x18005036d  push    r14
0x18005036f  push    r15
0x180050371  lea     rbp, [rsp-638h]
0x180050379  sub     rsp, 738h
0x180050380  mov     rax, cs:__security_cookie
0x180050387  xor     rax, rsp
0x18005038a  mov     [rbp+670h+var_50], rax
0x180050391  mov     edi, dword ptr [rbp+670h+arg_20]
0x180050397  xorps   xmm0, xmm0
0x18005039a  mov     r12, [rbp+670h+arg_28]
0x1800503a1  xor     eax, eax
0x1800503a3  movups  xmmword ptr [rsp+770h+var_700], xmm0
0x1800503a8  mov     [rbp+670h+var_6F0], rax
0x1800503ac  mov     r15, r9
0x1800503af  mov     ebx, r8d
0x1800503b2  mov     r14, rdx
0x1800503b5  mov     rsi, rcx
0x1800503b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800503bf  lea     r13, WPP_GLOBAL_Control
0x1800503c6  cmp     rcx, r13
0x1800503c9  jz      short loc_18005043A
0x1800503cb  test    dword ptr [rcx+1Ch], 4000h
0x1800503d2  jz      short loc_1800503F5
0x1800503d4  mov     rcx, [rcx+10h]
0x1800503d8  mov     [rsp+770h+Arguments], r9
0x1800503dd  mov     r9, rsi
0x1800503e0  mov     [rsp+770h+nSize], ebx
0x1800503e4  mov     [rsp+770h+lpBuffer], rdx
0x1800503e9  call    WPP_SF_ZZDZ
0x1800503ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800503f5  cmp     rcx, r13
0x1800503f8  jz      short loc_18005043A
0x1800503fa  test    dword ptr [rcx+1Ch], 4000h
0x180050401  jz      short loc_18005043A
0x180050403  xorps   xmm0, xmm0
0x180050406  lea     rax, [rsp+770h+var_710]
0x18005040b  movups  [rsp+770h+var_710], xmm0
0x180050410  mov     qword ptr [rsp+770h+var_710], r12
0x180050415  mov     r9d, edi
0x180050418  mov     word ptr [rsp+770h+var_710+8], di
0x18005041d  movaps  xmm0, [rsp+770h+var_710]
0x180050422  movdqa  [rsp+770h+var_710], xmm0
0x180050428  mov     rcx, [rcx+10h]
0x18005042c  mov     qword ptr [rsp+770h+nSize], rax
0x180050431  mov     dword ptr [rsp+770h+lpBuffer], edi
0x180050435  call    WPP_SF_dD_HEX_
0x18005043a  cmp     cs:?MsvpGlobalEventLogHandle@@3PEAXEA, 0; void * MsvpGlobalEventLogHandle
0x180050442  jnz     short loc_180050451
0x180050444  call    ?MsvpInitializeEventLogHandle@@YAJXZ; MsvpInitializeEventLogHandle(void)
0x180050449  test    eax, eax
0x18005044b  js      loc_18005062B
0x180050451  xor     eax, eax
0x180050453  mov     qword ptr [rsp+770h+nSize], r14
0x180050458  mov     edx, 114h; BufferCount
0x18005045d  mov     [rbp+670h+var_4DA], ax
0x180050464  lea     r9, aWzWz; "%wZ@%wZ"
0x18005046b  mov     [rbp+670h+var_28A], ax
0x180050472  lea     rcx, [rbp+670h+Buffer]; Buffer
0x180050479  mov     [rbp+670h+var_5A], ax
0x180050480  mov     [rsp+770h+lpBuffer], rsi
0x180050485  lea     r8d, [rdx-1]; MaxCount
0x180050489  call    _snwprintf_s
0x18005048e  lea     rax, [rbp+670h+Buffer]
0x180050495  mov     [rsp+770h+var_700], rax
0x18005049a  mov     rax, [r15+8]
0x18005049e  mov     [rsp+770h+var_700+8], rax
0x1800504a3  mov     rax, cs:lpSource
0x1800504aa  test    rax, rax
0x1800504ad  jnz     short loc_1800504FE
0x1800504af  xor     r8d, r8d; dwFlags
0x1800504b2  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800504b9  xor     edx, edx; hFile
0x1800504bb  call    cs:__imp_LoadLibraryExW
0x1800504c1  mov     cs:lpSource, rax
0x1800504c8  test    rax, rax
0x1800504cb  jnz     short loc_1800504FE
0x1800504cd  mov     rax, cs:WPP_GLOBAL_Control
0x1800504d4  cmp     rax, r13
0x1800504d7  jz      loc_18005062B
0x1800504dd  test    byte ptr [rax+1Ch], 1
0x1800504e1  jz      loc_18005062B
0x1800504e7  call    cs:__imp_GetLastError
0x1800504ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800504f4  mov     edx, 0Fh
0x1800504f9  jmp     loc_180050618
0x1800504fe  lea     rcx, [rbp+670h+var_6E0]
0x180050502  mov     [rsp+770h+Arguments], 0; Arguments
0x18005050b  mov     [rsp+770h+nSize], 103h; nSize
0x180050513  xor     r9d, r9d; dwLanguageId
0x180050516  mov     [rsp+770h+lpBuffer], rcx; lpBuffer
0x18005051b  mov     r8d, ebx; dwMessageId
0x18005051e  mov     ecx, 1A00h; dwFlags
0x180050523  mov     rdx, rax; lpSource
0x180050526  call    cs:__imp_FormatMessageW
0x18005052c  test    eax, eax
0x18005052e  jnz     short loc_18005056E
0x180050530  mov     rax, cs:WPP_GLOBAL_Control
0x180050537  cmp     rax, r13
0x18005053a  jz      short loc_180050567
0x18005053c  test    byte ptr [rax+1Ch], 1
0x180050540  jz      short loc_180050567
0x180050542  call    cs:__imp_GetLastError
0x180050548  mov     rcx, cs:WPP_GLOBAL_Control
0x18005054f  lea     r8, WPP_f868da5819ea3f687010c6986c962ee6_Traceguids
0x180050556  mov     edx, 10h
0x18005055b  mov     r9d, eax
0x18005055e  mov     rcx, [rcx+10h]
0x180050562  call    WPP_SF_d
0x180050567  mov     dword ptr [rbp+670h+var_6E0], 20h ; ' '
0x18005056e  lea     rax, [rbp+670h+var_6E0]
0x180050572  mov     edx, 124h; BufferCount
0x180050577  lea     rcx, [rbp+670h+var_4D0]; Buffer
0x18005057e  lea     r8d, [rdx-1]; MaxCount
0x180050582  test    ebx, ebx
0x180050584  jns     short loc_18005059D
0x180050586  mov     [rsp+770h+nSize], ebx
0x18005058a  lea     r9, aWsX; "\"%ws (%#x)\""
0x180050591  mov     [rsp+770h+lpBuffer], rax
0x180050596  call    _snwprintf_s
0x18005059b  jmp     short loc_1800505B6
0x18005059d  mov     dword ptr [rsp+770h+Arguments], ebx; int
0x1800505a1  lea     r9, aWsXD; "\"%ws (%#x, %d)\""
0x1800505a8  mov     [rsp+770h+nSize], ebx; int
0x1800505ac  mov     [rsp+770h+lpBuffer], rax; int
0x1800505b1  call    _snwprintf_s
0x1800505b6  mov     rcx, cs:?MsvpGlobalEventLogHandle@@3PEAXEA; int
0x1800505bd  lea     rax, [rbp+670h+var_4D0]
0x1800505c4  mov     dword ptr [rsp+770h+Size], edi; Size
0x1800505c8  mov     edx, 4; int
0x1800505cd  mov     [rbp+670h+var_6F0], rax
0x1800505d1  mov     r9d, 0B001h; int
0x1800505d7  lea     rax, [rsp+770h+var_700]
0x1800505dc  mov     [rsp+770h+var_728], r12; __int64
0x1800505e1  mov     dword ptr [rsp+770h+var_730], 3; WORD
0x1800505e9  mov     r8d, edx; int
0x1800505ec  mov     [rsp+770h+var_738], rax; __int64
0x1800505f1  call    NetpEventlogWriteEx3
0x1800505f6  test    eax, eax
0x1800505f8  jz      short loc_18005062B
0x1800505fa  cmp     eax, 0B7h
0x1800505ff  jz      short loc_18005062B
0x180050601  mov     rcx, cs:WPP_GLOBAL_Control
0x180050608  cmp     rcx, r13
0x18005060b  jz      short loc_18005062B
0x18005060d  test    byte ptr [rcx+1Ch], 2
0x180050611  jz      short loc_18005062B
0x180050613  mov     edx, 11h
0x180050618  mov     rcx, [rcx+10h]
0x18005061c  lea     r8, WPP_f868da5819ea3f687010c6986c962ee6_Traceguids
0x180050623  mov     r9d, eax
0x180050626  call    WPP_SF_d
0x18005062b  mov     rcx, [rbp+670h+var_50]
0x180050632  xor     rcx, rsp; StackCookie
0x180050635  call    __security_check_cookie
0x18005063a  add     rsp, 738h
0x180050641  pop     r15
0x180050643  pop     r14
0x180050645  pop     r13
0x180050647  pop     r12
0x180050649  pop     rdi
0x18005064a  pop     rsi
0x18005064b  pop     rbx
0x18005064c  pop     rbp
0x18005064d  retn
```
