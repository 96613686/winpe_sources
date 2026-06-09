# SHGetDetailsOfInfo(HINSTANCE__ *,COLUMN_INFO const *,uint,uint,_SHELLDETAILS *)

- ea: `0x180018b14`
- end: `0x180018c85`
- name: `?SHGetDetailsOfInfo@@YAJPEAUHINSTANCE__@@PEBUCOLUMN_INFO@@IIPEAU_SHELLDETAILS@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(HINSTANCE, const struct COLUMN_INFO *, unsigned int, unsigned int, struct _SHELLDETAILS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800164c0`

## callees

- `0x180018b14`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180018b8f`
- `SHLWAPI!SHStrDupW` at `0x180018c16`
- `SHLWAPI!SHStrDupW` at `0x180018c50`
- `SHLWAPI!SHStrDupW` at `0x180018b8f`
- `SHLWAPI!SHStrDupW` at `0x180018c16`
- `SHLWAPI!SHStrDupW` at `0x180018c50`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180018b80`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180018b80`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018bc3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018bc3`

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

  if ( a4 >= 0xF )
    return (unsigned int)-2147467263;
  v5 = 32LL * a4;
  a5->fmt = *(_DWORD *)((char *)&off_180035380 + v5 + 12);
  a5->cxChar = *(_DWORD *)((char *)&off_180035380 + v5 + 16);
  v6 = *(_DWORD *)((char *)&off_180035380 + v5 + 24);
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
           *(PROPERTYKEY **)((char *)&off_180035380 + v5),
           (*(PROPERTYKEY **)((char *)&off_180035380 + v5))->pid,
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
  if ( (*(_DWORD *)((_BYTE *)&off_180035380 + v5 + 20) & 0x100) != 0 )
  {
    a5->str.uType = 0;
    return (unsigned int)SHStrDupW(&psz, &a5->str.pOleStr);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180018b14  mov     [rsp+arg_8], rbx
0x180018b19  push    rsi
0x180018b1a  push    rdi
0x180018b1b  push    r14
0x180018b1d  sub     rsp, 270h
0x180018b24  mov     rax, cs:__security_cookie
0x180018b2b  xor     rax, rsp
0x180018b2e  mov     [rsp+288h+var_28], rax
0x180018b36  mov     rdi, [rsp+288h+arg_20]
0x180018b3e  cmp     r9d, 0Fh
0x180018b42  jnb     loc_180018C5A
0x180018b48  lea     r14, off_180035380
0x180018b4f  mov     esi, r9d
0x180018b52  shl     rsi, 5
0x180018b56  mov     eax, [rsi+r14+0Ch]
0x180018b5b  mov     [rdi], eax
0x180018b5d  mov     eax, [rsi+r14+10h]
0x180018b62  mov     [rdi+4], eax
0x180018b65  mov     edx, [rsi+r14+18h]; uID
0x180018b6a  test    edx, edx
0x180018b6c  jz      short loc_180018B9C
0x180018b6e  mov     r9d, 104h; cchBufferMax
0x180018b74  mov     dword ptr [rdi+8], 0
0x180018b7b  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x180018b80  call    cs:__imp_LoadStringW
0x180018b86  lea     rdx, [rdi+10h]; ppwsz
0x180018b8a  lea     rcx, [rsp+288h+Buffer]; psz
0x180018b8f  call    cs:__imp_SHStrDupW
0x180018b95  mov     ebx, eax
0x180018b97  jmp     loc_180018C2F
0x180018b9c  xor     edx, edx; pUnkOuter
0x180018b9e  mov     [rsp+288h+var_248], 0
0x180018ba7  lea     rax, [rsp+288h+var_248]
0x180018bac  lea     r9, _GUID_757a7d9f_919a_4118_99d7_dbb208c8cc66; riid
0x180018bb3  mov     [rsp+288h+ppv], rax; ppv
0x180018bb8  lea     rcx, CLSID_PropertiesUI; rclsid
0x180018bbf  lea     r8d, [rdx+1]; dwClsContext
0x180018bc3  call    cs:__imp_CoCreateInstance
0x180018bc9  mov     ebx, eax
0x180018bcb  test    eax, eax
0x180018bcd  js      short loc_180018C33
0x180018bcf  lfence
0x180018bd2  mov     rcx, [rsp+288h+var_248]
0x180018bd7  lea     r8, [rsp+288h+Buffer]
0x180018bdc  mov     rdx, [rsi+r14]
0x180018be0  xor     r9d, r9d
0x180018be3  mov     [rsp+288h+var_260], 80h
0x180018beb  mov     [rsp+288h+ppv], r8
0x180018bf0  mov     rax, [rcx]
0x180018bf3  mov     r8d, [rdx+10h]
0x180018bf7  mov     rax, [rax+28h]
0x180018bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c00  mov     ebx, eax
0x180018c02  test    eax, eax
0x180018c04  js      short loc_180018C1E
0x180018c06  lea     rdx, [rdi+10h]; ppwsz
0x180018c0a  mov     dword ptr [rdi+8], 0
0x180018c11  lea     rcx, [rsp+288h+Buffer]; psz
0x180018c16  call    cs:__imp_SHStrDupW
0x180018c1c  mov     ebx, eax
0x180018c1e  mov     rcx, [rsp+288h+var_248]
0x180018c23  mov     rax, [rcx]
0x180018c26  mov     rax, [rax+10h]
0x180018c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c2f  test    ebx, ebx
0x180018c31  jns     short loc_180018C5F
0x180018c33  test    dword ptr [rsi+r14+14h], 100h
0x180018c3c  jz      short loc_180018C5F
0x180018c3e  lea     rdx, [rdi+10h]; ppwsz
0x180018c42  mov     dword ptr [rdi+8], 0
0x180018c49  lea     rcx, psz; psz
0x180018c50  call    cs:__imp_SHStrDupW
0x180018c56  mov     ebx, eax
0x180018c58  jmp     short loc_180018C5F
0x180018c5a  mov     ebx, 80004001h
0x180018c5f  mov     eax, ebx
0x180018c61  mov     rcx, [rsp+288h+var_28]
0x180018c69  xor     rcx, rsp; StackCookie
0x180018c6c  call    __security_check_cookie
0x180018c71  mov     rbx, [rsp+288h+arg_8]
0x180018c79  add     rsp, 270h
0x180018c80  pop     r14
0x180018c82  pop     rdi
0x180018c83  pop     rsi
0x180018c84  retn
```
