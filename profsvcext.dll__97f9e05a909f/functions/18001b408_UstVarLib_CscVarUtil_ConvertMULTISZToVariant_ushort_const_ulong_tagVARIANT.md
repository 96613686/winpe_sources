# UstVarLib::CscVarUtil_ConvertMULTISZToVariant(ushort const *,ulong,tagVARIANT *)

- ea: `0x18001b408`
- end: `0x18001b5e4`
- name: `?CscVarUtil_ConvertMULTISZToVariant@UstVarLib@@YAJPEBGKPEAUtagVARIANT@@@Z`
- size: `476`
- prototype: `__int64 __fastcall(OLECHAR *psz, const unsigned __int16 *, __int64, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800025b0`

## callees

- `0x18001afa0`
- `0x18001b008`
- `0x18001b408`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001b4c7`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b4c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b500`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b500`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001b566`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001b566`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18001b4ef`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18001b4ef`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18001b49a`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18001b49a`

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
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_000984ba6c40394f4476e2ecf531d2d4_Traceguids, a4);
    }
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
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_000984ba6c40394f4476e2ecf531d2d4_Traceguids, a4);
      }
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
              if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_000984ba6c40394f4476e2ecf531d2d4_Traceguids, v15);
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
0x18001b408  push    rbx
0x18001b40a  push    rbp
0x18001b40b  push    rsi
0x18001b40c  push    rdi
0x18001b40d  push    r12
0x18001b40f  push    r13
0x18001b411  push    r14
0x18001b413  push    r15
0x18001b415  sub     rsp, 28h
0x18001b419  mov     r12, r8
0x18001b41c  mov     rbx, rcx
0x18001b41f  cmp     edx, 4
0x18001b422  jb      loc_18001B59E
0x18001b428  mov     esi, edx
0x18001b42a  xor     r15d, r15d
0x18001b42d  dec     rsi
0x18001b430  lea     rsi, [rcx+rsi*2]
0x18001b434  cmp     r15w, [rsi]
0x18001b438  jnz     loc_18001B59E
0x18001b43e  cmp     r15w, [rsi-2]
0x18001b443  jnz     loc_18001B59E
0x18001b449  mov     edi, r15d
0x18001b44c  mov     r8d, r15d
0x18001b44f  mov     rdx, rcx
0x18001b452  cmp     rcx, rsi
0x18001b455  jnb     loc_18001B56E
0x18001b45b  test    rdx, rdx
0x18001b45e  jz      short loc_18001B471
0x18001b460  cmp     [rdx], r15w
0x18001b464  jz      short loc_18001B471
0x18001b466  cmp     rdx, rsi
0x18001b469  jnb     short loc_18001B471
0x18001b46b  add     rdx, 2
0x18001b46f  jnz     short loc_18001B460
0x18001b471  mov     rcx, rdx
0x18001b474  lea     eax, [r8+1]
0x18001b478  add     rdx, 2
0x18001b47c  cmp     rcx, rsi
0x18001b47f  cmovnb  eax, r8d
0x18001b483  mov     r8d, eax; cElements
0x18001b486  cmp     rdx, rsi
0x18001b489  jb      short loc_18001B45B
0x18001b48b  test    eax, eax
0x18001b48d  jle     loc_18001B56E
0x18001b493  mov     ecx, 8; vt
0x18001b498  xor     edx, edx; lLbound
0x18001b49a  call    cs:__imp_SafeArrayCreateVector
0x18001b4a0  mov     r14, rax
0x18001b4a3  test    rax, rax
0x18001b4a6  jnz     short loc_18001B4B2
0x18001b4a8  mov     edi, 8007000Eh
0x18001b4ad  jmp     loc_18001B5D1
0x18001b4b2  mov     r13d, r15d
0x18001b4b5  lea     rbp, WPP_GLOBAL_Control
0x18001b4bc  test    edi, edi
0x18001b4be  js      loc_18001B563
0x18001b4c4  mov     rcx, rbx; psz
0x18001b4c7  call    cs:__imp_SysAllocString
0x18001b4cd  mov     r15, rax
0x18001b4d0  test    rax, rax
0x18001b4d3  jnz     short loc_18001B4DC
0x18001b4d5  mov     edi, 8007000Eh
0x18001b4da  jmp     short loc_18001B548
0x18001b4dc  mov     [rsp+68h+rgIndices], r13d
0x18001b4e1  lea     rdx, [rsp+68h+rgIndices]; rgIndices
0x18001b4e6  mov     r8, r15; pv
0x18001b4e9  mov     rcx, r14; psa
0x18001b4ec  inc     r13d
0x18001b4ef  call    cs:__imp_SafeArrayPutElement
0x18001b4f5  mov     edi, eax
0x18001b4f7  xor     eax, eax
0x18001b4f9  test    edi, edi
0x18001b4fb  jns     short loc_18001B508
0x18001b4fd  mov     rcx, r15; bstrString
0x18001b500  call    cs:__imp_SysFreeString
0x18001b506  jmp     short loc_18001B548
0x18001b508  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b50f  cmp     rcx, rbp
0x18001b512  jz      short loc_18001B53F
0x18001b514  test    byte ptr [rcx+1Ch], 1
0x18001b518  jz      short loc_18001B53F
0x18001b51a  mov     rcx, [rcx+10h]
0x18001b51e  lea     r8, WPP_000984ba6c40394f4476e2ecf531d2d4_Traceguids
0x18001b525  mov     edx, 0Bh
0x18001b52a  mov     r9, r15
0x18001b52d  call    WPP_SF_S
0x18001b532  xor     eax, eax
0x18001b534  jmp     short loc_18001B53F
0x18001b536  cmp     [rbx], ax
0x18001b539  jz      short loc_18001B544
0x18001b53b  add     rbx, 2
0x18001b53f  cmp     rbx, rsi
0x18001b542  jb      short loc_18001B536
0x18001b544  add     rbx, 2
0x18001b548  cmp     rbx, rsi
0x18001b54b  jb      loc_18001B4BC
0x18001b551  test    edi, edi
0x18001b553  js      short loc_18001B563
0x18001b555  mov     word ptr [r12], 2008h
0x18001b55c  mov     [r12+8], r14
0x18001b561  jmp     short loc_18001B5D1
0x18001b563  mov     rcx, r14; psa
0x18001b566  call    cs:__imp_SafeArrayDestroy
0x18001b56c  jmp     short loc_18001B5D1
0x18001b56e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b575  lea     rbp, WPP_GLOBAL_Control
0x18001b57c  cmp     rcx, rbp
0x18001b57f  jz      short loc_18001B5D1
0x18001b581  test    byte ptr [rcx+1Ch], 2
0x18001b585  jz      short loc_18001B5D1
0x18001b587  mov     rcx, [rcx+10h]
0x18001b58b  lea     r8, WPP_000984ba6c40394f4476e2ecf531d2d4_Traceguids
0x18001b592  mov     edx, 0Ch
0x18001b597  call    WPP_SF_
0x18001b59c  jmp     short loc_18001B5D1
0x18001b59e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5a5  lea     rbp, WPP_GLOBAL_Control
0x18001b5ac  cmp     rcx, rbp
0x18001b5af  jz      short loc_18001B5CC
0x18001b5b1  test    byte ptr [rcx+1Ch], 1
0x18001b5b5  jz      short loc_18001B5CC
0x18001b5b7  mov     rcx, [rcx+10h]
0x18001b5bb  lea     r8, WPP_000984ba6c40394f4476e2ecf531d2d4_Traceguids
0x18001b5c2  mov     edx, 0Ah
0x18001b5c7  call    WPP_SF_
0x18001b5cc  mov     edi, 8007000Dh
0x18001b5d1  mov     eax, edi
0x18001b5d3  add     rsp, 28h
0x18001b5d7  pop     r15
0x18001b5d9  pop     r14
0x18001b5db  pop     r13
0x18001b5dd  pop     r12
0x18001b5df  pop     rdi
0x18001b5e0  pop     rsi
0x18001b5e1  pop     rbp
0x18001b5e2  pop     rbx
0x18001b5e3  retn
```
