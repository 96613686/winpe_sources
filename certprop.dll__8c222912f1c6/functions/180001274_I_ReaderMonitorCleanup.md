# I_ReaderMonitorCleanup

- ea: `0x180001274`
- end: `0x180001324`
- name: `I_ReaderMonitorCleanup`
- size: `176`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800010c4`
- `0x180019fa4`

## callees

- `0x180001274`
- `0x180014a04`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000130d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000130d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800012fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800012fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001286`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001295`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800012a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800012b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800012c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800012e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001286`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001295`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800012a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800012b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800012c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800012e8`

## pseudocode

```c
void __fastcall I_ReaderMonitorCleanup(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  _QWORD *v7; // rcx
  void *v8; // rcx
  struct _TP_CLEANUP_GROUP *v9; // rcx

  v2 = *(void **)(a1 + 88);
  if ( v2 )
    CloseHandle(v2);
  v3 = *(void **)(a1 + 96);
  if ( v3 )
    CloseHandle(v3);
  v4 = *(void **)(a1 + 104);
  if ( v4 )
    CloseHandle(v4);
  v5 = *(void **)(a1 + 240);
  if ( v5 )
    CloseHandle(v5);
  v6 = *(void **)(a1 + 248);
  if ( v6 )
    CloseHandle(v6);
  v7 = *(_QWORD **)(a1 + 112);
  if ( v7 )
    I_ReaderListFree(v7);
  v8 = *(void **)(a1 + 224);
  if ( v8 )
    CloseHandle(v8);
  if ( *(_DWORD *)(a1 + 216) )
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v9 = *(struct _TP_CLEANUP_GROUP **)(a1 + 208);
  if ( v9 )
  {
    CloseThreadpoolCleanupGroup(v9);
    *(_QWORD *)(a1 + 208) = 0;
  }
}

```

## disassembly

```asm
0x180001274  push    rbx
0x180001276  sub     rsp, 20h
0x18000127a  mov     rbx, rcx
0x18000127d  mov     rcx, [rcx+58h]; hObject
0x180001281  test    rcx, rcx
0x180001284  jz      short loc_18000128C
0x180001286  call    cs:__imp_CloseHandle
0x18000128c  mov     rcx, [rbx+60h]; hObject
0x180001290  test    rcx, rcx
0x180001293  jz      short loc_18000129B
0x180001295  call    cs:__imp_CloseHandle
0x18000129b  mov     rcx, [rbx+68h]; hObject
0x18000129f  test    rcx, rcx
0x1800012a2  jz      short loc_1800012AA
0x1800012a4  call    cs:__imp_CloseHandle
0x1800012aa  mov     rcx, [rbx+0F0h]; hObject
0x1800012b1  test    rcx, rcx
0x1800012b4  jz      short loc_1800012BC
0x1800012b6  call    cs:__imp_CloseHandle
0x1800012bc  mov     rcx, [rbx+0F8h]; hObject
0x1800012c3  test    rcx, rcx
0x1800012c6  jz      short loc_1800012CE
0x1800012c8  call    cs:__imp_CloseHandle
0x1800012ce  mov     rcx, [rbx+70h]
0x1800012d2  test    rcx, rcx
0x1800012d5  jz      short loc_1800012DC
0x1800012d7  call    I_ReaderListFree
0x1800012dc  mov     rcx, [rbx+0E0h]; hObject
0x1800012e3  test    rcx, rcx
0x1800012e6  jz      short loc_1800012EE
0x1800012e8  call    cs:__imp_CloseHandle
0x1800012ee  cmp     dword ptr [rbx+0D8h], 0
0x1800012f5  jz      short loc_180001301
0x1800012f7  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800012fb  call    cs:__imp_DeleteCriticalSection
0x180001301  mov     rcx, [rbx+0D0h]; ptpcg
0x180001308  test    rcx, rcx
0x18000130b  jz      short loc_18000131E
0x18000130d  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180001313  mov     qword ptr [rbx+0D0h], 0
0x18000131e  add     rsp, 20h
0x180001322  pop     rbx
0x180001323  retn
```
