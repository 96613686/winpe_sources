# DirectoryServerUtil::GetGuidStringFromOctetString(char const *,ulong,ushort * *)

- ea: `0x18004af2c`
- end: `0x18004b0c0`
- name: `?GetGuidStringFromOctetString@DirectoryServerUtil@@CAJPEBDKPEAPEAG@Z`
- size: `404`
- prototype: `__int64 __fastcall(const char *Src, size_t Size, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18004b0c8`

## callees

- `0x1800084f4`
- `0x18000ddf0`
- `0x1800307c4`
- `0x180043ef8`
- `0x180044300`
- `0x180044c56`
- `0x180046ac1`
- `0x18004af2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004b011`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004b011`
- `RPCRT4!RpcStringFreeW` at `0x18004b094`
- `RPCRT4!RpcStringFreeW` at `0x18004b094`
- `RPCRT4!UuidToStringW` at `0x18004afef`
- `RPCRT4!UuidToStringW` at `0x18004afef`

## string_xrefs

- `0x18004b063`: `CopyStringW`
- `0x18004af74`: `DirectoryServerUtil::GetGuidStringFromOctetString`
- `0x18004af8e`: `DirectoryServerUtil::GetGuidStringFromOctetString`
- `0x18004afb0`: `DirectoryServerUtil::GetGuidStringFromOctetString`
- `0x18004affc`: `DirectoryServerUtil::GetGuidStringFromOctetString`
- `0x18004b025`: `DirectoryServerUtil::GetGuidStringFromOctetString`
- `0x18004b06a`: `DirectoryServerUtil::GetGuidStringFromOctetString`

## pseudocode

```c
__int64 __fastcall DirectoryServerUtil::GetGuidStringFromOctetString(
        const char *Src,
        size_t Size,
        unsigned __int16 **a3)
{
  unsigned __int16 *v5; // rdi
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rdx
  unsigned int v8; // eax
  unsigned __int64 v9; // rdx
  int v10; // eax
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int16 *v13; // [rsp+28h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-20h] BYREF

  StringUuid = 0;
  v13 = 0;
  v5 = 0;
  Uuid = 0;
  if ( !Src )
  {
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DirectoryServerUtil::GetGuidStringFromOctetString",
      L"pcszInput");
    v7 = L"pcszInput";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DirectoryServerUtil::GetGuidStringFromOctetString", v7);
    goto LABEL_18;
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DirectoryServerUtil::GetGuidStringFromOctetString",
      L"ppszGuidString");
    v7 = L"ppszGuidString";
    goto LABEL_3;
  }
  *a3 = 0;
  if ( (_DWORD)Size )
  {
    if ( (unsigned int)Size > 0x10 )
    {
      *(_DWORD *)_o__errno() = 34;
      invalid_parameter_noinfo();
      Logger::TraceError(
        L"%s: Unable to convert the input \"%hs\" into GUID object.",
        L"DirectoryServerUtil::GetGuidStringFromOctetString",
        Src);
      goto LABEL_12;
    }
    memcpy_0(&Uuid, Src, (unsigned int)Size);
  }
  v8 = UuidToStringW(&Uuid, &StringUuid);
  if ( v8 )
  {
    Logger::TraceError(
      L"%s: UuidToStringW failed with error code (RPC_STATUS): 0x%08x",
      L"DirectoryServerUtil::GetGuidStringFromOctetString",
      v8);
LABEL_12:
    v6 = -2147024809;
    goto LABEL_18;
  }
  v9 = -1;
  do
    ++v9;
  while ( StringUuid[v9] );
  v10 = CopyStringW(StringUuid, v9, &v13);
  v6 = v10;
  if ( v10 >= 0 )
  {
    *a3 = v13;
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DirectoryServerUtil::GetGuidStringFromOctetString",
      L"CopyStringW",
      (unsigned int)v10);
    v5 = v13;
  }
LABEL_18:
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  if ( v5 )
    operator delete(v5);
  return v6;
}

