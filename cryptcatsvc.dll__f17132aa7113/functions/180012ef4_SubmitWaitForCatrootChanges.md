# SubmitWaitForCatrootChanges

- ea: `0x180012ef4`
- end: `0x180012f5e`
- name: `SubmitWaitForCatrootChanges`
- size: `106`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012f70`
- `0x1800131b8`

## callees

- `0x180012ef4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180012f4d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180012f4d`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x180012f39`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x180012f39`

## pseudocode

```c
void __fastcall SubmitWaitForCatrootChanges(PTP_WAIT pwa, __int64 a2)
{
  if ( ReadDirectoryChangesW(*(HANDLE *)a2, (LPVOID)(a2 + 40), 0x1000u, 1, 0x19u, 0, (LPOVERLAPPED)(a2 + 8), 0) )
    SetThreadpoolWait(pwa, *(HANDLE *)(a2 + 32), 0);
}

```

## disassembly

```asm
0x180012ef4  mov     r11, rsp
0x180012ef7  mov     [r11+8], rbx
0x180012efb  push    rdi
0x180012efc  sub     rsp, 40h
0x180012f00  mov     qword ptr [r11-10h], 0
0x180012f08  lea     rax, [rdx+8]
0x180012f0c  mov     rbx, rdx
0x180012f0f  mov     [r11-18h], rax
0x180012f13  mov     rdi, rcx
0x180012f16  mov     qword ptr [r11-20h], 0
0x180012f1e  add     rdx, 28h ; '('; lpBuffer
0x180012f22  mov     [rsp+48h+dwNotifyFilter], 19h; dwNotifyFilter
0x180012f2a  mov     r9d, 1; bWatchSubtree
0x180012f30  mov     r8d, 1000h; nBufferLength
0x180012f36  mov     rcx, [rbx]; hDirectory
0x180012f39  call    cs:__imp_ReadDirectoryChangesW
0x180012f3f  test    eax, eax
0x180012f41  jz      short loc_180012F53
0x180012f43  mov     rdx, [rbx+20h]; h
0x180012f47  xor     r8d, r8d; pftTimeout
0x180012f4a  mov     rcx, rdi; pwa
0x180012f4d  call    cs:__imp_SetThreadpoolWait
0x180012f53  mov     rbx, [rsp+48h+arg_0]
0x180012f58  add     rsp, 40h
0x180012f5c  pop     rdi
0x180012f5d  retn
```
