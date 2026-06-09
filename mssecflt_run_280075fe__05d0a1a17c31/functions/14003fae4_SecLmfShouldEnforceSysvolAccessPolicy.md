# SecLmfShouldEnforceSysvolAccessPolicy

- ea: `0x14003fae4`
- end: `0x14003fd54`
- name: `SecLmfShouldEnforceSysvolAccessPolicy`
- size: `624`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003fa28`

## callees

- `0x140005f34`
- `0x140006754`
- `0x140006b6c`
- `0x140010347`
- `0x1400103e3`
- `0x1400105b7`
- `0x140011650`
- `0x140026a80`
- `0x14003e234`
- `0x14003ec68`
- `0x14003fae4`
- `0x1400400e8`

## import_xrefs

- `ntoskrnl!FsRtlDissectName` at `0x14003fc06`
- `ntoskrnl!FsRtlDissectName` at `0x14003fc27`
- `ntoskrnl!FsRtlDissectName` at `0x14003fc06`
- `ntoskrnl!FsRtlDissectName` at `0x14003fc27`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003fc41`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003fc41`

## pseudocode

```c
char __fastcall SecLmfShouldEnforceSysvolAccessPolicy(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _BYTE *a3)
{
  char v3; // si
  PFLT_CONTEXT v7; // rcx
  __int64 RequestorProcess; // rax
  __int64 v9; // r8
  __int64 v10; // rbx
  __int64 v11; // rcx
  UNICODE_STRING Path; // [rsp+30h] [rbp-79h] BYREF
  PFLT_CONTEXT Context; // [rsp+40h] [rbp-69h] BYREF
  PSLIST_ENTRY ListEntry; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v16[16]; // [rsp+50h] [rbp-59h] BYREF
  struct _UNICODE_STRING RemainingName; // [rsp+60h] [rbp-49h] BYREF
  struct _UNICODE_STRING FinalComponent; // [rsp+70h] [rbp-39h] BYREF
  struct _UNICODE_STRING v19; // [rsp+80h] [rbp-29h] BYREF
  struct _UNICODE_STRING Stream; // [rsp+90h] [rbp-19h] BYREF
  struct _UNICODE_STRING Extension; // [rsp+A0h] [rbp-9h] BYREF
  struct _UNICODE_STRING FirstName; // [rsp+B0h] [rbp+7h] BYREF

  Context = 0;
  ListEntry = 0;
  v3 = 0;
  v16[0] = 0;
  Extension = 0;
  Stream = 0;
  FinalComponent = 0;
  FirstName = 0;
  v19 = 0;
  RemainingName = 0;
  if ( !SecLmfInitialized
    || !SecLmfSysvolAccessPolicyConfigCount
    || (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 0x408B80) != 0 )
  {
    return v3;
  }
  if ( FltGetInstanceContext_0(*(PFLT_INSTANCE *)(a2 + 24), &Context) < 0 )
    goto LABEL_24;
  v7 = Context;
  if ( *((_DWORD *)Context + 16) != 13 )
    goto LABEL_25;
  RequestorProcess = SecFltGetRequestorProcess(CallbackData);
  if ( (int)SecGetProcessContextByObject(RequestorProcess, &ListEntry) < 0 )
    goto LABEL_24;
  _mm_lfence();
  if ( (int)KclCheckCurrentTokenMembership(SecGpSvcSid, v16) < 0 )
    goto LABEL_24;
  if ( FltParseFileName_0((PCUNICODE_STRING)(*(_QWORD *)(a2 + 32) + 88LL), &Extension, &Stream, &FinalComponent) < 0 )
    goto LABEL_24;
  Path = *(UNICODE_STRING *)(*(_QWORD *)(a2 + 32) + 88LL);
  FsRtlDissectName(&Path, &FirstName, &RemainingName);
  Path = RemainingName;
  FsRtlDissectName(&Path, &v19, &RemainingName);
  if ( !RtlCompareUnicodeString(&GptIniFileName, &FinalComponent, 1u) )
    goto LABEL_24;
  v10 = 0;
  if ( !SecLmfSysvolAccessPolicyConfigCount )
    goto LABEL_24;
  while ( 1 )
  {
    LOBYTE(v9) = v16[0];
    if ( !(unsigned __int8)SecLmfEvaluateSingleSysvolAccessPolicy(
                             SecLmfSysvolAccessPolicyConfig + 40 * v10,
                             ListEntry,
                             v9) )
      goto LABEL_20;
    v11 = *(_QWORD *)(SecLmfSysvolAccessPolicyConfig + 40 * v10 + 16);
    if ( v11 )
    {
      if ( !(unsigned __int8)SecIsInNameArray(v11, &v19) )
        goto LABEL_20;
    }
    if ( !*(_QWORD *)(*(_QWORD *)(a2 + 32) + 24LL) )
      break;
    if ( *(_DWORD *)(SecLmfSysvolAccessPolicyConfig + 40 * v10 + 8) == 1 )
    {
      v3 = 0;
LABEL_19:
      SecAuditFileAccessBlock(
        CallbackData,
        *(_DWORD *)(SecLmfSysvolAccessPolicyConfig + 40 * v10 + 4),
        (__int64)&Event57);
      if ( v3 )
        goto LABEL_24;
      goto LABEL_20;
    }
    if ( *(_DWORD *)(SecLmfSysvolAccessPolicyConfig + 40 * v10 + 8) == 3 )
    {
      v3 = 1;
      goto LABEL_19;
    }
LABEL_20:
    v10 = (unsigned int)(v10 + 1);
    if ( (unsigned int)v10 >= SecLmfSysvolAccessPolicyConfigCount )
      goto LABEL_24;
  }
  if ( a3 )
    *a3 = 1;
LABEL_24:
  v7 = Context;
LABEL_25:
  if ( v7 )
  {
    FltReleaseContext_0(v7);
    Context = 0;
  }
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  return v3;
}

