# GetLocalComputerName

- ea: `0x180010f2c`
- end: `0x180011030`
- name: `GetLocalComputerName`
- size: `260`
- prototype: `__int64 __fastcall(STRSAFE_LPSTR pszDest)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180015ae0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x180010f2c`
- `0x1800143dc`
- `0x18002a138`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x180010f77`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x180010f77`

## string_xrefs

- `0x180010fb3`: `GetLocalComputerName: StringCchPrintfA Failed`

## pseudocode

```c
int __fastcall GetLocalComputerName(STRSAFE_LPSTR pszDest)
{
  int result; // eax
  DWORD nSize; // [rsp+30h] [rbp-848h] BYREF
  CHAR Buffer[40]; // [rsp+38h] [rbp-840h] BYREF
  int v5; // [rsp+60h] [rbp-818h] BYREF
  _BYTE v6[2044]; // [rsp+64h] [rbp-814h] BYREF

  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  *pszDest = 0;
  nSize = 25;
  result = GetComputerNameA(Buffer, &nSize);
  if ( !result )
    goto LABEL_5;
  result = StringCchPrintfA(pszDest, 0x19u, "%hs%hs", "MSRAS-0-", Buffer);
  if ( result < 0 )
  {
    if ( byte_18004CF33 < 0 )
      result = McTemplateU0z_EventWriteTransfer(
                 &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                 RasPppTraceError,
                 L"GetLocalComputerName: StringCchPrintfA Failed");
LABEL_5:
    *pszDest = 0;
    return result;
  }
  if ( (byte_18004CF34 & 1) != 0 )
  {
    LOWORD(v5) = 0;
    result = FormatRRASErrorString(&v5, L"Local identification = %hs", pszDest);
    if ( (byte_18004CF34 & 1) != 0 )
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v5);
  }
  return result;
}

```

## disassembly

```asm
0x180010f2c  push    rbx
0x180010f2e  sub     rsp, 870h
0x180010f35  mov     rax, cs:__security_cookie
0x180010f3c  xor     rax, rsp
0x180010f3f  mov     [rsp+878h+var_18], rax
0x180010f47  mov     rbx, rcx
0x180010f4a  xor     eax, eax
0x180010f4c  lea     rcx, [rsp+878h+var_814]; void *
0x180010f51  mov     [rsp+878h+var_818], eax
0x180010f55  xor     edx, edx; Val
0x180010f57  mov     r8d, 7FCh; Size
0x180010f5d  call    memset_0
0x180010f62  lea     rdx, [rsp+878h+nSize]; nSize
0x180010f67  mov     byte ptr [rbx], 0
0x180010f6a  lea     rcx, [rsp+878h+Buffer]; lpBuffer
0x180010f6f  mov     [rsp+878h+nSize], 19h
0x180010f77  call    cs:__imp_GetComputerNameA
0x180010f7d  test    eax, eax
0x180010f7f  jz      short loc_180010FCD
0x180010f81  lea     rax, [rsp+878h+Buffer]
0x180010f86  mov     edx, 19h; cchDest
0x180010f8b  lea     r9, SubStr; "MSRAS-0-"
0x180010f92  mov     [rsp+878h+var_858], rax
0x180010f97  lea     r8, pszFormat; "%hs%hs"
0x180010f9e  mov     rcx, rbx; pszDest
0x180010fa1  call    StringCchPrintfA
0x180010fa6  test    eax, eax
0x180010fa8  jns     short loc_180010FE9
0x180010faa  test    cs:byte_18004CF33, 80h
0x180010fb1  jz      short loc_180010FCD
0x180010fb3  lea     r8, aGetlocalcomput; "GetLocalComputerName: StringCchPrintfA "...
0x180010fba  lea     rdx, RasPppTraceError
0x180010fc1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010fc8  call    McTemplateU0z_EventWriteTransfer
0x180010fcd  mov     byte ptr [rbx], 0
0x180010fd0  mov     rcx, [rsp+878h+var_18]
0x180010fd8  xor     rcx, rsp; StackCookie
0x180010fdb  call    __security_check_cookie
0x180010fe0  add     rsp, 870h
0x180010fe7  pop     rbx
0x180010fe8  retn
0x180010fe9  test    cs:byte_18004CF34, 1
0x180010ff0  jz      short loc_180010FD0
0x180010ff2  xor     eax, eax
0x180010ff4  lea     rdx, aLocalIdentific; "Local identification = %hs"
0x180010ffb  mov     r8, rbx
0x180010ffe  mov     word ptr [rsp+878h+var_818], ax
0x180011003  lea     rcx, [rsp+878h+var_818]
0x180011008  call    FormatRRASErrorString
0x18001100d  test    cs:byte_18004CF34, 1
0x180011014  jz      short loc_180010FD0
0x180011016  lea     r8, [rsp+878h+var_818]
0x18001101b  lea     rdx, RasPppTraceInfo
0x180011022  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011029  call    McTemplateU0z_EventWriteTransfer
0x18001102e  jmp     short loc_180010FD0
```
