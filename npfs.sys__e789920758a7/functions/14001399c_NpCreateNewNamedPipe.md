# NpCreateNewNamedPipe

- ea: `0x14001399c`
- end: `0x140013d5d`
- name: `NpCreateNewNamedPipe`
- size: `961`
- prototype: `__int64 __fastcall(__int64, int, __int64, _WORD *, int, struct _SECURITY_SUBJECT_CONTEXT *, int, __int16, __int64, PEPROCESS Process, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140011aa0`

## callees

- `0x14000b030`
- `0x14000e830`
- `0x1400107c0`
- `0x140010d18`
- `0x1400111c0`
- `0x14001399c`
- `0x140013ec0`
- `0x140015878`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140013b67`
- `ntoskrnl!ExAllocatePool2` at `0x140013b67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013c97`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013c97`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140013c37`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140013c37`
- `ntoskrnl!SeAssignSecurity` at `0x140013c62`
- `ntoskrnl!SeAssignSecurity` at `0x140013c62`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x140013c83`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x140013c83`
- `ntoskrnl!PsGetProcessId` at `0x140013aa1`
- `ntoskrnl!PsGetProcessId` at `0x140013aa1`
- `ntoskrnl!PsGetProcessSessionId` at `0x140013ab8`
- `ntoskrnl!PsGetProcessSessionId` at `0x140013ab8`

## pseudocode

