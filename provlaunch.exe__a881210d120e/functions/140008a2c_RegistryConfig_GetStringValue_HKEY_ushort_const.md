# RegistryConfig::GetStringValue(HKEY__ *,ushort const *)

- ea: `0x140008a2c`
- end: `0x140008b32`
- name: `?GetStringValue@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG@Z`
- size: `262`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x140008ce4`

## callees

- `0x140007b38`
- `0x140008a2c`
- `0x14000972c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140008b18`
- `msvcrt!??3@YAXPEAX@Z` at `0x140008b18`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140008a9a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140008afa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140008a9a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140008afa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall RegistryConfig::GetStringValue(__int64 a1, _QWORD *a2, HKEY a3, const WCHAR *a4)
{
  PVOID v7; // rbx
  PVOID Src[2]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v10; // [rsp+58h] [rbp-20h]
  DWORD pcbData; // [rsp+80h] [rbp+8h] BYREF
  int v12; // [rsp+84h] [rbp+Ch]
  _QWORD *v13; // [rsp+88h] [rbp+10h]

  v13 = a2;
  v12 = HIDWORD(a1);
  a2[3] = 7;
  a2[2] = 0;
  *(_WORD *)a2 = 0;
  pcbData = 0;
  if ( !RegGetValueW(a3, 0, a4, 6u, 0, 0, &pcbData) )
  {
    *(_OWORD *)Src = 0;
    v10 = 0;
    if ( pcbData )
      std::vector<unsigned short>::_Reallocate(Src, pcbData);
    v7 = Src[0];
    if ( !RegGetValueW(a3, 0, a4, 6u, 0, Src[0], &pcbData) )
      std::wstring::assign(a2, v7);
    if ( v7 )
      operator delete(v7);
  }
  return a2;
}

```

## disassembly

```asm
0x140008a2c  mov     r11, rsp
0x140008a2f  mov     [r11+18h], rbx
0x140008a33  mov     [r11+10h], rdx
0x140008a37  mov     [r11+8], rcx
0x140008a3b  push    rbp
0x140008a3c  push    rsi
0x140008a3d  push    rdi
0x140008a3e  sub     rsp, 60h
0x140008a42  mov     rsi, r9
0x140008a45  mov     rbp, r8
0x140008a48  mov     rdi, rdx
0x140008a4b  mov     [rsp+78h+var_38], 0
0x140008a53  mov     qword ptr [rdx+18h], 7
0x140008a5b  mov     qword ptr [rdx+10h], 0
0x140008a63  xor     eax, eax
0x140008a65  mov     [rdx], ax
0x140008a68  mov     [rsp+78h+var_38], 1
0x140008a70  mov     [r11+8], eax
0x140008a74  lea     rax, [r11+8]
0x140008a78  mov     [r11-48h], rax
0x140008a7c  mov     qword ptr [r11-50h], 0
0x140008a84  mov     qword ptr [r11-58h], 0
0x140008a8c  mov     r9d, 6; dwFlags
0x140008a92  mov     r8, rsi; lpValue
0x140008a95  xor     edx, edx; lpSubKey
0x140008a97  mov     rcx, rbp; hkey
0x140008a9a  call    cs:__imp_RegGetValueW
0x140008aa0  test    eax, eax
0x140008aa2  jnz     short loc_140008B1E
0x140008aa4  xorps   xmm0, xmm0
0x140008aa7  movdqu  xmmword ptr [rsp+78h+Src], xmm0
0x140008aad  mov     [rsp+78h+var_20], 0
0x140008ab6  mov     edx, [rsp+78h+arg_0]
0x140008abd  test    rdx, rdx
0x140008ac0  jz      short loc_140008ACC
0x140008ac2  lea     rcx, [rsp+78h+Src]
0x140008ac7  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x140008acc  lea     rax, [rsp+78h+arg_0]
0x140008ad4  mov     [rsp+78h+pcbData], rax; pcbData
0x140008ad9  mov     rbx, [rsp+78h+Src]
0x140008ade  mov     [rsp+78h+pvData], rbx; pvData
0x140008ae3  mov     [rsp+78h+pdwType], 0; pdwType
0x140008aec  mov     r9d, 6; dwFlags
0x140008af2  mov     r8, rsi; lpValue
0x140008af5  xor     edx, edx; lpSubKey
0x140008af7  mov     rcx, rbp; hkey
0x140008afa  call    cs:__imp_RegGetValueW
0x140008b00  test    eax, eax
0x140008b02  jnz     short loc_140008B10
0x140008b04  mov     rdx, rbx; Src
0x140008b07  mov     rcx, rdi; void *
0x140008b0a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x140008b0f  nop
0x140008b10  test    rbx, rbx
0x140008b13  jz      short loc_140008B1E
0x140008b15  mov     rcx, rbx
0x140008b18  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140008b1e  mov     rax, rdi
0x140008b21  mov     rbx, [rsp+78h+arg_10]
0x140008b29  add     rsp, 60h
0x140008b2d  pop     rdi
0x140008b2e  pop     rsi
0x140008b2f  pop     rbp
0x140008b30  retn
```
