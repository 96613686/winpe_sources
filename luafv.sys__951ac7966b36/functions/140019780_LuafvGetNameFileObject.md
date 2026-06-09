# LuafvGetNameFileObject

- ea: `0x140019780`
- end: `0x140019a6c`
- name: `LuafvGetNameFileObject`
- size: `748`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, _OWORD *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140018ce8`
- `0x140018f70`
- `0x1400258a0`

## callees

- `0x140001adc`
- `0x140005f30`
- `0x140006080`
- `0x140006380`
- `0x140019780`
- `0x14001b6a0`
- `0x14001dd90`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x140019826`
- `FLTMGR!FltGetStreamHandleContext` at `0x140019826`
- `FLTMGR!FltReleaseContext` at `0x14001989c`
- `FLTMGR!FltReleaseContext` at `0x1400199a1`
- `FLTMGR!FltReleaseContext` at `0x14001989c`
- `FLTMGR!FltReleaseContext` at `0x1400199a1`
- `FLTMGR!FltGetInstanceContext` at `0x14001985d`
- `FLTMGR!FltGetInstanceContext` at `0x14001985d`
- `FLTMGR!FltQueryInformationFile` at `0x140019914`
- `FLTMGR!FltQueryInformationFile` at `0x140019a48`
- `FLTMGR!FltQueryInformationFile` at `0x140019914`
- `FLTMGR!FltQueryInformationFile` at `0x140019a48`

## pseudocode

```c
__int64 __fastcall LuafvGetNameFileObject(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, _OWORD *a3)
{
  _OWORD *v3; // r12
  PVOID FsContext; // r15
  char *v8; // rdi
  struct _FLT_INSTANCE *v9; // rcx
  NTSTATUS InstanceContext; // ebx
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned __int16 v13; // r14
  const void *v14; // rsi
  char *v15; // r8
  ULONG v16; // r9d
  ULONG v17; // edx
  char *Pool; // rax
  char *v19; // r8
  ULONG v20; // r9d
  ULONG v21; // edx
  char *v22; // rax
  ULONG Length; // [rsp+30h] [rbp-69h] BYREF
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-61h] BYREF
  PFLT_CONTEXT v25; // [rsp+40h] [rbp-59h] BYREF
  _OWORD *v26; // [rsp+48h] [rbp-51h]
  __int128 v27; // [rsp+50h] [rbp-49h]
  _BYTE v28[80]; // [rsp+60h] [rbp-39h] BYREF

  v3 = a3;
  v26 = a3;
  v25 = 0;
  Context = 0;
  Length = 0;
  v27 = 0;
  memset(v28, 0, 0x48u);
  if ( !FileObject )
    return 3221225523LL;
  FsContext = FileObject->FsContext;
  v8 = v28;
  if ( FsContext && *(_WORD *)FsContext == 30310 )
  {
    Context = (PFLT_CONTEXT)*((_QWORD *)FsContext + 32);
  }
  else if ( Instance && FltGetStreamHandleContext(Instance, FileObject, &Context) >= 0 )
  {
    FsContext = 0;
  }
  else
  {
    FsContext = 0;
    Context = 0;
  }
  if ( !(unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline() )
  {
    v9 = Instance;
    if ( Context )
      goto LABEL_12;
    Length = 72;
    v15 = v28;
    v16 = 72;
    while ( 1 )
    {
      InstanceContext = FltQueryInformationFile(v9, FileObject, v15, v16, FileNameInformation, &Length);
      if ( InstanceContext != -2147483643 )
        break;
      if ( v8 == v28 )
      {
        v17 = 512;
      }
      else
      {
        LuafvFreePool((__int64)v8);
        v17 = 2 * Length;
      }
      Length = v17;
      Pool = LuafvAllocatePool(1, v17, 1);
      v8 = Pool;
      if ( !Pool )
        goto LABEL_45;
      v16 = Length;
      v15 = Pool;
      v9 = Instance;
    }
LABEL_23:
    if ( InstanceContext < 0 )
    {
LABEL_27:
      if ( v8 != v28 && v8 )
        LuafvFreePool((__int64)v8);
      goto LABEL_30;
    }
    v3 = v26;
    v14 = v8 + 4;
    v13 = *(_WORD *)v8;
LABEL_25:
    Length = v13;
    *((_QWORD *)&v27 + 1) = LuafvAllocatePool(1, v13, 2);
    if ( *((_QWORD *)&v27 + 1) )
    {
      LOWORD(v27) = Length;
      WORD1(v27) = Length;
      memmove(*((void **)&v27 + 1), v14, Length);
      *v3 = v27;
    }
    else
    {
LABEL_45:
      InstanceContext = -1073741670;
    }
    goto LABEL_27;
  }
  if ( !Context || !*(_QWORD *)Context )
  {
    Length = 72;
    v19 = v28;
    v20 = 72;
    while ( 1 )
    {
      InstanceContext = FltQueryInformationFile(Instance, FileObject, v19, v20, FileNameInformation, &Length);
      if ( InstanceContext != -2147483643 )
        goto LABEL_23;
      if ( v8 == v28 )
      {
        v21 = 512;
      }
      else
      {
        LuafvFreePool((__int64)v8);
        v21 = 2 * Length;
      }
      Length = v21;
      v22 = LuafvAllocatePool(1, v21, 1);
      v8 = v22;
      if ( !v22 )
        goto LABEL_45;
      v20 = Length;
      v19 = v22;
    }
  }
  v9 = Instance;
LABEL_12:
  InstanceContext = FltGetInstanceContext(v9, &v25);
  if ( InstanceContext >= 0 )
  {
    v11 = *(_QWORD *)Context;
    if ( (*((_BYTE *)Context + 52) & 2) != 0 )
      v11 += 48;
    v12 = *((_QWORD *)v25 + 3);
    v13 = *(_WORD *)v11 - *(_WORD *)(v12 + 56);
    v14 = (const void *)(*(_QWORD *)(v11 + 8) + *(unsigned __int16 *)(v12 + 56));
    FltReleaseContext(v25);
    goto LABEL_25;
  }
LABEL_30:
  if ( !FsContext )
  {
    if ( Context )
      FltReleaseContext(Context);
  }
  return (unsigned int)InstanceContext;
}

```

