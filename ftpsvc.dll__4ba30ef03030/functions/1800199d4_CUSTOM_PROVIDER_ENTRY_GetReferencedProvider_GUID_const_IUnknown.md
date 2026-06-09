# CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(_GUID const &,IUnknown * *)

- ea: `0x1800199d4`
- end: `0x180019b41`
- name: `?GetReferencedProvider@CUSTOM_PROVIDER_ENTRY@@QEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(CUSTOM_PROVIDER_ENTRY *__hidden this, const struct _GUID *, struct IUnknown **)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000fb34`
- `0x180015b60`
- `0x18001c450`
- `0x18001d704`
- `0x18001d8a0`
- `0x180033398`
- `0x180037910`
- `0x180037f14`

## callees

- `0x1800199d4`
- `0x180019bd4`
- `0x180049010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180019b13`
- `ole32!CoTaskMemFree` at `0x180019b13`
- `ole32!StringFromIID` at `0x180019aab`
- `ole32!StringFromIID` at `0x180019aab`
- `iisutil!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x180019a0b`
- `iisutil!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x180019a0b`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800199f6`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800199f6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180019b21`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180019b21`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180019b2c`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180019b2c`
- `iisutil!PuDbgPrintError` at `0x180019b00`
- `iisutil!PuDbgPrintError` at `0x180019b00`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(
        CUSTOM_PROVIDER_ENTRY *this,
        const struct _GUID *a2,
        struct IUnknown **a3)
{
  CReaderWriterLock3 *v3; // rbp
  int CustomProviderNoLock; // edi
  __int64 v8; // rcx
  int v9; // r14d
  const wchar_t *v10; // rcx
  LPOLESTR lpsz; // [rsp+80h] [rbp+8h] BYREF

  v3 = (CUSTOM_PROVIDER_ENTRY *)((char *)this + 552);
  CustomProviderNoLock = 0;
  CReaderWriterLock3::ReadLock((CUSTOM_PROVIDER_ENTRY *)((char *)this + 552));
  v8 = *((_QWORD *)this + 70);
  if ( v8 )
  {
    v9 = 0;
  }
  else
  {
    CReaderWriterLock3::ConvertSharedToExclusive(v3);
    v8 = *((_QWORD *)this + 70);
    v9 = 1;
    if ( !v8 )
    {
      CustomProviderNoLock = CUSTOM_PROVIDER_ENTRY::LoadCustomProviderNoLock(this, a2, 0);
      if ( CustomProviderNoLock < 0 )
        goto LABEL_17;
      v8 = *((_QWORD *)this + 70);
    }
  }
  if ( *((_QWORD *)this + 71) == *(_QWORD *)&a2->Data1 && *((_QWORD *)this + 72) == *(_QWORD *)a2->Data4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    *a3 = (struct IUnknown *)*((_QWORD *)this + 70);
  }
  else
  {
    CustomProviderNoLock = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, struct IUnknown **))v8)(
                             v8,
                             a2,
                             a3);
    if ( CustomProviderNoLock < 0 )
    {
      lpsz = 0;
      StringFromIID(a2, &lpsz);
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v10 = &WideCharStr;
        if ( lpsz )
          v10 = lpsz;
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\custom_provider_entry.cxx",
          129,
          "CUSTOM_PROVIDER_ENTRY::GetReferencedProvider",
          CustomProviderNoLock,
          "Failed to retrieve provider interface[%S].\n",
          v10);
      }
      if ( lpsz )
        CoTaskMemFree(lpsz);
    }
  }
  if ( !v9 )
  {
    CReaderWriterLock3::ReadUnlock(v3);
    return (unsigned int)CustomProviderNoLock;
  }
LABEL_17:
  CReaderWriterLock3::WriteUnlock(v3);
  return (unsigned int)CustomProviderNoLock;
}

```

## disassembly

