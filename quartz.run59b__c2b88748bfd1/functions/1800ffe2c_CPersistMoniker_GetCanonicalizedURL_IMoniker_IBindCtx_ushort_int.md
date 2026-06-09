# CPersistMoniker::GetCanonicalizedURL(IMoniker *,IBindCtx *,ushort * *,int *)

- ea: `0x1800ffe2c`
- end: `0x180100038`
- name: `?GetCanonicalizedURL@CPersistMoniker@@AEAAJPEAUIMoniker@@PEAUIBindCtx@@PEAPEAGPEAH@Z`
- size: `524`
- prototype: `__int64 __fastcall(CPersistMoniker *__hidden this, struct IMoniker *, struct IBindCtx *, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180100080`

## callees

- `0x1800078b0`
- `0x1800388a0`
- `0x1800589cc`
- `0x1800ffe2c`
- `0x18015bb20`
- `0x18015bb8c`
- `0x18015e010`

## import_xrefs

- `KERNEL32!SetErrorMode` at `0x1800ffe81`
- `KERNEL32!SetErrorMode` at `0x1800ffeaf`
- `KERNEL32!SetErrorMode` at `0x1800ffe81`
- `KERNEL32!SetErrorMode` at `0x1800ffeaf`
- `KERNEL32!LoadLibraryExW` at `0x1800ffe9e`
- `KERNEL32!LoadLibraryExW` at `0x1800ffe9e`
- `KERNEL32!GetProcAddress` at `0x1800ffed4`
- `KERNEL32!GetProcAddress` at `0x1800ffed4`
- `ole32!CoTaskMemFree` at `0x1800fffff`
- `ole32!CoTaskMemFree` at `0x1800fffff`

## string_xrefs

- `0x1800ffe8f`: `WININET.DLL`

## pseudocode

