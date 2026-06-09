# RegIssueSaveKeyEvent

- ea: `0x140037a04`
- end: `0x140037d2f`
- name: `RegIssueSaveKeyEvent`
- size: `811`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x140008278`

## callees

- `0x1400061dc`
- `0x140006684`
- `0x140006854`
- `0x140006b6c`
- `0x140006d3c`
- `0x14000885c`
- `0x140010080`
- `0x1400102ff`
- `0x1400105c3`
- `0x1400108b8`
- `0x140011650`
- `0x140036418`
- `0x140037a04`
- `0x14003a4c4`
- `0x14003a5b8`
- `0x14003a768`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140037b4e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140037bf7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140037b4e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140037bf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037ce7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037ce7`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037a99`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037b7b`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037c2f`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037a99`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037b7b`
- `ntoskrnl!IoGetCurrentProcess` at `0x140037c2f`

## pseudocode

```c
void __fastcall RegIssueSaveKeyEvent(__int64 a1)
{
  const UNICODE_STRING *v2; // rcx
  PEPROCESS CurrentProcess; // rax
  __int64 v4; // r8
  unsigned int *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  char v8; // r15
  volatile signed __int64 *v9; // rbx
  int v10; // r12d
  struct _SLIST_ENTRY *v11; // rdi
  void *Sid; // rsi
  __int64 v13; // r14
  PEPROCESS v14; // rax
  char v15; // al
  __int64 v16; // rdx
  int SessionsFilterMasksAndAsimovNamespaces; // eax
  __int64 i; // r12
  char CurrentThreadId; // r13
  char v20; // di
  volatile signed __int64 *v21; // rbx
  struct _SLIST_ENTRY *Next; // rsi
  void *v23; // r14
  __int64 v24; // r15
  ULONG64 v25; // r12
  PEPROCESS v26; // rax
  char ProcessSessionId_0; // al
  __int64 v28; // rdx
  __int64 v29; // [rsp+58h] [rbp-49h]
  char v30; // [rsp+58h] [rbp-49h]
  int v31; // [rsp+68h] [rbp-39h]
  __int64 v32; // [rsp+70h] [rbp-31h]
  PSLIST_ENTRY ListEntry; // [rsp+78h] [rbp-29h] BYREF
  PVOID P; // [rsp+80h] [rbp-21h] BYREF
  __int64 v35; // [rsp+88h] [rbp-19h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+90h] [rbp-11h] BYREF
  __int64 v37; // [rsp+98h] [rbp-9h] BYREF
  wchar_t *Str; // [rsp+A0h] [rbp-1h]
  __int64 v39; // [rsp+A8h] [rbp+7h] BYREF
  wchar_t *v40; // [rsp+B0h] [rbp+Fh]
  _BYTE v41[8]; // [rsp+B8h] [rbp+17h] BYREF
  ULONG64 Filter; // [rsp+C0h] [rbp+1Fh] BYREF

  v2 = *(const UNICODE_STRING **)(a1 + 40);
  P = 0;
  v41[0] = 0;
  ListEntry = 0;
  v37 = 0;
  Str = 0;
  v39 = 0;
  v40 = 0;
  Filter = 0;
  v35 = 0;
  FileNameInformation = 0;
  if ( v2 )
  {
    if ( !RtlUnicodeStringValidateWorker(v2, 0x7FFFu, 0) )
    {
      if ( *(_QWORD *)(a1 + 48) )
      {
        if ( *(_QWORD *)(a1 + 56) )
        {
          CurrentProcess = IoGetCurrentProcess();
          LOBYTE(v4) = 1;
          if ( (int)SecGetProcessContextWithAssertions(CurrentProcess, &ListEntry, v4) >= 0
            && (int)SecGetEffectiveTokenUser(KeGetCurrentThread(), (__int64)ListEntry, &P, v41, 0) >= 0
            && FltGetFileNameInformationUnsafe_0(*(PFILE_OBJECT *)(a1 + 48), 0, 0x101u, &FileNameInformation) >= 0
            && (int)SecUnicodeToNullTerminatedUnicode(&FileNameInformation->Name, &v39) >= 0
            && (int)SecUnicodeToNullTerminatedUnicode(*(_QWORD *)(a1 + 40), &v37) >= 0 )
          {
            v5 = *(unsigned int **)(a1 + 56);
            v6 = *((_QWORD *)v5 + 1);
            v7 = *v5;
            if ( (BYTE8(xmmword_14001B740) & 0x40) != 0 )
            {
              SessionsFilterMasksAndAsimovNamespaces = SecGetSessionsFilterMasksAndAsimovNamespaces(v7, v6, &v35);
              if ( SessionsFilterMasksAndAsimovNamespaces < 0 )
                goto LABEL_17;
              for ( i = v35; ; i = *(_QWORD *)(v32 + 16) )
              {
                v32 = i;
                if ( !i )
                  break;
                CurrentThreadId = (unsigned __int8)PsGetCurrentThreadId();
                v20 = *(_BYTE *)(i + 8);
                v21 = (volatile signed __int64 *)SecData;
                Next = ListEntry[3].Next;
                v23 = *(void **)P;
                v24 = *((_QWORD *)&ListEntry[2].Next + 1);
                v25 = *(_QWORD *)i;
                v31 = (int)ListEntry[2].Next;
                v26 = IoGetCurrentProcess();
                ProcessSessionId_0 = PsGetProcessSessionId_0(v26);
                v28 = _InterlockedIncrement64(v21 + 42);
                LOBYTE(v29) = v20;
                SessionsFilterMasksAndAsimovNamespaces = EventWriteSaveKey(
                                                           v25,
                                                           v28,
                                                           v31,
                                                           v24,
                                                           CurrentThreadId,
                                                           v23,
                                                           ProcessSessionId_0,
                                                           Str,
                                                           v40,
                                                           Next,
                                                           v29);
              }
            }
            else
            {
              SecGetSessionsFilterMaskFromMatchEntries(v7, v6, &Filter);
              v8 = (unsigned __int8)PsGetCurrentThreadId();
              v9 = (volatile signed __int64 *)SecData;
              v10 = (int)ListEntry[2].Next;
              v11 = ListEntry[3].Next;
              Sid = *(void **)P;
              v13 = *((_QWORD *)&ListEntry[2].Next + 1);
              v14 = IoGetCurrentProcess();
              v15 = PsGetProcessSessionId_0(v14);
              v16 = _InterlockedIncrement64(v9 + 42);
              v30 = 0;
              SessionsFilterMasksAndAsimovNamespaces = EventWriteSaveKey(
                                                         Filter,
                                                         v16,
                                                         v10,
                                                         v13,
                                                         v8,
                                                         Sid,
                                                         v15,
                                                         Str,
                                                         v40,
                                                         v11,
                                                         v30);
            }
            SecIncrementEtwCounters((unsigned int)SessionsFilterMasksAndAsimovNamespaces);
          }
        }
      }
    }
  }
LABEL_17:
  SecReleaseSessionsFilterMasksAndAsimovNamespaces(v35);
  SecFreeNullTerminatedUnicode(&v37);
  SecFreeNullTerminatedUnicode(&v39);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( P && v41[0] )
    ExFreePoolWithTag(P, 0);
  if ( FileNameInformation )
    FltReleaseFileNameInformation_0(FileNameInformation);
}

