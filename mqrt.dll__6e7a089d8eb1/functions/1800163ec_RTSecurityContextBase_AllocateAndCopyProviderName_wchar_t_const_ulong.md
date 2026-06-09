# RTSecurityContextBase::AllocateAndCopyProviderName(wchar_t const *,ulong)

- ea: `0x1800163ec`
- end: `0x1800164a1`
- name: `?AllocateAndCopyProviderName@RTSecurityContextBase@@IEAAXPEB_WK@Z`
- size: `181`
- prototype: `void(RTSecurityContextBase *__hidden this, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016944`
- `0x180016f9c`

## callees

- `0x1800022d6`
- `0x180006fdc`
- `0x180013c74`
- `0x1800163ec`
- `0x180021010`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18001646d`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18001646d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RTSecurityContextBase::AllocateAndCopyProviderName(
        RTSecurityContextBase *this,
        const wchar_t *a2,
        unsigned int a3)
{
  wchar_t *v6; // rax
  int v7; // eax
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  *((_DWORD *)this + 13) = a3;
  if ( a2 && a3 )
  {
    v6 = (wchar_t *)MmAllocate(saturated_mul(a3, 2u));
    *((_QWORD *)this + 3) = v6;
    v7 = StringCchCopyW(v6, a3, a2);
    if ( v7 < 0 )
    {
      LogMsgHR(v7, (wchar_t *)L"rt/rtsecctx", 0xC8u);
      exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x1800163ec  mov     [rsp+arg_0], rbx
0x1800163f1  mov     [rsp+arg_8], rsi
0x1800163f6  push    rdi
0x1800163f7  sub     rsp, 40h
0x1800163fb  mov     rdi, rdx
0x1800163fe  mov     rsi, rcx
0x180016401  mov     [rcx+34h], r8d
0x180016405  test    rdx, rdx
0x180016408  jz      loc_180016491
0x18001640e  test    r8d, r8d
0x180016411  jz      short loc_180016491
0x180016413  mov     ebx, r8d
0x180016416  mov     eax, 2
0x18001641b  mul     rbx
0x18001641e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180016425  cmovb   rax, rcx
0x180016429  mov     rcx, rax; unsigned __int64
0x18001642c  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180016431  mov     [rsi+18h], rax
0x180016435  mov     r8, rdi; wchar_t *
0x180016438  mov     edx, ebx; unsigned __int64
0x18001643a  mov     rcx, rax; wchar_t *
0x18001643d  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180016442  test    eax, eax
0x180016444  jns     short loc_180016491
0x180016446  mov     r8d, 0C8h; unsigned __int16
0x18001644c  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x180016453  mov     ecx, eax; int
0x180016455  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001645a  nop
0x18001645b  mov     r8d, 1
0x180016461  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x180016468  lea     rcx, [rsp+48h+pExceptionObject]
0x18001646d  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180016473  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001647a  mov     [rsp+48h+pExceptionObject], rax
0x18001647f  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180016486  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001648b  call    _CxxThrowException_0
0x180016491  mov     rbx, [rsp+48h+arg_0]
0x180016496  mov     rsi, [rsp+48h+arg_8]
0x18001649b  add     rsp, 40h
0x18001649f  pop     rdi
0x1800164a0  retn
```
