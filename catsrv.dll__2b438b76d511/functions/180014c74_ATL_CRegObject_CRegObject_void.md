# ATL::CRegObject::~CRegObject(void)

- ea: `0x180014c74`
- end: `0x180014ceb`
- name: `??1CRegObject@ATL@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017624`

## callees

- `0x180008d00`
- `0x180014c74`

## import_xrefs

- `msvcrt!free` at `0x180014ce4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ccb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ccb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014c87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014c87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014ca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014cab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014cb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014ca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014cab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014cb4`

## pseudocode

```c
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  int i; // ebp
  LPVOID *v4; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  for ( i = 0; i < *((_DWORD *)this + 2); ++i )
  {
    v4 = *(LPVOID **)(*(_QWORD *)this + 8LL * i);
    CoTaskMemFree(v4[1]);
    CoTaskMemFree(*v4);
    CoTaskMemFree(v4);
  }
  *((_DWORD *)this + 2) = 0;
  LeaveCriticalSection(v1);
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((ATL::CComAutoDeleteCriticalSection *)v1);
  free(*(void **)this);
}

```

## disassembly

```asm
0x180014c74  push    rbx
0x180014c76  push    rbp
0x180014c77  push    rsi
0x180014c78  push    rdi
0x180014c79  sub     rsp, 28h
0x180014c7d  lea     rsi, [rcx+10h]
0x180014c81  mov     rdi, rcx
0x180014c84  mov     rcx, rsi; lpCriticalSection
0x180014c87  call    cs:__imp_EnterCriticalSection
0x180014c8d  xor     ebp, ebp
0x180014c8f  cmp     [rdi+8], ebp
0x180014c92  jle     short loc_180014CC1
0x180014c94  mov     rax, [rdi]
0x180014c97  movsxd  rcx, ebp
0x180014c9a  mov     rbx, [rax+rcx*8]
0x180014c9e  mov     rcx, [rbx+8]; pv
0x180014ca2  call    cs:__imp_CoTaskMemFree
0x180014ca8  mov     rcx, [rbx]; pv
0x180014cab  call    cs:__imp_CoTaskMemFree
0x180014cb1  mov     rcx, rbx; pv
0x180014cb4  call    cs:__imp_CoTaskMemFree
0x180014cba  inc     ebp
0x180014cbc  cmp     ebp, [rdi+8]
0x180014cbf  jl      short loc_180014C94
0x180014cc1  mov     rcx, rsi; lpCriticalSection
0x180014cc4  mov     dword ptr [rdi+8], 0
0x180014ccb  call    cs:__imp_LeaveCriticalSection
0x180014cd1  mov     rcx, rsi; this
0x180014cd4  call    ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
0x180014cd9  mov     rcx, [rdi]
0x180014cdc  add     rsp, 28h
0x180014ce0  pop     rdi
0x180014ce1  pop     rsi
0x180014ce2  pop     rbp
0x180014ce3  pop     rbx
0x180014ce4  jmp     cs:__imp_free
```
