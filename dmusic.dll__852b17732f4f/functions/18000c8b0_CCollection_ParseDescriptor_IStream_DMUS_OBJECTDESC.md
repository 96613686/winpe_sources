# CCollection::ParseDescriptor(IStream *,_DMUS_OBJECTDESC *)

- ea: `0x18000c8b0`
- end: `0x18000caf5`
- name: `?ParseDescriptor@CCollection@@UEAAJPEAUIStream@@PEAU_DMUS_OBJECTDESC@@@Z`
- size: `581`
- prototype: `__int64 __fastcall(CCollection *__hidden this, struct IStream *, struct _DMUS_OBJECTDESC *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800016d0`
- `0x180005e08`
- `0x180006320`
- `0x18000c8b0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000ca6e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000ca6e`

## pseudocode

```c
__int64 __fastcall CCollection::ParseDescriptor(CCollection *this, struct IStream *a2, struct _DMUS_OBJECTDESC *a3)
{
  int v4; // ebx
  __int64 v5; // rax
  __int64 result; // rax
  int v7; // [rsp+30h] [rbp-D0h] BYREF
  int v8; // [rsp+38h] [rbp-C8h] BYREF
  int v9; // [rsp+3Ch] [rbp-C4h]
  struct IStream *v10; // [rsp+40h] [rbp-C0h]
  __int128 *v11; // [rsp+48h] [rbp-B8h]
  __int128 *v12; // [rsp+50h] [rbp-B0h]
  __int64 v13; // [rsp+58h] [rbp-A8h]
  int v14; // [rsp+60h] [rbp-A0h]
  __int64 v15; // [rsp+68h] [rbp-98h] BYREF
  __int64 v16; // [rsp+70h] [rbp-90h]
  __int64 v17; // [rsp+78h] [rbp-88h]
  __int64 v18; // [rsp+80h] [rbp-80h]
  __int128 v19; // [rsp+88h] [rbp-78h] BYREF
  __int128 v20; // [rsp+98h] [rbp-68h]
  __int128 v21; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v22; // [rsp+B8h] [rbp-48h]
  CHAR MultiByteStr[64]; // [rsp+D0h] [rbp-30h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  v10 = a2;
  *(_DWORD *)a3 = 856;
  v8 = 0;
  v11 = (__int128 *)&v15;
  v13 = 0;
  v19 = 0;
  v14 = 0;
  v20 = 0;
  v15 = 0;
  v21 = 0;
  v16 = 0;
  v22 = 0;
  v18 = 0;
  v7 = 0;
  v17 = 0;
  v12 = 0;
  v9 = 1;
  if ( (unsigned int)CRiffParser::NextChunk((CRiffParser *)&v8, &v7) && (_DWORD)v16 == 542329924 )
  {
    v4 = 2;
    *(_QWORD *)&v20 = v11;
    v12 = v11;
    v11 = &v19;
    *(GUID *)((char *)a3 + 24) = CLSID_DirectMusicCollection;
    HIDWORD(v19) = 0;
    v9 = 1;
    while ( (unsigned int)CRiffParser::NextChunk((CRiffParser *)&v8, &v7) )
    {
      switch ( (_DWORD)v19 )
      {
        case 0x5453494C:
          if ( DWORD2(v19) == 1330007625 )
          {
            *(_QWORD *)&v22 = v11;
            v12 = v11;
            v11 = &v21;
            HIDWORD(v21) = 0;
            v9 = 1;
            while ( (unsigned int)CRiffParser::NextChunk((CRiffParser *)&v8, &v7) )
            {
              if ( (_DWORD)v21 == 1296125513 )
              {
                v7 = CRiffParser::Read((CRiffParser *)&v8, MultiByteStr, 0x40u);
                MultiByteStr[63] = 0;
                MultiByteToWideChar(0, 0, MultiByteStr, -1, (LPWSTR)a3 + 28, 64);
                v4 |= 4u;
              }
            }
            if ( v11 )
            {
              v5 = *((_QWORD *)v11 + 2);
              v11 = (__int128 *)v5;
              if ( v5 )
                v12 = *(__int128 **)(v5 + 16);
            }
          }
          break;
        case 0x64696C64:
          v7 = CRiffParser::Read((CRiffParser *)&v8, (char *)a3 + 8, 0x10u);
          v4 |= 1u;
          break;
        case 0x73726576:
          v7 = CRiffParser::Read((CRiffParser *)&v8, (char *)a3 + 48, 8u);
          v4 |= 0x80u;
          break;
      }
    }
    result = (unsigned int)v7;
  }
  else
  {
    v4 = 0;
    result = 2289570056LL;
  }
  if ( (int)result >= 0 )
    *((_DWORD *)a3 + 1) = v4;
  return result;
}

```

