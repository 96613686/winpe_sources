# KpsDerPack(ulong,void *,uchar * *,ulong *)

- ea: `0x1800289f8`
- end: `0x180028bff`
- name: `?KpsDerPack@@YAKKPEAXPEAPEAEPEAK@Z`
- size: `519`
- prototype: `__int64 __fastcall(__int64, void *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002a42c`

## callees

- `0x18001ae38`
- `0x180026a08`
- `0x1800289f8`
- `0x18002c458`
- `0x1800300f4`
- `0x18003012c`
- `0x180031002`

## import_xrefs

- `MSASN1!ASN1_CreateEncoder` at `0x180028a6e`
- `MSASN1!ASN1_CreateEncoder` at `0x180028a6e`
- `MSASN1!ASN1_FreeEncoded` at `0x180028b91`
- `MSASN1!ASN1_FreeEncoded` at `0x180028b91`
- `MSASN1!ASN1_Encode` at `0x180028acd`
- `MSASN1!ASN1_Encode` at `0x180028acd`
- `MSASN1!ASN1_CloseEncoder` at `0x180028ba7`
- `MSASN1!ASN1_CloseEncoder` at `0x180028ba7`

## string_xrefs

- `0x180028b34`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
__int64 __fastcall KpsDerPack(__int64 a1, void *a2, unsigned __int8 **a3, unsigned int *a4)
{
  unsigned int v4; // ebx
  char v7; // bp
  unsigned int Encoder; // edi
  int v10; // r8d
  int v11; // r8d
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // rdi
  __int64 v14; // rax
  _QWORD v16[5]; // [rsp+30h] [rbp-28h] BYREF

  v4 = 0;
  v16[0] = 0;
  v7 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, 40);
  Encoder = ASN1_CreateEncoder(KRB5_Module, v16, 0, 0);
  if ( Encoder )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, v10, Encoder, 0, 172);
LABEL_8:
    v4 = Encoder;
    goto LABEL_18;
  }
  Encoder = ASN1_Encode(v16[0], a2, 40);
  if ( Encoder )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, v11, Encoder, 0, 188);
    goto LABEL_8;
  }
  v7 = 1;
  v12 = (unsigned __int8 *)KpsAllocMem(*(unsigned int *)(v16[0] + 28LL));
  v13 = v12;
  if ( v12 )
  {
    memcpy_0(v12, *(const void **)(v16[0] + 16LL), *(unsigned int *)(v16[0] + 28LL));
    v14 = v16[0];
    *a3 = v13;
    *a4 = *(_DWORD *)(v14 + 28);
  }
  else
  {
    v4 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
        8,
        (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
        1224);
  }
LABEL_18:
  KpsFreeMem(0);
  if ( v7 )
    ASN1_FreeEncoded(v16[0], *(_QWORD *)(v16[0] + 16LL));
  if ( v16[0] )
    ASN1_CloseEncoder();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800289f8  mov     rax, rsp
