# LdrpMapDllNtFileName

- ea: `0x180028bd0`
- end: `0x18002911a`
- name: `LdrpMapDllNtFileName`
- size: `1354`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027a20`
- `0x1800be2e0`
- `0x1800f7704`

## callees

- `0x180027444`
- `0x180028bd0`
- `0x180029364`
- `0x180029b70`
- `0x180029c3c`
- `0x18004cef8`
- `0x1800526f0`
- `0x180091650`
- `0x1800acb14`
- `0x1800d90dc`
- `0x1801033f8`
- `0x18015e4b0`
- `0x18015e930`
- `0x18015ec10`
- `0x180161160`
- `0x180161cc0`
- `0x18016f020`

## pseudocode

```c
__int64 __fastcall LdrpMapDllNtFileName(__int64 a1, UNICODE_STRING *a2)
{
  __int64 v2; // rdi
  __int64 v3; // r14
  int v4; // r12d
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  ULONG v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r15
  __int64 v16; // rcx
  __int64 v17; // r13
  NTSTATUS v18; // eax
  int v19; // r9d
  int v20; // edi
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rbx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  int v32; // r9d
  char *v33; // rcx
  int v34; // r9d
  int v35; // eax
  HANDLE v36; // [rsp+30h] [rbp-69h]
  HANDLE FileHandle; // [rsp+40h] [rbp-59h] BYREF
  __int64 v38; // [rsp+48h] [rbp-51h]
  HANDLE Handle; // [rsp+50h] [rbp-49h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-41h] BYREF
  UNICODE_STRING v41; // [rsp+88h] [rbp-11h] BYREF
  _QWORD v42[2]; // [rsp+98h] [rbp-1h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp+Fh] BYREF
  char v44; // [rsp+100h] [rbp+67h] BYREF
  int v45; // [rsp+110h] [rbp+77h] BYREF
  int v46; // [rsp+118h] [rbp+7Fh] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v3 = *(_QWORD *)(a1 + 176);
  v4 = 0;
  v46 = 0;
  FileHandle = 0;
  Handle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  v41 = 0;
  if ( (unsigned __int8)LdrpCheckForRetryLoading(a1, 0) )
    return 3221226029LL;
  v7 = *(_QWORD *)(v2 + 48);
  v38 = v2 + 72;
  LdrpLogDllState(v7, v2 + 72, 5285);
  v11 = 64;
  ObjectAttributes.Length = 48;
  if ( !LdrpUseImpersonatedDeviceMap )
    v11 = 2112;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = v11;
  ObjectAttributes.ObjectName = a2;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v15 = 2147353476;
  if ( (unsigned int)RtlGetCurrentServiceSessionId(2112, v8, v9, v10) )
    v16 = (__int64)NtCurrentPeb()->SharedData + 554;
  else
    v16 = 2147353476;
  v17 = 2147353477;
  if ( *(_BYTE *)v16 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
  {
    v33 = (unsigned int)RtlGetCurrentServiceSessionId(v16, v12, v13, v14)
        ? (char *)NtCurrentPeb()->SharedData + 555
        : (char *)2147353477;
    if ( (*v33 & 0x20) != 0 )
    {
      LOBYTE(v32) = -1;
      LdrpLogEtwEvent(5253, -1, 255, v32, 0, 0);
    }
  }
  if ( (NtCurrentPeb()->NtGlobalFlag & 0x40000) != 0 )
  {
    v41 = *a2;
    ZwSystemDebugControl(38, &v41, 16, 0, 0, 0);
  }
  while ( 1 )
  {
    v18 = NtOpenFile(&FileHandle, 0x100021u, &ObjectAttributes, &IoStatusBlock, 5u, 0x60u);
    v20 = v18;
    if ( v18 >= 0 )
      break;
    if ( v18 == -1073741772 || v18 == -1073741766 )
      return (unsigned int)-1073741515;
    if ( v18 != -1073741790 || v4 || !(unsigned __int8)LdrpCheckComponentOnDemandEtwEvent(a1) )
      return (unsigned int)v20;
    v4 = 1;
  }
  if ( LdrpAuditIntegrityContinuity
    && (v20 = LdrpValidateIntegrityContinuity(a1, FileHandle), v20 < 0)
    && LdrpEnforceIntegrityContinuity
    || (*(_DWORD *)(a1 + 32) & 0x1000000) != 0
    && (v45 = 0, v44 = 0, (NtCurrentPeb()->BitField & 0x10) == 0)
    && (LOBYTE(v19) = 8,
        v20 = LdrpSetModuleSigningLevel(
                (_DWORD)FileHandle,
                *(_QWORD *)(a1 + 56),
                (unsigned int)&v45,
                v19,
                (__int64)&v44),
        v20 < 0) )
  {
LABEL_31:
    NtClose(FileHandle);
    return (unsigned int)v20;
  }
  v36 = FileHandle;
  v21 = NtCreateSection(&Handle, 13, 0);
  v20 = v21;
  if ( v21 < 0 )
  {
    if ( (unsigned int)(v21 + 1073740674) <= 1 || v21 == -1073740702 )
    {
      v35 = LdrAppxHandleIntegrityFailure((unsigned int)v21);
      v26 = v38;
      v20 = v35;
    }
    else
    {
      v26 = v38;
      if ( v21 != -1073741801 && v21 != -1073741670 && v21 != -1073741523 )
      {
        v42[0] = v38;
        v42[1] = v21;
        if ( (int)NtRaiseHardError(3221225595LL, 2, 1, v42, 1, &v46, v36) >= 0 && LdrInitState != 3 )
          ++LdrpFatalHardErrorCount;
      }
    }
    LdrpLogError((unsigned int)v20, 5253, 0, v26);
    goto LABEL_31;
  }
  if ( (unsigned int)RtlGetCurrentServiceSessionId(v23, v22, v24, v25) )
    v15 = (__int64)NtCurrentPeb()->SharedData + 554;
  if ( *(_BYTE *)v15 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v29, v28, v30, v31) )
      v17 = (__int64)NtCurrentPeb()->SharedData + 555;
    if ( (*(_BYTE *)v17 & 0x20) != 0 )
    {
      LOBYTE(v34) = -1;
      LdrpLogEtwEvent(5254, -1, 255, v34, 0, 0);
    }
  }
  if ( !UseWOW64 && (*(_DWORD *)(a1 + 32) & 0x100) == 0 )
  {
    if ( LdrpAdvapi32DllHandle )
    {
      v20 = ((__int64 (__fastcall *)(HANDLE, UNICODE_STRING *))(__ROR8__(
                                                                  LdrpSaferIsDllAllowedRoutine,
                                                                  64 - (MEMORY[0x7FFE0330] & 0x3Fu))
                                                              ^ MEMORY[0x7FFE0330]))(
              FileHandle,
              a2);
      if ( v20 == -1073741275 )
        goto LABEL_29;
    }
    else
    {
      v20 = 0;
    }
    if ( v20 < 0 )
    {
LABEL_30:
      NtClose(Handle);
      goto LABEL_31;
    }
  }
