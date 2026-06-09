# VidMmOpenResourcePoolForProcess(VIDMM_PROCESS *,VIDMM_RESOURCE_POOL * *,void * *)

- ea: `0x1400c9fec`
- end: `0x1400ca20d`
- name: `?VidMmOpenResourcePoolForProcess@@YAJPEAVVIDMM_PROCESS@@PEAPEAUVIDMM_RESOURCE_POOL@@PEAPEAX@Z`
- size: `545`
- prototype: `__int64 __fastcall(struct VIDMM_PROCESS *, struct VIDMM_RESOURCE_POOL **, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140128f3c`

## callees

- `0x1400c9488`
- `0x1400c9588`
- `0x1400c9a50`
- `0x1400c9c3c`
- `0x1400c9fec`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400ca194`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ca1ab`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ca194`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ca1ab`
- `ntoskrnl!ObCloseHandle` at `0x1400ca17d`
- `ntoskrnl!ObCloseHandle` at `0x1400ca1dc`
- `ntoskrnl!ObCloseHandle` at `0x1400ca17d`
- `ntoskrnl!ObCloseHandle` at `0x1400ca1dc`
- `ntoskrnl!PsPartitionType` at `0x1400ca106`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400ca120`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400ca120`
- `watchdog!WdLogSingleEntry1` at `0x1400ca058`
- `watchdog!WdLogSingleEntry1` at `0x1400ca0d2`
- `watchdog!WdLogSingleEntry1` at `0x1400ca13b`
- `watchdog!WdLogSingleEntry1` at `0x1400ca058`
- `watchdog!WdLogSingleEntry1` at `0x1400ca0d2`
- `watchdog!WdLogSingleEntry1` at `0x1400ca13b`

## pseudocode

```c
__int64 __fastcall VidMmOpenResourcePoolForProcess(
        struct VIDMM_PROCESS *a1,
        struct VIDMM_RESOURCE_POOL **a2,
        void **a3)
{
  struct VIDMM_PARTITION *v3; // rdi
  struct VIDMM_PARTITION *v4; // rsi
  int Partition; // ebx
  int v8; // eax
  int ResourcePool; // eax
  NTSTATUS v10; // eax
  __int64 v11; // rax
  PVOID v13; // [rsp+40h] [rbp-40h] BYREF
  struct VIDMM_PARTITION *v14; // [rsp+48h] [rbp-38h]
  HANDLE Handle; // [rsp+50h] [rbp-30h] BYREF
  PVOID Object; // [rsp+58h] [rbp-28h] BYREF
  struct VIDMM_PARTITION *v17; // [rsp+60h] [rbp-20h]
  HANDLE v18; // [rsp+68h] [rbp-18h] BYREF
  struct VIDMM_RESOURCE_POOL *v19; // [rsp+70h] [rbp-10h]
  char v21; // [rsp+C8h] [rbp+48h] BYREF

  v21 = 0;
  v19 = 0;
  v3 = 0;
  v14 = 0;
  v4 = 0;
  v17 = 0;
  Object = 0;
  v13 = 0;
  v18 = 0;
  Handle = 0;
  Partition = ReferenceProcessPartitions(
                (_DWORD)a1,
                (unsigned int)&Object,
                (unsigned int)&v13,
                (unsigned int)&v18,
                (__int64)&v21);
  if ( Partition < 0 )
  {
    WdLogSingleEntry1(3, a1);
    WdLogGlobalForLineNumber = 1589;
    goto LABEL_15;
  }
  Partition = FindOrCreatePartition((struct _EPARTITION *)Object);
  if ( Partition >= 0 )
  {
    if ( !v13 || (v8 = FindOrCreatePartition((struct _EPARTITION *)v13), v4 = v17, Partition = v8, v8 >= 0) )
    {
      v3 = v14;
      ResourcePool = FindOrCreateResourcePool(v14, v4);
      Partition = ResourcePool;
      if ( ResourcePool < 0 )
      {
        WdLogSingleEntry1(3, ResourcePool);
        WdLogGlobalForLineNumber = 1636;
        goto LABEL_15;
      }
      if ( (*((_DWORD *)v3 + 28) & 1) != 0 )
      {
        v10 = ObOpenObjectByPointer(*((PVOID *)v3 + 11), 0, 0, 0x1F0003u, PsPartitionType, 0, &Handle);
        Partition = v10;
        if ( v10 < 0 )
        {
          WdLogSingleEntry1(3, v10);
          WdLogGlobalForLineNumber = 1649;
          goto LABEL_15;
        }
        v11 = (__int64)Handle;
      }
      else
      {
        v11 = -1;
        Handle = (HANDLE)-1LL;
      }
      *a3 = (void *)v11;
      Partition = 0;
      goto LABEL_17;
    }
  }
  v3 = v14;
LABEL_15:
  if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    ObCloseHandle(Handle, 0);
LABEL_17:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( v13 )
    ObfDereferenceObject(v13);
  if ( v3 )
    VidMmDereferencePartition(v3);
  if ( v4 )
    VidMmDereferencePartition(v4);
  if ( v18 )
    ObCloseHandle(v18, 0);
  *a2 = v19;
  return (unsigned int)Partition;
}

```

