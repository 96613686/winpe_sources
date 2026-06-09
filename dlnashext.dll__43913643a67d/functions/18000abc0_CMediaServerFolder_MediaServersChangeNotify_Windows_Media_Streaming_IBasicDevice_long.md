# CMediaServerFolder::MediaServersChangeNotify(Windows::Media::Streaming::IBasicDevice *,long)

- ea: `0x18000abc0`
- end: `0x18000ad71`
- name: `?MediaServersChangeNotify@CMediaServerFolder@@SAJPEAUIBasicDevice@Streaming@Media@Windows@@J@Z`
- size: `433`
- prototype: `static int(struct Windows::Media::Streaming::IBasicDevice *, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007b44`
- `0x180022ff8`
- `0x1800230c0`

## callees

- `0x18000abc0`
- `0x18000bc18`
- `0x18000e9cc`
- `0x180011930`
- `0x180019958`
- `0x180019b84`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000acf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000acf4`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x18000ac98`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x18000ac98`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x18000ac80`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x18000ac80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ac2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000acbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ac2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000acbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ad42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ad42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMediaServerFolder::MediaServersChangeNotify(
        struct Windows::Media::Streaming::IBasicDevice *a1,
        LONG a2)
{
  HRESULT v4; // ebx
  PCWSTR StringRawBuffer; // rax
  unsigned int v6; // eax
  LPITEMIDLIST v7; // rcx
  LPITEMIDLIST ppidl; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  SFGAOF psfgaoOut[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszName[264]; // [rsp+50h] [rbp-B0h] BYREF

  string = 0;
  v4 = (*(__int64 (__fastcall **)(struct Windows::Media::Streaming::IBasicDevice *, HSTRING *))(*(_QWORD *)a1 + 80LL))(
         a1,
         &string);
  if ( v4 >= 0 )
  {
    CMediaServerFolder::_ReformatFriendlyName(a1);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v4 = StringCchPrintfW(pszName, 0x104u, L"shell:::{289AF617-1CC3-42A6-926C-E6A863F0E3BA}\\%ws", StringRawBuffer);
    if ( v4 >= 0 )
    {
      psfgaoOut[0] = 0;
      ppidl = 0;
      v4 = SHParseDisplayName(pszName, 0, &ppidl, 0, psfgaoOut);
      if ( v4 >= 0 )
      {
        SHChangeNotify(a2, 0, ppidl, 0);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v6 = (unsigned int)WindowsGetStringRawBuffer(string, 0);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)&WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids,
            v6,
            a2);
        }
      }
      v7 = ppidl;
      ppidl = 0;
      CoTaskMemFree(v7);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v4 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids,
      (unsigned int)v4);
  }
  if ( string )
    WindowsDeleteString(string);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000abc0  mov     [rsp-8+arg_10], rbx
