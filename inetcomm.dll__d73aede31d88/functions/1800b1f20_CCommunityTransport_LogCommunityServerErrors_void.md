# CCommunityTransport::_LogCommunityServerErrors(void)

- ea: `0x1800b1f20`
- end: `0x1800b2175`
- name: `?_LogCommunityServerErrors@CCommunityTransport@@AEAAXXZ`
- size: `597`
- prototype: `void __fastcall(CCommunityTransport *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ada04`

## callees

- `0x1800b1f20`

## import_xrefs

- `MSOERT2!__imp_HrRegGetDWORDW` at `0x1800b1f98`
- `MSOERT2!__imp_HrRegGetDWORDW` at `0x1800b1fb1`
- `MSOERT2!__imp_HrRegGetDWORDW` at `0x1800b2035`
- `MSOERT2!__imp_HrRegGetDWORDW` at `0x1800b2067`
- `MSOERT2!__imp_HrRegGetDWORDW` at `0x1800b1f98`
- `MSOERT2!__imp_HrRegGetDWORDW` at `0x1800b1fb1`
- `MSOERT2!__imp_HrRegGetDWORDW` at `0x1800b2035`
- `MSOERT2!__imp_HrRegGetDWORDW` at `0x1800b2067`
- `MSOERT2!__imp_HrRegSetDWORDW` at `0x1800b1ff3`
- `MSOERT2!__imp_HrRegSetDWORDW` at `0x1800b200a`
- `MSOERT2!__imp_HrRegSetDWORDW` at `0x1800b208b`
- `MSOERT2!__imp_HrRegSetDWORDW` at `0x1800b20ad`
- `MSOERT2!__imp_HrRegSetDWORDW` at `0x1800b1ff3`
- `MSOERT2!__imp_HrRegSetDWORDW` at `0x1800b200a`
- `MSOERT2!__imp_HrRegSetDWORDW` at `0x1800b208b`
- `MSOERT2!__imp_HrRegSetDWORDW` at `0x1800b20ad`
- `MSOERT2!__imp_SHRegSetPercentW` at `0x1800b20fe`
- `MSOERT2!__imp_SHRegSetPercentW` at `0x1800b214b`
- `MSOERT2!__imp_SHRegSetPercentW` at `0x1800b20fe`
- `MSOERT2!__imp_SHRegSetPercentW` at `0x1800b214b`
- `SHLWAPI!SHRegCloseUSKey` at `0x1800b1f6d`
- `SHLWAPI!SHRegCloseUSKey` at `0x1800b1f6d`
- `SHLWAPI!SHRegCreateUSKeyW` at `0x1800b1f5e`
- `SHLWAPI!SHRegCreateUSKeyW` at `0x1800b1f5e`

## string_xrefs

- `0x1800b1f4c`: `Software\Microsoft\Windows Mail\CommunityServer`

## pseudocode

```c
void __fastcall CCommunityTransport::_LogCommunityServerErrors(CCommunityTransport *this)
{
  __int64 i; // r14
  unsigned int DWORDW; // ebx
  unsigned int v4; // eax
  unsigned int v5; // ebp
  unsigned int v6; // esi
  BOOL v7; // ebx
  unsigned int v8; // edi
  BOOL v9; // ebx
  unsigned int v10; // ebx
  int v11; // [rsp+20h] [rbp-38h]
  int v12; // [rsp+20h] [rbp-38h]
  int v13; // [rsp+20h] [rbp-38h]
  int v14; // [rsp+20h] [rbp-38h]
  HUSKEY hUSKey; // [rsp+68h] [rbp+10h] BYREF

  hUSKey = 0;
  if ( !SHRegCreateUSKeyW(L"Software\\Microsoft\\Windows Mail\\CommunityServer", 4u, 0, &hUSKey, 2u) )
    SHRegCloseUSKey(hUSKey);
  for ( i = 1; i != 10; ++i )
  {
    DWORDW = HrRegGetDWORDW(
               -2147483647,
               L"Software\\Microsoft\\Windows Mail\\CommunityServer",
               qword_1800D3EB8[i],
               0,
               v11);
    v4 = HrRegGetDWORDW(-2147483647, L"Software\\Microsoft\\Windows Mail\\CommunityServer", qword_1800D3E68[i], 0, v12);
    v5 = -1;
    if ( DWORDW + *((_DWORD *)this + i + 3282) >= DWORDW )
      v5 = DWORDW + *((_DWORD *)this + i + 3282);
    v6 = -1;
    if ( v4 + *((_DWORD *)this + i + 3292) >= v4 )
      v6 = v4 + *((_DWORD *)this + i + 3292);
    HrRegSetDWORDW(-2147483647, L"Software\\Microsoft\\Windows Mail\\CommunityServer", qword_1800D3EB8[i], v5);
    HrRegSetDWORDW(-2147483647, L"Software\\Microsoft\\Windows Mail\\CommunityServer", qword_1800D3E68[i], v6);
    v7 = *((_DWORD *)this + i + 3282) != 0;
    v8 = HrRegGetDWORDW(-2147483647, L"Software\\Microsoft\\Windows Mail\\CommunityServer", qword_1800D3DC8[i], 0, v13)
       + v7;
    v9 = *((_DWORD *)this + i + 3292) != 0;
    v10 = HrRegGetDWORDW(-2147483647, L"Software\\Microsoft\\Windows Mail\\CommunityServer", qword_1800D3D78[i], 0, v14)
        + v9;
    HrRegSetDWORDW(-2147483647, L"Software\\Microsoft\\Windows Mail\\CommunityServer", qword_1800D3DC8[i], v8);
    HrRegSetDWORDW(-2147483647, L"Software\\Microsoft\\Windows Mail\\CommunityServer", qword_1800D3D78[i], v10);
    SHRegSetPercentW(-2147483647, L"Software\\Microsoft\\Windows Mail\\CommunityServer", qword_1800D3E18[i]);
    v11 = 3;
    SHRegSetPercentW(-2147483647, L"Software\\Microsoft\\Windows Mail\\CommunityServer", qword_1800D3D28[i]);
  }
}

```

