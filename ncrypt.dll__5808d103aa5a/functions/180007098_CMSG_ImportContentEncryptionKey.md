# CMSG_ImportContentEncryptionKey

- ea: `0x180007098`
- end: `0x180007113`
- name: `CMSG_ImportContentEncryptionKey`
- size: `123`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002790`
- `0x180007420`

## callees

- `0x180006a70`
- `0x180007098`
- `0x18000d02c`

## string_xrefs

- `0x1800070ed`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\cmsg.c`

## pseudocode

```c
__int64 __fastcall CMSG_ImportContentEncryptionKey(__int64 a1, __int64 a2, UCHAR *a3, ULONG a4)
{
  int v4; // edx
  unsigned int v5; // ebx
  int v6; // r8d

  v5 = CNG_ImportCEKBCryptKeyAndAlgorithmInfo(a2, a3, a4, a1 + 16, a1 + 88);
  if ( v5 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      v6,
      (unsigned int)"Status",
      v5,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c",
      25);
  return v5;
}

```

## disassembly

```asm
0x180007098  push    rbx
0x18000709a  sub     rsp, 40h
0x18000709e  mov     r10d, r9d
0x1800070a1  lea     rax, [rcx+58h]
0x1800070a5  mov     r11, r8
0x1800070a8  mov     [rsp+48h+var_28], rax
0x1800070ad  mov     rbx, rdx
0x1800070b0  lea     r9, [rcx+10h]
0x1800070b4  mov     r8d, r10d
0x1800070b7  mov     rdx, r11
0x1800070ba  mov     rcx, rbx
0x1800070bd  call    CNG_ImportCEKBCryptKeyAndAlgorithmInfo
0x1800070c2  mov     ebx, eax
0x1800070c4  test    eax, eax
0x1800070c6  jnz     short loc_1800070D0
0x1800070c8  mov     eax, ebx
0x1800070ca  add     rsp, 40h
0x1800070ce  pop     rbx
0x1800070cf  retn
0x1800070d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070d7  lea     rax, WPP_GLOBAL_Control
0x1800070de  cmp     rcx, rax
0x1800070e1  jz      short loc_1800070C8
0x1800070e3  test    byte ptr [rcx+1Ch], 1
0x1800070e7  jz      short loc_1800070C8
0x1800070e9  mov     rcx, [rcx+10h]
0x1800070ed  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800070f4  mov     [rsp+48h+var_18], 219h
0x1800070fc  lea     r9, aStatus; "Status"
0x180007103  mov     [rsp+48h+var_20], rax
0x180007108  mov     dword ptr [rsp+48h+var_28], ebx
0x18000710c  call    WPP_SF_sDsd
0x180007111  jmp     short loc_1800070C8
```
