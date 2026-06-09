# CGroupPolicyObject::Close(void)

- ea: `0x140004950`
- end: `0x1400049d4`
- name: `?Close@CGroupPolicyObject@@UEAAJXZ`
- size: `132`
- prototype: `__int64 __fastcall(CGroupPolicyObject *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400048c0`

## callees

- `0x140004950`
- `0x140005040`
- `0x140030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140004996`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140004996`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000498c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400049ba`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000498c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400049ba`

## string_xrefs

- `0x1400049ac`: `%s: Unable to restore COM to MTA mode. CoInitializeEx(COINIT_MULTITHREADED) failed with error code: 0x%08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
__int64 __fastcall CGroupPolicyObject::Close(CGroupPolicyObject *this)
{
  unsigned int v2; // edi
  __int64 v3; // rcx
  HRESULT v4; // eax

  v2 = 0;
  v3 = *((_QWORD *)this + 1);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 1) = 0;
  }
  if ( *((_DWORD *)this + 4) == 1 )
  {
    CoUninitialize();
  }
  else
  {
    if ( *((_DWORD *)this + 4) == 2 )
    {
      CoUninitialize();
    }
    else if ( *((_DWORD *)this + 4) != 3 )
    {
      goto LABEL_11;
    }
    v4 = CoInitializeEx(0, 0);
    v2 = v4;
    if ( v4 < 0 )
      Logger::TraceWarning(
        L"%s: Unable to restore COM to MTA mode. CoInitializeEx(COINIT_MULTITHREADED) failed with error code: 0x%08x.",
        L"CGroupPolicyObject::Close",
        (unsigned int)v4);
  }
LABEL_11:
  *((_DWORD *)this + 4) = 0;
  return v2;
}

```

## disassembly

```asm
0x140004950  mov     [rsp+arg_0], rbx
0x140004955  push    rdi
0x140004956  sub     rsp, 20h
0x14000495a  mov     rbx, rcx
0x14000495d  xor     edi, edi
0x14000495f  mov     rcx, [rcx+8]
0x140004963  test    rcx, rcx
0x140004966  jz      short loc_140004978
0x140004968  mov     rax, [rcx]
0x14000496b  mov     rax, [rax+10h]
0x14000496f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004974  mov     [rbx+8], rdi
0x140004978  mov     ecx, [rbx+10h]
0x14000497b  sub     ecx, 1
0x14000497e  jz      short loc_1400049BA
0x140004980  sub     ecx, 1
0x140004983  jz      short loc_14000498C
0x140004985  cmp     ecx, 1
0x140004988  jz      short loc_140004992
0x14000498a  jmp     short loc_1400049C0
0x14000498c  call    cs:__imp_CoUninitialize
0x140004992  xor     edx, edx; dwCoInit
0x140004994  xor     ecx, ecx; pvReserved
0x140004996  call    cs:__imp_CoInitializeEx
0x14000499c  mov     edi, eax
0x14000499e  test    eax, eax
0x1400049a0  jns     short loc_1400049C0
0x1400049a2  mov     r8d, eax
0x1400049a5  lea     rdx, aCgrouppolicyob_2; "CGroupPolicyObject::Close"
0x1400049ac  lea     rcx, aSUnableToResto; "%s: Unable to restore COM to MTA mode. "...
0x1400049b3  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1400049b8  jmp     short loc_1400049C0
0x1400049ba  call    cs:__imp_CoUninitialize
0x1400049c0  mov     dword ptr [rbx+10h], 0
0x1400049c7  mov     eax, edi
0x1400049c9  mov     rbx, [rsp+28h+arg_0]
0x1400049ce  add     rsp, 20h
0x1400049d2  pop     rdi
0x1400049d3  retn
```
