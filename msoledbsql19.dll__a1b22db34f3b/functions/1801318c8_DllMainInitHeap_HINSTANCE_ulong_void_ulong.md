# DllMainInitHeap(HINSTANCE__ *,ulong,void *,ulong)

- ea: `0x1801318c8`
- end: `0x180131a2c`
- name: `?DllMainInitHeap@@YAHPEAUHINSTANCE__@@KPEAXK@Z`
- size: `356`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180131a34`

## callees

- `0x1800030c0`
- `0x180003d80`
- `0x1801318c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801319c5`
- `KERNEL32!GetLastError` at `0x1801319c5`
- `KERNEL32!HeapSetInformation` at `0x18013193b`
- `KERNEL32!HeapSetInformation` at `0x18013193b`
- `KERNEL32!GetProcessHeap` at `0x1801319a1`
- `KERNEL32!GetProcessHeap` at `0x1801319a1`
- `KERNEL32!HeapDestroy` at `0x180131a07`
- `KERNEL32!HeapDestroy` at `0x180131a07`
- `KERNEL32!HeapCreate` at `0x18013190d`
- `KERNEL32!HeapCreate` at `0x18013190d`

## pseudocode

```c
__int64 __fastcall DllMainInitHeap(HINSTANCE a1, int a2, void *a3, int a4)
{
  __int64 result; // rax
  int v5; // eax
  int HeapInformation; // [rsp+30h] [rbp-18h] BYREF

  if ( !a2 )
  {
    if ( !g_fDisableMpHeap && !a3 )
    {
      HeapDestroy(g_hHeapMalloc);
      g_hHeapMalloc = 0;
    }
    return 1;
  }
  if ( a2 != 1 )
    return 1;
  if ( a4 )
  {
    if ( a4 == 1 )
    {
      g_fDisableMpHeap = 0;
      goto LABEL_6;
    }
    v5 = g_fDisableMpHeap;
  }
  else
  {
    v5 = 1;
    g_fDisableMpHeap = 1;
  }
  if ( v5 )
  {
    g_hHeapMalloc = GetProcessHeap();
    return 1;
  }
LABEL_6:
  result = (__int64)HeapCreate(2u, 0, 0);
  g_hHeapMalloc = (HANDLE)result;
  if ( result )
  {
    HeapInformation = 2;
    if ( HeapSetInformation((HANDLE)result, HeapCompatibilityInformation, &HeapInformation, 4u) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180263A58[0] )
          bidTraceW(off_1802606E8[0], 101376, off_180263A58[0], g_hHeapMalloc);
      }
    }
    else if ( (bidGblFlags & 2) != 0 && off_180263A60[0] )
    {
      GetLastError();
      bidTraceW(off_1802606E8[0], 106496, off_180263A60[0], g_hHeapMalloc);
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1801318c8  sub     rsp, 48h
0x1801318cc  mov     rax, cs:__security_cookie
0x1801318d3  xor     rax, rsp
0x1801318d6  mov     [rsp+48h+var_10], rax
0x1801318db  test    edx, edx
0x1801318dd  jz      loc_1801319F2
0x1801318e3  cmp     edx, 1
0x1801318e6  jnz     loc_180131A15
0x1801318ec  test    r9d, r9d
0x1801318ef  jz      loc_18013198E
0x1801318f5  cmp     r9d, edx
0x1801318f8  jnz     loc_180131986
0x1801318fe  and     cs:?g_fDisableMpHeap@@3HA, 0; int g_fDisableMpHeap
0x180131905  xor     edx, edx; dwInitialSize
0x180131907  xor     r8d, r8d; dwMaximumSize
0x18013190a  lea     ecx, [rdx+2]; flOptions
0x18013190d  call    cs:__imp_HeapCreate
0x180131913  mov     cs:?g_hHeapMalloc@@3PEAXEA, rax; void * g_hHeapMalloc
0x18013191a  test    rax, rax
0x18013191d  jz      loc_1801319F0
0x180131923  mov     r9d, 4; HeapInformationLength
0x180131929  mov     [rsp+48h+HeapInformation], 2
0x180131931  lea     r8, [rsp+48h+HeapInformation]; HeapInformation
0x180131936  xor     edx, edx; HeapInformationClass
0x180131938  mov     rcx, rax; HeapHandle
0x18013193b  call    cs:__imp_HeapSetInformation
0x180131941  test    eax, eax
0x180131943  jz      short loc_1801319B0
0x180131945  test    byte ptr cs:_bidGblFlags, 2
0x18013194c  jz      loc_180131A15
0x180131952  mov     rax, cs:off_180263A58; "<DllMainInitHeap|HEAP|INFO> LFH is enab"...
0x180131959  test    rax, rax
0x18013195c  jz      loc_180131A15
0x180131962  mov     r8, cs:off_180263A58; "<DllMainInitHeap|HEAP|INFO> LFH is enab"...
0x180131969  mov     edx, 18C00h
0x18013196e  mov     rcx, cs:off_1802606E8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ms"...
0x180131975  mov     r9, cs:?g_hHeapMalloc@@3PEAXEA; void * g_hHeapMalloc
0x18013197c  call    _bidTraceW
0x180131981  jmp     loc_180131A15
0x180131986  mov     eax, cs:?g_fDisableMpHeap@@3HA; int g_fDisableMpHeap
0x18013198c  jmp     short loc_180131999
0x18013198e  mov     eax, 1
0x180131993  mov     cs:?g_fDisableMpHeap@@3HA, eax; int g_fDisableMpHeap
0x180131999  test    eax, eax
0x18013199b  jz      loc_180131905
0x1801319a1  call    cs:__imp_GetProcessHeap
0x1801319a7  mov     cs:?g_hHeapMalloc@@3PEAXEA, rax; void * g_hHeapMalloc
0x1801319ae  jmp     short loc_180131A15
0x1801319b0  test    byte ptr cs:_bidGblFlags, 2
0x1801319b7  jz      short loc_180131A15
0x1801319b9  mov     rax, cs:off_180263A60; "<DllMainInitHeap|HEAP|INFO> LFH cannot "...
0x1801319c0  test    rax, rax
0x1801319c3  jz      short loc_180131A15
0x1801319c5  call    cs:__imp_GetLastError
0x1801319cb  mov     r8, cs:off_180263A60; "<DllMainInitHeap|HEAP|INFO> LFH cannot "...
0x1801319d2  mov     edx, 1A000h
0x1801319d7  mov     rcx, cs:off_1802606E8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ms"...
0x1801319de  mov     r9, cs:?g_hHeapMalloc@@3PEAXEA; void * g_hHeapMalloc
0x1801319e5  mov     [rsp+48h+var_28], eax
0x1801319e9  call    _bidTraceW
0x1801319ee  jmp     short loc_180131A15
0x1801319f0  jmp     short loc_180131A1A
0x1801319f2  cmp     cs:?g_fDisableMpHeap@@3HA, 0; int g_fDisableMpHeap
0x1801319f9  jnz     short loc_180131A15
0x1801319fb  test    r8, r8
0x1801319fe  jnz     short loc_180131A15
0x180131a00  mov     rcx, cs:?g_hHeapMalloc@@3PEAXEA; hHeap
0x180131a07  call    cs:__imp_HeapDestroy
0x180131a0d  and     cs:?g_hHeapMalloc@@3PEAXEA, 0; void * g_hHeapMalloc
0x180131a15  mov     eax, 1
0x180131a1a  mov     rcx, [rsp+48h+var_10]
0x180131a1f  xor     rcx, rsp; StackCookie
0x180131a22  call    __security_check_cookie
0x180131a27  add     rsp, 48h
0x180131a2b  retn
```
