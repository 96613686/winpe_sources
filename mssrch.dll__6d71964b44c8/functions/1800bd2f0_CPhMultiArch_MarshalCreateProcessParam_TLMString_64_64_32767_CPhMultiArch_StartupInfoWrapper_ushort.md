# CPhMultiArch::MarshalCreateProcessParam(TLMString<64,64,32767> &,CPhMultiArch::StartupInfoWrapper *,ushort *)

- ea: `0x1800bd2f0`
- end: `0x1800bd4c7`
- name: `?MarshalCreateProcessParam@CPhMultiArch@@SAJAEAV?$TLMString@$0EA@$0EA@$0HPPP@@@PEAVStartupInfoWrapper@1@PEAG@Z`
- size: `471`
- prototype: `__int64 __fastcall(CLMString *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002538c`
- `0x1801b5950`

## callees

- `0x18000ee60`
- `0x18000f880`
- `0x180027164`
- `0x1800bd2f0`
- `0x1800cae14`
- `0x1800f8f24`
- `0x180109038`
- `0x1801249ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800bd455`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800bd455`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800bd3ac`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800bd3fb`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800bd3ac`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800bd3fb`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800bd489`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800bd4b2`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800bd489`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800bd4b2`
- `ntdll!RtlReplaceSystemDirectoryInPath` at `0x1800bd367`
- `ntdll!RtlReplaceSystemDirectoryInPath` at `0x1800bd367`
- `ntdll!RtlInitUnicodeString` at `0x1800bd351`
- `ntdll!RtlInitUnicodeString` at `0x1800bd351`

## pseudocode

```c
int __fastcall CPhMultiArch::MarshalCreateProcessParam(CLMString *this, __int64 a2, _WORD *a3)
{
  const WCHAR *Buffer; // rax
  __int64 v7; // r9
  int v8; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v10; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v11; // rbx
  int LastError; // ebx
  const char *v13; // r9
  const char *v14; // r9
  int v15; // esi
  int cbSize; // [rsp+20h] [rbp-30h]
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  struct _PROC_THREAD_ATTRIBUTE_LIST *v19; // [rsp+80h] [rbp+30h] BYREF
  ULONG_PTR Size; // [rsp+88h] [rbp+38h] BYREF

  DestinationString = 0;
  if ( *a3 != 332 && *a3 != 452 && *a3 != 0x8664 && *a3 != 0xAA64 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  Buffer = CLMString::GetBuffer(this, 0);
  RtlInitUnicodeString(&DestinationString, Buffer);
  LOBYTE(v7) = 1;
  v8 = RtlReplaceSystemDirectoryInPath(&DestinationString, 1, (unsigned __int16)*a3, v7);
  if ( v8 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x266,
             (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\phmultiarch.cxx",
             (const char *)(unsigned int)v8,
             cbSize);
  if ( !a2 )
    return 0;
  Size = 0;
  InitializeProcThreadAttributeList(0, 1u, 0, &Size);
  v10 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)operator new[](Size, (const struct std::nothrow_t *)&std::nothrow);
  v19 = v10;
  v11 = v10;
  if ( !v10 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x278,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\phmultiarch.cxx",
      (const char *)0x8007000ELL,
      cbSize);
LABEL_13:
    std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&v19);
    return LastError;
  }
  if ( !InitializeProcThreadAttributeList(v10, 1u, 0, &Size) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x27C,
                  (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\phmultiarch.cxx",
                  v13);
    goto LABEL_13;
  }
  if ( UpdateProcThreadAttribute(v11, 0, 0x20019u, a3, 2u, 0, 0) )
  {
    *(_QWORD *)(a2 + 104) = v11;
    v19 = 0;
    std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&v19);
    if ( !*(_QWORD *)(a2 + 104) )
      DeleteProcThreadAttributeList(v11);
    return 0;
  }
  v15 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x286,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\phmultiarch.cxx",
          v14);
  std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&v19);
  if ( !*(_QWORD *)(a2 + 104) )
    DeleteProcThreadAttributeList(v11);
  return v15;
}

