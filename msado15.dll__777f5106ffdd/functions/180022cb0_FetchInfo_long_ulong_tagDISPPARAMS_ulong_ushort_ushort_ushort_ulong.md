# FetchInfo(long,ulong,tagDISPPARAMS *,ulong,ushort * *,ushort * *,ushort * *,ulong *)

- ea: `0x180022cb0`
- end: `0x180023039`
- name: `?FetchInfo@@YAJJKPEAUtagDISPPARAMS@@KPEAPEAG11PEAK@Z`
- size: `905`
- prototype: `__int64 __fastcall(int, unsigned int, struct tagDISPPARAMS *, unsigned int, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180021c50`
- `0x180023040`
- `0x180023430`

## callees

- `0x180022cb0`
- `0x180023478`
- `0x1800c8f34`
- `0x1800ca578`
- `0x1800cdaea`
- `0x1800cdb20`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryW` at `0x180022dea`
- `KERNEL32!GetWindowsDirectoryW` at `0x180022dea`
- `USER32!LoadStringW` at `0x180022d6e`
- `USER32!LoadStringW` at `0x180022d6e`
- `OLEAUT32!__imp_SysAllocString` at `0x180022e4a`
- `OLEAUT32!__imp_SysAllocString` at `0x180022f50`
- `OLEAUT32!__imp_SysAllocString` at `0x180022fde`
- `OLEAUT32!__imp_SysAllocString` at `0x180022e4a`
- `OLEAUT32!__imp_SysAllocString` at `0x180022f50`
- `OLEAUT32!__imp_SysAllocString` at `0x180022fde`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180022ee2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180022ee2`

## pseudocode

