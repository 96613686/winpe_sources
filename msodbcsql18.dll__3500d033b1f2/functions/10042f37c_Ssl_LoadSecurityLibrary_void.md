# Ssl::LoadSecurityLibrary(void)

- ea: `0x10042f37c`
- end: `0x10042f650`
- name: `?LoadSecurityLibrary@Ssl@@CAKXZ`
- size: `724`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10042ec14`

## callees

- `0x100417768`
- `0x10042f37c`
- `0x10043a7c4`
- `0x10043a930`
- `0x100545d84`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10042f401`
- `KERNEL32!GetLastError` at `0x10042f4aa`
- `KERNEL32!GetLastError` at `0x10042f565`
- `KERNEL32!GetLastError` at `0x10042f401`
- `KERNEL32!GetLastError` at `0x10042f4aa`
- `KERNEL32!GetLastError` at `0x10042f565`
- `KERNEL32!GetProcAddress` at `0x10042f49b`
- `KERNEL32!GetProcAddress` at `0x10042f49b`
- `KERNEL32!FreeLibrary` at `0x10042f4b9`
- `KERNEL32!FreeLibrary` at `0x10042f574`
- `KERNEL32!FreeLibrary` at `0x10042f4b9`
- `KERNEL32!FreeLibrary` at `0x10042f574`

## string_xrefs

- `0x10042f3e5`: `secur32.dll`
- `0x10042f491`: `InitSecurityInterfaceW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Ssl::LoadSecurityLibrary(void)
{
  HMODULE v0; // rax
  DWORD LastError; // ebx
  wchar_t *v2; // r8
  __int64 v3; // rdx
  __int64 (*ProcAddress)(void); // rax
  __int64 v6; // [rsp+60h] [rbp+8h] BYREF

  v6 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7C70[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_1005D39F0)(
      bidID,
      0,
      0,
      &v6,
      off_1005E7C70[0],
      0);
  v0 = SNILoadSystemLibA("secur32.dll");
  Ssl::s_hSecurity = v0;
  if ( v0 )
  {
    ProcAddress = GetProcAddress(v0, "InitSecurityInterfaceW");
    if ( ProcAddress )
    {
      Ssl::s_pfTable = (struct _SECURITY_FUNCTION_TABLE_W *)ProcAddress();
      if ( Ssl::s_pfTable )
      {
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E55B0[0] )
          bidTraceW(0, 2622464, off_1005E55B0[0], 0);
        LastError = 0;
      }
      else
      {
        LastError = GetLastError();
        FreeLibrary(Ssl::s_hSecurity);
        Ssl::s_hSecurity = 0;
        if ( (bidGblFlags & 2) != 0 && off_1005E55A0[0] )
        {
          SniErrorIdFromStringId(0xC3B4u);
          bidTraceW(0, 2615296, off_1005E55A0[0], 6);
        }
        SNISetLastError(6, LastError, 50100);
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E55A8[0] )
        {
          v2 = off_1005E55A8[0];
          v3 = 2617344;
          goto LABEL_26;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      FreeLibrary(Ssl::s_hSecurity);
      Ssl::s_hSecurity = 0;
      if ( (bidGblFlags & 2) != 0 && off_1005E5590[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(0, 2599936, off_1005E5590[0], 6);
      }
      SNISetLastError(6, LastError, 50100);
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5598[0] )
      {
        v2 = off_1005E5598[0];
        v3 = 2601984;
        goto LABEL_26;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_1005E5580[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(0, 2580480, off_1005E5580[0], 6);
    }
    SNISetLastError(6, LastError, 50100);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5588[0] )
    {
      v2 = off_1005E5588[0];
      v3 = 2582528;
LABEL_26:
      bidTraceW(0, v3, v2, LastError);
    }
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v6);
  return LastError;
}

```

## disassembly

