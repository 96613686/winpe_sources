# srcsrvResolveTokenVar(_PROCESS_ENTRY *,void *,ushort const *,ushort const *,ushort *,unsigned __int64)

- ea: `0x18019f818`
- end: `0x18019f8dc`
- name: `?srcsrvResolveTokenVar@@YAHPEAU_PROCESS_ENTRY@@PEAXPEBG2PEAG_K@Z`
- size: `196`
- prototype: `__int64 __usercall@<rax>(struct _PROCESS_ENTRY *@<rcx>, void *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1801a7270`

## callees

- `0x18000dfac`
- `0x180021374`
- `0x18019f1c4`
- `0x18019f818`
- `0x1801bf65c`
- `0x180205010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f8a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f8a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f867`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f867`

## string_xrefs

- `0x18019f853`: `Need a newer version of srcsrv.dll\n`

## pseudocode

```c
__int64 __fastcall srcsrvResolveTokenVar(
        struct _PROCESS_ENTRY *a1,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int64 a6)
{
  void *v11; // rdx
  DWORD v12; // ecx
  int *v13; // r8
  unsigned __int16 **v14; // r9
  WCHAR *v15; // rax

  if ( (unsigned int)srcsrvInit(*((void **)a1 + 6)) )
  {
    if ( qword_1802AF998 )
    {
      if ( (unsigned int)qword_1802AF998(*((_QWORD *)a1 + 6), a2, a3, a4, a5, a6) )
        return 1;
      if ( GetLastError() != 22 && (unsigned int)spew() )
      {
        v15 = FormatAnyStatus(v12, v11, v13, v14);
        _pwprint(a1, L"Source server error - %s\n", v15);
      }
    }
    else
    {
      if ( (unsigned int)spew() )
        _pwprint(a1, L"Need a newer version of srcsrv.dll\n");
      SetLastError(0x32u);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18019f818  push    rbx
0x18019f81a  push    rbp
0x18019f81b  push    rsi
0x18019f81c  push    rdi
0x18019f81d  sub     rsp, 48h
0x18019f821  mov     rbx, rcx
0x18019f824  mov     rdi, r9
0x18019f827  mov     rcx, [rcx+30h]; void *
0x18019f82b  mov     rsi, r8
0x18019f82e  mov     rbp, rdx
0x18019f831  call    ?srcsrvInit@@YAHPEAX@Z; srcsrvInit(void *)
0x18019f836  test    eax, eax
0x18019f838  jz      loc_18019F8D1
0x18019f83e  mov     rax, cs:qword_1802AF998
0x18019f845  test    rax, rax
0x18019f848  jnz     short loc_18019F86F
0x18019f84a  call    ?spew@@YAHXZ; spew(void)
0x18019f84f  test    eax, eax
0x18019f851  jz      short loc_18019F862
0x18019f853  lea     rdx, aNeedANewerVers; "Need a newer version of srcsrv.dll\n"
0x18019f85a  mov     rcx, rbx; struct _PROCESS_ENTRY *
0x18019f85d  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18019f862  mov     ecx, 32h ; '2'; dwErrCode
0x18019f867  call    cs:__imp_SetLastError
0x18019f86d  jmp     short loc_18019F8D1
0x18019f86f  mov     ecx, dword ptr [rsp+68h+arg_28]
0x18019f876  mov     r9, rdi
0x18019f879  mov     [rsp+68h+var_40], ecx
0x18019f87d  mov     r8, rsi
0x18019f880  mov     rcx, [rsp+68h+arg_20]
0x18019f888  mov     rdx, rbp
0x18019f88b  mov     [rsp+68h+var_48], rcx
0x18019f890  mov     rcx, [rbx+30h]
0x18019f894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f899  test    eax, eax
0x18019f89b  jz      short loc_18019F8A4
0x18019f89d  mov     eax, 1
0x18019f8a2  jmp     short loc_18019F8D3
0x18019f8a4  call    cs:__imp_GetLastError
0x18019f8aa  mov     ecx, eax
0x18019f8ac  cmp     eax, 16h
0x18019f8af  jz      short loc_18019F8D1
0x18019f8b1  call    ?spew@@YAHXZ; spew(void)
0x18019f8b6  test    eax, eax
0x18019f8b8  jz      short loc_18019F8D1
0x18019f8ba  call    ?FormatAnyStatus@@YAPEBGJPEAXPEAHPEAPEAG@Z; FormatAnyStatus(long,void *,int *,ushort * *)
0x18019f8bf  mov     r8, rax
0x18019f8c2  lea     rdx, aSourceServerEr; "Source server error - %s\n"
0x18019f8c9  mov     rcx, rbx; struct _PROCESS_ENTRY *
0x18019f8cc  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18019f8d1  xor     eax, eax
0x18019f8d3  add     rsp, 48h
0x18019f8d7  pop     rdi
0x18019f8d8  pop     rsi
0x18019f8d9  pop     rbp
0x18019f8da  pop     rbx
0x18019f8db  retn
```
