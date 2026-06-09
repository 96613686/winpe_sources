# ReadNFAObjectsFromRegistry

- ea: `0x180039788`
- end: `0x180039ad8`
- name: `ReadNFAObjectsFromRegistry`
- size: `848`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180039c80`

## callees

- `0x180006f00`
- `0x180006f60`
- `0x18000e510`
- `0x180035608`
- `0x180039788`
- `0x18003ab84`
- `0x180042ab0`
- `0x180042cf8`
- `0x180042ef8`

## pseudocode

```c
__int64 __fastcall ReadNFAObjectsFromRegistry(
        HKEY a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        _QWORD *a6,
        _DWORD *a7,
        _QWORD *a8,
        _DWORD *a9,
        _QWORD *a10,
        _DWORD *a11)
{
  _QWORD *v11; // rsi
  __int64 v13; // rdi
  unsigned int v14; // eax
  unsigned int v15; // ebx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  void *v19; // r14
  unsigned int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  _QWORD *v24; // r12
  unsigned int v25; // eax
  __int64 v26; // rdi
  __int64 v27; // r15
  __int64 v28; // r14
  __int64 v29; // rcx
  void *v30; // rbx
  LPVOID v31; // rax
  LPVOID lpMem; // [rsp+30h] [rbp-20h] BYREF
  LPVOID v33; // [rsp+38h] [rbp-18h]
  __int64 v34; // [rsp+40h] [rbp-10h] BYREF
  __int64 v35; // [rsp+48h] [rbp-8h] BYREF
  SIZE_T v38; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v39; // [rsp+A8h] [rbp+58h]

  v39 = a4;
  v11 = 0;
  v34 = 0;
  v35 = 0;
  lpMem = 0;
  *a10 = 0;
  v38 = 0;
  *a9 = 0;
  *a8 = 0;
  *a11 = 0;
  *a6 = 0;
  *a7 = 0;
  if ( !a5 )
    return 0;
  v13 = a5;
  v14 = NsuSizeTMultiply(a5, 8, &v38);
  v15 = v14;
  if ( v14 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_43;
    v17 = 16;
    v18 = v14;
    goto LABEL_7;
  }
  v33 = IpsecAllocMem(v38);
  v19 = v33;
  if ( !v33 )
  {
    v18 = 14;
    v15 = 14;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_43;
    v17 = 17;
LABEL_7:
    WPP_SF_d(v16[2], v17, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, v18);
LABEL_43:
    LODWORD(v27) = 0;
    LODWORD(v28) = 0;
    LODWORD(v26) = 0;
    v31 = 0;
    v24 = 0;
    goto LABEL_44;
  }
  v20 = NsuSizeTMultiply(v13, 8, &v38);
  v15 = v20;
  if ( v20 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_42;
    v22 = 18;
    v23 = v20;
    goto LABEL_16;
  }
  v24 = IpsecAllocMem(v38);
  if ( !v24 )
  {
    v23 = 14;
    v15 = 14;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_42;
    v22 = 19;
LABEL_16:
    WPP_SF_d(v21[2], v22, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, v23);
LABEL_42:
    FreeIpsecNFAObjects(v19);
    goto LABEL_43;
  }
  v11 = IpsecAllocMem(v38);
  if ( !v11 )
  {
    v15 = 14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, 14);
LABEL_41:
    FreeNFAReferences(v24, 0);
    v11 = 0;
    goto LABEL_42;
  }
  v25 = 0;
  v26 = 0;
  v27 = 0;
  LODWORD(v38) = 0;
  v28 = 0;
  if ( !a5 )
    goto LABEL_37;
  do
  {
    if ( !(unsigned int)UnMarshallRegistryNFAObject(
                          a1,
                          a2,
                          *(unsigned __int16 **)(v39 + 8LL * v25),
                          &v34,
                          (unsigned __int16 **)&v35,
                          (unsigned __int16 **)&lpMem) )
    {
      v29 = v35;
      *((_QWORD *)v33 + v26) = v34;
      if ( v29 )
      {
        v24[v27] = v29;
        v27 = (unsigned int)(v27 + 1);
      }
      v30 = lpMem;
      if ( lpMem )
      {
        if ( (unsigned int)IsStringInArray(v11, lpMem, (unsigned int)v28) )
        {
          IpsecFreeMem(v30);
          lpMem = 0;
        }
        else
        {
          v11[v28] = v30;
          v28 = (unsigned int)(v28 + 1);
        }
      }
      v26 = (unsigned int)(v26 + 1);
    }
    v25 = v38 + 1;
    LODWORD(v38) = v25;
  }
  while ( v25 < a5 );
  if ( !(_DWORD)v26 )
  {
LABEL_37:
    v15 = 13;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, 13);
    FreeNFAReferences(v11, 0);
    v19 = v33;
    goto LABEL_41;
  }
  v31 = v33;
  v15 = 0;
