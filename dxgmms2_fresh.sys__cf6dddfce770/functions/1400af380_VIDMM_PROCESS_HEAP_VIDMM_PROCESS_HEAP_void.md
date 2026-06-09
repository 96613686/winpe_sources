# VIDMM_PROCESS_HEAP::~VIDMM_PROCESS_HEAP(void)

- ea: `0x1400af380`
- end: `0x1400af59b`
- name: `??1VIDMM_PROCESS_HEAP@@UEAA@XZ`
- size: `539`
- prototype: `void __fastcall(VIDMM_PROCESS_HEAP *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14004a980`

## callees

- `0x14003df20`
- `0x1400af380`

## import_xrefs

- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400af575`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400af575`
- `watchdog!WdLogSingleEntry5` at `0x1400af3cc`
- `watchdog!WdLogSingleEntry5` at `0x1400af41c`
- `watchdog!WdLogSingleEntry5` at `0x1400af46b`
- `watchdog!WdLogSingleEntry5` at `0x1400af4bb`
- `watchdog!WdLogSingleEntry5` at `0x1400af50b`
- `watchdog!WdLogSingleEntry5` at `0x1400af55b`
- `watchdog!WdLogSingleEntry5` at `0x1400af3cc`
- `watchdog!WdLogSingleEntry5` at `0x1400af41c`
- `watchdog!WdLogSingleEntry5` at `0x1400af46b`
- `watchdog!WdLogSingleEntry5` at `0x1400af4bb`
- `watchdog!WdLogSingleEntry5` at `0x1400af50b`
- `watchdog!WdLogSingleEntry5` at `0x1400af55b`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400af39f`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400af3ee`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400af43e`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400af48d`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400af4dd`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400af52d`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VIDMM_PROCESS_HEAP::~VIDMM_PROCESS_HEAP(VIDMM_PROCESS_HEAP *this)
{
  *(_QWORD *)this = &VIDMM_PROCESS_HEAP::`vftable';
  if ( *((VIDMM_PROCESS_HEAP **)this + 26) != (VIDMM_PROCESS_HEAP *)((char *)this + 208) )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 2, 0, 0, 0);
    WdLogGlobalForLineNumber = 227;
  }
  if ( *((VIDMM_PROCESS_HEAP **)this + 24) != (VIDMM_PROCESS_HEAP *)((char *)this + 192) )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 2, 1, 0, 0);
    WdLogGlobalForLineNumber = 227;
  }
  if ( *((VIDMM_PROCESS_HEAP **)this + 28) != (VIDMM_PROCESS_HEAP *)((char *)this + 224) )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 2, 2, 0, 0);
    WdLogGlobalForLineNumber = 227;
  }
  if ( *((VIDMM_PROCESS_HEAP **)this + 30) != (VIDMM_PROCESS_HEAP *)((char *)this + 240) )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 2, 3, 0, 0);
    WdLogGlobalForLineNumber = 227;
  }
  if ( *((VIDMM_PROCESS_HEAP **)this + 32) != (VIDMM_PROCESS_HEAP *)((char *)this + 256) )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 2, 4, 0, 0);
    WdLogGlobalForLineNumber = 227;
  }
  if ( *((VIDMM_PROCESS_HEAP **)this + 34) != (VIDMM_PROCESS_HEAP *)((char *)this + 272) )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 2, 5, 0, 0);
    WdLogGlobalForLineNumber = 227;
  }
  ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)this + 64));
  DXGFASTMUTEX::~DXGFASTMUTEX((VIDMM_PROCESS_HEAP *)((char *)this + 16));
  *(_QWORD *)this = &VIDMM_HEAP_INTERFACE::`vftable';
}

