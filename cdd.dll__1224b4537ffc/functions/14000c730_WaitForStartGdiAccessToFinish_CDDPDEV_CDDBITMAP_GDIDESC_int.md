# WaitForStartGdiAccessToFinish(CDDPDEV *,CDDBITMAP_GDIDESC *,int)

- ea: `0x14000c730`
- end: `0x14000c809`
- name: `?WaitForStartGdiAccessToFinish@@YAXPEAUCDDPDEV@@PEAUCDDBITMAP_GDIDESC@@H@Z`
- size: `217`
- prototype: `void __fastcall(struct CDDPDEV *, struct CDDBITMAP_GDIDESC *, int)`
- caller_count: `20`
- callee_count: `3`
- tags: ``

## callers

- `0x140002504`
- `0x140004904`
- `0x140005cc0`
- `0x140006a70`
- `0x140007b00`
- `0x14000a254`
- `0x14000d63c`
- `0x1400161b0`
- `0x140017518`
- `0x140019458`
- `0x140022e70`
- `0x1400235c0`
- `0x140023e60`
- `0x140025090`
- `0x1400255b0`
- `0x140025c90`
- `0x1400261a0`
- `0x1400267f0`
- `0x140026d40`
- `0x140027370`

## callees

- `0x14000c730`
- `0x14002fbd4`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogSingleEntry1` at `0x14000c79e`
- `watchdog!WdLogSingleEntry1` at `0x14000c79e`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000c7b4`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000c7b4`

## pseudocode

```c
void __fastcall WaitForStartGdiAccessToFinish(struct CDDPDEV *a1, struct CDDBITMAP_GDIDESC *a2, int a3)
{
  __int64 v5; // r8
  int v7; // eax
  _QWORD *v8; // rax

  v5 = *((unsigned int *)a2 + 8);
  if ( (_DWORD)v5 )
  {
    v7 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))a1 + 28))(
           *((_QWORD *)a1 + 684),
           *((_QWORD *)a1 + 311),
           v5,
           0);
    if ( v7 < 0 )
    {
      WdLogSingleEntry1(4, v7);
      WdLogGlobalForLineNumber = 3086;
      v8 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v8[3] = gCddImageInfo;
      v8[4] = (unsigned int)dword_14003E570;
      v8[5] = 215857758;
      WdLogGlobalForLineNumber = 3086;
    }
    if ( a3 )
    {
      if ( (*(_DWORD *)(*((_QWORD *)a2 + 7) + 128LL) & 2) != 0 )
        FlushCpuCache(
          a1,
          *(struct CddBitmapStagingApertureMem **)(*((_QWORD *)a2 + 1) + 32LL),
          *(_DWORD *)(*(_QWORD *)a2 + 64LL),
          (const struct tagRECT *)((char *)a2 + 36));
    }
  }
}

```

## disassembly

```asm
0x14000c730  mov     [rsp+arg_0], rbx
0x14000c735  mov     [rsp+arg_8], rsi
0x14000c73a  push    rdi
0x14000c73b  sub     rsp, 30h
0x14000c73f  mov     esi, r8d
0x14000c742  mov     rbx, rdx
0x14000c745  mov     r8d, [rdx+20h]
0x14000c749  mov     rdi, rcx
0x14000c74c  test    r8d, r8d
0x14000c74f  jz      short loc_14000C785
0x14000c751  mov     rax, [rcx+0E0h]
0x14000c758  xor     r9d, r9d
0x14000c75b  mov     rdx, [rcx+9B8h]
0x14000c762  mov     rcx, [rcx+1560h]
0x14000c769  call    _guard_dispatch_icall
0x14000c76e  test    eax, eax
0x14000c770  js      short loc_14000C796
0x14000c772  test    esi, esi
0x14000c774  jz      short loc_14000C785
0x14000c776  mov     rax, [rbx+38h]
0x14000c77a  mov     ecx, [rax+80h]
0x14000c780  test    cl, 2
0x14000c783  jnz     short loc_14000C7E9
0x14000c785  mov     rbx, [rsp+38h+arg_0]
0x14000c78a  mov     rsi, [rsp+38h+arg_8]
0x14000c78f  add     rsp, 30h
0x14000c793  pop     rdi
0x14000c794  retn
0x14000c796  movsxd  rdx, eax
0x14000c799  mov     ecx, 4
0x14000c79e  call    cs:__imp_WdLogSingleEntry1
0x14000c7a5  nop     dword ptr [rax+rax+00h]
0x14000c7aa  mov     cs:WdLogGlobalForLineNumber, 0C0Eh
0x14000c7b4  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14000c7bb  nop     dword ptr [rax+rax+00h]
0x14000c7c0  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000c7c7  mov     [rax+18h], rcx
0x14000c7cb  mov     ecx, cs:dword_14003E570
0x14000c7d1  mov     [rax+20h], rcx
0x14000c7d5  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000c7dd  mov     cs:WdLogGlobalForLineNumber, 0C0Eh
0x14000c7e7  jmp     short loc_14000C772
0x14000c7e9  mov     r8, [rbx]
0x14000c7ec  lea     r9, [rbx+24h]; struct tagRECT *
0x14000c7f0  mov     rdx, [rbx+8]
0x14000c7f4  mov     rcx, rdi; struct CDDPDEV *
0x14000c7f7  mov     r8d, [r8+40h]; unsigned int
0x14000c7fb  mov     rdx, [rdx+20h]; this
0x14000c7ff  call    ?FlushCpuCache@@YAXPEAUCDDPDEV@@PEAVCddBitmapStagingApertureMem@@IPEBUtagRECT@@E@Z; FlushCpuCache(CDDPDEV *,CddBitmapStagingApertureMem *,uint,tagRECT const *,uchar)
0x14000c804  jmp     loc_14000C785
```
