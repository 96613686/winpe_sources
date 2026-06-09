# KpsFreeUserTable(_RTL_DYNAMIC_HASH_TABLE *)

- ea: `0x1800290d4`
- end: `0x1800291dc`
- name: `?KpsFreeUserTable@@YAXPEAU_RTL_DYNAMIC_HASH_TABLE@@@Z`
- size: `264`
- prototype: `void __fastcall(struct _RTL_DYNAMIC_HASH_TABLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028e78`

## callees

- `0x18001ae0c`
- `0x180026d9c`
- `0x180028e1c`
- `0x1800290d4`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x180029198`
- `ntdll!RtlDeleteHashTable` at `0x180029198`
- `ntdll!RtlInitEnumerationHashTable` at `0x18002913d`
- `ntdll!RtlInitEnumerationHashTable` at `0x18002913d`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18002916d`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18002916d`
- `ntdll!RtlRemoveEntryHashTable` at `0x180029151`
- `ntdll!RtlRemoveEntryHashTable` at `0x180029151`
- `ntdll!RtlEndEnumerationHashTable` at `0x180029189`
- `ntdll!RtlEndEnumerationHashTable` at `0x180029189`

## pseudocode

```c
void __fastcall KpsFreeUserTable(struct _RTL_DYNAMIC_HASH_TABLE *a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rax
  struct _KPS_USER_HASH_ENTRY *v6; // rdi
  _OWORD v7[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v8; // [rsp+40h] [rbp-18h]

  memset(v7, 0, sizeof(v7));
  v8 = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, a1);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    RtlInitEnumerationHashTable(a1, v7);
    while ( 1 )
    {
      v5 = RtlEnumerateEntryHashTable(a1, v7);
      v6 = (struct _KPS_USER_HASH_ENTRY *)v5;
      if ( !v5 )
        break;
      RtlRemoveEntryHashTable(a1, v5, 0);
      KpsDereferenceUserHashEntry(v6, v3, v4);
    }
    RtlEndEnumerationHashTable(a1, v7);
    RtlDeleteHashTable(a1);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_(v2[2], 29, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids);
}

```

## disassembly

```asm
0x1800290d4  mov     [rsp+arg_0], rbx
0x1800290d9  mov     [rsp+arg_8], rsi
0x1800290de  push    rdi
0x1800290df  sub     rsp, 50h
0x1800290e3  xorps   xmm0, xmm0
0x1800290e6  xor     eax, eax
0x1800290e8  movups  [rsp+58h+var_38], xmm0
0x1800290ed  mov     [rsp+58h+var_18], rax
0x1800290f2  mov     rbx, rcx
0x1800290f5  movups  [rsp+58h+var_28], xmm0
0x1800290fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180029101  lea     rsi, WPP_GLOBAL_Control
0x180029108  cmp     rcx, rsi
0x18002910b  jz      short loc_180029130
0x18002910d  test    byte ptr [rcx+1Ch], 20h
0x180029111  jz      short loc_180029130
0x180029113  mov     rcx, [rcx+10h]
0x180029117  lea     edx, [rax+1Ch]
0x18002911a  mov     r9, rbx
0x18002911d  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180029124  call    WPP_SF_q
0x180029129  mov     rcx, cs:WPP_GLOBAL_Control
0x180029130  test    rbx, rbx
0x180029133  jz      short loc_1800291AB
0x180029135  lea     rdx, [rsp+58h+var_38]
0x18002913a  mov     rcx, rbx
0x18002913d  call    cs:__imp_RtlInitEnumerationHashTable
0x180029144  nop     dword ptr [rax+rax+00h]
0x180029149  jmp     short loc_180029165
0x18002914b  xor     r8d, r8d
0x18002914e  mov     rdx, rdi
0x180029151  call    cs:__imp_RtlRemoveEntryHashTable
0x180029158  nop     dword ptr [rax+rax+00h]
0x18002915d  mov     rcx, rdi; lpMem
0x180029160  call    ?KpsDereferenceUserHashEntry@@YAXPEAU_KPS_USER_HASH_ENTRY@@@Z; KpsDereferenceUserHashEntry(_KPS_USER_HASH_ENTRY *)
0x180029165  lea     rdx, [rsp+58h+var_38]
0x18002916a  mov     rcx, rbx
0x18002916d  call    cs:__imp_RtlEnumerateEntryHashTable
0x180029174  nop     dword ptr [rax+rax+00h]
0x180029179  mov     rdi, rax
0x18002917c  mov     rcx, rbx
0x18002917f  test    rax, rax
0x180029182  jnz     short loc_18002914B
0x180029184  lea     rdx, [rsp+58h+var_38]
0x180029189  call    cs:__imp_RtlEndEnumerationHashTable
0x180029190  nop     dword ptr [rax+rax+00h]
0x180029195  mov     rcx, rbx
0x180029198  call    cs:__imp_RtlDeleteHashTable
0x18002919f  nop     dword ptr [rax+rax+00h]
0x1800291a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800291ab  cmp     rcx, rsi
0x1800291ae  jz      short loc_1800291CB
0x1800291b0  test    byte ptr [rcx+1Ch], 20h
0x1800291b4  jz      short loc_1800291CB
0x1800291b6  mov     rcx, [rcx+10h]
0x1800291ba  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x1800291c1  mov     edx, 1Dh
0x1800291c6  call    WPP_SF_
0x1800291cb  mov     rbx, [rsp+58h+arg_0]
0x1800291d0  mov     rsi, [rsp+58h+arg_8]
0x1800291d5  add     rsp, 50h
0x1800291d9  pop     rdi
0x1800291da  retn
```
