# UstVarLib::CscVarUtil_ConvertMULTISZToVariant(ushort const *,ulong,tagVARIANT *)

- ea: `0x180029c1c`
- end: `0x180029df8`
- name: `?CscVarUtil_ConvertMULTISZToVariant@UstVarLib@@YAJPEBGKPEAUtagVARIANT@@@Z`
- size: `476`
- prototype: `__int64 __fastcall(OLECHAR *psz, const unsigned __int16 *, unsigned int, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a5a0`

## callees

- `0x18000f5a4`
- `0x180014068`
- `0x180029c1c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180029cdb`
- `OLEAUT32!__imp_SysAllocString` at `0x180029cdb`
- `OLEAUT32!__imp_SysFreeString` at `0x180029d14`
- `OLEAUT32!__imp_SysFreeString` at `0x180029d14`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180029d7a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180029d7a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180029d03`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180029d03`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180029cae`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180029cae`

## pseudocode

```c
__int64 __fastcall UstVarLib::CscVarUtil_ConvertMULTISZToVariant(
        OLECHAR *psz,
        const unsigned __int16 *a2,
        __int64 a3,
        struct tagVARIANT *a4)
{
  const OLECHAR *v5; // rbx
  OLECHAR *v6; // rsi
  HRESULT v7; // edi
  signed int v8; // r8d
  OLECHAR *v9; // rdx
  OLECHAR *v10; // rcx
  signed int v11; // eax
  SAFEARRAY *Vector; // r14
  LONG v13; // r13d
  BSTR v14; // rax
  OLECHAR *v15; // r15
  LONG rgIndices; // [rsp+78h] [rbp+10h] BYREF

  v5 = psz;
  if ( (unsigned int)a2 < 4 || (v6 = &psz[(unsigned int)a2 - 1], *(_DWORD *)(v6 - 1)) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_000984ba6c40394f4476e2ecf531d2d4_Traceguids);
    return (unsigned int)-2147024883;
  }
  else
  {
    v7 = 0;
    v8 = 0;
    v9 = psz;
    if ( psz >= v6 )
      goto LABEL_32;
    do
    {
      for ( ; v9; ++v9 )
      {
        if ( !*v9 )
          break;
        if ( v9 >= v6 )
          break;
      }
      v10 = v9;
      v11 = v8 + 1;
      ++v9;
      if ( v10 >= v6 )
        v11 = v8;
      v8 = v11;
    }
    while ( v9 < v6 );
    if ( v11 <= 0 )
    {
LABEL_32:
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_000984ba6c40394f4476e2ecf531d2d4_Traceguids);
    }
    else
    {
      Vector = SafeArrayCreateVector(8u, 0, v11);
      if ( Vector )
      {
        v13 = 0;
        while ( v7 >= 0 )
        {
          v14 = SysAllocString(v5);
          v15 = v14;
          if ( v14 )
          {
            rgIndices = v13++;
            v7 = SafeArrayPutElement(Vector, &rgIndices, v14);
            if ( v7 >= 0 )
            {
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                WPP_SF_S(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  11,
                  WPP_000984ba6c40394f4476e2ecf531d2d4_Traceguids,
                  v15);
              }
              while ( v5 < v6 && *v5 )
                ++v5;
              ++v5;
            }
            else
            {
              SysFreeString(v15);
            }
          }
          else
          {
            v7 = -2147024882;
          }
          if ( v5 >= v6 )
          {
            if ( v7 >= 0 )
            {
              *(_WORD *)a3 = 8200;
              *(_QWORD *)(a3 + 8) = Vector;
              return (unsigned int)v7;
            }
            break;
          }
        }
        SafeArrayDestroy(Vector);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180029c1c  push    rbx
0x180029c1e  push    rbp
0x180029c1f  push    rsi
0x180029c20  push    rdi
0x180029c21  push    r12
0x180029c23  push    r13
0x180029c25  push    r14
0x180029c27  push    r15
0x180029c29  sub     rsp, 28h
0x180029c2d  mov     r12, r8
0x180029c30  mov     rbx, rcx
0x180029c33  cmp     edx, 4
0x180029c36  jb      loc_180029DB2
0x180029c3c  mov     esi, edx
0x180029c3e  xor     r15d, r15d
0x180029c41  dec     rsi
0x180029c44  lea     rsi, [rcx+rsi*2]
0x180029c48  cmp     r15w, [rsi]
0x180029c4c  jnz     loc_180029DB2
0x180029c52  cmp     r15w, [rsi-2]
0x180029c57  jnz     loc_180029DB2
0x180029c5d  mov     edi, r15d
0x180029c60  mov     r8d, r15d
0x180029c63  mov     rdx, rcx
0x180029c66  cmp     rcx, rsi
0x180029c69  jnb     loc_180029D82
0x180029c6f  test    rdx, rdx
0x180029c72  jz      short loc_180029C85
0x180029c74  cmp     [rdx], r15w
0x180029c78  jz      short loc_180029C85
0x180029c7a  cmp     rdx, rsi
0x180029c7d  jnb     short loc_180029C85
0x180029c7f  add     rdx, 2
0x180029c83  jnz     short loc_180029C74
0x180029c85  mov     rcx, rdx
0x180029c88  lea     eax, [r8+1]
0x180029c8c  add     rdx, 2
0x180029c90  cmp     rcx, rsi
0x180029c93  cmovnb  eax, r8d
0x180029c97  mov     r8d, eax; cElements
0x180029c9a  cmp     rdx, rsi
0x180029c9d  jb      short loc_180029C6F
0x180029c9f  test    eax, eax
0x180029ca1  jle     loc_180029D82
0x180029ca7  mov     ecx, 8; vt
0x180029cac  xor     edx, edx; lLbound
0x180029cae  call    cs:__imp_SafeArrayCreateVector
0x180029cb4  mov     r14, rax
0x180029cb7  test    rax, rax
0x180029cba  jnz     short loc_180029CC6
0x180029cbc  mov     edi, 8007000Eh
0x180029cc1  jmp     loc_180029DE5
0x180029cc6  mov     r13d, r15d
0x180029cc9  lea     rbp, WPP_GLOBAL_Control
0x180029cd0  test    edi, edi
0x180029cd2  js      loc_180029D77
0x180029cd8  mov     rcx, rbx; psz
0x180029cdb  call    cs:__imp_SysAllocString
0x180029ce1  mov     r15, rax
0x180029ce4  test    rax, rax
0x180029ce7  jnz     short loc_180029CF0
0x180029ce9  mov     edi, 8007000Eh
0x180029cee  jmp     short loc_180029D5C
0x180029cf0  mov     [rsp+68h+rgIndices], r13d
0x180029cf5  lea     rdx, [rsp+68h+rgIndices]; rgIndices
0x180029cfa  mov     r8, r15; pv
0x180029cfd  mov     rcx, r14; psa
0x180029d00  inc     r13d
0x180029d03  call    cs:__imp_SafeArrayPutElement
0x180029d09  mov     edi, eax
0x180029d0b  xor     eax, eax
0x180029d0d  test    edi, edi
0x180029d0f  jns     short loc_180029D1C
0x180029d11  mov     rcx, r15; bstrString
0x180029d14  call    cs:__imp_SysFreeString
0x180029d1a  jmp     short loc_180029D5C
0x180029d1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d23  cmp     rcx, rbp
0x180029d26  jz      short loc_180029D53
0x180029d28  test    byte ptr [rcx+1Ch], 1
0x180029d2c  jz      short loc_180029D53
0x180029d2e  mov     rcx, [rcx+10h]
0x180029d32  lea     r8, WPP_000984ba6c40394f4476e2ecf531d2d4_Traceguids
0x180029d39  mov     edx, 0Bh
0x180029d3e  mov     r9, r15
0x180029d41  call    WPP_SF_S
0x180029d46  xor     eax, eax
0x180029d48  jmp     short loc_180029D53
0x180029d4a  cmp     [rbx], ax
0x180029d4d  jz      short loc_180029D58
0x180029d4f  add     rbx, 2
0x180029d53  cmp     rbx, rsi
0x180029d56  jb      short loc_180029D4A
0x180029d58  add     rbx, 2
0x180029d5c  cmp     rbx, rsi
0x180029d5f  jb      loc_180029CD0
0x180029d65  test    edi, edi
0x180029d67  js      short loc_180029D77
0x180029d69  mov     word ptr [r12], 2008h
0x180029d70  mov     [r12+8], r14
0x180029d75  jmp     short loc_180029DE5
0x180029d77  mov     rcx, r14; psa
0x180029d7a  call    cs:__imp_SafeArrayDestroy
0x180029d80  jmp     short loc_180029DE5
0x180029d82  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d89  lea     rbp, WPP_GLOBAL_Control
0x180029d90  cmp     rcx, rbp
0x180029d93  jz      short loc_180029DE5
0x180029d95  test    byte ptr [rcx+1Ch], 2
0x180029d99  jz      short loc_180029DE5
0x180029d9b  mov     rcx, [rcx+10h]
0x180029d9f  lea     r8, WPP_000984ba6c40394f4476e2ecf531d2d4_Traceguids
0x180029da6  mov     edx, 0Ch
0x180029dab  call    WPP_SF_
0x180029db0  jmp     short loc_180029DE5
0x180029db2  mov     rcx, cs:WPP_GLOBAL_Control
0x180029db9  lea     rbp, WPP_GLOBAL_Control
0x180029dc0  cmp     rcx, rbp
0x180029dc3  jz      short loc_180029DE0
0x180029dc5  test    byte ptr [rcx+1Ch], 1
0x180029dc9  jz      short loc_180029DE0
0x180029dcb  mov     rcx, [rcx+10h]
0x180029dcf  lea     r8, WPP_000984ba6c40394f4476e2ecf531d2d4_Traceguids
0x180029dd6  mov     edx, 0Ah
0x180029ddb  call    WPP_SF_
0x180029de0  mov     edi, 8007000Dh
0x180029de5  mov     eax, edi
0x180029de7  add     rsp, 28h
0x180029deb  pop     r15
0x180029ded  pop     r14
0x180029def  pop     r13
0x180029df1  pop     r12
0x180029df3  pop     rdi
0x180029df4  pop     rsi
0x180029df5  pop     rbp
0x180029df6  pop     rbx
0x180029df7  retn
```
