# AlgCleanupInterface(_ALG_INTERFACE *)

- ea: `0x180029d7c`
- end: `0x180029e61`
- name: `?AlgCleanupInterface@@YAXPEAU_ALG_INTERFACE@@@Z`
- size: `229`
- prototype: `void __fastcall(struct _ALG_INTERFACE *lpMem)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800296d0`
- `0x180029b98`
- `0x180089bc4`
- `0x18008a0e4`
- `0x18008a334`
- `0x18008a5ac`
- `0x18008a8dc`
- `0x18008a9cc`

## callees

- `0x18000ca20`
- `0x180029d7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029dcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029e03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029dcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029e03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029ddf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029e17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029ddf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029e17`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029df7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029df7`

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
0x180029d7c  mov     [rsp+arg_0], rbx
0x180029d81  mov     [rsp+arg_8], rsi
0x180029d86  push    rdi
0x180029d87  sub     rsp, 20h
0x180029d8b  mov     rbx, rcx
0x180029d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d95  lea     rsi, WPP_GLOBAL_Control
0x180029d9c  cmp     rcx, rsi
0x180029d9f  jz      short loc_180029DC2
0x180029da1  test    byte ptr [rcx+1Ch], 1
0x180029da5  jz      short loc_180029DC2
0x180029da7  cmp     byte ptr [rcx+19h], 6
0x180029dab  jb      short loc_180029DC2
0x180029dad  mov     rcx, [rcx+10h]
0x180029db1  lea     r8, WPP_e2ed88314d28355b7de84c3e73689a3f_Traceguids
0x180029db8  mov     edx, 14h
0x180029dbd  call    WPP_SF_
0x180029dc2  mov     rdi, [rbx+68h]
0x180029dc6  test    rdi, rdi
0x180029dc9  jz      short loc_180029DF3
0x180029dcb  call    cs:__imp_GetProcessHeap
0x180029dd2  nop     dword ptr [rax+rax+00h]
0x180029dd7  mov     r8, rdi; lpMem
0x180029dda  xor     edx, edx; dwFlags
0x180029ddc  mov     rcx, rax; hHeap
0x180029ddf  call    cs:__imp_HeapFree
0x180029de6  nop     dword ptr [rax+rax+00h]
0x180029deb  mov     qword ptr [rbx+68h], 0
0x180029df3  lea     rcx, [rbx+10h]; lpCriticalSection
0x180029df7  call    cs:__imp_DeleteCriticalSection
0x180029dfe  nop     dword ptr [rax+rax+00h]
0x180029e03  call    cs:__imp_GetProcessHeap
0x180029e0a  nop     dword ptr [rax+rax+00h]
0x180029e0f  mov     r8, rbx; lpMem
0x180029e12  xor     edx, edx; dwFlags
0x180029e14  mov     rcx, rax; hHeap
0x180029e17  call    cs:__imp_HeapFree
0x180029e1e  nop     dword ptr [rax+rax+00h]
0x180029e23  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e2a  cmp     rcx, rsi
0x180029e2d  jz      short loc_180029E50
0x180029e2f  test    byte ptr [rcx+1Ch], 1
0x180029e33  jz      short loc_180029E50
0x180029e35  cmp     byte ptr [rcx+19h], 6
0x180029e39  jb      short loc_180029E50
0x180029e3b  mov     rcx, [rcx+10h]
0x180029e3f  lea     r8, WPP_e2ed88314d28355b7de84c3e73689a3f_Traceguids
0x180029e46  mov     edx, 15h
0x180029e4b  call    WPP_SF_
0x180029e50  mov     rbx, [rsp+28h+arg_0]
0x180029e55  mov     rsi, [rsp+28h+arg_8]
0x180029e5a  add     rsp, 20h
0x180029e5e  pop     rdi
0x180029e5f  retn
```
