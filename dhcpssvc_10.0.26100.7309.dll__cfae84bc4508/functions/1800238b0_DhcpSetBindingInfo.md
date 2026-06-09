# DhcpSetBindingInfo

- ea: `0x1800238b0`
- end: `0x180023a78`
- name: `DhcpSetBindingInfo`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004e3d0`

## callees

- `0x18000cc3c`
- `0x18001cfc8`
- `0x18001de8c`
- `0x18001ecb8`
- `0x1800238b0`
- `0x180024e28`
- `0x1800cc9e0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180023a0b`
- `ADVAPI32!RegCloseKey` at `0x180023a2d`
- `ADVAPI32!RegCloseKey` at `0x180023a0b`
- `ADVAPI32!RegCloseKey` at `0x180023a2d`
- `ADVAPI32!RegSetValueExW` at `0x1800239f9`
- `ADVAPI32!RegSetValueExW` at `0x1800239f9`
- `ADVAPI32!RegDeleteValueW` at `0x1800239b6`
- `ADVAPI32!RegDeleteValueW` at `0x1800239b6`

## pseudocode

```c
__int64 __fastcall DhcpSetBindingInfo(__int64 a1)
{
  unsigned int v2; // ebx
  unsigned int v3; // edx
  __int64 v4; // rcx
  unsigned int v5; // r14d
  __int64 v6; // rax
  unsigned int v7; // ebx
  __int128 v8; // xmm0
  int v9; // eax
  HKEY v10; // rcx
  HKEY hKey; // [rsp+38h] [rbp-69h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-61h] BYREF
  __int128 v14; // [rsp+48h] [rbp-59h] BYREF
  _WORD v15[64]; // [rsp+58h] [rbp-49h] BYREF

  v2 = 0;
  hKey = 0;
  v3 = 0;
  if ( !*(_DWORD *)a1 )
    goto LABEL_23;
  v4 = *(_QWORD *)(a1 + 8);
  do
  {
    if ( (*(_BYTE *)(v4 + 40LL * v3) & 1) != 0 && !*(_DWORD *)(v4 + 40LL * v3 + 4) )
      return 20051;
    ++v3;
  }
  while ( v3 < *(_DWORD *)a1 );
  v5 = 0;
  while ( 1 )
  {
    v14 = 0;
    v6 = *(_QWORD *)(a1 + 8);
    if ( (*(_BYTE *)(v6 + 40LL * v5) & 1) != 0 )
      goto LABEL_18;
    v7 = *(_DWORD *)(v6 + 40LL * v5 + 8);
    if ( *(_DWORD *)(v6 + 40LL * v5 + 24) != 16 )
      goto LABEL_22;
    v8 = *(_OWORD *)*(_QWORD *)(v6 + 40LL * v5 + 32);
    v15[0] = 0;
    v14 = v8;
    ConvertGuidToString(&v14, v15);
    v9 = DhcpOpenInterfaceByName(v15, &hKey);
    v10 = hKey;
    if ( v9 )
      goto LABEL_21;
    if ( !(unsigned int)IsAdapterStaticIP(hKey) || !(unsigned int)CheckKeyForBindability(hKey, v7) )
      break;
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 8) + 40LL * v5 + 4) == 1 )
    {
      v2 = RegDeleteValueW(hKey, L"BindToDHCPServer");
      if ( v2 - 2 <= 1 )
        v2 = 0;
    }
    else
    {
      *(_DWORD *)Data = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 40LL * v5 + 4);
      v2 = RegSetValueExW(hKey, L"BindToDHCPServer", 0, 4u, Data, 4u);
    }
    RegCloseKey(hKey);
    if ( v2 )
      goto LABEL_23;
LABEL_18:
    if ( ++v5 >= *(_DWORD *)a1 )
      goto LABEL_23;
  }
  v10 = hKey;
LABEL_21:
  RegCloseKey(v10);
LABEL_22:
  v2 = 20050;
LABEL_23:
  WalkthroughEndpoints(0, RefreshBinding);
  return v2;
}

