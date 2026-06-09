# FirewallCleanupBackgroundProcessing(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18003a5c0`
- end: `0x18003a73d`
- name: `?FirewallCleanupBackgroundProcessing@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `381`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180037cf4`
- `0x18003a5c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003a62a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003a62a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003a63b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003a6f7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003a63b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003a6f7`
- `FirewallAPI!FWClosePolicyStore` at `0x18003a6dd`
- `FirewallAPI!FWClosePolicyStore` at `0x18003a6dd`
- `FirewallAPI!FWFreeFirewallRules` at `0x18003a6c3`
- `FirewallAPI!FWFreeFirewallRules` at `0x18003a6c3`
- `FirewallAPI!FWOpenPolicyStore` at `0x18003a666`
- `FirewallAPI!FWOpenPolicyStore` at `0x18003a666`
- `FirewallAPI!FWDeleteFirewallRule` at `0x18003a6b2`
- `FirewallAPI!FWDeleteFirewallRule` at `0x18003a6b2`

## pseudocode

```c
void __fastcall FirewallCleanupBackgroundProcessing(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context, PTP_WORK Work)
{
  __int64 v3; // rax
  PVOID *v5; // rcx
  BOOL v6; // r14d
  unsigned int v7; // ebp
  HANDLE CurrentThread; // rsi
  _QWORD *v9; // rbx
  __int64 v10; // [rsp+78h] [rbp+10h] BYREF

  v3 = 0;
  v10 = 0;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
    v3 = v10;
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( Context )
  {
    CurrentThread = GetCurrentThread();
    v6 = SetThreadPriority(CurrentThread, 0x10000);
    v7 = FWOpenPolicyStore(545, 0, 2, 2, 0, &v10);
    if ( !v7 )
    {
      v9 = Context;
      do
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v9[2]);
        }
        FWDeleteFirewallRule(v10, v9[2]);
        v9 = (_QWORD *)*v9;
      }
      while ( v9 );
    }
    FWFreeFirewallRules(Context);
    v3 = v10;
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v6 = 0;
    v7 = 87;
    CurrentThread = 0;
  }
  if ( v3 )
  {
    FWClosePolicyStore(v3, Context, Work);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    SetThreadPriority(CurrentThread, 0x20000);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x200) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 63, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v7);
}

```

## disassembly

```asm
0x18003a5c0  push    rbx
0x18003a5c2  push    rbp
0x18003a5c3  push    rsi
0x18003a5c4  push    rdi
0x18003a5c5  push    r12
0x18003a5c7  push    r14
0x18003a5c9  sub     rsp, 38h
0x18003a5cd  xor     eax, eax
0x18003a5cf  mov     rdi, rdx
0x18003a5d2  mov     [rsp+68h+arg_8], rax
0x18003a5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a5de  lea     r12, WPP_GLOBAL_Control
0x18003a5e5  cmp     rcx, r12
0x18003a5e8  jz      short loc_18003A618
0x18003a5ea  test    dword ptr [rcx+1Ch], 200h
0x18003a5f1  jz      short loc_18003A618
0x18003a5f3  cmp     byte ptr [rcx+19h], 6
0x18003a5f7  jb      short loc_18003A618
0x18003a5f9  mov     rcx, [rcx+10h]
0x18003a5fd  lea     edx, [rax+3Dh]
0x18003a600  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003a607  call    WPP_SF_
0x18003a60c  mov     rax, [rsp+68h+arg_8]
0x18003a611  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a618  test    rdi, rdi
0x18003a61b  jnz     short loc_18003A62A
0x18003a61d  xor     r14d, r14d
0x18003a620  lea     ebp, [rdi+57h]
0x18003a623  xor     esi, esi
0x18003a625  jmp     loc_18003A6D5
0x18003a62a  call    cs:__imp_GetCurrentThread
0x18003a630  mov     rcx, rax; hThread
0x18003a633  mov     edx, 10000h; nPriority
0x18003a638  mov     rsi, rax
0x18003a63b  call    cs:__imp_SetThreadPriority
0x18003a641  mov     r8d, 2
0x18003a647  mov     ecx, 221h
0x18003a64c  mov     r14d, eax
0x18003a64f  mov     r9d, r8d
0x18003a652  lea     rax, [rsp+68h+arg_8]
0x18003a657  xor     edx, edx
0x18003a659  mov     [rsp+68h+var_40], rax
0x18003a65e  mov     [rsp+68h+var_48], 0
0x18003a666  call    cs:__imp_FWOpenPolicyStore
0x18003a66c  mov     ebp, eax
0x18003a66e  test    eax, eax
0x18003a670  jnz     short loc_18003A6C0
0x18003a672  mov     rbx, rdi
0x18003a675  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a67c  cmp     rcx, r12
0x18003a67f  jz      short loc_18003A6A9
0x18003a681  test    dword ptr [rcx+1Ch], 200h
0x18003a688  jz      short loc_18003A6A9
0x18003a68a  cmp     byte ptr [rcx+19h], 5
0x18003a68e  jb      short loc_18003A6A9
0x18003a690  mov     r9, [rbx+10h]
0x18003a694  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003a69b  mov     rcx, [rcx+10h]
0x18003a69f  mov     edx, 3Eh ; '>'
0x18003a6a4  call    WPP_SF_S
0x18003a6a9  mov     rdx, [rbx+10h]
0x18003a6ad  mov     rcx, [rsp+68h+arg_8]
0x18003a6b2  call    cs:__imp_FWDeleteFirewallRule
0x18003a6b8  mov     rbx, [rbx]
0x18003a6bb  test    rbx, rbx
0x18003a6be  jnz     short loc_18003A675
0x18003a6c0  mov     rcx, rdi
0x18003a6c3  call    cs:__imp_FWFreeFirewallRules
0x18003a6c9  mov     rax, [rsp+68h+arg_8]
0x18003a6ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a6d5  test    rax, rax
0x18003a6d8  jz      short loc_18003A6EA
0x18003a6da  mov     rcx, rax
0x18003a6dd  call    cs:__imp_FWClosePolicyStore
0x18003a6e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a6ea  test    r14d, r14d
0x18003a6ed  jz      short loc_18003A704
0x18003a6ef  mov     edx, 20000h; nPriority
0x18003a6f4  mov     rcx, rsi; hThread
0x18003a6f7  call    cs:__imp_SetThreadPriority
0x18003a6fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a704  cmp     rcx, r12
0x18003a707  jz      short loc_18003A730
0x18003a709  test    dword ptr [rcx+1Ch], 200h
0x18003a710  jz      short loc_18003A730
0x18003a712  cmp     byte ptr [rcx+19h], 6
0x18003a716  jb      short loc_18003A730
0x18003a718  mov     rcx, [rcx+10h]
0x18003a71c  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003a723  mov     edx, 3Fh ; '?'
0x18003a728  mov     r9d, ebp
0x18003a72b  call    WPP_SF_d
0x18003a730  add     rsp, 38h
0x18003a734  pop     r14
0x18003a736  pop     r12
0x18003a738  pop     rdi
0x18003a739  pop     rsi
0x18003a73a  pop     rbp
0x18003a73b  pop     rbx
0x18003a73c  retn
```
