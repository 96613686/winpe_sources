# UtilRegGetQWORD(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64,bool *,bool)

- ea: `0x18003d448`
- end: `0x18003d522`
- name: `?UtilRegGetQWORD@@YA_KPEAUHKEY__@@PEB_W1_KPEA_N_N@Z`
- size: `218`
- prototype: `unsigned __int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, unsigned __int64@<r9>, bool *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18003c08c`

## callees

- `0x18000a004`
- `0x18003d448`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d50c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d50c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003d4e2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003d4e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d4a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d4a8`

## pseudocode

```c
__int64 __fastcall UtilRegGetQWORD(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValue, __int64 a4, bool *a5, DWORD pcbData)
{
  bool *v6; // rdi
  HKEY *phkResult; // rax
  __int64 v11; // rbx
  HKEY hkey; // [rsp+60h] [rbp+8h] BYREF
  __int64 pvData; // [rsp+78h] [rbp+20h] BYREF

  v6 = a5;
  pvData = 0;
  pcbData = 8;
  hkey = 0;
  if ( a5 )
    *a5 = 0;
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  if ( RegOpenKeyExW(hKey, lpSubKey, 0, 0x101u, phkResult)
    || RegGetValueW(hkey, 0, lpValue, 0x40u, 0, &pvData, &pcbData) )
  {
    v11 = 0;
    pvData = 0;
    if ( v6 )
      *v6 = 1;
  }
  else
  {
    v11 = pvData;
  }
  if ( hkey )
    RegCloseKey(hkey);
  return v11;
}

```

## disassembly

```asm
0x18003d448  mov     rax, rsp
0x18003d44b  mov     [rax+10h], rbx
0x18003d44f  mov     [rax+20h], r9
0x18003d453  push    rbp
0x18003d454  push    rsi
0x18003d455  push    rdi
0x18003d456  sub     rsp, 40h
0x18003d45a  mov     rdi, [rsp+58h+arg_20]
0x18003d462  mov     rbx, r8
0x18003d465  mov     qword ptr [rax+20h], 0
0x18003d46d  mov     rsi, rdx
0x18003d470  mov     dword ptr [rax+30h], 8
0x18003d477  mov     rbp, rcx
0x18003d47a  mov     qword ptr [rax+8], 0
0x18003d482  test    rdi, rdi
0x18003d485  jz      short loc_18003D48A
0x18003d487  mov     byte ptr [rdi], 0
0x18003d48a  lea     rcx, [rsp+58h+hkey]
0x18003d48f  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18003d494  mov     r9d, 101h; samDesired
0x18003d49a  mov     [rsp+58h+phkResult], rax; phkResult
0x18003d49f  xor     r8d, r8d; ulOptions
0x18003d4a2  mov     rdx, rsi; lpSubKey
0x18003d4a5  mov     rcx, rbp; hKey
0x18003d4a8  call    cs:__imp_RegOpenKeyExW
0x18003d4ae  test    eax, eax
0x18003d4b0  jnz     short loc_18003D4F3
0x18003d4b2  mov     rcx, [rsp+58h+hkey]; hkey
0x18003d4b7  lea     rax, [rsp+58h+arg_28]
0x18003d4bf  mov     [rsp+58h+pcbData], rax; pcbData
0x18003d4c4  mov     r9d, 40h ; '@'; dwFlags
0x18003d4ca  lea     rax, [rsp+58h+arg_18]
0x18003d4cf  mov     r8, rbx; lpValue
0x18003d4d2  mov     [rsp+58h+pvData], rax; pvData
0x18003d4d7  xor     edx, edx; lpSubKey
0x18003d4d9  mov     [rsp+58h+phkResult], 0; pdwType
0x18003d4e2  call    cs:__imp_RegGetValueW
0x18003d4e8  test    eax, eax
0x18003d4ea  jnz     short loc_18003D4F3
0x18003d4ec  mov     rbx, [rsp+58h+arg_18]
0x18003d4f1  jmp     short loc_18003D502
0x18003d4f3  xor     ebx, ebx
0x18003d4f5  mov     [rsp+58h+arg_18], rbx
0x18003d4fa  test    rdi, rdi
0x18003d4fd  jz      short loc_18003D502
0x18003d4ff  mov     byte ptr [rdi], 1
0x18003d502  mov     rcx, [rsp+58h+hkey]; hKey
0x18003d507  test    rcx, rcx
0x18003d50a  jz      short loc_18003D512
0x18003d50c  call    cs:__imp_RegCloseKey
0x18003d512  mov     rax, rbx
0x18003d515  mov     rbx, [rsp+58h+arg_8]
0x18003d51a  add     rsp, 40h
0x18003d51e  pop     rdi
0x18003d51f  pop     rsi
0x18003d520  pop     rbp
0x18003d521  retn
```
