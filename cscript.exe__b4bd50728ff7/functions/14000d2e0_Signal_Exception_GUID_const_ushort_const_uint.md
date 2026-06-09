# Signal_Exception(_GUID const &,ushort const *,uint,...)

- ea: `0x14000d2e0`
- end: `0x14000d477`
- name: `?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ`
- size: `407`
- prototype: `__int64(const struct _GUID *, const unsigned __int16 *, unsigned int, ...)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140012050`
- `0x1400120b0`
- `0x1400121f0`
- `0x140012360`

## callees

- `0x140002180`
- `0x14000cf38`
- `0x14000d2e0`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000d459`
- `OLEAUT32!__imp_SysFreeString` at `0x14000d462`
- `OLEAUT32!__imp_SysFreeString` at `0x14000d459`
- `OLEAUT32!__imp_SysFreeString` at `0x14000d462`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14000d424`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14000d424`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x14000d327`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x14000d327`

## pseudocode

```c
__int64 Signal_Exception(const struct _GUID *a1, const unsigned __int16 *a2, unsigned int a3, ...)
{
  OLECHAR *v4; // rdi
  unsigned __int16 *v5; // rsi
  HRESULT v7; // ebx
  int Str; // eax
  int v9; // eax
  ICreateErrorInfo *pperrinfo; // [rsp+20h] [rbp-38h] BYREF
  LPCWCH lpWideCharStr; // [rsp+28h] [rbp-30h] BYREF
  char *v13; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int16 *v14; // [rsp+38h] [rbp-20h] BYREF
  IErrorInfo *perrinfo; // [rsp+40h] [rbp-18h] BYREF
  va_list va; // [rsp+A8h] [rbp+50h] BYREF

  va_start(va, a3);
  v13 = 0;
  v4 = 0;
  perrinfo = 0;
  v5 = 0;
  lpWideCharStr = 0;
  v14 = 0;
  pperrinfo = 0;
  v7 = CreateErrorInfo(&pperrinfo);
  if ( v7 >= 0 )
  {
    v7 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const struct _GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, a1);
    if ( v7 >= 0 )
    {
      v7 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))pperrinfo->lpVtbl->SetSource)(
             pperrinfo,
             a2);
      if ( v7 >= 0 )
      {
        Str = LoadStr((unsigned __int16 **)&lpWideCharStr, a3);
        v4 = (OLECHAR *)lpWideCharStr;
        if ( Str )
        {
          va_copy(v13, va);
          v9 = FormatLine(lpWideCharStr, &v14, &v13);
          v13 = 0;
          v7 = v9;
          v5 = v14;
          if ( v9 >= 0 )
          {
            v7 = ((__int64 (__fastcall *)(ICreateErrorInfo *, unsigned __int16 *))pperrinfo->lpVtbl->SetDescription)(
                   pperrinfo,
                   v14);
            if ( v7 >= 0 )
            {
              v7 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetHelpFile)(pperrinfo, 0);
              if ( v7 >= 0 )
              {
                v7 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetHelpContext)(
                       pperrinfo,
                       0);
                if ( v7 >= 0 )
                {
                  v7 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
                         pperrinfo,
                         &IID_IErrorInfo,
                         &perrinfo);
                  if ( v7 >= 0 )
                    v7 = SetErrorInfo(0, perrinfo);
                }
              }
            }
          }
        }
        else
        {
          v7 = -2147024882;
        }
      }
    }
  }
  if ( pperrinfo )
    ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  if ( perrinfo )
    ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
  SysFreeString(v4);
  SysFreeString(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000d2e0  mov     [rsp-30h+arg_10], r8d
0x14000d2e5  mov     [rsp-30h+arg_18], r9
0x14000d2ea  push    rbp
0x14000d2eb  push    rbx
0x14000d2ec  push    rsi
0x14000d2ed  push    rdi
0x14000d2ee  push    r14
0x14000d2f0  push    r15
0x14000d2f2  mov     rbp, rsp
0x14000d2f5  sub     rsp, 58h
0x14000d2f9  mov     r14, rcx
0x14000d2fc  mov     [rbp+var_28], 0
0x14000d304  xor     edi, edi
0x14000d306  mov     [rbp+perrinfo], 0
0x14000d30e  xor     esi, esi
0x14000d310  mov     [rbp+lpWideCharStr], rdi
0x14000d314  lea     rcx, [rbp+pperrinfo]; pperrinfo
0x14000d318  mov     [rbp+var_20], rsi
0x14000d31c  mov     r15, rdx
0x14000d31f  mov     [rbp+pperrinfo], 0
0x14000d327  call    cs:__imp_CreateErrorInfo
0x14000d32d  mov     ebx, eax
0x14000d32f  test    eax, eax
0x14000d331  js      loc_14000D42C
0x14000d337  mov     rcx, [rbp+pperrinfo]
0x14000d33b  mov     rdx, r14
0x14000d33e  mov     rax, [rcx]
0x14000d341  mov     rax, [rax+18h]
0x14000d345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d34a  mov     ebx, eax
0x14000d34c  test    eax, eax
0x14000d34e  js      loc_14000D42C
0x14000d354  mov     rcx, [rbp+pperrinfo]
0x14000d358  mov     rdx, r15
0x14000d35b  mov     rax, [rcx]
0x14000d35e  mov     rax, [rax+20h]
0x14000d362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d367  mov     ebx, eax
0x14000d369  test    eax, eax
0x14000d36b  js      loc_14000D42C
0x14000d371  mov     edx, [rbp+arg_10]; unsigned int
0x14000d374  lea     rcx, [rbp+lpWideCharStr]; unsigned __int16 **
0x14000d378  call    ?LoadStr@@YAHPEAPEAGI@Z; LoadStr(ushort * *,uint)
0x14000d37d  mov     rdi, [rbp+lpWideCharStr]
0x14000d381  test    eax, eax
0x14000d383  jnz     short loc_14000D38F
0x14000d385  mov     ebx, 8007000Eh
0x14000d38a  jmp     loc_14000D42C
0x14000d38f  lea     rax, [rbp+arg_18]
0x14000d393  mov     rcx, rdi; lpWideCharStr
0x14000d396  lea     r8, [rbp+var_28]; char **
0x14000d39a  mov     [rbp+var_28], rax
0x14000d39e  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x14000d3a2  call    ?FormatLine@@YAJPEBGPEAPEAGPEAPEAD@Z; FormatLine(ushort const *,ushort * *,char * *)
0x14000d3a7  mov     [rbp+var_28], rsi
0x14000d3ab  mov     ebx, eax
0x14000d3ad  mov     rsi, [rbp+var_20]
0x14000d3b1  test    eax, eax
0x14000d3b3  js      short loc_14000D42C
0x14000d3b5  mov     rcx, [rbp+pperrinfo]
0x14000d3b9  mov     rdx, rsi
0x14000d3bc  mov     rax, [rcx]
0x14000d3bf  mov     rax, [rax+28h]
0x14000d3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d3c8  mov     ebx, eax
0x14000d3ca  test    eax, eax
0x14000d3cc  js      short loc_14000D42C
0x14000d3ce  mov     rcx, [rbp+pperrinfo]
0x14000d3d2  xor     edx, edx
0x14000d3d4  mov     rax, [rcx]
0x14000d3d7  mov     rax, [rax+30h]
0x14000d3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d3e0  mov     ebx, eax
0x14000d3e2  test    eax, eax
0x14000d3e4  js      short loc_14000D42C
0x14000d3e6  mov     rcx, [rbp+pperrinfo]
0x14000d3ea  xor     edx, edx
0x14000d3ec  mov     rax, [rcx]
0x14000d3ef  mov     rax, [rax+38h]
0x14000d3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d3f8  mov     ebx, eax
0x14000d3fa  test    eax, eax
0x14000d3fc  js      short loc_14000D42C
0x14000d3fe  mov     rcx, [rbp+pperrinfo]
0x14000d402  lea     r8, [rbp+perrinfo]
0x14000d406  lea     rdx, IID_IErrorInfo
0x14000d40d  mov     rax, [rcx]
0x14000d410  mov     rax, [rax]
0x14000d413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d418  mov     ebx, eax
0x14000d41a  test    eax, eax
0x14000d41c  js      short loc_14000D42C
0x14000d41e  mov     rdx, [rbp+perrinfo]; perrinfo
0x14000d422  xor     ecx, ecx; dwReserved
0x14000d424  call    cs:__imp_SetErrorInfo
0x14000d42a  mov     ebx, eax
0x14000d42c  mov     rcx, [rbp+pperrinfo]
0x14000d430  test    rcx, rcx
0x14000d433  jz      short loc_14000D441
0x14000d435  mov     rax, [rcx]
0x14000d438  mov     rax, [rax+10h]
0x14000d43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d441  mov     rcx, [rbp+perrinfo]
0x14000d445  test    rcx, rcx
0x14000d448  jz      short loc_14000D456
0x14000d44a  mov     rax, [rcx]
0x14000d44d  mov     rax, [rax+10h]
0x14000d451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d456  mov     rcx, rdi; bstrString
0x14000d459  call    cs:__imp_SysFreeString
0x14000d45f  mov     rcx, rsi; bstrString
0x14000d462  call    cs:__imp_SysFreeString
0x14000d468  mov     eax, ebx
0x14000d46a  add     rsp, 58h
0x14000d46e  pop     r15
0x14000d470  pop     r14
0x14000d472  pop     rdi
0x14000d473  pop     rsi
0x14000d474  pop     rbx
0x14000d475  pop     rbp
0x14000d476  retn
```
