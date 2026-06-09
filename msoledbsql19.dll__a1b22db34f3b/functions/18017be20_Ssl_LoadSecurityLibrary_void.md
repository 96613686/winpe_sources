# Ssl::LoadSecurityLibrary(void)

- ea: `0x18017be20`
- end: `0x18017c153`
- name: `?LoadSecurityLibrary@Ssl@@CAKXZ`
- size: `819`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18017b5e0`

## callees

- `0x180001f70`
- `0x1800030c0`
- `0x180003d80`
- `0x180157620`
- `0x18015a6f0`
- `0x18015a880`
- `0x18017be20`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18017bf82`
- `KERNEL32!FreeLibrary` at `0x18017c055`
- `KERNEL32!FreeLibrary` at `0x18017bf82`
- `KERNEL32!FreeLibrary` at `0x18017c055`
- `KERNEL32!GetLastError` at `0x18017beb5`
- `KERNEL32!GetLastError` at `0x18017bf73`
- `KERNEL32!GetLastError` at `0x18017c046`
- `KERNEL32!GetLastError` at `0x18017beb5`
- `KERNEL32!GetLastError` at `0x18017bf73`
- `KERNEL32!GetLastError` at `0x18017c046`
- `KERNEL32!GetProcAddress` at `0x18017bf64`
- `KERNEL32!GetProcAddress` at `0x18017bf64`

## string_xrefs

- `0x18017be99`: `secur32.dll`
- `0x18017bf5a`: `InitSecurityInterfaceW`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Ssl::LoadSecurityLibrary(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  HMODULE v4; // rax
  DWORD LastError; // ebx
  __int64 (*ProcAddress)(void); // rax
  __int64 v8; // [rsp+40h] [rbp-18h] BYREF

  v8 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266DF0[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_180248060[0])(
      bidID,
      0,
      0,
      &v8,
      off_180266DF0[0],
      0);
  v4 = SNILoadSystemLibA("secur32.dll", a2, a3, a4);
  Ssl::s_hSecurity = v4;
  if ( v4 )
  {
    ProcAddress = GetProcAddress(v4, "InitSecurityInterfaceW");
    if ( ProcAddress )
    {
      Ssl::s_pfTable = (struct _SECURITY_FUNCTION_TABLE_W *)ProcAddress();
      if ( Ssl::s_pfTable )
      {
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265418[0] )
          bidTraceW(off_1802620D0[0], 2056192, off_180265418[0], 0);
        LastError = 0;
      }
      else
      {
        LastError = GetLastError();
        FreeLibrary(Ssl::s_hSecurity);
        Ssl::s_hSecurity = 0;
        if ( (bidGblFlags & 2) != 0 && off_180265408[0] )
        {
          SniErrorIdFromStringId(0xC3B4u);
          bidTraceW(off_1802620C0[0], 2049024, off_180265408[0], 5);
        }
        SNISetLastError(5, LastError, 50100);
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265410[0] )
          bidTraceW(off_1802620C8[0], 2051072, off_180265410[0], LastError);
      }
    }
    else
    {
      LastError = GetLastError();
      FreeLibrary(Ssl::s_hSecurity);
      Ssl::s_hSecurity = 0;
      if ( (bidGblFlags & 2) != 0 && off_1802653F8[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(off_1802620B0[0], 2033664, off_1802653F8[0], 5);
      }
      SNISetLastError(5, LastError, 50100);
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265400[0] )
        bidTraceW(off_1802620B8[0], 2035712, off_180265400[0], LastError);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_1802653E8[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(off_1802620A0[0], 2014208, off_1802653E8[0], 5);
    }
    SNISetLastError(5, LastError, 50100);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802653F0[0] )
      bidTraceW(off_1802620A8[0], 2016256, off_1802653F0[0], LastError);
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v8);
  return LastError;
}

