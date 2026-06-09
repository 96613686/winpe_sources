# threadQueryInListShared

- ea: `0x1800023c0`
- end: `0x1800023eb`
- name: `threadQueryInListShared`
- size: `43`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002900`
- `0x1800089c0`
- `0x180008c00`
- `0x180008d00`
- `0x18000da50`

## callees

- `0x1800023c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800023cf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800023cf`

## pseudocode

```c
_BOOL8 __fastcall threadQueryInListShared(__int64 a1)
{
  DWORD v1; // ecx

  v1 = *(_DWORD *)(a1 + 208);
  return v1 != -1 && TlsGetValue(v1) != 0;
}

```

## disassembly

```asm
0x1800023c0  sub     rsp, 28h
0x1800023c4  mov     ecx, [rcx+0D0h]; dwTlsIndex
0x1800023ca  cmp     ecx, 0FFFFFFFFh
0x1800023cd  jz      short loc_1800023E4
0x1800023cf  call    cs:__imp_TlsGetValue
0x1800023d5  xor     ecx, ecx
0x1800023d7  test    rax, rax
0x1800023da  setnz   cl
0x1800023dd  mov     eax, ecx
0x1800023df  add     rsp, 28h
0x1800023e3  retn
0x1800023e4  xor     eax, eax
0x1800023e6  add     rsp, 28h
0x1800023ea  retn
```
