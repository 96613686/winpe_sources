# Dhcpv6RegSaveOptions

- ea: `0x180007cc8`
- end: `0x180007ef6`
- name: `Dhcpv6RegSaveOptions`
- size: `558`
- prototype: `LSTATUS __fastcall(_QWORD **, __int64, HKEY, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180008a70`
- `0x180011400`

## callees

- `0x180007564`
- `0x180007cc8`
- `0x18000803c`
- `0x1800082c0`
- `0x18003098c`
- `0x1800340b4`
- `0x180034948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ddf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ddf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007dbf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007dbf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180007d58`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180007d58`

## pseudocode

```c
LSTATUS __fastcall Dhcpv6RegSaveOptions(_QWORD **a1, __int64 a2, HKEY a3, __int64 a4, unsigned int a5)
{
  _QWORD *v7; // r14
  int v8; // edi
  DWORD cbData; // r15d
  unsigned int v10; // ebp
  _QWORD *v11; // rbx
  __int64 v13; // rax
  _DWORD *v14; // rcx
  _QWORD *v15; // r14
  BYTE *lpData; // r12
  LSTATUS v17; // ebx
  int v18; // r8d
  const char *v19; // rcx
  _QWORD *v20; // rdi
  _DWORD *v21; // rbp
  char *v22; // rbx

  Dhcpv6RegClearOptDefsEx(a1, a4, a5, a2);
  v7 = *a1;
  v8 = 0;
  cbData = 0;
  v10 = 0;
  if ( *a1 == a1 )
    return RegDeleteValueW(a3, L"Dhcpv6InterfaceOptions");
  do
  {
    v11 = v7;
    ++v10;
    v7 = (_QWORD *)*v7;
    if ( *((_DWORD *)v11 + 8) == a5 && v11[3] == a4 )
    {
      v8 = Dhcpv6RegSaveOption(v11, a2);
      if ( v8 )
      {
        if ( (xmmword_1800423E0 & 2) != 0 )
        {
          v19 = "Vendor";
          if ( !*((_DWORD *)v11 + 5) )
            v19 = "NotVendor";
          WPP_SF_lsD((_DWORD)v19, 29, v18, *((unsigned __int16 *)v11 + 8), (__int64)v19, v8);
        }
      }
    }
    cbData += (*((_DWORD *)v11 + 14) + *((_DWORD *)v11 + 8) + 23) & 0xFFFFFFFC;
  }
  while ( v7 != a1 );
  if ( v8 && (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_dd(1025, 30, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids, v10, v8);
  if ( !v10 )
    return RegDeleteValueW(a3, L"Dhcpv6InterfaceOptions");
  v13 = DhcpAlloc(cbData);
  v14 = (_DWORD *)v13;
  if ( !v13 )
    return 8;
  v15 = *a1;
  lpData = (BYTE *)v13;
  while ( v15 != a1 )
  {
    v20 = v15;
    v15 = (_QWORD *)*v15;
    v21 = v14 + 5;
    *v14 = *((unsigned __int16 *)v20 + 8);
    v14[1] = *((_DWORD *)v20 + 8);
    v14[2] = *((_DWORD *)v20 + 14);
    v14[3] = *((_DWORD *)v20 + 5);
    v14[4] = *((_DWORD *)v20 + 10);
    if ( *((_DWORD *)v20 + 8) )
    {
      memcpy_0(v14 + 5, (const void *)v20[3], *((unsigned int *)v20 + 8));
      v22 = (char *)v21 + *((unsigned int *)v20 + 8);
    }
    else
    {
      v22 = (char *)(v14 + 5);
    }
    if ( *((_DWORD *)v20 + 14) )
    {
      memcpy_0(v22, (const void *)v20[6], *((unsigned int *)v20 + 14));
      v22 += *((unsigned int *)v20 + 14);
    }
    v14 = (_DWORD *)((unsigned __int64)(v22 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
  }
  v17 = RegSetValueExW(a3, L"Dhcpv6InterfaceOptions", 0, 3u, lpData, cbData);
  HeapFree(NtCurrentPeb()->ProcessHeap, 0, lpData);
  return v17;
}

```

## disassembly

```asm
0x180007cc8  mov     [rsp+arg_0], rbx
0x180007ccd  mov     [rsp+hKey], r8
0x180007cd2  mov     [rsp+arg_8], rdx
0x180007cd7  push    rbp
0x180007cd8  push    rsi
0x180007cd9  push    rdi
0x180007cda  push    r12
0x180007cdc  push    r13
0x180007cde  push    r14
0x180007ce0  push    r15
0x180007ce2  sub     rsp, 30h
0x180007ce6  mov     r13d, [rsp+68h+arg_20]
0x180007cee  mov     r12, r9
0x180007cf1  mov     r9, rdx
0x180007cf4  mov     r8d, r13d
0x180007cf7  mov     rdx, r12
0x180007cfa  mov     rsi, rcx
0x180007cfd  call    Dhcpv6RegClearOptDefsEx
0x180007d02  mov     r14, [rsi]
0x180007d05  xor     edi, edi
0x180007d07  xor     r15d, r15d
0x180007d0a  xor     ebp, ebp
0x180007d0c  cmp     r14, rsi
0x180007d0f  jz      short loc_180007D49
0x180007d11  mov     rbx, r14
0x180007d14  inc     ebp
0x180007d16  mov     r14, [r14]
0x180007d19  cmp     [rbx+20h], r13d
0x180007d1d  jnz     short loc_180007D29
0x180007d1f  cmp     [rbx+18h], r12
0x180007d23  jz      loc_180007DF2
0x180007d29  mov     edx, [rbx+20h]
0x180007d2c  add     edx, 17h
0x180007d2f  add     edx, [rbx+38h]
0x180007d32  and     edx, 0FFFFFFFCh
0x180007d35  add     r15d, edx
0x180007d38  cmp     r14, rsi
0x180007d3b  jnz     short loc_180007D11
0x180007d3d  test    edi, edi
0x180007d3f  jnz     loc_180007E8D
0x180007d45  test    ebp, ebp
0x180007d47  jnz     short loc_180007D7A
0x180007d49  mov     rcx, [rsp+68h+hKey]; hKey
0x180007d51  lea     rdx, aDhcpv6interfac; "Dhcpv6InterfaceOptions"
0x180007d58  call    cs:__imp_RegDeleteValueW
0x180007d5f  nop     dword ptr [rax+rax+00h]
0x180007d64  mov     rbx, [rsp+68h+arg_0]
0x180007d69  add     rsp, 30h
0x180007d6d  pop     r15
0x180007d6f  pop     r14
0x180007d71  pop     r13
0x180007d73  pop     r12
0x180007d75  pop     rdi
0x180007d76  pop     rsi
0x180007d77  pop     rbp
0x180007d78  retn
0x180007d7a  mov     ecx, r15d
0x180007d7d  call    DhcpAlloc
0x180007d82  mov     rcx, rax
0x180007d85  test    rax, rax
0x180007d88  jz      loc_180007EBC
0x180007d8e  mov     r14, [rsi]
0x180007d91  mov     r12, rax
0x180007d94  cmp     r14, rsi
0x180007d97  jnz     loc_180007E49
0x180007d9d  mov     rcx, [rsp+68h+hKey]; hKey
0x180007da5  lea     rdx, aDhcpv6interfac; "Dhcpv6InterfaceOptions"
0x180007dac  mov     [rsp+68h+cbData], r15d; cbData
0x180007db1  mov     r9d, 3; dwType
0x180007db7  xor     r8d, r8d; Reserved
0x180007dba  mov     [rsp+68h+lpData], r12; lpData
0x180007dbf  call    cs:__imp_RegSetValueExW
0x180007dc6  nop     dword ptr [rax+rax+00h]
0x180007dcb  mov     rcx, gs:60h
0x180007dd4  mov     r8, r12; lpMem
0x180007dd7  xor     edx, edx; dwFlags
0x180007dd9  mov     ebx, eax
0x180007ddb  mov     rcx, [rcx+30h]; hHeap
0x180007ddf  call    cs:__imp_HeapFree
0x180007de6  nop     dword ptr [rax+rax+00h]
0x180007deb  mov     eax, ebx
0x180007ded  jmp     loc_180007D64
0x180007df2  mov     rdx, [rsp+68h+arg_8]
0x180007df7  mov     rcx, rbx
0x180007dfa  call    Dhcpv6RegSaveOption
0x180007dff  mov     edi, eax
0x180007e01  test    eax, eax
0x180007e03  jz      loc_180007D29
0x180007e09  test    byte ptr cs:xmmword_1800423E0, 2
0x180007e10  jz      loc_180007D29
0x180007e16  cmp     dword ptr [rbx+14h], 0
0x180007e1a  lea     rax, aNotvendor; "NotVendor"
0x180007e21  movzx   r9d, word ptr [rbx+10h]
0x180007e26  lea     rcx, aVendor_1; "Vendor"
0x180007e2d  cmovz   rcx, rax
0x180007e31  mov     [rsp+68h+cbData], edi
0x180007e35  mov     edx, 1Dh
0x180007e3a  mov     [rsp+68h+lpData], rcx
0x180007e3f  call    WPP_SF_lsD
0x180007e44  jmp     loc_180007D29
0x180007e49  lea     rdi, [r14]
0x180007e4c  mov     r14, [r14]
0x180007e4f  movzx   eax, word ptr [rdi+10h]
0x180007e53  lea     rbp, [rcx+14h]
0x180007e57  mov     [rcx], eax
0x180007e59  mov     eax, [rdi+20h]
0x180007e5c  mov     [rcx+4], eax
0x180007e5f  mov     eax, [rdi+38h]
0x180007e62  mov     [rcx+8], eax
0x180007e65  mov     eax, [rdi+14h]
0x180007e68  mov     [rcx+0Ch], eax
0x180007e6b  mov     eax, [rdi+28h]
0x180007e6e  mov     [rcx+10h], eax
0x180007e71  cmp     dword ptr [rdi+20h], 0
0x180007e75  jnz     short loc_180007EC6
0x180007e77  mov     rbx, rbp
0x180007e7a  cmp     dword ptr [rdi+38h], 0
0x180007e7e  jnz     short loc_180007EDE
0x180007e80  lea     rcx, [rbx+3]
0x180007e84  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180007e88  jmp     loc_180007D94
0x180007e8d  test    byte ptr cs:xmmword_1800423E0, 2
0x180007e94  jz      loc_180007D45
0x180007e9a  mov     edx, 1Eh
0x180007e9f  mov     dword ptr [rsp+68h+lpData], edi
0x180007ea3  mov     ecx, 401h
0x180007ea8  lea     r8, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids
0x180007eaf  mov     r9d, ebp
0x180007eb2  call    WPP_SF_dd
0x180007eb7  jmp     loc_180007D45
0x180007ebc  mov     eax, 8
0x180007ec1  jmp     loc_180007D64
0x180007ec6  mov     r8d, [rdi+20h]; Size
0x180007eca  mov     rcx, rbp; void *
0x180007ecd  mov     rdx, [rdi+18h]; Src
0x180007ed1  call    memcpy_0
0x180007ed6  mov     ebx, [rdi+20h]
0x180007ed9  add     rbx, rbp
0x180007edc  jmp     short loc_180007E7A
0x180007ede  mov     r8d, [rdi+38h]; Size
0x180007ee2  mov     rcx, rbx; void *
0x180007ee5  mov     rdx, [rdi+30h]; Src
0x180007ee9  call    memcpy_0
0x180007eee  mov     eax, [rdi+38h]
0x180007ef1  add     rbx, rax
0x180007ef4  jmp     short loc_180007E80
```
