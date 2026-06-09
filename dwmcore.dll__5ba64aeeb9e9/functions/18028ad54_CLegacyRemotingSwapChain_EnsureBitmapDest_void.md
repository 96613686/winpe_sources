# CLegacyRemotingSwapChain::EnsureBitmapDest(void)

- ea: `0x18028ad54`
- end: `0x18028affa`
- name: `?EnsureBitmapDest@CLegacyRemotingSwapChain@@IEAAJXZ`
- size: `678`
- prototype: `__int64 __fastcall(CLegacyRemotingSwapChain *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18028b394`

## callees

- `0x18001dfb0`
- `0x180026eac`
- `0x180050270`
- `0x1800ca040`
- `0x1800cb6cc`
- `0x18015adb4`
- `0x1802284b0`
- `0x18028ad54`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18028ae81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18028ae81`
- `ntdll!NtCreateSection` at `0x18028ae48`
- `ntdll!NtCreateSection` at `0x18028ae48`
- `ntdll!NtMapViewOfSection` at `0x18028aecd`
- `ntdll!NtMapViewOfSection` at `0x18028aecd`

## pseudocode

```c
__int64 __fastcall CLegacyRemotingSwapChain::EnsureBitmapDest(CLegacyRemotingSwapChain *this)
{
  void **v1; // rsi
  unsigned int v3; // ebx
  __int64 v4; // rcx
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rcx
  unsigned int v7; // r15d
  unsigned int v8; // r12d
  NTSTATUS v9; // ebx
  int v10; // r9d
  HANDLE CurrentProcess; // rax
  int v12; // eax
  unsigned int SectionPageProtection; // [rsp+20h] [rbp-39h]
  struct IBitmapSource *v15; // [rsp+50h] [rbp-9h] BYREF
  unsigned int v16; // [rsp+58h] [rbp-1h] BYREF
  unsigned int v17; // [rsp+5Ch] [rbp+3h]
  union _LARGE_INTEGER MaximumSize; // [rsp+60h] [rbp+7h] BYREF
  ULONG_PTR ViewSize; // [rsp+68h] [rbp+Fh] BYREF
  union _LARGE_INTEGER SectionOffset; // [rsp+70h] [rbp+17h] BYREF
  enum DXGI_FORMAT v21[4]; // [rsp+78h] [rbp+1Fh] BYREF

  v1 = (void **)((char *)this + 184);
  if ( (unsigned __int64)(*((_QWORD *)this + 23) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v4 = *((_QWORD *)this + 8) + 8LL;
    v15 = 0;
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 32LL))(v4, &v16);
    (*(void (__fastcall **)(__int64, enum DXGI_FORMAT *))(*(_QWORD *)(*((_QWORD *)this + 8) + 8LL) + 24LL))(
      *((_QWORD *)this + 8) + 8LL,
      v21);
    v5 = v16 * ((unsigned __int64)GetPixelFormatSize(v21[0]) >> 3);
    if ( v5 > 0xFFFFFFFF )
    {
      v10 = -2147024362;
      v3 = -2147024362;
      SectionPageProtection = 371;
      goto LABEL_17;
    }
    v6 = v17 * (unsigned __int64)(unsigned int)v5;
    v7 = v5;
    if ( v6 > 0xFFFFFFFF )
    {
      v3 = -2147024362;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024362, 0x176u, 0);
    }
    else
    {
      v8 = v17 * v5;
      MaximumSize.QuadPart = (unsigned int)v6;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v1,
        0);
      v9 = NtCreateSection(v1, 6u, 0, &MaximumSize, 4u, 0x8000000u, 0);
      if ( v9 < 0 )
      {
        SectionPageProtection = 385;
LABEL_7:
        v3 = v9 | 0x10000000;
        v10 = v3;
LABEL_17:
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v10, SectionPageProtection, 0);
        goto LABEL_18;
      }
      ViewSize = 0;
      SectionOffset.QuadPart = 0;
      CurrentProcess = GetCurrentProcess();
      v9 = NtMapViewOfSection(
             *v1,
             CurrentProcess,
             (PVOID *)this + 24,
             0,
             0,
             &SectionOffset,
             &ViewSize,
             ViewUnmap,
             0,
             4u);
      if ( v9 < 0 )
      {
        SectionPageProtection = 399;
        goto LABEL_7;
      }
      wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(&v15);
      v12 = HrCreateBitmapFromMemoryEx(
              v16,
              v17,
              (const struct PixelFormatInfo *)v21,
              v7,
              v8,
              *((unsigned __int8 **)this + 24),
              0,
              &v15);
      v3 = v12;
      if ( v12 < 0 )
      {
        SectionPageProtection = 407;
        goto LABEL_13;
      }
      wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset((char *)this + 72);
      v12 = (**(__int64 (__fastcall ***)(struct IBitmapSource *, GUID *, char *))v15)(
              v15,
              &GUID_14d094dc_1246_4784_b811_74305a3ecec8,
              (char *)this + 72);
      v3 = v12;
      if ( v12 < 0 )
      {
        SectionPageProtection = 409;
LABEL_13:
        v10 = v12;
        goto LABEL_17;
      }
    }
