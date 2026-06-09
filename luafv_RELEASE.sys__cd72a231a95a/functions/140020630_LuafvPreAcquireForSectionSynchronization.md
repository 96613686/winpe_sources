# LuafvPreAcquireForSectionSynchronization

- ea: `0x140020630`
- end: `0x14002083f`
- name: `LuafvPreAcquireForSectionSynchronization`
- size: `527`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140001440`
- `0x140020630`

## import_xrefs

- `ntoskrnl!ZwCreateSection` at `0x1400207bf`
- `ntoskrnl!ZwCreateSection` at `0x1400207bf`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140020702`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14002082e`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140020702`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14002082e`
- `FLTMGR!FltReleasePushLockEx` at `0x1400207d3`
- `FLTMGR!FltReleasePushLockEx` at `0x1400207d3`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140020749`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140020749`

## pseudocode

```c
__int64 __fastcall LuafvPreAcquireForSectionSynchronization(PFLT_CALLBACK_DATA Data, __int64 a2, _QWORD *a3)
{
  __int64 v3; // r9
  __int64 result; // rax
  __int64 v7; // rbp
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  struct _FILE_OBJECT *v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rdi
  NTSTATUS v14; // r12d
  struct _FILE_OBJECT *v15; // rax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-58h] BYREF
  union _LARGE_INTEGER MaximumSize; // [rsp+A8h] [rbp+10h] BYREF

  v3 = *(_QWORD *)(a2 + 32);
  MaximumSize.QuadPart = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !v3 )
    return 1;
  v7 = *(_QWORD *)(v3 + 24);
  if ( !v7 || *(_WORD *)v7 != 30310 )
    return 1;
  Iopb = Data->Iopb;
  if ( Iopb->Parameters.Read.Length != 1 )
  {
    v15 = *(struct _FILE_OBJECT **)(v7 + 240);
    if ( !v15 )
      v15 = *(struct _FILE_OBJECT **)(v7 + 216);
    Iopb->TargetFileObject = v15;
    FltSetCallbackDataDirty(Data);
    return 1;
  }
  if ( (Iopb->Parameters.AcquireForSectionSynchronization.PageProtection & 0x44) != 0 )
    return LuafvPreWrite(Data, a2, a3);
  v12 = 1;
  if ( **(_QWORD **)(v3 + 40) )
    goto LABEL_8;
  v13 = *(_QWORD *)(v7 + 192);
  v14 = 0;
  FltAcquirePushLockExclusiveEx(v13 + 64, 0);
  if ( !*(_QWORD *)(v13 + 112) )
  {
    ObjectAttributes.Length = 48;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = 0;
    MaximumSize.QuadPart = 1;
    v14 = ZwCreateSection(
            (PHANDLE)(v13 + 112),
            5u,
            &ObjectAttributes,
            &MaximumSize,
            2u,
            0x8000000u,
            *(HANDLE *)(v7 + 208));
  }
  FltReleasePushLockEx(v13 + 64, 0);
  if ( v14 >= 0 )
  {
LABEL_8:
    v9 = *(_QWORD *)(a2 + 32);
    if ( v9 )
    {
      v10 = *(_QWORD *)(v9 + 24);
      if ( v10 )
      {
        if ( *(_WORD *)v10 == 30310 )
        {
          v11 = *(struct _FILE_OBJECT **)(v10 + 240);
          if ( v11 )
          {
            Data->Iopb->TargetFileObject = v11;
            FltSetCallbackDataDirty(Data);
          }
          else
          {
            v12 = 4;
            Data->IoStatus.Status = *(_DWORD *)(v10 + 248);
            Data->IoStatus.Information = 0;
          }
        }
      }
    }
    return v12;
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
0x140020630  push    rbx
0x140020632  push    rbp
0x140020633  push    rsi
0x140020634  push    r13
0x140020636  push    r14
0x140020638  sub     rsp, 70h
0x14002063c  mov     r9, [rdx+20h]
0x140020640  xorps   xmm0, xmm0
0x140020643  xor     r13d, r13d
0x140020646  xor     eax, eax
0x140020648  mov     qword ptr [rsp+98h+MaximumSize], r13
0x140020650  mov     rsi, rdx
0x140020653  mov     r14, rcx
0x140020656  movups  xmmword ptr [rsp+98h+ObjectAttributes.ObjectName], xmm0
0x14002065b  movups  xmmword ptr [rsp+98h+ObjectAttributes+1Ch], xmm0
0x140020660  movups  xmmword ptr [rsp+98h+ObjectAttributes.Length], xmm0
0x140020665  test    r9, r9
0x140020668  jnz     short loc_14002067C
0x14002066a  mov     eax, 1
0x14002066f  add     rsp, 70h
0x140020673  pop     r14
0x140020675  pop     r13
0x140020677  pop     rsi
0x140020678  pop     rbp
0x140020679  pop     rbx
0x14002067a  retn
0x14002067c  mov     rbp, [r9+18h]
0x140020680  test    rbp, rbp
0x140020683  jz      short loc_14002066A
0x140020685  mov     edx, 7666h
0x14002068a  cmp     [rbp+0], dx
0x14002068e  jnz     short loc_14002066A
0x140020690  mov     rcx, [rcx+10h]
0x140020694  cmp     dword ptr [rcx+18h], 1
0x140020698  jnz     loc_140020814
0x14002069e  mov     eax, [rcx+1Ch]
0x1400206a1  test    al, 44h
0x1400206a3  jz      short loc_140020710
0x1400206a5  mov     rdx, rsi
0x1400206a8  mov     rcx, r14; Data
0x1400206ab  call    LuafvPreWrite
0x1400206b0  jmp     short loc_14002066F
0x1400206b2  mov     rax, [rsi+20h]
0x1400206b6  test    rax, rax
0x1400206b9  jz      short loc_1400206E8
0x1400206bb  mov     rax, [rax+18h]
0x1400206bf  test    rax, rax
0x1400206c2  jz      short loc_1400206E8
0x1400206c4  cmp     [rax], dx
0x1400206c7  jnz     short loc_1400206E8
0x1400206c9  mov     rcx, [rax+0F0h]
0x1400206d0  test    rcx, rcx
0x1400206d3  jnz     short loc_1400206F7
0x1400206d5  mov     eax, [rax+0F8h]
0x1400206db  mov     ebx, 4
0x1400206e0  mov     [r14+18h], eax
0x1400206e4  mov     [r14+20h], r13
0x1400206e8  mov     eax, ebx
0x1400206ea  add     rsp, 70h
0x1400206ee  pop     r14
0x1400206f0  pop     r13
0x1400206f2  pop     rsi
0x1400206f3  pop     rbp
0x1400206f4  pop     rbx
0x1400206f5  retn
0x1400206f7  mov     rax, [r14+10h]
0x1400206fb  mov     [rax+8], rcx
0x1400206ff  mov     rcx, r14; Data
0x140020702  call    cs:__imp_FltSetCallbackDataDirty
0x140020709  nop     dword ptr [rax+rax+00h]
0x14002070e  jmp     short loc_1400206E8
0x140020710  mov     rax, [r9+28h]
0x140020714  mov     ebx, 1
0x140020719  cmp     [rax], r13
0x14002071c  jnz     short loc_1400206B2
0x14002071e  mov     [rsp+98h+arg_0], rdi
0x140020726  xor     edx, edx
0x140020728  mov     rdi, [rbp+0C0h]
0x14002072f  mov     [rsp+98h+arg_10], r12
0x140020737  mov     r12d, r13d
0x14002073a  mov     [rsp+98h+arg_18], r15
0x140020742  lea     r15, [rdi+40h]
0x140020746  mov     rcx, r15
0x140020749  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140020750  nop     dword ptr [rax+rax+00h]
0x140020755  lea     rcx, [rdi+70h]; SectionHandle
0x140020759  mov     rdi, [rsp+98h+arg_0]
0x140020761  cmp     [rcx], r12
0x140020764  jnz     short loc_1400207CE
0x140020766  xorps   xmm0, xmm0
0x140020769  mov     [rsp+98h+ObjectAttributes.Length], 30h ; '0'
0x140020771  movdqu  xmmword ptr [rsp+98h+ObjectAttributes.SecurityDescriptor], xmm0
0x140020777  mov     [rsp+98h+ObjectAttributes.RootDirectory], r13
0x14002077c  lea     r9, [rsp+98h+MaximumSize]; MaximumSize
0x140020784  mov     [rsp+98h+ObjectAttributes.Attributes], 240h
0x14002078c  lea     r8, [rsp+98h+ObjectAttributes]; ObjectAttributes
0x140020791  mov     [rsp+98h+ObjectAttributes.ObjectName], r13
0x140020796  mov     edx, 5; DesiredAccess
0x14002079b  mov     qword ptr [rsp+98h+MaximumSize], rbx
0x1400207a3  mov     rax, [rbp+0D0h]
0x1400207aa  mov     [rsp+98h+FileHandle], rax; FileHandle
0x1400207af  mov     [rsp+98h+AllocationAttributes], 8000000h; AllocationAttributes
0x1400207b7  mov     [rsp+98h+SectionPageProtection], 2; SectionPageProtection
0x1400207bf  call    cs:__imp_ZwCreateSection
0x1400207c6  nop     dword ptr [rax+rax+00h]
0x1400207cb  mov     r12d, eax
0x1400207ce  xor     edx, edx
0x1400207d0  mov     rcx, r15
0x1400207d3  call    cs:__imp_FltReleasePushLockEx
0x1400207da  nop     dword ptr [rax+rax+00h]
0x1400207df  mov     r15, [rsp+98h+arg_18]
0x1400207e7  test    r12d, r12d
0x1400207ea  mov     r12, [rsp+98h+arg_10]
0x1400207f2  jns     short loc_14002080A
0x1400207f4  mov     dword ptr [r14+18h], 0C000009Ah
0x1400207fc  mov     eax, 4
0x140020801  mov     [r14+20h], r13
0x140020805  jmp     loc_14002066F
0x14002080a  mov     edx, 7666h
0x14002080f  jmp     loc_1400206B2
0x140020814  mov     rax, [rbp+0F0h]
0x14002081b  test    rax, rax
0x14002081e  jnz     short loc_140020827
0x140020820  mov     rax, [rbp+0D8h]
0x140020827  mov     [rcx+8], rax
0x14002082b  mov     rcx, r14; Data
0x14002082e  call    cs:__imp_FltSetCallbackDataDirty
0x140020835  nop     dword ptr [rax+rax+00h]
0x14002083a  jmp     loc_14002066A
```
