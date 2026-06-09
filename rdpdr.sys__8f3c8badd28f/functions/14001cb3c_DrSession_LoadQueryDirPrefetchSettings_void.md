# DrSession::LoadQueryDirPrefetchSettings(void)

- ea: `0x14001cb3c`
- end: `0x14001cc3c`
- name: `?LoadQueryDirPrefetchSettings@DrSession@@QEAAXXZ`
- size: `256`
- prototype: `void __fastcall(DrSession *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14001bf2c`

## callees

- `0x14000537c`
- `0x140017544`
- `0x14001cb3c`

## string_xrefs

- `0x14001cbb4`: `QueryDirPrefetchMaxCacheEntries`

## pseudocode

```c
void __fastcall DrSession::LoadQueryDirPrefetchSettings(DrSession *this)
{
  int v1; // ebx
  const unsigned __int16 *v3; // rcx
  const unsigned __int16 *v4; // rcx
  __int64 v5; // r8
  int v6; // eax
  int v7; // [rsp+60h] [rbp+8h] BYREF

  v1 = 1;
  v7 = 1;
  if ( (int)QueryRegistryValue((const unsigned __int16 *)this, L"fAllowQueryDirPrefetch", (unsigned __int8 *)&v7) >= 0 )
    v1 = v7;
  *((_DWORD *)this + 346) = v1;
  v7 = 0;
  if ( (int)QueryRegistryValue(v3, L"QueryDirPrefetchMaxObjects", (unsigned __int8 *)&v7) >= 0 && v7 )
    *((_DWORD *)this + 381) = v7;
  else
    *((_DWORD *)this + 381) = 64;
  v7 = 0;
  if ( (int)QueryRegistryValue(v4, L"QueryDirPrefetchMaxCacheEntries", (unsigned __int8 *)&v7) < 0 || (v6 = v7) == 0 )
    v6 = 100;
  *((_DWORD *)this + 382) = v6;
  *((_DWORD *)this + 380) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_qDDDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      &WPP_GLOBAL_Control,
      v5,
      this,
      *((_DWORD *)this + 282),
      *((_DWORD *)this + 346),
      0,
      *((_DWORD *)this + 381),
      v6);
}

```

## disassembly

```asm
0x14001cb3c  mov     [rsp+arg_8], rbx
0x14001cb41  push    rdi
0x14001cb42  sub     rsp, 50h
0x14001cb46  mov     ebx, 1
0x14001cb4b  lea     r8, [rsp+58h+arg_0]; unsigned __int8 *
0x14001cb50  lea     rdx, aFallowquerydir; "fAllowQueryDirPrefetch"
0x14001cb57  mov     [rsp+58h+arg_0], ebx
0x14001cb5b  mov     rdi, rcx
0x14001cb5e  call    ?QueryRegistryValue@@YAJPEBG0PEAEK@Z; QueryRegistryValue(ushort const *,ushort const *,uchar *,ulong)
0x14001cb63  test    eax, eax
0x14001cb65  lea     r8, [rsp+58h+arg_0]; unsigned __int8 *
0x14001cb6a  lea     rdx, aQuerydirprefet_0; "QueryDirPrefetchMaxObjects"
0x14001cb71  cmovns  ebx, [rsp+58h+arg_0]
0x14001cb76  mov     [rdi+568h], ebx
0x14001cb7c  mov     [rsp+58h+arg_0], 0
0x14001cb84  call    ?QueryRegistryValue@@YAJPEBG0PEAEK@Z; QueryRegistryValue(ushort const *,ushort const *,uchar *,ulong)
0x14001cb89  test    eax, eax
0x14001cb8b  js      short loc_14001CB9D
0x14001cb8d  mov     eax, [rsp+58h+arg_0]
0x14001cb91  test    eax, eax
0x14001cb93  jz      short loc_14001CB9D
0x14001cb95  mov     [rdi+5F4h], eax
0x14001cb9b  jmp     short loc_14001CBA7
0x14001cb9d  mov     dword ptr [rdi+5F4h], 40h ; '@'
0x14001cba7  lea     r8, [rsp+58h+arg_0]; unsigned __int8 *
0x14001cbac  mov     [rsp+58h+arg_0], 0
0x14001cbb4  lea     rdx, aQuerydirprefet; "QueryDirPrefetchMaxCacheEntries"
0x14001cbbb  call    ?QueryRegistryValue@@YAJPEBG0PEAEK@Z; QueryRegistryValue(ushort const *,ushort const *,uchar *,ulong)
0x14001cbc0  test    eax, eax
0x14001cbc2  js      short loc_14001CBCC
0x14001cbc4  mov     eax, [rsp+58h+arg_0]
0x14001cbc8  test    eax, eax
0x14001cbca  jnz     short loc_14001CBD1
0x14001cbcc  mov     eax, 64h ; 'd'
0x14001cbd1  mov     [rdi+5F8h], eax
0x14001cbd7  mov     dword ptr [rdi+5F0h], 0
0x14001cbe1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cbe8  lea     rdx, WPP_GLOBAL_Control
0x14001cbef  cmp     rcx, rdx
0x14001cbf2  jz      short loc_14001CC30
0x14001cbf4  cmp     byte ptr [rcx+29h], 4
0x14001cbf8  jb      short loc_14001CC30
0x14001cbfa  mov     rcx, [rcx+18h]
0x14001cbfe  mov     r9, rdi
0x14001cc01  mov     [rsp+58h+var_18], eax
0x14001cc05  mov     eax, [rdi+5F4h]
0x14001cc0b  mov     [rsp+58h+var_20], eax
0x14001cc0f  mov     eax, [rdi+568h]
0x14001cc15  mov     [rsp+58h+var_28], 0
0x14001cc1d  mov     [rsp+58h+var_30], eax
0x14001cc21  mov     eax, [rdi+468h]
0x14001cc27  mov     [rsp+58h+var_38], eax
0x14001cc2b  call    WPP_SF_qDDDDD
0x14001cc30  mov     rbx, [rsp+58h+arg_8]
0x14001cc35  add     rsp, 50h
0x14001cc39  pop     rdi
0x14001cc3a  retn
```
