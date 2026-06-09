# AlgCleanupInterface(_ALG_INTERFACE *)

- ea: `0x1800276e0`
- end: `0x1800277a6`
- name: `?AlgCleanupInterface@@YAXPEAU_ALG_INTERFACE@@@Z`
- size: `198`
- prototype: `void __fastcall(struct _ALG_INTERFACE *lpMem)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180027094`
- `0x180027518`
- `0x1800833f0`
- `0x1800838b4`
- `0x180083ae4`
- `0x180083d40`
- `0x180084048`
- `0x180084130`

## callees

- `0x18000c110`
- `0x1800276e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002772f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027755`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002772f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002773d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027763`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002773d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027763`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002774f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002774f`

## pseudocode

```c
void __fastcall AlgCleanupInterface(struct _ALG_INTERFACE *lpMem)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v4; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_e2ed88314d28355b7de84c3e73689a3f_Traceguids);
  }
  v2 = (void *)*((_QWORD *)lpMem + 13);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    *((_QWORD *)lpMem + 13) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 16));
  v4 = GetProcessHeap();
  HeapFree(v4, 0, lpMem);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_e2ed88314d28355b7de84c3e73689a3f_Traceguids);
  }
}

```

## disassembly

```asm
0x1800276e0  mov     [rsp+arg_0], rbx
0x1800276e5  mov     [rsp+arg_8], rsi
0x1800276ea  push    rdi
0x1800276eb  sub     rsp, 20h
0x1800276ef  mov     rbx, rcx
0x1800276f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276f9  lea     rsi, WPP_GLOBAL_Control
0x180027700  cmp     rcx, rsi
0x180027703  jz      short loc_180027726
0x180027705  test    byte ptr [rcx+1Ch], 1
0x180027709  jz      short loc_180027726
0x18002770b  cmp     byte ptr [rcx+19h], 6
0x18002770f  jb      short loc_180027726
0x180027711  mov     rcx, [rcx+10h]
0x180027715  lea     r8, WPP_e2ed88314d28355b7de84c3e73689a3f_Traceguids
0x18002771c  mov     edx, 14h
0x180027721  call    WPP_SF_
0x180027726  mov     rdi, [rbx+68h]
0x18002772a  test    rdi, rdi
0x18002772d  jz      short loc_18002774B
0x18002772f  call    cs:__imp_GetProcessHeap
0x180027735  mov     r8, rdi; lpMem
0x180027738  xor     edx, edx; dwFlags
0x18002773a  mov     rcx, rax; hHeap
0x18002773d  call    cs:__imp_HeapFree
0x180027743  mov     qword ptr [rbx+68h], 0
0x18002774b  lea     rcx, [rbx+10h]; lpCriticalSection
0x18002774f  call    cs:__imp_DeleteCriticalSection
0x180027755  call    cs:__imp_GetProcessHeap
0x18002775b  mov     r8, rbx; lpMem
0x18002775e  xor     edx, edx; dwFlags
0x180027760  mov     rcx, rax; hHeap
0x180027763  call    cs:__imp_HeapFree
0x180027769  mov     rcx, cs:WPP_GLOBAL_Control
0x180027770  cmp     rcx, rsi
0x180027773  jz      short loc_180027796
0x180027775  test    byte ptr [rcx+1Ch], 1
0x180027779  jz      short loc_180027796
0x18002777b  cmp     byte ptr [rcx+19h], 6
0x18002777f  jb      short loc_180027796
0x180027781  mov     rcx, [rcx+10h]
0x180027785  lea     r8, WPP_e2ed88314d28355b7de84c3e73689a3f_Traceguids
0x18002778c  mov     edx, 15h
0x180027791  call    WPP_SF_
0x180027796  mov     rbx, [rsp+28h+arg_0]
0x18002779b  mov     rsi, [rsp+28h+arg_8]
0x1800277a0  add     rsp, 20h
0x1800277a4  pop     rdi
0x1800277a5  retn
```
