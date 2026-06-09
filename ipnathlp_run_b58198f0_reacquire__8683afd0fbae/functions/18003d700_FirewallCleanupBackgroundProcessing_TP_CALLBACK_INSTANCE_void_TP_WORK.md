# FirewallCleanupBackgroundProcessing(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18003d700`
- end: `0x18003d8a8`
- name: `?FirewallCleanupBackgroundProcessing@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `424`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18003a66c`
- `0x18003d700`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003d76a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003d76a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003d781`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003d85b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003d781`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003d85b`
- `FirewallAPI!FWClosePolicyStore` at `0x18003d83b`
- `FirewallAPI!FWClosePolicyStore` at `0x18003d83b`
- `FirewallAPI!FWFreeFirewallRules` at `0x18003d81b`
- `FirewallAPI!FWFreeFirewallRules` at `0x18003d81b`
- `FirewallAPI!FWOpenPolicyStore` at `0x18003d7b2`
- `FirewallAPI!FWOpenPolicyStore` at `0x18003d7b2`
- `FirewallAPI!FWDeleteFirewallRule` at `0x18003d804`
- `FirewallAPI!FWDeleteFirewallRule` at `0x18003d804`

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
  int v10; // [rsp+30h] [rbp-38h]
  __int64 v11; // [rsp+78h] [rbp+10h] BYREF

  v3 = 0;
  v11 = 0;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
    v3 = v11;
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( Context )
  {
    CurrentThread = GetCurrentThread();
    v6 = SetThreadPriority(CurrentThread, 0x10000);
    v7 = FWOpenPolicyStore(545, 0, 2, 2, 0, &v11, v10);
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
        FWDeleteFirewallRule(v11, v9[2]);
        v9 = (_QWORD *)*v9;
      }
      while ( v9 );
    }
    FWFreeFirewallRules(Context);
    v3 = v11;
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
    FWClosePolicyStore(v3);
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
0x18003d700  push    rbx
0x18003d702  push    rbp
0x18003d703  push    rsi
0x18003d704  push    rdi
0x18003d705  push    r12
0x18003d707  push    r14
0x18003d709  sub     rsp, 38h
0x18003d70d  xor     eax, eax
0x18003d70f  mov     rdi, rdx
0x18003d712  mov     [rsp+68h+arg_8], rax
0x18003d717  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d71e  lea     r12, WPP_GLOBAL_Control
0x18003d725  cmp     rcx, r12
0x18003d728  jz      short loc_18003D758
0x18003d72a  test    dword ptr [rcx+1Ch], 200h
0x18003d731  jz      short loc_18003D758
0x18003d733  cmp     byte ptr [rcx+19h], 6
0x18003d737  jb      short loc_18003D758
0x18003d739  mov     rcx, [rcx+10h]
0x18003d73d  lea     edx, [rax+3Dh]
0x18003d740  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003d747  call    WPP_SF_
0x18003d74c  mov     rax, [rsp+68h+arg_8]
0x18003d751  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d758  test    rdi, rdi
0x18003d75b  jnz     short loc_18003D76A
0x18003d75d  xor     r14d, r14d
0x18003d760  lea     ebp, [rdi+57h]
0x18003d763  xor     esi, esi
0x18003d765  jmp     loc_18003D833
0x18003d76a  call    cs:__imp_GetCurrentThread
0x18003d771  nop     dword ptr [rax+rax+00h]
0x18003d776  mov     rcx, rax; hThread
0x18003d779  mov     edx, 10000h; nPriority
0x18003d77e  mov     rsi, rax
0x18003d781  call    cs:__imp_SetThreadPriority
0x18003d788  nop     dword ptr [rax+rax+00h]
0x18003d78d  mov     r8d, 2
0x18003d793  mov     ecx, 221h
0x18003d798  mov     r14d, eax
0x18003d79b  mov     r9d, r8d
0x18003d79e  lea     rax, [rsp+68h+arg_8]
0x18003d7a3  xor     edx, edx
0x18003d7a5  mov     [rsp+68h+var_40], rax
0x18003d7aa  mov     [rsp+68h+var_48], 0
0x18003d7b2  call    cs:__imp_FWOpenPolicyStore
0x18003d7b9  nop     dword ptr [rax+rax+00h]
0x18003d7be  mov     ebp, eax
0x18003d7c0  test    eax, eax
0x18003d7c2  jnz     short loc_18003D818
0x18003d7c4  mov     rbx, rdi
0x18003d7c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d7ce  cmp     rcx, r12
0x18003d7d1  jz      short loc_18003D7FB
0x18003d7d3  test    dword ptr [rcx+1Ch], 200h
0x18003d7da  jz      short loc_18003D7FB
0x18003d7dc  cmp     byte ptr [rcx+19h], 5
0x18003d7e0  jb      short loc_18003D7FB
0x18003d7e2  mov     r9, [rbx+10h]
0x18003d7e6  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003d7ed  mov     rcx, [rcx+10h]
0x18003d7f1  mov     edx, 3Eh ; '>'
0x18003d7f6  call    WPP_SF_S
0x18003d7fb  mov     rdx, [rbx+10h]
0x18003d7ff  mov     rcx, [rsp+68h+arg_8]
0x18003d804  call    cs:__imp_FWDeleteFirewallRule
0x18003d80b  nop     dword ptr [rax+rax+00h]
0x18003d810  mov     rbx, [rbx]
0x18003d813  test    rbx, rbx
0x18003d816  jnz     short loc_18003D7C7
0x18003d818  mov     rcx, rdi
0x18003d81b  call    cs:__imp_FWFreeFirewallRules
0x18003d822  nop     dword ptr [rax+rax+00h]
0x18003d827  mov     rax, [rsp+68h+arg_8]
0x18003d82c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d833  test    rax, rax
0x18003d836  jz      short loc_18003D84E
0x18003d838  mov     rcx, rax
0x18003d83b  call    cs:__imp_FWClosePolicyStore
0x18003d842  nop     dword ptr [rax+rax+00h]
0x18003d847  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d84e  test    r14d, r14d
0x18003d851  jz      short loc_18003D86E
0x18003d853  mov     edx, 20000h; nPriority
0x18003d858  mov     rcx, rsi; hThread
0x18003d85b  call    cs:__imp_SetThreadPriority
0x18003d862  nop     dword ptr [rax+rax+00h]
0x18003d867  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d86e  cmp     rcx, r12
0x18003d871  jz      short loc_18003D89A
0x18003d873  test    dword ptr [rcx+1Ch], 200h
0x18003d87a  jz      short loc_18003D89A
0x18003d87c  cmp     byte ptr [rcx+19h], 6
0x18003d880  jb      short loc_18003D89A
0x18003d882  mov     rcx, [rcx+10h]
0x18003d886  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003d88d  mov     edx, 3Fh ; '?'
0x18003d892  mov     r9d, ebp
0x18003d895  call    WPP_SF_d
0x18003d89a  add     rsp, 38h
0x18003d89e  pop     r14
0x18003d8a0  pop     r12
0x18003d8a2  pop     rdi
0x18003d8a3  pop     rsi
0x18003d8a4  pop     rbp
0x18003d8a5  pop     rbx
0x18003d8a6  retn
```
