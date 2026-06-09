# MountMgrUniqueIdChangeRoutine

- ea: `0x14000d494`
- end: `0x14000d794`
- name: `MountMgrUniqueIdChangeRoutine`
- size: `768`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140019f70`

## callees

- `0x140001ae0`
- `0x140002f80`
- `0x140003280`
- `0x14000a96c`
- `0x14000d494`
- `0x140010e70`
- `0x140019140`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000d566`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000d566`
- `ntoskrnl!KeReleaseMutex` at `0x14000d738`
- `ntoskrnl!KeReleaseMutex` at `0x14000d738`
- `ntoskrnl!ExAllocatePool2` at `0x14000d5d5`
- `ntoskrnl!ExAllocatePool2` at `0x14000d6a2`
- `ntoskrnl!ExAllocatePool2` at `0x14000d5d5`
- `ntoskrnl!ExAllocatePool2` at `0x14000d6a2`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000d75b`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000d75b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d771`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d771`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d522`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d522`
- `ntoskrnl!RtlCompareMemory` at `0x14000d67e`
- `ntoskrnl!RtlCompareMemory` at `0x14000d67e`

## string_xrefs

- `0x14000d553`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall MountMgrUniqueIdChangeRoutine(__int64 a1, unsigned __int16 *a2)
{
  __int64 v2; // r13
  unsigned __int16 *v5; // rbp
  __int64 v6; // r8
  unsigned int v7; // edi
  __int64 v8; // r9
  __int64 v9; // r8
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  _WORD *Pool2; // rax
  _QWORD *v13; // r14
  _QWORD *v14; // rax
  __int64 **v15; // rsi
  char v16; // r13
  __int64 *v17; // rcx
  SIZE_T v18; // rbx
  __int64 *v19; // rbx
  bool v20; // zf
  _QWORD v22[23]; // [rsp+30h] [rbp-B8h] BYREF
  char v23; // [rsp+F0h] [rbp+8h]
  int v24; // [rsp+100h] [rbp+18h]
  __int64 v25; // [rsp+108h] [rbp+20h]

  v2 = *(_QWORD *)(a1 + 152);
  v25 = v2;
  v5 = 0;
  v24 = WaitForRemoteDatabaseSemaphore(v2);
  v7 = v24;
  if ( v24 < 0 )
  {
    v23 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 75, v6, (unsigned int)v24);
  }
  else
  {
    v23 = 1;
  }
  KeWaitForSingleObject((PVOID)(v2 + 56), Executive, 0, 0, 0);
  memset(v22, 0, 0x70u);
  v8 = *(_QWORD *)(a1 + 96);
  v22[0] = ChangeUniqueIdRoutine;
  v22[3] = a2;
  RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\MountedDevices", v22, v8, 0);
  if ( v23 )
  {
    Pool2 = (_WORD *)ExAllocatePool2(258, *a2 + 2LL, 1098149453);
    if ( Pool2 )
    {
      v5 = *(unsigned __int16 **)(a1 + 96);
      *(_QWORD *)(a1 + 96) = Pool2;
      *Pool2 = *a2;
      memmove((void *)(*(_QWORD *)(a1 + 96) + 2LL), a2 + 1, *a2);
      v13 = *(_QWORD **)(v2 + 16);
      if ( v13 != (_QWORD *)(v2 + 16) )
      {
        v14 = (_QWORD *)(v2 + 16);
        do
        {
          v15 = (__int64 **)v13[4];
          if ( v15 != v13 + 4 )
          {
            v16 = 0;
            do
            {
              v17 = v15[2];
              if ( *(_WORD *)v17 == *v5 )
              {
                v18 = *v5;
                if ( RtlCompareMemory((char *)v17 + 2, v5 + 1, v18) == v18 )
                {
                  v19 = (__int64 *)ExAllocatePool2(258, *a2 + 2LL, 1098149453);
                  if ( v19 )
                  {
                    v16 = 1;
                    ExFreePoolWithTag(v15[2], 0);
                    v15[2] = v19;
                    *(_WORD *)v19 = *a2;
                    memmove((char *)v15[2] + 2, a2 + 1, *a2);
                  }
                }
              }
              v15 = (__int64 **)*v15;
            }
            while ( v15 != v13 + 4 );
            v7 = v24;
            v20 = v16 == 0;
            v2 = v25;
            if ( !v20 )
            {
              v7 = ChangeRemoteDatabaseUniqueId(v13, v5, a2);
              v24 = v7;
            }
            v14 = (_QWORD *)(v25 + 16);
          }
          v13 = (_QWORD *)*v13;
        }
        while ( v13 != v14 );
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v11 = 77;
        goto LABEL_11;
      }
    }
  }
  else
  {
    ReconcileThisDatabaseWithMaster((PVOID)v2);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v11 = 76;
LABEL_11:
      WPP_SF_L(v10->AttachedDevice, v11, v9, (unsigned int)v24);
    }
  }
  KeReleaseMutex((PRKMUTEX)(v2 + 56), 0);
  if ( v23 )
    KeReleaseSemaphore((PRKSEMAPHORE)(v2 + 112), 0, 1, 0);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  return v7;
}

