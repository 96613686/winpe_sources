# LuafvGetNameFileObject

- ea: `0x140019730`
- end: `0x140019a1c`
- name: `LuafvGetNameFileObject`
- size: `748`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, _OWORD *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140018c98`
- `0x140018f20`
- `0x140025820`

## callees

- `0x140001adc`
- `0x140005bb0`
- `0x140005d00`
- `0x140006000`
- `0x140019730`
- `0x14001b650`
- `0x14001dd40`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x1400197d6`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400197d6`
- `FLTMGR!FltReleaseContext` at `0x14001984c`
- `FLTMGR!FltReleaseContext` at `0x140019951`
- `FLTMGR!FltReleaseContext` at `0x14001984c`
- `FLTMGR!FltReleaseContext` at `0x140019951`
- `FLTMGR!FltGetInstanceContext` at `0x14001980d`
- `FLTMGR!FltGetInstanceContext` at `0x14001980d`
- `FLTMGR!FltQueryInformationFile` at `0x1400198c4`
- `FLTMGR!FltQueryInformationFile` at `0x1400199f8`
- `FLTMGR!FltQueryInformationFile` at `0x1400198c4`
- `FLTMGR!FltQueryInformationFile` at `0x1400199f8`

## pseudocode

```c
__int64 __fastcall LuafvGetNameFileObject(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, _OWORD *a3)
{
  _OWORD *v3; // r12
  PVOID FsContext; // r15
  _BYTE *v8; // rdi
  struct _FLT_INSTANCE *v9; // rcx
  NTSTATUS InstanceContext; // ebx
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned __int16 v13; // r14
  const void *v14; // rsi
  __int64 v15; // r8
  _BYTE *v16; // r8
  ULONG v17; // r9d
  __int64 v18; // rdx
  __int64 Pool; // rax
  _BYTE *v20; // r8
  ULONG v21; // r9d
  __int64 v22; // rdx
  __int64 v23; // rax
  ULONG Length; // [rsp+30h] [rbp-69h] BYREF
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-61h] BYREF
  PFLT_CONTEXT v26; // [rsp+40h] [rbp-59h] BYREF
  _OWORD *v27; // [rsp+48h] [rbp-51h]
  __int128 v28; // [rsp+50h] [rbp-49h]
  _BYTE v29[80]; // [rsp+60h] [rbp-39h] BYREF

  v3 = a3;
  v27 = a3;
  v26 = 0;
  Context = 0;
  Length = 0;
  v28 = 0;
  memset(v29, 0, 0x48u);
  if ( !FileObject )
    return 3221225523LL;
  FsContext = FileObject->FsContext;
  v8 = v29;
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
    v16 = v29;
    v17 = 72;
    while ( 1 )
    {
      InstanceContext = FltQueryInformationFile(v9, FileObject, v16, v17, FileNameInformation, &Length);
      if ( InstanceContext != -2147483643 )
        break;
      if ( v8 == v29 )
      {
        v18 = 512;
      }
      else
      {
        LuafvFreePool(v8);
        v18 = 2 * Length;
      }
      LOBYTE(v15) = 1;
      Length = v18;
      Pool = LuafvAllocatePool(1, v18, v15);
      v8 = (_BYTE *)Pool;
      if ( !Pool )
        goto LABEL_45;
      v17 = Length;
      v16 = (_BYTE *)Pool;
      v9 = Instance;
    }
LABEL_23:
    if ( InstanceContext < 0 )
    {
LABEL_27:
      if ( v8 != v29 && v8 )
        LuafvFreePool(v8);
      goto LABEL_30;
    }
    v3 = v27;
    v14 = v8 + 4;
    v13 = *(_WORD *)v8;