LABEL_44:
  *a10 = v11;
  *a8 = v24;
  *a6 = v31;
  *a7 = v26;
  *a11 = v28;
  *a9 = v27;
  return v15;
}

```

## disassembly

```asm
0x180039788  mov     rax, rsp
0x18003978b  mov     [rax+20h], r9
0x18003978f  mov     [rax+18h], r8
0x180039793  mov     [rax+10h], rdx
0x180039797  mov     [rax+8], rcx
0x18003979b  push    rbp
0x18003979c  push    rbx
0x18003979d  push    rsi
0x18003979e  push    rdi
0x18003979f  push    r12
0x1800397a1  push    r14
0x1800397a3  push    r15
0x1800397a5  mov     rbp, rsp
0x1800397a8  sub     rsp, 50h
0x1800397ac  mov     rax, [rbp+arg_48]
0x1800397b3  xor     esi, esi
0x1800397b5  mov     [rbp+var_10], rsi
0x1800397b9  mov     [rbp+var_8], rsi
0x1800397bd  mov     [rbp+lpMem], rsi
0x1800397c1  mov     [rax], rsi
0x1800397c4  mov     rax, [rbp+arg_40]
0x1800397cb  mov     [rbp+arg_10], rsi
0x1800397cf  mov     [rax], esi
0x1800397d1  mov     rax, [rbp+arg_38]
0x1800397d5  mov     [rax], rsi
0x1800397d8  mov     rax, [rbp+arg_50]
0x1800397df  mov     [rax], esi
0x1800397e1  mov     rax, [rbp+arg_28]
0x1800397e5  mov     [rax], rsi
0x1800397e8  mov     rax, [rbp+arg_30]
0x1800397ec  mov     [rax], esi
0x1800397ee  cmp     [rbp+arg_20], esi
0x1800397f1  jnz     short loc_1800397FA
0x1800397f3  xor     eax, eax
0x1800397f5  jmp     loc_180039AC9
0x1800397fa  mov     edi, [rbp+arg_20]
0x1800397fd  lea     r8, [rbp+arg_10]
0x180039801  mov     r15d, 8
0x180039807  mov     ecx, edi
0x180039809  mov     edx, r15d
0x18003980c  call    NsuSizeTMultiply
0x180039811  mov     ebx, eax
0x180039813  test    eax, eax
0x180039815  jz      short loc_180039854
0x180039817  mov     rcx, cs:WPP_GLOBAL_Control
0x18003981e  lea     rdx, WPP_GLOBAL_Control
0x180039825  cmp     rcx, rdx
0x180039828  jz      loc_180039A87
0x18003982e  test    byte ptr [rcx+1Ch], 10h
0x180039832  jz      loc_180039A87
0x180039838  lea     edx, [r15+8]
0x18003983c  mov     r9d, eax
0x18003983f  mov     rcx, [rcx+10h]
0x180039843  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x18003984a  call    WPP_SF_d
0x18003984f  jmp     loc_180039A87
0x180039854  mov     rcx, [rbp+arg_10]
0x180039858  call    IpsecAllocMem
0x18003985d  mov     [rbp+var_18], rax
0x180039861  mov     r14, rax
0x180039864  test    rax, rax
0x180039867  jnz     short loc_180039896
0x180039869  lea     r9d, [rax+0Eh]
0x18003986d  mov     ebx, r9d
0x180039870  mov     rcx, cs:WPP_GLOBAL_Control
0x180039877  lea     rdx, WPP_GLOBAL_Control
0x18003987e  cmp     rcx, rdx
0x180039881  jz      loc_180039A87
0x180039887  test    byte ptr [rcx+1Ch], 10h
0x18003988b  jz      loc_180039A87
0x180039891  lea     edx, [rax+11h]
0x180039894  jmp     short loc_18003983F
0x180039896  lea     r8, [rbp+arg_10]
0x18003989a  mov     rdx, r15
0x18003989d  mov     rcx, rdi
0x1800398a0  call    NsuSizeTMultiply
0x1800398a5  mov     ebx, eax
0x1800398a7  test    eax, eax
0x1800398a9  jz      short loc_1800398E9
0x1800398ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800398b2  lea     rdx, WPP_GLOBAL_Control
0x1800398b9  cmp     rcx, rdx
0x1800398bc  jz      loc_180039A7D
0x1800398c2  test    byte ptr [rcx+1Ch], 10h
0x1800398c6  jz      loc_180039A7D
0x1800398cc  mov     edx, 12h
0x1800398d1  mov     r9d, eax
0x1800398d4  mov     rcx, [rcx+10h]
0x1800398d8  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x1800398df  call    WPP_SF_d
0x1800398e4  jmp     loc_180039A7D
0x1800398e9  mov     rcx, [rbp+arg_10]
0x1800398ed  call    IpsecAllocMem
0x1800398f2  mov     r12, rax
0x1800398f5  test    rax, rax
0x1800398f8  jnz     short loc_180039927
0x1800398fa  lea     r9d, [rax+0Eh]
0x1800398fe  mov     ebx, r9d
0x180039901  mov     rcx, cs:WPP_GLOBAL_Control
0x180039908  lea     rdx, WPP_GLOBAL_Control
0x18003990f  cmp     rcx, rdx
0x180039912  jz      loc_180039A7D
0x180039918  test    byte ptr [rcx+1Ch], 10h
0x18003991c  jz      loc_180039A7D
0x180039922  lea     edx, [rax+13h]
0x180039925  jmp     short loc_1800398D4
0x180039927  mov     rcx, [rbp+arg_10]
0x18003992b  call    IpsecAllocMem
0x180039930  mov     rsi, rax
0x180039933  test    rax, rax
0x180039936  jnz     short loc_180039978
0x180039938  lea     r9d, [rax+0Eh]
0x18003993c  mov     ebx, r9d
0x18003993f  mov     rcx, cs:WPP_GLOBAL_Control
0x180039946  lea     rdx, WPP_GLOBAL_Control
0x18003994d  cmp     rcx, rdx
0x180039950  jz      loc_180039A71
0x180039956  test    byte ptr [rcx+1Ch], 10h
0x18003995a  jz      loc_180039A71
0x180039960  mov     rcx, [rcx+10h]
0x180039964  lea     edx, [rax+14h]
0x180039967  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x18003996e  call    WPP_SF_d
0x180039973  jmp     loc_180039A71
0x180039978  xor     eax, eax
0x18003997a  xor     edi, edi
0x18003997c  xor     r15d, r15d
0x18003997f  mov     dword ptr [rbp+arg_10], eax
0x180039982  xor     r14d, r14d
0x180039985  cmp     [rbp+arg_20], eax
0x180039988  jbe     loc_180039A2F
0x18003998e  mov     rdx, [rbp+arg_8]
0x180039992  lea     r9, [rbp+var_10]
0x180039996  mov     rcx, [rbp+hKey]; hKey
0x18003999a  mov     r8d, eax
0x18003999d  lea     rax, [rbp+lpMem]
0x1800399a1  mov     [rsp+50h+var_28], rax; __int64
0x1800399a6  lea     rax, [rbp+var_8]
0x1800399aa  mov     [rsp+50h+var_30], rax; __int64
0x1800399af  mov     rax, [rbp+arg_18]
0x1800399b3  mov     r8, [rax+r8*8]
0x1800399b7  call    UnMarshallRegistryNFAObject
0x1800399bc  test    eax, eax
0x1800399be  jnz     short loc_180039A12
0x1800399c0  mov     rdx, [rbp+var_18]
0x1800399c4  mov     rcx, [rbp+var_8]
0x1800399c8  mov     rax, [rbp+var_10]
0x1800399cc  mov     [rdx+rdi*8], rax
0x1800399d0  test    rcx, rcx
0x1800399d3  jz      short loc_1800399DC
0x1800399d5  mov     [r12+r15*8], rcx
0x1800399d9  inc     r15d
0x1800399dc  mov     rbx, [rbp+lpMem]
0x1800399e0  test    rbx, rbx
0x1800399e3  jz      short loc_180039A10
0x1800399e5  mov     r8d, r14d
0x1800399e8  mov     rdx, rbx
0x1800399eb  mov     rcx, rsi
0x1800399ee  call    IsStringInArray
0x1800399f3  test    eax, eax
0x1800399f5  jnz     short loc_180039A00
0x1800399f7  mov     [rsi+r14*8], rbx
0x1800399fb  inc     r14d
0x1800399fe  jmp     short loc_180039A10
0x180039a00  mov     rcx, rbx; lpMem
0x180039a03  call    IpsecFreeMem
0x180039a08  mov     [rbp+lpMem], 0
0x180039a10  inc     edi
0x180039a12  mov     eax, dword ptr [rbp+arg_10]
0x180039a15  inc     eax
0x180039a17  mov     dword ptr [rbp+arg_10], eax
0x180039a1a  cmp     eax, [rbp+arg_20]
0x180039a1d  jb      loc_18003998E
0x180039a23  test    edi, edi
0x180039a25  jz      short loc_180039A2F
0x180039a27  mov     rax, [rbp+var_18]
0x180039a2b  xor     ebx, ebx
0x180039a2d  jmp     short loc_180039A95
0x180039a2f  mov     ebx, 0Dh
0x180039a34  mov     rcx, cs:WPP_GLOBAL_Control
0x180039a3b  lea     rdx, WPP_GLOBAL_Control
0x180039a42  cmp     rcx, rdx
0x180039a45  jz      short loc_180039A63
0x180039a47  test    byte ptr [rcx+1Ch], 10h
0x180039a4b  jz      short loc_180039A63
0x180039a4d  mov     rcx, [rcx+10h]
0x180039a51  lea     edx, [rbx+8]
0x180039a54  mov     r9d, ebx
0x180039a57  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x180039a5e  call    WPP_SF_d
0x180039a63  xor     edx, edx
0x180039a65  mov     rcx, rsi; lpMem
0x180039a68  call    FreeNFAReferences
0x180039a6d  mov     r14, [rbp+var_18]
0x180039a71  xor     edx, edx
0x180039a73  mov     rcx, r12; lpMem
0x180039a76  call    FreeNFAReferences
0x180039a7b  xor     esi, esi
0x180039a7d  xor     edx, edx
0x180039a7f  mov     rcx, r14; lpMem
0x180039a82  call    FreeIpsecNFAObjects
0x180039a87  mov     r15d, esi
0x180039a8a  mov     r14d, esi
0x180039a8d  mov     edi, esi
0x180039a8f  mov     rax, rsi
0x180039a92  mov     r12, rsi
0x180039a95  mov     rcx, [rbp+arg_48]
0x180039a9c  mov     [rcx], rsi
0x180039a9f  mov     rcx, [rbp+arg_38]
0x180039aa3  mov     [rcx], r12
0x180039aa6  mov     rcx, [rbp+arg_28]
0x180039aaa  mov     [rcx], rax
0x180039aad  mov     rax, [rbp+arg_30]
0x180039ab1  mov     [rax], edi
0x180039ab3  mov     rax, [rbp+arg_50]
0x180039aba  mov     [rax], r14d
0x180039abd  mov     rax, [rbp+arg_40]
0x180039ac4  mov     [rax], r15d
0x180039ac7  mov     eax, ebx
0x180039ac9  add     rsp, 50h
0x180039acd  pop     r15
0x180039acf  pop     r14
0x180039ad1  pop     r12
0x180039ad3  pop     rdi
0x180039ad4  pop     rsi
0x180039ad5  pop     rbx
0x180039ad6  pop     rbp
0x180039ad7  retn
```