```

## disassembly

```asm
0x1800bd2f0  mov     [rsp-18h+arg_0], rbx
0x1800bd2f5  push    rbp
0x1800bd2f6  push    rsi
0x1800bd2f7  push    rdi
0x1800bd2f8  mov     rbp, rsp
0x1800bd2fb  sub     rsp, 50h
0x1800bd2ff  mov     eax, 14Ch
0x1800bd304  xorps   xmm0, xmm0
0x1800bd307  mov     rsi, r8
0x1800bd30a  mov     rdi, rdx
0x1800bd30d  mov     rbx, rcx
0x1800bd310  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800bd314  cmp     [r8], ax
0x1800bd318  jz      short loc_1800BD340
0x1800bd31a  mov     eax, 1C4h
0x1800bd31f  cmp     [r8], ax
0x1800bd323  jz      short loc_1800BD340
0x1800bd325  mov     eax, 8664h
0x1800bd32a  cmp     [r8], ax
0x1800bd32e  jz      short loc_1800BD340
0x1800bd330  mov     eax, 0AA64h
0x1800bd335  cmp     [r8], ax
0x1800bd339  jz      short loc_1800BD340
0x1800bd33b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800bd340  xor     edx, edx; int
0x1800bd342  mov     rcx, rbx; this
0x1800bd345  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x1800bd34a  mov     rdx, rax; SourceString
0x1800bd34d  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800bd351  call    cs:__imp_RtlInitUnicodeString
0x1800bd357  movzx   r8d, word ptr [rsi]
0x1800bd35b  lea     rcx, [rbp+DestinationString]
0x1800bd35f  mov     edx, 1
0x1800bd364  mov     r9b, dl
0x1800bd367  call    cs:__imp_RtlReplaceSystemDirectoryInPath
0x1800bd36d  test    eax, eax
0x1800bd36f  jns     short loc_1800BD38E
0x1800bd371  mov     rcx, [rbp+18h]; this
0x1800bd375  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800bd37c  mov     r9d, eax; char *
0x1800bd37f  mov     edx, 266h; void *
0x1800bd384  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800bd389  jmp     loc_1800BD4BA
0x1800bd38e  test    rdi, rdi
0x1800bd391  jz      loc_1800BD4B8
0x1800bd397  xor     r8d, r8d; dwFlags
0x1800bd39a  mov     [rbp+Size], 0
0x1800bd3a2  lea     r9, [rbp+Size]; lpSize
0x1800bd3a6  xor     ecx, ecx; lpAttributeList
0x1800bd3a8  lea     edx, [r8+1]; dwAttributeCount
0x1800bd3ac  call    cs:__imp_InitializeProcThreadAttributeList
0x1800bd3b2  mov     rcx, [rbp+Size]; unsigned __int64
0x1800bd3b6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bd3bd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800bd3c2  mov     [rbp+arg_10], rax
0x1800bd3c6  mov     rbx, rax
0x1800bd3c9  test    rax, rax
0x1800bd3cc  jnz     short loc_1800BD3ED
0x1800bd3ce  mov     rcx, [rbp+18h]; this
0x1800bd3d2  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800bd3d9  mov     ebx, 8007000Eh
0x1800bd3de  mov     edx, 278h; void *
0x1800bd3e3  mov     r9d, ebx; char *
0x1800bd3e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd3eb  jmp     short loc_1800BD41C
0x1800bd3ed  xor     r8d, r8d; dwFlags
0x1800bd3f0  lea     r9, [rbp+Size]; lpSize
0x1800bd3f4  mov     rcx, rbx; lpAttributeList
0x1800bd3f7  lea     edx, [r8+1]; dwAttributeCount
0x1800bd3fb  call    cs:__imp_InitializeProcThreadAttributeList
0x1800bd401  test    eax, eax
0x1800bd403  jnz     short loc_1800BD42C
0x1800bd405  mov     rcx, [rbp+18h]; this
0x1800bd409  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800bd410  mov     edx, 27Ch; void *
0x1800bd415  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800bd41a  mov     ebx, eax
0x1800bd41c  lea     rcx, [rbp+arg_10]
0x1800bd420  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1800bd425  mov     eax, ebx
0x1800bd427  jmp     loc_1800BD4BA
0x1800bd42c  mov     [rsp+50h+lpReturnSize], 0; lpReturnSize
0x1800bd435  mov     r9, rsi; lpValue
0x1800bd438  mov     [rsp+50h+lpPreviousValue], 0; lpPreviousValue
0x1800bd441  xor     edx, edx; dwFlags
0x1800bd443  mov     r8d, 20019h; Attribute
0x1800bd449  mov     [rsp+50h+cbSize], 2; cbSize
0x1800bd452  mov     rcx, rbx; lpAttributeList
0x1800bd455  call    cs:__imp_UpdateProcThreadAttribute
0x1800bd45b  test    eax, eax
0x1800bd45d  jnz     short loc_1800BD493
0x1800bd45f  mov     rcx, [rbp+18h]; this
0x1800bd463  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800bd46a  mov     edx, 286h; void *
0x1800bd46f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800bd474  lea     rcx, [rbp+arg_10]
0x1800bd478  mov     esi, eax
0x1800bd47a  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1800bd47f  cmp     qword ptr [rdi+68h], 0
0x1800bd484  jnz     short loc_1800BD48F
0x1800bd486  mov     rcx, rbx; lpAttributeList
0x1800bd489  call    cs:__imp_DeleteProcThreadAttributeList
0x1800bd48f  mov     eax, esi
0x1800bd491  jmp     short loc_1800BD4BA
0x1800bd493  lea     rcx, [rbp+arg_10]
0x1800bd497  mov     [rdi+68h], rbx
0x1800bd49b  mov     [rbp+arg_10], 0
0x1800bd4a3  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1800bd4a8  cmp     qword ptr [rdi+68h], 0
0x1800bd4ad  jnz     short loc_1800BD4B8
0x1800bd4af  mov     rcx, rbx; lpAttributeList
0x1800bd4b2  call    cs:__imp_DeleteProcThreadAttributeList
0x1800bd4b8  xor     eax, eax
0x1800bd4ba  mov     rbx, [rsp+50h+arg_0]
0x1800bd4bf  add     rsp, 50h
0x1800bd4c3  pop     rdi
0x1800bd4c4  pop     rsi
0x1800bd4c5  pop     rbp
0x1800bd4c6  retn
```