```

## disassembly

```asm
0x18004af2c  push    rbp
0x18004af2e  push    rbx
0x18004af2f  push    rsi
0x18004af30  push    rdi
0x18004af31  push    r14
0x18004af33  mov     rbp, rsp
0x18004af36  sub     rsp, 50h
0x18004af3a  mov     rax, cs:__security_cookie
0x18004af41  xor     rax, rsp
0x18004af44  mov     [rbp+var_10], rax
0x18004af48  xor     r14d, r14d
0x18004af4b  xorps   xmm0, xmm0
0x18004af4e  mov     [rbp+StringUuid], r14
0x18004af52  mov     rsi, r8
0x18004af55  mov     [rbp+var_28], r14
0x18004af59  mov     rbx, rcx
0x18004af5c  mov     edi, r14d
0x18004af5f  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18004af63  test    rcx, rcx
0x18004af66  jnz     short loc_18004AF9F
0x18004af68  lea     r8, aPcszinput; "pcszInput"
0x18004af6f  mov     ebx, 80070057h
0x18004af74  lea     rdx, aDirectoryserve_5; "DirectoryServerUtil::GetGuidStringFromO"...
0x18004af7b  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18004af82  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004af87  lea     rdx, aPcszinput; "pcszInput"
0x18004af8e  lea     rcx, aDirectoryserve_5; "DirectoryServerUtil::GetGuidStringFromO"...
0x18004af95  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18004af9a  jmp     loc_18004B08A
0x18004af9f  test    rsi, rsi
0x18004afa2  jnz     short loc_18004AFCC
0x18004afa4  lea     r8, aPpszguidstring; "ppszGuidString"
0x18004afab  mov     ebx, 80070057h
0x18004afb0  lea     rdx, aDirectoryserve_5; "DirectoryServerUtil::GetGuidStringFromO"...
0x18004afb7  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18004afbe  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004afc3  lea     rdx, aPpszguidstring; "ppszGuidString"
0x18004afca  jmp     short loc_18004AF8E
0x18004afcc  mov     [r8], r14
0x18004afcf  test    edx, edx
0x18004afd1  jz      short loc_18004AFE7
0x18004afd3  cmp     edx, 10h
0x18004afd6  ja      short loc_18004B011
0x18004afd8  mov     r8d, edx; Size
0x18004afdb  lea     rcx, [rbp+Uuid]; void *
0x18004afdf  mov     rdx, rbx; Src
0x18004afe2  call    memcpy_0
0x18004afe7  lea     rdx, [rbp+StringUuid]; StringUuid
0x18004afeb  lea     rcx, [rbp+Uuid]; Uuid
0x18004afef  call    cs:__imp_UuidToStringW
0x18004aff5  test    eax, eax
0x18004aff7  jz      short loc_18004B03F
0x18004aff9  mov     r8d, eax
0x18004affc  lea     rdx, aDirectoryserve_5; "DirectoryServerUtil::GetGuidStringFromO"...
0x18004b003  lea     rcx, aSUuidtostringw_0; "%s: UuidToStringW failed with error cod"...
0x18004b00a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004b00f  jmp     short loc_18004B038
0x18004b011  call    cs:__imp__o__errno
0x18004b017  mov     dword ptr [rax], 22h ; '"'
0x18004b01d  call    _invalid_parameter_noinfo
0x18004b022  mov     r8, rbx
0x18004b025  lea     rdx, aDirectoryserve_5; "DirectoryServerUtil::GetGuidStringFromO"...
0x18004b02c  lea     rcx, aSUnableToConve; "%s: Unable to convert the input \"%hs\""...
0x18004b033  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004b038  mov     ebx, 80070057h
0x18004b03d  jmp     short loc_18004B08A
0x18004b03f  mov     rcx, [rbp+StringUuid]; Source
0x18004b043  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004b047  inc     rdx; unsigned __int64
0x18004b04a  cmp     [rcx+rdx*2], r14w
0x18004b04f  jnz     short loc_18004B047
0x18004b051  lea     r8, [rbp+var_28]; unsigned __int16 **
0x18004b055  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x18004b05a  mov     ebx, eax
0x18004b05c  test    eax, eax
0x18004b05e  jns     short loc_18004B083
0x18004b060  mov     r9d, eax
0x18004b063  lea     r8, aCopystringw; "CopyStringW"
0x18004b06a  lea     rdx, aDirectoryserve_5; "DirectoryServerUtil::GetGuidStringFromO"...
0x18004b071  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18004b078  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004b07d  mov     rdi, [rbp+var_28]
0x18004b081  jmp     short loc_18004B08A
0x18004b083  mov     rax, [rbp+var_28]
0x18004b087  mov     [rsi], rax
0x18004b08a  cmp     [rbp+StringUuid], r14
0x18004b08e  jz      short loc_18004B09A
0x18004b090  lea     rcx, [rbp+StringUuid]; String
0x18004b094  call    cs:__imp_RpcStringFreeW
0x18004b09a  test    rdi, rdi
0x18004b09d  jz      short loc_18004B0A7
0x18004b09f  mov     rcx, rdi; Block
0x18004b0a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b0a7  mov     eax, ebx
0x18004b0a9  mov     rcx, [rbp+var_10]
0x18004b0ad  xor     rcx, rsp; StackCookie
0x18004b0b0  call    __security_check_cookie
0x18004b0b5  add     rsp, 50h
0x18004b0b9  pop     r14
0x18004b0bb  pop     rdi
0x18004b0bc  pop     rsi
0x18004b0bd  pop     rbx
0x18004b0be  pop     rbp
0x18004b0bf  retn
```
