# CInterfaceMonitor::NsiInterfaceChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)

- ea: `0x180029bf0`
- end: `0x180029d58`
- name: `?NsiInterfaceChangeCallback@CInterfaceMonitor@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z`
- size: `360`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000c110`
- `0x180029bf0`
- `0x1800646f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029c6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029c6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029c97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029c97`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180029c83`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180029c83`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180029c8d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180029c8d`

## pseudocode

```c
void __fastcall CInterfaceMonitor::NsiInterfaceChangeCallback(__int64 a1, _QWORD **a2, __int64 a3, int a4)
{
  PVOID *v8; // rcx
  unsigned int v9; // eax
  _DWORD *v10; // rdx
  __int64 v11; // r8
  struct _TP_WORK *v12; // rcx
  __int64 v13; // rdx

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    if ( !a4 && *(_DWORD *)a3 == 1 && *(_DWORD *)(a3 + 20) == 536 )
    {
      v9 = *(_DWORD *)(a3 + 16);
      if ( v9 >= 4 )
      {
        v10 = *(_DWORD **)(a3 + 8);
        v11 = 0;
        if ( v9 >= 8 )
          v11 = (unsigned int)v10[1];
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 && *((_BYTE *)v8 + 25) >= 6u )
          WPP_SF_idD(v8[2], v10, v11, **a2, *v10, v11);
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
        v12 = *(struct _TP_WORK **)(a1 + 8);
        if ( v12 )
        {
          WaitForThreadpoolWorkCallbacks(v12, 1);
          SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 8));
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          v13 = 30;
LABEL_18:
          WPP_SF_(v8[2], v13, &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids);
        }
      }
    }
  }
  else if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 && *((_BYTE *)v8 + 25) >= 6u )
  {
    v13 = 28;
    goto LABEL_18;
  }
}

```

## disassembly

```asm
0x180029bf0  push    rbx
0x180029bf2  push    rbp
0x180029bf3  push    rsi
0x180029bf4  push    rdi
0x180029bf5  push    r14
0x180029bf7  sub     rsp, 30h
0x180029bfb  mov     edi, r9d
0x180029bfe  mov     rsi, r8
0x180029c01  mov     r14, rdx
0x180029c04  mov     rbx, rcx
0x180029c07  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c0e  lea     rbp, WPP_GLOBAL_Control
0x180029c15  cmp     rcx, rbp
0x180029c18  jz      short loc_180029C24
0x180029c1a  test    byte ptr [rcx+1Ch], 10h
0x180029c1e  jnz     loc_180029CD3
0x180029c24  test    rbx, rbx
0x180029c27  jz      loc_180029D31
0x180029c2d  test    edi, edi
0x180029c2f  jz      short loc_180029C3C
0x180029c31  add     rsp, 30h
0x180029c35  pop     r14
0x180029c37  pop     rdi
0x180029c38  pop     rsi
0x180029c39  pop     rbp
0x180029c3a  pop     rbx
0x180029c3b  retn
0x180029c3c  cmp     dword ptr [rsi], 1
0x180029c3f  jnz     short loc_180029C31
0x180029c41  cmp     dword ptr [rsi+14h], 218h
0x180029c48  jnz     short loc_180029C31
0x180029c4a  mov     eax, [rsi+10h]
0x180029c4d  cmp     eax, 4
0x180029c50  jb      short loc_180029C31
0x180029c52  mov     rdx, [rsi+8]
0x180029c56  xor     r8d, r8d
0x180029c59  cmp     eax, 8
0x180029c5c  jb      short loc_180029C62
0x180029c5e  mov     r8d, [rdx+4]
0x180029c62  cmp     rcx, rbp
0x180029c65  jnz     loc_180029CFE
0x180029c6b  lea     rcx, [rbx+58h]; lpCriticalSection
0x180029c6f  call    cs:__imp_EnterCriticalSection
0x180029c75  mov     rcx, [rbx+8]; pwk
0x180029c79  test    rcx, rcx
0x180029c7c  jz      short loc_180029C93
0x180029c7e  mov     edx, 1; fCancelPendingCallbacks
0x180029c83  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180029c89  mov     rcx, [rbx+8]; pwk
0x180029c8d  call    cs:__imp_SubmitThreadpoolWork
0x180029c93  lea     rcx, [rbx+58h]; lpCriticalSection
0x180029c97  call    cs:__imp_LeaveCriticalSection
0x180029c9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ca4  cmp     rcx, rbp
0x180029ca7  jz      short loc_180029C31
0x180029ca9  test    byte ptr [rcx+1Ch], 10h
0x180029cad  jz      short loc_180029C31
0x180029caf  cmp     byte ptr [rcx+19h], 6
0x180029cb3  jb      loc_180029C31
0x180029cb9  mov     edx, 1Eh
0x180029cbe  mov     rcx, [rcx+10h]
0x180029cc2  lea     r8, WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids
0x180029cc9  call    WPP_SF_
0x180029cce  jmp     loc_180029C31
0x180029cd3  cmp     byte ptr [rcx+19h], 6
0x180029cd7  jb      loc_180029C24
0x180029cdd  mov     rcx, [rcx+10h]
0x180029ce1  lea     r8, WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids
0x180029ce8  mov     edx, 1Bh
0x180029ced  call    WPP_SF_
0x180029cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180029cf9  jmp     loc_180029C24
0x180029cfe  test    byte ptr [rcx+1Ch], 10h
0x180029d02  jz      loc_180029C6B
0x180029d08  cmp     byte ptr [rcx+19h], 6
0x180029d0c  jb      loc_180029C6B
0x180029d12  mov     r9, [r14]
0x180029d15  mov     eax, [rdx]
0x180029d17  mov     rcx, [rcx+10h]
0x180029d1b  mov     [rsp+58h+var_30], r8d
0x180029d20  mov     r9, [r9]
0x180029d23  mov     [rsp+58h+var_38], eax
0x180029d27  call    WPP_SF_idD
0x180029d2c  jmp     loc_180029C6B
0x180029d31  cmp     rcx, rbp
0x180029d34  jz      loc_180029C31
0x180029d3a  test    byte ptr [rcx+1Ch], 10h
0x180029d3e  jz      loc_180029C31
0x180029d44  cmp     byte ptr [rcx+19h], 6
0x180029d48  jb      loc_180029C31
0x180029d4e  mov     edx, 1Ch
0x180029d53  jmp     loc_180029CBE
```
