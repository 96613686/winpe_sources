# RegistryConfig::GetStringValue(HKEY__ *,ushort const *)

- ea: `0x18000b6f8`
- end: `0x18000b814`
- name: `?GetStringValue@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18000ba60`

## callees

- `0x180007fac`
- `0x18000b6f8`
- `0x18000c12c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b7f4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b7f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b766`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b7d0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b766`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b7d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall RegistryConfig::GetStringValue(__int64 a1, _QWORD *a2, HKEY a3, const WCHAR *a4)
{
  __int64 v7; // r8
  __int64 v8; // r9
  PVOID v9; // rbx
  PVOID Src[2]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v12; // [rsp+58h] [rbp-20h]
  DWORD pcbData; // [rsp+80h] [rbp+8h] BYREF
  int v14; // [rsp+84h] [rbp+Ch]
  _QWORD *v15; // [rsp+88h] [rbp+10h]

  v15 = a2;
  v14 = HIDWORD(a1);
  a2[3] = 7;
  a2[2] = 0;
  *(_WORD *)a2 = 0;
  pcbData = 0;
  if ( !RegGetValueW(a3, 0, a4, 6u, 0, 0, &pcbData) )
  {
    *(_OWORD *)Src = 0;
    v12 = 0;
    if ( pcbData )
      std::vector<unsigned short>::_Reallocate(Src, pcbData, v7, v8);
    v9 = Src[0];
    if ( !RegGetValueW(a3, 0, a4, 6u, 0, Src[0], &pcbData) )
      std::wstring::assign(a2, v9);
    if ( v9 )
      operator delete(v9);
  }
  return a2;
}

```

## disassembly

```asm
0x18000b6f8  mov     r11, rsp
0x18000b6fb  mov     [r11+18h], rbx
0x18000b6ff  mov     [r11+10h], rdx
0x18000b703  mov     [r11+8], rcx
0x18000b707  push    rbp
0x18000b708  push    rsi
0x18000b709  push    rdi
0x18000b70a  sub     rsp, 60h
0x18000b70e  mov     rsi, r9
0x18000b711  mov     rbp, r8
0x18000b714  mov     rdi, rdx
0x18000b717  mov     [rsp+78h+var_38], 0
0x18000b71f  mov     qword ptr [rdx+18h], 7
0x18000b727  mov     qword ptr [rdx+10h], 0
0x18000b72f  xor     eax, eax
0x18000b731  mov     [rdx], ax
0x18000b734  mov     [rsp+78h+var_38], 1
0x18000b73c  mov     [r11+8], eax
0x18000b740  lea     rax, [r11+8]
0x18000b744  mov     [r11-48h], rax
0x18000b748  mov     qword ptr [r11-50h], 0
0x18000b750  mov     qword ptr [r11-58h], 0
0x18000b758  mov     r9d, 6; dwFlags
0x18000b75e  mov     r8, rsi; lpValue
0x18000b761  xor     edx, edx; lpSubKey
0x18000b763  mov     rcx, rbp; hkey
0x18000b766  call    cs:__imp_RegGetValueW
0x18000b76d  nop     dword ptr [rax+rax+00h]
0x18000b772  test    eax, eax
0x18000b774  jnz     loc_18000B800
0x18000b77a  xorps   xmm0, xmm0
0x18000b77d  movdqu  xmmword ptr [rsp+78h+Src], xmm0
0x18000b783  mov     [rsp+78h+var_20], 0
0x18000b78c  mov     edx, [rsp+78h+arg_0]
0x18000b793  test    rdx, rdx
0x18000b796  jz      short loc_18000B7A2
0x18000b798  lea     rcx, [rsp+78h+Src]
0x18000b79d  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18000b7a2  lea     rax, [rsp+78h+arg_0]
0x18000b7aa  mov     [rsp+78h+pcbData], rax; pcbData
0x18000b7af  mov     rbx, [rsp+78h+Src]
0x18000b7b4  mov     [rsp+78h+pvData], rbx; pvData
0x18000b7b9  mov     [rsp+78h+pdwType], 0; pdwType
0x18000b7c2  mov     r9d, 6; dwFlags
0x18000b7c8  mov     r8, rsi; lpValue
0x18000b7cb  xor     edx, edx; lpSubKey
0x18000b7cd  mov     rcx, rbp; hkey
0x18000b7d0  call    cs:__imp_RegGetValueW
0x18000b7d7  nop     dword ptr [rax+rax+00h]
0x18000b7dc  test    eax, eax
0x18000b7de  jnz     short loc_18000B7EC
0x18000b7e0  mov     rdx, rbx; Src
0x18000b7e3  mov     rcx, rdi; void *
0x18000b7e6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000b7eb  nop
0x18000b7ec  test    rbx, rbx
0x18000b7ef  jz      short loc_18000B800
0x18000b7f1  mov     rcx, rbx
0x18000b7f4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b7fb  nop     dword ptr [rax+rax+00h]
0x18000b800  mov     rax, rdi
0x18000b803  mov     rbx, [rsp+78h+arg_10]
0x18000b80b  add     rsp, 60h
0x18000b80f  pop     rdi
0x18000b810  pop     rsi
0x18000b811  pop     rbp
0x18000b812  retn
```
