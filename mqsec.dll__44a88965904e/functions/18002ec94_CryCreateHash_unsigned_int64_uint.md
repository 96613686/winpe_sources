# CryCreateHash(unsigned __int64,uint)

- ea: `0x18002ec94`
- end: `0x18002ed25`
- name: `?CryCreateHash@@YA_K_KI@Z`
- size: `145`
- prototype: `unsigned __int64 __fastcall(unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18002e9ec`
- `0x18002ec24`

## callees

- `0x180003426`
- `0x1800049ac`
- `0x18002ebfc`
- `0x18002ec94`

## import_xrefs

- `ADVAPI32!CryptCreateHash` at `0x18002ecb3`
- `ADVAPI32!CryptCreateHash` at `0x18002ecb3`
- `KERNEL32!GetLastError` at `0x18002ecc8`
- `KERNEL32!GetLastError` at `0x18002ecc8`

## pseudocode

```c
HCRYPTHASH __fastcall CryCreateHash(HCRYPTPROV a1, ALG_ID a2)
{
  DWORD LastError; // ebx
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-28h] BYREF
  HCRYPTHASH phHash; // [rsp+70h] [rbp+18h] BYREF

  phHash = 0;
  if ( !CryptCreateHash(a1, a2, 0, 0, &phHash) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 10, WPP_5ab7ea082e1234d389e989818fe95e01_Traceguids, LastError);
    bad_CryptoApi::bad_CryptoApi((bad_CryptoApi *)pExceptionObject, LastError);
    throw (bad_CryptoApi *)pExceptionObject;
  }
  return phHash;
}

```

## disassembly

```asm
0x18002ec94  push    rbx
0x18002ec96  sub     rsp, 50h
0x18002ec9a  lea     rax, [rsp+58h+arg_10]
0x18002ec9f  mov     [rsp+58h+arg_10], 0
0x18002eca8  xor     r9d, r9d; dwFlags
0x18002ecab  mov     [rsp+58h+phHash], rax; phHash
0x18002ecb0  xor     r8d, r8d; hKey
0x18002ecb3  call    cs:__imp_CryptCreateHash
0x18002ecb9  test    eax, eax
0x18002ecbb  jz      short loc_18002ECC8
0x18002ecbd  mov     rax, [rsp+58h+arg_10]
0x18002ecc2  add     rsp, 50h
0x18002ecc6  pop     rbx
0x18002ecc7  retn
0x18002ecc8  call    cs:__imp_GetLastError
0x18002ecce  mov     ebx, eax
0x18002ecd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ecd7  lea     rax, WPP_GLOBAL_Control
0x18002ecde  cmp     rcx, rax
0x18002ece1  jz      short loc_18002ED07
0x18002ece3  test    byte ptr [rcx+10Ch], 1
0x18002ecea  jz      short loc_18002ED07
0x18002ecec  mov     rcx, [rcx+100h]
0x18002ecf3  lea     r8, WPP_5ab7ea082e1234d389e989818fe95e01_Traceguids
0x18002ecfa  mov     edx, 0Ah
0x18002ecff  mov     r9d, ebx
0x18002ed02  call    WPP_SF_d
0x18002ed07  mov     edx, ebx; unsigned int
0x18002ed09  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18002ed0e  call    ??0bad_CryptoApi@@QEAA@K@Z; bad_CryptoApi::bad_CryptoApi(ulong)
0x18002ed13  lea     rdx, _TI4?AVbad_CryptoApi@@; pThrowInfo
0x18002ed1a  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002ed1f  call    _CxxThrowException_0
```
