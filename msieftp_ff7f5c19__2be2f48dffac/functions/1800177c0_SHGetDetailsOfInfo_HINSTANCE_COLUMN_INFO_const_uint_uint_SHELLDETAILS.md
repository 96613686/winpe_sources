# SHGetDetailsOfInfo(HINSTANCE__ *,COLUMN_INFO const *,uint,uint,_SHELLDETAILS *)

- ea: `0x1800177c0`
- end: `0x180017931`
- name: `?SHGetDetailsOfInfo@@YAJPEAUHINSTANCE__@@PEBUCOLUMN_INFO@@IIPEAU_SHELLDETAILS@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(HINSTANCE, const struct COLUMN_INFO *, unsigned int, unsigned int, struct _SHELLDETAILS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016a00`

## callees

- `0x180002240`
- `0x1800177c0`
- `0x180028010`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x18001783b`
- `SHLWAPI!SHStrDupW` at `0x1800178c2`
- `SHLWAPI!SHStrDupW` at `0x1800178fc`
- `SHLWAPI!SHStrDupW` at `0x18001783b`
- `SHLWAPI!SHStrDupW` at `0x1800178c2`
- `SHLWAPI!SHStrDupW` at `0x1800178fc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001782c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001782c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001786f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001786f`

## pseudocode

```c
__int64 __fastcall SHGetDetailsOfInfo(
        HINSTANCE a1,
        const struct COLUMN_INFO *a2,
        __int64 a3,
        unsigned int a4,
        struct _SHELLDETAILS *a5)
{
  __int64 v5; // rsi
  UINT v6; // edx
  HRESULT v7; // ebx
  LPVOID ppv; // [rsp+40h] [rbp-248h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-238h] BYREF

