# CryCreateHash(unsigned __int64,uint)

- ea: `0x18001e8f0`
- end: `0x18001e981`
- name: `?CryCreateHash@@YA_K_KI@Z`
- size: `145`
- prototype: `unsigned __int64 __fastcall(unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180019de4`

## callees

- `0x1800022d6`
- `0x1800087f8`
- `0x18001e8c8`
- `0x18001e8f0`

## import_xrefs

- `ADVAPI32!CryptCreateHash` at `0x18001e90f`
- `ADVAPI32!CryptCreateHash` at `0x18001e90f`
- `KERNEL32!GetLastError` at `0x18001e924`
- `KERNEL32!GetLastError` at `0x18001e924`

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
0x18001e8f0  push    rbx
0x18001e8f2  sub     rsp, 50h
0x18001e8f6  lea     rax, [rsp+58h+arg_10]
0x18001e8fb  mov     [rsp+58h+arg_10], 0
0x18001e904  xor     r9d, r9d; dwFlags
0x18001e907  mov     [rsp+58h+phHash], rax; phHash
0x18001e90c  xor     r8d, r8d; hKey
0x18001e90f  call    cs:__imp_CryptCreateHash
0x18001e915  test    eax, eax
0x18001e917  jz      short loc_18001E924
0x18001e919  mov     rax, [rsp+58h+arg_10]
0x18001e91e  add     rsp, 50h
0x18001e922  pop     rbx
0x18001e923  retn
0x18001e924  call    cs:__imp_GetLastError
0x18001e92a  mov     ebx, eax
0x18001e92c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e933  lea     rax, WPP_GLOBAL_Control
0x18001e93a  cmp     rcx, rax
0x18001e93d  jz      short loc_18001E963
0x18001e93f  test    byte ptr [rcx+10Ch], 1
0x18001e946  jz      short loc_18001E963
0x18001e948  mov     rcx, [rcx+100h]
0x18001e94f  lea     r8, WPP_5ab7ea082e1234d389e989818fe95e01_Traceguids
0x18001e956  mov     edx, 0Ah
0x18001e95b  mov     r9d, ebx
0x18001e95e  call    WPP_SF_d
0x18001e963  mov     edx, ebx; unsigned int
0x18001e965  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001e96a  call    ??0bad_CryptoApi@@QEAA@K@Z; bad_CryptoApi::bad_CryptoApi(ulong)
0x18001e96f  lea     rdx, _TI4?AVbad_CryptoApi@@; pThrowInfo
0x18001e976  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001e97b  call    _CxxThrowException_0
```
