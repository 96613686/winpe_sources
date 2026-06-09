# threadLeaveListShared

- ea: `0x1800021e0`
- end: `0x180002216`
- name: `threadLeaveListShared`
- size: `54`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180002540`
- `0x180002900`
- `0x180002b00`
- `0x180002e70`
- `0x180007ef0`
- `0x180008160`
- `0x1800089c0`
- `0x18000ad3c`
- `0x18000b8d0`
- `0x18000bca0`
- `0x18000c130`
- `0x18000cfe0`
- `0x18000d7b0`

## callees

- `0x1800021e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180002209`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800021f4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800021f4`

## pseudocode

```c
void __fastcall threadLeaveListShared(__int64 a1)
{
  DWORD v2; // ecx
  char *Value; // rax

  v2 = *(_DWORD *)(a1 + 208);
  if ( v2 != -1 )
  {
    Value = (char *)TlsGetValue(v2);
    TlsSetValue(*(_DWORD *)(a1 + 208), Value - 1);
  }
}

```

## disassembly

```asm
0x1800021e0  push    rbx
0x1800021e2  sub     rsp, 20h
0x1800021e6  mov     rbx, rcx
0x1800021e9  mov     ecx, [rcx+0D0h]; dwTlsIndex
0x1800021ef  cmp     ecx, 0FFFFFFFFh
0x1800021f2  jz      short loc_180002210
0x1800021f4  call    cs:__imp_TlsGetValue
0x1800021fa  mov     ecx, [rbx+0D0h]
0x180002200  lea     rdx, [rax-1]
0x180002204  add     rsp, 20h
0x180002208  pop     rbx
0x180002209  jmp     cs:__imp_TlsSetValue
0x180002210  add     rsp, 20h
0x180002214  pop     rbx
0x180002215  retn
```
