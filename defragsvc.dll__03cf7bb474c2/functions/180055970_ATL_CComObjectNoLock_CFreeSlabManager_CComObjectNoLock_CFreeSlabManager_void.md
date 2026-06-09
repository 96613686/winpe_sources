# ATL::CComObjectNoLock<CFreeSlabManager>::~CComObjectNoLock<CFreeSlabManager>(void)

- ea: `0x180055970`
- end: `0x180055a02`
- name: `??1?$CComObjectNoLock@VCFreeSlabManager@@@ATL@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(CFreeSlabManager *this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180034574`
- `0x180056430`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180055970`
- `0x180055a3c`
- `0x18005fc38`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800559d8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800559d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800559b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800559b5`

## pseudocode

```c
void __fastcall ATL::CComObjectNoLock<CFreeSlabManager>::~CComObjectNoLock<CFreeSlabManager>(CFreeSlabManager *this)
{
  _QWORD *v2; // rcx
  void *v3; // rdi
  _BYTE v4[72]; // [rsp+20h] [rbp-48h] BYREF

  *((_DWORD *)this + 4) = -1073741823;
  *(_QWORD *)this = &CSxComObjectNoLock<CFreeSlabManager>::`vftable';
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v4, "CFreeSlabManager::FinalRelease", 137, 1);
  while ( 1 )
  {
    v2 = (_QWORD *)*((_QWORD *)this + 14);
    if ( !v2 )
      break;
    *((_QWORD *)this + 14) = v2[2];
    CoTaskMemFree(v2);
  }
  v3 = (void *)*((_QWORD *)this + 5);
  if ( v3 )
  {
    CFreeSlabManagerDelegate::~CFreeSlabManagerDelegate(*((CFreeSlabManagerDelegate **)this + 5));
    operator delete(v3);
  }
  *((_QWORD *)this + 5) = 0;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v4);
  CFreeSlabManager::~CFreeSlabManager(this);
}

```

## disassembly

```asm
0x180055970  mov     [rsp+arg_0], rbx
0x180055975  push    rdi
0x180055976  sub     rsp, 60h
0x18005597a  lea     rax, ??_7?$CSxComObjectNoLock@VCFreeSlabManager@@@@6B@; const CSxComObjectNoLock<CFreeSlabManager>::`vftable'
0x180055981  mov     dword ptr [rcx+10h], 0C0000001h
0x180055988  mov     [rcx], rax
0x18005598b  lea     rdx, aCfreeslabmanag_32; "CFreeSlabManager::FinalRelease"
0x180055992  mov     rbx, rcx
0x180055995  mov     r9d, 1; unsigned __int16
0x18005599b  lea     rcx, [rsp+68h+var_48]; this
0x1800559a0  mov     r8d, 89h; unsigned __int16
0x1800559a6  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800559ab  jmp     short loc_1800559BB
0x1800559ad  mov     rax, [rcx+10h]
0x1800559b1  mov     [rbx+70h], rax
0x1800559b5  call    cs:__imp_CoTaskMemFree
0x1800559bb  mov     rcx, [rbx+70h]; pv
0x1800559bf  test    rcx, rcx
0x1800559c2  jnz     short loc_1800559AD
0x1800559c4  mov     rdi, [rbx+28h]
0x1800559c8  test    rdi, rdi
0x1800559cb  jz      short loc_1800559DE
0x1800559cd  mov     rcx, rdi; this
0x1800559d0  call    ??1CFreeSlabManagerDelegate@@QEAA@XZ; CFreeSlabManagerDelegate::~CFreeSlabManagerDelegate(void)
0x1800559d5  mov     rcx, rdi
0x1800559d8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800559de  mov     qword ptr [rbx+28h], 0
0x1800559e6  lea     rcx, [rsp+68h+var_48]; this
0x1800559eb  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800559f0  mov     rcx, rbx; this
0x1800559f3  mov     rbx, [rsp+68h+arg_0]
0x1800559f8  add     rsp, 60h
0x1800559fc  pop     rdi
0x1800559fd  jmp     ??1CFreeSlabManager@@QEAA@XZ; CFreeSlabManager::~CFreeSlabManager(void)
```
