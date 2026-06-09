# SHGetDetailsOfInfo(HINSTANCE__ *,COLUMN_INFO const *,uint,uint,_SHELLDETAILS *)

- ea: `0x18000f24c`
- end: `0x18000f3bd`
- name: `?SHGetDetailsOfInfo@@YAJPEAUHINSTANCE__@@PEBUCOLUMN_INFO@@IIPEAU_SHELLDETAILS@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(HINSTANCE, const struct COLUMN_INFO *, unsigned int, unsigned int, struct _SHELLDETAILS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e4f0`

## callees

- `0x180002620`
- `0x18000f24c`
- `0x180013010`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x18000f2c7`
- `SHLWAPI!SHStrDupW` at `0x18000f34e`
- `SHLWAPI!SHStrDupW` at `0x18000f388`
- `SHLWAPI!SHStrDupW` at `0x18000f2c7`
- `SHLWAPI!SHStrDupW` at `0x18000f34e`
- `SHLWAPI!SHStrDupW` at `0x18000f388`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000f2b8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000f2b8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f2fb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f2fb`

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

  if ( a4 >= 5 )
    return (unsigned int)-2147467263;
  v5 = 32LL * a4;
  a5->fmt = *(_DWORD *)((char *)&off_180014560 + v5 + 12);
  a5->cxChar = *(_DWORD *)((char *)&off_180014560 + v5 + 16);
  v6 = *(_DWORD *)((char *)&off_180014560 + v5 + 24);
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
           *(PROPERTYKEY **)((char *)&off_180014560 + v5),
           (*(PROPERTYKEY **)((char *)&off_180014560 + v5))->pid,
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
  if ( (*(_DWORD *)((_BYTE *)&off_180014560 + v5 + 20) & 0x100) != 0 )
  {
    a5->str.uType = 0;
    return (unsigned int)SHStrDupW(&psz, &a5->str.pOleStr);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000f24c  mov     [rsp+arg_8], rbx
0x18000f251  push    rsi
0x18000f252  push    rdi
0x18000f253  push    r14
0x18000f255  sub     rsp, 270h
0x18000f25c  mov     rax, cs:__security_cookie
0x18000f263  xor     rax, rsp
0x18000f266  mov     [rsp+288h+var_28], rax
0x18000f26e  mov     rdi, [rsp+288h+arg_20]
0x18000f276  cmp     r9d, 5
0x18000f27a  jnb     loc_18000F392
0x18000f280  lea     r14, off_180014560
0x18000f287  mov     esi, r9d
0x18000f28a  shl     rsi, 5
0x18000f28e  mov     eax, [rsi+r14+0Ch]
0x18000f293  mov     [rdi], eax
0x18000f295  mov     eax, [rsi+r14+10h]
0x18000f29a  mov     [rdi+4], eax
0x18000f29d  mov     edx, [rsi+r14+18h]; uID
0x18000f2a2  test    edx, edx
0x18000f2a4  jz      short loc_18000F2D4
0x18000f2a6  mov     r9d, 104h; cchBufferMax
0x18000f2ac  mov     dword ptr [rdi+8], 0
0x18000f2b3  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x18000f2b8  call    cs:__imp_LoadStringW
0x18000f2be  lea     rdx, [rdi+10h]; ppwsz
0x18000f2c2  lea     rcx, [rsp+288h+Buffer]; psz
0x18000f2c7  call    cs:__imp_SHStrDupW
0x18000f2cd  mov     ebx, eax
0x18000f2cf  jmp     loc_18000F367
0x18000f2d4  xor     edx, edx; pUnkOuter
0x18000f2d6  mov     [rsp+288h+var_248], 0
0x18000f2df  lea     rax, [rsp+288h+var_248]
0x18000f2e4  lea     r9, _GUID_757a7d9f_919a_4118_99d7_dbb208c8cc66; riid
0x18000f2eb  mov     [rsp+288h+ppv], rax; ppv
0x18000f2f0  lea     rcx, CLSID_PropertiesUI; rclsid
0x18000f2f7  lea     r8d, [rdx+1]; dwClsContext
0x18000f2fb  call    cs:__imp_CoCreateInstance
0x18000f301  mov     ebx, eax
0x18000f303  test    eax, eax
0x18000f305  js      short loc_18000F36B
0x18000f307  lfence
0x18000f30a  mov     rcx, [rsp+288h+var_248]
0x18000f30f  lea     r8, [rsp+288h+Buffer]
0x18000f314  mov     rdx, [rsi+r14]
0x18000f318  xor     r9d, r9d
0x18000f31b  mov     [rsp+288h+var_260], 80h
0x18000f323  mov     [rsp+288h+ppv], r8
0x18000f328  mov     rax, [rcx]
0x18000f32b  mov     r8d, [rdx+10h]
0x18000f32f  mov     rax, [rax+28h]
0x18000f333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f338  mov     ebx, eax
0x18000f33a  test    eax, eax
0x18000f33c  js      short loc_18000F356
0x18000f33e  lea     rdx, [rdi+10h]; ppwsz
0x18000f342  mov     dword ptr [rdi+8], 0
0x18000f349  lea     rcx, [rsp+288h+Buffer]; psz
0x18000f34e  call    cs:__imp_SHStrDupW
0x18000f354  mov     ebx, eax
0x18000f356  mov     rcx, [rsp+288h+var_248]
0x18000f35b  mov     rax, [rcx]
0x18000f35e  mov     rax, [rax+10h]
0x18000f362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f367  test    ebx, ebx
0x18000f369  jns     short loc_18000F397
0x18000f36b  test    dword ptr [rsi+r14+14h], 100h
0x18000f374  jz      short loc_18000F397
0x18000f376  lea     rdx, [rdi+10h]; ppwsz
0x18000f37a  mov     dword ptr [rdi+8], 0
0x18000f381  lea     rcx, psz; psz
0x18000f388  call    cs:__imp_SHStrDupW
0x18000f38e  mov     ebx, eax
0x18000f390  jmp     short loc_18000F397
0x18000f392  mov     ebx, 80004001h
0x18000f397  mov     eax, ebx
0x18000f399  mov     rcx, [rsp+288h+var_28]
0x18000f3a1  xor     rcx, rsp; StackCookie
0x18000f3a4  call    __security_check_cookie
0x18000f3a9  mov     rbx, [rsp+288h+arg_8]
0x18000f3b1  add     rsp, 270h
0x18000f3b8  pop     r14
0x18000f3ba  pop     rdi
0x18000f3bb  pop     rsi
0x18000f3bc  retn
```
