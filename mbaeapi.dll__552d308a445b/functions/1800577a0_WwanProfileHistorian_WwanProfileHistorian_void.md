# WwanProfileHistorian::~WwanProfileHistorian(void)

- ea: `0x1800577a0`
- end: `0x180057803`
- name: `??1WwanProfileHistorian@@QEAA@XZ`
- size: `99`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002d880`

## callees

- `0x180055448`
- `0x1800577a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800577da`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800577da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800577f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800577f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800577e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800577e9`

## pseudocode

```c
void __fastcall WwanProfileHistorian::~WwanProfileHistorian(LPCRITICAL_SECTION lpCriticalSection)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_59efe20e95083d54484ef368743a0c87_Traceguids);
  DeleteCriticalSection(lpCriticalSection);
  v2 = *(void **)&lpCriticalSection[1].LockCount;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
}

```

## disassembly

```asm
0x1800577a0  push    rbx
0x1800577a2  sub     rsp, 20h
0x1800577a6  mov     rbx, rcx
0x1800577a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800577b0  lea     rax, WPP_GLOBAL_Control
0x1800577b7  cmp     rcx, rax
0x1800577ba  jz      short loc_1800577D7
0x1800577bc  test    byte ptr [rcx+1Ch], 10h
0x1800577c0  jz      short loc_1800577D7
0x1800577c2  mov     rcx, [rcx+10h]
0x1800577c6  lea     r8, WPP_59efe20e95083d54484ef368743a0c87_Traceguids
0x1800577cd  mov     edx, 0Ch
0x1800577d2  call    WPP_SF_
0x1800577d7  mov     rcx, rbx; lpCriticalSection
0x1800577da  call    cs:__imp_DeleteCriticalSection
0x1800577e0  mov     rbx, [rbx+30h]
0x1800577e4  test    rbx, rbx
0x1800577e7  jz      short loc_1800577FD
0x1800577e9  call    cs:__imp_GetProcessHeap
0x1800577ef  mov     r8, rbx; lpMem
0x1800577f2  xor     edx, edx; dwFlags
0x1800577f4  mov     rcx, rax; hHeap
0x1800577f7  call    cs:__imp_HeapFree
0x1800577fd  add     rsp, 20h
0x180057801  pop     rbx
0x180057802  retn
```
