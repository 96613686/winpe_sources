# UlFindUrlGroupId

- ea: `0x1400d42f4`
- end: `0x1400d45b9`
- name: `UlFindUrlGroupId`
- size: `709`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400cbd30`
- `0x1400efd00`

## callees

- `0x14000a350`
- `0x1400272c8`
- `0x14009622c`
- `0x1400a1f70`
- `0x1400a4790`
- `0x1400d42f4`
- `0x140167b40`
- `0x1401c3008`
- `0x1401c8bcc`
- `0x1401c8d4c`
- `0x1401c9134`
- `0x1401c91f8`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d43db`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d43db`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d44ca`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d44ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d44d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d44d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4521`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4521`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d43c6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d43c6`

## pseudocode

```c
__int64 __fastcall UlFindUrlGroupId(__int64 a1, __int64 a2, void *a3, _QWORD *a4, _QWORD *a5)
{
  int v9; // edx
  int v10; // ecx
  int v11; // r8d
  _QWORD *v12; // r12
  int v13; // eax
  __int64 v14; // r8
  unsigned int v15; // ebx
  __int64 v16; // rdi
  int RegistrationNode; // eax
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  PVOID v22; // rcx
  ULONG_PTR v23; // rdx
  int v24; // eax
  ULONG_PTR BugCheckParameter2; // [rsp+40h] [rbp-71h] BYREF
  __int64 v27; // [rsp+48h] [rbp-69h] BYREF
  _BYTE v28[144]; // [rsp+50h] [rbp-61h] BYREF
  PVOID P; // [rsp+128h] [rbp+77h] BYREF

  BugCheckParameter2 = 0;
  P = 0;
  memset(v28, 0, 0x88u);
  v27 = 0;
  v12 = a5;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qSqqq(v10, v9, v11, a1, *(_QWORD *)(a2 + 8), (char)a3, (char)a4, (char)a5);
  *a4 = 0;
  v13 = UlReferenceRequestQueueByHandle(a3, &BugCheckParameter2);
  v15 = v13;
  if ( v13 < 0 )
  {
    if ( (xmmword_1401A2C90 & 0x10) == 0 )
      goto LABEL_23;
    v21 = 131;
    goto LABEL_22;
  }
  LOBYTE(v14) = 1;
  v13 = UlSanitizeUrl(a1, *(_QWORD *)(a2 + 8), v14, (unsigned int)&P, (__int64)v28);
  v15 = v13;
  if ( v13 < 0 )
  {
    if ( (xmmword_1401A2C90 & 0x10) == 0 )
      goto LABEL_23;
    v21 = 132;
LABEL_22:
    WPP_SF_d(516, v21, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, (unsigned int)v13);
    goto LABEL_23;
  }
  KeEnterCriticalRegion();
  v16 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(a1 + 1368), 0);
  RegistrationNode = UlpTreeFindRegistrationNode(a1, P, &v27);
  v15 = RegistrationNode;
  if ( RegistrationNode < 0 )
  {
    if ( (xmmword_1401A2C90 & 0x10) != 0 )
      WPP_SF_Sd(516, 133, (unsigned int)WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, (_DWORD)P, RegistrationNode);
  }
  else
  {
    v19 = v27;
    v20 = *(_QWORD *)(v27 + 88);
    if ( (*(_DWORD *)(v20 + 64) & 1) != 0 && *(_QWORD *)(v20 + 72) == BugCheckParameter2 )
    {
      *a4 = *(_QWORD *)(v20 + 8);
      *v12 = *(_QWORD *)(v19 + 80);
      v27 = 0;
    }
    else
    {
      if ( UxKirHttpBugFix25Q1 )
      {
        if ( (xmmword_1401A2C90 & 0x10) != 0 )
          WPP_SF_qiDqq(v18, *(_DWORD *)(v20 + 64) & 1, v27, v20);
      }
      else if ( (xmmword_1401A2C90 & 0x10) != 0 )
      {
        WPP_SF_qq(516, 135, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids, v20, *(_QWORD *)(v20 + 8));
      }
      v15 = -1073741790;
    }
  }
  ExReleaseCacheAwarePushLockSharedEx(v16, 0);
  KeLeaveCriticalRegion();
LABEL_23:
  v22 = P;
  if ( P )
  {
    ExFreePoolWithTag(P, 0);
    P = 0;
  }
  v23 = BugCheckParameter2;
  if ( BugCheckParameter2 )
  {
    v24 = _InterlockedDecrement((volatile signed __int32 *)BugCheckParameter2);
    if ( UxDebugCheckRefcount && v24 <= -1 )
      UlBugCheckEx(3u, v23, 0xAu, v24);
    if ( !v24 )
      UlFreeRequestQueue((PSECURITY_DESCRIPTOR *)BugCheckParameter2);
    BugCheckParameter2 = 0;
  }
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_iId(v22, v23, v14, *a4, *v12, v15);
  return v15;
}