```c
__int64 __fastcall NpCreateNewNamedPipe(
        __int64 a1,
        int a2,
        __int64 a3,
        _WORD *a4,
        int a5,
        struct _SECURITY_SUBJECT_CONTEXT *a6,
        int a7,
        __int16 a8,
        __int64 a9,
        PEPROCESS Process,
        __int64 a11,
        __int64 a12)
{
  _DWORD *v12; // rdi
  int v13; // r11d
  int v16; // r9d
  NTSTATUS Fcb; // ebx
  __int16 v18; // dx
  int ProcessSessionId; // eax
  char *v20; // rsi
  char *v21; // r15
  char *v22; // rbx
  char *v23; // r12
  char *Pool2; // r14
  int v25; // eax
  char *v26; // rcx
  char **v27; // rax
  char **v28; // rax
  __int64 v29; // rdi
  PACCESS_TOKEN ClientToken; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  NTSTATUS *v36; // rax
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+50h] [rbp-30h] BYREF
  __int64 v38; // [rsp+58h] [rbp-28h] BYREF
  PVOID P; // [rsp+60h] [rbp-20h] BYREF
  __int64 v40; // [rsp+68h] [rbp-18h] BYREF
  HANDLE ProcessId; // [rsp+70h] [rbp-10h]

  v12 = (_DWORD *)a9;
  v13 = (int)a4;
  NewDescriptor = 0;
  v40 = 0;
  P = 0;
  v38 = 0;
  if ( !*(_BYTE *)(a9 + 32) )
    goto LABEL_41;
  v16 = *(_DWORD *)(a9 + 12);
  if ( !v16 || *(__int64 *)(a9 + 24) >= 0 )
    goto LABEL_41;
  if ( a7 == 1 )
  {
    Fcb = -1073741772;
LABEL_42:
    v36 = (NTSTATUS *)a12;
    *(_QWORD *)(a12 + 8) = 0;
    *v36 = Fcb;
    return (unsigned int)Fcb;
  }
  switch ( a8 )
  {
    case 3:
      v18 = 2;
      break;
    case 1:
      v18 = 1;
      break;
    case 2:
      v18 = 0;
      break;
    default:
LABEL_41:
      Fcb = -1073741811;
      goto LABEL_42;
  }
  if ( (*(_DWORD *)a9 & 1) == 0 && *(_DWORD *)(a9 + 4) == 1 )
    goto LABEL_41;
  Fcb = NpCreateFcb(
          a1,
          a2,
          v13,
          v16,
          *(_QWORD *)(a9 + 24),
          v18,
          !(*(_BYTE *)a9 & 1),
          ((*(_DWORD *)a9 >> 1) & 1) == 0,
          (__int64)&P);
  if ( Fcb < 0 )
    goto LABEL_42;
  ProcessId = PsGetProcessId(Process);
  ProcessSessionId = PsGetProcessSessionId(Process);
  v20 = (char *)P;
  LODWORD(a9) = ProcessSessionId;
  v21 = (char *)P + 296;
  v22 = (char *)*((_QWORD *)P + 37);
  v23 = (char *)P + 328;
  while ( v22 != v21 )
  {
    if ( *((_QWORD *)v22 + 2) == 1 )
      goto LABEL_20;
    v22 = *(char **)v22;
  }
  v22 = 0;
LABEL_20:
  if ( P == (PVOID)-328LL )
  {
    Pool2 = (char *)ExAllocatePool2(256, 40, 1950445646);
    if ( !Pool2 )
    {
      Fcb = -1073741670;
LABEL_31:
      v29 = a1;
LABEL_32:
      NpUnlinkFcb(v29, v20, a11);
      NpFreeFcb(v20);
      goto LABEL_42;
    }
  }
  else
  {
    Pool2 = (char *)P + 328;
  }
  v25 = (int)ProcessId;
  *((_QWORD *)Pool2 + 2) = 1;
  *((_DWORD *)Pool2 + 8) = v25;
  *((_QWORD *)Pool2 + 3) = 4;
  if ( v22 )
  {
    v26 = *(char **)v22;
    if ( *(char **)(*(_QWORD *)v22 + 8LL) != v22 || (v27 = (char **)*((_QWORD *)v22 + 1), *v27 != v22) )
LABEL_28:
      __fastfail(3u);
    *v27 = v26;
    *((_QWORD *)v26 + 1) = v27;
    if ( v22 != v23 )
      ExFreePoolWithTag(v22, 0);
  }
  v28 = (char **)*((_QWORD *)v21 + 1);
  if ( *v28 != v21 )
    goto LABEL_28;
  *(_QWORD *)Pool2 = v21;
  *((_QWORD *)Pool2 + 1) = v28;
  *v28 = Pool2;
  *((_QWORD *)v21 + 1) = Pool2;
  Fcb = NpSetAttributeInList(v21, v20 + 368, 2, &a9, 4);
  if ( Fcb < 0 )
    goto LABEL_31;
  Fcb = NpCreateCcb(
          (_DWORD)v20,
          a3,
          (unsigned int)((a5 & 0xF2000003) != 0) + 1,
          v12[1],
          v12[2],
          v12[4],
          v12[5],
          (__int64)&v38);
  if ( Fcb < 0 )
    goto LABEL_31;
  ClientToken = a6[2].ClientToken;
  GenericMapping = IoGetFileObjectGenericMapping();
  Fcb = SeAssignSecurity(0, ClientToken, &NewDescriptor, 0, a6 + 1, GenericMapping, PagedPool);
  if ( Fcb < 0 || (Fcb = ObLogSecurityDescriptor(NewDescriptor, &v40, 1), ExFreePoolWithTag(NewDescriptor, 0), Fcb < 0) )
  {
    v29 = a1;
    --*((_DWORD *)v20 + 62);
    NpDeleteCcb(a1, v38, a11);
    goto LABEL_32;
  }
  v32 = v38;
  *((_QWORD *)v20 + 19) = v40;
  v33 = *(_QWORD *)(v32 + 40);
  *(_DWORD *)(a3 + 80) |= 0x80u;
  *(_QWORD *)(a3 + 24) = v33;
  *(_QWORD *)(a3 + 48) = 1;
  *(_QWORD *)(a3 + 32) = v32 | 3;
  *(_QWORD *)(v32 + 56) = a3;
  if ( *a4 )
    NpCheckForNotifyWithFilter(a1, a11, 1, (_DWORD)a4, 1);
  v34 = a12;
  *(_DWORD *)a12 = 0;
  *(_QWORD *)(v34 + 8) = 2;
  return 0;
}

```

## disassembly

