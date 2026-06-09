# CiReloadCatalogsForHvci

- ea: `0x180061568`
- end: `0x1800617aa`
- name: `CiReloadCatalogsForHvci`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800bbdbc`

## callees

- `0x18000c53c`
- `0x18002c0d0`
- `0x180061568`
- `0x18008c1a0`
- `0x18008e55c`
- `0x18008e728`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18006169e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006169e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180061774`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180061774`
- `ntoskrnl!KeStackAttachProcess` at `0x1800616e5`
- `ntoskrnl!KeStackAttachProcess` at `0x1800616e5`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180061733`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180061733`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006175e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006175e`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1800616cb`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1800616cb`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180061742`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180061742`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800616b0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800616b0`
- `ntoskrnl!ExReleaseResourceLite` at `0x180061752`
- `ntoskrnl!ExReleaseResourceLite` at `0x180061752`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800616bc`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800616bc`

## pseudocode

```c
__int64 __fastcall CiReloadCatalogsForHvci(
        __int64 a1,
        unsigned int a2,
        char a3,
        unsigned __int8 a4,
        struct _UNICODE_STRING *a5)
{
  struct _UNICODE_STRING *SourceString; // rsi
  int v6; // r15d
  __int64 v10; // rdx
  __int64 CurrentSiloState; // r13
  int AcceptedRootKeys; // eax
  char v13; // bl
  int FileOrHeaderHashInCatalogs; // esi
  __int64 CurrentServerSilo; // rax
  __int64 v16; // rbx
  int v17; // edx
  int v19; // [rsp+78h] [rbp-B8h]
  __int64 v20; // [rsp+B0h] [rbp-80h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+B8h] [rbp-78h] BYREF
  int v22[4]; // [rsp+C8h] [rbp-68h] BYREF
  __int128 v23; // [rsp+D8h] [rbp-58h]
  __int64 v24; // [rsp+E8h] [rbp-48h]
  struct _KAPC_STATE ApcState; // [rsp+F0h] [rbp-40h] BYREF

  SourceString = a5;
  v6 = a4;
  memset(&ApcState, 0, sizeof(ApcState));
  v24 = 0;
  LODWORD(v20) = 0;
  *(_OWORD *)v22 = 0;
  v23 = 0;
  UnicodeString = 0;
  CurrentSiloState = CiGetCurrentSiloState();
  if ( !a5 )
  {
    *(_QWORD *)v22 = a1;
    LOBYTE(v10) = a3;
    v22[2] = a2;
    LOBYTE(v22[3]) = a3;
    AcceptedRootKeys = CipGetAcceptedRootKeys(a2, v10, 0);
    LODWORD(v23) = AcceptedRootKeys;
    v13 = 0;
    while ( 1 )
    {
      FileOrHeaderHashInCatalogs = CiFindFileOrHeaderHashInCatalogs(
                                     (__int64 *)v22,
                                     *(_QWORD *)(a1 + 3024),
                                     *(_DWORD *)(a1 + 3020),
                                     *(_DWORD *)(a1 + 3016),
                                     0,
                                     0,
                                     0,
                                     v6,
                                     v13 != 0,
                                     0,
                                     0,
                                     AcceptedRootKeys,
                                     0,
                                     0,
                                     0,
                                     v19,
                                     0,
                                     &UnicodeString,
                                     0,
                                     0,
                                     0);
      if ( FileOrHeaderHashInCatalogs >= 0 )
        break;
      if ( (unsigned __int8)++v13 >= 2u )
        goto LABEL_8;
      AcceptedRootKeys = v23;
    }
    SourceString = &UnicodeString;
  }
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)(CurrentSiloState + 24), 1u);
  CurrentServerSilo = PsGetCurrentServerSilo();
  v16 = PsAttachSiloToCurrentThread(CurrentServerSilo);
  KeStackAttachProcess(g_CiSystemProcess, &ApcState);
  LOBYTE(v17) = 1;
  FileOrHeaderHashInCatalogs = I_ReloadCatalog(a1, v17, 0, 0, 0, SourceString, 0, 0, 0, 0, 0, (__int64)&v20);
  KeUnstackDetachProcess(&ApcState);
  PsDetachSiloFromCurrentThread(v16);
  ExReleaseResourceLite((PERESOURCE)(CurrentSiloState + 24));
  KeLeaveCriticalRegion();
