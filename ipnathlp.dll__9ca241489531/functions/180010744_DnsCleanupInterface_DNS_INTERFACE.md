# DnsCleanupInterface(_DNS_INTERFACE *)

- ea: `0x180010744`
- end: `0x180010823`
- name: `?DnsCleanupInterface@@YAXPEAU_DNS_INTERFACE@@@Z`
- size: `223`
- prototype: `void __fastcall(struct _DNS_INTERFACE *lpMem)`
- caller_count: `22`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f5f0`
- `0x1800100d8`
- `0x180010830`
- `0x180012b80`
- `0x180012e18`
- `0x180025b68`
- `0x180025dd8`
- `0x180028840`
- `0x180028924`
- `0x18002c1c4`
- `0x18002e830`
- `0x18003afa0`
- `0x1800618bc`
- `0x18006212c`
- `0x180062420`
- `0x1800627fc`
- `0x18006299c`
- `0x180062c20`
- `0x180062f90`
- `0x180064760`
- `0x180064b80`
- `0x180064e8c`

## callees

- `0x18000c110`
- `0x180010744`
- `0x18003c4fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010793`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010793`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107e0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800107cc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800107cc`

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
0x180010744  mov     [rsp+arg_0], rbx
0x180010749  mov     [rsp+arg_8], rsi
0x18001074e  push    rdi
0x18001074f  sub     rsp, 20h
0x180010753  mov     rbx, rcx
0x180010756  mov     rcx, cs:WPP_GLOBAL_Control
0x18001075d  lea     rsi, WPP_GLOBAL_Control
0x180010764  cmp     rcx, rsi
0x180010767  jz      short loc_18001078A
0x180010769  test    byte ptr [rcx+1Ch], 10h
0x18001076d  jz      short loc_18001078A
0x18001076f  cmp     byte ptr [rcx+19h], 6
0x180010773  jb      short loc_18001078A
0x180010775  mov     rcx, [rcx+10h]
0x180010779  lea     r8, WPP_56b6188218e633e268d52c8066432fe3_Traceguids
0x180010780  mov     edx, 49h ; 'I'
0x180010785  call    WPP_SF_
0x18001078a  mov     rdi, [rbx+58h]
0x18001078e  test    rdi, rdi
0x180010791  jz      short loc_1800107AF
0x180010793  call    cs:__imp_GetProcessHeap
0x180010799  mov     r8, rdi; lpMem
0x18001079c  xor     edx, edx; dwFlags
0x18001079e  mov     rcx, rax; hHeap
0x1800107a1  call    cs:__imp_HeapFree
0x1800107a7  mov     qword ptr [rbx+58h], 0
0x1800107af  lea     rdi, [rbx+60h]
0x1800107b3  cmp     [rdi], rdi
0x1800107b6  jz      short loc_1800107C2
0x1800107b8  mov     rdx, [rdi]; struct _DNS_QUERY *
0x1800107bb  call    ?DnsDeleteQuery@@YAXPEAU_DNS_INTERFACE@@PEAU_DNS_QUERY@@@Z; DnsDeleteQuery(_DNS_INTERFACE *,_DNS_QUERY *)
0x1800107c0  jmp     short loc_1800107B3
0x1800107c2  dec     cs:?DnsInterfaceCount@@3JA; long DnsInterfaceCount
0x1800107c8  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800107cc  call    cs:__imp_DeleteCriticalSection
0x1800107d2  call    cs:__imp_GetProcessHeap
0x1800107d8  mov     r8, rbx; lpMem
0x1800107db  xor     edx, edx; dwFlags
0x1800107dd  mov     rcx, rax; hHeap
0x1800107e0  call    cs:__imp_HeapFree
0x1800107e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107ed  cmp     rcx, rsi
0x1800107f0  jz      short loc_180010813
0x1800107f2  test    byte ptr [rcx+1Ch], 10h
0x1800107f6  jz      short loc_180010813
0x1800107f8  cmp     byte ptr [rcx+19h], 6
0x1800107fc  jb      short loc_180010813
0x1800107fe  mov     rcx, [rcx+10h]
0x180010802  lea     r8, WPP_56b6188218e633e268d52c8066432fe3_Traceguids
0x180010809  mov     edx, 4Ah ; 'J'
0x18001080e  call    WPP_SF_
0x180010813  mov     rbx, [rsp+28h+arg_0]
0x180010818  mov     rsi, [rsp+28h+arg_8]
0x18001081d  add     rsp, 20h
0x180010821  pop     rdi
0x180010822  retn
```
