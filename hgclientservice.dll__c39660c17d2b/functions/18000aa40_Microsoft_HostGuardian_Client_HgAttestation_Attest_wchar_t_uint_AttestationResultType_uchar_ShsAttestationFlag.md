# Microsoft::HostGuardian::Client::HgAttestation::Attest(wchar_t *,uint,AttestationResultType *,uchar,ShsAttestationFlag *,wchar_t * *,uint *,AttestationResult * *)

- ea: `0x18000aa40`
- end: `0x18000aafa`
- name: `?Attest@HgAttestation@Client@HostGuardian@Microsoft@@UEAAJPEA_WIPEAW4AttestationResultType@@EPEAW4ShsAttestationFlag@@PEAPEA_WPEAIPEAPEAUAttestationResult@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(Microsoft::HostGuardian::Client::HgAttestation *__hidden this, wchar_t *, unsigned int, enum AttestationResultType *, char, enum ShsAttestationFlag *, wchar_t **, unsigned int *, struct AttestationResult **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800064b4`
- `0x18000aa40`
- `0x18000d4d8`

## string_xrefs

- `0x18000aae1`: `servercommon\base\securehostingservice\common\service\lib\hgattestation.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgAttestation::Attest(
        Microsoft::HostGuardian::Client::HgAttestation *this,
        wchar_t *a2,
        unsigned int a3,
        enum AttestationResultType *a4,
        char a5,
        enum ShsAttestationFlag *a6,
        wchar_t **a7,
        unsigned int *a8,
        struct AttestationResult **a9)
{
  const char *v9; // r9
  __int64 result; // rax
  wil *v11; // rcx
  __int64 i; // rdi
  struct AttestationResult *v13; // rax
  int v14; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a3 && a4 && a6 && a8 && a9 )
  {
    try
    {
      *a8 = 0;
      *a9 = 0;
      *(_DWORD *)a6 = 0;
      Microsoft::HostGuardian::Client::HgServiceController::QueryAttestationResults(
        *((Microsoft::HostGuardian::Client::HgServiceController **)g_service + 24),
        a2,
        a3,
        a4,
        a5 == 1,
        a6,
        a7,
        a8,
        a9);
      result = 0;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x37,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgattestation.cpp",
        v9);
      if ( *a9 )
      {
        for ( i = 0; (unsigned int)i < *a8; i = (unsigned int)(i + 1) )
        {
          v13 = *a9;
          if ( !*((_DWORD *)*a9 + 6 * i + 2) )
            break;
          if ( !*((_QWORD *)v13 + 3 * i + 2) )
            break;
          CoTaskMemFree(*((LPVOID *)v13 + 3 * i + 2));
          *((_QWORD *)*a9 + 3 * i + 2) = 0;
          *((_DWORD *)*a9 + 6 * i + 2) = 0;
        }
        CoTaskMemFree(*a9);
        *a9 = 0;
      }
      return (unsigned int)wil::ResultFromCaughtException(v11);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgattestation.cpp",
      (const char *)0x80070057LL,
      v14);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000aa40  push    rbx
0x18000aa42  sub     rsp, 50h
0x18000aa46  mov     r11, rdx
0x18000aa49  xor     ecx, ecx
0x18000aa4b  test    r8d, r8d
0x18000aa4e  jz      loc_18000AAD4
0x18000aa54  test    r9, r9
0x18000aa57  jz      short loc_18000AAD4
0x18000aa59  mov     r10, [rsp+58h+arg_28]
0x18000aa61  test    r10, r10
0x18000aa64  jz      short loc_18000AAD4
0x18000aa66  mov     rax, [rsp+58h+arg_38]
0x18000aa6e  test    rax, rax
0x18000aa71  jz      short loc_18000AAD4
0x18000aa73  mov     rdx, [rsp+58h+arg_40]
0x18000aa7b  test    rdx, rdx
0x18000aa7e  jz      short loc_18000AAD4
0x18000aa80  mov     [rax], ecx
0x18000aa82  mov     [rdx], rcx
0x18000aa85  mov     [r10], ecx
0x18000aa88  cmp     [rsp+58h+arg_20], 1
0x18000aa90  setz    cl
0x18000aa93  mov     [rsp+58h+var_18], rdx; struct AttestationResult **
0x18000aa98  mov     [rsp+58h+var_20], rax; unsigned int *
0x18000aa9d  mov     rax, [rsp+58h+arg_30]
0x18000aaa5  mov     [rsp+58h+var_28], rax; wchar_t **
0x18000aaaa  mov     [rsp+58h+var_30], r10; enum ShsAttestationFlag *
0x18000aaaf  mov     [rsp+58h+var_38], cl; bool
0x18000aab3  mov     rdx, r11; wchar_t *
0x18000aab6  mov     rcx, cs:?g_service@@3PEAVHgService@Client@HostGuardian@Microsoft@@EA; Microsoft::HostGuardian::Client::HgService * g_service
0x18000aabd  mov     rcx, [rcx+0C0h]; this
0x18000aac4  call    ?QueryAttestationResults@HgServiceController@Client@HostGuardian@Microsoft@@QEAAXQEA_WIPEAW4AttestationResultType@@_NPEAW4ShsAttestationFlag@@PEAPEA_WPEAIPEAPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::HgServiceController::QueryAttestationResults(wchar_t * const,uint,AttestationResultType *,bool,ShsAttestationFlag *,wchar_t * *,uint *,AttestationResult * *)
0x18000aac9  nop
0x18000aaca  xor     eax, eax
0x18000aacc  jmp     short loc_18000AAF4
0x18000aace  mov     eax, [rsp+58h+arg_10]
0x18000aad2  jmp     short loc_18000AAF4
0x18000aad4  mov     rcx, [rsp+58h]; this
0x18000aad9  mov     ebx, 80070057h
0x18000aade  mov     r9d, ebx; char *
0x18000aae1  lea     r8, aServercommonBa_5; "servercommon\\base\\securehostingservic"...
0x18000aae8  mov     edx, 22h ; '"'; void *
0x18000aaed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aaf2  mov     eax, ebx
0x18000aaf4  add     rsp, 50h
0x18000aaf8  pop     rbx
0x18000aaf9  retn
```
