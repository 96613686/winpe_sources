# GetTriggerInfo

- ea: `0x14000d00c`
- end: `0x14000d0fe`
- name: `GetTriggerInfo`
- size: `242`
- prototype: `CRuntimeTriggerInfo **__fastcall(CRuntimeTriggerInfo **, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000d110`

## callees

- `0x140001cc6`
- `0x1400030ac`
- `0x140008034`
- `0x14000ce94`
- `0x14000d00c`
- `0x14000ed18`
- `0x1400109e0`
- `0x1400120e8`

## import_xrefs

- `ADVAPI32!RegConnectRegistryW` at `0x14000d045`
- `ADVAPI32!RegConnectRegistryW` at `0x14000d045`

## pseudocode

```c
CRuntimeTriggerInfo **__fastcall GetTriggerInfo(CRuntimeTriggerInfo **a1, const wchar_t *a2, const wchar_t *a3)
{
  LSTATUS v6; // eax
  CRuntimeTriggerInfo *v7; // rax
  CRuntimeTriggerInfo *v8; // rbx
  _bstr_t *v9; // rax
  CRuntimeTriggerInfo *v11; // [rsp+28h] [rbp-28h] BYREF
  void **pExceptionObject; // [rsp+30h] [rbp-20h] BYREF
  int v13; // [rsp+38h] [rbp-18h]
  __int128 v14; // [rsp+40h] [rbp-10h]
  HKEY phkResult; // [rsp+88h] [rbp+38h] BYREF

  phkResult = 0;
  v6 = RegConnectRegistryW(0, HKEY_LOCAL_MACHINE, &phkResult);
  if ( v6 )
  {
    bad_win32_error::bad_win32_error((bad_win32_error *)&pExceptionObject, v6);
    throw (bad_win32_error *)&pExceptionObject;
  }
  v7 = (CRuntimeTriggerInfo *)MmAllocate(0x858u);
  v11 = v7;
  if ( v7 )
    v8 = CRuntimeTriggerInfo::CRuntimeTriggerInfo(v7, a3);
  else
    v8 = 0;
  *a1 = v8;
  v9 = _bstr_t::_bstr_t((_bstr_t *)&v11, a2);
  if ( (int)CRuntimeTriggerInfo::Retrieve(v8, phkResult, v9) < 0 )
  {
    pExceptionObject = &_com_error::`vftable';
    v13 = -2147467259;
    v14 = 0;
    throw (_com_error *)&pExceptionObject;
  }
  CRegHandle::~CRegHandle(&phkResult);
  return a1;
}

```

## disassembly

```asm
0x14000d00c  mov     [rsp-18h+arg_8], rbx
0x14000d011  mov     [rsp-18h+arg_0], rcx
0x14000d016  push    rbp
0x14000d017  push    rsi
0x14000d018  push    rdi
0x14000d019  mov     rbp, rsp
0x14000d01c  sub     rsp, 50h
0x14000d020  mov     rbx, r8
0x14000d023  mov     rsi, rdx
0x14000d026  mov     rdi, rcx
0x14000d029  mov     [rbp+var_30], 0
0x14000d030  mov     [rbp+phkResult], 0
0x14000d038  lea     r8, [rbp+phkResult]; phkResult
0x14000d03c  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14000d043  xor     ecx, ecx; lpMachineName
0x14000d045  call    cs:__imp_RegConnectRegistryW
0x14000d04b  test    eax, eax
0x14000d04d  jz      short loc_14000D06B
0x14000d04f  mov     edx, eax; unsigned int
0x14000d051  lea     rcx, [rbp+pExceptionObject]; this
0x14000d055  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x14000d05a  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x14000d061  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000d065  call    _CxxThrowException_0
0x14000d06b  mov     ecx, 858h; unsigned __int64
0x14000d070  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x14000d075  mov     [rbp+var_28], rax
0x14000d079  test    rax, rax
0x14000d07c  jz      short loc_14000D08E
0x14000d07e  mov     rdx, rbx; wchar_t *
0x14000d081  mov     rcx, rax; this
0x14000d084  call    ??0CRuntimeTriggerInfo@@QEAA@PEB_W@Z; CRuntimeTriggerInfo::CRuntimeTriggerInfo(wchar_t const *)
0x14000d089  mov     rbx, rax
0x14000d08c  jmp     short loc_14000D090
0x14000d08e  xor     ebx, ebx
0x14000d090  mov     [rdi], rbx
0x14000d093  mov     [rbp+var_30], 1
0x14000d09a  mov     rdx, rsi; wchar_t *
0x14000d09d  lea     rcx, [rbp+var_28]; this
0x14000d0a1  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000d0a6  mov     r8, rax
0x14000d0a9  mov     rdx, [rbp+phkResult]
0x14000d0ad  mov     rcx, rbx
0x14000d0b0  call    ?Retrieve@CRuntimeTriggerInfo@@QEAAJPEAUHKEY__@@V_bstr_t@@@Z; CRuntimeTriggerInfo::Retrieve(HKEY__ *,_bstr_t)
0x14000d0b5  test    eax, eax
0x14000d0b7  jns     short loc_14000D0E4
0x14000d0b9  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x14000d0c0  mov     [rbp+pExceptionObject], rax
0x14000d0c4  mov     [rbp+var_18], 80004005h
0x14000d0cb  xorps   xmm0, xmm0
0x14000d0ce  movdqu  [rbp+var_10], xmm0
0x14000d0d3  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x14000d0da  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000d0de  call    _CxxThrowException_0
0x14000d0e4  lea     rcx, [rbp+phkResult]; this
0x14000d0e8  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x14000d0ed  mov     rax, rdi
0x14000d0f0  mov     rbx, [rsp+50h+arg_8]
0x14000d0f5  add     rsp, 50h
0x14000d0f9  pop     rdi
0x14000d0fa  pop     rsi
0x14000d0fb  pop     rbp
0x14000d0fc  retn
```
