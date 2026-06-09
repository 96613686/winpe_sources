# EfsRpcCloseRaw

- ea: `0x180005850`
- end: `0x180005882`
- name: `EfsRpcCloseRaw`
- size: `50`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005850`
- `0x18000b308`

## import_xrefs

- `EFSCORE!EfsDllCloseFileRaw` at `0x18000586f`
- `EFSCORE!EfsDllCloseFileRaw` at `0x18000586f`

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
0x180005850  push    rbx
0x180005852  sub     rsp, 20h
0x180005856  mov     rbx, rcx
0x180005859  call    EfsEnforceClientAuthentication
0x18000585e  test    eax, eax
0x180005860  jnz     short loc_18000587C
0x180005862  mov     rcx, [rbx]
0x180005865  test    rcx, rcx
0x180005868  jz      short loc_18000587C
0x18000586a  cmp     dword ptr [rcx], 1
0x18000586d  jnz     short loc_18000587C
0x18000586f  call    cs:__imp_EfsDllCloseFileRaw
0x180005875  mov     qword ptr [rbx], 0
0x18000587c  add     rsp, 20h
0x180005880  pop     rbx
0x180005881  retn
```
