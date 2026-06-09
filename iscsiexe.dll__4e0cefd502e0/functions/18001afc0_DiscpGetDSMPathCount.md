# DiscpGetDSMPathCount

- ea: `0x18001afc0`
- end: `0x18001b0a7`
- name: `DiscpGetDSMPathCount`
- size: `231`
- prototype: `__int64 __fastcall(unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ae70`

## callees

- `0x180003198`
- `0x18001afc0`

## import_xrefs

- `ISCSIUM!DiscpQuerySingleInstance` at `0x18001b037`
- `ISCSIUM!DiscpQuerySingleInstance` at `0x18001b037`
- `ISCSIUM!DiscpParseSingleInstance` at `0x18001b062`
- `ISCSIUM!DiscpParseSingleInstance` at `0x18001b062`
- `ISCSIUM!DiscpGetPnpDeviceId` at `0x18001afec`
- `ISCSIUM!DiscpGetPnpDeviceId` at `0x18001afec`
- `ISCSIUM!DiscpFreeMemory` at `0x18001b088`
- `ISCSIUM!DiscpFreeMemory` at `0x18001b092`
- `ISCSIUM!DiscpFreeMemory` at `0x18001b088`
- `ISCSIUM!DiscpFreeMemory` at `0x18001b092`

## pseudocode

```c
__int64 __fastcall DiscpGetDSMPathCount(unsigned int a1, _DWORD *a2)
{
  unsigned int PnpDeviceId; // ebx
  __int64 v4; // rdx
  STRSAFE_LPWSTR pszDest; // [rsp+30h] [rbp-20h] BYREF
  __int64 v7; // [rsp+38h] [rbp-18h] BYREF
  __int64 v8; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v9; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v10; // [rsp+88h] [rbp+38h] BYREF

  pszDest = 0;
  v7 = 0;
  v9 = 0;
  v8 = 0;
  v10 = 0;
  PnpDeviceId = DiscpGetPnpDeviceId(&pszDest, a1);
  if ( !PnpDeviceId )
  {
    v4 = -1;
    do
      ++v4;
    while ( pszDest[v4] );
    StringCchCatW(pszDest, v4 + 3, L"_0");
    PnpDeviceId = DiscpQuerySingleInstance(DSM_QueryLBPolicy_GUID, 0, pszDest, &v7, &v9);
    if ( !PnpDeviceId )
    {
      PnpDeviceId = DiscpParseSingleInstance(v7, v9, 0, 0, &v8, &v10);
      if ( !PnpDeviceId )
      {
        if ( v10 < 0x28 )
          PnpDeviceId = 87;
        else
          *a2 = *(_DWORD *)(v8 + 8);
      }
      DiscpFreeMemory(v7);
    }
    DiscpFreeMemory(pszDest);
  }
  return PnpDeviceId;
}

```

## disassembly

```asm
0x18001afc0  mov     [rsp-18h+arg_0], rbx
0x18001afc5  push    rbp
0x18001afc6  push    rsi
0x18001afc7  push    rdi
0x18001afc8  mov     rbp, rsp
0x18001afcb  sub     rsp, 50h
0x18001afcf  xor     esi, esi
0x18001afd1  mov     rdi, rdx
0x18001afd4  mov     edx, ecx
0x18001afd6  mov     [rbp+pszDest], rsi
0x18001afda  lea     rcx, [rbp+pszDest]
0x18001afde  mov     [rbp+var_18], rsi
0x18001afe2  mov     [rbp+arg_10], esi
0x18001afe5  mov     [rbp+var_10], rsi
0x18001afe9  mov     [rbp+arg_18], esi
0x18001afec  call    cs:__imp_DiscpGetPnpDeviceId
0x18001aff2  mov     ebx, eax
0x18001aff4  test    eax, eax
0x18001aff6  jnz     loc_18001B098
0x18001affc  mov     rcx, [rbp+pszDest]; pszDest
0x18001b000  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001b004  inc     rdx
0x18001b007  cmp     [rcx+rdx*2], si
0x18001b00b  jnz     short loc_18001B004
0x18001b00d  add     rdx, 3; cchDest
0x18001b011  lea     r8, a0; "_0"
0x18001b018  call    StringCchCatW
0x18001b01d  mov     r8, [rbp+pszDest]
0x18001b021  lea     rax, [rbp+arg_10]
0x18001b025  lea     r9, [rbp+var_18]
0x18001b029  mov     [rsp+50h+var_30], rax
0x18001b02e  xor     edx, edx
0x18001b030  lea     rcx, DSM_QueryLBPolicy_GUID
0x18001b037  call    cs:__imp_DiscpQuerySingleInstance
0x18001b03d  mov     ebx, eax
0x18001b03f  test    eax, eax
0x18001b041  jnz     short loc_18001B08E
0x18001b043  mov     edx, [rbp+arg_10]
0x18001b046  lea     rax, [rbp+arg_18]
0x18001b04a  mov     rcx, [rbp+var_18]
0x18001b04e  xor     r9d, r9d
0x18001b051  mov     [rsp+50h+var_28], rax
0x18001b056  xor     r8d, r8d
0x18001b059  lea     rax, [rbp+var_10]
0x18001b05d  mov     [rsp+50h+var_30], rax
0x18001b062  call    cs:__imp_DiscpParseSingleInstance
0x18001b068  mov     ebx, eax
0x18001b06a  test    eax, eax
0x18001b06c  jnz     short loc_18001B084
0x18001b06e  cmp     [rbp+arg_18], 28h ; '('
0x18001b072  jb      short loc_18001B07F
0x18001b074  mov     rax, [rbp+var_10]
0x18001b078  mov     ecx, [rax+8]
0x18001b07b  mov     [rdi], ecx
0x18001b07d  jmp     short loc_18001B084
0x18001b07f  mov     ebx, 57h ; 'W'
0x18001b084  mov     rcx, [rbp+var_18]
0x18001b088  call    cs:__imp_DiscpFreeMemory
0x18001b08e  mov     rcx, [rbp+pszDest]
0x18001b092  call    cs:__imp_DiscpFreeMemory
0x18001b098  mov     eax, ebx
0x18001b09a  mov     rbx, [rsp+50h+arg_0]
0x18001b09f  add     rsp, 50h
0x18001b0a3  pop     rdi
0x18001b0a4  pop     rsi
0x18001b0a5  pop     rbp
0x18001b0a6  retn
```
