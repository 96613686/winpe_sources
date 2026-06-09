# Signal_Exception(_GUID const &,ushort const *,ushort const *,...)

- ea: `0x14000d178`
- end: `0x14000d2d9`
- name: `?Signal_Exception@@YAJAEBU_GUID@@PEBG1ZZ`
- size: `353`
- prototype: `__int64(const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400121f0`

## callees

- `0x14000cf38`
- `0x14000d178`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000d2c6`
- `OLEAUT32!__imp_SysFreeString` at `0x14000d2c6`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14000d291`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14000d291`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x14000d1b7`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x14000d1b7`

## pseudocode

```c
__int64 Signal_Exception(const struct _GUID *a1, const unsigned __int16 *a2, const unsigned __int16 *a3, ...)
{
  unsigned __int16 *v4; // rdi
  HRESULT v6; // ebx
  ICreateErrorInfo *pperrinfo; // [rsp+20h] [rbp-20h] BYREF
  char *v9; // [rsp+28h] [rbp-18h] BYREF
  IErrorInfo *perrinfo; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v11; // [rsp+38h] [rbp-8h] BYREF
  va_list va; // [rsp+88h] [rbp+48h] BYREF

  va_start(va, a3);
  v9 = 0;
  v4 = 0;
  perrinfo = 0;
  v11 = 0;
  pperrinfo = 0;
  v6 = CreateErrorInfo(&pperrinfo);
  if ( v6 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const struct _GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, a1);
    if ( v6 >= 0 )
    {
      v6 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))pperrinfo->lpVtbl->SetSource)(
             pperrinfo,
             a2);
      if ( v6 >= 0 )
      {
        va_copy(v9, va);
        FormatLine(a3, &v11, &v9);
        v9 = 0;
        v4 = v11;
        v6 = ((__int64 (__fastcall *)(ICreateErrorInfo *, unsigned __int16 *))pperrinfo->lpVtbl->SetDescription)(
               pperrinfo,
               v11);
        if ( v6 >= 0 )
        {
          v6 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetHelpFile)(pperrinfo, 0);
          if ( v6 >= 0 )
          {
            v6 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetHelpContext)(pperrinfo, 0);
            if ( v6 >= 0 )
            {
              v6 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
                     pperrinfo,
                     &IID_IErrorInfo,
                     &perrinfo);
              if ( v6 >= 0 )
                v6 = SetErrorInfo(0, perrinfo);
            }
          }
        }
      }
    }
  }
  if ( pperrinfo )
    ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  if ( perrinfo )
    ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
  SysFreeString(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000d178  mov     [rsp-28h+lpWideCharStr], r8
0x14000d17d  mov     [rsp-28h+arg_18], r9
0x14000d182  push    rbp
0x14000d183  push    rbx
0x14000d184  push    rsi
0x14000d185  push    rdi
0x14000d186  push    r14
0x14000d188  mov     rbp, rsp
0x14000d18b  sub     rsp, 40h
0x14000d18f  mov     rsi, rcx
0x14000d192  mov     [rbp+var_18], 0
0x14000d19a  xor     edi, edi
0x14000d19c  mov     [rbp+perrinfo], 0
0x14000d1a4  lea     rcx, [rbp+pperrinfo]; pperrinfo
0x14000d1a8  mov     [rbp+var_8], rdi
0x14000d1ac  mov     r14, rdx
0x14000d1af  mov     [rbp+pperrinfo], 0
0x14000d1b7  call    cs:__imp_CreateErrorInfo
0x14000d1bd  mov     ebx, eax
0x14000d1bf  test    eax, eax
0x14000d1c1  js      loc_14000D299
0x14000d1c7  mov     rcx, [rbp+pperrinfo]
0x14000d1cb  mov     rdx, rsi
0x14000d1ce  mov     rax, [rcx]
0x14000d1d1  mov     rax, [rax+18h]
0x14000d1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d1da  mov     ebx, eax
0x14000d1dc  test    eax, eax
0x14000d1de  js      loc_14000D299
0x14000d1e4  mov     rcx, [rbp+pperrinfo]
0x14000d1e8  mov     rdx, r14
0x14000d1eb  mov     rax, [rcx]
0x14000d1ee  mov     rax, [rax+20h]
0x14000d1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d1f7  mov     ebx, eax
0x14000d1f9  test    eax, eax
0x14000d1fb  js      loc_14000D299
0x14000d201  mov     rcx, [rbp+lpWideCharStr]; lpWideCharStr
0x14000d205  lea     rax, [rbp+arg_18]
0x14000d209  lea     r8, [rbp+var_18]; char **
0x14000d20d  mov     [rbp+var_18], rax
0x14000d211  lea     rdx, [rbp+var_8]; unsigned __int16 **
0x14000d215  call    ?FormatLine@@YAJPEBGPEAPEAGPEAPEAD@Z; FormatLine(ushort const *,ushort * *,char * *)
0x14000d21a  mov     rcx, [rbp+pperrinfo]
0x14000d21e  mov     [rbp+var_18], rdi
0x14000d222  mov     rdi, [rbp+var_8]
0x14000d226  mov     rdx, rdi
0x14000d229  mov     rax, [rcx]
0x14000d22c  mov     rax, [rax+28h]
0x14000d230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d235  mov     ebx, eax
0x14000d237  test    eax, eax
0x14000d239  js      short loc_14000D299
0x14000d23b  mov     rcx, [rbp+pperrinfo]
0x14000d23f  xor     edx, edx
0x14000d241  mov     rax, [rcx]
0x14000d244  mov     rax, [rax+30h]
0x14000d248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d24d  mov     ebx, eax
0x14000d24f  test    eax, eax
0x14000d251  js      short loc_14000D299
0x14000d253  mov     rcx, [rbp+pperrinfo]
0x14000d257  xor     edx, edx
0x14000d259  mov     rax, [rcx]
0x14000d25c  mov     rax, [rax+38h]
0x14000d260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d265  mov     ebx, eax
0x14000d267  test    eax, eax
0x14000d269  js      short loc_14000D299
0x14000d26b  mov     rcx, [rbp+pperrinfo]
0x14000d26f  lea     r8, [rbp+perrinfo]
0x14000d273  lea     rdx, IID_IErrorInfo
0x14000d27a  mov     rax, [rcx]
0x14000d27d  mov     rax, [rax]
0x14000d280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d285  mov     ebx, eax
0x14000d287  test    eax, eax
0x14000d289  js      short loc_14000D299
0x14000d28b  mov     rdx, [rbp+perrinfo]; perrinfo
0x14000d28f  xor     ecx, ecx; dwReserved
0x14000d291  call    cs:__imp_SetErrorInfo
0x14000d297  mov     ebx, eax
0x14000d299  mov     rcx, [rbp+pperrinfo]
0x14000d29d  test    rcx, rcx
0x14000d2a0  jz      short loc_14000D2AE
0x14000d2a2  mov     rax, [rcx]
0x14000d2a5  mov     rax, [rax+10h]
0x14000d2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d2ae  mov     rcx, [rbp+perrinfo]
0x14000d2b2  test    rcx, rcx
0x14000d2b5  jz      short loc_14000D2C3
0x14000d2b7  mov     rax, [rcx]
0x14000d2ba  mov     rax, [rax+10h]
0x14000d2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d2c3  mov     rcx, rdi; bstrString
0x14000d2c6  call    cs:__imp_SysFreeString
0x14000d2cc  mov     eax, ebx
0x14000d2ce  add     rsp, 40h
0x14000d2d2  pop     r14
0x14000d2d4  pop     rdi
0x14000d2d5  pop     rsi
0x14000d2d6  pop     rbx
0x14000d2d7  pop     rbp
0x14000d2d8  retn
```
