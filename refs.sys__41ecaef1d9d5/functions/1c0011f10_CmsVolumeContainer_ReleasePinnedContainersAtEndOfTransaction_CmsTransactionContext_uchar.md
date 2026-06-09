# CmsVolumeContainer::ReleasePinnedContainersAtEndOfTransaction(CmsTransactionContext *,uchar)

- ea: `0x1c0011f10`
- end: `0x1c0012008`
- name: `?ReleasePinnedContainersAtEndOfTransaction@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@E@Z`
- size: `248`
- prototype: `void __fastcall(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1c0011b90`
- `0x1c00224d0`

## callees

- `0x1c0011f10`
- `0x1c00da3ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1c0073f23`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0074029`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0073f23`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0074029`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0011faa`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0073ed4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0073f5b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0011faa`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0073ed4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0073f5b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0011fda`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0073efb`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0073f99`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0074001`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0011fda`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0073efb`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0073f99`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0074001`

## pseudocode

```c
void __fastcall CmsVolumeContainer::ReleasePinnedContainersAtEndOfTransaction(
        CmsVolumeContainer *this,
        struct CmsTransactionContext *a2,
        char a3)
{
  struct SmsContainer **v4; // r15
  _DWORD *v6; // rdi
  char *v7; // rbx
  char v9; // r14
  __int64 v10; // rsi
  _QWORD *v11; // rbx
  _DWORD *v12; // r12
  __int64 v13; // r13
  CmsVolumeContainer *v14; // rdi
  char v15; // al
  __int64 v16; // rcx
  _QWORD *v17; // rax
  char v18; // al
  __int64 v19; // rcx
  _QWORD *i; // rbx
  struct SmsContainer *v21; // r8
  _QWORD *v22; // rax

  v4 = (struct SmsContainer **)((char *)a2 + 2776);
  v6 = (_DWORD *)((char *)a2 + 2808);
  v7 = (char *)a2 + 2776;
  v9 = 0;
  v10 = 4;
  do
  {
    if ( *(_QWORD *)v7 )
    {
      ExReleasePushLockEx(*(_QWORD *)v7 + 104LL, 2);
      --*((_DWORD *)a2 + 707);
      if ( a3
        && (v15 = *(_BYTE *)(*(_QWORD *)v7 + 24LL), (v15 & 0x40) != 0)
        && v15 < 0
        && (*(_BYTE *)(*(_QWORD *)v7 + 25LL) & 1) != 0 )
      {
        v9 = 1;
      }
      else
      {
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v7 + 88LL));
        IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)this + 328), 0, 0x20u);
        --*((_DWORD *)a2 + 706);
        *(_QWORD *)v7 = 0;
        *v6 = 0;
      }
    }
    v7 += 8;
    ++v6;
    --v10;
  }
  while ( v10 );
  v11 = (_QWORD *)*((_QWORD *)a2 + 328);
  v12 = (_DWORD *)((char *)a2 + 2808);
  v13 = 4;
  if ( v11 )
  {
    v14 = this;
    do
    {
      v16 = v11[1];
      v17 = v11;
      if ( v16 )
      {
        if ( a3 )
        {
          v18 = *(_BYTE *)(v16 + 24);
          if ( (v18 & 0x40) != 0 && v18 < 0 && (*(_BYTE *)(v16 + 25) & 1) != 0 )
            goto LABEL_23;
        }
        ExReleasePushLockEx(v16 + 104, 2);
        --*((_DWORD *)a2 + 707);
        _InterlockedDecrement((volatile signed __int32 *)(v11[1] + 88LL));
        IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)this + 328), 0, 0x20u);
        --*((_DWORD *)a2 + 706);
        v17 = (_QWORD *)*((_QWORD *)a2 + 328);
      }
      *((_QWORD *)a2 + 328) = *v17;
      ExFreePoolWithTag(v11, 0);
      v11 = (_QWORD *)*((_QWORD *)a2 + 328);
    }
    while ( v11 );
  }
  if ( v9 )
  {
    v14 = this;
LABEL_23:
    while ( v11 )
    {
      v19 = v11[1];
      if ( v19 )
      {
        ExReleasePushLockEx(v19 + 104, 2);
        --*((_DWORD *)a2 + 707);
      }
      v11 = (_QWORD *)*v11;
    }
    do
    {
      if ( *v4 )
      {
        CmsVolumeContainer::RequeryWH(v14, a2, *v4);
        _InterlockedDecrement((volatile signed __int32 *)*v4 + 22);
        IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)v14 + 328), 0, 0x20u);
        --*((_DWORD *)a2 + 706);
        *v4 = 0;
        *v12 = 0;
      }
      ++v4;
      ++v12;
      --v13;
    }
    while ( v13 );
    for ( i = (_QWORD *)*((_QWORD *)a2 + 328); i; i = (_QWORD *)*((_QWORD *)a2 + 328) )
    {
      v21 = (struct SmsContainer *)i[1];
      v22 = i;
      if ( v21 )
      {
        CmsVolumeContainer::RequeryWH(v14, a2, v21);
        _InterlockedDecrement((volatile signed __int32 *)(i[1] + 88LL));
        IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)v14 + 328), 0, 0x20u);
        --*((_DWORD *)a2 + 706);
        v22 = (_QWORD *)*((_QWORD *)a2 + 328);
      }
      *((_QWORD *)a2 + 328) = *v22;
      ExFreePoolWithTag(i, 0);
    }
  }
}

