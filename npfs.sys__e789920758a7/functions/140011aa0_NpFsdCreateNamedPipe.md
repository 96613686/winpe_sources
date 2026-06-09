# NpFsdCreateNamedPipe

- ea: `0x140011aa0`
- end: `0x140011f56`
- name: `NpFsdCreateNamedPipe`
- size: `1206`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x14000c734`
- `0x140010ef4`
- `0x140011aa0`
- `0x140011f60`
- `0x140012730`
- `0x14001399c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140011ec5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140011ec5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011b4b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011b4b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011c10`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011e1b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011c10`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011e1b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011d0f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011e30`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011eb0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011d0f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011e30`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011eb0`
- `ntoskrnl!IofCompleteRequest` at `0x140011bc1`
- `ntoskrnl!IofCompleteRequest` at `0x140011d3a`
- `ntoskrnl!IofCompleteRequest` at `0x140011bc1`
- `ntoskrnl!IofCompleteRequest` at `0x140011d3a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011ba9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011ba9`
- `ntoskrnl!SeFreePrivileges` at `0x140011f38`
- `ntoskrnl!SeFreePrivileges` at `0x140011f38`
- `ntoskrnl!SeAccessCheck` at `0x140011ce0`
- `ntoskrnl!SeAccessCheck` at `0x140011ce0`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140011c92`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140011c92`
- `ntoskrnl!IoGetRequestorProcess` at `0x140011b18`
- `ntoskrnl!IoGetRequestorProcess` at `0x140011b18`

## pseudocode

```c
__int64 __fastcall NpFsdCreateNamedPipe(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  __int64 v3; // r15
  char v4; // si
  IRP *v5; // r14
  __int64 v6; // rbx
  char v7; // di
  PIO_SECURITY_CONTEXT SecurityContext; // rax
  struct _ACCESS_STATE *AccessState; // r12
  PACCESS_TOKEN ClientToken; // rdx
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v14; // r8
  __int64 Prefix; // rbx
  __int16 v16; // cx
  void *v17; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v19; // di
  __int64 *v20; // rbx
  IRP *v21; // rcx
  int v22; // eax
  int NewNamedPipe; // eax
  int Status; // eax
  __int16 AccessMode[4]; // [rsp+38h] [rbp-81h]
  __int64 v26; // [rsp+50h] [rbp-69h]
  int v27[4]; // [rsp+60h] [rbp-59h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+70h] [rbp-49h] BYREF
  __int64 v29[2]; // [rsp+80h] [rbp-39h] BYREF
  int v30[4]; // [rsp+90h] [rbp-29h] BYREF
  DWORD GrantedAccess; // [rsp+A0h] [rbp-19h] BYREF
  PPRIVILEGE_SET Privileges; // [rsp+A8h] [rbp-11h] BYREF
  __int64 Parameters; // [rsp+B8h] [rbp-1h]
  int v34[2]; // [rsp+C0h] [rbp+7h]
  PEPROCESS Process; // [rsp+C8h] [rbp+Fh]
  KPROCESSOR_MODE RequestorMode; // [rsp+120h] [rbp+67h]
  int AccessStatus; // [rsp+130h] [rbp+77h] BYREF
  int Options; // [rsp+138h] [rbp+7Fh]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v3 = *(_QWORD *)(a1 + 64);
  v4 = 0;
  v29[1] = (__int64)v29;
  UnicodeString = 0;
  AccessStatus = 0;
  v29[0] = (__int64)v29;
  GrantedAccess = 0;
  v5 = a2;
  Privileges = 0;
  *(_QWORD *)v34 = CurrentStackLocation->FileObject;
  v27[0] = 0;
  v6 = *(_QWORD *)(*(_QWORD *)v34 + 64LL);
  UnicodeString = *(struct _UNICODE_STRING *)(*(_QWORD *)v34 + 88LL);
  Options = CurrentStackLocation->Parameters.Create.Options;
  Parameters = (__int64)CurrentStackLocation->Parameters.CreatePipe.Parameters;
  v7 = 1;
  Process = IoGetRequestorProcess(a2);
  if ( (CurrentStackLocation->Flags & 1) != 0 )
    RequestorMode = 1;
  else
    RequestorMode = v5->RequestorMode;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  *(_OWORD *)v30 = 0;
  AccessState = SecurityContext->AccessState;
  KeEnterCriticalRegion();
  if ( v5->RequestorMode == 1 )
  {
    ClientToken = AccessState->SubjectSecurityContext.ClientToken;
    if ( !ClientToken )
      ClientToken = AccessState->SubjectSecurityContext.PrimaryToken;
  }
  else
  {
    ClientToken = 0;
  }
  AccessStatus = NpTranslateAlias(&UnicodeString, ClientToken, v27);
  v12 = 2;
  if ( AccessStatus >= 0 )
  {
    if ( v6 )
    {
      if ( **(_WORD **)(v6 + 24) != 518 || (*(_QWORD *)(v6 + 32) & 1) == 0 )
        goto LABEL_9;
      Prefix = 0;
      if ( !UnicodeString.Length )
      {
LABEL_16:
        Options = HIBYTE(Options);
        if ( Prefix && *(_WORD *)Prefix == 514 )
        {
          if ( LOWORD(v30[0]) )
          {
            v7 = 0;
            Status = -1073741773;
          }
          else
          {
            ExAcquirePushLockExclusiveEx(Prefix + 128, 0, v12, v11);
            ExReleasePushLockExclusiveEx(v3 + 192, 0);
            v4 = 0;
            *(_OWORD *)&v5->IoStatus.Status = *(_OWORD *)NpCreateExistingNamedPipe(
                                                           v30,
                                                           *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId
                                                                     + 16),
                                                           AccessState,
                                                           RequestorMode,
                                                           Options,
                                                           CurrentStackLocation->Parameters.Create.ShareAccess,
                                                           Parameters,
                                                           v26,
                                                           (__int64)v29);
            Status = v5->IoStatus.Status;
          }
          AccessStatus = Status;
          if ( v7 )
            ExReleasePushLockExclusiveEx(Prefix + 128, 0);
          goto LABEL_28;
        }
        v16 = v30[0];
        if ( !LOWORD(v30[0]) )
          goto LABEL_33;
        if ( **(_WORD **)&v30[2] == 92 )
          v16 = LOWORD(v30[0]) - 2;
        if ( v16 )
        {
          if ( !Prefix )
          {
            v17 = *(void **)(v3 + 136);
            LODWORD(Prefix) = 0;
LABEL_24:
            if ( v17 )
            {
              Privileges = 0;
              GenericMapping = IoGetFileObjectGenericMapping();
              v19 = SeAccessCheck(
                      v17,
                      &AccessState->SubjectSecurityContext,
                      0,
                      2u,
                      0,
                      &Privileges,
                      GenericMapping,
                      RequestorMode,
                      &GrantedAccess,
                      &AccessStatus);
              if ( Privileges )
                SeFreePrivileges(Privileges);
              if ( !v19 )
                goto LABEL_28;
            }
            goto LABEL_35;
          }
          if ( *(_WORD *)Prefix == 515 )
          {
            v17 = *(void **)(Prefix + 152);
            goto LABEL_24;
          }
        }
        else
        {
LABEL_33:
          if ( !Prefix )
          {
            LODWORD(Prefix) = 0;
LABEL_35:
            AccessMode[0] = CurrentStackLocation->Parameters.Create.ShareAccess;
            v22 = *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 16);
            *(struct _UNICODE_STRING *)v30 = UnicodeString;
            NewNamedPipe = NpCreateNewNamedPipe(
                             v3,
                             Prefix,
                             v34[0],
                             (int)v30,
                             v22,
                             (__int64)AccessState,
                             Options,
                             AccessMode[0],
                             Parameters,
                             Process,
                             (__int64)v29,
                             (__int64)&v5->IoStatus);
LABEL_36:
            AccessStatus = NewNamedPipe;
LABEL_28:
            if ( v4 )
              ExReleasePushLockExclusiveEx(v3 + 192, 0);
            goto LABEL_30;
          }
          if ( *(_WORD *)Prefix == 519 )
          {
            NewNamedPipe = NpOpenSymlink(Prefix, v5);
            goto LABEL_36;
          }
        }
        NewNamedPipe = -1073741773;
        goto LABEL_36;
      }
      if ( UnicodeString.Length < 2u || *UnicodeString.Buffer == 92 )
      {
LABEL_9:
        AccessStatus = -1073741773;
        goto LABEL_10;
      }
    }
    else if ( UnicodeString.Length <= 2u || *UnicodeString.Buffer != 92 )
    {
      AccessStatus = -1073741773;
LABEL_30:
      v20 = (__int64 *)v29[0];
      if ( (__int64 *)v29[0] != v29 )
      {
        do
        {
          v21 = (IRP *)(v20 - 21);
          v20 = (__int64 *)*v20;
          IofCompleteRequest(v21, 2);
        }
        while ( v20 != v29 );
        v5 = a2;
      }
      goto LABEL_10;
    }
    ExAcquirePushLockExclusiveEx(v3 + 192, 0, 2, v11);
    LOBYTE(v14) = 1;
    v4 = 1;
    Prefix = NpFindPrefix(v3, &UnicodeString, v14, v30);
    goto LABEL_16;
  }
