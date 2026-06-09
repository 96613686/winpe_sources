# IsROBOMode(ushort const *,int *)

- ea: `0x1800ce5f8`
- end: `0x1800ce6f8`
- name: `?IsROBOMode@@YAJPEBGPEAH@Z`
- size: `256`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001b900`
- `0x1800223d0`

## callees

- `0x18002201c`
- `0x1800ce5f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ce676`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ce6d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ce676`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ce6d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ce644`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ce644`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800ce699`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800ce699`

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
0x1800ce5f8  mov     rax, rsp
0x1800ce5fb  mov     [rax+8], rbx
0x1800ce5ff  mov     [rax+10h], rsi
0x1800ce603  push    rdi
0x1800ce604  sub     rsp, 30h
0x1800ce608  mov     rdi, rdx
0x1800ce60b  mov     rsi, rcx
0x1800ce60e  mov     dword ptr [rax+18h], 0
0x1800ce615  mov     qword ptr [rax+20h], 0
0x1800ce61d  mov     ecx, 1
0x1800ce622  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800ce627  lea     rcx, [rsp+38h+hKey]
0x1800ce62c  mov     [rsp+38h+phkResult], rcx; phkResult
0x1800ce631  mov     r9d, 20019h; samDesired
0x1800ce637  xor     r8d, r8d; ulOptions
0x1800ce63a  mov     rdx, rax; lpSubKey
0x1800ce63d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ce644  call    cs:__imp_RegOpenKeyExW
0x1800ce64b  nop     dword ptr [rax+rax+00h]
0x1800ce650  mov     ebx, eax
0x1800ce652  test    eax, eax
0x1800ce654  jle     short loc_1800CE65F
0x1800ce656  movzx   ebx, ax
0x1800ce659  or      ebx, 80070000h
0x1800ce65f  test    ebx, ebx
0x1800ce661  jns     short loc_1800CE685
0x1800ce663  mov     rcx, [rsp+38h+hKey]; hKey
0x1800ce668  mov     [rsp+38h+hKey], 0
0x1800ce671  test    rcx, rcx
0x1800ce674  jz      short loc_1800CE683
0x1800ce676  call    cs:__imp_RegCloseKey
0x1800ce67d  nop     dword ptr [rax+rax+00h]
0x1800ce682  nop
0x1800ce683  jmp     short loc_1800CE6E5
0x1800ce685  lea     r9, [rsp+38h+arg_10]
0x1800ce68a  lea     r8, aRenewrobosuppo; "RenewROBOSupport"
0x1800ce691  mov     rdx, rsi
0x1800ce694  mov     rcx, [rsp+38h+hKey]
0x1800ce699  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800ce6a0  nop     dword ptr [rax+rax+00h]
0x1800ce6a5  mov     ebx, eax
0x1800ce6a7  cmp     eax, 80070002h
0x1800ce6ac  jz      short loc_1800CE6BB
0x1800ce6ae  cmp     eax, 8007065Dh
0x1800ce6b3  jz      short loc_1800CE6BB
0x1800ce6b5  mov     eax, [rsp+38h+arg_10]
0x1800ce6b9  jmp     short loc_1800CE6C3
0x1800ce6bb  xor     eax, eax
0x1800ce6bd  mov     [rsp+38h+arg_10], eax
0x1800ce6c1  xor     ebx, ebx
0x1800ce6c3  mov     [rdi], eax
0x1800ce6c5  mov     rcx, [rsp+38h+hKey]; hKey
0x1800ce6ca  mov     [rsp+38h+hKey], 0
0x1800ce6d3  test    rcx, rcx
0x1800ce6d6  jz      short loc_1800CE6E5
0x1800ce6d8  call    cs:__imp_RegCloseKey
0x1800ce6df  nop     dword ptr [rax+rax+00h]
0x1800ce6e4  nop
0x1800ce6e5  mov     eax, ebx
0x1800ce6e7  mov     rbx, [rsp+38h+arg_0]
0x1800ce6ec  mov     rsi, [rsp+38h+arg_8]
0x1800ce6f1  add     rsp, 30h
0x1800ce6f5  pop     rdi
0x1800ce6f6  retn
```
