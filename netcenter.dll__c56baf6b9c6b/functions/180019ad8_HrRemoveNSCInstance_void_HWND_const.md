# HrRemoveNSCInstance(void *,HWND__ * const)

- ea: `0x180019ad8`
- end: `0x180019b99`
- name: `?HrRemoveNSCInstance@@YAJPEAXQEAUHWND__@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(void *, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000df98`

## callees

- `0x180007618`
- `0x180014274`
- `0x180019ad8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019afb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019afb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019b55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019b55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b1f`

## pseudocode

```c
__int64 __fastcall HrRemoveNSCInstance(void *a1, HWND a2)
{
  __int64 *i; // rbx
  void **v5; // rcx

  if ( !a1 )
    return 2147500035LL;
  EnterCriticalSection(&g_csNSCInstanceList);
  for ( i = *(__int64 **)g_NCSInstanceList; i != (__int64 *)g_NCSInstanceList; i = (__int64 *)*i )
  {
    v5 = (void **)i[2];
    if ( v5[1] == a1 )
    {
      CoTaskMemFree(v5);
      *(_QWORD *)i[1] = *i;
      *(_QWORD *)(*i + 8) = i[1];
      --qword_180032618;
      std::_Deallocate<16>(i, 24);
      break;
    }
  }
  LeaveCriticalSection(&g_csNSCInstanceList);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_31aceb967a8f36dcbf14b86f9200de5a_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180019ad8  mov     [rsp+arg_0], rbx
0x180019add  push    rdi
0x180019ade  sub     rsp, 20h
0x180019ae2  mov     rdi, rcx
0x180019ae5  test    rcx, rcx
0x180019ae8  jnz     short loc_180019AF4
0x180019aea  mov     eax, 80004003h
0x180019aef  jmp     loc_180019B8E
0x180019af4  lea     rcx, ?g_csNSCInstanceList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019afb  call    cs:__imp_EnterCriticalSection
0x180019b01  mov     rax, cs:?g_NCSInstanceList@@3V?$list@PEAUtagNSC_INSTANCE_DATA@@V?$allocator@PEAUtagNSC_INSTANCE_DATA@@@std@@@std@@A; std::list<tagNSC_INSTANCE_DATA *> g_NCSInstanceList
0x180019b08  mov     rbx, [rax]
0x180019b0b  cmp     rbx, rax
0x180019b0e  jz      short loc_180019B4E
0x180019b10  mov     rcx, [rbx+10h]; pv
0x180019b14  cmp     [rcx+8], rdi
0x180019b18  jz      short loc_180019B1F
0x180019b1a  mov     rbx, [rbx]
0x180019b1d  jmp     short loc_180019B0B
0x180019b1f  call    cs:__imp_CoTaskMemFree
0x180019b25  mov     rdx, [rbx+8]
0x180019b29  mov     rcx, rbx
0x180019b2c  mov     rax, [rbx]
0x180019b2f  mov     [rdx], rax
0x180019b32  mov     rdx, [rbx]
0x180019b35  mov     rax, [rbx+8]
0x180019b39  mov     [rdx+8], rax
0x180019b3d  mov     edx, 18h
0x180019b42  dec     cs:qword_180032618
0x180019b49  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180019b4e  lea     rcx, ?g_csNSCInstanceList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019b55  call    cs:__imp_LeaveCriticalSection
0x180019b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b62  lea     rax, WPP_GLOBAL_Control
0x180019b69  cmp     rcx, rax
0x180019b6c  jz      short loc_180019B8C
0x180019b6e  test    byte ptr [rcx+1Ch], 8
0x180019b72  jz      short loc_180019B8C
0x180019b74  mov     rcx, [rcx+10h]
0x180019b78  lea     r8, WPP_31aceb967a8f36dcbf14b86f9200de5a_Traceguids
0x180019b7f  mov     edx, 13h
0x180019b84  xor     r9d, r9d
0x180019b87  call    WPP_SF_d
0x180019b8c  xor     eax, eax
0x180019b8e  mov     rbx, [rsp+28h+arg_0]
0x180019b93  add     rsp, 20h
0x180019b97  pop     rdi
0x180019b98  retn
```
