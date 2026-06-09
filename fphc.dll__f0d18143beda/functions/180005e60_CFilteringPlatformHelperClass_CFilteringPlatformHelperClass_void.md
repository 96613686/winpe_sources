# CFilteringPlatformHelperClass::~CFilteringPlatformHelperClass(void)

- ea: `0x180005e60`
- end: `0x180005eee`
- name: `??1CFilteringPlatformHelperClass@@QEAA@XZ`
- size: `142`
- prototype: `void __fastcall(CFilteringPlatformHelperClass *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005fa0`

## callees

- `0x180005e60`
- `0x180006628`
- `0x180012010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180005e8c`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005eb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005eb9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005edc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005edc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CFilteringPlatformHelperClass::~CFilteringPlatformHelperClass(CFilteringPlatformHelperClass *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  v2 = *((_QWORD *)this + 55);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  SysFreeString(*((BSTR *)this + 69));
  v3 = *((_QWORD *)this + 68);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  _attributes_array_t::FreeElements((CFilteringPlatformHelperClass *)((char *)this + 24));
  CoTaskMemFree(*((LPVOID *)this + 4));
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 6) = 0;
  if ( *((_BYTE *)this + 112) )
  {
    *((_BYTE *)this + 112) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  }
}

```

## disassembly

```asm
0x180005e60  mov     [rsp+arg_0], rbx
0x180005e65  push    rdi
0x180005e66  sub     rsp, 20h
0x180005e6a  mov     rdi, rcx
0x180005e6d  mov     rcx, [rcx+1B8h]
0x180005e74  test    rcx, rcx
0x180005e77  jz      short loc_180005E85
0x180005e79  mov     rax, [rcx]
0x180005e7c  mov     rax, [rax+10h]
0x180005e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e85  mov     rcx, [rdi+228h]; bstrString
0x180005e8c  call    cs:__imp_SysFreeString
0x180005e92  nop
0x180005e93  mov     rcx, [rdi+220h]
0x180005e9a  test    rcx, rcx
0x180005e9d  jz      short loc_180005EAC
0x180005e9f  mov     rax, [rcx]
0x180005ea2  mov     rax, [rax+10h]
0x180005ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eab  nop
0x180005eac  lea     rcx, [rdi+18h]; this
0x180005eb0  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x180005eb5  mov     rcx, [rdi+20h]; pv
0x180005eb9  call    cs:__imp_CoTaskMemFree
0x180005ebf  mov     qword ptr [rdi+20h], 0
0x180005ec7  mov     dword ptr [rdi+18h], 0
0x180005ece  lea     rcx, [rdi+48h]; lpCriticalSection
0x180005ed2  cmp     byte ptr [rcx+28h], 0
0x180005ed6  jz      short loc_180005EE3
0x180005ed8  mov     byte ptr [rcx+28h], 0
0x180005edc  call    cs:__imp_DeleteCriticalSection
0x180005ee2  nop
0x180005ee3  mov     rbx, [rsp+28h+arg_0]
0x180005ee8  add     rsp, 20h
0x180005eec  pop     rdi
0x180005eed  retn
```
