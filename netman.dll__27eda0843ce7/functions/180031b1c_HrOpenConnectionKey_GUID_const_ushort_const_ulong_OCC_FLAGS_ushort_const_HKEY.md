# HrOpenConnectionKey(_GUID const *,ushort const *,ulong,OCC_FLAGS,ushort const *,HKEY__ * *)

- ea: `0x180031b1c`
- end: `0x180031d03`
- name: `?HrOpenConnectionKey@@YAJPEBU_GUID@@PEBGKW4OCC_FLAGS@@1PEAPEAUHKEY__@@@Z`
- size: `487`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025020`
- `0x180025ab4`
- `0x180025b84`

## callees

- `0x180001710`
- `0x180002320`
- `0x180003d5c`
- `0x180004c00`
- `0x180017560`
- `0x18002ff54`
- `0x1800302b8`
- `0x180030324`
- `0x180030434`
- `0x180030474`
- `0x180031b1c`
- `0x180032110`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180031b91`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180031b91`

## pseudocode

```c
__int64 __fastcall HrOpenConnectionKey(const struct _GUID *a1, __int64 a2, REGSAM a3, char a4, __int64 a5, HKEY *a6)
{
  HKEY v10; // rcx
  __int64 v11; // r8
  unsigned int v12; // ebx
  HKEY v13; // rcx
  CIntelliName *v14; // rcx
  const unsigned __int16 *v15; // rdx
  __int64 v16; // r8
  HKEY v17; // rcx
  __int64 v18; // rax
  struct _SECURITY_ATTRIBUTES *v20; // [rsp+20h] [rbp-E0h]
  tagNETCON_MEDIATYPE v21; // [rsp+40h] [rbp-C0h] BYREF
  tagNETCON_MEDIATYPE v22; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v23; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v24[4]; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v26[256]; // [rsp+B0h] [rbp-50h] BYREF

  memset_0(sz, 0, 0x4Eu);
  if ( !a1 )
    return 2147942487LL;
  *a6 = 0;
  StringFromGUID2(a1, sz, 39);
  StringCchPrintfW(
    v26,
    0x100u,
    L"System\\CurrentControlSet\\Control\\Network\\{4D36E972-E325-11CE-BFC1-08002BE10318}\\%s\\Connection",
    sz);
  if ( (a4 & 1) != 0 )
  {
    v23 = 0;
    v12 = HrRegCreateKeyEx(v10, v26, v11, a3, v20, a6, &v23);
    if ( !v12 )
    {
      v13 = *a6;
      v24[0] = 0;
      if ( HrRegQueryDword(v13, L"MediaSubType", v24) == -2147024894 )
      {
        v21 = NCM_NONE;
        v22 = NCM_NONE;
        if ( (int)CIntelliName::HrGetPseudoMediaTypes(v14, a1, &v21, (enum tagNETCON_SUBMEDIATYPE *)&v22) >= 0
          && v22 != NCM_DIRECT )
        {
          v17 = *a6;
          v21 = v22;
          HrRegSetValueEx(v17, v15, v16, (const unsigned __int8 *)&v21);
        }
      }
    }
    return v12;
  }
  if ( (a4 & 2) != 0 )
  {
    v12 = 0;
    v18 = -1;
    do
      ++v18;
    while ( sz[v18] );
    if ( !v18 )
      return v12;
    StringCchCopyW(v26, 0x100u, L"System\\CurrentControlSet\\Control\\Class\\{4D36E972-E325-11CE-BFC1-08002bE10318}");
    StringCchCatW(v26, 0x100u, L"\\");
    StringCchCatW(v26, 0x100u, sz);
    return (unsigned int)HrRegDeleteKeyTree(HKEY_LOCAL_MACHINE, v26);
  }
  else
  {
    return (unsigned int)HrRegOpenKeyEx(HKEY_LOCAL_MACHINE, v26, a3, a6);
  }
}