```c
__int64 __fastcall FetchInfo(
        int a1,
        int a2,
        struct tagDISPPARAMS *a3,
        __int64 a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7,
        unsigned int *a8)
{
  __int64 v9; // rdx
  unsigned __int16 v11; // bx
  unsigned int v12; // ebp
  int v13; // eax
  UINT Lo; // edx
  int StringW; // ebx
  unsigned __int16 *v17; // rax
  __int64 v18; // rdx
  unsigned int v19; // edx
  unsigned int v20; // r8d
  __int64 v21; // rcx
  unsigned __int16 *v22; // rax
  VARIANTARG *rgvarg; // rdx
  unsigned __int16 *v24; // rax
  unsigned __int16 *v25; // rax
  __int64 v26; // [rsp+20h] [rbp-CB8h]
  __int64 v27; // [rsp+30h] [rbp-CA8h] BYREF
  int v28; // [rsp+38h] [rbp-CA0h]
  wchar_t v29; // [rsp+3Ch] [rbp-C9Ch]
  WCHAR v30[264]; // [rsp+40h] [rbp-C98h] BYREF
  OLECHAR psz[280]; // [rsp+250h] [rbp-A88h] BYREF
  WCHAR Buffer[1032]; // [rsp+480h] [rbp-858h] BYREF

  v9 = 0;
  v11 = a1;
  v12 = 1240640;
  while ( 1 )
  {
    v13 = qword_1800E1080[v9];
    if ( !v13 )
      break;
    if ( v13 == a1 )
    {
      v12 = HIDWORD(qword_1800E1080[v9]);
      break;
    }
    v9 = (unsigned int)(v9 + 1);
  }
  if ( !a5 && !a7 && !a8 )
  {
LABEL_22:
    if ( !a6 )
      return 0;
    v19 = 0;
    v20 = 0;
    while ( 1 )
    {
      v21 = 3LL * (int)v19;
      if ( a2 == **(_DWORD **)((char *)&objlib + v21 * 8) )
        break;
      v20 = ++v19;
      if ( v19 >= 0x31 )
        goto LABEL_35;
    }
    if ( v20 < 0x31 )
    {
      v22 = SysAllocStringLen((&off_180121D90)[v21], qword_180121D88[v21]);
      *a6 = v22;
      if ( v22 )
        return 0;
      if ( (bidGblFlags & 2) != 0 )
      {
        LODWORD(v26) = 2356;
        v18 = 2412553;
        goto LABEL_38;
      }
      return 2147942414LL;
    }
LABEL_35:
    v24 = SysAllocString(L"Provider");
    *a6 = v24;
    if ( v24 )
      return 0;
    if ( (bidGblFlags & 2) != 0 )
    {
      LODWORD(v26) = 2363;
      v18 = 2419721;
      goto LABEL_38;
    }
    return 2147942414LL;
  }
  if ( !byte_180122CE1 )
  {
    byte_180122CE1 = 1;
    LoadErrorDll();
  }
  if ( a3 && (rgvarg = a3->rgvarg) != 0 && a3->cArgs == 1 && rgvarg->vt == 3 )
    Lo = rgvarg->cyVal.Lo;
  else
    Lo = v11;
  StringW = LoadStringW(*((HINSTANCE *)g_pStaticGlobals + 1), Lo, Buffer, 1024);
  if ( !StringW || !a5 || (v17 = SysAllocString(Buffer), (*a5 = v17) != 0) )
  {
    if ( a7 && StringW )
    {
      v28 = *(_DWORD *)L"P\\";
      v29 = aHelp[6];
      v27 = *(_QWORD *)L"\\HELP\\";
      memset_0(v30, 0, 0x20Au);
      memset_0(psz, 0, sizeof(psz));
      if ( GetWindowsDirectoryW(v30, 0x105u) > 0x105 )
        return 2147549493LL;
      StringCchPrintfW(psz, 0x118u, L"%s%s%s", v30, &v27, L"ADO270.CHM");
      v25 = SysAllocString(psz);
      *a7 = v25;
      if ( !v25 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return 2147942414LL;
        LODWORD(v26) = 2336;
        v18 = 2392073;
        goto LABEL_38;
      }
    }
    if ( a8 )
      *a8 = v12;
    goto LABEL_22;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    LODWORD(v26) = 2311;
    v18 = 2366473;
LABEL_38:
    bidTraceW(off_18012A218[0], v18, L"<FetchInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n", 2147942414LL, v26);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180022cb0  mov     [rsp+arg_8], rbx
0x180022cb5  push    rbp
0x180022cb6  push    rsi
0x180022cb7  push    rdi
0x180022cb8  push    r12
0x180022cba  push    r13
0x180022cbc  push    r14
0x180022cbe  push    r15
0x180022cc0  sub     rsp, 0CA0h
0x180022cc7  mov     rax, cs:__security_cookie
0x180022cce  xor     rax, rsp
0x180022cd1  mov     [rsp+0CD8h+var_48], rax
0x180022cd9  mov     rdi, [rsp+0CD8h+arg_20]
0x180022ce1  lea     r9, cs:180000000h
0x180022ce8  mov     r13, [rsp+0CD8h+arg_28]
0x180022cf0  mov     r15d, edx
0x180022cf3  mov     r14, [rsp+0CD8h+arg_30]
0x180022cfb  xor     edx, edx
0x180022cfd  mov     r12, [rsp+0CD8h+arg_38]
0x180022d05  mov     rsi, r8
0x180022d08  mov     ebx, ecx
0x180022d0a  mov     ebp, 12EE40h
0x180022d0f  lea     rcx, ds:0[rdx*8]
0x180022d17  mov     eax, [rcx+r9+0E1080h]
0x180022d1f  test    eax, eax
0x180022d21  jz      short loc_180022D33
0x180022d23  cmp     eax, ebx
0x180022d25  jnz     loc_180022E32
0x180022d2b  mov     ebp, [rcx+r9+0E1084h]
0x180022d33  test    rdi, rdi
0x180022d36  jz      loc_180023011
0x180022d3c  cmp     cs:byte_180122CE1, 0
0x180022d43  jz      loc_180023028
0x180022d49  test    rsi, rsi
0x180022d4c  jnz     loc_180022F13
0x180022d52  movzx   edx, bx; uID
0x180022d55  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180022d5c  lea     r8, [rsp+0CD8h+Buffer]; lpBuffer
0x180022d64  mov     r9d, 400h; cchBufferMax
0x180022d6a  mov     rcx, [rcx+8]; hInstance
0x180022d6e  call    cs:__imp_LoadStringW
0x180022d75  nop     dword ptr [rax+rax+00h]
0x180022d7a  mov     ebx, eax
0x180022d7c  test    eax, eax
0x180022d7e  jnz     loc_180022E39
0x180022d84  test    r14, r14
0x180022d87  jz      loc_180022E81
0x180022d8d  test    ebx, ebx
0x180022d8f  jz      loc_180022E81
0x180022d95  mov     eax, dword ptr cs:aHelp+8; "P\\"
0x180022d9b  lea     rcx, [rsp+0CD8h+var_C98]; void *
0x180022da0  movsd   xmm0, qword ptr cs:aHelp; "\\HELP\\"
0x180022da8  xor     edx, edx; Val
0x180022daa  mov     [rsp+0CD8h+var_CA0], eax
0x180022dae  mov     r8d, 20Ah; Size
0x180022db4  movzx   eax, word ptr cs:aHelp+0Ch; ""
0x180022dbb  mov     [rsp+0CD8h+var_C9C], ax
0x180022dc0  movsd   [rsp+0CD8h+var_CA8], xmm0
0x180022dc6  call    memset_0
0x180022dcb  xor     edx, edx; Val
0x180022dcd  lea     rcx, [rsp+0CD8h+psz]; void *
0x180022dd5  mov     r8d, 230h; Size
0x180022ddb  call    memset_0
0x180022de0  mov     edx, 105h; uSize
0x180022de5  lea     rcx, [rsp+0CD8h+var_C98]; lpBuffer
0x180022dea  call    cs:__imp_GetWindowsDirectoryW
0x180022df1  nop     dword ptr [rax+rax+00h]
0x180022df6  cmp     eax, 105h
0x180022dfb  jbe     loc_180022FA2
0x180022e01  mov     eax, 80010135h
0x180022e06  mov     rcx, [rsp+0CD8h+var_48]
0x180022e0e  xor     rcx, rsp; StackCookie
0x180022e11  call    __security_check_cookie
0x180022e16  mov     rbx, [rsp+0CD8h+arg_8]
0x180022e1e  add     rsp, 0CA0h
0x180022e25  pop     r15
0x180022e27  pop     r14
0x180022e29  pop     r13
0x180022e2b  pop     r12
0x180022e2d  pop     rdi
0x180022e2e  pop     rsi
0x180022e2f  pop     rbp
0x180022e30  retn
0x180022e32  inc     edx
0x180022e34  jmp     loc_180022D0F
0x180022e39  test    rdi, rdi
0x180022e3c  jz      loc_180022D84
0x180022e42  lea     rcx, [rsp+0CD8h+Buffer]; psz
0x180022e4a  call    cs:__imp_SysAllocString
0x180022e51  nop     dword ptr [rax+rax+00h]
0x180022e56  mov     [rdi], rax
0x180022e59  test    rax, rax
0x180022e5c  jnz     loc_180022D84
0x180022e62  test    byte ptr cs:_bidGblFlags, 2
0x180022e69  jz      loc_180022F98
0x180022e6f  mov     dword ptr [rsp+0CD8h+var_CB8], 907h
0x180022e77  mov     edx, 241C09h
0x180022e7c  jmp     loc_180022F7F
0x180022e81  lea     r9, cs:180000000h
0x180022e88  test    r12, r12
0x180022e8b  jz      short loc_180022E91
0x180022e8d  mov     [r12], ebp
0x180022e91  test    r13, r13
0x180022e94  jnz     short loc_180022E9D
0x180022e96  xor     eax, eax
0x180022e98  jmp     loc_180022E06
0x180022e9d  xor     edx, edx
0x180022e9f  xor     r8d, r8d
0x180022ea2  nop     dword ptr [rax+00h]
0x180022ea6  nop     word ptr [rax+rax+00000000h]
0x180022eb0  movsxd  rax, edx
0x180022eb3  lea     rcx, [rax+rax*2]
0x180022eb7  lea     rcx, ds:0[rcx*8]
0x180022ebf  mov     rax, [rcx+r9+121D80h]
0x180022ec7  cmp     r15d, [rax]
0x180022eca  jnz     short loc_180022F3B
0x180022ecc  cmp     r8d, 31h ; '1'
0x180022ed0  jnb     short loc_180022F49
0x180022ed2  mov     edx, [rcx+r9+121D88h]; ui
0x180022eda  mov     rcx, [rcx+r9+121D90h]; strIn
0x180022ee2  call    cs:__imp_SysAllocStringLen
0x180022ee9  nop     dword ptr [rax+rax+00h]
0x180022eee  mov     [r13+0], rax
0x180022ef2  test    rax, rax
0x180022ef5  jnz     short loc_180022E96
0x180022ef7  test    byte ptr cs:_bidGblFlags, 2
0x180022efe  jz      loc_180022F98
0x180022f04  mov     dword ptr [rsp+0CD8h+var_CB8], 934h
0x180022f0c  mov     edx, 24D009h
0x180022f11  jmp     short loc_180022F7F
0x180022f13  mov     rdx, [rsi]
0x180022f16  test    rdx, rdx
0x180022f19  jz      loc_180022D52
0x180022f1f  cmp     dword ptr [rsi+10h], 1
0x180022f23  jnz     loc_180022D52
0x180022f29  cmp     word ptr [rdx], 3
0x180022f2d  jnz     loc_180022D52
0x180022f33  mov     edx, [rdx+8]
0x180022f36  jmp     loc_180022D55
0x180022f3b  inc     edx
0x180022f3d  mov     r8d, edx
0x180022f40  cmp     edx, 31h ; '1'
0x180022f43  jb      loc_180022EB0
0x180022f49  lea     rcx, psz; "Provider"
0x180022f50  call    cs:__imp_SysAllocString
0x180022f57  nop     dword ptr [rax+rax+00h]
0x180022f5c  mov     [r13+0], rax
0x180022f60  test    rax, rax
0x180022f63  jnz     loc_180022E96
0x180022f69  test    byte ptr cs:_bidGblFlags, 2
0x180022f70  jz      short loc_180022F98
0x180022f72  mov     dword ptr [rsp+0CD8h+var_CB8], 93Bh
0x180022f7a  mov     edx, 24EC09h
0x180022f7f  mov     rcx, cs:off_18012A218; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180022f86  lea     r8, aFetchinfoAdoEr; "<FetchInfo|ADO|ERR> 0x%08x{HRESULT} lin"...
0x180022f8d  mov     r9d, 8007000Eh
0x180022f93  call    _bidTraceW
0x180022f98  mov     eax, 8007000Eh
0x180022f9d  jmp     loc_180022E06
0x180022fa2  lea     rax, aAdo270Chm; "ADO270.CHM"
0x180022fa9  mov     edx, 118h; unsigned __int64
0x180022fae  mov     [rsp+0CD8h+var_CB0], rax
0x180022fb3  lea     r9, [rsp+0CD8h+var_C98]
0x180022fb8  lea     rax, [rsp+0CD8h+var_CA8]
0x180022fbd  lea     r8, aSSS; "%s%s%s"
0x180022fc4  mov     [rsp+0CD8h+var_CB8], rax
0x180022fc9  lea     rcx, [rsp+0CD8h+psz]; unsigned __int16 *
0x180022fd1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022fd6  lea     rcx, [rsp+0CD8h+psz]; psz
0x180022fde  call    cs:__imp_SysAllocString
0x180022fe5  nop     dword ptr [rax+rax+00h]
0x180022fea  mov     [r14], rax
0x180022fed  test    rax, rax
0x180022ff0  jnz     loc_180022E81
0x180022ff6  test    byte ptr cs:_bidGblFlags, 2
0x180022ffd  jz      short loc_180022F98
0x180022fff  mov     dword ptr [rsp+0CD8h+var_CB8], 920h
0x180023007  mov     edx, 248009h
0x18002300c  jmp     loc_180022F7F
0x180023011  test    r14, r14
0x180023014  jnz     loc_180022D3C
0x18002301a  test    r12, r12
0x18002301d  jz      loc_180022E91
0x180023023  jmp     loc_180022D3C
0x180023028  mov     cs:byte_180122CE1, 1
0x18002302f  call    ?LoadErrorDll@@YAXXZ; LoadErrorDll(void)
0x180023034  jmp     loc_180022D49
```