```

## disassembly

```asm
0x1400af380  push    rbx
0x1400af382  sub     rsp, 30h
0x1400af386  lea     rax, ??_7VIDMM_PROCESS_HEAP@@6B@; const VIDMM_PROCESS_HEAP::`vftable'
0x1400af38d  mov     rbx, rcx
0x1400af390  mov     [rcx], rax
0x1400af393  lea     rax, [rcx+0D0h]
0x1400af39a  cmp     [rax], rax
0x1400af39d  jz      short loc_1400AF3E2
0x1400af39f  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400af3a6  mov     dword ptr [rax], 1
0x1400af3ac  xor     r9d, r9d
0x1400af3af  mov     [rsp+38h+var_10], 0
0x1400af3b8  mov     edx, 10Eh
0x1400af3bd  mov     [rsp+38h+var_18], 0
0x1400af3c6  xor     ecx, ecx
0x1400af3c8  lea     r8d, [r9+2]
0x1400af3cc  call    cs:__imp_WdLogSingleEntry5
0x1400af3d3  nop     dword ptr [rax+rax+00h]
0x1400af3d8  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400af3e2  lea     rax, [rcx+0C0h]
0x1400af3e9  cmp     [rax], rax
0x1400af3ec  jz      short loc_1400AF432
0x1400af3ee  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400af3f5  mov     dword ptr [rax], 1
0x1400af3fb  xor     ecx, ecx
0x1400af3fd  mov     [rsp+38h+var_10], 0
0x1400af406  mov     edx, 10Eh
0x1400af40b  mov     [rsp+38h+var_18], 0
0x1400af414  lea     r9d, [rcx+1]
0x1400af418  lea     r8d, [rcx+2]
0x1400af41c  call    cs:__imp_WdLogSingleEntry5
0x1400af423  nop     dword ptr [rax+rax+00h]
0x1400af428  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400af432  lea     rax, [rcx+0E0h]
0x1400af439  cmp     [rax], rax
0x1400af43c  jz      short loc_1400AF481
0x1400af43e  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400af445  mov     dword ptr [rax], 1
0x1400af44b  xor     ecx, ecx
0x1400af44d  mov     [rsp+38h+var_10], 0
0x1400af456  mov     edx, 10Eh
0x1400af45b  mov     [rsp+38h+var_18], 0
0x1400af464  lea     r9d, [rcx+2]
0x1400af468  mov     r8d, r9d
0x1400af46b  call    cs:__imp_WdLogSingleEntry5
0x1400af472  nop     dword ptr [rax+rax+00h]
0x1400af477  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400af481  lea     rax, [rcx+0F0h]
0x1400af488  cmp     [rax], rax
0x1400af48b  jz      short loc_1400AF4D1
0x1400af48d  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400af494  mov     dword ptr [rax], 1
0x1400af49a  xor     ecx, ecx
0x1400af49c  mov     [rsp+38h+var_10], 0
0x1400af4a5  mov     edx, 10Eh
0x1400af4aa  mov     [rsp+38h+var_18], 0
0x1400af4b3  lea     r9d, [rcx+3]
0x1400af4b7  lea     r8d, [rcx+2]
0x1400af4bb  call    cs:__imp_WdLogSingleEntry5
0x1400af4c2  nop     dword ptr [rax+rax+00h]
0x1400af4c7  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400af4d1  lea     rax, [rcx+100h]
0x1400af4d8  cmp     [rax], rax
0x1400af4db  jz      short loc_1400AF521
0x1400af4dd  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400af4e4  mov     dword ptr [rax], 1
0x1400af4ea  xor     ecx, ecx
0x1400af4ec  mov     [rsp+38h+var_10], 0
0x1400af4f5  mov     edx, 10Eh
0x1400af4fa  mov     [rsp+38h+var_18], 0
0x1400af503  lea     r9d, [rcx+4]
0x1400af507  lea     r8d, [rcx+2]
0x1400af50b  call    cs:__imp_WdLogSingleEntry5
0x1400af512  nop     dword ptr [rax+rax+00h]
0x1400af517  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400af521  lea     rax, [rcx+110h]
0x1400af528  cmp     [rax], rax
0x1400af52b  jz      short loc_1400AF571
0x1400af52d  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400af534  mov     dword ptr [rax], 1
0x1400af53a  xor     ecx, ecx
0x1400af53c  mov     [rsp+38h+var_10], 0
0x1400af545  mov     edx, 10Eh
0x1400af54a  mov     [rsp+38h+var_18], 0
0x1400af553  lea     r9d, [rcx+5]
0x1400af557  lea     r8d, [rcx+2]
0x1400af55b  call    cs:__imp_WdLogSingleEntry5
0x1400af562  nop     dword ptr [rax+rax+00h]
0x1400af567  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400af571  add     rcx, 40h ; '@'; Lookaside
0x1400af575  call    cs:__imp_ExDeletePagedLookasideList
0x1400af57c  nop     dword ptr [rax+rax+00h]
0x1400af581  lea     rcx, [rbx+10h]; this
0x1400af585  call    ??1DXGFASTMUTEX@@QEAA@XZ; DXGFASTMUTEX::~DXGFASTMUTEX(void)
0x1400af58a  lea     rax, ??_7VIDMM_HEAP_INTERFACE@@6B@; const VIDMM_HEAP_INTERFACE::`vftable'
0x1400af591  mov     [rbx], rax
0x1400af594  add     rsp, 30h
0x1400af598  pop     rbx
0x1400af599  retn
```
