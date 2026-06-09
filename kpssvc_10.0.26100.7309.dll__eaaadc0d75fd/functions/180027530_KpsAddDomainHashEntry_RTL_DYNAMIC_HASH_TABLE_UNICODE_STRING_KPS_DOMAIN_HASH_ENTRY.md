# KpsAddDomainHashEntry(_RTL_DYNAMIC_HASH_TABLE *,_UNICODE_STRING *,_KPS_DOMAIN_HASH_ENTRY * *)

- ea: `0x180027530`
- end: `0x1800276bf`
- name: `?KpsAddDomainHashEntry@@YAKPEAU_RTL_DYNAMIC_HASH_TABLE@@PEAU_UNICODE_STRING@@PEAPEAU_KPS_DOMAIN_HASH_ENTRY@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(struct _RTL_DYNAMIC_HASH_TABLE *, struct _UNICODE_STRING *, struct _UNICODE_STRING **)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800280d8`
- `0x180029c48`
- `0x18002b03c`

## callees

- `0x18001ae38`
- `0x180027530`
- `0x180028e78`
- `0x18002c534`
- `0x180030060`
- `0x1800300f4`

## import_xrefs

- `ntdll!RtlInsertEntryHashTable` at `0x180027659`
- `ntdll!RtlInsertEntryHashTable` at `0x180027659`
- `ntdll!RtlCreateHashTable` at `0x180027611`
- `ntdll!RtlCreateHashTable` at `0x180027611`
- `ntdll!RtlDuplicateUnicodeString` at `0x1800275da`
- `ntdll!RtlDuplicateUnicodeString` at `0x1800275da`

## pseudocode

