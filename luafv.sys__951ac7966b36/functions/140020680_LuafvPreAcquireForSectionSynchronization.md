# LuafvPreAcquireForSectionSynchronization

- ea: `0x140020680`
- end: `0x14002088f`
- name: `LuafvPreAcquireForSectionSynchronization`
- size: `527`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140001440`
- `0x140020680`

## import_xrefs

- `ntoskrnl!ZwCreateSection` at `0x14002080f`
- `ntoskrnl!ZwCreateSection` at `0x14002080f`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140020752`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14002087e`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140020752`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14002087e`
- `FLTMGR!FltReleasePushLockEx` at `0x140020823`
- `FLTMGR!FltReleasePushLockEx` at `0x140020823`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140020799`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140020799`

## pseudocode

```c
__int64 __fastcall LuafvPreAcquireForSectionSynchronization(PFLT_CALLBACK_DATA Data, __int64 a2)
{
  __int64 v2; // r9
  __int64 result; // rax
  __int64 v6; // rbp
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  struct _FILE_OBJECT *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rdi
  NTSTATUS v13; // r12d
  struct _FILE_OBJECT *v14; // rax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-58h] BYREF
  union _LARGE_INTEGER MaximumSize; // [rsp+A8h] [rbp+10h] BYREF

  v2 = *(_QWORD *)(a2 + 32);
  MaximumSize.QuadPart = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !v2 )
    return 1;
  v6 = *(_QWORD *)(v2 + 24);
  if ( !v6 || *(_WORD *)v6 != 30310 )
    return 1;
  Iopb = Data->Iopb;
  if ( Iopb->Parameters.Read.Length != 1 )
  {
    v14 = *(struct _FILE_OBJECT **)(v6 + 240);
    if ( !v14 )
      v14 = *(struct _FILE_OBJECT **)(v6 + 216);
    Iopb->TargetFileObject = v14;
    FltSetCallbackDataDirty(Data);
    return 1;
  }
  if ( (Iopb->Parameters.AcquireForSectionSynchronization.PageProtection & 0x44) != 0 )
    return LuafvPreWrite(Data);
  v11 = 1;
  if ( **(_QWORD **)(v2 + 40) )
    goto LABEL_8;
  v12 = *(_QWORD *)(v6 + 192);
  v13 = 0;
  FltAcquirePushLockExclusiveEx(v12 + 64, 0);
  if ( !*(_QWORD *)(v12 + 112) )
  {
    ObjectAttributes.Length = 48;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = 0;
    MaximumSize.QuadPart = 1;
    v13 = ZwCreateSection(
            (PHANDLE)(v12 + 112),
            5u,
            &ObjectAttributes,
            &MaximumSize,
            2u,
            0x8000000u,
            *(HANDLE *)(v6 + 208));
  }
  FltReleasePushLockEx(v12 + 64, 0);
  if ( v13 >= 0 )
  {
LABEL_8:
    v8 = *(_QWORD *)(a2 + 32);
    if ( v8 )
    {
      v9 = *(_QWORD *)(v8 + 24);
      if ( v9 )
      {
        if ( *(_WORD *)v9 == 30310 )
        {
          v10 = *(struct _FILE_OBJECT **)(v9 + 240);
          if ( v10 )
          {
            Data->Iopb->TargetFileObject = v10;
            FltSetCallbackDataDirty(Data);
          }
          else
          {
            v11 = 4;
            Data->IoStatus.Status = *(_DWORD *)(v9 + 248);
            Data->IoStatus.Information = 0;
          }
        }
      }
    }
    return v11;
  }
  else
  {
    Data->IoStatus.Status = -1073741670;
    result = 4;
    Data->IoStatus.Information = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140020680  push    rbx
0x140020682  push    rbp
0x140020683  push    rsi
0x140020684  push    r13
0x140020686  push    r14
0x140020688  sub     rsp, 70h
0x14002068c  mov     r9, [rdx+20h]
0x140020690  xorps   xmm0, xmm0
0x140020693  xor     r13d, r13d
0x140020696  xor     eax, eax
0x140020698  mov     qword ptr [rsp+98h+MaximumSize], r13
0x1400206a0  mov     rsi, rdx
0x1400206a3  mov     r14, rcx
0x1400206a6  movups  xmmword ptr [rsp+98h+ObjectAttributes.ObjectName], xmm0
0x1400206ab  movups  xmmword ptr [rsp+98h+ObjectAttributes+1Ch], xmm0
0x1400206b0  movups  xmmword ptr [rsp+98h+ObjectAttributes.Length], xmm0
0x1400206b5  test    r9, r9
0x1400206b8  jnz     short loc_1400206CC
0x1400206ba  mov     eax, 1
0x1400206bf  add     rsp, 70h
0x1400206c3  pop     r14
0x1400206c5  pop     r13
0x1400206c7  pop     rsi
0x1400206c8  pop     rbp
0x1400206c9  pop     rbx
0x1400206ca  retn
0x1400206cc  mov     rbp, [r9+18h]
0x1400206d0  test    rbp, rbp
0x1400206d3  jz      short loc_1400206BA
0x1400206d5  mov     edx, 7666h
0x1400206da  cmp     [rbp+0], dx
0x1400206de  jnz     short loc_1400206BA
0x1400206e0  mov     rcx, [rcx+10h]
0x1400206e4  cmp     dword ptr [rcx+18h], 1
0x1400206e8  jnz     loc_140020864
0x1400206ee  mov     eax, [rcx+1Ch]
0x1400206f1  test    al, 44h
0x1400206f3  jz      short loc_140020760
0x1400206f5  mov     rdx, rsi
0x1400206f8  mov     rcx, r14; Data
0x1400206fb  call    LuafvPreWrite
0x140020700  jmp     short loc_1400206BF
0x140020702  mov     rax, [rsi+20h]
0x140020706  test    rax, rax
0x140020709  jz      short loc_140020738
0x14002070b  mov     rax, [rax+18h]
0x14002070f  test    rax, rax
0x140020712  jz      short loc_140020738
0x140020714  cmp     [rax], dx
0x140020717  jnz     short loc_140020738
0x140020719  mov     rcx, [rax+0F0h]
0x140020720  test    rcx, rcx
0x140020723  jnz     short loc_140020747
0x140020725  mov     eax, [rax+0F8h]
0x14002072b  mov     ebx, 4
0x140020730  mov     [r14+18h], eax
0x140020734  mov     [r14+20h], r13
0x140020738  mov     eax, ebx
0x14002073a  add     rsp, 70h
0x14002073e  pop     r14
0x140020740  pop     r13
0x140020742  pop     rsi
0x140020743  pop     rbp
0x140020744  pop     rbx
0x140020745  retn
0x140020747  mov     rax, [r14+10h]
0x14002074b  mov     [rax+8], rcx
0x14002074f  mov     rcx, r14; Data
0x140020752  call    cs:__imp_FltSetCallbackDataDirty
0x140020759  nop     dword ptr [rax+rax+00h]
0x14002075e  jmp     short loc_140020738
0x140020760  mov     rax, [r9+28h]
0x140020764  mov     ebx, 1
0x140020769  cmp     [rax], r13
0x14002076c  jnz     short loc_140020702
0x14002076e  mov     [rsp+98h+arg_0], rdi
0x140020776  xor     edx, edx
0x140020778  mov     rdi, [rbp+0C0h]
0x14002077f  mov     [rsp+98h+arg_10], r12
0x140020787  mov     r12d, r13d
0x14002078a  mov     [rsp+98h+arg_18], r15
0x140020792  lea     r15, [rdi+40h]
0x140020796  mov     rcx, r15
0x140020799  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400207a0  nop     dword ptr [rax+rax+00h]
0x1400207a5  lea     rcx, [rdi+70h]; SectionHandle
0x1400207a9  mov     rdi, [rsp+98h+arg_0]
0x1400207b1  cmp     [rcx], r12
0x1400207b4  jnz     short loc_14002081E
0x1400207b6  xorps   xmm0, xmm0
0x1400207b9  mov     [rsp+98h+ObjectAttributes.Length], 30h ; '0'
0x1400207c1  movdqu  xmmword ptr [rsp+98h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400207c7  mov     [rsp+98h+ObjectAttributes.RootDirectory], r13
0x1400207cc  lea     r9, [rsp+98h+MaximumSize]; MaximumSize
0x1400207d4  mov     [rsp+98h+ObjectAttributes.Attributes], 240h
0x1400207dc  lea     r8, [rsp+98h+ObjectAttributes]; ObjectAttributes
0x1400207e1  mov     [rsp+98h+ObjectAttributes.ObjectName], r13
0x1400207e6  mov     edx, 5; DesiredAccess
0x1400207eb  mov     qword ptr [rsp+98h+MaximumSize], rbx
0x1400207f3  mov     rax, [rbp+0D0h]
0x1400207fa  mov     [rsp+98h+FileHandle], rax; FileHandle
0x1400207ff  mov     [rsp+98h+AllocationAttributes], 8000000h; AllocationAttributes
0x140020807  mov     [rsp+98h+SectionPageProtection], 2; SectionPageProtection
0x14002080f  call    cs:__imp_ZwCreateSection
0x140020816  nop     dword ptr [rax+rax+00h]
0x14002081b  mov     r12d, eax
0x14002081e  xor     edx, edx
0x140020820  mov     rcx, r15
0x140020823  call    cs:__imp_FltReleasePushLockEx
0x14002082a  nop     dword ptr [rax+rax+00h]
0x14002082f  mov     r15, [rsp+98h+arg_18]
0x140020837  test    r12d, r12d
0x14002083a  mov     r12, [rsp+98h+arg_10]
0x140020842  jns     short loc_14002085A
0x140020844  mov     dword ptr [r14+18h], 0C000009Ah
0x14002084c  mov     eax, 4
0x140020851  mov     [r14+20h], r13
0x140020855  jmp     loc_1400206BF
0x14002085a  mov     edx, 7666h
0x14002085f  jmp     loc_140020702
0x140020864  mov     rax, [rbp+0F0h]
0x14002086b  test    rax, rax
0x14002086e  jnz     short loc_140020877
0x140020870  mov     rax, [rbp+0D8h]
0x140020877  mov     [rcx+8], rax
0x14002087b  mov     rcx, r14; Data
0x14002087e  call    cs:__imp_FltSetCallbackDataDirty
0x140020885  nop     dword ptr [rax+rax+00h]
0x14002088a  jmp     loc_1400206BA
```
