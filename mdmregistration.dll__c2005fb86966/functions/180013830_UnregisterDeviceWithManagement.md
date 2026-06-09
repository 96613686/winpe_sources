# UnregisterDeviceWithManagement

- ea: `0x180013830`
- end: `0x180013bea`
- name: `UnregisterDeviceWithManagement`
- size: `954`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x180004a7c`
- `0x180005b20`
- `0x18000cf04`
- `0x180012fcc`
- `0x180013830`
- `0x18003ba2c`
- `0x1800469e8`
- `0x18004b97c`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180013b49`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180013b49`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800138a5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800138a5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180013b66`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180013b66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013a1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013a1b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180013bc0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180013bc0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800138bd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800138bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UnregisterDeviceWithManagement(unsigned __int16 *a1)
{
  HRESULT v2; // ebx
  int v3; // ebx
  int EnrollmentGUIDAsString; // edi
  unsigned __int16 *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  LPWSTR FileNameW; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v13; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v16; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v18; // [rsp+50h] [rbp-B0h] BYREF
  __int128 Buf2; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID Buf1; // [rsp+70h] [rbp-90h] BYREF
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Filename[264]; // [rsp+A0h] [rbp-60h] BYREF

  v17 = 0;
  Buf2 = 0;
  v15 = 0;
  if ( WindowsCreateStringReference(L"Windows.Internal.Management.Enrollment.Enroller", 0x2Fu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  Buf1 = 0;
  v2 = CoInitializeEx(0, 0);
  if ( v2 < 0 )
  {
    EnrollmentGUIDAsString = v2;
    v3 = 0;
  }
  else
  {
    v3 = 1;
    if ( !a1
      || (EnrollmentGUIDAsString = DmConvertInternalAccountIdToEnrollmentId(a1, &Buf1), EnrollmentGUIDAsString >= 0) )
    {
      EnrollmentGUIDAsString = (*(__int64 (__fastcall **)(void *, __int64, __int64 *))(off_1800704F8 + 32LL))(
                                 &off_1800704F8,
                                 222306401,
                                 &v17);
      if ( EnrollmentGUIDAsString >= 0 )
      {
        EnrollmentGUIDAsString = Windows::Foundation::ActivateInstance<Windows::Internal::Management::Enrollment::IEnrollment>(
                                   string,
                                   &v15);
        if ( EnrollmentGUIDAsString >= 0 )
        {
LABEL_8:
          v14 = 0;
          while ( !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 24LL))(v17, &v14) )
          {
            v16 = 0;
            EnrollmentGUIDAsString = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v14 + 24LL))(
                                       v14,
                                       &Buf2);
            if ( EnrollmentGUIDAsString >= 0 && (!a1 || !memcmp_0(&Buf1, &Buf2, 0x10u)) )
            {
              v18 = Buf2;
              EnrollmentGUIDAsString = get_EnrollmentGUIDAsString(&v18, &v16);
              if ( EnrollmentGUIDAsString < 0 )
              {
                if ( v14 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                goto LABEL_37;
              }
              v13 = 0;
              EnrollmentGUIDAsString = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v15 + 48LL))(
                                         v15,
                                         v16,
                                         &v13);
              WindowsDeleteString(v16);
              if ( EnrollmentGUIDAsString < 0 )
              {
                v8 = v13;
                if ( v13 )
                {
                  v13 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
                }
                if ( v14 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                goto LABEL_37;
              }
              EnrollmentGUIDAsString = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(v13);
              if ( EnrollmentGUIDAsString < 0 )
              {
                v7 = v13;
                if ( v13 )
                {
                  v13 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
                }
                if ( v14 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                goto LABEL_37;
              }
              PopupUnenrollmentUI(v5);
              v6 = v13;
              if ( v13 )
              {
                v13 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
              }
            }
            if ( v14 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
              goto LABEL_8;
            }
          }
          if ( v14 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
    }
  }
LABEL_37:
  memset_0(Filename, 0, 0x208u);
  if ( GetModuleFileNameW(0, Filename, 0x104u)
    && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 2) != 0 )
  {
    FileNameW = PathFindFileNameW(Filename);
    McTemplateU0zd_EventWriteTransfer(
      v10,
      EnterpriseDiagnosticsMDMRegistrationUnregisterDevice,
      FileNameW,
      (unsigned int)EnrollmentGUIDAsString);
  }
  v11 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v3 )
    CoUninitialize();
  return (unsigned int)EnrollmentGUIDAsString;
}

