# GetStringFromManifest(ushort const *,ushort *,ulong,ushort const *)

- ea: `0x180032210`
- end: `0x180032260`
- name: `?GetStringFromManifest@@YAJPEBGPEAGK0@Z`
- size: `80`
- prototype: `__int64 __fastcall(LPCWSTR lpKeyName, LPWSTR lpReturnedString, DWORD nSize, LPCWSTR lpFileName)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180031a74`
- `0x180031e68`
- `0x180032a34`
- `0x180032ea4`
- `0x180033398`

## callees

- `0x18000b200`
- `0x180032210`

## import_xrefs

- `KERNEL32!GetPrivateProfileStringW` at `0x180032232`
- `KERNEL32!GetPrivateProfileStringW` at `0x180032232`

## string_xrefs

- `0x18003222b`: `DriverConfig`

## pseudocode

```c
__int64 __fastcall GetStringFromManifest(LPCWSTR lpKeyName, LPWSTR lpReturnedString, DWORD nSize, LPCWSTR lpFileName)
{
  DWORD PrivateProfileStringW; // edx
  NCoreLibrary *v6; // rcx
  unsigned int v7; // ecx

  PrivateProfileStringW = GetPrivateProfileStringW(L"DriverConfig", lpKeyName, 0, lpReturnedString, nSize, lpFileName);
  if ( PrivateProfileStringW )
  {
    v7 = 0;
    if ( PrivateProfileStringW == nSize - 1 )
      return (unsigned int)-2147021875;
  }
  else
  {
    return (unsigned int)NCoreLibrary::GetLastErrorAsFailHR(v6);
  }
  return v7;
}

```

## disassembly

```asm
0x180032210  push    rbx
0x180032212  sub     rsp, 30h
0x180032216  mov     [rsp+38h+lpFileName], r9; lpFileName
0x18003221b  mov     ebx, r8d
0x18003221e  mov     r9, rdx; lpReturnedString
0x180032221  mov     [rsp+38h+nSize], ebx; nSize
0x180032225  mov     rdx, rcx; lpKeyName
0x180032228  xor     r8d, r8d; lpDefault
0x18003222b  lea     rcx, AppName; "DriverConfig"
0x180032232  call    cs:__imp_GetPrivateProfileStringW
0x180032238  mov     edx, eax
0x18003223a  test    eax, eax
0x18003223c  jnz     short loc_180032247
0x18003223e  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180032243  mov     ecx, eax
0x180032245  jmp     short loc_180032258
0x180032247  xor     ecx, ecx
0x180032249  lea     eax, [rbx-1]
0x18003224c  cmp     edx, eax
0x18003224e  mov     r8d, 80070BCDh
0x180032254  cmovz   ecx, r8d
0x180032258  mov     eax, ecx
0x18003225a  add     rsp, 30h
0x18003225e  pop     rbx
0x18003225f  retn
```
