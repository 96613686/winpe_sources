# CMachineEnroller::DeleteTemporaryFiles(void)

- ea: `0x18004ecb8`
- end: `0x18004ee0b`
- name: `?DeleteTemporaryFiles@CMachineEnroller@@SAJXZ`
- size: `339`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180050558`
- `0x180077490`

## callees

- `0x180007040`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x180032f20`
- `0x18004ecb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ed70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ed70`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004ede1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004ede1`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18004ed66`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18004ed66`

## string_xrefs

- `0x18004ed5a`: `MachineEnrollmentProv.xml`
- `0x18004ed42`: `UpdatedProvXML.txt`
- `0x18004ed36`: `FailedProvXML.txt`
- `0x18004ed4e`: `ReceivedProvXML.txt`

## pseudocode

```c
__int64 CMachineEnroller::DeleteTemporaryFiles(void)
{
  signed int LastError; // eax
  int v1; // ebx
  unsigned int i; // edi
  unsigned __int16 *v4[6]; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v5; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v6[526]; // [rsp+52h] [rbp-AEh] BYREF
  WCHAR FileName; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v8[526]; // [rsp+262h] [rbp+162h] BYREF

  v5 = 0;
  memset_0(v6, 0, 0x206u);
  FileName = 0;
  memset_0(v8, 0, 0x206u);
  v4[0] = L"SoapRequest.txt";
  v4[1] = L"SoapResponse.txt";
  v4[2] = L"FailedProvXML.txt";
  v4[3] = L"UpdatedProvXML.txt";
  v4[4] = L"ReceivedProvXML.txt";
  v4[5] = L"MachineEnrollmentProv.xml";
  if ( (unsigned int)GetTempPath2W(260, &v5) )
  {
    v1 = StringCchCatW(&v5, 0x104u, L"\\");
    if ( v1 >= 0 )
    {
      for ( i = 0; i < 6; ++i )
      {
        v1 = StringCchCopyW(&FileName, 0x104u, &v5);
        if ( v1 < 0 )
          break;
        v1 = StringCchCatW(&FileName, 0x104u, v4[i]);
        if ( v1 < 0 )
          break;
        DeleteFileW(&FileName);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18004ecb8  push    rbp
0x18004ecba  push    rbx
0x18004ecbb  push    rsi
0x18004ecbc  push    rdi
0x18004ecbd  lea     rbp, [rsp-388h]
0x18004ecc5  sub     rsp, 488h
0x18004eccc  mov     rax, cs:__security_cookie
0x18004ecd3  xor     rax, rsp
0x18004ecd6  mov     [rbp+3A0h+var_30], rax
0x18004ecdd  xor     eax, eax
0x18004ecdf  lea     rcx, [rsp+4A0h+var_44E]; void *
0x18004ece4  mov     ebx, 206h
0x18004ece9  mov     [rsp+4A0h+var_450], ax
0x18004ecee  mov     r8d, ebx; Size
0x18004ecf1  xor     edx, edx; Val
0x18004ecf3  call    memset_0
0x18004ecf8  xor     eax, eax
0x18004ecfa  lea     rcx, [rbp+3A0h+var_23E]; void *
0x18004ed01  mov     r8d, ebx; Size
0x18004ed04  mov     [rbp+3A0h+FileName], ax
0x18004ed0b  xor     edx, edx; Val
0x18004ed0d  call    memset_0
0x18004ed12  lea     rax, aSoaprequestTxt; "SoapRequest.txt"
0x18004ed19  mov     esi, 104h
0x18004ed1e  mov     [rsp+4A0h+var_480], rax
0x18004ed23  lea     rdx, [rsp+4A0h+var_450]
0x18004ed28  lea     rax, aSoapresponseTx; "SoapResponse.txt"
0x18004ed2f  mov     ecx, esi
0x18004ed31  mov     [rsp+4A0h+var_478], rax
0x18004ed36  lea     rax, aFailedprovxmlT; "FailedProvXML.txt"
0x18004ed3d  mov     [rsp+4A0h+var_470], rax
0x18004ed42  lea     rax, aUpdatedprovxml; "UpdatedProvXML.txt"
0x18004ed49  mov     [rsp+4A0h+var_468], rax
0x18004ed4e  lea     rax, aReceivedprovxm; "ReceivedProvXML.txt"
0x18004ed55  mov     [rsp+4A0h+var_460], rax
0x18004ed5a  lea     rax, aMachineenrollm; "MachineEnrollmentProv.xml"
0x18004ed61  mov     [rsp+4A0h+var_458], rax
0x18004ed66  call    cs:__imp_GetTempPath2W
0x18004ed6c  test    eax, eax
0x18004ed6e  jnz     short loc_18004ED87
0x18004ed70  call    cs:__imp_GetLastError
0x18004ed76  mov     ebx, eax
0x18004ed78  test    eax, eax
0x18004ed7a  jle     short loc_18004EDEE
0x18004ed7c  movzx   ebx, ax
0x18004ed7f  or      ebx, 80070000h
0x18004ed85  jmp     short loc_18004EDEE
0x18004ed87  lea     r8, asc_18007FF94; "\\"
0x18004ed8e  mov     rdx, rsi; unsigned __int64
0x18004ed91  lea     rcx, [rsp+4A0h+var_450]; unsigned __int16 *
0x18004ed96  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004ed9b  mov     ebx, eax
0x18004ed9d  test    eax, eax
0x18004ed9f  js      short loc_18004EDEE
0x18004eda1  xor     edi, edi
0x18004eda3  lea     r8, [rsp+4A0h+var_450]; unsigned __int16 *
0x18004eda8  mov     rdx, rsi; unsigned __int64
0x18004edab  lea     rcx, [rbp+3A0h+FileName]; unsigned __int16 *
0x18004edb2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004edb7  mov     ebx, eax
0x18004edb9  test    eax, eax
0x18004edbb  js      short loc_18004EDEE
0x18004edbd  movsxd  r8, edi
0x18004edc0  lea     rcx, [rbp+3A0h+FileName]; unsigned __int16 *
0x18004edc7  mov     rdx, rsi; unsigned __int64
0x18004edca  mov     r8, [rsp+r8*8+4A0h+var_480]; unsigned __int16 *
0x18004edcf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004edd4  mov     ebx, eax
0x18004edd6  test    eax, eax
0x18004edd8  js      short loc_18004EDEE
0x18004edda  lea     rcx, [rbp+3A0h+FileName]; lpFileName
0x18004ede1  call    cs:__imp_DeleteFileW
0x18004ede7  inc     edi
0x18004ede9  cmp     edi, 6
0x18004edec  jb      short loc_18004EDA3
0x18004edee  mov     eax, ebx
0x18004edf0  mov     rcx, [rbp+3A0h+var_30]
0x18004edf7  xor     rcx, rsp; StackCookie
0x18004edfa  call    __security_check_cookie
0x18004edff  add     rsp, 488h
0x18004ee06  pop     rdi
0x18004ee07  pop     rsi
0x18004ee08  pop     rbx
0x18004ee09  pop     rbp
0x18004ee0a  retn
```
