# DfsRootFolder::UpdateLinkInformationPrologue(ulong)

- ea: `0x14000b4bc`
- end: `0x14000b563`
- name: `?UpdateLinkInformationPrologue@DfsRootFolder@@QEAAKK@Z`
- size: `167`
- prototype: `unsigned int __fastcall(DfsRootFolder *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000a6cc`
- `0x140021460`
- `0x1400448ec`

## callees

- `0x14000b4bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b4e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b50c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b4e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b50c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14000b4d2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14000b4d2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x14000b4f4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x14000b4f4`

## pseudocode

```c
unsigned int __fastcall DfsRootFolder::UpdateLinkInformationPrologue(HANDLE *this, int a2)
{
  unsigned int result; // eax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax

  if ( !ResetEvent(this[50]) )
    return GetLastError();
  if ( !a2 )
    goto LABEL_8;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  this[40] = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup )
  {
    this[43] = ThreadpoolCleanupGroup;
    this[44] = DfsThreadpoolSimpleWorkCancellationCallback;
    goto LABEL_8;
  }
  result = GetLastError();
  if ( !result )
  {
LABEL_8:
    *((_DWORD *)this + 102) = 0;
    *((_DWORD *)this + 104) = 0;
    *((_DWORD *)this + 105) = 0;
    *((_DWORD *)this + 106) = 0;
    result = 0;
    *((_DWORD *)this + 103) = a2;
  }
  return result;
}

```

## disassembly

```asm
0x14000b4bc  mov     [rsp+arg_0], rbx
0x14000b4c1  push    rdi
0x14000b4c2  sub     rsp, 20h
0x14000b4c6  mov     rbx, rcx
0x14000b4c9  mov     edi, edx
0x14000b4cb  mov     rcx, [rcx+190h]; hEvent
0x14000b4d2  call    cs:__imp_ResetEvent
0x14000b4d9  nop     dword ptr [rax+rax+00h]
0x14000b4de  test    eax, eax
0x14000b4e0  jnz     short loc_14000B4F0
0x14000b4e2  call    cs:__imp_GetLastError
0x14000b4e9  nop     dword ptr [rax+rax+00h]
0x14000b4ee  jmp     short loc_14000B557
0x14000b4f0  test    edi, edi
0x14000b4f2  jz      short loc_14000B533
0x14000b4f4  call    cs:__imp_CreateThreadpoolCleanupGroup
0x14000b4fb  nop     dword ptr [rax+rax+00h]
0x14000b500  mov     [rbx+140h], rax
0x14000b507  test    rax, rax
0x14000b50a  jnz     short loc_14000B51E
0x14000b50c  call    cs:__imp_GetLastError
0x14000b513  nop     dword ptr [rax+rax+00h]
0x14000b518  test    eax, eax
0x14000b51a  jz      short loc_14000B533
0x14000b51c  jmp     short loc_14000B557
0x14000b51e  mov     [rbx+158h], rax
0x14000b525  lea     rax, ?DfsThreadpoolSimpleWorkCancellationCallback@@YAXPEAX0@Z; DfsThreadpoolSimpleWorkCancellationCallback(void *,void *)
0x14000b52c  mov     [rbx+160h], rax
0x14000b533  and     dword ptr [rbx+198h], 0
0x14000b53a  and     dword ptr [rbx+1A0h], 0
0x14000b541  and     dword ptr [rbx+1A4h], 0
0x14000b548  and     dword ptr [rbx+1A8h], 0
0x14000b54f  xor     eax, eax
0x14000b551  mov     [rbx+19Ch], edi
0x14000b557  mov     rbx, [rsp+28h+arg_0]
0x14000b55c  add     rsp, 20h
0x14000b560  pop     rdi
0x14000b561  retn
```
