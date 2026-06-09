# CFileAccessor::~CFileAccessor(void)

- ea: `0x180007ff0`
- end: `0x1800080a3`
- name: `??1CFileAccessor@@QEAA@XZ`
- size: `179`
- prototype: `void __fastcall(wchar_t *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007f8c`

## callees

- `0x180003110`
- `0x1800055b0`
- `0x180006ad0`
- `0x180007078`
- `0x180007ff0`
- `0x18000d904`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008050`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008067`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000807b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000808f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008050`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008067`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000807b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000808f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008015`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008015`

## pseudocode

```c
void __fastcall CFileAccessor::~CFileAccessor(wchar_t *this)
{
  void *v2; // rcx
  char *v3; // rcx
  char *v4; // rcx
  char *v5; // rcx
  char *v6; // rcx

  CFileAccessor::Reset((CFileAccessor *)this);
  v2 = (void *)*((_QWORD *)this + 116);
  *((_QWORD *)this + 116) = 0;
  if ( v2 )
    LocalFree(v2);
  TLMString<64,64,32767>::~TLMString<64,64,32767>(this + 348);
  CURL::~CURL((CURL *)(this + 112));
  TComPointer<CFileStream>::~TComPointer<CFileStream>((_QWORD *)this + 27);
  v3 = (char *)*((_QWORD *)this + 26);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v3);
  v4 = (char *)*((_QWORD *)this + 25);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  v5 = (char *)*((_QWORD *)this + 13);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  v6 = (char *)*((_QWORD *)this + 12);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(this + 20));
}

```

## disassembly

```asm
0x180007ff0  push    rbx
0x180007ff2  sub     rsp, 20h
0x180007ff6  mov     rbx, rcx
0x180007ff9  call    ?Reset@CFileAccessor@@QEAAJXZ; CFileAccessor::Reset(void)
0x180007ffe  mov     rcx, [rbx+3A0h]; hMem
0x180008005  mov     qword ptr [rbx+3A0h], 0
0x180008010  test    rcx, rcx
0x180008013  jz      short loc_18000801B
0x180008015  call    cs:__imp_LocalFree
0x18000801b  lea     rcx, [rbx+2B8h]
0x180008022  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180008027  lea     rcx, [rbx+0E0h]; this
0x18000802e  call    ??1CURL@@QEAA@XZ; CURL::~CURL(void)
0x180008033  lea     rcx, [rbx+0D8h]
0x18000803a  call    ??1?$TComPointer@VCFileStream@@@@QEAA@XZ; TComPointer<CFileStream>::~TComPointer<CFileStream>(void)
0x18000803f  mov     rcx, [rbx+0D0h]; hObject
0x180008046  lea     rax, [rcx-1]
0x18000804a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000804e  ja      short loc_180008056
0x180008050  call    cs:__imp_CloseHandle
0x180008056  mov     rcx, [rbx+0C8h]; hObject
0x18000805d  lea     rax, [rcx-1]
0x180008061  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008065  ja      short loc_18000806D
0x180008067  call    cs:__imp_CloseHandle
0x18000806d  mov     rcx, [rbx+68h]; hObject
0x180008071  lea     rax, [rcx-1]
0x180008075  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008079  ja      short loc_180008081
0x18000807b  call    cs:__imp_CloseHandle
0x180008081  mov     rcx, [rbx+60h]; hObject
0x180008085  lea     rax, [rcx-1]
0x180008089  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000808d  ja      short loc_180008095
0x18000808f  call    cs:__imp_CloseHandle
0x180008095  lea     rcx, [rbx+28h]; this
0x180008099  add     rsp, 20h
0x18000809d  pop     rbx
0x18000809e  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
