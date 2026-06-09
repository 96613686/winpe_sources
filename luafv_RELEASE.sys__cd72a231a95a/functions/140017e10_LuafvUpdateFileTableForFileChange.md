# LuafvUpdateFileTableForFileChange

- ea: `0x140017e10`
- end: `0x14001802a`
- name: `LuafvUpdateFileTableForFileChange`
- size: `538`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140002404`
- `0x1400175f8`
- `0x140018f20`
- `0x14001a378`
- `0x140025300`

## callees

- `0x140017e10`
- `0x14001ba60`
- `0x14001d37c`
- `0x14001d8e0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140017e9c`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017edf`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017f11`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017f54`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017fb4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140018014`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017e9c`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017edf`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017f11`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017f54`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017fb4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140018014`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017e79`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017ebc`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017eee`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017f31`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017f77`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017fd7`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017e79`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017ebc`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017eee`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017f31`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017f77`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017fd7`
- `FLTMGR!FltReleasePushLockEx` at `0x140017fa5`
- `FLTMGR!FltReleasePushLockEx` at `0x140018005`
- `FLTMGR!FltReleasePushLockEx` at `0x140017fa5`
- `FLTMGR!FltReleasePushLockEx` at `0x140018005`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140017ead`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140017f22`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140017ead`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140017f22`

## pseudocode

```c
void __fastcall LuafvUpdateFileTableForFileChange(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // rdi
  bool v8; // zf
  __int128 v9; // [rsp+20h] [rbp-58h] BYREF
  __int64 v10; // [rsp+40h] [rbp-38h]

  v10 = 0;
  v9 = 0;
  if ( a2 )
  {
    v3 = a2;
  }
  else
  {
    if ( (int)LuafvFindTableNode(0, a1, 5, &v9) < 0 )
      return;
    v3 = v9;
    if ( !(_BYTE)v10 || BYTE2(v10) )
    {
      v4 = 0;
LABEL_21:
      LuafvDereferenceTableNodeEx(v3, v4, 0);
      return;
    }
  }
  v5 = *(_QWORD *)(v3 + 32);
  ExAcquireFastMutex(&FastMutex);
  if ( *(struct _KTHREAD **)(v5 + 8) == KeGetCurrentThread() )
  {
    ++*(_DWORD *)(v5 + 16);
  }
  else
  {
    ExReleaseFastMutex(&FastMutex);
    FltAcquirePushLockExclusiveEx(v5, 0);
    ExAcquireFastMutex(&FastMutex);
    *(_QWORD *)(v5 + 8) = KeGetCurrentThread();
    *(_DWORD *)(v5 + 16) = 1;
  }
  ExReleaseFastMutex(&FastMutex);
  ExAcquireFastMutex(&FastMutex);
  if ( *(struct _KTHREAD **)(v3 + 8) == KeGetCurrentThread() )
  {
    ++*(_DWORD *)(v3 + 16);
  }
  else
  {
    ExReleaseFastMutex(&FastMutex);
    FltAcquirePushLockExclusiveEx(v3, 0);
    ExAcquireFastMutex(&FastMutex);
    *(_QWORD *)(v3 + 8) = KeGetCurrentThread();
    *(_DWORD *)(v3 + 16) = 1;
  }
  ExReleaseFastMutex(&FastMutex);
  if ( (*(_BYTE *)(v3 + 30) & 0x84) == 0 )
  {
    LOBYTE(v6) = 1;
    RemoveTableNode(v3, v6);
  }
  v7 = *(_QWORD *)(v3 + 32);
  ExAcquireFastMutex(&FastMutex);
  if ( *(struct _KTHREAD **)(v7 + 8) == KeGetCurrentThread() )
  {
    v8 = (*(_DWORD *)(v7 + 16))-- == 1;
    if ( !v8 )
      goto LABEL_19;
    *(_QWORD *)(v7 + 8) = 0;
  }
  FltReleasePushLockEx(v7, 0);
LABEL_19:
  ExReleaseFastMutex(&FastMutex);
  if ( !a2 )
  {
    LOBYTE(v4) = 1;
    goto LABEL_21;
  }
  ExAcquireFastMutex(&FastMutex);
  if ( *(struct _KTHREAD **)(v3 + 8) != KeGetCurrentThread() )
    goto LABEL_25;
  v8 = (*(_DWORD *)(v3 + 16))-- == 1;
  if ( v8 )
  {
    *(_QWORD *)(v3 + 8) = 0;
LABEL_25:
    FltReleasePushLockEx(v3, 0);
  }
  ExReleaseFastMutex(&FastMutex);
}

```