```

## disassembly

```asm
0x1c0011f10  mov     [rsp+arg_8], rbx
0x1c0011f15  mov     [rsp+arg_10], r8b
0x1c0011f1a  mov     [rsp+arg_0], rcx
0x1c0011f1f  push    rbp
0x1c0011f20  push    rsi
0x1c0011f21  push    rdi
0x1c0011f22  push    r12
0x1c0011f24  push    r13
0x1c0011f26  push    r14
0x1c0011f28  push    r15
0x1c0011f2a  sub     rsp, 20h
0x1c0011f2e  movzx   r13d, [rsp+58h+arg_10]
0x1c0011f34  lea     r15, [rdx+0AD8h]
0x1c0011f3b  mov     r12, [rsp+58h+arg_0]
0x1c0011f40  lea     rdi, [rdx+0AF8h]
0x1c0011f47  mov     rbx, r15
0x1c0011f4a  mov     rbp, rdx
0x1c0011f4d  xor     r14b, r14b
0x1c0011f50  mov     esi, 4
0x1c0011f55  mov     rcx, [rbx]
0x1c0011f58  test    rcx, rcx
0x1c0011f5b  jnz     short loc_1C0011FA1
0x1c0011f5d  add     rbx, 8
0x1c0011f61  add     rdi, 4
0x1c0011f65  sub     rsi, 1
0x1c0011f69  jnz     short loc_1C0011F55
0x1c0011f6b  mov     rbx, [rbp+0A40h]
0x1c0011f72  lea     r12, [rbp+0AF8h]
0x1c0011f79  lea     r13d, [rsi+4]
0x1c0011f7d  test    rbx, rbx
0x1c0011f80  jnz     loc_1C0073EA1
0x1c0011f86  test    r14b, r14b
0x1c0011f89  jnz     short loc_1C0011FFE
0x1c0011f8b  mov     rbx, [rsp+58h+arg_8]
0x1c0011f90  add     rsp, 20h
0x1c0011f94  pop     r15
0x1c0011f96  pop     r14
0x1c0011f98  pop     r13
0x1c0011f9a  pop     r12
0x1c0011f9c  pop     rdi
0x1c0011f9d  pop     rsi
0x1c0011f9e  pop     rbp
0x1c0011f9f  retn
0x1c0011fa1  add     rcx, 68h ; 'h'
0x1c0011fa5  mov     edx, 2
0x1c0011faa  call    cs:__imp_ExReleasePushLockEx
0x1c0011fb1  nop     dword ptr [rax+rax+00h]
0x1c0011fb6  dec     dword ptr [rbp+0B0Ch]
0x1c0011fbc  test    r13b, r13b
0x1c0011fbf  jnz     loc_1C0073E78
0x1c0011fc5  mov     rax, [rbx]
0x1c0011fc8  lea     rcx, [r12+148h]; RemoveLock
0x1c0011fd0  xor     edx, edx; Tag
0x1c0011fd2  lock dec dword ptr [rax+58h]
0x1c0011fd6  lea     r8d, [rdx+20h]; RemlockSize
0x1c0011fda  call    cs:__imp_IoReleaseRemoveLockEx
0x1c0011fe1  nop     dword ptr [rax+rax+00h]
0x1c0011fe6  dec     dword ptr [rbp+0B08h]
0x1c0011fec  mov     qword ptr [rbx], 0
0x1c0011ff3  mov     dword ptr [rdi], 0
0x1c0011ff9  jmp     loc_1C0011F5D
0x1c0011ffe  mov     rdi, [rsp+58h+arg_0]
0x1c0012003  jmp     loc_1C0073F44
0x1c0073e78  mov     rcx, [rbx]
0x1c0073e7b  movzx   eax, byte ptr [rcx+18h]
0x1c0073e7f  test    al, 40h
0x1c0073e81  jz      loc_1C0011FC5
0x1c0073e87  test    al, al
0x1c0073e89  jns     loc_1C0011FC5
0x1c0073e8f  test    byte ptr [rcx+19h], 1
0x1c0073e93  jz      loc_1C0011FC5
0x1c0073e99  mov     r14b, 1
0x1c0073e9c  jmp     loc_1C0011F5D
0x1c0073ea1  mov     rdi, [rsp+58h+arg_0]
0x1c0073ea6  mov     rcx, [rbx+8]
0x1c0073eaa  mov     rax, rbx
0x1c0073ead  test    rcx, rcx
0x1c0073eb0  jz      short loc_1C0073F14
0x1c0073eb2  cmp     [rsp+58h+arg_10], 0
0x1c0073eb7  jz      short loc_1C0073ECB
0x1c0073eb9  movzx   eax, byte ptr [rcx+18h]
0x1c0073ebd  test    al, 40h
0x1c0073ebf  jz      short loc_1C0073ECB
0x1c0073ec1  test    al, al
0x1c0073ec3  jns     short loc_1C0073ECB
0x1c0073ec5  test    byte ptr [rcx+19h], 1
0x1c0073ec9  jnz     short loc_1C0073F44
0x1c0073ecb  add     rcx, 68h ; 'h'
0x1c0073ecf  mov     edx, 2
0x1c0073ed4  call    cs:__imp_ExReleasePushLockEx
0x1c0073edb  nop     dword ptr [rax+rax+00h]
0x1c0073ee0  dec     dword ptr [rbp+0B0Ch]
0x1c0073ee6  lea     rcx, [rdi+148h]; RemoveLock
0x1c0073eed  mov     rax, [rbx+8]
0x1c0073ef1  xor     edx, edx; Tag
0x1c0073ef3  lock dec dword ptr [rax+58h]
0x1c0073ef7  lea     r8d, [rdx+20h]; RemlockSize
0x1c0073efb  call    cs:__imp_IoReleaseRemoveLockEx
0x1c0073f02  nop     dword ptr [rax+rax+00h]
0x1c0073f07  dec     dword ptr [rbp+0B08h]
0x1c0073f0d  mov     rax, [rbp+0A40h]
0x1c0073f14  mov     rax, [rax]
0x1c0073f17  xor     edx, edx; Tag
0x1c0073f19  mov     rcx, rbx; P
0x1c0073f1c  mov     [rbp+0A40h], rax
0x1c0073f23  call    cs:__imp_ExFreePoolWithTag
0x1c0073f2a  nop     dword ptr [rax+rax+00h]
0x1c0073f2f  mov     rbx, [rbp+0A40h]
0x1c0073f36  test    rbx, rbx
0x1c0073f39  jnz     loc_1C0073EA6
0x1c0073f3f  jmp     loc_1C0011F86
0x1c0073f44  test    rbx, rbx
0x1c0073f47  jz      short loc_1C0073F75
0x1c0073f49  mov     rcx, [rbx+8]
0x1c0073f4d  test    rcx, rcx
0x1c0073f50  jz      short loc_1C0073F6D
0x1c0073f52  add     rcx, 68h ; 'h'
0x1c0073f56  mov     edx, 2
0x1c0073f5b  call    cs:__imp_ExReleasePushLockEx
0x1c0073f62  nop     dword ptr [rax+rax+00h]
0x1c0073f67  dec     dword ptr [rbp+0B0Ch]
0x1c0073f6d  mov     rbx, [rbx]
0x1c0073f70  test    rbx, rbx
0x1c0073f73  jnz     short loc_1C0073F49
0x1c0073f75  mov     r8, [r15]; struct SmsContainer *
0x1c0073f78  test    r8, r8
0x1c0073f7b  jz      short loc_1C0073FBA
0x1c0073f7d  mov     rcx, rdi; this
0x1c0073f80  call    ?RequeryWH@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::RequeryWH(CmsTransactionContext *,SmsContainer *)
0x1c0073f85  mov     rax, [r15]
0x1c0073f88  lea     rcx, [rdi+148h]; RemoveLock
0x1c0073f8f  xor     edx, edx; Tag
0x1c0073f91  lock dec dword ptr [rax+58h]
0x1c0073f95  lea     r8d, [rdx+20h]; RemlockSize
0x1c0073f99  call    cs:__imp_IoReleaseRemoveLockEx
0x1c0073fa0  nop     dword ptr [rax+rax+00h]
0x1c0073fa5  dec     dword ptr [rbp+0B08h]
0x1c0073fab  mov     qword ptr [r15], 0
0x1c0073fb2  mov     dword ptr [r12], 0
0x1c0073fba  add     r15, 8
0x1c0073fbe  add     r12, 4
0x1c0073fc2  sub     r13, 1
0x1c0073fc6  jnz     short loc_1C0073F75
0x1c0073fc8  mov     rbx, [rbp+0A40h]
0x1c0073fcf  test    rbx, rbx
0x1c0073fd2  jz      loc_1C0011F8B
0x1c0073fd8  mov     r8, [rbx+8]; struct SmsContainer *
0x1c0073fdc  mov     rax, rbx
0x1c0073fdf  test    r8, r8
0x1c0073fe2  jz      short loc_1C007401A
0x1c0073fe4  mov     rcx, rdi; this
0x1c0073fe7  call    ?RequeryWH@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::RequeryWH(CmsTransactionContext *,SmsContainer *)
0x1c0073fec  mov     rax, [rbx+8]
0x1c0073ff0  lea     rcx, [rdi+148h]; RemoveLock
0x1c0073ff7  xor     edx, edx; Tag
0x1c0073ff9  lock dec dword ptr [rax+58h]
0x1c0073ffd  lea     r8d, [rdx+20h]; RemlockSize
0x1c0074001  call    cs:__imp_IoReleaseRemoveLockEx
0x1c0074008  nop     dword ptr [rax+rax+00h]
0x1c007400d  dec     dword ptr [rbp+0B08h]
0x1c0074013  mov     rax, [rbp+0A40h]
0x1c007401a  mov     rax, [rax]
0x1c007401d  xor     edx, edx; Tag
0x1c007401f  mov     rcx, rbx; P
0x1c0074022  mov     [rbp+0A40h], rax
0x1c0074029  call    cs:__imp_ExFreePoolWithTag
0x1c0074030  nop     dword ptr [rax+rax+00h]
0x1c0074035  mov     rbx, [rbp+0A40h]
0x1c007403c  test    rbx, rbx
0x1c007403f  jnz     short loc_1C0073FD8
0x1c0074041  jmp     loc_1C0011F8B
```
