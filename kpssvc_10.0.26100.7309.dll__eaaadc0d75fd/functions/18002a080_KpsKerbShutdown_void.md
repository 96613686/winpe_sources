# KpsKerbShutdown(void)

- ea: `0x18002a080`
- end: `0x18002a177`
- name: `?KpsKerbShutdown@@YAXXZ`
- size: `247`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002ccd0`
- `0x18002cf60`

## callees

- `0x18001ae0c`
- `0x180028f28`
- `0x18002a080`

## import_xrefs

- `MSASN1!ASN1_CloseModule` at `0x18002a114`
- `MSASN1!ASN1_CloseModule` at `0x18002a114`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a0ee`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a0ee`
- `ntdll!RtlEnterCriticalSection` at `0x18002a0cf`
- `ntdll!RtlEnterCriticalSection` at `0x18002a0cf`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a101`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a101`

## pseudocode

```c
void KpsKerbShutdown(void)
{
  _QWORD *v0; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( KpsGlobalKerbState )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
    KpsFreeDomainTable(qword_18003ACE8);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
    ASN1_CloseModule(KRB5_Module);
    KRB5_Module = 0;
    v0 = WPP_GLOBAL_Control;
    qword_18003ACE8 = 0;
    KpsGlobalKerbState = 0;
    xmmword_18003ACC8 = 0;
    xmmword_18003ACD8 = 0;
  }
  if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 0x20) != 0 )
    WPP_SF_(v0[2], 162, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids);
}

```

## disassembly

```asm
0x18002a080  push    rdi
0x18002a082  sub     rsp, 20h
0x18002a086  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a08d  lea     rdi, WPP_GLOBAL_Control
0x18002a094  cmp     rcx, rdi
0x18002a097  jz      short loc_18002A0BB
0x18002a099  test    byte ptr [rcx+1Ch], 20h
0x18002a09d  jz      short loc_18002A0BB
0x18002a09f  mov     rcx, [rcx+10h]
0x18002a0a3  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002a0aa  mov     edx, 0A1h
0x18002a0af  call    WPP_SF_
0x18002a0b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0bb  cmp     byte ptr cs:?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A, 0; _KPS_GLOBAL_KERB_STATE KpsGlobalKerbState
0x18002a0c2  jz      loc_18002A150
0x18002a0c8  lea     rcx, ?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A+8; CriticalSection
0x18002a0cf  call    cs:__imp_RtlEnterCriticalSection
0x18002a0d6  nop     dword ptr [rax+rax+00h]
0x18002a0db  mov     rcx, cs:qword_18003ACE8; struct _RTL_DYNAMIC_HASH_TABLE *
0x18002a0e2  call    ?KpsFreeDomainTable@@YAXPEAU_RTL_DYNAMIC_HASH_TABLE@@@Z; KpsFreeDomainTable(_RTL_DYNAMIC_HASH_TABLE *)
0x18002a0e7  lea     rcx, ?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A+8; CriticalSection
0x18002a0ee  call    cs:__imp_RtlLeaveCriticalSection
0x18002a0f5  nop     dword ptr [rax+rax+00h]
0x18002a0fa  lea     rcx, ?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A+8; CriticalSection
0x18002a101  call    cs:__imp_RtlDeleteCriticalSection
0x18002a108  nop     dword ptr [rax+rax+00h]
0x18002a10d  mov     rcx, cs:KRB5_Module
0x18002a114  call    cs:__imp_ASN1_CloseModule
0x18002a11b  nop     dword ptr [rax+rax+00h]
0x18002a120  and     cs:KRB5_Module, 0
0x18002a128  xorps   xmm0, xmm0
0x18002a12b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a132  xor     eax, eax
0x18002a134  mov     cs:qword_18003ACE8, rax
0x18002a13b  movups  cs:?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A, xmm0; _KPS_GLOBAL_KERB_STATE KpsGlobalKerbState
0x18002a142  movups  cs:xmmword_18003ACC8, xmm0
0x18002a149  movups  cs:xmmword_18003ACD8, xmm0
0x18002a150  cmp     rcx, rdi
0x18002a153  jz      short loc_18002A170
0x18002a155  test    byte ptr [rcx+1Ch], 20h
0x18002a159  jz      short loc_18002A170
0x18002a15b  mov     rcx, [rcx+10h]
0x18002a15f  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002a166  mov     edx, 0A2h
0x18002a16b  call    WPP_SF_
0x18002a170  add     rsp, 20h
0x18002a174  pop     rdi
0x18002a175  retn
```