```asm
0x1800199d4  push    rbx
0x1800199d6  push    rbp
0x1800199d7  push    rsi
0x1800199d8  push    rdi
0x1800199d9  push    r14
0x1800199db  push    r15
0x1800199dd  sub     rsp, 48h
0x1800199e1  lea     rbp, [rcx+228h]
0x1800199e8  mov     rbx, rcx
0x1800199eb  mov     rcx, rbp
0x1800199ee  mov     r15, r8
0x1800199f1  mov     rsi, rdx
0x1800199f4  xor     edi, edi
0x1800199f6  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800199fc  mov     rcx, [rbx+230h]
0x180019a03  test    rcx, rcx
0x180019a06  jnz     short loc_180019A42
0x180019a08  mov     rcx, rbp
0x180019a0b  call    cs:__imp_?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ConvertSharedToExclusive(void)
0x180019a11  mov     rcx, [rbx+230h]
0x180019a18  lea     r14d, [rdi+1]
0x180019a1c  test    rcx, rcx
0x180019a1f  jnz     short loc_180019A45
0x180019a21  xor     r8d, r8d; int
0x180019a24  mov     rdx, rsi; struct _GUID *
0x180019a27  mov     rcx, rbx; this
0x180019a2a  call    ?LoadCustomProviderNoLock@CUSTOM_PROVIDER_ENTRY@@AEAAJAEBU_GUID@@H@Z; CUSTOM_PROVIDER_ENTRY::LoadCustomProviderNoLock(_GUID const &,int)
0x180019a2f  mov     edi, eax
0x180019a31  test    eax, eax
0x180019a33  js      loc_180019B1E
0x180019a39  mov     rcx, [rbx+230h]
0x180019a40  jmp     short loc_180019A45
0x180019a42  xor     r14d, r14d
0x180019a45  mov     rax, [rbx+238h]
0x180019a4c  cmp     rax, [rsi]
0x180019a4f  jnz     short loc_180019A79
0x180019a51  mov     rax, [rbx+240h]
0x180019a58  cmp     rax, [rsi+8]
0x180019a5c  jnz     short loc_180019A79
0x180019a5e  mov     rax, [rcx]
0x180019a61  mov     rax, [rax+8]
0x180019a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a6a  mov     rax, [rbx+230h]
0x180019a71  mov     [r15], rax
0x180019a74  jmp     loc_180019B19
0x180019a79  mov     rax, [rcx]
0x180019a7c  mov     r8, r15
0x180019a7f  mov     rdx, rsi
0x180019a82  mov     rax, [rax]
0x180019a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a8a  mov     edi, eax
0x180019a8c  test    eax, eax
0x180019a8e  jns     loc_180019B19
0x180019a94  lea     rdx, [rsp+78h+lpsz]; lplpsz
0x180019a9c  mov     [rsp+78h+lpsz], 0
0x180019aa8  mov     rcx, rsi; rclsid
0x180019aab  call    cs:__imp_StringFromIID
0x180019ab1  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180019ab8  jz      short loc_180019B06
0x180019aba  mov     rax, [rsp+78h+lpsz]
0x180019ac2  lea     rcx, WideCharStr
0x180019ac9  test    rax, rax
0x180019acc  lea     r9, aCustomProvider_3; "CUSTOM_PROVIDER_ENTRY::GetReferencedPro"...
0x180019ad3  mov     r8d, 81h
0x180019ad9  lea     rdx, aInetsrvIisIisr_37; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180019ae0  cmovnz  rcx, rax
0x180019ae4  lea     rax, aFailedToRetrie_7; "Failed to retrieve provider interface[%"...
0x180019aeb  mov     [rsp+78h+var_48], rcx
0x180019af0  mov     rcx, cs:g_pDebug
0x180019af7  mov     [rsp+78h+var_50], rax
0x180019afc  mov     [rsp+78h+var_58], edi
0x180019b00  call    cs:__imp_PuDbgPrintError
0x180019b06  mov     rcx, [rsp+78h+lpsz]; pv
0x180019b0e  test    rcx, rcx
0x180019b11  jz      short loc_180019B19
0x180019b13  call    cs:__imp_CoTaskMemFree
0x180019b19  test    r14d, r14d
0x180019b1c  jz      short loc_180019B29
0x180019b1e  mov     rcx, rbp
0x180019b21  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180019b27  jmp     short loc_180019B32
0x180019b29  mov     rcx, rbp
0x180019b2c  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180019b32  mov     eax, edi
0x180019b34  add     rsp, 48h
0x180019b38  pop     r15
0x180019b3a  pop     r14
0x180019b3c  pop     rdi
0x180019b3d  pop     rsi
0x180019b3e  pop     rbp
0x180019b3f  pop     rbx
0x180019b40  retn
```