```

## disassembly

```asm
0x18017be20  push    rbx
0x18017be22  sub     rsp, 50h
0x18017be26  mov     rax, cs:__security_cookie
0x18017be2d  xor     rax, rsp
0x18017be30  mov     [rsp+58h+var_10], rax
0x18017be35  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFFh
0x18017be3e  mov     eax, cs:_bidGblFlags
0x18017be44  and     eax, 20004h
0x18017be49  cmp     eax, 20004h
0x18017be4e  jnz     short loc_18017BE99
0x18017be50  mov     rax, cs:off_180266DF0; "<Ssl::LoadSecurityLibrary|API|SNI> \n"
0x18017be57  test    rax, rax
0x18017be5a  jz      short loc_18017BE99
0x18017be5c  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18017be64  jz      short loc_18017BE99
0x18017be66  mov     rax, cs:off_180248060
0x18017be6d  mov     [rsp+58h+var_30], 0
0x18017be76  mov     rcx, cs:off_180266DF0; "<Ssl::LoadSecurityLibrary|API|SNI> \n"
0x18017be7d  mov     [rsp+58h+var_38], rcx
0x18017be82  lea     r9, [rsp+58h+var_18]
0x18017be87  xor     r8d, r8d
0x18017be8a  xor     edx, edx
0x18017be8c  mov     rcx, cs:_bidID
0x18017be93  call    cs:__guard_dispatch_icall_fptr
0x18017be99  lea     rcx, aSecur32Dll; "secur32.dll"
0x18017bea0  call    SNILoadSystemLibA
0x18017bea5  mov     cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Ssl::s_hSecurity
0x18017beac  test    rax, rax
0x18017beaf  jnz     loc_18017BF5A
0x18017beb5  call    cs:__imp_GetLastError
0x18017bebb  mov     ebx, eax
0x18017bebd  test    byte ptr cs:_bidGblFlags, 2
0x18017bec4  jz      short loc_18017BF02
0x18017bec6  mov     rax, cs:off_1802653E8; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x18017becd  test    rax, rax
0x18017bed0  jz      short loc_18017BF02
0x18017bed2  mov     ecx, 0C3B4h; unsigned int
0x18017bed7  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18017bedc  mov     dword ptr [rsp+58h+var_30], ebx
0x18017bee0  mov     dword ptr [rsp+58h+var_38], eax
0x18017bee4  mov     r9d, 5
0x18017beea  mov     r8, cs:off_1802653E8; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x18017bef1  mov     edx, 1EBC00h
0x18017bef6  mov     rcx, cs:off_1802620A0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017befd  call    _bidTraceW
0x18017bf02  mov     r8d, 0C3B4h
0x18017bf08  mov     edx, ebx
0x18017bf0a  mov     ecx, 5
0x18017bf0f  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18017bf14  mov     eax, cs:_bidGblFlags
0x18017bf1a  and     eax, 20002h
0x18017bf1f  cmp     eax, 20002h
0x18017bf24  jnz     loc_18017C133
0x18017bf2a  mov     rax, cs:off_1802653F0; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x18017bf31  test    rax, rax
0x18017bf34  jz      loc_18017C133
0x18017bf3a  mov     r9d, ebx
0x18017bf3d  mov     r8, cs:off_1802653F0; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x18017bf44  mov     edx, 1EC400h
0x18017bf49  mov     rcx, cs:off_1802620A8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017bf50  call    _bidTraceW
0x18017bf55  jmp     loc_18017C133
0x18017bf5a  lea     rdx, aInitsecurityin; "InitSecurityInterfaceW"
0x18017bf61  mov     rcx, rax; hModule
0x18017bf64  call    cs:__imp_GetProcAddress
0x18017bf6a  test    rax, rax
0x18017bf6d  jnz     loc_18017C030
0x18017bf73  call    cs:__imp_GetLastError
0x18017bf79  mov     ebx, eax
0x18017bf7b  mov     rcx, cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA; hLibModule
0x18017bf82  call    cs:__imp_FreeLibrary
0x18017bf88  mov     cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * Ssl::s_hSecurity
0x18017bf93  test    byte ptr cs:_bidGblFlags, 2
0x18017bf9a  jz      short loc_18017BFD8
0x18017bf9c  mov     rax, cs:off_1802653F8; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x18017bfa3  test    rax, rax
0x18017bfa6  jz      short loc_18017BFD8
0x18017bfa8  mov     ecx, 0C3B4h; unsigned int
0x18017bfad  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18017bfb2  mov     dword ptr [rsp+58h+var_30], ebx
0x18017bfb6  mov     dword ptr [rsp+58h+var_38], eax
0x18017bfba  mov     r9d, 5
0x18017bfc0  mov     r8, cs:off_1802653F8; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x18017bfc7  mov     edx, 1F0800h
0x18017bfcc  mov     rcx, cs:off_1802620B0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017bfd3  call    _bidTraceW
0x18017bfd8  mov     r8d, 0C3B4h
0x18017bfde  mov     edx, ebx
0x18017bfe0  mov     ecx, 5
0x18017bfe5  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18017bfea  mov     eax, cs:_bidGblFlags
0x18017bff0  and     eax, 20002h
0x18017bff5  cmp     eax, 20002h
0x18017bffa  jnz     loc_18017C133
0x18017c000  mov     rax, cs:off_180265400; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x18017c007  test    rax, rax
0x18017c00a  jz      loc_18017C133
0x18017c010  mov     r9d, ebx
0x18017c013  mov     r8, cs:off_180265400; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x18017c01a  mov     edx, 1F1000h
0x18017c01f  mov     rcx, cs:off_1802620B8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017c026  call    _bidTraceW
0x18017c02b  jmp     loc_18017C133
0x18017c030  call    cs:__guard_dispatch_icall_fptr
0x18017c036  mov     cs:?s_pfTable@Ssl@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA, rax; _SECURITY_FUNCTION_TABLE_W * Ssl::s_pfTable
0x18017c03d  test    rax, rax
0x18017c040  jnz     loc_18017C0F8
0x18017c046  call    cs:__imp_GetLastError
0x18017c04c  mov     ebx, eax
0x18017c04e  mov     rcx, cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA; hLibModule
0x18017c055  call    cs:__imp_FreeLibrary
0x18017c05b  mov     cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * Ssl::s_hSecurity
0x18017c066  test    byte ptr cs:_bidGblFlags, 2
0x18017c06d  jz      short loc_18017C0AB
0x18017c06f  mov     rax, cs:off_180265408; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x18017c076  test    rax, rax
0x18017c079  jz      short loc_18017C0AB
0x18017c07b  mov     ecx, 0C3B4h; unsigned int
0x18017c080  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18017c085  mov     dword ptr [rsp+58h+var_30], ebx
0x18017c089  mov     dword ptr [rsp+58h+var_38], eax
0x18017c08d  mov     r9d, 5
0x18017c093  mov     r8, cs:off_180265408; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x18017c09a  mov     edx, 1F4400h
0x18017c09f  mov     rcx, cs:off_1802620C0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017c0a6  call    _bidTraceW
0x18017c0ab  mov     r8d, 0C3B4h
0x18017c0b1  mov     edx, ebx
0x18017c0b3  mov     ecx, 5
0x18017c0b8  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18017c0bd  mov     eax, cs:_bidGblFlags
0x18017c0c3  and     eax, 20002h
0x18017c0c8  cmp     eax, 20002h
0x18017c0cd  jnz     short loc_18017C133
0x18017c0cf  mov     rax, cs:off_180265410; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x18017c0d6  test    rax, rax
0x18017c0d9  jz      short loc_18017C133
0x18017c0db  mov     r9d, ebx
0x18017c0de  mov     r8, cs:off_180265410; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x18017c0e5  mov     edx, 1F4C00h
0x18017c0ea  mov     rcx, cs:off_1802620C8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017c0f1  call    _bidTraceW
0x18017c0f6  jmp     short loc_18017C133
0x18017c0f8  mov     eax, cs:_bidGblFlags
0x18017c0fe  and     eax, 20002h
0x18017c103  cmp     eax, 20002h
0x18017c108  jnz     short loc_18017C131
0x18017c10a  mov     rax, cs:off_180265418; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x18017c111  test    rax, rax
0x18017c114  jz      short loc_18017C131
0x18017c116  xor     r9d, r9d
0x18017c119  mov     r8, cs:off_180265418; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x18017c120  mov     edx, 1F6000h
0x18017c125  mov     rcx, cs:off_1802620D0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017c12c  call    _bidTraceW
0x18017c131  xor     ebx, ebx
0x18017c133  lea     rcx, [rsp+58h+var_18]; this
0x18017c138  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18017c13d  nop
0x18017c13e  mov     eax, ebx
0x18017c140  mov     rcx, [rsp+58h+var_10]
0x18017c145  xor     rcx, rsp; StackCookie
0x18017c148  call    __security_check_cookie
0x18017c14d  add     rsp, 50h
0x18017c151  pop     rbx
0x18017c152  retn
```
