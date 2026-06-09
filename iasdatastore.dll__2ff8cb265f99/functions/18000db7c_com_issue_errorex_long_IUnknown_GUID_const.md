# _com_issue_errorex(long,IUnknown *,_GUID const &)

- ea: `0x18000db7c`
- end: `0x18000dc0e`
- name: `?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z`
- size: `146`
- prototype: `void __fastcall __noreturn(int, struct IUnknown *, const struct _GUID *)`
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800079fc`
- `0x1800081b8`
- `0x1800086c8`
- `0x180008ce4`
- `0x1800093cc`
- `0x180009af8`
- `0x18000a4a0`
- `0x18000b210`
- `0x18000bf74`
- `0x18000c000`

## callees

- `0x18000db7c`
- `0x18000dc14`
- `0x180010010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x18000dbee`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18000dbee`

## pseudocode

```c
void __fastcall __noreturn _com_issue_errorex(int a1, struct IUnknown *a2, const struct _GUID *a3)
{
  struct IErrorInfo *v5; // rdx
  struct IUnknownVtbl *lpVtbl; // rax
  int v8; // ebx
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF
  IErrorInfo *pperrinfo; // [rsp+48h] [rbp+20h] BYREF

  v5 = 0;
  pperrinfo = 0;
  if ( a2 )
  {
    lpVtbl = a2->lpVtbl;
    v9 = 0;
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
           a2,
           &GUID_df0b3d60_548f_101b_8e65_08002b2bd119,
           &v9) < 0
      || (v8 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *))(*(_QWORD *)v9 + 24LL))(v9, a3),
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9),
          v8)
      || !GetErrorInfo(0, &pperrinfo) )
    {
      v5 = pperrinfo;
    }
    else
    {
      v5 = 0;
      pperrinfo = 0;
    }
  }
  _com_raise_error(a1, v5);
}

```

## disassembly

```asm
0x18000db7c  mov     r11, rsp
0x18000db7f  mov     [r11+8], rbx
0x18000db83  push    rdi
0x18000db84  sub     rsp, 20h
0x18000db88  mov     r9, rdx
0x18000db8b  mov     rbx, r8
0x18000db8e  xor     edx, edx
0x18000db90  mov     edi, ecx
0x18000db92  mov     [r11+20h], rdx
0x18000db96  test    r9, r9
0x18000db99  jz      short loc_18000DC06
0x18000db9b  mov     rax, [r9]
0x18000db9e  lea     r8, [r11+10h]
0x18000dba2  mov     [r11+10h], rdx
0x18000dba6  mov     rcx, r9
0x18000dba9  lea     rdx, _GUID_df0b3d60_548f_101b_8e65_08002b2bd119
0x18000dbb0  mov     rax, [rax]
0x18000dbb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbb8  test    eax, eax
0x18000dbba  js      short loc_18000DC01
0x18000dbbc  mov     rcx, [rsp+28h+arg_8]
0x18000dbc1  mov     rdx, rbx
0x18000dbc4  mov     rax, [rcx]
0x18000dbc7  mov     rax, [rax+18h]
0x18000dbcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbd0  mov     rcx, [rsp+28h+arg_8]
0x18000dbd5  mov     ebx, eax
0x18000dbd7  mov     rdx, [rcx]
0x18000dbda  mov     rax, [rdx+10h]
0x18000dbde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbe3  test    ebx, ebx
0x18000dbe5  jnz     short loc_18000DC01
0x18000dbe7  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x18000dbec  xor     ecx, ecx; dwReserved
0x18000dbee  call    cs:__imp_GetErrorInfo
0x18000dbf4  test    eax, eax
0x18000dbf6  jz      short loc_18000DC01
0x18000dbf8  xor     edx, edx
0x18000dbfa  mov     [rsp+28h+pperrinfo], rdx
0x18000dbff  jmp     short loc_18000DC06
0x18000dc01  mov     rdx, [rsp+28h+pperrinfo]; struct IErrorInfo *
0x18000dc06  mov     ecx, edi; int
0x18000dc08  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
