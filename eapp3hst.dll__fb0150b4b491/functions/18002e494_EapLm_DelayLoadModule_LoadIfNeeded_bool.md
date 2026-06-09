# EapLm::DelayLoadModule::LoadIfNeeded(bool)

- ea: `0x18002e494`
- end: `0x18002e676`
- name: `?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z`
- size: `482`
- prototype: `char __fastcall(EapLm::DelayLoadModule *this, char)`
- caller_count: `34`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180017ea0`
- `0x1800182b0`
- `0x180018780`
- `0x1800188e0`
- `0x180018f70`
- `0x180019010`
- `0x1800191e0`
- `0x180019320`
- `0x1800196a0`
- `0x1800197a0`
- `0x180019a70`
- `0x18001a090`
- `0x18001a390`
- `0x18001a720`
- `0x18001aab0`
- `0x18001ae60`
- `0x18001b8f0`
- `0x18001bc00`
- `0x18001bf10`
- `0x18001c0a0`
- `0x18001c480`
- `0x18001c520`
- `0x18001c730`
- `0x18001c820`
- `0x18001cae0`
- `0x18001cba0`
- `0x18001ce00`
- `0x18001d120`
- `0x18001d370`
- `0x18001d6a0`
- `0x18001d9f0`
- `0x18001dd00`
- `0x18001dfa0`
- `0x180023dcc`

## callees

- `0x1800017a0`
- `0x18000eb74`
- `0x180012d18`
- `0x180013150`
- `0x1800139a4`
- `0x1800151ec`
- `0x180015534`
- `0x1800165a4`
- `0x18002ca08`
- `0x18002e494`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e5a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e602`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e633`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e5a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e602`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e633`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e4e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e64c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e4e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e64c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5b9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002e531`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002e531`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall EapLm::DelayLoadModule::LoadIfNeeded(EapLm::DelayLoadModule *this, char a2)
{
  __int64 v5; // rax
  __int64 v6; // r10
  const WCHAR *v7; // rax
  __int64 v8; // rdx
  HMODULE LibraryW; // r8
  DWORD LastError; // eax
  const CHAR *v11; // rcx
  HMODULE v12; // r8
  FARPROC ProcAddress; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  DWORD v16; // eax
  char v17; // di
  const CHAR *v18; // rcx
  const CHAR *v19; // rcx
  __int64 v20; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v21[96]; // [rsp+30h] [rbp-78h] BYREF

  if ( *(_BYTE *)this )
    return 1;
  LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v20, (char *)this + 8);
  if ( *(_BYTE *)this )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v20 + 16));
    return 1;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v5 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 80);
    WPP_SF_S(*(_QWORD *)(v6 + 16), 11, WPP_a9519d4148563418b56d4839f4a6b35c_Traceguids, v5);
  }
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 80);
  LibraryW = LoadLibraryW(v7);
  *((_QWORD *)this + 26) = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    EapHost::EapError::EapError(
      (EapHost::EapError *)v21,
      0x80420011,
      (EapLm::DelayLoadModule *)((char *)this + 240),
      LastError);
    EapHost::EapError::FillRootCauseString(
      (EapHost::EapError *)v21,
      0,
      *((unsigned __int8 *)this + 248),
      *((unsigned int *)this + 66));
    EapHost::EapException::Throw((const struct EapHost::EapError *)v21);
  }
  if ( (unsigned __int8)std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(
                          (char *)this + 112,
                          v8,
                          LibraryW) )
    v11 = *(const CHAR **)v11;
  ProcAddress = GetProcAddress(v12, v11);
  *((_QWORD *)this + 27) = ProcAddress;
  if ( ProcAddress )
  {
    v17 = 1;
    if ( *((_QWORD *)this + 24) )
    {
      if ( (unsigned __int8)std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(
                              (char *)this + 176,
                              v14,
                              v15) )
        v18 = *(const CHAR **)v18;
      *((_QWORD *)this + 28) = GetProcAddress(*((HMODULE *)this + 26), v18);
    }
    if ( *((_QWORD *)this + 20) )
    {
      if ( (unsigned __int8)std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(
                              (char *)this + 144,
                              v14,
                              v15) )
        v19 = *(const CHAR **)v19;
      *((_QWORD *)this + 29) = GetProcAddress(*((HMODULE *)this + 26), v19);
    }
    *(_BYTE *)this = 1;
  }
  else
  {
    if ( !a2 )
    {
      v16 = GetLastError();
      EapHost::EapException::Throw(L"GetProcAddress", L"MethodProc", v16);
    }
    v17 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v20 + 16));
  return v17;
}

```

## disassembly