```

## disassembly

```asm
0x1800238b0  mov     rax, rsp
0x1800238b3  mov     [rax+10h], rbx
0x1800238b7  mov     [rax+18h], rsi
0x1800238bb  mov     [rax+20h], rdi
0x1800238bf  push    rbp
0x1800238c0  push    r14
0x1800238c2  push    r15
0x1800238c4  lea     rbp, [rax-5Fh]
0x1800238c8  sub     rsp, 0E0h
0x1800238cf  mov     rax, cs:__security_cookie
0x1800238d6  xor     rax, rsp
0x1800238d9  mov     [rbp+57h+var_20], rax
0x1800238dd  xor     r15d, r15d
0x1800238e0  mov     rdi, rcx
0x1800238e3  mov     ebx, r15d
0x1800238e6  mov     [rbp+57h+hKey], r15
0x1800238ea  mov     edx, r15d
0x1800238ed  cmp     [rcx], r15d
0x1800238f0  jbe     loc_180023A3E
0x1800238f6  mov     rcx, [rcx+8]
0x1800238fa  mov     eax, edx
0x1800238fc  lea     r8, [rax+rax*4]
0x180023900  test    byte ptr [rcx+r8*8], 1
0x180023905  jz      short loc_180023912
0x180023907  cmp     [rcx+r8*8+4], r15d
0x18002390c  jz      loc_1800239D1
0x180023912  inc     edx
0x180023914  cmp     edx, [rdi]
0x180023916  jb      short loc_1800238FA
0x180023918  mov     r14d, r15d
0x18002391b  mov     eax, r14d
0x18002391e  xorps   xmm0, xmm0
0x180023921  movups  [rbp+57h+var_B0], xmm0
0x180023925  lea     rsi, [rax+rax*4]
0x180023929  mov     rax, [rdi+8]
0x18002392d  test    byte ptr [rax+rsi*8], 1
0x180023931  jnz     loc_180023A1B
0x180023937  cmp     dword ptr [rax+rsi*8+18h], 10h
0x18002393c  mov     ebx, [rax+rsi*8+8]
0x180023940  jnz     loc_180023A39
0x180023946  mov     rax, [rax+rsi*8+20h]
0x18002394b  lea     rdx, [rbp+57h+var_A0]
0x18002394f  lea     rcx, [rbp+57h+var_B0]
0x180023953  movups  xmm0, xmmword ptr [rax]
0x180023956  mov     [rbp+57h+var_A0], r15w
0x18002395b  movdqu  [rbp+57h+var_B0], xmm0
0x180023960  call    ConvertGuidToString
0x180023965  lea     rdx, [rbp+57h+hKey]
0x180023969  lea     rcx, [rbp+57h+var_A0]
0x18002396d  call    DhcpOpenInterfaceByName
0x180023972  mov     rcx, [rbp+57h+hKey]
0x180023976  test    eax, eax
0x180023978  jnz     loc_180023A2D
0x18002397e  call    IsAdapterStaticIP
0x180023983  test    eax, eax
0x180023985  jz      loc_180023A29
0x18002398b  mov     rcx, [rbp+57h+hKey]
0x18002398f  mov     edx, ebx
0x180023991  call    CheckKeyForBindability
0x180023996  test    eax, eax
0x180023998  jz      loc_180023A29
0x18002399e  mov     rax, [rdi+8]
0x1800239a2  lea     rdx, aBindtodhcpserv; "BindToDHCPServer"
0x1800239a9  mov     ecx, [rax+rsi*8+4]
0x1800239ad  cmp     ecx, 1
0x1800239b0  jnz     short loc_1800239D8
0x1800239b2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800239b6  call    cs:__imp_RegDeleteValueW
0x1800239bd  nop     dword ptr [rax+rax+00h]
0x1800239c2  mov     ebx, eax
0x1800239c4  add     eax, 0FFFFFFFEh
0x1800239c7  cmp     eax, 1
0x1800239ca  ja      short loc_180023A07
0x1800239cc  mov     ebx, r15d
0x1800239cf  jmp     short loc_180023A07
0x1800239d1  mov     eax, 4E53h
0x1800239d6  jmp     short loc_180023A4E
0x1800239d8  mov     dword ptr [rbp+57h+Data], ecx
0x1800239db  lea     rax, [rbp+57h+Data]
0x1800239df  mov     rcx, [rbp+57h+hKey]; hKey
0x1800239e3  mov     r9d, 4; dwType
0x1800239e9  mov     [rsp+0F0h+cbData], 4; cbData
0x1800239f1  xor     r8d, r8d; Reserved
0x1800239f4  mov     [rsp+0F0h+lpData], rax; lpData
0x1800239f9  call    cs:__imp_RegSetValueExW
0x180023a00  nop     dword ptr [rax+rax+00h]
0x180023a05  mov     ebx, eax
0x180023a07  mov     rcx, [rbp+57h+hKey]; hKey
0x180023a0b  call    cs:__imp_RegCloseKey
0x180023a12  nop     dword ptr [rax+rax+00h]
0x180023a17  test    ebx, ebx
0x180023a19  jnz     short loc_180023A3E
0x180023a1b  inc     r14d
0x180023a1e  cmp     r14d, [rdi]
0x180023a21  jb      loc_18002391B
0x180023a27  jmp     short loc_180023A3E
0x180023a29  mov     rcx, [rbp+57h+hKey]; hKey
0x180023a2d  call    cs:__imp_RegCloseKey
0x180023a34  nop     dword ptr [rax+rax+00h]
0x180023a39  mov     ebx, 4E52h
0x180023a3e  lea     rdx, RefreshBinding
0x180023a45  xor     ecx, ecx
0x180023a47  call    WalkthroughEndpoints
0x180023a4c  mov     eax, ebx
0x180023a4e  mov     rcx, [rbp+57h+var_20]
0x180023a52  xor     rcx, rsp; StackCookie
0x180023a55  call    __security_check_cookie
0x180023a5a  lea     r11, [rsp+0F0h+var_10]
0x180023a62  mov     rbx, [r11+28h]
0x180023a66  mov     rsi, [r11+30h]
0x180023a6a  mov     rdi, [r11+38h]
0x180023a6e  mov     rsp, r11
0x180023a71  pop     r15
0x180023a73  pop     r14
0x180023a75  pop     rbp
0x180023a76  retn
```