LABEL_29:
  v20 = LdrpMapDllWithSectionHandle(a1, (__int64)Handle);
  if ( !v3 || v20 < 0 )
    goto LABEL_30;
  *(_QWORD *)(a1 + 184) = FileHandle;
  *(_QWORD *)(a1 + 24) = Handle;
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180028bd0  push    rbp
0x180028bd2  push    rbx
0x180028bd3  push    rsi
0x180028bd4  push    rdi
0x180028bd5  push    r12
0x180028bd7  push    r14
0x180028bd9  lea     rbp, [rsp-2Fh]
0x180028bde  sub     rsp, 0C8h
0x180028be5  mov     rdi, [rcx+38h]
0x180028be9  xorps   xmm0, xmm0
0x180028bec  mov     r14, [rcx+0B0h]
0x180028bf3  xor     r12d, r12d
0x180028bf6  mov     rsi, rdx
0x180028bf9  mov     [rbp+57h+arg_18], r12d
0x180028bfd  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180028c01  xor     eax, eax
0x180028c03  mov     [rbp+57h+FileHandle], r12
0x180028c07  xor     edx, edx
0x180028c09  mov     [rbp+57h+Handle], r12
0x180028c0d  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180028c11  mov     rbx, rcx
0x180028c14  movups  xmmword ptr [rbp+57h+IoStatusBlock.___u0], xmm0
0x180028c18  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180028c1c  movups  [rbp+57h+var_68], xmm0
0x180028c20  call    LdrpCheckForRetryLoading
0x180028c25  test    al, al
0x180028c27  jnz     loc_180028E1D
0x180028c2d  mov     rcx, [rdi+30h]
0x180028c31  lea     rax, [rdi+48h]
0x180028c35  mov     rdx, rax
0x180028c38  mov     [rsp+0F0h+arg_8], r13
0x180028c40  mov     r8d, 14A5h
0x180028c46  mov     [rsp+0F0h+var_30], r15
0x180028c4e  mov     [rbp+57h+var_A8], rax
0x180028c52  call    LdrpLogDllState
0x180028c57  cmp     cs:LdrpUseImpersonatedDeviceMap, r12b
0x180028c5e  mov     eax, 40h ; '@'
0x180028c63  mov     ecx, 840h
0x180028c68  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180028c6f  cmovz   eax, ecx
0x180028c72  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x180028c76  xorps   xmm0, xmm0
0x180028c79  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x180028c7c  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x180028c80  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180028c85  call    RtlGetCurrentServiceSessionId
0x180028c8a  mov     r15d, 7FFE0384h
0x180028c90  test    eax, eax
0x180028c92  jnz     loc_180028FCE
0x180028c98  mov     ecx, r15d
0x180028c9b  mov     r13d, 7FFE0385h
0x180028ca1  cmp     [rcx], r12b
0x180028ca4  jz      short loc_180028CBC
0x180028ca6  mov     rax, gs:60h
0x180028caf  test    byte ptr [rax+378h], 4
0x180028cb6  jnz     loc_180028F20
0x180028cbc  mov     rax, gs:60h
0x180028cc5  test    dword ptr [rax+0BCh], 40000h
0x180028ccf  jz      short loc_180028CF9
0x180028cd1  movaps  xmm0, xmmword ptr [rsi]
0x180028cd4  lea     rdx, [rbp+57h+var_68]
0x180028cd8  mov     qword ptr [rsp+0F0h+OpenOptions], r12
0x180028cdd  xor     r9d, r9d
0x180028ce0  mov     r8d, 10h
0x180028ce6  mov     [rsp+0F0h+ShareAccess], r12d
0x180028ceb  mov     ecx, 26h ; '&'
0x180028cf0  movups  [rbp+57h+var_68], xmm0
0x180028cf4  call    ZwSystemDebugControl
0x180028cf9  mov     [rsp+0F0h+OpenOptions], 60h ; '`'; OpenOptions
0x180028d01  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180028d05  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180028d09  mov     [rsp+0F0h+ShareAccess], 5; ShareAccess
0x180028d11  mov     edx, 100021h; DesiredAccess
0x180028d16  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180028d1a  call    NtOpenFile
0x180028d1f  mov     edi, eax
0x180028d21  test    eax, eax
0x180028d23  js      loc_180028EBA
0x180028d29  cmp     cs:LdrpAuditIntegrityContinuity, 0
0x180028d30  jnz     loc_18002900E
0x180028d36  mov     r12d, 1000000h
0x180028d3c  test    [rbx+20h], r12d
0x180028d40  jnz     loc_180029056
0x180028d46  cmp     cs:UseWOW64, 0
0x180028d4d  jnz     loc_1800290C4
0x180028d53  mov     rax, [rbp+57h+FileHandle]
0x180028d57  lea     rcx, [rbp+57h+Handle]
0x180028d5b  mov     [rsp+0F0h+var_C0], rax
0x180028d60  xor     r9d, r9d
0x180028d63  mov     [rsp+0F0h+OpenOptions], r12d
0x180028d68  xor     r8d, r8d
0x180028d6b  mov     edx, 0Dh
0x180028d70  mov     [rsp+0F0h+ShareAccess], 10h
0x180028d78  call    NtCreateSection
0x180028d7d  movsxd  rdi, eax
0x180028d80  test    eax, eax
0x180028d82  jns     loc_180028E33
0x180028d88  lea     eax, [rdi+3FFFFB82h]
0x180028d8e  cmp     eax, 1
0x180028d91  jbe     loc_1800290A0
0x180028d97  cmp     edi, 0C0000462h
0x180028d9d  jz      loc_1800290A0
0x180028da3  mov     rbx, [rbp+57h+var_A8]
0x180028da7  cmp     edi, 0C0000017h
0x180028dad  jz      loc_1800290AD
0x180028db3  cmp     edi, 0C000009Ah
0x180028db9  jz      loc_1800290AD
0x180028dbf  cmp     edi, 0C000012Dh
0x180028dc5  jz      loc_1800290AD
0x180028dcb  lea     rax, [rbp+57h+arg_18]
0x180028dcf  mov     [rbp+57h+var_58], rbx
0x180028dd3  mov     qword ptr [rsp+0F0h+OpenOptions], rax
0x180028dd8  lea     r9, [rbp+57h+var_58]
0x180028ddc  mov     edx, 2
0x180028de1  mov     [rsp+0F0h+ShareAccess], 1
0x180028de9  mov     ecx, 0C000007Bh
0x180028dee  mov     [rbp+57h+var_50], rdi
0x180028df2  mov     r8d, 1
0x180028df8  call    NtRaiseHardError
0x180028dfd  test    eax, eax
0x180028dff  js      loc_1800290AD
0x180028e05  cmp     cs:LdrInitState, 3
0x180028e0c  jz      loc_1800290AD
0x180028e12  inc     cs:LdrpFatalHardErrorCount
0x180028e18  jmp     loc_1800290AD
0x180028e1d  mov     eax, 0C000022Dh
0x180028e22  add     rsp, 0C8h
0x180028e29  pop     r14
0x180028e2b  pop     r12
0x180028e2d  pop     rdi
0x180028e2e  pop     rsi
0x180028e2f  pop     rbx
0x180028e30  pop     rbp
0x180028e31  retn
0x180028e33  call    RtlGetCurrentServiceSessionId
0x180028e38  test    eax, eax
0x180028e3a  jnz     loc_180028FEA
0x180028e40  cmp     byte ptr [r15], 0
0x180028e44  jz      short loc_180028E5C
0x180028e46  mov     rax, gs:60h
0x180028e4f  test    byte ptr [rax+378h], 4
0x180028e56  jnz     loc_180028F74
0x180028e5c  cmp     cs:UseWOW64, 0
0x180028e63  jnz     short loc_180028E6E
0x180028e65  test    dword ptr [rbx+20h], 100h
0x180028e6c  jz      short loc_180028ECC
0x180028e6e  mov     rdx, [rbp+57h+Handle]
0x180028e72  mov     rcx, rbx
0x180028e75  call    LdrpMapDllWithSectionHandle
0x180028e7a  mov     edi, eax
0x180028e7c  test    r14, r14
0x180028e7f  jnz     loc_180029036
0x180028e85  mov     rcx, [rbp+57h+Handle]; Handle
0x180028e89  call    NtClose
0x180028e8e  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180028e92  call    NtClose
0x180028e97  mov     r13, [rsp+0F0h+arg_8]
0x180028e9f  mov     eax, edi
0x180028ea1  mov     r15, [rsp+0F0h+var_30]
0x180028ea9  add     rsp, 0C8h
0x180028eb0  pop     r14
0x180028eb2  pop     r12
0x180028eb4  pop     rdi
0x180028eb5  pop     rsi
0x180028eb6  pop     rbx
0x180028eb7  pop     rbp
0x180028eb8  retn
0x180028eba  cmp     eax, 0C0000034h
0x180028ebf  jnz     loc_1800290D9
0x180028ec5  mov     edi, 0C0000135h
0x180028eca  jmp     short loc_180028E97
0x180028ecc  cmp     cs:LdrpAdvapi32DllHandle, 0
0x180028ed4  jz      loc_180029113
0x180028eda  mov     eax, ds:7FFE0330h
0x180028ee1  mov     ecx, 40h ; '@'
0x180028ee6  mov     edx, eax
0x180028ee8  and     edx, 3Fh
0x180028eeb  sub     ecx, edx
0x180028eed  mov     rdx, cs:LdrpSaferIsDllAllowedRoutine
0x180028ef4  ror     rdx, cl
0x180028ef7  mov     rcx, [rbp+57h+FileHandle]
0x180028efb  xor     rax, rdx
0x180028efe  mov     rdx, rsi
0x180028f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f06  mov     edi, eax
0x180028f08  cmp     eax, 0C0000225h
0x180028f0d  jz      loc_180028E6E
0x180028f13  test    edi, edi
0x180028f15  js      loc_180028E85
0x180028f1b  jmp     loc_180028E6E
0x180028f20  call    RtlGetCurrentServiceSessionId
0x180028f25  test    eax, eax
0x180028f27  jz      loc_180029006
0x180028f2d  mov     rax, gs:60h
0x180028f36  mov     rcx, [rax+90h]
0x180028f3d  add     rcx, 22Bh
0x180028f44  test    byte ptr [rcx], 20h
0x180028f47  jz      loc_180028CBC
0x180028f4d  mov     r9b, 0FFh
0x180028f50  mov     qword ptr [rsp+0F0h+OpenOptions], r12
0x180028f55  movzx   r8d, r9b
0x180028f59  mov     qword ptr [rsp+0F0h+ShareAccess], r12
0x180028f5e  mov     ecx, 1485h
0x180028f63  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180028f6a  call    LdrpLogEtwEvent
0x180028f6f  jmp     loc_180028CBC
0x180028f74  call    RtlGetCurrentServiceSessionId
0x180028f79  test    eax, eax
0x180028f7b  jz      short loc_180028F94
0x180028f7d  mov     rax, gs:60h
0x180028f86  mov     r13, [rax+90h]
0x180028f8d  add     r13, 22Bh
0x180028f94  test    byte ptr [r13+0], 20h
0x180028f99  jz      loc_180028E5C
0x180028f9f  mov     r9b, 0FFh
0x180028fa2  mov     qword ptr [rsp+0F0h+OpenOptions], 0
0x180028fab  movzx   r8d, r9b
0x180028faf  mov     qword ptr [rsp+0F0h+ShareAccess], 0
0x180028fb8  mov     ecx, 1486h
0x180028fbd  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180028fc4  call    LdrpLogEtwEvent
0x180028fc9  jmp     loc_180028E5C
0x180028fce  mov     rax, gs:60h
0x180028fd7  mov     rcx, [rax+90h]
0x180028fde  add     rcx, 22Ah
0x180028fe5  jmp     loc_180028C9B
0x180028fea  mov     rax, gs:60h
0x180028ff3  mov     r15, [rax+90h]
0x180028ffa  add     r15, 22Ah
0x180029001  jmp     loc_180028E40
0x180029006  mov     rcx, r13
0x180029009  jmp     loc_180028F44
0x18002900e  mov     rdx, [rbp+57h+FileHandle]
0x180029012  mov     rcx, rbx
0x180029015  call    LdrpValidateIntegrityContinuity
0x18002901a  mov     edi, eax
0x18002901c  test    eax, eax
0x18002901e  jns     loc_180028D36
0x180029024  cmp     cs:LdrpEnforceIntegrityContinuity, 0
0x18002902b  jnz     loc_180028E8E
0x180029031  jmp     loc_180028D36
0x180029036  test    edi, edi
0x180029038  js      loc_180028E85
0x18002903e  mov     rax, [rbp+57h+FileHandle]
0x180029042  mov     [rbx+0B8h], rax
0x180029049  mov     rax, [rbp+57h+Handle]
0x18002904d  mov     [rbx+18h], rax
0x180029051  jmp     loc_180028E97
0x180029056  mov     [rbp+57h+arg_10], 0
0x18002905d  mov     rax, gs:60h
0x180029066  mov     [rbp+57h+arg_0], 0
0x18002906a  test    byte ptr [rax+3], 10h
0x18002906e  jnz     loc_180028D46
0x180029074  mov     rdx, [rbx+38h]
0x180029078  lea     rax, [rbp+57h+arg_0]
0x18002907c  mov     rcx, [rbp+57h+FileHandle]
0x180029080  lea     r8, [rbp+57h+arg_10]
0x180029084  mov     r9b, 8
0x180029087  mov     qword ptr [rsp+0F0h+ShareAccess], rax
0x18002908c  call    LdrpSetModuleSigningLevel
0x180029091  mov     edi, eax
0x180029093  test    eax, eax
0x180029095  js      loc_180028E8E
0x18002909b  jmp     loc_180028D46
0x1800290a0  mov     ecx, edi
0x1800290a2  call    LdrAppxHandleIntegrityFailure
0x1800290a7  mov     rbx, [rbp+57h+var_A8]
0x1800290ab  mov     edi, eax
0x1800290ad  mov     edx, 1485h
0x1800290b2  mov     r9, rbx
0x1800290b5  xor     r8d, r8d
0x1800290b8  mov     ecx, edi
0x1800290ba  call    LdrpLogError
0x1800290bf  jmp     loc_180028E8E
0x1800290c4  test    dword ptr [rbx+20h], 800h
0x1800290cb  mov     eax, 1100000h
0x1800290d0  cmovz   r12d, eax
0x1800290d4  jmp     loc_180028D53
0x1800290d9  cmp     eax, 0C000003Ah
0x1800290de  jz      loc_180028EC5
0x1800290e4  cmp     eax, 0C0000022h
0x1800290e9  jnz     loc_180028E97
0x1800290ef  test    r12d, r12d
0x1800290f2  jnz     loc_180028E97
0x1800290f8  mov     rcx, rbx
0x1800290fb  call    LdrpCheckComponentOnDemandEtwEvent
0x180029100  test    al, al
0x180029102  jz      loc_180028E97
0x180029108  mov     r12d, 1
0x18002910e  jmp     loc_180028CF9
0x180029113  xor     edi, edi
0x180029115  jmp     loc_180028F13
```
