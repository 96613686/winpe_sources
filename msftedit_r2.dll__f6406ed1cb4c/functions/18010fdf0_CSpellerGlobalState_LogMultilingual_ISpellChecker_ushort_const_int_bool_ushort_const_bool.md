# CSpellerGlobalState::LogMultilingual(ISpellChecker *,ushort const *,int,bool,ushort const *,bool)

- ea: `0x18010fdf0`
- end: `0x18010feeb`
- name: `?LogMultilingual@CSpellerGlobalState@@QEAA_NPEAUISpellChecker@@PEBGH_N12@Z`
- size: `251`
- prototype: `bool(CSpellerGlobalState *__hidden this, struct ISpellChecker *, const unsigned __int16 *, int, bool, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180109d50`
- `0x180274fa0`

## callees

- `0x18010fdf0`
- `0x180121bb0`
- `0x180124800`
- `0x180128980`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010fe7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010fe7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fe4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fece`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fe4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fece`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010febd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010febd`

## pseudocode

```c
char __fastcall CSpellerGlobalState::LogMultilingual(
        CSpellerGlobalState *this,
        struct ISpellChecker *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        bool a5,
        const unsigned __int16 *a6,
        bool a7)
{
  __int64 v7; // rax
  char v10; // si
  __int64 v11; // rdi
  int (__fastcall *v12)(__int64, HSTRING *); // rbx
  unsigned __int64 v13; // rdx
  unsigned __int8 v14; // cl
  const unsigned __int16 *StringRawBuffer; // rbx
  __int64 v16; // rcx
  CSpellCheckerTelemetry *v17; // rcx
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF
  HSTRING string; // [rsp+50h] [rbp+18h] BYREF

  string = (HSTRING)a3;
  v7 = *(_QWORD *)a2;
  pv = 0;
  v10 = 0;
  if ( (*(int (__fastcall **)(struct ISpellChecker *, LPVOID *))(v7 + 24))(a2, &pv) >= 0 )
  {
    v11 = *((_QWORD *)this + 37);
    string = 0;
    v12 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v11 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    if ( v12(v11, &string) >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( a7 )
      {
        if ( CSpellCheckerTelemetry::IsEnabled(v14, v13) )
        {
          wil::details::static_lazy<CSpellCheckerTelemetry>::get(
            v16,
            _lambda_3c853e741dc03bb96b7f8662095382b4_::_lambda_invoker_cdecl_);
          CSpellCheckerTelemetry::LogSpellerMultilingual_(v17, (unsigned __int16 *)pv, StringRawBuffer, a4);
        }
        v10 = 1;
      }
    }
    CoTaskMemFree(pv);
    WindowsDeleteString(string);
  }
  return v10;
}

```

## disassembly

```asm
0x18010fdf0  mov     r11, rsp
0x18010fdf3  mov     [r11+8], rbx
0x18010fdf7  mov     [r11+18h], r8
0x18010fdfb  push    rbp
0x18010fdfc  push    rsi
0x18010fdfd  push    rdi
0x18010fdfe  sub     rsp, 20h
0x18010fe02  mov     rax, [rdx]
0x18010fe05  mov     r8, rdx
0x18010fe08  mov     rdi, rcx
0x18010fe0b  mov     qword ptr [r11+10h], 0
0x18010fe13  lea     rdx, [r11+10h]
0x18010fe17  mov     rcx, r8
0x18010fe1a  mov     ebp, r9d
0x18010fe1d  xor     sil, sil
0x18010fe20  mov     rax, [rax+18h]
0x18010fe24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fe29  test    eax, eax
0x18010fe2b  js      loc_18010FEDA
0x18010fe31  mov     rdi, [rdi+128h]
0x18010fe38  xor     ecx, ecx; string
0x18010fe3a  mov     [rsp+38h+string], 0
0x18010fe43  mov     rax, [rdi]
0x18010fe46  mov     rbx, [rax+38h]
0x18010fe4a  call    cs:__imp_WindowsDeleteString
0x18010fe51  nop     dword ptr [rax+rax+00h]
0x18010fe56  lea     rdx, [rsp+38h+string]
0x18010fe5b  mov     [rsp+38h+string], 0
0x18010fe64  mov     rcx, rdi
0x18010fe67  mov     rax, rbx
0x18010fe6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fe6f  test    eax, eax
0x18010fe71  js      short loc_18010FEB8
0x18010fe73  mov     rcx, [rsp+38h+string]; string
0x18010fe78  xor     edx, edx; length
0x18010fe7a  call    cs:__imp_WindowsGetStringRawBuffer
0x18010fe81  nop     dword ptr [rax+rax+00h]
0x18010fe86  mov     rbx, rax
0x18010fe89  cmp     [rsp+38h+arg_30], sil
0x18010fe8e  jz      short loc_18010FEB8
0x18010fe90  call    ?IsEnabled@CSpellCheckerTelemetry@@SA_NE_K@Z; CSpellCheckerTelemetry::IsEnabled(uchar,unsigned __int64)
0x18010fe95  test    al, al
0x18010fe97  jz      short loc_18010FEB5
0x18010fe99  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_3c853e741dc03bb96b7f8662095382b4_@@CA@XZ; _lambda_3c853e741dc03bb96b7f8662095382b4_::_lambda_invoker_cdecl_(void)
0x18010fea0  call    ?get@?$static_lazy@VCSpellCheckerTelemetry@@@details@wil@@QEAAPEAVCSpellCheckerTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CSpellCheckerTelemetry>::get(void (*)(void))
0x18010fea5  mov     rdx, [rsp+38h+pv]; unsigned __int16 *
0x18010feaa  mov     r9d, ebp; unsigned int
0x18010fead  mov     r8, rbx; unsigned __int16 *
0x18010feb0  call    ?LogSpellerMultilingual_@CSpellCheckerTelemetry@@QEBAXPEAGPEBGK@Z; CSpellCheckerTelemetry::LogSpellerMultilingual_(ushort *,ushort const *,ulong)
0x18010feb5  mov     sil, 1
0x18010feb8  mov     rcx, [rsp+38h+pv]; pv
0x18010febd  call    cs:__imp_CoTaskMemFree
0x18010fec4  nop     dword ptr [rax+rax+00h]
0x18010fec9  mov     rcx, [rsp+38h+string]; string
0x18010fece  call    cs:__imp_WindowsDeleteString
0x18010fed5  nop     dword ptr [rax+rax+00h]
0x18010feda  mov     rbx, [rsp+38h+arg_0]
0x18010fedf  mov     al, sil
0x18010fee2  add     rsp, 20h
0x18010fee6  pop     rdi
0x18010fee7  pop     rsi
0x18010fee8  pop     rbp
0x18010fee9  retn
```
