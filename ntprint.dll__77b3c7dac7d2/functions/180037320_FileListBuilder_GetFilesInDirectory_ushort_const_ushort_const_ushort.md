# FileListBuilder::GetFilesInDirectory(ushort const *,ushort const *,ushort * *)

- ea: `0x180037320`
- end: `0x18003753b`
- name: `?GetFilesInDirectory@FileListBuilder@@QEAAJPEBG0PEAPEAG@Z`
- size: `539`
- prototype: `int(FileListBuilder *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180036ea4`

## callees

- `0x180002f48`
- `0x18001c660`
- `0x180036a0c`
- `0x180037320`
- `0x180037544`
- `0x180037eec`
- `0x180037f94`
- `0x18003a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800373be`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800373be`

## string_xrefs

- `0x18003748b`: `StringCbCopyNEx failed! hr: 0x%x`
- `0x180037492`: `FileListBuilder::GetFilesInDirectory`
- `0x1800374a7`: `FileListBuilder::GetFilesInDirectory`
- `0x1800374c7`: `FileListBuilder::GetFilesInDirectory`
- `0x1800374e1`: `FileListBuilder::GetFilesInDirectory`
- `0x18003751c`: `FileListBuilder::GetFilesInDirectory`
- `0x180037515`: `GetFilesInDirectoryRecursive for %ws with filter %ws failed! Hr: 0x%x`

## pseudocode

```c
__int64 __fastcall FileListBuilder::GetFilesInDirectory(
        FileListBuilder *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  int FilesInDirectoryRecursive; // eax
  int v9; // ebx
  unsigned __int16 *v10; // rsi
  unsigned int v11; // r12d
  __int64 v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned __int64 v16; // rdi
  unsigned __int16 *v17; // rax
  unsigned int v18; // ebp
  unsigned __int16 *v19; // r14
  __int64 v20; // rax
  const unsigned __int16 *v21; // r8
  __int64 v22; // rax
  int v23; // eax
  unsigned int v25; // [rsp+30h] [rbp-68h]
  unsigned __int64 v26[11]; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int16 *v27; // [rsp+B8h] [rbp+20h] BYREF

  *a4 = 0;
  FilesInDirectoryRecursive = FileListBuilder::GetFilesInDirectoryRecursive(this, a2, &qword_18003C420, a3);
  v9 = FilesInDirectoryRecursive;
  if ( FilesInDirectoryRecursive < 0 )
  {
    SplLibTelemetry::WriteDbgTraceError(
      "FileListBuilder::GetFilesInDirectory",
      L"GetFilesInDirectoryRecursive for %ws with filter %ws failed! Hr: 0x%x",
      a2,
      a3,
      FilesInDirectoryRecursive);
  }
  else
  {
    v10 = 0;
    if ( *((_DWORD *)this + 7) )
    {
      v11 = *((_DWORD *)this + 6);
      if ( v11 )
      {
        v12 = 0;
        do
        {
          v13 = (*(__int64 (__fastcall **)(FileListBuilder *, _QWORD))(*(_QWORD *)this + 8LL))(this, (unsigned int)v10);
          if ( v13 )
          {
            v14 = *(_QWORD *)(v13 + 8);
            v15 = -1;
            do
              ++v15;
            while ( *(_WORD *)(v14 + 2 * v15) );
            v12 += 2LL * (unsigned int)(v15 + 1);
          }
          LODWORD(v10) = (_DWORD)v10 + 1;
        }
        while ( (unsigned int)v10 < v11 );
        v16 = v12 + 2;
        v26[0] = v16;
        v17 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)v16);
        v10 = v17;
        if ( v17 )
        {
          memset_0(v17, 0, v16);
          v27 = v10;
          v18 = 0;
          v19 = v10;
          while ( v18 < v11 )
          {
            v20 = (*(__int64 (__fastcall **)(FileListBuilder *, _QWORD))(*(_QWORD *)this + 8LL))(this, v18);
            if ( v20 && (v21 = *(const unsigned __int16 **)(v20 + 8)) != 0 )
            {
              v22 = -1;
              do
                ++v22;
              while ( v21[v22] );
              v23 = StringCbCopyNExW(v19, v16, v21, 2LL * (unsigned int)(v22 + 1), &v27, v26, v25);
              v9 = v23;
              if ( v23 < 0 )
              {
                SplLibTelemetry::WriteDbgTraceError(
                  "FileListBuilder::GetFilesInDirectory",
                  L"StringCbCopyNEx failed! hr: 0x%x",
                  (unsigned int)v23);
                break;
              }
              v19 = v27 + 1;
              v16 = v26[0] - 2;
              ++v27;
              v26[0] -= 2LL;
              ++v18;
            }
            else
            {
              ++v18;
              if ( v9 < 0 )
                break;
            }
          }
        }
        else
        {
          SplLibTelemetry::WriteDbgTraceError(
            "FileListBuilder::GetFilesInDirectory",
            L"Failed to allocate space for the list of files!");
          v9 = -2147024882;
        }
      }
      else
      {
        SplLibTelemetry::WriteDbgTraceInfo(
          "FileListBuilder::GetFilesInDirectory",
          L"No files for filter (%ws) found for %ws.",
          a3,
          a2);
        v9 = -2147024637;
      }
    }
    else
    {
      SplLibTelemetry::WriteDbgTraceError(
        "FileListBuilder::GetFilesInDirectory",
        L"Failed to get the total number of files in the list!");
      v9 = -2147418113;
    }
    if ( v9 < 0 )
    {
      if ( v10 )
        DllFreeSplMem(v10);
    }
    else
    {
      *a4 = v10;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180037320  push    rbx
0x180037322  push    rbp
0x180037323  push    rsi
0x180037324  push    rdi
0x180037325  push    r12
0x180037327  push    r13
0x180037329  push    r14
0x18003732b  push    r15
0x18003732d  sub     rsp, 58h
0x180037331  mov     r13, r9
0x180037334  mov     rdi, r8
0x180037337  xor     r14d, r14d
0x18003733a  mov     rbp, rdx
0x18003733d  mov     [r9], r14
0x180037340  mov     r15, rcx
0x180037343  mov     r9, r8; unsigned __int16 *
0x180037346  lea     r8, qword_18003C420; unsigned __int16 *
0x18003734d  call    ?GetFilesInDirectoryRecursive@FileListBuilder@@AEAAJPEBG00@Z; FileListBuilder::GetFilesInDirectoryRecursive(ushort const *,ushort const *,ushort const *)
0x180037352  mov     ebx, eax
0x180037354  test    eax, eax
0x180037356  js      loc_18003750B
0x18003735c  mov     esi, r14d
0x18003735f  cmp     [r15+1Ch], r14d
0x180037363  jz      loc_1800374DA
0x180037369  mov     r12d, [r15+18h]
0x18003736d  test    r12d, r12d
0x180037370  jz      loc_1800374BA
0x180037376  mov     edi, r14d
0x180037379  mov     rax, [r15]
0x18003737c  mov     edx, esi
0x18003737e  mov     rcx, r15
0x180037381  mov     rax, [rax+8]
0x180037385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003738a  test    rax, rax
0x18003738d  jz      short loc_1800373A7
0x18003738f  mov     rcx, [rax+8]
0x180037393  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037397  inc     rax
0x18003739a  cmp     [rcx+rax*2], r14w
0x18003739f  jnz     short loc_180037397
0x1800373a1  inc     eax
0x1800373a3  lea     rdi, [rdi+rax*2]
0x1800373a7  inc     esi
0x1800373a9  cmp     esi, r12d
0x1800373ac  jb      short loc_180037379
0x1800373ae  add     rdi, 2
0x1800373b2  mov     ecx, 40h ; '@'; uFlags
0x1800373b7  mov     edx, edi; uBytes
0x1800373b9  mov     [rsp+98h+var_58], rdi
0x1800373be  call    cs:__imp_LocalAlloc
0x1800373c4  mov     rsi, rax
0x1800373c7  test    rax, rax
0x1800373ca  jz      loc_1800374A0
0x1800373d0  mov     r8, rdi; Size
0x1800373d3  xor     edx, edx; Val
0x1800373d5  mov     rcx, rax; void *
0x1800373d8  call    memset_0
0x1800373dd  xor     ecx, ecx
0x1800373df  mov     [rsp+98h+arg_18], rsi
0x1800373e7  mov     ebp, ecx
0x1800373e9  mov     r14, rsi
0x1800373ec  cmp     ebp, r12d
0x1800373ef  jnb     loc_1800374F2
0x1800373f5  mov     rax, [r15]
0x1800373f8  mov     edx, ebp
0x1800373fa  mov     rcx, r15
0x1800373fd  mov     rax, [rax+8]
0x180037401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037406  xor     ecx, ecx
0x180037408  test    rax, rax
0x18003740b  jz      short loc_18003747C
0x18003740d  mov     r8, [rax+8]; unsigned __int16 *
0x180037411  test    r8, r8
0x180037414  jz      short loc_18003747C
0x180037416  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003741a  inc     rax
0x18003741d  cmp     [r8+rax*2], cx
0x180037422  jnz     short loc_18003741A
0x180037424  lea     r9d, [rax+1]
0x180037428  mov     rdx, rdi; unsigned __int64
0x18003742b  lea     rax, [rsp+98h+var_58]
0x180037430  add     r9, r9; unsigned __int64
0x180037433  mov     [rsp+98h+var_70], rax; unsigned __int64 *
0x180037438  mov     rcx, r14; unsigned __int16 *
0x18003743b  lea     rax, [rsp+98h+arg_18]
0x180037443  mov     [rsp+98h+var_78], rax; unsigned __int16 **
0x180037448  call    ?StringCbCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCbCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18003744d  mov     ebx, eax
0x18003744f  test    eax, eax
0x180037451  js      short loc_180037488
0x180037453  mov     r14, [rsp+98h+arg_18]
0x18003745b  mov     rdi, [rsp+98h+var_58]
0x180037460  add     r14, 2
0x180037464  sub     rdi, 2
0x180037468  mov     [rsp+98h+arg_18], r14
0x180037470  mov     [rsp+98h+var_58], rdi
0x180037475  inc     ebp
0x180037477  jmp     loc_1800373EC
0x18003747c  inc     ebp
0x18003747e  test    ebx, ebx
0x180037480  jns     loc_1800373EC
0x180037486  jmp     short loc_1800374F2
0x180037488  mov     r8d, eax
0x18003748b  lea     rdx, aStringcbcopyne; "StringCbCopyNEx failed! hr: 0x%x"
0x180037492  lea     rcx, aFilelistbuilde; "FileListBuilder::GetFilesInDirectory"
0x180037499  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18003749e  jmp     short loc_1800374F2
0x1800374a0  lea     rdx, aFailedToAlloca_1; "Failed to allocate space for the list o"...
0x1800374a7  lea     rcx, aFilelistbuilde; "FileListBuilder::GetFilesInDirectory"
0x1800374ae  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800374b3  mov     ebx, 8007000Eh
0x1800374b8  jmp     short loc_1800374F2
0x1800374ba  mov     r9, rbp
0x1800374bd  lea     rdx, aNoFilesForFilt; "No files for filter (%ws) found for %ws"...
0x1800374c4  mov     r8, rdi
0x1800374c7  lea     rcx, aFilelistbuilde; "FileListBuilder::GetFilesInDirectory"
0x1800374ce  call    ?WriteDbgTraceInfo@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800374d3  mov     ebx, 80070103h
0x1800374d8  jmp     short loc_1800374F2
0x1800374da  lea     rdx, aFailedToGetThe_0; "Failed to get the total number of files"...
0x1800374e1  lea     rcx, aFilelistbuilde; "FileListBuilder::GetFilesInDirectory"
0x1800374e8  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800374ed  mov     ebx, 8000FFFFh
0x1800374f2  test    ebx, ebx
0x1800374f4  js      short loc_1800374FC
0x1800374f6  mov     [r13+0], rsi
0x1800374fa  jmp     short loc_180037528
0x1800374fc  test    rsi, rsi
0x1800374ff  jz      short loc_180037528
0x180037501  mov     rcx, rsi
0x180037504  call    DllFreeSplMem
0x180037509  jmp     short loc_180037528
0x18003750b  mov     r9, rdi
0x18003750e  mov     dword ptr [rsp+98h+var_78], eax
0x180037512  mov     r8, rbp
0x180037515  lea     rdx, aGetfilesindire; "GetFilesInDirectoryRecursive for %ws wi"...
0x18003751c  lea     rcx, aFilelistbuilde; "FileListBuilder::GetFilesInDirectory"
0x180037523  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180037528  mov     eax, ebx
0x18003752a  add     rsp, 58h
0x18003752e  pop     r15
0x180037530  pop     r14
0x180037532  pop     r13
0x180037534  pop     r12
0x180037536  pop     rdi
0x180037537  pop     rsi
0x180037538  pop     rbp
0x180037539  pop     rbx
0x18003753a  retn
```
