# CDefragEngine::~CDefragEngine(void)

- ea: `0x18001c424`
- end: `0x18001c564`
- name: `??1CDefragEngine@@QEAA@XZ`
- size: `320`
- prototype: `void __fastcall(CDefragEngine *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180047100`
- `0x180047190`

## callees

- `0x180017e50`
- `0x18001ac0c`
- `0x18001c424`
- `0x18001c578`
- `0x180038c3c`
- `0x180038f18`
- `0x1800458cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c462`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c4ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c4cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c4ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c50e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c4ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c4cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c4ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c50e`

## pseudocode

```c
void __fastcall CDefragEngine::~CDefragEngine(CDefragEngine *this)
{
  CSxStringList *v2; // rcx
  char *v3; // rcx
  char *v4; // rcx
  char *v5; // rcx
  char *v6; // rcx
  CDfClientList *v7; // rcx
  CDfVolumeList *v8; // rcx
  CSxRefTraceList *v9; // rcx

  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_bf5248634d2b3b92b4f78ef82fe4291c_Traceguids);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  *((_DWORD *)this + 45) = 1;
  std::deque<__MIDL___MIDL_itf_dfengine_0000_0000_0008>::~deque<__MIDL___MIDL_itf_dfengine_0000_0000_0008>((char *)this + 192);
  v2 = (CSxStringList *)*((_QWORD *)this + 23);
  if ( v2 )
  {
    *((_QWORD *)this + 23) = 0;
    CSxStringList::Release(v2);
  }
  v3 = (char *)*((_QWORD *)this + 18);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 18) = 0;
  }
  v4 = (char *)*((_QWORD *)this + 17);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 17) = 0;
  }
  v5 = (char *)*((_QWORD *)this + 16);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 16) = 0;
  }
  v6 = (char *)*((_QWORD *)this + 15);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 15) = 0;
  }
  v7 = (CDfClientList *)*((_QWORD *)this + 14);
  if ( v7 )
  {
    *((_QWORD *)this + 14) = 0;
    CDfClientList::Release(v7);
  }
  v8 = (CDfVolumeList *)*((_QWORD *)this + 13);
  if ( v8 )
  {
    *((_QWORD *)this + 13) = 0;
    CDfVolumeList::Release(v8);
  }
  v9 = (CSxRefTraceList *)*((_QWORD *)this + 7);
  if ( v9 )
  {
    *((_QWORD *)this + 7) = 0;
    CSxRefTraceList::Release(v9);
  }
}

```

## disassembly

```asm
0x18001c424  push    rbx
0x18001c426  sub     rsp, 20h
0x18001c42a  mov     rbx, rcx
0x18001c42d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c434  lea     rax, WPP_GLOBAL_Control
0x18001c43b  cmp     rcx, rax
0x18001c43e  jz      short loc_18001C45E
0x18001c440  test    dword ptr [rcx+1Ch], 8000000h
0x18001c447  jz      short loc_18001C45E
0x18001c449  mov     rcx, [rcx+10h]
0x18001c44d  lea     r8, WPP_bf5248634d2b3b92b4f78ef82fe4291c_Traceguids
0x18001c454  mov     edx, 0Ah
0x18001c459  call    WPP_SF_
0x18001c45e  lea     rcx, [rbx+40h]; lpCriticalSection
0x18001c462  call    cs:__imp_DeleteCriticalSection
0x18001c468  lea     rcx, [rbx+0C0h]
0x18001c46f  mov     dword ptr [rbx+0B4h], 1
0x18001c479  call    ??1?$deque@U__MIDL___MIDL_itf_dfengine_0000_0000_0008@@V?$allocator@U__MIDL___MIDL_itf_dfengine_0000_0000_0008@@@std@@@std@@QEAA@XZ; std::deque<__MIDL___MIDL_itf_dfengine_0000_0000_0008>::~deque<__MIDL___MIDL_itf_dfengine_0000_0000_0008>(void)
0x18001c47e  mov     rcx, [rbx+0B8h]; this
0x18001c485  test    rcx, rcx
0x18001c488  jz      short loc_18001C49A
0x18001c48a  mov     qword ptr [rbx+0B8h], 0
0x18001c495  call    ?Release@CSxStringList@@QEAAKXZ; CSxStringList::Release(void)
0x18001c49a  mov     rcx, [rbx+90h]; hObject
0x18001c4a1  lea     rax, [rcx-1]
0x18001c4a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c4a9  ja      short loc_18001C4BC
0x18001c4ab  call    cs:__imp_CloseHandle
0x18001c4b1  mov     qword ptr [rbx+90h], 0
0x18001c4bc  mov     rcx, [rbx+88h]; hObject
0x18001c4c3  lea     rax, [rcx-1]
0x18001c4c7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c4cb  ja      short loc_18001C4DE
0x18001c4cd  call    cs:__imp_CloseHandle
0x18001c4d3  mov     qword ptr [rbx+88h], 0
0x18001c4de  mov     rcx, [rbx+80h]; hObject
0x18001c4e5  lea     rax, [rcx-1]
0x18001c4e9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c4ed  ja      short loc_18001C500
0x18001c4ef  call    cs:__imp_CloseHandle
0x18001c4f5  mov     qword ptr [rbx+80h], 0
0x18001c500  mov     rcx, [rbx+78h]; hObject
0x18001c504  lea     rax, [rcx-1]
0x18001c508  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c50c  ja      short loc_18001C51C
0x18001c50e  call    cs:__imp_CloseHandle
0x18001c514  mov     qword ptr [rbx+78h], 0
0x18001c51c  mov     rcx, [rbx+70h]; this
0x18001c520  test    rcx, rcx
0x18001c523  jz      short loc_18001C532
0x18001c525  mov     qword ptr [rbx+70h], 0
0x18001c52d  call    ?Release@CDfClientList@@QEAAKXZ; CDfClientList::Release(void)
0x18001c532  mov     rcx, [rbx+68h]; this
0x18001c536  test    rcx, rcx
0x18001c539  jz      short loc_18001C548
0x18001c53b  mov     qword ptr [rbx+68h], 0
0x18001c543  call    ?Release@CDfVolumeList@@QEAAKXZ; CDfVolumeList::Release(void)
0x18001c548  mov     rcx, [rbx+38h]; this
0x18001c54c  test    rcx, rcx
0x18001c54f  jz      short loc_18001C55E
0x18001c551  mov     qword ptr [rbx+38h], 0
0x18001c559  call    ?Release@CSxRefTraceList@@QEAAKXZ; CSxRefTraceList::Release(void)
0x18001c55e  add     rsp, 20h
0x18001c562  pop     rbx
0x18001c563  retn
```
