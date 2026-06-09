# DfsRootFolder::RenamePath(_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x14002ec0c`
- end: `0x14002ef5c`
- name: `?RenamePath@DfsRootFolder@@QEAAKPEAU_UNICODE_STRING@@0@Z`
- size: `848`
- prototype: `unsigned int(DfsRootFolder *__hidden this, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x1400291d0`
- `0x1400296d8`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x14000fd24`
- `0x1400298e0`
- `0x14002ec0c`
- `0x1400586a8`
- `0x140058db8`

## import_xrefs

- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ed1b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ed2f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ed42`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ed56`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ed6a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ed91`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002eda5`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002edfc`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ee10`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ee23`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ee37`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ee4a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ee5e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ed1b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ed2f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ed42`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ed56`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ed6a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ed91`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002eda5`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002edfc`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ee10`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ee23`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ee37`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ee4a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14002ee5e`
- `ntdll!RtlAppendUnicodeToString` at `0x14002ed7e`
- `ntdll!RtlAppendUnicodeToString` at `0x14002ed7e`
- `ntdll!RtlNtStatusToDosError` at `0x14002ee73`
- `ntdll!RtlNtStatusToDosError` at `0x14002ee73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002eea9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002eea9`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14002ee99`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14002ee99`

## pseudocode

```c
__int64 __fastcall DfsRootFolder::RenamePath(
        DfsRootFolder *this,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3)
{
  const UNICODE_STRING *v3; // r15
  DfsRootFolder *v6; // rcx
  unsigned int v7; // eax
  PWSTR Buffer; // r13
  ULONG LastError; // edi
  unsigned int v10; // ebx
  WCHAR *v11; // rax
  NTSTATUS appended; // eax
  unsigned int v13; // ebx
  WCHAR *v14; // rax
  struct _UNICODE_STRING Destination; // [rsp+38h] [rbp-19h] BYREF
  struct _UNICODE_STRING v17; // [rsp+48h] [rbp-9h] BYREF
  UNICODE_STRING Source; // [rsp+58h] [rbp+7h] BYREF
  UNICODE_STRING v19; // [rsp+68h] [rbp+17h] BYREF
  struct _UNICODE_STRING v20; // [rsp+78h] [rbp+27h] BYREF
  UNICODE_STRING v21; // [rsp+88h] [rbp+37h] BYREF

  *(_DWORD *)(&Source.MaximumLength + 1) = 0;
  v3 = (const UNICODE_STRING *)((char *)this + 184);
  *(_DWORD *)(&v19.MaximumLength + 1) = 0;
  Destination = 0;
  v17 = 0;
  v20 = 0;
  v21 = 0;
  DfsRtlInitUnicodeStringEx(&Destination, 0);
  DfsRtlInitUnicodeStringEx(&v17, 0);
  DfsRtlInitUnicodeStringEx(&v20, 0);
  *(_DWORD *)&Source.Length = 131074;
  Source.Buffer = (PWSTR)L"\\";
  *(_DWORD *)&v19.Length = 131074;
  v19.Buffer = (PWSTR)&dword_140064ADC;
  DfsRtlInitUnicodeStringEx(&v21, L"DFS.");
  v7 = DfsRootFolder::CreateRenameName(v6, &v20);
  Buffer = v20.Buffer;
  LastError = v7;
  if ( v7 )
    goto LABEL_12;
  v10 = v19.Length + v20.Length + v21.Length + v3->Length + a3->Length + a2->Length + 3 * Source.Length;
  if ( v10 > 0xFFFF )
    goto LABEL_12;
  v11 = (WCHAR *)operator new(v10);
  if ( !v11 )
    goto LABEL_8;
  Destination.Buffer = v11;
  Destination.MaximumLength = v10;
  RtlAppendUnicodeStringToString(&Destination, v3);
  RtlAppendUnicodeStringToString(&Destination, &Source);
  RtlAppendUnicodeStringToString(&Destination, a2);
  RtlAppendUnicodeStringToString(&Destination, &Source);
  RtlAppendUnicodeStringToString(&Destination, &v21);
  RtlAppendUnicodeToString(&Destination, Buffer + 1);
  RtlAppendUnicodeStringToString(&Destination, a3);
  appended = RtlAppendUnicodeStringToString(&Destination, &v19);
  if ( !appended )
  {
    v13 = v19.Length + v3->Length + a3->Length + a2->Length + 2 * Source.Length;
    if ( v13 > 0xFFFF )
      goto LABEL_12;
    v14 = (WCHAR *)operator new(v13);
    if ( v14 )
    {
      v17.Buffer = v14;
      v17.MaximumLength = v13;
      RtlAppendUnicodeStringToString(&v17, v3);
      RtlAppendUnicodeStringToString(&v17, &Source);
      RtlAppendUnicodeStringToString(&v17, a2);
      RtlAppendUnicodeStringToString(&v17, &Source);
      RtlAppendUnicodeStringToString(&v17, a3);
      appended = RtlAppendUnicodeStringToString(&v17, &v19);
      goto LABEL_9;
    }
LABEL_8:
    appended = -1073741670;
  }
LABEL_9:
  LastError = RtlNtStatusToDosError(appended);
  if ( !LastError && !MoveFileExW((LPCWSTR)v17.Buffer + 4, (LPCWSTR)Destination.Buffer + 4, 2u) )
    LastError = GetLastError();
LABEL_12:
  if ( Buffer )
    DfsFreeUnicodeString(&v20);
  if ( v17.Buffer )
    operator delete(v17.Buffer);
  if ( Destination.Buffer )
    operator delete(Destination.Buffer);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (((1 << (LastError != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_ZD(
      *((_QWORD *)pWppControl + 2),
      82,
      (unsigned int)WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids,
      (_DWORD)a2,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x14002ec0c  mov     rax, rsp
0x14002ec0f  mov     [rax+8], rbx
0x14002ec13  mov     [rax+10h], rsi
0x14002ec17  mov     [rax+18h], rdi
0x14002ec1b  mov     [rax+20h], r13
0x14002ec1f  push    rbp
0x14002ec20  push    r14
0x14002ec22  push    r15
0x14002ec24  lea     rbp, [rax-5Fh]
0x14002ec28  sub     rsp, 90h
0x14002ec2f  and     dword ptr [rbp+57h+Source+4], 0
0x14002ec33  lea     r15, [rcx+0B8h]
0x14002ec3a  and     dword ptr [rbp+57h+var_40+4], 0
0x14002ec3e  lea     rcx, [rbp+57h+Destination]
0x14002ec42  xorps   xmm0, xmm0
0x14002ec45  mov     rsi, rdx
0x14002ec48  xorps   xmm1, xmm1
0x14002ec4b  xor     edx, edx
0x14002ec4d  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x14002ec51  mov     r14, r8
0x14002ec54  movups  xmmword ptr [rbp+57h+var_60.Length], xmm1
0x14002ec58  movups  xmmword ptr [rbp+57h+var_30.Length], xmm0
0x14002ec5c  movups  xmmword ptr [rbp+57h+var_20.Length], xmm0
0x14002ec60  call    DfsRtlInitUnicodeStringEx
0x14002ec65  xor     edx, edx
0x14002ec67  lea     rcx, [rbp+57h+var_60]
0x14002ec6b  call    DfsRtlInitUnicodeStringEx
0x14002ec70  xor     edx, edx
0x14002ec72  lea     rcx, [rbp+57h+var_30]
0x14002ec76  call    DfsRtlInitUnicodeStringEx
0x14002ec7b  lea     rax, asc_14006334C; "\\"
0x14002ec82  mov     dword ptr [rbp+57h+Source.Length], 20002h
0x14002ec89  mov     [rbp+57h+Source.Buffer], rax
0x14002ec8d  lea     rdx, aDfs; "DFS."
0x14002ec94  lea     rax, dword_140064ADC
0x14002ec9b  mov     dword ptr [rbp+57h+var_40.Length], 20002h
0x14002eca2  lea     rcx, [rbp+57h+var_20]
0x14002eca6  mov     [rbp+57h+var_40.Buffer], rax
0x14002ecaa  call    DfsRtlInitUnicodeStringEx
0x14002ecaf  lea     rdx, [rbp+57h+var_30]; struct _UNICODE_STRING *
0x14002ecb3  call    ?CreateRenameName@DfsRootFolder@@QEAAKPEAU_UNICODE_STRING@@@Z; DfsRootFolder::CreateRenameName(_UNICODE_STRING *)
0x14002ecb8  mov     r13, [rbp+57h+var_30.Buffer]
0x14002ecbc  mov     edi, eax
0x14002ecbe  test    eax, eax
0x14002ecc0  jnz     loc_14002EEB7
0x14002ecc6  movzx   ecx, [rbp+57h+Source.Length]
0x14002ecca  movzx   eax, [rbp+57h+var_20.Length]
0x14002ecce  lea     ebx, [rcx+rcx*2]
0x14002ecd1  movzx   ecx, word ptr [rsi]
0x14002ecd4  add     ebx, ecx
0x14002ecd6  movzx   ecx, word ptr [r14]
0x14002ecda  add     ebx, ecx
0x14002ecdc  movzx   ecx, word ptr [r15]
0x14002ece0  add     ebx, ecx
0x14002ece2  add     ebx, eax
0x14002ece4  movzx   eax, [rbp+57h+var_30.Length]
0x14002ece8  add     ebx, eax
0x14002ecea  movzx   eax, [rbp+57h+var_40.Length]
0x14002ecee  add     ebx, eax
0x14002ecf0  cmp     ebx, 0FFFFh
0x14002ecf6  ja      loc_14002EEB7
0x14002ecfc  mov     ecx, ebx; Size
0x14002ecfe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002ed03  test    rax, rax
0x14002ed06  jz      loc_14002EE6C
0x14002ed0c  mov     rdx, r15; Source
0x14002ed0f  mov     [rbp+57h+Destination.Buffer], rax
0x14002ed13  lea     rcx, [rbp+57h+Destination]; Destination
0x14002ed17  mov     [rbp+57h+Destination.MaximumLength], bx
0x14002ed1b  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002ed22  nop     dword ptr [rax+rax+00h]
0x14002ed27  lea     rdx, [rbp+57h+Source]; Source
0x14002ed2b  lea     rcx, [rbp+57h+Destination]; Destination
0x14002ed2f  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002ed36  nop     dword ptr [rax+rax+00h]
0x14002ed3b  mov     rdx, rsi; Source
0x14002ed3e  lea     rcx, [rbp+57h+Destination]; Destination
0x14002ed42  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002ed49  nop     dword ptr [rax+rax+00h]
0x14002ed4e  lea     rdx, [rbp+57h+Source]; Source
0x14002ed52  lea     rcx, [rbp+57h+Destination]; Destination
0x14002ed56  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002ed5d  nop     dword ptr [rax+rax+00h]
0x14002ed62  lea     rdx, [rbp+57h+var_20]; Source
0x14002ed66  lea     rcx, [rbp+57h+Destination]; Destination
0x14002ed6a  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002ed71  nop     dword ptr [rax+rax+00h]
0x14002ed76  lea     rdx, [r13+2]; Source
0x14002ed7a  lea     rcx, [rbp+57h+Destination]; Destination
0x14002ed7e  call    cs:__imp_RtlAppendUnicodeToString
0x14002ed85  nop     dword ptr [rax+rax+00h]
0x14002ed8a  mov     rdx, r14; Source
0x14002ed8d  lea     rcx, [rbp+57h+Destination]; Destination
0x14002ed91  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002ed98  nop     dword ptr [rax+rax+00h]
0x14002ed9d  lea     rdx, [rbp+57h+var_40]; Source
0x14002eda1  lea     rcx, [rbp+57h+Destination]; Destination
0x14002eda5  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002edac  nop     dword ptr [rax+rax+00h]
0x14002edb1  test    eax, eax
0x14002edb3  jnz     loc_14002EE71
0x14002edb9  movzx   eax, word ptr [rsi]
0x14002edbc  movzx   ecx, [rbp+57h+Source.Length]
0x14002edc0  lea     ebx, [rax+rcx*2]
0x14002edc3  movzx   eax, word ptr [r14]
0x14002edc7  add     ebx, eax
0x14002edc9  movzx   eax, word ptr [r15]
0x14002edcd  add     ebx, eax
0x14002edcf  movzx   eax, [rbp+57h+var_40.Length]
0x14002edd3  add     ebx, eax
0x14002edd5  cmp     ebx, 0FFFFh
0x14002eddb  ja      loc_14002EEB7
0x14002ede1  mov     ecx, ebx; Size
0x14002ede3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002ede8  test    rax, rax
0x14002edeb  jz      short loc_14002EE6C
0x14002eded  mov     rdx, r15; Source
0x14002edf0  mov     [rbp+57h+var_60.Buffer], rax
0x14002edf4  lea     rcx, [rbp+57h+var_60]; Destination
0x14002edf8  mov     [rbp+57h+var_60.MaximumLength], bx
0x14002edfc  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002ee03  nop     dword ptr [rax+rax+00h]
0x14002ee08  lea     rdx, [rbp+57h+Source]; Source
0x14002ee0c  lea     rcx, [rbp+57h+var_60]; Destination
0x14002ee10  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002ee17  nop     dword ptr [rax+rax+00h]
0x14002ee1c  mov     rdx, rsi; Source
0x14002ee1f  lea     rcx, [rbp+57h+var_60]; Destination
0x14002ee23  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002ee2a  nop     dword ptr [rax+rax+00h]
0x14002ee2f  lea     rdx, [rbp+57h+Source]; Source
0x14002ee33  lea     rcx, [rbp+57h+var_60]; Destination
0x14002ee37  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002ee3e  nop     dword ptr [rax+rax+00h]
0x14002ee43  mov     rdx, r14; Source
0x14002ee46  lea     rcx, [rbp+57h+var_60]; Destination
0x14002ee4a  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002ee51  nop     dword ptr [rax+rax+00h]
0x14002ee56  lea     rdx, [rbp+57h+var_40]; Source
0x14002ee5a  lea     rcx, [rbp+57h+var_60]; Destination
0x14002ee5e  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002ee65  nop     dword ptr [rax+rax+00h]
0x14002ee6a  jmp     short loc_14002EE71
0x14002ee6c  mov     eax, 0C000009Ah
0x14002ee71  mov     ecx, eax; Status
0x14002ee73  call    cs:__imp_RtlNtStatusToDosError
0x14002ee7a  nop     dword ptr [rax+rax+00h]
0x14002ee7f  mov     edi, eax
0x14002ee81  test    eax, eax
0x14002ee83  jnz     short loc_14002EEB7
0x14002ee85  mov     rcx, [rbp+57h+var_60.Buffer]
0x14002ee89  lea     r8d, [rax+2]; dwFlags
0x14002ee8d  mov     rdx, [rbp+57h+Destination.Buffer]
0x14002ee91  add     rcx, 8; lpExistingFileName
0x14002ee95  add     rdx, 8; lpNewFileName
0x14002ee99  call    cs:__imp_MoveFileExW
0x14002eea0  nop     dword ptr [rax+rax+00h]
0x14002eea5  test    eax, eax
0x14002eea7  jnz     short loc_14002EEB7
0x14002eea9  call    cs:__imp_GetLastError
0x14002eeb0  nop     dword ptr [rax+rax+00h]
0x14002eeb5  mov     edi, eax
0x14002eeb7  test    r13, r13
0x14002eeba  jz      short loc_14002EEC5
0x14002eebc  lea     rcx, [rbp+57h+var_30]
0x14002eec0  call    DfsFreeUnicodeString
0x14002eec5  mov     rcx, [rbp+57h+var_60.Buffer]; Block
0x14002eec9  test    rcx, rcx
0x14002eecc  jz      short loc_14002EED3
0x14002eece  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002eed3  mov     rcx, [rbp+57h+Destination.Buffer]; Block
0x14002eed7  test    rcx, rcx
0x14002eeda  jz      short loc_14002EEE1
0x14002eedc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002eee1  lea     rax, WPP_GLOBAL_Control
0x14002eee8  cmp     cs:WPP_GLOBAL_Control, rax
0x14002eeef  jz      short loc_14002EF38
0x14002eef1  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002eef8  test    rcx, rcx
0x14002eefb  jz      short loc_14002EF38
0x14002eefd  mov     eax, edi
0x14002eeff  neg     eax
0x14002ef01  mov     eax, 20h ; ' '
0x14002ef06  sbb     edx, edx
0x14002ef08  and     edx, 0FFFFFFECh
0x14002ef0b  add     edx, 1Fh
0x14002ef0e  bts     eax, edx
0x14002ef11  test    [rcx+1Ch], eax
0x14002ef14  jz      short loc_14002EF38
0x14002ef16  cmp     byte ptr [rcx+19h], 3
0x14002ef1a  jb      short loc_14002EF38
0x14002ef1c  mov     rcx, [rcx+10h]
0x14002ef20  lea     r8, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids
0x14002ef27  mov     edx, 52h ; 'R'
0x14002ef2c  mov     [rsp+0A0h+var_80], edi
0x14002ef30  mov     r9, rsi
0x14002ef33  call    WPP_SF_ZD
0x14002ef38  lea     r11, [rsp+0A0h+var_10]
0x14002ef40  mov     eax, edi
0x14002ef42  mov     rbx, [r11+20h]
0x14002ef46  mov     rsi, [r11+28h]
0x14002ef4a  mov     rdi, [r11+30h]
0x14002ef4e  mov     r13, [r11+38h]
0x14002ef52  mov     rsp, r11
0x14002ef55  pop     r15
0x14002ef57  pop     r14
0x14002ef59  pop     rbp
0x14002ef5a  retn
```
