# CRegBag::GetPropertyInfo(ulong,ulong,tagPROPBAG2 *,ulong *)

- ea: `0x1800115d0`
- end: `0x18001190f`
- name: `?GetPropertyInfo@CRegBag@@UEAAJKKPEAUtagPROPBAG2@@PEAK@Z`
- size: `831`
- prototype: `int(CRegBag *__hidden this, unsigned int, unsigned int, struct tagPROPBAG2 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task`

## callees

- `0x180004740`
- `0x180004b48`
- `0x1800054bc`
- `0x18000bd70`
- `0x1800115d0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800117a9`
- `ole32!CoTaskMemAlloc` at `0x1800118a7`
- `ole32!CoTaskMemAlloc` at `0x1800117a9`
- `ole32!CoTaskMemAlloc` at `0x1800118a7`
- `ADVAPI32!RegEnumValueW` at `0x180011737`
- `ADVAPI32!RegEnumValueW` at `0x180011737`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001167f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001167f`
- `ADVAPI32!RegEnumKeyExW` at `0x180011869`
- `ADVAPI32!RegEnumKeyExW` at `0x180011869`

## pseudocode

```c
LSTATUS __fastcall CRegBag::GetPropertyInfo(
        HKEY *this,
        DWORD a2,
        unsigned int a3,
        struct tagPROPBAG2 *a4,
        unsigned int *a5)
{
  DWORD v5; // edi
  DWORD v7; // r12d
  HKEY *v8; // r14
  HKEY v9; // rcx
  LSTATUS result; // eax
  DWORD v11; // r8d
  DWORD v12; // eax
  DWORD v13; // ecx
  DWORD v14; // r13d
  unsigned int v15; // r15d
  unsigned __int64 v16; // rdx
  void *v17; // rsi
  __int64 v18; // rax
  SIZE_T v19; // r14
  OLECHAR *v20; // rax
  unsigned __int64 v21; // rdx
  WCHAR *v22; // rcx
  DWORD v23; // r14d
  unsigned __int64 v24; // rdx
  WCHAR *v25; // rdi
  __int64 v26; // rsi
  __int64 v27; // rax
  SIZE_T v28; // r12
  OLECHAR *v29; // rax
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-11h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-Dh] BYREF
  DWORD Type; // [rsp+70h] [rbp-9h] BYREF
  DWORD cSubKeys; // [rsp+74h] [rbp-5h] BYREF
  DWORD cbMaxValueLen; // [rsp+78h] [rbp-1h] BYREF
  DWORD cchValueName[19]; // [rsp+7Ch] [rbp+3h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+F0h] [rbp+77h] BYREF

  v5 = a3;
  v7 = a2;
  v8 = this;
  if ( !a4 || !a5 )
    return -2147467261;
  memset_0(a4, 0, 40LL * a3);
  v9 = v8[10];
  cSubKeys = 0;
  cValues = 0;
  cbMaxSubKeyLen = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  result = RegQueryInfoKeyW(
             v9,
             0,
             0,
             0,
             &cSubKeys,
             &cbMaxSubKeyLen,
             0,
             &cValues,
             &cbMaxValueNameLen,
             &cbMaxValueLen,
             0,
             0);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( cbMaxSubKeyLen > 0x400 || cbMaxValueNameLen > 0x400 )
    return -2147418113;
  v11 = 2 * cbMaxSubKeyLen + 2;
  v12 = cValues;
  v13 = 2 * cbMaxValueNameLen + 2;
  cbMaxSubKeyLen = v11;
  v14 = 0;
  cbMaxValueNameLen = v13;
  v15 = 0;
  if ( v7 < cValues )
  {
    v17 = operator new[](saturated_mul(v13 + 1, 2u));
    while ( 1 )
    {
      if ( v14 >= v5
        || (Type = 0,
            cchValueName[0] = cbMaxValueNameLen + 1,
            RegEnumValueW(v8[10], v14, (LPWSTR)v17, cchValueName, 0, &Type, 0, 0)) )
      {
        operator delete(v17, v16);
        v12 = cValues;
        v11 = cbMaxSubKeyLen;
        break;
      }
      if ( v14 >= v7 )
      {
        a4[v15].dwType = 1;
        switch ( Type )
        {
          case 1u:
            *(_DWORD *)&a4[v15].vt = 65544;
            break;
          case 4u:
            a4[v15].vt = 19;
            break;
          case 0xBu:
            a4[v15].vt = 21;
            break;
          default:
            a4[v15].vt = 8209;
            break;
        }
        v18 = -1;
        do
          ++v18;
        while ( *((_WORD *)v17 + v18) );
        v19 = 2 * v18 + 3;
        v20 = (OLECHAR *)CoTaskMemAlloc(v19);
        a4[v15].pstrName = v20;
        if ( !v20 )
        {
          v22 = (WCHAR *)v17;
LABEL_26:
          operator delete(v22, v21);
          return -2147024882;
        }
        StringCchCopyW(v20, v19, (const unsigned __int16 *)v17);
        v5 = a3;
        ++v15;
        v8 = this;
      }
      ++v14;
    }
  }
  if ( v7 < v12 + cSubKeys )
  {
    v23 = 0;
    v25 = (WCHAR *)operator new[](saturated_mul(v11 + 1, 2u));
    while ( v23 + v14 < a3 )
    {
      cchValueName[0] = cbMaxSubKeyLen + 1;
      if ( RegEnumKeyExW(this[10], v23, v25, cchValueName, 0, 0, 0, 0) )
        break;
      if ( v23 + v14 >= v7 )
      {
        v26 = v15;
        v27 = -1;
        a4[v26].dwType = 3;
        a4[v26].vt = 13;
        do
          ++v27;
        while ( v25[v27] );
        v28 = 2 * v27 + 3;
        v29 = (OLECHAR *)CoTaskMemAlloc(v28);
        a4[v15].pstrName = v29;
        if ( !v29 )
        {
          v22 = v25;
          goto LABEL_26;
        }
        StringCchCopyW(v29, v28, v25);
        v7 = a2;
        ++v15;
      }
      ++v23;
    }
    operator delete(v25, v24);
  }
  *a5 = v15;
  return 0;
}

