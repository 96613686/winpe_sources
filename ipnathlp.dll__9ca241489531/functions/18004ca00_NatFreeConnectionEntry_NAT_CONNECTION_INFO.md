# NatFreeConnectionEntry(_NAT_CONNECTION_INFO *)

- ea: `0x18004ca00`
- end: `0x18004cb2d`
- name: `?NatFreeConnectionEntry@@YAXPEAU_NAT_CONNECTION_INFO@@@Z`
- size: `301`
- prototype: `void __fastcall(struct _NAT_CONNECTION_INFO *)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004c214`
- `0x180078178`
- `0x18007c648`

## callees

- `0x18000c110`
- `0x18004ca00`
- `0x180079cbc`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ca52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ca6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ca8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cad9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ca52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ca6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ca8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cad9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ca60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ca7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ca9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004cae7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ca60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ca7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ca9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004cae7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cab9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cacb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cab9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cacb`

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
0x18004ca00  mov     [rsp+arg_0], rbx
0x18004ca05  mov     [rsp+arg_8], rbp
0x18004ca0a  push    rdi
0x18004ca0b  sub     rsp, 20h
0x18004ca0f  mov     rbx, rcx
0x18004ca12  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ca19  lea     rbp, WPP_GLOBAL_Control
0x18004ca20  cmp     rcx, rbp
0x18004ca23  jz      short loc_18004CA49
0x18004ca25  test    dword ptr [rcx+1Ch], 200h
0x18004ca2c  jz      short loc_18004CA49
0x18004ca2e  cmp     byte ptr [rcx+19h], 6
0x18004ca32  jb      short loc_18004CA49
0x18004ca34  mov     rcx, [rcx+10h]
0x18004ca38  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x18004ca3f  mov     edx, 7Ah ; 'z'
0x18004ca44  call    WPP_SF_
0x18004ca49  mov     rdi, [rbx+18h]
0x18004ca4d  test    rdi, rdi
0x18004ca50  jz      short loc_18004CA66
0x18004ca52  call    cs:__imp_GetProcessHeap
0x18004ca58  mov     r8, rdi; lpMem
0x18004ca5b  xor     edx, edx; dwFlags
0x18004ca5d  mov     rcx, rax; hHeap
0x18004ca60  call    cs:__imp_HeapFree
0x18004ca66  mov     rdi, [rbx+20h]
0x18004ca6a  test    rdi, rdi
0x18004ca6d  jz      short loc_18004CA83
0x18004ca6f  call    cs:__imp_GetProcessHeap
0x18004ca75  mov     r8, rdi; lpMem
0x18004ca78  xor     edx, edx; dwFlags
0x18004ca7a  mov     rcx, rax; hHeap
0x18004ca7d  call    cs:__imp_HeapFree
0x18004ca83  mov     rdi, [rbx+28h]
0x18004ca87  test    rdi, rdi
0x18004ca8a  jz      short loc_18004CAA0
0x18004ca8c  call    cs:__imp_GetProcessHeap
0x18004ca92  mov     r8, rdi; lpMem
0x18004ca95  xor     edx, edx; dwFlags
0x18004ca97  mov     rcx, rax; hHeap
0x18004ca9a  call    cs:__imp_HeapFree
0x18004caa0  mov     rcx, [rbx+60h]
0x18004caa4  test    rcx, rcx
0x18004caa7  jz      short loc_18004CAB5
0x18004caa9  mov     rax, [rcx]
0x18004caac  mov     rax, [rax+10h]
0x18004cab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cab5  mov     rcx, [rbx+68h]; pv
0x18004cab9  call    cs:__imp_CoTaskMemFree
0x18004cabf  mov     rcx, [rbx+90h]; pv
0x18004cac6  test    rcx, rcx
0x18004cac9  jz      short loc_18004CAD1
0x18004cacb  call    cs:__imp_CoTaskMemFree
0x18004cad1  mov     rcx, rbx; struct _NAT_CONNECTION_INFO *
0x18004cad4  call    ?NatFreePortMappingList@@YAXPEAU_NAT_CONNECTION_INFO@@@Z; NatFreePortMappingList(_NAT_CONNECTION_INFO *)
0x18004cad9  call    cs:__imp_GetProcessHeap
0x18004cadf  mov     r8, rbx; lpMem
0x18004cae2  xor     edx, edx; dwFlags
0x18004cae4  mov     rcx, rax; hHeap
0x18004cae7  call    cs:__imp_HeapFree
0x18004caed  mov     rcx, cs:WPP_GLOBAL_Control
0x18004caf4  cmp     rcx, rbp
0x18004caf7  jz      short loc_18004CB1D
0x18004caf9  test    dword ptr [rcx+1Ch], 200h
0x18004cb00  jz      short loc_18004CB1D
0x18004cb02  cmp     byte ptr [rcx+19h], 6
0x18004cb06  jb      short loc_18004CB1D
0x18004cb08  mov     rcx, [rcx+10h]
0x18004cb0c  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x18004cb13  mov     edx, 7Bh ; '{'
0x18004cb18  call    WPP_SF_
0x18004cb1d  mov     rbx, [rsp+28h+arg_0]
0x18004cb22  mov     rbp, [rsp+28h+arg_8]
0x18004cb27  add     rsp, 20h
0x18004cb2b  pop     rdi
0x18004cb2c  retn
```
