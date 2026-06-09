# LipsStateIkeFilterUpdateListCreate

- ea: `0x180045e14`
- end: `0x180045f15`
- name: `LipsStateIkeFilterUpdateListCreate`
- size: `257`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180045c1c`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x180042ef8`
- `0x180045e14`

## string_xrefs

- `0x180045ed2`: `LipsStateIkeFilterUpdateListCreate`

## pseudocode

```c
__int64 __fastcall LipsStateIkeFilterUpdateListCreate(__int64 a1, _QWORD *a2, unsigned int *a3)
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
    i = *(_QWORD *)(i + 192);
  v8 = NsuSizeTMultiply(v3, 8, &v16);
  v9 = v8;
  if ( v8 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return LipsReportError(v9, (int)"LipsStateIkeFilterUpdateListCreate");
    v11 = 36;
    v12 = v8;
LABEL_11:
    WPP_SF_d(v10[2], v11, WPP_b2e62c343c9f3927bd54de5c93575086_Traceguids, v12);
    return LipsReportError(v9, (int)"LipsStateIkeFilterUpdateListCreate");
  }
  v13 = IpsecAllocMem(v16);
  if ( !v13 )
  {
    v9 = 8;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return LipsReportError(v9, (int)"LipsStateIkeFilterUpdateListCreate");
    v11 = 37;
    v12 = 8;
    goto LABEL_11;
  }
  for ( j = 0; (unsigned int)j < v3; v6 = *(_QWORD *)(v6 + 192) )
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
0x180045e14  mov     [rsp+arg_8], rbx
0x180045e19  mov     [rsp+arg_10], rsi
0x180045e1e  push    rdi
0x180045e1f  push    r14
0x180045e21  push    r15
0x180045e23  sub     rsp, 20h
0x180045e27  xor     ebx, ebx
0x180045e29  mov     [rsp+38h+arg_0], 0
0x180045e32  mov     [rdx], rbx
0x180045e35  mov     r14, r8
0x180045e38  mov     [r8], ebx
0x180045e3b  mov     r15, rdx
0x180045e3e  mov     rsi, rcx
0x180045e41  mov     rax, rcx
0x180045e44  test    rcx, rcx
0x180045e47  jz      short loc_180045E57
0x180045e49  mov     rax, [rax+0C0h]
0x180045e50  inc     ebx
0x180045e52  test    rax, rax
0x180045e55  jnz     short loc_180045E49
0x180045e57  mov     ecx, ebx
0x180045e59  lea     r8, [rsp+38h+arg_0]
0x180045e5e  mov     edx, 8
0x180045e63  call    NsuSizeTMultiply
0x180045e68  mov     edi, eax
0x180045e6a  test    eax, eax
0x180045e6c  jz      short loc_180045E91
0x180045e6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180045e75  lea     rdx, WPP_GLOBAL_Control
0x180045e7c  cmp     rcx, rdx
0x180045e7f  jz      short loc_180045ED2
0x180045e81  test    byte ptr [rcx+1Ch], 10h
0x180045e85  jz      short loc_180045ED2
0x180045e87  mov     edx, 24h ; '$'
0x180045e8c  mov     r9d, eax
0x180045e8f  jmp     short loc_180045EC2
0x180045e91  mov     rcx, [rsp+38h+arg_0]
0x180045e96  call    IpsecAllocMem
0x180045e9b  test    rax, rax
0x180045e9e  jnz     short loc_180045EE2
0x180045ea0  lea     edi, [rax+8]
0x180045ea3  mov     rcx, cs:WPP_GLOBAL_Control
0x180045eaa  lea     rdx, WPP_GLOBAL_Control
0x180045eb1  cmp     rcx, rdx
0x180045eb4  jz      short loc_180045ED2
0x180045eb6  test    byte ptr [rcx+1Ch], 10h
0x180045eba  jz      short loc_180045ED2
0x180045ebc  lea     edx, [rax+25h]
0x180045ebf  mov     r9d, edi
0x180045ec2  mov     rcx, [rcx+10h]
0x180045ec6  lea     r8, WPP_b2e62c343c9f3927bd54de5c93575086_Traceguids
0x180045ecd  call    WPP_SF_d
0x180045ed2  lea     rdx, aLipsstateikefi_4; "LipsStateIkeFilterUpdateListCreate"
0x180045ed9  mov     ecx, edi
0x180045edb  call    LipsReportError
0x180045ee0  jmp     short loc_180045F01
0x180045ee2  xor     ecx, ecx
0x180045ee4  test    ebx, ebx
0x180045ee6  jz      short loc_180045EF9
0x180045ee8  mov     [rax+rcx*8], rsi
0x180045eec  inc     ecx
0x180045eee  mov     rsi, [rsi+0C0h]
0x180045ef5  cmp     ecx, ebx
0x180045ef7  jb      short loc_180045EE8
0x180045ef9  mov     [r15], rax
0x180045efc  xor     eax, eax
0x180045efe  mov     [r14], ebx
0x180045f01  mov     rbx, [rsp+38h+arg_8]
0x180045f06  mov     rsi, [rsp+38h+arg_10]
0x180045f0b  add     rsp, 20h
0x180045f0f  pop     r15
0x180045f11  pop     r14
0x180045f13  pop     rdi
0x180045f14  retn
```