## disassembly

```asm
0x1400c9fec  mov     [rsp-28h+arg_0], rbx
0x1400c9ff1  mov     [rsp-28h+arg_8], rdx
0x1400c9ff6  push    rbp
0x1400c9ff7  push    rsi
0x1400c9ff8  push    rdi
0x1400c9ff9  push    r12
0x1400c9ffb  push    r13
0x1400c9ffd  mov     rbp, rsp
0x1400ca000  sub     rsp, 80h
0x1400ca007  xor     eax, eax
0x1400ca009  lea     r9, [rbp+var_18]
0x1400ca00d  mov     [rbp+arg_18], al
0x1400ca010  lea     rdx, [rbp+Object]
0x1400ca014  mov     [rbp+var_10], rax
0x1400ca018  mov     edi, eax
0x1400ca01a  mov     [rbp+var_38], rax
0x1400ca01e  mov     esi, eax
0x1400ca020  mov     [rbp+var_20], rax
0x1400ca024  mov     r13, r8
0x1400ca027  mov     [rbp+Object], rax
0x1400ca02b  lea     r8, [rbp+var_40]
0x1400ca02f  mov     [rbp+var_40], rax
0x1400ca033  mov     r12, rcx
0x1400ca036  mov     [rbp+var_18], rax
0x1400ca03a  mov     [rbp+var_30], rax
0x1400ca03e  lea     rax, [rbp+arg_18]
0x1400ca042  mov     [rsp+80h+ObjectType], rax
0x1400ca047  call    ReferenceProcessPartitions
0x1400ca04c  mov     ebx, eax
0x1400ca04e  test    eax, eax
0x1400ca050  jns     short loc_1400CA073
0x1400ca052  mov     rdx, r12
0x1400ca055  lea     ecx, [rsi+3]
0x1400ca058  call    cs:__imp_WdLogSingleEntry1
0x1400ca05f  nop     dword ptr [rax+rax+00h]
0x1400ca064  mov     cs:WdLogGlobalForLineNumber, 635h
0x1400ca06e  jmp     loc_1400CA16D
0x1400ca073  mov     dl, [rbp+arg_18]
0x1400ca076  lea     r8, [rbp+var_38]
0x1400ca07a  mov     rcx, [rbp+Object]; struct _EPARTITION *
0x1400ca07e  call    FindOrCreatePartition
0x1400ca083  mov     ebx, eax
0x1400ca085  test    eax, eax
0x1400ca087  js      loc_1400CA169
0x1400ca08d  cmp     [rbp+var_40], rsi
0x1400ca091  jz      short loc_1400CA0B0
0x1400ca093  mov     rcx, [rbp+var_40]; struct _EPARTITION *
0x1400ca097  lea     r8, [rbp+var_20]
0x1400ca09b  xor     edx, edx
0x1400ca09d  call    FindOrCreatePartition
0x1400ca0a2  mov     rsi, [rbp+var_20]
0x1400ca0a6  mov     ebx, eax
0x1400ca0a8  test    eax, eax
0x1400ca0aa  js      loc_1400CA169
0x1400ca0b0  mov     rdi, [rbp+var_38]
0x1400ca0b4  lea     r8, [rbp+var_10]
0x1400ca0b8  mov     rcx, rdi; struct VIDMM_PARTITION *
0x1400ca0bb  mov     rdx, rsi; struct VIDMM_PARTITION *
0x1400ca0be  call    FindOrCreateResourcePool
0x1400ca0c3  movsxd  rbx, eax
0x1400ca0c6  test    eax, eax
0x1400ca0c8  jns     short loc_1400CA0ED
0x1400ca0ca  mov     rdx, rbx
0x1400ca0cd  mov     ecx, 3
0x1400ca0d2  call    cs:__imp_WdLogSingleEntry1
0x1400ca0d9  nop     dword ptr [rax+rax+00h]
0x1400ca0de  mov     cs:WdLogGlobalForLineNumber, 664h
0x1400ca0e8  jmp     loc_1400CA16D
0x1400ca0ed  mov     eax, [rdi+70h]
0x1400ca0f0  test    al, 1
0x1400ca0f2  jz      short loc_1400CA159
0x1400ca0f4  lea     rax, [rbp+var_30]
0x1400ca0f8  mov     r9d, 1F0003h; DesiredAccess
0x1400ca0fe  mov     [rsp+80h+Handle], rax; Handle
0x1400ca103  xor     r8d, r8d; PassedAccessState
0x1400ca106  mov     rax, cs:__imp_PsPartitionType
0x1400ca10d  xor     edx, edx; HandleAttributes
0x1400ca10f  mov     [rsp+80h+AccessMode], 0; AccessMode
0x1400ca114  mov     rcx, [rax]
0x1400ca117  mov     [rsp+80h+ObjectType], rcx; ObjectType
0x1400ca11c  mov     rcx, [rdi+58h]; Object
0x1400ca120  call    cs:__imp_ObOpenObjectByPointer
0x1400ca127  nop     dword ptr [rax+rax+00h]
0x1400ca12c  movsxd  rbx, eax
0x1400ca12f  test    eax, eax
0x1400ca131  jns     short loc_1400CA153
0x1400ca133  mov     rdx, rbx
0x1400ca136  mov     ecx, 3
0x1400ca13b  call    cs:__imp_WdLogSingleEntry1
0x1400ca142  nop     dword ptr [rax+rax+00h]
0x1400ca147  mov     cs:WdLogGlobalForLineNumber, 671h
0x1400ca151  jmp     short loc_1400CA16D
0x1400ca153  mov     rax, [rbp+var_30]
0x1400ca157  jmp     short loc_1400CA161
0x1400ca159  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400ca15d  mov     [rbp+var_30], rax
0x1400ca161  mov     [r13+0], rax
0x1400ca165  xor     ebx, ebx
0x1400ca167  jmp     short loc_1400CA189
0x1400ca169  mov     rdi, [rbp+var_38]
0x1400ca16d  mov     rcx, [rbp+var_30]; Handle
0x1400ca171  lea     rax, [rcx-1]
0x1400ca175  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400ca179  ja      short loc_1400CA189
0x1400ca17b  xor     edx, edx; PreviousMode
0x1400ca17d  call    cs:__imp_ObCloseHandle
0x1400ca184  nop     dword ptr [rax+rax+00h]
0x1400ca189  cmp     [rbp+Object], 0
0x1400ca18e  jz      short loc_1400CA1A0
0x1400ca190  mov     rcx, [rbp+Object]; Object
0x1400ca194  call    cs:__imp_ObfDereferenceObject
0x1400ca19b  nop     dword ptr [rax+rax+00h]
0x1400ca1a0  cmp     [rbp+var_40], 0
0x1400ca1a5  jz      short loc_1400CA1B7
0x1400ca1a7  mov     rcx, [rbp+var_40]; Object
0x1400ca1ab  call    cs:__imp_ObfDereferenceObject
0x1400ca1b2  nop     dword ptr [rax+rax+00h]
0x1400ca1b7  test    rdi, rdi
0x1400ca1ba  jz      short loc_1400CA1C4
0x1400ca1bc  mov     rcx, rdi; this
0x1400ca1bf  call    ?VidMmDereferencePartition@@YAXPEBUVIDMM_PARTITION@@@Z; VidMmDereferencePartition(VIDMM_PARTITION const *)
0x1400ca1c4  test    rsi, rsi
0x1400ca1c7  jz      short loc_1400CA1D1
0x1400ca1c9  mov     rcx, rsi; this
0x1400ca1cc  call    ?VidMmDereferencePartition@@YAXPEBUVIDMM_PARTITION@@@Z; VidMmDereferencePartition(VIDMM_PARTITION const *)
0x1400ca1d1  mov     rcx, [rbp+var_18]; Handle
0x1400ca1d5  test    rcx, rcx
0x1400ca1d8  jz      short loc_1400CA1E8
0x1400ca1da  xor     edx, edx; PreviousMode
0x1400ca1dc  call    cs:__imp_ObCloseHandle
0x1400ca1e3  nop     dword ptr [rax+rax+00h]
0x1400ca1e8  mov     rax, [rbp+var_10]
0x1400ca1ec  mov     rcx, [rbp+arg_8]
0x1400ca1f0  mov     [rcx], rax
0x1400ca1f3  mov     eax, ebx
0x1400ca1f5  mov     rbx, [rsp+80h+arg_0]
0x1400ca1fd  add     rsp, 80h
0x1400ca204  pop     r13
0x1400ca206  pop     r12
0x1400ca208  pop     rdi
0x1400ca209  pop     rsi
0x1400ca20a  pop     rbp
0x1400ca20b  retn
```
