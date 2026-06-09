# ATL::CRegObject::~CRegObject(void)

- ea: `0x180015220`
- end: `0x180015297`
- name: `??1CRegObject@ATL@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180015ca0`
- `0x18001c08d`

## callees

- `0x1800151f4`
- `0x180015220`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x180015260`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x180015260`
- `msvcrt!free` at `0x180015290`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015233`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015233`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015277`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015277`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001524e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015257`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001524e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015257`

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
    operator delete(v4);
  }
  *((_DWORD *)this + 2) = 0;
  LeaveCriticalSection(v1);
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((ATL::CComAutoDeleteCriticalSection *)v1);
  free(*(void **)this);
}

```

## disassembly

```asm
0x180015220  push    rbx
0x180015222  push    rbp
0x180015223  push    rsi
0x180015224  push    rdi
0x180015225  sub     rsp, 28h
0x180015229  lea     rsi, [rcx+10h]
0x18001522d  mov     rdi, rcx
0x180015230  mov     rcx, rsi; lpCriticalSection
0x180015233  call    cs:__imp_EnterCriticalSection
0x180015239  xor     ebp, ebp
0x18001523b  cmp     [rdi+8], ebp
0x18001523e  jle     short loc_18001526D
0x180015240  mov     rax, [rdi]
0x180015243  movsxd  rcx, ebp
0x180015246  mov     rbx, [rax+rcx*8]
0x18001524a  mov     rcx, [rbx+8]; pv
0x18001524e  call    cs:__imp_CoTaskMemFree
0x180015254  mov     rcx, [rbx]; pv
0x180015257  call    cs:__imp_CoTaskMemFree
0x18001525d  mov     rcx, rbx
0x180015260  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015266  inc     ebp
0x180015268  cmp     ebp, [rdi+8]
0x18001526b  jl      short loc_180015240
0x18001526d  mov     rcx, rsi; lpCriticalSection
0x180015270  mov     dword ptr [rdi+8], 0
0x180015277  call    cs:__imp_LeaveCriticalSection
0x18001527d  mov     rcx, rsi; this
0x180015280  call    ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
0x180015285  mov     rcx, [rdi]
0x180015288  add     rsp, 28h
0x18001528c  pop     rdi
0x18001528d  pop     rsi
0x18001528e  pop     rbp
0x18001528f  pop     rbx
0x180015290  jmp     cs:__imp_free
```