```

## disassembly

```asm
0x14003fae4  push    rbp
0x14003fae6  push    rbx
0x14003fae7  push    rsi
0x14003fae8  push    rdi
0x14003fae9  push    r12
0x14003faeb  push    r14
0x14003faed  push    r15
0x14003faef  lea     rbp, [rsp-27h]
0x14003faf4  sub     rsp, 0D0h
0x14003fafb  mov     rax, cs:__security_cookie
0x14003fb02  xor     rax, rsp
0x14003fb05  mov     [rbp+57h+var_40], rax
0x14003fb09  xorps   xmm0, xmm0
0x14003fb0c  mov     [rbp+57h+Context], 0
0x14003fb14  xorps   xmm1, xmm1
0x14003fb17  mov     [rbp+57h+ListEntry], 0
0x14003fb1f  xor     sil, sil
0x14003fb22  mov     r15, r8
0x14003fb25  cmp     cs:SecLmfInitialized, sil
0x14003fb2c  mov     rdi, rdx
0x14003fb2f  mov     r12, rcx
0x14003fb32  mov     [rbp+57h+var_B0], sil
0x14003fb36  movups  xmmword ptr [rbp+57h+Extension.Length], xmm0
0x14003fb3a  movups  xmmword ptr [rbp+57h+Stream.Length], xmm1
0x14003fb3e  movups  xmmword ptr [rbp+57h+FinalComponent.Length], xmm0
0x14003fb42  movups  xmmword ptr [rbp+57h+FirstName.Length], xmm1
0x14003fb46  movups  xmmword ptr [rbp+57h+var_80.Length], xmm0
0x14003fb4a  movups  xmmword ptr [rbp+57h+RemainingName.Length], xmm1
0x14003fb4e  jz      loc_14003FD32
0x14003fb54  cmp     cs:SecLmfSysvolAccessPolicyConfigCount, 0
0x14003fb5b  jz      loc_14003FD32
0x14003fb61  mov     rax, [rdx+20h]
0x14003fb65  test    dword ptr [rax+50h], 408B80h
0x14003fb6c  jnz     loc_14003FD32
0x14003fb72  mov     rcx, [rdi+18h]; Instance
0x14003fb76  lea     rdx, [rbp+57h+Context]; Context
0x14003fb7a  call    FltGetInstanceContext_0
0x14003fb7f  test    eax, eax
0x14003fb81  js      loc_14003FD0E
0x14003fb87  mov     rcx, [rbp+57h+Context]
0x14003fb8b  cmp     dword ptr [rcx+40h], 0Dh
0x14003fb8f  jnz     loc_14003FD12
0x14003fb95  mov     rcx, r12
0x14003fb98  call    SecFltGetRequestorProcess
0x14003fb9d  mov     rcx, rax
0x14003fba0  lea     rdx, [rbp+57h+ListEntry]
0x14003fba4  call    SecGetProcessContextByObject
0x14003fba9  test    eax, eax
0x14003fbab  js      loc_14003FD0E
0x14003fbb1  lfence
0x14003fbb4  mov     rcx, cs:SecGpSvcSid; Sid
0x14003fbbb  lea     rdx, [rbp+57h+var_B0]
0x14003fbbf  call    KclCheckCurrentTokenMembership
0x14003fbc4  test    eax, eax
0x14003fbc6  js      loc_14003FD0E
0x14003fbcc  mov     rcx, [rdi+20h]
0x14003fbd0  lea     r9, [rbp+57h+FinalComponent]; FinalComponent
0x14003fbd4  add     rcx, 58h ; 'X'; FileName
0x14003fbd8  lea     r8, [rbp+57h+Stream]; Stream
0x14003fbdc  lea     rdx, [rbp+57h+Extension]; Extension
0x14003fbe0  call    FltParseFileName_0
0x14003fbe5  test    eax, eax
0x14003fbe7  js      loc_14003FD0E
0x14003fbed  mov     rax, [rdi+20h]
0x14003fbf1  lea     r8, [rbp+57h+RemainingName]; RemainingName
0x14003fbf5  lea     rdx, [rbp+57h+FirstName]; FirstName
0x14003fbf9  lea     rcx, [rbp+57h+Path]; Path
0x14003fbfd  movups  xmm0, xmmword ptr [rax+58h]
0x14003fc01  movdqu  xmmword ptr [rbp+57h+Path.Length], xmm0
0x14003fc06  call    cs:__imp_FsRtlDissectName
0x14003fc0d  nop     dword ptr [rax+rax+00h]
0x14003fc12  movaps  xmm0, xmmword ptr [rbp+57h+RemainingName.Length]
0x14003fc16  lea     r8, [rbp+57h+RemainingName]; RemainingName
0x14003fc1a  lea     rdx, [rbp+57h+var_80]; FirstName
0x14003fc1e  movdqa  xmmword ptr [rbp+57h+Path.Length], xmm0
0x14003fc23  lea     rcx, [rbp+57h+Path]; Path
0x14003fc27  call    cs:__imp_FsRtlDissectName
0x14003fc2e  nop     dword ptr [rax+rax+00h]
0x14003fc33  mov     r8b, 1; CaseInSensitive
0x14003fc36  lea     rdx, [rbp+57h+FinalComponent]; String2
0x14003fc3a  lea     rcx, GptIniFileName; String1
0x14003fc41  call    cs:__imp_RtlCompareUnicodeString
0x14003fc48  nop     dword ptr [rax+rax+00h]
0x14003fc4d  test    eax, eax
0x14003fc4f  jz      loc_14003FD0E
0x14003fc55  xor     ebx, ebx
0x14003fc57  cmp     cs:SecLmfSysvolAccessPolicyConfigCount, ebx
0x14003fc5d  jbe     loc_14003FD0E
0x14003fc63  mov     rax, cs:SecLmfSysvolAccessPolicyConfig
0x14003fc6a  lea     r14, [rbx+rbx*4]
0x14003fc6e  mov     r8b, [rbp+57h+var_B0]
0x14003fc72  mov     rdx, [rbp+57h+ListEntry]
0x14003fc76  lea     rcx, [rax+r14*8]
0x14003fc7a  call    SecLmfEvaluateSingleSysvolAccessPolicy
0x14003fc7f  test    al, al
0x14003fc81  jz      short loc_14003FCF5
0x14003fc83  mov     rax, cs:SecLmfSysvolAccessPolicyConfig
0x14003fc8a  mov     rcx, [rax+r14*8+10h]
0x14003fc8f  test    rcx, rcx
0x14003fc92  jz      short loc_14003FCA1
0x14003fc94  lea     rdx, [rbp+57h+var_80]
0x14003fc98  call    SecIsInNameArray
0x14003fc9d  test    al, al
0x14003fc9f  jz      short loc_14003FCF5
0x14003fca1  mov     rax, [rdi+20h]
0x14003fca5  cmp     qword ptr [rax+18h], 0
0x14003fcaa  jz      short loc_14003FD05
0x14003fcac  mov     rdx, cs:SecLmfSysvolAccessPolicyConfig
0x14003fcb3  mov     ecx, [rdx+r14*8+8]
0x14003fcb8  sub     ecx, 1
0x14003fcbb  jz      short loc_14003FCC7
0x14003fcbd  cmp     ecx, 2
0x14003fcc0  jnz     short loc_14003FCF5
0x14003fcc2  mov     sil, 1
0x14003fcc5  jmp     short loc_14003FCCA
0x14003fcc7  xor     sil, sil
0x14003fcca  lea     rax, Event57
0x14003fcd1  xor     r9d, r9d
0x14003fcd4  mov     [rsp+100h+var_D8], rax; __int64
0x14003fcd9  mov     r8b, sil
0x14003fcdc  mov     eax, [rdx+r14*8+4]
0x14003fce1  mov     rcx, r12; CallbackData
0x14003fce4  mov     rdx, rdi
0x14003fce7  mov     [rsp+100h+var_E0], eax; int
0x14003fceb  call    SecAuditFileAccessBlock
0x14003fcf0  test    sil, sil
0x14003fcf3  jnz     short loc_14003FD0E
0x14003fcf5  inc     ebx
0x14003fcf7  cmp     ebx, cs:SecLmfSysvolAccessPolicyConfigCount
0x14003fcfd  jb      loc_14003FC63
0x14003fd03  jmp     short loc_14003FD0E
0x14003fd05  test    r15, r15
0x14003fd08  jz      short loc_14003FD0E
0x14003fd0a  mov     byte ptr [r15], 1
0x14003fd0e  mov     rcx, [rbp+57h+Context]; Context
0x14003fd12  test    rcx, rcx
0x14003fd15  jz      short loc_14003FD24
0x14003fd17  call    FltReleaseContext_0
0x14003fd1c  mov     [rbp+57h+Context], 0
0x14003fd24  mov     rcx, [rbp+57h+ListEntry]; ListEntry
0x14003fd28  test    rcx, rcx
0x14003fd2b  jz      short loc_14003FD32
0x14003fd2d  call    SecReleaseProcessContext
0x14003fd32  mov     al, sil
0x14003fd35  mov     rcx, [rbp+57h+var_40]
0x14003fd39  xor     rcx, rsp; StackCookie
0x14003fd3c  call    __security_check_cookie
0x14003fd41  add     rsp, 0D0h
0x14003fd48  pop     r15
0x14003fd4a  pop     r14
0x14003fd4c  pop     r12
0x14003fd4e  pop     rdi
0x14003fd4f  pop     rsi
0x14003fd50  pop     rbx
0x14003fd51  pop     rbp
0x14003fd52  retn
```
