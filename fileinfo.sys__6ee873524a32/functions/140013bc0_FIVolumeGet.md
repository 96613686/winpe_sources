# FIVolumeGet

- ea: `0x140013bc0`
- end: `0x140013d65`
- name: `FIVolumeGet`
- size: `421`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x14000e5a0`
- `0x1400100d0`
- `0x140010cd0`
- `0x140012c54`
- `0x140013560`
- `0x1400138d4`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x140002e30`
- `0x140013bc0`
- `0x1400142d0`

## import_xrefs

- `ntoskrnl!IoGetBaseFileSystemDeviceObject` at `0x140013c8b`
- `ntoskrnl!IoGetBaseFileSystemDeviceObject` at `0x140013c8b`
- `FLTMGR!FltSetInstanceContext` at `0x140013cc8`
- `FLTMGR!FltSetInstanceContext` at `0x140013cc8`
- `FLTMGR!FltReleaseContext` at `0x140013c5a`
- `FLTMGR!FltReleaseContext` at `0x140013cee`
- `FLTMGR!FltReleaseContext` at `0x140013c5a`
- `FLTMGR!FltReleaseContext` at `0x140013cee`
- `FLTMGR!FltGetInstanceContext` at `0x140013bf6`
- `FLTMGR!FltGetInstanceContext` at `0x140013bf6`

## pseudocode

