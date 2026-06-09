# LuafvCreateVirtualFile

- ea: `0x140022d98`
- end: `0x140023051`
- name: `LuafvCreateVirtualFile`
- size: `697`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140015388`
- `0x140024790`

## callees

- `0x140016238`
- `0x1400175f8`
- `0x1400185bc`
- `0x14001ba60`
- `0x14001d8e0`
- `0x140022d98`
- `0x140023058`
- `0x140023cc4`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140022ec9`
- `ntoskrnl!ExReleaseFastMutex` at `0x140022f0c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002302a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140022ec9`
- `ntoskrnl!ExReleaseFastMutex` at `0x140022f0c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002302a`
- `ntoskrnl!ExAcquireFastMutex` at `0x140022ea6`
- `ntoskrnl!ExAcquireFastMutex` at `0x140022ee9`
- `ntoskrnl!ExAcquireFastMutex` at `0x140022fe9`
- `ntoskrnl!ExAcquireFastMutex` at `0x140022ea6`
- `ntoskrnl!ExAcquireFastMutex` at `0x140022ee9`
- `ntoskrnl!ExAcquireFastMutex` at `0x140022fe9`
- `FLTMGR!FltReleasePushLockEx` at `0x140023017`
- `FLTMGR!FltReleasePushLockEx` at `0x140023017`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140022eda`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140022eda`

## pseudocode

```c
__int64 __fastcall LuafvCreateVirtualFile(__int64 a1, __int64 a2, __int64 *a3, __int64 a4)
{
  __int64 v4; // rsi
  __int64 v7; // r9
  __int64 v8; // rbx
  __int64 result; // rax
  char v10; // r14
  char v11; // r12
  int VirtualPath; // eax
  unsigned int TableNode; // edi
  __int64 v14; // r9
  __int64 *v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // eax
  _OWORD v20[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h]

  v4 = *a3;
  v21 = 0;
  v7 = a1;
  v8 = *(_QWORD *)(v4 + 80);
  v20[0] = 0;
  if ( v8 )
  {
    v10 = 1;
    *(_QWORD *)&v20[0] = v8;
    LOBYTE(v21) = 1;
  }
  else
  {
    result = LuafvFindTableNode(0, v4 + 48, 4, v20);
    if ( (int)result < 0 )
      return result;
    v10 = v21;
    v8 = *(_QWORD *)&v20[0];
    v7 = a1;
  }
  if ( v10 && (*(_BYTE *)(*(_QWORD *)(v8 + 32) + 30LL) & 1) != 0 )
    goto LABEL_14;
  v11 = 0;
  VirtualPath = LuafvCreateVirtualPath(*(PFLT_INSTANCE *)(v7 + 24));
  TableNode = VirtualPath;
  if ( VirtualPath < 0 )
  {
    v14 = (unsigned int)VirtualPath;
    v15 = LuafvCreateVirtualPathFailed;
LABEL_9:
    LuafvLogFileError(a2, v4, v15, v14);
    goto LABEL_28;
  }
  if ( v10 )
    goto LABEL_14;
  TableNode = LuafvFindTableNode(0, v4 + 48, 12, v20);
  LuafvDereferenceTableNodeEx(v8, 0, 0);
  if ( (TableNode & 0x80000000) == 0 )
  {
    v8 = *(_QWORD *)&v20[0];
    if ( !(_BYTE)v21 )
    {
      TableNode = -1073741766;
      goto LABEL_28;
    }
LABEL_14:
    ExAcquireFastMutex(&FastMutex);
    if ( *(struct _KTHREAD **)(v8 + 8) == KeGetCurrentThread() )
    {
      ++*(_DWORD *)(v8 + 16);
    }
    else
    {
      ExReleaseFastMutex(&FastMutex);
      FltAcquirePushLockExclusiveEx(v8, 0);
      ExAcquireFastMutex(&FastMutex);
      *(_QWORD *)(v8 + 8) = KeGetCurrentThread();
      *(_DWORD *)(v8 + 16) = 1;
    }
    ExReleaseFastMutex(&FastMutex);
    v11 = 1;
    if ( (*(_BYTE *)(v8 + 30) & 1) != 0 )
    {
      TableNode = 0;
    }
    else
    {
      v18 = LuafvCopyFile(*(PFLT_INSTANCE *)(a1 + 24), a4, (*(_BYTE *)(v4 + 40) & 4) != 0);
      TableNode = v18;
      if ( v18 < 0 )
      {
        if ( (unsigned int)(v18 + 1073741772) > 1 && v18 != -1073741766 )
        {
          v14 = (unsigned int)v18;
          v15 = LuafvCopyFileFailed;
          goto LABEL_9;
        }
        TableNode = 0;
      }
      else
      {
        *((_BYTE *)a3 + 52) |= 0x60u;
        if ( (dword_14000EAD8 & 1) != 0 )
          LuafvLogVirtualCreate(a2, a3);
      }
      *(_WORD *)(v8 + 30) |= 0x81u;
    }
    LuafvLogUtcEvent(qword_14000E280, qword_14000E290, v17, a2, v4, 1);
LABEL_28:
    if ( !*(_QWORD *)(v4 + 80) )
    {
      LOBYTE(v16) = v11;
      LuafvDereferenceTableNodeEx(v8, v16, 0);
      return TableNode;
    }
    if ( !v11 )
      return TableNode;
    ExAcquireFastMutex(&FastMutex);
    if ( *(struct _KTHREAD **)(v8 + 8) == KeGetCurrentThread() )
    {
      if ( (*(_DWORD *)(v8 + 16))-- != 1 )
      {
LABEL_35:
        ExReleaseFastMutex(&FastMutex);
        return TableNode;
      }
      *(_QWORD *)(v8 + 8) = 0;
    }
    FltReleasePushLockEx(v8, 0);
    goto LABEL_35;
  }
  return TableNode;
}

```

