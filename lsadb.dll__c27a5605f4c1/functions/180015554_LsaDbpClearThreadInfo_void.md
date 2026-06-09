# LsaDbpClearThreadInfo(void)

- ea: `0x180015554`
- end: `0x18001565e`
- name: `?LsaDbpClearThreadInfo@@YAXXZ`
- size: `266`
- prototype: `void(void)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800154f0`
- `0x18001f130`
- `0x18001f260`
- `0x18001fdd0`

## callees

- `0x18000fd18`
- `0x180010d78`
- `0x180011d30`
- `0x180015554`
- `0x1800157c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015624`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015624`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180015605`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180015605`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015564`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001561c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001561c`
- `LSASRV!LsapFreeLsaHeap` at `0x18001564d`
- `LSASRV!LsapFreeLsaHeap` at `0x18001564d`
- `NTDSA!THDestroy` at `0x1800155df`
- `NTDSA!THDestroy` at `0x1800155df`
- `NTDSA!THRestore` at `0x1800155f0`
- `NTDSA!THRestore` at `0x1800155f0`

## pseudocode

```c
void LsaDbpClearThreadInfo(void)
{
  _DWORD *Value; // rax
  _DWORD *v1; // rdi
  unsigned int v2; // ecx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  DWORD LastError; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8

  Value = TlsGetValue(LsaDbpDsThreadState);
  v1 = Value;
  if ( Value )
  {
    v2 = Value[1];
    if ( v2 <= 1 )
    {
      if ( Value[3] )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_e6ef33379d4a35ad358d2a6e144c5a99_Traceguids);
        LsaDbpDsCauseTransactionToCommitOrAbort(0);
      }
      if ( v1[2] )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_e6ef33379d4a35ad358d2a6e144c5a99_Traceguids);
        v3 = THDestroy();
        LsaDbpDsMapDsReturnToStatus(v3);
        THRestore(*((_QWORD *)v1 + 4));
        *((_QWORD *)v1 + 4) = 0;
        v1[2] = 0;
      }
      if ( !TlsSetValue(LsaDbpDsThreadState, 0) && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        CurrentThreadId = GetCurrentThreadId();
        WPP_SF_qLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v8, v1, CurrentThreadId, LastError);
      }
      LsapFreeLsaHeap(v1, v4, v5);
    }
    else
    {
      Value[1] = v2 - 1;
    }
  }
}

```

## disassembly

```asm
0x180015554  mov     [rsp+arg_0], rbx
0x180015559  push    rdi
0x18001555a  sub     rsp, 30h
0x18001555e  mov     ecx, cs:?LsaDbpDsThreadState@@3KA; dwTlsIndex
0x180015564  call    cs:__imp_TlsGetValue
0x18001556a  xor     ebx, ebx
0x18001556c  mov     rdi, rax
0x18001556f  test    rax, rax
0x180015572  jz      loc_180015653
0x180015578  mov     ecx, [rax+4]
0x18001557b  cmp     ecx, 1
0x18001557e  jbe     short loc_18001558A
0x180015580  dec     ecx
0x180015582  mov     [rax+4], ecx
0x180015585  jmp     loc_180015653
0x18001558a  cmp     [rax+0Ch], ebx
0x18001558d  jz      short loc_1800155B8
0x18001558f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015596  test    byte ptr [rcx+1Ch], 1
0x18001559a  jz      short loc_1800155B1
0x18001559c  mov     rcx, [rcx+10h]
0x1800155a0  lea     r8, WPP_e6ef33379d4a35ad358d2a6e144c5a99_Traceguids
0x1800155a7  mov     edx, 0Bh
0x1800155ac  call    WPP_SF_
0x1800155b1  xor     ecx, ecx; unsigned __int8
0x1800155b3  call    ?LsaDbpDsCauseTransactionToCommitOrAbort@@YAJE@Z; LsaDbpDsCauseTransactionToCommitOrAbort(uchar)
0x1800155b8  cmp     [rdi+8], ebx
0x1800155bb  jz      short loc_1800155FD
0x1800155bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800155c4  test    byte ptr [rcx+1Ch], 1
0x1800155c8  jz      short loc_1800155DF
0x1800155ca  mov     rcx, [rcx+10h]
0x1800155ce  lea     r8, WPP_e6ef33379d4a35ad358d2a6e144c5a99_Traceguids
0x1800155d5  mov     edx, 0Ch
0x1800155da  call    WPP_SF_
0x1800155df  call    cs:__imp_THDestroy
0x1800155e5  mov     ecx, eax; unsigned int
0x1800155e7  call    ?LsaDbpDsMapDsReturnToStatus@@YAJK@Z; LsaDbpDsMapDsReturnToStatus(ulong)
0x1800155ec  mov     rcx, [rdi+20h]
0x1800155f0  call    cs:__imp_THRestore
0x1800155f6  mov     [rdi+20h], rbx
0x1800155fa  mov     [rdi+8], ebx
0x1800155fd  mov     ecx, cs:?LsaDbpDsThreadState@@3KA; dwTlsIndex
0x180015603  xor     edx, edx; lpTlsValue
0x180015605  call    cs:__imp_TlsSetValue
0x18001560b  test    eax, eax
0x18001560d  jnz     short loc_18001564A
0x18001560f  mov     rax, cs:WPP_GLOBAL_Control
0x180015616  test    byte ptr [rax+1Ch], 1
0x18001561a  jz      short loc_18001564A
0x18001561c  call    cs:__imp_GetLastError
0x180015622  mov     ebx, eax
0x180015624  call    cs:__imp_GetCurrentThreadId
0x18001562a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015631  mov     edx, 0Dh
0x180015636  mov     [rsp+38h+var_10], ebx
0x18001563a  mov     r9, rdi
0x18001563d  mov     [rsp+38h+var_18], eax
0x180015641  mov     rcx, [rcx+10h]
0x180015645  call    WPP_SF_qLL
0x18001564a  mov     rcx, rdi
0x18001564d  call    cs:__imp_LsapFreeLsaHeap
0x180015653  mov     rbx, [rsp+38h+arg_0]
0x180015658  add     rsp, 30h
0x18001565c  pop     rdi
0x18001565d  retn
```
