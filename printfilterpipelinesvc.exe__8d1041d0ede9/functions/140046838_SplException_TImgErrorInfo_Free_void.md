# SplException::TImgErrorInfo::Free(void)

- ea: `0x140046838`
- end: `0x1400468c6`
- name: `?Free@TImgErrorInfo@SplException@@QEAAXXZ`
- size: `142`
- prototype: `void __fastcall(SplException::TImgErrorInfo *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140045e40`
- `0x1400463f8`
- `0x140046578`
- `0x1400467b8`
- `0x1400467c4`
- `0x1400537a4`

## callees

- `0x140002c68`
- `0x140046838`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14004684d`
- `OLEAUT32!__imp_SysFreeString` at `0x140046857`
- `OLEAUT32!__imp_SysFreeString` at `0x140046861`
- `OLEAUT32!__imp_SysFreeString` at `0x14004686b`
- `OLEAUT32!__imp_SysFreeString` at `0x140046880`
- `OLEAUT32!__imp_SysFreeString` at `0x14004689b`
- `OLEAUT32!__imp_SysFreeString` at `0x14004684d`
- `OLEAUT32!__imp_SysFreeString` at `0x140046857`
- `OLEAUT32!__imp_SysFreeString` at `0x140046861`
- `OLEAUT32!__imp_SysFreeString` at `0x14004686b`
- `OLEAUT32!__imp_SysFreeString` at `0x140046880`
- `OLEAUT32!__imp_SysFreeString` at `0x14004689b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140046891`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140046891`

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
0x140046838  mov     [rsp+arg_0], rbx
0x14004683d  mov     [rsp+arg_8], rsi
0x140046842  push    rdi
0x140046843  sub     rsp, 20h
0x140046847  mov     rbx, rcx
0x14004684a  mov     rcx, [rcx]; bstrString
0x14004684d  call    cs:__imp_SysFreeString
0x140046853  mov     rcx, [rbx+20h]; bstrString
0x140046857  call    cs:__imp_SysFreeString
0x14004685d  mov     rcx, [rbx+28h]; bstrString
0x140046861  call    cs:__imp_SysFreeString
0x140046867  mov     rcx, [rbx+30h]; bstrString
0x14004686b  call    cs:__imp_SysFreeString
0x140046871  xor     esi, esi
0x140046873  cmp     [rbx+48h], esi
0x140046876  jbe     short loc_14004688D
0x140046878  mov     rcx, [rbx+50h]
0x14004687c  mov     rcx, [rcx+rsi*8]; bstrString
0x140046880  call    cs:__imp_SysFreeString
0x140046886  inc     esi
0x140046888  cmp     esi, [rbx+48h]
0x14004688b  jb      short loc_140046878
0x14004688d  mov     rcx, [rbx+50h]; pv
0x140046891  call    cs:__imp_CoTaskMemFree
0x140046897  mov     rcx, [rbx+58h]; bstrString
0x14004689b  call    cs:__imp_SysFreeString
0x1400468a1  xor     edx, edx; Val
0x1400468a3  mov     rcx, rbx; void *
0x1400468a6  lea     r8d, [rdx+68h]; Size
0x1400468aa  call    memset_0
0x1400468af  mov     rsi, [rsp+28h+arg_8]
0x1400468b4  mov     dword ptr [rbx+60h], 0FFFFFFFFh
0x1400468bb  mov     rbx, [rsp+28h+arg_0]
0x1400468c0  add     rsp, 20h
0x1400468c4  pop     rdi
0x1400468c5  retn
```
