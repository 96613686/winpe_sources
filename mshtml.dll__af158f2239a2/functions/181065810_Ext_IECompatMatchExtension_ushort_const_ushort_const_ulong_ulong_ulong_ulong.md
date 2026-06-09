# Ext_IECompatMatchExtension(ushort const *,ushort const *,ulong,ulong,ulong *,ulong *)

- ea: `0x181065810`
- end: `0x181065a8e`
- name: `?Ext_IECompatMatchExtension@@YAJPEBG0KKPEAK1@Z`
- size: `638`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x181065a94`

## callees

- `0x181065290`
- `0x181065810`
- `0x181065c90`
- `0x181066024`

## import_xrefs

- `msvcrt!wcstok_s` at `0x181065905`
- `msvcrt!wcstok_s` at `0x181065919`
- `msvcrt!wcstok_s` at `0x18106592d`
- `msvcrt!wcstok_s` at `0x181065941`
- `msvcrt!wcstok_s` at `0x181065a5d`
- `msvcrt!wcstok_s` at `0x181065a6f`
- `msvcrt!wcstok_s` at `0x181065a81`
- `msvcrt!wcstok_s` at `0x181065905`
- `msvcrt!wcstok_s` at `0x181065919`
- `msvcrt!wcstok_s` at `0x18106592d`
- `msvcrt!wcstok_s` at `0x181065941`
- `msvcrt!wcstok_s` at `0x181065a5d`
- `msvcrt!wcstok_s` at `0x181065a6f`
- `msvcrt!wcstok_s` at `0x181065a81`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrToIntExW` at `0x1810659bd`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrToIntExW` at `0x1810659e3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrToIntExW` at `0x1810659bd`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrToIntExW` at `0x1810659e3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x181065978`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x181065978`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x181065a11`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x181065a1b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x181065a25`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x181065a2f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x181065a11`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x181065a1b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x181065a25`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x181065a2f`

## string_xrefs

- `0x181065851`: `DllName`
- `0x1810658bb`: `CompatibilityFlags`

## pseudocode