```asm
0x10042f37c  mov     r11, rsp
0x10042f37f  push    rbx
0x10042f380  sub     rsp, 50h
0x10042f384  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x10042f38c  or      qword ptr [r11+8], 0FFFFFFFFFFFFFFFFh
0x10042f391  mov     eax, cs:_bidGblFlags
0x10042f397  mov     ecx, 20004h
0x10042f39c  and     eax, ecx
0x10042f39e  cmp     eax, ecx
0x10042f3a0  jnz     short loc_10042F3E5
0x10042f3a2  mov     rax, cs:off_1005E7C70; "<Ssl::LoadSecurityLibrary|API|SNI> \n"
0x10042f3a9  test    rax, rax
0x10042f3ac  jz      short loc_10042F3E5
0x10042f3ae  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10042f3b6  jz      short loc_10042F3E5
0x10042f3b8  mov     rax, cs:off_1005D39F0
0x10042f3bf  and     qword ptr [r11-30h], 0
0x10042f3c4  mov     rcx, cs:off_1005E7C70; "<Ssl::LoadSecurityLibrary|API|SNI> \n"
0x10042f3cb  mov     [r11-38h], rcx
0x10042f3cf  lea     r9, [r11+8]
0x10042f3d3  xor     r8d, r8d
0x10042f3d6  xor     edx, edx
0x10042f3d8  mov     rcx, cs:_bidID
0x10042f3df  call    cs:__guard_dispatch_icall_fptr
0x10042f3e5  lea     rcx, aSecur32Dll_0; "secur32.dll"
0x10042f3ec  call    SNILoadSystemLibA
0x10042f3f1  mov     cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Ssl::s_hSecurity
0x10042f3f8  test    rax, rax
0x10042f3fb  jnz     loc_10042F491
0x10042f401  call    cs:__imp_GetLastError
0x10042f407  mov     ebx, eax
0x10042f409  test    byte ptr cs:_bidGblFlags, 2
0x10042f410  jz      short loc_10042F449
0x10042f412  mov     rax, cs:off_1005E5580; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x10042f419  test    rax, rax
0x10042f41c  jz      short loc_10042F449
0x10042f41e  mov     ecx, 0C3B4h; unsigned int
0x10042f423  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10042f428  mov     [rsp+58h+var_30], ebx
0x10042f42c  mov     [rsp+58h+var_38], eax
0x10042f430  mov     r9d, 6
0x10042f436  mov     r8, cs:off_1005E5580; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x10042f43d  mov     edx, 276000h
0x10042f442  xor     ecx, ecx
0x10042f444  call    _bidTraceW
0x10042f449  mov     r8d, 0C3B4h
0x10042f44f  mov     edx, ebx
0x10042f451  mov     ecx, 6
0x10042f456  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10042f45b  mov     eax, cs:_bidGblFlags
0x10042f461  mov     ecx, 20002h
0x10042f466  and     eax, ecx
0x10042f468  cmp     eax, ecx
0x10042f46a  jnz     loc_10042F63E
0x10042f470  mov     rax, cs:off_1005E5588; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x10042f477  test    rax, rax
0x10042f47a  jz      loc_10042F63E
0x10042f480  mov     r8, cs:off_1005E5588; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x10042f487  mov     edx, 276800h
0x10042f48c  jmp     loc_10042F5FD
0x10042f491  lea     rdx, aInitsecurityin; "InitSecurityInterfaceW"
0x10042f498  mov     rcx, rax; hModule
0x10042f49b  call    cs:__imp_GetProcAddress
0x10042f4a1  test    rax, rax
0x10042f4a4  jnz     loc_10042F54F
0x10042f4aa  call    cs:__imp_GetLastError
0x10042f4b0  mov     ebx, eax
0x10042f4b2  mov     rcx, cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA; hLibModule
0x10042f4b9  call    cs:__imp_FreeLibrary
0x10042f4bf  and     cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * Ssl::s_hSecurity
0x10042f4c7  test    byte ptr cs:_bidGblFlags, 2
0x10042f4ce  jz      short loc_10042F507
0x10042f4d0  mov     rax, cs:off_1005E5590; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x10042f4d7  test    rax, rax
0x10042f4da  jz      short loc_10042F507
0x10042f4dc  mov     ecx, 0C3B4h; unsigned int
0x10042f4e1  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10042f4e6  mov     [rsp+58h+var_30], ebx
0x10042f4ea  mov     [rsp+58h+var_38], eax
0x10042f4ee  mov     r9d, 6
0x10042f4f4  mov     r8, cs:off_1005E5590; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x10042f4fb  mov     edx, 27AC00h
0x10042f500  xor     ecx, ecx
0x10042f502  call    _bidTraceW
0x10042f507  mov     r8d, 0C3B4h
0x10042f50d  mov     edx, ebx
0x10042f50f  mov     ecx, 6
0x10042f514  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10042f519  mov     eax, cs:_bidGblFlags
0x10042f51f  mov     ecx, 20002h
0x10042f524  and     eax, ecx
0x10042f526  cmp     eax, ecx
0x10042f528  jnz     loc_10042F63E
0x10042f52e  mov     rax, cs:off_1005E5598; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x10042f535  test    rax, rax
0x10042f538  jz      loc_10042F63E
0x10042f53e  mov     r8, cs:off_1005E5598; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x10042f545  mov     edx, 27B400h
0x10042f54a  jmp     loc_10042F5FD
0x10042f54f  call    cs:__guard_dispatch_icall_fptr
0x10042f555  mov     cs:?s_pfTable@Ssl@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA, rax; _SECURITY_FUNCTION_TABLE_W * Ssl::s_pfTable
0x10042f55c  test    rax, rax
0x10042f55f  jnz     loc_10042F609
0x10042f565  call    cs:__imp_GetLastError
0x10042f56b  mov     ebx, eax
0x10042f56d  mov     rcx, cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA; hLibModule
0x10042f574  call    cs:__imp_FreeLibrary
0x10042f57a  and     cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * Ssl::s_hSecurity
0x10042f582  test    byte ptr cs:_bidGblFlags, 2
0x10042f589  jz      short loc_10042F5C2
0x10042f58b  mov     rax, cs:off_1005E55A0; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x10042f592  test    rax, rax
0x10042f595  jz      short loc_10042F5C2
0x10042f597  mov     ecx, 0C3B4h; unsigned int
0x10042f59c  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10042f5a1  mov     [rsp+58h+var_30], ebx
0x10042f5a5  mov     [rsp+58h+var_38], eax
0x10042f5a9  mov     r9d, 6
0x10042f5af  mov     r8, cs:off_1005E55A0; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x10042f5b6  mov     edx, 27E800h
0x10042f5bb  xor     ecx, ecx
0x10042f5bd  call    _bidTraceW
0x10042f5c2  mov     r8d, 0C3B4h
0x10042f5c8  mov     edx, ebx
0x10042f5ca  mov     ecx, 6
0x10042f5cf  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10042f5d4  mov     eax, cs:_bidGblFlags
0x10042f5da  mov     ecx, 20002h
0x10042f5df  and     eax, ecx
0x10042f5e1  cmp     eax, ecx
0x10042f5e3  jnz     short loc_10042F63E
0x10042f5e5  mov     rax, cs:off_1005E55A8; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x10042f5ec  test    rax, rax
0x10042f5ef  jz      short loc_10042F63E
0x10042f5f1  mov     r8, cs:off_1005E55A8; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x10042f5f8  mov     edx, 27F000h
0x10042f5fd  mov     r9d, ebx
0x10042f600  xor     ecx, ecx
0x10042f602  call    _bidTraceW
0x10042f607  jmp     short loc_10042F63E
0x10042f609  mov     eax, cs:_bidGblFlags
0x10042f60f  mov     ecx, 20002h
0x10042f614  and     eax, ecx
0x10042f616  cmp     eax, ecx
0x10042f618  jnz     short loc_10042F63C
0x10042f61a  mov     rax, cs:off_1005E55B0; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x10042f621  test    rax, rax
0x10042f624  jz      short loc_10042F63C
0x10042f626  xor     r9d, r9d
0x10042f629  mov     r8, cs:off_1005E55B0; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x10042f630  mov     edx, 280400h
0x10042f635  xor     ecx, ecx
0x10042f637  call    _bidTraceW
0x10042f63c  xor     ebx, ebx
0x10042f63e  lea     rcx, [rsp+58h+arg_0]; this
0x10042f643  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x10042f648  mov     eax, ebx
0x10042f64a  add     rsp, 50h
0x10042f64e  pop     rbx
0x10042f64f  retn
```
