# RegistryConfig::GetStringValue(HKEY__ *,ushort const *)

- ea: `0x18000b0bc`
- end: `0x18000b1c2`
- name: `?GetStringValue@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG@Z`
- size: `262`
- prototype: `__int64 __fastcall(__int64, __int64, HKEY, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18000b3f0`

## callees

- `0x180007c18`
- `0x18000b0bc`
- `0x18000ba6c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b1a8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b1a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b12a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b18a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b12a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b18a`

## pseudocode

```c
__int64 __fastcall RegistryConfig::GetStringValue(__int64 a1, __int64 a2, HKEY a3, const WCHAR *a4)
{
  char *v7; // rbx
  PVOID Src[2]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v10; // [rsp+58h] [rbp-20h]
  DWORD pcbData; // [rsp+80h] [rbp+8h] BYREF
  int v12; // [rsp+84h] [rbp+Ch]
  __int64 v13; // [rsp+88h] [rbp+10h]

  v13 = a2;
  v12 = HIDWORD(a1);
  *(_QWORD *)(a2 + 24) = 7;
  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)a2 = 0;
  pcbData = 0;
  if ( !RegGetValueW(a3, 0, a4, 6u, 0, 0, &pcbData) )
  {
    *(_OWORD *)Src = 0;
    v10 = 0;
    if ( pcbData )
      std::vector<unsigned short>::_Reallocate((__int64)Src, pcbData);
    v7 = (char *)Src[0];
    if ( !RegGetValueW(a3, 0, a4, 6u, 0, Src[0], &pcbData) )
      std::wstring::assign((void **)a2, v7);
    if ( v7 )
      operator delete(v7);
  }
  return a2;
}

```

## disassembly

```asm
0x18000b0bc  mov     r11, rsp
0x18000b0bf  mov     [r11+18h], rbx
0x18000b0c3  mov     [r11+10h], rdx
0x18000b0c7  mov     [r11+8], rcx
0x18000b0cb  push    rbp
0x18000b0cc  push    rsi
0x18000b0cd  push    rdi
0x18000b0ce  sub     rsp, 60h
0x18000b0d2  mov     rsi, r9
0x18000b0d5  mov     rbp, r8
0x18000b0d8  mov     rdi, rdx
0x18000b0db  mov     [rsp+78h+var_38], 0
0x18000b0e3  mov     qword ptr [rdx+18h], 7
0x18000b0eb  mov     qword ptr [rdx+10h], 0
0x18000b0f3  xor     eax, eax
0x18000b0f5  mov     [rdx], ax
0x18000b0f8  mov     [rsp+78h+var_38], 1
0x18000b100  mov     [r11+8], eax
0x18000b104  lea     rax, [r11+8]
0x18000b108  mov     [r11-48h], rax
0x18000b10c  mov     qword ptr [r11-50h], 0
0x18000b114  mov     qword ptr [r11-58h], 0
0x18000b11c  mov     r9d, 6; dwFlags
0x18000b122  mov     r8, rsi; lpValue
0x18000b125  xor     edx, edx; lpSubKey
0x18000b127  mov     rcx, rbp; hkey
0x18000b12a  call    cs:__imp_RegGetValueW
0x18000b130  test    eax, eax
0x18000b132  jnz     short loc_18000B1AE
0x18000b134  xorps   xmm0, xmm0
0x18000b137  movdqu  xmmword ptr [rsp+78h+Src], xmm0
0x18000b13d  mov     [rsp+78h+var_20], 0
0x18000b146  mov     edx, [rsp+78h+arg_0]
0x18000b14d  test    rdx, rdx
0x18000b150  jz      short loc_18000B15C
0x18000b152  lea     rcx, [rsp+78h+Src]
0x18000b157  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18000b15c  lea     rax, [rsp+78h+arg_0]
0x18000b164  mov     [rsp+78h+pcbData], rax; pcbData
0x18000b169  mov     rbx, [rsp+78h+Src]
0x18000b16e  mov     [rsp+78h+pvData], rbx; pvData
0x18000b173  mov     [rsp+78h+pdwType], 0; pdwType
0x18000b17c  mov     r9d, 6; dwFlags
0x18000b182  mov     r8, rsi; lpValue
0x18000b185  xor     edx, edx; lpSubKey
0x18000b187  mov     rcx, rbp; hkey
0x18000b18a  call    cs:__imp_RegGetValueW
0x18000b190  test    eax, eax
0x18000b192  jnz     short loc_18000B1A0
0x18000b194  mov     rdx, rbx; Src
0x18000b197  mov     rcx, rdi; void *
0x18000b19a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000b19f  nop
0x18000b1a0  test    rbx, rbx
0x18000b1a3  jz      short loc_18000B1AE
0x18000b1a5  mov     rcx, rbx
0x18000b1a8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b1ae  mov     rax, rdi
0x18000b1b1  mov     rbx, [rsp+78h+arg_10]
0x18000b1b9  add     rsp, 60h
0x18000b1bd  pop     rdi
0x18000b1be  pop     rsi
0x18000b1bf  pop     rbp
0x18000b1c0  retn
```
