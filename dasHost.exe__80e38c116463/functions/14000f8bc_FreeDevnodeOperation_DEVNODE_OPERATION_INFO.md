# FreeDevnodeOperation(_DEVNODE_OPERATION_INFO *)

- ea: `0x14000f8bc`
- end: `0x14000f95e`
- name: `?FreeDevnodeOperation@@YAXPEAU_DEVNODE_OPERATION_INFO@@@Z`
- size: `162`
- prototype: `void __fastcall(struct _DEVNODE_OPERATION_INFO *lpMem)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e6a0`
- `0x14000e780`
- `0x14000e9a0`
- `0x14000ea90`
- `0x14000f2c8`
- `0x14000fd20`

## callees

- `0x140009090`
- `0x14000f8bc`
- `0x14001a068`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f952`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f952`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f944`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f944`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f936`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f936`

## pseudocode

```c
void __fastcall FreeDevnodeOperation(struct _DEVNODE_OPERATION_INFO *lpMem)
{
  struct _DEVPROPERTY *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  HANDLE ProcessHeap; // rax

  if ( lpMem )
  {
    v2 = (struct _DEVPROPERTY *)*((_QWORD *)lpMem + 1);
    if ( v2 )
    {
      MidlFreeDevProperties(v2, *(_DWORD *)lpMem);
      *((_QWORD *)lpMem + 1) = 0;
      *(_DWORD *)lpMem = 0;
    }
    v3 = (void *)*((_QWORD *)lpMem + 4);
    if ( v3 )
    {
      MIDL_user_free(v3);
      *((_QWORD *)lpMem + 4) = 0;
    }
    v4 = (void *)*((_QWORD *)lpMem + 5);
    if ( v4 )
    {
      MIDL_user_free(v4);
      *((_QWORD *)lpMem + 5) = 0;
    }
    v5 = (void *)*((_QWORD *)lpMem + 6);
    if ( v5 )
    {
      MIDL_user_free(v5);
      *((_QWORD *)lpMem + 6) = 0;
    }
    v6 = (void *)*((_QWORD *)lpMem + 8);
    if ( v6 )
    {
      CloseHandle(v6);
      *((_QWORD *)lpMem + 8) = 0;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x14000f8bc  test    rcx, rcx
0x14000f8bf  jz      locret_14000F95D
0x14000f8c5  push    rbx
0x14000f8c6  sub     rsp, 20h
0x14000f8ca  mov     rbx, rcx
0x14000f8cd  mov     rcx, [rcx+8]; struct _DEVPROPERTY *
0x14000f8d1  test    rcx, rcx
0x14000f8d4  jz      short loc_14000F8EB
0x14000f8d6  mov     edx, [rbx]; unsigned int
0x14000f8d8  call    ?MidlFreeDevProperties@@YAXPEAU_DEVPROPERTY@@K@Z; MidlFreeDevProperties(_DEVPROPERTY *,ulong)
0x14000f8dd  mov     qword ptr [rbx+8], 0
0x14000f8e5  mov     dword ptr [rbx], 0
0x14000f8eb  mov     rcx, [rbx+20h]; void *
0x14000f8ef  test    rcx, rcx
0x14000f8f2  jz      short loc_14000F901
0x14000f8f4  call    MIDL_user_free
0x14000f8f9  mov     qword ptr [rbx+20h], 0
0x14000f901  mov     rcx, [rbx+28h]; void *
0x14000f905  test    rcx, rcx
0x14000f908  jz      short loc_14000F917
0x14000f90a  call    MIDL_user_free
0x14000f90f  mov     qword ptr [rbx+28h], 0
0x14000f917  mov     rcx, [rbx+30h]; void *
0x14000f91b  test    rcx, rcx
0x14000f91e  jz      short loc_14000F92D
0x14000f920  call    MIDL_user_free
0x14000f925  mov     qword ptr [rbx+30h], 0
0x14000f92d  mov     rcx, [rbx+40h]; hObject
0x14000f931  test    rcx, rcx
0x14000f934  jz      short loc_14000F944
0x14000f936  call    cs:__imp_CloseHandle
0x14000f93c  mov     qword ptr [rbx+40h], 0
0x14000f944  call    cs:__imp_GetProcessHeap
0x14000f94a  mov     r8, rbx; lpMem
0x14000f94d  xor     edx, edx; dwFlags
0x14000f94f  mov     rcx, rax; hHeap
0x14000f952  call    cs:__imp_HeapFree
0x14000f958  add     rsp, 20h
0x14000f95c  pop     rbx
0x14000f95d  retn
```
