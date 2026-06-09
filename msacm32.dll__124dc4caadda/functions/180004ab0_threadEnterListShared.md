# threadEnterListShared

- ea: `0x180004ab0`
- end: `0x180004ae2`
- name: `threadEnterListShared`
- size: `50`
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

- `0x180004ab0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180004ada`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180004ada`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004aca`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004aca`

## pseudocode

```c
void __fastcall threadEnterListShared(__int64 a1)
{
  DWORD v2; // ecx
  char *Value; // rax

  v2 = *(_DWORD *)(a1 + 208);
  if ( v2 != -1 )
  {
    Value = (char *)TlsGetValue(v2);
    TlsSetValue(*(_DWORD *)(a1 + 208), Value + 1);
  }
}

```

## disassembly

```asm
0x180004ab0  push    rbx
0x180004ab2  sub     rsp, 20h
0x180004ab6  mov     rbx, rcx
0x180004ab9  mov     ecx, [rcx+0D0h]; dwTlsIndex
0x180004abf  cmp     ecx, 0FFFFFFFFh
0x180004ac2  jnz     short loc_180004ACA
0x180004ac4  add     rsp, 20h
0x180004ac8  pop     rbx
0x180004ac9  retn
0x180004aca  call    cs:__imp_TlsGetValue
0x180004ad0  mov     ecx, [rbx+0D0h]; dwTlsIndex
0x180004ad6  lea     rdx, [rax+1]; lpTlsValue
0x180004ada  call    cs:__imp_TlsSetValue
0x180004ae0  jmp     short loc_180004AC4
```