LABEL_8:
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)FileOrHeaderHashInCatalogs;
}

```

## disassembly

```asm
0x180061568  mov     [rsp-38h+arg_18], rbx
0x18006156d  push    rbp
0x18006156e  push    rsi
0x18006156f  push    rdi
0x180061570  push    r12
0x180061572  push    r13
0x180061574  push    r14
0x180061576  push    r15
0x180061578  mov     rbp, rsp
0x18006157b  sub     rsp, 130h
0x180061582  mov     rax, cs:__security_cookie
0x180061589  xor     rax, rsp
0x18006158c  mov     [rbp+var_10], rax
0x180061590  mov     rsi, [rbp+arg_20]
0x180061594  xorps   xmm0, xmm0
0x180061597  xorps   xmm1, xmm1
0x18006159a  movzx   r15d, r9b
0x18006159e  xor     eax, eax
0x1800615a0  xor     r12d, r12d
0x1800615a3  movups  xmmword ptr [rbp+ApcState.ApcListHead.Flink], xmm0
0x1800615a7  mov     [rbp+var_48], rax
0x1800615ab  mov     dil, r8b
0x1800615ae  movups  xmmword ptr [rbp+ApcState.ApcListHead.Flink+10h], xmm0
0x1800615b2  mov     dword ptr [rbp+var_80], r12d
0x1800615b6  mov     ebx, edx
0x1800615b8  movups  xmmword ptr [rbp+ApcState.Process], xmm0
0x1800615bc  mov     r14, rcx
0x1800615bf  movups  xmmword ptr [rbp+var_68], xmm1
0x1800615c3  movups  [rbp+var_58], xmm1
0x1800615c7  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x1800615cb  call    CiGetCurrentSiloState
0x1800615d0  mov     r13, rax
0x1800615d3  test    rsi, rsi
0x1800615d6  jnz     loc_18006169E
0x1800615dc  xor     r8d, r8d
0x1800615df  mov     qword ptr [rbp+var_68], r14
0x1800615e3  mov     dl, dil
0x1800615e6  mov     [rbp+var_68+8], ebx
0x1800615e9  mov     ecx, ebx
0x1800615eb  mov     byte ptr [rbp+var_68+0Ch], dil
0x1800615ef  call    CipGetAcceptedRootKeys
0x1800615f4  mov     dword ptr [rbp+var_58], eax
0x1800615f7  mov     bl, r12b
0x1800615fa  mov     r9d, [r14+0BC8h]
0x180061601  lea     rdx, [rbp+UnicodeString]
0x180061605  mov     r8d, [r14+0BCCh]
0x18006160c  mov     ecx, r12d
0x18006160f  mov     [rsp+130h+var_90], r12; __int64
0x180061617  test    bl, bl
0x180061619  mov     [rsp+130h+var_98], r12; __int64
0x180061621  mov     [rsp+130h+var_A0], r12; __int64
0x180061629  setnz   cl
0x18006162c  mov     [rsp+130h+var_A8], rdx; __int64
0x180061634  mov     rdx, [r14+0BD0h]
0x18006163b  mov     [rsp+130h+var_B0], r12; __int64
0x180061643  mov     [rsp+130h+var_C0], r12; __int64
0x180061648  mov     [rsp+130h+var_C8], r12; __int64
0x18006164d  mov     [rsp+130h+var_D0], r12; PCUNICODE_STRING
0x180061652  mov     dword ptr [rsp+130h+var_D8], eax; int
0x180061656  mov     dword ptr [rsp+130h+var_E0], r12d; int
0x18006165b  mov     dword ptr [rsp+130h+var_E8], r12d; int
0x180061660  mov     [rsp+130h+var_F0], ecx; int
0x180061664  lea     rcx, [rbp+var_68]; int
0x180061668  mov     [rsp+130h+var_F8], r15d; int
0x18006166d  mov     dword ptr [rsp+130h+var_100], r12d; int
0x180061672  mov     dword ptr [rsp+130h+SourceString], r12d; int
0x180061677  mov     [rsp+130h+var_110], r12; __int64
0x18006167c  call    CiFindFileOrHeaderHashInCatalogs
0x180061681  mov     esi, eax
0x180061683  test    eax, eax
0x180061685  jns     short loc_18006169A
0x180061687  inc     bl
0x180061689  cmp     bl, 2
0x18006168c  jnb     loc_18006176A
0x180061692  mov     eax, dword ptr [rbp+var_58]
0x180061695  jmp     loc_1800615FA
0x18006169a  lea     rsi, [rbp+UnicodeString]
0x18006169e  call    cs:__imp_KeEnterCriticalRegion
0x1800616a5  nop     dword ptr [rax+rax+00h]
0x1800616aa  mov     dl, 1; Wait
0x1800616ac  lea     rcx, [r13+18h]; Resource
0x1800616b0  call    cs:__imp_ExAcquireResourceSharedLite
0x1800616b7  nop     dword ptr [rax+rax+00h]
0x1800616bc  call    cs:__imp_PsGetCurrentServerSilo
0x1800616c3  nop     dword ptr [rax+rax+00h]
0x1800616c8  mov     rcx, rax
0x1800616cb  call    cs:__imp_PsAttachSiloToCurrentThread
0x1800616d2  nop     dword ptr [rax+rax+00h]
0x1800616d7  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x1800616de  lea     rdx, [rbp+ApcState]; ApcState
0x1800616e2  mov     rbx, rax
0x1800616e5  call    cs:__imp_KeStackAttachProcess
0x1800616ec  nop     dword ptr [rax+rax+00h]
0x1800616f1  lea     rax, [rbp+var_80]
0x1800616f5  xor     r9d, r9d; int
0x1800616f8  mov     [rsp+130h+var_D8], rax; __int64
0x1800616fd  xor     r8d, r8d; int
0x180061700  mov     [rsp+130h+var_E0], r12; __int64
0x180061705  mov     dl, 1; int
0x180061707  mov     [rsp+130h+var_E8], r12; __int64
0x18006170c  mov     rcx, r14; int
0x18006170f  mov     qword ptr [rsp+130h+var_F0], r12; int
0x180061714  mov     qword ptr [rsp+130h+var_F8], r12; int
0x180061719  mov     [rsp+130h+var_100], r12; PCUNICODE_STRING
0x18006171e  mov     [rsp+130h+SourceString], rsi; SourceString
0x180061723  mov     dword ptr [rsp+130h+var_110], r12d; int
0x180061728  call    I_ReloadCatalog
0x18006172d  lea     rcx, [rbp+ApcState]; ApcState
0x180061731  mov     esi, eax
0x180061733  call    cs:__imp_KeUnstackDetachProcess
0x18006173a  nop     dword ptr [rax+rax+00h]
0x18006173f  mov     rcx, rbx
0x180061742  call    cs:__imp_PsDetachSiloFromCurrentThread
0x180061749  nop     dword ptr [rax+rax+00h]
0x18006174e  lea     rcx, [r13+18h]; Resource
0x180061752  call    cs:__imp_ExReleaseResourceLite
0x180061759  nop     dword ptr [rax+rax+00h]
0x18006175e  call    cs:__imp_KeLeaveCriticalRegion
0x180061765  nop     dword ptr [rax+rax+00h]
0x18006176a  cmp     [rbp+UnicodeString.Buffer], r12
0x18006176e  jz      short loc_180061780
0x180061770  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180061774  call    cs:__imp_RtlFreeUnicodeString
0x18006177b  nop     dword ptr [rax+rax+00h]
0x180061780  mov     eax, esi
0x180061782  mov     rcx, [rbp+var_10]
0x180061786  xor     rcx, rsp; StackCookie
0x180061789  call    __security_check_cookie
0x18006178e  mov     rbx, [rsp+130h+arg_18]
0x180061796  add     rsp, 130h
0x18006179d  pop     r15
0x18006179f  pop     r14
0x1800617a1  pop     r13
0x1800617a3  pop     r12
0x1800617a5  pop     rdi
0x1800617a6  pop     rsi
0x1800617a7  pop     rbp
0x1800617a8  retn
```
