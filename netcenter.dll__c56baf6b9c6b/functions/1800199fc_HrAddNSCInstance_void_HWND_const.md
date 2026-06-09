# HrAddNSCInstance(void *,HWND__ * const)

- ea: `0x1800199fc`
- end: `0x180019ad2`
- name: `?HrAddNSCInstance@@YAJPEAXQEAUHWND__@@@Z`
- size: `214`
- prototype: `int(void *, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bf2c`

## callees

- `0x180014274`
- `0x18001985c`
- `0x1800199fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019a5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019a5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019a82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019a3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019a3c`
- `USER32!IsWindow` at `0x180019a23`
- `USER32!IsWindow` at `0x180019a23`

## pseudocode

```c
__int64 __fastcall HrAddNSCInstance(void *a1, HWND a2)
{
  _QWORD *v5; // rax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  LPVOID v8; // [rsp+40h] [rbp+18h] BYREF

  if ( !a1 )
    return 2147500035LL;
  if ( !IsWindow(a2) )
    return 2147942487LL;
  v5 = CoTaskMemAlloc(0x10u);
  v8 = v5;
  if ( v5 )
  {
    v6 = 0;
    v5[1] = a1;
    *v5 = a2;
    EnterCriticalSection(&g_csNSCInstanceList);
    try
    {
      std::list<tagNSC_INSTANCE_DATA *>::_Emplace<tagNSC_INSTANCE_DATA * const &>(v7, g_NCSInstanceList, &v8);
    }
    catch ( ... )
    {
      CoTaskMemFree(v8);
      v6 = -2147024882;
    }
    LeaveCriticalSection(&g_csNSCInstanceList);
  }
  else
  {
    v6 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_31aceb967a8f36dcbf14b86f9200de5a_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1800199fc  mov     [rsp+arg_8], rbx
0x180019a01  mov     [rsp+arg_18], rsi
0x180019a06  push    rdi
0x180019a07  sub     rsp, 20h
0x180019a0b  mov     rsi, rdx
0x180019a0e  mov     rdi, rcx
0x180019a11  test    rcx, rcx
0x180019a14  jnz     short loc_180019A20
0x180019a16  mov     eax, 80004003h
0x180019a1b  jmp     loc_180019AC2
0x180019a20  mov     rcx, rsi; hWnd
0x180019a23  call    cs:__imp_IsWindow
0x180019a29  test    eax, eax
0x180019a2b  jnz     short loc_180019A37
0x180019a2d  mov     eax, 80070057h
0x180019a32  jmp     loc_180019AC2
0x180019a37  mov     ecx, 10h; cb
0x180019a3c  call    cs:__imp_CoTaskMemAlloc
0x180019a42  mov     [rsp+28h+arg_10], rax
0x180019a47  test    rax, rax
0x180019a4a  jz      short loc_180019A8A
0x180019a4c  xor     ebx, ebx
0x180019a4e  mov     [rax+8], rdi
0x180019a52  mov     [rax], rsi
0x180019a55  lea     rcx, ?g_csNSCInstanceList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019a5c  call    cs:__imp_EnterCriticalSection
0x180019a62  nop
0x180019a63  lea     r8, [rsp+28h+arg_10]
0x180019a68  mov     rdx, cs:?g_NCSInstanceList@@3V?$list@PEAUtagNSC_INSTANCE_DATA@@V?$allocator@PEAUtagNSC_INSTANCE_DATA@@@std@@@std@@A; std::list<tagNSC_INSTANCE_DATA *> g_NCSInstanceList
0x180019a6f  call    ??$_Emplace@AEBQEAUtagNSC_INSTANCE_DATA@@@?$list@PEAUtagNSC_INSTANCE_DATA@@V?$allocator@PEAUtagNSC_INSTANCE_DATA@@@std@@@std@@QEAAPEAU?$_List_node@PEAUtagNSC_INSTANCE_DATA@@PEAX@1@QEAU21@AEBQEAUtagNSC_INSTANCE_DATA@@@Z; std::list<tagNSC_INSTANCE_DATA *>::_Emplace<tagNSC_INSTANCE_DATA * const &>(std::_List_node<tagNSC_INSTANCE_DATA *,void *> * const,tagNSC_INSTANCE_DATA * const &)
0x180019a74  nop
0x180019a75  jmp     short loc_180019A7B
0x180019a77  mov     ebx, [rsp+28h+arg_0]
0x180019a7b  lea     rcx, ?g_csNSCInstanceList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019a82  call    cs:__imp_LeaveCriticalSection
0x180019a88  jmp     short loc_180019A8F
0x180019a8a  mov     ebx, 8007000Eh
0x180019a8f  lea     rax, WPP_GLOBAL_Control
0x180019a96  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a9d  cmp     rcx, rax
0x180019aa0  jz      short loc_180019AC0
0x180019aa2  test    byte ptr [rcx+1Ch], 8
0x180019aa6  jz      short loc_180019AC0
0x180019aa8  mov     edx, 11h
0x180019aad  mov     r9d, ebx
0x180019ab0  lea     r8, WPP_31aceb967a8f36dcbf14b86f9200de5a_Traceguids
0x180019ab7  mov     rcx, [rcx+10h]
0x180019abb  call    WPP_SF_d
0x180019ac0  mov     eax, ebx
0x180019ac2  mov     rbx, [rsp+28h+arg_8]
0x180019ac7  mov     rsi, [rsp+28h+arg_18]
0x180019acc  add     rsp, 20h
0x180019ad0  pop     rdi
0x180019ad1  retn
```
