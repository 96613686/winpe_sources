# PuDbgPrintError

- ea: `0x1800025bc`
- end: `0x180002782`
- name: `PuDbgPrintError`
- size: `454`
- prototype: `__int64 __fastcall(struct _DEBUG_PRINTS *, char *, unsigned int, char *, DWORD dwMessageId, char *, char)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001a90`

## callees

- `0x180002154`
- `0x1800022ac`
- `0x1800025bc`
- `0x180002a54`
- `0x180002be0`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x1800026af`
- `msvcrt!_snprintf_s` at `0x1800026af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000273e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000273e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002616`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002735`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002735`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x180002685`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x180002685`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000275b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000275b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000274b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000274b`

## pseudocode

```c
void __fastcall PuDbgPrintError(
        struct _DEBUG_PRINTS *a1,
        char *a2,
        int a3,
        char *a4,
        DWORD dwMessageId,
        char *a6,
        char a7)
{
  DWORD LastError; // r15d
  __int64 v12; // rbx
  size_t v13; // r8
  HANDLE ProcessHeap; // rax
  bool lpBuffer; // [rsp+20h] [rbp-E0h]
  bool lpBuffera; // [rsp+20h] [rbp-E0h]
  CHAR Buffer[8]; // [rsp+40h] [rbp-C0h] BYREF
  char *v18; // [rsp+48h] [rbp-B8h] BYREF
  char *v19[4]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-90h]
  int v21; // [rsp+78h] [rbp-88h]
  __int16 v22; // [rsp+7Ch] [rbp-84h]
  unsigned int v23; // [rsp+80h] [rbp-80h]
  char v24[64]; // [rsp+90h] [rbp-70h] BYREF
  char v25; // [rsp+D0h] [rbp-30h] BYREF

  v21 = 256;
  lpMem = &v25;
  v23 = 0;
  v25 = 0;
  v22 = 256;
  LastError = GetLastError();
  v18 = &a7;
  FormatMsgToBuffer(v19, a1, a2, a3, a4, a6, &v18);
  *(_QWORD *)Buffer = 0;
  FormatMessageA(0x1100u, 0, dwMessageId, 0, Buffer, 0, 0);
  if ( *(_QWORD *)Buffer )
  {
    _snprintf_s(v24, 0x40u, 0x3Fu, "\tError(%x): ", dwMessageId);
    v12 = -1;
    v24[63] = 0;
    v13 = -1;
    do
      ++v13;
    while ( v24[v13] );
    STRA::AuxAppend((STRA *)v19, (const unsigned __int8 *)v24, v13, v23, lpBuffer);
    if ( *(_QWORD *)Buffer )
    {
      do
        ++v12;
      while ( *(_BYTE *)(*(_QWORD *)Buffer + v12) );
      STRA::AuxAppend((STRA *)v19, *(const unsigned __int8 **)Buffer, (unsigned int)v12, v23, lpBuffera);
    }
    STRA::AuxAppend((STRA *)v19, "\n", 1u, v23, lpBuffera);
  }
  PupOutputMessage(a1, (struct STRA *)v19);
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  SetLastError(LastError);
  if ( (_BYTE)v22 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x1800025bc  push    rbp
0x1800025be  push    rbx
0x1800025bf  push    rsi
0x1800025c0  push    rdi
0x1800025c1  push    r12
0x1800025c3  push    r14
0x1800025c5  push    r15
0x1800025c7  lea     rbp, [rsp-0E0h]
0x1800025cf  sub     rsp, 1E0h
0x1800025d6  mov     rax, cs:__security_cookie
0x1800025dd  xor     rax, rsp
0x1800025e0  mov     [rbp+110h+var_40], rax
0x1800025e7  lea     rax, [rbp+110h+var_140]
0x1800025eb  mov     [rsp+210h+var_198], 100h
0x1800025f3  xor     r12d, r12d
0x1800025f6  mov     [rsp+210h+lpMem], rax
0x1800025fb  mov     [rbp+110h+var_190], r12d
0x1800025ff  mov     rsi, r9
0x180002602  mov     [rbp+110h+var_140], r12b
0x180002606  mov     edi, r8d
0x180002609  mov     rbx, rdx
0x18000260c  mov     [rsp+210h+var_194], 100h
0x180002613  mov     r14, rcx
0x180002616  call    cs:__imp_GetLastError
0x18000261c  mov     rcx, [rbp+110h+arg_28]
0x180002623  mov     r9d, edi; unsigned int
0x180002626  mov     r15d, eax
0x180002629  mov     r8, rbx; char *
0x18000262c  lea     rax, [rbp+110h+arg_30]
0x180002633  mov     rdx, r14; struct _DEBUG_PRINTS *
0x180002636  mov     [rsp+210h+var_1C8], rax
0x18000263b  lea     rax, [rsp+210h+var_1C8]
0x180002640  mov     [rsp+210h+Arguments], rax; char **
0x180002645  mov     qword ptr [rsp+210h+nSize], rcx; char *
0x18000264a  lea     rcx, [rsp+210h+var_1C0]; this
0x18000264f  mov     [rsp+210h+lpBuffer], rsi; char *
0x180002654  call    ?FormatMsgToBuffer@@YAXPEAVSTRA@@PEAU_DEBUG_PRINTS@@PEBDK22PEAPEAD@Z; FormatMsgToBuffer(STRA *,_DEBUG_PRINTS *,char const *,ulong,char const *,char const *,char * *)
0x180002659  mov     ebx, [rbp+110h+dwMessageId]
0x18000265f  lea     rax, [rsp+210h+Buffer]
0x180002664  mov     [rsp+210h+Arguments], r12; Arguments
0x180002669  xor     r9d, r9d; dwLanguageId
0x18000266c  mov     [rsp+210h+nSize], r12d; nSize
0x180002671  mov     r8d, ebx; dwMessageId
0x180002674  xor     edx, edx; lpSource
0x180002676  mov     [rsp+210h+lpBuffer], rax; lpBuffer
0x18000267b  mov     ecx, 1100h; dwFlags
0x180002680  mov     qword ptr [rsp+210h+Buffer], r12
0x180002685  call    cs:__imp_FormatMessageA
0x18000268b  cmp     qword ptr [rsp+210h+Buffer], r12
0x180002690  jz      loc_18000271E
0x180002696  lea     r9, aErrorX; "\tError(%x): "
0x18000269d  mov     dword ptr [rsp+210h+lpBuffer], ebx; bool
0x1800026a1  lea     edx, [r12+40h]; BufferCount
0x1800026a6  lea     r8d, [r12+3Fh]; MaxCount
0x1800026ab  lea     rcx, [rbp+110h+var_180]; Buffer
0x1800026af  call    cs:__imp__snprintf_s
0x1800026b5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800026b9  mov     [rbp+110h+var_141], r12b
0x1800026bd  mov     r8, rbx
0x1800026c0  lea     rax, [rbp+110h+var_180]
0x1800026c4  inc     r8; Size
0x1800026c7  cmp     [rax+r8], r12b
0x1800026cb  jnz     short loc_1800026C4
0x1800026cd  mov     r9d, [rbp+110h+var_190]; unsigned int
0x1800026d1  lea     rdx, [rbp+110h+var_180]; Src
0x1800026d5  lea     rcx, [rsp+210h+var_1C0]; this
0x1800026da  call    ?AuxAppend@STRA@@AEAAJPEBEKK_N@Z; STRA::AuxAppend(uchar const *,ulong,ulong,bool)
0x1800026df  mov     rdx, qword ptr [rsp+210h+Buffer]; Src
0x1800026e4  test    rdx, rdx
0x1800026e7  jz      short loc_180002703
0x1800026e9  inc     rbx
0x1800026ec  cmp     [rdx+rbx], r12b
0x1800026f0  jnz     short loc_1800026E9
0x1800026f2  mov     r9d, [rbp+110h+var_190]; unsigned int
0x1800026f6  lea     rcx, [rsp+210h+var_1C0]; this
0x1800026fb  mov     r8d, ebx; Size
0x1800026fe  call    ?AuxAppend@STRA@@AEAAJPEBEKK_N@Z; STRA::AuxAppend(uchar const *,ulong,ulong,bool)
0x180002703  mov     r9d, [rbp+110h+var_190]; unsigned int
0x180002707  lea     rdx, asc_1800048C0; "\n"
0x18000270e  mov     r8d, 1; Size
0x180002714  lea     rcx, [rsp+210h+var_1C0]; this
0x180002719  call    ?AuxAppend@STRA@@AEAAJPEBEKK_N@Z; STRA::AuxAppend(uchar const *,ulong,ulong,bool)
0x18000271e  lea     rdx, [rsp+210h+var_1C0]; struct STRA *
0x180002723  mov     rcx, r14; struct _DEBUG_PRINTS *
0x180002726  call    ?PupOutputMessage@@YAXPEAU_DEBUG_PRINTS@@PEAVSTRA@@@Z; PupOutputMessage(_DEBUG_PRINTS *,STRA *)
0x18000272b  mov     rcx, qword ptr [rsp+210h+Buffer]; hMem
0x180002730  test    rcx, rcx
0x180002733  jz      short loc_18000273B
0x180002735  call    cs:__imp_LocalFree
0x18000273b  mov     ecx, r15d; dwErrCode
0x18000273e  call    cs:__imp_SetLastError
0x180002744  cmp     byte ptr [rsp+210h+var_194], r12b
0x180002749  jz      short loc_180002761
0x18000274b  call    cs:__imp_GetProcessHeap
0x180002751  mov     r8, [rsp+210h+lpMem]; lpMem
0x180002756  xor     edx, edx; dwFlags
0x180002758  mov     rcx, rax; hHeap
0x18000275b  call    cs:__imp_HeapFree
0x180002761  mov     rcx, [rbp+110h+var_40]
0x180002768  xor     rcx, rsp; StackCookie
0x18000276b  call    __security_check_cookie
0x180002770  add     rsp, 1E0h
0x180002777  pop     r15
0x180002779  pop     r14
0x18000277b  pop     r12
0x18000277d  pop     rdi
0x18000277e  pop     rsi
0x18000277f  pop     rbx
0x180002780  pop     rbp
0x180002781  retn
```