## disassembly

```asm
0x18000c8b0  push    rbp
0x18000c8b2  push    rbx
0x18000c8b3  push    rsi
0x18000c8b4  push    rdi
0x18000c8b5  lea     rbp, [rsp-28h]
0x18000c8ba  sub     rsp, 128h
0x18000c8c1  mov     rax, cs:__security_cookie
0x18000c8c8  xor     rax, rsp
0x18000c8cb  mov     [rbp+40h+var_30], rax
0x18000c8cf  xor     esi, esi
0x18000c8d1  mov     rdi, r8
0x18000c8d4  test    rdx, rdx
0x18000c8d7  jz      loc_18000CAD8
0x18000c8dd  test    r8, r8
0x18000c8e0  jz      loc_18000CAD8
0x18000c8e6  xorps   xmm0, xmm0
0x18000c8e9  mov     [rsp+140h+var_100], rdx
0x18000c8ee  xorps   xmm1, xmm1
0x18000c8f1  mov     dword ptr [r8], 358h
0x18000c8f8  lea     rax, [rsp+140h+var_D8]
0x18000c8fd  mov     [rsp+140h+var_108], esi
0x18000c901  lea     rdx, [rsp+140h+var_110]; int *
0x18000c906  mov     [rsp+140h+var_F8], rax
0x18000c90b  lea     rcx, [rsp+140h+var_108]; this
0x18000c910  mov     [rsp+140h+var_E8], rsi
0x18000c915  movups  [rbp+40h+var_B8], xmm0
0x18000c919  mov     [rsp+140h+var_E0], esi
0x18000c91d  movups  [rbp+40h+var_A8], xmm0
0x18000c921  mov     [rsp+140h+var_D8], rsi
0x18000c926  movups  [rbp+40h+var_98], xmm1
0x18000c92a  mov     [rsp+140h+var_D0], rsi
0x18000c92f  movups  [rbp+40h+var_88], xmm1
0x18000c933  mov     [rbp+40h+var_C0], rsi
0x18000c937  mov     [rsp+140h+var_110], esi
0x18000c93b  mov     [rsp+140h+var_C8], rsi
0x18000c940  mov     [rsp+140h+var_F0], rsi
0x18000c945  mov     [rsp+140h+var_104], 1
0x18000c94d  call    ?NextChunk@CRiffParser@@QEAAHPEAJ@Z; CRiffParser::NextChunk(long *)
0x18000c952  test    eax, eax
0x18000c954  jz      loc_18000CAC8
0x18000c95a  cmp     dword ptr [rsp+140h+var_D0], 20534C44h
0x18000c962  jnz     loc_18000CAC8
0x18000c968  mov     rax, [rsp+140h+var_F8]
0x18000c96d  lea     ebx, [rsi+2]
0x18000c970  movups  xmm0, xmmword ptr cs:CLSID_DirectMusicCollection.Data1
0x18000c977  mov     qword ptr [rbp+40h+var_A8], rax
0x18000c97b  mov     [rsp+140h+var_F0], rax
0x18000c980  lea     rax, [rbp+40h+var_B8]
0x18000c984  mov     [rsp+140h+var_F8], rax
0x18000c989  movdqu  xmmword ptr [rdi+18h], xmm0
0x18000c98e  mov     dword ptr [rbp+40h+var_B8+0Ch], esi
0x18000c991  mov     [rsp+140h+var_104], 1
0x18000c999  jmp     loc_18000CAAB
0x18000c99e  mov     eax, dword ptr [rbp+40h+var_B8]
0x18000c9a1  cmp     eax, 5453494Ch
0x18000c9a6  jz      short loc_18000C9FB
0x18000c9a8  cmp     eax, 64696C64h
0x18000c9ad  jz      short loc_18000C9DB
0x18000c9af  cmp     eax, 73726576h
0x18000c9b4  jnz     loc_18000CAAB
0x18000c9ba  lea     rdx, [rdi+30h]; void *
0x18000c9be  mov     r8d, 8; unsigned int
0x18000c9c4  lea     rcx, [rsp+140h+var_108]; this
0x18000c9c9  call    ?Read@CRiffParser@@QEAAJPEAXK@Z; CRiffParser::Read(void *,ulong)
0x18000c9ce  mov     [rsp+140h+var_110], eax
0x18000c9d2  bts     ebx, 7
0x18000c9d6  jmp     loc_18000CAAB
0x18000c9db  lea     rdx, [rdi+8]; void *
0x18000c9df  mov     r8d, 10h; unsigned int
0x18000c9e5  lea     rcx, [rsp+140h+var_108]; this
0x18000c9ea  call    ?Read@CRiffParser@@QEAAJPEAXK@Z; CRiffParser::Read(void *,ulong)
0x18000c9ef  mov     [rsp+140h+var_110], eax
0x18000c9f3  or      ebx, 1
0x18000c9f6  jmp     loc_18000CAAB
0x18000c9fb  cmp     dword ptr [rbp+40h+var_B8+8], 4F464E49h
0x18000ca02  jnz     loc_18000CAAB
0x18000ca08  mov     rax, [rsp+140h+var_F8]
0x18000ca0d  mov     qword ptr [rbp+40h+var_88], rax
0x18000ca11  mov     [rsp+140h+var_F0], rax
0x18000ca16  lea     rax, [rbp+40h+var_98]
0x18000ca1a  mov     [rsp+140h+var_F8], rax
0x18000ca1f  mov     dword ptr [rbp+40h+var_98+0Ch], esi
0x18000ca22  mov     [rsp+140h+var_104], 1
0x18000ca2a  jmp     short loc_18000CA77
0x18000ca2c  cmp     dword ptr [rbp+40h+var_98], 4D414E49h
0x18000ca33  jnz     short loc_18000CA77
0x18000ca35  mov     r8d, 40h ; '@'; unsigned int
0x18000ca3b  lea     rdx, [rbp+40h+MultiByteStr]; void *
0x18000ca3f  lea     rcx, [rsp+140h+var_108]; this
0x18000ca44  call    ?Read@CRiffParser@@QEAAJPEAXK@Z; CRiffParser::Read(void *,ulong)
0x18000ca49  mov     [rsp+140h+var_110], eax
0x18000ca4d  lea     r8, [rbp+40h+MultiByteStr]; lpMultiByteStr
0x18000ca51  lea     rax, [rdi+38h]
0x18000ca55  mov     [rsp+140h+cchWideChar], 40h ; '@'; cchWideChar
0x18000ca5d  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000ca61  mov     [rsp+140h+lpWideCharStr], rax; lpWideCharStr
0x18000ca66  xor     edx, edx; dwFlags
0x18000ca68  mov     [rbp+40h+var_31], sil
0x18000ca6c  xor     ecx, ecx; CodePage
0x18000ca6e  call    cs:__imp_MultiByteToWideChar
0x18000ca74  or      ebx, 4
0x18000ca77  lea     rdx, [rsp+140h+var_110]; int *
0x18000ca7c  lea     rcx, [rsp+140h+var_108]; this
0x18000ca81  call    ?NextChunk@CRiffParser@@QEAAHPEAJ@Z; CRiffParser::NextChunk(long *)
0x18000ca86  test    eax, eax
0x18000ca88  jnz     short loc_18000CA2C
0x18000ca8a  mov     rax, [rsp+140h+var_F8]
0x18000ca8f  test    rax, rax
0x18000ca92  jz      short loc_18000CAAB
0x18000ca94  mov     rax, [rax+10h]
0x18000ca98  mov     [rsp+140h+var_F8], rax
0x18000ca9d  test    rax, rax
0x18000caa0  jz      short loc_18000CAAB
0x18000caa2  mov     rax, [rax+10h]
0x18000caa6  mov     [rsp+140h+var_F0], rax
0x18000caab  lea     rdx, [rsp+140h+var_110]; int *
0x18000cab0  lea     rcx, [rsp+140h+var_108]; this
0x18000cab5  call    ?NextChunk@CRiffParser@@QEAAHPEAJ@Z; CRiffParser::NextChunk(long *)
0x18000caba  test    eax, eax
0x18000cabc  jnz     loc_18000C99E
0x18000cac2  mov     eax, [rsp+140h+var_110]
0x18000cac6  jmp     short loc_18000CACF
0x18000cac8  mov     ebx, esi
0x18000caca  mov     eax, 88781108h
0x18000cacf  test    eax, eax
0x18000cad1  js      short loc_18000CADD
0x18000cad3  mov     [rdi+4], ebx
0x18000cad6  jmp     short loc_18000CADD
0x18000cad8  mov     eax, 80004003h
0x18000cadd  mov     rcx, [rbp+40h+var_30]
0x18000cae1  xor     rcx, rsp; StackCookie
0x18000cae4  call    __security_check_cookie
0x18000cae9  add     rsp, 128h
0x18000caf0  pop     rdi
0x18000caf1  pop     rsi
0x18000caf2  pop     rbx
0x18000caf3  pop     rbp
0x18000caf4  retn
```
