# EfsRpcCloseRaw

- ea: `0x180005cb0`
- end: `0x180005ce9`
- name: `EfsRpcCloseRaw`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005cb0`
- `0x18000bf0c`

## import_xrefs

- `EFSCORE!EfsDllCloseFileRaw` at `0x180005ccf`
- `EFSCORE!EfsDllCloseFileRaw` at `0x180005ccf`

## pseudocode

```c
__int64 __fastcall EfsRpcCloseRaw(_QWORD *a1)
{
  __int64 result; // rax

  result = EfsEnforceClientAuthentication();
  if ( !(_DWORD)result && *a1 && *(_DWORD *)*a1 == 1 )
  {
    result = EfsDllCloseFileRaw();
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005cb0  push    rbx
0x180005cb2  sub     rsp, 20h
0x180005cb6  mov     rbx, rcx
0x180005cb9  call    EfsEnforceClientAuthentication
0x180005cbe  test    eax, eax
0x180005cc0  jnz     short loc_180005CE2
0x180005cc2  mov     rcx, [rbx]
0x180005cc5  test    rcx, rcx
0x180005cc8  jz      short loc_180005CE2
0x180005cca  cmp     dword ptr [rcx], 1
0x180005ccd  jnz     short loc_180005CE2
0x180005ccf  call    cs:__imp_EfsDllCloseFileRaw
0x180005cd6  nop     dword ptr [rax+rax+00h]
0x180005cdb  mov     qword ptr [rbx], 0
0x180005ce2  add     rsp, 20h
0x180005ce6  pop     rbx
0x180005ce7  retn
```
