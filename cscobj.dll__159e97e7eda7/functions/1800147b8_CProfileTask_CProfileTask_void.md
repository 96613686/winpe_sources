# CProfileTask::~CProfileTask(void)

- ea: `0x1800147b8`
- end: `0x1800148c4`
- name: `??1CProfileTask@@UEAA@XZ`
- size: `268`
- prototype: `void __fastcall(CProfileTask *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800148cc`
- `0x1800148f8`
- `0x180014930`

## callees

- `0x1800147b8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014826`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014886`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014826`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014886`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800147dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800147dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800147e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800147e7`

## pseudocode

```c
void __fastcall CProfileTask::~CProfileTask(CProfileTask *this)
{
  void *v2; // rcx
  unsigned int v3; // edi
  unsigned int v4; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &CProfileTask::`vftable';
  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 )
  {
    SetEvent(v2);
    CloseHandle(*((HANDLE *)this + 11));
  }
  v3 = *((_DWORD *)this + 16);
  *((_QWORD *)this + 6) = &CInterfaceInGITBase::`vftable';
  if ( v3 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, v3);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  *((_QWORD *)this + 1) = &CInterfaceInGITBase::`vftable';
  v4 = *((_DWORD *)this + 6);
  if ( v4 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, v4);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
}

```

## disassembly

```asm
0x1800147b8  mov     [rsp+arg_8], rbx
0x1800147bd  mov     [rsp+arg_10], rsi
0x1800147c2  push    rdi
0x1800147c3  sub     rsp, 30h
0x1800147c7  lea     rax, ??_7CProfileTask@@6B@; const CProfileTask::`vftable'
0x1800147ce  mov     rbx, rcx
0x1800147d1  mov     [rcx], rax
0x1800147d4  mov     rcx, [rcx+58h]; hEvent
0x1800147d8  test    rcx, rcx
0x1800147db  jz      short loc_1800147ED
0x1800147dd  call    cs:__imp_SetEvent
0x1800147e3  mov     rcx, [rbx+58h]; hObject
0x1800147e7  call    cs:__imp_CloseHandle
0x1800147ed  mov     edi, [rbx+40h]
0x1800147f0  lea     rsi, ??_7CInterfaceInGITBase@@6B@; const CInterfaceInGITBase::`vftable'
0x1800147f7  mov     [rbx+30h], rsi
0x1800147fb  test    edi, edi
0x1800147fd  jz      short loc_180014854
0x1800147ff  xor     edx, edx; pUnkOuter
0x180014801  mov     [rsp+38h+arg_0], 0
0x18001480a  lea     rax, [rsp+38h+arg_0]
0x18001480f  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180014816  mov     [rsp+38h+ppv], rax; ppv
0x18001481b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180014822  lea     r8d, [rdx+1]; dwClsContext
0x180014826  call    cs:__imp_CoCreateInstance
0x18001482c  test    eax, eax
0x18001482e  js      short loc_180014854
0x180014830  mov     rcx, [rsp+38h+arg_0]
0x180014835  mov     edx, edi
0x180014837  mov     rax, [rcx]
0x18001483a  mov     rax, [rax+20h]
0x18001483e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014843  mov     rcx, [rsp+38h+arg_0]
0x180014848  mov     rax, [rcx]
0x18001484b  mov     rax, [rax+10h]
0x18001484f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014854  mov     [rbx+8], rsi
0x180014858  mov     ebx, [rbx+18h]
0x18001485b  test    ebx, ebx
0x18001485d  jz      short loc_1800148B4
0x18001485f  xor     edx, edx; pUnkOuter
0x180014861  mov     [rsp+38h+arg_0], 0
0x18001486a  lea     rax, [rsp+38h+arg_0]
0x18001486f  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180014876  mov     [rsp+38h+ppv], rax; ppv
0x18001487b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180014882  lea     r8d, [rdx+1]; dwClsContext
0x180014886  call    cs:__imp_CoCreateInstance
0x18001488c  test    eax, eax
0x18001488e  js      short loc_1800148B4
0x180014890  mov     rcx, [rsp+38h+arg_0]
0x180014895  mov     edx, ebx
0x180014897  mov     rax, [rcx]
0x18001489a  mov     rax, [rax+20h]
0x18001489e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148a3  mov     rcx, [rsp+38h+arg_0]
0x1800148a8  mov     rax, [rcx]
0x1800148ab  mov     rax, [rax+10h]
0x1800148af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148b4  mov     rbx, [rsp+38h+arg_8]
0x1800148b9  mov     rsi, [rsp+38h+arg_10]
0x1800148be  add     rsp, 30h
0x1800148c2  pop     rdi
0x1800148c3  retn
```