## disassembly

```asm
0x140022d98  mov     [rsp-38h+arg_8], rbx
0x140022d9d  mov     [rsp-38h+arg_18], r9
0x140022da2  mov     [rsp-38h+arg_0], rcx
0x140022da7  push    rbp
0x140022da8  push    rsi
0x140022da9  push    rdi
0x140022daa  push    r12
0x140022dac  push    r13
0x140022dae  push    r14
0x140022db0  push    r15
0x140022db2  mov     rbp, rsp
0x140022db5  sub     rsp, 60h
0x140022db9  mov     rsi, [r8]
0x140022dbc  xor     eax, eax
0x140022dbe  xorps   xmm0, xmm0
0x140022dc1  mov     [rbp+var_10], rax
0x140022dc5  mov     r13, r8
0x140022dc8  mov     r15, rdx
0x140022dcb  mov     r9, rcx
0x140022dce  mov     rbx, [rsi+50h]
0x140022dd2  lea     rdi, [rsi+30h]
0x140022dd6  movups  [rbp+var_30], xmm0
0x140022dda  test    rbx, rbx
0x140022ddd  jnz     short loc_140022E07
0x140022ddf  lea     r9, [rbp+var_30]
0x140022de3  mov     rdx, rdi
0x140022de6  lea     r8d, [rax+4]
0x140022dea  xor     ecx, ecx
0x140022dec  call    LuafvFindTableNode
0x140022df1  test    eax, eax
0x140022df3  js      loc_140023038
0x140022df9  mov     r14b, byte ptr [rbp+var_10]
0x140022dfd  mov     rbx, qword ptr [rbp+var_30]
0x140022e01  mov     r9, [rbp+arg_0]
0x140022e05  jmp     short loc_140022E12
0x140022e07  mov     r14b, 1
0x140022e0a  mov     qword ptr [rbp+var_30], rbx
0x140022e0e  mov     byte ptr [rbp+var_10], r14b
0x140022e12  test    r14b, r14b
0x140022e15  jz      short loc_140022E21
0x140022e17  mov     rax, [rbx+20h]
0x140022e1b  test    byte ptr [rax+1Eh], 1
0x140022e1f  jnz     short loc_140022E9C
0x140022e21  mov     rcx, [r9+18h]; Instance
0x140022e25  mov     r8, rsi
0x140022e28  mov     rdx, r15
0x140022e2b  xor     r12b, r12b
0x140022e2e  call    LuafvCreateVirtualPath
0x140022e33  mov     edi, eax
0x140022e35  test    eax, eax
0x140022e37  jns     short loc_140022E53
0x140022e39  mov     r9d, eax
0x140022e3c  lea     r8, LuafvCreateVirtualPathFailed
0x140022e43  mov     rdx, rsi
0x140022e46  mov     rcx, r15
0x140022e49  call    LuafvLogFileError
0x140022e4e  jmp     loc_140022FC6
0x140022e53  test    r14b, r14b
0x140022e56  jnz     short loc_140022E98
0x140022e58  lea     r9, [rbp+var_30]
0x140022e5c  mov     r8d, 0Ch
0x140022e62  lea     rdx, [rsi+30h]
0x140022e66  xor     ecx, ecx
0x140022e68  call    LuafvFindTableNode
0x140022e6d  xor     r8d, r8d
0x140022e70  xor     edx, edx
0x140022e72  mov     rcx, rbx
0x140022e75  mov     edi, eax
0x140022e77  call    LuafvDereferenceTableNodeEx
0x140022e7c  test    edi, edi
0x140022e7e  js      loc_140023036
0x140022e84  mov     rbx, qword ptr [rbp+var_30]
0x140022e88  cmp     byte ptr [rbp+var_10], r12b
0x140022e8c  jnz     short loc_140022E98
0x140022e8e  mov     edi, 0C000003Ah
0x140022e93  jmp     loc_140022FC6
0x140022e98  lea     rdi, [rsi+30h]
0x140022e9c  lea     r14, FastMutex
0x140022ea3  mov     rcx, r14; FastMutex
0x140022ea6  call    cs:__imp_ExAcquireFastMutex
0x140022ead  nop     dword ptr [rax+rax+00h]
0x140022eb2  mov     rax, gs:188h
0x140022ebb  cmp     [rbx+8], rax
0x140022ebf  jnz     short loc_140022EC6
0x140022ec1  inc     dword ptr [rbx+10h]
0x140022ec4  jmp     short loc_140022F09
0x140022ec6  mov     rcx, r14; FastMutex
0x140022ec9  call    cs:__imp_ExReleaseFastMutex
0x140022ed0  nop     dword ptr [rax+rax+00h]
0x140022ed5  xor     edx, edx
0x140022ed7  mov     rcx, rbx
0x140022eda  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140022ee1  nop     dword ptr [rax+rax+00h]
0x140022ee6  mov     rcx, r14; FastMutex
0x140022ee9  call    cs:__imp_ExAcquireFastMutex
0x140022ef0  nop     dword ptr [rax+rax+00h]
0x140022ef5  mov     rax, gs:188h
0x140022efe  mov     [rbx+8], rax
0x140022f02  mov     dword ptr [rbx+10h], 1
0x140022f09  mov     rcx, r14; FastMutex
0x140022f0c  call    cs:__imp_ExReleaseFastMutex
0x140022f13  nop     dword ptr [rax+rax+00h]
0x140022f18  mov     r14d, 1
0x140022f1e  mov     r12b, 1
0x140022f21  test    [rbx+1Eh], r14b
0x140022f25  jz      short loc_140022F2B
0x140022f27  xor     edi, edi
0x140022f29  jmp     short loc_140022FA6
0x140022f2b  mov     al, [rsi+28h]
0x140022f2e  mov     r9, rdi
0x140022f31  mov     rcx, [rbp+arg_0]
0x140022f35  mov     r8, rsi
0x140022f38  shr     al, 2
0x140022f3b  mov     rdx, r15
0x140022f3e  and     al, r14b
0x140022f41  mov     [rsp+60h+var_38], al; char
0x140022f45  mov     rax, [rbp+arg_18]
0x140022f49  mov     rcx, [rcx+18h]; Instance
0x140022f4d  mov     [rsp+60h+var_40], rax; __int64
0x140022f52  call    LuafvCopyFile
0x140022f57  mov     edi, eax
0x140022f59  test    eax, eax
0x140022f5b  js      short loc_140022F7A
0x140022f5d  or      byte ptr [r13+34h], 60h
0x140022f62  mov     eax, cs:dword_14000EAD8
0x140022f68  test    r14b, al
0x140022f6b  jz      short loc_140022F9D
0x140022f6d  mov     rdx, r13
0x140022f70  mov     rcx, r15
0x140022f73  call    LuafvLogVirtualCreate
0x140022f78  jmp     short loc_140022F9D
0x140022f7a  add     eax, 3FFFFFCCh
0x140022f7f  cmp     eax, r14d
0x140022f82  jbe     short loc_140022F9B
0x140022f84  cmp     edi, 0C000003Ah
0x140022f8a  jz      short loc_140022F9B
0x140022f8c  mov     r9d, edi
0x140022f8f  lea     r8, LuafvCopyFileFailed
0x140022f96  jmp     loc_140022E43
0x140022f9b  xor     edi, edi
0x140022f9d  mov     eax, 81h
0x140022fa2  or      [rbx+1Eh], ax
0x140022fa6  mov     dword ptr [rsp+60h+var_38], r14d
0x140022fab  lea     rdx, qword_14000E290
0x140022fb2  mov     r9, r15
0x140022fb5  mov     [rsp+60h+var_40], rsi
0x140022fba  lea     rcx, qword_14000E280
0x140022fc1  call    LuafvLogUtcEvent
0x140022fc6  cmp     qword ptr [rsi+50h], 0
0x140022fcb  jnz     short loc_140022FDD
0x140022fcd  xor     r8d, r8d
0x140022fd0  mov     dl, r12b
0x140022fd3  mov     rcx, rbx
0x140022fd6  call    LuafvDereferenceTableNodeEx
0x140022fdb  jmp     short loc_140023036
0x140022fdd  test    r12b, r12b
0x140022fe0  jz      short loc_140023036
0x140022fe2  lea     rcx, FastMutex; FastMutex
0x140022fe9  call    cs:__imp_ExAcquireFastMutex
0x140022ff0  nop     dword ptr [rax+rax+00h]
0x140022ff5  mov     rax, gs:188h
0x140022ffe  cmp     [rbx+8], rax
0x140023002  jnz     short loc_140023012
0x140023004  sub     dword ptr [rbx+10h], 1
0x140023008  jnz     short loc_140023023
0x14002300a  mov     qword ptr [rbx+8], 0
0x140023012  xor     edx, edx
0x140023014  mov     rcx, rbx
0x140023017  call    cs:__imp_FltReleasePushLockEx
0x14002301e  nop     dword ptr [rax+rax+00h]
0x140023023  lea     rcx, FastMutex; FastMutex
0x14002302a  call    cs:__imp_ExReleaseFastMutex
0x140023031  nop     dword ptr [rax+rax+00h]
0x140023036  mov     eax, edi
0x140023038  mov     rbx, [rsp+60h+arg_8]
0x140023040  add     rsp, 60h
0x140023044  pop     r15
0x140023046  pop     r14
0x140023048  pop     r13
0x14002304a  pop     r12
0x14002304c  pop     rdi
0x14002304d  pop     rsi
0x14002304e  pop     rbp
0x14002304f  retn
```
