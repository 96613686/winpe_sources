# LuafvCreateVirtualFile

- ea: `0x140022de8`
- end: `0x1400230a1`
- name: `LuafvCreateVirtualFile`
- size: `697`
- prototype: `__int64 __fastcall(__int64, struct _FLT_CALLBACK_DATA *, __int64, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140015388`
- `0x1400247e0`

## callees

- `0x140016238`
- `0x140017648`
- `0x14001860c`
- `0x14001bab0`
- `0x14001d930`
- `0x140022de8`
- `0x1400230a8`
- `0x140023d14`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140022f19`
- `ntoskrnl!ExReleaseFastMutex` at `0x140022f5c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002307a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140022f19`
- `ntoskrnl!ExReleaseFastMutex` at `0x140022f5c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002307a`
- `ntoskrnl!ExAcquireFastMutex` at `0x140022ef6`
- `ntoskrnl!ExAcquireFastMutex` at `0x140022f39`
- `ntoskrnl!ExAcquireFastMutex` at `0x140023039`
- `ntoskrnl!ExAcquireFastMutex` at `0x140022ef6`
- `ntoskrnl!ExAcquireFastMutex` at `0x140022f39`
- `ntoskrnl!ExAcquireFastMutex` at `0x140023039`
- `FLTMGR!FltReleasePushLockEx` at `0x140023067`
- `FLTMGR!FltReleasePushLockEx` at `0x140023067`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140022f2a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140022f2a`

## pseudocode

```c
__int64 __fastcall LuafvCreateVirtualFile(__int64 a1, struct _FLT_CALLBACK_DATA *a2, __int64 a3, void *a4)
{
  __m128i *v4; // rsi
  __int64 v7; // r9
  __int64 v8; // rbx
  __m128i *v9; // rdi
  __int64 result; // rax
  char v11; // r14
  char v12; // r12
  int VirtualPath; // eax
  unsigned int TableNode; // edi
  __int64 v15; // r9
  __int64 *v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  int v19; // eax
  _OWORD v21[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v22; // [rsp+50h] [rbp-10h]

  v4 = *(__m128i **)a3;
  v22 = 0;
  v7 = a1;
  v8 = v4[5].m128i_i64[0];
  v9 = v4 + 3;
  v21[0] = 0;
  if ( v8 )
  {
    v11 = 1;
    *(_QWORD *)&v21[0] = v8;
    LOBYTE(v22) = 1;
  }
  else
  {
    result = LuafvFindTableNode(0, &v4[3], 4, v21);
    if ( (int)result < 0 )
      return result;
    v11 = v22;
    v8 = *(_QWORD *)&v21[0];
    v7 = a1;
  }
  if ( v11 && (*(_BYTE *)(*(_QWORD *)(v8 + 32) + 30LL) & 1) != 0 )
    goto LABEL_15;
  v12 = 0;
  VirtualPath = LuafvCreateVirtualPath(*(PFLT_INSTANCE *)(v7 + 24), (__int64)a2, (__int64)v4);
  TableNode = VirtualPath;
  if ( VirtualPath < 0 )
  {
    v15 = (unsigned int)VirtualPath;
    v16 = LuafvCreateVirtualPathFailed;
LABEL_9:
    LuafvLogFileError(a2, v4, v16, v15);
    goto LABEL_29;
  }
  if ( v11 )
  {
LABEL_14:
    v9 = v4 + 3;
LABEL_15:
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
    v12 = 1;
    if ( (*(_BYTE *)(v8 + 30) & 1) != 0 )
    {
      TableNode = 0;
    }
    else
    {
      v19 = LuafvCopyFile(*(PFLT_INSTANCE *)(a1 + 24), a2, v4, v9, a4, (v4[2].m128i_i8[8] & 4) != 0);
      TableNode = v19;
      if ( v19 < 0 )
      {
        if ( (unsigned int)(v19 + 1073741772) > 1 && v19 != -1073741766 )
        {
          v15 = (unsigned int)v19;
          v16 = LuafvCopyFileFailed;
          goto LABEL_9;
        }
        TableNode = 0;
      }
      else
      {
        *(_BYTE *)(a3 + 52) |= 0x60u;
        if ( (dword_14000F118 & 1) != 0 )
          LuafvLogVirtualCreate(a2, a3);
      }
      *(_WORD *)(v8 + 30) |= 0x81u;
    }
    LuafvLogUtcEvent(qword_14000E280, qword_14000E290, v18, a2, v4, 1);
LABEL_29:
    if ( !v4[5].m128i_i64[0] )
    {
      LOBYTE(v17) = v12;
      LuafvDereferenceTableNodeEx(v8, v17, 0);
      return TableNode;
    }
    if ( !v12 )
      return TableNode;
    ExAcquireFastMutex(&FastMutex);
    if ( *(struct _KTHREAD **)(v8 + 8) == KeGetCurrentThread() )
    {
      if ( (*(_DWORD *)(v8 + 16))-- != 1 )
      {
LABEL_36:
        ExReleaseFastMutex(&FastMutex);
        return TableNode;
      }
      *(_QWORD *)(v8 + 8) = 0;
    }
    FltReleasePushLockEx(v8, 0);
    goto LABEL_36;
  }
  TableNode = LuafvFindTableNode(0, &v4[3], 12, v21);
  LuafvDereferenceTableNodeEx(v8, 0, 0);
  if ( (TableNode & 0x80000000) == 0 )
  {
    v8 = *(_QWORD *)&v21[0];
    if ( !(_BYTE)v22 )
    {
      TableNode = -1073741766;
      goto LABEL_29;
    }
    goto LABEL_14;
  }
  return TableNode;
}

```