LABEL_10:
  KeLeaveCriticalRegion();
  v5->IoStatus.Status = AccessStatus;
  IofCompleteRequest(v5, 2);
  if ( v27[0] )
    RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)AccessStatus;
}

```

## disassembly

```asm
0x140011aa0  mov     [rsp-8+arg_8], rdx
0x140011aa5  push    rbp
0x140011aa6  push    rbx
0x140011aa7  push    rsi
0x140011aa8  push    rdi
0x140011aa9  push    r12
0x140011aab  push    r13
0x140011aad  push    r14
0x140011aaf  push    r15
0x140011ab1  lea     rbp, [rsp-1Fh]
0x140011ab6  sub     rsp, 0D8h
0x140011abd  mov     r13, [rdx+0B8h]
0x140011ac4  lea     rax, [rbp+57h+var_90]
0x140011ac8  mov     r15, [rcx+40h]
0x140011acc  xor     esi, esi
0x140011ace  mov     [rbp+57h+var_88], rax
0x140011ad2  xorps   xmm0, xmm0
0x140011ad5  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x140011ad9  mov     [rbp+57h+arg_10], esi
0x140011adc  lea     rax, [rbp+57h+var_90]
0x140011ae0  mov     [rbp+57h+var_90], rax
0x140011ae4  mov     rcx, rdx; Irp
0x140011ae7  mov     [rbp+57h+var_70], esi
0x140011aea  mov     r14, rdx
0x140011aed  mov     [rbp+57h+var_68], rsi
0x140011af1  mov     rax, [r13+30h]
0x140011af5  mov     qword ptr [rbp+57h+var_50], rax
0x140011af9  mov     [rbp+57h+var_B0], esi
0x140011afc  movups  xmm0, xmmword ptr [rax+58h]
0x140011b00  mov     rbx, [rax+40h]
0x140011b04  movdqu  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x140011b09  mov     eax, [r13+10h]
0x140011b0d  mov     [rbp+57h+arg_18], eax
0x140011b10  mov     rax, [r13+20h]
0x140011b14  mov     [rbp+57h+var_58], rax
0x140011b18  call    cs:__imp_IoGetRequestorProcess
0x140011b1f  nop     dword ptr [rax+rax+00h]
0x140011b24  mov     dil, 1
0x140011b27  mov     [rbp+57h+Process], rax
0x140011b2b  test    [r13+2], dil
0x140011b2f  jnz     loc_140011ED6
0x140011b35  mov     al, [r14+40h]
0x140011b39  mov     [rbp+57h+arg_0], al
0x140011b3c  mov     rax, [r13+8]
0x140011b40  xorps   xmm0, xmm0
0x140011b43  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x140011b47  mov     r12, [rax+8]
0x140011b4b  call    cs:__imp_KeEnterCriticalRegion
0x140011b52  nop     dword ptr [rax+rax+00h]
0x140011b57  cmp     [r14+40h], dil
0x140011b5b  jnz     loc_140011EDF
0x140011b61  mov     rdx, [r12+20h]
0x140011b66  test    rdx, rdx
0x140011b69  jnz     short loc_140011B70
0x140011b6b  mov     rdx, [r12+30h]
0x140011b70  lea     r8, [rbp+57h+var_B0]
0x140011b74  lea     rcx, [rbp+57h+UnicodeString]
0x140011b78  call    NpTranslateAlias
0x140011b7d  mov     [rbp+57h+arg_10], eax
0x140011b80  mov     r8d, 2
0x140011b86  test    eax, eax
0x140011b88  js      short loc_140011BA9
0x140011b8a  test    rbx, rbx
0x140011b8d  jz      short loc_140011BEE
0x140011b8f  mov     rax, [rbx+18h]
0x140011b93  mov     ecx, 206h
0x140011b98  cmp     [rax], cx
0x140011b9b  jz      loc_140011DCD
0x140011ba1  mov     eax, 0C0000033h
0x140011ba6  mov     [rbp+57h+arg_10], eax
0x140011ba9  call    cs:__imp_KeLeaveCriticalRegion
0x140011bb0  nop     dword ptr [rax+rax+00h]
0x140011bb5  mov     eax, [rbp+57h+arg_10]
0x140011bb8  mov     dl, 2; PriorityBoost
0x140011bba  mov     rcx, r14; Irp
0x140011bbd  mov     [r14+30h], eax
0x140011bc1  call    cs:__imp_IofCompleteRequest
0x140011bc8  nop     dword ptr [rax+rax+00h]
0x140011bcd  cmp     [rbp+57h+var_B0], esi
0x140011bd0  jnz     loc_140011EC1
0x140011bd6  mov     eax, [rbp+57h+arg_10]
0x140011bd9  add     rsp, 0D8h
0x140011be0  pop     r15
0x140011be2  pop     r14
0x140011be4  pop     r13
0x140011be6  pop     r12
0x140011be8  pop     rdi
0x140011be9  pop     rsi
0x140011bea  pop     rbx
0x140011beb  pop     rbp
0x140011bec  retn
0x140011bee  cmp     [rbp+57h+UnicodeString.Length], r8w
0x140011bf3  jbe     loc_140011F49
0x140011bf9  mov     rax, [rbp+57h+UnicodeString.Buffer]
0x140011bfd  cmp     word ptr [rax], 5Ch ; '\'
0x140011c01  jnz     loc_140011F49
0x140011c07  xor     edx, edx
0x140011c09  lea     rcx, [r15+0C0h]
0x140011c10  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140011c17  nop     dword ptr [rax+rax+00h]
0x140011c1c  lea     r9, [rbp+57h+var_80]
0x140011c20  mov     r8b, dil
0x140011c23  lea     rdx, [rbp+57h+UnicodeString]
0x140011c27  mov     rcx, r15
0x140011c2a  mov     sil, dil
0x140011c2d  call    NpFindPrefix
0x140011c32  xor     edx, edx
0x140011c34  mov     rbx, rax
0x140011c37  shr     [rbp+57h+arg_18], 18h
0x140011c3b  test    rbx, rbx
0x140011c3e  jz      short loc_140011C4E
0x140011c40  mov     eax, 202h
0x140011c45  cmp     [rbx], ax
0x140011c48  jz      loc_140011E08
0x140011c4e  movzx   ecx, word ptr [rbp+57h+var_80]
0x140011c52  test    cx, cx
0x140011c55  jz      loc_140011D58
0x140011c5b  mov     rax, qword ptr [rbp+57h+var_80+8]
0x140011c5f  cmp     word ptr [rax], 5Ch ; '\'
0x140011c63  jz      loc_140011EE7
0x140011c69  test    cx, cx
0x140011c6c  jz      loc_140011D58
0x140011c72  test    rbx, rbx
0x140011c75  jnz     loc_140011F22
0x140011c7b  mov     rdi, [r15+88h]
0x140011c82  mov     rbx, rdx
0x140011c85  test    rdi, rdi
0x140011c88  jz      loc_140011D64
0x140011c8e  mov     [rbp+57h+var_68], rdx
0x140011c92  call    cs:__imp_IoGetFileObjectGenericMapping
0x140011c99  nop     dword ptr [rax+rax+00h]
0x140011c9e  mov     r8b, [rbp+57h+arg_0]
0x140011ca2  lea     rcx, [rbp+57h+arg_10]
0x140011ca6  mov     [rsp+110h+AccessStatus], rcx; AccessStatus
0x140011cab  lea     rdx, [r12+20h]; SubjectSecurityContext
0x140011cb0  lea     rcx, [rbp+57h+var_70]
0x140011cb4  mov     r9d, 2; DesiredAccess
0x140011cba  mov     [rsp+110h+GrantedAccess], rcx; GrantedAccess
0x140011cbf  mov     rcx, rdi; SecurityDescriptor
0x140011cc2  mov     byte ptr [rsp+110h+AccessMode], r8b; AccessMode
0x140011cc7  xor     r8d, r8d; SubjectContextLocked
0x140011cca  mov     [rsp+110h+GenericMapping], rax; GenericMapping
0x140011ccf  lea     rax, [rbp+57h+var_68]
0x140011cd3  mov     [rsp+110h+Privileges], rax; Privileges
0x140011cd8  mov     [rsp+110h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x140011ce0  call    cs:__imp_SeAccessCheck
0x140011ce7  nop     dword ptr [rax+rax+00h]
0x140011cec  mov     rcx, [rbp+57h+var_68]; Privileges
0x140011cf0  mov     dil, al
0x140011cf3  test    rcx, rcx
0x140011cf6  jnz     loc_140011F38
0x140011cfc  test    dil, dil
0x140011cff  jnz     short loc_140011D64
0x140011d01  test    sil, sil
0x140011d04  jz      short loc_140011D1B
0x140011d06  lea     rcx, [r15+0C0h]
0x140011d0d  xor     edx, edx
0x140011d0f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140011d16  nop     dword ptr [rax+rax+00h]
0x140011d1b  xor     esi, esi
0x140011d1d  mov     rbx, [rbp+57h+var_90]
0x140011d21  lea     rax, [rbp+57h+var_90]
0x140011d25  cmp     rbx, rax
0x140011d28  jz      loc_140011BA9
0x140011d2e  lea     rcx, [rbx-0A8h]; Irp
0x140011d35  mov     dl, 2; PriorityBoost
0x140011d37  mov     rbx, [rbx]
0x140011d3a  call    cs:__imp_IofCompleteRequest
0x140011d41  nop     dword ptr [rax+rax+00h]
0x140011d46  lea     rax, [rbp+57h+var_90]
0x140011d4a  cmp     rbx, rax
0x140011d4d  jnz     short loc_140011D2E
0x140011d4f  mov     r14, [rbp+57h+arg_8]
0x140011d53  jmp     loc_140011BA9
0x140011d58  test    rbx, rbx
0x140011d5b  jnz     loc_140011EFE
0x140011d61  mov     rbx, rdx
0x140011d64  mov     rcx, [r13+8]
0x140011d68  lea     rax, [r14+30h]
0x140011d6c  movaps  xmm0, xmmword ptr [rbp+57h+UnicodeString.Length]
0x140011d70  lea     r9, [rbp+57h+var_80]; int
0x140011d74  mov     r8, qword ptr [rbp+57h+var_50]; int
0x140011d78  mov     rdx, rbx; int
0x140011d7b  mov     [rsp+110h+var_B8], rax; __int64
0x140011d80  lea     rax, [rbp+57h+var_90]
0x140011d84  mov     [rsp+110h+var_C0], rax; __int64
0x140011d89  mov     rax, [rbp+57h+Process]
0x140011d8d  mov     [rsp+110h+AccessStatus], rax; Process
0x140011d92  mov     rax, [rbp+57h+var_58]
0x140011d96  mov     [rsp+110h+GrantedAccess], rax; __int64
0x140011d9b  movzx   eax, word ptr [r13+1Ah]
0x140011da0  mov     [rsp+110h+AccessMode], ax; __int16
0x140011da5  mov     eax, [rbp+57h+arg_18]
0x140011da8  mov     dword ptr [rsp+110h+GenericMapping], eax; int
0x140011dac  mov     eax, [rcx+10h]
0x140011daf  mov     rcx, r15; int
0x140011db2  mov     [rsp+110h+Privileges], r12; __int64
0x140011db7  movdqa  xmmword ptr [rbp+57h+var_80], xmm0
0x140011dbc  mov     [rsp+110h+PreviouslyGrantedAccess], eax; int
0x140011dc0  call    NpCreateNewNamedPipe
0x140011dc5  mov     [rbp+57h+arg_10], eax
0x140011dc8  jmp     loc_140011D01
0x140011dcd  mov     rax, [rbx+20h]
0x140011dd1  test    dil, al
0x140011dd4  jz      loc_140011BA1
0x140011dda  movzx   eax, [rbp+57h+UnicodeString.Length]
0x140011dde  xor     edx, edx
0x140011de0  mov     ebx, edx
0x140011de2  test    ax, ax
0x140011de5  jz      loc_140011C37
0x140011deb  cmp     ax, r8w
0x140011def  jb      loc_140011BA1
0x140011df5  mov     rax, [rbp+57h+UnicodeString.Buffer]
0x140011df9  cmp     word ptr [rax], 5Ch ; '\'
0x140011dfd  jnz     loc_140011C09
0x140011e03  jmp     loc_140011BA1
0x140011e08  cmp     word ptr [rbp+57h+var_80], dx
0x140011e0c  jnz     loc_140011EF4
0x140011e12  lea     rcx, [rbx+80h]
0x140011e19  xor     edx, edx
0x140011e1b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140011e22  nop     dword ptr [rax+rax+00h]
0x140011e27  lea     rcx, [r15+0C0h]
0x140011e2e  xor     edx, edx
0x140011e30  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140011e37  nop     dword ptr [rax+rax+00h]
0x140011e3c  mov     rcx, [r13+8]
0x140011e40  lea     rax, [rbp+57h+var_90]
0x140011e44  mov     r8b, [rbp+57h+arg_0]
0x140011e48  xor     sil, sil
0x140011e4b  mov     r9, qword ptr [rbp+57h+var_50]
0x140011e4f  mov     rdx, r15
0x140011e52  mov     [rsp+110h+var_B8], rax; __int64
0x140011e57  mov     rax, [rbp+57h+var_58]
0x140011e5b  mov     [rsp+110h+AccessStatus], rax; __int64
0x140011e60  movzx   eax, word ptr [r13+1Ah]
0x140011e65  mov     word ptr [rsp+110h+GrantedAccess], ax; __int16
0x140011e6a  mov     eax, [rbp+57h+arg_18]
0x140011e6d  mov     dword ptr [rsp+110h+AccessMode], eax; int
0x140011e71  mov     eax, [rcx+10h]
0x140011e74  lea     rcx, [rbp+57h+var_80]; AccessStatus
0x140011e78  mov     byte ptr [rsp+110h+GenericMapping], r8b; KPROCESSOR_MODE
0x140011e7d  mov     r8, rbx
0x140011e80  mov     [rsp+110h+Privileges], r12; AccessState
0x140011e85  mov     [rsp+110h+PreviouslyGrantedAccess], eax; int
0x140011e89  call    NpCreateExistingNamedPipe
0x140011e8e  movups  xmm0, xmmword ptr [rax]
0x140011e91  movdqu  xmmword ptr [r14+30h], xmm0
0x140011e97  mov     eax, [r14+30h]
0x140011e9b  mov     [rbp+57h+arg_10], eax
0x140011e9e  test    dil, dil
0x140011ea1  jz      loc_140011D01
0x140011ea7  lea     rcx, [rbx+80h]
0x140011eae  xor     edx, edx
0x140011eb0  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140011eb7  nop     dword ptr [rax+rax+00h]
0x140011ebc  jmp     loc_140011D01
0x140011ec1  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x140011ec5  call    cs:__imp_RtlFreeUnicodeString
0x140011ecc  nop     dword ptr [rax+rax+00h]
0x140011ed1  jmp     loc_140011BD6
0x140011ed6  mov     [rbp+57h+arg_0], dil
0x140011eda  jmp     loc_140011B3C
0x140011edf  mov     rdx, rsi
0x140011ee2  jmp     loc_140011B70
0x140011ee7  mov     eax, 0FFFEh
0x140011eec  add     cx, ax
0x140011eef  jmp     loc_140011C69
0x140011ef4  mov     dil, dl
0x140011ef7  mov     eax, 0C0000033h
0x140011efc  jmp     short loc_140011E9B
0x140011efe  mov     eax, 207h
0x140011f03  cmp     [rbx], ax
0x140011f06  jnz     short loc_140011F18
0x140011f08  mov     rdx, r14
0x140011f0b  mov     rcx, rbx
0x140011f0e  call    NpOpenSymlink
0x140011f13  jmp     loc_140011DC5
0x140011f18  mov     eax, 0C0000033h
0x140011f1d  jmp     loc_140011DC5
0x140011f22  mov     eax, 203h
0x140011f27  cmp     [rbx], ax
0x140011f2a  jnz     short loc_140011F18
0x140011f2c  mov     rdi, [rbx+98h]
0x140011f33  jmp     loc_140011C85
0x140011f38  call    cs:__imp_SeFreePrivileges
0x140011f3f  nop     dword ptr [rax+rax+00h]
0x140011f44  jmp     loc_140011CFC
0x140011f49  mov     eax, 0C0000033h
0x140011f4e  mov     [rbp+57h+arg_10], eax
0x140011f51  jmp     loc_140011D1D
```
