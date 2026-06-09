# ATL::CRegObject::~CRegObject(void)

- ea: `0x180010640`
- end: `0x1800106bc`
- name: `??1CRegObject@ATL@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `100`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180013660`
- `0x180019990`
- `0x18001b590`
- `0x18001cc50`
- `0x18001e8c0`
- `0x18001e940`
- `0x1800200f0`
- `0x180021650`
- `0x180023140`
- `0x180024890`
- `0x180025ec0`
- `0x180027390`
- `0x1800287a0`
- `0x180029a50`
- `0x180030910`
- `0x180030990`
- `0x180030a10`
- `0x180030a90`
- `0x180030b10`
- `0x180030b90`
- `0x180036460`
- `0x1800364e0`
- `0x180036560`
- `0x180042c4c`
- `0x180045d80`
- `0x180045e00`
- `0x180045e80`
- `0x180045f00`
- `0x180045f80`
- `0x180046000`
- `0x180046080`
- `0x180046100`
- `0x180046180`
- `0x18004aa80`
- `0x18004d740`
- `0x18004e5d0`
- `0x18004ee40`
- `0x18004fc60`
- `0x1800523a0`
- `0x1800565c0`
- `0x1800760c0`
- `0x180076120`
- `0x180076180`
- `0x1800761e0`
- `0x180076240`
- `0x1800762a0`
- `0x180076300`
- `0x180076360`
- `0x1800763c0`
- `0x180076420`

## callees

- `0x180004740`
- `0x180010640`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800106b5`
- `ole32!CoTaskMemFree` at `0x18001066e`
- `ole32!CoTaskMemFree` at `0x180010677`
- `ole32!CoTaskMemFree` at `0x18001066e`
- `ole32!CoTaskMemFree` at `0x180010677`
- `KERNEL32!LeaveCriticalSection` at `0x18001069b`
- `KERNEL32!LeaveCriticalSection` at `0x18001069b`
- `KERNEL32!EnterCriticalSection` at `0x180010653`
- `KERNEL32!EnterCriticalSection` at `0x180010653`
- `KERNEL32!DeleteCriticalSection` at `0x1800106a4`
- `KERNEL32!DeleteCriticalSection` at `0x1800106a4`

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
    operator delete(v4, 0x10u);
  }
  *((_DWORD *)this + 2) = 0;
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
  free(*(void **)this);
}

```

## disassembly

```asm
0x180010640  push    rbx
0x180010642  push    rbp
0x180010643  push    rsi
0x180010644  push    rdi
0x180010645  sub     rsp, 28h
0x180010649  lea     rsi, [rcx+10h]
0x18001064d  mov     rdi, rcx
0x180010650  mov     rcx, rsi; lpCriticalSection
0x180010653  call    cs:__imp_EnterCriticalSection
0x180010659  xor     ebp, ebp
0x18001065b  cmp     [rdi+8], ebp
0x18001065e  jle     short loc_180010691
0x180010660  mov     rax, [rdi]
0x180010663  movsxd  rcx, ebp
0x180010666  mov     rbx, [rax+rcx*8]
0x18001066a  mov     rcx, [rbx+8]; pv
0x18001066e  call    cs:__imp_CoTaskMemFree
0x180010674  mov     rcx, [rbx]; pv
0x180010677  call    cs:__imp_CoTaskMemFree
0x18001067d  mov     edx, 10h; unsigned __int64
0x180010682  mov     rcx, rbx; void *
0x180010685  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001068a  inc     ebp
0x18001068c  cmp     ebp, [rdi+8]
0x18001068f  jl      short loc_180010660
0x180010691  mov     rcx, rsi; lpCriticalSection
0x180010694  mov     dword ptr [rdi+8], 0
0x18001069b  call    cs:__imp_LeaveCriticalSection
0x1800106a1  mov     rcx, rsi; lpCriticalSection
0x1800106a4  call    cs:__imp_DeleteCriticalSection
0x1800106aa  mov     rcx, [rdi]
0x1800106ad  add     rsp, 28h
0x1800106b1  pop     rdi
0x1800106b2  pop     rsi
0x1800106b3  pop     rbp
0x1800106b4  pop     rbx
0x1800106b5  jmp     cs:__imp_free
```