```

## disassembly

```asm
0x180013830  push    rbp
0x180013832  push    rbx
0x180013833  push    rsi
0x180013834  push    rdi
0x180013835  lea     rbp, [rsp-1C8h]
0x18001383d  sub     rsp, 2C8h
0x180013844  mov     rax, cs:__security_cookie
0x18001384b  xor     rax, rsp
0x18001384e  mov     [rbp+1E0h+var_30], rax
0x180013855  mov     rsi, rcx
0x180013858  mov     [rsp+2E0h+var_2A0], 0
0x180013861  xorps   xmm0, xmm0
0x180013864  movups  [rsp+2E0h+Buf2], xmm0
0x180013869  mov     [rsp+2E0h+var_2B0], 0
0x180013872  lea     r9, [rbp+1E0h+string]; string
0x180013876  lea     r8, [rbp+1E0h+hstringHeader]; hstringHeader
0x18001387a  mov     edx, 2Fh ; '/'; length
0x18001387f  lea     rcx, ?RuntimeClass_Windows_Internal_Management_Enrollment_Enroller@@3QBGB; "Windows.Internal.Management.Enrollment."...
0x180013886  call    cs:__imp_WindowsCreateStringReference
0x18001388d  nop     dword ptr [rax+rax+00h]
0x180013892  test    eax, eax
0x180013894  jns     short loc_1800138B1
0x180013896  xor     r9d, r9d; lpArguments
0x180013899  xor     r8d, r8d; nNumberOfArguments
0x18001389c  lea     edx, [r9+1]; dwExceptionFlags
0x1800138a0  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800138a5  call    cs:__imp_RaiseException
0x1800138ac  nop     dword ptr [rax+rax+00h]
0x1800138b1  xorps   xmm0, xmm0
0x1800138b4  movups  [rsp+2E0h+Buf1], xmm0
0x1800138b9  xor     edx, edx; dwCoInit
0x1800138bb  xor     ecx, ecx; pvReserved
0x1800138bd  call    cs:__imp_CoInitializeEx
0x1800138c4  nop     dword ptr [rax+rax+00h]
0x1800138c9  mov     ebx, eax
0x1800138cb  test    eax, eax
0x1800138cd  js      loc_180013B28
0x1800138d3  not     ebx
0x1800138d5  shr     ebx, 1Fh
0x1800138d8  test    rsi, rsi
0x1800138db  jz      short loc_1800138F4
0x1800138dd  lea     rdx, [rsp+2E0h+Buf1]; struct _GUID *
0x1800138e2  mov     rcx, rsi; unsigned __int16 *
0x1800138e5  call    ?DmConvertInternalAccountIdToEnrollmentId@@YAJPEAGPEAU_GUID@@@Z; DmConvertInternalAccountIdToEnrollmentId(ushort *,_GUID *)
0x1800138ea  mov     edi, eax
0x1800138ec  test    eax, eax
0x1800138ee  js      loc_180013B2C
0x1800138f4  mov     rax, cs:off_1800704F8
0x1800138fb  lea     r8, [rsp+2E0h+var_2A0]
0x180013900  mov     edx, 0D402061h
0x180013905  lea     rcx, off_1800704F8
0x18001390c  mov     rax, [rax+20h]
0x180013910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013915  mov     edi, eax
0x180013917  test    eax, eax
0x180013919  js      loc_180013B2C
0x18001391f  mov     rdi, [rbp+1E0h+string]
0x180013923  mov     rcx, [rsp+2E0h+var_2B0]
0x180013928  test    rcx, rcx
0x18001392b  jz      short loc_180013943
0x18001392d  mov     [rsp+2E0h+var_2B0], 0
0x180013936  mov     rax, [rcx]
0x180013939  mov     rax, [rax+10h]
0x18001393d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013942  nop
0x180013943  lea     rdx, [rsp+2E0h+var_2B0]
0x180013948  mov     rcx, rdi
0x18001394b  call    ??$ActivateInstance@UIEnrollment@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIEnrollment@Enrollment@Management@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::Management::Enrollment::IEnrollment>(HSTRING__ *,Windows::Internal::Management::Enrollment::IEnrollment * *)
0x180013950  mov     edi, eax
0x180013952  test    eax, eax
0x180013954  js      loc_180013B2C
0x18001395a  mov     [rsp+2E0h+var_2B8], 0
0x180013963  mov     rcx, [rsp+2E0h+var_2A0]
0x180013968  mov     rax, [rcx]
0x18001396b  lea     rdx, [rsp+2E0h+var_2B8]
0x180013970  mov     rax, [rax+18h]
0x180013974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013979  test    eax, eax
0x18001397b  jnz     loc_180013B0F
0x180013981  mov     [rsp+2E0h+var_2A8], 0
0x18001398a  mov     rcx, [rsp+2E0h+var_2B8]
0x18001398f  mov     rax, [rcx]
0x180013992  lea     rdx, [rsp+2E0h+Buf2]
0x180013997  mov     rax, [rax+18h]
0x18001399b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139a0  mov     edi, eax
0x1800139a2  test    eax, eax
0x1800139a4  js      loc_180013A65
0x1800139aa  test    rsi, rsi
0x1800139ad  jz      short loc_1800139CC
0x1800139af  mov     r8d, 10h; Size
0x1800139b5  lea     rdx, [rsp+2E0h+Buf2]; Buf2
0x1800139ba  lea     rcx, [rsp+2E0h+Buf1]; Buf1
0x1800139bf  call    memcmp_0
0x1800139c4  test    eax, eax
0x1800139c6  jnz     loc_180013A65
0x1800139cc  movaps  xmm0, [rsp+2E0h+Buf2]
0x1800139d1  movdqa  [rsp+2E0h+var_290], xmm0
0x1800139d7  lea     rdx, [rsp+2E0h+var_2A8]
0x1800139dc  lea     rcx, [rsp+2E0h+var_290]
0x1800139e1  call    get_EnrollmentGUIDAsString
0x1800139e6  mov     edi, eax
0x1800139e8  test    eax, eax
0x1800139ea  js      loc_180013AF6
0x1800139f0  mov     [rsp+2E0h+var_2C0], 0
0x1800139f9  mov     rcx, [rsp+2E0h+var_2B0]
0x1800139fe  mov     rax, [rcx]
0x180013a01  lea     r8, [rsp+2E0h+var_2C0]
0x180013a06  mov     rdx, [rsp+2E0h+var_2A8]
0x180013a0b  mov     rax, [rax+30h]
0x180013a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a14  mov     edi, eax
0x180013a16  mov     rcx, [rsp+2E0h+var_2A8]; string
0x180013a1b  call    cs:__imp_WindowsDeleteString
0x180013a22  nop     dword ptr [rax+rax+00h]
0x180013a27  test    edi, edi
0x180013a29  js      loc_180013ABD
0x180013a2f  mov     rcx, [rsp+2E0h+var_2C0]
0x180013a34  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x180013a39  mov     edi, eax
0x180013a3b  test    eax, eax
0x180013a3d  js      short loc_180013A84
0x180013a3f  call    ?PopupUnenrollmentUI@@YAJPEAG@Z; PopupUnenrollmentUI(ushort *)
0x180013a44  nop
0x180013a45  mov     rcx, [rsp+2E0h+var_2C0]
0x180013a4a  test    rcx, rcx
0x180013a4d  jz      short loc_180013A65
0x180013a4f  mov     [rsp+2E0h+var_2C0], 0
0x180013a58  mov     rax, [rcx]
0x180013a5b  mov     rax, [rax+10h]
0x180013a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a64  nop
0x180013a65  mov     rcx, [rsp+2E0h+var_2B8]
0x180013a6a  test    rcx, rcx
0x180013a6d  jz      loc_180013963
0x180013a73  mov     rax, [rcx]
0x180013a76  mov     rax, [rax+10h]
0x180013a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a7f  jmp     loc_18001395A
0x180013a84  mov     rcx, [rsp+2E0h+var_2C0]
0x180013a89  test    rcx, rcx
0x180013a8c  jz      short loc_180013AA4
0x180013a8e  mov     [rsp+2E0h+var_2C0], 0
0x180013a97  mov     rax, [rcx]
0x180013a9a  mov     rax, [rax+10h]
0x180013a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013aa3  nop
0x180013aa4  mov     rcx, [rsp+2E0h+var_2B8]
0x180013aa9  test    rcx, rcx
0x180013aac  jz      short loc_180013ABB
0x180013aae  mov     rax, [rcx]
0x180013ab1  mov     rax, [rax+10h]
0x180013ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013aba  nop
0x180013abb  jmp     short loc_180013B2C
0x180013abd  mov     rcx, [rsp+2E0h+var_2C0]
0x180013ac2  test    rcx, rcx
0x180013ac5  jz      short loc_180013ADD
0x180013ac7  mov     [rsp+2E0h+var_2C0], 0
0x180013ad0  mov     rax, [rcx]
0x180013ad3  mov     rax, [rax+10h]
0x180013ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013adc  nop
0x180013add  mov     rcx, [rsp+2E0h+var_2B8]
0x180013ae2  test    rcx, rcx
0x180013ae5  jz      short loc_180013AF4
0x180013ae7  mov     rax, [rcx]
0x180013aea  mov     rax, [rax+10h]
0x180013aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013af3  nop
0x180013af4  jmp     short loc_180013B2C
0x180013af6  mov     rcx, [rsp+2E0h+var_2B8]
0x180013afb  test    rcx, rcx
0x180013afe  jz      short loc_180013B0D
0x180013b00  mov     rax, [rcx]
0x180013b03  mov     rax, [rax+10h]
0x180013b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b0c  nop
0x180013b0d  jmp     short loc_180013B2C
0x180013b0f  mov     rcx, [rsp+2E0h+var_2B8]
0x180013b14  test    rcx, rcx
0x180013b17  jz      short loc_180013B26
0x180013b19  mov     rax, [rcx]
0x180013b1c  mov     rax, [rax+10h]
0x180013b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b25  nop
0x180013b26  jmp     short loc_180013B2C
0x180013b28  mov     edi, ebx
0x180013b2a  xor     ebx, ebx
0x180013b2c  xor     edx, edx; Val
0x180013b2e  mov     r8d, 208h; Size
0x180013b34  lea     rcx, [rbp+1E0h+Filename]; void *
0x180013b38  call    memset_0
0x180013b3d  mov     r8d, 104h; nSize
0x180013b43  lea     rdx, [rbp+1E0h+Filename]; lpFilename
0x180013b47  xor     ecx, ecx; hModule
0x180013b49  call    cs:__imp_GetModuleFileNameW
0x180013b50  nop     dword ptr [rax+rax+00h]
0x180013b55  test    eax, eax
0x180013b57  jz      short loc_180013B85
0x180013b59  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 2
0x180013b60  jz      short loc_180013B85
0x180013b62  lea     rcx, [rbp+1E0h+Filename]; pszPath
0x180013b66  call    cs:__imp_PathFindFileNameW
0x180013b6d  nop     dword ptr [rax+rax+00h]
0x180013b72  mov     r8, rax
0x180013b75  mov     r9d, edi
0x180013b78  lea     rdx, EnterpriseDiagnosticsMDMRegistrationUnregisterDevice
0x180013b7f  call    McTemplateU0zd_EventWriteTransfer
0x180013b84  nop
0x180013b85  mov     rcx, [rsp+2E0h+var_2B0]
0x180013b8a  test    rcx, rcx
0x180013b8d  jz      short loc_180013BA5
0x180013b8f  mov     [rsp+2E0h+var_2B0], 0
0x180013b98  mov     rax, [rcx]
0x180013b9b  mov     rax, [rax+10h]
0x180013b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ba4  nop
0x180013ba5  mov     rcx, [rsp+2E0h+var_2A0]
0x180013baa  test    rcx, rcx
0x180013bad  jz      short loc_180013BBC
0x180013baf  mov     rax, [rcx]
0x180013bb2  mov     rax, [rax+10h]
0x180013bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bbb  nop
0x180013bbc  test    ebx, ebx
0x180013bbe  jz      short loc_180013BCC
0x180013bc0  call    cs:__imp_CoUninitialize
0x180013bc7  nop     dword ptr [rax+rax+00h]
0x180013bcc  mov     eax, edi
0x180013bce  mov     rcx, [rbp+1E0h+var_30]
0x180013bd5  xor     rcx, rsp; StackCookie
0x180013bd8  call    __security_check_cookie
0x180013bdd  add     rsp, 2C8h
0x180013be4  pop     rdi
0x180013be5  pop     rsi
0x180013be6  pop     rbx
0x180013be7  pop     rbp
0x180013be8  retn
```
