# KpsFreeDomainTable(_RTL_DYNAMIC_HASH_TABLE *)

- ea: `0x180028f28`
- end: `0x180029030`
- name: `?KpsFreeDomainTable@@YAXPEAU_RTL_DYNAMIC_HASH_TABLE@@@Z`
- size: `264`
- prototype: `void __fastcall(struct _RTL_DYNAMIC_HASH_TABLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a080`

## callees

- `0x18001ae0c`
- `0x180026d9c`
- `0x180028dc0`
- `0x180028f28`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x180028fec`
- `ntdll!RtlDeleteHashTable` at `0x180028fec`
- `ntdll!RtlInitEnumerationHashTable` at `0x180028f91`
- `ntdll!RtlInitEnumerationHashTable` at `0x180028f91`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180028fc1`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180028fc1`
- `ntdll!RtlRemoveEntryHashTable` at `0x180028fa5`
- `ntdll!RtlRemoveEntryHashTable` at `0x180028fa5`
- `ntdll!RtlEndEnumerationHashTable` at `0x180028fdd`
- `ntdll!RtlEndEnumerationHashTable` at `0x180028fdd`

## pseudocode

```c
void __fastcall KpsFreeDomainTable(struct _RTL_DYNAMIC_HASH_TABLE *a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rax
  struct _KPS_DOMAIN_HASH_ENTRY *v6; // rdi
  _OWORD v7[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v8; // [rsp+40h] [rbp-18h]

  memset(v7, 0, sizeof(v7));
  v8 = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, a1);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    RtlInitEnumerationHashTable(a1, v7);
    while ( 1 )
    {
      v5 = RtlEnumerateEntryHashTable(a1, v7);
      v6 = (struct _KPS_DOMAIN_HASH_ENTRY *)v5;
      if ( !v5 )
        break;
      RtlRemoveEntryHashTable(a1, v5, 0);
      KpsDereferenceDomainHashEntry(v6, v3, v4);
    }
    RtlEndEnumerationHashTable(a1, v7);
    RtlDeleteHashTable(a1);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_(v2[2], 42, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids);
}

```

## disassembly

```asm
0x180028f28  mov     [rsp+arg_0], rbx
0x180028f2d  mov     [rsp+arg_8], rsi
0x180028f32  push    rdi
0x180028f33  sub     rsp, 50h
0x180028f37  xorps   xmm0, xmm0
0x180028f3a  xor     eax, eax
0x180028f3c  movups  [rsp+58h+var_38], xmm0
0x180028f41  mov     [rsp+58h+var_18], rax
0x180028f46  mov     rbx, rcx
0x180028f49  movups  [rsp+58h+var_28], xmm0
0x180028f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f55  lea     rsi, WPP_GLOBAL_Control
0x180028f5c  cmp     rcx, rsi
0x180028f5f  jz      short loc_180028F84
0x180028f61  test    byte ptr [rcx+1Ch], 20h
0x180028f65  jz      short loc_180028F84
0x180028f67  mov     rcx, [rcx+10h]
0x180028f6b  lea     edx, [rax+29h]
0x180028f6e  mov     r9, rbx
0x180028f71  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180028f78  call    WPP_SF_q
0x180028f7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f84  test    rbx, rbx
0x180028f87  jz      short loc_180028FFF
0x180028f89  lea     rdx, [rsp+58h+var_38]
0x180028f8e  mov     rcx, rbx
0x180028f91  call    cs:__imp_RtlInitEnumerationHashTable
0x180028f98  nop     dword ptr [rax+rax+00h]
0x180028f9d  jmp     short loc_180028FB9
0x180028f9f  xor     r8d, r8d
0x180028fa2  mov     rdx, rdi
0x180028fa5  call    cs:__imp_RtlRemoveEntryHashTable
0x180028fac  nop     dword ptr [rax+rax+00h]
0x180028fb1  mov     rcx, rdi; lpMem
0x180028fb4  call    ?KpsDereferenceDomainHashEntry@@YAXPEAU_KPS_DOMAIN_HASH_ENTRY@@@Z; KpsDereferenceDomainHashEntry(_KPS_DOMAIN_HASH_ENTRY *)
0x180028fb9  lea     rdx, [rsp+58h+var_38]
0x180028fbe  mov     rcx, rbx
0x180028fc1  call    cs:__imp_RtlEnumerateEntryHashTable
0x180028fc8  nop     dword ptr [rax+rax+00h]
0x180028fcd  mov     rdi, rax
0x180028fd0  mov     rcx, rbx
0x180028fd3  test    rax, rax
0x180028fd6  jnz     short loc_180028F9F
0x180028fd8  lea     rdx, [rsp+58h+var_38]
0x180028fdd  call    cs:__imp_RtlEndEnumerationHashTable
0x180028fe4  nop     dword ptr [rax+rax+00h]
0x180028fe9  mov     rcx, rbx
0x180028fec  call    cs:__imp_RtlDeleteHashTable
0x180028ff3  nop     dword ptr [rax+rax+00h]
0x180028ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x180028fff  cmp     rcx, rsi
0x180029002  jz      short loc_18002901F
0x180029004  test    byte ptr [rcx+1Ch], 20h
0x180029008  jz      short loc_18002901F
0x18002900a  mov     rcx, [rcx+10h]
0x18002900e  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180029015  mov     edx, 2Ah ; '*'
0x18002901a  call    WPP_SF_
0x18002901f  mov     rbx, [rsp+58h+arg_0]
0x180029024  mov     rsi, [rsp+58h+arg_8]
0x180029029  add     rsp, 50h
0x18002902d  pop     rdi
0x18002902e  retn
```