```

## disassembly

```asm
0x1800115d0  mov     rax, rsp
0x1800115d3  mov     [rax+18h], r8d
0x1800115d7  mov     [rax+10h], edx
0x1800115da  mov     [rax+8], rcx
0x1800115de  push    rbp
0x1800115df  push    rbx
0x1800115e0  push    rsi
0x1800115e1  push    rdi
0x1800115e2  push    r12
0x1800115e4  push    r13
0x1800115e6  push    r14
0x1800115e8  push    r15
0x1800115ea  lea     rbp, [rax-57h]
0x1800115ee  sub     rsp, 88h
0x1800115f5  xor     esi, esi
0x1800115f7  mov     edi, r8d
0x1800115fa  mov     rbx, r9
0x1800115fd  mov     r12d, edx
0x180011600  mov     r14, rcx
0x180011603  test    r9, r9
0x180011606  jz      loc_1800118F6
0x18001160c  cmp     [rbp+4Fh+arg_20], rsi
0x180011610  jz      loc_1800118F6
0x180011616  lea     r8, [rdi+rdi*4]
0x18001161a  xor     edx, edx; Val
0x18001161c  shl     r8, 3; Size
0x180011620  mov     rcx, rbx; void *
0x180011623  call    memset_0
0x180011628  mov     rcx, [r14+50h]; hKey
0x18001162c  lea     rax, [rbp+4Fh+cbMaxValueLen]
0x180011630  mov     [rsp+58h], rsi; lpftLastWriteTime
0x180011635  xor     r9d, r9d; lpReserved
0x180011638  mov     [rsp+0C0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18001163d  xor     r8d, r8d; lpcchClass
0x180011640  mov     [rsp+0C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180011645  xor     edx, edx; lpClass
0x180011647  lea     rax, [rbp+4Fh+cbMaxValueNameLen]
0x18001164b  mov     [rbp+4Fh+cSubKeys], esi
0x18001164e  mov     [rsp+0C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180011653  lea     rax, [rbp+4Fh+cValues]
0x180011657  mov     [rsp+0C0h+lpcValues], rax; lpcValues
0x18001165c  lea     rax, [rbp+4Fh+cbMaxSubKeyLen]
0x180011660  mov     [rsp+0C0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180011665  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18001166a  lea     rax, [rbp+4Fh+cSubKeys]
0x18001166e  mov     [rsp+0C0h+lpcSubKeys], rax; lpcSubKeys
0x180011673  mov     [rbp+4Fh+cValues], esi
0x180011676  mov     [rbp+4Fh+cbMaxSubKeyLen], esi
0x180011679  mov     [rbp+4Fh+cbMaxValueNameLen], esi
0x18001167c  mov     [rbp+4Fh+cbMaxValueLen], esi
0x18001167f  call    cs:__imp_RegQueryInfoKeyW
0x180011685  test    eax, eax
0x180011687  jz      short loc_18001169C
0x180011689  jle     loc_1800118FB
0x18001168f  movzx   eax, ax
0x180011692  or      eax, 80070000h
0x180011697  jmp     loc_1800118FB
0x18001169c  mov     eax, [rbp+4Fh+cbMaxSubKeyLen]
0x18001169f  mov     edx, 400h
0x1800116a4  cmp     eax, edx
0x1800116a6  ja      loc_1800118EF
0x1800116ac  mov     ecx, [rbp+4Fh+cbMaxValueNameLen]
0x1800116af  cmp     ecx, edx
0x1800116b1  ja      loc_1800118EF
0x1800116b7  lea     r8d, ds:2[rax*2]
0x1800116bf  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800116c3  mov     eax, [rbp+4Fh+cValues]
0x1800116c6  lea     ecx, ds:2[rcx*2]
0x1800116cd  mov     [rbp+4Fh+cbMaxSubKeyLen], r8d
0x1800116d1  mov     r13d, esi
0x1800116d4  mov     [rbp+4Fh+cbMaxValueNameLen], ecx
0x1800116d7  mov     r15d, esi
0x1800116da  cmp     r12d, eax
0x1800116dd  jnb     loc_180011800
0x1800116e3  inc     ecx
0x1800116e5  lea     eax, [r9+3]
0x1800116e9  mul     rcx
0x1800116ec  cmovb   rax, r9
0x1800116f0  mov     rcx, rax; unsigned __int64
0x1800116f3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800116f8  mov     rsi, rax
0x1800116fb  cmp     r13d, edi
0x1800116fe  jnb     loc_1800117EB
0x180011704  mov     ecx, [rbp+4Fh+cbMaxValueNameLen]
0x180011707  lea     rax, [rbp+4Fh+Type]
0x18001170b  xor     edx, edx
0x18001170d  lea     r9, [rbp+4Fh+cchValueName]; lpcchValueName
0x180011711  mov     [rsp+0C0h+lpcValues], rdx; lpcbData
0x180011716  inc     ecx
0x180011718  mov     [rsp+0C0h+lpcbMaxClassLen], rdx; lpData
0x18001171d  mov     r8, rsi; lpValueName
0x180011720  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpType
0x180011725  mov     [rsp+0C0h+lpcSubKeys], rdx; lpReserved
0x18001172a  mov     [rbp+4Fh+Type], edx
0x18001172d  mov     edx, r13d; dwIndex
0x180011730  mov     [rbp+4Fh+cchValueName], ecx
0x180011733  mov     rcx, [r14+50h]; hKey
0x180011737  call    cs:__imp_RegEnumValueW
0x18001173d  xor     ecx, ecx
0x18001173f  test    eax, eax
0x180011741  jnz     loc_1800117EB
0x180011747  cmp     r13d, r12d
0x18001174a  jb      loc_1800117D1
0x180011750  mov     eax, r15d
0x180011753  lea     edx, [rcx+1]
0x180011756  lea     rdi, [rax+rax*4]
0x18001175a  mov     [rbx+rdi*8], edx
0x18001175d  mov     eax, [rbp+4Fh+Type]
0x180011760  sub     eax, edx
0x180011762  jz      short loc_180011789
0x180011764  sub     eax, 3
0x180011767  jz      short loc_180011780
0x180011769  cmp     eax, 7
0x18001176c  jz      short loc_180011777
0x18001176e  mov     word ptr [rbx+rdi*8+4], 2011h
0x180011775  jmp     short loc_180011791
0x180011777  mov     word ptr [rbx+rdi*8+4], 15h
0x18001177e  jmp     short loc_180011791
0x180011780  mov     word ptr [rbx+rdi*8+4], 13h
0x180011787  jmp     short loc_180011791
0x180011789  mov     dword ptr [rbx+rdi*8+4], 10008h
0x180011791  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011795  inc     rax
0x180011798  cmp     [rsi+rax*2], cx
0x18001179c  jnz     short loc_180011795
0x18001179e  lea     r14, ds:3[rax*2]
0x1800117a6  mov     rcx, r14; cb
0x1800117a9  call    cs:__imp_CoTaskMemAlloc
0x1800117af  mov     [rbx+rdi*8+10h], rax
0x1800117b4  test    rax, rax
0x1800117b7  jz      short loc_1800117D9
0x1800117b9  mov     r8, rsi; unsigned __int16 *
0x1800117bc  mov     rdx, r14; unsigned __int64
0x1800117bf  mov     rcx, rax; unsigned __int16 *
0x1800117c2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800117c7  mov     edi, [rbp+4Fh+arg_10]
0x1800117ca  inc     r15d
0x1800117cd  mov     r14, [rbp+4Fh+arg_0]
0x1800117d1  inc     r13d
0x1800117d4  jmp     loc_1800116FB
0x1800117d9  mov     rcx, rsi; void *
0x1800117dc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800117e1  mov     eax, 8007000Eh
0x1800117e6  jmp     loc_1800118FB
0x1800117eb  mov     rcx, rsi; void *
0x1800117ee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800117f3  mov     eax, [rbp+4Fh+cValues]
0x1800117f6  xor     esi, esi
0x1800117f8  mov     r8d, [rbp+4Fh+cbMaxSubKeyLen]
0x1800117fc  or      r9, 0FFFFFFFFFFFFFFFFh
0x180011800  mov     edx, [rbp+4Fh+cSubKeys]
0x180011803  add     edx, eax
0x180011805  cmp     r12d, edx
0x180011808  jnb     loc_1800118E4
0x18001180e  lea     edx, [r8+1]
0x180011812  mov     eax, 2
0x180011817  mul     rdx
0x18001181a  mov     r14d, esi
0x18001181d  cmovb   rax, r9
0x180011821  mov     rcx, rax; unsigned __int64
0x180011824  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011829  mov     rdi, rax
0x18001182c  lea     esi, [r14+r13]
0x180011830  cmp     esi, [rbp+4Fh+arg_10]
0x180011833  jnb     loc_1800118DC
0x180011839  mov     ecx, [rbp+4Fh+cbMaxSubKeyLen]
0x18001183c  lea     r9, [rbp+4Fh+cchValueName]; lpcchName
0x180011840  xor     eax, eax
0x180011842  inc     ecx
0x180011844  mov     [rsp+0C0h+lpcValues], rax; lpftLastWriteTime
0x180011849  mov     r8, rdi; lpName
0x18001184c  mov     [rsp+0C0h+lpcbMaxClassLen], rax; lpcchClass
0x180011851  mov     edx, r14d; dwIndex
0x180011854  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpClass
0x180011859  mov     [rsp+0C0h+lpcSubKeys], rax; lpReserved
0x18001185e  mov     rax, [rbp+4Fh+arg_0]
0x180011862  mov     [rbp+4Fh+cchValueName], ecx
0x180011865  mov     rcx, [rax+50h]; hKey
0x180011869  call    cs:__imp_RegEnumKeyExW
0x18001186f  xor     ecx, ecx
0x180011871  test    eax, eax
0x180011873  jnz     short loc_1800118DC
0x180011875  cmp     esi, r12d
0x180011878  jb      short loc_1800118CC
0x18001187a  mov     eax, r15d
0x18001187d  lea     rsi, [rax+rax*4]
0x180011881  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011885  mov     dword ptr [rbx+rsi*8], 3
0x18001188c  mov     word ptr [rbx+rsi*8+4], 0Dh
0x180011893  inc     rax
0x180011896  cmp     [rdi+rax*2], cx
0x18001189a  jnz     short loc_180011893
0x18001189c  lea     r12, ds:3[rax*2]
0x1800118a4  mov     rcx, r12; cb
0x1800118a7  call    cs:__imp_CoTaskMemAlloc
0x1800118ad  mov     [rbx+rsi*8+10h], rax
0x1800118b2  test    rax, rax
0x1800118b5  jz      short loc_1800118D4
0x1800118b7  mov     r8, rdi; unsigned __int16 *
0x1800118ba  mov     rdx, r12; unsigned __int64
0x1800118bd  mov     rcx, rax; unsigned __int16 *
0x1800118c0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800118c5  mov     r12d, [rbp+4Fh+arg_8]
0x1800118c9  inc     r15d
0x1800118cc  inc     r14d
0x1800118cf  jmp     loc_18001182C
0x1800118d4  mov     rcx, rdi
0x1800118d7  jmp     loc_1800117DC
0x1800118dc  mov     rcx, rdi; void *
0x1800118df  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800118e4  mov     rax, [rbp+4Fh+arg_20]
0x1800118e8  mov     [rax], r15d
0x1800118eb  xor     eax, eax
0x1800118ed  jmp     short loc_1800118FB
0x1800118ef  mov     eax, 8000FFFFh
0x1800118f4  jmp     short loc_1800118FB
0x1800118f6  mov     eax, 80004003h
0x1800118fb  add     rsp, 88h
0x180011902  pop     r15
0x180011904  pop     r14
0x180011906  pop     r13
0x180011908  pop     r12
0x18001190a  pop     rdi
0x18001190b  pop     rsi
0x18001190c  pop     rbx
0x18001190d  pop     rbp
0x18001190e  retn
```
