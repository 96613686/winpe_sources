# ReleaseGlobals

- ea: `0x14000d8b4`
- end: `0x14000d96f`
- name: `ReleaseGlobals`
- size: `187`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400030b8`
- `0x14000dce0`

## callees

- `0x14000c9c0`
- `0x14000d8b4`
- `0x14000e634`
- `0x14000e838`
- `0x14000e87c`
- `0x14000e8c8`
- `0x14000e928`
- `0x14000ec3c`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x14000d95e`
- `WS2_32!__imp_WSACleanup` at `0x14000d95e`

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

  if ( qword_140014218 && *(_DWORD *)qword_140014218 == 9 )
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
          Item = _DynArrayGetItem(qword_140014218, 3, 0);
          if ( Item )
          {
            if ( *(_DWORD *)(Item + 4) == 0x80000 )
              DynArrayRemove(*(_QWORD *)(Item + 16), Count2);
          }
        }
      }
    }
    DestroyDynamicArray(&qword_140014218);
  }
  if ( g_bWinsockLoaded == 1 )
    WSACleanup();
  return 1;
}

```

## disassembly

```asm
0x14000d8b4  push    rbx
0x14000d8b6  sub     rsp, 20h
0x14000d8ba  mov     rax, cs:qword_140014218
0x14000d8c1  test    rax, rax
0x14000d8c4  jz      loc_14000D955
0x14000d8ca  cmp     dword ptr [rax], 9
0x14000d8cd  jnz     loc_14000D955
0x14000d8d3  mov     edx, 3
0x14000d8d8  call    DynArrayGetCount2
0x14000d8dd  mov     ebx, eax
0x14000d8df  test    eax, eax
0x14000d8e1  jz      short loc_14000D949
0x14000d8e3  dec     ebx
0x14000d8e5  mov     r8d, ebx
0x14000d8e8  call    DynArrayGetItemType2
0x14000d8ed  cmp     eax, 10000h
0x14000d8f2  jnz     short loc_14000D945
0x14000d8f4  mov     r8d, ebx
0x14000d8f7  call    DynArrayItem2
0x14000d8fc  mov     [rsp+28h+arg_0], rax
0x14000d901  test    rax, rax
0x14000d904  jz      short loc_14000D945
0x14000d906  lea     rcx, [rax+10h]
0x14000d90a  call    FreeMemory
0x14000d90f  lea     rcx, [rsp+28h+arg_0]
0x14000d914  call    FreeMemory
0x14000d919  mov     rcx, cs:qword_140014218
0x14000d920  xor     r8d, r8d
0x14000d923  lea     edx, [r8+3]
0x14000d927  call    __DynArrayGetItem
0x14000d92c  test    rax, rax
0x14000d92f  jz      short loc_14000D945
0x14000d931  cmp     dword ptr [rax+4], 80000h
0x14000d938  jnz     short loc_14000D945
0x14000d93a  mov     rcx, [rax+10h]
0x14000d93e  mov     edx, ebx
0x14000d940  call    DynArrayRemove
0x14000d945  test    ebx, ebx
0x14000d947  jnz     short loc_14000D8E3
0x14000d949  lea     rcx, qword_140014218
0x14000d950  call    DestroyDynamicArray
0x14000d955  cmp     cs:g_bWinsockLoaded, 1
0x14000d95c  jnz     short loc_14000D964
0x14000d95e  call    cs:__imp_WSACleanup
0x14000d964  mov     eax, 1
0x14000d969  add     rsp, 20h
0x14000d96d  pop     rbx
0x14000d96e  retn
```
