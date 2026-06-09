# operator new(unsigned __int64)

- ea: `0x14001bff8`
- end: `0x14001c07f`
- name: `??2@YAPEAX_K@Z`
- size: `135`
- prototype: `void *__fastcall(ULONG cjMemSize)`
- caller_count: `9`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140001230`
- `0x140003840`
- `0x14001b6e8`
- `0x14001d980`
- `0x14002d4b4`
- `0x14002fa88`
- `0x140034460`
- `0x14003454c`
- `0x140034838`

## callees

- `0x14001bff8`
- `0x14001c088`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001c027`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001c027`
- `watchdog!WdLogSingleEntry0` at `0x14001c010`
- `watchdog!WdLogSingleEntry0` at `0x14001c010`
- `WIN32K!EngAllocMem` at `0x14001c06c`
- `WIN32K!EngAllocMem` at `0x14001c06c`

## pseudocode

```c
PVOID __fastcall operator new(unsigned __int64 cjMemSize)
{
  ULONG v1; // ebx
  __int64 v2; // rdx
  __int64 v3; // rcx
  _QWORD *v4; // rax
  PVOID result; // rax

  v1 = cjMemSize;
  if ( cjMemSize <= 0xFFFFFFFF )
  {
    Feature_CddInSystemSpace__private_IsEnabledPreCheck();
    return EngAllocMem(5u, v1, 0x64646344u);
  }
  else
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 720;
    v4 = (_QWORD *)WdLogNewEntry5_WdAssertion(v3, v2);
    v4[3] = gCddImageInfo;
    v4[4] = (unsigned int)dword_14003E570;
    v4[5] = 215857758;
    result = 0;
    WdLogGlobalForLineNumber = 720;
  }
  return result;
}

```

## disassembly

```asm
0x14001bff8  push    rbx
0x14001bffa  sub     rsp, 20h
0x14001bffe  mov     eax, 0FFFFFFFFh
0x14001c003  mov     rbx, rcx
0x14001c006  cmp     rcx, rax
0x14001c009  jbe     short loc_14001C05A
0x14001c00b  mov     ecx, 1
0x14001c010  call    cs:__imp_WdLogSingleEntry0
0x14001c017  nop     dword ptr [rax+rax+00h]
0x14001c01c  mov     ebx, 2D0h
0x14001c021  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001c027  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14001c02e  nop     dword ptr [rax+rax+00h]
0x14001c033  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001c03a  mov     [rax+18h], rcx
0x14001c03e  mov     ecx, cs:dword_14003E570
0x14001c044  mov     [rax+20h], rcx
0x14001c048  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001c050  xor     eax, eax
0x14001c052  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001c058  jmp     short loc_14001C078
0x14001c05a  call    Feature_CddInSystemSpace__private_IsEnabledPreCheck
0x14001c05f  mov     edx, ebx; cjMemSize
0x14001c061  mov     ecx, 5; fl
0x14001c066  mov     r8d, 64646344h; ulTag
0x14001c06c  call    cs:__imp_EngAllocMem
0x14001c073  nop     dword ptr [rax+rax+00h]
0x14001c078  add     rsp, 20h
0x14001c07c  pop     rbx
0x14001c07d  retn
```
