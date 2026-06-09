# CfpGetSyncRootInfoByPath

- ea: `0x18001035c`
- end: `0x1800103fb`
- name: `CfpGetSyncRootInfoByPath`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800101a0`
- `0x180012c28`

## callees

- `0x1800046bc`
- `0x180010294`
- `0x18001035c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180010398`
- `ntdll!RtlNtStatusToDosError` at `0x180010398`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103e3`

## pseudocode

```c
__int64 __fastcall CfpGetSyncRootInfoByPath(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  NTSTATUS v5; // eax
  signed int v6; // eax
  signed int SyncRootInfoByHandle; // ebx
  __int64 v9; // [rsp+20h] [rbp-68h]
  __int64 v10; // [rsp+30h] [rbp-58h]
  HANDLE hObject; // [rsp+50h] [rbp-38h] BYREF

  hObject = (HANDLE)-1LL;
  v5 = CfpCreateFile(a1, a2, 0, 7u, v9, 0x20u, v10, &hObject);
  v6 = RtlNtStatusToDosError(v5);
  SyncRootInfoByHandle = v6;
  if ( v6 > 0 )
    SyncRootInfoByHandle = (unsigned __int16)v6 | 0x80070000;
  if ( SyncRootInfoByHandle >= 0 )
    SyncRootInfoByHandle = CfpGetSyncRootInfoByHandle(hObject, a5);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return (unsigned int)SyncRootInfoByHandle;
}

```

## disassembly

```asm
0x18001035c  push    rbx
0x18001035e  push    rbp
0x18001035f  push    rsi
0x180010360  push    rdi
0x180010361  sub     rsp, 68h
0x180010365  lea     rax, [rsp+88h+hObject]
0x18001036a  mov     [rsp+88h+hObject], 0FFFFFFFFFFFFFFFFh
0x180010373  mov     edi, r9d
0x180010376  mov     [rsp+88h+var_50], rax
0x18001037b  mov     rsi, r8
0x18001037e  mov     [rsp+88h+var_60], 20h ; ' '
0x180010386  mov     r9d, 7
0x18001038c  xor     r8d, r8d
0x18001038f  mov     ebp, edx
0x180010391  call    CfpCreateFile
0x180010396  mov     ecx, eax; Status
0x180010398  call    cs:__imp_RtlNtStatusToDosError
0x18001039f  nop     dword ptr [rax+rax+00h]
0x1800103a4  mov     ebx, eax
0x1800103a6  test    eax, eax
0x1800103a8  jle     short loc_1800103B3
0x1800103aa  movzx   ebx, ax
0x1800103ad  or      ebx, 80070000h
0x1800103b3  test    ebx, ebx
0x1800103b5  js      short loc_1800103D8
0x1800103b7  mov     rax, [rsp+88h+arg_20]
0x1800103bf  mov     r9d, edi
0x1800103c2  mov     rcx, [rsp+88h+hObject]; hFile
0x1800103c7  mov     r8, rsi
0x1800103ca  mov     edx, ebp
0x1800103cc  mov     [rsp+88h+var_68], rax; __int64
0x1800103d1  call    CfpGetSyncRootInfoByHandle
0x1800103d6  mov     ebx, eax
0x1800103d8  mov     rcx, [rsp+88h+hObject]; hObject
0x1800103dd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800103e1  jz      short loc_1800103EF
0x1800103e3  call    cs:__imp_CloseHandle
0x1800103ea  nop     dword ptr [rax+rax+00h]
0x1800103ef  mov     eax, ebx
0x1800103f1  add     rsp, 68h
0x1800103f5  pop     rdi
0x1800103f6  pop     rsi
0x1800103f7  pop     rbp
0x1800103f8  pop     rbx
0x1800103f9  retn
```
