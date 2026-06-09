# UtcThrottle::~UtcThrottle(void)

- ea: `0x1400188f0`
- end: `0x140018982`
- name: `??1UtcThrottle@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(UtcThrottle *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400a7d20`

## callees

- `0x1400188f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001897b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140018968`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140018968`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140018904`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140018904`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140018913`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140018913`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018921`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018937`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001894e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018921`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018937`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001894e`

## pseudocode

```c
void __fastcall UtcThrottle::~UtcThrottle(UtcThrottle *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
    SetEvent(v3);
  if ( *(_QWORD *)this )
  {
    CloseHandle(*(HANDLE *)this);
    *(_QWORD *)this = 0;
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 1) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 2) = 0;
  }
  *((_BYTE *)this + 64) = 0;
  if ( v1 )
    LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
}

```

## disassembly

```asm
0x1400188f0  mov     [rsp+arg_0], rbx
0x1400188f5  push    rdi
0x1400188f6  sub     rsp, 20h
0x1400188fa  lea     rdi, [rcx+18h]
0x1400188fe  mov     rbx, rcx
0x140018901  mov     rcx, rdi; lpCriticalSection
0x140018904  call    cs:__imp_EnterCriticalSection
0x14001890a  mov     rcx, [rbx+10h]; hEvent
0x14001890e  test    rcx, rcx
0x140018911  jz      short loc_140018919
0x140018913  call    cs:__imp_SetEvent
0x140018919  mov     rcx, [rbx]; hObject
0x14001891c  test    rcx, rcx
0x14001891f  jz      short loc_14001892E
0x140018921  call    cs:__imp_CloseHandle
0x140018927  mov     qword ptr [rbx], 0
0x14001892e  mov     rcx, [rbx+8]; hObject
0x140018932  test    rcx, rcx
0x140018935  jz      short loc_140018945
0x140018937  call    cs:__imp_CloseHandle
0x14001893d  mov     qword ptr [rbx+8], 0
0x140018945  mov     rcx, [rbx+10h]; hObject
0x140018949  test    rcx, rcx
0x14001894c  jz      short loc_14001895C
0x14001894e  call    cs:__imp_CloseHandle
0x140018954  mov     qword ptr [rbx+10h], 0
0x14001895c  mov     byte ptr [rbx+40h], 0
0x140018960  test    rdi, rdi
0x140018963  jz      short loc_14001896E
0x140018965  mov     rcx, rdi; lpCriticalSection
0x140018968  call    cs:__imp_LeaveCriticalSection
0x14001896e  mov     rcx, rdi
0x140018971  mov     rbx, [rsp+28h+arg_0]
0x140018976  add     rsp, 20h
0x14001897a  pop     rdi
0x14001897b  jmp     cs:__imp_DeleteCriticalSection
```
