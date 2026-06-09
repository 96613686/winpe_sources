# CloneDirectoryNFAObject

- ea: `0x180035e94`
- end: `0x18003615b`
- name: `CloneDirectoryNFAObject`
- size: `711`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180036164`

## callees

- `0x180006f00`
- `0x18000c828`
- `0x18000e510`
- `0x180035e94`
- `0x180036bd0`
- `0x180036c54`
- `0x180042c6c`

## pseudocode

```c
__int64 __fastcall CloneDirectoryNFAObject(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned __int16 *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // r9
  unsigned __int16 *v12; // rcx
  __int64 v13; // rax
  unsigned __int16 *v14; // rcx
  __int64 v15; // rax
  void *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx

  v4 = IpsecAllocMem(88);
  v5 = v4;
  if ( !v4 )
  {
    v6 = 14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, 14);
    goto LABEL_50;
  }
  if ( *(_QWORD *)a1 )
  {
    v6 = CopyDSToFQRegString(*(_QWORD *)a1, 0, v4);
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_49;
      v8 = 123;
      goto LABEL_47;
    }
  }
  else
  {
    v6 = 0;
  }
  v9 = *(unsigned __int16 **)(a1 + 8);
  if ( v9 )
  {
    v10 = IpsecAllocStr(v9);
    *(_QWORD *)(v5 + 8) = v10;
    if ( !v10 )
    {
      v11 = 14;
      v6 = 14;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_49;
      v8 = 124;
      goto LABEL_48;
    }
  }
  v12 = *(unsigned __int16 **)(a1 + 80);
  if ( v12 )
  {
    v13 = IpsecAllocStr(v12);
    *(_QWORD *)(v5 + 80) = v13;
    if ( !v13 )
    {
      v11 = 14;
      v6 = 14;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_49;
      v8 = 125;
      goto LABEL_48;
    }
  }
  v14 = *(unsigned __int16 **)(a1 + 16);
  if ( v14 )
  {
    v15 = IpsecAllocStr(v14);
    *(_QWORD *)(v5 + 16) = v15;
    if ( !v15 )
    {
      v11 = 14;
      v6 = 14;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_49;
      v8 = 126;
      goto LABEL_48;
    }
  }
  *(_DWORD *)(v5 + 24) = *(_DWORD *)(a1 + 24);
  v16 = *(void **)(a1 + 32);
  if ( v16 )
  {
    v6 = CopyBinaryValue(v16, *(unsigned int *)(a1 + 40));
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_49;
      v8 = 127;
      goto LABEL_47;
    }
    *(_DWORD *)(v5 + 40) = *(_DWORD *)(a1 + 40);
  }
  v17 = *(_QWORD *)(a1 + 48);
  if ( v17 && (v6 = CopyDSToFQRegString(v17, 1, v5 + 48)) != 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_49;
    v8 = 128;
  }
  else
  {
    v18 = *(_QWORD *)(a1 + 56);
    if ( v18 && (v6 = CopyDSToFQRegString(v18, 1, v5 + 56)) != 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_49;
      v8 = 129;
    }
    else
    {
      v19 = *(_QWORD *)(a1 + 64);
      if ( !v19 || (v6 = CopyDSToFQRegString(v19, 1, v5 + 64)) == 0 )
      {
        *(_DWORD *)(v5 + 72) = *(_DWORD *)(a1 + 72);
        *a2 = v5;
        return v6;
      }
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_49;
      v8 = 130;
    }
  }
LABEL_47:
  v11 = v6;
LABEL_48:
  WPP_SF_d(v7[2], v8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v11);
LABEL_49:
  FreeIpsecNFAObject((LPVOID)v5);
LABEL_50:
  *a2 = 0;
  return v6;
}

