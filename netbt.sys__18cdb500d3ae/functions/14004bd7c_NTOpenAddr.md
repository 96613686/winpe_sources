# NTOpenAddr

- ea: `0x14004bd7c`
- end: `0x14004bf0d`
- name: `NTOpenAddr`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14004b7a0`

## callees

- `0x1400031bc`
- `0x1400400a4`
- `0x140040428`
- `0x14004bd7c`

## pseudocode

```c
__int64 __fastcall NTOpenAddr(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  unsigned int v6; // ebx
  __int64 v7; // r12
  unsigned int v8; // ebp
  unsigned __int16 *v9; // rsi
  int i; // r15d
  unsigned int v12; // ecx
  unsigned int v13; // eax
  int v14; // ecx
  bool v15; // cf
  unsigned int v16; // eax
  __int64 v17; // [rsp+30h] [rbp-68h] BYREF
  __int128 v18; // [rsp+38h] [rbp-60h]
  __int64 v19; // [rsp+48h] [rbp-50h]

  v3 = *(unsigned __int16 *)(a3 + 6);
  v19 = 0;
  v17 = 0;
  v6 = -1073741305;
  v18 = 0;
  if ( v3 >= 0x1A )
  {
    v7 = *(unsigned __int8 *)(a3 + 5);
    v8 = 4;
    v9 = (unsigned __int16 *)(v7 + a3 + 13);
    for ( i = 0; ; ++i )
    {
      if ( v3 < v8 )
        return v6;
      if ( i >= *(_DWORD *)(v7 + a3 + 9) )
        return v6;
      v12 = v8 + 4;
      if ( v3 < v8 + 4 )
        return v6;
      v13 = *v9;
      v8 = v12 + v13;
      if ( v3 < v12 + v13 )
        return v6;
      v14 = v9[1];
      if ( v14 == 17 )
      {
        v15 = v13 < 0x12;
      }
      else
      {
        if ( v14 != 22 )
          goto LABEL_19;
        v15 = v13 < 0x22;
      }
      if ( !v15 )
      {
        v16 = NbtOpenAddress(&v17, (__int64)v9, *(_DWORD *)(a1 + 488), a1, a2);
        v6 = v16;
        if ( v16 && (BYTE3(xmmword_140038420) & 2) != 0 )
          WPP_SF_d(1049, 13, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, v16);
        return v6;
      }
LABEL_19:
      if ( (xmmword_140038420 & 0x40) != 0 )
        WPP_SF_d(1030, 12, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, v9[1]);
      v9 = (unsigned __int16 *)((char *)v9 + *v9 + 4);
    }
  }
  if ( (xmmword_140038420 & 0x40) != 0 )
    WPP_SF_dq(1030, 10, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, v3, 26);
  if ( (BYTE3(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_dq(1054, 11, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, v3, 26);
  return v6;
}

```

## disassembly

```asm
0x14004bd7c  mov     rax, rsp
0x14004bd7f  mov     [rax+10h], rdx
0x14004bd83  push    rbx
0x14004bd84  push    rbp
0x14004bd85  push    rsi
0x14004bd86  push    rdi
0x14004bd87  push    r12
0x14004bd89  push    r13
0x14004bd8b  push    r14
0x14004bd8d  push    r15
0x14004bd8f  sub     rsp, 58h
0x14004bd93  movzx   edi, word ptr [r8+6]
0x14004bd98  mov     esi, 1Ah
0x14004bd9d  mov     qword ptr [rax-50h], 0
0x14004bda5  xorps   xmm0, xmm0
0x14004bda8  mov     qword ptr [rax-68h], 0
0x14004bdb0  mov     r14, r8
0x14004bdb3  mov     r13, rcx
0x14004bdb6  mov     ebx, 0C0000207h
0x14004bdbb  movdqu  xmmword ptr [rax-60h], xmm0
0x14004bdc0  cmp     edi, esi
0x14004bdc2  jb      loc_14004BE71
0x14004bdc8  movzx   r12d, byte ptr [r8+5]
0x14004bdcd  lea     ebp, [rsi-16h]
0x14004bdd0  lea     rsi, [r8+0Dh]
0x14004bdd4  add     rsi, r12
0x14004bdd7  xor     r15d, r15d
0x14004bdda  cmp     edi, ebp
0x14004bddc  jnb     short loc_14004BDF2
0x14004bdde  mov     eax, ebx
0x14004bde0  add     rsp, 58h
0x14004bde4  pop     r15
0x14004bde6  pop     r14
0x14004bde8  pop     r13
0x14004bdea  pop     r12
0x14004bdec  pop     rdi
0x14004bded  pop     rsi
0x14004bdee  pop     rbp
0x14004bdef  pop     rbx
0x14004bdf0  retn
0x14004bdf2  cmp     r15d, [r12+r14+9]
0x14004bdf7  jge     short loc_14004BDDE
0x14004bdf9  lea     ecx, [rbp+4]
0x14004bdfc  cmp     edi, ecx
0x14004bdfe  jb      short loc_14004BDDE
0x14004be00  movzx   eax, word ptr [rsi]
0x14004be03  lea     ebp, [rcx+rax]
0x14004be06  cmp     edi, ebp
0x14004be08  jb      short loc_14004BDDE
0x14004be0a  movzx   ecx, word ptr [rsi+2]
0x14004be0e  cmp     ecx, 11h
0x14004be11  jnz     loc_14004BEAA
0x14004be17  cmp     eax, 12h
0x14004be1a  jb      loc_14004BEAF
0x14004be20  mov     rax, [rsp+98h+arg_8]
0x14004be28  lea     rcx, [rsp+98h+var_68]
0x14004be2d  mov     r8d, [r13+1E8h]
0x14004be34  mov     r9, r13
0x14004be37  mov     rdx, rsi
0x14004be3a  mov     [rsp+98h+var_78], rax
0x14004be3f  call    NbtOpenAddress
0x14004be44  mov     ebx, eax
0x14004be46  test    eax, eax
0x14004be48  jz      short loc_14004BDDE
0x14004be4a  test    byte ptr cs:xmmword_140038420+3, 2
0x14004be51  jz      short loc_14004BDDE
0x14004be53  mov     edx, 0Dh
0x14004be58  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x14004be5f  mov     ecx, 419h
0x14004be64  mov     r9d, eax
0x14004be67  call    WPP_SF_d
0x14004be6c  jmp     loc_14004BDDE
0x14004be71  test    byte ptr cs:xmmword_140038420, 40h
0x14004be78  jnz     short loc_14004BECA
0x14004be7a  test    byte ptr cs:xmmword_140038420+3, 40h
0x14004be81  jz      loc_14004BDDE
0x14004be87  mov     edx, 0Bh
0x14004be8c  mov     [rsp+98h+var_78], rsi
0x14004be91  mov     ecx, 41Eh
0x14004be96  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x14004be9d  mov     r9d, edi
0x14004bea0  call    WPP_SF_dq
0x14004bea5  jmp     loc_14004BDDE
0x14004beaa  cmp     ecx, 16h
0x14004bead  jz      short loc_14004BEEA
0x14004beaf  test    byte ptr cs:xmmword_140038420, 40h
0x14004beb6  jnz     short loc_14004BEF2
0x14004beb8  movzx   eax, word ptr [rsi]
0x14004bebb  add     rsi, 4
0x14004bebf  add     rsi, rax
0x14004bec2  inc     r15d
0x14004bec5  jmp     loc_14004BDDA
0x14004beca  mov     edx, 0Ah
0x14004becf  mov     [rsp+98h+var_78], rsi
0x14004bed4  mov     ecx, 406h
0x14004bed9  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x14004bee0  mov     r9d, edi
0x14004bee3  call    WPP_SF_dq
0x14004bee8  jmp     short loc_14004BE7A
0x14004beea  cmp     eax, 22h ; '"'
0x14004beed  jmp     loc_14004BE1A
0x14004bef2  mov     r9d, ecx
0x14004bef5  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x14004befc  mov     ecx, 406h
0x14004bf01  mov     edx, 0Ch
0x14004bf06  call    WPP_SF_d
0x14004bf0b  jmp     short loc_14004BEB8
```
