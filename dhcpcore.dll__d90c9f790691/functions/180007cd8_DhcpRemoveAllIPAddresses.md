# DhcpRemoveAllIPAddresses

- ea: `0x180007cd8`
- end: `0x180007e0e`
- name: `DhcpRemoveAllIPAddresses`
- size: `310`
- prototype: `unsigned int __fastcall(_QWORD *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800232e8`

## callees

- `0x180007328`
- `0x180007cd8`
- `0x180008740`
- `0x18004d1a0`
- `0x18004d958`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007dfa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007dfa`
- `NSI!NsiGetParameter` at `0x180007d3a`
- `NSI!NsiGetParameter` at `0x180007d3a`

## pseudocode

```c
unsigned int __fastcall DhcpRemoveAllIPAddresses(_QWORD *a1, int a2)
{
  __int64 v4; // rdx
  unsigned int result; // eax
  _DWORD *v6; // rdi
  __int64 i; // rbx
  char v8; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v9; // [rsp+80h] [rbp+18h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp+20h] BYREF

  v9 = 0;
  lpMem = 0;
  v8 = 0;
  if ( (unsigned int)NsiGetParameter(1, &NPI_MS_IPV4_MODULEID, 7, a1, 8, 0, &v8, 1, 231) )
  {
    LOBYTE(v4) = 0;
    v8 = 0;
  }
  else
  {
    LOBYTE(v4) = v8;
  }
  result = DhcpEnumIPv4Address(a1, v4, &v9, &lpMem);
  v6 = lpMem;
  if ( result )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      result = WPP_SF_D(1025, 221, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, result);
  }
  else
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      result = WPP_SF_qD(1028, 220, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, *a1, a2);
    for ( i = 0; (unsigned int)i < v9; i = (unsigned int)(i + 1) )
    {
      if ( a2 != v6[i] )
        result = DhcpDelIPv4Address(a1);
    }
  }
  if ( v6 )
    return HeapFree(NtCurrentPeb()->ProcessHeap, 0, v6);
  return result;
}

```

## disassembly

```asm
0x180007cd8  mov     rax, rsp
0x180007cdb  mov     [rax+10h], rbx
0x180007cdf  push    rbp
0x180007ce0  push    rdi
0x180007ce1  push    r14
0x180007ce3  sub     rsp, 50h
0x180007ce7  mov     dword ptr [rax-28h], 0E7h
0x180007cee  mov     r8d, 7
0x180007cf4  mov     dword ptr [rax-30h], 1
0x180007cfb  mov     ebp, edx
0x180007cfd  mov     dword ptr [rax+18h], 0
0x180007d04  mov     r14, rcx
0x180007d07  mov     qword ptr [rax+20h], 0
0x180007d0f  mov     r9, rcx
0x180007d12  mov     byte ptr [rax+8], 0
0x180007d16  lea     rax, [rax+8]
0x180007d1a  mov     [rsp+68h+var_38], rax
0x180007d1f  lea     ecx, [r8-6]
0x180007d23  mov     [rsp+68h+var_40], 0
0x180007d2b  lea     rdx, NPI_MS_IPV4_MODULEID
0x180007d32  mov     [rsp+68h+var_48], 8
0x180007d3a  call    cs:__imp_NsiGetParameter
0x180007d40  test    eax, eax
0x180007d42  jz      short loc_180007D4C
0x180007d44  xor     dl, dl
0x180007d46  mov     [rsp+68h+arg_0], dl
0x180007d4a  jmp     short loc_180007D50
0x180007d4c  mov     dl, [rsp+68h+arg_0]
0x180007d50  lea     r9, [rsp+68h+lpMem]
0x180007d58  mov     rcx, r14
0x180007d5b  lea     r8, [rsp+68h+arg_10]
0x180007d63  call    DhcpEnumIPv4Address
0x180007d68  mov     rdi, [rsp+68h+lpMem]
0x180007d70  test    eax, eax
0x180007d72  jz      short loc_180007D98
0x180007d74  test    byte ptr cs:xmmword_1800616A0, 2
0x180007d7b  jz      short loc_180007DE3
0x180007d7d  mov     edx, 0DDh
0x180007d82  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180007d89  mov     ecx, 401h
0x180007d8e  mov     r9d, eax
0x180007d91  call    WPP_SF_D
0x180007d96  jmp     short loc_180007DE3
0x180007d98  test    byte ptr cs:xmmword_1800616A0, 10h
0x180007d9f  jz      short loc_180007DBE
0x180007da1  mov     r9, [r14]
0x180007da4  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180007dab  mov     edx, 0DCh
0x180007db0  mov     [rsp+68h+var_48], ebp
0x180007db4  mov     ecx, 404h
0x180007db9  call    WPP_SF_qD
0x180007dbe  xor     ebx, ebx
0x180007dc0  cmp     [rsp+68h+arg_10], ebx
0x180007dc7  jbe     short loc_180007DE3
0x180007dc9  mov     edx, [rdi+rbx*4]
0x180007dcc  cmp     ebp, edx
0x180007dce  jz      short loc_180007DD8
0x180007dd0  mov     rcx, r14
0x180007dd3  call    DhcpDelIPv4Address
0x180007dd8  inc     ebx
0x180007dda  cmp     ebx, [rsp+68h+arg_10]
0x180007de1  jb      short loc_180007DC9
0x180007de3  test    rdi, rdi
0x180007de6  jz      short loc_180007E00
0x180007de8  mov     rcx, gs:60h
0x180007df1  mov     r8, rdi; lpMem
0x180007df4  xor     edx, edx; dwFlags
0x180007df6  mov     rcx, [rcx+30h]; hHeap
0x180007dfa  call    cs:__imp_HeapFree
0x180007e00  mov     rbx, [rsp+68h+arg_8]
0x180007e05  add     rsp, 50h
0x180007e09  pop     r14
0x180007e0b  pop     rdi
0x180007e0c  pop     rbp
0x180007e0d  retn
```
