# VIDMM_PROCESS_HEAP::~VIDMM_PROCESS_HEAP(void)

- ea: `0x1400ade30`
- end: `0x1400ae04b`
- name: `??1VIDMM_PROCESS_HEAP@@UEAA@XZ`
- size: `539`
- prototype: `void __fastcall(VIDMM_PROCESS_HEAP *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14004a270`

## callees

- `0x14003f5a4`
- `0x1400ade30`

## import_xrefs

- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400ae025`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400ae025`
- `watchdog!WdLogSingleEntry5` at `0x1400ade7c`
- `watchdog!WdLogSingleEntry5` at `0x1400adecc`
- `watchdog!WdLogSingleEntry5` at `0x1400adf1b`
- `watchdog!WdLogSingleEntry5` at `0x1400adf6b`
- `watchdog!WdLogSingleEntry5` at `0x1400adfbb`
- `watchdog!WdLogSingleEntry5` at `0x1400ae00b`
- `watchdog!WdLogSingleEntry5` at `0x1400ade7c`
- `watchdog!WdLogSingleEntry5` at `0x1400adecc`
- `watchdog!WdLogSingleEntry5` at `0x1400adf1b`
- `watchdog!WdLogSingleEntry5` at `0x1400adf6b`
- `watchdog!WdLogSingleEntry5` at `0x1400adfbb`
- `watchdog!WdLogSingleEntry5` at `0x1400ae00b`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400ade4f`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400ade9e`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400adeee`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400adf3d`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400adf8d`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400adfdd`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VIDMM_PROCESS_HEAP::~VIDMM_PROCESS_HEAP(VIDMM_PROCESS_HEAP *this)
{
  *(_QWORD *)this = &VIDMM_PROCESS_HEAP::`vftable';
  if ( *((VIDMM_PROCESS_HEAP **)this + 26) != (VIDMM_PROCESS_HEAP *)((char *)this + 208) )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 2);
    WdLogGlobalForLineNumber = 222;
  }
  if ( *((VIDMM_PROCESS_HEAP **)this + 24) != (VIDMM_PROCESS_HEAP *)((char *)this + 192) )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 2);
    WdLogGlobalForLineNumber = 222;
  }
  if ( *((VIDMM_PROCESS_HEAP **)this + 28) != (VIDMM_PROCESS_HEAP *)((char *)this + 224) )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 2);
    WdLogGlobalForLineNumber = 222;
  }
  if ( *((VIDMM_PROCESS_HEAP **)this + 30) != (VIDMM_PROCESS_HEAP *)((char *)this + 240) )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 2);
    WdLogGlobalForLineNumber = 222;
  }
  if ( *((VIDMM_PROCESS_HEAP **)this + 32) != (VIDMM_PROCESS_HEAP *)((char *)this + 256) )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 2);
    WdLogGlobalForLineNumber = 222;
  }
  if ( *((VIDMM_PROCESS_HEAP **)this + 34) != (VIDMM_PROCESS_HEAP *)((char *)this + 272) )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 2);
    WdLogGlobalForLineNumber = 222;
  }
  ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)this + 64));
  DXGFASTMUTEX::~DXGFASTMUTEX((VIDMM_PROCESS_HEAP *)((char *)this + 16));
  *(_QWORD *)this = &VIDMM_HEAP_INTERFACE::`vftable';
}

