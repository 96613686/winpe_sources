# DfsRootFolder::UpdateLinkInformationEpilogue(void)

- ea: `0x14000b40c`
- end: `0x14000b49c`
- name: `?UpdateLinkInformationEpilogue@DfsRootFolder@@QEAAKXZ`
- size: `144`
- prototype: `unsigned int __fastcall(DfsRootFolder *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000a6cc`
- `0x140021460`
- `0x1400448ec`

## callees

- `0x14000b3b8`
- `0x14000b40c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14000b44b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14000b44b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x14000b47b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x14000b47b`

## pseudocode

```c
__int64 __fastcall DfsRootFolder::UpdateLinkInformationEpilogue(DfsRootFolder *this)
{
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( *((_DWORD *)this + 103) )
  {
    Handles[0] = *((HANDLE *)this + 50);
    Handles[1] = hEvent;
    WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
    if ( HIBYTE(word_140071515) )
    {
      DfsRootFolder::UpdateLinkInformationCancel((PTP_CLEANUP_GROUP *)this);
      *((_DWORD *)this + 102) = 1223;
    }
    else
    {
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 40));
      *((_QWORD *)this + 40) = 0;
    }
  }
  return *((unsigned int *)this + 102);
}

```

## disassembly

```asm
0x14000b40c  push    rbx
0x14000b40e  sub     rsp, 40h
0x14000b412  cmp     dword ptr [rcx+19Ch], 0
0x14000b419  mov     rbx, rcx
0x14000b41c  jz      short loc_14000B48F
0x14000b41e  mov     rax, [rcx+190h]
0x14000b425  lea     rdx, [rsp+48h+Handles]; lpHandles
0x14000b42a  and     [rsp+48h+var_28], 0
0x14000b42f  xor     r8d, r8d; bWaitAll
0x14000b432  mov     [rsp+48h+Handles], rax
0x14000b437  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14000b43b  mov     rax, cs:hEvent
0x14000b442  mov     [rsp+48h+var_10], rax
0x14000b447  lea     ecx, [r8+2]; nCount
0x14000b44b  call    cs:__imp_WaitForMultipleObjectsEx
0x14000b452  nop     dword ptr [rax+rax+00h]
0x14000b457  cmp     byte ptr cs:word_140071515+1, 0
0x14000b45e  jz      short loc_14000B474
0x14000b460  mov     rcx, rbx; this
0x14000b463  call    ?UpdateLinkInformationCancel@DfsRootFolder@@QEAAXXZ; DfsRootFolder::UpdateLinkInformationCancel(void)
0x14000b468  mov     dword ptr [rbx+198h], 4C7h
0x14000b472  jmp     short loc_14000B48F
0x14000b474  mov     rcx, [rbx+140h]; ptpcg
0x14000b47b  call    cs:__imp_CloseThreadpoolCleanupGroup
0x14000b482  nop     dword ptr [rax+rax+00h]
0x14000b487  and     qword ptr [rbx+140h], 0
0x14000b48f  mov     eax, [rbx+198h]
0x14000b495  add     rsp, 40h
0x14000b499  pop     rbx
0x14000b49a  retn
```
