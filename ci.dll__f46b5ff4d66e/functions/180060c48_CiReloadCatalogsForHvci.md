# CiReloadCatalogsForHvci

- ea: `0x180060c48`
- end: `0x180060e8a`
- name: `CiReloadCatalogsForHvci`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800baa9c`

## callees

- `0x18000c52c`
- `0x18002bef0`
- `0x180060c48`
- `0x18009675c`
- `0x180096928`
- `0x1800a1968`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180060d7e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180060d7e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180060e54`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180060e54`
- `ntoskrnl!KeStackAttachProcess` at `0x180060dc5`
- `ntoskrnl!KeStackAttachProcess` at `0x180060dc5`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180060e13`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180060e13`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180060e3e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180060e3e`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180060dab`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180060dab`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180060e22`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180060e22`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180060d90`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180060d90`
- `ntoskrnl!ExReleaseResourceLite` at `0x180060e32`
- `ntoskrnl!ExReleaseResourceLite` at `0x180060e32`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180060d9c`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180060d9c`

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
  __int128 v22; // [rsp+C8h] [rbp-68h] BYREF
  __int128 v23; // [rsp+D8h] [rbp-58h]
  __int64 v24; // [rsp+E8h] [rbp-48h]
  struct _KAPC_STATE ApcState; // [rsp+F0h] [rbp-40h] BYREF

  SourceString = a5;
  v6 = a4;
  memset(&ApcState, 0, sizeof(ApcState));
  v24 = 0;
  LODWORD(v20) = 0;
  v22 = 0;
  v23 = 0;
  UnicodeString = 0;
  CurrentSiloState = CiGetCurrentSiloState();
  if ( !a5 )
  {
    *(_QWORD *)&v22 = a1;
    LOBYTE(v10) = a3;
    DWORD2(v22) = a2;
    BYTE12(v22) = a3;
    AcceptedRootKeys = CipGetAcceptedRootKeys(a2, v10, 0);
    LODWORD(v23) = AcceptedRootKeys;
    v13 = 0;
    while ( 1 )
    {
      FileOrHeaderHashInCatalogs = CiFindFileOrHeaderHashInCatalogs(
                                     (__int64 *)&v22,
                                     *(_QWORD *)(a1 + 3016),
                                     *(_DWORD *)(a1 + 3012),
                                     *(_DWORD *)(a1 + 3008),
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
0x180060c48  mov     [rsp-38h+arg_18], rbx
0x180060c4d  push    rbp
0x180060c4e  push    rsi
0x180060c4f  push    rdi
0x180060c50  push    r12
0x180060c52  push    r13
0x180060c54  push    r14
0x180060c56  push    r15
0x180060c58  mov     rbp, rsp
0x180060c5b  sub     rsp, 130h
0x180060c62  mov     rax, cs:__security_cookie
0x180060c69  xor     rax, rsp
0x180060c6c  mov     [rbp+var_10], rax
0x180060c70  mov     rsi, [rbp+arg_20]
0x180060c74  xorps   xmm0, xmm0
0x180060c77  xorps   xmm1, xmm1
0x180060c7a  movzx   r15d, r9b
0x180060c7e  xor     eax, eax
0x180060c80  xor     r12d, r12d
0x180060c83  movups  xmmword ptr [rbp+ApcState.ApcListHead.Flink], xmm0
0x180060c87  mov     [rbp+var_48], rax
0x180060c8b  mov     dil, r8b
0x180060c8e  movups  xmmword ptr [rbp+ApcState.ApcListHead.Flink+10h], xmm0
0x180060c92  mov     dword ptr [rbp+var_80], r12d
0x180060c96  mov     ebx, edx
0x180060c98  movups  xmmword ptr [rbp+ApcState.Process], xmm0
0x180060c9c  mov     r14, rcx
0x180060c9f  movups  [rbp+var_68], xmm1
0x180060ca3  movups  [rbp+var_58], xmm1
0x180060ca7  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180060cab  call    CiGetCurrentSiloState
0x180060cb0  mov     r13, rax
0x180060cb3  test    rsi, rsi
0x180060cb6  jnz     loc_180060D7E
0x180060cbc  xor     r8d, r8d
0x180060cbf  mov     qword ptr [rbp+var_68], r14
0x180060cc3  mov     dl, dil
0x180060cc6  mov     dword ptr [rbp+var_68+8], ebx
0x180060cc9  mov     ecx, ebx
0x180060ccb  mov     byte ptr [rbp+var_68+0Ch], dil
0x180060ccf  call    CipGetAcceptedRootKeys
0x180060cd4  mov     dword ptr [rbp+var_58], eax
0x180060cd7  mov     bl, r12b
0x180060cda  mov     r9d, [r14+0BC0h]
0x180060ce1  lea     rdx, [rbp+UnicodeString]
0x180060ce5  mov     r8d, [r14+0BC4h]
0x180060cec  mov     ecx, r12d
0x180060cef  mov     [rsp+130h+var_90], r12
0x180060cf7  test    bl, bl
0x180060cf9  mov     [rsp+130h+var_98], r12
0x180060d01  mov     [rsp+130h+var_A0], r12
0x180060d09  setnz   cl
0x180060d0c  mov     [rsp+130h+var_A8], rdx
0x180060d14  mov     rdx, [r14+0BC8h]
0x180060d1b  mov     [rsp+130h+var_B0], r12
0x180060d23  mov     [rsp+130h+var_C0], r12
0x180060d28  mov     [rsp+130h+var_C8], r12
0x180060d2d  mov     [rsp+130h+var_D0], r12
0x180060d32  mov     dword ptr [rsp+130h+var_D8], eax
0x180060d36  mov     dword ptr [rsp+130h+var_E0], r12d
0x180060d3b  mov     dword ptr [rsp+130h+var_E8], r12d
0x180060d40  mov     [rsp+130h+var_F0], ecx
0x180060d44  lea     rcx, [rbp+var_68]
0x180060d48  mov     [rsp+130h+var_F8], r15d
0x180060d4d  mov     dword ptr [rsp+130h+var_100], r12d
0x180060d52  mov     dword ptr [rsp+130h+SourceString], r12d
0x180060d57  mov     qword ptr [rsp+130h+var_110], r12
0x180060d5c  call    CiFindFileOrHeaderHashInCatalogs
0x180060d61  mov     esi, eax
0x180060d63  test    eax, eax
0x180060d65  jns     short loc_180060D7A
0x180060d67  inc     bl
0x180060d69  cmp     bl, 2
0x180060d6c  jnb     loc_180060E4A
0x180060d72  mov     eax, dword ptr [rbp+var_58]
0x180060d75  jmp     loc_180060CDA
0x180060d7a  lea     rsi, [rbp+UnicodeString]
0x180060d7e  call    cs:__imp_KeEnterCriticalRegion
0x180060d85  nop     dword ptr [rax+rax+00h]
0x180060d8a  mov     dl, 1; Wait
0x180060d8c  lea     rcx, [r13+18h]; Resource
0x180060d90  call    cs:__imp_ExAcquireResourceSharedLite
0x180060d97  nop     dword ptr [rax+rax+00h]
0x180060d9c  call    cs:__imp_PsGetCurrentServerSilo
0x180060da3  nop     dword ptr [rax+rax+00h]
0x180060da8  mov     rcx, rax
0x180060dab  call    cs:__imp_PsAttachSiloToCurrentThread
0x180060db2  nop     dword ptr [rax+rax+00h]
0x180060db7  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x180060dbe  lea     rdx, [rbp+ApcState]; ApcState
0x180060dc2  mov     rbx, rax
0x180060dc5  call    cs:__imp_KeStackAttachProcess
0x180060dcc  nop     dword ptr [rax+rax+00h]
0x180060dd1  lea     rax, [rbp+var_80]
0x180060dd5  xor     r9d, r9d; int
0x180060dd8  mov     [rsp+130h+var_D8], rax; __int64
0x180060ddd  xor     r8d, r8d; int
0x180060de0  mov     [rsp+130h+var_E0], r12; __int64
0x180060de5  mov     dl, 1; int
0x180060de7  mov     [rsp+130h+var_E8], r12; __int64
0x180060dec  mov     rcx, r14; int
0x180060def  mov     qword ptr [rsp+130h+var_F0], r12; int
0x180060df4  mov     qword ptr [rsp+130h+var_F8], r12; int
0x180060df9  mov     [rsp+130h+var_100], r12; PCUNICODE_STRING
0x180060dfe  mov     [rsp+130h+SourceString], rsi; SourceString
0x180060e03  mov     [rsp+130h+var_110], r12d; int
0x180060e08  call    I_ReloadCatalog
0x180060e0d  lea     rcx, [rbp+ApcState]; ApcState
0x180060e11  mov     esi, eax
0x180060e13  call    cs:__imp_KeUnstackDetachProcess
0x180060e1a  nop     dword ptr [rax+rax+00h]
0x180060e1f  mov     rcx, rbx
0x180060e22  call    cs:__imp_PsDetachSiloFromCurrentThread
0x180060e29  nop     dword ptr [rax+rax+00h]
0x180060e2e  lea     rcx, [r13+18h]; Resource
0x180060e32  call    cs:__imp_ExReleaseResourceLite
0x180060e39  nop     dword ptr [rax+rax+00h]
0x180060e3e  call    cs:__imp_KeLeaveCriticalRegion
0x180060e45  nop     dword ptr [rax+rax+00h]
0x180060e4a  cmp     [rbp+UnicodeString.Buffer], r12
0x180060e4e  jz      short loc_180060E60
0x180060e50  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180060e54  call    cs:__imp_RtlFreeUnicodeString
0x180060e5b  nop     dword ptr [rax+rax+00h]
0x180060e60  mov     eax, esi
0x180060e62  mov     rcx, [rbp+var_10]
0x180060e66  xor     rcx, rsp; StackCookie
0x180060e69  call    __security_check_cookie
0x180060e6e  mov     rbx, [rsp+130h+arg_18]
0x180060e76  add     rsp, 130h
0x180060e7d  pop     r15
0x180060e7f  pop     r14
0x180060e81  pop     r13
0x180060e83  pop     r12
0x180060e85  pop     rdi
0x180060e86  pop     rsi
0x180060e87  pop     rbp
0x180060e88  retn
```