## disassembly

```asm
0x140022de8  mov     [rsp-38h+arg_8], rbx
0x140022ded  mov     [rsp-38h+arg_18], r9
0x140022df2  mov     [rsp-38h+arg_0], rcx
0x140022df7  push    rbp
0x140022df8  push    rsi
0x140022df9  push    rdi
0x140022dfa  push    r12
0x140022dfc  push    r13
0x140022dfe  push    r14
0x140022e00  push    r15
0x140022e02  mov     rbp, rsp
0x140022e05  sub     rsp, 60h
0x140022e09  mov     rsi, [r8]
0x140022e0c  xor     eax, eax
0x140022e0e  xorps   xmm0, xmm0
0x140022e11  mov     [rbp+var_10], rax
0x140022e15  mov     r13, r8
0x140022e18  mov     r15, rdx
0x140022e1b  mov     r9, rcx
0x140022e1e  mov     rbx, [rsi+50h]
0x140022e22  lea     rdi, [rsi+30h]
0x140022e26  movups  [rbp+var_30], xmm0
0x140022e2a  test    rbx, rbx
0x140022e2d  jnz     short loc_140022E57
0x140022e2f  lea     r9, [rbp+var_30]
0x140022e33  mov     rdx, rdi
0x140022e36  lea     r8d, [rax+4]
0x140022e3a  xor     ecx, ecx
0x140022e3c  call    LuafvFindTableNode
0x140022e41  test    eax, eax
0x140022e43  js      loc_140023088
0x140022e49  mov     r14b, byte ptr [rbp+var_10]
0x140022e4d  mov     rbx, qword ptr [rbp+var_30]
0x140022e51  mov     r9, [rbp+arg_0]
0x140022e55  jmp     short loc_140022E62
0x140022e57  mov     r14b, 1
0x140022e5a  mov     qword ptr [rbp+var_30], rbx
0x140022e5e  mov     byte ptr [rbp+var_10], r14b
0x140022e62  test    r14b, r14b
0x140022e65  jz      short loc_140022E71
0x140022e67  mov     rax, [rbx+20h]
0x140022e6b  test    byte ptr [rax+1Eh], 1
0x140022e6f  jnz     short loc_140022EEC
0x140022e71  mov     rcx, [r9+18h]; Instance
0x140022e75  mov     r8, rsi
0x140022e78  mov     rdx, r15
0x140022e7b  xor     r12b, r12b
0x140022e7e  call    LuafvCreateVirtualPath
0x140022e83  mov     edi, eax
0x140022e85  test    eax, eax
0x140022e87  jns     short loc_140022EA3
0x140022e89  mov     r9d, eax
0x140022e8c  lea     r8, LuafvCreateVirtualPathFailed
0x140022e93  mov     rdx, rsi
0x140022e96  mov     rcx, r15
0x140022e99  call    LuafvLogFileError
0x140022e9e  jmp     loc_140023016
0x140022ea3  test    r14b, r14b
0x140022ea6  jnz     short loc_140022EE8
0x140022ea8  lea     r9, [rbp+var_30]
0x140022eac  mov     r8d, 0Ch
0x140022eb2  lea     rdx, [rsi+30h]
0x140022eb6  xor     ecx, ecx
0x140022eb8  call    LuafvFindTableNode
0x140022ebd  xor     r8d, r8d
0x140022ec0  xor     edx, edx
0x140022ec2  mov     rcx, rbx
0x140022ec5  mov     edi, eax
0x140022ec7  call    LuafvDereferenceTableNodeEx
0x140022ecc  test    edi, edi
0x140022ece  js      loc_140023086
0x140022ed4  mov     rbx, qword ptr [rbp+var_30]
0x140022ed8  cmp     byte ptr [rbp+var_10], r12b
0x140022edc  jnz     short loc_140022EE8
0x140022ede  mov     edi, 0C000003Ah
0x140022ee3  jmp     loc_140023016
0x140022ee8  lea     rdi, [rsi+30h]
0x140022eec  lea     r14, FastMutex
0x140022ef3  mov     rcx, r14; FastMutex
0x140022ef6  call    cs:__imp_ExAcquireFastMutex
0x140022efd  nop     dword ptr [rax+rax+00h]
0x140022f02  mov     rax, gs:188h
0x140022f0b  cmp     [rbx+8], rax
0x140022f0f  jnz     short loc_140022F16
0x140022f11  inc     dword ptr [rbx+10h]
0x140022f14  jmp     short loc_140022F59
0x140022f16  mov     rcx, r14; FastMutex
0x140022f19  call    cs:__imp_ExReleaseFastMutex
0x140022f20  nop     dword ptr [rax+rax+00h]
0x140022f25  xor     edx, edx
0x140022f27  mov     rcx, rbx
0x140022f2a  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140022f31  nop     dword ptr [rax+rax+00h]
0x140022f36  mov     rcx, r14; FastMutex
0x140022f39  call    cs:__imp_ExAcquireFastMutex
0x140022f40  nop     dword ptr [rax+rax+00h]
0x140022f45  mov     rax, gs:188h
0x140022f4e  mov     [rbx+8], rax
0x140022f52  mov     dword ptr [rbx+10h], 1
0x140022f59  mov     rcx, r14; FastMutex
0x140022f5c  call    cs:__imp_ExReleaseFastMutex
0x140022f63  nop     dword ptr [rax+rax+00h]
0x140022f68  mov     r14d, 1
0x140022f6e  mov     r12b, 1
0x140022f71  test    [rbx+1Eh], r14b
0x140022f75  jz      short loc_140022F7B
0x140022f77  xor     edi, edi
0x140022f79  jmp     short loc_140022FF6
0x140022f7b  mov     al, [rsi+28h]
0x140022f7e  mov     r9, rdi
0x140022f81  mov     rcx, [rbp+arg_0]
0x140022f85  mov     r8, rsi
0x140022f88  shr     al, 2
0x140022f8b  mov     rdx, r15
0x140022f8e  and     al, r14b
0x140022f91  mov     [rsp+60h+var_38], al; char
0x140022f95  mov     rax, [rbp+arg_18]
0x140022f99  mov     rcx, [rcx+18h]; Instance
0x140022f9d  mov     [rsp+60h+var_40], rax; __int64
0x140022fa2  call    LuafvCopyFile
0x140022fa7  mov     edi, eax
0x140022fa9  test    eax, eax
0x140022fab  js      short loc_140022FCA
0x140022fad  or      byte ptr [r13+34h], 60h
0x140022fb2  mov     eax, cs:dword_14000F118
0x140022fb8  test    r14b, al
0x140022fbb  jz      short loc_140022FED
0x140022fbd  mov     rdx, r13
0x140022fc0  mov     rcx, r15
0x140022fc3  call    LuafvLogVirtualCreate
0x140022fc8  jmp     short loc_140022FED
0x140022fca  add     eax, 3FFFFFCCh
0x140022fcf  cmp     eax, r14d
0x140022fd2  jbe     short loc_140022FEB
0x140022fd4  cmp     edi, 0C000003Ah
0x140022fda  jz      short loc_140022FEB
0x140022fdc  mov     r9d, edi
0x140022fdf  lea     r8, LuafvCopyFileFailed
0x140022fe6  jmp     loc_140022E93
0x140022feb  xor     edi, edi
0x140022fed  mov     eax, 81h
0x140022ff2  or      [rbx+1Eh], ax
0x140022ff6  mov     dword ptr [rsp+60h+var_38], r14d
0x140022ffb  lea     rdx, qword_14000E290
0x140023002  mov     r9, r15
0x140023005  mov     [rsp+60h+var_40], rsi
0x14002300a  lea     rcx, qword_14000E280
0x140023011  call    LuafvLogUtcEvent
0x140023016  cmp     qword ptr [rsi+50h], 0
0x14002301b  jnz     short loc_14002302D
0x14002301d  xor     r8d, r8d
0x140023020  mov     dl, r12b
0x140023023  mov     rcx, rbx
0x140023026  call    LuafvDereferenceTableNodeEx
0x14002302b  jmp     short loc_140023086
0x14002302d  test    r12b, r12b
0x140023030  jz      short loc_140023086
0x140023032  lea     rcx, FastMutex; FastMutex
0x140023039  call    cs:__imp_ExAcquireFastMutex
0x140023040  nop     dword ptr [rax+rax+00h]
0x140023045  mov     rax, gs:188h
0x14002304e  cmp     [rbx+8], rax
0x140023052  jnz     short loc_140023062
0x140023054  sub     dword ptr [rbx+10h], 1
0x140023058  jnz     short loc_140023073
0x14002305a  mov     qword ptr [rbx+8], 0
0x140023062  xor     edx, edx
0x140023064  mov     rcx, rbx
0x140023067  call    cs:__imp_FltReleasePushLockEx
0x14002306e  nop     dword ptr [rax+rax+00h]
0x140023073  lea     rcx, FastMutex; FastMutex
0x14002307a  call    cs:__imp_ExReleaseFastMutex
0x140023081  nop     dword ptr [rax+rax+00h]
0x140023086  mov     eax, edi
0x140023088  mov     rbx, [rsp+60h+arg_8]
0x140023090  add     rsp, 60h
0x140023094  pop     r15
0x140023096  pop     r14
0x140023098  pop     r13
0x14002309a  pop     r12
0x14002309c  pop     rdi
0x14002309d  pop     rsi
0x14002309e  pop     rbp
0x14002309f  retn
```
