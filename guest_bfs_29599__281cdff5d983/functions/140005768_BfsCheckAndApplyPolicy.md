# BfsCheckAndApplyPolicy

- ea: `0x140005768`
- end: `0x140005d96`
- name: `BfsCheckAndApplyPolicy`
- size: `1582`
- prototype: `char __fastcall(PVOID FltObject, PVOID, PACCESS_TOKEN Token, PFLT_CALLBACK_DATA Data, __int64 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140002620`

## callees

- `0x140001008`
- `0x140003614`
- `0x1400052c8`
- `0x140005768`
- `0x1400061d0`
- `0x1400067c0`
- `0x140006c84`
- `0x140006db4`
- `0x140006fa4`
- `0x1400071d4`
- `0x140009014`
- `0x14000a4f4`
- `0x1400100e0`
- `0x1400104ec`
- `0x140013860`

## import_xrefs

- `ntoskrnl!SeExports` at `0x140005a7b`
- `ntoskrnl!SeExports` at `0x140005ab9`
- `ntoskrnl!RtlCheckTokenCapability` at `0x140005a92`
- `ntoskrnl!RtlCheckTokenCapability` at `0x140005ad0`
- `ntoskrnl!RtlCheckTokenCapability` at `0x140005a92`
- `ntoskrnl!RtlCheckTokenCapability` at `0x140005ad0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005963`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000597a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005963`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000597a`
- `ntoskrnl!SeQueryInformationToken` at `0x1400057cf`
- `ntoskrnl!SeQueryInformationToken` at `0x140005829`
- `ntoskrnl!SeQueryInformationToken` at `0x1400057cf`
- `ntoskrnl!SeQueryInformationToken` at `0x140005829`
- `ntoskrnl!ExAllocatePool2` at `0x140005d2c`
- `ntoskrnl!ExAllocatePool2` at `0x140005d2c`
- `FLTMGR!FltGetFileNameInformation` at `0x140005847`
- `FLTMGR!FltGetFileNameInformation` at `0x140005d00`
- `FLTMGR!FltGetFileNameInformation` at `0x140005847`
- `FLTMGR!FltGetFileNameInformation` at `0x140005d00`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000594c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000594c`
- `FLTMGR!FltReferenceFileNameInformation` at `0x140005d66`
- `FLTMGR!FltReferenceFileNameInformation` at `0x140005d66`

## pseudocode

```c
char __fastcall BfsCheckAndApplyPolicy(
        PVOID FltObject,
        PVOID a2,
        PACCESS_TOKEN Token,
        PFLT_CALLBACK_DATA Data,
        __int64 *a5)
{
  char v9; // di
  NTSTATUS v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // ecx
  int PolicyEntry; // edi
  int v15; // r8d
  int v16; // r9d
  volatile signed __int32 *v17; // rbx
  char *v19; // r9
  int Policy; // eax
  NTSTATUS v21; // ecx
  int v22; // r8d
  int v23; // r9d
  int v24; // eax
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  int v31; // eax
  __int64 Pool2; // rax
  int v33; // [rsp+20h] [rbp-91h]
  __int64 v34; // [rsp+20h] [rbp-91h]
  __int64 v35; // [rsp+20h] [rbp-91h]
  _BYTE v36[3]; // [rsp+31h] [rbp-80h] BYREF
  int v37; // [rsp+34h] [rbp-7Dh] BYREF
  char v38; // [rsp+38h] [rbp-79h] BYREF
  char v39; // [rsp+39h] [rbp-78h] BYREF
  PVOID v40; // [rsp+40h] [rbp-71h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+48h] [rbp-69h] BYREF
  PVOID TokenInformation; // [rsp+50h] [rbp-61h] BYREF
  PVOID P; // [rsp+58h] [rbp-59h] BYREF
  __int128 v44; // [rsp+60h] [rbp-51h] BYREF
  __int128 v45; // [rsp+70h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v46; // [rsp+80h] [rbp-31h] BYREF
  int *v47; // [rsp+A0h] [rbp-11h]
  __int64 v48; // [rsp+A8h] [rbp-9h]

  v38 = 0;
  TokenInformation = 0;
  v40 = 0;
  FileNameInformation = 0;
  P = 0;
  v39 = 0;
  v9 = 0;
  v45 = 0;
  v10 = SeQueryInformationToken(Token, TokenUser, &TokenInformation);
  if ( v10 >= 0 )
  {
    v10 = SeQueryInformationToken(Token, TokenAppContainerSid, &P);
    if ( v10 >= 0 )
    {
      v10 = FltGetFileNameInformation(Data, 0x101u, &FileNameInformation);
      if ( v10 == -1073741311 )
      {
        v44 = (unsigned __int64)Token;
        v10 = BfsQueueDeferredWorkItemAndWait(FltObject, a2, Data, (__int64)&BfsQueryFileNameInformationCallback);
        FileNameInformation = (PFLT_FILE_NAME_INFORMATION)*((_QWORD *)&v44 + 1);
      }
      if ( v10 >= 0 )
      {
        v34 = *(_QWORD *)P;
        if ( (unsigned __int8)BfsPolicyEntryExists(FltObject, a2, &gBfsPolicyTable, *(_QWORD *)TokenInformation) )
        {
          v34 = *(_QWORD *)P;
          PolicyEntry = BfsGetPolicyEntry(FltObject, a2, &gBfsPolicyTable, *(_QWORD *)TokenInformation);
          if ( PolicyEntry < 0 )
            goto LABEL_10;
          v44 = *(_OWORD *)BfsGetFileName(&v44, FileNameInformation);
          v17 = (volatile signed __int32 *)v40;
          if ( (unsigned int)((__int64 (*)(void))Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline)() )
            v19 = &v39;
          else
            v19 = 0;
          Policy = BfsGetPolicy(*((_QWORD *)v40 + 6), &FileNameInformation->Volume, &v44, v19);
          if ( Policy )
          {
            if ( Policy != 1 )
            {
              if ( Policy != 2 )
                goto LABEL_13;
              v9 = 0;
              if ( !(unsigned __int8)BfsQueryAccessOnly((Data->Iopb->Parameters.Create.Options & 1) + 1, Data) )
              {
                if ( (unsigned __int8)BfsQueryAccessOnly((Data->Iopb->Parameters.Create.Options & 1) + 1, Data) )
                  goto LABEL_14;
                goto LABEL_66;
              }
            }
LABEL_56:
            LODWORD(v34) = (_DWORD)a5;
            v31 = BfsApplyPolicyAsUser(Data, Token, FileNameInformation, v17);
            v21 = v31;
            if ( v31 >= 0 )
            {
              if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline((unsigned int)v31) )
                *(_BYTE *)(*a5 + 72) = v39;
LABEL_61:
              v9 = 1;
              goto LABEL_14;
            }
            goto LABEL_57;
          }
        }
        else
        {
          PolicyEntry = BfsGetNotPresentPolicyEntry(&gBfsPolicyTable, *(_QWORD *)TokenInformation, *(_QWORD *)P, &v40);
          if ( PolicyEntry < 0 )
          {
LABEL_10:
            if ( (unsigned int)dword_140019000 > 3 )
            {
              v37 = PolicyEntry;
              v47 = &v37;
              v48 = 4;
              tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_140016D91, v15, v16, v34, &v46);
            }
            goto LABEL_12;
          }
          v17 = (volatile signed __int32 *)v40;
        }
        v36[0] = 0;
        if ( (unsigned int)((__int64 (*)(void))Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline)() )
        {
          v24 = *((_DWORD *)v17 + 27);
          if ( v24 )
          {
            v36[0] = v24 == 1;
          }
          else
          {
            PolicyEntry = RtlCheckTokenCapability(0, *(_QWORD *)&SeExports[1].SeUnsolicitedInputPrivilege, v36);
            v21 = 2 - (v36[0] != 0);
            *((_DWORD *)v17 + 27) = v21;
          }
        }
        else
        {
          PolicyEntry = RtlCheckTokenCapability(0, *(_QWORD *)&SeExports[1].SeUnsolicitedInputPrivilege, v36);
        }
        if ( PolicyEntry < 0 )
        {
          if ( PolicyEntry != -1073741790 )
          {
            if ( (unsigned int)dword_140019000 <= 3 )
              goto LABEL_13;
            v37 = PolicyEntry;
            goto LABEL_65;
          }
          goto LABEL_66;
        }
        v9 = 0;
        if ( !v36[0] )
          goto LABEL_66;
        v25 = BfsFileInPublisherDirectory(Token, FileNameInformation, &v38, &v45);
        if ( v25 < 0 )
        {
          if ( (unsigned int)dword_140019000 > 3 )
          {
            v37 = v25;
            v47 = &v37;
            v48 = 4;
            tlgWriteTransfer_EtwWriteTransfer(v25, (int)&byte_140016D91, v26, v27, v34, &v46);
          }
          goto LABEL_14;
        }
        if ( !v38 )
        {
LABEL_66:
          if ( FileNameInformation || (v21 = FltGetFileNameInformation(Data, 0x101u, &FileNameInformation), v21 >= 0) )
          {
            Pool2 = *a5;
            if ( !*a5 )
            {
              Pool2 = ExAllocatePool2(256, 96, 1131636290);
              *a5 = Pool2;
              if ( !Pool2 )
              {
                if ( (unsigned int)dword_140019000 <= 3 )
                  goto LABEL_13;
                v37 = -1073741801;
                goto LABEL_65;
              }
            }
            *(_DWORD *)(Pool2 + 8) = 1;
            FltReferenceFileNameInformation(FileNameInformation);
            *(_QWORD *)(*a5 + 48) = FileNameInformation;
            *(_QWORD *)(*a5 + 64) = v17;
            _InterlockedIncrement(v17 + 36);
            *(_DWORD *)*a5 |= 1u;
            goto LABEL_61;
          }
LABEL_57:
          if ( (unsigned int)dword_140019000 <= 3 )
            goto LABEL_13;
          v37 = v21;
LABEL_65:
          v48 = 4;
          v47 = &v37;
          tlgWriteTransfer_EtwWriteTransfer(v21, (int)&byte_140016D91, v22, v23, v34, &v46);
          goto LABEL_13;
        }
        if ( v17 )
        {
          if ( *((_DWORD *)v17 + 14) != 2 )
            goto LABEL_52;
          BfsDereferencePolicyEntryEx((PVOID)v17);
        }
        v35 = *(_QWORD *)P;
        v28 = BfsGetPolicyEntry(FltObject, a2, &gBfsPolicyTable, *(_QWORD *)TokenInformation);
        if ( v28 < 0 )
        {
LABEL_49:
          if ( (unsigned int)dword_140019000 <= 3 )
          {
LABEL_12:
            v17 = (volatile signed __int32 *)v40;
LABEL_13:
            v9 = 0;
            goto LABEL_14;
          }
          v37 = v28;
          v47 = &v37;
          v48 = 4;
          tlgWriteTransfer_EtwWriteTransfer(v28, (int)&byte_140016D91, v29, v30, v35, &v46);
          v17 = (volatile signed __int32 *)v40;
LABEL_14:
          if ( v17 )
            BfsDereferencePolicyEntryEx((PVOID)v17);
          goto LABEL_16;
        }
        v17 = (volatile signed __int32 *)v40;
LABEL_52:
        if ( *((_DWORD *)v17 + 14) == 268435457 )
        {
          v35 = *(_QWORD *)P;
          v28 = BfsGetPolicyEntry(FltObject, a2, &gBfsPolicyTable, *(_QWORD *)TokenInformation);
          if ( v28 < 0 )
            goto LABEL_49;
          v17 = (volatile signed __int32 *)v40;
          BfsDereferencePolicyEntryEx(v40);
        }
        BfsAddOrModifyEntry(*((_QWORD *)v17 + 6), 2, 1, 2, (__int64)&FileNameInformation->Volume, (__int64)&v45);
        goto LABEL_56;
      }
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v37 = v10;
    v47 = &v37;
    v48 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v10, (int)&byte_140016D91, v11, v12, v33, &v46);
  }