  if ( a4 >= 6 )
    return (unsigned int)-2147467263;
  v5 = 32LL * a4;
  a5->fmt = *(_DWORD *)((char *)&off_180029880 + v5 + 12);
  a5->cxChar = *(_DWORD *)((char *)&off_180029880 + v5 + 16);
  v6 = *(_DWORD *)((char *)&off_180029880 + v5 + 24);
  if ( v6 )
  {
    a5->str.uType = 0;
    LoadStringW(a1, v6, Buffer, 260);
    v7 = SHStrDupW(Buffer, &a5->str.pOleStr);
    goto LABEL_8;
  }
  ppv = 0;
  v7 = CoCreateInstance(&CLSID_PropertiesUI, 0, 1u, &GUID_757a7d9f_919a_4118_99d7_dbb208c8cc66, &ppv);
  if ( v7 >= 0 )
  {
    _mm_lfence();
    v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, WCHAR *, int))(*(_QWORD *)ppv + 40LL))(
           ppv,
           *(PROPERTYKEY **)((char *)&off_180029880 + v5),
           (*(PROPERTYKEY **)((char *)&off_180029880 + v5))->pid,
           0,
           Buffer,
           128);
    if ( v7 >= 0 )
    {
      a5->str.uType = 0;
      v7 = SHStrDupW(Buffer, &a5->str.pOleStr);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_8:
    if ( v7 >= 0 )
      return (unsigned int)v7;
  }
  if ( (*(_DWORD *)((_BYTE *)&off_180029880 + v5 + 20) & 0x100) != 0 )
  {
    a5->str.uType = 0;
    return (unsigned int)SHStrDupW(&lParam, &a5->str.pOleStr);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800177c0  mov     [rsp+arg_8], rbx
0x1800177c5  push    rsi
0x1800177c6  push    rdi
0x1800177c7  push    r14
0x1800177c9  sub     rsp, 270h
0x1800177d0  mov     rax, cs:__security_cookie
0x1800177d7  xor     rax, rsp
0x1800177da  mov     [rsp+288h+var_28], rax
0x1800177e2  mov     rdi, [rsp+288h+arg_20]
0x1800177ea  cmp     r9d, 6
0x1800177ee  jnb     loc_180017906
0x1800177f4  lea     r14, off_180029880
0x1800177fb  mov     esi, r9d
0x1800177fe  shl     rsi, 5
0x180017802  mov     eax, [rsi+r14+0Ch]
0x180017807  mov     [rdi], eax
0x180017809  mov     eax, [rsi+r14+10h]
0x18001780e  mov     [rdi+4], eax
0x180017811  mov     edx, [rsi+r14+18h]; uID
0x180017816  test    edx, edx
0x180017818  jz      short loc_180017848
0x18001781a  mov     r9d, 104h; cchBufferMax
0x180017820  mov     dword ptr [rdi+8], 0
0x180017827  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x18001782c  call    cs:__imp_LoadStringW
0x180017832  lea     rdx, [rdi+10h]; ppwsz
0x180017836  lea     rcx, [rsp+288h+Buffer]; psz
0x18001783b  call    cs:__imp_SHStrDupW
0x180017841  mov     ebx, eax
0x180017843  jmp     loc_1800178DB
0x180017848  xor     edx, edx; pUnkOuter
0x18001784a  mov     [rsp+288h+var_248], 0
0x180017853  lea     rax, [rsp+288h+var_248]
0x180017858  lea     r9, _GUID_757a7d9f_919a_4118_99d7_dbb208c8cc66; riid
0x18001785f  mov     [rsp+288h+ppv], rax; ppv
0x180017864  lea     rcx, CLSID_PropertiesUI; rclsid
0x18001786b  lea     r8d, [rdx+1]; dwClsContext
0x18001786f  call    cs:__imp_CoCreateInstance
0x180017875  mov     ebx, eax
0x180017877  test    eax, eax
0x180017879  js      short loc_1800178DF
0x18001787b  lfence
0x18001787e  mov     rcx, [rsp+288h+var_248]
0x180017883  lea     r8, [rsp+288h+Buffer]
0x180017888  mov     rdx, [rsi+r14]
0x18001788c  xor     r9d, r9d
0x18001788f  mov     [rsp+288h+var_260], 80h
0x180017897  mov     [rsp+288h+ppv], r8
0x18001789c  mov     rax, [rcx]
0x18001789f  mov     r8d, [rdx+10h]
0x1800178a3  mov     rax, [rax+28h]
0x1800178a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178ac  mov     ebx, eax
0x1800178ae  test    eax, eax
0x1800178b0  js      short loc_1800178CA
0x1800178b2  lea     rdx, [rdi+10h]; ppwsz
0x1800178b6  mov     dword ptr [rdi+8], 0
0x1800178bd  lea     rcx, [rsp+288h+Buffer]; psz
0x1800178c2  call    cs:__imp_SHStrDupW
0x1800178c8  mov     ebx, eax
0x1800178ca  mov     rcx, [rsp+288h+var_248]
0x1800178cf  mov     rax, [rcx]
0x1800178d2  mov     rax, [rax+10h]
0x1800178d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178db  test    ebx, ebx
0x1800178dd  jns     short loc_18001790B
0x1800178df  test    dword ptr [rsi+r14+14h], 100h
0x1800178e8  jz      short loc_18001790B
0x1800178ea  lea     rdx, [rdi+10h]; ppwsz
0x1800178ee  mov     dword ptr [rdi+8], 0
0x1800178f5  lea     rcx, lParam; psz
0x1800178fc  call    cs:__imp_SHStrDupW
0x180017902  mov     ebx, eax
0x180017904  jmp     short loc_18001790B
0x180017906  mov     ebx, 80004001h
0x18001790b  mov     eax, ebx
0x18001790d  mov     rcx, [rsp+288h+var_28]
0x180017915  xor     rcx, rsp; StackCookie
0x180017918  call    __security_check_cookie
0x18001791d  mov     rbx, [rsp+288h+arg_8]
0x180017925  add     rsp, 270h
0x18001792c  pop     r14
0x18001792e  pop     rdi
0x18001792f  pop     rsi
0x180017930  retn
```
