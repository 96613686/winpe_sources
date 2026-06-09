# CGenerateMSI::~CGenerateMSI(void)

- ea: `0x180050d90`
- end: `0x180050e37`
- name: `??1CGenerateMSI@@QEAA@XZ`
- size: `167`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180050d28`

## callees

- `0x180008d00`
- `0x180050d90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050da7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050dd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050de8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050e00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050e18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050da7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050dd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050de8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050e00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050e18`
- `msi!__imp_MsiCloseHandle` at `0x180050dbc`
- `msi!__imp_MsiCloseHandle` at `0x180050dbc`

## pseudocode

```c
void __fastcall CGenerateMSI::~CGenerateMSI(LPVOID *this)
{
  MSIHANDLE v2; // ecx

  *this = &CGenerateMSI::`vftable';
  CoTaskMemFree(this[9]);
  this[9] = 0;
  v2 = *((_DWORD *)this + 16);
  if ( v2 )
  {
    MsiCloseHandle(v2);
    *((_DWORD *)this + 16) = 0;
  }
  CoTaskMemFree(this[76]);
  this[76] = 0;
  CoTaskMemFree(this[78]);
  this[78] = 0;
  CoTaskMemFree(this[79]);
  this[79] = 0;
  CoTaskMemFree(this[80]);
  this[80] = 0;
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((ATL::CComAutoDeleteCriticalSection *)(this + 2));
}

```

## disassembly

```asm
0x180050d90  push    rbx
0x180050d92  sub     rsp, 20h
0x180050d96  mov     rbx, rcx
0x180050d99  lea     rax, ??_7CGenerateMSI@@6B@; const CGenerateMSI::`vftable'
0x180050da0  mov     [rcx], rax
0x180050da3  mov     rcx, [rcx+48h]; pv
0x180050da7  call    cs:__imp_CoTaskMemFree
0x180050dad  mov     qword ptr [rbx+48h], 0
0x180050db5  mov     ecx, [rbx+40h]; hAny
0x180050db8  test    ecx, ecx
0x180050dba  jz      short loc_180050DC9
0x180050dbc  call    cs:__imp_MsiCloseHandle
0x180050dc2  mov     dword ptr [rbx+40h], 0
0x180050dc9  mov     rcx, [rbx+260h]; pv
0x180050dd0  call    cs:__imp_CoTaskMemFree
0x180050dd6  mov     qword ptr [rbx+260h], 0
0x180050de1  mov     rcx, [rbx+270h]; pv
0x180050de8  call    cs:__imp_CoTaskMemFree
0x180050dee  mov     qword ptr [rbx+270h], 0
0x180050df9  mov     rcx, [rbx+278h]; pv
0x180050e00  call    cs:__imp_CoTaskMemFree
0x180050e06  mov     qword ptr [rbx+278h], 0
0x180050e11  mov     rcx, [rbx+280h]; pv
0x180050e18  call    cs:__imp_CoTaskMemFree
0x180050e1e  mov     qword ptr [rbx+280h], 0
0x180050e29  lea     rcx, [rbx+10h]; this
0x180050e2d  add     rsp, 20h
0x180050e31  pop     rbx
0x180050e32  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
