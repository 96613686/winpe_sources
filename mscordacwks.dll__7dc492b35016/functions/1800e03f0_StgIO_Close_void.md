# StgIO::Close(void)

- ea: `0x1800e03f0`
- end: `0x1800e05e4`
- name: `?Close@StgIO@@QEAAXXZ`
- size: `500`
- prototype: `void __fastcall(StgIO *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x1800dfd8c`
- `0x1800dfdc0`
- `0x1800e05e4`

## callees

- `0x180072664`
- `0x180072810`
- `0x1800e03f0`
- `0x180106100`

## import_xrefs

- `KERNEL32!UnmapViewOfFile` at `0x1800e0519`
- `KERNEL32!UnmapViewOfFile` at `0x1800e0519`
- `KERNEL32!FreeLibrary` at `0x1800e04fb`
- `KERNEL32!FreeLibrary` at `0x1800e04fb`
- `KERNEL32!CloseHandle` at `0x1800e0480`
- `KERNEL32!CloseHandle` at `0x1800e0523`
- `KERNEL32!CloseHandle` at `0x1800e0480`
- `KERNEL32!CloseHandle` at `0x1800e0523`
- `KERNEL32!HeapFree` at `0x1800e0468`
- `KERNEL32!HeapFree` at `0x1800e04b6`
- `KERNEL32!HeapFree` at `0x1800e0468`
- `KERNEL32!HeapFree` at `0x1800e04b6`
- `KERNEL32!GetProcessHeap` at `0x1800e0453`
- `KERNEL32!GetProcessHeap` at `0x1800e04a1`
- `KERNEL32!GetProcessHeap` at `0x1800e0453`
- `KERNEL32!GetProcessHeap` at `0x1800e04a1`
- `ole32!CoTaskMemFree` at `0x1800e04ce`
- `ole32!CoTaskMemFree` at `0x1800e04ce`

## pseudocode

```c
void __fastcall StgIO::Close(StgIO *this)
{
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  void *v7; // rsi
  HANDLE ProcessHeap; // rax
  void *v9; // rcx
  void *v10; // rsi
  HANDLE v11; // rax
  void *v12; // rcx
  __int64 v13; // rcx
  HMODULE v14; // rcx
  const void *v15; // rcx
  void *v16; // rcx
  int v17; // edx
  void *v18; // rcx
  int v19; // eax

  v2 = *((_DWORD *)this + 34) - 1;
  if ( !v2 )
  {
LABEL_12:
    v9 = (void *)*((_QWORD *)this + 11);
    if ( v9 != (void *)-1LL )
      CloseHandle(v9);
    goto LABEL_14;
  }
  v3 = v2 - 1;
  if ( !v3 )
  {
    v14 = (HMODULE)*((_QWORD *)this + 13);
    if ( v14 )
      FreeLibrary(v14);
    *((_QWORD *)this + 13) = 0;
    goto LABEL_14;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v13 = *((_QWORD *)this + 10);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    goto LABEL_14;
  }
  v5 = v4 - 1;
  if ( !v5 )
    goto LABEL_7;
  v6 = v5 - 1;
  if ( v6 )
  {
    if ( v6 != 1 )
      return;
    goto LABEL_7;
  }
  v12 = (void *)*((_QWORD *)this + 14);
  if ( !v12 )
  {
LABEL_7:
    if ( (*((_BYTE *)this + 72) & 8) != 0 )
    {
      v7 = (void *)*((_QWORD *)this + 14);
      if ( v7 )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v7);
        *((_QWORD *)this + 15) = 0;
        *((_QWORD *)this + 14) = 0;
      }
    }
    goto LABEL_12;
  }
  CoTaskMemFree(v12);
  *((_QWORD *)this + 14) = 0;
LABEL_14:
  if ( (*((_BYTE *)this + 72) & 8) != 0 && (v10 = (void *)*((_QWORD *)this + 14)) != 0 )
  {
    v11 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
    {
      v11 = GetProcessHeap();
      `ClrFreeInProcessHeap'::`2'::ProcessHeap = v11;
    }
    HeapFree(v11, 0, v10);
  }
  else if ( *((_QWORD *)this + 12) && (v15 = (const void *)*((_QWORD *)this + 14)) != 0 )
  {
    UnmapViewOfFile(v15);
    CloseHandle(*((HANDLE *)this + 12));
  }
  else
  {
    v16 = (void *)*((_QWORD *)this + 20);
    if ( v16 && *((_QWORD *)this + 14) )
    {
      operator delete(v16);
      v17 = StgIO::m_iPageSize;
      v18 = (void *)*((_QWORD *)this + 14);
      v19 = *((_DWORD *)this + 32) - 1;
      *((_QWORD *)this + 20) = 0;
      ClrVirtualFree(v18, (v19 & (unsigned int)~(v17 - 1)) + v17, 0x4000u);
      ClrVirtualFree(*((void **)this + 14), 0, 0x8000u);
    }
  }
  *((_BYTE *)this + 72) &= 0xF4u;
  *((_QWORD *)this + 11) = -1;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 20) = 0;
  *(_DWORD *)this = 0;
  *((_WORD *)this + 2) = 0;
  *((_DWORD *)this + 17) = 1;
}

