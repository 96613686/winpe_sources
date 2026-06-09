# PerflibciExpandPath

- ea: `0x18000d4ac`
- end: `0x18000d52c`
- name: `PerflibciExpandPath`
- size: `128`
- prototype: `DWORD __fastcall(LPCWSTR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000d158`

## callees

- `0x180005da0`
- `0x180008050`
- `0x18000d4ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d50f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d50f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000d4e1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000d4e1`

## pseudocode

```c
DWORD __fastcall PerflibciExpandPath(LPCWSTR *a1)
{
  WCHAR *v2; // rax
  WCHAR *v3; // rbx
  DWORD result; // eax
  DWORD v5; // esi

  v2 = (WCHAR *)operator new(0x208u);
  v3 = v2;
  if ( !v2 )
    return 14;
  v5 = ExpandEnvironmentStringsW(*a1, v2, 0x104u);
  if ( v5 - 1 > 0x103 )
  {
    operator delete(v3);
    if ( v5 )
      return 111;
    else
      return GetLastError();
  }
  else
  {
    operator delete((void *)*a1);
    result = 0;
    *a1 = v3;
  }
  return result;
}

```

## disassembly

```asm
0x18000d4ac  mov     [rsp+arg_0], rbx
0x18000d4b1  mov     [rsp+arg_8], rsi
0x18000d4b6  push    rdi
0x18000d4b7  sub     rsp, 20h
0x18000d4bb  mov     rdi, rcx
0x18000d4be  mov     ecx, 208h
0x18000d4c3  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000d4c8  mov     rbx, rax
0x18000d4cb  test    rax, rax
0x18000d4ce  jnz     short loc_18000D4D5
0x18000d4d0  lea     eax, [rbx+0Eh]
0x18000d4d3  jmp     short loc_18000D51C
0x18000d4d5  mov     rcx, [rdi]; lpSrc
0x18000d4d8  mov     r8d, 104h; nSize
0x18000d4de  mov     rdx, rbx; lpDst
0x18000d4e1  call    cs:__imp_ExpandEnvironmentStringsW
0x18000d4e7  mov     esi, eax
0x18000d4e9  lea     ecx, [rax-1]
0x18000d4ec  cmp     ecx, 103h
0x18000d4f2  ja      short loc_18000D503
0x18000d4f4  mov     rcx, [rdi]; Block
0x18000d4f7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d4fc  xor     eax, eax
0x18000d4fe  mov     [rdi], rbx
0x18000d501  jmp     short loc_18000D51C
0x18000d503  mov     rcx, rbx; Block
0x18000d506  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d50b  test    esi, esi
0x18000d50d  jnz     short loc_18000D517
0x18000d50f  call    cs:__imp_GetLastError
0x18000d515  jmp     short loc_18000D51C
0x18000d517  mov     eax, 6Fh ; 'o'
0x18000d51c  mov     rbx, [rsp+28h+arg_0]
0x18000d521  mov     rsi, [rsp+28h+arg_8]
0x18000d526  add     rsp, 20h
0x18000d52a  pop     rdi
0x18000d52b  retn
```
