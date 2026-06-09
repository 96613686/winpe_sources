# SplException::TImgErrorInfo::Free(void)

- ea: `0x1800973c8`
- end: `0x180097456`
- name: `?Free@TImgErrorInfo@SplException@@QEAAXXZ`
- size: `142`
- prototype: `void __fastcall(SplException::TImgErrorInfo *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180097354`
- `0x1800ad334`
- `0x1800b82a8`
- `0x1800dac74`
- `0x18010a788`
- `0x18010a8a4`

## callees

- `0x1800973c8`
- `0x1800d6354`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097421`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097421`
- `OLEAUT32!__imp_SysFreeString` at `0x1800973dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800973e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800973f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800973fb`
- `OLEAUT32!__imp_SysFreeString` at `0x180097410`
- `OLEAUT32!__imp_SysFreeString` at `0x18009742b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800973dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800973e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800973f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800973fb`
- `OLEAUT32!__imp_SysFreeString` at `0x180097410`
- `OLEAUT32!__imp_SysFreeString` at `0x18009742b`

## pseudocode

```c
void __fastcall SplException::TImgErrorInfo::Free(SplException::TImgErrorInfo *this)
{
  __int64 i; // rsi

  SysFreeString(*(BSTR *)this);
  SysFreeString(*((BSTR *)this + 4));
  SysFreeString(*((BSTR *)this + 5));
  SysFreeString(*((BSTR *)this + 6));
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 18); i = (unsigned int)(i + 1) )
    SysFreeString(*(BSTR *)(*((_QWORD *)this + 10) + 8 * i));
  CoTaskMemFree(*((LPVOID *)this + 10));
  SysFreeString(*((BSTR *)this + 11));
  memset_0(this, 0, 0x68u);
  *((_DWORD *)this + 24) = -1;
}

```

## disassembly

```asm
0x1800973c8  mov     [rsp+arg_0], rbx
0x1800973cd  mov     [rsp+arg_8], rsi
0x1800973d2  push    rdi
0x1800973d3  sub     rsp, 20h
0x1800973d7  mov     rbx, rcx
0x1800973da  mov     rcx, [rcx]; bstrString
0x1800973dd  call    cs:__imp_SysFreeString
0x1800973e3  mov     rcx, [rbx+20h]; bstrString
0x1800973e7  call    cs:__imp_SysFreeString
0x1800973ed  mov     rcx, [rbx+28h]; bstrString
0x1800973f1  call    cs:__imp_SysFreeString
0x1800973f7  mov     rcx, [rbx+30h]; bstrString
0x1800973fb  call    cs:__imp_SysFreeString
0x180097401  xor     esi, esi
0x180097403  cmp     [rbx+48h], esi
0x180097406  jbe     short loc_18009741D
0x180097408  mov     rcx, [rbx+50h]
0x18009740c  mov     rcx, [rcx+rsi*8]; bstrString
0x180097410  call    cs:__imp_SysFreeString
0x180097416  inc     esi
0x180097418  cmp     esi, [rbx+48h]
0x18009741b  jb      short loc_180097408
0x18009741d  mov     rcx, [rbx+50h]; pv
0x180097421  call    cs:__imp_CoTaskMemFree
0x180097427  mov     rcx, [rbx+58h]; bstrString
0x18009742b  call    cs:__imp_SysFreeString
0x180097431  xor     edx, edx; Val
0x180097433  mov     rcx, rbx; void *
0x180097436  lea     r8d, [rdx+68h]; Size
0x18009743a  call    memset_0
0x18009743f  mov     rsi, [rsp+28h+arg_8]
0x180097444  mov     dword ptr [rbx+60h], 0FFFFFFFFh
0x18009744b  mov     rbx, [rsp+28h+arg_0]
0x180097450  add     rsp, 20h
0x180097454  pop     rdi
0x180097455  retn
```
