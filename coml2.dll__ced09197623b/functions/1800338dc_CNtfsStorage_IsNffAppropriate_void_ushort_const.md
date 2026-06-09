# CNtfsStorage::IsNffAppropriate(void *,ushort const *)

- ea: `0x1800338dc`
- end: `0x1800339f9`
- name: `?IsNffAppropriate@CNtfsStorage@@KAJPEAXPEBG@Z`
- size: `285`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180033810`

## callees

- `0x1800338dc`
- `0x180033a00`
- `0x180033dd0`
- `0x180033ec0`
- `0x180033fe8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800339f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800339f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800339ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800339ab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033968`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033968`

## pseudocode

```c
__int64 __fastcall CNtfsStorage::IsNffAppropriate(void *a1, const unsigned __int16 *a2, __int64 a3, int a4)
{
  signed int IsStorageFileHandle; // ebx
  int v6; // eax
  signed int LastError; // eax
  struct _OVERLAPPED Overlapped; // [rsp+20h] [rbp-20h] BYREF
  unsigned int v10; // [rsp+58h] [rbp+18h] BYREF
  int v11; // [rsp+5Ch] [rbp+1Ch]
  LPVOID lpMem; // [rsp+60h] [rbp+20h] BYREF

  v11 = HIDWORD(a2);
  lpMem = 0;
  v10 = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  IsStorageFileHandle = EnumNtStreams(a1, (struct _FILE_STREAM_INFORMATION **)&lpMem, &v10, a4);
  if ( IsStorageFileHandle < 0 )
  {
    IsStorageFileHandle = -2147287039;
  }
  else if ( !(unsigned int)CNtfsStorage::IsControlStreamExtant((struct _FILE_STREAM_INFORMATION *)lpMem) )
  {
    if ( (unsigned int)CNtfsStorage::IsOfflineFile(a1) )
    {
      memset(&Overlapped, 0, 24);
      Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
      if ( Overlapped.hEvent )
      {
        IsStorageFileHandle = StgIsStorageFileHandle(a1, &Overlapped);
        if ( IsStorageFileHandle >= 0 )
        {
          v6 = 0;
          if ( !IsStorageFileHandle )
            v6 = -2147287039;
          IsStorageFileHandle = v6;
        }
      }
      else
      {
        LastError = GetLastError();
        IsStorageFileHandle = LastError;
        if ( LastError > 0 )
          IsStorageFileHandle = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      IsStorageFileHandle = -2147286527;
    }
  }
  if ( lpMem )
    HeapFree(g_hHeap, 0, lpMem);
  if ( Overlapped.hEvent )
    CloseHandle(Overlapped.hEvent);
  return (unsigned int)IsStorageFileHandle;
}

```

## disassembly

```asm
0x1800338dc  mov     [rsp-8+arg_0], rbx
0x1800338e1  mov     [rsp-8+arg_18], rsi
0x1800338e6  mov     qword ptr [rsp-8+arg_8], rdx
0x1800338eb  push    rbp
0x1800338ec  mov     rbp, rsp
0x1800338ef  sub     rsp, 40h
0x1800338f3  xorps   xmm0, xmm0
0x1800338f6  mov     [rbp+lpMem], 0
0x1800338fe  lea     r8, [rbp+arg_8]; unsigned int *
0x180033902  mov     [rbp+arg_8], 0
0x180033909  lea     rdx, [rbp+lpMem]; struct _FILE_STREAM_INFORMATION **
0x18003390d  mov     [rbp+Overlapped.Internal], 0
0x180033915  movdqu  xmmword ptr [rbp+Overlapped.InternalHigh], xmm0
0x18003391a  mov     rsi, rcx
0x18003391d  mov     [rbp+Overlapped.hEvent], 0
0x180033925  call    ?EnumNtStreams@@YAJPEAXPEAPEAU_FILE_STREAM_INFORMATION@@PEAKH@Z; EnumNtStreams(void *,_FILE_STREAM_INFORMATION * *,ulong *,int)
0x18003392a  mov     ebx, eax
0x18003392c  test    eax, eax
0x18003392e  js      loc_1800339E3
0x180033934  mov     rcx, [rbp+lpMem]; struct _FILE_STREAM_INFORMATION *
0x180033938  call    ?IsControlStreamExtant@CNtfsStorage@@CAHPEAU_FILE_STREAM_INFORMATION@@@Z; CNtfsStorage::IsControlStreamExtant(_FILE_STREAM_INFORMATION *)
0x18003393d  test    eax, eax
0x18003393f  jnz     short loc_180033997
0x180033941  mov     rcx, rsi; void *
0x180033944  call    ?IsOfflineFile@CNtfsStorage@@CAJPEAX@Z; CNtfsStorage::IsOfflineFile(void *)
0x180033949  test    eax, eax
0x18003394b  jz      loc_1800339EA
0x180033951  xorps   xmm0, xmm0
0x180033954  xor     r9d, r9d; lpName
0x180033957  xor     r8d, r8d; bInitialState
0x18003395a  xor     ecx, ecx; lpEventAttributes
0x18003395c  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x180033960  lea     edx, [r9+1]; bManualReset
0x180033964  movups  xmmword ptr [rbp-10h], xmm0
0x180033968  call    cs:__imp_CreateEventW
0x18003396e  mov     [rbp+Overlapped.hEvent], rax
0x180033972  test    rax, rax
0x180033975  jz      short loc_1800339CC
0x180033977  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18003397b  mov     rcx, rsi; hFile
0x18003397e  call    StgIsStorageFileHandle
0x180033983  mov     ebx, eax
0x180033985  test    eax, eax
0x180033987  js      short loc_180033997
0x180033989  xor     eax, eax
0x18003398b  mov     ecx, 80030001h
0x180033990  test    ebx, ebx
0x180033992  cmovz   eax, ecx
0x180033995  mov     ebx, eax
0x180033997  cmp     [rbp+lpMem], 0
0x18003399c  jz      short loc_1800339B1
0x18003399e  mov     r8, [rbp+lpMem]; lpMem
0x1800339a2  xor     edx, edx; dwFlags
0x1800339a4  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800339ab  call    cs:__imp_HeapFree
0x1800339b1  mov     rcx, [rbp+Overlapped.hEvent]; hObject
0x1800339b5  test    rcx, rcx
0x1800339b8  jnz     short loc_1800339F1
0x1800339ba  mov     rsi, [rsp+40h+arg_18]
0x1800339bf  mov     eax, ebx
0x1800339c1  mov     rbx, [rsp+40h+arg_0]
0x1800339c6  add     rsp, 40h
0x1800339ca  pop     rbp
0x1800339cb  retn
0x1800339cc  call    cs:__imp_GetLastError
0x1800339d2  mov     ebx, eax
0x1800339d4  test    eax, eax
0x1800339d6  jle     short loc_180033997
0x1800339d8  movzx   ebx, ax
0x1800339db  or      ebx, 80070000h
0x1800339e1  jmp     short loc_180033997
0x1800339e3  mov     ebx, 80030001h
0x1800339e8  jmp     short loc_180033997
0x1800339ea  mov     ebx, 80030201h
0x1800339ef  jmp     short loc_180033997
0x1800339f1  call    cs:__imp_CloseHandle
0x1800339f7  jmp     short loc_1800339BA
```
