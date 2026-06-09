# RasRegisterPnPCommon

- ea: `0x18001d8b0`
- end: `0x18001db3e`
- name: `RasRegisterPnPCommon`
- size: `654`
- prototype: `__int64 __fastcall(__int64, void *, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001db50`
- `0x18001dc60`

## callees

- `0x180002f80`
- `0x18001d8b0`
- `0x180020fd8`
- `0x180021000`
- `0x18002151c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d9e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d9eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d9e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d9eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d903`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d903`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001da1a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001da1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da24`

## pseudocode

```c
__int64 __fastcall RasRegisterPnPCommon(__int64 a1, void *a2, __int64 a3, int a4)
{
  unsigned int v5; // edi
  DWORD CurrentProcessId; // eax
  DWORD v9; // r14d
  PVOID *v10; // rcx
  __int64 v11; // r9
  unsigned int v12; // ebx
  __int64 v13; // rdx
  HANDLE CurrentProcess; // rbx
  HANDLE v15; // rax
  unsigned int LastError; // eax
  __int64 bInheritHandle; // [rsp+28h] [rbp-50h]
  HANDLE TargetHandle; // [rsp+80h] [rbp+8h] BYREF

  v5 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qDc(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2, a3, a4 != 0);
  }
  CurrentProcessId = GetCurrentProcessId();
  v9 = CurrentProcessId;
  TargetHandle = 0;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      519,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 || (v5 & 2) == 0 && (v5 & 1) == 0 )
  {
    v11 = 87;
    v12 = 87;
    if ( v10 == &WPP_GLOBAL_Control )
      return v12;
    if ( (*((_BYTE *)v10 + 28) & 0x40) == 0 || *((_BYTE *)v10 + 25) < 2u )
      goto LABEL_42;
    v13 = 520;
    goto LABEL_40;
  }
  if ( (v5 & 1) == 0 )
    goto LABEL_30;
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 && *((_BYTE *)v10 + 25) >= 5u )
  {
    WPP_SF_(v10[2], 521, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a4 )
    goto LABEL_30;
  if ( a2 )
  {
    CurrentProcess = GetCurrentProcess();
    v15 = GetCurrentProcess();
    if ( !DuplicateHandle(v15, a2, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( !LastError )
        goto LABEL_41;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v12;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_42;
      v13 = 523;
      goto LABEL_29;
    }
LABEL_30:
    LODWORD(bInheritHandle) = a4;
    LastError = SubmitLocalRequest(0x56u, a1, v5, v9, TargetHandle, bInheritHandle);
    v12 = LastError;
    if ( !LastError )
      goto LABEL_41;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v12;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_42;
    v13 = 524;
LABEL_29:
    v11 = LastError;
    goto LABEL_40;
  }
  v11 = 87;
  v12 = 87;
  if ( v10 == &WPP_GLOBAL_Control )
    return v12;
  if ( (*((_BYTE *)v10 + 28) & 0x40) != 0 && *((_BYTE *)v10 + 25) >= 2u )
  {
    v13 = 522;
LABEL_40:
    WPP_SF_d(v10[2], v13, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v11);
LABEL_41:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_42:
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 525, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x18001d8b0  push    rbx
0x18001d8b2  push    rbp
0x18001d8b3  push    rsi
0x18001d8b4  push    rdi
0x18001d8b5  push    r14
0x18001d8b7  push    r15
0x18001d8b9  sub     rsp, 48h
0x18001d8bd  mov     ebp, r9d
0x18001d8c0  mov     edi, r8d
0x18001d8c3  mov     rsi, rdx
0x18001d8c6  mov     r15, rcx
0x18001d8c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d8d0  lea     rbx, WPP_GLOBAL_Control
0x18001d8d7  cmp     rcx, rbx
0x18001d8da  jz      short loc_18001D903
0x18001d8dc  test    byte ptr [rcx+1Ch], 40h
0x18001d8e0  jz      short loc_18001D903
0x18001d8e2  cmp     byte ptr [rcx+19h], 6
0x18001d8e6  jb      short loc_18001D903
0x18001d8e8  mov     rcx, [rcx+10h]
0x18001d8ec  test    r9d, r9d
0x18001d8ef  mov     r9, rdx
0x18001d8f2  setnz   al
0x18001d8f5  mov     byte ptr [rsp+78h+bInheritHandle], al
0x18001d8f9  mov     [rsp+78h+dwDesiredAccess], r8d
0x18001d8fe  call    WPP_SF_qDc
0x18001d903  call    cs:__imp_GetCurrentProcessId
0x18001d909  mov     r14d, eax
0x18001d90c  mov     [rsp+78h+TargetHandle], 0
0x18001d918  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d91f  cmp     rcx, rbx
0x18001d922  jz      short loc_18001D94F
0x18001d924  test    byte ptr [rcx+1Ch], 40h
0x18001d928  jz      short loc_18001D94F
0x18001d92a  cmp     byte ptr [rcx+19h], 5
0x18001d92e  jb      short loc_18001D94F
0x18001d930  mov     rcx, [rcx+10h]
0x18001d934  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d93b  mov     edx, 207h
0x18001d940  mov     r9d, eax
0x18001d943  call    WPP_SF_d
0x18001d948  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d94f  test    r15, r15
0x18001d952  jz      loc_18001DAC9
0x18001d958  mov     edx, edi
0x18001d95a  and     edx, 1
0x18001d95d  test    dil, 2
0x18001d961  jnz     short loc_18001D96B
0x18001d963  test    edx, edx
0x18001d965  jz      loc_18001DAC9
0x18001d96b  test    edx, edx
0x18001d96d  jz      loc_18001DA6C
0x18001d973  cmp     rcx, rbx
0x18001d976  jz      short loc_18001D9A0
0x18001d978  test    byte ptr [rcx+1Ch], 40h
0x18001d97c  jz      short loc_18001D9A0
0x18001d97e  cmp     byte ptr [rcx+19h], 5
0x18001d982  jb      short loc_18001D9A0
0x18001d984  mov     rcx, [rcx+10h]
0x18001d988  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d98f  mov     edx, 209h
0x18001d994  call    WPP_SF_
0x18001d999  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9a0  test    ebp, ebp
0x18001d9a2  jz      loc_18001DA6C
0x18001d9a8  test    rsi, rsi
0x18001d9ab  jnz     short loc_18001D9E2
0x18001d9ad  lea     r9d, [rsi+57h]
0x18001d9b1  mov     ebx, r9d
0x18001d9b4  lea     rdi, WPP_GLOBAL_Control
0x18001d9bb  cmp     rcx, rdi
0x18001d9be  jz      loc_18001DB2F
0x18001d9c4  test    byte ptr [rcx+1Ch], 40h
0x18001d9c8  jz      loc_18001DB06
0x18001d9ce  cmp     byte ptr [rcx+19h], 2
0x18001d9d2  jb      loc_18001DB06
0x18001d9d8  mov     edx, 20Ah
0x18001d9dd  jmp     loc_18001DAEF
0x18001d9e2  call    cs:__imp_GetCurrentProcess
0x18001d9e8  mov     rbx, rax
0x18001d9eb  call    cs:__imp_GetCurrentProcess
0x18001d9f1  mov     [rsp+78h+dwOptions], 2; dwOptions
0x18001d9f9  lea     r9, [rsp+78h+TargetHandle]; lpTargetHandle
0x18001da01  mov     rcx, rax; hSourceProcessHandle
0x18001da04  mov     dword ptr [rsp+78h+bInheritHandle], 0; bInheritHandle
0x18001da0c  mov     r8, rbx; hTargetProcessHandle
0x18001da0f  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x18001da17  mov     rdx, rsi; hSourceHandle
0x18001da1a  call    cs:__imp_DuplicateHandle
0x18001da20  test    eax, eax
0x18001da22  jnz     short loc_18001DA6C
0x18001da24  call    cs:__imp_GetLastError
0x18001da2a  mov     ebx, eax
0x18001da2c  test    eax, eax
0x18001da2e  jz      loc_18001DAC0
0x18001da34  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da3b  lea     rdi, WPP_GLOBAL_Control
0x18001da42  cmp     rcx, rdi
0x18001da45  jz      loc_18001DB2F
0x18001da4b  test    byte ptr [rcx+1Ch], 40h
0x18001da4f  jz      loc_18001DB06
0x18001da55  cmp     byte ptr [rcx+19h], 2
0x18001da59  jb      loc_18001DB06
0x18001da5f  mov     edx, 20Bh
0x18001da64  mov     r9d, eax
0x18001da67  jmp     loc_18001DAEF
0x18001da6c  mov     rax, [rsp+78h+TargetHandle]
0x18001da74  mov     ecx, 56h ; 'V'
0x18001da79  mov     dword ptr [rsp+78h+bInheritHandle], ebp
0x18001da7d  mov     r9d, r14d
0x18001da80  mov     r8d, edi
0x18001da83  mov     qword ptr [rsp+78h+dwDesiredAccess], rax
0x18001da88  mov     rdx, r15
0x18001da8b  call    SubmitLocalRequest
0x18001da90  mov     ebx, eax
0x18001da92  test    eax, eax
0x18001da94  jz      short loc_18001DAC0
0x18001da96  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da9d  lea     rdi, WPP_GLOBAL_Control
0x18001daa4  cmp     rcx, rdi
0x18001daa7  jz      loc_18001DB2F
0x18001daad  test    byte ptr [rcx+1Ch], 40h
0x18001dab1  jz      short loc_18001DB06
0x18001dab3  cmp     byte ptr [rcx+19h], 2
0x18001dab7  jb      short loc_18001DB06
0x18001dab9  mov     edx, 20Ch
0x18001dabe  jmp     short loc_18001DA64
0x18001dac0  lea     rdi, WPP_GLOBAL_Control
0x18001dac7  jmp     short loc_18001DAFF
0x18001dac9  mov     r9d, 57h ; 'W'
0x18001dacf  mov     ebx, r9d
0x18001dad2  lea     rdi, WPP_GLOBAL_Control
0x18001dad9  cmp     rcx, rdi
0x18001dadc  jz      short loc_18001DB2F
0x18001dade  test    byte ptr [rcx+1Ch], 40h
0x18001dae2  jz      short loc_18001DB06
0x18001dae4  cmp     byte ptr [rcx+19h], 2
0x18001dae8  jb      short loc_18001DB06
0x18001daea  mov     edx, 208h
0x18001daef  mov     rcx, [rcx+10h]
0x18001daf3  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001dafa  call    WPP_SF_d
0x18001daff  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db06  cmp     rcx, rdi
0x18001db09  jz      short loc_18001DB2F
0x18001db0b  test    byte ptr [rcx+1Ch], 40h
0x18001db0f  jz      short loc_18001DB2F
0x18001db11  cmp     byte ptr [rcx+19h], 6
0x18001db15  jb      short loc_18001DB2F
0x18001db17  mov     rcx, [rcx+10h]
0x18001db1b  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001db22  mov     edx, 20Dh
0x18001db27  mov     r9d, ebx
0x18001db2a  call    WPP_SF_d
0x18001db2f  mov     eax, ebx
0x18001db31  add     rsp, 48h
0x18001db35  pop     r15
0x18001db37  pop     r14
0x18001db39  pop     rdi
0x18001db3a  pop     rsi
0x18001db3b  pop     rbp
0x18001db3c  pop     rbx
0x18001db3d  retn
```
