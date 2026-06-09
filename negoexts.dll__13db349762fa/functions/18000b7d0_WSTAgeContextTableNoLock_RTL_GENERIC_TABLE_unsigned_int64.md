# WSTAgeContextTableNoLock(_RTL_GENERIC_TABLE *,unsigned __int64 *)

- ea: `0x18000b7d0`
- end: `0x18000b8c9`
- name: `?WSTAgeContextTableNoLock@@YAKPEAU_RTL_GENERIC_TABLE@@PEA_K@Z`
- size: `249`
- prototype: `unsigned int __fastcall(PRTL_GENERIC_TABLE Table, unsigned __int64 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b6b0`
- `0x18000b718`
- `0x18000b774`
- `0x1800169d4`
- `0x18001d138`

## callees

- `0x18000b7d0`
- `0x18000ca08`
- `0x180015aa8`

## import_xrefs

- `ntdll!RtlGetElementGenericTable` at `0x18000b7fb`
- `ntdll!RtlGetElementGenericTable` at `0x18000b7fb`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000b88a`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000b88a`
- `ntdll!RtlNumberGenericTableElements` at `0x18000b8b2`
- `ntdll!RtlNumberGenericTableElements` at `0x18000b8b2`

## pseudocode

```c
__int64 __fastcall WSTAgeContextTableNoLock(PRTL_GENERIC_TABLE Table, unsigned __int64 *a2)
{
  unsigned int v2; // ebx
  ULONG v3; // edi
  __int64 *ElementGenericTable; // rax
  __int64 *v7; // r14
  unsigned __int64 v9; // rax
  __int64 v10; // r15

  v2 = 0;
  v3 = 0;
  do
  {
    ElementGenericTable = (__int64 *)RtlGetElementGenericTable(Table, v3);
    v7 = ElementGenericTable;
    if ( !ElementGenericTable )
      break;
    v9 = ElementGenericTable[1];
    if ( v9 >= NegoExtsGlobalWillNever )
    {
      ++v3;
    }
    else
    {
      if ( v9 > *a2 )
        return v2;
      v10 = *v7;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_qDDZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(*(_QWORD *)(v10 + 24) + 44LL),
          *(_DWORD *)(*(_QWORD *)(v10 + 24) + 40LL),
          v10 + 168);
      if ( !RtlDeleteElementGenericTable(Table, v7) )
        return v2;
      _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 16), 0, 1);
      ++v2;
      WSTDereferenceContext((struct _WST_CONTEXT *)v10);
    }
  }
  while ( v3 < RtlNumberGenericTableElements(Table) );
  return v2;
}

```

## disassembly

```asm
0x18000b7d0  push    rbx
0x18000b7d2  push    rbp
0x18000b7d3  push    rsi
0x18000b7d4  push    rdi
0x18000b7d5  push    r12
0x18000b7d7  push    r14
0x18000b7d9  sub     rsp, 48h
0x18000b7dd  xor     ebx, ebx
0x18000b7df  mov     [rsp+78h+arg_0], r15
0x18000b7e7  xor     edi, edi
0x18000b7e9  lea     r12, WPP_GLOBAL_Control
0x18000b7f0  mov     rbp, rdx
0x18000b7f3  mov     rsi, rcx
0x18000b7f6  mov     edx, edi; I
0x18000b7f8  mov     rcx, rsi; Table
0x18000b7fb  call    cs:__imp_RtlGetElementGenericTable
0x18000b801  mov     r14, rax
0x18000b804  test    rax, rax
0x18000b807  jnz     short loc_18000B820
0x18000b809  mov     r15, [rsp+78h+arg_0]
0x18000b811  mov     eax, ebx
0x18000b813  add     rsp, 48h
0x18000b817  pop     r14
0x18000b819  pop     r12
0x18000b81b  pop     rdi
0x18000b81c  pop     rsi
0x18000b81d  pop     rbp
0x18000b81e  pop     rbx
0x18000b81f  retn
0x18000b820  mov     rax, [rax+8]
0x18000b824  cmp     rax, cs:?NegoExtsGlobalWillNever@@3_KA; unsigned __int64 NegoExtsGlobalWillNever
0x18000b82b  jnb     loc_18000B8C5
0x18000b831  cmp     rax, [rbp+0]
0x18000b835  ja      short loc_18000B809
0x18000b837  mov     r15, [r14]
0x18000b83a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b841  cmp     rcx, r12
0x18000b844  jz      short loc_18000B884
0x18000b846  test    byte ptr [rcx+1Ch], 2
0x18000b84a  jz      short loc_18000B884
0x18000b84c  mov     r8, [r15+18h]
0x18000b850  lea     rax, [r15+0A8h]
0x18000b857  mov     rcx, [rcx+10h]; LoggerHandle
0x18000b85b  mov     edx, 10h
0x18000b860  mov     [rsp+78h+var_48], rax; __int64
0x18000b865  mov     r9, r15
0x18000b868  mov     eax, [r8+28h]
0x18000b86c  mov     dword ptr [rsp+78h+var_50], eax; char
0x18000b870  mov     eax, [r8+2Ch]
0x18000b874  lea     r8, WPP_daa775e63f0b32280135cd3ef20378c2_Traceguids
0x18000b87b  mov     dword ptr [rsp+78h+var_58], eax; char
0x18000b87f  call    WPP_SF_qDDZ
0x18000b884  mov     rdx, r14; Buffer
0x18000b887  mov     rcx, rsi; Table
0x18000b88a  call    cs:__imp_RtlDeleteElementGenericTable
0x18000b890  test    al, al
0x18000b892  jz      loc_18000B809
0x18000b898  xor     edx, edx
0x18000b89a  mov     eax, 1
0x18000b89f  lock cmpxchg [r15+10h], edx
0x18000b8a5  inc     ebx
0x18000b8a7  mov     rcx, r15; struct _WST_CONTEXT *
0x18000b8aa  call    ?WSTDereferenceContext@@YAXPEAU_WST_CONTEXT@@@Z; WSTDereferenceContext(_WST_CONTEXT *)
0x18000b8af  mov     rcx, rsi; Table
0x18000b8b2  call    cs:__imp_RtlNumberGenericTableElements
0x18000b8b8  cmp     edi, eax
0x18000b8ba  jb      loc_18000B7F6
0x18000b8c0  jmp     loc_18000B809
0x18000b8c5  inc     edi
0x18000b8c7  jmp     short loc_18000B8AF
```