```

## disassembly

```asm
0x1400ade30  push    rbx
0x1400ade32  sub     rsp, 30h
0x1400ade36  lea     rax, ??_7VIDMM_PROCESS_HEAP@@6B@; const VIDMM_PROCESS_HEAP::`vftable'
0x1400ade3d  mov     rbx, rcx
0x1400ade40  mov     [rcx], rax
0x1400ade43  lea     rax, [rcx+0D0h]
0x1400ade4a  cmp     [rax], rax
0x1400ade4d  jz      short loc_1400ADE92
0x1400ade4f  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400ade56  mov     dword ptr [rax], 1
0x1400ade5c  xor     r9d, r9d
0x1400ade5f  mov     [rsp+38h+var_10], 0
0x1400ade68  mov     edx, 10Eh
0x1400ade6d  mov     [rsp+38h+var_18], 0
0x1400ade76  xor     ecx, ecx
0x1400ade78  lea     r8d, [r9+2]
0x1400ade7c  call    cs:__imp_WdLogSingleEntry5
0x1400ade83  nop     dword ptr [rax+rax+00h]
0x1400ade88  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400ade92  lea     rax, [rcx+0C0h]
0x1400ade99  cmp     [rax], rax
0x1400ade9c  jz      short loc_1400ADEE2
0x1400ade9e  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400adea5  mov     dword ptr [rax], 1
0x1400adeab  xor     ecx, ecx
0x1400adead  mov     [rsp+38h+var_10], 0
0x1400adeb6  mov     edx, 10Eh
0x1400adebb  mov     [rsp+38h+var_18], 0
0x1400adec4  lea     r9d, [rcx+1]
0x1400adec8  lea     r8d, [rcx+2]
0x1400adecc  call    cs:__imp_WdLogSingleEntry5
0x1400aded3  nop     dword ptr [rax+rax+00h]
0x1400aded8  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400adee2  lea     rax, [rcx+0E0h]
0x1400adee9  cmp     [rax], rax
0x1400adeec  jz      short loc_1400ADF31
0x1400adeee  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400adef5  mov     dword ptr [rax], 1
0x1400adefb  xor     ecx, ecx
0x1400adefd  mov     [rsp+38h+var_10], 0
0x1400adf06  mov     edx, 10Eh
0x1400adf0b  mov     [rsp+38h+var_18], 0
0x1400adf14  lea     r9d, [rcx+2]
0x1400adf18  mov     r8d, r9d
0x1400adf1b  call    cs:__imp_WdLogSingleEntry5
0x1400adf22  nop     dword ptr [rax+rax+00h]
0x1400adf27  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400adf31  lea     rax, [rcx+0F0h]
0x1400adf38  cmp     [rax], rax
0x1400adf3b  jz      short loc_1400ADF81
0x1400adf3d  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400adf44  mov     dword ptr [rax], 1
0x1400adf4a  xor     ecx, ecx
0x1400adf4c  mov     [rsp+38h+var_10], 0
0x1400adf55  mov     edx, 10Eh
0x1400adf5a  mov     [rsp+38h+var_18], 0
0x1400adf63  lea     r9d, [rcx+3]
0x1400adf67  lea     r8d, [rcx+2]
0x1400adf6b  call    cs:__imp_WdLogSingleEntry5
0x1400adf72  nop     dword ptr [rax+rax+00h]
0x1400adf77  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400adf81  lea     rax, [rcx+100h]
0x1400adf88  cmp     [rax], rax
0x1400adf8b  jz      short loc_1400ADFD1
0x1400adf8d  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400adf94  mov     dword ptr [rax], 1
0x1400adf9a  xor     ecx, ecx
0x1400adf9c  mov     [rsp+38h+var_10], 0
0x1400adfa5  mov     edx, 10Eh
0x1400adfaa  mov     [rsp+38h+var_18], 0
0x1400adfb3  lea     r9d, [rcx+4]
0x1400adfb7  lea     r8d, [rcx+2]
0x1400adfbb  call    cs:__imp_WdLogSingleEntry5
0x1400adfc2  nop     dword ptr [rax+rax+00h]
0x1400adfc7  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400adfd1  lea     rax, [rcx+110h]
0x1400adfd8  cmp     [rax], rax
0x1400adfdb  jz      short loc_1400AE021
0x1400adfdd  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400adfe4  mov     dword ptr [rax], 1
0x1400adfea  xor     ecx, ecx
0x1400adfec  mov     [rsp+38h+var_10], 0
0x1400adff5  mov     edx, 10Eh
0x1400adffa  mov     [rsp+38h+var_18], 0
0x1400ae003  lea     r9d, [rcx+5]
0x1400ae007  lea     r8d, [rcx+2]
0x1400ae00b  call    cs:__imp_WdLogSingleEntry5
0x1400ae012  nop     dword ptr [rax+rax+00h]
0x1400ae017  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400ae021  add     rcx, 40h ; '@'; Lookaside
0x1400ae025  call    cs:__imp_ExDeletePagedLookasideList
0x1400ae02c  nop     dword ptr [rax+rax+00h]
0x1400ae031  lea     rcx, [rbx+10h]; this
0x1400ae035  call    ??1DXGFASTMUTEX@@QEAA@XZ; DXGFASTMUTEX::~DXGFASTMUTEX(void)
0x1400ae03a  lea     rax, ??_7VIDMM_HEAP_INTERFACE@@6B@; const VIDMM_HEAP_INTERFACE::`vftable'
0x1400ae041  mov     [rbx], rax
0x1400ae044  add     rsp, 30h
0x1400ae048  pop     rbx
0x1400ae049  retn
```
