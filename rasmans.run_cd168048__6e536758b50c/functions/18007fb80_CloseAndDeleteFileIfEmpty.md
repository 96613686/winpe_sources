# CloseAndDeleteFileIfEmpty

- ea: `0x18007fb80`
- end: `0x18007fc5a`
- name: `CloseAndDeleteFileIfEmpty`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180081a40`

## callees

- `0x18007fb80`
- `0x180093bbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fbc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fc1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fbc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fc1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007fc3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007fc3b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007fbac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007fbac`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007fc0d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007fc0d`

## pseudocode

```c
__int64 __fastcall CloseAndDeleteFileIfEmpty(int a1, const WCHAR *a2)
{
  __int64 v2; // rdi
  DWORD LastError; // ebx
  __int64 ***v6; // rcx
  __int64 **v7; // rcx
  __int64 *i; // rax

  v2 = a1;
  if ( !g_hmutexPb )
    return 10;
  LastError = WaitForSingleObject(g_hmutexPb, 0xFFFFFFFF);
  if ( (LastError & 0xFFFFFF7F) != 0 )
  {
    return GetLastError();
  }
  else
  {
    if ( (unsigned int)v2 <= 0x1F3 && (v6 = (__int64 ***)gpRasfiles[v2]) != 0 )
    {
      v7 = *v6;
      for ( i = *v7; i != (__int64 *)v7; i = (__int64 *)*i )
      {
        if ( (*((_BYTE *)i + 25) & 1) != 0 )
          goto LABEL_14;
      }
      if ( (unsigned int)RasfileClose((unsigned int)v2) )
      {
        if ( !DeleteFileW(a2) )
          LastError = GetLastError();
      }
    }
    else
    {
LABEL_14:
      RasfileClose((unsigned int)v2);
    }
    ReleaseMutex(g_hmutexPb);
  }
  return LastError;
}

```

## disassembly

```asm
0x18007fb80  mov     [rsp+arg_0], rbx
0x18007fb85  mov     [rsp+arg_8], rsi
0x18007fb8a  push    rdi
0x18007fb8b  sub     rsp, 20h
0x18007fb8f  movsxd  rdi, ecx
0x18007fb92  mov     rsi, rdx
0x18007fb95  mov     rcx, cs:g_hmutexPb; hHandle
0x18007fb9c  test    rcx, rcx
0x18007fb9f  jnz     short loc_18007FBA9
0x18007fba1  lea     eax, [rcx+0Ah]
0x18007fba4  jmp     loc_18007FC49
0x18007fba9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007fbac  call    cs:__imp_WaitForSingleObject
0x18007fbb3  nop     dword ptr [rax+rax+00h]
0x18007fbb8  mov     ebx, eax
0x18007fbba  test    eax, 0FFFFFF7Fh
0x18007fbbf  jz      short loc_18007FBD1
0x18007fbc1  call    cs:__imp_GetLastError
0x18007fbc8  nop     dword ptr [rax+rax+00h]
0x18007fbcd  mov     ebx, eax
0x18007fbcf  jmp     short loc_18007FC47
0x18007fbd1  cmp     edi, 1F3h
0x18007fbd7  ja      short loc_18007FC2D
0x18007fbd9  lea     rcx, gpRasfiles
0x18007fbe0  mov     rcx, [rcx+rdi*8]
0x18007fbe4  test    rcx, rcx
0x18007fbe7  jz      short loc_18007FC2D
0x18007fbe9  mov     rcx, [rcx]
0x18007fbec  mov     rax, [rcx]
0x18007fbef  jmp     short loc_18007FBFA
0x18007fbf1  test    byte ptr [rax+19h], 1
0x18007fbf5  jnz     short loc_18007FC2D
0x18007fbf7  mov     rax, [rax]
0x18007fbfa  cmp     rax, rcx
0x18007fbfd  jnz     short loc_18007FBF1
0x18007fbff  mov     ecx, edi
0x18007fc01  call    RasfileClose
0x18007fc06  test    eax, eax
0x18007fc08  jz      short loc_18007FC34
0x18007fc0a  mov     rcx, rsi; lpFileName
0x18007fc0d  call    cs:__imp_DeleteFileW
0x18007fc14  nop     dword ptr [rax+rax+00h]
0x18007fc19  test    eax, eax
0x18007fc1b  jnz     short loc_18007FC34
0x18007fc1d  call    cs:__imp_GetLastError
0x18007fc24  nop     dword ptr [rax+rax+00h]
0x18007fc29  mov     ebx, eax
0x18007fc2b  jmp     short loc_18007FC34
0x18007fc2d  mov     ecx, edi
0x18007fc2f  call    RasfileClose
0x18007fc34  mov     rcx, cs:g_hmutexPb; hMutex
0x18007fc3b  call    cs:__imp_ReleaseMutex
0x18007fc42  nop     dword ptr [rax+rax+00h]
0x18007fc47  mov     eax, ebx
0x18007fc49  mov     rbx, [rsp+28h+arg_0]
0x18007fc4e  mov     rsi, [rsp+28h+arg_8]
0x18007fc53  add     rsp, 20h
0x18007fc57  pop     rdi
0x18007fc58  retn
```