## disassembly

```asm
0x140019780  push    rbp
0x140019782  push    rbx
0x140019783  push    rsi
0x140019784  push    rdi
0x140019785  push    r12
0x140019787  push    r14
0x140019789  push    r15
0x14001978b  lea     rbp, [rsp-27h]
0x140019790  sub     rsp, 0C0h
0x140019797  mov     rax, cs:__security_cookie
0x14001979e  xor     rax, rsp
0x1400197a1  mov     [rbp+57h+var_40], rax
0x1400197a5  mov     r12, r8
0x1400197a8  mov     [rbp+57h+var_A8], r8
0x1400197ac  mov     r14, rdx
0x1400197af  mov     [rbp+57h+var_B0], 0
0x1400197b7  mov     rsi, rcx
0x1400197ba  mov     [rbp+57h+Context], 0
0x1400197c2  xorps   xmm0, xmm0
0x1400197c5  mov     [rbp+57h+Length], 0
0x1400197cc  mov     ebx, 48h ; 'H'
0x1400197d1  lea     rcx, [rbp+57h+var_90]; void *
0x1400197d5  mov     r8d, ebx; Size
0x1400197d8  xor     edx, edx; Val
0x1400197da  movups  [rbp+57h+var_A0], xmm0
0x1400197de  call    memset
0x1400197e3  test    r14, r14
0x1400197e6  jnz     short loc_1400197F2
0x1400197e8  mov     eax, 0C0000033h
0x1400197ed  jmp     loc_1400199AF
0x1400197f2  mov     r15, [r14+18h]
0x1400197f6  lea     rdi, [rbp+57h+var_90]
0x1400197fa  test    r15, r15
0x1400197fd  jz      short loc_140019817
0x1400197ff  mov     eax, 7666h
0x140019804  cmp     [r15], ax
0x140019808  jnz     short loc_140019817
0x14001980a  mov     rax, [r15+100h]
0x140019811  mov     [rbp+57h+Context], rax
0x140019815  jmp     short loc_140019842
0x140019817  test    rsi, rsi
0x14001981a  jz      short loc_14001983B
0x14001981c  lea     r8, [rbp+57h+Context]; Context
0x140019820  mov     rdx, r14; FileObject
0x140019823  mov     rcx, rsi; Instance
0x140019826  call    cs:__imp_FltGetStreamHandleContext
0x14001982d  nop     dword ptr [rax+rax+00h]
0x140019832  test    eax, eax
0x140019834  js      short loc_14001983B
0x140019836  xor     r15d, r15d
0x140019839  jmp     short loc_140019842
0x14001983b  xor     r15d, r15d
0x14001983e  mov     [rbp+57h+Context], r15
0x140019842  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x140019847  test    eax, eax
0x140019849  jnz     loc_1400199CE
0x14001984f  cmp     [rbp+57h+Context], 0
0x140019854  mov     rcx, rsi; Instance
0x140019857  jz      short loc_1400198AD
0x140019859  lea     rdx, [rbp+57h+var_B0]; Context
0x14001985d  call    cs:__imp_FltGetInstanceContext
0x140019864  nop     dword ptr [rax+rax+00h]
0x140019869  mov     ebx, eax
0x14001986b  test    eax, eax
0x14001986d  js      loc_140019993
0x140019873  mov     rdx, [rbp+57h+Context]
0x140019877  test    byte ptr [rdx+34h], 2
0x14001987b  mov     rdx, [rdx]
0x14001987e  jz      short loc_140019884
0x140019880  add     rdx, 30h ; '0'
0x140019884  mov     rcx, [rbp+57h+var_B0]; Context
0x140019888  movzx   r14d, word ptr [rdx]
0x14001988c  mov     rax, [rcx+18h]
0x140019890  movzx   esi, word ptr [rax+38h]
0x140019894  sub     r14w, si
0x140019898  add     rsi, [rdx+8]
0x14001989c  call    cs:__imp_FltReleaseContext
0x1400198a3  nop     dword ptr [rax+rax+00h]
0x1400198a8  jmp     loc_140019939
0x1400198ad  mov     [rbp+57h+Length], ebx
0x1400198b0  lea     r8, [rbp+57h+var_90]
0x1400198b4  mov     r12d, 9
0x1400198ba  mov     r9d, ebx
0x1400198bd  jmp     short loc_140019903
0x1400198bf  lea     rax, [rbp+57h+var_90]
0x1400198c3  cmp     rdi, rax
0x1400198c6  jnz     short loc_1400198CF
0x1400198c8  mov     edx, 200h
0x1400198cd  jmp     short loc_1400198DD
0x1400198cf  mov     rcx, rdi
0x1400198d2  call    LuafvFreePool
0x1400198d7  mov     eax, [rbp+57h+Length]
0x1400198da  lea     edx, [rax+rax]
0x1400198dd  mov     r8b, 1
0x1400198e0  mov     [rbp+57h+Length], edx
0x1400198e3  mov     ecx, 1
0x1400198e8  call    LuafvAllocatePool
0x1400198ed  mov     rdi, rax
0x1400198f0  test    rax, rax
0x1400198f3  jz      loc_140019A62
0x1400198f9  mov     r9d, [rbp+57h+Length]; Length
0x1400198fd  mov     r8, rax; FileInformation
0x140019900  mov     rcx, rsi; Instance
0x140019903  lea     rax, [rbp+57h+Length]
0x140019907  mov     rdx, r14; FileObject
0x14001990a  mov     [rsp+0F0h+LengthReturned], rax; LengthReturned
0x14001990f  mov     [rsp+0F0h+FileInformationClass], r12d; FileInformationClass
0x140019914  call    cs:__imp_FltQueryInformationFile
0x14001991b  nop     dword ptr [rax+rax+00h]
0x140019920  mov     ebx, eax
0x140019922  cmp     eax, 80000005h
0x140019927  jz      short loc_1400198BF
0x140019929  test    ebx, ebx
0x14001992b  js      short loc_14001997D
0x14001992d  mov     r12, [rbp+57h+var_A8]
0x140019931  lea     rsi, [rdi+4]
0x140019935  movzx   r14d, word ptr [rdi]
0x140019939  movzx   edx, r14w
0x14001993d  mov     r8b, 2
0x140019940  mov     ecx, 1
0x140019945  mov     [rbp+57h+Length], edx
0x140019948  call    LuafvAllocatePool
0x14001994d  mov     qword ptr [rbp+57h+var_A0+8], rax
0x140019951  mov     rcx, rax; void *
0x140019954  test    rax, rax
0x140019957  jz      loc_140019A62
0x14001995d  mov     eax, [rbp+57h+Length]
0x140019960  mov     rdx, rsi; Src
0x140019963  mov     r8d, eax; Size
0x140019966  mov     word ptr [rbp+57h+var_A0], ax
0x14001996a  mov     word ptr [rbp+57h+var_A0+2], ax
0x14001996e  call    memmove
0x140019973  movups  xmm0, [rbp+57h+var_A0]
0x140019977  movdqu  xmmword ptr [r12], xmm0
0x14001997d  lea     rax, [rbp+57h+var_90]
0x140019981  cmp     rdi, rax
0x140019984  jz      short loc_140019993
0x140019986  test    rdi, rdi
0x140019989  jz      short loc_140019993
0x14001998b  mov     rcx, rdi
0x14001998e  call    LuafvFreePool
0x140019993  test    r15, r15
0x140019996  jnz     short loc_1400199AD
0x140019998  mov     rcx, [rbp+57h+Context]; Context
0x14001999c  test    rcx, rcx
0x14001999f  jz      short loc_1400199AD
0x1400199a1  call    cs:__imp_FltReleaseContext
0x1400199a8  nop     dword ptr [rax+rax+00h]
0x1400199ad  mov     eax, ebx
0x1400199af  mov     rcx, [rbp+57h+var_40]
0x1400199b3  xor     rcx, rsp; StackCookie
0x1400199b6  call    __security_check_cookie
0x1400199bb  add     rsp, 0C0h
0x1400199c2  pop     r15
0x1400199c4  pop     r14
0x1400199c6  pop     r12
0x1400199c8  pop     rdi
0x1400199c9  pop     rsi
0x1400199ca  pop     rbx
0x1400199cb  pop     rbp
0x1400199cc  retn
0x1400199ce  mov     rax, [rbp+57h+Context]
0x1400199d2  test    rax, rax
0x1400199d5  jz      short loc_1400199E5
0x1400199d7  cmp     qword ptr [rax], 0
0x1400199db  jz      short loc_1400199E5
0x1400199dd  mov     rcx, rsi
0x1400199e0  jmp     loc_140019859
0x1400199e5  mov     [rbp+57h+Length], ebx
0x1400199e8  lea     r8, [rbp+57h+var_90]
0x1400199ec  mov     r12d, 9
0x1400199f2  mov     r9d, ebx
0x1400199f5  jmp     short loc_140019A34
0x1400199f7  lea     rax, [rbp+57h+var_90]
0x1400199fb  cmp     rdi, rax
0x1400199fe  jnz     short loc_140019A07
0x140019a00  mov     edx, 200h
0x140019a05  jmp     short loc_140019A15
0x140019a07  mov     rcx, rdi
0x140019a0a  call    LuafvFreePool
0x140019a0f  mov     eax, [rbp+57h+Length]
0x140019a12  lea     edx, [rax+rax]
0x140019a15  mov     r8b, 1
0x140019a18  mov     [rbp+57h+Length], edx
0x140019a1b  mov     ecx, 1
0x140019a20  call    LuafvAllocatePool
0x140019a25  mov     rdi, rax
0x140019a28  test    rax, rax
0x140019a2b  jz      short loc_140019A62
0x140019a2d  mov     r9d, [rbp+57h+Length]; Length
0x140019a31  mov     r8, rax; FileInformation
0x140019a34  lea     rax, [rbp+57h+Length]
0x140019a38  mov     rdx, r14; FileObject
0x140019a3b  mov     [rsp+0F0h+LengthReturned], rax; LengthReturned
0x140019a40  mov     rcx, rsi; Instance
0x140019a43  mov     [rsp+0F0h+FileInformationClass], r12d; FileInformationClass
0x140019a48  call    cs:__imp_FltQueryInformationFile
0x140019a4f  nop     dword ptr [rax+rax+00h]
0x140019a54  mov     ebx, eax
0x140019a56  cmp     eax, 80000005h
0x140019a5b  jz      short loc_1400199F7
0x140019a5d  jmp     loc_140019929
0x140019a62  mov     ebx, 0C000009Ah
0x140019a67  jmp     loc_14001997D
```
