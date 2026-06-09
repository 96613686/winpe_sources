# WSTDeleteUserModeContext(unsigned __int64)

- ea: `0x18000c5a4`
- end: `0x18000c5e0`
- name: `?WSTDeleteUserModeContext@@YAJ_K@Z`
- size: `60`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180019200`
- `0x1800194d0`

## callees

- `0x18000c5a4`
- `0x18000c700`
- `0x180018ea0`

## pseudocode

```c
__int64 __fastcall WSTDeleteUserModeContext(unsigned __int64 a1)
{
  int v1; // ebx
  struct _NEGOEXTS_UMODE_CONTEXT *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v1 = WSTReferenceUserModeContextByLsaHandle(a1, 1u, &v3);
  if ( v1 < 0 )
    return 0;
  if ( v3 )
    WSTDereferenceUserModeContext(v3);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000c5a4  push    rbx
0x18000c5a6  sub     rsp, 20h
0x18000c5aa  lea     r8, [rsp+28h+arg_8]; struct _NEGOEXTS_UMODE_CONTEXT **
0x18000c5af  mov     [rsp+28h+arg_8], 0
0x18000c5b8  mov     dl, 1; unsigned __int8
0x18000c5ba  call    ?WSTReferenceUserModeContextByLsaHandle@@YAJ_KEPEAPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z; WSTReferenceUserModeContextByLsaHandle(unsigned __int64,uchar,_NEGOEXTS_UMODE_CONTEXT * *)
0x18000c5bf  mov     ebx, eax
0x18000c5c1  test    eax, eax
0x18000c5c3  jns     short loc_18000C5C9
0x18000c5c5  xor     eax, eax
0x18000c5c7  jmp     short loc_18000C5DA
0x18000c5c9  mov     rcx, [rsp+28h+arg_8]; struct _NEGOEXTS_UMODE_CONTEXT *
0x18000c5ce  test    rcx, rcx
0x18000c5d1  jz      short loc_18000C5D8
0x18000c5d3  call    ?WSTDereferenceUserModeContext@@YAXPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z; WSTDereferenceUserModeContext(_NEGOEXTS_UMODE_CONTEXT *)
0x18000c5d8  mov     eax, ebx
0x18000c5da  add     rsp, 20h
0x18000c5de  pop     rbx
0x18000c5df  retn
```
