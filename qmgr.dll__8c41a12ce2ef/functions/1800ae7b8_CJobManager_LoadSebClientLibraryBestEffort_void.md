# CJobManager::LoadSebClientLibraryBestEffort(void)

- ea: `0x1800ae7b8`
- end: `0x1800ae9f9`
- name: `?LoadSebClientLibraryBestEffort@CJobManager@@QEAA_NXZ`
- size: `577`
- prototype: `bool __fastcall(CJobManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c67c`

## callees

- `0x18009d024`
- `0x1800ae7b8`
- `0x1800b0fc0`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ae830`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ae830`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ae8ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ae936`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ae8ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ae936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae85d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae8be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae8c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae8d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae95c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae85d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae8be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae8c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae8d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae95c`

## string_xrefs

- `0x1800ae829`: `SystemEventsBrokerClient.dll`

## pseudocode

```c
bool __fastcall CJobManager::LoadSebClientLibraryBestEffort(CJobManager *this)
{
  HMODULE *v2; // rdi
  bool result; // al
  HMODULE Library; // rax
  unsigned int LastError; // ecx
  FARPROC ProcAddress; // rax
  unsigned int v7; // ecx
  FARPROC v8; // rax
  unsigned int v9; // ecx
  const ComError *v10; // [rsp+30h] [rbp-138h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-128h] BYREF
  __int128 v12; // [rsp+48h] [rbp-120h]
  unsigned int v13; // [rsp+58h] [rbp-110h]
  int v14; // [rsp+5Ch] [rbp-10Ch]
  int v15; // [rsp+60h] [rbp-108h]
  void **v16; // [rsp+A0h] [rbp-C8h] BYREF
  __int128 v17; // [rsp+A8h] [rbp-C0h]
  unsigned int v18; // [rsp+B8h] [rbp-B0h]
  int v19; // [rsp+BCh] [rbp-ACh]
  int v20; // [rsp+C0h] [rbp-A8h]
  void **v21; // [rsp+100h] [rbp-68h] BYREF
  __int128 v22; // [rsp+108h] [rbp-60h]
  unsigned int v23; // [rsp+118h] [rbp-50h]
  int v24; // [rsp+11Ch] [rbp-4Ch]
  int v25; // [rsp+120h] [rbp-48h]

  v2 = (HMODULE *)((char *)this + 1792);
  if ( *((_QWORD *)this + 224) )
    return 1;
  if ( *((_BYTE *)this + 1784) )
    return 0;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 273, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
  Library = LoadLibraryExW(L"SystemEventsBrokerClient.dll", 0, 0x800u);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    v2,
    Library);
  try
  {
    if ( !*v2 )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v12 = 0;
      pExceptionObject = &ComError::`vftable';
      v13 = LastError;
      v14 = 6216;
      v15 = 1;
      throw (ComError *)&pExceptionObject;
    }
    ProcAddress = GetProcAddress(*v2, "SebQueryEventPackage");
    *((_QWORD *)this + 226) = ProcAddress;
    if ( !ProcAddress )
    {
      if ( (int)GetLastError() > 0 )
        v7 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v7 = GetLastError();
      v17 = 0;
      v16 = &ComError::`vftable';
      v18 = v7;
      v19 = 6225;
      v20 = 1;
      throw (ComError *)&v16;
    }
    v8 = GetProcAddress(*v2, "SebSignalEvent");
    *((_QWORD *)this + 225) = v8;
    if ( !v8 )
    {
      if ( (int)GetLastError() > 0 )
        v9 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v9 = GetLastError();
      v22 = 0;
      v21 = &ComError::`vftable';
      v23 = v9;
      v24 = 6233;
      v25 = 1;
      throw (ComError *)&v21;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 274, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
    result = 1;
  }
  catch ( const ComError *v10 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      (char *)this + 1792,
      0);
    *((_BYTE *)this + 1784) = 1;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        275,
        &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids,
        *((unsigned int *)v10 + 6),
        *((_DWORD *)v10 + 7));
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800ae7b8  mov     [rsp+arg_8], rbx
0x1800ae7bd  mov     [rsp+arg_10], rsi
0x1800ae7c2  mov     [rsp+arg_0], rcx
0x1800ae7c7  push    rdi
0x1800ae7c8  sub     rsp, 160h
0x1800ae7cf  mov     rbx, rcx
0x1800ae7d2  lea     rdi, [rcx+700h]
0x1800ae7d9  cmp     qword ptr [rdi], 0
0x1800ae7dd  jz      short loc_1800AE7E6
0x1800ae7df  mov     al, 1
0x1800ae7e1  jmp     loc_1800AE9E3
0x1800ae7e6  cmp     byte ptr [rcx+6F8h], 0
0x1800ae7ed  jnz     loc_1800AE9E1
0x1800ae7f3  lea     rsi, WPP_GLOBAL_Control
0x1800ae7fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae801  cmp     rcx, rsi
0x1800ae804  jz      short loc_1800AE821
0x1800ae806  test    byte ptr [rcx+1Ch], 1
0x1800ae80a  jz      short loc_1800AE821
0x1800ae80c  mov     edx, 111h
0x1800ae811  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x1800ae818  mov     rcx, [rcx+10h]
0x1800ae81c  call    WPP_SF_
0x1800ae821  xor     edx, edx; hFile
0x1800ae823  mov     r8d, 800h; dwFlags
0x1800ae829  lea     rcx, aSystemeventsbr; "SystemEventsBrokerClient.dll"
0x1800ae830  call    cs:__imp_LoadLibraryExW
0x1800ae836  mov     rdx, rax
0x1800ae839  mov     rcx, rdi
0x1800ae83c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800ae841  mov     rcx, [rdi]; hModule
0x1800ae844  test    rcx, rcx
0x1800ae847  jnz     short loc_1800AE8A5
0x1800ae849  call    cs:__imp_GetLastError
0x1800ae84f  test    eax, eax
0x1800ae851  jg      short loc_1800AE85D
0x1800ae853  call    cs:__imp_GetLastError
0x1800ae859  mov     ecx, eax
0x1800ae85b  jmp     short loc_1800AE86C
0x1800ae85d  call    cs:__imp_GetLastError
0x1800ae863  movzx   ecx, ax
0x1800ae866  or      ecx, 80070000h
0x1800ae86c  xorps   xmm0, xmm0
0x1800ae86f  movups  [rsp+168h+var_120], xmm0
0x1800ae874  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800ae87b  mov     [rsp+168h+pExceptionObject], rax
0x1800ae880  mov     [rsp+168h+var_110], ecx
0x1800ae884  mov     [rsp+168h+var_10C], 1848h
0x1800ae88c  mov     [rsp+168h+var_108], 1
0x1800ae894  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800ae89b  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x1800ae8a0  call    _CxxThrowException_0
0x1800ae8a5  lea     rdx, aSebqueryeventp; "SebQueryEventPackage"
0x1800ae8ac  call    cs:__imp_GetProcAddress
0x1800ae8b2  mov     [rbx+710h], rax
0x1800ae8b9  test    rax, rax
0x1800ae8bc  jnz     short loc_1800AE92C
0x1800ae8be  call    cs:__imp_GetLastError
0x1800ae8c4  test    eax, eax
0x1800ae8c6  jg      short loc_1800AE8D2
0x1800ae8c8  call    cs:__imp_GetLastError
0x1800ae8ce  mov     ecx, eax
0x1800ae8d0  jmp     short loc_1800AE8E1
0x1800ae8d2  call    cs:__imp_GetLastError
0x1800ae8d8  movzx   ecx, ax
0x1800ae8db  or      ecx, 80070000h
0x1800ae8e1  xorps   xmm0, xmm0
0x1800ae8e4  movups  [rsp+168h+var_C0], xmm0
0x1800ae8ec  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800ae8f3  mov     [rsp+168h+var_C8], rax
0x1800ae8fb  mov     [rsp+168h+var_B0], ecx
0x1800ae902  mov     [rsp+168h+var_AC], 1851h
0x1800ae90d  mov     [rsp+168h+var_A8], 1
0x1800ae918  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800ae91f  lea     rcx, [rsp+168h+var_C8]; pExceptionObject
0x1800ae927  call    _CxxThrowException_0
0x1800ae92c  lea     rdx, aSebsignalevent; "SebSignalEvent"
0x1800ae933  mov     rcx, [rdi]; hModule
0x1800ae936  call    cs:__imp_GetProcAddress
0x1800ae93c  mov     [rbx+708h], rax
0x1800ae943  test    rax, rax
0x1800ae946  jnz     short loc_1800AE9B6
0x1800ae948  call    cs:__imp_GetLastError
0x1800ae94e  test    eax, eax
0x1800ae950  jg      short loc_1800AE95C
0x1800ae952  call    cs:__imp_GetLastError
0x1800ae958  mov     ecx, eax
0x1800ae95a  jmp     short loc_1800AE96B
0x1800ae95c  call    cs:__imp_GetLastError
0x1800ae962  movzx   ecx, ax
0x1800ae965  or      ecx, 80070000h
0x1800ae96b  xorps   xmm0, xmm0
0x1800ae96e  movups  [rsp+168h+var_60], xmm0
0x1800ae976  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800ae97d  mov     [rsp+168h+var_68], rax
0x1800ae985  mov     [rsp+168h+var_50], ecx
0x1800ae98c  mov     [rsp+168h+var_4C], 1859h
0x1800ae997  mov     [rsp+168h+var_48], 1
0x1800ae9a2  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800ae9a9  lea     rcx, [rsp+168h+var_68]; pExceptionObject
0x1800ae9b1  call    _CxxThrowException_0
0x1800ae9b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae9bd  cmp     rcx, rsi
0x1800ae9c0  jz      short loc_1800AE9DD
0x1800ae9c2  test    byte ptr [rcx+1Ch], 1
0x1800ae9c6  jz      short loc_1800AE9DD
0x1800ae9c8  mov     edx, 112h
0x1800ae9cd  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x1800ae9d4  mov     rcx, [rcx+10h]
0x1800ae9d8  call    WPP_SF_
0x1800ae9dd  mov     al, 1
0x1800ae9df  jmp     short loc_1800AE9E3
0x1800ae9e1  xor     al, al
0x1800ae9e3  lea     r11, [rsp+168h+var_8]
0x1800ae9eb  mov     rbx, [r11+18h]
0x1800ae9ef  mov     rsi, [r11+20h]
0x1800ae9f3  mov     rsp, r11
0x1800ae9f6  pop     rdi
0x1800ae9f7  retn
```
