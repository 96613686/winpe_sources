# LuafvPreCleanup

- ea: `0x140021a70`
- end: `0x140021ca6`
- name: `LuafvPreCleanup`
- size: `566`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001adc`
- `0x140021a70`

## import_xrefs

- `ntoskrnl!IoRemoveShareAccess` at `0x140021c0f`
- `ntoskrnl!IoRemoveShareAccess` at `0x140021c0f`
- `ntoskrnl!ObfDereferenceObject` at `0x140021c68`
- `ntoskrnl!ObfDereferenceObject` at `0x140021c68`
- `FLTMGR!FltFreeCallbackData` at `0x140021bd8`
- `FLTMGR!FltFreeCallbackData` at `0x140021bd8`
- `FLTMGR!FltPerformSynchronousIo` at `0x140021bc8`
- `FLTMGR!FltPerformSynchronousIo` at `0x140021bc8`
- `FLTMGR!FltAllocateCallbackData` at `0x140021b9c`
- `FLTMGR!FltAllocateCallbackData` at `0x140021b9c`
- `FLTMGR!FltGetStreamHandleContext` at `0x140021acf`
- `FLTMGR!FltGetStreamHandleContext` at `0x140021acf`
- `FLTMGR!FltReleasePushLockEx` at `0x140021b6a`
- `FLTMGR!FltReleasePushLockEx` at `0x140021c20`
- `FLTMGR!FltReleasePushLockEx` at `0x140021b6a`
- `FLTMGR!FltReleasePushLockEx` at `0x140021c20`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140021b25`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140021bf8`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140021b25`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140021bf8`
- `FLTMGR!FltClose` at `0x140021b79`
- `FLTMGR!FltClose` at `0x140021be7`
- `FLTMGR!FltClose` at `0x140021c8d`
- `FLTMGR!FltClose` at `0x140021b79`
- `FLTMGR!FltClose` at `0x140021be7`
- `FLTMGR!FltClose` at `0x140021c8d`

## pseudocode

```c
__int64 __fastcall LuafvPreCleanup(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 v7; // rax
  struct _FILE_OBJECT *v8; // rdi
  __int64 result; // rax
  PVOID FsContext; // rsi
  __int64 v11; // r15
  struct _FILE_OBJECT *v12; // rax
  void *v13; // rbx
  void *v14; // r12
  _QWORD *v15; // rdx
  void *v16; // rcx
  void *v17; // rcx
  struct _FILE_OBJECT *FileObject; // [rsp+20h] [rbp-10h]
  __int64 v19; // [rsp+28h] [rbp-8h]
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+70h] [rbp+40h] BYREF
  PFLT_CONTEXT Context; // [rsp+88h] [rbp+58h] BYREF

  v4 = *(_QWORD *)(a1 + 16);
  Context = 0;
  RetNewCallbackData = 0;
  v7 = *(_QWORD *)(v4 + 8);
  if ( v7 && (*(_DWORD *)(v7 + 80) & 0x400000) != 0 )
    return 5;
  v8 = *(struct _FILE_OBJECT **)(a2 + 32);
  if ( v8 && (FsContext = v8->FsContext) != 0 && *(_WORD *)FsContext == 30310 )
  {
    v19 = *((_QWORD *)FsContext + 24);
    v11 = v19 + 64;
    FltAcquirePushLockExclusiveEx(v19 + 64, 0);
    v12 = (struct _FILE_OBJECT *)*((_QWORD *)FsContext + 29);
    v13 = (void *)*((_QWORD *)FsContext + 26);
    v14 = (void *)*((_QWORD *)FsContext + 28);
    *((_QWORD *)FsContext + 26) = 0;
    *((_QWORD *)FsContext + 28) = 0;
    v8->Flags |= 0x4000u;
    FileObject = v12;
    FltReleasePushLockEx(v19 + 64, 0);
    FltClose(v13);
    if ( v14 )
    {
      if ( v8->LockOperation
        && FltAllocateCallbackData(*(PFLT_INSTANCE *)(a2 + 24), FileObject, &RetNewCallbackData) >= 0 )
      {
        RetNewCallbackData->Iopb->MajorFunction = 17;
        RetNewCallbackData->Iopb->MinorFunction = 3;
        FltPerformSynchronousIo(RetNewCallbackData);
        FltFreeCallbackData(RetNewCallbackData);
      }
      FltClose(v14);
    }
    FltAcquirePushLockExclusiveEx(v11, 0);
    IoRemoveShareAccess(v8, (PSHARE_ACCESS)(v19 + 72));
    FltReleasePushLockEx(v11, 0);
    result = 4;
    *(_DWORD *)(a1 + 24) = 0;
  }
  else
  {
    if ( (unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline(a1, a2, a3, a4) )
    {
      if ( FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) >= 0 )
      {
        v15 = Context;
        if ( Context )
        {
          if ( (*((_BYTE *)Context + 53) & 0x10) != 0 )
          {
            v16 = (void *)*((_QWORD *)Context + 4);
            if ( v16 )
            {
              ObfDereferenceObject(v16);
              *((_QWORD *)Context + 4) = 0;
              v15 = Context;
            }
            v17 = (void *)v15[3];
            if ( v17 )
            {
              FltClose(v17);
              *((_QWORD *)Context + 3) = 0;
            }
          }
        }
      }
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x140021a70  mov     [rsp-38h+arg_8], rbx
0x140021a75  push    rbp
0x140021a76  push    rsi
0x140021a77  push    rdi
0x140021a78  push    r12
0x140021a7a  push    r13
0x140021a7c  push    r14
0x140021a7e  push    r15
0x140021a80  mov     rbp, rsp
0x140021a83  sub     rsp, 30h
0x140021a87  mov     rax, [rcx+10h]
0x140021a8b  xor     ebx, ebx
0x140021a8d  mov     [rbp+Context], rbx
0x140021a91  mov     r14, rdx
0x140021a94  mov     [rbp+RetNewCallbackData], rbx
0x140021a98  mov     r13, rcx
0x140021a9b  mov     rax, [rax+8]
0x140021a9f  test    rax, rax
0x140021aa2  jz      short loc_140021AB1
0x140021aa4  test    dword ptr [rax+50h], 400000h
0x140021aab  jnz     loc_140021C3E
0x140021ab1  mov     rdi, [rdx+20h]
0x140021ab5  test    rdi, rdi
0x140021ab8  jnz     short loc_140021AFE
0x140021aba  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x140021abf  test    eax, eax
0x140021ac1  jz      short loc_140021AE3
0x140021ac3  mov     rdx, [r14+20h]; FileObject
0x140021ac7  lea     r8, [rbp+Context]; Context
0x140021acb  mov     rcx, [r14+18h]; Instance
0x140021acf  call    cs:__imp_FltGetStreamHandleContext
0x140021ad6  nop     dword ptr [rax+rax+00h]
0x140021adb  test    eax, eax
0x140021add  jns     loc_140021C48
0x140021ae3  mov     eax, 1
0x140021ae8  mov     rbx, [rsp+30h+arg_8]
0x140021aed  add     rsp, 30h
0x140021af1  pop     r15
0x140021af3  pop     r14
0x140021af5  pop     r13
0x140021af7  pop     r12
0x140021af9  pop     rdi
0x140021afa  pop     rsi
0x140021afb  pop     rbp
0x140021afc  retn
0x140021afe  mov     rsi, [rdi+18h]
0x140021b02  test    rsi, rsi
0x140021b05  jz      short loc_140021ABA
0x140021b07  mov     eax, 7666h
0x140021b0c  cmp     [rsi], ax
0x140021b0f  jnz     short loc_140021ABA
0x140021b11  mov     rax, [rsi+0C0h]
0x140021b18  xor     edx, edx
0x140021b1a  mov     [rbp+var_8], rax
0x140021b1e  lea     r15, [rax+40h]
0x140021b22  mov     rcx, r15
0x140021b25  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140021b2c  nop     dword ptr [rax+rax+00h]
0x140021b31  mov     rax, [rsi+0E8h]
0x140021b38  xor     edx, edx
0x140021b3a  mov     rbx, [rsi+0D0h]
0x140021b41  mov     rcx, r15
0x140021b44  mov     r12, [rsi+0E0h]
0x140021b4b  mov     qword ptr [rsi+0D0h], 0
0x140021b56  mov     qword ptr [rsi+0E0h], 0
0x140021b61  bts     dword ptr [rdi+50h], 0Eh
0x140021b66  mov     [rbp+FileObject], rax
0x140021b6a  call    cs:__imp_FltReleasePushLockEx
0x140021b71  nop     dword ptr [rax+rax+00h]
0x140021b76  mov     rcx, rbx; FileHandle
0x140021b79  call    cs:__imp_FltClose
0x140021b80  nop     dword ptr [rax+rax+00h]
0x140021b85  test    r12, r12
0x140021b88  jz      short loc_140021BF3
0x140021b8a  cmp     byte ptr [rdi+48h], 0
0x140021b8e  jz      short loc_140021BE4
0x140021b90  mov     rdx, [rbp+FileObject]; FileObject
0x140021b94  lea     r8, [rbp+RetNewCallbackData]; RetNewCallbackData
0x140021b98  mov     rcx, [r14+18h]; Instance
0x140021b9c  call    cs:__imp_FltAllocateCallbackData
0x140021ba3  nop     dword ptr [rax+rax+00h]
0x140021ba8  test    eax, eax
0x140021baa  js      short loc_140021BE4
0x140021bac  mov     rax, [rbp+RetNewCallbackData]
0x140021bb0  mov     rdx, [rax+10h]
0x140021bb4  mov     byte ptr [rdx+4], 11h
0x140021bb8  mov     rax, [rbp+RetNewCallbackData]
0x140021bbc  mov     rdx, [rax+10h]
0x140021bc0  mov     byte ptr [rdx+5], 3
0x140021bc4  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x140021bc8  call    cs:__imp_FltPerformSynchronousIo
0x140021bcf  nop     dword ptr [rax+rax+00h]
0x140021bd4  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x140021bd8  call    cs:__imp_FltFreeCallbackData
0x140021bdf  nop     dword ptr [rax+rax+00h]
0x140021be4  mov     rcx, r12; FileHandle
0x140021be7  call    cs:__imp_FltClose
0x140021bee  nop     dword ptr [rax+rax+00h]
0x140021bf3  xor     edx, edx
0x140021bf5  mov     rcx, r15
0x140021bf8  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140021bff  nop     dword ptr [rax+rax+00h]
0x140021c04  mov     rdx, [rbp+var_8]
0x140021c08  mov     rcx, rdi; FileObject
0x140021c0b  add     rdx, 48h ; 'H'; ShareAccess
0x140021c0f  call    cs:__imp_IoRemoveShareAccess
0x140021c16  nop     dword ptr [rax+rax+00h]
0x140021c1b  xor     edx, edx
0x140021c1d  mov     rcx, r15
0x140021c20  call    cs:__imp_FltReleasePushLockEx
0x140021c27  nop     dword ptr [rax+rax+00h]
0x140021c2c  mov     eax, 4
0x140021c31  mov     dword ptr [r13+18h], 0
0x140021c39  jmp     loc_140021AE8
0x140021c3e  mov     eax, 5
0x140021c43  jmp     loc_140021AE8
0x140021c48  mov     rdx, [rbp+Context]
0x140021c4c  test    rdx, rdx
0x140021c4f  jz      loc_140021AE3
0x140021c55  test    byte ptr [rdx+35h], 10h
0x140021c59  jz      loc_140021AE3
0x140021c5f  mov     rcx, [rdx+20h]; Object
0x140021c63  test    rcx, rcx
0x140021c66  jz      short loc_140021C80
0x140021c68  call    cs:__imp_ObfDereferenceObject
0x140021c6f  nop     dword ptr [rax+rax+00h]
0x140021c74  mov     rax, [rbp+Context]
0x140021c78  mov     [rax+20h], rbx
0x140021c7c  mov     rdx, [rbp+Context]
0x140021c80  mov     rcx, [rdx+18h]; FileHandle
0x140021c84  test    rcx, rcx
0x140021c87  jz      loc_140021AE3
0x140021c8d  call    cs:__imp_FltClose
0x140021c94  nop     dword ptr [rax+rax+00h]
0x140021c99  mov     rax, [rbp+Context]
0x140021c9d  mov     [rax+18h], rbx
0x140021ca1  jmp     loc_140021AE3
```
