# TokenInfo<ImpKernelMode>::Get(_TOKEN_INFORMATION_CLASS,char const *,void * *,unsigned __int64 *)

- ea: `0x14004ed88`
- end: `0x14004eec3`
- name: `?Get@?$TokenInfo@VImpKernelMode@@@@QEAAJW4_TOKEN_INFORMATION_CLASS@@PEBDPEAPEAXPEA_K@Z`
- size: `315`
- prototype: `__int64 __fastcall(int, int, int, int, ImpKernelMode *)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14004e27c`
- `0x14004e6ec`
- `0x14004eecc`
- `0x14004f088`

## callees

- `0x14004e4f8`
- `0x14004ed88`
- `0x14004f114`
- `0x14004f2e8`
- `0x1400875c8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004ee4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ee4e`
- `ntoskrnl!SeQueryInformationToken` at `0x14004edc2`
- `ntoskrnl!SeQueryInformationToken` at `0x14004edc2`

## string_xrefs

- `0x14004ee6a`: `Error in Getting Token Information(%s): %d (ResultBuffer=%p, ResultBufferLength=%p)`

## pseudocode

```c
__int64 __fastcall TokenInfo<ImpKernelMode>::Get(
        PACCESS_TOKEN **a1,
        TOKEN_INFORMATION_CLASS a2,
        const char *a3,
        _QWORD *a4,
        ImpKernelMode *a5)
{
  __int64 v5; // rbp
  NTSTATUS InformationToken; // edi
  PACCESS_TOKEN **v10; // rsi
  PACCESS_TOKEN *v11; // rcx
  PACCESS_TOKEN *v12; // r12
  ImpKernelMode *v13; // rcx
  unsigned int *v14; // r9
  void **v15; // r8
  unsigned int v17; // [rsp+98h] [rbp+10h] BYREF

  v5 = a2;
  InformationToken = 0;
  v10 = &a1[a2];
  if ( !v10[1] )
  {
    v11 = *a1;
    v17 = 0;
    InformationToken = SeQueryInformationToken(*v11, a2, (PVOID *)v10 + 1);
    if ( InformationToken >= 0 )
    {
      v12 = v10[1];
      InformationToken = CsvCamQueryInformationTokenLength((unsigned int)v5, v12, &v17);
      if ( InformationToken >= 0 )
      {
        a1[v5 + 56] = (PACCESS_TOKEN *)v17;
        if ( (_DWORD)v5 == 13 )
          TokenInfo<ImpKernelMode>::RemoveUnsupportedPrivileges(a1);
        goto LABEL_6;
      }
      ExFreePoolWithTag(v12, 0);
      v10[1] = 0;
    }
    ImpKernelMode::Log(
      a1,
      1,
      "Error in Getting Token Information(%s): %d (ResultBuffer=%p, ResultBufferLength=%p)",
      a3,
      InformationToken,
      a4,
      a5);
    return (unsigned int)InformationToken;
  }
LABEL_6:
  if ( a4 )
    *a4 = v10[1];
  v13 = a5;
  if ( a5 )
    *(_QWORD *)a5 = a1[v5 + 56];
  if ( (_DWORD)v5 == 33 )
  {
    v14 = (unsigned int *)(a1 + 112);
    v15 = (void **)(a1 + 111);
    return (unsigned int)ImpKernelMode::ConvertClaimsInfoToBlob(v13, v10[1], v15, v14);
  }
  if ( (_DWORD)v5 == 34 )
  {
    v14 = (unsigned int *)(a1 + 114);
    v15 = (void **)(a1 + 113);
    return (unsigned int)ImpKernelMode::ConvertClaimsInfoToBlob(v13, v10[1], v15, v14);
  }
  return (unsigned int)InformationToken;
}

```

## disassembly

