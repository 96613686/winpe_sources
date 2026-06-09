# FIVolumeAddPagefile

- ea: `0x14000e5a0`
- end: `0x14000e7cc`
- name: `FIVolumeAddPagefile`
- size: `556`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x14000deb0`
- `0x140016bc0`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x14000d1b8`
- `0x14000e5a0`
- `0x140013bc0`
- `0x140013fb0`
- `0x140014520`
- `0x140014730`
- `0x140016494`

## import_xrefs

- `FLTMGR!FltReleaseFileNameInformation` at `0x14000e7ac`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000e7ac`
- `FLTMGR!FltGetFileNameInformation` at `0x14000e60a`
- `FLTMGR!FltGetFileNameInformation` at `0x14000e60a`
- `FLTMGR!FltReleaseContext` at `0x14000e777`
- `FLTMGR!FltReleaseContext` at `0x14000e797`
- `FLTMGR!FltReleaseContext` at `0x14000e777`
- `FLTMGR!FltReleaseContext` at `0x14000e797`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14000e67c`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14000e67c`

## pseudocode

```c
__int64 __fastcall FIVolumeAddPagefile(int a1, __int64 a2, struct _FLT_CALLBACK_DATA *a3)
{
  PFLT_CONTEXT v6; // rdi
  int v7; // r12d
  int v8; // eax
  volatile signed __int32 *v9; // rsi
  NTSTATUS v10; // ebx
  FLT_FILE_NAME_OPTIONS v11; // eax
  struct _FILE_OBJECT *v12; // rdi
  struct _FLT_INSTANCE *v13; // rbx
  FLT_FILE_NAME_OPTIONS v14; // eax
  _DWORD *v15; // rbx
  __int64 v16; // rax
  PFLT_CONTEXT *v17; // rcx
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+20h] [rbp-58h] BYREF
  PFLT_CONTEXT Context; // [rsp+28h] [rbp-50h] BYREF
  PFLT_CONTEXT v21; // [rsp+30h] [rbp-48h] BYREF
  _DWORD v22[2]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v23; // [rsp+40h] [rbp-38h]
  PFLT_CONTEXT v24; // [rsp+48h] [rbp-30h]
  int v25; // [rsp+50h] [rbp-28h]
  int v26; // [rsp+54h] [rbp-24h]
  char *v27; // [rsp+58h] [rbp-20h]
  __int64 v28; // [rsp+60h] [rbp-18h]
  int v29; // [rsp+D8h] [rbp+60h] BYREF

  v26 = 0;
  v29 = 0;
  v21 = 0;
  Context = 0;
  FileNameInformation = 0;
  v6 = 0;
  v7 = 0;
  v8 = FIVolumeGet(a2, &v21, 0);
  v9 = (volatile signed __int32 *)v21;
  v10 = v8;
  if ( v8 < 0 )
    goto LABEL_22;
  if ( !a1 )
  {
    v11 = FIGetFileNameOptions(*(_QWORD *)(a2 + 16));
    FltGetFileNameInformation(a3, v11, &FileNameInformation);
LABEL_12:
    if ( _InterlockedIncrement(v9 + 32) > 32 )
    {
      _InterlockedDecrement(v9 + 32);
      v10 = -1073741673;
      goto LABEL_22;
    }
    v7 = 1;
    v10 = FIStreamCreate(&Context);
    if ( v10 >= 0 )
    {
      v15 = Context;
      v16 = *(_QWORD *)(a2 + 16);
      v23 = 0;
      v22[1] = 0;
      v24 = Context;
      *((_QWORD *)Context + 4) = *(_QWORD *)(v16 + 24);
      v15[14] |= 0x14u;
      *((_QWORD *)v15 + 6) = FileNameInformation;
      FileNameInformation = 0;
      *((_QWORD *)v15 + 3) = v9;
      v27 = (char *)(v15 + 12);
      v22[0] = dword_140009A74;
      v25 = 2;
      v28 = 0;
      FIStreamLog((__int64)v22);
      FILockExclusiveAcquire((__int64)(v9 + 6));
      v17 = (PFLT_CONTEXT *)*((_QWORD *)v9 + 5);
      if ( *v17 != v9 + 8 )
        __fastfail(3u);
      *((_QWORD *)v15 + 1) = v17;
      *(_QWORD *)v15 = v9 + 8;
      *v17 = v15;
      *((_QWORD *)v9 + 5) = v15;
      FILockExclusiveRelease((__int64)(v9 + 6));
      v7 = 0;
      v10 = 0;
      goto LABEL_22;
    }
    v6 = Context;
    goto LABEL_20;
  }
  if ( a1 != 1 )
  {
    v10 = -1073741595;
LABEL_20:
    if ( v6 )
      FltReleaseContext(v6);
    goto LABEL_22;
  }
  if ( *((WCHAR **)v21 + 13) == FIUnknown )
    FIVolumeQueueQuery(a2, (__int64)v21);
  if ( (unsigned int)FIAddPagefile(*(_QWORD *)(a2 + 16), &v29) )
  {
    v12 = *(struct _FILE_OBJECT **)(a2 + 16);
    v13 = *(struct _FLT_INSTANCE **)(a2 + 8);
    v14 = FIGetFileNameOptions(v12);
    FltGetFileNameInformationUnsafe(v12, v13, v14, &FileNameInformation);
    goto LABEL_12;
  }
  v10 = -1073741673;
  if ( v29 != -1 )
    v10 = 0;