LABEL_16:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  return v9;
}

```

## disassembly

```asm
0x140005768  push    rbp
0x14000576a  push    rbx
0x14000576b  push    rsi
0x14000576c  push    rdi
0x14000576d  push    r12
0x14000576f  push    r13
0x140005771  push    r14
0x140005773  push    r15
0x140005775  lea     rbp, [rsp-17h]
0x14000577a  sub     rsp, 0C8h
0x140005781  mov     rax, cs:__security_cookie
0x140005788  xor     rax, rsp
0x14000578b  mov     [rbp+4Fh+var_50], rax
0x14000578f  mov     rsi, [rbp+4Fh+arg_20]
0x140005793  xor     ebx, ebx
0x140005795  mov     r13, r8
0x140005798  mov     [rbp+4Fh+var_C8], bl
0x14000579b  mov     r12, rdx
0x14000579e  mov     [rbp+4Fh+TokenInformation], rbx
0x1400057a2  mov     r15, rcx
0x1400057a5  mov     [rbp+4Fh+var_C0], rbx
0x1400057a9  xorps   xmm0, xmm0
0x1400057ac  mov     [rsp+100h+var_D0], bl
0x1400057b0  lea     edx, [rbx+1]; TokenInformationClass
0x1400057b3  mov     [rbp+4Fh+FileNameInformation], rbx
0x1400057b7  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x1400057bb  mov     [rbp+4Fh+P], rbx
0x1400057bf  mov     rcx, r13; Token
0x1400057c2  mov     [rbp+4Fh+var_C7], bl
0x1400057c5  mov     r14, r9
0x1400057c8  mov     dil, bl
0x1400057cb  movups  [rbp+4Fh+var_90], xmm0
0x1400057cf  call    cs:__imp_SeQueryInformationToken
0x1400057d6  nop     dword ptr [rax+rax+00h]
0x1400057db  mov     ecx, eax; int
0x1400057dd  test    eax, eax
0x1400057df  jns     short loc_14000581D
0x1400057e1  mov     eax, cs:dword_140019000
0x1400057e7  cmp     eax, 3
0x1400057ea  jbe     loc_140005943
0x1400057f0  lea     rax, [rbp+4Fh+var_CC]
0x1400057f4  mov     [rbp+4Fh+var_CC], ecx
0x1400057f7  mov     [rbp+4Fh+var_60], rax
0x1400057fb  lea     rdx, byte_140016D91; int
0x140005802  lea     rax, [rbp+4Fh+var_80]
0x140005806  mov     [rbp+4Fh+var_58], 4
0x14000580e  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140005813  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005818  jmp     loc_140005943
0x14000581d  lea     r8, [rbp+4Fh+P]; TokenInformation
0x140005821  mov     edx, 1Fh; TokenInformationClass
0x140005826  mov     rcx, r13; Token
0x140005829  call    cs:__imp_SeQueryInformationToken
0x140005830  nop     dword ptr [rax+rax+00h]
0x140005835  mov     ecx, eax
0x140005837  test    eax, eax
0x140005839  js      short loc_1400057E1
0x14000583b  lea     r8, [rbp+4Fh+FileNameInformation]; FileNameInformation
0x14000583f  mov     edx, 101h; NameOptions
0x140005844  mov     rcx, r14; CallbackData
0x140005847  call    cs:__imp_FltGetFileNameInformation
0x14000584e  nop     dword ptr [rax+rax+00h]
0x140005853  mov     ecx, eax
0x140005855  cmp     eax, 0C0000201h
0x14000585a  jnz     short loc_14000588C
0x14000585c  lea     rax, BfsQueryFileNameInformationCallback
0x140005863  mov     qword ptr [rbp+4Fh+var_A0+8], rbx
0x140005867  lea     r9, [rbp+4Fh+var_A0]
0x14000586b  mov     [rsp+100h+var_E0], rax; __int64
0x140005870  mov     r8, r14; Data
0x140005873  mov     qword ptr [rbp+4Fh+var_A0], r13
0x140005877  mov     rdx, r12; PVOID
0x14000587a  mov     rcx, r15; FltObject
0x14000587d  call    BfsQueueDeferredWorkItemAndWait
0x140005882  mov     ecx, eax
0x140005884  mov     rax, qword ptr [rbp+4Fh+var_A0+8]
0x140005888  mov     [rbp+4Fh+FileNameInformation], rax
0x14000588c  test    ecx, ecx
0x14000588e  js      loc_1400057E1
0x140005894  mov     rax, [rbp+4Fh+P]
0x140005898  lea     rdi, gBfsPolicyTable
0x14000589f  mov     r9, [rbp+4Fh+TokenInformation]
0x1400058a3  mov     r8, rdi
0x1400058a6  mov     rdx, r12
0x1400058a9  mov     rcx, [rax]
0x1400058ac  mov     r9, [r9]
0x1400058af  mov     [rsp+100h+var_E0], rcx; int
0x1400058b4  mov     rcx, r15
0x1400058b7  call    BfsPolicyEntryExists
0x1400058bc  test    al, al
0x1400058be  jz      loc_140005A3F
0x1400058c4  mov     r9, [rbp+4Fh+TokenInformation]
0x1400058c8  lea     rax, [rbp+4Fh+var_C0]
0x1400058cc  mov     [rsp+100h+var_D8], rax
0x1400058d1  mov     r8, rdi
0x1400058d4  mov     rax, [rbp+4Fh+P]
0x1400058d8  mov     rdx, r12
0x1400058db  mov     r9, [r9]
0x1400058de  mov     rcx, [rax]
0x1400058e1  mov     [rsp+100h+var_E0], rcx; int
0x1400058e6  mov     rcx, r15
0x1400058e9  call    BfsGetPolicyEntry
0x1400058ee  mov     edi, eax
0x1400058f0  test    eax, eax
0x1400058f2  jns     loc_1400059AA
0x1400058f8  mov     eax, cs:dword_140019000
0x1400058fe  cmp     eax, 3
0x140005901  jbe     short loc_14000592B
0x140005903  lea     rax, [rbp+4Fh+var_CC]
0x140005907  mov     [rbp+4Fh+var_CC], edi
0x14000590a  mov     [rbp+4Fh+var_60], rax
0x14000590e  lea     rdx, byte_140016D91; int
0x140005915  lea     rax, [rbp+4Fh+var_80]
0x140005919  mov     [rbp+4Fh+var_58], 4
0x140005921  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140005926  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000592b  mov     rbx, [rbp+4Fh+var_C0]
0x14000592f  mov     dil, [rsp+100h+var_D0]
0x140005934  test    rbx, rbx
0x140005937  jz      short loc_140005943
0x140005939  xor     edx, edx
0x14000593b  mov     rcx, rbx; P
0x14000593e  call    BfsDereferencePolicyEntryEx
0x140005943  mov     rcx, [rbp+4Fh+FileNameInformation]; FileNameInformation
0x140005947  test    rcx, rcx
0x14000594a  jz      short loc_140005958
0x14000594c  call    cs:__imp_FltReleaseFileNameInformation
0x140005953  nop     dword ptr [rax+rax+00h]
0x140005958  mov     rcx, [rbp+4Fh+TokenInformation]; P
0x14000595c  test    rcx, rcx
0x14000595f  jz      short loc_14000596F
0x140005961  xor     edx, edx; Tag
0x140005963  call    cs:__imp_ExFreePoolWithTag
0x14000596a  nop     dword ptr [rax+rax+00h]
0x14000596f  mov     rcx, [rbp+4Fh+P]; P
0x140005973  test    rcx, rcx
0x140005976  jz      short loc_140005986
0x140005978  xor     edx, edx; Tag
0x14000597a  call    cs:__imp_ExFreePoolWithTag
0x140005981  nop     dword ptr [rax+rax+00h]
0x140005986  mov     al, dil
0x140005989  mov     rcx, [rbp+4Fh+var_50]
0x14000598d  xor     rcx, rsp; StackCookie
0x140005990  call    __security_check_cookie
0x140005995  add     rsp, 0C8h
0x14000599c  pop     r15
0x14000599e  pop     r14
0x1400059a0  pop     r13
0x1400059a2  pop     r12
0x1400059a4  pop     rdi
0x1400059a5  pop     rsi
0x1400059a6  pop     rbx
0x1400059a7  pop     rbp
0x1400059a8  retn
0x1400059aa  mov     rdx, [rbp+4Fh+FileNameInformation]
0x1400059ae  lea     rcx, [rbp+4Fh+var_A0]
0x1400059b2  call    BfsGetFileName
0x1400059b7  movups  xmm1, xmmword ptr [rax]
0x1400059ba  movdqu  [rbp+4Fh+var_A0], xmm1
0x1400059bf  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x1400059c4  mov     rdx, [rbp+4Fh+FileNameInformation]
0x1400059c8  lea     r8, [rbp+4Fh+var_A0]
0x1400059cc  mov     rbx, [rbp+4Fh+var_C0]
0x1400059d0  add     rdx, 18h
0x1400059d4  mov     rcx, [rbx+30h]
0x1400059d8  test    eax, eax
0x1400059da  jz      short loc_1400059E2
0x1400059dc  lea     r9, [rbp+4Fh+var_C7]
0x1400059e0  jmp     short loc_1400059E5
0x1400059e2  xor     r9d, r9d
0x1400059e5  call    BfsGetPolicy
0x1400059ea  test    eax, eax
0x1400059ec  jz      short loc_140005A67
0x1400059ee  cmp     eax, 1
0x1400059f1  jz      loc_140005C5D
0x1400059f7  cmp     eax, 2
0x1400059fa  jnz     loc_14000592F
0x140005a00  mov     rax, [r14+10h]
0x140005a04  mov     rdx, r14
0x140005a07  mov     ecx, [rax+20h]
0x140005a0a  and     ecx, 1
0x140005a0d  inc     ecx
0x140005a0f  call    BfsQueryAccessOnly
0x140005a14  xor     edi, edi
0x140005a16  test    al, al
0x140005a18  jnz     loc_140005C5D
0x140005a1e  mov     rax, [r14+10h]
0x140005a22  mov     rdx, r14
0x140005a25  mov     ecx, [rax+20h]
0x140005a28  and     ecx, 1
0x140005a2b  inc     ecx
0x140005a2d  call    BfsQueryAccessOnly
0x140005a32  test    al, al
0x140005a34  jnz     loc_140005934
0x140005a3a  jmp     loc_140005CEE
0x140005a3f  mov     r8, [rbp+4Fh+P]
0x140005a43  lea     r9, [rbp+4Fh+var_C0]
0x140005a47  mov     rdx, [rbp+4Fh+TokenInformation]
0x140005a4b  mov     rcx, rdi
0x140005a4e  mov     r8, [r8]
0x140005a51  mov     rdx, [rdx]
0x140005a54  call    BfsGetNotPresentPolicyEntry
0x140005a59  mov     edi, eax
0x140005a5b  test    eax, eax
0x140005a5d  js      loc_1400058F8
0x140005a63  mov     rbx, [rbp+4Fh+var_C0]
0x140005a67  mov     [rbp+4Fh+var_CF], 0
0x140005a6b  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x140005a70  test    eax, eax
0x140005a72  jz      short loc_140005AB9
0x140005a74  mov     eax, [rbx+6Ch]
0x140005a77  test    eax, eax
0x140005a79  jnz     short loc_140005AAF
0x140005a7b  mov     rax, cs:__imp_SeExports
0x140005a82  lea     r8, [rbp+4Fh+var_CF]
0x140005a86  xor     ecx, ecx
0x140005a88  mov     rdx, [rax]
0x140005a8b  mov     rdx, [rdx+250h]
0x140005a92  call    cs:__imp_RtlCheckTokenCapability
0x140005a99  nop     dword ptr [rax+rax+00h]
0x140005a9e  mov     edi, eax
0x140005aa0  mov     al, [rbp+4Fh+var_CF]
0x140005aa3  neg     al
0x140005aa5  sbb     ecx, ecx
0x140005aa7  add     ecx, 2
0x140005aaa  mov     [rbx+6Ch], ecx
0x140005aad  jmp     short loc_140005ADE
0x140005aaf  cmp     eax, 1
0x140005ab2  jnz     short loc_140005ADE
0x140005ab4  mov     [rbp+4Fh+var_CF], al
0x140005ab7  jmp     short loc_140005ADE
0x140005ab9  mov     rax, cs:__imp_SeExports
0x140005ac0  lea     r8, [rbp+4Fh+var_CF]
0x140005ac4  xor     ecx, ecx
0x140005ac6  mov     rdx, [rax]
0x140005ac9  mov     rdx, [rdx+250h]
0x140005ad0  call    cs:__imp_RtlCheckTokenCapability
0x140005ad7  nop     dword ptr [rax+rax+00h]
0x140005adc  mov     edi, eax
0x140005ade  test    edi, edi
0x140005ae0  js      loc_140005CA8
0x140005ae6  xor     edi, edi
0x140005ae8  cmp     [rbp+4Fh+var_CF], dil
0x140005aec  jz      loc_140005CEE
0x140005af2  mov     rdx, [rbp+4Fh+FileNameInformation]
0x140005af6  lea     r9, [rbp+4Fh+var_90]
0x140005afa  lea     r8, [rbp+4Fh+var_C8]
0x140005afe  mov     rcx, r13
0x140005b01  call    BfsFileInPublisherDirectory
0x140005b06  mov     ecx, eax; int
0x140005b08  test    eax, eax
0x140005b0a  jns     short loc_140005B48
0x140005b0c  mov     eax, cs:dword_140019000
0x140005b12  cmp     eax, 3
0x140005b15  jbe     loc_140005934
0x140005b1b  lea     rax, [rbp+4Fh+var_CC]
0x140005b1f  mov     [rbp+4Fh+var_CC], ecx
0x140005b22  mov     [rbp+4Fh+var_60], rax
0x140005b26  lea     rdx, byte_140016D91; int
0x140005b2d  lea     rax, [rbp+4Fh+var_80]
0x140005b31  mov     [rbp+4Fh+var_58], 4
0x140005b39  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140005b3e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005b43  jmp     loc_140005934
0x140005b48  cmp     [rbp+4Fh+var_C8], dil
0x140005b4c  jz      loc_140005CEE
0x140005b52  test    rbx, rbx
0x140005b55  jz      short loc_140005B6B
0x140005b57  cmp     dword ptr [rbx+38h], 2
0x140005b5b  jnz     loc_140005BE3
0x140005b61  xor     edx, edx
0x140005b63  mov     rcx, rbx; P
0x140005b66  call    BfsDereferencePolicyEntryEx
0x140005b6b  mov     r9, [rbp+4Fh+TokenInformation]
0x140005b6f  lea     rax, [rbp+4Fh+var_C0]
0x140005b73  mov     [rsp+100h+var_D8], rax
0x140005b78  lea     r8, gBfsPolicyTable
0x140005b7f  mov     rax, [rbp+4Fh+P]
0x140005b83  mov     rdx, r12
0x140005b86  mov     r9, [r9]
0x140005b89  mov     rcx, [rax]
0x140005b8c  mov     [rsp+100h+var_E0], rcx; int
0x140005b91  mov     rcx, r15
0x140005b94  call    BfsGetPolicyEntry
0x140005b99  mov     ecx, eax; int
0x140005b9b  test    eax, eax
0x140005b9d  jns     short loc_140005BDF
0x140005b9f  mov     eax, cs:dword_140019000
0x140005ba5  cmp     eax, 3
0x140005ba8  jbe     loc_14000592B
0x140005bae  lea     rax, [rbp+4Fh+var_CC]
0x140005bb2  mov     [rbp+4Fh+var_CC], ecx
0x140005bb5  mov     [rbp+4Fh+var_60], rax
0x140005bb9  lea     rdx, byte_140016D91; int
0x140005bc0  lea     rax, [rbp+4Fh+var_80]
0x140005bc4  mov     [rbp+4Fh+var_58], 4
0x140005bcc  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140005bd1  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005bd6  mov     rbx, [rbp+4Fh+var_C0]
0x140005bda  jmp     loc_140005934
  ... truncated ...
```
