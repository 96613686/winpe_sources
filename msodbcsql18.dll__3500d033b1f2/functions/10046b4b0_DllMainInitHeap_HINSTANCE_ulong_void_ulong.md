# DllMainInitHeap(HINSTANCE__ *,ulong,void *,ulong)

- ea: `0x10046b4b0`
- end: `0x10046b5ee`
- name: `?DllMainInitHeap@@YAHPEAUHINSTANCE__@@KPEAXK@Z`
- size: `318`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10046b5f4`

## callees

- `0x10046b4b0`
- `0x100546aa8`

## import_xrefs

- `KERNEL32!HeapCreate` at `0x10046b4e6`
- `KERNEL32!HeapCreate` at `0x10046b4e6`
- `KERNEL32!HeapDestroy` at `0x10046b5d6`
- `KERNEL32!HeapDestroy` at `0x10046b5d6`
- `KERNEL32!GetProcessHeap` at `0x10046b575`
- `KERNEL32!GetProcessHeap` at `0x10046b575`
- `KERNEL32!HeapSetInformation` at `0x10046b514`
- `KERNEL32!HeapSetInformation` at `0x10046b514`
- `KERNEL32!GetLastError` at `0x10046b599`
- `KERNEL32!GetLastError` at `0x10046b599`

## pseudocode

```c
__int64 __fastcall DllMainInitHeap(HINSTANCE a1, int a2, void *a3, int a4)
{
  __int64 result; // rax
  int v5; // eax
  int HeapInformation; // [rsp+48h] [rbp+10h] BYREF

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
        if ( off_1005E6C10[0] )
          bidTraceW(0, 114688, off_1005E6C10[0], g_hHeapMalloc);
      }
    }
    else if ( (bidGblFlags & 2) != 0 && off_1005E6C18[0] )
    {
      GetLastError();
      bidTraceW(0, 119808, off_1005E6C18[0], g_hHeapMalloc);
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x10046b4b0  sub     rsp, 38h
0x10046b4b4  test    edx, edx
0x10046b4b6  jz      loc_10046B5C1
0x10046b4bc  cmp     edx, 1
0x10046b4bf  jnz     loc_10046B5E4
0x10046b4c5  test    r9d, r9d
0x10046b4c8  jz      loc_10046B562
0x10046b4ce  cmp     r9d, edx
0x10046b4d1  jnz     loc_10046B55A
0x10046b4d7  and     cs:?g_fDisableMpHeap@@3HA, 0; int g_fDisableMpHeap
0x10046b4de  xor     edx, edx; dwInitialSize
0x10046b4e0  xor     r8d, r8d; dwMaximumSize
0x10046b4e3  lea     ecx, [rdx+2]; flOptions
0x10046b4e6  call    cs:__imp_HeapCreate
0x10046b4ec  mov     cs:?g_hHeapMalloc@@3PEAXEA, rax; void * g_hHeapMalloc
0x10046b4f3  test    rax, rax
0x10046b4f6  jz      loc_10046B5BF
0x10046b4fc  mov     r9d, 4; HeapInformationLength
0x10046b502  mov     [rsp+38h+HeapInformation], 2
0x10046b50a  lea     r8, [rsp+38h+HeapInformation]; HeapInformation
0x10046b50f  xor     edx, edx; HeapInformationClass
0x10046b511  mov     rcx, rax; HeapHandle
0x10046b514  call    cs:__imp_HeapSetInformation
0x10046b51a  test    eax, eax
0x10046b51c  jz      short loc_10046B584
0x10046b51e  test    byte ptr cs:_bidGblFlags, 2
0x10046b525  jz      loc_10046B5E4
0x10046b52b  mov     rax, cs:off_1005E6C10; "<DllMainInitHeap|HEAP|INFO> LFH is enab"...
0x10046b532  test    rax, rax
0x10046b535  jz      loc_10046B5E4
0x10046b53b  mov     r9, cs:?g_hHeapMalloc@@3PEAXEA; void * g_hHeapMalloc
0x10046b542  mov     edx, 1C000h
0x10046b547  mov     r8, cs:off_1005E6C10; "<DllMainInitHeap|HEAP|INFO> LFH is enab"...
0x10046b54e  xor     ecx, ecx
0x10046b550  call    _bidTraceW
0x10046b555  jmp     loc_10046B5E4
0x10046b55a  mov     eax, cs:?g_fDisableMpHeap@@3HA; int g_fDisableMpHeap
0x10046b560  jmp     short loc_10046B56D
0x10046b562  mov     eax, 1
0x10046b567  mov     cs:?g_fDisableMpHeap@@3HA, eax; int g_fDisableMpHeap
0x10046b56d  test    eax, eax
0x10046b56f  jz      loc_10046B4DE
0x10046b575  call    cs:__imp_GetProcessHeap
0x10046b57b  mov     cs:?g_hHeapMalloc@@3PEAXEA, rax; void * g_hHeapMalloc
0x10046b582  jmp     short loc_10046B5E4
0x10046b584  test    byte ptr cs:_bidGblFlags, 2
0x10046b58b  jz      short loc_10046B5E4
0x10046b58d  mov     rax, cs:off_1005E6C18; "<DllMainInitHeap|HEAP|INFO> LFH cannot "...
0x10046b594  test    rax, rax
0x10046b597  jz      short loc_10046B5E4
0x10046b599  call    cs:__imp_GetLastError
0x10046b59f  mov     r9, cs:?g_hHeapMalloc@@3PEAXEA; void * g_hHeapMalloc
0x10046b5a6  mov     edx, 1D400h
0x10046b5ab  mov     r8, cs:off_1005E6C18; "<DllMainInitHeap|HEAP|INFO> LFH cannot "...
0x10046b5b2  xor     ecx, ecx
0x10046b5b4  mov     [rsp+38h+var_18], eax
0x10046b5b8  call    _bidTraceW
0x10046b5bd  jmp     short loc_10046B5E4
0x10046b5bf  jmp     short loc_10046B5E9
0x10046b5c1  cmp     cs:?g_fDisableMpHeap@@3HA, 0; int g_fDisableMpHeap
0x10046b5c8  jnz     short loc_10046B5E4
0x10046b5ca  test    r8, r8
0x10046b5cd  jnz     short loc_10046B5E4
0x10046b5cf  mov     rcx, cs:?g_hHeapMalloc@@3PEAXEA; hHeap
0x10046b5d6  call    cs:__imp_HeapDestroy
0x10046b5dc  and     cs:?g_hHeapMalloc@@3PEAXEA, 0; void * g_hHeapMalloc
0x10046b5e4  mov     eax, 1
0x10046b5e9  add     rsp, 38h
0x10046b5ed  retn
```
