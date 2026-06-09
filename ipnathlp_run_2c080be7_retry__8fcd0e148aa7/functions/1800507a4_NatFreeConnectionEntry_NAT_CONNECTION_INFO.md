# NatFreeConnectionEntry(_NAT_CONNECTION_INFO *)

- ea: `0x1800507a4`
- end: `0x18005090e`
- name: `?NatFreeConnectionEntry@@YAXPEAU_NAT_CONNECTION_INFO@@@Z`
- size: `362`
- prototype: `void __fastcall(struct _NAT_CONNECTION_INFO *)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004ff48`
- `0x18007e1f0`
- `0x180082978`

## callees

- `0x18000ca20`
- `0x1800507a4`
- `0x18007fd90`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800507f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005081f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050848`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800508ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800507f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005081f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050848`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800508ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005080a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050833`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005085c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800508c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005080a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050833`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005085c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800508c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050881`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050899`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050881`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050899`

## pseudocode

```c
void __fastcall NatFreeConnectionEntry(struct _NAT_CONNECTION_INFO *a1)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax
  __int64 v8; // rcx
  void *v9; // rcx
  HANDLE v10; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids);
  }
  v2 = (void *)*((_QWORD *)a1 + 3);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = (void *)*((_QWORD *)a1 + 4);
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  v6 = (void *)*((_QWORD *)a1 + 5);
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
  v8 = *((_QWORD *)a1 + 12);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  CoTaskMemFree(*((LPVOID *)a1 + 13));
  v9 = (void *)*((_QWORD *)a1 + 18);
  if ( v9 )
    CoTaskMemFree(v9);
  NatFreePortMappingList(a1);
  v10 = GetProcessHeap();
  HeapFree(v10, 0, a1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids);
  }
}

```

## disassembly

```asm
0x1800507a4  mov     [rsp+arg_0], rbx
0x1800507a9  mov     [rsp+arg_8], rbp
0x1800507ae  push    rdi
0x1800507af  sub     rsp, 20h
0x1800507b3  mov     rbx, rcx
0x1800507b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800507bd  lea     rbp, WPP_GLOBAL_Control
0x1800507c4  cmp     rcx, rbp
0x1800507c7  jz      short loc_1800507ED
0x1800507c9  test    dword ptr [rcx+1Ch], 200h
0x1800507d0  jz      short loc_1800507ED
0x1800507d2  cmp     byte ptr [rcx+19h], 6
0x1800507d6  jb      short loc_1800507ED
0x1800507d8  mov     rcx, [rcx+10h]
0x1800507dc  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x1800507e3  mov     edx, 7Ah ; 'z'
0x1800507e8  call    WPP_SF_
0x1800507ed  mov     rdi, [rbx+18h]
0x1800507f1  test    rdi, rdi
0x1800507f4  jz      short loc_180050816
0x1800507f6  call    cs:__imp_GetProcessHeap
0x1800507fd  nop     dword ptr [rax+rax+00h]
0x180050802  mov     r8, rdi; lpMem
0x180050805  xor     edx, edx; dwFlags
0x180050807  mov     rcx, rax; hHeap
0x18005080a  call    cs:__imp_HeapFree
0x180050811  nop     dword ptr [rax+rax+00h]
0x180050816  mov     rdi, [rbx+20h]
0x18005081a  test    rdi, rdi
0x18005081d  jz      short loc_18005083F
0x18005081f  call    cs:__imp_GetProcessHeap
0x180050826  nop     dword ptr [rax+rax+00h]
0x18005082b  mov     r8, rdi; lpMem
0x18005082e  xor     edx, edx; dwFlags
0x180050830  mov     rcx, rax; hHeap
0x180050833  call    cs:__imp_HeapFree
0x18005083a  nop     dword ptr [rax+rax+00h]
0x18005083f  mov     rdi, [rbx+28h]
0x180050843  test    rdi, rdi
0x180050846  jz      short loc_180050868
0x180050848  call    cs:__imp_GetProcessHeap
0x18005084f  nop     dword ptr [rax+rax+00h]
0x180050854  mov     r8, rdi; lpMem
0x180050857  xor     edx, edx; dwFlags
0x180050859  mov     rcx, rax; hHeap
0x18005085c  call    cs:__imp_HeapFree
0x180050863  nop     dword ptr [rax+rax+00h]
0x180050868  mov     rcx, [rbx+60h]
0x18005086c  test    rcx, rcx
0x18005086f  jz      short loc_18005087D
0x180050871  mov     rax, [rcx]
0x180050874  mov     rax, [rax+10h]
0x180050878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005087d  mov     rcx, [rbx+68h]; pv
0x180050881  call    cs:__imp_CoTaskMemFree
0x180050888  nop     dword ptr [rax+rax+00h]
0x18005088d  mov     rcx, [rbx+90h]; pv
0x180050894  test    rcx, rcx
0x180050897  jz      short loc_1800508A5
0x180050899  call    cs:__imp_CoTaskMemFree
0x1800508a0  nop     dword ptr [rax+rax+00h]
0x1800508a5  mov     rcx, rbx; struct _NAT_CONNECTION_INFO *
0x1800508a8  call    ?NatFreePortMappingList@@YAXPEAU_NAT_CONNECTION_INFO@@@Z; NatFreePortMappingList(_NAT_CONNECTION_INFO *)
0x1800508ad  call    cs:__imp_GetProcessHeap
0x1800508b4  nop     dword ptr [rax+rax+00h]
0x1800508b9  mov     r8, rbx; lpMem
0x1800508bc  xor     edx, edx; dwFlags
0x1800508be  mov     rcx, rax; hHeap
0x1800508c1  call    cs:__imp_HeapFree
0x1800508c8  nop     dword ptr [rax+rax+00h]
0x1800508cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800508d4  cmp     rcx, rbp
0x1800508d7  jz      short loc_1800508FD
0x1800508d9  test    dword ptr [rcx+1Ch], 200h
0x1800508e0  jz      short loc_1800508FD
0x1800508e2  cmp     byte ptr [rcx+19h], 6
0x1800508e6  jb      short loc_1800508FD
0x1800508e8  mov     rcx, [rcx+10h]
0x1800508ec  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x1800508f3  mov     edx, 7Bh ; '{'
0x1800508f8  call    WPP_SF_
0x1800508fd  mov     rbx, [rsp+28h+arg_0]
0x180050902  mov     rbp, [rsp+28h+arg_8]
0x180050907  add     rsp, 20h
0x18005090b  pop     rdi
0x18005090c  retn
```
