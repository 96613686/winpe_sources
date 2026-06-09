# Ext_IECompatMatchExtension(ushort const *,ushort const *,ulong,ulong,ulong *,ulong *)

- ea: `0x181096158`
- end: `0x18109642f`
- name: `?Ext_IECompatMatchExtension@@YAJPEBG0KKPEAK1@Z`
- size: `727`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x181096438`

## callees

- `0x181095b80`
- `0x181096158`
- `0x181096638`
- `0x1810969f0`

## import_xrefs

- `msvcrt!wcstok_s` at `0x18109624d`
- `msvcrt!wcstok_s` at `0x181096267`
- `msvcrt!wcstok_s` at `0x181096281`
- `msvcrt!wcstok_s` at `0x18109629b`
- `msvcrt!wcstok_s` at `0x1810963ec`
- `msvcrt!wcstok_s` at `0x181096404`
- `msvcrt!wcstok_s` at `0x18109641c`
- `msvcrt!wcstok_s` at `0x18109624d`
- `msvcrt!wcstok_s` at `0x181096267`
- `msvcrt!wcstok_s` at `0x181096281`
- `msvcrt!wcstok_s` at `0x18109629b`
- `msvcrt!wcstok_s` at `0x1810963ec`
- `msvcrt!wcstok_s` at `0x181096404`
- `msvcrt!wcstok_s` at `0x18109641c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrToIntExW` at `0x181096323`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrToIntExW` at `0x181096353`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrToIntExW` at `0x181096323`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrToIntExW` at `0x181096353`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1810962d8`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1810962d8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x181096387`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x181096397`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1810963a7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1810963b7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x181096387`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x181096397`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1810963a7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1810963b7`

## string_xrefs

