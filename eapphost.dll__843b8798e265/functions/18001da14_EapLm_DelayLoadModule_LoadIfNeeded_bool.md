# EapLm::DelayLoadModule::LoadIfNeeded(bool)

- ea: `0x18001da14`
- end: `0x18001dbdf`
- name: `?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z`
- size: `459`
- prototype: `bool __fastcall(EapLm::DelayLoadModule *__hidden this, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180013bfc`

## callees

- `0x180002af0`
- `0x180004af8`
- `0x18000a3e4`
- `0x18001204c`
- `0x180012b14`
- `0x18001b964`
- `0x18001da14`
- `0x18001dbe8`
- `0x18001e4ac`
- `0x18001e7c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001db10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001db68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001db98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001db10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001db68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001db98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dab5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dab5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dbb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dbb7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001da9a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001da9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall EapLm::DelayLoadModule::LoadIfNeeded(EapLm::DelayLoadModule *this)
{
  __int64 v2; // rax
  __int64 v3; // r10
  const WCHAR *v4; // rax
  __int64 v5; // rdx
  HMODULE LibraryW; // r8
  DWORD LastError; // eax
  const CHAR *v8; // rax
  HMODULE v9; // r8
  FARPROC ProcAddress; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  DWORD v13; // eax
  const CHAR *v14; // rax
  const CHAR *v15; // rax
  __int64 v17; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v18[96]; // [rsp+30h] [rbp-78h] BYREF

  if ( !*(_BYTE *)this )
  {
    LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v17, (char *)this + 8);
    if ( !*(_BYTE *)this )
    {
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v2 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 80);
        WPP_SF_S(*(_QWORD *)(v3 + 16), 11, WPP_a9519d4148563418b56d4839f4a6b35c_Traceguids, v2);
      }
      v4 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 80);
      LibraryW = LoadLibraryW(v4);
      *((_QWORD *)this + 26) = LibraryW;
      if ( !LibraryW )
      {
        LastError = GetLastError();
        EapHost::EapError::EapError(
          (EapHost::EapError *)v18,
          0x80420011,
          (EapLm::DelayLoadModule *)((char *)this + 240),
          LastError);
        EapHost::EapError::FillRootCauseString(
          (EapHost::EapError *)v18,
          0,
          *((unsigned __int8 *)this + 248),
          *((unsigned int *)this + 66));
        EapHost::EapException::Throw((const struct EapHost::EapError *)v18);
      }
      v8 = (const CHAR *)std::_String_val<std::_Simple_types<char>>::_Myptr((char *)this + 112, v5, LibraryW);
      ProcAddress = GetProcAddress(v9, v8);
      *((_QWORD *)this + 27) = ProcAddress;
      if ( !ProcAddress )
      {
        v13 = GetLastError();
        EapHost::EapException::Throw(L"GetProcAddress", L"MethodProc", v13);
      }
      if ( *((_QWORD *)this + 24) )
      {
        v14 = (const CHAR *)std::_String_val<std::_Simple_types<char>>::_Myptr((char *)this + 176, v11, v12);
        *((_QWORD *)this + 28) = GetProcAddress(*((HMODULE *)this + 26), v14);
      }
      if ( *((_QWORD *)this + 20) )
      {
        v15 = (const CHAR *)std::_String_val<std::_Simple_types<char>>::_Myptr((char *)this + 144, v11, v12);
        *((_QWORD *)this + 29) = GetProcAddress(*((HMODULE *)this + 26), v15);
      }
      *(_BYTE *)this = 1;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 16));
  }
  return 1;
}

```

## disassembly