```

## disassembly

```asm
0x14000d494  push    rbx
0x14000d496  push    rbp
0x14000d497  push    rsi
0x14000d498  push    rdi
0x14000d499  push    r12
0x14000d49b  push    r13
0x14000d49d  push    r14
0x14000d49f  push    r15
0x14000d4a1  sub     rsp, 0A8h
0x14000d4a8  mov     r13, [rcx+98h]
0x14000d4af  mov     rbx, rcx
0x14000d4b2  mov     rcx, r13
0x14000d4b5  mov     [rsp+0E8h+arg_18], r13
0x14000d4bd  mov     r15, rdx
0x14000d4c0  xor     ebp, ebp
0x14000d4c2  call    WaitForRemoteDatabaseSemaphore
0x14000d4c7  mov     [rsp+0E8h+arg_10], eax
0x14000d4ce  mov     edi, eax
0x14000d4d0  lea     rsi, WPP_GLOBAL_Control
0x14000d4d7  test    eax, eax
0x14000d4d9  js      short loc_14000D4E5
0x14000d4db  mov     [rsp+0E8h+arg_0], 1
0x14000d4e3  jmp     short loc_14000D511
0x14000d4e5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d4ec  mov     [rsp+0E8h+arg_0], bpl
0x14000d4f4  cmp     rcx, rsi
0x14000d4f7  jz      short loc_14000D511
0x14000d4f9  mov     eax, [rcx+2Ch]
0x14000d4fc  test    al, 1
0x14000d4fe  jz      short loc_14000D511
0x14000d500  mov     rcx, [rcx+18h]
0x14000d504  mov     edx, 4Bh ; 'K'
0x14000d509  mov     r9d, edi
0x14000d50c  call    WPP_SF_L
0x14000d511  lea     rcx, [r13+38h]; Object
0x14000d515  mov     [rsp+0E8h+Timeout], rbp; Timeout
0x14000d51a  xor     r9d, r9d; Alertable
0x14000d51d  xor     r8d, r8d; WaitMode
0x14000d520  xor     edx, edx; WaitReason
0x14000d522  call    cs:__imp_KeWaitForSingleObject
0x14000d529  nop     dword ptr [rax+rax+00h]
0x14000d52e  xor     edx, edx; Val
0x14000d530  lea     rcx, [rsp+0E8h+var_B8]; void *
0x14000d535  lea     r8d, [rdx+70h]; Size
0x14000d539  call    memset
0x14000d53e  mov     r9, [rbx+60h]
0x14000d542  lea     rax, ChangeUniqueIdRoutine
0x14000d549  lea     r8, [rsp+0E8h+var_B8]
0x14000d54e  mov     [rsp+0E8h+var_B8], rax
0x14000d553  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14000d55a  mov     [rsp+0E8h+var_A0], r15
0x14000d55f  xor     ecx, ecx
0x14000d561  mov     [rsp+0E8h+Timeout], rbp
0x14000d566  call    cs:__imp_RtlQueryRegistryValuesEx
0x14000d56d  nop     dword ptr [rax+rax+00h]
0x14000d572  cmp     [rsp+0E8h+arg_0], bpl
0x14000d57a  jnz     short loc_14000D5C2
0x14000d57c  mov     rdx, rbx
0x14000d57f  mov     rcx, r13; Context
0x14000d582  call    ReconcileThisDatabaseWithMaster
0x14000d587  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d58e  cmp     rcx, rsi
0x14000d591  jz      loc_14000D732
0x14000d597  mov     eax, [rcx+2Ch]
0x14000d59a  test    al, 1
0x14000d59c  jz      loc_14000D732
0x14000d5a2  cmp     byte ptr [rcx+29h], 2
0x14000d5a6  jb      loc_14000D732
0x14000d5ac  mov     edx, 4Ch ; 'L'
0x14000d5b1  mov     rcx, [rcx+18h]
0x14000d5b5  mov     r9d, edi
0x14000d5b8  call    WPP_SF_L
0x14000d5bd  jmp     loc_14000D732
0x14000d5c2  movzx   edx, word ptr [r15]
0x14000d5c6  mov     ecx, 102h
0x14000d5cb  add     rdx, 2
0x14000d5cf  mov     r8d, 41746E4Dh
0x14000d5d5  call    cs:__imp_ExAllocatePool2
0x14000d5dc  nop     dword ptr [rax+rax+00h]
0x14000d5e1  mov     rcx, rax
0x14000d5e4  test    rax, rax
0x14000d5e7  jnz     short loc_14000D60B
0x14000d5e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d5f0  cmp     rcx, rsi
0x14000d5f3  jz      loc_14000D732
0x14000d5f9  mov     eax, [rcx+2Ch]
0x14000d5fc  test    al, 1
0x14000d5fe  jz      loc_14000D732
0x14000d604  mov     edx, 4Dh ; 'M'
0x14000d609  jmp     short loc_14000D5B1
0x14000d60b  mov     rbp, [rbx+60h]
0x14000d60f  lea     rdx, [r15+2]; Src
0x14000d613  mov     [rbx+60h], rcx
0x14000d617  movzx   eax, word ptr [r15]
0x14000d61b  mov     [rcx], ax
0x14000d61e  mov     rcx, [rbx+60h]
0x14000d622  movzx   r8d, word ptr [r15]; Size
0x14000d626  add     rcx, 2; void *
0x14000d62a  call    memmove
0x14000d62f  lea     rsi, [r13+10h]
0x14000d633  mov     r14, [rsi]
0x14000d636  cmp     r14, rsi
0x14000d639  jz      loc_14000D732
0x14000d63f  lea     rax, [r13+10h]
0x14000d643  lea     r12, [r14+20h]
0x14000d647  mov     [rsp+0E8h+arg_8], 0
0x14000d64f  mov     rsi, [r12]
0x14000d653  cmp     rsi, r12
0x14000d656  jz      loc_14000D726
0x14000d65c  mov     r13b, [rsp+0E8h+arg_8]
0x14000d664  mov     rcx, [rsi+10h]
0x14000d668  movzx   eax, word ptr [rbp+0]
0x14000d66c  cmp     [rcx], ax
0x14000d66f  jnz     short loc_14000D6EB
0x14000d671  lea     rdx, [rbp+2]; Source2
0x14000d675  add     rcx, 2; Source1
0x14000d679  mov     r8d, eax; Length
0x14000d67c  mov     ebx, eax
0x14000d67e  call    cs:__imp_RtlCompareMemory
0x14000d685  nop     dword ptr [rax+rax+00h]
0x14000d68a  cmp     rax, rbx
0x14000d68d  jnz     short loc_14000D6EB
0x14000d68f  movzx   edx, word ptr [r15]
0x14000d693  mov     ecx, 102h
0x14000d698  add     rdx, 2
0x14000d69c  mov     r8d, 41746E4Dh
0x14000d6a2  call    cs:__imp_ExAllocatePool2
0x14000d6a9  nop     dword ptr [rax+rax+00h]
0x14000d6ae  mov     rbx, rax
0x14000d6b1  test    rax, rax
0x14000d6b4  jz      short loc_14000D6EB
0x14000d6b6  mov     rcx, [rsi+10h]; P
0x14000d6ba  xor     edx, edx; Tag
0x14000d6bc  mov     r13b, 1
0x14000d6bf  call    cs:__imp_ExFreePoolWithTag
0x14000d6c6  nop     dword ptr [rax+rax+00h]
0x14000d6cb  mov     [rsi+10h], rbx
0x14000d6cf  lea     rdx, [r15+2]; Src
0x14000d6d3  movzx   ecx, word ptr [r15]
0x14000d6d7  mov     [rbx], cx
0x14000d6da  mov     rcx, [rsi+10h]
0x14000d6de  movzx   r8d, word ptr [r15]; Size
0x14000d6e2  add     rcx, 2; void *
0x14000d6e6  call    memmove
0x14000d6eb  mov     rsi, [rsi]
0x14000d6ee  cmp     rsi, r12
0x14000d6f1  jnz     loc_14000D664
0x14000d6f7  mov     edi, [rsp+0E8h+arg_10]
0x14000d6fe  test    r13b, r13b
0x14000d701  mov     r13, [rsp+0E8h+arg_18]
0x14000d709  jz      short loc_14000D722
0x14000d70b  mov     r8, r15
0x14000d70e  mov     rdx, rbp
0x14000d711  mov     rcx, r14
0x14000d714  call    ChangeRemoteDatabaseUniqueId
0x14000d719  mov     edi, eax
0x14000d71b  mov     [rsp+0E8h+arg_10], eax
0x14000d722  lea     rax, [r13+10h]
0x14000d726  mov     r14, [r14]
0x14000d729  cmp     r14, rax
0x14000d72c  jnz     loc_14000D643
0x14000d732  xor     edx, edx; Wait
0x14000d734  lea     rcx, [r13+38h]; Mutex
0x14000d738  call    cs:__imp_KeReleaseMutex
0x14000d73f  nop     dword ptr [rax+rax+00h]
0x14000d744  cmp     [rsp+0E8h+arg_0], 0
0x14000d74c  jz      short loc_14000D767
0x14000d74e  xor     r9d, r9d; Wait
0x14000d751  lea     rcx, [r13+70h]; Semaphore
0x14000d755  xor     edx, edx; Increment
0x14000d757  lea     r8d, [r9+1]; Adjustment
0x14000d75b  call    cs:__imp_KeReleaseSemaphore
0x14000d762  nop     dword ptr [rax+rax+00h]
0x14000d767  test    rbp, rbp
0x14000d76a  jz      short loc_14000D77D
0x14000d76c  xor     edx, edx; Tag
0x14000d76e  mov     rcx, rbp; P
0x14000d771  call    cs:__imp_ExFreePoolWithTag
0x14000d778  nop     dword ptr [rax+rax+00h]
0x14000d77d  mov     eax, edi
0x14000d77f  add     rsp, 0A8h
0x14000d786  pop     r15
0x14000d788  pop     r14
0x14000d78a  pop     r13
0x14000d78c  pop     r12
0x14000d78e  pop     rdi
0x14000d78f  pop     rsi
0x14000d790  pop     rbp
0x14000d791  pop     rbx
0x14000d792  retn
```