```

## disassembly

```asm
0x180035e94  push    rbx
0x180035e96  push    rsi
0x180035e97  push    rdi
0x180035e98  push    r14
0x180035e9a  sub     rsp, 28h
0x180035e9e  mov     rdi, rcx
0x180035ea1  mov     r14, rdx
0x180035ea4  mov     ecx, 58h ; 'X'
0x180035ea9  call    IpsecAllocMem
0x180035eae  mov     rsi, rax
0x180035eb1  test    rax, rax
0x180035eb4  jnz     short loc_180035EF6
0x180035eb6  lea     r9d, [rax+0Eh]
0x180035eba  mov     ebx, r9d
0x180035ebd  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ec4  lea     rax, WPP_GLOBAL_Control
0x180035ecb  cmp     rcx, rax
0x180035ece  jz      loc_18003613D
0x180035ed4  test    byte ptr [rcx+1Ch], 10h
0x180035ed8  jz      loc_18003613D
0x180035ede  mov     rcx, [rcx+10h]
0x180035ee2  lea     edx, [rsi+7Ah]
0x180035ee5  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180035eec  call    WPP_SF_d
0x180035ef1  jmp     loc_18003613D
0x180035ef6  mov     rcx, [rdi]
0x180035ef9  test    rcx, rcx
0x180035efc  jz      short loc_180035F39
0x180035efe  mov     r8, rsi
0x180035f01  xor     edx, edx
0x180035f03  call    CopyDSToFQRegString
0x180035f08  mov     ebx, eax
0x180035f0a  test    eax, eax
0x180035f0c  jz      short loc_180035F3B
0x180035f0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180035f15  lea     rax, WPP_GLOBAL_Control
0x180035f1c  cmp     rcx, rax
0x180035f1f  jz      loc_180036135
0x180035f25  test    byte ptr [rcx+1Ch], 10h
0x180035f29  jz      loc_180036135
0x180035f2f  mov     edx, 7Bh ; '{'
0x180035f34  jmp     loc_180036122
0x180035f39  xor     ebx, ebx
0x180035f3b  mov     rcx, [rdi+8]; unsigned __int16 *
0x180035f3f  test    rcx, rcx
0x180035f42  jz      short loc_180035F83
0x180035f44  call    IpsecAllocStr
0x180035f49  mov     [rsi+8], rax
0x180035f4d  test    rax, rax
0x180035f50  jnz     short loc_180035F83
0x180035f52  lea     r9d, [rax+0Eh]
0x180035f56  mov     ebx, r9d
0x180035f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180035f60  lea     rax, WPP_GLOBAL_Control
0x180035f67  cmp     rcx, rax
0x180035f6a  jz      loc_180036135
0x180035f70  test    byte ptr [rcx+1Ch], 10h
0x180035f74  jz      loc_180036135
0x180035f7a  lea     edx, [r9+6Eh]
0x180035f7e  jmp     loc_180036125
0x180035f83  mov     rcx, [rdi+50h]; unsigned __int16 *
0x180035f87  test    rcx, rcx
0x180035f8a  jz      short loc_180035FCB
0x180035f8c  call    IpsecAllocStr
0x180035f91  mov     [rsi+50h], rax
0x180035f95  test    rax, rax
0x180035f98  jnz     short loc_180035FCB
0x180035f9a  lea     r9d, [rax+0Eh]
0x180035f9e  mov     ebx, r9d
0x180035fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180035fa8  lea     rax, WPP_GLOBAL_Control
0x180035faf  cmp     rcx, rax
0x180035fb2  jz      loc_180036135
0x180035fb8  test    byte ptr [rcx+1Ch], 10h
0x180035fbc  jz      loc_180036135
0x180035fc2  lea     edx, [r9+6Fh]
0x180035fc6  jmp     loc_180036125
0x180035fcb  mov     rcx, [rdi+10h]; unsigned __int16 *
0x180035fcf  test    rcx, rcx
0x180035fd2  jz      short loc_180036013
0x180035fd4  call    IpsecAllocStr
0x180035fd9  mov     [rsi+10h], rax
0x180035fdd  test    rax, rax
0x180035fe0  jnz     short loc_180036013
0x180035fe2  lea     r9d, [rax+0Eh]
0x180035fe6  mov     ebx, r9d
0x180035fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ff0  lea     rax, WPP_GLOBAL_Control
0x180035ff7  cmp     rcx, rax
0x180035ffa  jz      loc_180036135
0x180036000  test    byte ptr [rcx+1Ch], 10h
0x180036004  jz      loc_180036135
0x18003600a  lea     edx, [r9+70h]
0x18003600e  jmp     loc_180036125
0x180036013  mov     eax, [rdi+18h]
0x180036016  mov     [rsi+18h], eax
0x180036019  mov     rcx, [rdi+20h]; Src
0x18003601d  test    rcx, rcx
0x180036020  jz      short loc_180036065
0x180036022  mov     edx, [rdi+28h]; Size
0x180036025  lea     r8, [rsi+20h]
0x180036029  call    CopyBinaryValue
0x18003602e  mov     ebx, eax
0x180036030  test    eax, eax
0x180036032  jz      short loc_18003605F
0x180036034  mov     rcx, cs:WPP_GLOBAL_Control
0x18003603b  lea     rax, WPP_GLOBAL_Control
0x180036042  cmp     rcx, rax
0x180036045  jz      loc_180036135
0x18003604b  test    byte ptr [rcx+1Ch], 10h
0x18003604f  jz      loc_180036135
0x180036055  mov     edx, 7Fh
0x18003605a  jmp     loc_180036122
0x18003605f  mov     eax, [rdi+28h]
0x180036062  mov     [rsi+28h], eax
0x180036065  mov     rcx, [rdi+30h]
0x180036069  test    rcx, rcx
0x18003606c  jz      short loc_1800360AA
0x18003606e  lea     r8, [rsi+30h]
0x180036072  mov     edx, 1
0x180036077  call    CopyDSToFQRegString
0x18003607c  mov     ebx, eax
0x18003607e  test    eax, eax
0x180036080  jz      short loc_1800360AA
0x180036082  mov     rcx, cs:WPP_GLOBAL_Control
0x180036089  lea     rax, WPP_GLOBAL_Control
0x180036090  cmp     rcx, rax
0x180036093  jz      loc_180036135
0x180036099  test    byte ptr [rcx+1Ch], 10h
0x18003609d  jz      loc_180036135
0x1800360a3  mov     edx, 80h
0x1800360a8  jmp     short loc_180036122
0x1800360aa  mov     rcx, [rdi+38h]
0x1800360ae  test    rcx, rcx
0x1800360b1  jz      short loc_1800360E7
0x1800360b3  lea     r8, [rsi+38h]
0x1800360b7  mov     edx, 1
0x1800360bc  call    CopyDSToFQRegString
0x1800360c1  mov     ebx, eax
0x1800360c3  test    eax, eax
0x1800360c5  jz      short loc_1800360E7
0x1800360c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800360ce  lea     rax, WPP_GLOBAL_Control
0x1800360d5  cmp     rcx, rax
0x1800360d8  jz      short loc_180036135
0x1800360da  test    byte ptr [rcx+1Ch], 10h
0x1800360de  jz      short loc_180036135
0x1800360e0  mov     edx, 81h
0x1800360e5  jmp     short loc_180036122
0x1800360e7  mov     rcx, [rdi+40h]
0x1800360eb  test    rcx, rcx
0x1800360ee  jz      short loc_180036146
0x1800360f0  lea     r8, [rsi+40h]
0x1800360f4  mov     edx, 1
0x1800360f9  call    CopyDSToFQRegString
0x1800360fe  mov     ebx, eax
0x180036100  test    eax, eax
0x180036102  jz      short loc_180036146
0x180036104  mov     rcx, cs:WPP_GLOBAL_Control
0x18003610b  lea     rax, WPP_GLOBAL_Control
0x180036112  cmp     rcx, rax
0x180036115  jz      short loc_180036135
0x180036117  test    byte ptr [rcx+1Ch], 10h
0x18003611b  jz      short loc_180036135
0x18003611d  mov     edx, 82h
0x180036122  mov     r9d, ebx
0x180036125  mov     rcx, [rcx+10h]
0x180036129  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180036130  call    WPP_SF_d
0x180036135  mov     rcx, rsi; lpMem
0x180036138  call    FreeIpsecNFAObject
0x18003613d  mov     qword ptr [r14], 0
0x180036144  jmp     short loc_18003614F
0x180036146  mov     eax, [rdi+48h]
0x180036149  mov     [rsi+48h], eax
0x18003614c  mov     [r14], rsi
0x18003614f  mov     eax, ebx
0x180036151  add     rsp, 28h
0x180036155  pop     r14
0x180036157  pop     rdi
0x180036158  pop     rsi
0x180036159  pop     rbx
0x18003615a  retn
```