```c
__int64 __fastcall KpsAddDomainHashEntry(
        struct _RTL_DYNAMIC_HASH_TABLE *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING **a3)
{
  struct _UNICODE_STRING *v6; // rax
  struct _UNICODE_STRING *v7; // rdi
  __int64 v8; // r9
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned __int64 v13; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_qZ(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2);
  *a3 = 0;
  v6 = (struct _UNICODE_STRING *)KpsAllocMem(0x68u);
  v7 = v6;
  if ( v6 )
  {
    v12 = RtlDuplicateUnicodeString(1u, a2, v6 + 2);
    v9 = v12;
    if ( v12 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 38;
        v8 = v12;
        goto LABEL_8;
      }
    }
    else
    {
      if ( (unsigned __int8)RtlCreateHashTable(&v7[6], 0, 0) )
      {
        v13 = HashUnicodeString(a2);
        RtlInsertEntryHashTable(a1, v7, v13, 0);
        LODWORD(v7[1].Buffer) = 1;
        *a3 = v7;
        v7 = 0;
        goto LABEL_18;
      }
      v8 = 8;
      v9 = 8;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 39;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v8 = 8;
    v9 = 8;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 37;
LABEL_8:
      WPP_SF_D(v10[2], v11, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v8);
    }
  }
LABEL_18:
  KpsFreeDomainHashEntry((struct _KPS_DOMAIN_HASH_ENTRY *)v7);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180027530  mov     rax, rsp
0x180027533  mov     [rax+8], rbx
0x180027537  mov     [rax+10h], rbp
0x18002753b  mov     [rax+18h], rsi
0x18002753f  push    rdi
0x180027540  push    r14
0x180027542  push    r15
0x180027544  sub     rsp, 30h
0x180027548  mov     r14, r8
0x18002754b  mov     rsi, rdx
0x18002754e  mov     rbp, rcx
0x180027551  mov     rcx, cs:WPP_GLOBAL_Control
0x180027558  lea     r15, WPP_GLOBAL_Control
0x18002755f  cmp     rcx, r15
0x180027562  jz      short loc_18002757F
0x180027564  test    byte ptr [rcx+1Ch], 20h
0x180027568  jz      short loc_18002757F
0x18002756a  mov     rcx, [rcx+10h]; LoggerHandle
0x18002756e  mov     edx, 24h ; '$'
0x180027573  mov     r9, rbp
0x180027576  mov     [rax-28h], rsi
0x18002757a  call    WPP_SF_qZ
0x18002757f  and     qword ptr [r14], 0
0x180027583  mov     ecx, 68h ; 'h'; unsigned __int64
0x180027588  call    ?KpsAllocMem@@YAPEAX_K@Z; KpsAllocMem(unsigned __int64)
0x18002758d  mov     rdi, rax
0x180027590  test    rax, rax
0x180027593  jnz     short loc_1800275CE
0x180027595  lea     r9d, [rax+8]
0x180027599  mov     ebx, r9d
0x18002759c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275a3  cmp     rcx, r15
0x1800275a6  jz      loc_180027671
0x1800275ac  test    byte ptr [rcx+1Ch], 1
0x1800275b0  jz      loc_180027671
0x1800275b6  lea     edx, [rax+25h]
0x1800275b9  mov     rcx, [rcx+10h]
0x1800275bd  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x1800275c4  call    WPP_SF_D
0x1800275c9  jmp     loc_180027671
0x1800275ce  lea     r8, [rax+20h]; DestinationString
0x1800275d2  mov     rdx, rsi; SourceString
0x1800275d5  mov     ecx, 1; Flags
0x1800275da  call    cs:__imp_RtlDuplicateUnicodeString
0x1800275e1  nop     dword ptr [rax+rax+00h]
0x1800275e6  mov     ebx, eax
0x1800275e8  test    eax, eax
0x1800275ea  jz      short loc_180027608
0x1800275ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275f3  cmp     rcx, r15
0x1800275f6  jz      short loc_180027671
0x1800275f8  test    byte ptr [rcx+1Ch], 1
0x1800275fc  jz      short loc_180027671
0x1800275fe  mov     edx, 26h ; '&'
0x180027603  mov     r9d, eax
0x180027606  jmp     short loc_1800275B9
0x180027608  lea     rcx, [rdi+60h]
0x18002760c  xor     r8d, r8d
0x18002760f  xor     edx, edx
0x180027611  call    cs:__imp_RtlCreateHashTable
0x180027618  nop     dword ptr [rax+rax+00h]
0x18002761d  test    al, al
0x18002761f  jnz     short loc_180027645
0x180027621  mov     r9d, 8
0x180027627  mov     ebx, r9d
0x18002762a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027631  cmp     rcx, r15
0x180027634  jz      short loc_180027671
0x180027636  test    byte ptr [rcx+1Ch], 1
0x18002763a  jz      short loc_180027671
0x18002763c  lea     edx, [r9+1Fh]
0x180027640  jmp     loc_1800275B9
0x180027645  mov     rcx, rsi; struct _UNICODE_STRING *
0x180027648  call    ?HashUnicodeString@@YA_KPEAU_UNICODE_STRING@@@Z; HashUnicodeString(_UNICODE_STRING *)
0x18002764d  xor     r9d, r9d
0x180027650  mov     r8, rax
0x180027653  mov     rdx, rdi
0x180027656  mov     rcx, rbp
0x180027659  call    cs:__imp_RtlInsertEntryHashTable
0x180027660  nop     dword ptr [rax+rax+00h]
0x180027665  mov     dword ptr [rdi+18h], 1
0x18002766c  mov     [r14], rdi
0x18002766f  xor     edi, edi
0x180027671  mov     rcx, rdi; lpMem
0x180027674  call    ?KpsFreeDomainHashEntry@@YAXPEAU_KPS_DOMAIN_HASH_ENTRY@@@Z; KpsFreeDomainHashEntry(_KPS_DOMAIN_HASH_ENTRY *)
0x180027679  mov     rcx, cs:WPP_GLOBAL_Control
0x180027680  cmp     rcx, r15
0x180027683  jz      short loc_1800276A3
0x180027685  test    byte ptr [rcx+1Ch], 20h
0x180027689  jz      short loc_1800276A3
0x18002768b  mov     rcx, [rcx+10h]
0x18002768f  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180027696  mov     edx, 28h ; '('
0x18002769b  mov     r9d, ebx
0x18002769e  call    WPP_SF_D
0x1800276a3  mov     rbp, [rsp+48h+arg_8]
0x1800276a8  mov     eax, ebx
0x1800276aa  mov     rbx, [rsp+48h+arg_0]
0x1800276af  mov     rsi, [rsp+48h+arg_10]
0x1800276b4  add     rsp, 30h
0x1800276b8  pop     r15
0x1800276ba  pop     r14
0x1800276bc  pop     rdi
0x1800276bd  retn
```
