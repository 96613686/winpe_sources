# BuildExceptionInfo(IErrorInfo *,STRU *)

- ea: `0x18002a880`
- end: `0x18002aabe`
- name: `?BuildExceptionInfo@@YAJPEAUIErrorInfo@@PEAVSTRU@@@Z`
- size: `574`
- prototype: `__int64 __fastcall(struct IErrorInfo *, struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180014288`

## callees

- `0x18002a880`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!_ultow` at `0x18002a9a2`
- `msvcrt!_ultow` at `0x18002a9a2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aa61`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aa78`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aa61`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aa78`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002a9eb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002a9eb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002a9fe`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002aa14`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002aa27`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002aa3d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002aa50`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002a9fe`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002aa14`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002aa27`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002aa3d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002aa50`
- `iisutil!PuDbgPrintError` at `0x18002a91b`
- `iisutil!PuDbgPrintError` at `0x18002a91b`

## string_xrefs

- `0x18002a8f0`: ` Failed to QI for the Config Exception \n`
- `0x18002a9e1`: `Configuration error: `

## pseudocode

```c
__int64 __fastcall BuildExceptionInfo(struct IErrorInfo *a1, struct STRU *a2)
{
  struct IErrorInfoVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IErrorInfo *, const IID *const, void **); // rax
  int v5; // ebx
  unsigned int Value; // [rsp+30h] [rbp-29h] BYREF
  __int64 v8; // [rsp+38h] [rbp-21h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-19h] BYREF
  BSTR v10; // [rsp+48h] [rbp-11h] BYREF
  wchar_t Buffer[40]; // [rsp+50h] [rbp-9h] BYREF

  lpVtbl = a1->lpVtbl;
  Value = 0;
  bstrString = 0;
  v10 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  v8 = 0;
  v5 = ((__int64 (__fastcall *)(struct IErrorInfo *, GUID *, __int64 *))QueryInterface)(
         a1,
         &GUID_4dfa1df3_8900_4bc7_bbb5_d1a458c52410,
         &v8);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v8 + 32LL))(v8, &bstrString);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v8 + 24LL))(v8, &Value);
      if ( v5 >= 0 )
      {
        _ultow(Value, Buffer, 10);
        v5 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v8 + 72LL))(v8, &v10);
        if ( v5 >= 0 )
        {
          v5 = STRU::Copy(a2, L"Configuration error: ");
          if ( v5 >= 0 )
          {
            v5 = STRU::Append(a2, v10);
            if ( v5 >= 0 )
            {
              v5 = STRU::Append(a2, L"Filename: ");
              if ( v5 >= 0 )
              {
                v5 = STRU::Append(a2, bstrString);
                if ( v5 >= 0 )
                {
                  v5 = STRU::Append(a2, L"\r\nLine: ");
                  if ( v5 >= 0 )
                    v5 = STRU::Append(a2, Buffer);
                }
              }
            }
          }
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          PuDbgPrintError(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_util\\ftp_util.cxx",
            1411,
            "BuildExceptionInfo",
            v5,
            " Failed to get error string for exception\n");
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_util\\ftp_util.cxx",
          1397,
          "BuildExceptionInfo",
          v5,
          " Failed to get error line number for exception \n");
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_util\\ftp_util.cxx",
        1386,
        "BuildExceptionInfo",
        v5,
        " Failed to get error filename for exception\n");
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_util\\ftp_util.cxx",
      1375,
      "BuildExceptionInfo",
      v5,
      " Failed to QI for the Config Exception \n");
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v10 )
  {
    SysFreeString(v10);
    v10 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002a880  mov     [rsp-8+arg_10], rbx
0x18002a885  mov     [rsp-8+arg_18], rdi
0x18002a88a  push    rbp
0x18002a88b  lea     rbp, [rsp-57h]
0x18002a890  sub     rsp, 0B0h
0x18002a897  mov     rax, cs:__security_cookie
0x18002a89e  xor     rax, rsp
0x18002a8a1  mov     [rbp+57h+var_10], rax
0x18002a8a5  mov     rax, [rcx]
0x18002a8a8  lea     r8, [rbp+57h+var_78]
0x18002a8ac  mov     rdi, rdx
0x18002a8af  mov     [rbp+57h+Value], 0
0x18002a8b6  lea     rdx, _GUID_4dfa1df3_8900_4bc7_bbb5_d1a458c52410
0x18002a8bd  mov     [rbp+57h+bstrString], 0
0x18002a8c5  mov     [rbp+57h+var_68], 0
0x18002a8cd  mov     rax, [rax]
0x18002a8d0  mov     [rbp+57h+var_78], 0
0x18002a8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a8dd  mov     ebx, eax
0x18002a8df  test    eax, eax
0x18002a8e1  jns     short loc_18002A926
0x18002a8e3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a8ea  jz      loc_18002AA58
0x18002a8f0  lea     rax, aFailedToQiForT; " Failed to QI for the Config Exception "...
0x18002a8f7  mov     r8d, 55Fh
0x18002a8fd  mov     rcx, cs:g_pDebug
0x18002a904  lea     r9, aBuildexception; "BuildExceptionInfo"
0x18002a90b  mov     [rsp+0B0h+var_88], rax
0x18002a910  lea     rdx, aInetsrvIisIisr_12; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18002a917  mov     [rsp+0B0h+var_90], ebx
0x18002a91b  call    cs:__imp_PuDbgPrintError
0x18002a921  jmp     loc_18002AA58
0x18002a926  mov     rcx, [rbp+57h+var_78]
0x18002a92a  lea     rdx, [rbp+57h+bstrString]
0x18002a92e  mov     rax, [rcx]
0x18002a931  mov     rax, [rax+20h]
0x18002a935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a93a  mov     ebx, eax
0x18002a93c  test    eax, eax
0x18002a93e  jns     short loc_18002A95C
0x18002a940  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a947  jz      loc_18002AA58
0x18002a94d  lea     rax, aFailedToGetErr; " Failed to get error filename for excep"...
0x18002a954  mov     r8d, 56Ah
0x18002a95a  jmp     short loc_18002A8FD
0x18002a95c  mov     rcx, [rbp+57h+var_78]
0x18002a960  lea     rdx, [rbp+57h+Value]
0x18002a964  mov     rax, [rcx]
0x18002a967  mov     rax, [rax+18h]
0x18002a96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a970  mov     ebx, eax
0x18002a972  test    eax, eax
0x18002a974  jns     short loc_18002A995
0x18002a976  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a97d  jz      loc_18002AA58
0x18002a983  lea     rax, aFailedToGetErr_1; " Failed to get error line number for ex"...
0x18002a98a  mov     r8d, 575h
0x18002a990  jmp     loc_18002A8FD
0x18002a995  mov     ecx, [rbp+57h+Value]; Value
0x18002a998  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18002a99c  mov     r8d, 0Ah; Radix
0x18002a9a2  call    cs:__imp__ultow
0x18002a9a8  mov     rcx, [rbp+57h+var_78]
0x18002a9ac  lea     rdx, [rbp+57h+var_68]
0x18002a9b0  mov     rax, [rcx]
0x18002a9b3  mov     rax, [rax+48h]
0x18002a9b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9bc  mov     ebx, eax
0x18002a9be  test    eax, eax
0x18002a9c0  jns     short loc_18002A9E1
0x18002a9c2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a9c9  jz      loc_18002AA58
0x18002a9cf  lea     rax, aFailedToGetErr_0; " Failed to get error string for excepti"...
0x18002a9d6  mov     r8d, 583h
0x18002a9dc  jmp     loc_18002A8FD
0x18002a9e1  lea     rdx, aConfigurationE; "Configuration error: "
0x18002a9e8  mov     rcx, rdi
0x18002a9eb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002a9f1  mov     ebx, eax
0x18002a9f3  test    eax, eax
0x18002a9f5  js      short loc_18002AA58
0x18002a9f7  mov     rdx, [rbp+57h+var_68]
0x18002a9fb  mov     rcx, rdi
0x18002a9fe  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002aa04  mov     ebx, eax
0x18002aa06  test    eax, eax
0x18002aa08  js      short loc_18002AA58
0x18002aa0a  lea     rdx, aFilename; "Filename: "
0x18002aa11  mov     rcx, rdi
0x18002aa14  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002aa1a  mov     ebx, eax
0x18002aa1c  test    eax, eax
0x18002aa1e  js      short loc_18002AA58
0x18002aa20  mov     rdx, [rbp+57h+bstrString]
0x18002aa24  mov     rcx, rdi
0x18002aa27  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002aa2d  mov     ebx, eax
0x18002aa2f  test    eax, eax
0x18002aa31  js      short loc_18002AA58
0x18002aa33  lea     rdx, aLine; "\r\nLine: "
0x18002aa3a  mov     rcx, rdi
0x18002aa3d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002aa43  mov     ebx, eax
0x18002aa45  test    eax, eax
0x18002aa47  js      short loc_18002AA58
0x18002aa49  lea     rdx, [rbp+57h+Buffer]
0x18002aa4d  mov     rcx, rdi
0x18002aa50  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002aa56  mov     ebx, eax
0x18002aa58  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002aa5c  test    rcx, rcx
0x18002aa5f  jz      short loc_18002AA6F
0x18002aa61  call    cs:__imp_SysFreeString
0x18002aa67  mov     [rbp+57h+bstrString], 0
0x18002aa6f  mov     rcx, [rbp+57h+var_68]; bstrString
0x18002aa73  test    rcx, rcx
0x18002aa76  jz      short loc_18002AA86
0x18002aa78  call    cs:__imp_SysFreeString
0x18002aa7e  mov     [rbp+57h+var_68], 0
0x18002aa86  mov     rcx, [rbp+57h+var_78]
0x18002aa8a  test    rcx, rcx
0x18002aa8d  jz      short loc_18002AA9B
0x18002aa8f  mov     rax, [rcx]
0x18002aa92  mov     rax, [rax+10h]
0x18002aa96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa9b  mov     eax, ebx
0x18002aa9d  mov     rcx, [rbp+57h+var_10]
0x18002aaa1  xor     rcx, rsp; StackCookie
0x18002aaa4  call    __security_check_cookie
0x18002aaa9  lea     r11, [rsp+0B0h+var_s0]
0x18002aab1  mov     rbx, [r11+20h]
0x18002aab5  mov     rdi, [r11+28h]
0x18002aab9  mov     rsp, r11
0x18002aabc  pop     rbp
0x18002aabd  retn
```
