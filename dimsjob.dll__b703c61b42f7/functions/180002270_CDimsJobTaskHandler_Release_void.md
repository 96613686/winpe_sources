# CDimsJobTaskHandler::Release(void)

- ea: `0x180002270`
- end: `0x1800022ae`
- name: `?Release@CDimsJobTaskHandler@@UEAAKXZ`
- size: `62`
- prototype: `__int64 __fastcall(volatile signed __int32 *hMem)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002270`
- `0x1800022f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800022a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800022a6`

## pseudocode

```c
__int64 __fastcall CDimsJobTaskHandler::Release(volatile signed __int32 *hMem)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(hMem + 15);
  if ( !v2 && hMem )
  {
    CDimsJobTaskHandler::~CDimsJobTaskHandler((CDimsJobTaskHandler *)hMem);
    LocalFree((HLOCAL)hMem);
  }
  return v2;
}

```

## disassembly

```asm
0x180002270  mov     [rsp+arg_0], rbx
0x180002275  push    rdi
0x180002276  sub     rsp, 20h
0x18000227a  mov     rdi, rcx
0x18000227d  mov     ebx, 0FFFFFFFFh
0x180002282  lock xadd [rcx+3Ch], ebx
0x180002287  sub     ebx, 1
0x18000228a  jz      short loc_180002299
0x18000228c  mov     eax, ebx
0x18000228e  mov     rbx, [rsp+28h+arg_0]
0x180002293  add     rsp, 20h
0x180002297  pop     rdi
0x180002298  retn
0x180002299  test    rdi, rdi
0x18000229c  jz      short loc_18000228C
0x18000229e  call    ??1CDimsJobTaskHandler@@IEAA@XZ; CDimsJobTaskHandler::~CDimsJobTaskHandler(void)
0x1800022a3  mov     rcx, rdi; hMem
0x1800022a6  call    cs:__imp_LocalFree
0x1800022ac  jmp     short loc_18000228C
```