## disassembly

```asm
0x1800b1f20  mov     rax, rsp
0x1800b1f23  mov     [rax+8], rbx
0x1800b1f27  mov     [rax+18h], rbp
0x1800b1f2b  push    rsi
0x1800b1f2c  push    rdi
0x1800b1f2d  push    r13
0x1800b1f2f  push    r14
0x1800b1f31  push    r15
0x1800b1f33  sub     rsp, 30h
0x1800b1f37  xor     r8d, r8d; hRelativeUSKey
0x1800b1f3a  mov     qword ptr [rax+10h], 0
0x1800b1f42  mov     r15, rcx
0x1800b1f45  mov     dword ptr [rax-38h], 2
0x1800b1f4c  lea     r13, pwzPath; "Software\\Microsoft\\Windows Mail\\Comm"...
0x1800b1f53  lea     r9, [rax+10h]; phNewUSKey
0x1800b1f57  mov     rcx, r13; pwzPath
0x1800b1f5a  lea     edx, [r8+4]; samDesired
0x1800b1f5e  call    cs:__imp_SHRegCreateUSKeyW
0x1800b1f64  test    eax, eax
0x1800b1f66  jnz     short loc_1800B1F73
0x1800b1f68  mov     rcx, [rsp+58h+hUSKey]; hUSKey
0x1800b1f6d  call    cs:__imp_SHRegCloseUSKey
0x1800b1f73  mov     r14d, 1
0x1800b1f79  lea     rbp, __ImageBase
0x1800b1f80  mov     rdi, 0FFFFFFFF80000001h
0x1800b1f87  mov     r8, ss:rva qword_1800D3EB8[rbp+r14*8]
0x1800b1f8f  xor     r9d, r9d
0x1800b1f92  mov     rdx, r13
0x1800b1f95  mov     rcx, rdi
0x1800b1f98  call    cs:__imp_HrRegGetDWORDW
0x1800b1f9e  mov     r8, ss:rva qword_1800D3E68[rbp+r14*8]
0x1800b1fa6  xor     r9d, r9d
0x1800b1fa9  mov     rdx, r13
0x1800b1fac  mov     rcx, rdi
0x1800b1faf  mov     ebx, eax
0x1800b1fb1  call    cs:__imp_HrRegGetDWORDW
0x1800b1fb7  mov     edx, [r15+r14*4+3348h]
0x1800b1fbf  or      ebp, 0FFFFFFFFh
0x1800b1fc2  add     edx, ebx
0x1800b1fc4  mov     rcx, rdi
0x1800b1fc7  cmp     edx, ebx
0x1800b1fc9  lea     rbx, __ImageBase
0x1800b1fd0  mov     r8, ds:rva qword_1800D3EB8[rbx+r14*8]
0x1800b1fd8  cmovnb  ebp, edx
0x1800b1fdb  mov     edx, [r15+r14*4+3370h]
0x1800b1fe3  add     edx, eax
0x1800b1fe5  or      esi, 0FFFFFFFFh
0x1800b1fe8  cmp     edx, eax
0x1800b1fea  mov     r9d, ebp
0x1800b1fed  cmovnb  esi, edx
0x1800b1ff0  mov     rdx, r13
0x1800b1ff3  call    cs:__imp_HrRegSetDWORDW
0x1800b1ff9  mov     r8, ds:rva qword_1800D3E68[rbx+r14*8]
0x1800b2001  mov     r9d, esi
0x1800b2004  mov     rdx, r13
0x1800b2007  mov     rcx, rdi
0x1800b200a  call    cs:__imp_HrRegSetDWORDW
0x1800b2010  xor     ebx, ebx
0x1800b2012  lea     r8, __ImageBase
0x1800b2019  cmp     [r15+r14*4+3348h], ebx
0x1800b2021  mov     rdx, r13
0x1800b2024  mov     r8, ds:rva qword_1800D3DC8[r8+r14*8]
0x1800b202c  mov     rcx, rdi
0x1800b202f  setnz   bl
0x1800b2032  xor     r9d, r9d
0x1800b2035  call    cs:__imp_HrRegGetDWORDW
0x1800b203b  mov     rdx, r13
0x1800b203e  mov     rcx, 0FFFFFFFF80000001h
0x1800b2045  lea     edi, [rax+rbx]
0x1800b2048  xor     ebx, ebx
0x1800b204a  cmp     [r15+r14*4+3370h], ebx
0x1800b2052  lea     rax, __ImageBase
0x1800b2059  mov     r8, ds:rva qword_1800D3D78[rax+r14*8]
0x1800b2061  setnz   bl
0x1800b2064  xor     r9d, r9d
0x1800b2067  call    cs:__imp_HrRegGetDWORDW
0x1800b206d  mov     r9d, edi
0x1800b2070  mov     rdx, r13
0x1800b2073  add     ebx, eax
0x1800b2075  mov     rcx, 0FFFFFFFF80000001h
0x1800b207c  lea     rax, __ImageBase
0x1800b2083  mov     r8, ds:rva qword_1800D3DC8[rax+r14*8]
0x1800b208b  call    cs:__imp_HrRegSetDWORDW
0x1800b2091  lea     rax, __ImageBase
0x1800b2098  mov     r9d, ebx
0x1800b209b  mov     r8, ds:rva qword_1800D3D78[rax+r14*8]
0x1800b20a3  mov     rdx, r13
0x1800b20a6  mov     rcx, 0FFFFFFFF80000001h
0x1800b20ad  call    cs:__imp_HrRegSetDWORDW
0x1800b20b3  xorps   xmm3, xmm3
0x1800b20b6  mov     [rsp+58h+var_38], 3
0x1800b20be  mov     eax, 1
0x1800b20c3  xorps   xmm0, xmm0
0x1800b20c6  cmp     esi, eax
0x1800b20c8  mov     rdx, r13
0x1800b20cb  cmovb   esi, eax
0x1800b20ce  mov     eax, ebp
0x1800b20d0  mov     ecx, esi
0x1800b20d2  lea     rbp, __ImageBase
0x1800b20d9  mov     r8, ss:rva qword_1800D3E18[rbp+r14*8]
0x1800b20e1  cvtsi2sd xmm3, rax
0x1800b20e6  cvtsi2sd xmm0, rcx
0x1800b20eb  mov     rcx, 0FFFFFFFF80000001h
0x1800b20f2  mulsd   xmm3, cs:__real@4059000000000000
0x1800b20fa  divsd   xmm3, xmm0
0x1800b20fe  call    cs:__imp_SHRegSetPercentW
0x1800b2104  mov     r8, ss:rva qword_1800D3D28[rbp+r14*8]
0x1800b210c  xorps   xmm3, xmm3
0x1800b210f  mov     eax, edi
0x1800b2111  mov     esi, 1
0x1800b2116  xorps   xmm0, xmm0
0x1800b2119  mov     [rsp+58h+var_38], 3
0x1800b2121  cmp     ebx, esi
0x1800b2123  mov     rdi, 0FFFFFFFF80000001h
0x1800b212a  mov     rdx, r13
0x1800b212d  cvtsi2sd xmm3, rax
0x1800b2132  cmovb   ebx, esi
0x1800b2135  mov     ecx, ebx
0x1800b2137  mulsd   xmm3, cs:__real@4059000000000000
0x1800b213f  cvtsi2sd xmm0, rcx
0x1800b2144  mov     rcx, rdi
0x1800b2147  divsd   xmm3, xmm0
0x1800b214b  call    cs:__imp_SHRegSetPercentW
0x1800b2151  add     r14, rsi
0x1800b2154  cmp     r14, 0Ah
0x1800b2158  jnz     loc_1800B1F87
0x1800b215e  mov     rbx, [rsp+58h+arg_0]
0x1800b2163  mov     rbp, [rsp+58h+arg_10]
0x1800b2168  add     rsp, 30h
0x1800b216c  pop     r15
0x1800b216e  pop     r14
0x1800b2170  pop     r13
0x1800b2172  pop     rdi
0x1800b2173  pop     rsi
0x1800b2174  retn
```
