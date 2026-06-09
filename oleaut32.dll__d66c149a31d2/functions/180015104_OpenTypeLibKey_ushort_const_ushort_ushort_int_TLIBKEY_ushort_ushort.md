# OpenTypeLibKey(ushort const *,ushort,ushort,int,TLIBKEY *,ushort *,ushort *)

- ea: `0x180015104`
- end: `0x1800153b6`
- name: `?OpenTypeLibKey@@YAJPEBGGGHPEAUTLIBKEY@@PEAG2@Z`
- size: `690`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpSubKey@<rcx>, unsigned __int16@<dx>, unsigned __int16@<r8w>, int@<r9d>, struct TLIBKEY *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014f30`
- `0x180042400`

## callees

- `0x180012750`
- `0x180015104`
- `0x18004d900`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800151c0`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800151ee`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800151c0`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800151ee`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180015346`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001536b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180015346`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001536b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800152f4`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180015314`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800152f4`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180015314`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800152a9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800152a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001539c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800153a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001539c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800153a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015199`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001520e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800152d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015199`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001520e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800152d7`

## pseudocode

```c
__int64 __fastcall OpenTypeLibKey(
        LPCWSTR lpSubKey,
        int a2,
        unsigned __int16 a3,
        int a4,
        HKEY *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7)
{
  unsigned __int16 *v7; // r12
  unsigned int v9; // r14d
  unsigned int v11; // r15d
  __int64 result; // rax
  bool v13; // sf
  WCHAR *i; // rdx
  unsigned __int16 v15; // bx
  unsigned __int16 v16; // di
  DWORD v17; // r12d
  unsigned __int16 v18; // si
  unsigned __int16 v19; // dx
  HKEY phkResult; // [rsp+40h] [rbp-61h] BYREF
  unsigned int v21; // [rsp+48h] [rbp-59h]
  HKEY hKey; // [rsp+50h] [rbp-51h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-49h] BYREF
  int v24; // [rsp+5Ch] [rbp-45h]
  wchar_t *EndPtr; // [rsp+60h] [rbp-41h] BYREF
  unsigned __int16 *v26; // [rsp+68h] [rbp-39h]
  unsigned __int16 *v27; // [rsp+70h] [rbp-31h]
  WCHAR SubKey[12]; // [rsp+78h] [rbp-29h] BYREF
  WCHAR v29[12]; // [rsp+90h] [rbp-11h] BYREF

  v7 = a7;
  v9 = a3;
  v27 = a6;
  v26 = a7;
  EndPtr = 0;
  hKey = 0;
  phkResult = 0;
  v24 = a4;
  v11 = (unsigned __int16)a2;
  result = OpenClassesRootKeyExW(L"TypeLib", a2, &hKey);
  v13 = (int)result < 0;
  if ( (int)result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v13 = (int)result < 0;
  }
  if ( v13 )
    return result;
  if ( RegOpenKeyExW(hKey, lpSubKey, 0, 0x2000000u, &phkResult) )
  {
LABEL_32:
    RegCloseKey(hKey);
    return 2147647517LL;
  }
  if ( a4 )
  {
    v15 = 0;
  }
  else
  {
    _o__ultow_s(v11, SubKey, 5, 16);
    for ( i = SubKey; *i; ++i )
      ;
    *i = 46;
    _o__ultow_s(v9, i + 1, 5, 16);
    v15 = v9;
    if ( !RegOpenKeyExW(phkResult, SubKey, 0, 0x2000000u, a5 + 2) )
    {
      v16 = v11;
      goto LABEL_10;
    }
  }
  v16 = 0;
  v29[0] = 0;
  v17 = 0;
  v21 = 0;
  while ( 1 )
  {
    cchName = 10;
    if ( RegEnumKeyExW(phkResult, v17, SubKey, &cchName, 0, 0, 0, 0) )
      break;
    v18 = wcstoul(SubKey, &EndPtr, 16);
    if ( *EndPtr != 46 )
      goto LABEL_27;
    v19 = wcstoul(EndPtr + 1, 0, 16);
    if ( v24 )
    {
      if ( (v19 | (v18 << 16)) > v21 )
      {
        v21 = v19 | (v18 << 16);
LABEL_26:
        v15 = v19;
        v16 = v18;
        _o_wcscpy_s(v29, 10, SubKey);
      }
    }
    else if ( v18 == (_WORD)v11 )
    {
      if ( v19 == (_WORD)v9 )
      {
        v16 = v11;
        v15 = v9;
        _o_wcscpy_s(v29, 10, SubKey);
        break;
      }
      if ( v19 > v15 )
        goto LABEL_26;
    }
LABEL_27:
    ++v17;
  }
  if ( !v29[0] )
  {
    RegCloseKey(phkResult);
    goto LABEL_32;
  }
  RegOpenKeyExW(phkResult, v29, 0, 0x2000000u, a5 + 2);
  v7 = v26;
LABEL_10:
  *a5 = hKey;
  a5[1] = phkResult;
  if ( v27 )
    *v27 = v16;
  if ( v7 )
    *v7 = v15;
  return 0;
}

```

