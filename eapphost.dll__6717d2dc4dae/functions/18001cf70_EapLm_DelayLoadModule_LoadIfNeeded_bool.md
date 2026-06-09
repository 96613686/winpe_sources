# EapLm::DelayLoadModule::LoadIfNeeded(bool)

- ea: `0x18001cf70`
- end: `0x18001d110`
- name: `?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z`
- size: `416`
- prototype: `bool __fastcall(EapLm::DelayLoadModule *__hidden this, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180013430`

## callees

- `0x180002a90`
- `0x180004988`
- `0x180009f70`
- `0x1800118e8`
- `0x180012394`
- `0x18001af5c`
- `0x18001cf70`
- `0x18001d118`
- `0x18001d9bc`
- `0x18001dcbc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d060`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d0ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d0d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d060`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d0ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d0d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d00b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d00b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d072`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d0ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d0ef`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001cff6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001cff6`

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
    LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v17, (__int64)this + 8);
    if ( !*(_BYTE *)this )
    {
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v2 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        WPP_SF_S(*(_QWORD *)(v3 + 16), 11, WPP_a9519d4148563418b56d4839f4a6b35c_Traceguids, v2);
      }
      v4 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
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
0x18001cf70  push    rbx
0x18001cf72  sub     rsp, 0A0h
0x18001cf79  mov     rax, cs:__security_cookie
0x18001cf80  xor     rax, rsp
0x18001cf83  mov     [rsp+0A8h+var_18], rax
0x18001cf8b  mov     rbx, rcx
0x18001cf8e  cmp     byte ptr [rcx], 0
0x18001cf91  jnz     loc_18001D0F5
0x18001cf97  lea     rdx, [rcx+8]
0x18001cf9b  lea     rcx, [rsp+0A8h+var_88]
0x18001cfa0  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x18001cfa5  nop
0x18001cfa6  cmp     byte ptr [rbx], 0
0x18001cfa9  jnz     loc_18001D0E6
0x18001cfaf  lea     rax, WPP_GLOBAL_Control
0x18001cfb6  mov     r10, cs:WPP_GLOBAL_Control
0x18001cfbd  cmp     r10, rax
0x18001cfc0  jz      short loc_18001CFEA
0x18001cfc2  test    byte ptr [r10+1Ch], 4
0x18001cfc7  jz      short loc_18001CFEA
0x18001cfc9  lea     rcx, [rbx+50h]
0x18001cfcd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001cfd2  mov     edx, 0Bh
0x18001cfd7  mov     r9, rax
0x18001cfda  lea     r8, WPP_a9519d4148563418b56d4839f4a6b35c_Traceguids
0x18001cfe1  mov     rcx, [r10+10h]
0x18001cfe5  call    WPP_SF_S
0x18001cfea  lea     rcx, [rbx+50h]
0x18001cfee  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001cff3  mov     rcx, rax; lpLibFileName
0x18001cff6  call    cs:__imp_LoadLibraryW
0x18001cffc  mov     r8, rax
0x18001cfff  mov     [rbx+0D0h], rax
0x18001d006  test    rax, rax
0x18001d009  jnz     short loc_18001D051
0x18001d00b  call    cs:__imp_GetLastError
0x18001d011  mov     r9d, eax; unsigned int
0x18001d014  lea     r8, [rbx+0F0h]; struct EapHost::EapMethodType *
0x18001d01b  mov     edx, 80420011h; unsigned int
0x18001d020  lea     rcx, [rsp+0A8h+var_78]; this
0x18001d025  call    ??0EapError@EapHost@@QEAA@IPEBVEapMethodType@1@I@Z; EapHost::EapError::EapError(uint,EapHost::EapMethodType const *,uint)
0x18001d02a  nop
0x18001d02b  movzx   r8d, byte ptr [rbx+0F8h]
0x18001d033  mov     r9d, [rbx+108h]
0x18001d03a  xor     edx, edx; unsigned int
0x18001d03c  lea     rcx, [rsp+0A8h+var_78]; this
0x18001d041  call    ?FillRootCauseString@EapError@EapHost@@QEAAXKZZ; EapHost::EapError::FillRootCauseString(ulong,...)
0x18001d046  lea     rcx, [rsp+0A8h+var_78]; struct EapHost::EapError *
0x18001d04b  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18001d051  lea     rcx, [rbx+70h]
0x18001d055  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001d05a  mov     rdx, rax; lpProcName
0x18001d05d  mov     rcx, r8; hModule
0x18001d060  call    cs:__imp_GetProcAddress
0x18001d066  mov     [rbx+0D8h], rax
0x18001d06d  test    rax, rax
0x18001d070  jnz     short loc_18001D08F
0x18001d072  call    cs:__imp_GetLastError
0x18001d078  mov     r8d, eax; int
0x18001d07b  lea     rdx, aMethodproc; "MethodProc"
0x18001d082  lea     rcx, aGetprocaddress; "GetProcAddress"
0x18001d089  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x18001d08f  lea     rcx, [rbx+0B0h]
0x18001d096  cmp     qword ptr [rcx+10h], 0
0x18001d09b  jz      short loc_18001D0B9
0x18001d09d  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001d0a2  mov     rdx, rax; lpProcName
0x18001d0a5  mov     rcx, [rbx+0D0h]; hModule
0x18001d0ac  call    cs:__imp_GetProcAddress
0x18001d0b2  mov     [rbx+0E0h], rax
0x18001d0b9  lea     rcx, [rbx+90h]
0x18001d0c0  cmp     qword ptr [rcx+10h], 0
0x18001d0c5  jz      short loc_18001D0E3
0x18001d0c7  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001d0cc  mov     rdx, rax; lpProcName
0x18001d0cf  mov     rcx, [rbx+0D0h]; hModule
0x18001d0d6  call    cs:__imp_GetProcAddress
0x18001d0dc  mov     [rbx+0E8h], rax
0x18001d0e3  mov     byte ptr [rbx], 1
0x18001d0e6  mov     rcx, [rsp+0A8h+var_88]
0x18001d0eb  add     rcx, 10h; lpCriticalSection
0x18001d0ef  call    cs:__imp_LeaveCriticalSection
0x18001d0f5  mov     al, 1
0x18001d0f7  mov     rcx, [rsp+0A8h+var_18]
0x18001d0ff  xor     rcx, rsp; StackCookie
0x18001d102  call    __security_check_cookie
0x18001d107  add     rsp, 0A0h
0x18001d10e  pop     rbx
0x18001d10f  retn
```
