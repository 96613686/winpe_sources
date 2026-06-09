# LipsStateIpsecFilterUpdateListCreate

- ea: `0x180046dd4`
- end: `0x180046ed5`
- name: `LipsStateIpsecFilterUpdateListCreate`
- size: `257`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180046bdc`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x180042ef8`
- `0x180046dd4`

## string_xrefs

- `0x180046e92`: `LipsStateIpsecFilterUpdateListCreate`

## pseudocode

```c
__int64 __fastcall LipsStateIpsecFilterUpdateListCreate(__int64 a1, _QWORD *a2, unsigned int *a3)
{
  unsigned int v3; // ebx
  __int64 v6; // rsi
  __int64 i; // rax
  unsigned int v8; // eax
  unsigned int v9; // edi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  _QWORD *v13; // rax
  __int64 result; // rax
  __int64 j; // rcx
  SIZE_T v16; // [rsp+40h] [rbp+8h] BYREF

  v3 = 0;
  v16 = 0;
  *a2 = 0;
  *a3 = 0;
  v6 = a1;
  for ( i = a1; i; ++v3 )
    i = *(_QWORD *)(i + 208);
  v8 = NsuSizeTMultiply(v3, 8, &v16);
  v9 = v8;
  if ( v8 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return LipsReportError(v9, (int)"LipsStateIpsecFilterUpdateListCreate");
    v11 = 48;
    v12 = v8;
LABEL_11:
    WPP_SF_d(v10[2], v11, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids, v12);
    return LipsReportError(v9, (int)"LipsStateIpsecFilterUpdateListCreate");
  }
  v13 = IpsecAllocMem(v16);
  if ( !v13 )
  {
    v9 = 8;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return LipsReportError(v9, (int)"LipsStateIpsecFilterUpdateListCreate");
    v11 = 49;
    v12 = 8;
    goto LABEL_11;
  }
  for ( j = 0; (unsigned int)j < v3; v6 = *(_QWORD *)(v6 + 208) )
  {
    v13[j] = v6;
    j = (unsigned int)(j + 1);
  }
  *a2 = v13;
  result = 0;
  *a3 = v3;
  return result;
}

```

## disassembly

```asm
0x180046dd4  mov     [rsp+arg_8], rbx
0x180046dd9  mov     [rsp+arg_10], rsi
0x180046dde  push    rdi
0x180046ddf  push    r14
0x180046de1  push    r15
0x180046de3  sub     rsp, 20h
0x180046de7  xor     ebx, ebx
0x180046de9  mov     [rsp+38h+arg_0], 0
0x180046df2  mov     [rdx], rbx
0x180046df5  mov     r14, r8
0x180046df8  mov     [r8], ebx
0x180046dfb  mov     r15, rdx
0x180046dfe  mov     rsi, rcx
0x180046e01  mov     rax, rcx
0x180046e04  test    rcx, rcx
0x180046e07  jz      short loc_180046E17
0x180046e09  mov     rax, [rax+0D0h]
0x180046e10  inc     ebx
0x180046e12  test    rax, rax
0x180046e15  jnz     short loc_180046E09
0x180046e17  mov     ecx, ebx
0x180046e19  lea     r8, [rsp+38h+arg_0]
0x180046e1e  mov     edx, 8
0x180046e23  call    NsuSizeTMultiply
0x180046e28  mov     edi, eax
0x180046e2a  test    eax, eax
0x180046e2c  jz      short loc_180046E51
0x180046e2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180046e35  lea     rdx, WPP_GLOBAL_Control
0x180046e3c  cmp     rcx, rdx
0x180046e3f  jz      short loc_180046E92
0x180046e41  test    byte ptr [rcx+1Ch], 10h
0x180046e45  jz      short loc_180046E92
0x180046e47  mov     edx, 30h ; '0'
0x180046e4c  mov     r9d, eax
0x180046e4f  jmp     short loc_180046E82
0x180046e51  mov     rcx, [rsp+38h+arg_0]
0x180046e56  call    IpsecAllocMem
0x180046e5b  test    rax, rax
0x180046e5e  jnz     short loc_180046EA2
0x180046e60  lea     edi, [rax+8]
0x180046e63  mov     rcx, cs:WPP_GLOBAL_Control
0x180046e6a  lea     rdx, WPP_GLOBAL_Control
0x180046e71  cmp     rcx, rdx
0x180046e74  jz      short loc_180046E92
0x180046e76  test    byte ptr [rcx+1Ch], 10h
0x180046e7a  jz      short loc_180046E92
0x180046e7c  lea     edx, [rax+31h]
0x180046e7f  mov     r9d, edi
0x180046e82  mov     rcx, [rcx+10h]
0x180046e86  lea     r8, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids
0x180046e8d  call    WPP_SF_d
0x180046e92  lea     rdx, aLipsstateipsec_6; "LipsStateIpsecFilterUpdateListCreate"
0x180046e99  mov     ecx, edi
0x180046e9b  call    LipsReportError
0x180046ea0  jmp     short loc_180046EC1
0x180046ea2  xor     ecx, ecx
0x180046ea4  test    ebx, ebx
0x180046ea6  jz      short loc_180046EB9
0x180046ea8  mov     [rax+rcx*8], rsi
0x180046eac  inc     ecx
0x180046eae  mov     rsi, [rsi+0D0h]
0x180046eb5  cmp     ecx, ebx
0x180046eb7  jb      short loc_180046EA8
0x180046eb9  mov     [r15], rax
0x180046ebc  xor     eax, eax
0x180046ebe  mov     [r14], ebx
0x180046ec1  mov     rbx, [rsp+38h+arg_8]
0x180046ec6  mov     rsi, [rsp+38h+arg_10]
0x180046ecb  add     rsp, 20h
0x180046ecf  pop     r15
0x180046ed1  pop     r14
0x180046ed3  pop     rdi
0x180046ed4  retn
```
