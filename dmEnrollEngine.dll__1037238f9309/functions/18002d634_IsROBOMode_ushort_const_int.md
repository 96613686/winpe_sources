# IsROBOMode(ushort const *,int *)

- ea: `0x18002d634`
- end: `0x18002d71b`
- name: `?IsROBOMode@@YAJPEBGPEAH@Z`
- size: `231`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180050558`

## callees

- `0x18002d634`
- `0x18002d998`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d680`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d680`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d6ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d702`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d6ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d702`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18002d6c9`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18002d6c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsROBOMode(const unsigned __int16 *a1, int *a2)
{
  const WCHAR *v4; // rax
  LSTATUS v5; // eax
  signed int v6; // ebx
  HKEY v7; // rcx
  signed int DWORD; // eax
  int v9; // eax
  HKEY v10; // rcx
  int v12; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v12 = 0;
  hKey = 0;
  v4 = (const WCHAR *)DMGetKnownRegPath(1);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, &hKey);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
    DWORD = OmaDmRegistryGetDWORD(hKey, a1, L"RenewROBOSupport", (unsigned int *)&v12);
    v6 = DWORD;
    if ( DWORD == -2147024894 || DWORD == -2147023267 )
    {
      v9 = 0;
      v12 = 0;
      v6 = 0;
    }
    else
    {
      v9 = v12;
    }
    *a2 = v9;
    v10 = hKey;
    hKey = 0;
    if ( v10 )
      RegCloseKey(v10);
  }
  else
  {
    v7 = hKey;
    hKey = 0;
    if ( v7 )
      RegCloseKey(v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002d634  mov     rax, rsp
0x18002d637  mov     [rax+8], rbx
0x18002d63b  mov     [rax+10h], rsi
0x18002d63f  push    rdi
0x18002d640  sub     rsp, 30h
0x18002d644  mov     rdi, rdx
0x18002d647  mov     rsi, rcx
0x18002d64a  mov     dword ptr [rax+18h], 0
0x18002d651  mov     qword ptr [rax+20h], 0
0x18002d659  mov     ecx, 1
0x18002d65e  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18002d663  lea     rcx, [rsp+38h+hKey]
0x18002d668  mov     [rsp+38h+phkResult], rcx; phkResult
0x18002d66d  mov     r9d, 20019h; samDesired
0x18002d673  xor     r8d, r8d; ulOptions
0x18002d676  mov     rdx, rax; lpSubKey
0x18002d679  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d680  call    cs:__imp_RegOpenKeyExW
0x18002d686  mov     ebx, eax
0x18002d688  test    eax, eax
0x18002d68a  jle     short loc_18002D695
0x18002d68c  movzx   ebx, ax
0x18002d68f  or      ebx, 80070000h
0x18002d695  test    ebx, ebx
0x18002d697  jns     short loc_18002D6B5
0x18002d699  mov     rcx, [rsp+38h+hKey]; hKey
0x18002d69e  mov     [rsp+38h+hKey], 0
0x18002d6a7  test    rcx, rcx
0x18002d6aa  jz      short loc_18002D6B3
0x18002d6ac  call    cs:__imp_RegCloseKey
0x18002d6b2  nop
0x18002d6b3  jmp     short loc_18002D709
0x18002d6b5  lea     r9, [rsp+38h+arg_10]
0x18002d6ba  lea     r8, aRenewrobosuppo; "RenewROBOSupport"
0x18002d6c1  mov     rdx, rsi
0x18002d6c4  mov     rcx, [rsp+38h+hKey]
0x18002d6c9  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002d6cf  mov     ebx, eax
0x18002d6d1  cmp     eax, 80070002h
0x18002d6d6  jz      short loc_18002D6E5
0x18002d6d8  cmp     eax, 8007065Dh
0x18002d6dd  jz      short loc_18002D6E5
0x18002d6df  mov     eax, [rsp+38h+arg_10]
0x18002d6e3  jmp     short loc_18002D6ED
0x18002d6e5  xor     eax, eax
0x18002d6e7  mov     [rsp+38h+arg_10], eax
0x18002d6eb  xor     ebx, ebx
0x18002d6ed  mov     [rdi], eax
0x18002d6ef  mov     rcx, [rsp+38h+hKey]; hKey
0x18002d6f4  mov     [rsp+38h+hKey], 0
0x18002d6fd  test    rcx, rcx
0x18002d700  jz      short loc_18002D709
0x18002d702  call    cs:__imp_RegCloseKey
0x18002d708  nop
0x18002d709  mov     eax, ebx
0x18002d70b  mov     rbx, [rsp+38h+arg_0]
0x18002d710  mov     rsi, [rsp+38h+arg_8]
0x18002d715  add     rsp, 30h
0x18002d719  pop     rdi
0x18002d71a  retn
```
