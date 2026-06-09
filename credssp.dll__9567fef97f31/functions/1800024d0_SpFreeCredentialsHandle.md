# SpFreeCredentialsHandle

- ea: `0x1800024d0`
- end: `0x18000252e`
- name: `SpFreeCredentialsHandle`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800024d0`

## import_xrefs

- `SspiCli!FreeCredentialsHandle` at `0x1800024ef`
- `SspiCli!FreeCredentialsHandle` at `0x1800024fe`
- `SspiCli!FreeCredentialsHandle` at `0x1800024ef`
- `SspiCli!FreeCredentialsHandle` at `0x1800024fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002512`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000251b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002512`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000251b`

## pseudocode

```c
__int64 __fastcall SpFreeCredentialsHandle(__int64 a1)
{
  struct _SecHandle *v2; // rdi
  unsigned int v3; // ebx
  SECURITY_STATUS v4; // eax
  SECURITY_STATUS v5; // eax
  void *dwUpper; // rcx

  if ( !a1 )
    return 2148074241LL;
  v2 = *(struct _SecHandle **)(a1 + 8);
  v3 = 0;
  v4 = FreeCredentialsHandle(v2);
  if ( v4 < 0 )
    v3 = v4;
  v5 = FreeCredentialsHandle(v2 + 1);
  dwUpper = (void *)v2[2].dwUpper;
  if ( v5 < 0 )
    v3 = v5;
  if ( dwUpper )
    LocalFree(dwUpper);
  LocalFree(v2);
  return v3;
}

```

## disassembly

```asm
0x1800024d0  mov     [rsp+arg_0], rbx
0x1800024d5  push    rdi
0x1800024d6  sub     rsp, 20h
0x1800024da  test    rcx, rcx
0x1800024dd  jnz     short loc_1800024E6
0x1800024df  mov     eax, 80090301h
0x1800024e4  jmp     short loc_180002523
0x1800024e6  mov     rdi, [rcx+8]
0x1800024ea  xor     ebx, ebx
0x1800024ec  mov     rcx, rdi; phCredential
0x1800024ef  call    cs:__imp_FreeCredentialsHandle
0x1800024f5  test    eax, eax
0x1800024f7  lea     rcx, [rdi+10h]; phCredential
0x1800024fb  cmovs   ebx, eax
0x1800024fe  call    cs:__imp_FreeCredentialsHandle
0x180002504  mov     rcx, [rdi+28h]; hMem
0x180002508  test    eax, eax
0x18000250a  cmovs   ebx, eax
0x18000250d  test    rcx, rcx
0x180002510  jz      short loc_180002518
0x180002512  call    cs:__imp_LocalFree
0x180002518  mov     rcx, rdi; hMem
0x18000251b  call    cs:__imp_LocalFree
0x180002521  mov     eax, ebx
0x180002523  mov     rbx, [rsp+28h+arg_0]
0x180002528  add     rsp, 20h
0x18000252c  pop     rdi
0x18000252d  retn
```
