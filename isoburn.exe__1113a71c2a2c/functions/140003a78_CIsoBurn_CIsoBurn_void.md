# CIsoBurn::~CIsoBurn(void)

- ea: `0x140003a78`
- end: `0x140003adc`
- name: `??1CIsoBurn@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(CIsoBurn *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003d90`

## callees

- `0x140003a78`
- `0x140010010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140003aa4`
- `KERNEL32!CloseHandle` at `0x140003aa4`
- `KERNEL32!DeleteCriticalSection` at `0x140003ad0`
- `KERNEL32!DeleteCriticalSection` at `0x140003ad0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140003a85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140003a92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140003a85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140003a92`

## pseudocode

```c
void __fastcall CIsoBurn::~CIsoBurn(CIsoBurn *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  CoTaskMemFree(*((LPVOID *)this + 15));
  CoTaskMemFree(*((LPVOID *)this + 16));
  v2 = (void *)*((_QWORD *)this + 18);
  if ( v2 )
    CloseHandle(v2);
  v3 = *((_QWORD *)this + 19);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( *((_BYTE *)this + 112) )
  {
    *((_BYTE *)this + 112) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  }
}

```

## disassembly

```asm
0x140003a78  push    rbx
0x140003a7a  sub     rsp, 20h
0x140003a7e  mov     rbx, rcx
0x140003a81  mov     rcx, [rcx+78h]; pv
0x140003a85  call    cs:__imp_CoTaskMemFree
0x140003a8b  mov     rcx, [rbx+80h]; pv
0x140003a92  call    cs:__imp_CoTaskMemFree
0x140003a98  mov     rcx, [rbx+90h]; hObject
0x140003a9f  test    rcx, rcx
0x140003aa2  jz      short loc_140003AAA
0x140003aa4  call    cs:__imp_CloseHandle
0x140003aaa  mov     rcx, [rbx+98h]
0x140003ab1  test    rcx, rcx
0x140003ab4  jz      short loc_140003AC2
0x140003ab6  mov     rax, [rcx]
0x140003ab9  mov     rax, [rax+10h]
0x140003abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ac2  lea     rcx, [rbx+48h]; lpCriticalSection
0x140003ac6  cmp     byte ptr [rcx+28h], 0
0x140003aca  jz      short loc_140003AD6
0x140003acc  mov     byte ptr [rcx+28h], 0
0x140003ad0  call    cs:__imp_DeleteCriticalSection
0x140003ad6  add     rsp, 20h
0x140003ada  pop     rbx
0x140003adb  retn
```