```

## disassembly

```asm
0x1800e03f0  mov     [rsp+arg_0], rbx
0x1800e03f5  mov     [rsp+arg_8], rsi
0x1800e03fa  push    rdi
0x1800e03fb  sub     rsp, 20h
0x1800e03ff  mov     rbx, rcx
0x1800e0402  xor     edi, edi
0x1800e0404  mov     ecx, [rcx+88h]
0x1800e040a  sub     ecx, 1
0x1800e040d  jz      short loc_1800E0476
0x1800e040f  sub     ecx, 1
0x1800e0412  jz      loc_1800E04F2
0x1800e0418  sub     ecx, 1
0x1800e041b  jz      loc_1800E04DA
0x1800e0421  sub     ecx, 1
0x1800e0424  jz      short loc_1800E0438
0x1800e0426  sub     ecx, 1
0x1800e0429  jz      loc_1800E04C1
0x1800e042f  cmp     ecx, 1
0x1800e0432  jnz     loc_1800E05D4
0x1800e0438  test    byte ptr [rbx+48h], 8
0x1800e043c  jz      short loc_1800E0476
0x1800e043e  mov     rsi, [rbx+70h]
0x1800e0442  test    rsi, rsi
0x1800e0445  jz      short loc_1800E0476
0x1800e0447  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800e044e  test    rax, rax
0x1800e0451  jnz     short loc_1800E0460
0x1800e0453  call    cs:__imp_GetProcessHeap
0x1800e0459  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800e0460  mov     r8, rsi; lpMem
0x1800e0463  xor     edx, edx; dwFlags
0x1800e0465  mov     rcx, rax; hHeap
0x1800e0468  call    cs:__imp_HeapFree
0x1800e046e  mov     [rbx+78h], rdi
0x1800e0472  mov     [rbx+70h], rdi
0x1800e0476  mov     rcx, [rbx+58h]; hObject
0x1800e047a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800e047e  jz      short loc_1800E0486
0x1800e0480  call    cs:__imp_CloseHandle
0x1800e0486  test    byte ptr [rbx+48h], 8
0x1800e048a  jz      short loc_1800E050A
0x1800e048c  mov     rsi, [rbx+70h]
0x1800e0490  test    rsi, rsi
0x1800e0493  jz      short loc_1800E050A
0x1800e0495  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800e049c  test    rax, rax
0x1800e049f  jnz     short loc_1800E04AE
0x1800e04a1  call    cs:__imp_GetProcessHeap
0x1800e04a7  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800e04ae  mov     r8, rsi; lpMem
0x1800e04b1  xor     edx, edx; dwFlags
0x1800e04b3  mov     rcx, rax; hHeap
0x1800e04b6  call    cs:__imp_HeapFree
0x1800e04bc  jmp     loc_1800E0584
0x1800e04c1  mov     rcx, [rbx+70h]; pv
0x1800e04c5  test    rcx, rcx
0x1800e04c8  jz      loc_1800E0438
0x1800e04ce  call    cs:__imp_CoTaskMemFree
0x1800e04d4  mov     [rbx+70h], rdi
0x1800e04d8  jmp     short loc_1800E0486
0x1800e04da  mov     rcx, [rbx+50h]
0x1800e04de  test    rcx, rcx
0x1800e04e1  jz      short loc_1800E0486
0x1800e04e3  mov     rax, [rcx]
0x1800e04e6  mov     rax, [rax+10h]
0x1800e04ea  call    cs:__guard_dispatch_icall_fptr
0x1800e04f0  jmp     short loc_1800E0486
0x1800e04f2  mov     rcx, [rbx+68h]; hLibModule
0x1800e04f6  test    rcx, rcx
0x1800e04f9  jz      short loc_1800E0501
0x1800e04fb  call    cs:__imp_FreeLibrary
0x1800e0501  mov     [rbx+68h], rdi
0x1800e0505  jmp     loc_1800E0486
0x1800e050a  cmp     [rbx+60h], rdi
0x1800e050e  jz      short loc_1800E052B
0x1800e0510  mov     rcx, [rbx+70h]; lpBaseAddress
0x1800e0514  test    rcx, rcx
0x1800e0517  jz      short loc_1800E052B
0x1800e0519  call    cs:__imp_UnmapViewOfFile
0x1800e051f  mov     rcx, [rbx+60h]; hObject
0x1800e0523  call    cs:__imp_CloseHandle
0x1800e0529  jmp     short loc_1800E0584
0x1800e052b  mov     rcx, [rbx+0A0h]; lpMem
0x1800e0532  test    rcx, rcx
0x1800e0535  jz      short loc_1800E0584
0x1800e0537  cmp     [rbx+70h], rdi
0x1800e053b  jz      short loc_1800E0584
0x1800e053d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800e0542  mov     edx, cs:?m_iPageSize@StgIO@@0HA; int StgIO::m_iPageSize
0x1800e0548  mov     eax, [rbx+80h]
0x1800e054e  mov     rcx, [rbx+70h]; void *
0x1800e0552  dec     eax
0x1800e0554  mov     [rbx+0A0h], rdi
0x1800e055b  lea     r8d, [rdx-1]
0x1800e055f  not     r8d
0x1800e0562  and     r8d, eax
0x1800e0565  add     edx, r8d; unsigned __int64
0x1800e0568  mov     r8d, 4000h; unsigned int
0x1800e056e  call    ?ClrVirtualFree@@YAHPEAX_KK@Z; ClrVirtualFree(void *,unsigned __int64,ulong)
0x1800e0573  mov     rcx, [rbx+70h]; void *
0x1800e0577  xor     edx, edx; unsigned __int64
0x1800e0579  mov     r8d, 8000h; unsigned int
0x1800e057f  call    ?ClrVirtualFree@@YAHPEAX_KK@Z; ClrVirtualFree(void *,unsigned __int64,ulong)
0x1800e0584  and     byte ptr [rbx+48h], 0F4h
0x1800e0588  or      qword ptr [rbx+58h], 0FFFFFFFFFFFFFFFFh
0x1800e058d  and     qword ptr [rbx+80h], 0
0x1800e0595  and     qword ptr [rbx+88h], 0
0x1800e059d  and     qword ptr [rbx+98h], 0
0x1800e05a5  mov     [rbx+50h], rdi
0x1800e05a9  mov     [rbx+68h], rdi
0x1800e05ad  mov     [rbx+60h], rdi
0x1800e05b1  mov     [rbx+70h], rdi
0x1800e05b5  mov     [rbx+78h], rdi
0x1800e05b9  mov     [rbx+90h], rdi
0x1800e05c0  mov     [rbx+0A0h], rdi
0x1800e05c7  mov     [rbx], edi
0x1800e05c9  mov     [rbx+4], di
0x1800e05cd  mov     dword ptr [rbx+44h], 1
0x1800e05d4  mov     rbx, [rsp+28h+arg_0]
0x1800e05d9  mov     rsi, [rsp+28h+arg_8]
0x1800e05de  add     rsp, 20h
0x1800e05e2  pop     rdi
0x1800e05e3  retn
```
