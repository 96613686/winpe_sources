# AslpFileGetCrcChecksum

- ea: `0x18000fea0`
- end: `0x18000ff9c`
- name: `AslpFileGetCrcChecksum`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f980`

## callees

- `0x18000b8ac`
- `0x18000e240`
- `0x18000fea0`

## string_xrefs

- `0x18000ff41`: `Overflow/underflow encountered computing position for CRC_CHECKSUM [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetCrcChecksum(_DWORD *a1, __int64 a2)
{
  unsigned __int64 v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rdx
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned __int64 v9; // r11
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // r8

  v3 = *(_QWORD *)(a2 + 16);
  v4 = 0;
  if ( v3 >= 0x2000 )
  {
    v8 = AslComputeCrc32(0, *(_QWORD *)(a2 + 24), 4096);
    v10 = v9 + v3;
    v11 = -1;
    if ( v9 + v3 >= v9 )
      v11 = v9 + v3;
    v12 = v11;
    v7 = v9 + v3 < v9 ? 0xC0000095 : 0;
    if ( v10 < v9 || (v11 < 0x1000 ? (v6 = -1) : (v6 = v11 - 4096), v7 = v12 < 0x1000 ? 0xC0000095 : 0, v12 < 0x1000) )
    {
      AslLogCallPrintf(
        1,
        "AslpFileGetCrcChecksum",
        5021,
        "Overflow/underflow encountered computing position for CRC_CHECKSUM [%x]",
        v7);
      return v7;
    }
    v5 = 4096;
    v4 = v8;
  }
  else
  {
    v5 = *(unsigned int *)(a2 + 32);
    v6 = *(_QWORD *)(a2 + 24);
  }
  *a1 = AslComputeCrc32(v4, v6, v5);
  return 0;
}

```

## disassembly

```asm
0x18000fea0  mov     [rsp+arg_0], rbx
0x18000fea5  mov     [rsp+arg_8], rsi
0x18000feaa  push    rdi
0x18000feab  sub     rsp, 40h
0x18000feaf  mov     rdi, rcx
0x18000feb2  mov     rbx, [rdx+10h]
0x18000feb6  xor     ecx, ecx
0x18000feb8  cmp     rbx, 2000h
0x18000febf  jnb     short loc_18000FEDB
0x18000fec1  mov     r8d, [rdx+20h]
0x18000fec5  mov     rdx, [rdx+18h]
0x18000fec9  call    AslComputeCrc32
0x18000fece  mov     [rdi], eax
0x18000fed0  xor     ebx, ebx
0x18000fed2  mov     [rsp+48h+var_18], ebx
0x18000fed6  jmp     loc_18000FF5F
0x18000fedb  mov     r11, [rdx+18h]
0x18000fedf  mov     esi, 1000h
0x18000fee4  mov     r8d, esi
0x18000fee7  mov     rdx, r11
0x18000feea  call    AslComputeCrc32
0x18000feef  lea     rcx, [r11+rbx]
0x18000fef3  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000fef7  mov     rdx, r9
0x18000fefa  cmp     rcx, r11
0x18000fefd  cmovnb  rdx, rcx
0x18000ff01  mov     r8, rdx
0x18000ff04  sbb     ebx, ebx
0x18000ff06  mov     r10d, 0C0000095h
0x18000ff0c  and     ebx, r10d
0x18000ff0f  mov     [rsp+48h+var_18], ebx
0x18000ff13  cmp     rcx, r11
0x18000ff16  jb      short loc_18000FF3D
0x18000ff18  cmp     rdx, rsi
0x18000ff1b  jb      short loc_18000FF22
0x18000ff1d  sub     rdx, rsi
0x18000ff20  jmp     short loc_18000FF25
0x18000ff22  mov     rdx, r9
0x18000ff25  cmp     r8, rsi
0x18000ff28  sbb     ebx, ebx
0x18000ff2a  and     ebx, r10d
0x18000ff2d  mov     [rsp+48h+var_18], ebx
0x18000ff31  cmp     r8, rsi
0x18000ff34  jb      short loc_18000FF3D
0x18000ff36  mov     r8d, esi
0x18000ff39  mov     ecx, eax
0x18000ff3b  jmp     short loc_18000FEC9
0x18000ff3d  mov     [rsp+48h+var_28], ebx
0x18000ff41  lea     r9, aOverflowUnderf; "Overflow/underflow encountered computin"...
0x18000ff48  mov     r8d, 139Dh
0x18000ff4e  lea     rdx, aAslpfilegetcrc; "AslpFileGetCrcChecksum"
0x18000ff55  mov     ecx, 1
0x18000ff5a  call    AslLogCallPrintf
0x18000ff5f  jmp     short loc_18000FF8A
0x18000ff61  mov     ebx, eax
0x18000ff63  mov     [rsp+48h+var_18], eax
0x18000ff67  mov     [rsp+48h+var_28], eax
0x18000ff6b  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x18000ff72  mov     r8d, 13AAh
0x18000ff78  lea     rdx, aAslpfilegetcrc; "AslpFileGetCrcChecksum"
0x18000ff7f  mov     ecx, 1
0x18000ff84  call    AslLogCallPrintf
0x18000ff89  nop
0x18000ff8a  mov     eax, ebx
0x18000ff8c  mov     rbx, [rsp+48h+arg_0]
0x18000ff91  mov     rsi, [rsp+48h+arg_8]
0x18000ff96  add     rsp, 40h
0x18000ff9a  pop     rdi
0x18000ff9b  retn
0x180019716  push    rbp
0x180019718  sub     rsp, 30h
0x18001971c  mov     rbp, rdx
0x18001971f  mov     rax, [rcx]
0x180019722  xor     ecx, ecx
0x180019724  cmp     dword ptr [rax], 0C00000FDh
0x18001972a  setnz   cl
0x18001972d  mov     [rbp+34h], ecx
0x180019730  mov     eax, [rbp+34h]
0x180019733  add     rsp, 30h
0x180019737  pop     rbp
0x180019738  retn
```
