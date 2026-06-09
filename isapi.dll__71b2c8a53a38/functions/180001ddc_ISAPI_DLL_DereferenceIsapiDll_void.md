# ISAPI_DLL::DereferenceIsapiDll(void)

- ea: `0x180001ddc`
- end: `0x180001e36`
- name: `?DereferenceIsapiDll@ISAPI_DLL@@QEAAXXZ`
- size: `90`
- prototype: `void __fastcall(ISAPI_DLL *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001c84`
- `0x180002d9c`
- `0x1800033f0`
- `0x180005224`

## callees

- `0x180001bac`
- `0x180001ddc`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180001e25`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180001e25`
- `iisutil!WriteRefTraceLog` at `0x180001e04`
- `iisutil!WriteRefTraceLog` at `0x180001e04`

## pseudocode

```c
void __fastcall ISAPI_DLL::DereferenceIsapiDll(ISAPI_DLL *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 1);
  if ( ISAPI_DLL::sm_pTraceLog )
    WriteRefTraceLog(ISAPI_DLL::sm_pTraceLog, v2, this);
  if ( !v2 )
  {
    if ( this )
    {
      ISAPI_DLL::~ISAPI_DLL(this);
      ALLOC_CACHE_HANDLER::Free(ISAPI_DLL::sm_pachIsapiDlls, this);
    }
  }
}

```

## disassembly

```asm
0x180001ddc  mov     [rsp+arg_0], rbx
0x180001de1  push    rdi
0x180001de2  sub     rsp, 20h
0x180001de6  mov     rbx, rcx
0x180001de9  or      edi, 0FFFFFFFFh
0x180001dec  lock xadd [rcx+4], edi
0x180001df1  mov     rcx, cs:?sm_pTraceLog@ISAPI_DLL@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * ISAPI_DLL::sm_pTraceLog
0x180001df8  dec     edi
0x180001dfa  test    rcx, rcx
0x180001dfd  jz      short loc_180001E0A
0x180001dff  mov     r8, rbx
0x180001e02  mov     edx, edi
0x180001e04  call    cs:__imp_WriteRefTraceLog
0x180001e0a  test    edi, edi
0x180001e0c  jnz     short loc_180001E2B
0x180001e0e  test    rbx, rbx
0x180001e11  jz      short loc_180001E2B
0x180001e13  mov     rcx, rbx; this
0x180001e16  call    ??1ISAPI_DLL@@AEAA@XZ; ISAPI_DLL::~ISAPI_DLL(void)
0x180001e1b  mov     rcx, cs:?sm_pachIsapiDlls@ISAPI_DLL@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ISAPI_DLL::sm_pachIsapiDlls
0x180001e22  mov     rdx, rbx
0x180001e25  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180001e2b  mov     rbx, [rsp+28h+arg_0]
0x180001e30  add     rsp, 20h
0x180001e34  pop     rdi
0x180001e35  retn
```