```c
__int64 __fastcall Ext_IECompatMatchExtension(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int *a6)
{
  HKEY v7; // rcx
  int v8; // ebx
  int v9; // r9d
  HKEY v10; // rcx
  int v11; // r9d
  HKEY v12; // rcx
  int v13; // r9d
  wchar_t *v14; // rcx
  wchar_t *v15; // rdi
  wchar_t *v16; // r14
  wchar_t *v17; // rax
  wchar_t *i; // rcx
  const WCHAR *v19; // r12
  wchar_t *v20; // rax
  const WCHAR *v21; // r15
  int v22; // eax
  BOOL v23; // eax
  int v24; // ecx
  unsigned int *v26; // [rsp+30h] [rbp-51h]
  unsigned int *v27; // [rsp+30h] [rbp-51h]
  unsigned int *v28; // [rsp+30h] [rbp-51h]
  unsigned int *v29; // [rsp+30h] [rbp-51h]
  int piRet; // [rsp+38h] [rbp-49h] BYREF
  int v31; // [rsp+3Ch] [rbp-45h] BYREF
  wchar_t *v32; // [rsp+40h] [rbp-41h] BYREF
  wchar_t *v33; // [rsp+48h] [rbp-39h] BYREF
  wchar_t *v34; // [rsp+50h] [rbp-31h] BYREF
  wchar_t *String; // [rsp+58h] [rbp-29h] BYREF
  wchar_t *Context; // [rsp+60h] [rbp-21h] BYREF
  wchar_t *v37; // [rsp+68h] [rbp-19h] BYREF
  wchar_t *v38; // [rsp+70h] [rbp-11h] BYREF
  wchar_t *v39; // [rsp+78h] [rbp-9h] BYREF

  String = 0;
  v8 = SHRegAllocData((HKEY)a1, a1, L"DllName", a4, (void **)&String, v26);
  if ( v8 >= 0 )
  {
    v34 = 0;
    v8 = SHRegAllocData(v7, a1, L"Version", v9, (void **)&v34, v27);
    if ( v8 >= 0 )
    {
      v33 = 0;
      v8 = SHRegAllocData(v10, a1, L"BlockType", v11, (void **)&v33, v28);
      if ( v8 >= 0 )
      {
        v32 = 0;
        v8 = SHRegAllocData(v12, a1, L"CompatibilityFlags", v13, (void **)&v32, v29);
        if ( v8 >= 0 )
        {
          v14 = String;
          Context = 0;
          v8 = 0;
          v37 = 0;
          *a6 = 0;
          v38 = 0;
          v39 = 0;
          v15 = wcstok_s(v14, L";", &Context);
          v16 = wcstok_s(v34, L";", &v37);
          v17 = wcstok_s(v33, L";", &v38);
          for ( i = v32; ; i = 0 )
          {
            v19 = v17;
            v20 = wcstok_s(i, L";", &v39);
            v21 = v20;
            if ( !v15 || !v16 || !v19 || !v20 )
              break;
            if ( (!StrCmpICW(L"*", v15) || (unsigned int)Ext_CompareFileNames(a2, v15))
              && !(unsigned int)Ext_IsVersionInRange(v16, a3, a4) )
            {
              piRet = 0;
              if ( StrToIntExW(v21, 1, &piRet) )
              {
                v22 = piRet;
              }
              else
              {
                v22 = 0;
                piRet = 0;
              }
              if ( v22 )
              {
                *a6 |= v22;
              }
              else
              {
                v31 = 0;
                v23 = StrToIntExW(v19, 1, &v31);
                v24 = 0;
                if ( v23 )
                  v24 = v31;
                if ( (v24 & 0x10) != 0 || (v24 & 0xC) == 0 || (v24 & 4) != 0 )
                {
                  v8 = 1;
                  *a6 = 0;
                  *a5 = v24;
                  break;
                }
              }
            }
            v15 = wcstok_s(0, L";", &Context);
            v16 = wcstok_s(0, L";", &v37);
            v17 = wcstok_s(0, L";", &v38);
          }
          CoTaskMemFree(v32);
        }
        CoTaskMemFree(v33);
      }
      CoTaskMemFree(v34);
    }
    CoTaskMemFree(String);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x181065810  mov     rax, rsp
0x181065813  mov     [rax+20h], r9d
0x181065817  mov     [rax+18h], r8d
0x18106581b  mov     [rax+10h], rdx
0x18106581f  mov     [rax+8], rcx
0x181065823  push    rbp
0x181065824  push    rbx
0x181065825  push    rsi
0x181065826  push    rdi
0x181065827  push    r12
0x181065829  push    r13
0x18106582b  push    r14
0x18106582d  push    r15
0x18106582f  lea     rbp, [rax-4Fh]
0x181065833  sub     rsp, 88h
0x18106583a  mov     rdi, [rbp+47h+arg_0]
0x18106583e  lea     rax, [rbp+47h+String]
0x181065842  xor     r13d, r13d
0x181065845  mov     [rsp+20h], rax; void **
0x18106584a  mov     rdx, rdi; unsigned __int16 *
0x18106584d  mov     [rbp+47h+String], r13
0x181065851  lea     r8, aDllname; "DllName"
0x181065858  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18106585d  mov     ebx, eax
0x18106585f  test    eax, eax
0x181065861  js      loc_181065A35
0x181065867  lea     rax, [rbp+47h+var_78]
0x18106586b  mov     [rbp+47h+var_78], r13
0x18106586f  lea     r8, aVersion_1; "Version"
0x181065876  mov     [rsp+20h], rax; void **
0x18106587b  mov     rdx, rdi; unsigned __int16 *
0x18106587e  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x181065883  mov     ebx, eax
0x181065885  test    eax, eax
0x181065887  js      loc_181065A2B
0x18106588d  lea     rax, [rbp+47h+var_80]
0x181065891  mov     [rbp+47h+var_80], r13
0x181065895  lea     r8, aBlocktype; "BlockType"
0x18106589c  mov     [rsp+20h], rax; void **
0x1810658a1  mov     rdx, rdi; unsigned __int16 *
0x1810658a4  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1810658a9  mov     ebx, eax
0x1810658ab  test    eax, eax
0x1810658ad  js      loc_181065A21
0x1810658b3  lea     rax, [rbp+47h+var_88]
0x1810658b7  mov     [rbp+47h+var_88], r13
0x1810658bb  lea     r8, aCompatibilityf; "CompatibilityFlags"
0x1810658c2  mov     [rsp+20h], rax; void **
0x1810658c7  mov     rdx, rdi; unsigned __int16 *
0x1810658ca  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1810658cf  mov     ebx, eax
0x1810658d1  test    eax, eax
0x1810658d3  js      loc_181065A17
0x1810658d9  mov     rsi, [rbp+47h+arg_28]
0x1810658dd  lea     r15, asc_1813D2CF4; ";"
0x1810658e4  mov     rcx, [rbp+47h+String]; String
0x1810658e8  lea     r8, [rbp+47h+Context]; Context
0x1810658ec  mov     rdx, r15; Delimiter
0x1810658ef  mov     [rbp+47h+Context], r13
0x1810658f3  mov     ebx, r13d
0x1810658f6  mov     [rbp+47h+var_60], r13
0x1810658fa  mov     [rsi], r13d
0x1810658fd  mov     [rbp+47h+var_58], r13
0x181065901  mov     [rbp+47h+var_50], r13
0x181065905  call    cs:__imp_wcstok_s
0x18106590b  mov     rcx, [rbp+47h+var_78]; String
0x18106590f  lea     r8, [rbp+47h+var_60]; Context
0x181065913  mov     rdx, r15; Delimiter
0x181065916  mov     rdi, rax
0x181065919  call    cs:__imp_wcstok_s
0x18106591f  mov     rcx, [rbp+47h+var_80]; String
0x181065923  lea     r8, [rbp+47h+var_58]; Context
0x181065927  mov     rdx, r15; Delimiter
0x18106592a  mov     r14, rax
0x18106592d  call    cs:__imp_wcstok_s
0x181065933  mov     rcx, [rbp+47h+var_88]; String
0x181065937  lea     r8, [rbp+47h+var_50]; Context
0x18106593b  mov     rdx, r15; Delimiter
0x18106593e  mov     r12, rax
0x181065941  call    cs:__imp_wcstok_s
0x181065947  mov     r15, rax
0x18106594a  test    rdi, rdi
0x18106594d  jz      loc_181065A0D
0x181065953  test    r14, r14
0x181065956  jz      loc_181065A0D
0x18106595c  test    r12, r12
0x18106595f  jz      loc_181065A0D
0x181065965  test    rax, rax
0x181065968  jz      loc_181065A0D
0x18106596e  mov     rdx, rdi; pszStr2
0x181065971  lea     rcx, asc_1813C1EB0; "*"
0x181065978  call    cs:__imp_StrCmpICW
0x18106597e  test    eax, eax
0x181065980  jz      short loc_181065996
0x181065982  mov     rcx, [rbp+47h+arg_8]; unsigned __int16 *
0x181065986  mov     rdx, rdi; unsigned __int16 *
0x181065989  call    ?Ext_CompareFileNames@@YAHPEBG0@Z; Ext_CompareFileNames(ushort const *,ushort const *)
0x18106598e  test    eax, eax
0x181065990  jz      loc_181065A4D
0x181065996  mov     r8d, [rbp+47h+arg_18]; unsigned int
0x18106599a  mov     rcx, r14; unsigned __int16 *
0x18106599d  mov     edx, [rbp+47h+arg_10]; unsigned int
0x1810659a0  call    ?Ext_IsVersionInRange@@YAJPEBGKK@Z; Ext_IsVersionInRange(ushort const *,ulong,ulong)
0x1810659a5  test    eax, eax
0x1810659a7  jnz     loc_181065A4D
0x1810659ad  lea     edi, [rax+1]
0x1810659b0  mov     [rbp+47h+piRet], r13d
0x1810659b4  mov     edx, edi; dwFlags
0x1810659b6  lea     r8, [rbp+47h+piRet]; piRet
0x1810659ba  mov     rcx, r15; pszString
0x1810659bd  call    cs:__imp_StrToIntExW
0x1810659c3  test    eax, eax
0x1810659c5  jnz     short loc_1810659CF
0x1810659c7  mov     eax, r13d
0x1810659ca  mov     [rbp+47h+piRet], eax
0x1810659cd  jmp     short loc_1810659D2
0x1810659cf  mov     eax, [rbp+47h+piRet]
0x1810659d2  test    eax, eax
0x1810659d4  jnz     short loc_181065A4B
0x1810659d6  lea     r8, [rbp+47h+var_8C]; piRet
0x1810659da  mov     [rbp+47h+var_8C], r13d
0x1810659de  mov     edx, edi; dwFlags
0x1810659e0  mov     rcx, r12; pszString
0x1810659e3  call    cs:__imp_StrToIntExW
0x1810659e9  mov     ecx, r13d
0x1810659ec  test    eax, eax
0x1810659ee  jz      short loc_1810659F3
0x1810659f0  mov     ecx, [rbp+47h+var_8C]
0x1810659f3  test    cl, 10h
0x1810659f6  jnz     short loc_181065A02
0x1810659f8  test    cl, 0Ch
0x1810659fb  jz      short loc_181065A02
0x1810659fd  test    cl, 4
0x181065a00  jz      short loc_181065A4D
0x181065a02  mov     rax, [rbp+47h+arg_20]
0x181065a06  mov     ebx, edi
0x181065a08  mov     [rsi], r13d
0x181065a0b  mov     [rax], ecx
0x181065a0d  mov     rcx, [rbp+47h+var_88]; pv
0x181065a11  call    cs:__imp_CoTaskMemFree
0x181065a17  mov     rcx, [rbp+47h+var_80]; pv
0x181065a1b  call    cs:__imp_CoTaskMemFree
0x181065a21  mov     rcx, [rbp+47h+var_78]; pv
0x181065a25  call    cs:__imp_CoTaskMemFree
0x181065a2b  mov     rcx, [rbp+47h+String]; pv
0x181065a2f  call    cs:__imp_CoTaskMemFree
0x181065a35  mov     eax, ebx
0x181065a37  add     rsp, 88h
0x181065a3e  pop     r15
0x181065a40  pop     r14
0x181065a42  pop     r13
0x181065a44  pop     r12
0x181065a46  pop     rdi
0x181065a47  pop     rsi
0x181065a48  pop     rbx
0x181065a49  pop     rbp
0x181065a4a  retn
0x181065a4b  or      [rsi], eax
0x181065a4d  lea     r15, asc_1813D2CF4; ";"
0x181065a54  xor     ecx, ecx; String
0x181065a56  mov     rdx, r15; Delimiter
0x181065a59  lea     r8, [rbp+47h+Context]; Context
0x181065a5d  call    cs:__imp_wcstok_s
0x181065a63  lea     r8, [rbp+47h+var_60]; Context
0x181065a67  mov     rdx, r15; Delimiter
0x181065a6a  xor     ecx, ecx; String
0x181065a6c  mov     rdi, rax
0x181065a6f  call    cs:__imp_wcstok_s
0x181065a75  lea     r8, [rbp+47h+var_58]; Context
0x181065a79  mov     rdx, r15; Delimiter
0x181065a7c  xor     ecx, ecx; String
0x181065a7e  mov     r14, rax
0x181065a81  call    cs:__imp_wcstok_s
0x181065a87  xor     ecx, ecx
0x181065a89  jmp     loc_181065937
```
