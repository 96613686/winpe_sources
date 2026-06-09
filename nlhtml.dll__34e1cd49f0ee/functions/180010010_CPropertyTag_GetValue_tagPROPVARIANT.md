# CPropertyTag::GetValue(tagPROPVARIANT * *)

- ea: `0x180010010`
- end: `0x1800100e3`
- name: `?GetValue@CPropertyTag@@UEAAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(CPropertyTag *__hidden this, struct tagPROPVARIANT **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000eac8`
- `0x18000fab0`
- `0x180010010`
- `0x180023388`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800100a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800100a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010069`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010091`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010069`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010091`

## pseudocode

```c
__int64 __fastcall CPropertyTag::GetValue(const void **this, struct tagPROPVARIANT **a2)
{
  const wchar_t *v2; // r9
  __int64 result; // rax
  struct tagPROPVARIANT *v6; // rax
  struct tagPROPVARIANT *v7; // rbx
  SIZE_T v8; // rsi
  void *v9; // rax

  v2 = (const wchar_t *)*((unsigned int *)this + 62);
  if ( !(_DWORD)v2 )
  {
    result = CPropertyTag::ReadProperty((CPropertyTag *)this);
    if ( (int)result < 0 )
      return result;
    v6 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
    v7 = v6;
    if ( v6 )
    {
      v6->vt = 31;
      v8 = 2 * *((_DWORD *)this + 196);
      v9 = CoTaskMemAlloc(v8);
      v7->hVal.QuadPart = (LONGLONG)v9;
      if ( v9 )
      {
        memcpy_0(v9, this[33], v8);
        *a2 = v7;
        result = 268042;
        *((_DWORD *)this + 196) = 0;
        *((_DWORD *)this + 62) = 1;
        return result;
      }
      CoTaskMemFree(v7);
    }
    return 2147942414LL;
  }
  if ( (_DWORD)v2 == 1 )
    return 2147751682LL;
  SearchIndexerDebug::Error(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\proptag.cxx",
    (const wchar_t *)0x18F,
    (unsigned int)L"[HTML] CTitleTag::GetValue, unknown value of _eState: %d\n",
    v2);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180010010  push    rbx
0x180010012  push    rsi
0x180010013  push    rdi
0x180010014  push    r14
0x180010016  sub     rsp, 28h
0x18001001a  mov     r9d, [rcx+0F8h]; wchar_t *
0x180010021  mov     r14, rdx
0x180010024  mov     rdi, rcx
0x180010027  test    r9d, r9d
0x18001002a  jz      short loc_18001005B
0x18001002c  cmp     r9d, 1
0x180010030  jz      short loc_180010054
0x180010032  lea     r8, aHtmlCtitletagG; "[HTML] CTitleTag::GetValue, unknown val"...
0x180010039  mov     edx, 18Fh; wchar_t *
0x18001003e  lea     rcx, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180010045  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x18001004a  mov     eax, 80004005h
0x18001004f  jmp     loc_1800100D9
0x180010054  mov     eax, 80041702h
0x180010059  jmp     short loc_1800100D9
0x18001005b  call    ?ReadProperty@CPropertyTag@@IEAAJXZ; CPropertyTag::ReadProperty(void)
0x180010060  test    eax, eax
0x180010062  js      short loc_1800100D9
0x180010064  mov     ecx, 18h; cb
0x180010069  call    cs:__imp_CoTaskMemAlloc
0x18001006f  mov     rbx, rax
0x180010072  test    rax, rax
0x180010075  jnz     short loc_18001007E
0x180010077  mov     eax, 8007000Eh
0x18001007c  jmp     short loc_1800100D9
0x18001007e  mov     word ptr [rax], 1Fh
0x180010083  mov     eax, [rdi+310h]
0x180010089  add     eax, eax
0x18001008b  movsxd  rsi, eax
0x18001008e  mov     rcx, rsi; cb
0x180010091  call    cs:__imp_CoTaskMemAlloc
0x180010097  mov     [rbx+8], rax
0x18001009b  test    rax, rax
0x18001009e  jnz     short loc_1800100AB
0x1800100a0  mov     rcx, rbx; pv
0x1800100a3  call    cs:__imp_CoTaskMemFree
0x1800100a9  jmp     short loc_180010077
0x1800100ab  mov     rdx, [rdi+108h]; Src
0x1800100b2  mov     r8, rsi; Size
0x1800100b5  mov     rcx, rax; void *
0x1800100b8  call    memcpy_0
0x1800100bd  mov     [r14], rbx
0x1800100c0  mov     eax, 4170Ah
0x1800100c5  mov     dword ptr [rdi+310h], 0
0x1800100cf  mov     dword ptr [rdi+0F8h], 1
0x1800100d9  add     rsp, 28h
0x1800100dd  pop     r14
0x1800100df  pop     rdi
0x1800100e0  pop     rsi
0x1800100e1  pop     rbx
0x1800100e2  retn
```
