# PEvtStartServiceEx(ulong)

- ea: `0x180012d98`
- end: `0x180012e28`
- name: `?PEvtStartServiceEx@@YAJK@Z`
- size: `144`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180011cd0`
- `0x180012a0c`

## callees

- `0x180012d0c`
- `0x180012d98`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012dd9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012dd9`

## pseudocode

```c
__int64 __fastcall PEvtStartServiceEx()
{
  __int64 result; // rax
  _QWORD *v1; // rcx
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+10h] BYREF

  result = 2147549183LL;
  if ( g_pPixEvtCtrlBlk )
  {
    if ( (unsigned int)PEvtSetState(0) )
    {
      if ( *((_DWORD *)g_pPixEvtCtrlBlk + 2) )
      {
        return 2147942487LL;
      }
      else
      {
        PerformanceCount.QuadPart = 0;
        QueryPerformanceCounter(&PerformanceCount);
        v1 = g_pPixEvtCtrlBlk;
        *((LARGE_INTEGER *)g_pPixEvtCtrlBlk + 1095) = PerformanceCount;
        v1[1096] = -1;
        *((_WORD *)v1 + 4374) = -1;
        *((_WORD *)v1 + 4375) = -1;
        result = 0;
        *((_DWORD *)v1 + 18580) = 0;
      }
    }
    else
    {
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012d98  sub     rsp, 28h
0x180012d9c  cmp     cs:?g_pPixEvtCtrlBlk@@3PEAUPEvtCtrlBlk@@EA, 0; PEvtCtrlBlk * g_pPixEvtCtrlBlk
0x180012da4  mov     eax, 8000FFFFh
0x180012da9  jz      short loc_180012E23
0x180012dab  xor     ecx, ecx
0x180012dad  call    ?PEvtSetState@@YA?AW4PEvtCommand@@W41@@Z; PEvtSetState(PEvtCommand)
0x180012db2  test    eax, eax
0x180012db4  jnz     short loc_180012DBD
0x180012db6  mov     eax, 1
0x180012dbb  jmp     short loc_180012E23
0x180012dbd  mov     rax, cs:?g_pPixEvtCtrlBlk@@3PEAUPEvtCtrlBlk@@EA; PEvtCtrlBlk * g_pPixEvtCtrlBlk
0x180012dc4  mov     ecx, [rax+8]
0x180012dc7  test    ecx, ecx
0x180012dc9  jnz     short loc_180012E1E
0x180012dcb  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x180012dd0  mov     qword ptr [rsp+28h+PerformanceCount], 0
0x180012dd9  call    cs:__imp_QueryPerformanceCounter
0x180012ddf  mov     rax, qword ptr [rsp+28h+PerformanceCount]
0x180012de4  mov     rcx, cs:?g_pPixEvtCtrlBlk@@3PEAUPEvtCtrlBlk@@EA; PEvtCtrlBlk * g_pPixEvtCtrlBlk
0x180012deb  mov     [rcx+2238h], rax
0x180012df2  mov     eax, 0FFFFh
0x180012df7  mov     qword ptr [rcx+2240h], 0FFFFFFFFFFFFFFFFh
0x180012e02  mov     [rcx+222Ch], ax
0x180012e09  mov     [rcx+222Eh], ax
0x180012e10  xor     eax, eax
0x180012e12  mov     dword ptr [rcx+12250h], 0
0x180012e1c  jmp     short loc_180012E23
0x180012e1e  mov     eax, 80070057h
0x180012e23  add     rsp, 28h
0x180012e27  retn
```
