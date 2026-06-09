# RasRegisterPnPCommon

- ea: `0x18001e310`
- end: `0x18001e5bd`
- name: `RasRegisterPnPCommon`
- size: `685`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e5d0`
- `0x18001e6f0`

## callees

- `0x1800030d0`
- `0x18001e310`
- `0x180021ae4`
- `0x180021b14`
- `0x180022074`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e448`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e457`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e448`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e457`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e363`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e363`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001e48c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001e48c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e49c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e49c`

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
0x18001e310  push    rbx
0x18001e312  push    rbp
0x18001e313  push    rsi
0x18001e314  push    rdi
0x18001e315  push    r14
0x18001e317  push    r15
0x18001e319  sub     rsp, 48h
0x18001e31d  mov     ebp, r9d
0x18001e320  mov     edi, r8d
0x18001e323  mov     rsi, rdx
0x18001e326  mov     r15, rcx
0x18001e329  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e330  lea     rbx, WPP_GLOBAL_Control
0x18001e337  cmp     rcx, rbx
0x18001e33a  jz      short loc_18001E363
0x18001e33c  test    byte ptr [rcx+1Ch], 40h
0x18001e340  jz      short loc_18001E363
0x18001e342  cmp     byte ptr [rcx+19h], 6
0x18001e346  jb      short loc_18001E363
0x18001e348  mov     rcx, [rcx+10h]
0x18001e34c  test    r9d, r9d
0x18001e34f  mov     r9, rdx
0x18001e352  setnz   al
0x18001e355  mov     byte ptr [rsp+78h+bInheritHandle], al
0x18001e359  mov     [rsp+78h+dwDesiredAccess], r8d
0x18001e35e  call    WPP_SF_qDc
0x18001e363  call    cs:__imp_GetCurrentProcessId
0x18001e36a  nop     dword ptr [rax+rax+00h]
0x18001e36f  mov     r14d, eax
0x18001e372  mov     [rsp+78h+TargetHandle], 0
0x18001e37e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e385  cmp     rcx, rbx
0x18001e388  jz      short loc_18001E3B5
0x18001e38a  test    byte ptr [rcx+1Ch], 40h
0x18001e38e  jz      short loc_18001E3B5
0x18001e390  cmp     byte ptr [rcx+19h], 5
0x18001e394  jb      short loc_18001E3B5
0x18001e396  mov     rcx, [rcx+10h]
0x18001e39a  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e3a1  mov     edx, 207h
0x18001e3a6  mov     r9d, eax
0x18001e3a9  call    WPP_SF_d
0x18001e3ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3b5  test    r15, r15
0x18001e3b8  jz      loc_18001E547
0x18001e3be  mov     edx, edi
0x18001e3c0  and     edx, 1
0x18001e3c3  test    dil, 2
0x18001e3c7  jnz     short loc_18001E3D1
0x18001e3c9  test    edx, edx
0x18001e3cb  jz      loc_18001E547
0x18001e3d1  test    edx, edx
0x18001e3d3  jz      loc_18001E4EA
0x18001e3d9  cmp     rcx, rbx
0x18001e3dc  jz      short loc_18001E406
0x18001e3de  test    byte ptr [rcx+1Ch], 40h
0x18001e3e2  jz      short loc_18001E406
0x18001e3e4  cmp     byte ptr [rcx+19h], 5
0x18001e3e8  jb      short loc_18001E406
0x18001e3ea  mov     rcx, [rcx+10h]
0x18001e3ee  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e3f5  mov     edx, 209h
0x18001e3fa  call    WPP_SF_
0x18001e3ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e406  test    ebp, ebp
0x18001e408  jz      loc_18001E4EA
0x18001e40e  test    rsi, rsi
0x18001e411  jnz     short loc_18001E448
0x18001e413  lea     r9d, [rsi+57h]
0x18001e417  mov     ebx, r9d
0x18001e41a  lea     rdi, WPP_GLOBAL_Control
0x18001e421  cmp     rcx, rdi
0x18001e424  jz      loc_18001E5AD
0x18001e42a  test    byte ptr [rcx+1Ch], 40h
0x18001e42e  jz      loc_18001E584
0x18001e434  cmp     byte ptr [rcx+19h], 2
0x18001e438  jb      loc_18001E584
0x18001e43e  mov     edx, 20Ah
0x18001e443  jmp     loc_18001E56D
0x18001e448  call    cs:__imp_GetCurrentProcess
0x18001e44f  nop     dword ptr [rax+rax+00h]
0x18001e454  mov     rbx, rax
0x18001e457  call    cs:__imp_GetCurrentProcess
0x18001e45e  nop     dword ptr [rax+rax+00h]
0x18001e463  mov     [rsp+78h+dwOptions], 2; dwOptions
0x18001e46b  lea     r9, [rsp+78h+TargetHandle]; lpTargetHandle
0x18001e473  mov     rcx, rax; hSourceProcessHandle
0x18001e476  mov     dword ptr [rsp+78h+bInheritHandle], 0; bInheritHandle
0x18001e47e  mov     r8, rbx; hTargetProcessHandle
0x18001e481  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x18001e489  mov     rdx, rsi; hSourceHandle
0x18001e48c  call    cs:__imp_DuplicateHandle
0x18001e493  nop     dword ptr [rax+rax+00h]
0x18001e498  test    eax, eax
0x18001e49a  jnz     short loc_18001E4EA
0x18001e49c  call    cs:__imp_GetLastError
0x18001e4a3  nop     dword ptr [rax+rax+00h]
0x18001e4a8  mov     ebx, eax
0x18001e4aa  test    eax, eax
0x18001e4ac  jz      loc_18001E53E
0x18001e4b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e4b9  lea     rdi, WPP_GLOBAL_Control
0x18001e4c0  cmp     rcx, rdi
0x18001e4c3  jz      loc_18001E5AD
0x18001e4c9  test    byte ptr [rcx+1Ch], 40h
0x18001e4cd  jz      loc_18001E584
0x18001e4d3  cmp     byte ptr [rcx+19h], 2
0x18001e4d7  jb      loc_18001E584
0x18001e4dd  mov     edx, 20Bh
0x18001e4e2  mov     r9d, eax
0x18001e4e5  jmp     loc_18001E56D
0x18001e4ea  mov     rax, [rsp+78h+TargetHandle]
0x18001e4f2  mov     ecx, 56h ; 'V'
0x18001e4f7  mov     dword ptr [rsp+78h+bInheritHandle], ebp
0x18001e4fb  mov     r9d, r14d
0x18001e4fe  mov     r8d, edi
0x18001e501  mov     qword ptr [rsp+78h+dwDesiredAccess], rax
0x18001e506  mov     rdx, r15
0x18001e509  call    SubmitLocalRequest
0x18001e50e  mov     ebx, eax
0x18001e510  test    eax, eax
0x18001e512  jz      short loc_18001E53E
0x18001e514  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e51b  lea     rdi, WPP_GLOBAL_Control
0x18001e522  cmp     rcx, rdi
0x18001e525  jz      loc_18001E5AD
0x18001e52b  test    byte ptr [rcx+1Ch], 40h
0x18001e52f  jz      short loc_18001E584
0x18001e531  cmp     byte ptr [rcx+19h], 2
0x18001e535  jb      short loc_18001E584
0x18001e537  mov     edx, 20Ch
0x18001e53c  jmp     short loc_18001E4E2
0x18001e53e  lea     rdi, WPP_GLOBAL_Control
0x18001e545  jmp     short loc_18001E57D
0x18001e547  mov     r9d, 57h ; 'W'
0x18001e54d  mov     ebx, r9d
0x18001e550  lea     rdi, WPP_GLOBAL_Control
0x18001e557  cmp     rcx, rdi
0x18001e55a  jz      short loc_18001E5AD
0x18001e55c  test    byte ptr [rcx+1Ch], 40h
0x18001e560  jz      short loc_18001E584
0x18001e562  cmp     byte ptr [rcx+19h], 2
0x18001e566  jb      short loc_18001E584
0x18001e568  mov     edx, 208h
0x18001e56d  mov     rcx, [rcx+10h]
0x18001e571  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e578  call    WPP_SF_d
0x18001e57d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e584  cmp     rcx, rdi
0x18001e587  jz      short loc_18001E5AD
0x18001e589  test    byte ptr [rcx+1Ch], 40h
0x18001e58d  jz      short loc_18001E5AD
0x18001e58f  cmp     byte ptr [rcx+19h], 6
0x18001e593  jb      short loc_18001E5AD
0x18001e595  mov     rcx, [rcx+10h]
0x18001e599  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e5a0  mov     edx, 20Dh
0x18001e5a5  mov     r9d, ebx
0x18001e5a8  call    WPP_SF_d
0x18001e5ad  mov     eax, ebx
0x18001e5af  add     rsp, 48h
0x18001e5b3  pop     r15
0x18001e5b5  pop     r14
0x18001e5b7  pop     rdi
0x18001e5b8  pop     rsi
0x18001e5b9  pop     rbp
0x18001e5ba  pop     rbx
0x18001e5bb  retn
```
