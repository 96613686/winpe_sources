# KpsUpdateDomainRediscovery(_KPS_IO *)

- ea: `0x18002b03c`
- end: `0x18002b246`
- name: `?KpsUpdateDomainRediscovery@@YAKPEAU_KPS_IO@@@Z`
- size: `522`
- prototype: `__int64 __fastcall(struct _KPS_IO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800223fc`

## callees

- `0x18001ae38`
- `0x180026bc0`
- `0x180026d9c`
- `0x180027530`
- `0x180028dc0`
- `0x18002a180`
- `0x18002a838`
- `0x18002b03c`
- `0x18002c3f4`
- `0x18002c534`
- `0x18002ffd8`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002b1fa`
- `ntdll!RtlLeaveCriticalSection` at `0x18002b1fa`
- `ntdll!RtlEnterCriticalSection` at `0x18002b08c`
- `ntdll!RtlEnterCriticalSection` at `0x18002b08c`

## string_xrefs

- `0x18002b0f1`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
__int64 __fastcall KpsUpdateDomainRediscovery(struct _KPS_IO *a1)
{
  unsigned int v1; // edi
  char v3; // bp
  struct _UNICODE_STRING *v4; // rsi
  struct _KPS_DOMAIN_HASH_ENTRY *v5; // rbx
  __int64 v6; // r8
  struct _KPS_DOMAIN_HASH_ENTRY *lpMem; // [rsp+60h] [rbp+8h] BYREF

  v1 = 0;
  v3 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, a1);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
  v4 = (struct _UNICODE_STRING *)((char *)a1 + 112);
  lpMem = KpsLookupDomainHashEntry(qword_18003ACE8, v4);
  if ( lpMem )
  {
    v5 = lpMem;
    *((_QWORD *)lpMem + 11) = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                             * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
  }
  else
  {
    KpsSqmIncrement(1u);
    v1 = KpsAddDomainHashEntry(qword_18003ACE8, v4, &lpMem);
    if ( v1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ZDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v1,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
          100);
      v5 = lpMem;
    }
    else
    {
      v3 = 1;
      v5 = lpMem;
      *((_QWORD *)lpMem + 11) = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                               * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_qZ(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v4);
      KpsRebalanceHashTable(qword_18003ACE8);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_ddd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          v6,
          *((unsigned int *)qword_18003ACE8 + 6),
          *((_DWORD *)qword_18003ACE8 + 2),
          *((_DWORD *)qword_18003ACE8 + 5));
    }
  }
  if ( v5 && !v3 )
    KpsDereferenceDomainHashEntry(v5);
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x18002b03c  mov     [rsp+arg_8], rbx
0x18002b041  mov     [rsp+arg_10], rbp
0x18002b046  push    rsi
0x18002b047  push    rdi
0x18002b048  push    r14
0x18002b04a  sub     rsp, 40h
0x18002b04e  xor     edi, edi
0x18002b050  mov     rsi, rcx
0x18002b053  xor     bpl, bpl
0x18002b056  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b05d  lea     r14, WPP_GLOBAL_Control
0x18002b064  cmp     rcx, r14
0x18002b067  jz      short loc_18002B085
0x18002b069  test    byte ptr [rcx+1Ch], 20h
0x18002b06d  jz      short loc_18002B085
0x18002b06f  mov     rcx, [rcx+10h]
0x18002b073  lea     edx, [rdi+3Ah]
0x18002b076  mov     r9, rsi
0x18002b079  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002b080  call    WPP_SF_q
0x18002b085  lea     rcx, ?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A+8; CriticalSection
0x18002b08c  call    cs:__imp_RtlEnterCriticalSection
0x18002b093  nop     dword ptr [rax+rax+00h]
0x18002b098  mov     rcx, cs:qword_18003ACE8; struct _RTL_DYNAMIC_HASH_TABLE *
0x18002b09f  add     rsi, 70h ; 'p'
0x18002b0a3  mov     rdx, rsi; struct _UNICODE_STRING *
0x18002b0a6  call    ?KpsLookupDomainHashEntry@@YAPEAU_KPS_DOMAIN_HASH_ENTRY@@PEAU_RTL_DYNAMIC_HASH_TABLE@@PEAU_UNICODE_STRING@@@Z; KpsLookupDomainHashEntry(_RTL_DYNAMIC_HASH_TABLE *,_UNICODE_STRING *)
0x18002b0ab  mov     [rsp+58h+lpMem], rax
0x18002b0b0  test    rax, rax
0x18002b0b3  jnz     loc_18002B1BE
0x18002b0b9  lea     ecx, [rax+1]; unsigned int
0x18002b0bc  call    ?KpsSqmIncrement@@YAXK@Z; KpsSqmIncrement(ulong)
0x18002b0c1  mov     rcx, cs:qword_18003ACE8; struct _RTL_DYNAMIC_HASH_TABLE *
0x18002b0c8  lea     r8, [rsp+58h+lpMem]; struct _KPS_DOMAIN_HASH_ENTRY **
0x18002b0cd  mov     rdx, rsi; struct _UNICODE_STRING *
0x18002b0d0  call    ?KpsAddDomainHashEntry@@YAKPEAU_RTL_DYNAMIC_HASH_TABLE@@PEAU_UNICODE_STRING@@PEAPEAU_KPS_DOMAIN_HASH_ENTRY@@@Z; KpsAddDomainHashEntry(_RTL_DYNAMIC_HASH_TABLE *,_UNICODE_STRING *,_KPS_DOMAIN_HASH_ENTRY * *)
0x18002b0d5  mov     edi, eax
0x18002b0d7  test    eax, eax
0x18002b0d9  jz      short loc_18002B127
0x18002b0db  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0e2  cmp     rcx, r14
0x18002b0e5  jz      short loc_18002B11D
0x18002b0e7  test    byte ptr [rcx+1Ch], 1
0x18002b0eb  jz      short loc_18002B11D
0x18002b0ed  mov     rcx, [rcx+10h]; LoggerHandle
0x18002b0f1  lea     rax, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002b0f8  mov     dword ptr [rsp+58h+var_28], 464h; char
0x18002b100  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002b107  mov     [rsp+58h+var_30], rax; __int64
0x18002b10c  mov     edx, 3Bh ; ';'
0x18002b111  mov     r9, rsi
0x18002b114  mov     dword ptr [rsp+58h+var_38], edi; char
0x18002b118  call    WPP_SF_ZDsd
0x18002b11d  mov     rbx, [rsp+58h+lpMem]
0x18002b122  jmp     loc_18002B1E1
0x18002b127  mov     ecx, ds:7FFE0004h
0x18002b12e  mov     eax, 7FFE0320h
0x18002b133  shl     rcx, 20h
0x18002b137  mov     bpl, 1
0x18002b13a  mov     rax, [rax]
0x18002b13d  mov     rbx, [rsp+58h+lpMem]
0x18002b142  shl     rax, 8
0x18002b146  mul     rcx
0x18002b149  mov     [rbx+58h], rdx
0x18002b14d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b154  cmp     rcx, r14
0x18002b157  jz      short loc_18002B175
0x18002b159  test    byte ptr [rcx+1Ch], 40h
0x18002b15d  jz      short loc_18002B175
0x18002b15f  mov     rcx, [rcx+10h]; LoggerHandle
0x18002b163  mov     edx, 3Ch ; '<'
0x18002b168  mov     r9, rbx
0x18002b16b  mov     qword ptr [rsp+58h+var_38], rsi; __int64
0x18002b170  call    WPP_SF_qZ
0x18002b175  mov     rcx, cs:qword_18003ACE8; struct _RTL_DYNAMIC_HASH_TABLE *
0x18002b17c  call    ?KpsRebalanceHashTable@@YAXPEAU_RTL_DYNAMIC_HASH_TABLE@@@Z; KpsRebalanceHashTable(_RTL_DYNAMIC_HASH_TABLE *)
0x18002b181  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b188  cmp     rcx, r14
0x18002b18b  jz      short loc_18002B1E1
0x18002b18d  test    byte ptr [rcx+1Ch], 40h
0x18002b191  jz      short loc_18002B1E1
0x18002b193  mov     r9, cs:qword_18003ACE8
0x18002b19a  mov     edx, 3Dh ; '='
0x18002b19f  mov     rcx, [rcx+10h]
0x18002b1a3  mov     eax, [r9+14h]
0x18002b1a7  mov     dword ptr [rsp+58h+var_30], eax
0x18002b1ab  mov     eax, [r9+8]
0x18002b1af  mov     r9d, [r9+18h]
0x18002b1b3  mov     dword ptr [rsp+58h+var_38], eax
0x18002b1b7  call    WPP_SF_ddd
0x18002b1bc  jmp     short loc_18002B1E1
0x18002b1be  mov     ecx, ds:7FFE0004h
0x18002b1c5  mov     eax, 7FFE0320h
0x18002b1ca  shl     rcx, 20h
0x18002b1ce  mov     rax, [rax]
0x18002b1d1  mov     rbx, [rsp+58h+lpMem]
0x18002b1d6  shl     rax, 8
0x18002b1da  mul     rcx
0x18002b1dd  mov     [rbx+58h], rdx
0x18002b1e1  test    rbx, rbx
0x18002b1e4  jz      short loc_18002B1F3
0x18002b1e6  test    bpl, bpl
0x18002b1e9  jnz     short loc_18002B1F3
0x18002b1eb  mov     rcx, rbx; lpMem
0x18002b1ee  call    ?KpsDereferenceDomainHashEntry@@YAXPEAU_KPS_DOMAIN_HASH_ENTRY@@@Z; KpsDereferenceDomainHashEntry(_KPS_DOMAIN_HASH_ENTRY *)
0x18002b1f3  lea     rcx, ?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A+8; CriticalSection
0x18002b1fa  call    cs:__imp_RtlLeaveCriticalSection
0x18002b201  nop     dword ptr [rax+rax+00h]
0x18002b206  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b20d  cmp     rcx, r14
0x18002b210  jz      short loc_18002B230
0x18002b212  test    byte ptr [rcx+1Ch], 20h
0x18002b216  jz      short loc_18002B230
0x18002b218  mov     rcx, [rcx+10h]
0x18002b21c  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002b223  mov     edx, 3Eh ; '>'
0x18002b228  mov     r9d, edi
0x18002b22b  call    WPP_SF_D
0x18002b230  mov     rbx, [rsp+58h+arg_8]
0x18002b235  mov     eax, edi
0x18002b237  mov     rbp, [rsp+58h+arg_10]
0x18002b23c  add     rsp, 40h
0x18002b240  pop     r14
0x18002b242  pop     rdi
0x18002b243  pop     rsi
0x18002b244  retn
```