LABEL_22:
  if ( v9 )
  {
    if ( v7 )
      _InterlockedDecrement(v9 + 32);
    FltReleaseContext((PFLT_CONTEXT)v9);
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000e5a0  push    rbp
0x14000e5a2  push    rbx
0x14000e5a3  push    rsi
0x14000e5a4  push    rdi
0x14000e5a5  push    r12
0x14000e5a7  push    r13
0x14000e5a9  push    r14
0x14000e5ab  push    r15
0x14000e5ad  mov     rbp, rsp
0x14000e5b0  sub     rsp, 78h
0x14000e5b4  xor     eax, eax
0x14000e5b6  mov     r14, rdx
0x14000e5b9  mov     r13, r8
0x14000e5bc  mov     [rbp+var_24], eax
0x14000e5bf  mov     r15d, ecx
0x14000e5c2  mov     [rbp+arg_18], eax
0x14000e5c5  mov     rcx, r14
0x14000e5c8  mov     [rbp+var_48], rax
0x14000e5cc  xor     r8d, r8d
0x14000e5cf  mov     [rbp+Context], rax
0x14000e5d3  lea     rdx, [rbp+var_48]
0x14000e5d7  mov     [rbp+FileNameInformation], rax
0x14000e5db  mov     edi, eax
0x14000e5dd  mov     r12d, eax
0x14000e5e0  call    FIVolumeGet
0x14000e5e5  mov     rsi, [rbp+var_48]
0x14000e5e9  mov     ebx, eax
0x14000e5eb  test    eax, eax
0x14000e5ed  js      loc_14000E783
0x14000e5f3  test    r15d, r15d
0x14000e5f6  jnz     short loc_14000E618
0x14000e5f8  mov     rcx, [r14+10h]
0x14000e5fc  call    FIGetFileNameOptions
0x14000e601  mov     edx, eax; NameOptions
0x14000e603  lea     r8, [rbp+FileNameInformation]; FileNameInformation
0x14000e607  mov     rcx, r13; CallbackData
0x14000e60a  call    cs:__imp_FltGetFileNameInformation
0x14000e611  nop     dword ptr [rax+rax+00h]
0x14000e616  jmp     short loc_14000E688
0x14000e618  cmp     r15d, 1
0x14000e61c  jnz     loc_14000E76A
0x14000e622  mov     rax, [rsi+68h]
0x14000e626  lea     rcx, FIUnknown; "\\FI_UNKNOWN"
0x14000e62d  cmp     rax, rcx
0x14000e630  jnz     short loc_14000E63D
0x14000e632  mov     rdx, rsi
0x14000e635  mov     rcx, r14
0x14000e638  call    FIVolumeQueueQuery
0x14000e63d  mov     rcx, [r14+10h]
0x14000e641  lea     rdx, [rbp+arg_18]
0x14000e645  call    FIAddPagefile
0x14000e64a  test    eax, eax
0x14000e64c  jnz     short loc_14000E65F
0x14000e64e  cmp     [rbp+arg_18], 0FFFFFFFFh
0x14000e652  mov     ebx, 0C0000097h
0x14000e657  cmovnz  ebx, eax
0x14000e65a  jmp     loc_14000E783
0x14000e65f  mov     rdi, [r14+10h]
0x14000e663  mov     rbx, [r14+8]
0x14000e667  mov     rcx, rdi
0x14000e66a  call    FIGetFileNameOptions
0x14000e66f  mov     r8d, eax; NameOptions
0x14000e672  lea     r9, [rbp+FileNameInformation]; FileNameInformation
0x14000e676  mov     rdx, rbx; Instance
0x14000e679  mov     rcx, rdi; FileObject
0x14000e67c  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14000e683  nop     dword ptr [rax+rax+00h]
0x14000e688  mov     eax, 1
0x14000e68d  lock xadd [rsi+80h], eax
0x14000e695  inc     eax
0x14000e697  cmp     eax, 20h ; ' '
0x14000e69a  jle     short loc_14000E6AD
0x14000e69c  lock dec dword ptr [rsi+80h]
0x14000e6a3  mov     ebx, 0C0000097h
0x14000e6a8  jmp     loc_14000E783
0x14000e6ad  lea     rcx, [rbp+Context]
0x14000e6b1  mov     r12d, 1
0x14000e6b7  call    FIStreamCreate
0x14000e6bc  mov     ebx, eax
0x14000e6be  test    eax, eax
0x14000e6c0  js      loc_14000E764
0x14000e6c6  mov     rbx, [rbp+Context]
0x14000e6ca  mov     rax, [r14+10h]
0x14000e6ce  mov     [rbp+var_38], 0
0x14000e6d6  mov     [rbp+var_3C], 0
0x14000e6dd  mov     [rbp+var_30], rbx
0x14000e6e1  mov     rcx, [rax+18h]
0x14000e6e5  mov     [rbx+20h], rcx
0x14000e6e9  lea     rcx, [rbx+30h]
0x14000e6ed  or      dword ptr [rbx+38h], 14h
0x14000e6f1  mov     rax, [rbp+FileNameInformation]
0x14000e6f5  mov     [rcx], rax
0x14000e6f8  mov     [rbp+FileNameInformation], 0
0x14000e700  mov     [rbx+18h], rsi
0x14000e704  mov     eax, cs:dword_140009A74
0x14000e70a  mov     [rbp+var_20], rcx
0x14000e70e  lea     rcx, [rbp+var_40]
0x14000e712  mov     [rbp+var_40], eax
0x14000e715  mov     [rbp+var_28], 2
0x14000e71c  mov     [rbp+var_18], 0
0x14000e724  call    FIStreamLog
0x14000e729  lea     rcx, [rsi+18h]
0x14000e72d  call    FILockExclusiveAcquire
0x14000e732  lea     rax, [rsi+20h]
0x14000e736  mov     rcx, [rax+8]
0x14000e73a  cmp     [rcx], rax
0x14000e73d  jz      short loc_14000E746
0x14000e73f  lea     ecx, [r12+2]
0x14000e744  int     29h; Win8: RtlFailFast(ecx)
0x14000e746  mov     [rbx+8], rcx
0x14000e74a  mov     [rbx], rax
0x14000e74d  mov     [rcx], rbx
0x14000e750  lea     rcx, [rsi+18h]
0x14000e754  mov     [rax+8], rbx
0x14000e758  call    FILockExclusiveRelease
0x14000e75d  xor     r12d, r12d
0x14000e760  xor     ebx, ebx
0x14000e762  jmp     short loc_14000E783
0x14000e764  mov     rdi, [rbp+Context]
0x14000e768  jmp     short loc_14000E76F
0x14000e76a  mov     ebx, 0C00000E5h
0x14000e76f  test    rdi, rdi
0x14000e772  jz      short loc_14000E783
0x14000e774  mov     rcx, rdi; Context
0x14000e777  call    cs:__imp_FltReleaseContext
0x14000e77e  nop     dword ptr [rax+rax+00h]
0x14000e783  test    rsi, rsi
0x14000e786  jz      short loc_14000E7A3
0x14000e788  test    r12d, r12d
0x14000e78b  jz      short loc_14000E794
0x14000e78d  lock dec dword ptr [rsi+80h]
0x14000e794  mov     rcx, rsi; Context
0x14000e797  call    cs:__imp_FltReleaseContext
0x14000e79e  nop     dword ptr [rax+rax+00h]
0x14000e7a3  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x14000e7a7  test    rcx, rcx
0x14000e7aa  jz      short loc_14000E7B8
0x14000e7ac  call    cs:__imp_FltReleaseFileNameInformation
0x14000e7b3  nop     dword ptr [rax+rax+00h]
0x14000e7b8  mov     eax, ebx
0x14000e7ba  add     rsp, 78h
0x14000e7be  pop     r15
0x14000e7c0  pop     r14
0x14000e7c2  pop     r13
0x14000e7c4  pop     r12
0x14000e7c6  pop     rdi
0x14000e7c7  pop     rsi
0x14000e7c8  pop     rbx
0x14000e7c9  pop     rbp
0x14000e7ca  retn
```
