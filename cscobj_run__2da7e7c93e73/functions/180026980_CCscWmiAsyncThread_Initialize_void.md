# CCscWmiAsyncThread::_Initialize(void)

- ea: `0x180026980`
- end: `0x180026a53`
- name: `?_Initialize@CCscWmiAsyncThread@@AEAAJXZ`
- size: `211`
- prototype: `__int64 __fastcall(void **this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800267fc`

## callees

- `0x1800084e0`
- `0x180009864`
- `0x1800140c8`
- `0x180026980`
- `0x18002a270`
- `0x18002a7bc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800269c9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800269c9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026a30`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026a30`

## string_xrefs

- `0x1800269ae`: `%systemroot%\system32\cscobj.dll`

## pseudocode

```c
__int64 __fastcall CCscWmiAsyncThread::_Initialize(void **this)
{
  int Error; // ebx
  HMODULE LibraryW; // rax
  void *v4; // rdx
  UstVarLib *v5; // rcx
  HANDLE EventW; // rax
  UstVarLib *v7; // rcx
  LPCWSTR lpLibFileName; // [rsp+40h] [rbp+8h] BYREF

  Error = CscSec_OpenThreadTokenForAccessCheckAndImpersonation(this + 5);
  if ( Error >= 0 )
  {
    lpLibFileName = 0;
    Error = CscUtil_ExpandEnvironmentStringsAlloc(
              L"%systemroot%\\system32\\cscobj.dll",
              (unsigned __int16 **)&lpLibFileName);
    if ( Error >= 0 )
    {
      LibraryW = LoadLibraryW(lpLibFileName);
      this[4] = LibraryW;
      if ( !LibraryW )
      {
        Error = UstVarLib::ResultFromLastError(v5);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          WPP_SF_SD(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            14,
            (unsigned int)WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids,
            (_DWORD)lpLibFileName,
            Error);
      }
      CscUtil_HeapFree((void *)lpLibFileName, v4);
      if ( Error >= 0 )
      {
        EventW = CreateEventW(0, 1, 0, 0);
        this[6] = EventW;
        if ( !EventW )
          return (unsigned int)UstVarLib::ResultFromLastError(v7);
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180026980  mov     [rsp+arg_8], rbx
0x180026985  push    rsi
0x180026986  sub     rsp, 30h
0x18002698a  mov     rsi, rcx
0x18002698d  add     rcx, 28h ; '('; TokenHandle
0x180026991  call    ?CscSec_OpenThreadTokenForAccessCheckAndImpersonation@@YAJPEAPEAX@Z; CscSec_OpenThreadTokenForAccessCheckAndImpersonation(void * *)
0x180026996  mov     ebx, eax
0x180026998  test    eax, eax
0x18002699a  js      loc_180026A46
0x1800269a0  lea     rdx, [rsp+38h+lpLibFileName]; unsigned __int16 **
0x1800269a5  mov     [rsp+38h+lpLibFileName], 0
0x1800269ae  lea     rcx, aSystemrootSyst_0; "%systemroot%\\system32\\cscobj.dll"
0x1800269b5  call    ?CscUtil_ExpandEnvironmentStringsAlloc@@YAJPEBGPEAPEAG@Z; CscUtil_ExpandEnvironmentStringsAlloc(ushort const *,ushort * *)
0x1800269ba  mov     ebx, eax
0x1800269bc  test    eax, eax
0x1800269be  js      loc_180026A46
0x1800269c4  mov     rcx, [rsp+38h+lpLibFileName]; lpLibFileName
0x1800269c9  call    cs:__imp_LoadLibraryW
0x1800269cf  mov     [rsi+20h], rax
0x1800269d3  test    rax, rax
0x1800269d6  jnz     short loc_180026A16
0x1800269d8  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x1800269dd  mov     ebx, eax
0x1800269df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269e6  lea     rax, WPP_GLOBAL_Control
0x1800269ed  cmp     rcx, rax
0x1800269f0  jz      short loc_180026A16
0x1800269f2  test    byte ptr [rcx+1Ch], 2
0x1800269f6  jz      short loc_180026A16
0x1800269f8  mov     r9, [rsp+38h+lpLibFileName]
0x1800269fd  lea     r8, WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids
0x180026a04  mov     rcx, [rcx+10h]
0x180026a08  mov     edx, 0Eh
0x180026a0d  mov     [rsp+38h+var_18], ebx
0x180026a11  call    WPP_SF_SD
0x180026a16  mov     rcx, [rsp+38h+lpLibFileName]; lpMem
0x180026a1b  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180026a20  test    ebx, ebx
0x180026a22  js      short loc_180026A46
0x180026a24  xor     r9d, r9d; lpName
0x180026a27  xor     r8d, r8d; bInitialState
0x180026a2a  xor     ecx, ecx; lpEventAttributes
0x180026a2c  lea     edx, [r9+1]; bManualReset
0x180026a30  call    cs:__imp_CreateEventW
0x180026a36  mov     [rsi+30h], rax
0x180026a3a  test    rax, rax
0x180026a3d  jnz     short loc_180026A46
0x180026a3f  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x180026a44  mov     ebx, eax
0x180026a46  mov     eax, ebx
0x180026a48  mov     rbx, [rsp+38h+arg_8]
0x180026a4d  add     rsp, 30h
0x180026a51  pop     rsi
0x180026a52  retn
```
