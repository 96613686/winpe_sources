# InstallOnePortMonitor(HWND__ *,void *,ushort *,ushort *,ushort *)

- ea: `0x18001718c`
- end: `0x180017356`
- name: `?InstallOnePortMonitor@@YAHPEAUHWND__@@PEAXPEAG22@Z`
- size: `458`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, HINF InfHandle@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001706c`

## callees

- `0x18001718c`
- `0x18001735c`
- `0x1800173e8`
- `0x18001e470`

## import_xrefs

- `USER32!MessageBoxW` at `0x18001731d`
- `USER32!MessageBoxW` at `0x18001731d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017280`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017326`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001732f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001733d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017280`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017326`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001732f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001733d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800171b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800172f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800171b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800172f2`
- `SETUPAPI!SetupOpenFileQueue` at `0x1800171fa`
- `SETUPAPI!SetupOpenFileQueue` at `0x1800171fa`
- `SETUPAPI!SetupInstallFilesFromInfSectionW` at `0x180017228`
- `SETUPAPI!SetupInstallFilesFromInfSectionW` at `0x180017228`
- `SETUPAPI!SetupGetLineTextW` at `0x1800171ec`
- `SETUPAPI!SetupGetLineTextW` at `0x1800171ec`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180017272`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180017272`
- `SETUPAPI!SetupCommitFileQueueW` at `0x180017256`
- `SETUPAPI!SetupCommitFileQueueW` at `0x180017256`
- `SETUPAPI!SetupCloseFileQueue` at `0x18001728e`
- `SETUPAPI!SetupCloseFileQueue` at `0x18001728e`
- `SETUPAPI!SetupInitDefaultQueueCallback` at `0x180017238`
- `SETUPAPI!SetupInitDefaultQueueCallback` at `0x180017238`
- `SETUPAPI!SetupDefaultQueueCallbackW` at `0x180017246`

## string_xrefs

- `0x1800171cb`: `PortMonitorDll`

## pseudocode

```c
__int64 __fastcall InstallOnePortMonitor(
        HWND hWnd,
        HINF InfHandle,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *SourceRootPath)
{
  unsigned int v7; // esi
  WCHAR *ReturnBuffer; // rax
  __int64 v11; // rbp
  WCHAR *v12; // r14
  HSPFILEQ v13; // rbx
  PVOID inited; // rax
  void *v15; // rdi
  unsigned __int16 *StringFromRcFile; // rdi
  __int64 v17; // rax
  WCHAR *v18; // rbx
  __int64 v19; // rdx
  SIZE_T v20; // r14
  unsigned __int16 *v21; // rax
  WCHAR *v22; // rbp

  v7 = 0;
  ReturnBuffer = (WCHAR *)LocalAlloc(0x40u, 0x208u);
  v11 = -1;
  v12 = ReturnBuffer;
  if ( !ReturnBuffer )
    goto LABEL_12;
  v13 = 0;
  if ( SetupGetLineTextW(0, InfHandle, a4, cszPortMonitorDllKey, ReturnBuffer, 0x104u, 0) )
  {
    v13 = SetupOpenFileQueue();
    if ( v13 != (HSPFILEQ)-1LL )
    {
      if ( SetupInstallFilesFromInfSectionW(InfHandle, 0, v13, a4, SourceRootPath, 0x500u) )
      {
        inited = SetupInitDefaultQueueCallback(hWnd);
        v15 = inited;
        if ( inited )
        {
          v7 = SetupCommitFileQueueW(hWnd, v13, SetupDefaultQueueCallbackW, inited);
          if ( v7 )
            v7 = AddPrintMonitor(a3, v12);
          SetupTermDefaultQueueCallback(v15);
        }
      }
    }
  }
  LocalFree(v12);
  if ( v13 )
    SetupCloseFileQueue(v13);
  if ( !v7 )
  {
LABEL_12:
    StringFromRcFile = (unsigned __int16 *)GetStringFromRcFile(0x3F2u);
    v17 = GetStringFromRcFile(0x3EEu);
    v18 = (WCHAR *)v17;
    if ( StringFromRcFile )
    {
      if ( v17 )
      {
        v19 = -1;
        do
          ++v19;
        while ( a3[v19] );
        do
          ++v11;
        while ( StringFromRcFile[v11] );
        v20 = (unsigned int)(2 * (v19 + v11) + 4);
        v21 = (unsigned __int16 *)LocalAlloc(0x40u, v20);
        v22 = v21;
        if ( v21 )
        {
          StringCbPrintfW(v21, (unsigned int)v20, StringFromRcFile, a3);
          MessageBoxW(hWnd, v22, v18, 0);
          LocalFree(v22);
        }
      }
      LocalFree(StringFromRcFile);
    }
    if ( v18 )
      LocalFree(v18);
  }
  return v7;
}

