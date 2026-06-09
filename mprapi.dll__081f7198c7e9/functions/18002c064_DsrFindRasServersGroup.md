# DsrFindRasServersGroup

- ea: `0x18002c064`
- end: `0x18002c42f`
- name: `DsrFindRasServersGroup`
- size: `971`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800090c4`

## callees

- `0x180009350`
- `0x180009868`
- `0x18002bae0`
- `0x18002bca8`
- `0x18002c064`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002c39f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002c3ad`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002c3bb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002c3c9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002c39f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002c3ad`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002c3bb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002c3c9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002c0ff`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002c234`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002c307`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002c0ff`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002c234`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002c307`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c18b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c18b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c401`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c401`
- `OLEAUT32!__imp_VariantInit` at `0x18002c17e`
- `OLEAUT32!__imp_VariantInit` at `0x18002c17e`
- `OLEAUT32!__imp_VariantClear` at `0x18002c1e7`
- `OLEAUT32!__imp_VariantClear` at `0x18002c1e7`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsGetObject` at `0x18002c146`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsGetObject` at `0x18002c146`

## string_xrefs

- `0x18002c20e`: `GroupSid = %ls`
- `0x18002c249`: `(objectSid=%s)`
- `0x18002c184`: `objectSid`

## pseudocode

```c
__int64 __fastcall DsrFindRasServersGroup(__int64 a1, wchar_t **a2)
{
  wchar_t *v3; // r12
  unsigned __int16 *v4; // rdi
  PSID v5; // r14
  OLECHAR *v6; // r13
  __int64 v7; // rsi
  __int64 v8; // rax
  size_t v9; // r13
  wchar_t *v10; // rax
  WCHAR *v11; // r15
  HRESULT Object; // ebx
  BSTR v13; // rax
  __int64 v14; // rdx
  signed int inited; // eax
  __int64 v16; // rax
  size_t v17; // rbx
  wchar_t *v18; // rax
  __int64 i; // r9
  size_t v20; // rsi
  wchar_t *v21; // r10
  __int64 result; // rax
  unsigned __int16 *v23; // [rsp+30h] [rbp-59h] BYREF
  __int64 v24; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v25[2]; // [rsp+48h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-31h] BYREF
  __int128 v27; // [rsp+70h] [rbp-19h] BYREF
  __int128 v28; // [rsp+80h] [rbp-9h]
  __int64 v29; // [rsp+90h] [rbp+7h]
  void *ppObject; // [rsp+F0h] [rbp+67h] BYREF
  wchar_t **v31; // [rsp+F8h] [rbp+6Fh]
  __int64 v32; // [rsp+100h] [rbp+77h] BYREF
  PSID pSid; // [rsp+108h] [rbp+7Fh] BYREF

  v31 = a2;
  v29 = 0;
  ppObject = 0;
  v25[0] = L"distinguishedName";
  v3 = 0;
  v24 = 0;
  v23 = 0;
  v4 = 0;
  v32 = 0;
  v5 = 0;
  v25[1] = 0;
  v6 = 0;
  pSid = 0;
  v27 = 0;
  v28 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( a1 && a2 )
  {
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(a1 + 2 * v8) );
    v9 = 2 * v8 + 16;
    v10 = (wchar_t *)GlobalAlloc(0, (unsigned int)(2 * v8 + 16));
    v11 = v10;
    if ( !v10 )
    {
      Object = 8;
      v6 = 0;
      goto LABEL_31;
    }
    StringCbPrintfW(v10, v9, L"%s%s", L"LDAP://", a1);
    Object = ADsGetObject(v11, &IID_IDirectorySearch, &ppObject);
    if ( Object < 0
      || (Object = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppObject)(ppObject, &IID_IADs, &v24),
          Object < 0) )
    {
      v6 = 0;
    }
    else
    {
      VariantInit(&pvarg);
      v13 = SysAllocString(L"objectSid");
      v6 = v13;
      if ( !v13 )
      {
LABEL_10:
        Object = 8;
        goto LABEL_31;
      }
      Object = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v24 + 136LL))(v24, v13, &pvarg);
      if ( Object >= 0 )
      {
        Object = DsrSidInit(&pvarg, (unsigned __int8 **)&pSid);
        if ( Object )
        {
          v5 = pSid;
        }
        else
        {
          VariantClear(&pvarg);
          v5 = pSid;
          inited = DsrSidInitAscii((unsigned __int8 *)pSid, v14, &v23);
          v4 = v23;
          Object = inited;
          if ( inited >= 0 )
          {
            DsrTraceEx(0, "GroupSid = %ls", v23);
            v16 = -1;
            do
              ++v16;
            while ( v4[v16] );
            v17 = 2 * v16 + 30;
            v18 = (wchar_t *)GlobalAlloc(0, (unsigned int)(2 * v16 + 30));
            v3 = v18;
            if ( !v18 )
              goto LABEL_10;
            StringCbPrintfW(v18, v17, L"(objectSid=%s)", v4);
            for ( i = 0; v25[i]; i = (unsigned int)(i + 1) )
              ;
            Object = (*(__int64 (__fastcall **)(void *, wchar_t *, _QWORD *, __int64, __int64 *))(*(_QWORD *)ppObject
                                                                                                + 32LL))(
                       ppObject,
                       v3,
                       v25,
                       i,
                       &v32);
            if ( Object >= 0 )
            {
              if ( (*(unsigned int (__fastcall **)(void *, __int64))(*(_QWORD *)ppObject + 56LL))(ppObject, v32) == 20498 )
              {
                Object = 1168;
              }
              else
              {
                Object = (*(__int64 (__fastcall **)(void *, __int64, const wchar_t *, __int128 *))(*(_QWORD *)ppObject
                                                                                                 + 80LL))(
                           ppObject,
                           v32,
                           L"distinguishedName",
                           &v27);
                if ( Object >= 0 )
                {
                  Object = 0;
                  do
                    ++v7;
                  while ( *(_WORD *)(*(_QWORD *)(v28 + 8) + 2 * v7) );
                  v20 = 2 * v7 + 16;
                  v21 = (wchar_t *)GlobalAlloc(0, (unsigned int)v20);
                  *v31 = v21;
                  if ( !v21 )
                  {
                    (*(void (__fastcall **)(void *, __int128 *))(*(_QWORD *)ppObject + 88LL))(ppObject, &v27);
                    goto LABEL_10;
                  }
                  StringCbPrintfW(v21, v20, L"%s%s", L"LDAP://", *(_QWORD *)(v28 + 8));
                  (*(void (__fastcall **)(void *, __int128 *))(*(_QWORD *)ppObject + 88LL))(ppObject, &v27);
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v11 = 0;
    Object = 87;
  }
LABEL_31:
  if ( v32 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 96LL))(ppObject);
  if ( v11 )
    GlobalFree(v11);
  if ( v3 )
    GlobalFree(v3);
  if ( v5 )
    GlobalFree(v5);
  if ( v4 )
    GlobalFree(v4);
  if ( ppObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v6 )
    SysFreeString(v6);
  result = (unsigned __int16)Object;
  if ( (Object & 0x1FFF0000) != 0x70000 )
    return (unsigned int)Object;
  return result;
}

```

## disassembly

```asm
0x18002c064  mov     [rsp-8+arg_8], rdx
0x18002c069  push    rbp
0x18002c06a  push    rbx
0x18002c06b  push    rsi
0x18002c06c  push    rdi
0x18002c06d  push    r12
0x18002c06f  push    r13
0x18002c071  push    r14
0x18002c073  push    r15
0x18002c075  lea     rbp, [rsp-1Fh]
0x18002c07a  sub     rsp, 0A8h
0x18002c081  mov     rbx, rcx
0x18002c084  xorps   xmm0, xmm0
0x18002c087  xor     ecx, ecx
0x18002c089  mov     rax, rdx
0x18002c08c  xor     edx, edx
0x18002c08e  mov     [rbp+57h+var_50], rcx
0x18002c092  lea     rcx, aDistinguishedn; "distinguishedName"
0x18002c099  mov     [rbp+57h+ppObject], rdx
0x18002c09d  mov     [rbp+57h+var_98], rcx
0x18002c0a1  mov     r12d, edx
0x18002c0a4  xor     ecx, ecx; uFlags
0x18002c0a6  mov     [rbp+57h+var_A0], rdx
0x18002c0aa  mov     [rbp+57h+var_B0], rdx
0x18002c0ae  mov     edi, edx
0x18002c0b0  mov     [rbp+57h+arg_10], rdx
0x18002c0b4  mov     r14d, edx
0x18002c0b7  mov     [rbp+57h+var_90], rdx
0x18002c0bb  mov     r13d, edx
0x18002c0be  mov     qword ptr [rbp+57h+pvarg+10h], rcx
0x18002c0c2  mov     [rbp+57h+pSid], rdx
0x18002c0c6  movups  [rbp+57h+var_70], xmm0
0x18002c0ca  movups  [rbp+57h+var_60], xmm0
0x18002c0ce  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18002c0d2  test    rbx, rbx
0x18002c0d5  jz      loc_18002C376
0x18002c0db  test    rax, rax
0x18002c0de  jz      loc_18002C376
0x18002c0e4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002c0e8  mov     rax, rsi
0x18002c0eb  inc     rax
0x18002c0ee  cmp     [rbx+rax*2], dx
0x18002c0f2  jnz     short loc_18002C0EB
0x18002c0f4  lea     r13, ds:10h[rax*2]
0x18002c0fc  mov     edx, r13d; dwBytes
0x18002c0ff  call    cs:__imp_GlobalAlloc
0x18002c105  xor     ecx, ecx
0x18002c107  mov     r15, rax
0x18002c10a  test    rax, rax
0x18002c10d  jnz     short loc_18002C11A
0x18002c10f  lea     ebx, [rax+8]
0x18002c112  mov     r13d, ecx
0x18002c115  jmp     loc_18002C37E
0x18002c11a  lea     r9, aLdap; "LDAP://"
0x18002c121  mov     [rsp+0E0h+var_C0], rbx
0x18002c126  lea     r8, aSS_1; "%s%s"
0x18002c12d  mov     rdx, r13; cbDest
0x18002c130  mov     rcx, r15; pszDest
0x18002c133  call    StringCbPrintfW
0x18002c138  lea     r8, [rbp+57h+ppObject]; ppObject
0x18002c13c  mov     rcx, r15; lpszPathName
0x18002c13f  lea     rdx, IID_IDirectorySearch; riid
0x18002c146  call    cs:__imp_ADsGetObject
0x18002c14c  mov     ebx, eax
0x18002c14e  test    eax, eax
0x18002c150  js      loc_18002C371
0x18002c156  mov     rcx, [rbp+57h+ppObject]
0x18002c15a  lea     r8, [rbp+57h+var_A0]
0x18002c15e  lea     rdx, IID_IADs
0x18002c165  mov     rax, [rcx]
0x18002c168  mov     rax, [rax]
0x18002c16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c170  mov     ebx, eax
0x18002c172  test    eax, eax
0x18002c174  js      loc_18002C371
0x18002c17a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002c17e  call    cs:__imp_VariantInit
0x18002c184  lea     rcx, psz; "objectSid"
0x18002c18b  call    cs:__imp_SysAllocString
0x18002c191  mov     r13, rax
0x18002c194  test    rax, rax
0x18002c197  jnz     short loc_18002C1A3
0x18002c199  mov     ebx, 8
0x18002c19e  jmp     loc_18002C37E
0x18002c1a3  mov     rcx, [rbp+57h+var_A0]
0x18002c1a7  lea     r8, [rbp+57h+pvarg]
0x18002c1ab  mov     rdx, r13
0x18002c1ae  mov     rax, [rcx]
0x18002c1b1  mov     rax, [rax+88h]
0x18002c1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1bd  mov     ebx, eax
0x18002c1bf  test    eax, eax
0x18002c1c1  js      loc_18002C37E
0x18002c1c7  lea     rdx, [rbp+57h+pSid]; unsigned __int8 **
0x18002c1cb  lea     rcx, [rbp+57h+pvarg]; struct tagVARIANT *
0x18002c1cf  call    ?DsrSidInit@@YAKPEAUtagVARIANT@@PEAPEAE@Z; DsrSidInit(tagVARIANT *,uchar * *)
0x18002c1d4  mov     ebx, eax
0x18002c1d6  test    eax, eax
0x18002c1d8  jz      short loc_18002C1E3
0x18002c1da  mov     r14, [rbp+57h+pSid]
0x18002c1de  jmp     loc_18002C37E
0x18002c1e3  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002c1e7  call    cs:__imp_VariantClear
0x18002c1ed  mov     r14, [rbp+57h+pSid]
0x18002c1f1  lea     r8, [rbp+57h+var_B0]; unsigned __int16 **
0x18002c1f5  mov     rcx, r14; pSid
0x18002c1f8  call    ?DsrSidInitAscii@@YAJPEAEKPEAPEAG@Z; DsrSidInitAscii(uchar *,ulong,ushort * *)
0x18002c1fd  mov     rdi, [rbp+57h+var_B0]
0x18002c201  mov     ebx, eax
0x18002c203  test    eax, eax
0x18002c205  js      loc_18002C37E
0x18002c20b  mov     r8, rdi
0x18002c20e  lea     rdx, aGroupsidLs; "GroupSid = %ls"
0x18002c215  xor     ecx, ecx
0x18002c217  call    DsrTraceEx
0x18002c21c  mov     rax, rsi
0x18002c21f  xor     ecx, ecx; uFlags
0x18002c221  inc     rax
0x18002c224  cmp     [rdi+rax*2], cx
0x18002c228  jnz     short loc_18002C221
0x18002c22a  lea     rbx, ds:1Eh[rax*2]
0x18002c232  mov     edx, ebx; dwBytes
0x18002c234  call    cs:__imp_GlobalAlloc
0x18002c23a  mov     r12, rax
0x18002c23d  test    rax, rax
0x18002c240  jz      loc_18002C199
0x18002c246  mov     r9, rdi
0x18002c249  lea     r8, aObjectsidS; "(objectSid=%s)"
0x18002c250  mov     rdx, rbx; cbDest
0x18002c253  mov     rcx, rax; pszDest
0x18002c256  call    StringCbPrintfW
0x18002c25b  xor     ecx, ecx
0x18002c25d  mov     r9d, ecx
0x18002c260  cmp     [rbp+57h+var_98], rcx
0x18002c264  jz      short loc_18002C270
0x18002c266  inc     r9d
0x18002c269  cmp     [rbp+r9*8+57h+var_98], rcx
0x18002c26e  jnz     short loc_18002C266
0x18002c270  mov     rcx, [rbp+57h+ppObject]
0x18002c274  lea     rdx, [rbp+57h+arg_10]
0x18002c278  mov     [rsp+0E0h+var_C0], rdx
0x18002c27d  lea     r8, [rbp+57h+var_98]
0x18002c281  mov     rdx, r12
0x18002c284  mov     rax, [rcx]
0x18002c287  mov     rax, [rax+20h]
0x18002c28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c290  mov     ebx, eax
0x18002c292  test    eax, eax
0x18002c294  js      loc_18002C37E
0x18002c29a  mov     rcx, [rbp+57h+ppObject]
0x18002c29e  mov     rdx, [rbp+57h+arg_10]
0x18002c2a2  mov     rax, [rcx]
0x18002c2a5  mov     rax, [rax+38h]
0x18002c2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2ae  cmp     eax, 5012h
0x18002c2b3  jnz     short loc_18002C2BF
0x18002c2b5  mov     ebx, 490h
0x18002c2ba  jmp     loc_18002C37E
0x18002c2bf  mov     rcx, [rbp+57h+ppObject]
0x18002c2c3  lea     r9, [rbp+57h+var_70]
0x18002c2c7  mov     rdx, [rbp+57h+arg_10]
0x18002c2cb  lea     r8, aDistinguishedn; "distinguishedName"
0x18002c2d2  mov     rax, [rcx]
0x18002c2d5  mov     rax, [rax+50h]
0x18002c2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2de  mov     ebx, eax
0x18002c2e0  test    eax, eax
0x18002c2e2  js      loc_18002C37E
0x18002c2e8  mov     rax, qword ptr [rbp+57h+var_60]
0x18002c2ec  xor     ebx, ebx
0x18002c2ee  mov     rcx, [rax+8]
0x18002c2f2  inc     rsi
0x18002c2f5  cmp     [rcx+rsi*2], bx
0x18002c2f9  jnz     short loc_18002C2F2
0x18002c2fb  lea     rsi, ds:10h[rsi*2]
0x18002c303  xor     ecx, ecx; uFlags
0x18002c305  mov     edx, esi; dwBytes
0x18002c307  call    cs:__imp_GlobalAlloc
0x18002c30d  mov     r10, rax
0x18002c310  mov     rax, [rbp+57h+arg_8]
0x18002c314  mov     [rax], r10
0x18002c317  test    r10, r10
0x18002c31a  jnz     short loc_18002C335
0x18002c31c  mov     rcx, [rbp+57h+ppObject]
0x18002c320  lea     rdx, [rbp+57h+var_70]
0x18002c324  mov     rax, [rcx]
0x18002c327  mov     rax, [rax+58h]
0x18002c32b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c330  jmp     loc_18002C199
0x18002c335  mov     rax, qword ptr [rbp+57h+var_60]
0x18002c339  lea     r9, aLdap; "LDAP://"
0x18002c340  lea     r8, aSS_1; "%s%s"
0x18002c347  mov     rdx, rsi; cbDest
0x18002c34a  mov     rcx, [rax+8]
0x18002c34e  mov     [rsp+0E0h+var_C0], rcx
0x18002c353  mov     rcx, r10; pszDest
0x18002c356  call    StringCbPrintfW
0x18002c35b  mov     rcx, [rbp+57h+ppObject]
0x18002c35f  lea     rdx, [rbp+57h+var_70]
0x18002c363  mov     rax, [rcx]
0x18002c366  mov     rax, [rax+58h]
0x18002c36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c36f  jmp     short loc_18002C37E
0x18002c371  mov     r13, rdi
0x18002c374  jmp     short loc_18002C37E
0x18002c376  mov     r15, rdx
0x18002c379  mov     ebx, 57h ; 'W'
0x18002c37e  mov     rdx, [rbp+57h+arg_10]
0x18002c382  test    rdx, rdx
0x18002c385  jz      short loc_18002C397
0x18002c387  mov     rcx, [rbp+57h+ppObject]
0x18002c38b  mov     rax, [rcx]
0x18002c38e  mov     rax, [rax+60h]
0x18002c392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c397  test    r15, r15
0x18002c39a  jz      short loc_18002C3A5
0x18002c39c  mov     rcx, r15; hMem
0x18002c39f  call    cs:__imp_GlobalFree
0x18002c3a5  test    r12, r12
0x18002c3a8  jz      short loc_18002C3B3
0x18002c3aa  mov     rcx, r12; hMem
0x18002c3ad  call    cs:__imp_GlobalFree
0x18002c3b3  test    r14, r14
0x18002c3b6  jz      short loc_18002C3C1
0x18002c3b8  mov     rcx, r14; hMem
0x18002c3bb  call    cs:__imp_GlobalFree
0x18002c3c1  test    rdi, rdi
0x18002c3c4  jz      short loc_18002C3CF
0x18002c3c6  mov     rcx, rdi; hMem
0x18002c3c9  call    cs:__imp_GlobalFree
0x18002c3cf  mov     rcx, [rbp+57h+ppObject]
0x18002c3d3  test    rcx, rcx
0x18002c3d6  jz      short loc_18002C3E4
0x18002c3d8  mov     rax, [rcx]
0x18002c3db  mov     rax, [rax+10h]
0x18002c3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3e4  mov     rcx, [rbp+57h+var_A0]
0x18002c3e8  test    rcx, rcx
0x18002c3eb  jz      short loc_18002C3F9
0x18002c3ed  mov     rax, [rcx]
0x18002c3f0  mov     rax, [rax+10h]
0x18002c3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3f9  test    r13, r13
0x18002c3fc  jz      short loc_18002C407
0x18002c3fe  mov     rcx, r13; bstrString
0x18002c401  call    cs:__imp_SysFreeString
0x18002c407  mov     ecx, ebx
0x18002c409  movzx   eax, bx
0x18002c40c  and     ecx, 1FFF0000h
0x18002c412  cmp     ecx, 70000h
0x18002c418  cmovnz  eax, ebx
0x18002c41b  add     rsp, 0A8h
0x18002c422  pop     r15
0x18002c424  pop     r14
0x18002c426  pop     r13
0x18002c428  pop     r12
0x18002c42a  pop     rdi
0x18002c42b  pop     rsi
0x18002c42c  pop     rbx
0x18002c42d  pop     rbp
0x18002c42e  retn
```
