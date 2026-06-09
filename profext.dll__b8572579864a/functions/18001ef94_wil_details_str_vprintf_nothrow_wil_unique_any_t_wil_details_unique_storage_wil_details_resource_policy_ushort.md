# wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,char * &)

- ea: `0x18001ef94`
- end: `0x18001f0bc`
- name: `??$str_vprintf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBGAEAPEAD@Z`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001ef5c`

## callees

- `0x180004594`
- `0x18000c7d4`
- `0x18001eef0`
- `0x18001ef94`
- `0x18001f274`
- `0x1800210f0`

## import_xrefs

- `msvcrt!_vscwprintf` at `0x18001efb3`
- `msvcrt!_vscwprintf` at `0x18001efb3`

## string_xrefs

- `0x18001f094`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        __int64 a1,
        const wchar_t *a2,
        va_list *a3)
{
  int v6; // eax
  __int64 v7; // rdi
  __int64 v8; // rdx
  __int64 v9; // rax
  STRSAFE_LPWSTR v10; // rsi
  HRESULT v11; // ebx
  __int64 v12; // rdx
  size_t v13; // rdi
  int argList; // [rsp+20h] [rbp-28h]
  va_list argLista; // [rsp+20h] [rbp-28h]
  size_t pcchNewDestLength[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  STRSAFE_LPWSTR pszDest; // [rsp+98h] [rbp+50h] BYREF

  v6 = _vscwprintf(a2, *a3);
  pszDest = 0;
  v7 = v6;
  v9 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         pcchNewDestLength,
         v8,
         v6);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &pszDest,
    v9);
  wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>((void **)pcchNewDestLength);
  v10 = pszDest;
  if ( !pszDest )
  {
    v11 = -2147024882;
    v12 = 1997;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v11,
      argList);
    goto LABEL_13;
  }
  v13 = v7 + 1;
  if ( !v13 )
  {
    v11 = -2147024809;
    goto LABEL_11;
  }
  if ( v13 > 0x7FFFFFFF )
  {
    v11 = -2147024809;
    *pszDest = 0;
LABEL_11:
    v12 = 2001;
    goto LABEL_12;
  }
  argLista = *a3;
  pcchNewDestLength[0] = 0;
  v11 = StringVPrintfWorkerW(pszDest, v13, pcchNewDestLength, a2, argLista);
  if ( v11 < 0 )
  {
    if ( (v13 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
      *v10 = 0;
    goto LABEL_11;
  }
  pcchNewDestLength[0] = (size_t)v10;
  pszDest = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    a1,
    pcchNewDestLength);
  wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>((void **)pcchNewDestLength);
  v11 = 0;
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>((void **)&pszDest);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001ef94  push    rbp
0x18001ef96  push    rbx
0x18001ef97  push    rsi
0x18001ef98  push    rdi
0x18001ef99  push    r14
0x18001ef9b  push    r15
0x18001ef9d  mov     rbp, rsp
0x18001efa0  sub     rsp, 48h
0x18001efa4  mov     r15, rdx
0x18001efa7  mov     r14, rcx
0x18001efaa  mov     rdx, [r8]; ArgList
0x18001efad  mov     rcx, r15; Format
0x18001efb0  mov     rbx, r8
0x18001efb3  call    cs:__imp__vscwprintf
0x18001efba  nop     dword ptr [rax+rax+00h]
0x18001efbf  lea     rcx, [rbp+pcchNewDestLength]
0x18001efc3  mov     [rbp+pszDest], 0
0x18001efcb  movsxd  rdi, eax
0x18001efce  mov     r8, rdi
0x18001efd1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001efd6  mov     rdx, rax
0x18001efd9  lea     rcx, [rbp+pszDest]
0x18001efdd  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18001efe2  lea     rcx, [rbp+pcchNewDestLength]
0x18001efe6  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001efeb  mov     rsi, [rbp+pszDest]
0x18001efef  test    rsi, rsi
0x18001eff2  jnz     short loc_18001F003
0x18001eff4  mov     ebx, 8007000Eh
0x18001eff9  mov     edx, 7CDh
0x18001effe  jmp     loc_18001F090
0x18001f003  add     rdi, 1
0x18001f007  jz      short loc_18001F07C
0x18001f009  cmp     rdi, 7FFFFFFFh
0x18001f010  jbe     short loc_18001F019
0x18001f012  mov     ebx, 80070057h
0x18001f017  jmp     short loc_18001F086
0x18001f019  mov     rax, [rbx]
0x18001f01c  lea     r8, [rbp+pcchNewDestLength]; pcchNewDestLength
0x18001f020  mov     r9, r15; pszFormat
0x18001f023  mov     [rsp+48h+argList], rax; argList
0x18001f028  mov     rdx, rdi; cchDest
0x18001f02b  mov     [rbp+pcchNewDestLength], 0
0x18001f033  mov     rcx, rsi; pszDest
0x18001f036  call    StringVPrintfWorkerW
0x18001f03b  mov     ebx, eax
0x18001f03d  test    eax, eax
0x18001f03f  jns     short loc_18001F057
0x18001f041  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001f04b  test    rax, rdi
0x18001f04e  jbe     short loc_18001F08B
0x18001f050  xor     eax, eax
0x18001f052  mov     [rsi], ax
0x18001f055  jmp     short loc_18001F08B
0x18001f057  lea     rdx, [rbp+pcchNewDestLength]
0x18001f05b  mov     [rbp+pcchNewDestLength], rsi
0x18001f05f  mov     rcx, r14
0x18001f062  mov     [rbp+pszDest], 0
0x18001f06a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18001f06f  lea     rcx, [rbp+pcchNewDestLength]
0x18001f073  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001f078  xor     ebx, ebx
0x18001f07a  jmp     short loc_18001F0A3
0x18001f07c  mov     ebx, 80070057h
0x18001f081  test    rdi, rdi
0x18001f084  jz      short loc_18001F08B
0x18001f086  xor     ecx, ecx
0x18001f088  mov     [rsi], cx
0x18001f08b  mov     edx, 7D1h; void *
0x18001f090  mov     rcx, [rbp+30h]; this
0x18001f094  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f09b  mov     r9d, ebx; char *
0x18001f09e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f0a3  lea     rcx, [rbp+pszDest]
0x18001f0a7  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001f0ac  mov     eax, ebx
0x18001f0ae  add     rsp, 48h
0x18001f0b2  pop     r15
0x18001f0b4  pop     r14
0x18001f0b6  pop     rdi
0x18001f0b7  pop     rsi
0x18001f0b8  pop     rbx
0x18001f0b9  pop     rbp
0x18001f0ba  retn
```
