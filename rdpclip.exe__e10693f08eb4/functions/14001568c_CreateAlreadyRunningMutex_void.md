# CreateAlreadyRunningMutex(void)

- ea: `0x14001568c`
- end: `0x140015777`
- name: `?CreateAlreadyRunningMutex@@YAJXZ`
- size: `235`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140015c20`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x14001568c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400156ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400156ed`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400156e0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400156e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015757`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015757`

## string_xrefs

- `0x1400156d5`: `RdpClipAlreadyRunningMutex`

## pseudocode

```c
signed int CreateAlreadyRunningMutex(void)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int result; // eax
  HANDLE v2; // rcx
  unsigned int v3; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_355c378141323d6b66da1816bd4a5ba5_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  g_hAlreadyRunningMutex = CreateMutexW(0, 0, L"RdpClipAlreadyRunningMutex");
  result = GetLastError();
  v2 = g_hAlreadyRunningMutex;
  if ( g_hAlreadyRunningMutex )
  {
    if ( result == 183 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v3 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_355c378141323d6b66da1816bd4a5ba5_Traceguids, v3);
        v2 = g_hAlreadyRunningMutex;
      }
      CloseHandle(v2);
      result = -2147024713;
      g_hAlreadyRunningMutex = 0;
    }
    else
    {
      return 0;
    }
  }
  else if ( result > 0 )
  {
    return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x14001568c  push    rbx
0x14001568e  sub     rsp, 20h
0x140015692  mov     rax, cs:WPP_GLOBAL_Control
0x140015699  lea     rbx, WPP_GLOBAL_Control
0x1400156a0  cmp     rax, rbx
0x1400156a3  jz      short loc_1400156D5
0x1400156a5  test    byte ptr [rax+1Ch], 1
0x1400156a9  jz      short loc_1400156D5
0x1400156ab  cmp     byte ptr [rax+19h], 5
0x1400156af  jb      short loc_1400156D5
0x1400156b1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400156b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400156bd  lea     r8, WPP_355c378141323d6b66da1816bd4a5ba5_Traceguids
0x1400156c4  mov     edx, 0Ah
0x1400156c9  mov     r9d, eax
0x1400156cc  mov     rcx, [rcx+10h]
0x1400156d0  call    WPP_SF_d
0x1400156d5  lea     r8, aRdpclipalready; "RdpClipAlreadyRunningMutex"
0x1400156dc  xor     edx, edx; bInitialOwner
0x1400156de  xor     ecx, ecx; lpMutexAttributes
0x1400156e0  call    cs:__imp_CreateMutexW
0x1400156e6  mov     cs:?g_hAlreadyRunningMutex@@3PEAXEA, rax; void * g_hAlreadyRunningMutex
0x1400156ed  call    cs:__imp_GetLastError
0x1400156f3  mov     rcx, cs:?g_hAlreadyRunningMutex@@3PEAXEA; void * g_hAlreadyRunningMutex
0x1400156fa  test    rcx, rcx
0x1400156fd  jnz     short loc_14001570D
0x1400156ff  test    eax, eax
0x140015701  jle     short loc_140015771
0x140015703  movzx   eax, ax
0x140015706  or      eax, 80070000h
0x14001570b  jmp     short loc_140015771
0x14001570d  cmp     eax, 0B7h
0x140015712  jnz     short loc_14001576F
0x140015714  mov     rax, cs:WPP_GLOBAL_Control
0x14001571b  cmp     rax, rbx
0x14001571e  jz      short loc_140015757
0x140015720  test    byte ptr [rax+1Ch], 1
0x140015724  jz      short loc_140015757
0x140015726  cmp     byte ptr [rax+19h], 2
0x14001572a  jb      short loc_140015757
0x14001572c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140015731  mov     rcx, cs:WPP_GLOBAL_Control
0x140015738  lea     r8, WPP_355c378141323d6b66da1816bd4a5ba5_Traceguids
0x14001573f  mov     edx, 0Bh
0x140015744  mov     r9d, eax
0x140015747  mov     rcx, [rcx+10h]
0x14001574b  call    WPP_SF_d
0x140015750  mov     rcx, cs:?g_hAlreadyRunningMutex@@3PEAXEA; hObject
0x140015757  call    cs:__imp_CloseHandle
0x14001575d  mov     eax, 800700B7h
0x140015762  mov     cs:?g_hAlreadyRunningMutex@@3PEAXEA, 0; void * g_hAlreadyRunningMutex
0x14001576d  jmp     short loc_140015771
0x14001576f  xor     eax, eax
0x140015771  add     rsp, 20h
0x140015775  pop     rbx
0x140015776  retn
```
