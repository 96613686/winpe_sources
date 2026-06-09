# GetRegistryString

- ea: `0x18000faac`
- end: `0x18000fc05`
- name: `GetRegistryString`
- size: `345`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180006300`
- `0x180009584`

## callees

- `0x180001f90`
- `0x180002160`
- `0x18000faac`
- `0x180012a00`
- `0x180012b80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fb2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fb82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fb2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fb82`

## pseudocode

```c
__int64 __fastcall GetRegistryString(HKEY hKey, __int64 a2, LPBYTE *a3, DWORD *a4)
{
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 v9; // r8
  LPBYTE v10; // rsi
  unsigned int v11; // eax
  __int64 v12; // rcx
  DWORD cbData; // [rsp+68h] [rbp+10h] BYREF
  int v15; // [rsp+6Ch] [rbp+14h]
  DWORD Type; // [rsp+70h] [rbp+18h] BYREF
  LPBYTE lpData; // [rsp+78h] [rbp+20h] BYREF

  v15 = HIDWORD(a2);
  Type = 0;
  cbData = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_(1028, 10, WPP_94d5010c5674399d06148e3a91870046_Traceguids);
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v8 = RegQueryValueExW(hKey, L"DhcpOptionLocationList", 0, &Type, 0, &cbData);
  if ( !v8 && cbData )
  {
    lpData = (LPBYTE)DhcpAlloc(cbData + 2LL, v7, v9);
    v10 = lpData;
    if ( lpData )
    {
      v11 = RegQueryValueExW(hKey, L"DhcpOptionLocationList", 0, &Type, lpData, &cbData);
      v8 = v11;
      if ( v11 )
      {
        if ( (xmmword_18001E1E0 & 2) != 0 )
          WPP_SF_d(1025, 11, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v11);
        DhcpFree(&lpData);
      }
      else
      {
        v12 = cbData & 0xFFFFFFFE;
        *a3 = v10;
        *(_WORD *)&v10[v12] = 0;
        if ( a4 )
          *a4 = cbData;
      }
    }
    else
    {
      v8 = 8;
    }
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 12, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18000faac  mov     qword ptr [rsp+cbData], rdx
0x18000fab1  push    rbx
0x18000fab2  push    rbp
0x18000fab3  push    rsi
0x18000fab4  push    rdi
0x18000fab5  push    r14
0x18000fab7  sub     rsp, 30h
0x18000fabb  mov     rdi, r9
0x18000fabe  mov     [rsp+58h+Type], 0
0x18000fac6  mov     r14, r8
0x18000fac9  mov     [rsp+58h+cbData], 0
0x18000fad1  mov     rbp, rcx
0x18000fad4  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000fadb  jz      short loc_18000FAF3
0x18000fadd  mov     edx, 0Ah
0x18000fae2  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000fae9  mov     ecx, 404h
0x18000faee  call    WPP_SF_
0x18000faf3  mov     qword ptr [r14], 0
0x18000fafa  test    rdi, rdi
0x18000fafd  jz      short loc_18000FB05
0x18000faff  mov     dword ptr [rdi], 0
0x18000fb05  lea     rax, [rsp+58h+cbData]
0x18000fb0a  xor     r8d, r8d; lpReserved
0x18000fb0d  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000fb12  lea     r9, [rsp+58h+Type]; lpType
0x18000fb17  lea     rdx, aDhcpoptionloca; "DhcpOptionLocationList"
0x18000fb1e  mov     [rsp+58h+lpData], 0; lpData
0x18000fb27  mov     rcx, rbp; hKey
0x18000fb2a  call    cs:__imp_RegQueryValueExW
0x18000fb30  mov     ebx, eax
0x18000fb32  test    eax, eax
0x18000fb34  jnz     loc_18000FBD6
0x18000fb3a  mov     eax, [rsp+58h+cbData]
0x18000fb3e  test    eax, eax
0x18000fb40  jz      loc_18000FBD6
0x18000fb46  lea     rcx, [rax+2]
0x18000fb4a  call    DhcpAlloc
0x18000fb4f  mov     [rsp+58h+arg_18], rax
0x18000fb54  mov     rsi, rax
0x18000fb57  test    rax, rax
0x18000fb5a  jnz     short loc_18000FB61
0x18000fb5c  lea     ebx, [rax+8]
0x18000fb5f  jmp     short loc_18000FBD6
0x18000fb61  lea     rax, [rsp+58h+cbData]
0x18000fb66  xor     r8d, r8d; lpReserved
0x18000fb69  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000fb6e  lea     r9, [rsp+58h+Type]; lpType
0x18000fb73  lea     rdx, aDhcpoptionloca; "DhcpOptionLocationList"
0x18000fb7a  mov     [rsp+58h+lpData], rsi; lpData
0x18000fb7f  mov     rcx, rbp; hKey
0x18000fb82  call    cs:__imp_RegQueryValueExW
0x18000fb88  mov     ebx, eax
0x18000fb8a  test    eax, eax
0x18000fb8c  jnz     short loc_18000FBAA
0x18000fb8e  mov     ecx, [rsp+58h+cbData]
0x18000fb92  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000fb96  mov     [r14], rsi
0x18000fb99  mov     [rcx+rsi], ax
0x18000fb9d  test    rdi, rdi
0x18000fba0  jz      short loc_18000FBD6
0x18000fba2  mov     eax, [rsp+58h+cbData]
0x18000fba6  mov     [rdi], eax
0x18000fba8  jmp     short loc_18000FBD6
0x18000fbaa  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000fbb1  jz      short loc_18000FBCC
0x18000fbb3  mov     edx, 0Bh
0x18000fbb8  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000fbbf  mov     ecx, 401h
0x18000fbc4  mov     r9d, eax
0x18000fbc7  call    WPP_SF_d
0x18000fbcc  lea     rcx, [rsp+58h+arg_18]
0x18000fbd1  call    DhcpFree
0x18000fbd6  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000fbdd  jz      short loc_18000FBF8
0x18000fbdf  mov     edx, 0Ch
0x18000fbe4  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000fbeb  mov     ecx, 404h
0x18000fbf0  mov     r9d, ebx
0x18000fbf3  call    WPP_SF_d
0x18000fbf8  mov     eax, ebx
0x18000fbfa  add     rsp, 30h
0x18000fbfe  pop     r14
0x18000fc00  pop     rdi
0x18000fc01  pop     rsi
0x18000fc02  pop     rbp
0x18000fc03  pop     rbx
0x18000fc04  retn
```