```

## disassembly

```asm
0x180031b1c  mov     [rsp-8+arg_8], rbx
0x180031b21  mov     [rsp-8+arg_18], rsi
0x180031b26  push    rbp
0x180031b27  push    rdi
0x180031b28  push    r12
0x180031b2a  push    r14
0x180031b2c  push    r15
0x180031b2e  lea     rbp, [rsp-1C0h]
0x180031b36  sub     rsp, 2C0h
0x180031b3d  mov     rax, cs:__security_cookie
0x180031b44  xor     rax, rsp
0x180031b47  mov     [rbp+1E0h+var_30], rax
0x180031b4e  mov     rdi, [rbp+1E0h+arg_28]
0x180031b55  xor     edx, edx; Val
0x180031b57  mov     ebx, r8d
0x180031b5a  mov     r14, rcx
0x180031b5d  lea     rcx, [rsp+2E0h+sz]; void *
0x180031b62  mov     esi, r9d
0x180031b65  lea     r8d, [rdx+4Eh]; Size
0x180031b69  call    memset_0
0x180031b6e  xor     r15d, r15d
0x180031b71  test    r14, r14
0x180031b74  jnz     short loc_180031B80
0x180031b76  mov     eax, 80070057h
0x180031b7b  jmp     loc_180031CD8
0x180031b80  mov     r8d, 27h ; '''; cchMax
0x180031b86  mov     [rdi], r15
0x180031b89  lea     rdx, [rsp+2E0h+sz]; lpsz
0x180031b8e  mov     rcx, r14; rguid
0x180031b91  call    cs:__imp_StringFromGUID2
0x180031b97  mov     r12d, 100h
0x180031b9d  lea     r9, [rsp+2E0h+sz]
0x180031ba2  mov     edx, r12d; unsigned __int64
0x180031ba5  lea     r8, ?c_szRegKeyConFmt@@3QBGB; "System\\CurrentControlSet\\Control\\Net"...
0x180031bac  lea     rcx, [rbp+1E0h+var_230]; unsigned __int16 *
0x180031bb0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180031bb5  test    sil, 1
0x180031bb9  jz      loc_180031C54
0x180031bbf  lea     rax, [rsp+2E0h+var_294]
0x180031bc4  mov     [rsp+2E0h+var_294], r15d
0x180031bc9  mov     [rsp+2E0h+var_2B0], rax; unsigned int *
0x180031bce  lea     rdx, [rbp+1E0h+var_230]; unsigned __int16 *
0x180031bd2  mov     r9d, ebx; unsigned int
0x180031bd5  mov     [rsp+2E0h+var_2B8], rdi; HKEY *
0x180031bda  call    ?HrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; HrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180031bdf  mov     ebx, eax
0x180031be1  test    eax, eax
0x180031be3  jnz     loc_180031CD6
0x180031be9  mov     rcx, [rdi]; HKEY
0x180031bec  lea     r8, [rsp+2E0h+var_290]; unsigned int *
0x180031bf1  lea     rdx, ?c_szRegValueMediaSubType@@3QBGB; "MediaSubType"
0x180031bf8  mov     [rsp+2E0h+var_290], r15d
0x180031bfd  call    ?HrRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; HrRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x180031c02  cmp     eax, 80070002h
0x180031c07  jnz     loc_180031CD6
0x180031c0d  lea     r9, [rsp+2E0h+var_298]; enum tagNETCON_SUBMEDIATYPE *
0x180031c12  mov     [rsp+2E0h+var_2A0], r15d
0x180031c17  lea     r8, [rsp+2E0h+var_2A0]; enum tagNETCON_MEDIATYPE *
0x180031c1c  mov     [rsp+2E0h+var_298], r15d
0x180031c21  mov     rdx, r14; struct _GUID *
0x180031c24  call    ?HrGetPseudoMediaTypes@CIntelliName@@QEBAJAEBU_GUID@@PEAW4tagNETCON_MEDIATYPE@@PEAW4tagNETCON_SUBMEDIATYPE@@@Z; CIntelliName::HrGetPseudoMediaTypes(_GUID const &,tagNETCON_MEDIATYPE *,tagNETCON_SUBMEDIATYPE *)
0x180031c29  test    eax, eax
0x180031c2b  js      loc_180031CD6
0x180031c31  mov     eax, [rsp+2E0h+var_298]
0x180031c35  cmp     eax, 1
0x180031c38  jz      loc_180031CD6
0x180031c3e  mov     rcx, [rdi]; HKEY
0x180031c41  lea     r9, [rsp+2E0h+var_2A0]; unsigned __int8 *
0x180031c46  mov     [rsp+2E0h+var_2A0], eax
0x180031c4a  call    ?HrRegSetValueEx@@YAJPEAUHKEY__@@PEBGKPEBEK@Z; HrRegSetValueEx(HKEY__ *,ushort const *,ulong,uchar const *,ulong)
0x180031c4f  jmp     loc_180031CD6
0x180031c54  test    sil, 2
0x180031c58  jz      short loc_180031CBE
0x180031c5a  mov     ebx, r15d
0x180031c5d  lea     rcx, [rsp+2E0h+sz]
0x180031c62  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031c66  inc     rax
0x180031c69  cmp     [rcx+rax*2], r15w
0x180031c6e  jnz     short loc_180031C66
0x180031c70  test    rax, rax
0x180031c73  jz      short loc_180031CD6
0x180031c75  lea     r8, ?c_szRegKeyNetworkAdapters@@3QBGB; "System\\CurrentControlSet\\Control\\Cla"...
0x180031c7c  mov     rdx, r12; unsigned __int64
0x180031c7f  lea     rcx, [rbp+1E0h+var_230]; unsigned __int16 *
0x180031c83  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031c88  lea     r8, asc_18003AB20; "\\"
0x180031c8f  mov     rdx, r12; unsigned __int64
0x180031c92  lea     rcx, [rbp+1E0h+var_230]; unsigned __int16 *
0x180031c96  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180031c9b  lea     r8, [rsp+2E0h+sz]; unsigned __int16 *
0x180031ca0  mov     rdx, r12; unsigned __int64
0x180031ca3  lea     rcx, [rbp+1E0h+var_230]; unsigned __int16 *
0x180031ca7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180031cac  lea     rdx, [rbp+1E0h+var_230]; unsigned __int16 *
0x180031cb0  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180031cb7  call    ?HrRegDeleteKeyTree@@YAJPEAUHKEY__@@PEBG@Z; HrRegDeleteKeyTree(HKEY__ *,ushort const *)
0x180031cbc  jmp     short loc_180031CD4
0x180031cbe  mov     r9, rdi; HKEY *
0x180031cc1  lea     rdx, [rbp+1E0h+var_230]; unsigned __int16 *
0x180031cc5  mov     r8d, ebx; unsigned int
0x180031cc8  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180031ccf  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x180031cd4  mov     ebx, eax
0x180031cd6  mov     eax, ebx
0x180031cd8  mov     rcx, [rbp+1E0h+var_30]
0x180031cdf  xor     rcx, rsp; StackCookie
0x180031ce2  call    __security_check_cookie
0x180031ce7  lea     r11, [rsp+2E0h+var_20]
0x180031cef  mov     rbx, [r11+38h]
0x180031cf3  mov     rsi, [r11+48h]
0x180031cf7  mov     rsp, r11
0x180031cfa  pop     r15
0x180031cfc  pop     r14
0x180031cfe  pop     r12
0x180031d00  pop     rdi
0x180031d01  pop     rbp
0x180031d02  retn
```
