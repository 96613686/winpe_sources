# PEvtStopService(void)

- ea: `0x1800053f0`
- end: `0x180005453`
- name: `?PEvtStopService@@YAJXZ`
- size: `99`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004ba8`
- `0x180011cd0`

## callees

- `0x1800053f0`
- `0x180012d0c`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000542f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000542f`

## pseudocode

```c
__int64 PEvtStopService(void)
{
  __int64 result; // rax
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp+8h] BYREF

  result = 2147549183LL;
  if ( g_pPixEvtCtrlBlk )
  {
    PEvtSetState(1);
    if ( *((_DWORD *)g_pPixEvtCtrlBlk + 2) == 1 )
    {
      PerformanceCount.QuadPart = 0;
      QueryPerformanceCounter(&PerformanceCount);
      *((LARGE_INTEGER *)g_pPixEvtCtrlBlk + 1096) = PerformanceCount;
      return 0;
    }
    else
    {
      return 2147942487LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800053f0  sub     rsp, 28h
0x1800053f4  cmp     cs:?g_pPixEvtCtrlBlk@@3PEAUPEvtCtrlBlk@@EA, 0; PEvtCtrlBlk * g_pPixEvtCtrlBlk
0x1800053fc  mov     eax, 8000FFFFh
0x180005401  jnz     short loc_180005408
0x180005403  add     rsp, 28h
0x180005407  retn
0x180005408  mov     ecx, 1
0x18000540d  call    ?PEvtSetState@@YA?AW4PEvtCommand@@W41@@Z; PEvtSetState(PEvtCommand)
0x180005412  mov     rax, cs:?g_pPixEvtCtrlBlk@@3PEAUPEvtCtrlBlk@@EA; PEvtCtrlBlk * g_pPixEvtCtrlBlk
0x180005419  mov     ecx, [rax+8]
0x18000541c  cmp     ecx, 1
0x18000541f  jnz     short loc_18000544C
0x180005421  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x180005426  mov     qword ptr [rsp+28h+PerformanceCount], 0
0x18000542f  call    cs:__imp_QueryPerformanceCounter
0x180005435  mov     rax, cs:?g_pPixEvtCtrlBlk@@3PEAUPEvtCtrlBlk@@EA; PEvtCtrlBlk * g_pPixEvtCtrlBlk
0x18000543c  mov     rcx, qword ptr [rsp+28h+PerformanceCount]
0x180005441  mov     [rax+2240h], rcx
0x180005448  xor     eax, eax
0x18000544a  jmp     short loc_180005403
0x18000544c  mov     eax, 80070057h
0x180005451  jmp     short loc_180005403
```