```asm
0x18002e494  mov     [rsp+arg_8], rbx
0x18002e499  push    rdi
0x18002e49a  sub     rsp, 0A0h
0x18002e4a1  mov     rax, cs:__security_cookie
0x18002e4a8  xor     rax, rsp
0x18002e4ab  mov     [rsp+0A8h+var_18], rax
0x18002e4b3  mov     dil, dl
0x18002e4b6  mov     rbx, rcx
0x18002e4b9  cmp     byte ptr [rcx], 0
0x18002e4bc  jz      short loc_18002E4C5
0x18002e4be  mov     al, 1
0x18002e4c0  jmp     loc_18002E655
0x18002e4c5  lea     rdx, [rcx+8]
0x18002e4c9  lea     rcx, [rsp+0A8h+var_88]
0x18002e4ce  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x18002e4d3  nop
0x18002e4d4  cmp     byte ptr [rbx], 0
0x18002e4d7  jz      short loc_18002E4EA
0x18002e4d9  mov     rcx, [rsp+0A8h+var_88]
0x18002e4de  add     rcx, 10h; lpCriticalSection
0x18002e4e2  call    cs:__imp_LeaveCriticalSection
0x18002e4e8  jmp     short loc_18002E4BE
0x18002e4ea  lea     rax, WPP_GLOBAL_Control
0x18002e4f1  mov     r10, cs:WPP_GLOBAL_Control
0x18002e4f8  cmp     r10, rax
0x18002e4fb  jz      short loc_18002E525
0x18002e4fd  test    byte ptr [r10+1Ch], 4
0x18002e502  jz      short loc_18002E525
0x18002e504  lea     rcx, [rbx+50h]
0x18002e508  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002e50d  mov     edx, 0Bh
0x18002e512  mov     r9, rax
0x18002e515  lea     r8, WPP_a9519d4148563418b56d4839f4a6b35c_Traceguids
0x18002e51c  mov     rcx, [r10+10h]
0x18002e520  call    WPP_SF_S
0x18002e525  lea     rcx, [rbx+50h]
0x18002e529  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002e52e  mov     rcx, rax; lpLibFileName
0x18002e531  call    cs:__imp_LoadLibraryW
0x18002e537  mov     r8, rax
0x18002e53a  mov     [rbx+0D0h], rax
0x18002e541  test    rax, rax
0x18002e544  jnz     short loc_18002E58C
0x18002e546  call    cs:__imp_GetLastError
0x18002e54c  mov     r9d, eax; unsigned int
0x18002e54f  lea     r8, [rbx+0F0h]; struct EapHost::EapMethodType *
0x18002e556  mov     edx, 80420011h; unsigned int
0x18002e55b  lea     rcx, [rsp+0A8h+var_78]; this
0x18002e560  call    ??0EapError@EapHost@@QEAA@IPEBVEapMethodType@1@I@Z; EapHost::EapError::EapError(uint,EapHost::EapMethodType const *,uint)
0x18002e565  nop
0x18002e566  movzx   r8d, byte ptr [rbx+0F8h]
0x18002e56e  mov     r9d, [rbx+108h]
0x18002e575  xor     edx, edx; unsigned int
0x18002e577  lea     rcx, [rsp+0A8h+var_78]; this
0x18002e57c  call    ?FillRootCauseString@EapError@EapHost@@QEAAXKZZ; EapHost::EapError::FillRootCauseString(ulong,...)
0x18002e581  lea     rcx, [rsp+0A8h+var_78]; struct EapHost::EapError *
0x18002e586  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18002e58c  lea     rcx, [rbx+70h]
0x18002e590  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(void)
0x18002e595  test    al, al
0x18002e597  jz      short loc_18002E59C
0x18002e599  mov     rcx, [rcx]
0x18002e59c  mov     rdx, rcx; lpProcName
0x18002e59f  mov     rcx, r8; hModule
0x18002e5a2  call    cs:__imp_GetProcAddress
0x18002e5a8  mov     [rbx+0D8h], rax
0x18002e5af  test    rax, rax
0x18002e5b2  jnz     short loc_18002E5DB
0x18002e5b4  test    dil, dil
0x18002e5b7  jnz     short loc_18002E5D6
0x18002e5b9  call    cs:__imp_GetLastError
0x18002e5bf  mov     r8d, eax; int
0x18002e5c2  lea     rdx, aMethodproc; "MethodProc"
0x18002e5c9  lea     rcx, aGetprocaddress; "GetProcAddress"
0x18002e5d0  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x18002e5d6  xor     dil, dil
0x18002e5d9  jmp     short loc_18002E643
0x18002e5db  mov     dil, 1
0x18002e5de  lea     rcx, [rbx+0B0h]
0x18002e5e5  cmp     qword ptr [rcx+10h], 0
0x18002e5ea  jz      short loc_18002E60F
0x18002e5ec  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(void)
0x18002e5f1  test    al, al
0x18002e5f3  jz      short loc_18002E5F8
0x18002e5f5  mov     rcx, [rcx]
0x18002e5f8  mov     rdx, rcx; lpProcName
0x18002e5fb  mov     rcx, [rbx+0D0h]; hModule
0x18002e602  call    cs:__imp_GetProcAddress
0x18002e608  mov     [rbx+0E0h], rax
0x18002e60f  lea     rcx, [rbx+90h]
0x18002e616  cmp     qword ptr [rcx+10h], 0
0x18002e61b  jz      short loc_18002E640
0x18002e61d  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(void)
0x18002e622  test    al, al
0x18002e624  jz      short loc_18002E629
0x18002e626  mov     rcx, [rcx]
0x18002e629  mov     rdx, rcx; lpProcName
0x18002e62c  mov     rcx, [rbx+0D0h]; hModule
0x18002e633  call    cs:__imp_GetProcAddress
0x18002e639  mov     [rbx+0E8h], rax
0x18002e640  mov     [rbx], dil
0x18002e643  mov     rcx, [rsp+0A8h+var_88]
0x18002e648  add     rcx, 10h; lpCriticalSection
0x18002e64c  call    cs:__imp_LeaveCriticalSection
0x18002e652  mov     al, dil
0x18002e655  mov     rcx, [rsp+0A8h+var_18]
0x18002e65d  xor     rcx, rsp; StackCookie
0x18002e660  call    __security_check_cookie
0x18002e665  mov     rbx, [rsp+0A8h+arg_8]
0x18002e66d  add     rsp, 0A0h
0x18002e674  pop     rdi
0x18002e675  retn
```
