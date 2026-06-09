# DeleteLogMarshallingArea

- ea: `0x18000aaa0`
- end: `0x18000aafb`
- name: `DeleteLogMarshallingArea`
- size: `91`
- prototype: `BOOL __stdcall(PVOID pvMarshal)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000aec0`
- `0x18000d500`

## callees

- `0x18000aaa0`
- `0x180011854`
- `0x180013058`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aace`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aae6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aace`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aae6`

## pseudocode

```c
BOOL __stdcall DeleteLogMarshallingArea(PVOID pvMarshal)
{
  if ( pvMarshal && *(_DWORD *)pvMarshal == -1040322550 && *((_DWORD *)pvMarshal + 1) == 368 )
  {
    CClfsMarshallingContext::PrepareForDelete((CClfsMarshallingContext *)pvMarshal);
    CClfsMarshallingContext::Release((CClfsMarshallingContext *)pvMarshal);
    SetLastError(0);
    return 1;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18000aaa0  push    rbx
0x18000aaa2  sub     rsp, 20h
0x18000aaa6  mov     rbx, rcx
0x18000aaa9  test    rcx, rcx
0x18000aaac  jz      short loc_18000AAE1
0x18000aaae  cmp     dword ptr [rcx], 0C1FDF00Ah
0x18000aab4  jnz     short loc_18000AAE1
0x18000aab6  cmp     dword ptr [rcx+4], 170h
0x18000aabd  jnz     short loc_18000AAE1
0x18000aabf  call    ?PrepareForDelete@CClfsMarshallingContext@@QEAAKXZ; CClfsMarshallingContext::PrepareForDelete(void)
0x18000aac4  mov     rcx, rbx; this
0x18000aac7  call    ?Release@CClfsMarshallingContext@@QEAAKXZ; CClfsMarshallingContext::Release(void)
0x18000aacc  xor     ecx, ecx; dwErrCode
0x18000aace  call    cs:__imp_SetLastError
0x18000aad5  nop     dword ptr [rax+rax+00h]
0x18000aada  mov     eax, 1
0x18000aadf  jmp     short loc_18000AAF4
0x18000aae1  mov     ecx, 57h ; 'W'; dwErrCode
0x18000aae6  call    cs:__imp_SetLastError
0x18000aaed  nop     dword ptr [rax+rax+00h]
0x18000aaf2  xor     eax, eax
0x18000aaf4  add     rsp, 20h
0x18000aaf8  pop     rbx
0x18000aaf9  retn
```
