# PuDbgPrintError

- ea: `0x180002714`
- end: `0x180002905`
- name: `PuDbgPrintError`
- size: `497`
- prototype: `__int64 __fastcall(struct _DEBUG_PRINTS *, char *, unsigned int, char *, DWORD dwMessageId, char *, char)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001ab0`

## callees

- `0x180002224`
- `0x1800023a8`
- `0x180002714`
- `0x180002c48`
- `0x180002de0`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x180002813`
- `msvcrt!_snprintf_s` at `0x180002813`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800028ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800028ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000276e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000276e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000289f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000289f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x1800027e3`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x1800027e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800028d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800028d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800028c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800028c1`

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
0x180002714  push    rbp
0x180002716  push    rbx
0x180002717  push    rsi
0x180002718  push    rdi
0x180002719  push    r12
0x18000271b  push    r14
0x18000271d  push    r15
0x18000271f  lea     rbp, [rsp-0E0h]
0x180002727  sub     rsp, 1E0h
0x18000272e  mov     rax, cs:__security_cookie
0x180002735  xor     rax, rsp
0x180002738  mov     [rbp+110h+var_40], rax
0x18000273f  lea     rax, [rbp+110h+var_140]
0x180002743  mov     [rsp+210h+var_198], 100h
0x18000274b  xor     r12d, r12d
0x18000274e  mov     [rsp+210h+lpMem], rax
0x180002753  mov     [rbp+110h+var_190], r12d
0x180002757  mov     rsi, r9
0x18000275a  mov     [rbp+110h+var_140], r12b
0x18000275e  mov     edi, r8d
0x180002761  mov     rbx, rdx
0x180002764  mov     [rsp+210h+var_194], 100h
0x18000276b  mov     r14, rcx
0x18000276e  call    cs:__imp_GetLastError
0x180002775  nop     dword ptr [rax+rax+00h]
0x18000277a  mov     rcx, [rbp+110h+arg_28]
0x180002781  mov     r9d, edi; unsigned int
0x180002784  mov     r15d, eax
0x180002787  mov     r8, rbx; char *
0x18000278a  lea     rax, [rbp+110h+arg_30]
0x180002791  mov     rdx, r14; struct _DEBUG_PRINTS *
0x180002794  mov     [rsp+210h+var_1C8], rax
0x180002799  lea     rax, [rsp+210h+var_1C8]
0x18000279e  mov     [rsp+210h+Arguments], rax; char **
0x1800027a3  mov     qword ptr [rsp+210h+nSize], rcx; char *
0x1800027a8  lea     rcx, [rsp+210h+var_1C0]; this
0x1800027ad  mov     [rsp+210h+lpBuffer], rsi; char *
0x1800027b2  call    ?FormatMsgToBuffer@@YAXPEAVSTRA@@PEAU_DEBUG_PRINTS@@PEBDK22PEAPEAD@Z; FormatMsgToBuffer(STRA *,_DEBUG_PRINTS *,char const *,ulong,char const *,char const *,char * *)
0x1800027b7  mov     ebx, [rbp+110h+dwMessageId]
0x1800027bd  lea     rax, [rsp+210h+Buffer]
0x1800027c2  mov     [rsp+210h+Arguments], r12; Arguments
0x1800027c7  xor     r9d, r9d; dwLanguageId
0x1800027ca  mov     [rsp+210h+nSize], r12d; nSize
0x1800027cf  mov     r8d, ebx; dwMessageId
0x1800027d2  xor     edx, edx; lpSource
0x1800027d4  mov     [rsp+210h+lpBuffer], rax; lpBuffer
0x1800027d9  mov     ecx, 1100h; dwFlags
0x1800027de  mov     qword ptr [rsp+210h+Buffer], r12
0x1800027e3  call    cs:__imp_FormatMessageA
0x1800027ea  nop     dword ptr [rax+rax+00h]
0x1800027ef  cmp     qword ptr [rsp+210h+Buffer], r12
0x1800027f4  jz      loc_180002888
0x1800027fa  lea     r9, aErrorX; "\tError(%x): "
0x180002801  mov     dword ptr [rsp+210h+lpBuffer], ebx; bool
0x180002805  lea     edx, [r12+40h]; BufferCount
0x18000280a  lea     r8d, [r12+3Fh]; MaxCount
0x18000280f  lea     rcx, [rbp+110h+var_180]; Buffer
0x180002813  call    cs:__imp__snprintf_s
0x18000281a  nop     dword ptr [rax+rax+00h]
0x18000281f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002823  mov     [rbp+110h+var_141], r12b
0x180002827  mov     r8, rbx
0x18000282a  lea     rax, [rbp+110h+var_180]
0x18000282e  inc     r8; Size
0x180002831  cmp     [rax+r8], r12b
0x180002835  jnz     short loc_18000282E
0x180002837  mov     r9d, [rbp+110h+var_190]; unsigned int
0x18000283b  lea     rdx, [rbp+110h+var_180]; Src
0x18000283f  lea     rcx, [rsp+210h+var_1C0]; this
0x180002844  call    ?AuxAppend@STRA@@AEAAJPEBEKK_N@Z; STRA::AuxAppend(uchar const *,ulong,ulong,bool)
0x180002849  mov     rdx, qword ptr [rsp+210h+Buffer]; Src
0x18000284e  test    rdx, rdx
0x180002851  jz      short loc_18000286D
0x180002853  inc     rbx
0x180002856  cmp     [rdx+rbx], r12b
0x18000285a  jnz     short loc_180002853
0x18000285c  mov     r9d, [rbp+110h+var_190]; unsigned int
0x180002860  lea     rcx, [rsp+210h+var_1C0]; this
0x180002865  mov     r8d, ebx; Size
0x180002868  call    ?AuxAppend@STRA@@AEAAJPEBEKK_N@Z; STRA::AuxAppend(uchar const *,ulong,ulong,bool)
0x18000286d  mov     r9d, [rbp+110h+var_190]; unsigned int
0x180002871  lea     rdx, asc_1800058C0; "\n"
0x180002878  mov     r8d, 1; Size
0x18000287e  lea     rcx, [rsp+210h+var_1C0]; this
0x180002883  call    ?AuxAppend@STRA@@AEAAJPEBEKK_N@Z; STRA::AuxAppend(uchar const *,ulong,ulong,bool)
0x180002888  lea     rdx, [rsp+210h+var_1C0]; struct STRA *
0x18000288d  mov     rcx, r14; struct _DEBUG_PRINTS *
0x180002890  call    ?PupOutputMessage@@YAXPEAU_DEBUG_PRINTS@@PEAVSTRA@@@Z; PupOutputMessage(_DEBUG_PRINTS *,STRA *)
0x180002895  mov     rcx, qword ptr [rsp+210h+Buffer]; hMem
0x18000289a  test    rcx, rcx
0x18000289d  jz      short loc_1800028AB
0x18000289f  call    cs:__imp_LocalFree
0x1800028a6  nop     dword ptr [rax+rax+00h]
0x1800028ab  mov     ecx, r15d; dwErrCode
0x1800028ae  call    cs:__imp_SetLastError
0x1800028b5  nop     dword ptr [rax+rax+00h]
0x1800028ba  cmp     byte ptr [rsp+210h+var_194], r12b
0x1800028bf  jz      short loc_1800028E3
0x1800028c1  call    cs:__imp_GetProcessHeap
0x1800028c8  nop     dword ptr [rax+rax+00h]
0x1800028cd  mov     r8, [rsp+210h+lpMem]; lpMem
0x1800028d2  xor     edx, edx; dwFlags
0x1800028d4  mov     rcx, rax; hHeap
0x1800028d7  call    cs:__imp_HeapFree
0x1800028de  nop     dword ptr [rax+rax+00h]
0x1800028e3  mov     rcx, [rbp+110h+var_40]
0x1800028ea  xor     rcx, rsp; StackCookie
0x1800028ed  call    __security_check_cookie
0x1800028f2  add     rsp, 1E0h
0x1800028f9  pop     r15
0x1800028fb  pop     r14
0x1800028fd  pop     r12
0x1800028ff  pop     rdi
0x180002900  pop     rsi
0x180002901  pop     rbx
0x180002902  pop     rbp
0x180002903  retn
```
