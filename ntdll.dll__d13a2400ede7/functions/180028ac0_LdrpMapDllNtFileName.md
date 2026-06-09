# LdrpMapDllNtFileName

- ea: `0x180028ac0`
- end: `0x18002900a`
- name: `LdrpMapDllNtFileName`
- size: `1354`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027910`
- `0x1800c25c0`
- `0x1800f81e4`

## callees

- `0x180028ac0`
- `0x180029254`
- `0x180029a60`
- `0x180029b2c`
- `0x18002a604`
- `0x180069af8`
- `0x18006f0d0`
- `0x18009d420`
- `0x1800b7654`
- `0x1800d9b5c`
- `0x180104178`
- `0x18015ecc0`
- `0x18015f140`
- `0x18015f420`
- `0x180161970`
- `0x1801624d0`
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
  int v21; // r12d
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rbx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  int v33; // r9d
  char *v34; // rcx
  int v35; // r9d
  int v36; // eax
  __int64 v37; // [rsp+30h] [rbp-69h]
  HANDLE FileHandle; // [rsp+40h] [rbp-59h] BYREF
  __int64 v39; // [rsp+48h] [rbp-51h]
  HANDLE Handle; // [rsp+50h] [rbp-49h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-41h] BYREF
  UNICODE_STRING v42; // [rsp+88h] [rbp-11h] BYREF
  _QWORD v43[2]; // [rsp+98h] [rbp-1h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp+Fh] BYREF
  char v45; // [rsp+100h] [rbp+67h] BYREF
  int v46; // [rsp+110h] [rbp+77h] BYREF
  int v47; // [rsp+118h] [rbp+7Fh] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v3 = *(_QWORD *)(a1 + 176);
  v4 = 0;
  v47 = 0;
  FileHandle = 0;
  Handle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  v42 = 0;
  if ( (unsigned __int8)LdrpCheckForRetryLoading(a1, 0) )
    return 3221226029LL;
  v7 = *(_QWORD *)(v2 + 48);
  v39 = v2 + 72;
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
    v34 = (unsigned int)RtlGetCurrentServiceSessionId(v16, v12, v13, v14)
        ? (char *)NtCurrentPeb()->SharedData + 555
        : (char *)2147353477;
    if ( (*v34 & 0x20) != 0 )
    {
      LOBYTE(v33) = -1;
      LdrpLogEtwEvent(5253, -1, 255, v33, 0, 0);
    }
  }
  if ( (NtCurrentPeb()->NtGlobalFlag & 0x40000) != 0 )
  {
    v42 = *a2;
    ZwSystemDebugControl(38, &v42, 16, 0, 0, 0);
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
    || (v21 = 0x1000000, (*(_DWORD *)(a1 + 32) & 0x1000000) != 0)
    && (v46 = 0, v45 = 0, (NtCurrentPeb()->BitField & 0x10) == 0)
    && (LOBYTE(v19) = 8,
        v20 = LdrpSetModuleSigningLevel(
                (_DWORD)FileHandle,
                *(_QWORD *)(a1 + 56),
                (unsigned int)&v46,
                v19,
                (__int64)&v45),
        v20 < 0) )
  {
LABEL_32:
    NtClose(FileHandle);
    return (unsigned int)v20;
  }
  if ( UseWOW64 && (*(_DWORD *)(a1 + 32) & 0x800) == 0 )
    v21 = 17825792;
  v22 = NtCreateSection(&Handle, 13, 0, 0, 16, v21, FileHandle);
  v20 = v22;
  if ( v22 < 0 )
  {
    if ( (unsigned int)(v22 + 1073740674) <= 1 || v22 == -1073740702 )
    {
      v36 = LdrAppxHandleIntegrityFailure((unsigned int)v22);
      v27 = v39;
      v20 = v36;
    }
    else
    {
      v27 = v39;
      if ( v22 != -1073741801 && v22 != -1073741670 && v22 != -1073741523 )
      {
        v43[0] = v39;
        v43[1] = v22;
        if ( (int)NtRaiseHardError(3221225595LL, 2, 1, v43, 1, &v47, v37) >= 0 && LdrInitState != 3 )
          ++LdrpFatalHardErrorCount;
      }
    }
    LdrpLogError((unsigned int)v20, 5253, 0, v27);
    goto LABEL_32;
  }
  if ( (unsigned int)RtlGetCurrentServiceSessionId(v24, v23, v25, v26) )
    v15 = (__int64)NtCurrentPeb()->SharedData + 554;
  if ( *(_BYTE *)v15 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v30, v29, v31, v32) )
      v17 = (__int64)NtCurrentPeb()->SharedData + 555;
    if ( (*(_BYTE *)v17 & 0x20) != 0 )
    {
      LOBYTE(v35) = -1;
      LdrpLogEtwEvent(5254, -1, 255, v35, 0, 0);
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
        goto LABEL_30;
    }
    else
    {
      v20 = 0;
    }
    if ( v20 < 0 )
    {
LABEL_31:
      NtClose(Handle);
      goto LABEL_32;
    }
  }
LABEL_30:
  v20 = LdrpMapDllWithSectionHandle(a1, (__int64)Handle);
  if ( !v3 || v20 < 0 )
    goto LABEL_31;
  *(_QWORD *)(a1 + 184) = FileHandle;
  *(_QWORD *)(a1 + 24) = Handle;
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180028ac0  push    rbp
0x180028ac2  push    rbx
0x180028ac3  push    rsi
0x180028ac4  push    rdi
0x180028ac5  push    r12
0x180028ac7  push    r14
0x180028ac9  lea     rbp, [rsp-2Fh]
0x180028ace  sub     rsp, 0C8h
0x180028ad5  mov     rdi, [rcx+38h]
0x180028ad9  xorps   xmm0, xmm0
0x180028adc  mov     r14, [rcx+0B0h]
0x180028ae3  xor     r12d, r12d
0x180028ae6  mov     rsi, rdx
0x180028ae9  mov     [rbp+57h+arg_18], r12d
0x180028aed  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180028af1  xor     eax, eax
0x180028af3  mov     [rbp+57h+FileHandle], r12
0x180028af7  xor     edx, edx
0x180028af9  mov     [rbp+57h+Handle], r12
0x180028afd  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180028b01  mov     rbx, rcx
0x180028b04  movups  xmmword ptr [rbp+57h+IoStatusBlock.___u0], xmm0
0x180028b08  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180028b0c  movups  [rbp+57h+var_68], xmm0
0x180028b10  call    LdrpCheckForRetryLoading
0x180028b15  test    al, al
0x180028b17  jnz     loc_180028D0D
0x180028b1d  mov     rcx, [rdi+30h]
0x180028b21  lea     rax, [rdi+48h]
0x180028b25  mov     rdx, rax
0x180028b28  mov     [rsp+0F0h+arg_8], r13
0x180028b30  mov     r8d, 14A5h
0x180028b36  mov     [rsp+0F0h+var_30], r15
0x180028b3e  mov     [rbp+57h+var_A8], rax
0x180028b42  call    LdrpLogDllState
0x180028b47  cmp     cs:LdrpUseImpersonatedDeviceMap, r12b
0x180028b4e  mov     eax, 40h ; '@'
0x180028b53  mov     ecx, 840h
0x180028b58  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180028b5f  cmovz   eax, ecx
0x180028b62  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x180028b66  xorps   xmm0, xmm0
0x180028b69  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x180028b6c  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x180028b70  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180028b75  call    RtlGetCurrentServiceSessionId
0x180028b7a  mov     r15d, 7FFE0384h
0x180028b80  test    eax, eax
0x180028b82  jnz     loc_180028EBE
0x180028b88  mov     ecx, r15d
0x180028b8b  mov     r13d, 7FFE0385h
0x180028b91  cmp     [rcx], r12b
0x180028b94  jz      short loc_180028BAC
0x180028b96  mov     rax, gs:60h
0x180028b9f  test    byte ptr [rax+378h], 4
0x180028ba6  jnz     loc_180028E10
0x180028bac  mov     rax, gs:60h
0x180028bb5  test    dword ptr [rax+0BCh], 40000h
0x180028bbf  jz      short loc_180028BE9
0x180028bc1  movaps  xmm0, xmmword ptr [rsi]
0x180028bc4  lea     rdx, [rbp+57h+var_68]
0x180028bc8  mov     qword ptr [rsp+0F0h+OpenOptions], r12
0x180028bcd  xor     r9d, r9d
0x180028bd0  mov     r8d, 10h
0x180028bd6  mov     [rsp+0F0h+ShareAccess], r12d
0x180028bdb  mov     ecx, 26h ; '&'
0x180028be0  movups  [rbp+57h+var_68], xmm0
0x180028be4  call    ZwSystemDebugControl
0x180028be9  mov     [rsp+0F0h+OpenOptions], 60h ; '`'; OpenOptions
0x180028bf1  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180028bf5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180028bf9  mov     [rsp+0F0h+ShareAccess], 5; ShareAccess
0x180028c01  mov     edx, 100021h; DesiredAccess
0x180028c06  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180028c0a  call    NtOpenFile
0x180028c0f  mov     edi, eax
0x180028c11  test    eax, eax
0x180028c13  js      loc_180028DAA
0x180028c19  cmp     cs:LdrpAuditIntegrityContinuity, 0
0x180028c20  jnz     loc_180028EFE
0x180028c26  mov     r12d, 1000000h
0x180028c2c  test    [rbx+20h], r12d
0x180028c30  jnz     loc_180028F46
0x180028c36  cmp     cs:UseWOW64, 0
0x180028c3d  jnz     loc_180028FB4
0x180028c43  mov     rax, [rbp+57h+FileHandle]
0x180028c47  lea     rcx, [rbp+57h+Handle]
0x180028c4b  mov     [rsp+0F0h+var_C0], rax
0x180028c50  xor     r9d, r9d
0x180028c53  mov     [rsp+0F0h+OpenOptions], r12d
0x180028c58  xor     r8d, r8d
0x180028c5b  mov     edx, 0Dh
0x180028c60  mov     [rsp+0F0h+ShareAccess], 10h
0x180028c68  call    NtCreateSection
0x180028c6d  movsxd  rdi, eax
0x180028c70  test    eax, eax
0x180028c72  jns     loc_180028D23
0x180028c78  lea     eax, [rdi+3FFFFB82h]
0x180028c7e  cmp     eax, 1
0x180028c81  jbe     loc_180028F90
0x180028c87  cmp     edi, 0C0000462h
0x180028c8d  jz      loc_180028F90
0x180028c93  mov     rbx, [rbp+57h+var_A8]
0x180028c97  cmp     edi, 0C0000017h
0x180028c9d  jz      loc_180028F9D
0x180028ca3  cmp     edi, 0C000009Ah
0x180028ca9  jz      loc_180028F9D
0x180028caf  cmp     edi, 0C000012Dh
0x180028cb5  jz      loc_180028F9D
0x180028cbb  lea     rax, [rbp+57h+arg_18]
0x180028cbf  mov     [rbp+57h+var_58], rbx
0x180028cc3  mov     qword ptr [rsp+0F0h+OpenOptions], rax
0x180028cc8  lea     r9, [rbp+57h+var_58]
0x180028ccc  mov     edx, 2
0x180028cd1  mov     [rsp+0F0h+ShareAccess], 1
0x180028cd9  mov     ecx, 0C000007Bh
0x180028cde  mov     [rbp+57h+var_50], rdi
0x180028ce2  mov     r8d, 1
0x180028ce8  call    NtRaiseHardError
0x180028ced  test    eax, eax
0x180028cef  js      loc_180028F9D
0x180028cf5  cmp     cs:LdrInitState, 3
0x180028cfc  jz      loc_180028F9D
0x180028d02  inc     cs:LdrpFatalHardErrorCount
0x180028d08  jmp     loc_180028F9D
0x180028d0d  mov     eax, 0C000022Dh
0x180028d12  add     rsp, 0C8h
0x180028d19  pop     r14
0x180028d1b  pop     r12
0x180028d1d  pop     rdi
0x180028d1e  pop     rsi
0x180028d1f  pop     rbx
0x180028d20  pop     rbp
0x180028d21  retn
0x180028d23  call    RtlGetCurrentServiceSessionId
0x180028d28  test    eax, eax
0x180028d2a  jnz     loc_180028EDA
0x180028d30  cmp     byte ptr [r15], 0
0x180028d34  jz      short loc_180028D4C
0x180028d36  mov     rax, gs:60h
0x180028d3f  test    byte ptr [rax+378h], 4
0x180028d46  jnz     loc_180028E64
0x180028d4c  cmp     cs:UseWOW64, 0
0x180028d53  jnz     short loc_180028D5E
0x180028d55  test    dword ptr [rbx+20h], 100h
0x180028d5c  jz      short loc_180028DBC
0x180028d5e  mov     rdx, [rbp+57h+Handle]
0x180028d62  mov     rcx, rbx
0x180028d65  call    LdrpMapDllWithSectionHandle
0x180028d6a  mov     edi, eax
0x180028d6c  test    r14, r14
0x180028d6f  jnz     loc_180028F26
0x180028d75  mov     rcx, [rbp+57h+Handle]; Handle
0x180028d79  call    NtClose
0x180028d7e  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180028d82  call    NtClose
0x180028d87  mov     r13, [rsp+0F0h+arg_8]
0x180028d8f  mov     eax, edi
0x180028d91  mov     r15, [rsp+0F0h+var_30]
0x180028d99  add     rsp, 0C8h
0x180028da0  pop     r14
0x180028da2  pop     r12
0x180028da4  pop     rdi
0x180028da5  pop     rsi
0x180028da6  pop     rbx
0x180028da7  pop     rbp
0x180028da8  retn
0x180028daa  cmp     eax, 0C0000034h
0x180028daf  jnz     loc_180028FC9
0x180028db5  mov     edi, 0C0000135h
0x180028dba  jmp     short loc_180028D87
0x180028dbc  cmp     cs:LdrpAdvapi32DllHandle, 0
0x180028dc4  jz      loc_180029003
0x180028dca  mov     eax, ds:7FFE0330h
0x180028dd1  mov     ecx, 40h ; '@'
0x180028dd6  mov     edx, eax
0x180028dd8  and     edx, 3Fh
0x180028ddb  sub     ecx, edx
0x180028ddd  mov     rdx, cs:LdrpSaferIsDllAllowedRoutine
0x180028de4  ror     rdx, cl
0x180028de7  mov     rcx, [rbp+57h+FileHandle]
0x180028deb  xor     rax, rdx
0x180028dee  mov     rdx, rsi
0x180028df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028df6  mov     edi, eax
0x180028df8  cmp     eax, 0C0000225h
0x180028dfd  jz      loc_180028D5E
0x180028e03  test    edi, edi
0x180028e05  js      loc_180028D75
0x180028e0b  jmp     loc_180028D5E
0x180028e10  call    RtlGetCurrentServiceSessionId
0x180028e15  test    eax, eax
0x180028e17  jz      loc_180028EF6
0x180028e1d  mov     rax, gs:60h
0x180028e26  mov     rcx, [rax+90h]
0x180028e2d  add     rcx, 22Bh
0x180028e34  test    byte ptr [rcx], 20h
0x180028e37  jz      loc_180028BAC
0x180028e3d  mov     r9b, 0FFh
0x180028e40  mov     qword ptr [rsp+0F0h+OpenOptions], r12
0x180028e45  movzx   r8d, r9b
0x180028e49  mov     qword ptr [rsp+0F0h+ShareAccess], r12
0x180028e4e  mov     ecx, 1485h
0x180028e53  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180028e5a  call    LdrpLogEtwEvent
0x180028e5f  jmp     loc_180028BAC
0x180028e64  call    RtlGetCurrentServiceSessionId
0x180028e69  test    eax, eax
0x180028e6b  jz      short loc_180028E84
0x180028e6d  mov     rax, gs:60h
0x180028e76  mov     r13, [rax+90h]
0x180028e7d  add     r13, 22Bh
0x180028e84  test    byte ptr [r13+0], 20h
0x180028e89  jz      loc_180028D4C
0x180028e8f  mov     r9b, 0FFh
0x180028e92  mov     qword ptr [rsp+0F0h+OpenOptions], 0
0x180028e9b  movzx   r8d, r9b
0x180028e9f  mov     qword ptr [rsp+0F0h+ShareAccess], 0
0x180028ea8  mov     ecx, 1486h
0x180028ead  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180028eb4  call    LdrpLogEtwEvent
0x180028eb9  jmp     loc_180028D4C
0x180028ebe  mov     rax, gs:60h
0x180028ec7  mov     rcx, [rax+90h]
0x180028ece  add     rcx, 22Ah
0x180028ed5  jmp     loc_180028B8B
0x180028eda  mov     rax, gs:60h
0x180028ee3  mov     r15, [rax+90h]
0x180028eea  add     r15, 22Ah
0x180028ef1  jmp     loc_180028D30
0x180028ef6  mov     rcx, r13
0x180028ef9  jmp     loc_180028E34
0x180028efe  mov     rdx, [rbp+57h+FileHandle]
0x180028f02  mov     rcx, rbx
0x180028f05  call    LdrpValidateIntegrityContinuity
0x180028f0a  mov     edi, eax
0x180028f0c  test    eax, eax
0x180028f0e  jns     loc_180028C26
0x180028f14  cmp     cs:LdrpEnforceIntegrityContinuity, 0
0x180028f1b  jnz     loc_180028D7E
0x180028f21  jmp     loc_180028C26
0x180028f26  test    edi, edi
0x180028f28  js      loc_180028D75
0x180028f2e  mov     rax, [rbp+57h+FileHandle]
0x180028f32  mov     [rbx+0B8h], rax
0x180028f39  mov     rax, [rbp+57h+Handle]
0x180028f3d  mov     [rbx+18h], rax
0x180028f41  jmp     loc_180028D87
0x180028f46  mov     [rbp+57h+arg_10], 0
0x180028f4d  mov     rax, gs:60h
0x180028f56  mov     [rbp+57h+arg_0], 0
0x180028f5a  test    byte ptr [rax+3], 10h
0x180028f5e  jnz     loc_180028C36
0x180028f64  mov     rdx, [rbx+38h]
0x180028f68  lea     rax, [rbp+57h+arg_0]
0x180028f6c  mov     rcx, [rbp+57h+FileHandle]
0x180028f70  lea     r8, [rbp+57h+arg_10]
0x180028f74  mov     r9b, 8
0x180028f77  mov     qword ptr [rsp+0F0h+ShareAccess], rax
0x180028f7c  call    LdrpSetModuleSigningLevel
0x180028f81  mov     edi, eax
0x180028f83  test    eax, eax
0x180028f85  js      loc_180028D7E
0x180028f8b  jmp     loc_180028C36
0x180028f90  mov     ecx, edi
0x180028f92  call    LdrAppxHandleIntegrityFailure
0x180028f97  mov     rbx, [rbp+57h+var_A8]
0x180028f9b  mov     edi, eax
0x180028f9d  mov     edx, 1485h
0x180028fa2  mov     r9, rbx
0x180028fa5  xor     r8d, r8d
0x180028fa8  mov     ecx, edi
0x180028faa  call    LdrpLogError
0x180028faf  jmp     loc_180028D7E
0x180028fb4  test    dword ptr [rbx+20h], 800h
0x180028fbb  mov     eax, 1100000h
0x180028fc0  cmovz   r12d, eax
0x180028fc4  jmp     loc_180028C43
0x180028fc9  cmp     eax, 0C000003Ah
0x180028fce  jz      loc_180028DB5
0x180028fd4  cmp     eax, 0C0000022h
0x180028fd9  jnz     loc_180028D87
0x180028fdf  test    r12d, r12d
0x180028fe2  jnz     loc_180028D87
0x180028fe8  mov     rcx, rbx
0x180028feb  call    LdrpCheckComponentOnDemandEtwEvent
0x180028ff0  test    al, al
0x180028ff2  jz      loc_180028D87
0x180028ff8  mov     r12d, 1
0x180028ffe  jmp     loc_180028BE9
0x180029003  xor     edi, edi
0x180029005  jmp     loc_180028E03
```
