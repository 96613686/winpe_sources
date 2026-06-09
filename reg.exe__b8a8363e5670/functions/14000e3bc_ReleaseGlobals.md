# ReleaseGlobals

- ea: `0x14000e3bc`
- end: `0x14000e47e`
- name: `ReleaseGlobals`
- size: `194`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400031f4`
- `0x14000e864`

## callees

- `0x14000d2d0`
- `0x14000e3bc`
- `0x14000f2c4`
- `0x14000f4d8`
- `0x14000f51c`
- `0x14000f568`
- `0x14000f5c8`
- `0x14000f8e8`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x14000e466`
- `WS2_32!__imp_WSACleanup` at `0x14000e466`

## pseudocode

```c
__int64 __fastcall ReleaseGlobals(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  unsigned int Count2; // ebx
  __int64 v4; // rax
  __int64 Item; // rax
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  if ( qword_140015218 && *(_DWORD *)qword_140015218 == 9 )
  {
    Count2 = DynArrayGetCount2(a1, 3);
    while ( Count2 )
    {
      if ( (unsigned int)DynArrayGetItemType2(v2, v1, --Count2) == 0x10000 )
      {
        v4 = DynArrayItem2(v2, v1, Count2);
        v7 = v4;
        if ( v4 )
        {
          FreeMemory(v4 + 16);
          FreeMemory(&v7);
          Item = _DynArrayGetItem(qword_140015218, 3, 0);
          if ( Item )
          {
            if ( *(_DWORD *)(Item + 4) == 0x80000 )
              DynArrayRemove(*(_QWORD *)(Item + 16), Count2);
          }
        }
      }
    }
    DestroyDynamicArray(&qword_140015218);
  }
  if ( g_bWinsockLoaded == 1 )
    WSACleanup();
  return 1;
}

```

## disassembly

```asm
0x14000e3bc  push    rbx
0x14000e3be  sub     rsp, 20h
0x14000e3c2  mov     rax, cs:qword_140015218
0x14000e3c9  test    rax, rax
0x14000e3cc  jz      loc_14000E45D
0x14000e3d2  cmp     dword ptr [rax], 9
0x14000e3d5  jnz     loc_14000E45D
0x14000e3db  mov     edx, 3
0x14000e3e0  call    DynArrayGetCount2
0x14000e3e5  mov     ebx, eax
0x14000e3e7  test    eax, eax
0x14000e3e9  jz      short loc_14000E451
0x14000e3eb  dec     ebx
0x14000e3ed  mov     r8d, ebx
0x14000e3f0  call    DynArrayGetItemType2
0x14000e3f5  cmp     eax, 10000h
0x14000e3fa  jnz     short loc_14000E44D
0x14000e3fc  mov     r8d, ebx
0x14000e3ff  call    DynArrayItem2
0x14000e404  mov     [rsp+28h+arg_0], rax
0x14000e409  test    rax, rax
0x14000e40c  jz      short loc_14000E44D
0x14000e40e  lea     rcx, [rax+10h]
0x14000e412  call    FreeMemory
0x14000e417  lea     rcx, [rsp+28h+arg_0]
0x14000e41c  call    FreeMemory
0x14000e421  mov     rcx, cs:qword_140015218
0x14000e428  xor     r8d, r8d
0x14000e42b  lea     edx, [r8+3]
0x14000e42f  call    __DynArrayGetItem
0x14000e434  test    rax, rax
0x14000e437  jz      short loc_14000E44D
0x14000e439  cmp     dword ptr [rax+4], 80000h
0x14000e440  jnz     short loc_14000E44D
0x14000e442  mov     rcx, [rax+10h]
0x14000e446  mov     edx, ebx
0x14000e448  call    DynArrayRemove
0x14000e44d  test    ebx, ebx
0x14000e44f  jnz     short loc_14000E3EB
0x14000e451  lea     rcx, qword_140015218
0x14000e458  call    DestroyDynamicArray
0x14000e45d  cmp     cs:g_bWinsockLoaded, 1
0x14000e464  jnz     short loc_14000E472
0x14000e466  call    cs:__imp_WSACleanup
0x14000e46d  nop     dword ptr [rax+rax+00h]
0x14000e472  mov     eax, 1
0x14000e477  add     rsp, 20h
0x14000e47b  pop     rbx
0x14000e47c  retn
```