```asm
0x18001da14  push    rbx
0x18001da16  sub     rsp, 0A0h
0x18001da1d  mov     rax, cs:__security_cookie
0x18001da24  xor     rax, rsp
0x18001da27  mov     [rsp+0A8h+var_18], rax
0x18001da2f  mov     rbx, rcx
0x18001da32  cmp     byte ptr [rcx], 0
0x18001da35  jnz     loc_18001DBC3
0x18001da3b  lea     rdx, [rcx+8]
0x18001da3f  lea     rcx, [rsp+0A8h+var_88]
0x18001da44  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x18001da49  nop
0x18001da4a  cmp     byte ptr [rbx], 0
0x18001da4d  jnz     loc_18001DBAE
0x18001da53  lea     rax, WPP_GLOBAL_Control
0x18001da5a  mov     r10, cs:WPP_GLOBAL_Control
0x18001da61  cmp     r10, rax
0x18001da64  jz      short loc_18001DA8E
0x18001da66  test    byte ptr [r10+1Ch], 4
0x18001da6b  jz      short loc_18001DA8E
0x18001da6d  lea     rcx, [rbx+50h]
0x18001da71  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001da76  mov     edx, 0Bh
0x18001da7b  mov     r9, rax
0x18001da7e  lea     r8, WPP_a9519d4148563418b56d4839f4a6b35c_Traceguids
0x18001da85  mov     rcx, [r10+10h]
0x18001da89  call    WPP_SF_S
0x18001da8e  lea     rcx, [rbx+50h]
0x18001da92  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001da97  mov     rcx, rax; lpLibFileName
0x18001da9a  call    cs:__imp_LoadLibraryW
0x18001daa1  nop     dword ptr [rax+rax+00h]
0x18001daa6  mov     r8, rax
0x18001daa9  mov     [rbx+0D0h], rax
0x18001dab0  test    rax, rax
0x18001dab3  jnz     short loc_18001DB01
0x18001dab5  call    cs:__imp_GetLastError
0x18001dabc  nop     dword ptr [rax+rax+00h]
0x18001dac1  mov     r9d, eax; unsigned int
0x18001dac4  lea     r8, [rbx+0F0h]; struct EapHost::EapMethodType *
0x18001dacb  mov     edx, 80420011h; unsigned int
0x18001dad0  lea     rcx, [rsp+0A8h+var_78]; this
0x18001dad5  call    ??0EapError@EapHost@@QEAA@IPEBVEapMethodType@1@I@Z; EapHost::EapError::EapError(uint,EapHost::EapMethodType const *,uint)
0x18001dada  nop
0x18001dadb  movzx   r8d, byte ptr [rbx+0F8h]
0x18001dae3  mov     r9d, [rbx+108h]
0x18001daea  xor     edx, edx; unsigned int
0x18001daec  lea     rcx, [rsp+0A8h+var_78]; this
0x18001daf1  call    ?FillRootCauseString@EapError@EapHost@@QEAAXKZZ; EapHost::EapError::FillRootCauseString(ulong,...)
0x18001daf6  lea     rcx, [rsp+0A8h+var_78]; struct EapHost::EapError *
0x18001dafb  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18001db01  lea     rcx, [rbx+70h]
0x18001db05  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001db0a  mov     rdx, rax; lpProcName
0x18001db0d  mov     rcx, r8; hModule
0x18001db10  call    cs:__imp_GetProcAddress
0x18001db17  nop     dword ptr [rax+rax+00h]
0x18001db1c  mov     [rbx+0D8h], rax
0x18001db23  test    rax, rax
0x18001db26  jnz     short loc_18001DB4B
0x18001db28  call    cs:__imp_GetLastError
0x18001db2f  nop     dword ptr [rax+rax+00h]
0x18001db34  mov     r8d, eax; int
0x18001db37  lea     rdx, aMethodproc; "MethodProc"
0x18001db3e  lea     rcx, aGetprocaddress; "GetProcAddress"
0x18001db45  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x18001db4b  lea     rcx, [rbx+0B0h]
0x18001db52  cmp     qword ptr [rcx+10h], 0
0x18001db57  jz      short loc_18001DB7B
0x18001db59  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001db5e  mov     rdx, rax; lpProcName
0x18001db61  mov     rcx, [rbx+0D0h]; hModule
0x18001db68  call    cs:__imp_GetProcAddress
0x18001db6f  nop     dword ptr [rax+rax+00h]
0x18001db74  mov     [rbx+0E0h], rax
0x18001db7b  lea     rcx, [rbx+90h]
0x18001db82  cmp     qword ptr [rcx+10h], 0
0x18001db87  jz      short loc_18001DBAB
0x18001db89  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001db8e  mov     rdx, rax; lpProcName
0x18001db91  mov     rcx, [rbx+0D0h]; hModule
0x18001db98  call    cs:__imp_GetProcAddress
0x18001db9f  nop     dword ptr [rax+rax+00h]
0x18001dba4  mov     [rbx+0E8h], rax
0x18001dbab  mov     byte ptr [rbx], 1
0x18001dbae  mov     rcx, [rsp+0A8h+var_88]
0x18001dbb3  add     rcx, 10h; lpCriticalSection
0x18001dbb7  call    cs:__imp_LeaveCriticalSection
0x18001dbbe  nop     dword ptr [rax+rax+00h]
0x18001dbc3  mov     al, 1
0x18001dbc5  mov     rcx, [rsp+0A8h+var_18]
0x18001dbcd  xor     rcx, rsp; StackCookie
0x18001dbd0  call    __security_check_cookie
0x18001dbd5  add     rsp, 0A0h
0x18001dbdc  pop     rbx
0x18001dbdd  retn
```