- `0x181096199`: `DllName`
- `0x181096203`: `CompatibilityFlags`

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
0x181096158  mov     rax, rsp
0x18109615b  mov     [rax+20h], r9d
0x18109615f  mov     [rax+18h], r8d
0x181096163  mov     [rax+10h], rdx
0x181096167  mov     [rax+8], rcx
0x18109616b  push    rbp
0x18109616c  push    rbx
0x18109616d  push    rsi
0x18109616e  push    rdi
0x18109616f  push    r12
0x181096171  push    r13
0x181096173  push    r14
0x181096175  push    r15
0x181096177  lea     rbp, [rax-4Fh]
0x18109617b  sub     rsp, 88h
0x181096182  mov     rdi, [rbp+47h+arg_0]
0x181096186  lea     rax, [rbp+47h+String]
0x18109618a  xor     r13d, r13d
0x18109618d  mov     [rsp+20h], rax; void **
0x181096192  mov     rdx, rdi; unsigned __int16 *
0x181096195  mov     [rbp+47h+String], r13
0x181096199  lea     r8, aDllname; "DllName"
0x1810961a0  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1810961a5  mov     ebx, eax
0x1810961a7  test    eax, eax
0x1810961a9  js      loc_1810963C3
0x1810961af  lea     rax, [rbp+47h+var_78]
0x1810961b3  mov     [rbp+47h+var_78], r13
0x1810961b7  lea     r8, aVersion_1; "Version"
0x1810961be  mov     [rsp+20h], rax; void **
0x1810961c3  mov     rdx, rdi; unsigned __int16 *
0x1810961c6  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1810961cb  mov     ebx, eax
0x1810961cd  test    eax, eax
0x1810961cf  js      loc_1810963B3
0x1810961d5  lea     rax, [rbp+47h+var_80]
0x1810961d9  mov     [rbp+47h+var_80], r13
0x1810961dd  lea     r8, aBlocktype; "BlockType"
0x1810961e4  mov     [rsp+20h], rax; void **
0x1810961e9  mov     rdx, rdi; unsigned __int16 *
0x1810961ec  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1810961f1  mov     ebx, eax
0x1810961f3  test    eax, eax
0x1810961f5  js      loc_1810963A3
0x1810961fb  lea     rax, [rbp+47h+var_88]
0x1810961ff  mov     [rbp+47h+var_88], r13
0x181096203  lea     r8, aCompatibilityf; "CompatibilityFlags"
0x18109620a  mov     [rsp+20h], rax; void **
0x18109620f  mov     rdx, rdi; unsigned __int16 *
0x181096212  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x181096217  mov     ebx, eax
0x181096219  test    eax, eax
0x18109621b  js      loc_181096393
0x181096221  mov     rsi, [rbp+47h+arg_28]
0x181096225  lea     r15, asc_1813F6C0C; ";"
0x18109622c  mov     rcx, [rbp+47h+String]; String
0x181096230  lea     r8, [rbp+47h+Context]; Context
0x181096234  mov     rdx, r15; Delimiter
0x181096237  mov     [rbp+47h+Context], r13
0x18109623b  mov     ebx, r13d
0x18109623e  mov     [rbp+47h+var_60], r13
0x181096242  mov     [rsi], r13d
0x181096245  mov     [rbp+47h+var_58], r13
0x181096249  mov     [rbp+47h+var_50], r13
0x18109624d  call    cs:__imp_wcstok_s
0x181096254  nop     dword ptr [rax+rax+00h]
0x181096259  mov     rcx, [rbp+47h+var_78]; String
0x18109625d  lea     r8, [rbp+47h+var_60]; Context
0x181096261  mov     rdx, r15; Delimiter
0x181096264  mov     rdi, rax
0x181096267  call    cs:__imp_wcstok_s
0x18109626e  nop     dword ptr [rax+rax+00h]
0x181096273  mov     rcx, [rbp+47h+var_80]; String
0x181096277  lea     r8, [rbp+47h+var_58]; Context
0x18109627b  mov     rdx, r15; Delimiter
0x18109627e  mov     r14, rax
0x181096281  call    cs:__imp_wcstok_s
0x181096288  nop     dword ptr [rax+rax+00h]
0x18109628d  mov     rcx, [rbp+47h+var_88]; String
0x181096291  lea     r8, [rbp+47h+var_50]; Context
0x181096295  mov     rdx, r15; Delimiter
0x181096298  mov     r12, rax
0x18109629b  call    cs:__imp_wcstok_s
0x1810962a2  nop     dword ptr [rax+rax+00h]
0x1810962a7  mov     r15, rax
0x1810962aa  test    rdi, rdi
0x1810962ad  jz      loc_181096383
0x1810962b3  test    r14, r14
0x1810962b6  jz      loc_181096383
0x1810962bc  test    r12, r12
0x1810962bf  jz      loc_181096383
0x1810962c5  test    rax, rax
0x1810962c8  jz      loc_181096383
0x1810962ce  mov     rdx, rdi; pszStr2
0x1810962d1  lea     rcx, asc_1813F30D0; "*"
0x1810962d8  call    cs:__imp_StrCmpICW
0x1810962df  nop     dword ptr [rax+rax+00h]
0x1810962e4  test    eax, eax
0x1810962e6  jz      short loc_1810962FC
0x1810962e8  mov     rcx, [rbp+47h+arg_8]; unsigned __int16 *
0x1810962ec  mov     rdx, rdi; unsigned __int16 *
0x1810962ef  call    ?Ext_CompareFileNames@@YAHPEBG0@Z; Ext_CompareFileNames(ushort const *,ushort const *)
0x1810962f4  test    eax, eax
0x1810962f6  jz      loc_1810963DC
0x1810962fc  mov     r8d, [rbp+47h+arg_18]; unsigned int
0x181096300  mov     rcx, r14; unsigned __int16 *
0x181096303  mov     edx, [rbp+47h+arg_10]; unsigned int
0x181096306  call    ?Ext_IsVersionInRange@@YAJPEBGKK@Z; Ext_IsVersionInRange(ushort const *,ulong,ulong)
0x18109630b  test    eax, eax
0x18109630d  jnz     loc_1810963DC
0x181096313  lea     edi, [rax+1]
0x181096316  mov     [rbp+47h+piRet], r13d
0x18109631a  mov     edx, edi; dwFlags
0x18109631c  lea     r8, [rbp+47h+piRet]; piRet
0x181096320  mov     rcx, r15; pszString
0x181096323  call    cs:__imp_StrToIntExW
0x18109632a  nop     dword ptr [rax+rax+00h]
0x18109632f  test    eax, eax
0x181096331  jnz     short loc_18109633B
0x181096333  mov     eax, r13d
0x181096336  mov     [rbp+47h+piRet], eax
0x181096339  jmp     short loc_18109633E
0x18109633b  mov     eax, [rbp+47h+piRet]
0x18109633e  test    eax, eax
0x181096340  jnz     loc_1810963DA
0x181096346  lea     r8, [rbp+47h+var_8C]; piRet
0x18109634a  mov     [rbp+47h+var_8C], r13d
0x18109634e  mov     edx, edi; dwFlags
0x181096350  mov     rcx, r12; pszString
0x181096353  call    cs:__imp_StrToIntExW
0x18109635a  nop     dword ptr [rax+rax+00h]
0x18109635f  mov     ecx, r13d
0x181096362  test    eax, eax
0x181096364  jz      short loc_181096369
0x181096366  mov     ecx, [rbp+47h+var_8C]
0x181096369  test    cl, 10h
0x18109636c  jnz     short loc_181096378
0x18109636e  test    cl, 0Ch
0x181096371  jz      short loc_181096378
0x181096373  test    cl, 4
0x181096376  jz      short loc_1810963DC
0x181096378  mov     rax, [rbp+47h+arg_20]
0x18109637c  mov     ebx, edi
0x18109637e  mov     [rsi], r13d
0x181096381  mov     [rax], ecx
0x181096383  mov     rcx, [rbp+47h+var_88]; pv
0x181096387  call    cs:__imp_CoTaskMemFree
0x18109638e  nop     dword ptr [rax+rax+00h]
0x181096393  mov     rcx, [rbp+47h+var_80]; pv
0x181096397  call    cs:__imp_CoTaskMemFree
0x18109639e  nop     dword ptr [rax+rax+00h]
0x1810963a3  mov     rcx, [rbp+47h+var_78]; pv
0x1810963a7  call    cs:__imp_CoTaskMemFree
0x1810963ae  nop     dword ptr [rax+rax+00h]
0x1810963b3  mov     rcx, [rbp+47h+String]; pv
0x1810963b7  call    cs:__imp_CoTaskMemFree
0x1810963be  nop     dword ptr [rax+rax+00h]
0x1810963c3  mov     eax, ebx
0x1810963c5  add     rsp, 88h
0x1810963cc  pop     r15
0x1810963ce  pop     r14
0x1810963d0  pop     r13
0x1810963d2  pop     r12
0x1810963d4  pop     rdi
0x1810963d5  pop     rsi
0x1810963d6  pop     rbx
0x1810963d7  pop     rbp
0x1810963d8  retn
0x1810963da  or      [rsi], eax
0x1810963dc  lea     r15, asc_1813F6C0C; ";"
0x1810963e3  xor     ecx, ecx; String
0x1810963e5  mov     rdx, r15; Delimiter
0x1810963e8  lea     r8, [rbp+47h+Context]; Context
0x1810963ec  call    cs:__imp_wcstok_s
0x1810963f3  nop     dword ptr [rax+rax+00h]
0x1810963f8  lea     r8, [rbp+47h+var_60]; Context
0x1810963fc  mov     rdx, r15; Delimiter
0x1810963ff  xor     ecx, ecx; String
0x181096401  mov     rdi, rax
0x181096404  call    cs:__imp_wcstok_s
0x18109640b  nop     dword ptr [rax+rax+00h]
0x181096410  lea     r8, [rbp+47h+var_58]; Context
0x181096414  mov     rdx, r15; Delimiter
0x181096417  xor     ecx, ecx; String
0x181096419  mov     r14, rax
0x18109641c  call    cs:__imp_wcstok_s
0x181096423  nop     dword ptr [rax+rax+00h]
0x181096428  xor     ecx, ecx
0x18109642a  jmp     loc_181096291
```