```

## disassembly

```asm
0x140037a04  mov     rax, rsp
0x140037a07  mov     [rax+10h], rbx
0x140037a0b  mov     [rax+18h], rsi
0x140037a0f  mov     [rax+20h], rdi
0x140037a13  push    rbp
0x140037a14  push    r12
0x140037a16  push    r13
0x140037a18  push    r14
0x140037a1a  push    r15
0x140037a1c  lea     rbp, [rax-5Fh]
0x140037a20  sub     rsp, 0D0h
0x140037a27  mov     rax, cs:__security_cookie
0x140037a2e  xor     rax, rsp
0x140037a31  mov     [rbp+57h+var_30], rax
0x140037a35  xor     r13d, r13d
0x140037a38  mov     rbx, rcx
0x140037a3b  mov     rcx, [rcx+28h]; SourceString
0x140037a3f  mov     [rbp+57h+P], r13
0x140037a43  mov     [rbp+57h+var_40], r13b
0x140037a47  mov     [rbp+57h+ListEntry], r13
0x140037a4b  mov     [rbp+57h+var_60], r13
0x140037a4f  mov     [rbp+57h+var_58], r13
0x140037a53  mov     [rbp+57h+var_50], r13
0x140037a57  mov     [rbp+57h+var_48], r13
0x140037a5b  mov     [rbp+57h+Filter], r13
0x140037a5f  mov     [rbp+57h+var_70], r13
0x140037a63  mov     [rbp+57h+FileNameInformation], r13
0x140037a67  test    rcx, rcx
0x140037a6a  jz      loc_140037CAD
0x140037a70  xor     r8d, r8d; dwFlags
0x140037a73  mov     edx, 7FFFh; cchMax
0x140037a78  call    RtlUnicodeStringValidateWorker
0x140037a7d  test    eax, eax
0x140037a7f  jnz     loc_140037CAD
0x140037a85  cmp     [rbx+30h], r13
0x140037a89  jz      loc_140037CAD
0x140037a8f  cmp     [rbx+38h], r13
0x140037a93  jz      loc_140037CAD
0x140037a99  call    cs:__imp_IoGetCurrentProcess
0x140037aa0  nop     dword ptr [rax+rax+00h]
0x140037aa5  mov     r8b, 1
0x140037aa8  lea     rdx, [rbp+57h+ListEntry]
0x140037aac  mov     rcx, rax
0x140037aaf  call    SecGetProcessContextWithAssertions
0x140037ab4  test    eax, eax
0x140037ab6  js      loc_140037CAD
0x140037abc  mov     rcx, gs:188h; Thread
0x140037ac5  lea     r9, [rbp+57h+var_40]
0x140037ac9  mov     rdx, [rbp+57h+ListEntry]
0x140037acd  lea     r8, [rbp+57h+P]
0x140037ad1  mov     qword ptr [rsp+0F0h+var_D0], r13; __int64
0x140037ad6  call    SecGetEffectiveTokenUser
0x140037adb  test    eax, eax
0x140037add  js      loc_140037CAD
0x140037ae3  mov     rcx, [rbx+30h]; FileObject
0x140037ae7  lea     r9, [rbp+57h+FileNameInformation]; FileNameInformation
0x140037aeb  xor     edx, edx; Instance
0x140037aed  mov     r8d, 101h; NameOptions
0x140037af3  call    FltGetFileNameInformationUnsafe_0
0x140037af8  test    eax, eax
0x140037afa  js      loc_140037CAD
0x140037b00  mov     rcx, [rbp+57h+FileNameInformation]
0x140037b04  lea     rdx, [rbp+57h+var_50]
0x140037b08  add     rcx, 8
0x140037b0c  call    SecUnicodeToNullTerminatedUnicode
0x140037b11  test    eax, eax
0x140037b13  js      loc_140037CAD
0x140037b19  mov     rcx, [rbx+28h]
0x140037b1d  lea     rdx, [rbp+57h+var_60]
0x140037b21  call    SecUnicodeToNullTerminatedUnicode
0x140037b26  test    eax, eax
0x140037b28  js      loc_140037CAD
0x140037b2e  test    byte ptr cs:xmmword_14001B740+8, 40h
0x140037b35  mov     rcx, [rbx+38h]
0x140037b39  mov     rdx, [rcx+8]
0x140037b3d  mov     ecx, [rcx]
0x140037b3f  jnz     loc_140037BDD
0x140037b45  lea     r8, [rbp+57h+Filter]
0x140037b49  call    SecGetSessionsFilterMaskFromMatchEntries
0x140037b4e  call    cs:__imp_PsGetCurrentThreadId
0x140037b55  nop     dword ptr [rax+rax+00h]
0x140037b5a  mov     rdx, [rbp+57h+ListEntry]
0x140037b5e  mov     r15, rax
0x140037b61  mov     rcx, [rbp+57h+P]
0x140037b65  mov     rbx, cs:SecData
0x140037b6c  mov     r12d, [rdx+20h]
0x140037b70  mov     rdi, [rdx+30h]
0x140037b74  mov     rsi, [rcx]
0x140037b77  mov     r14, [rdx+28h]
0x140037b7b  call    cs:__imp_IoGetCurrentProcess
0x140037b82  nop     dword ptr [rax+rax+00h]
0x140037b87  mov     rcx, rax
0x140037b8a  call    PsGetProcessSessionId_0
0x140037b8f  lea     edx, [r13+1]
0x140037b93  lock xadd [rbx+150h], rdx
0x140037b9c  mov     rcx, [rbp+57h+var_48]
0x140037ba0  inc     rdx
0x140037ba3  mov     [rsp+0F0h+var_A0], r13b; char
0x140037ba8  mov     r9, r14
0x140037bab  mov     qword ptr [rsp+0F0h+var_A8], rdi; char
0x140037bb0  mov     r8d, r12d
0x140037bb3  mov     [rsp+0F0h+var_B0], rcx; wchar_t *
0x140037bb8  mov     rcx, [rbp+57h+var_58]
0x140037bbc  mov     [rsp+0F0h+Str], rcx; Str
0x140037bc1  mov     rcx, [rbp+57h+Filter]; Filter
0x140037bc5  mov     dword ptr [rsp+0F0h+var_C0], eax; char
0x140037bc9  mov     [rsp+0F0h+Sid], rsi; Sid
0x140037bce  mov     dword ptr [rsp+0F0h+var_D0], r15d; char
0x140037bd3  call    EventWriteSaveKey
0x140037bd8  jmp     loc_140037CA6
0x140037bdd  lea     r8, [rbp+57h+var_70]
0x140037be1  call    SecGetSessionsFilterMasksAndAsimovNamespaces
0x140037be6  test    eax, eax
0x140037be8  js      loc_140037CAD
0x140037bee  mov     r12, [rbp+57h+var_70]
0x140037bf2  jmp     loc_140037C99
0x140037bf7  call    cs:__imp_PsGetCurrentThreadId
0x140037bfe  nop     dword ptr [rax+rax+00h]
0x140037c03  mov     rdx, [rbp+57h+ListEntry]
0x140037c07  mov     r13, rax
0x140037c0a  mov     rcx, [rbp+57h+P]
0x140037c0e  mov     dil, [r12+8]
0x140037c13  mov     rbx, cs:SecData
0x140037c1a  mov     eax, [rdx+20h]
0x140037c1d  mov     rsi, [rdx+30h]
0x140037c21  mov     r14, [rcx]
0x140037c24  mov     r15, [rdx+28h]
0x140037c28  mov     r12, [r12]
0x140037c2c  mov     [rbp+57h+var_90], eax
0x140037c2f  call    cs:__imp_IoGetCurrentProcess
0x140037c36  nop     dword ptr [rax+rax+00h]
0x140037c3b  mov     rcx, rax
0x140037c3e  call    PsGetProcessSessionId_0
0x140037c43  mov     edx, 1
0x140037c48  lock xadd [rbx+150h], rdx
0x140037c51  mov     r10, [rbp+57h+var_48]
0x140037c55  inc     rdx
0x140037c58  mov     r8d, [rbp+57h+var_90]
0x140037c5c  mov     r9, r15
0x140037c5f  mov     [rsp+0F0h+var_A0], dil; char
0x140037c64  mov     rcx, r12; Filter
0x140037c67  mov     qword ptr [rsp+0F0h+var_A8], rsi; char
0x140037c6c  mov     [rsp+0F0h+var_B0], r10; wchar_t *
0x140037c71  mov     r10, [rbp+57h+var_58]
0x140037c75  mov     [rsp+0F0h+Str], r10; Str
0x140037c7a  mov     dword ptr [rsp+0F0h+var_C0], eax; char
0x140037c7e  mov     [rsp+0F0h+Sid], r14; Sid
0x140037c83  mov     dword ptr [rsp+0F0h+var_D0], r13d; char
0x140037c88  call    EventWriteSaveKey
0x140037c8d  mov     r12, [rbp+57h+var_88]
0x140037c91  xor     r13d, r13d
0x140037c94  mov     r12, [r12+10h]
0x140037c99  mov     [rbp+57h+var_88], r12
0x140037c9d  test    r12, r12
0x140037ca0  jnz     loc_140037BF7
0x140037ca6  mov     ecx, eax
0x140037ca8  call    SecIncrementEtwCounters
0x140037cad  mov     rcx, [rbp+57h+var_70]
0x140037cb1  call    SecReleaseSessionsFilterMasksAndAsimovNamespaces
0x140037cb6  lea     rcx, [rbp+57h+var_60]
0x140037cba  call    SecFreeNullTerminatedUnicode
0x140037cbf  lea     rcx, [rbp+57h+var_50]
0x140037cc3  call    SecFreeNullTerminatedUnicode
0x140037cc8  mov     rcx, [rbp+57h+ListEntry]; ListEntry
0x140037ccc  test    rcx, rcx
0x140037ccf  jz      short loc_140037CD6
0x140037cd1  call    SecReleaseProcessContext
0x140037cd6  mov     rcx, [rbp+57h+P]; P
0x140037cda  test    rcx, rcx
0x140037cdd  jz      short loc_140037CF3
0x140037cdf  cmp     [rbp+57h+var_40], r13b
0x140037ce3  jz      short loc_140037CF3
0x140037ce5  xor     edx, edx; Tag
0x140037ce7  call    cs:__imp_ExFreePoolWithTag
0x140037cee  nop     dword ptr [rax+rax+00h]
0x140037cf3  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140037cf7  test    rcx, rcx
0x140037cfa  jz      short loc_140037D01
0x140037cfc  call    FltReleaseFileNameInformation_0
0x140037d01  mov     rcx, [rbp+57h+var_30]
0x140037d05  xor     rcx, rsp; StackCookie
0x140037d08  call    __security_check_cookie
0x140037d0d  lea     r11, [rsp+0F0h+var_20]
0x140037d15  mov     rbx, [r11+38h]
0x140037d19  mov     rsi, [r11+40h]
0x140037d1d  mov     rdi, [r11+48h]
0x140037d21  mov     rsp, r11
0x140037d24  pop     r15
0x140037d26  pop     r14
0x140037d28  pop     r13
0x140037d2a  pop     r12
0x140037d2c  pop     rbp
0x140037d2d  retn
```
