# CMMCProtocol::ScParseTaskpadURL(ushort const *,_GUID &)

- ea: `0x18009f60c`
- end: `0x18009f6f8`
- name: `?ScParseTaskpadURL@CMMCProtocol@@SA?AVSC@mmcerror@@PEBGAEAU_GUID@@@Z`
- size: `236`
- prototype: `mmcerror::SC *__fastcall(mmcerror::SC *, const wchar_t *, GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18009f700`

## callees

- `0x1800304c0`
- `0x18009f60c`

## import_xrefs

- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18009f627`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18009f627`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18009f6a6`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18009f6c4`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18009f6a6`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18009f6c4`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18009f6db`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18009f6db`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18009f664`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18009f664`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18009f639`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18009f639`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18009f679`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18009f6ce`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18009f679`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18009f6ce`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18009f66f`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18009f6e6`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18009f66f`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18009f6e6`
- `msvcrt!_wcsnicmp` at `0x18009f693`
- `msvcrt!_wcsnicmp` at `0x18009f693`
- `ole32!CLSIDFromString` at `0x18009f6b8`
- `ole32!CLSIDFromString` at `0x18009f6b8`

## string_xrefs

- `0x18009f62e`: `CMMCProtocol::ScParseTaskpadURL`

## pseudocode

```c
mmcerror::SC *__fastcall CMMCProtocol::ScParseTaskpadURL(mmcerror::SC *a1, const wchar_t *a2, GUID *a3)
{
  __int64 v6; // rax
  const struct mmcerror::SC *v7; // rdx
  unsigned int v8; // eax
  _BYTE v10[24]; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v11[40]; // [rsp+40h] [rbp-28h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v10, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v10, L"CMMCProtocol::ScParseTaskpadURL");
  *a3 = GUID_NULL;
  v6 = ScCheckPointers(v11, a2, 2147942487LL);
  mmcerror::SC::operator=(v10, v6);
  mmcerror::SC::~SC((mmcerror::SC *)v11);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v10) )
    goto LABEL_5;
  if ( !_wcsnicmp(a2, L"--mmc:", 6u) )
  {
    v8 = CLSIDFromString(a2 + 6, a3);
    mmcerror::SC::operator=(v10, v8);
    mmcerror::SC::operator bool(v10);
LABEL_5:
    v7 = (const struct mmcerror::SC *)v10;
    goto LABEL_6;
  }
  v7 = (const struct mmcerror::SC *)mmcerror::SC::operator=(v10, 2147500037LL);
LABEL_6:
  mmcerror::SC::SC(a1, v7);
  mmcerror::SC::~SC((mmcerror::SC *)v10);
  return a1;
}

```

## disassembly

```asm
0x18009f60c  push    rbp
0x18009f60e  push    rbx
0x18009f60f  push    rsi
0x18009f610  push    rdi
0x18009f611  mov     rbp, rsp
0x18009f614  sub     rsp, 68h
0x18009f618  mov     rsi, r8
0x18009f61b  mov     rdi, rdx
0x18009f61e  mov     rbx, rcx
0x18009f621  xor     edx, edx
0x18009f623  lea     rcx, [rbp+var_40]
0x18009f627  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18009f62d  nop
0x18009f62e  lea     rdx, aCmmcprotocolSc_1; "CMMCProtocol::ScParseTaskpadURL"
0x18009f635  lea     rcx, [rbp+var_40]
0x18009f639  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x18009f63f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18009f646  movdqu  xmmword ptr [rsi], xmm0
0x18009f64a  mov     r8d, 80070057h
0x18009f650  mov     rdx, rdi
0x18009f653  lea     rcx, [rbp+var_28]
0x18009f657  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x18009f65c  nop
0x18009f65d  mov     rdx, rax
0x18009f660  lea     rcx, [rbp+var_40]
0x18009f664  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18009f66a  nop
0x18009f66b  lea     rcx, [rbp+var_28]
0x18009f66f  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18009f675  lea     rcx, [rbp+var_40]
0x18009f679  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18009f67f  test    al, al
0x18009f681  jnz     short loc_18009F6D4
0x18009f683  mov     r8d, 6; MaxCount
0x18009f689  lea     rdx, aMmc_2; "--mmc:"
0x18009f690  mov     rcx, rdi; String1
0x18009f693  call    cs:__imp__wcsnicmp
0x18009f699  test    eax, eax
0x18009f69b  jz      short loc_18009F6B1
0x18009f69d  mov     edx, 80004005h
0x18009f6a2  lea     rcx, [rbp+var_40]
0x18009f6a6  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18009f6ac  mov     rdx, rax
0x18009f6af  jmp     short loc_18009F6D8
0x18009f6b1  lea     rcx, [rdi+0Ch]; lpsz
0x18009f6b5  mov     rdx, rsi; pclsid
0x18009f6b8  call    cs:__imp_CLSIDFromString
0x18009f6be  mov     edx, eax
0x18009f6c0  lea     rcx, [rbp+var_40]
0x18009f6c4  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18009f6ca  lea     rcx, [rbp+var_40]
0x18009f6ce  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18009f6d4  lea     rdx, [rbp+var_40]
0x18009f6d8  mov     rcx, rbx
0x18009f6db  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x18009f6e1  nop
0x18009f6e2  lea     rcx, [rbp+var_40]
0x18009f6e6  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18009f6ec  mov     rax, rbx
0x18009f6ef  add     rsp, 68h
0x18009f6f3  pop     rdi
0x18009f6f4  pop     rsi
0x18009f6f5  pop     rbx
0x18009f6f6  pop     rbp
0x18009f6f7  retn
```