0x18000abc5  mov     [rsp-8+arg_18], rsi
0x18000abca  push    rbp
0x18000abcb  push    rdi
0x18000abcc  push    r15
0x18000abce  lea     rbp, [rsp-170h]
0x18000abd6  sub     rsp, 270h
0x18000abdd  mov     rax, cs:__security_cookie
0x18000abe4  xor     rax, rsp
0x18000abe7  mov     [rbp+180h+var_20], rax
0x18000abee  mov     esi, edx
0x18000abf0  mov     rdi, rcx
0x18000abf3  mov     [rsp+280h+string], 0
0x18000abfc  mov     rax, [rcx]
0x18000abff  lea     rdx, [rsp+280h+string]
0x18000ac04  mov     rax, [rax+50h]
0x18000ac08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac0d  mov     ebx, eax
0x18000ac0f  lea     r15, WPP_GLOBAL_Control
0x18000ac16  test    eax, eax
0x18000ac18  js      loc_18000ACFA
0x18000ac1e  mov     rcx, rdi; struct Windows::Media::Streaming::IBasicDevice *
0x18000ac21  call    ?_ReformatFriendlyName@CMediaServerFolder@@CAJPEAUIBasicDevice@Streaming@Media@Windows@@@Z; CMediaServerFolder::_ReformatFriendlyName(Windows::Media::Streaming::IBasicDevice *)
0x18000ac26  xor     edx, edx; length
0x18000ac28  mov     rcx, [rsp+280h+string]; string
0x18000ac2d  call    cs:__imp_WindowsGetStringRawBuffer
0x18000ac33  mov     r9, rax
0x18000ac36  lea     r8, aShell289af6171; "shell:::{289AF617-1CC3-42A6-926C-E6A863"...
0x18000ac3d  mov     edx, 104h; unsigned __int64
0x18000ac42  lea     rcx, [rsp+280h+pszName]; unsigned __int16 *
0x18000ac47  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ac4c  mov     ebx, eax
0x18000ac4e  test    eax, eax
0x18000ac50  js      loc_18000ACFA
0x18000ac56  mov     [rsp+280h+var_240], 0
0x18000ac5e  mov     [rsp+280h+ppidl], 0
0x18000ac67  lea     rax, [rsp+280h+var_240]
0x18000ac6c  mov     [rsp+280h+psfgaoOut], rax; psfgaoOut
0x18000ac71  xor     r9d, r9d; sfgaoIn
0x18000ac74  lea     r8, [rsp+280h+ppidl]; ppidl
0x18000ac79  xor     edx, edx; pbc
0x18000ac7b  lea     rcx, [rsp+280h+pszName]; pszName
0x18000ac80  call    cs:__imp_SHParseDisplayName
0x18000ac86  mov     ebx, eax
0x18000ac88  test    eax, eax
0x18000ac8a  js      short loc_18000ACE6
0x18000ac8c  xor     r9d, r9d; dwItem2
0x18000ac8f  mov     r8, [rsp+280h+ppidl]; dwItem1
0x18000ac94  xor     edx, edx; uFlags
0x18000ac96  mov     ecx, esi; wEventId
0x18000ac98  call    cs:__imp_SHChangeNotify
0x18000ac9e  mov     rax, cs:WPP_GLOBAL_Control
0x18000aca5  cmp     rax, r15
0x18000aca8  jz      short loc_18000ACE6
0x18000acaa  test    byte ptr [rax+1Ch], 40h
0x18000acae  jz      short loc_18000ACE6
0x18000acb0  cmp     byte ptr [rax+19h], 4
0x18000acb4  jb      short loc_18000ACE6
0x18000acb6  xor     edx, edx; length
0x18000acb8  mov     rcx, [rsp+280h+string]; string
0x18000acbd  call    cs:__imp_WindowsGetStringRawBuffer
0x18000acc3  mov     edx, 0Eh
0x18000acc8  mov     dword ptr [rsp+280h+psfgaoOut], esi
0x18000accc  mov     r9, rax
0x18000accf  lea     r8, WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids
0x18000acd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acdd  mov     rcx, [rcx+10h]
0x18000ace1  call    WPP_SF_Sd
0x18000ace6  mov     rcx, [rsp+280h+ppidl]; pv
0x18000aceb  mov     [rsp+280h+ppidl], 0
0x18000acf4  call    cs:__imp_CoTaskMemFree
0x18000acfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad01  cmp     rcx, r15
0x18000ad04  jz      short loc_18000AD38
0x18000ad06  test    byte ptr [rcx+1Ch], 2
0x18000ad0a  jz      short loc_18000AD38
0x18000ad0c  mov     edx, ebx
0x18000ad0e  sar     edx, 1Fh
0x18000ad11  and     edx, 0FFFFFFFDh
0x18000ad14  add     edx, 5
0x18000ad17  movzx   eax, byte ptr [rcx+19h]
0x18000ad1b  cmp     eax, edx
0x18000ad1d  jb      short loc_18000AD38
0x18000ad1f  mov     edx, 0Fh
0x18000ad24  mov     r9d, ebx
0x18000ad27  lea     r8, WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids
0x18000ad2e  mov     rcx, [rcx+10h]
0x18000ad32  call    WPP_SF_d
0x18000ad37  nop
0x18000ad38  mov     rcx, [rsp+280h+string]; string
0x18000ad3d  test    rcx, rcx
0x18000ad40  jz      short loc_18000AD48
0x18000ad42  call    cs:__imp_WindowsDeleteString
0x18000ad48  mov     eax, ebx
0x18000ad4a  mov     rcx, [rbp+180h+var_20]
0x18000ad51  xor     rcx, rsp; StackCookie
0x18000ad54  call    __security_check_cookie
0x18000ad59  lea     r11, [rsp+280h+var_10]
0x18000ad61  mov     rbx, [r11+30h]
0x18000ad65  mov     rsi, [r11+38h]
0x18000ad69  mov     rsp, r11
0x18000ad6c  pop     r15
0x18000ad6e  pop     rdi
0x18000ad6f  pop     rbp
0x18000ad70  retn
```
