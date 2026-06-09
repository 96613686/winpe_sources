# KpsDerUnpack(ulong,void *,ulong,void * *)

- ea: `0x180028c08`
- end: `0x180028db7`
- name: `?KpsDerUnpack@@YAKKPEAXKPEAPEAX@Z`
- size: `431`
- prototype: `__int64 __fastcall(unsigned int, void *, __int64, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800285a0`
- `0x18002aae8`
- `0x18002b4e0`

## callees

- `0x18001ae38`
- `0x180028c08`
- `0x18002c458`

## import_xrefs

- `MSASN1!ASN1_CloseDecoder` at `0x180028d5f`
- `MSASN1!ASN1_CloseDecoder` at `0x180028d5f`
- `MSASN1!ASN1_Decode` at `0x180028ce9`
- `MSASN1!ASN1_Decode` at `0x180028ce9`
- `MSASN1!ASN1_FreeDecoded` at `0x180028d3f`
- `MSASN1!ASN1_FreeDecoded` at `0x180028d3f`
- `MSASN1!ASN1_CreateDecoder` at `0x180028c80`
- `MSASN1!ASN1_CreateDecoder` at `0x180028c80`

## pseudocode

```c
__int64 __fastcall KpsDerUnpack(unsigned int a1, void *a2, __int64 a3, void **a4)
{
  unsigned int v4; // ebx
  int v6; // r15d
  unsigned int Decoder; // edi
  int v9; // r8d
  _QWORD *v10; // rcx
  void *v11; // rdx
  int v12; // r8d
  void *v14; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v15[4]; // [rsp+38h] [rbp-20h] BYREF

  v4 = 0;
  v15[0] = 0;
  v14 = 0;
  v6 = (int)a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, a1);
  Decoder = ASN1_CreateDecoder(KRB5_Module, v15, 0, 0);
  if ( Decoder )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    WPP_SF_dsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, v9, Decoder, 0, 8);
LABEL_8:
    v10 = WPP_GLOBAL_Control;
LABEL_9:
    v11 = v14;
    v4 = Decoder;
    goto LABEL_15;
  }
  Decoder = ASN1_Decode(v15[0], &v14, a1, 8);
  if ( Decoder )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    WPP_SF_dsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, v12, Decoder, v6, 24);
    goto LABEL_8;
  }
  v11 = 0;
  v10 = WPP_GLOBAL_Control;
  *a4 = v14;
  v14 = 0;
LABEL_15:
  if ( v11 )
  {
    ASN1_FreeDecoded(v15[0], v11, a1);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v15[0] )
  {
    ASN1_CloseDecoder(v15[0]);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x20) != 0 )
    WPP_SF_D(v10[2], 71, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180028c08  mov     rax, rsp
0x180028c0b  mov     [rax+8], rbx
0x180028c0f  mov     [rax+10h], rbp
0x180028c13  mov     [rax+18h], rsi
0x180028c17  mov     [rax+20h], rdi
0x180028c1b  push    r13
0x180028c1d  push    r14
0x180028c1f  push    r15
0x180028c21  sub     rsp, 40h
0x180028c25  xor     ebx, ebx
0x180028c27  mov     r14, r9
0x180028c2a  and     [rax-20h], rbx
0x180028c2e  mov     ebp, r8d
0x180028c31  and     [rax-28h], rbx
0x180028c35  mov     r15, rdx
0x180028c38  mov     esi, ecx
0x180028c3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c41  lea     r13, WPP_GLOBAL_Control
0x180028c48  cmp     rcx, r13
0x180028c4b  jz      short loc_180028C69
0x180028c4d  test    byte ptr [rcx+1Ch], 20h
0x180028c51  jz      short loc_180028C69
0x180028c53  mov     rcx, [rcx+10h]
0x180028c57  lea     edx, [rbx+44h]
0x180028c5a  mov     r9d, esi
0x180028c5d  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180028c64  call    WPP_SF_D
0x180028c69  mov     rcx, cs:KRB5_Module
0x180028c70  lea     rdx, [rsp+58h+var_20]
0x180028c75  and     [rsp+58h+var_38], rbx
0x180028c7a  xor     r9d, r9d
0x180028c7d  xor     r8d, r8d
0x180028c80  call    cs:__imp_ASN1_CreateDecoder
0x180028c87  nop     dword ptr [rax+rax+00h]
0x180028c8c  mov     edi, eax
0x180028c8e  test    eax, eax
0x180028c90  jz      short loc_180028CCD
0x180028c92  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c99  cmp     rcx, r13
0x180028c9c  jz      short loc_180028CC4
0x180028c9e  test    byte ptr [rcx+1Ch], 1
0x180028ca2  jz      short loc_180028CC4
0x180028ca4  mov     edx, 45h ; 'E'
0x180028ca9  mov     [rsp+58h+var_30], 508h
0x180028cb1  mov     rcx, [rcx+10h]
0x180028cb5  mov     r9d, edi
0x180028cb8  call    WPP_SF_dsd
0x180028cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180028cc4  mov     rdx, [rsp+58h+var_28]
0x180028cc9  mov     ebx, edi
0x180028ccb  jmp     short loc_180028D32
0x180028ccd  mov     rcx, [rsp+58h+var_20]
0x180028cd2  lea     rdx, [rsp+58h+var_28]
0x180028cd7  mov     [rsp+58h+var_30], ebp
0x180028cdb  mov     r9d, 8
0x180028ce1  mov     r8d, esi
0x180028ce4  mov     [rsp+58h+var_38], r15
0x180028ce9  call    cs:__imp_ASN1_Decode
0x180028cf0  nop     dword ptr [rax+rax+00h]
0x180028cf5  mov     edi, eax
0x180028cf7  test    eax, eax
0x180028cf9  jz      short loc_180028D1C
0x180028cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d02  cmp     rcx, r13
0x180028d05  jz      short loc_180028CC4
0x180028d07  test    byte ptr [rcx+1Ch], 1
0x180028d0b  jz      short loc_180028CC4
0x180028d0d  mov     edx, 46h ; 'F'
0x180028d12  mov     [rsp+58h+var_30], 518h
0x180028d1a  jmp     short loc_180028CB1
0x180028d1c  mov     rax, [rsp+58h+var_28]
0x180028d21  xor     edx, edx
0x180028d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d2a  mov     [r14], rax
0x180028d2d  mov     [rsp+58h+var_28], rdx
0x180028d32  test    rdx, rdx
0x180028d35  jz      short loc_180028D52
0x180028d37  mov     rcx, [rsp+58h+var_20]
0x180028d3c  mov     r8d, esi
0x180028d3f  call    cs:__imp_ASN1_FreeDecoded
0x180028d46  nop     dword ptr [rax+rax+00h]
0x180028d4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d52  mov     rax, [rsp+58h+var_20]
0x180028d57  test    rax, rax
0x180028d5a  jz      short loc_180028D72
0x180028d5c  mov     rcx, rax
0x180028d5f  call    cs:__imp_ASN1_CloseDecoder
0x180028d66  nop     dword ptr [rax+rax+00h]
0x180028d6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d72  cmp     rcx, r13
0x180028d75  jz      short loc_180028D95
0x180028d77  test    byte ptr [rcx+1Ch], 20h
0x180028d7b  jz      short loc_180028D95
0x180028d7d  mov     rcx, [rcx+10h]
0x180028d81  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180028d88  mov     edx, 47h ; 'G'
0x180028d8d  mov     r9d, ebx
0x180028d90  call    WPP_SF_D
0x180028d95  mov     rbp, [rsp+58h+arg_8]
0x180028d9a  mov     eax, ebx
0x180028d9c  mov     rbx, [rsp+58h+arg_0]
0x180028da1  mov     rsi, [rsp+58h+arg_10]
0x180028da6  mov     rdi, [rsp+58h+arg_18]
0x180028dab  add     rsp, 40h
0x180028daf  pop     r15
0x180028db1  pop     r14
0x180028db3  pop     r13
0x180028db5  retn
```
