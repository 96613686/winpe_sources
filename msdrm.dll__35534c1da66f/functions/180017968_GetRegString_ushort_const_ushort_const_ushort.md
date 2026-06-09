# GetRegString(ushort const *,ushort const *,ushort * *)

- ea: `0x180017968`
- end: `0x180017ac3`
- name: `?GetRegString@@YAHPEBG0PEAPEAG@Z`
- size: `347`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180017cf4`

## callees

- `0x180001290`
- `0x180004654`
- `0x180017968`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017a95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017a95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800179fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800179fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017a2f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017a2f`

## pseudocode

```c
__int64 __fastcall GetRegString(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned __int16 **a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rax
  unsigned int v8; // edi
  unsigned __int16 *v9; // rax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 Data[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  Type = 0;
  memset_0(Data, 0, 0x208u);
  cbData = 520;
  v6 = 0;
  if ( lpSubKey && lpValueName && a3 )
  {
    if ( !RegOpenKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 0x20019u, &hKey)
      && !RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)Data, &cbData)
      && Type == 1 )
    {
      v7 = -1;
      do
        ++v7;
      while ( Data[v7] );
      v8 = v7 + 1;
      v9 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)(v7 + 1), 2u));
      *a3 = v9;
      if ( v9 )
      {
        if ( (int)StringCchCopyW(v9, v8, Data) >= 0 )
          v6 = 1;
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v6;
}

```

## disassembly

```asm
0x180017968  mov     [rsp-8+arg_18], rbx
0x18001796d  push    rbp
0x18001796e  push    rsi
0x18001796f  push    rdi
0x180017970  push    r14
0x180017972  push    r15
0x180017974  lea     rbp, [rsp-160h]
0x18001797c  sub     rsp, 260h
0x180017983  mov     rax, cs:__security_cookie
0x18001798a  xor     rax, rsp
0x18001798d  mov     [rbp+180h+var_30], rax
0x180017994  mov     r14, r8
0x180017997  mov     rdi, rdx
0x18001799a  mov     rsi, rcx
0x18001799d  xor     r15d, r15d
0x1800179a0  mov     ebx, 208h
0x1800179a5  mov     [rsp+280h+hKey], r15
0x1800179aa  mov     r8d, ebx; Size
0x1800179ad  mov     [rsp+280h+Type], r15d
0x1800179b2  xor     edx, edx; Val
0x1800179b4  lea     rcx, [rsp+280h+Data]; void *
0x1800179b9  call    memset_0
0x1800179be  mov     [rsp+280h+cbData], ebx
0x1800179c2  mov     ebx, r15d
0x1800179c5  test    rsi, rsi
0x1800179c8  jz      loc_180017A9B
0x1800179ce  test    rdi, rdi
0x1800179d1  jz      loc_180017A9B
0x1800179d7  test    r14, r14
0x1800179da  jz      loc_180017A9B
0x1800179e0  lea     rax, [rsp+280h+hKey]
0x1800179e5  mov     r9d, 20019h; samDesired
0x1800179eb  xor     r8d, r8d; ulOptions
0x1800179ee  mov     [rsp+280h+phkResult], rax; phkResult
0x1800179f3  mov     rdx, rsi; lpSubKey
0x1800179f6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800179fd  call    cs:__imp_RegOpenKeyExW
0x180017a03  test    eax, eax
0x180017a05  jnz     loc_180017A8B
0x180017a0b  mov     rcx, [rsp+280h+hKey]; hKey
0x180017a10  lea     rax, [rsp+280h+cbData]
0x180017a15  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180017a1a  lea     r9, [rsp+280h+Type]; lpType
0x180017a1f  lea     rax, [rsp+280h+Data]
0x180017a24  xor     r8d, r8d; lpReserved
0x180017a27  mov     rdx, rdi; lpValueName
0x180017a2a  mov     [rsp+280h+phkResult], rax; lpData
0x180017a2f  call    cs:__imp_RegQueryValueExW
0x180017a35  test    eax, eax
0x180017a37  jnz     short loc_180017A8B
0x180017a39  lea     esi, [rax+1]
0x180017a3c  cmp     [rsp+280h+Type], esi
0x180017a40  jnz     short loc_180017A8B
0x180017a42  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180017a46  lea     rdx, [rsp+280h+Data]
0x180017a4b  mov     rax, rcx
0x180017a4e  inc     rax
0x180017a51  cmp     [rdx+rax*2], r15w
0x180017a56  jnz     short loc_180017A4E
0x180017a58  lea     edi, [rax+1]
0x180017a5b  mov     eax, 2
0x180017a60  mul     rdi
0x180017a63  cmovb   rax, rcx
0x180017a67  mov     rcx, rax; unsigned __int64
0x180017a6a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180017a6f  mov     [r14], rax
0x180017a72  test    rax, rax
0x180017a75  jz      short loc_180017A8B
0x180017a77  lea     r8, [rsp+280h+Data]; unsigned __int16 *
0x180017a7c  mov     edx, edi; unsigned __int64
0x180017a7e  mov     rcx, rax; unsigned __int16 *
0x180017a81  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017a86  test    eax, eax
0x180017a88  cmovns  ebx, esi
0x180017a8b  mov     rcx, [rsp+280h+hKey]; hKey
0x180017a90  test    rcx, rcx
0x180017a93  jz      short loc_180017A9B
0x180017a95  call    cs:__imp_RegCloseKey
0x180017a9b  mov     eax, ebx
0x180017a9d  mov     rcx, [rbp+180h+var_30]
0x180017aa4  xor     rcx, rsp; StackCookie
0x180017aa7  call    __security_check_cookie
0x180017aac  mov     rbx, [rsp+280h+arg_18]
0x180017ab4  add     rsp, 260h
0x180017abb  pop     r15
0x180017abd  pop     r14
0x180017abf  pop     rdi
0x180017ac0  pop     rsi
0x180017ac1  pop     rbp
0x180017ac2  retn
```
