# ATL::CRegObject::~CRegObject(void)

- ea: `0x180010ff0`
- end: `0x18001106d`
- name: `??1CRegObject@ATL@@QEAA@XZ`
- size: `125`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015204`
- `0x180056118`

## callees

- `0x180010f88`
- `0x180010ff0`

## import_xrefs

- `msvcrt!free` at `0x18001105d`
- `msvcrt!free` at `0x18001105d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001104a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001104a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011003`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011003`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001101f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011028`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011032`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001101f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011028`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011032`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  int i; // ebp
  LPVOID *v4; // rbx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  for ( i = 0; i < *((_DWORD *)this + 2); ++i )
  {
    v4 = *(LPVOID **)(*(_QWORD *)this + 8LL * i);
    CoTaskMemFree(v4[1]);
    CoTaskMemFree(*v4);
    CoTaskMemFree(v4);
  }
  *((_DWORD *)this + 2) = 0;
  LeaveCriticalSection(v2);
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((ATL::CComAutoDeleteCriticalSection *)v2);
  free(*(void **)this);
}

```

## disassembly

```asm
0x180010ff0  push    rbx
0x180010ff2  push    rbp
0x180010ff3  push    rsi
0x180010ff4  push    rdi
0x180010ff5  sub     rsp, 28h
0x180010ff9  mov     rdi, rcx
0x180010ffc  lea     rsi, [rcx+10h]
0x180011000  mov     rcx, rsi; lpCriticalSection
0x180011003  call    cs:__imp_EnterCriticalSection
0x180011009  nop
0x18001100a  xor     ebp, ebp
0x18001100c  cmp     [rdi+8], ebp
0x18001100f  jle     short loc_180011040
0x180011011  movsxd  rcx, ebp
0x180011014  mov     rax, [rdi]
0x180011017  mov     rbx, [rax+rcx*8]
0x18001101b  mov     rcx, [rbx+8]; pv
0x18001101f  call    cs:__imp_CoTaskMemFree
0x180011025  mov     rcx, [rbx]; pv
0x180011028  call    cs:__imp_CoTaskMemFree
0x18001102e  nop
0x18001102f  mov     rcx, rbx; pv
0x180011032  call    cs:__imp_CoTaskMemFree
0x180011038  nop
0x180011039  inc     ebp
0x18001103b  cmp     ebp, [rdi+8]
0x18001103e  jl      short loc_180011011
0x180011040  mov     dword ptr [rdi+8], 0
0x180011047  mov     rcx, rsi; lpCriticalSection
0x18001104a  call    cs:__imp_LeaveCriticalSection
0x180011050  nop
0x180011051  mov     rcx, rsi; this
0x180011054  call    ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
0x180011059  nop
0x18001105a  mov     rcx, [rdi]; Block
0x18001105d  call    cs:__imp_free
0x180011063  nop
0x180011064  add     rsp, 28h
0x180011068  pop     rdi
0x180011069  pop     rsi
0x18001106a  pop     rbp
0x18001106b  pop     rbx
0x18001106c  retn
```
