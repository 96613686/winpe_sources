# SetUserInfoHelper

- ea: `0x180012e04`
- end: `0x180012ee8`
- name: `SetUserInfoHelper`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001b750`

## callees

- `0x18000c814`
- `0x18000db90`
- `0x18000f47c`
- `0x180012e04`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012eb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012eb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012ec9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012ec9`
- `DMCmnUtils!CopyString` at `0x180012e47`
- `DMCmnUtils!CopyString` at `0x180012e47`

## pseudocode

```c
__int64 __fastcall SetUserInfoHelper(__int16 *a1, int a2, __int64 a3, const WCHAR *a4, _DWORD *a5)
{
  int AccountIDFromLookupID; // ebx
  HKEY v8; // rcx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp+8h] BYREF

  hKey = 0;
  hMem = 0;
  if ( !a1 )
    goto LABEL_2;
  if ( !a2 )
  {
    AccountIDFromLookupID = OmaDmGetAccountIDFromLookupID(a1, 0, (unsigned __int16 **)&hMem);
LABEL_8:
    if ( AccountIDFromLookupID < 0 )
      goto LABEL_11;
    goto LABEL_9;
  }
  if ( a2 != 1 )
  {
LABEL_2:
    AccountIDFromLookupID = -2147024809;
    goto LABEL_11;
  }
  AccountIDFromLookupID = CopyString((const unsigned __int16 *)a1, 0xFFFFFFFF, (unsigned __int16 **)&hMem);
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_8;
LABEL_9:
  AccountIDFromLookupID = GetAccountKey((const unsigned __int16 *)hMem, 1, 0x20106u, &hKey, 0);
  if ( AccountIDFromLookupID >= 0 )
  {
    v8 = hKey;
    *a5 = 1;
    AccountIDFromLookupID = InternalSaveUserInfoToKey(v8, a3, a4);
  }
LABEL_11:
  LocalFree(hMem);
  RegCloseKey(hKey);
  return (unsigned int)AccountIDFromLookupID;
}

```

## disassembly

```asm
0x180012e04  mov     rax, rsp
0x180012e07  mov     [rax+10h], rbx
0x180012e0b  mov     [rax+18h], rsi
0x180012e0f  push    rdi
0x180012e10  sub     rsp, 40h
0x180012e14  mov     qword ptr [rax-18h], 0
0x180012e1c  mov     rdi, r9
0x180012e1f  mov     qword ptr [rax+8], 0
0x180012e27  mov     rsi, r8
0x180012e2a  test    rcx, rcx
0x180012e2d  jnz     short loc_180012E36
0x180012e2f  mov     ebx, 80070057h
0x180012e34  jmp     short loc_180012EB3
0x180012e36  test    edx, edx
0x180012e38  jz      short loc_180012E5B
0x180012e3a  cmp     edx, 1
0x180012e3d  jnz     short loc_180012E2F
0x180012e3f  lea     r8, [rsp+48h+hMem]
0x180012e44  or      edx, 0FFFFFFFFh
0x180012e47  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180012e4e  nop     dword ptr [rax+rax+00h]
0x180012e53  mov     ebx, eax
0x180012e55  test    eax, eax
0x180012e57  js      short loc_180012E69
0x180012e59  jmp     short loc_180012E6D
0x180012e5b  lea     r8, [rsp+48h+hMem]
0x180012e60  xor     edx, edx
0x180012e62  call    ?OmaDmGetAccountIDFromLookupID@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAPEAG@Z; OmaDmGetAccountIDFromLookupID(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort * *)
0x180012e67  mov     ebx, eax
0x180012e69  test    ebx, ebx
0x180012e6b  js      short loc_180012EB3
0x180012e6d  mov     rcx, [rsp+48h+hMem]
0x180012e72  lea     r9, [rsp+48h+hKey]
0x180012e77  mov     edx, 1
0x180012e7c  mov     [rsp+48h+var_28], 0
0x180012e85  mov     r8d, 20106h
0x180012e8b  call    GetAccountKey
0x180012e90  mov     ebx, eax
0x180012e92  test    eax, eax
0x180012e94  js      short loc_180012EB3
0x180012e96  mov     rax, [rsp+48h+arg_20]
0x180012e9b  mov     r8, rdi; lpData
0x180012e9e  mov     rcx, [rsp+48h+hKey]; hKey
0x180012ea3  mov     rdx, rsi; __int64
0x180012ea6  mov     dword ptr [rax], 1
0x180012eac  call    InternalSaveUserInfoToKey
0x180012eb1  mov     ebx, eax
0x180012eb3  mov     rcx, [rsp+48h+hMem]; hMem
0x180012eb8  call    cs:__imp_LocalFree
0x180012ebf  nop     dword ptr [rax+rax+00h]
0x180012ec4  mov     rcx, [rsp+48h+hKey]; hKey
0x180012ec9  call    cs:__imp_RegCloseKey
0x180012ed0  nop     dword ptr [rax+rax+00h]
0x180012ed5  mov     rsi, [rsp+48h+arg_10]
0x180012eda  mov     eax, ebx
0x180012edc  mov     rbx, [rsp+48h+arg_8]
0x180012ee1  add     rsp, 40h
0x180012ee5  pop     rdi
0x180012ee6  retn
```