LABEL_18:
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v15);
    return v3;
  }
  return 0;
}

```

## disassembly

```asm
0x18028ad54  mov     [rsp-8+arg_8], rbx
0x18028ad59  mov     [rsp-8+arg_10], rsi
0x18028ad5e  push    rbp
0x18028ad5f  push    r12
0x18028ad61  push    r13
0x18028ad63  push    r14
0x18028ad65  push    r15
0x18028ad67  lea     rbp, [rsp-37h]
0x18028ad6c  sub     rsp, 90h
0x18028ad73  mov     rax, cs:__security_cookie
0x18028ad7a  xor     rax, rsp
0x18028ad7d  mov     [rbp+57h+var_28], rax
0x18028ad81  lea     rsi, [rcx+0B8h]
0x18028ad88  mov     r14, rcx
0x18028ad8b  mov     rax, [rsi]
0x18028ad8e  dec     rax
0x18028ad91  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18028ad95  ja      short loc_18028AD9E
0x18028ad97  xor     ebx, ebx
0x18028ad99  jmp     loc_18028AFCF
0x18028ad9e  mov     rcx, [rcx+40h]
0x18028ada2  lea     rdx, [rbp+57h+var_58]
0x18028ada6  add     rcx, 8
0x18028adaa  mov     [rbp+57h+var_60], 0
0x18028adb2  mov     rax, [rcx]
0x18028adb5  mov     rax, [rax+20h]
0x18028adb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028adbe  mov     rcx, [r14+40h]
0x18028adc2  lea     rdx, [rbp+57h+var_38]
0x18028adc6  add     rcx, 8
0x18028adca  mov     rax, [rcx]
0x18028adcd  mov     rax, [rax+18h]
0x18028add1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028add6  mov     ecx, [rbp+57h+var_38]; enum DXGI_FORMAT
0x18028add9  call    ?GetPixelFormatSize@@YAEW4DXGI_FORMAT@@@Z; GetPixelFormatSize(DXGI_FORMAT)
0x18028adde  movzx   edx, al
0x18028ade1  mov     r8d, 0FFFFFFFFh
0x18028ade7  mov     eax, [rbp+57h+var_58]
0x18028adea  shr     rdx, 3
0x18028adee  imul    rdx, rax
0x18028adf2  cmp     rdx, r8
0x18028adf5  ja      loc_18028AF9E
0x18028adfb  mov     eax, [rbp+57h+var_54]
0x18028adfe  mov     ecx, edx
0x18028ae00  imul    rcx, rax
0x18028ae04  mov     r15d, edx
0x18028ae07  xor     edx, edx
0x18028ae09  cmp     rcx, r8
0x18028ae0c  ja      loc_18028AF82
0x18028ae12  mov     r12d, ecx
0x18028ae15  mov     rcx, rsi
0x18028ae18  mov     qword ptr [rbp+57h+MaximumSize], r12
0x18028ae1c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18028ae21  xor     r8d, r8d; ObjectAttributes
0x18028ae24  mov     [rsp+0B0h+FileHandle], 0; FileHandle
0x18028ae2d  mov     [rsp+0B0h+AllocationAttributes], 8000000h; AllocationAttributes
0x18028ae35  lea     r9, [rbp+57h+MaximumSize]; MaximumSize
0x18028ae39  mov     rcx, rsi; SectionHandle
0x18028ae3c  mov     [rsp+0B0h+SectionPageProtection], 4; SectionPageProtection
0x18028ae44  lea     edx, [r8+6]; DesiredAccess
0x18028ae48  call    cs:__imp_NtCreateSection
0x18028ae4e  mov     ebx, eax
0x18028ae50  test    eax, eax
0x18028ae52  jns     short loc_18028AE71
0x18028ae54  mov     qword ptr [rsp+0B0h+AllocationAttributes], 0
0x18028ae5d  mov     [rsp+0B0h+SectionPageProtection], 181h
0x18028ae65  bts     ebx, 1Ch
0x18028ae69  mov     r9d, ebx
0x18028ae6c  jmp     loc_18028AFB8
0x18028ae71  mov     [rbp+57h+ViewSize], 0
0x18028ae79  mov     qword ptr [rbp+57h+SectionOffset], 0
0x18028ae81  call    cs:__imp_GetCurrentProcess
0x18028ae87  mov     [rsp+0B0h+AccessProtection], 4; AccessProtection
0x18028ae8f  lea     rcx, [rbp+57h+ViewSize]
0x18028ae93  mov     [rsp+0B0h+AllocationType], 0; AllocationType
0x18028ae9b  lea     r13, [r14+0C0h]
0x18028aea2  mov     [rsp+0B0h+InheritDisposition], 2; InheritDisposition
0x18028aeaa  xor     r9d, r9d; ZeroBits
0x18028aead  mov     [rsp+0B0h+FileHandle], rcx; ViewSize
0x18028aeb2  mov     r8, r13; BaseAddress
0x18028aeb5  lea     rcx, [rbp+57h+SectionOffset]
0x18028aeb9  mov     rdx, rax; ProcessHandle
0x18028aebc  mov     qword ptr [rsp+0B0h+AllocationAttributes], rcx; SectionOffset
0x18028aec1  mov     rcx, [rsi]; SectionHandle
0x18028aec4  mov     qword ptr [rsp+0B0h+SectionPageProtection], 0; CommitSize
0x18028aecd  call    cs:__imp_NtMapViewOfSection
0x18028aed3  mov     ebx, eax
0x18028aed5  test    eax, eax
0x18028aed7  jns     short loc_18028AEEF
0x18028aed9  mov     qword ptr [rsp+0B0h+AllocationAttributes], 0
0x18028aee2  mov     [rsp+0B0h+SectionPageProtection], 18Fh
0x18028aeea  jmp     loc_18028AE65
0x18028aeef  lea     rcx, [rbp+57h+var_60]
0x18028aef3  call    ?reset@?$com_ptr_t@UIDXGISwapChain1@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(void)
0x18028aef8  mov     edx, [rbp+57h+var_54]; unsigned int
0x18028aefb  lea     rax, [rbp+57h+var_60]
0x18028aeff  mov     ecx, [rbp+57h+var_58]; unsigned int
0x18028af02  lea     r8, [rbp+57h+var_38]; struct PixelFormatInfo *
0x18028af06  mov     qword ptr [rsp+0B0h+InheritDisposition], rax; struct IBitmapSource **
0x18028af0b  mov     r9d, r15d; unsigned int
0x18028af0e  mov     rax, [r13+0]
0x18028af12  mov     [rsp+0B0h+FileHandle], 0; struct IUnknown *
0x18028af1b  mov     qword ptr [rsp+0B0h+AllocationAttributes], rax; unsigned __int8 *
0x18028af20  mov     [rsp+0B0h+SectionPageProtection], r12d; unsigned int
0x18028af25  call    ?HrCreateBitmapFromMemoryEx@@YAJIIAEBUPixelFormatInfo@@IIPEAEPEAUIUnknown@@PEAPEAVIBitmapSource@@@Z; HrCreateBitmapFromMemoryEx(uint,uint,PixelFormatInfo const &,uint,uint,uchar *,IUnknown *,IBitmapSource * *)
0x18028af2a  mov     ebx, eax
0x18028af2c  test    eax, eax
0x18028af2e  js      short loc_18028AF6F
0x18028af30  lea     rcx, [r14+48h]
0x18028af34  call    ?reset@?$com_ptr_t@UIDXGISwapChain1@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(void)
0x18028af39  mov     rcx, [rbp+57h+var_60]
0x18028af3d  lea     r8, [r14+48h]
0x18028af41  lea     rdx, _GUID_14d094dc_1246_4784_b811_74305a3ecec8
0x18028af48  mov     rax, [rcx]
0x18028af4b  mov     rax, [rax]
0x18028af4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028af53  mov     ebx, eax
0x18028af55  test    eax, eax
0x18028af57  jns     short loc_18028AFC6
0x18028af59  mov     qword ptr [rsp+0B0h+AllocationAttributes], 0
0x18028af62  mov     [rsp+0B0h+SectionPageProtection], 199h
0x18028af6a  mov     r9d, eax
0x18028af6d  jmp     short loc_18028AFB8
0x18028af6f  mov     qword ptr [rsp+0B0h+AllocationAttributes], 0
0x18028af78  mov     [rsp+0B0h+SectionPageProtection], 197h
0x18028af80  jmp     short loc_18028AF6A
0x18028af82  mov     r9d, 80070216h
0x18028af88  mov     qword ptr [rsp+0B0h+AllocationAttributes], 0
0x18028af91  mov     ebx, r9d
0x18028af94  mov     [rsp+0B0h+SectionPageProtection], 176h
0x18028af9c  jmp     short loc_18028AFBA
0x18028af9e  mov     r9d, 80070216h; int
0x18028afa4  mov     qword ptr [rsp+0B0h+AllocationAttributes], 0; void *
0x18028afad  mov     ebx, r9d
0x18028afb0  mov     [rsp+0B0h+SectionPageProtection], 173h; unsigned int
0x18028afb8  xor     edx, edx; int *
0x18028afba  xor     r8d, r8d; unsigned int
0x18028afbd  lea     ecx, [r8+14h]; unsigned int
0x18028afc1  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18028afc6  lea     rcx, [rbp+57h+var_60]
0x18028afca  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x18028afcf  mov     eax, ebx
0x18028afd1  mov     rcx, [rbp+57h+var_28]
0x18028afd5  xor     rcx, rsp; StackCookie
0x18028afd8  call    __security_check_cookie
0x18028afdd  lea     r11, [rsp+0B0h+var_20]
0x18028afe5  mov     rbx, [r11+38h]
0x18028afe9  mov     rsi, [r11+40h]
0x18028afed  mov     rsp, r11
0x18028aff0  pop     r15
0x18028aff2  pop     r14
0x18028aff4  pop     r13
0x18028aff6  pop     r12
0x18028aff8  pop     rbp
0x18028aff9  retn
```
