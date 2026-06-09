# ExpandRegLocationFromValue

- ea: `0x18001afbc`
- end: `0x18001b11e`
- name: `ExpandRegLocationFromValue`
- size: `354`
- prototype: `__int64 __fastcall(void *Src, __int64, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x180006a18`

## callees

- `0x180005178`
- `0x180005330`
- `0x18001afbc`
- `0x18004d1a0`
- `0x18004d310`
- `0x18004d9e8`
- `0x18004e7e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b0e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b0e1`

## string_xrefs

- `0x18001b0aa`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\?\DhcpClassIdBin`

## pseudocode

```c
__int64 __fastcall ExpandRegLocationFromValue(void *Src, __int64 a2, void *a3)
{
  int v5; // eax
  void *v6; // rbx
  wchar_t *v7; // rcx
  unsigned int v8; // esi
  DWORD v10; // [rsp+30h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-8h] BYREF
  DWORD v12; // [rsp+68h] [rbp+28h] BYREF
  int v13; // [rsp+6Ch] [rbp+2Ch]

  v13 = HIDWORD(a2);
  lpMem = 0;
  v10 = 0;
  v12 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_SSS((_DWORD)Src, a2, (_DWORD)a3, (_DWORD)a3, (__int64)Src);
  v5 = DhcpRegReadFromLocation(Src, a3, (BYTE **)&lpMem, &v12, &v10);
  if ( v5 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_SD(1025, 29, (unsigned int)WPP_94d5010c5674399d06148e3a91870046_Traceguids, (_DWORD)Src, v5);
LABEL_12:
    v6 = lpMem;
    v7 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\?\\DhcpClassIdBin";
    goto LABEL_14;
  }
  if ( v12 != 7 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_d(1025, 30, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v12);
    goto LABEL_12;
  }
  if ( v10 < 2 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_d(1025, 31, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v10);
    goto LABEL_12;
  }
  v6 = lpMem;
  v7 = (wchar_t *)lpMem;
LABEL_14:
  v8 = DhcpRegExpandString(v7, a3);
  if ( v6 )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 32, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18001afbc  mov     rax, rsp
0x18001afbf  mov     [rax+8], rbx
0x18001afc3  mov     [rax+18h], rsi
0x18001afc7  mov     [rax+10h], rdx
0x18001afcb  push    rbp
0x18001afcc  push    rdi
0x18001afcd  push    r14
0x18001afcf  mov     rbp, rsp
0x18001afd2  sub     rsp, 40h
0x18001afd6  mov     r14, r9
0x18001afd9  mov     [rbp+lpMem], 0
0x18001afe1  mov     rsi, r8
0x18001afe4  mov     [rbp+var_10], 0
0x18001afeb  mov     rbx, rcx
0x18001afee  mov     [rbp+arg_8], 0
0x18001aff5  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001affc  jz      short loc_18001B00A
0x18001affe  mov     r9, r8
0x18001b001  mov     [rax-38h], rcx
0x18001b005  call    WPP_SF_SSS
0x18001b00a  lea     rax, [rbp+var_10]
0x18001b00e  mov     rdx, rsi; void *
0x18001b011  lea     r9, [rbp+arg_8]
0x18001b015  mov     [rsp+40h+var_20], rax; LPDWORD
0x18001b01a  lea     r8, [rbp+lpMem]
0x18001b01e  mov     rcx, rbx; Src
0x18001b021  call    DhcpRegReadFromLocation
0x18001b026  test    eax, eax
0x18001b028  jz      short loc_18001B052
0x18001b02a  test    byte ptr cs:xmmword_1800616A0, 2
0x18001b031  jz      short loc_18001B0A6
0x18001b033  mov     edx, 1Dh
0x18001b038  mov     dword ptr [rsp+40h+var_20], eax
0x18001b03c  mov     ecx, 401h
0x18001b041  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18001b048  mov     r9, rbx
0x18001b04b  call    WPP_SF_SD
0x18001b050  jmp     short loc_18001B0A6
0x18001b052  mov     r9d, [rbp+arg_8]
0x18001b056  cmp     r9d, 7
0x18001b05a  jz      short loc_18001B07D
0x18001b05c  test    byte ptr cs:xmmword_1800616A0, 2
0x18001b063  jz      short loc_18001B0A6
0x18001b065  mov     edx, 1Eh
0x18001b06a  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18001b071  mov     ecx, 401h
0x18001b076  call    WPP_SF_d
0x18001b07b  jmp     short loc_18001B0A6
0x18001b07d  mov     r9d, [rbp+var_10]
0x18001b081  cmp     r9d, 2
0x18001b085  jnb     short loc_18001B0B3
0x18001b087  test    byte ptr cs:xmmword_1800616A0, 2
0x18001b08e  jz      short loc_18001B0A6
0x18001b090  mov     edx, 1Fh
0x18001b095  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18001b09c  mov     ecx, 401h
0x18001b0a1  call    WPP_SF_d
0x18001b0a6  mov     rbx, [rbp+lpMem]
0x18001b0aa  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x18001b0b1  jmp     short loc_18001B0BA
0x18001b0b3  mov     rbx, [rbp+lpMem]
0x18001b0b7  mov     rcx, rbx; Src
0x18001b0ba  mov     r8, r14
0x18001b0bd  mov     rdx, rsi; void *
0x18001b0c0  mov     rdi, rbx
0x18001b0c3  call    DhcpRegExpandString
0x18001b0c8  mov     esi, eax
0x18001b0ca  test    rbx, rbx
0x18001b0cd  jz      short loc_18001B0E7
0x18001b0cf  mov     rcx, gs:60h
0x18001b0d8  mov     r8, rbx; lpMem
0x18001b0db  xor     edx, edx; dwFlags
0x18001b0dd  mov     rcx, [rcx+30h]; hHeap
0x18001b0e1  call    cs:__imp_HeapFree
0x18001b0e7  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001b0ee  jz      short loc_18001B109
0x18001b0f0  mov     edx, 20h ; ' '
0x18001b0f5  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18001b0fc  mov     ecx, 404h
0x18001b101  mov     r9d, esi
0x18001b104  call    WPP_SF_D
0x18001b109  mov     rbx, [rsp+40h+arg_0]
0x18001b10e  mov     eax, esi
0x18001b110  mov     rsi, [rsp+40h+arg_10]
0x18001b115  add     rsp, 40h
0x18001b119  pop     r14
0x18001b11b  pop     rdi
0x18001b11c  pop     rbp
0x18001b11d  retn
```