## disassembly

```asm
0x180015104  mov     [rsp-8+arg_18], rbx
0x180015109  push    rbp
0x18001510a  push    rsi
0x18001510b  push    rdi
0x18001510c  push    r12
0x18001510e  push    r13
0x180015110  push    r14
0x180015112  push    r15
0x180015114  lea     rbp, [rsp-0Fh]
0x180015119  sub     rsp, 0B0h
0x180015120  mov     rax, cs:__security_cookie
0x180015127  xor     rax, rsp
0x18001512a  mov     [rbp+3Fh+var_38], rax
0x18001512e  mov     rax, [rbp+3Fh+arg_28]
0x180015132  xor     esi, esi
0x180015134  mov     r12, [rbp+3Fh+arg_30]
0x180015138  mov     rbx, rcx
0x18001513b  mov     r13, [rbp+3Fh+arg_20]
0x18001513f  lea     rcx, ?TypeLib@Constants@Catalog@Com@@3QBGB; "TypeLib"
0x180015146  movzx   r14d, r8w
0x18001514a  mov     edi, r9d
0x18001514d  lea     r8, [rbp+3Fh+hKey]
0x180015151  mov     [rbp+3Fh+var_70], rax
0x180015155  mov     [rbp+3Fh+var_78], r12
0x180015159  mov     [rbp+3Fh+EndPtr], rsi
0x18001515d  mov     [rbp+3Fh+hKey], rsi
0x180015161  mov     [rbp+3Fh+var_A0], rsi
0x180015165  mov     [rbp+3Fh+var_84], r9d
0x180015169  movzx   r15d, dx
0x18001516d  call    OpenClassesRootKeyExW
0x180015172  test    eax, eax
0x180015174  jg      loc_18001538D
0x18001517a  js      loc_18001524A
0x180015180  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180015184  lea     rax, [rbp+3Fh+var_A0]
0x180015188  mov     r9d, 2000000h; samDesired
0x18001518e  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180015193  xor     r8d, r8d; ulOptions
0x180015196  mov     rdx, rbx; lpSubKey
0x180015199  call    cs:__imp_RegOpenKeyExW
0x18001519f  test    eax, eax
0x1800151a1  jnz     loc_1800153A2
0x1800151a7  test    edi, edi
0x1800151a9  jnz     loc_180015271
0x1800151af  lea     ebx, [rax+5]
0x1800151b2  mov     ecx, r15d
0x1800151b5  mov     r8d, ebx
0x1800151b8  lea     r9d, [rax+10h]
0x1800151bc  lea     rdx, [rbp+3Fh+SubKey]
0x1800151c0  call    cs:__imp__o__ultow_s
0x1800151c6  lea     rdx, [rbp+3Fh+SubKey]
0x1800151ca  cmp     [rbp+3Fh+SubKey], si
0x1800151ce  jz      short loc_1800151D9
0x1800151d0  add     rdx, 2
0x1800151d4  cmp     [rdx], si
0x1800151d7  jnz     short loc_1800151D0
0x1800151d9  mov     word ptr [rdx], 2Eh ; '.'
0x1800151de  mov     ecx, r14d
0x1800151e1  add     rdx, 2
0x1800151e5  mov     r9d, 10h
0x1800151eb  mov     r8, rbx
0x1800151ee  call    cs:__imp__o__ultow_s
0x1800151f4  mov     rcx, [rbp+3Fh+var_A0]; hKey
0x1800151f8  lea     rsi, [r13+10h]
0x1800151fc  mov     r9d, 2000000h; samDesired
0x180015202  mov     [rsp+0E0h+phkResult], rsi; phkResult
0x180015207  xor     r8d, r8d; ulOptions
0x18001520a  lea     rdx, [rbp+3Fh+SubKey]; lpSubKey
0x18001520e  call    cs:__imp_RegOpenKeyExW
0x180015214  xor     esi, esi
0x180015216  movzx   ebx, r14w
0x18001521a  test    eax, eax
0x18001521c  jnz     short loc_180015273
0x18001521e  movzx   edi, r15w
0x180015222  mov     rax, [rbp+3Fh+hKey]
0x180015226  mov     [r13+0], rax
0x18001522a  mov     rax, [rbp+3Fh+var_A0]
0x18001522e  mov     [r13+8], rax
0x180015232  mov     rax, [rbp+3Fh+var_70]
0x180015236  test    rax, rax
0x180015239  jz      short loc_18001523E
0x18001523b  mov     [rax], di
0x18001523e  test    r12, r12
0x180015241  jz      short loc_180015248
0x180015243  mov     [r12], bx
0x180015248  xor     eax, eax
0x18001524a  mov     rcx, [rbp+3Fh+var_38]
0x18001524e  xor     rcx, rsp; StackCookie
0x180015251  call    __security_check_cookie
0x180015256  mov     rbx, [rsp+0E0h+arg_18]
0x18001525e  add     rsp, 0B0h
0x180015265  pop     r15
0x180015267  pop     r14
0x180015269  pop     r13
0x18001526b  pop     r12
0x18001526d  pop     rdi
0x18001526e  pop     rsi
0x18001526f  pop     rbp
0x180015270  retn
0x180015271  mov     ebx, esi
0x180015273  mov     edi, esi
0x180015275  mov     [rbp+3Fh+var_50], si
0x180015279  mov     r12d, esi
0x18001527c  mov     [rbp+3Fh+var_98], esi
0x18001527f  mov     rcx, [rbp+3Fh+var_A0]; hKey
0x180015283  lea     r9, [rbp+3Fh+cchName]; lpcchName
0x180015287  mov     [rsp+0E0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18001528c  lea     r8, [rbp+3Fh+SubKey]; lpName
0x180015290  mov     [rsp+0E0h+lpcchClass], rsi; lpcchClass
0x180015295  mov     edx, r12d; dwIndex
0x180015298  mov     [rsp+0E0h+lpClass], rsi; lpClass
0x18001529d  mov     [rsp+0E0h+phkResult], rsi; lpReserved
0x1800152a2  mov     [rbp+3Fh+cchName], 0Ah
0x1800152a9  call    cs:__imp_RegEnumKeyExW
0x1800152af  test    eax, eax
0x1800152b1  jz      short loc_1800152E6
0x1800152b3  mov     rcx, [rbp+3Fh+var_A0]; hKey
0x1800152b7  cmp     [rbp+3Fh+var_50], si
0x1800152bb  jz      loc_18001539C
0x1800152c1  lea     rax, [r13+10h]
0x1800152c5  mov     r9d, 2000000h; samDesired
0x1800152cb  xor     r8d, r8d; ulOptions
0x1800152ce  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800152d3  lea     rdx, [rbp+3Fh+var_50]; lpSubKey
0x1800152d7  call    cs:__imp_RegOpenKeyExW
0x1800152dd  mov     r12, [rbp+3Fh+var_78]
0x1800152e1  jmp     loc_180015222
0x1800152e6  mov     r8d, 10h; Radix
0x1800152ec  lea     rdx, [rbp+3Fh+EndPtr]; EndPtr
0x1800152f0  lea     rcx, [rbp+3Fh+SubKey]; String
0x1800152f4  call    cs:__imp_wcstoul
0x1800152fa  mov     rcx, [rbp+3Fh+EndPtr]
0x1800152fe  mov     esi, eax
0x180015300  mov     eax, 2Eh ; '.'
0x180015305  cmp     [rcx], ax
0x180015308  jnz     short loc_18001534C
0x18001530a  add     rcx, 2; String
0x18001530e  lea     r8d, [rax-1Eh]; Radix
0x180015312  xor     edx, edx; EndPtr
0x180015314  call    cs:__imp_wcstoul
0x18001531a  cmp     [rbp+3Fh+var_84], 0
0x18001531e  mov     edx, eax
0x180015320  jnz     short loc_180015378
0x180015322  cmp     si, r15w
0x180015326  jnz     short loc_18001534C
0x180015328  cmp     dx, r14w
0x18001532c  jz      short loc_180015356
0x18001532e  cmp     dx, bx
0x180015331  jbe     short loc_18001534C
0x180015333  movzx   ebx, dx
0x180015336  lea     r8, [rbp+3Fh+SubKey]
0x18001533a  mov     edx, 0Ah
0x18001533f  lea     rcx, [rbp+3Fh+var_50]
0x180015343  movzx   edi, si
0x180015346  call    cs:__imp__o_wcscpy_s
0x18001534c  inc     r12d
0x18001534f  xor     esi, esi
0x180015351  jmp     loc_18001527F
0x180015356  lea     r8, [rbp+3Fh+SubKey]
0x18001535a  mov     edx, 0Ah
0x18001535f  lea     rcx, [rbp+3Fh+var_50]
0x180015363  movzx   edi, r15w
0x180015367  movzx   ebx, r14w
0x18001536b  call    cs:__imp__o_wcscpy_s
0x180015371  xor     esi, esi
0x180015373  jmp     loc_1800152B3
0x180015378  movzx   ecx, si
0x18001537b  shl     ecx, 10h
0x18001537e  movzx   eax, dx
0x180015381  or      ecx, eax
0x180015383  cmp     ecx, [rbp+3Fh+var_98]
0x180015386  jbe     short loc_18001534C
0x180015388  mov     [rbp+3Fh+var_98], ecx
0x18001538b  jmp     short loc_180015333
0x18001538d  movzx   eax, ax
0x180015390  or      eax, 80070000h
0x180015395  test    eax, eax
0x180015397  jmp     loc_18001517A
0x18001539c  call    cs:__imp_RegCloseKey
0x1800153a2  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800153a6  call    cs:__imp_RegCloseKey
0x1800153ac  mov     eax, 8002801Dh
0x1800153b1  jmp     loc_18001524A
```