```asm
0x14001399c  mov     [rsp-38h+arg_8], rbx
0x1400139a1  mov     [rsp-38h+arg_18], r9
0x1400139a6  mov     [rsp-38h+arg_0], rcx
0x1400139ab  push    rbp
0x1400139ac  push    rsi
0x1400139ad  push    rdi
0x1400139ae  push    r12
0x1400139b0  push    r13
0x1400139b2  push    r14
0x1400139b4  push    r15
0x1400139b6  mov     rbp, rsp
0x1400139b9  sub     rsp, 80h
0x1400139c0  mov     rdi, [rbp+arg_40]
0x1400139c7  xor     r14d, r14d
0x1400139ca  mov     r11, r9
0x1400139cd  mov     [rbp+NewDescriptor], r14
0x1400139d1  mov     r13, r8
0x1400139d4  mov     [rbp+var_18], r14
0x1400139d8  mov     rbx, rdx
0x1400139db  mov     [rbp+P], r14
0x1400139df  mov     r10, rcx
0x1400139e2  mov     [rbp+var_28], r14
0x1400139e6  cmp     [rdi+20h], r14b
0x1400139ea  jz      loc_140013D2D
0x1400139f0  mov     r9d, [rdi+0Ch]
0x1400139f4  test    r9d, r9d
0x1400139f7  jz      loc_140013D2D
0x1400139fd  cmp     [rdi+18h], r14
0x140013a01  jge     loc_140013D2D
0x140013a07  lea     r8d, [r14+1]
0x140013a0b  cmp     [rbp+arg_30], r8d
0x140013a0f  jnz     short loc_140013A1B
0x140013a11  mov     ebx, 0C0000034h
0x140013a16  jmp     loc_140013D32
0x140013a1b  movzx   eax, [rbp+arg_38]
0x140013a1f  mov     ecx, 2
0x140013a24  lea     edx, [rcx+1]
0x140013a27  cmp     ax, dx
0x140013a2a  jnz     short loc_140013A30
0x140013a2c  mov     edx, ecx
0x140013a2e  jmp     short loc_140013A47
0x140013a30  cmp     ax, r8w
0x140013a34  jnz     short loc_140013A3B
0x140013a36  mov     edx, r8d
0x140013a39  jmp     short loc_140013A47
0x140013a3b  cmp     ax, cx
0x140013a3e  jnz     loc_140013D2D
0x140013a44  mov     edx, r14d
0x140013a47  mov     eax, [rdi]
0x140013a49  mov     ecx, eax
0x140013a4b  and     ecx, r8d
0x140013a4e  jnz     short loc_140013A5A
0x140013a50  cmp     [rdi+4], r8d
0x140013a54  jz      loc_140013D2D
0x140013a5a  xor     ecx, r8d
0x140013a5d  shr     eax, 1
0x140013a5f  not     eax
0x140013a61  and     eax, r8d
0x140013a64  lea     r8, [rbp+P]
0x140013a68  mov     [rsp+80h+var_40], r8
0x140013a6d  mov     r8, r11
0x140013a70  mov     dword ptr [rsp+80h+var_48], eax
0x140013a74  mov     rax, [rdi+18h]
0x140013a78  mov     [rsp+80h+PoolType], ecx
0x140013a7c  mov     rcx, r10
0x140013a7f  mov     dword ptr [rsp+80h+GenericMapping], edx
0x140013a83  mov     rdx, rbx
0x140013a86  mov     [rsp+80h+SubjectContext], rax
0x140013a8b  call    NpCreateFcb
0x140013a90  mov     ebx, eax
0x140013a92  test    eax, eax
0x140013a94  js      loc_140013D32
0x140013a9a  mov     rcx, [rbp+Process]; Process
0x140013aa1  call    cs:__imp_PsGetProcessId
0x140013aa8  nop     dword ptr [rax+rax+00h]
0x140013aad  mov     rcx, [rbp+Process]
0x140013ab4  mov     [rbp+var_10], rax
0x140013ab8  call    cs:__imp_PsGetProcessSessionId
0x140013abf  nop     dword ptr [rax+rax+00h]
0x140013ac4  mov     rsi, [rbp+P]
0x140013ac8  mov     dword ptr [rbp+arg_40], eax
0x140013ace  lea     r15, [rsi+128h]
0x140013ad5  mov     rbx, [r15]
0x140013ad8  lea     r12, [rsi+148h]
0x140013adf  jmp     short loc_140013AEB
0x140013ae1  cmp     qword ptr [rbx+10h], 1
0x140013ae6  jz      short loc_140013AF3
0x140013ae8  mov     rbx, [rbx]
0x140013aeb  cmp     rbx, r15
0x140013aee  jnz     short loc_140013AE1
0x140013af0  mov     rbx, r14
0x140013af3  test    r12, r12
0x140013af6  jz      short loc_140013B57
0x140013af8  mov     r14, r12
0x140013afb  mov     rax, [rbp+var_10]
0x140013aff  mov     qword ptr [r14+10h], 1
0x140013b07  mov     [r14+20h], eax
0x140013b0b  mov     qword ptr [r14+18h], 4
0x140013b13  test    rbx, rbx
0x140013b16  jz      short loc_140013B47
0x140013b18  mov     rcx, [rbx]
0x140013b1b  cmp     [rcx+8], rbx
0x140013b1f  jnz     short loc_140013B50
0x140013b21  mov     rax, [rbx+8]
0x140013b25  cmp     [rax], rbx
0x140013b28  jnz     short loc_140013B50
0x140013b2a  mov     [rax], rcx
0x140013b2d  mov     [rcx+8], rax
0x140013b31  cmp     rbx, r12
0x140013b34  jz      short loc_140013B47
0x140013b36  xor     edx, edx; Tag
0x140013b38  mov     rcx, rbx; P
0x140013b3b  call    cs:__imp_ExFreePoolWithTag
0x140013b42  nop     dword ptr [rax+rax+00h]
0x140013b47  mov     rax, [r15+8]
0x140013b4b  cmp     [rax], r15
0x140013b4e  jz      short loc_140013BA3
0x140013b50  mov     ecx, 3
0x140013b55  int     29h; Win8: RtlFailFast(ecx)
0x140013b57  mov     edx, 28h ; '('
0x140013b5c  mov     ecx, 100h
0x140013b61  mov     r8d, 7441704Eh
0x140013b67  call    cs:__imp_ExAllocatePool2
0x140013b6e  nop     dword ptr [rax+rax+00h]
0x140013b73  mov     r14, rax
0x140013b76  test    rax, rax
0x140013b79  jnz     short loc_140013AFB
0x140013b7b  mov     ebx, 0C000009Ah
0x140013b80  mov     rdi, [rbp+arg_0]
0x140013b84  mov     r8, [rbp+arg_50]
0x140013b8b  mov     rdx, rsi
0x140013b8e  mov     rcx, rdi
0x140013b91  call    NpUnlinkFcb
0x140013b96  mov     rcx, rsi; P
0x140013b99  call    NpFreeFcb
0x140013b9e  jmp     loc_140013D32
0x140013ba3  mov     [r14], r15
0x140013ba6  lea     rdx, [rsi+170h]
0x140013bad  mov     [r14+8], rax
0x140013bb1  lea     r9, [rbp+arg_40]
0x140013bb8  mov     [rax], r14
0x140013bbb  mov     r12d, 2
0x140013bc1  mov     r8d, r12d
0x140013bc4  mov     [r15+8], r14
0x140013bc8  mov     rcx, r15
0x140013bcb  mov     [rsp+80h+SubjectContext], 4
0x140013bd4  call    NpSetAttributeInList
0x140013bd9  xor     r14d, r14d
0x140013bdc  mov     ebx, eax
0x140013bde  test    eax, eax
0x140013be0  js      short loc_140013B80
0x140013be2  test    [rbp+arg_20], 0F2000003h
0x140013be9  lea     rax, [rbp+var_28]
0x140013bed  mov     r9d, [rdi+4]
0x140013bf1  lea     r15d, [r12-1]
0x140013bf6  mov     [rsp+80h+var_48], rax
0x140013bfb  mov     r8d, r14d
0x140013bfe  mov     eax, [rdi+14h]
0x140013c01  setnz   r8b
0x140013c05  mov     [rsp+80h+PoolType], eax
0x140013c09  add     r8d, r15d
0x140013c0c  mov     eax, [rdi+10h]
0x140013c0f  mov     rdx, r13
0x140013c12  mov     dword ptr [rsp+80h+GenericMapping], eax
0x140013c16  mov     rcx, rsi
0x140013c19  mov     eax, [rdi+8]
0x140013c1c  mov     dword ptr [rsp+80h+SubjectContext], eax
0x140013c20  call    NpCreateCcb
0x140013c25  mov     ebx, eax
0x140013c27  test    eax, eax
0x140013c29  js      loc_140013B80
0x140013c2f  mov     rbx, [rbp+arg_28]
0x140013c33  mov     rdi, [rbx+40h]
0x140013c37  call    cs:__imp_IoGetFileObjectGenericMapping
0x140013c3e  nop     dword ptr [rax+rax+00h]
0x140013c43  lea     rcx, [rbx+20h]
0x140013c47  mov     [rsp+80h+PoolType], r15d; PoolType
0x140013c4c  mov     [rsp+80h+GenericMapping], rax; GenericMapping
0x140013c51  lea     r8, [rbp+NewDescriptor]; NewDescriptor
0x140013c55  mov     [rsp+80h+SubjectContext], rcx; SubjectContext
0x140013c5a  xor     r9d, r9d; IsDirectoryObject
0x140013c5d  xor     ecx, ecx; ParentDescriptor
0x140013c5f  mov     rdx, rdi; ExplicitDescriptor
0x140013c62  call    cs:__imp_SeAssignSecurity
0x140013c69  nop     dword ptr [rax+rax+00h]
0x140013c6e  mov     ebx, eax
0x140013c70  test    eax, eax
0x140013c72  js      loc_140013D0B
0x140013c78  mov     rcx, [rbp+NewDescriptor]
0x140013c7c  lea     rdx, [rbp+var_18]
0x140013c80  mov     r8d, r15d
0x140013c83  call    cs:__imp_ObLogSecurityDescriptor
0x140013c8a  nop     dword ptr [rax+rax+00h]
0x140013c8f  mov     rcx, [rbp+NewDescriptor]; P
0x140013c93  xor     edx, edx; Tag
0x140013c95  mov     ebx, eax
0x140013c97  call    cs:__imp_ExFreePoolWithTag
0x140013c9e  nop     dword ptr [rax+rax+00h]
0x140013ca3  test    ebx, ebx
0x140013ca5  js      short loc_140013D0B
0x140013ca7  mov     rcx, [rbp+var_28]
0x140013cab  mov     rax, [rbp+var_18]
0x140013caf  mov     r9, [rbp+arg_18]
0x140013cb3  mov     [rsi+98h], rax
0x140013cba  mov     rax, [rcx+28h]
0x140013cbe  bts     dword ptr [r13+50h], 7
0x140013cc4  mov     [r13+18h], rax
0x140013cc8  mov     rax, rcx
0x140013ccb  or      rax, 3
0x140013ccf  mov     [r13+30h], r15
0x140013cd3  mov     [r13+20h], rax
0x140013cd7  mov     [rcx+38h], r13
0x140013cdb  cmp     [r9], r14w
0x140013cdf  jz      short loc_140013CF9
0x140013ce1  mov     rdx, [rbp+arg_50]
0x140013ce8  mov     r8d, r15d
0x140013ceb  mov     rcx, [rbp+arg_0]
0x140013cef  mov     dword ptr [rsp+80h+SubjectContext], r15d
0x140013cf4  call    NpCheckForNotifyWithFilter
0x140013cf9  mov     rax, [rbp+arg_58]
0x140013d00  mov     [rax], r14d
0x140013d03  mov     [rax+8], r12
0x140013d07  xor     eax, eax
0x140013d09  jmp     short loc_140013D41
0x140013d0b  mov     rdi, [rbp+arg_0]
0x140013d0f  dec     dword ptr [rsi+0F8h]
0x140013d15  mov     rcx, rdi
0x140013d18  mov     r8, [rbp+arg_50]
0x140013d1f  mov     rdx, [rbp+var_28]
0x140013d23  call    NpDeleteCcb
0x140013d28  jmp     loc_140013B84
0x140013d2d  mov     ebx, 0C000000Dh
0x140013d32  mov     rax, [rbp+arg_58]
0x140013d39  mov     [rax+8], r14
0x140013d3d  mov     [rax], ebx
0x140013d3f  mov     eax, ebx
0x140013d41  mov     rbx, [rsp+80h+arg_8]
0x140013d49  add     rsp, 80h
0x140013d50  pop     r15
0x140013d52  pop     r14
0x140013d54  pop     r13
0x140013d56  pop     r12
0x140013d58  pop     rdi
0x140013d59  pop     rsi
0x140013d5a  pop     rbp
0x140013d5b  retn
```
