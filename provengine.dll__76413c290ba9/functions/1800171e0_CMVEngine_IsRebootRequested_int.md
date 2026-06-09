# CMVEngine::IsRebootRequested(int *)

- ea: `0x1800171e0`
- end: `0x1800172e2`
- name: `?IsRebootRequested@CMVEngine@@UEAAJPEAH@Z`
- size: `258`
- prototype: `__int64 __fastcall(CMVEngine *__hidden this, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800098dc`
- `0x180009900`
- `0x1800171e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001724e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001724e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017281`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017281`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800172b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800172d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800172b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800172d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMVEngine::IsRebootRequested(CMVEngine *this, int *a2)
{
  unsigned int v3; // ebx
  unsigned int v5; // eax
  HKEY v6; // rcx
  int phkResult; // [rsp+20h] [rbp-18h]
  unsigned int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int Data; // [rsp+48h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  if ( !a2 )
  {
    v3 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCED,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)0x80004003LL,
      phkResult);
    return v3;
  }
  *a2 = 0;
  Data = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 1u, 0x20019u, &hKey) )
  {
    cbData = 4;
    v5 = RegQueryValueExW(hKey, 0, 0, 0, (LPBYTE)&Data, &cbData);
    if ( v5 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xCF7,
             (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
             (const char *)v5,
             phkResulta);
      if ( hKey )
        RegCloseKey(hKey);
      return v3;
    }
  }
  v6 = hKey;
  *a2 = Data != 0;
  if ( v6 )
    RegCloseKey(v6);
  return 0;
}

```

## disassembly

```asm
0x1800171e0  push    rbx
0x1800171e2  sub     rsp, 30h
0x1800171e6  mov     rbx, rdx
0x1800171e9  test    rdx, rdx
0x1800171ec  jnz     short loc_180017213
0x1800171ee  mov     rcx, [rsp+38h]; this
0x1800171f3  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800171fa  mov     ebx, 80004003h
0x1800171ff  mov     edx, 0CEDh; void *
0x180017204  mov     r9d, ebx; char *
0x180017207  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001720c  mov     eax, ebx
0x18001720e  jmp     loc_1800172DC
0x180017213  mov     dword ptr [rdx], 0
0x180017219  lea     rax, [rsp+38h+hKey]
0x18001721e  mov     rdx, cs:lpSubKey; lpSubKey
0x180017225  mov     r9d, 20019h; samDesired
0x18001722b  mov     r8d, 1; ulOptions
0x180017231  mov     [rsp+38h+phkResult], rax; phkResult
0x180017236  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001723d  mov     [rsp+38h+Data], 0
0x180017245  mov     [rsp+38h+hKey], 0
0x18001724e  call    cs:__imp_RegOpenKeyExW
0x180017254  test    eax, eax
0x180017256  jnz     short loc_1800172BF
0x180017258  mov     rcx, [rsp+38h+hKey]; hKey
0x18001725d  lea     rax, [rsp+38h+cbData]
0x180017262  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180017267  xor     r9d, r9d; lpType
0x18001726a  lea     rax, [rsp+38h+Data]
0x18001726f  mov     [rsp+38h+cbData], 4
0x180017277  xor     r8d, r8d; lpReserved
0x18001727a  mov     [rsp+38h+phkResult], rax; unsigned int
0x18001727f  xor     edx, edx; lpValueName
0x180017281  call    cs:__imp_RegQueryValueExW
0x180017287  test    eax, eax
0x180017289  jz      short loc_1800172BF
0x18001728b  mov     rcx, [rsp+38h]; this
0x180017290  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180017297  mov     r9d, eax; char *
0x18001729a  mov     edx, 0CF7h; void *
0x18001729f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800172a4  mov     rcx, [rsp+38h+hKey]; hKey
0x1800172a9  mov     ebx, eax
0x1800172ab  test    rcx, rcx
0x1800172ae  jz      loc_18001720C
0x1800172b4  call    cs:__imp_RegCloseKey
0x1800172ba  jmp     loc_18001720C
0x1800172bf  mov     rcx, [rsp+38h+hKey]; hKey
0x1800172c4  xor     eax, eax
0x1800172c6  cmp     [rsp+38h+Data], eax
0x1800172ca  setnbe  al
0x1800172cd  mov     [rbx], eax
0x1800172cf  test    rcx, rcx
0x1800172d2  jz      short loc_1800172DA
0x1800172d4  call    cs:__imp_RegCloseKey
0x1800172da  xor     eax, eax
0x1800172dc  add     rsp, 30h
0x1800172e0  pop     rbx
0x1800172e1  retn
```
