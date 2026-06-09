# CiReloadCatalogsForHvci

- ea: `0x180061404`
- end: `0x180061646`
- name: `CiReloadCatalogsForHvci`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800bbf1c`

## callees

- `0x18000c52c`
- `0x18002bf20`
- `0x180061404`
- `0x180097d8c`
- `0x180097f58`
- `0x1800a2f98`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18006153a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006153a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180061610`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180061610`
- `ntoskrnl!KeStackAttachProcess` at `0x180061581`
- `ntoskrnl!KeStackAttachProcess` at `0x180061581`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800615cf`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800615cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800615fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800615fa`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180061567`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180061567`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800615de`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800615de`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18006154c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18006154c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800615ee`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800615ee`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180061558`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180061558`

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
0x180061404  mov     [rsp-38h+arg_18], rbx
0x180061409  push    rbp
0x18006140a  push    rsi
0x18006140b  push    rdi
0x18006140c  push    r12
0x18006140e  push    r13
0x180061410  push    r14
0x180061412  push    r15
0x180061414  mov     rbp, rsp
0x180061417  sub     rsp, 130h
0x18006141e  mov     rax, cs:__security_cookie
0x180061425  xor     rax, rsp
0x180061428  mov     [rbp+var_10], rax
0x18006142c  mov     rsi, [rbp+arg_20]
0x180061430  xorps   xmm0, xmm0
0x180061433  xorps   xmm1, xmm1
0x180061436  movzx   r15d, r9b
0x18006143a  xor     eax, eax
0x18006143c  xor     r12d, r12d
0x18006143f  movups  xmmword ptr [rbp+ApcState.ApcListHead.Flink], xmm0
0x180061443  mov     [rbp+var_48], rax
0x180061447  mov     dil, r8b
0x18006144a  movups  xmmword ptr [rbp+ApcState.ApcListHead.Flink+10h], xmm0
0x18006144e  mov     dword ptr [rbp+var_80], r12d
0x180061452  mov     ebx, edx
0x180061454  movups  xmmword ptr [rbp+ApcState.Process], xmm0
0x180061458  mov     r14, rcx
0x18006145b  movups  [rbp+var_68], xmm1
0x18006145f  movups  [rbp+var_58], xmm1
0x180061463  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180061467  call    CiGetCurrentSiloState
0x18006146c  mov     r13, rax
0x18006146f  test    rsi, rsi
0x180061472  jnz     loc_18006153A
0x180061478  xor     r8d, r8d
0x18006147b  mov     qword ptr [rbp+var_68], r14
0x18006147f  mov     dl, dil
0x180061482  mov     dword ptr [rbp+var_68+8], ebx
0x180061485  mov     ecx, ebx
0x180061487  mov     byte ptr [rbp+var_68+0Ch], dil
0x18006148b  call    CipGetAcceptedRootKeys
0x180061490  mov     dword ptr [rbp+var_58], eax
0x180061493  mov     bl, r12b
0x180061496  mov     r9d, [r14+0BC0h]
0x18006149d  lea     rdx, [rbp+UnicodeString]
0x1800614a1  mov     r8d, [r14+0BC4h]
0x1800614a8  mov     ecx, r12d
0x1800614ab  mov     [rsp+130h+var_90], r12
0x1800614b3  test    bl, bl
0x1800614b5  mov     [rsp+130h+var_98], r12
0x1800614bd  mov     [rsp+130h+var_A0], r12
0x1800614c5  setnz   cl
0x1800614c8  mov     [rsp+130h+var_A8], rdx
0x1800614d0  mov     rdx, [r14+0BC8h]
0x1800614d7  mov     [rsp+130h+var_B0], r12
0x1800614df  mov     [rsp+130h+var_C0], r12
0x1800614e4  mov     [rsp+130h+var_C8], r12
0x1800614e9  mov     [rsp+130h+var_D0], r12
0x1800614ee  mov     dword ptr [rsp+130h+var_D8], eax
0x1800614f2  mov     dword ptr [rsp+130h+var_E0], r12d
0x1800614f7  mov     dword ptr [rsp+130h+var_E8], r12d
0x1800614fc  mov     [rsp+130h+var_F0], ecx
0x180061500  lea     rcx, [rbp+var_68]
0x180061504  mov     [rsp+130h+var_F8], r15d
0x180061509  mov     dword ptr [rsp+130h+var_100], r12d
0x18006150e  mov     dword ptr [rsp+130h+SourceString], r12d
0x180061513  mov     qword ptr [rsp+130h+var_110], r12
0x180061518  call    CiFindFileOrHeaderHashInCatalogs
0x18006151d  mov     esi, eax
0x18006151f  test    eax, eax
0x180061521  jns     short loc_180061536
0x180061523  inc     bl
0x180061525  cmp     bl, 2
0x180061528  jnb     loc_180061606
0x18006152e  mov     eax, dword ptr [rbp+var_58]
0x180061531  jmp     loc_180061496
0x180061536  lea     rsi, [rbp+UnicodeString]
0x18006153a  call    cs:__imp_KeEnterCriticalRegion
0x180061541  nop     dword ptr [rax+rax+00h]
0x180061546  mov     dl, 1; Wait
0x180061548  lea     rcx, [r13+18h]; Resource
0x18006154c  call    cs:__imp_ExAcquireResourceSharedLite
0x180061553  nop     dword ptr [rax+rax+00h]
0x180061558  call    cs:__imp_PsGetCurrentServerSilo
0x18006155f  nop     dword ptr [rax+rax+00h]
0x180061564  mov     rcx, rax
0x180061567  call    cs:__imp_PsAttachSiloToCurrentThread
0x18006156e  nop     dword ptr [rax+rax+00h]
0x180061573  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x18006157a  lea     rdx, [rbp+ApcState]; ApcState
0x18006157e  mov     rbx, rax
0x180061581  call    cs:__imp_KeStackAttachProcess
0x180061588  nop     dword ptr [rax+rax+00h]
0x18006158d  lea     rax, [rbp+var_80]
0x180061591  xor     r9d, r9d; int
0x180061594  mov     [rsp+130h+var_D8], rax; __int64
0x180061599  xor     r8d, r8d; int
0x18006159c  mov     [rsp+130h+var_E0], r12; __int64
0x1800615a1  mov     dl, 1; int
0x1800615a3  mov     [rsp+130h+var_E8], r12; __int64
0x1800615a8  mov     rcx, r14; int
0x1800615ab  mov     qword ptr [rsp+130h+var_F0], r12; int
0x1800615b0  mov     qword ptr [rsp+130h+var_F8], r12; int
0x1800615b5  mov     [rsp+130h+var_100], r12; PCUNICODE_STRING
0x1800615ba  mov     [rsp+130h+SourceString], rsi; SourceString
0x1800615bf  mov     [rsp+130h+var_110], r12d; int
0x1800615c4  call    I_ReloadCatalog
0x1800615c9  lea     rcx, [rbp+ApcState]; ApcState
0x1800615cd  mov     esi, eax
0x1800615cf  call    cs:__imp_KeUnstackDetachProcess
0x1800615d6  nop     dword ptr [rax+rax+00h]
0x1800615db  mov     rcx, rbx
0x1800615de  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1800615e5  nop     dword ptr [rax+rax+00h]
0x1800615ea  lea     rcx, [r13+18h]; Resource
0x1800615ee  call    cs:__imp_ExReleaseResourceLite
0x1800615f5  nop     dword ptr [rax+rax+00h]
0x1800615fa  call    cs:__imp_KeLeaveCriticalRegion
0x180061601  nop     dword ptr [rax+rax+00h]
0x180061606  cmp     [rbp+UnicodeString.Buffer], r12
0x18006160a  jz      short loc_18006161C
0x18006160c  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180061610  call    cs:__imp_RtlFreeUnicodeString
0x180061617  nop     dword ptr [rax+rax+00h]
0x18006161c  mov     eax, esi
0x18006161e  mov     rcx, [rbp+var_10]
0x180061622  xor     rcx, rsp; StackCookie
0x180061625  call    __security_check_cookie
0x18006162a  mov     rbx, [rsp+130h+arg_18]
0x180061632  add     rsp, 130h
0x180061639  pop     r15
0x18006163b  pop     r14
0x18006163d  pop     r13
0x18006163f  pop     r12
0x180061641  pop     rdi
0x180061642  pop     rsi
0x180061643  pop     rbp
0x180061644  retn
```