## disassembly

```asm
0x140017e10  push    rbx
0x140017e12  push    rbp
0x140017e13  push    rsi
0x140017e14  push    rdi
0x140017e15  sub     rsp, 58h
0x140017e19  xor     eax, eax
0x140017e1b  xorps   xmm0, xmm0
0x140017e1e  mov     [rsp+78h+var_38], rax
0x140017e23  mov     rsi, rdx
0x140017e26  movups  [rsp+78h+var_58], xmm0
0x140017e2b  test    rdx, rdx
0x140017e2e  jnz     short loc_140017E68
0x140017e30  lea     r8d, [rdx+5]
0x140017e34  mov     rdx, rcx
0x140017e37  xor     ecx, ecx
0x140017e39  lea     r9, [rsp+78h+var_58]
0x140017e3e  call    LuafvFindTableNode
0x140017e43  test    eax, eax
0x140017e45  js      loc_140018020
0x140017e4b  mov     rbx, qword ptr [rsp+78h+var_58]
0x140017e50  cmp     byte ptr [rsp+78h+var_38], sil
0x140017e55  jz      short loc_140017E5E
0x140017e57  cmp     byte ptr [rsp+78h+var_38+2], sil
0x140017e5c  jz      short loc_140017E6B
0x140017e5e  xor     r8d, r8d
0x140017e61  xor     edx, edx
0x140017e63  jmp     loc_140017FCA
0x140017e68  mov     rbx, rsi
0x140017e6b  mov     rdi, [rbx+20h]
0x140017e6f  lea     rbp, FastMutex
0x140017e76  mov     rcx, rbp; FastMutex
0x140017e79  call    cs:__imp_ExAcquireFastMutex
0x140017e80  nop     dword ptr [rax+rax+00h]
0x140017e85  mov     rax, gs:188h
0x140017e8e  cmp     [rdi+8], rax
0x140017e92  jnz     short loc_140017E99
0x140017e94  inc     dword ptr [rdi+10h]
0x140017e97  jmp     short loc_140017EDC
0x140017e99  mov     rcx, rbp; FastMutex
0x140017e9c  call    cs:__imp_ExReleaseFastMutex
0x140017ea3  nop     dword ptr [rax+rax+00h]
0x140017ea8  xor     edx, edx
0x140017eaa  mov     rcx, rdi
0x140017ead  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140017eb4  nop     dword ptr [rax+rax+00h]
0x140017eb9  mov     rcx, rbp; FastMutex
0x140017ebc  call    cs:__imp_ExAcquireFastMutex
0x140017ec3  nop     dword ptr [rax+rax+00h]
0x140017ec8  mov     rax, gs:188h
0x140017ed1  mov     [rdi+8], rax
0x140017ed5  mov     dword ptr [rdi+10h], 1
0x140017edc  mov     rcx, rbp; FastMutex
0x140017edf  call    cs:__imp_ExReleaseFastMutex
0x140017ee6  nop     dword ptr [rax+rax+00h]
0x140017eeb  mov     rcx, rbp; FastMutex
0x140017eee  call    cs:__imp_ExAcquireFastMutex
0x140017ef5  nop     dword ptr [rax+rax+00h]
0x140017efa  mov     rax, gs:188h
0x140017f03  cmp     [rbx+8], rax
0x140017f07  jnz     short loc_140017F0E
0x140017f09  inc     dword ptr [rbx+10h]
0x140017f0c  jmp     short loc_140017F51
0x140017f0e  mov     rcx, rbp; FastMutex
0x140017f11  call    cs:__imp_ExReleaseFastMutex
0x140017f18  nop     dword ptr [rax+rax+00h]
0x140017f1d  xor     edx, edx
0x140017f1f  mov     rcx, rbx
0x140017f22  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140017f29  nop     dword ptr [rax+rax+00h]
0x140017f2e  mov     rcx, rbp; FastMutex
0x140017f31  call    cs:__imp_ExAcquireFastMutex
0x140017f38  nop     dword ptr [rax+rax+00h]
0x140017f3d  mov     rax, gs:188h
0x140017f46  mov     [rbx+8], rax
0x140017f4a  mov     dword ptr [rbx+10h], 1
0x140017f51  mov     rcx, rbp; FastMutex
0x140017f54  call    cs:__imp_ExReleaseFastMutex
0x140017f5b  nop     dword ptr [rax+rax+00h]
0x140017f60  test    byte ptr [rbx+1Eh], 84h
0x140017f64  jnz     short loc_140017F70
0x140017f66  mov     dl, 1
0x140017f68  mov     rcx, rbx
0x140017f6b  call    RemoveTableNode
0x140017f70  mov     rdi, [rbx+20h]
0x140017f74  mov     rcx, rbp; FastMutex
0x140017f77  call    cs:__imp_ExAcquireFastMutex
0x140017f7e  nop     dword ptr [rax+rax+00h]
0x140017f83  mov     rax, gs:188h
0x140017f8c  cmp     [rdi+8], rax
0x140017f90  jnz     short loc_140017FA0
0x140017f92  sub     dword ptr [rdi+10h], 1
0x140017f96  jnz     short loc_140017FB1
0x140017f98  mov     qword ptr [rdi+8], 0
0x140017fa0  xor     edx, edx
0x140017fa2  mov     rcx, rdi
0x140017fa5  call    cs:__imp_FltReleasePushLockEx
0x140017fac  nop     dword ptr [rax+rax+00h]
0x140017fb1  mov     rcx, rbp; FastMutex
0x140017fb4  call    cs:__imp_ExReleaseFastMutex
0x140017fbb  nop     dword ptr [rax+rax+00h]
0x140017fc0  test    rsi, rsi
0x140017fc3  jnz     short loc_140017FD4
0x140017fc5  xor     r8d, r8d
0x140017fc8  mov     dl, 1
0x140017fca  mov     rcx, rbx
0x140017fcd  call    LuafvDereferenceTableNodeEx
0x140017fd2  jmp     short loc_140018020
0x140017fd4  mov     rcx, rbp; FastMutex
0x140017fd7  call    cs:__imp_ExAcquireFastMutex
0x140017fde  nop     dword ptr [rax+rax+00h]
0x140017fe3  mov     rax, gs:188h
0x140017fec  cmp     [rbx+8], rax
0x140017ff0  jnz     short loc_140018000
0x140017ff2  sub     dword ptr [rbx+10h], 1
0x140017ff6  jnz     short loc_140018011
0x140017ff8  mov     qword ptr [rbx+8], 0
0x140018000  xor     edx, edx
0x140018002  mov     rcx, rbx
0x140018005  call    cs:__imp_FltReleasePushLockEx
0x14001800c  nop     dword ptr [rax+rax+00h]
0x140018011  mov     rcx, rbp; FastMutex
0x140018014  call    cs:__imp_ExReleaseFastMutex
0x14001801b  nop     dword ptr [rax+rax+00h]
0x140018020  add     rsp, 58h
0x140018024  pop     rdi
0x140018025  pop     rsi
0x140018026  pop     rbp
0x140018027  pop     rbx
0x140018028  retn
```
