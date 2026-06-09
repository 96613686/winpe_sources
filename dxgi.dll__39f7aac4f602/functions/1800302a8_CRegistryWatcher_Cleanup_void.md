# CRegistryWatcher::Cleanup(void)

- ea: `0x1800302a8`
- end: `0x18003030e`
- name: `?Cleanup@CRegistryWatcher@@AEAAXXZ`
- size: `102`
- prototype: `void __fastcall(CRegistryWatcher *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002fcbc`
- `0x1800301d0`
- `0x1800301dc`

## callees

- `0x1800302a8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800302d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800302d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800302df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800302df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800302fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800302fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800302ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800302ee`

## pseudocode

```c
void __fastcall CRegistryWatcher::Cleanup(PTP_WAIT *this)
{
  struct _TP_WAIT *v2; // rcx
  HKEY v3; // rcx
  PTP_WAIT v4; // rcx

  v2 = *this;
  if ( v2 )
  {
    WaitForThreadpoolWaitCallbacks(v2, 1);
    CloseThreadpoolWait(*this);
    *this = 0;
  }
  v3 = (HKEY)this[3];
  if ( v3 )
  {
    RegCloseKey(v3);
    this[3] = 0;
  }
  v4 = this[4];
  if ( v4 )
  {
    CloseHandle(v4);
    this[4] = 0;
  }
}

```

## disassembly

```asm
0x1800302a8  push    rbx
0x1800302aa  sub     rsp, 20h
0x1800302ae  mov     rbx, rcx
0x1800302b1  mov     rcx, [rcx]; pwa
0x1800302b4  test    rcx, rcx
0x1800302b7  jnz     short loc_1800302D1
0x1800302b9  mov     rcx, [rbx+18h]; hKey
0x1800302bd  test    rcx, rcx
0x1800302c0  jnz     short loc_1800302EE
0x1800302c2  mov     rcx, [rbx+20h]; hObject
0x1800302c6  test    rcx, rcx
0x1800302c9  jnz     short loc_1800302FE
0x1800302cb  add     rsp, 20h
0x1800302cf  pop     rbx
0x1800302d0  retn
0x1800302d1  mov     edx, 1; fCancelPendingCallbacks
0x1800302d6  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800302dc  mov     rcx, [rbx]; pwa
0x1800302df  call    cs:__imp_CloseThreadpoolWait
0x1800302e5  mov     qword ptr [rbx], 0
0x1800302ec  jmp     short loc_1800302B9
0x1800302ee  call    cs:__imp_RegCloseKey
0x1800302f4  mov     qword ptr [rbx+18h], 0
0x1800302fc  jmp     short loc_1800302C2
0x1800302fe  call    cs:__imp_CloseHandle
0x180030304  mov     qword ptr [rbx+20h], 0
0x18003030c  jmp     short loc_1800302CB
```