```c
__int64 __fastcall FIVolumeGet(__int64 *a1, PFLT_CONTEXT *a2, int *a3)
{
  int v6; // esi
  struct _FLT_INSTANCE *v7; // rcx
  NTSTATUS InstanceContext; // eax
  NTSTATUS v9; // edi
  _QWORD *v11; // rdi
  PDEVICE_OBJECT BaseFileSystemDeviceObject; // rax
  __int64 v13; // rdx
  struct _FLT_INSTANCE *v14; // rcx
  NTSTATUS v15; // eax
  _QWORD *v16; // rax
  _QWORD *v17; // rcx
  PFLT_CONTEXT Context; // [rsp+50h] [rbp+8h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+60h] [rbp+18h] BYREF

  OldContext = 0;
  if ( a3 )
    v6 = *a3;
  else
    v6 = 0;
  v7 = (struct _FLT_INSTANCE *)a1[1];
  Context = 0;
  InstanceContext = FltGetInstanceContext(v7, &Context);
  v9 = InstanceContext;
  if ( InstanceContext >= 0 )
  {
    v6 |= 1u;
LABEL_5:
    if ( FIShimIsListEmptyUnsynchronized(Context) )
    {
      FILockExclusiveAcquire((__int64)&qword_140009388);
      v16 = Context;
      if ( (_QWORD *)*v16 == v16 )
      {
        v17 = (_QWORD *)qword_140009398;
        if ( *(__int64 **)qword_140009398 != &qword_140009390 )
          __fastfail(3u);
        *(_QWORD *)Context = &qword_140009390;
        v16[1] = v17;
        *v17 = v16;
        qword_140009398 = (__int64)v16;
      }
      FILockExclusiveRelease((__int64)&qword_140009388);
    }
    v9 = 0;
    *a2 = Context;
    goto LABEL_7;
  }
  if ( InstanceContext == -1073741275 )
  {
    if ( (v6 & 0x10000) != 0 )
    {
      v9 = -1073741275;
    }
    else
    {
      v9 = FIVolumeCreate(&Context);
      if ( v9 >= 0 )
      {
        v11 = Context;
        BaseFileSystemDeviceObject = IoGetBaseFileSystemDeviceObject((PFILE_OBJECT)a1[2]);
        v13 = *a1;
        v14 = (struct _FLT_INSTANCE *)a1[1];
        v11[9] = BaseFileSystemDeviceObject;
        *((_QWORD *)Context + 7) = v14;
        *((_QWORD *)Context + 6) = v13;
        OldContext = 0;
        v15 = FltSetInstanceContext(v14, FLT_SET_CONTEXT_KEEP_IF_EXISTS, Context, &OldContext);
        v9 = v15;
        if ( v15 >= 0 )
          goto LABEL_5;
        if ( v15 == -1071906814 )
        {
          FltReleaseContext(Context);
          Context = OldContext;
          goto LABEL_5;
        }
      }
    }
  }
  else
  {
    v6 |= 2u;
  }
  if ( Context )
    FltReleaseContext(Context);
LABEL_7:
  if ( a3 )
    *a3 = v6;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140013bc0  mov     [rsp+arg_8], rbx
0x140013bc5  push    rbp
0x140013bc6  push    rsi
0x140013bc7  push    rdi
0x140013bc8  push    r14
0x140013bca  push    r15
0x140013bcc  sub     rsp, 20h
0x140013bd0  xor     ebp, ebp
0x140013bd2  mov     rbx, r8
0x140013bd5  mov     [rsp+48h+OldContext], rbp
0x140013bda  mov     r14, rdx
0x140013bdd  mov     r15, rcx
0x140013be0  test    r8, r8
0x140013be3  jz      short loc_140013C42
0x140013be5  mov     esi, [r8]
0x140013be8  mov     rcx, [rcx+8]; Instance
0x140013bec  lea     rdx, [rsp+48h+Context]; Context
0x140013bf1  mov     [rsp+48h+Context], rbp
0x140013bf6  call    cs:__imp_FltGetInstanceContext
0x140013bfd  nop     dword ptr [rax+rax+00h]
0x140013c02  mov     edi, eax
0x140013c04  test    eax, eax
0x140013c06  js      short loc_140013C46
0x140013c08  or      esi, 1
0x140013c0b  mov     rcx, [rsp+48h+Context]
0x140013c10  call    FIShimIsListEmptyUnsynchronized
0x140013c15  test    al, al
0x140013c17  jnz     loc_140013D09
0x140013c1d  mov     rax, [rsp+48h+Context]
0x140013c22  mov     edi, ebp
0x140013c24  mov     [r14], rax
0x140013c27  test    rbx, rbx
0x140013c2a  jz      short loc_140013C2E
0x140013c2c  mov     [rbx], esi
0x140013c2e  mov     rbx, [rsp+48h+arg_8]
0x140013c33  mov     eax, edi
0x140013c35  add     rsp, 20h
0x140013c39  pop     r15
0x140013c3b  pop     r14
0x140013c3d  pop     rdi
0x140013c3e  pop     rsi
0x140013c3f  pop     rbp
0x140013c40  retn
0x140013c42  mov     esi, ebp
0x140013c44  jmp     short loc_140013BE8
0x140013c46  cmp     eax, 0C0000225h
0x140013c4b  jz      short loc_140013C68
0x140013c4d  or      esi, 2
0x140013c50  mov     rcx, [rsp+48h+Context]; Context
0x140013c55  test    rcx, rcx
0x140013c58  jz      short loc_140013C27
0x140013c5a  call    cs:__imp_FltReleaseContext
0x140013c61  nop     dword ptr [rax+rax+00h]
0x140013c66  jmp     short loc_140013C27
0x140013c68  bt      esi, 10h
0x140013c6c  jb      loc_140013D5B
0x140013c72  lea     rcx, [rsp+48h+Context]
0x140013c77  call    FIVolumeCreate
0x140013c7c  mov     edi, eax
0x140013c7e  test    eax, eax
0x140013c80  js      short loc_140013C50
0x140013c82  mov     rcx, [r15+10h]; FileObject
0x140013c86  mov     rdi, [rsp+48h+Context]
0x140013c8b  call    cs:__imp_IoGetBaseFileSystemDeviceObject
0x140013c92  nop     dword ptr [rax+rax+00h]
0x140013c97  mov     rdx, [r15]
0x140013c9a  lea     r9, [rsp+48h+OldContext]; OldContext
0x140013c9f  mov     rcx, [r15+8]; Instance
0x140013ca3  mov     [rdi+48h], rax
0x140013ca7  mov     rax, [rsp+48h+Context]
0x140013cac  mov     [rax+38h], rcx
0x140013cb0  mov     rax, [rsp+48h+Context]
0x140013cb5  mov     [rax+30h], rdx
0x140013cb9  mov     edx, 1; Operation
0x140013cbe  mov     r8, [rsp+48h+Context]; NewContext
0x140013cc3  mov     [rsp+48h+OldContext], rbp
0x140013cc8  call    cs:__imp_FltSetInstanceContext
0x140013ccf  nop     dword ptr [rax+rax+00h]
0x140013cd4  mov     edi, eax
0x140013cd6  test    eax, eax
0x140013cd8  jns     loc_140013C0B
0x140013cde  cmp     eax, 0C01C0002h
0x140013ce3  jnz     loc_140013C50
0x140013ce9  mov     rcx, [rsp+48h+Context]; Context
0x140013cee  call    cs:__imp_FltReleaseContext
0x140013cf5  nop     dword ptr [rax+rax+00h]
0x140013cfa  mov     rax, [rsp+48h+OldContext]
0x140013cff  mov     [rsp+48h+Context], rax
0x140013d04  jmp     loc_140013C0B
0x140013d09  lea     rcx, qword_140009388
0x140013d10  call    FILockExclusiveAcquire
0x140013d15  mov     rax, [rsp+48h+Context]
0x140013d1a  cmp     [rax], rax
0x140013d1d  jnz     short loc_140013D4A
0x140013d1f  mov     rcx, cs:qword_140009398
0x140013d26  lea     rdx, qword_140009390
0x140013d2d  cmp     [rcx], rdx
0x140013d30  jz      short loc_140013D39
0x140013d32  mov     ecx, 3
0x140013d37  int     29h; Win8: RtlFailFast(ecx)
0x140013d39  mov     [rax], rdx
0x140013d3c  mov     [rax+8], rcx
0x140013d40  mov     [rcx], rax
0x140013d43  mov     cs:qword_140009398, rax
0x140013d4a  lea     rcx, qword_140009388
0x140013d51  call    FILockExclusiveRelease
0x140013d56  jmp     loc_140013C1D
0x140013d5b  mov     edi, 0C0000225h
0x140013d60  jmp     loc_140013C50
```