```

## disassembly

```asm
0x1400d42f4  mov     [rsp-8+arg_0], rbx
0x1400d42f9  mov     [rsp-8+arg_8], rsi
0x1400d42fe  push    rbp
0x1400d42ff  push    rdi
0x1400d4300  push    r12
0x1400d4302  push    r14
0x1400d4304  push    r15
0x1400d4306  lea     rbp, [rsp-2Fh]
0x1400d430b  sub     rsp, 0E0h
0x1400d4312  mov     r14, r8
0x1400d4315  mov     [rbp+4Fh+BugCheckParameter2], 0
0x1400d431d  mov     rdi, rdx
0x1400d4320  mov     [rbp+4Fh+P], 0
0x1400d4328  mov     rsi, rcx
0x1400d432b  xor     edx, edx; Val
0x1400d432d  mov     r8d, 88h; Size
0x1400d4333  lea     rcx, [rbp+4Fh+var_B0]; void *
0x1400d4337  mov     r15, r9
0x1400d433a  call    memset
0x1400d433f  mov     [rbp+4Fh+var_B8], 0
0x1400d4347  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400d434e  mov     r12, [rbp+4Fh+arg_20]
0x1400d4352  jz      short loc_1400D4374
0x1400d4354  mov     rax, [rdi+8]
0x1400d4358  mov     r9, rsi
0x1400d435b  mov     [rsp+100h+var_C8], r12
0x1400d4360  mov     [rsp+100h+var_D0], r15
0x1400d4365  mov     [rsp+100h+var_D8], r14
0x1400d436a  mov     [rsp+100h+var_E0], rax
0x1400d436f  call    WPP_SF_qSqqq
0x1400d4374  mov     r9d, 0Fh
0x1400d437a  mov     qword ptr [r15], 0
0x1400d4381  lea     rax, [rbp+4Fh+BugCheckParameter2]
0x1400d4385  mov     rcx, r14; Handle
0x1400d4388  mov     [rsp+100h+var_E0], rax; PVOID
0x1400d438d  lea     r8d, [r9-0Eh]
0x1400d4391  call    UlReferenceRequestQueueByHandle
0x1400d4396  mov     ebx, eax
0x1400d4398  test    eax, eax
0x1400d439a  js      loc_1400D44F4
0x1400d43a0  mov     rdx, [rdi+8]
0x1400d43a4  lea     rax, [rbp+4Fh+var_B0]
0x1400d43a8  lea     r9, [rbp+4Fh+P]
0x1400d43ac  mov     [rsp+100h+var_E0], rax
0x1400d43b1  mov     r8b, 1
0x1400d43b4  mov     rcx, rsi
0x1400d43b7  call    UlSanitizeUrl
0x1400d43bc  mov     ebx, eax
0x1400d43be  test    eax, eax
0x1400d43c0  js      loc_1400D44E4
0x1400d43c6  call    cs:__imp_KeEnterCriticalRegion
0x1400d43cd  nop     dword ptr [rax+rax+00h]
0x1400d43d2  mov     rcx, [rsi+558h]
0x1400d43d9  xor     edx, edx
0x1400d43db  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400d43e2  nop     dword ptr [rax+rax+00h]
0x1400d43e7  mov     rdx, [rbp+4Fh+P]
0x1400d43eb  lea     r8, [rbp+4Fh+var_B8]
0x1400d43ef  mov     rcx, rsi
0x1400d43f2  mov     rdi, rax
0x1400d43f5  call    UlpTreeFindRegistrationNode
0x1400d43fa  mov     ebx, eax
0x1400d43fc  test    eax, eax
0x1400d43fe  js      loc_1400D449E
0x1400d4404  mov     r8, [rbp+4Fh+var_B8]
0x1400d4408  mov     r10, [rbp+4Fh+BugCheckParameter2]
0x1400d440c  mov     r9, [r8+58h]
0x1400d4410  mov     edx, [r9+40h]
0x1400d4414  and     edx, 1
0x1400d4417  jz      short loc_1400D443B
0x1400d4419  cmp     [r9+48h], r10
0x1400d441d  jnz     short loc_1400D443B
0x1400d441f  mov     rax, [r9+8]
0x1400d4423  mov     [r15], rax
0x1400d4426  mov     rax, [r8+50h]
0x1400d442a  mov     [r12], rax
0x1400d442e  mov     [rbp+4Fh+var_B8], 0
0x1400d4436  jmp     loc_1400D44C5
0x1400d443b  cmp     cs:UxKirHttpBugFix25Q1, 0
0x1400d4442  jz      short loc_1400D446F
0x1400d4444  test    byte ptr cs:xmmword_1401A2C90, 10h
0x1400d444b  jz      short loc_1400D4497
0x1400d444d  mov     rax, [r9+48h]
0x1400d4451  mov     [rsp+100h+var_C8], r10
0x1400d4456  mov     [rsp+100h+var_D0], rax
0x1400d445b  mov     rax, [r9+8]
0x1400d445f  mov     dword ptr [rsp+100h+var_D8], edx
0x1400d4463  mov     [rsp+100h+var_E0], rax
0x1400d4468  call    WPP_SF_qiDqq
0x1400d446d  jmp     short loc_1400D4497
0x1400d446f  test    byte ptr cs:xmmword_1401A2C90, 10h
0x1400d4476  jz      short loc_1400D4497
0x1400d4478  mov     rax, [r9+8]
0x1400d447c  lea     r8, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids
0x1400d4483  mov     edx, 87h
0x1400d4488  mov     [rsp+100h+var_E0], rax
0x1400d448d  mov     ecx, 204h
0x1400d4492  call    WPP_SF_qq
0x1400d4497  mov     ebx, 0C0000022h
0x1400d449c  jmp     short loc_1400D44C5
0x1400d449e  test    byte ptr cs:xmmword_1401A2C90, 10h
0x1400d44a5  jz      short loc_1400D44C5
0x1400d44a7  mov     r9, [rbp+4Fh+P]
0x1400d44ab  lea     r8, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids
0x1400d44b2  mov     edx, 85h
0x1400d44b7  mov     dword ptr [rsp+100h+var_E0], eax
0x1400d44bb  mov     ecx, 204h
0x1400d44c0  call    WPP_SF_Sd
0x1400d44c5  xor     edx, edx
0x1400d44c7  mov     rcx, rdi
0x1400d44ca  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400d44d1  nop     dword ptr [rax+rax+00h]
0x1400d44d6  call    cs:__imp_KeLeaveCriticalRegion
0x1400d44dd  nop     dword ptr [rax+rax+00h]
0x1400d44e2  jmp     short loc_1400D4516
0x1400d44e4  test    byte ptr cs:xmmword_1401A2C90, 10h
0x1400d44eb  jz      short loc_1400D4516
0x1400d44ed  mov     edx, 84h
0x1400d44f2  jmp     short loc_1400D4502
0x1400d44f4  test    byte ptr cs:xmmword_1401A2C90, 10h
0x1400d44fb  jz      short loc_1400D4516
0x1400d44fd  mov     edx, 83h
0x1400d4502  mov     r9d, eax
0x1400d4505  lea     r8, WPP_f4d73bf616603c4c4655c8a8a3871212_Traceguids
0x1400d450c  mov     ecx, 204h
0x1400d4511  call    WPP_SF_d
0x1400d4516  mov     rcx, [rbp+4Fh+P]; P
0x1400d451a  test    rcx, rcx
0x1400d451d  jz      short loc_1400D4535
0x1400d451f  xor     edx, edx; Tag
0x1400d4521  call    cs:__imp_ExFreePoolWithTag
0x1400d4528  nop     dword ptr [rax+rax+00h]
0x1400d452d  mov     [rbp+4Fh+P], 0
0x1400d4535  mov     rdx, [rbp+4Fh+BugCheckParameter2]; BugCheckParameter2
0x1400d4539  test    rdx, rdx
0x1400d453c  jz      short loc_1400D457C
0x1400d453e  or      eax, 0FFFFFFFFh
0x1400d4541  lock xadd [rdx], eax
0x1400d4545  dec     eax
0x1400d4547  cmp     cs:UxDebugCheckRefcount, 0
0x1400d454e  jz      short loc_1400D4567
0x1400d4550  cmp     eax, 0FFFFFFFFh
0x1400d4553  jg      short loc_1400D4567
0x1400d4555  mov     ecx, 3; BugCheckParameter1
0x1400d455a  movsxd  r9, eax; BugCheckParameter4
0x1400d455d  lea     r8d, [rcx+7]; BugCheckParameter3
0x1400d4561  call    UlBugCheckEx
0x1400d4567  test    eax, eax
0x1400d4569  jnz     short loc_1400D4574
0x1400d456b  mov     rcx, [rbp+4Fh+BugCheckParameter2]; P
0x1400d456f  call    UlFreeRequestQueue
0x1400d4574  mov     [rbp+4Fh+BugCheckParameter2], 0
0x1400d457c  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400d4583  jz      short loc_1400D459A
0x1400d4585  mov     rax, [r12]
0x1400d4589  mov     r9, [r15]
0x1400d458c  mov     dword ptr [rsp+100h+var_D8], ebx
0x1400d4590  mov     [rsp+100h+var_E0], rax
0x1400d4595  call    WPP_SF_iId
0x1400d459a  lea     r11, [rsp+100h+var_20]
0x1400d45a2  mov     eax, ebx
0x1400d45a4  mov     rbx, [r11+30h]
0x1400d45a8  mov     rsi, [r11+38h]
0x1400d45ac  mov     rsp, r11
0x1400d45af  pop     r15
0x1400d45b1  pop     r14
0x1400d45b3  pop     r12
0x1400d45b5  pop     rdi
0x1400d45b6  pop     rbp
0x1400d45b7  retn
```
