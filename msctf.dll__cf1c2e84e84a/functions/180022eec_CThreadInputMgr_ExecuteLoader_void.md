# CThreadInputMgr::_ExecuteLoader(void)

- ea: `0x180022eec`
- end: `0x180023049`
- name: `?_ExecuteLoader@CThreadInputMgr@@AEAAXXZ`
- size: `349`
- prototype: `void __fastcall(CThreadInputMgr *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180022cc0`

## callees

- `0x18000e7b0`
- `0x180022c48`
- `0x180022eec`
- `0x180023050`
- `0x18008ced0`
- `0x18009eaea`
- `0x1800aa584`
- `0x1800b8a20`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022f95`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022fb9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022fe1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022f95`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022fb9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022fe1`
- `USER32!GetSystemMetrics` at `0x180022f1c`
- `USER32!GetSystemMetrics` at `0x180022f1c`

## pseudocode

```c
void __fastcall CThreadInputMgr::_ExecuteLoader(CThreadInputMgr *this)
{
  unsigned int v2; // edx
  unsigned int v3; // ecx
  __int64 v4; // r8
  unsigned int inited; // eax
  _BYTE v6[16]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR String1[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( (*((_BYTE *)this + 3768) & 2) == 0 && !GetSystemMetrics(0x2000) )
  {
    if ( (unsigned int)IsMutexForWinSta() )
    {
      if ( !(unsigned int)IsMutexForDesktop() )
      {
        memset_0(String1, 0, 0x208u);
        if ( (unsigned int)GetThreadDesktopName(String1, v2) )
        {
          if ( CompareStringOrdinal(String1, -1, L"Default", -1, 1) != 2
            && CompareStringOrdinal(String1, -1, L"winlogon", -1, 1) != 2
            && CompareStringOrdinal(String1, -1, L"Screen-saver", -1, 1) != 2
            && (unsigned int)CheckKnownModuleNotForCtfmon() )
          {
            if ( (Microsoft_Windows_TSF_msctfEnableBits & 1) != 0 )
              McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_TSF_msctf_Context, StartingCTFMON, v4, 1, v6);
            inited = Internal_InitLocalMsCtfMonitor(v3);
            *((_DWORD *)this + 917) &= ~0x100000u;
            *((_DWORD *)this + 917) |= ~(inited >> 11) & 0x100000;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180022eec  mov     [rsp+arg_8], rbx
0x180022ef1  push    rsi
0x180022ef2  sub     rsp, 260h
0x180022ef9  mov     rax, cs:__security_cookie
0x180022f00  xor     rax, rsp
0x180022f03  mov     [rsp+268h+var_18], rax
0x180022f0b  test    byte ptr [rcx+0EB8h], 2
0x180022f12  mov     rbx, rcx
0x180022f15  jnz     short loc_180022F2F
0x180022f17  mov     ecx, 2000h; nIndex
0x180022f1c  call    cs:__imp_GetSystemMetrics
0x180022f22  test    eax, eax
0x180022f24  jnz     short loc_180022F2F
0x180022f26  call    ?IsMutexForWinSta@@YAHXZ; IsMutexForWinSta(void)
0x180022f2b  test    eax, eax
0x180022f2d  jnz     short loc_180022F50
0x180022f2f  mov     rcx, [rsp+268h+var_18]
0x180022f37  xor     rcx, rsp; StackCookie
0x180022f3a  call    __security_check_cookie
0x180022f3f  mov     rbx, [rsp+268h+arg_8]
0x180022f47  add     rsp, 260h
0x180022f4e  pop     rsi
0x180022f4f  retn
0x180022f50  call    ?IsMutexForDesktop@@YAHXZ; IsMutexForDesktop(void)
0x180022f55  test    eax, eax
0x180022f57  jnz     short loc_180022F2F
0x180022f59  xor     edx, edx; Val
0x180022f5b  lea     rcx, [rsp+268h+String1]; void *
0x180022f60  mov     r8d, 208h; Size
0x180022f66  call    memset_0
0x180022f6b  lea     rcx, [rsp+268h+String1]; unsigned __int16 *
0x180022f70  call    ?GetThreadDesktopName@@YAHPEAGK@Z; GetThreadDesktopName(ushort *,ulong)
0x180022f75  test    eax, eax
0x180022f77  jz      short loc_180022F2F
0x180022f79  or      esi, 0FFFFFFFFh
0x180022f7c  mov     [rsp+268h+bIgnoreCase], 1; bIgnoreCase
0x180022f84  mov     r9d, esi; cchCount2
0x180022f87  lea     r8, String2; "Default"
0x180022f8e  mov     edx, esi; cchCount1
0x180022f90  lea     rcx, [rsp+268h+String1]; lpString1
0x180022f95  call    cs:__imp_CompareStringOrdinal
0x180022f9b  cmp     eax, 2
0x180022f9e  jz      short loc_180022F2F
0x180022fa0  mov     r9d, esi; cchCount2
0x180022fa3  mov     [rsp+268h+bIgnoreCase], 1; bIgnoreCase
0x180022fab  lea     r8, aWinlogon; "winlogon"
0x180022fb2  mov     edx, esi; cchCount1
0x180022fb4  lea     rcx, [rsp+268h+String1]; lpString1
0x180022fb9  call    cs:__imp_CompareStringOrdinal
0x180022fbf  cmp     eax, 2
0x180022fc2  jz      loc_180022F2F
0x180022fc8  mov     r9d, esi; cchCount2
0x180022fcb  mov     [rsp+268h+bIgnoreCase], 1; bIgnoreCase
0x180022fd3  lea     r8, aScreenSaver; "Screen-saver"
0x180022fda  mov     edx, esi; cchCount1
0x180022fdc  lea     rcx, [rsp+268h+String1]; lpString1
0x180022fe1  call    cs:__imp_CompareStringOrdinal
0x180022fe7  cmp     eax, 2
0x180022fea  jz      loc_180022F2F
0x180022ff0  call    ?CheckKnownModuleNotForCtfmon@@YAHXZ; CheckKnownModuleNotForCtfmon(void)
0x180022ff5  test    eax, eax
0x180022ff7  jz      loc_180022F2F
0x180022ffd  test    cs:Microsoft_Windows_TSF_msctfEnableBits, 1
0x180023004  jz      short loc_180023027
0x180023006  lea     rax, [rsp+268h+var_238]
0x18002300b  lea     r9d, [rsi+2]
0x18002300f  mov     qword ptr [rsp+268h+bIgnoreCase], rax
0x180023014  lea     rdx, StartingCTFMON
0x18002301b  lea     rcx, Microsoft_Windows_TSF_msctf_Context
0x180023022  call    McGenEventWrite_EventWriteTransfer
0x180023027  call    ?Internal_InitLocalMsCtfMonitor@@YAJK@Z; Internal_InitLocalMsCtfMonitor(ulong)
0x18002302c  btr     dword ptr [rbx+0E54h], 14h
0x180023034  shr     eax, 0Bh
0x180023037  not     eax
0x180023039  and     eax, 100000h
0x18002303e  or      [rbx+0E54h], eax
0x180023044  jmp     loc_180022F2F
```
