# fsCryptCreateHash(unsigned __int64,uint,unsigned __int64,ulong,unsigned __int64 *)

- ea: `0x180030e4c`
- end: `0x180030ed9`
- name: `?fsCryptCreateHash@@YAH_KI0KPEA_K@Z`
- size: `141`
- prototype: `__int64 __fastcall(HCRYPTPROV, ALG_ID, __int64, __int64, HCRYPTHASH *phHash)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180030888`
- `0x180030a5c`

## callees

- `0x180030e4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030ec1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030ec1`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180030e7e`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180030e7e`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180030e9b`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180030ea8`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180030eb5`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180030e9b`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180030ea8`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180030eb5`
- `CRYPTSP!CryptCreateHash` at `0x180030e6d`
- `CRYPTSP!CryptCreateHash` at `0x180030e6d`

## pseudocode

```c
__int64 __fastcall fsCryptCreateHash(HCRYPTPROV a1, ALG_ID a2, __int64 a3, __int64 a4, HCRYPTHASH *phHash)
{
  unsigned int Hash; // edi
  DWORD LastError; // ebx

  Hash = CryptCreateHash(a1, a2, 0, 0, phHash);
  if ( Hash )
  {
    if ( !DbgIsSSActive(0x404u) )
      return Hash;
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  CSPrintErrorLineFile(0x2FF0C22u, LastError);
  CSPrintErrorLineFile(0x3000C22u, a2);
  CSPrintErrorLineFile(0x3010C22u, 0);
  if ( LastError )
    SetLastError(LastError);
  return Hash;
}

```

## disassembly

```asm
0x180030e4c  mov     [rsp+arg_0], rbx
0x180030e51  mov     [rsp+arg_8], rsi
0x180030e56  push    rdi
0x180030e57  sub     rsp, 30h
0x180030e5b  mov     rax, [rsp+38h+arg_20]
0x180030e60  xor     r9d, r9d; dwFlags
0x180030e63  xor     r8d, r8d; hKey
0x180030e66  mov     [rsp+38h+phHash], rax; phHash
0x180030e6b  mov     esi, edx
0x180030e6d  call    cs:__imp_CryptCreateHash
0x180030e73  mov     edi, eax
0x180030e75  test    eax, eax
0x180030e77  jz      short loc_180030E8C
0x180030e79  mov     ecx, 404h
0x180030e7e  call    cs:__imp_?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x180030e84  test    eax, eax
0x180030e86  jz      short loc_180030EC7
0x180030e88  xor     ebx, ebx
0x180030e8a  jmp     short loc_180030E94
0x180030e8c  call    cs:__imp_GetLastError
0x180030e92  mov     ebx, eax
0x180030e94  mov     edx, ebx
0x180030e96  mov     ecx, 2FF0C22h
0x180030e9b  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180030ea1  mov     edx, esi
0x180030ea3  mov     ecx, 3000C22h
0x180030ea8  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180030eae  xor     edx, edx
0x180030eb0  mov     ecx, 3010C22h
0x180030eb5  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180030ebb  test    ebx, ebx
0x180030ebd  jz      short loc_180030EC7
0x180030ebf  mov     ecx, ebx; dwErrCode
0x180030ec1  call    cs:__imp_SetLastError
0x180030ec7  mov     rbx, [rsp+38h+arg_0]
0x180030ecc  mov     eax, edi
0x180030ece  mov     rsi, [rsp+38h+arg_8]
0x180030ed3  add     rsp, 30h
0x180030ed7  pop     rdi
0x180030ed8  retn
```