```c
__int64 __fastcall CPersistMoniker::GetCanonicalizedURL(
        CPersistMoniker *this,
        struct IMoniker *a2,
        struct IBindCtx *a3,
        LPVOID *a4,
        int *a5)
{
  UINT v8; // ebx
  HMODULE Library; // rsi
  int v10; // ebx
  FARPROC ProcAddress; // rsi
  const unsigned __int16 *v12; // r8
  unsigned __int16 *v13; // rcx
  __int64 v14; // rdx
  unsigned __int16 *v15; // rdx
  unsigned __int16 i; // ax
  bool v17; // zf
  int v18; // eax
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  struct _GUID Buf1; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v22[2088]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v23[2088]; // [rsp+10A0h] [rbp+FA0h] BYREF

  *a5 = 0;
  *a4 = 0;
  v8 = SetErrorMode(0x8000u);
  Library = LoadLibraryExW(L"WININET.DLL", 0, 0x800u);
  SetErrorMode(v8);
  if ( !Library || (ProcAddress = GetProcAddress(Library, "InternetCanonicalizeUrlW")) == 0 )
  {
    v10 = -2147467260;
    goto LABEL_20;
  }
  v10 = ((__int64 (__fastcall *)(struct IMoniker *, struct IBindCtx *, _QWORD, LPVOID *))a2->lpVtbl->GetDisplayName)(
          a2,
          a3,
          0,
          a4);
  if ( v10 < 0 || (v12 = (const unsigned __int16 *)*a4, v20 = 2084, v10 = StringCchCopyW(v23, 0x824u, v12), v10 < 0) )
  {
LABEL_20:
    if ( *a4 )
      CoTaskMemFree(*a4);
    return (unsigned int)v10;
  }
  if ( !((unsigned int (__fastcall *)(unsigned __int16 *, unsigned __int16 *, int *, __int64))ProcAddress)(
          v23,
          v22,
          &v20,
          805306368) )
  {
    v10 = -2147012891;
    goto LABEL_20;
  }
  v13 = (unsigned __int16 *)*a4;
  v14 = -1;
  do
    ++v14;
  while ( v13[v14] );
  v10 = StringCchCopyW(v13, v14 + 1, v22);
  v15 = v22;
  for ( i = v22[0]; i && i != 92 && i != 58; i = *v15 )
    ++v15;
  if ( *v15 != 58
    || (Buf1 = 0, (int)GetURLSource(v22, v15 - v22, &Buf1) < 0)
    || (v17 = memcmp_0(&Buf1, &CLSID_URLReader, 0x10u) == 0, v18 = 1, v17) )
  {
    v18 = 0;
  }
  *a5 = v18;
  if ( v10 < 0 )
    goto LABEL_20;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800ffe2c  mov     [rsp-8+arg_0], rbx
0x1800ffe31  push    rbp
0x1800ffe32  push    rsi
0x1800ffe33  push    rdi
0x1800ffe34  push    r12
0x1800ffe36  push    r13
0x1800ffe38  push    r14
0x1800ffe3a  push    r15
0x1800ffe3c  lea     rbp, [rsp-2000h]
0x1800ffe44  mov     eax, 2100h
0x1800ffe49  call    _alloca_probe
0x1800ffe4e  sub     rsp, rax
0x1800ffe51  mov     rax, cs:__security_cookie
0x1800ffe58  xor     rax, rsp
0x1800ffe5b  mov     [rbp+2030h+var_40], rax
0x1800ffe62  mov     r12, [rbp+2030h+arg_20]
0x1800ffe69  xor     r13d, r13d
0x1800ffe6c  mov     ecx, 8000h; uMode
0x1800ffe71  mov     rdi, r9
0x1800ffe74  mov     r15, r8
0x1800ffe77  mov     r14, rdx
0x1800ffe7a  mov     [r12], r13d
0x1800ffe7e  mov     [r9], r13
0x1800ffe81  call    cs:__imp_SetErrorMode
0x1800ffe88  nop     dword ptr [rax+rax+00h]
0x1800ffe8d  xor     edx, edx; hFile
0x1800ffe8f  lea     rcx, aWininetDll; "WININET.DLL"
0x1800ffe96  mov     r8d, 800h; dwFlags
0x1800ffe9c  mov     ebx, eax
0x1800ffe9e  call    cs:__imp_LoadLibraryExW
0x1800ffea5  nop     dword ptr [rax+rax+00h]
0x1800ffeaa  mov     ecx, ebx; uMode
0x1800ffeac  mov     rsi, rax
0x1800ffeaf  call    cs:__imp_SetErrorMode
0x1800ffeb6  nop     dword ptr [rax+rax+00h]
0x1800ffebb  test    rsi, rsi
0x1800ffebe  jnz     short loc_1800FFECA
0x1800ffec0  mov     ebx, 80004004h
0x1800ffec5  jmp     loc_1800FFFF7
0x1800ffeca  lea     rdx, aInternetcanoni; "InternetCanonicalizeUrlW"
0x1800ffed1  mov     rcx, rsi; hModule
0x1800ffed4  call    cs:__imp_GetProcAddress
0x1800ffedb  nop     dword ptr [rax+rax+00h]
0x1800ffee0  mov     rsi, rax
0x1800ffee3  test    rax, rax
0x1800ffee6  jz      short loc_1800FFEC0
0x1800ffee8  mov     rax, [r14]
0x1800ffeeb  mov     r9, rdi
0x1800ffeee  xor     r8d, r8d
0x1800ffef1  mov     rdx, r15
0x1800ffef4  mov     rcx, r14
0x1800ffef7  mov     rax, [rax+0A0h]
0x1800ffefe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fff03  mov     ebx, eax
0x1800fff05  test    eax, eax
0x1800fff07  js      loc_1800FFFF7
0x1800fff0d  mov     r8, [rdi]; unsigned __int16 *
0x1800fff10  lea     rcx, [rbp+2030h+var_1090]; unsigned __int16 *
0x1800fff17  mov     edx, 824h; unsigned __int64
0x1800fff1c  mov     [rsp+2130h+var_2100], edx
0x1800fff20  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800fff25  mov     ebx, eax
0x1800fff27  test    eax, eax
0x1800fff29  js      loc_1800FFFF7
0x1800fff2f  mov     r9d, 30000000h
0x1800fff35  lea     r8, [rsp+2130h+var_2100]
0x1800fff3a  lea     rdx, [rsp+2130h+var_20E0]
0x1800fff3f  mov     rax, rsi
0x1800fff42  lea     rcx, [rbp+2030h+var_1090]
0x1800fff49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fff4e  test    eax, eax
0x1800fff50  jnz     short loc_1800FFF5C
0x1800fff52  mov     ebx, 80072EE5h
0x1800fff57  jmp     loc_1800FFFF7
0x1800fff5c  mov     rcx, [rdi]; unsigned __int16 *
0x1800fff5f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800fff63  inc     rdx
0x1800fff66  cmp     [rcx+rdx*2], r13w
0x1800fff6b  jnz     short loc_1800FFF63
0x1800fff6d  inc     rdx; unsigned __int64
0x1800fff70  lea     r8, [rsp+2130h+var_20E0]; unsigned __int16 *
0x1800fff75  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800fff7a  mov     ebx, eax
0x1800fff7c  lea     rdx, [rsp+2130h+var_20E0]
0x1800fff81  movzx   eax, [rsp+2130h+var_20E0]
0x1800fff86  jmp     short loc_1800FFF9B
0x1800fff88  cmp     ax, 5Ch ; '\'
0x1800fff8c  jz      short loc_1800FFFA0
0x1800fff8e  cmp     ax, 3Ah ; ':'
0x1800fff92  jz      short loc_1800FFFA0
0x1800fff94  add     rdx, 2
0x1800fff98  movzx   eax, word ptr [rdx]
0x1800fff9b  test    ax, ax
0x1800fff9e  jnz     short loc_1800FFF88
0x1800fffa0  cmp     word ptr [rdx], 3Ah ; ':'
0x1800fffa4  jnz     short loc_1800FFFEC
0x1800fffa6  lea     rax, [rsp+2130h+var_20E0]
0x1800fffab  xorps   xmm0, xmm0
0x1800fffae  sub     rdx, rax
0x1800fffb1  lea     r8, [rsp+2130h+Buf1]; struct _GUID *
0x1800fffb6  sar     rdx, 1; int
0x1800fffb9  lea     rcx, [rsp+2130h+var_20E0]; unsigned __int16 *
0x1800fffbe  movups  xmmword ptr [rsp+2130h+Buf1.Data1], xmm0
0x1800fffc3  call    ?GetURLSource@@YAJPEBGHPEAU_GUID@@@Z; GetURLSource(ushort const *,int,_GUID *)
0x1800fffc8  test    eax, eax
0x1800fffca  js      short loc_1800FFFEC
0x1800fffcc  mov     r8d, 10h; Size
0x1800fffd2  lea     rdx, CLSID_URLReader; Buf2
0x1800fffd9  lea     rcx, [rsp+2130h+Buf1]; Buf1
0x1800fffde  call    memcmp_0
0x1800fffe3  test    eax, eax
0x1800fffe5  mov     eax, 1
0x1800fffea  jnz     short loc_1800FFFEF
0x1800fffec  mov     eax, r13d
0x1800fffef  mov     [r12], eax
0x1800ffff3  test    ebx, ebx
0x1800ffff5  jns     short loc_18010000B
0x1800ffff7  mov     rcx, [rdi]; pv
0x1800ffffa  test    rcx, rcx
0x1800ffffd  jz      short loc_18010000B
0x1800fffff  call    cs:__imp_CoTaskMemFree
0x180100006  nop     dword ptr [rax+rax+00h]
0x18010000b  mov     eax, ebx
0x18010000d  mov     rcx, [rbp+2030h+var_40]
0x180100014  xor     rcx, rsp; StackCookie
0x180100017  call    __security_check_cookie
0x18010001c  mov     rbx, [rsp+2130h+arg_0]
0x180100024  add     rsp, 2100h
0x18010002b  pop     r15
0x18010002d  pop     r14
0x18010002f  pop     r13
0x180100031  pop     r12
0x180100033  pop     rdi
0x180100034  pop     rsi
0x180100035  pop     rbp
0x180100036  retn
```
