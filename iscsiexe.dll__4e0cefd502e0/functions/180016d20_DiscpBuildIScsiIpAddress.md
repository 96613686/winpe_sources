# DiscpBuildIScsiIpAddress

- ea: `0x180016d20`
- end: `0x180016ddf`
- name: `DiscpBuildIScsiIpAddress`
- size: `191`
- prototype: `__int64 __fastcall(char, __int64, char, int *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800034a0`
- `0x180004af8`
- `0x180009f14`
- `0x18000b17c`
- `0x180010b5c`
- `0x180011fb8`

## callees

- `0x180001cfe`
- `0x180016d20`

## import_xrefs

- `ISCSIUM!DiscpCopyToCountedString` at `0x180016d5c`
- `ISCSIUM!DiscpCopyToCountedString` at `0x180016d5c`
- `ISCSIUM!DiscpTextAddrToBinary` at `0x180016d8e`
- `ISCSIUM!DiscpTextAddrToBinary` at `0x180016d8e`
- `ISCSIUM!DiscpIsDNSAddress` at `0x180016d3f`
- `ISCSIUM!DiscpIsDNSAddress` at `0x180016d3f`

## pseudocode

```c
__int64 __fastcall DiscpBuildIScsiIpAddress(char a1, __int64 a2, char a3, int *a4)
{
  unsigned int v7; // edx
  __int64 v8; // rdx
  int v9; // eax
  __int128 v10; // xmm0
  int v11; // ecx
  _DWORD v13[10]; // [rsp+20h] [rbp-28h] BYREF

  if ( a1 || !(unsigned __int8)DiscpIsDNSAddress(a2) )
  {
    memset(v13, 0, 28);
    memset_0(a4, 0, 0x224u);
    LOBYTE(v8) = a3;
    v7 = DiscpTextAddrToBinary(a2, v8, v13);
    if ( !v7 )
    {
      if ( v13[0] )
      {
        v10 = *(_OWORD *)&v13[3];
        v11 = v13[2];
        a4[6] = v13[1];
        v9 = 2;
        *(_OWORD *)(a4 + 2) = v10;
        a4[7] = v11;
      }
      else
      {
        a4[1] = v13[1];
        v9 = 1;
      }
      *a4 = v9;
      *((_WORD *)a4 + 16) = 512;
    }
  }
  else
  {
    *a4 = 0;
    DiscpCopyToCountedString(a4 + 8, a2, 256);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180016d20  mov     [rsp+arg_0], rbx
0x180016d25  mov     [rsp+arg_8], rsi
0x180016d2a  push    rdi
0x180016d2b  sub     rsp, 40h
0x180016d2f  mov     rbx, r9
0x180016d32  mov     sil, r8b
0x180016d35  mov     rdi, rdx
0x180016d38  test    cl, cl
0x180016d3a  jnz     short loc_180016D66
0x180016d3c  mov     rcx, rdx
0x180016d3f  call    cs:__imp_DiscpIsDNSAddress
0x180016d45  test    al, al
0x180016d47  jz      short loc_180016D66
0x180016d49  lea     rcx, [rbx+20h]
0x180016d4d  mov     dword ptr [rbx], 0
0x180016d53  mov     r8d, 100h
0x180016d59  mov     rdx, rdi
0x180016d5c  call    cs:__imp_DiscpCopyToCountedString
0x180016d62  xor     edx, edx
0x180016d64  jmp     short loc_180016DCD
0x180016d66  xorps   xmm0, xmm0
0x180016d69  xor     edx, edx; Val
0x180016d6b  movups  xmmword ptr [rsp+48h+var_28], xmm0
0x180016d70  mov     r8d, 224h; Size
0x180016d76  mov     rcx, rbx; void *
0x180016d79  movups  xmmword ptr [rsp+48h+var_28+0Ch], xmm0
0x180016d7e  call    memset_0
0x180016d83  lea     r8, [rsp+48h+var_28]
0x180016d88  mov     dl, sil
0x180016d8b  mov     rcx, rdi
0x180016d8e  call    cs:__imp_DiscpTextAddrToBinary
0x180016d94  mov     edx, eax
0x180016d96  test    eax, eax
0x180016d98  jnz     short loc_180016DCD
0x180016d9a  mov     eax, [rsp+48h+var_28+4]
0x180016d9e  cmp     [rsp+48h+var_28], edx
0x180016da2  jnz     short loc_180016DAC
0x180016da4  mov     [rbx+4], eax
0x180016da7  lea     eax, [rdx+1]
0x180016daa  jmp     short loc_180016DC5
0x180016dac  movups  xmm0, xmmword ptr [rsp+48h+var_28+0Ch]
0x180016db1  mov     ecx, [rsp+48h+var_28+8]
0x180016db5  mov     [rbx+18h], eax
0x180016db8  mov     eax, 2
0x180016dbd  movdqu  xmmword ptr [rbx+8], xmm0
0x180016dc2  mov     [rbx+1Ch], ecx
0x180016dc5  mov     [rbx], eax
0x180016dc7  mov     word ptr [rbx+20h], 200h
0x180016dcd  mov     rbx, [rsp+48h+arg_0]
0x180016dd2  mov     eax, edx
0x180016dd4  mov     rsi, [rsp+48h+arg_8]
0x180016dd9  add     rsp, 40h
0x180016ddd  pop     rdi
0x180016dde  retn
```