0x1800289fb  mov     [rax+8], rbx
0x1800289ff  mov     [rax+10h], rbp
0x180028a03  mov     [rax+18h], rsi
0x180028a07  mov     [rax+20h], rdi
0x180028a0b  push    r13
0x180028a0d  push    r14
0x180028a0f  push    r15
0x180028a11  sub     rsp, 40h
0x180028a15  xor     ebx, ebx
0x180028a17  mov     r14, r9
0x180028a1a  and     [rax-28h], rbx
0x180028a1e  mov     r15, r8
0x180028a21  xor     bpl, bpl
0x180028a24  mov     rsi, rdx
0x180028a27  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a2e  lea     r13, WPP_GLOBAL_Control
0x180028a35  cmp     rcx, r13
0x180028a38  jz      short loc_180028A57
0x180028a3a  test    byte ptr [rcx+1Ch], 20h
0x180028a3e  jz      short loc_180028A57
0x180028a40  mov     rcx, [rcx+10h]
0x180028a44  lea     edx, [rbx+3Fh]
0x180028a47  lea     r9d, [rbx+28h]
0x180028a4b  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180028a52  call    WPP_SF_D
0x180028a57  mov     rcx, cs:KRB5_Module
0x180028a5e  lea     rdx, [rsp+58h+var_28]
0x180028a63  and     [rsp+58h+var_38], rbx
0x180028a68  xor     r9d, r9d
0x180028a6b  xor     r8d, r8d
0x180028a6e  call    cs:__imp_ASN1_CreateEncoder
0x180028a75  nop     dword ptr [rax+rax+00h]
0x180028a7a  mov     edi, eax
0x180028a7c  test    eax, eax
0x180028a7e  jz      short loc_180028AB2
0x180028a80  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a87  cmp     rcx, r13
0x180028a8a  jz      short loc_180028AAB
0x180028a8c  test    byte ptr [rcx+1Ch], 1
0x180028a90  jz      short loc_180028AAB
0x180028a92  mov     edx, 40h ; '@'
0x180028a97  mov     [rsp+58h+var_30], 4ACh
0x180028a9f  mov     rcx, [rcx+10h]
0x180028aa3  mov     r9d, edi
0x180028aa6  call    WPP_SF_dsd
0x180028aab  mov     ebx, edi
0x180028aad  jmp     loc_180028B7C
0x180028ab2  and     [rsp+58h+var_30], ebx
0x180028ab6  mov     r9d, 10h
0x180028abc  mov     rcx, [rsp+58h+var_28]
0x180028ac1  mov     rdx, rsi
0x180028ac4  and     [rsp+58h+var_38], rbx
0x180028ac9  lea     r8d, [r9+18h]
0x180028acd  call    cs:__imp_ASN1_Encode
0x180028ad4  nop     dword ptr [rax+rax+00h]
0x180028ad9  mov     edi, eax
0x180028adb  test    eax, eax
0x180028add  jz      short loc_180028B00
0x180028adf  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ae6  cmp     rcx, r13
0x180028ae9  jz      short loc_180028AAB
0x180028aeb  test    byte ptr [rcx+1Ch], 1
0x180028aef  jz      short loc_180028AAB
0x180028af1  mov     edx, 41h ; 'A'
0x180028af6  mov     [rsp+58h+var_30], 4BCh
0x180028afe  jmp     short loc_180028A9F
0x180028b00  mov     rax, [rsp+58h+var_28]
0x180028b05  mov     bpl, 1
0x180028b08  mov     ecx, [rax+1Ch]; unsigned __int64
0x180028b0b  call    ?KpsAllocMem@@YAPEAX_K@Z; KpsAllocMem(unsigned __int64)
0x180028b10  mov     rdi, rax
0x180028b13  test    rax, rax
0x180028b16  jnz     short loc_180028B59
0x180028b18  lea     ebx, [rax+8]
0x180028b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b22  cmp     rcx, r13
0x180028b25  jz      short loc_180028B7C
0x180028b27  test    [rcx+1Ch], bpl
0x180028b2b  jz      short loc_180028B7C
0x180028b2d  mov     rcx, [rcx+10h]
0x180028b31  lea     edx, [rax+42h]
0x180028b34  lea     rax, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x180028b3b  mov     [rsp+58h+var_30], 4C8h
0x180028b43  mov     r9d, ebx
0x180028b46  mov     [rsp+58h+var_38], rax
0x180028b4b  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180028b52  call    WPP_SF_Dsd
0x180028b57  jmp     short loc_180028B7C
0x180028b59  mov     rdx, [rsp+58h+var_28]
0x180028b5e  mov     rcx, rdi; void *
0x180028b61  mov     r8d, [rdx+1Ch]; Size
0x180028b65  mov     rdx, [rdx+10h]; Src
0x180028b69  call    memcpy_0
0x180028b6e  mov     rax, [rsp+58h+var_28]
0x180028b73  mov     [r15], rdi
0x180028b76  mov     ecx, [rax+1Ch]
0x180028b79  mov     [r14], ecx
0x180028b7c  xor     ecx, ecx; lpMem
0x180028b7e  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x180028b83  test    bpl, bpl
0x180028b86  jz      short loc_180028B9D
0x180028b88  mov     rcx, [rsp+58h+var_28]
0x180028b8d  mov     rdx, [rcx+10h]
0x180028b91  call    cs:__imp_ASN1_FreeEncoded
0x180028b98  nop     dword ptr [rax+rax+00h]
0x180028b9d  mov     rcx, [rsp+58h+var_28]
0x180028ba2  test    rcx, rcx
0x180028ba5  jz      short loc_180028BB3
0x180028ba7  call    cs:__imp_ASN1_CloseEncoder
0x180028bae  nop     dword ptr [rax+rax+00h]
0x180028bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180028bba  cmp     rcx, r13
0x180028bbd  jz      short loc_180028BDD
0x180028bbf  test    byte ptr [rcx+1Ch], 20h
0x180028bc3  jz      short loc_180028BDD
0x180028bc5  mov     rcx, [rcx+10h]
0x180028bc9  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180028bd0  mov     edx, 43h ; 'C'
0x180028bd5  mov     r9d, ebx
0x180028bd8  call    WPP_SF_D
0x180028bdd  mov     rbp, [rsp+58h+arg_8]
0x180028be2  mov     eax, ebx
0x180028be4  mov     rbx, [rsp+58h+arg_0]
0x180028be9  mov     rsi, [rsp+58h+arg_10]
0x180028bee  mov     rdi, [rsp+58h+arg_18]
0x180028bf3  add     rsp, 40h
0x180028bf7  pop     r15
0x180028bf9  pop     r14
0x180028bfb  pop     r13
0x180028bfd  retn
```
