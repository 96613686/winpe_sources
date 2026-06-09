# UpdatePreFetchJob(_CUCS_PRE_FETCH_JOB_ENTRY *)

- ea: `0x180003a44`
- end: `0x180003a95`
- name: `?UpdatePreFetchJob@@YAXPEAU_CUCS_PRE_FETCH_JOB_ENTRY@@@Z`
- size: `81`
- prototype: `void __fastcall(struct _CUCS_PRE_FETCH_JOB_ENTRY *, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800026cc`
- `0x1800028f0`
- `0x180003c90`

## callees

- `0x180003a44`
- `0x180003b60`
- `0x180004c90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a70`

## pseudocode

```c
void __fastcall UpdatePreFetchJob(struct _CUCS_PRE_FETCH_JOB_ENTRY *a1, __int64 a2)
{
  DWORD LastError; // eax
  __int64 v4; // rdx

  *((_DWORD *)a1 + 29) = 6;
  if ( !(unsigned int)UpdatePreFetchJobCacheFile(a1, a2) && !*((_DWORD *)a1 + 30) )
  {
    LastError = GetLastError();
    *((_DWORD *)a1 + 30) = LastError;
    if ( !LastError )
      *((_DWORD *)a1 + 30) = -2147418113;
    UpdatePreFetchJobCacheFile(a1, v4);
    *((_DWORD *)a1 + 30) = 0;
  }
  RemovePreFetchJobFromDir(a1);
}

```

## disassembly

```asm
0x180003a44  push    rbx
0x180003a46  sub     rsp, 20h
0x180003a4a  mov     rbx, rcx
0x180003a4d  mov     dword ptr [rcx+74h], 6
0x180003a54  call    ?UpdatePreFetchJobCacheFile@@YAHPEAU_CUCS_PRE_FETCH_JOB_ENTRY@@@Z; UpdatePreFetchJobCacheFile(_CUCS_PRE_FETCH_JOB_ENTRY *)
0x180003a59  test    eax, eax
0x180003a5b  jz      short loc_180003A6A
0x180003a5d  mov     rcx, rbx; hMem
0x180003a60  add     rsp, 20h
0x180003a64  pop     rbx
0x180003a65  jmp     RemovePreFetchJobFromDir
0x180003a6a  cmp     dword ptr [rbx+78h], 0
0x180003a6e  jnz     short loc_180003A5D
0x180003a70  call    cs:__imp_GetLastError
0x180003a76  mov     [rbx+78h], eax
0x180003a79  test    eax, eax
0x180003a7b  jnz     short loc_180003A84
0x180003a7d  mov     dword ptr [rbx+78h], 8000FFFFh
0x180003a84  mov     rcx, rbx; struct _CUCS_PRE_FETCH_JOB_ENTRY *
0x180003a87  call    ?UpdatePreFetchJobCacheFile@@YAHPEAU_CUCS_PRE_FETCH_JOB_ENTRY@@@Z; UpdatePreFetchJobCacheFile(_CUCS_PRE_FETCH_JOB_ENTRY *)
0x180003a8c  mov     dword ptr [rbx+78h], 0
0x180003a93  jmp     short loc_180003A5D
```
