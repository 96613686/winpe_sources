# LuafvPreCleanup

- ea: `0x140021a20`
- end: `0x140021c56`
- name: `LuafvPreCleanup`
- size: `566`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001adc`
- `0x140021a20`

## import_xrefs

- `ntoskrnl!IoRemoveShareAccess` at `0x140021bbf`
- `ntoskrnl!IoRemoveShareAccess` at `0x140021bbf`
- `ntoskrnl!ObfDereferenceObject` at `0x140021c18`
- `ntoskrnl!ObfDereferenceObject` at `0x140021c18`
- `FLTMGR!FltFreeCallbackData` at `0x140021b88`
- `FLTMGR!FltFreeCallbackData` at `0x140021b88`
- `FLTMGR!FltPerformSynchronousIo` at `0x140021b78`
- `FLTMGR!FltPerformSynchronousIo` at `0x140021b78`
- `FLTMGR!FltAllocateCallbackData` at `0x140021b4c`
- `FLTMGR!FltAllocateCallbackData` at `0x140021b4c`
- `FLTMGR!FltGetStreamHandleContext` at `0x140021a7f`
- `FLTMGR!FltGetStreamHandleContext` at `0x140021a7f`
- `FLTMGR!FltReleasePushLockEx` at `0x140021b1a`
- `FLTMGR!FltReleasePushLockEx` at `0x140021bd0`
- `FLTMGR!FltReleasePushLockEx` at `0x140021b1a`
- `FLTMGR!FltReleasePushLockEx` at `0x140021bd0`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140021ad5`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140021ba8`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140021ad5`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140021ba8`
- `FLTMGR!FltClose` at `0x140021b29`
- `FLTMGR!FltClose` at `0x140021b97`
- `FLTMGR!FltClose` at `0x140021c3d`
- `FLTMGR!FltClose` at `0x140021b29`
- `FLTMGR!FltClose` at `0x140021b97`
- `FLTMGR!FltClose` at `0x140021c3d`

## pseudocode

```c
__int64 __fastcall LuafvPreCleanup(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v5; // rax
  struct _FILE_OBJECT *v6; // rdi
  __int64 result; // rax
  PVOID FsContext; // rsi
  __int64 v9; // r15
  struct _FILE_OBJECT *v10; // rax
  void *v11; // rbx
  void *v12; // r12
  _QWORD *v13; // rdx
  void *v14; // rcx
  void *v15; // rcx
  struct _FILE_OBJECT *FileObject; // [rsp+20h] [rbp-10h]
  __int64 v17; // [rsp+28h] [rbp-8h]
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+70h] [rbp+40h] BYREF
  PFLT_CONTEXT Context; // [rsp+88h] [rbp+58h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  Context = 0;
  RetNewCallbackData = 0;
  v5 = *(_QWORD *)(v2 + 8);
  if ( v5 && (*(_DWORD *)(v5 + 80) & 0x400000) != 0 )
    return 5;
  v6 = *(struct _FILE_OBJECT **)(a2 + 32);
  if ( v6 && (FsContext = v6->FsContext) != 0 && *(_WORD *)FsContext == 30310 )
  {
    v17 = *((_QWORD *)FsContext + 24);
    v9 = v17 + 64;
    FltAcquirePushLockExclusiveEx(v17 + 64, 0);
    v10 = (struct _FILE_OBJECT *)*((_QWORD *)FsContext + 29);
    v11 = (void *)*((_QWORD *)FsContext + 26);
    v12 = (void *)*((_QWORD *)FsContext + 28);
    *((_QWORD *)FsContext + 26) = 0;
    *((_QWORD *)FsContext + 28) = 0;
    v6->Flags |= 0x4000u;
    FileObject = v10;
    FltReleasePushLockEx(v17 + 64, 0);
    FltClose(v11);
    if ( v12 )
    {
      if ( v6->LockOperation
        && FltAllocateCallbackData(*(PFLT_INSTANCE *)(a2 + 24), FileObject, &RetNewCallbackData) >= 0 )
      {
        RetNewCallbackData->Iopb->MajorFunction = 17;
        RetNewCallbackData->Iopb->MinorFunction = 3;
        FltPerformSynchronousIo(RetNewCallbackData);
        FltFreeCallbackData(RetNewCallbackData);
      }
      FltClose(v12);
    }
    FltAcquirePushLockExclusiveEx(v9, 0);
    IoRemoveShareAccess(v6, (PSHARE_ACCESS)(v17 + 72));
    FltReleasePushLockEx(v9, 0);
    result = 4;
    *(_DWORD *)(a1 + 24) = 0;
  }
  else
  {
    if ( (unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) >= 0 )
      {
        v13 = Context;
        if ( Context )
        {
          if ( (*((_BYTE *)Context + 53) & 0x10) != 0 )
          {
            v14 = (void *)*((_QWORD *)Context + 4);
            if ( v14 )
            {
              ObfDereferenceObject(v14);
              *((_QWORD *)Context + 4) = 0;
              v13 = Context;
            }
            v15 = (void *)v13[3];
            if ( v15 )
            {
              FltClose(v15);
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
0x140021a20  mov     [rsp-38h+arg_8], rbx
0x140021a25  push    rbp
0x140021a26  push    rsi
0x140021a27  push    rdi
0x140021a28  push    r12
0x140021a2a  push    r13
0x140021a2c  push    r14
0x140021a2e  push    r15
0x140021a30  mov     rbp, rsp
0x140021a33  sub     rsp, 30h
0x140021a37  mov     rax, [rcx+10h]
0x140021a3b  xor     ebx, ebx
0x140021a3d  mov     [rbp+Context], rbx
0x140021a41  mov     r14, rdx
0x140021a44  mov     [rbp+RetNewCallbackData], rbx
0x140021a48  mov     r13, rcx
0x140021a4b  mov     rax, [rax+8]
0x140021a4f  test    rax, rax
0x140021a52  jz      short loc_140021A61
0x140021a54  test    dword ptr [rax+50h], 400000h
0x140021a5b  jnz     loc_140021BEE
0x140021a61  mov     rdi, [rdx+20h]
0x140021a65  test    rdi, rdi
0x140021a68  jnz     short loc_140021AAE
0x140021a6a  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x140021a6f  test    eax, eax
0x140021a71  jz      short loc_140021A93
0x140021a73  mov     rdx, [r14+20h]; FileObject
0x140021a77  lea     r8, [rbp+Context]; Context
0x140021a7b  mov     rcx, [r14+18h]; Instance
0x140021a7f  call    cs:__imp_FltGetStreamHandleContext
0x140021a86  nop     dword ptr [rax+rax+00h]
0x140021a8b  test    eax, eax
0x140021a8d  jns     loc_140021BF8
0x140021a93  mov     eax, 1
0x140021a98  mov     rbx, [rsp+30h+arg_8]
0x140021a9d  add     rsp, 30h
0x140021aa1  pop     r15
0x140021aa3  pop     r14
0x140021aa5  pop     r13
0x140021aa7  pop     r12
0x140021aa9  pop     rdi
0x140021aaa  pop     rsi
0x140021aab  pop     rbp
0x140021aac  retn
0x140021aae  mov     rsi, [rdi+18h]
0x140021ab2  test    rsi, rsi
0x140021ab5  jz      short loc_140021A6A
0x140021ab7  mov     eax, 7666h
0x140021abc  cmp     [rsi], ax
0x140021abf  jnz     short loc_140021A6A
0x140021ac1  mov     rax, [rsi+0C0h]
0x140021ac8  xor     edx, edx
0x140021aca  mov     [rbp+var_8], rax
0x140021ace  lea     r15, [rax+40h]
0x140021ad2  mov     rcx, r15
0x140021ad5  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140021adc  nop     dword ptr [rax+rax+00h]
0x140021ae1  mov     rax, [rsi+0E8h]
0x140021ae8  xor     edx, edx
0x140021aea  mov     rbx, [rsi+0D0h]
0x140021af1  mov     rcx, r15
0x140021af4  mov     r12, [rsi+0E0h]
0x140021afb  mov     qword ptr [rsi+0D0h], 0
0x140021b06  mov     qword ptr [rsi+0E0h], 0
0x140021b11  bts     dword ptr [rdi+50h], 0Eh
0x140021b16  mov     [rbp+FileObject], rax
0x140021b1a  call    cs:__imp_FltReleasePushLockEx
0x140021b21  nop     dword ptr [rax+rax+00h]
0x140021b26  mov     rcx, rbx; FileHandle
0x140021b29  call    cs:__imp_FltClose
0x140021b30  nop     dword ptr [rax+rax+00h]
0x140021b35  test    r12, r12
0x140021b38  jz      short loc_140021BA3
0x140021b3a  cmp     byte ptr [rdi+48h], 0
0x140021b3e  jz      short loc_140021B94
0x140021b40  mov     rdx, [rbp+FileObject]; FileObject
0x140021b44  lea     r8, [rbp+RetNewCallbackData]; RetNewCallbackData
0x140021b48  mov     rcx, [r14+18h]; Instance
0x140021b4c  call    cs:__imp_FltAllocateCallbackData
0x140021b53  nop     dword ptr [rax+rax+00h]
0x140021b58  test    eax, eax
0x140021b5a  js      short loc_140021B94
0x140021b5c  mov     rax, [rbp+RetNewCallbackData]
0x140021b60  mov     rdx, [rax+10h]
0x140021b64  mov     byte ptr [rdx+4], 11h
0x140021b68  mov     rax, [rbp+RetNewCallbackData]
0x140021b6c  mov     rdx, [rax+10h]
0x140021b70  mov     byte ptr [rdx+5], 3
0x140021b74  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x140021b78  call    cs:__imp_FltPerformSynchronousIo
0x140021b7f  nop     dword ptr [rax+rax+00h]
0x140021b84  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x140021b88  call    cs:__imp_FltFreeCallbackData
0x140021b8f  nop     dword ptr [rax+rax+00h]
0x140021b94  mov     rcx, r12; FileHandle
0x140021b97  call    cs:__imp_FltClose
0x140021b9e  nop     dword ptr [rax+rax+00h]
0x140021ba3  xor     edx, edx
0x140021ba5  mov     rcx, r15
0x140021ba8  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140021baf  nop     dword ptr [rax+rax+00h]
0x140021bb4  mov     rdx, [rbp+var_8]
0x140021bb8  mov     rcx, rdi; FileObject
0x140021bbb  add     rdx, 48h ; 'H'; ShareAccess
0x140021bbf  call    cs:__imp_IoRemoveShareAccess
0x140021bc6  nop     dword ptr [rax+rax+00h]
0x140021bcb  xor     edx, edx
0x140021bcd  mov     rcx, r15
0x140021bd0  call    cs:__imp_FltReleasePushLockEx
0x140021bd7  nop     dword ptr [rax+rax+00h]
0x140021bdc  mov     eax, 4
0x140021be1  mov     dword ptr [r13+18h], 0
0x140021be9  jmp     loc_140021A98
0x140021bee  mov     eax, 5
0x140021bf3  jmp     loc_140021A98
0x140021bf8  mov     rdx, [rbp+Context]
0x140021bfc  test    rdx, rdx
0x140021bff  jz      loc_140021A93
0x140021c05  test    byte ptr [rdx+35h], 10h
0x140021c09  jz      loc_140021A93
0x140021c0f  mov     rcx, [rdx+20h]; Object
0x140021c13  test    rcx, rcx
0x140021c16  jz      short loc_140021C30
0x140021c18  call    cs:__imp_ObfDereferenceObject
0x140021c1f  nop     dword ptr [rax+rax+00h]
0x140021c24  mov     rax, [rbp+Context]
0x140021c28  mov     [rax+20h], rbx
0x140021c2c  mov     rdx, [rbp+Context]
0x140021c30  mov     rcx, [rdx+18h]; FileHandle
0x140021c34  test    rcx, rcx
0x140021c37  jz      loc_140021A93
0x140021c3d  call    cs:__imp_FltClose
0x140021c44  nop     dword ptr [rax+rax+00h]
0x140021c49  mov     rax, [rbp+Context]
0x140021c4d  mov     [rax+18h], rbx
0x140021c51  jmp     loc_140021A93
```