```asm
0x14004ed88  mov     rax, rsp
0x14004ed8b  push    rbx
0x14004ed8c  push    rbp
0x14004ed8d  push    rsi
0x14004ed8e  push    rdi
0x14004ed8f  push    r12
0x14004ed91  push    r13
0x14004ed93  push    r14
0x14004ed95  push    r15
0x14004ed97  sub     rsp, 48h
0x14004ed9b  movsxd  rbp, edx
0x14004ed9e  xor     edi, edi
0x14004eda0  mov     r14, r9
0x14004eda3  mov     r13, r8
0x14004eda6  mov     rbx, rcx
0x14004eda9  lea     rsi, [rcx+rbp*8]
0x14004edad  cmp     [rsi+8], rdi
0x14004edb1  jnz     short loc_14004EE10
0x14004edb3  mov     rcx, [rcx]
0x14004edb6  lea     r8, [rsi+8]; TokenInformation
0x14004edba  mov     edx, ebp; TokenInformationClass
0x14004edbc  mov     [rax+10h], edi
0x14004edbf  mov     rcx, [rcx]; Token
0x14004edc2  call    cs:__imp_SeQueryInformationToken
0x14004edc9  nop     dword ptr [rax+rax+00h]
0x14004edce  mov     edi, eax
0x14004edd0  test    eax, eax
0x14004edd2  js      loc_14004EE62
0x14004edd8  mov     r12, [rsi+8]
0x14004eddc  lea     r8, [rsp+88h+arg_8]
0x14004ede4  mov     rdx, r12
0x14004ede7  mov     ecx, ebp
0x14004ede9  call    CsvCamQueryInformationTokenLength
0x14004edee  mov     edi, eax
0x14004edf0  test    eax, eax
0x14004edf2  js      short loc_14004EE49
0x14004edf4  mov     eax, [rsp+88h+arg_8]
0x14004edfb  mov     [rbx+rbp*8+1C0h], rax
0x14004ee03  cmp     ebp, 0Dh
0x14004ee06  jnz     short loc_14004EE10
0x14004ee08  mov     rcx, rbx
0x14004ee0b  call    ?RemoveUnsupportedPrivileges@?$TokenInfo@VImpKernelMode@@@@QEAAXXZ; TokenInfo<ImpKernelMode>::RemoveUnsupportedPrivileges(void)
0x14004ee10  test    r14, r14
0x14004ee13  jz      short loc_14004EE1C
0x14004ee15  mov     rax, [rsi+8]
0x14004ee19  mov     [r14], rax
0x14004ee1c  mov     rcx, [rsp+88h+arg_20]; this
0x14004ee24  test    rcx, rcx
0x14004ee27  jz      short loc_14004EE34
0x14004ee29  mov     rax, [rbx+rbp*8+1C0h]
0x14004ee31  mov     [rcx], rax
0x14004ee34  cmp     ebp, 21h ; '!'
0x14004ee37  jnz     short loc_14004EE91
0x14004ee39  lea     r9, [rbx+380h]
0x14004ee40  lea     r8, [rbx+378h]
0x14004ee47  jmp     short loc_14004EEA4
0x14004ee49  xor     edx, edx; Tag
0x14004ee4b  mov     rcx, r12; P
0x14004ee4e  call    cs:__imp_ExFreePoolWithTag
0x14004ee55  nop     dword ptr [rax+rax+00h]
0x14004ee5a  mov     qword ptr [rsi+8], 0
0x14004ee62  mov     rax, [rsp+88h+arg_20]
0x14004ee6a  lea     r8, aErrorInGetting_1; "Error in Getting Token Information(%s):"...
0x14004ee71  mov     [rsp+88h+var_58], rax
0x14004ee76  mov     r9, r13
0x14004ee79  mov     [rsp+88h+var_60], r14
0x14004ee7e  mov     edx, 1
0x14004ee83  mov     rcx, rbx
0x14004ee86  mov     [rsp+88h+var_68], edi
0x14004ee8a  call    ?Log@ImpKernelMode@@IEAAXW4LOG_LEVEL@@PEBDZZ; ImpKernelMode::Log(LOG_LEVEL,char const *,...)
0x14004ee8f  jmp     short loc_14004EEAF
0x14004ee91  cmp     ebp, 22h ; '"'
0x14004ee94  jnz     short loc_14004EEAF
0x14004ee96  lea     r9, [rbx+390h]; unsigned int *
0x14004ee9d  lea     r8, [rbx+388h]; void **
0x14004eea4  mov     rdx, [rsi+8]; void *
0x14004eea8  call    ?ConvertClaimsInfoToBlob@ImpKernelMode@@IEAAJPEAXPEAPEAXPEAK@Z; ImpKernelMode::ConvertClaimsInfoToBlob(void *,void * *,ulong *)
0x14004eead  mov     edi, eax
0x14004eeaf  mov     eax, edi
0x14004eeb1  add     rsp, 48h
0x14004eeb5  pop     r15
0x14004eeb7  pop     r14
0x14004eeb9  pop     r13
0x14004eebb  pop     r12
0x14004eebd  pop     rdi
0x14004eebe  pop     rsi
0x14004eebf  pop     rbp
0x14004eec0  pop     rbx
0x14004eec1  retn
```
