# DnsCleanupInterface(_DNS_INTERFACE *)

- ea: `0x180011428`
- end: `0x180011526`
- name: `?DnsCleanupInterface@@YAXPEAU_DNS_INTERFACE@@@Z`
- size: `254`
- prototype: `void __fastcall(struct _DNS_INTERFACE *lpMem)`
- caller_count: `22`
- callee_count: `3`
- tags: ``

## callers

- `0x1800101a8`
- `0x180010d70`
- `0x180011530`
- `0x180013ad0`
- `0x180013dbc`
- `0x180020340`
- `0x18002043c`
- `0x180027fd8`
- `0x180028268`
- `0x1800309c0`
- `0x1800331d0`
- `0x18003e124`
- `0x180066444`
- `0x180066d44`
- `0x180067060`
- `0x180067468`
- `0x180067624`
- `0x1800678e0`
- `0x180067cb0`
- `0x180069640`
- `0x180069ab0`
- `0x180069dd4`

## callees

- `0x18000ca20`
- `0x180011428`
- `0x18003f734`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011477`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800114c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011477`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800114c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001148b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800114dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001148b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800114dc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800114bc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800114bc`

## pseudocode

```c
void __fastcall DnsCleanupInterface(struct _DNS_INTERFACE *lpMem)
{
  struct _DNS_INTERFACE *v2; // rcx
  void *v3; // rdi
  HANDLE ProcessHeap; // rax
  struct _DNS_QUERY **i; // rdi
  HANDLE v6; // rax

  v2 = (struct _DNS_INTERFACE *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_56b6188218e633e268d52c8066432fe3_Traceguids);
  }
  v3 = (void *)*((_QWORD *)lpMem + 11);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    *((_QWORD *)lpMem + 11) = 0;
  }
  for ( i = (struct _DNS_QUERY **)((char *)lpMem + 96); *i != (struct _DNS_QUERY *)i; DnsDeleteQuery(v2, *i) )
    ;
  --DnsInterfaceCount;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 16));
  v6 = GetProcessHeap();
  HeapFree(v6, 0, lpMem);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_56b6188218e633e268d52c8066432fe3_Traceguids);
  }
}

```

## disassembly

```asm
0x180011428  mov     [rsp+arg_0], rbx
0x18001142d  mov     [rsp+arg_8], rsi
0x180011432  push    rdi
0x180011433  sub     rsp, 20h
0x180011437  mov     rbx, rcx
0x18001143a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011441  lea     rsi, WPP_GLOBAL_Control
0x180011448  cmp     rcx, rsi
0x18001144b  jz      short loc_18001146E
0x18001144d  test    byte ptr [rcx+1Ch], 10h
0x180011451  jz      short loc_18001146E
0x180011453  cmp     byte ptr [rcx+19h], 6
0x180011457  jb      short loc_18001146E
0x180011459  mov     rcx, [rcx+10h]
0x18001145d  lea     r8, WPP_56b6188218e633e268d52c8066432fe3_Traceguids
0x180011464  mov     edx, 49h ; 'I'
0x180011469  call    WPP_SF_
0x18001146e  mov     rdi, [rbx+58h]
0x180011472  test    rdi, rdi
0x180011475  jz      short loc_18001149F
0x180011477  call    cs:__imp_GetProcessHeap
0x18001147e  nop     dword ptr [rax+rax+00h]
0x180011483  mov     r8, rdi; lpMem
0x180011486  xor     edx, edx; dwFlags
0x180011488  mov     rcx, rax; hHeap
0x18001148b  call    cs:__imp_HeapFree
0x180011492  nop     dword ptr [rax+rax+00h]
0x180011497  mov     qword ptr [rbx+58h], 0
0x18001149f  lea     rdi, [rbx+60h]
0x1800114a3  cmp     [rdi], rdi
0x1800114a6  jz      short loc_1800114B2
0x1800114a8  mov     rdx, [rdi]; struct _DNS_QUERY *
0x1800114ab  call    ?DnsDeleteQuery@@YAXPEAU_DNS_INTERFACE@@PEAU_DNS_QUERY@@@Z; DnsDeleteQuery(_DNS_INTERFACE *,_DNS_QUERY *)
0x1800114b0  jmp     short loc_1800114A3
0x1800114b2  dec     cs:?DnsInterfaceCount@@3JA; long DnsInterfaceCount
0x1800114b8  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800114bc  call    cs:__imp_DeleteCriticalSection
0x1800114c3  nop     dword ptr [rax+rax+00h]
0x1800114c8  call    cs:__imp_GetProcessHeap
0x1800114cf  nop     dword ptr [rax+rax+00h]
0x1800114d4  mov     r8, rbx; lpMem
0x1800114d7  xor     edx, edx; dwFlags
0x1800114d9  mov     rcx, rax; hHeap
0x1800114dc  call    cs:__imp_HeapFree
0x1800114e3  nop     dword ptr [rax+rax+00h]
0x1800114e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114ef  cmp     rcx, rsi
0x1800114f2  jz      short loc_180011515
0x1800114f4  test    byte ptr [rcx+1Ch], 10h
0x1800114f8  jz      short loc_180011515
0x1800114fa  cmp     byte ptr [rcx+19h], 6
0x1800114fe  jb      short loc_180011515
0x180011500  mov     rcx, [rcx+10h]
0x180011504  lea     r8, WPP_56b6188218e633e268d52c8066432fe3_Traceguids
0x18001150b  mov     edx, 4Ah ; 'J'
0x180011510  call    WPP_SF_
0x180011515  mov     rbx, [rsp+28h+arg_0]
0x18001151a  mov     rsi, [rsp+28h+arg_8]
0x18001151f  add     rsp, 20h
0x180011523  pop     rdi
0x180011524  retn
```
