# LuafvUpdateFileTableForFileChange

- ea: `0x140017e60`
- end: `0x14001807a`
- name: `LuafvUpdateFileTableForFileChange`
- size: `538`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000217c`
- `0x140017648`
- `0x140018f70`
- `0x14001a3c8`
- `0x140025350`

## callees

- `0x140017e60`
- `0x14001bab0`
- `0x14001d3cc`
- `0x14001d930`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140017eec`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017f2f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017f61`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017fa4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140018004`
- `ntoskrnl!ExReleaseFastMutex` at `0x140018064`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017eec`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017f2f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017f61`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017fa4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140018004`
- `ntoskrnl!ExReleaseFastMutex` at `0x140018064`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017ec9`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017f0c`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017f3e`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017f81`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017fc7`
- `ntoskrnl!ExAcquireFastMutex` at `0x140018027`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017ec9`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017f0c`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017f3e`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017f81`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017fc7`
- `ntoskrnl!ExAcquireFastMutex` at `0x140018027`
- `FLTMGR!FltReleasePushLockEx` at `0x140017ff5`
- `FLTMGR!FltReleasePushLockEx` at `0x140018055`
- `FLTMGR!FltReleasePushLockEx` at `0x140017ff5`
- `FLTMGR!FltReleasePushLockEx` at `0x140018055`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140017efd`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140017f72`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140017efd`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140017f72`

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
    if ( (int)LuafvFindTableNode(0, a1, 5, (__int64)&v9) < 0 )
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
0x140017e60  push    rbx
0x140017e62  push    rbp
0x140017e63  push    rsi
0x140017e64  push    rdi
0x140017e65  sub     rsp, 58h
0x140017e69  xor     eax, eax
0x140017e6b  xorps   xmm0, xmm0
0x140017e6e  mov     [rsp+78h+var_38], rax
0x140017e73  mov     rsi, rdx
0x140017e76  movups  [rsp+78h+var_58], xmm0
0x140017e7b  test    rdx, rdx
0x140017e7e  jnz     short loc_140017EB8
0x140017e80  lea     r8d, [rdx+5]
0x140017e84  mov     rdx, rcx
0x140017e87  xor     ecx, ecx
0x140017e89  lea     r9, [rsp+78h+var_58]
0x140017e8e  call    LuafvFindTableNode
0x140017e93  test    eax, eax
0x140017e95  js      loc_140018070
0x140017e9b  mov     rbx, qword ptr [rsp+78h+var_58]
0x140017ea0  cmp     byte ptr [rsp+78h+var_38], sil
0x140017ea5  jz      short loc_140017EAE
0x140017ea7  cmp     byte ptr [rsp+78h+var_38+2], sil
0x140017eac  jz      short loc_140017EBB
0x140017eae  xor     r8d, r8d
0x140017eb1  xor     edx, edx
0x140017eb3  jmp     loc_14001801A
0x140017eb8  mov     rbx, rsi
0x140017ebb  mov     rdi, [rbx+20h]
0x140017ebf  lea     rbp, FastMutex
0x140017ec6  mov     rcx, rbp; FastMutex
0x140017ec9  call    cs:__imp_ExAcquireFastMutex
0x140017ed0  nop     dword ptr [rax+rax+00h]
0x140017ed5  mov     rax, gs:188h
0x140017ede  cmp     [rdi+8], rax
0x140017ee2  jnz     short loc_140017EE9
0x140017ee4  inc     dword ptr [rdi+10h]
0x140017ee7  jmp     short loc_140017F2C
0x140017ee9  mov     rcx, rbp; FastMutex
0x140017eec  call    cs:__imp_ExReleaseFastMutex
0x140017ef3  nop     dword ptr [rax+rax+00h]
0x140017ef8  xor     edx, edx
0x140017efa  mov     rcx, rdi
0x140017efd  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140017f04  nop     dword ptr [rax+rax+00h]
0x140017f09  mov     rcx, rbp; FastMutex
0x140017f0c  call    cs:__imp_ExAcquireFastMutex
0x140017f13  nop     dword ptr [rax+rax+00h]
0x140017f18  mov     rax, gs:188h
0x140017f21  mov     [rdi+8], rax
0x140017f25  mov     dword ptr [rdi+10h], 1
0x140017f2c  mov     rcx, rbp; FastMutex
0x140017f2f  call    cs:__imp_ExReleaseFastMutex
0x140017f36  nop     dword ptr [rax+rax+00h]
0x140017f3b  mov     rcx, rbp; FastMutex
0x140017f3e  call    cs:__imp_ExAcquireFastMutex
0x140017f45  nop     dword ptr [rax+rax+00h]
0x140017f4a  mov     rax, gs:188h
0x140017f53  cmp     [rbx+8], rax
0x140017f57  jnz     short loc_140017F5E
0x140017f59  inc     dword ptr [rbx+10h]
0x140017f5c  jmp     short loc_140017FA1
0x140017f5e  mov     rcx, rbp; FastMutex
0x140017f61  call    cs:__imp_ExReleaseFastMutex
0x140017f68  nop     dword ptr [rax+rax+00h]
0x140017f6d  xor     edx, edx
0x140017f6f  mov     rcx, rbx
0x140017f72  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140017f79  nop     dword ptr [rax+rax+00h]
0x140017f7e  mov     rcx, rbp; FastMutex
0x140017f81  call    cs:__imp_ExAcquireFastMutex
0x140017f88  nop     dword ptr [rax+rax+00h]
0x140017f8d  mov     rax, gs:188h
0x140017f96  mov     [rbx+8], rax
0x140017f9a  mov     dword ptr [rbx+10h], 1
0x140017fa1  mov     rcx, rbp; FastMutex
0x140017fa4  call    cs:__imp_ExReleaseFastMutex
0x140017fab  nop     dword ptr [rax+rax+00h]
0x140017fb0  test    byte ptr [rbx+1Eh], 84h
0x140017fb4  jnz     short loc_140017FC0
0x140017fb6  mov     dl, 1
0x140017fb8  mov     rcx, rbx
0x140017fbb  call    RemoveTableNode
0x140017fc0  mov     rdi, [rbx+20h]
0x140017fc4  mov     rcx, rbp; FastMutex
0x140017fc7  call    cs:__imp_ExAcquireFastMutex
0x140017fce  nop     dword ptr [rax+rax+00h]
0x140017fd3  mov     rax, gs:188h
0x140017fdc  cmp     [rdi+8], rax
0x140017fe0  jnz     short loc_140017FF0
0x140017fe2  sub     dword ptr [rdi+10h], 1
0x140017fe6  jnz     short loc_140018001
0x140017fe8  mov     qword ptr [rdi+8], 0
0x140017ff0  xor     edx, edx
0x140017ff2  mov     rcx, rdi
0x140017ff5  call    cs:__imp_FltReleasePushLockEx
0x140017ffc  nop     dword ptr [rax+rax+00h]
0x140018001  mov     rcx, rbp; FastMutex
0x140018004  call    cs:__imp_ExReleaseFastMutex
0x14001800b  nop     dword ptr [rax+rax+00h]
0x140018010  test    rsi, rsi
0x140018013  jnz     short loc_140018024
0x140018015  xor     r8d, r8d
0x140018018  mov     dl, 1
0x14001801a  mov     rcx, rbx
0x14001801d  call    LuafvDereferenceTableNodeEx
0x140018022  jmp     short loc_140018070
0x140018024  mov     rcx, rbp; FastMutex
0x140018027  call    cs:__imp_ExAcquireFastMutex
0x14001802e  nop     dword ptr [rax+rax+00h]
0x140018033  mov     rax, gs:188h
0x14001803c  cmp     [rbx+8], rax
0x140018040  jnz     short loc_140018050
0x140018042  sub     dword ptr [rbx+10h], 1
0x140018046  jnz     short loc_140018061
0x140018048  mov     qword ptr [rbx+8], 0
0x140018050  xor     edx, edx
0x140018052  mov     rcx, rbx
0x140018055  call    cs:__imp_FltReleasePushLockEx
0x14001805c  nop     dword ptr [rax+rax+00h]
0x140018061  mov     rcx, rbp; FastMutex
0x140018064  call    cs:__imp_ExReleaseFastMutex
0x14001806b  nop     dword ptr [rax+rax+00h]
0x140018070  add     rsp, 58h
0x140018074  pop     rdi
0x140018075  pop     rsi
0x140018076  pop     rbp
0x140018077  pop     rbx
0x140018078  retn
```
