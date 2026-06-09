# AppResurrectionManager::~AppResurrectionManager(void)

- ea: `0x180025e1c`
- end: `0x180025ebb`
- name: `??1AppResurrectionManager@@QEAA@XZ`
- size: `159`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180026070`

## callees

- `0x18001d910`
- `0x180025e1c`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x180025e9b`
- `ntdll!RtlDeleteHashTable` at `0x180025e9b`
- `ntdll!RtlRemoveEntryHashTable` at `0x180025e60`
- `ntdll!RtlRemoveEntryHashTable` at `0x180025e60`
- `ntdll!RtlInitEnumerationHashTable` at `0x180025e52`
- `ntdll!RtlInitEnumerationHashTable` at `0x180025e52`
- `ntdll!RtlEndEnumerationHashTable` at `0x180025e92`
- `ntdll!RtlEndEnumerationHashTable` at `0x180025e92`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180025e7c`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180025e7c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025ea4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025ea4`

## pseudocode

```c
void __fastcall AppResurrectionManager::~AppResurrectionManager(LPCRITICAL_SECTION lpCriticalSection)
{
  LPCRITICAL_SECTION v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rsi
  _OWORD v5[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+40h] [rbp-18h]

  memset(v5, 0, sizeof(v5));
  v6 = 0;
  if ( LOBYTE(lpCriticalSection[2].DebugInfo) )
  {
    v2 = lpCriticalSection + 1;
    RtlInitEnumerationHashTable(&lpCriticalSection[1], v5);
    while ( 1 )
    {
      v3 = RtlEnumerateEntryHashTable(v2, v5);
      v4 = v3;
      if ( !v3 )
        break;
      RtlRemoveEntryHashTable(v2, v3, 0);
      operator delete((void *)(v4 - 64));
    }
    RtlEndEnumerationHashTable(v2, v5);
    RtlDeleteHashTable(v2);
    DeleteCriticalSection(lpCriticalSection);
  }
}

```

## disassembly

```asm
0x180025e1c  mov     r11, rsp
0x180025e1f  mov     [r11+8], rbx
0x180025e23  mov     [r11+10h], rsi
0x180025e27  push    rdi
0x180025e28  sub     rsp, 50h
0x180025e2c  mov     rdi, rcx
0x180025e2f  xorps   xmm0, xmm0
0x180025e32  xor     eax, eax
0x180025e34  movups  [rsp+58h+var_38], xmm0
0x180025e39  movups  [rsp+58h+var_28], xmm0
0x180025e3e  mov     [r11-18h], rax
0x180025e42  cmp     [rcx+50h], al
0x180025e45  jz      short loc_180025EAB
0x180025e47  lea     rbx, [rcx+28h]
0x180025e4b  lea     rdx, [r11-38h]
0x180025e4f  mov     rcx, rbx
0x180025e52  call    cs:__imp_RtlInitEnumerationHashTable
0x180025e58  jmp     short loc_180025E74
0x180025e5a  xor     r8d, r8d
0x180025e5d  mov     rdx, rsi
0x180025e60  call    cs:__imp_RtlRemoveEntryHashTable
0x180025e66  lea     rcx, [rsi-40h]; Block
0x180025e6a  mov     edx, 58h ; 'X'
0x180025e6f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025e74  lea     rdx, [rsp+58h+var_38]
0x180025e79  mov     rcx, rbx
0x180025e7c  call    cs:__imp_RtlEnumerateEntryHashTable
0x180025e82  test    rax, rax
0x180025e85  mov     rsi, rax
0x180025e88  mov     rcx, rbx
0x180025e8b  jnz     short loc_180025E5A
0x180025e8d  lea     rdx, [rsp+58h+var_38]
0x180025e92  call    cs:__imp_RtlEndEnumerationHashTable
0x180025e98  mov     rcx, rbx
0x180025e9b  call    cs:__imp_RtlDeleteHashTable
0x180025ea1  mov     rcx, rdi; lpCriticalSection
0x180025ea4  call    cs:__imp_DeleteCriticalSection
0x180025eaa  nop
0x180025eab  mov     rbx, [rsp+58h+arg_0]
0x180025eb0  mov     rsi, [rsp+58h+arg_8]
0x180025eb5  add     rsp, 50h
0x180025eb9  pop     rdi
0x180025eba  retn
```