```

## disassembly

```asm
0x18001718c  push    rbx
0x18001718e  push    rbp
0x18001718f  push    rsi
0x180017190  push    rdi
0x180017191  push    r12
0x180017193  push    r13
0x180017195  push    r14
0x180017197  push    r15
0x180017199  sub     rsp, 48h
0x18001719d  mov     r15, rdx
0x1800171a0  mov     r13, rcx
0x1800171a3  xor     esi, esi
0x1800171a5  mov     edx, 208h; uBytes
0x1800171aa  mov     rdi, r9
0x1800171ad  mov     r12, r8
0x1800171b0  lea     ecx, [rsi+40h]; uFlags
0x1800171b3  call    cs:__imp_LocalAlloc
0x1800171b9  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800171bd  mov     r14, rax
0x1800171c0  test    rax, rax
0x1800171c3  jz      loc_18001729E
0x1800171c9  xor     ebx, ebx
0x1800171cb  lea     r9, ?cszPortMonitorDllKey@@3PAGA; "PortMonitorDll"
0x1800171d2  mov     [rsp+88h+RequiredSize], rbx; RequiredSize
0x1800171d7  mov     r8, rdi; Section
0x1800171da  mov     [rsp+88h+ReturnBufferSize], 104h; ReturnBufferSize
0x1800171e2  mov     rdx, r15; InfHandle
0x1800171e5  xor     ecx, ecx; Context
0x1800171e7  mov     [rsp+88h+ReturnBuffer], rax; ReturnBuffer
0x1800171ec  call    cs:__imp_SetupGetLineTextW
0x1800171f2  test    eax, eax
0x1800171f4  jz      loc_18001727A
0x1800171fa  call    cs:__imp_SetupOpenFileQueue
0x180017200  mov     rbx, rax
0x180017203  cmp     rax, rbp
0x180017206  jz      short loc_18001727A
0x180017208  mov     rax, [rsp+88h+SourceRootPath]
0x180017210  mov     r9, rdi; SectionName
0x180017213  mov     [rsp+88h+ReturnBufferSize], 500h; CopyFlags
0x18001721b  mov     r8, rbx; FileQueue
0x18001721e  xor     edx, edx; LayoutInfHandle
0x180017220  mov     [rsp+88h+ReturnBuffer], rax; SourceRootPath
0x180017225  mov     rcx, r15; InfHandle
0x180017228  call    cs:__imp_SetupInstallFilesFromInfSectionW
0x18001722e  xor     r15d, r15d
0x180017231  test    eax, eax
0x180017233  jz      short loc_18001727D
0x180017235  mov     rcx, r13; OwnerWindow
0x180017238  call    cs:__imp_SetupInitDefaultQueueCallback
0x18001723e  mov     rdi, rax
0x180017241  test    rax, rax
0x180017244  jz      short loc_18001727D
0x180017246  mov     r8, cs:__imp_SetupDefaultQueueCallbackW; MsgHandler
0x18001724d  mov     r9, rax; Context
0x180017250  mov     rdx, rbx; QueueHandle
0x180017253  mov     rcx, r13; Owner
0x180017256  call    cs:__imp_SetupCommitFileQueueW
0x18001725c  mov     esi, eax
0x18001725e  test    eax, eax
0x180017260  jz      short loc_18001726F
0x180017262  mov     rdx, r14
0x180017265  mov     rcx, r12
0x180017268  call    AddPrintMonitor
0x18001726d  mov     esi, eax
0x18001726f  mov     rcx, rdi; Context
0x180017272  call    cs:__imp_SetupTermDefaultQueueCallback
0x180017278  jmp     short loc_18001727D
0x18001727a  xor     r15d, r15d
0x18001727d  mov     rcx, r14; hMem
0x180017280  call    cs:__imp_LocalFree
0x180017286  test    rbx, rbx
0x180017289  jz      short loc_180017294
0x18001728b  mov     rcx, rbx; QueueHandle
0x18001728e  call    cs:__imp_SetupCloseFileQueue
0x180017294  test    esi, esi
0x180017296  jnz     loc_180017343
0x18001729c  jmp     short loc_1800172A1
0x18001729e  xor     r15d, r15d
0x1800172a1  mov     ecx, 3F2h; uID
0x1800172a6  call    GetStringFromRcFile
0x1800172ab  mov     ecx, 3EEh; uID
0x1800172b0  mov     rdi, rax
0x1800172b3  call    GetStringFromRcFile
0x1800172b8  mov     rbx, rax
0x1800172bb  test    rdi, rdi
0x1800172be  jz      short loc_180017335
0x1800172c0  test    rax, rax
0x1800172c3  jz      short loc_18001732C
0x1800172c5  mov     rdx, rbp
0x1800172c8  inc     rdx
0x1800172cb  cmp     [r12+rdx*2], r15w
0x1800172d0  jnz     short loc_1800172C8
0x1800172d2  inc     rbp
0x1800172d5  cmp     [rdi+rbp*2], r15w
0x1800172da  jnz     short loc_1800172D2
0x1800172dc  lea     rax, [rdx+rbp]
0x1800172e0  mov     ecx, 40h ; '@'; uFlags
0x1800172e5  lea     rax, ds:4[rax*2]
0x1800172ed  mov     edx, eax; uBytes
0x1800172ef  mov     r14d, eax
0x1800172f2  call    cs:__imp_LocalAlloc
0x1800172f8  mov     rbp, rax
0x1800172fb  test    rax, rax
0x1800172fe  jz      short loc_18001732C
0x180017300  mov     r9, r12
0x180017303  mov     r8, rdi; unsigned __int16 *
0x180017306  mov     edx, r14d; unsigned __int64
0x180017309  mov     rcx, rax; unsigned __int16 *
0x18001730c  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017311  xor     r9d, r9d; uType
0x180017314  mov     r8, rbx; lpCaption
0x180017317  mov     rdx, rbp; lpText
0x18001731a  mov     rcx, r13; hWnd
0x18001731d  call    cs:__imp_MessageBoxW
0x180017323  mov     rcx, rbp; hMem
0x180017326  call    cs:__imp_LocalFree
0x18001732c  mov     rcx, rdi; hMem
0x18001732f  call    cs:__imp_LocalFree
0x180017335  test    rbx, rbx
0x180017338  jz      short loc_180017343
0x18001733a  mov     rcx, rbx; hMem
0x18001733d  call    cs:__imp_LocalFree
0x180017343  mov     eax, esi
0x180017345  add     rsp, 48h
0x180017349  pop     r15
0x18001734b  pop     r14
0x18001734d  pop     r13
0x18001734f  pop     r12
0x180017351  pop     rdi
0x180017352  pop     rsi
0x180017353  pop     rbp
0x180017354  pop     rbx
0x180017355  retn
```
