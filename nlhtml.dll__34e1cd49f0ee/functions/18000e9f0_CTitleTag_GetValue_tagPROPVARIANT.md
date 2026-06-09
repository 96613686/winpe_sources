# CTitleTag::GetValue(tagPROPVARIANT * *)

- ea: `0x18000e9f0`
- end: `0x18000eac0`
- name: `?GetValue@CTitleTag@@UEAAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(CTitleTag *__hidden this, struct tagPROPVARIANT **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000e9f0`
- `0x18000eac8`
- `0x18000fab0`
- `0x180023388`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eab8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eab8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ea1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ea3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ea1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ea3b`

## pseudocode

```c
__int64 __fastcall CTitleTag::GetValue(const void **this, struct tagPROPVARIANT **a2)
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
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\titletag.cxx",
    (const wchar_t *)0x65,
    (unsigned int)L"[HTML] CTitleTag::GetValue, unknown value of _eState: %d\n",
    v2);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000e9f0  push    rbx
0x18000e9f2  push    rsi
0x18000e9f3  push    rdi
0x18000e9f4  push    r14
0x18000e9f6  sub     rsp, 28h
0x18000e9fa  mov     r9d, [rcx+0F8h]; wchar_t *
0x18000ea01  mov     r14, rdx
0x18000ea04  mov     rdi, rcx
0x18000ea07  test    r9d, r9d
0x18000ea0a  jnz     short loc_18000EA89
0x18000ea0c  call    ?ReadProperty@CPropertyTag@@IEAAJXZ; CPropertyTag::ReadProperty(void)
0x18000ea11  test    eax, eax
0x18000ea13  js      short loc_18000EA78
0x18000ea15  mov     ecx, 18h; cb
0x18000ea1a  call    cs:__imp_CoTaskMemAlloc
0x18000ea20  mov     rbx, rax
0x18000ea23  test    rax, rax
0x18000ea26  jz      short loc_18000EA82
0x18000ea28  mov     word ptr [rax], 1Fh
0x18000ea2d  mov     eax, [rdi+310h]
0x18000ea33  add     eax, eax
0x18000ea35  movsxd  rsi, eax
0x18000ea38  mov     rcx, rsi; cb
0x18000ea3b  call    cs:__imp_CoTaskMemAlloc
0x18000ea41  mov     [rbx+8], rax
0x18000ea45  test    rax, rax
0x18000ea48  jz      short loc_18000EAB5
0x18000ea4a  mov     rdx, [rdi+108h]; Src
0x18000ea51  mov     r8, rsi; Size
0x18000ea54  mov     rcx, rax; void *
0x18000ea57  call    memcpy_0
0x18000ea5c  mov     [r14], rbx
0x18000ea5f  mov     eax, 4170Ah
0x18000ea64  mov     dword ptr [rdi+310h], 0
0x18000ea6e  mov     dword ptr [rdi+0F8h], 1
0x18000ea78  add     rsp, 28h
0x18000ea7c  pop     r14
0x18000ea7e  pop     rdi
0x18000ea7f  pop     rsi
0x18000ea80  pop     rbx
0x18000ea81  retn
0x18000ea82  mov     eax, 8007000Eh
0x18000ea87  jmp     short loc_18000EA78
0x18000ea89  cmp     r9d, 1
0x18000ea8d  jnz     short loc_18000EA96
0x18000ea8f  mov     eax, 80041702h
0x18000ea94  jmp     short loc_18000EA78
0x18000ea96  lea     r8, aHtmlCtitletagG; "[HTML] CTitleTag::GetValue, unknown val"...
0x18000ea9d  mov     edx, 65h ; 'e'; wchar_t *
0x18000eaa2  lea     rcx, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000eaa9  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000eaae  mov     eax, 80004005h
0x18000eab3  jmp     short loc_18000EA78
0x18000eab5  mov     rcx, rbx; pv
0x18000eab8  call    cs:__imp_CoTaskMemFree
0x18000eabe  jmp     short loc_18000EA82
```
