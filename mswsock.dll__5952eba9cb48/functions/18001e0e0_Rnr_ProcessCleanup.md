# Rnr_ProcessCleanup

- ea: `0x18001e0e0`
- end: `0x18001e144`
- name: `Rnr_ProcessCleanup`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dbb0`
- `0x180020d30`

## callees

- `0x18001cd8c`
- `0x18001e0e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e102`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e128`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e102`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e128`

## pseudocode

```c
void Rnr_ProcessCleanup()
{
  if ( g_fRnrLockInit )
  {
    Nsp_GlobalCleanup();
    if ( g_fRnrLockInit )
    {
      DeleteCriticalSection(&g_RnrLock);
      g_fRnrLockInit = 0;
    }
  }
  if ( g_fSocketLockInit )
  {
    DeleteCriticalSection(&RNRPROV_SocketLock);
    g_fSocketLockInit = 0;
  }
}

```

## disassembly

```asm
0x18001e0e0  sub     rsp, 28h
0x18001e0e4  cmp     cs:g_fRnrLockInit, 0
0x18001e0eb  jz      short loc_18001E118
0x18001e0ed  call    Nsp_GlobalCleanup
0x18001e0f2  cmp     cs:g_fRnrLockInit, 0
0x18001e0f9  jz      short loc_18001E118
0x18001e0fb  lea     rcx, g_RnrLock; lpCriticalSection
0x18001e102  call    cs:__imp_DeleteCriticalSection
0x18001e109  nop     dword ptr [rax+rax+00h]
0x18001e10e  mov     cs:g_fRnrLockInit, 0
0x18001e118  cmp     cs:g_fSocketLockInit, 0
0x18001e11f  jz      short loc_18001E13E
0x18001e121  lea     rcx, RNRPROV_SocketLock; lpCriticalSection
0x18001e128  call    cs:__imp_DeleteCriticalSection
0x18001e12f  nop     dword ptr [rax+rax+00h]
0x18001e134  mov     cs:g_fSocketLockInit, 0
0x18001e13e  add     rsp, 28h
0x18001e142  retn
```
