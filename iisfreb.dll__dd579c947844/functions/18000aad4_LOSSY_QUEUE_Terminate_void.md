# LOSSY_QUEUE::Terminate(void)

- ea: `0x18000aad4`
- end: `0x18000ab63`
- name: `?Terminate@LOSSY_QUEUE@@QEAAJXZ`
- size: `143`
- prototype: `__int64 __fastcall(LOSSY_QUEUE *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008424`
- `0x180008958`

## callees

- `0x180001048`
- `0x18000aad4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000aae5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000aae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aaf4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aaf4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab0b`

## pseudocode

```c
__int64 __fastcall LOSSY_QUEUE::Terminate(LOSSY_QUEUE *this)
{
  _QWORD *v1; // rbx
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  v1 = FREB_LOG_FILE_MANAGER::sm_pLossyQueue;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)FREB_LOG_FILE_MANAGER::sm_pLossyQueue + 32));
  v2 = (void *)v1[9];
  if ( v2 )
  {
    CloseHandle(v2);
    v1[9] = 0;
  }
  v3 = (void *)v1[10];
  if ( v3 )
  {
    CloseHandle(v3);
    v1[10] = 0;
  }
  v4 = (void *)v1[1];
  if ( v4 )
  {
    operator delete(v4);
    v1[1] = 0;
  }
  v5 = (void *)v1[2];
  if ( v5 )
  {
    operator delete(v5);
    v1[2] = 0;
  }
  v6 = (void *)v1[3];
  if ( v6 )
  {
    operator delete(v6);
    v1[3] = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000aad4  push    rbx
0x18000aad6  sub     rsp, 20h
0x18000aada  mov     rbx, cs:?sm_pLossyQueue@FREB_LOG_FILE_MANAGER@@0PEAVLOSSY_QUEUE@@EA; LOSSY_QUEUE * FREB_LOG_FILE_MANAGER::sm_pLossyQueue
0x18000aae1  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000aae5  call    cs:__imp_DeleteCriticalSection
0x18000aaeb  mov     rcx, [rbx+48h]; hObject
0x18000aaef  test    rcx, rcx
0x18000aaf2  jz      short loc_18000AB02
0x18000aaf4  call    cs:__imp_CloseHandle
0x18000aafa  mov     qword ptr [rbx+48h], 0
0x18000ab02  mov     rcx, [rbx+50h]; hObject
0x18000ab06  test    rcx, rcx
0x18000ab09  jz      short loc_18000AB19
0x18000ab0b  call    cs:__imp_CloseHandle
0x18000ab11  mov     qword ptr [rbx+50h], 0
0x18000ab19  mov     rcx, [rbx+8]; Block
0x18000ab1d  test    rcx, rcx
0x18000ab20  jz      short loc_18000AB2F
0x18000ab22  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ab27  mov     qword ptr [rbx+8], 0
0x18000ab2f  mov     rcx, [rbx+10h]; Block
0x18000ab33  test    rcx, rcx
0x18000ab36  jz      short loc_18000AB45
0x18000ab38  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ab3d  mov     qword ptr [rbx+10h], 0
0x18000ab45  mov     rcx, [rbx+18h]; Block
0x18000ab49  test    rcx, rcx
0x18000ab4c  jz      short loc_18000AB5B
0x18000ab4e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ab53  mov     qword ptr [rbx+18h], 0
0x18000ab5b  xor     eax, eax
0x18000ab5d  add     rsp, 20h
0x18000ab61  pop     rbx
0x18000ab62  retn
```
