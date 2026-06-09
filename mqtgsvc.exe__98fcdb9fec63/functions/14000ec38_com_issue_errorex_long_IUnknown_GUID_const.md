# _com_issue_errorex(long,IUnknown *,_GUID const &)

- ea: `0x14000ec38`
- end: `0x14000ecca`
- name: `?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z`
- size: `146`
- prototype: `void __fastcall __noreturn(int, struct IUnknown *, const struct _GUID *)`
- caller_count: `16`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003f54`
- `0x140008378`
- `0x140008c04`
- `0x140008f08`
- `0x140009180`
- `0x140009e04`
- `0x14000a3a8`
- `0x14000a6dc`
- `0x14000b6f0`
- `0x14000b93c`
- `0x14000b984`
- `0x14000baa8`
- `0x14000d440`
- `0x14000d5ac`
- `0x14000e6d4`
- `0x14000e768`

## callees

- `0x14000ec38`
- `0x14000ecd0`
- `0x140020010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x14000ecaa`
- `OLEAUT32!__imp_GetErrorInfo` at `0x14000ecaa`

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
0x14000ec38  mov     r11, rsp
0x14000ec3b  mov     [r11+8], rbx
0x14000ec3f  push    rdi
0x14000ec40  sub     rsp, 20h
0x14000ec44  mov     r9, rdx
0x14000ec47  mov     rbx, r8
0x14000ec4a  xor     edx, edx
0x14000ec4c  mov     edi, ecx
0x14000ec4e  mov     [r11+20h], rdx
0x14000ec52  test    r9, r9
0x14000ec55  jz      short loc_14000ECC2
0x14000ec57  mov     rax, [r9]
0x14000ec5a  lea     r8, [r11+10h]
0x14000ec5e  mov     [r11+10h], rdx
0x14000ec62  mov     rcx, r9
0x14000ec65  lea     rdx, _GUID_df0b3d60_548f_101b_8e65_08002b2bd119
0x14000ec6c  mov     rax, [rax]
0x14000ec6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec74  test    eax, eax
0x14000ec76  js      short loc_14000ECBD
0x14000ec78  mov     rcx, [rsp+28h+arg_8]
0x14000ec7d  mov     rdx, rbx
0x14000ec80  mov     rax, [rcx]
0x14000ec83  mov     rax, [rax+18h]
0x14000ec87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec8c  mov     rcx, [rsp+28h+arg_8]
0x14000ec91  mov     ebx, eax
0x14000ec93  mov     rdx, [rcx]
0x14000ec96  mov     rax, [rdx+10h]
0x14000ec9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec9f  test    ebx, ebx
0x14000eca1  jnz     short loc_14000ECBD
0x14000eca3  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x14000eca8  xor     ecx, ecx; dwReserved
0x14000ecaa  call    cs:__imp_GetErrorInfo
0x14000ecb0  test    eax, eax
0x14000ecb2  jz      short loc_14000ECBD
0x14000ecb4  xor     edx, edx
0x14000ecb6  mov     [rsp+28h+pperrinfo], rdx
0x14000ecbb  jmp     short loc_14000ECC2
0x14000ecbd  mov     rdx, [rsp+28h+pperrinfo]; struct IErrorInfo *
0x14000ecc2  mov     ecx, edi; int
0x14000ecc4  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