LABEL_25:
    LOBYTE(v15) = 2;
    Length = v13;
    *((_QWORD *)&v28 + 1) = LuafvAllocatePool(1, v13, v15);
    if ( *((_QWORD *)&v28 + 1) )
    {
      LOWORD(v28) = Length;
      WORD1(v28) = Length;
      memmove(*((void **)&v28 + 1), v14, Length);
      *v3 = v28;
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
    v20 = v29;
    v21 = 72;
    while ( 1 )
    {
      InstanceContext = FltQueryInformationFile(Instance, FileObject, v20, v21, FileNameInformation, &Length);
      if ( InstanceContext != -2147483643 )
        goto LABEL_23;
      if ( v8 == v29 )
      {
        v22 = 512;
      }
      else
      {
        LuafvFreePool(v8);
        v22 = 2 * Length;
      }
      LOBYTE(v15) = 1;
      Length = v22;
      v23 = LuafvAllocatePool(1, v22, v15);
      v8 = (_BYTE *)v23;
      if ( !v23 )
        goto LABEL_45;
      v21 = Length;
      v20 = (_BYTE *)v23;
    }
  }
  v9 = Instance;
LABEL_12:
  InstanceContext = FltGetInstanceContext(v9, &v26);
  if ( InstanceContext >= 0 )
  {
    v11 = *(_QWORD *)Context;
    if ( (*((_BYTE *)Context + 52) & 2) != 0 )
      v11 += 48;
    v12 = *((_QWORD *)v26 + 3);
    v13 = *(_WORD *)v11 - *(_WORD *)(v12 + 56);
    v14 = (const void *)(*(_QWORD *)(v11 + 8) + *(unsigned __int16 *)(v12 + 56));
    FltReleaseContext(v26);
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
0x140019730  push    rbp
0x140019732  push    rbx
0x140019733  push    rsi
0x140019734  push    rdi
0x140019735  push    r12
0x140019737  push    r14
0x140019739  push    r15
0x14001973b  lea     rbp, [rsp-27h]
0x140019740  sub     rsp, 0C0h
0x140019747  mov     rax, cs:__security_cookie
0x14001974e  xor     rax, rsp
0x140019751  mov     [rbp+57h+var_40], rax
0x140019755  mov     r12, r8
0x140019758  mov     [rbp+57h+var_A8], r8
0x14001975c  mov     r14, rdx
0x14001975f  mov     [rbp+57h+var_B0], 0
0x140019767  mov     rsi, rcx
0x14001976a  mov     [rbp+57h+Context], 0
0x140019772  xorps   xmm0, xmm0
0x140019775  mov     [rbp+57h+Length], 0
0x14001977c  mov     ebx, 48h ; 'H'
0x140019781  lea     rcx, [rbp+57h+var_90]; void *
0x140019785  mov     r8d, ebx; Size
0x140019788  xor     edx, edx; Val
0x14001978a  movups  [rbp+57h+var_A0], xmm0
0x14001978e  call    memset
0x140019793  test    r14, r14
0x140019796  jnz     short loc_1400197A2
0x140019798  mov     eax, 0C0000033h
0x14001979d  jmp     loc_14001995F
0x1400197a2  mov     r15, [r14+18h]
0x1400197a6  lea     rdi, [rbp+57h+var_90]
0x1400197aa  test    r15, r15
0x1400197ad  jz      short loc_1400197C7
0x1400197af  mov     eax, 7666h
0x1400197b4  cmp     [r15], ax
0x1400197b8  jnz     short loc_1400197C7
0x1400197ba  mov     rax, [r15+100h]
0x1400197c1  mov     [rbp+57h+Context], rax
0x1400197c5  jmp     short loc_1400197F2
0x1400197c7  test    rsi, rsi
0x1400197ca  jz      short loc_1400197EB
0x1400197cc  lea     r8, [rbp+57h+Context]; Context
0x1400197d0  mov     rdx, r14; FileObject
0x1400197d3  mov     rcx, rsi; Instance
0x1400197d6  call    cs:__imp_FltGetStreamHandleContext
0x1400197dd  nop     dword ptr [rax+rax+00h]
0x1400197e2  test    eax, eax
0x1400197e4  js      short loc_1400197EB
0x1400197e6  xor     r15d, r15d
0x1400197e9  jmp     short loc_1400197F2
0x1400197eb  xor     r15d, r15d
0x1400197ee  mov     [rbp+57h+Context], r15
0x1400197f2  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x1400197f7  test    eax, eax
0x1400197f9  jnz     loc_14001997E
0x1400197ff  cmp     [rbp+57h+Context], 0
0x140019804  mov     rcx, rsi; Instance
0x140019807  jz      short loc_14001985D
0x140019809  lea     rdx, [rbp+57h+var_B0]; Context
0x14001980d  call    cs:__imp_FltGetInstanceContext
0x140019814  nop     dword ptr [rax+rax+00h]
0x140019819  mov     ebx, eax
0x14001981b  test    eax, eax
0x14001981d  js      loc_140019943
0x140019823  mov     rdx, [rbp+57h+Context]
0x140019827  test    byte ptr [rdx+34h], 2
0x14001982b  mov     rdx, [rdx]
0x14001982e  jz      short loc_140019834
0x140019830  add     rdx, 30h ; '0'
0x140019834  mov     rcx, [rbp+57h+var_B0]; Context
0x140019838  movzx   r14d, word ptr [rdx]
0x14001983c  mov     rax, [rcx+18h]
0x140019840  movzx   esi, word ptr [rax+38h]
0x140019844  sub     r14w, si
0x140019848  add     rsi, [rdx+8]
0x14001984c  call    cs:__imp_FltReleaseContext
0x140019853  nop     dword ptr [rax+rax+00h]
0x140019858  jmp     loc_1400198E9
0x14001985d  mov     [rbp+57h+Length], ebx
0x140019860  lea     r8, [rbp+57h+var_90]
0x140019864  mov     r12d, 9
0x14001986a  mov     r9d, ebx
0x14001986d  jmp     short loc_1400198B3
0x14001986f  lea     rax, [rbp+57h+var_90]
0x140019873  cmp     rdi, rax
0x140019876  jnz     short loc_14001987F
0x140019878  mov     edx, 200h
0x14001987d  jmp     short loc_14001988D
0x14001987f  mov     rcx, rdi
0x140019882  call    LuafvFreePool
0x140019887  mov     eax, [rbp+57h+Length]
0x14001988a  lea     edx, [rax+rax]
0x14001988d  mov     r8b, 1
0x140019890  mov     [rbp+57h+Length], edx
0x140019893  mov     ecx, 1
0x140019898  call    LuafvAllocatePool
0x14001989d  mov     rdi, rax
0x1400198a0  test    rax, rax
0x1400198a3  jz      loc_140019A12
0x1400198a9  mov     r9d, [rbp+57h+Length]; Length
0x1400198ad  mov     r8, rax; FileInformation
0x1400198b0  mov     rcx, rsi; Instance
0x1400198b3  lea     rax, [rbp+57h+Length]
0x1400198b7  mov     rdx, r14; FileObject
0x1400198ba  mov     [rsp+0F0h+LengthReturned], rax; LengthReturned
0x1400198bf  mov     [rsp+0F0h+FileInformationClass], r12d; FileInformationClass
0x1400198c4  call    cs:__imp_FltQueryInformationFile
0x1400198cb  nop     dword ptr [rax+rax+00h]
0x1400198d0  mov     ebx, eax
0x1400198d2  cmp     eax, 80000005h
0x1400198d7  jz      short loc_14001986F
0x1400198d9  test    ebx, ebx
0x1400198db  js      short loc_14001992D
0x1400198dd  mov     r12, [rbp+57h+var_A8]
0x1400198e1  lea     rsi, [rdi+4]
0x1400198e5  movzx   r14d, word ptr [rdi]
0x1400198e9  movzx   edx, r14w
0x1400198ed  mov     r8b, 2
0x1400198f0  mov     ecx, 1
0x1400198f5  mov     [rbp+57h+Length], edx
0x1400198f8  call    LuafvAllocatePool
0x1400198fd  mov     qword ptr [rbp+57h+var_A0+8], rax
0x140019901  mov     rcx, rax; void *
0x140019904  test    rax, rax
0x140019907  jz      loc_140019A12
0x14001990d  mov     eax, [rbp+57h+Length]
0x140019910  mov     rdx, rsi; Src
0x140019913  mov     r8d, eax; Size
0x140019916  mov     word ptr [rbp+57h+var_A0], ax
0x14001991a  mov     word ptr [rbp+57h+var_A0+2], ax
0x14001991e  call    memmove
0x140019923  movups  xmm0, [rbp+57h+var_A0]
0x140019927  movdqu  xmmword ptr [r12], xmm0
0x14001992d  lea     rax, [rbp+57h+var_90]
0x140019931  cmp     rdi, rax
0x140019934  jz      short loc_140019943
0x140019936  test    rdi, rdi
0x140019939  jz      short loc_140019943
0x14001993b  mov     rcx, rdi
0x14001993e  call    LuafvFreePool
0x140019943  test    r15, r15
0x140019946  jnz     short loc_14001995D
0x140019948  mov     rcx, [rbp+57h+Context]; Context
0x14001994c  test    rcx, rcx
0x14001994f  jz      short loc_14001995D
0x140019951  call    cs:__imp_FltReleaseContext
0x140019958  nop     dword ptr [rax+rax+00h]
0x14001995d  mov     eax, ebx
0x14001995f  mov     rcx, [rbp+57h+var_40]
0x140019963  xor     rcx, rsp; StackCookie
0x140019966  call    __security_check_cookie
0x14001996b  add     rsp, 0C0h
0x140019972  pop     r15
0x140019974  pop     r14
0x140019976  pop     r12
0x140019978  pop     rdi
0x140019979  pop     rsi
0x14001997a  pop     rbx
0x14001997b  pop     rbp
0x14001997c  retn
0x14001997e  mov     rax, [rbp+57h+Context]
0x140019982  test    rax, rax
0x140019985  jz      short loc_140019995
0x140019987  cmp     qword ptr [rax], 0
0x14001998b  jz      short loc_140019995
0x14001998d  mov     rcx, rsi
0x140019990  jmp     loc_140019809
0x140019995  mov     [rbp+57h+Length], ebx
0x140019998  lea     r8, [rbp+57h+var_90]
0x14001999c  mov     r12d, 9
0x1400199a2  mov     r9d, ebx
0x1400199a5  jmp     short loc_1400199E4
0x1400199a7  lea     rax, [rbp+57h+var_90]
0x1400199ab  cmp     rdi, rax
0x1400199ae  jnz     short loc_1400199B7
0x1400199b0  mov     edx, 200h
0x1400199b5  jmp     short loc_1400199C5
0x1400199b7  mov     rcx, rdi
0x1400199ba  call    LuafvFreePool
0x1400199bf  mov     eax, [rbp+57h+Length]
0x1400199c2  lea     edx, [rax+rax]
0x1400199c5  mov     r8b, 1
0x1400199c8  mov     [rbp+57h+Length], edx
0x1400199cb  mov     ecx, 1
0x1400199d0  call    LuafvAllocatePool
0x1400199d5  mov     rdi, rax
0x1400199d8  test    rax, rax
0x1400199db  jz      short loc_140019A12
0x1400199dd  mov     r9d, [rbp+57h+Length]; Length
0x1400199e1  mov     r8, rax; FileInformation
0x1400199e4  lea     rax, [rbp+57h+Length]
0x1400199e8  mov     rdx, r14; FileObject
0x1400199eb  mov     [rsp+0F0h+LengthReturned], rax; LengthReturned
0x1400199f0  mov     rcx, rsi; Instance
0x1400199f3  mov     [rsp+0F0h+FileInformationClass], r12d; FileInformationClass
0x1400199f8  call    cs:__imp_FltQueryInformationFile
0x1400199ff  nop     dword ptr [rax+rax+00h]
0x140019a04  mov     ebx, eax
0x140019a06  cmp     eax, 80000005h
0x140019a0b  jz      short loc_1400199A7
0x140019a0d  jmp     loc_1400198D9
0x140019a12  mov     ebx, 0C000009Ah
0x140019a17  jmp     loc_14001992D
```
