# Imapi2Utility::SQMLogImapiSession(IDiscRecorder2 *,ulong,_IMAPI_MEDIA_PHYSICAL_TYPE,long,ulong,ulong,ulong,long)

- ea: `0x180046bf4`
- end: `0x180047037`
- name: `?SQMLogImapiSession@Imapi2Utility@@YAJPEAUIDiscRecorder2@@KW4_IMAPI_MEDIA_PHYSICAL_TYPE@@JKKKJ@Z`
- size: `1091`
- prototype: `int(Imapi2Utility *__hidden this, struct IDiscRecorder2 *, unsigned int, enum _IMAPI_MEDIA_PHYSICAL_TYPE, int, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `4`
- callee_count: `13`
- tags: ``

## callers

- `0x18001dd30`
- `0x180025dd0`
- `0x1800306c0`
- `0x180039320`

## callees

- `0x180009b80`
- `0x18000a5f0`
- `0x18000a86c`
- `0x180046bf4`
- `0x1800489d0`
- `0x180048a34`
- `0x180048a94`
- `0x180048b14`
- `0x180048b8c`
- `0x18004962c`
- `0x18004984a`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `ole32!CoCreateGuid` at `0x180046ca0`
- `ole32!CoCreateGuid` at `0x180046ca0`
- `OLEAUT32!__imp_SysFreeString` at `0x180046fee`
- `OLEAUT32!__imp_SysFreeString` at `0x180046ff9`
- `OLEAUT32!__imp_SysFreeString` at `0x180047004`
- `OLEAUT32!__imp_SysFreeString` at `0x180046fee`
- `OLEAUT32!__imp_SysFreeString` at `0x180046ff9`
- `OLEAUT32!__imp_SysFreeString` at `0x180047004`
- `KERNEL32!GetVersionExW` at `0x180046d86`
- `KERNEL32!GetVersionExW` at `0x180046d86`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Imapi2Utility::SQMLogImapiSession(
        Imapi2Utility *this,
        struct IDiscRecorder2 *a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8)
{
  unsigned int v9; // r14d
  unsigned int v11; // ebx
  int CurrentPhysicalMediaType; // edi
  enum _IMAPI_MEDIA_PHYSICAL_TYPE *v13; // r8
  struct IDiscRecorder2Ex *v14; // rcx
  unsigned int v15; // esi
  const struct _EVENT_DESCRIPTOR *v16; // rcx
  unsigned int v17; // r8d
  const struct _EVENT_DESCRIPTOR *v18; // rcx
  const struct _EVENT_DESCRIPTOR *v19; // rcx
  const struct _EVENT_DESCRIPTOR *v20; // rcx
  const struct _EVENT_DESCRIPTOR *v21; // rcx
  const struct _EVENT_DESCRIPTOR *v22; // rcx
  const struct _EVENT_DESCRIPTOR *v23; // rcx
  const struct _EVENT_DESCRIPTOR *v24; // rcx
  const struct _EVENT_DESCRIPTOR *v25; // rcx
  GUID *p_pguid; // rcx
  struct _GUID *started; // rbx
  const struct _EVENT_DESCRIPTOR *v28; // rcx
  const struct _EVENT_DESCRIPTOR *v29; // rcx
  const struct _EVENT_DESCRIPTOR *v30; // rcx
  const struct _EVENT_DESCRIPTOR *v31; // rcx
  const struct _EVENT_DESCRIPTOR *v32; // rcx
  const struct _EVENT_DESCRIPTOR *v33; // rcx
  const struct _EVENT_DESCRIPTOR *v34; // rcx
  const struct _EVENT_DESCRIPTOR *v35; // rcx
  const struct _EVENT_DESCRIPTOR *v36; // rcx
  struct IDiscRecorder2Ex v38; // [rsp+20h] [rbp-E0h] BYREF
  struct IDiscRecorder2Ex *v39; // [rsp+28h] [rbp-D8h] BYREF
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  BSTR v41; // [rsp+38h] [rbp-C8h] BYREF
  BSTR v42; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v43[2]; // [rsp+48h] [rbp-B8h] BYREF
  GUID pguid; // [rsp+58h] [rbp-A8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF

  v9 = (unsigned int)a2;
  LODWORD(v38.lpVtbl) = a3;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  pguid = 0;
  bstrString = 0;
  v41 = 0;
  v42 = 0;
  v43[0] = 0;
  v43[1] = 0;
  v39 = 0;
  if ( !this )
  {
    v11 = -1062600701;
    goto LABEL_29;
  }
  if ( !(unsigned int)WinSqmIsOptedIn() )
  {
    v11 = 1;
    goto LABEL_29;
  }
  CurrentPhysicalMediaType = CoCreateGuid(&pguid);
  if ( CurrentPhysicalMediaType >= 0 )
  {
    CurrentPhysicalMediaType = (*(__int64 (__fastcall **)(Imapi2Utility *, BSTR *))(*(_QWORD *)this + 120LL))(
                                 this,
                                 &bstrString);
    if ( CurrentPhysicalMediaType >= 0 )
    {
      CurrentPhysicalMediaType = (*(__int64 (__fastcall **)(Imapi2Utility *, BSTR *))(*(_QWORD *)this + 128LL))(
                                   this,
                                   &v41);
      if ( CurrentPhysicalMediaType >= 0 )
      {
        CurrentPhysicalMediaType = (*(__int64 (__fastcall **)(Imapi2Utility *, BSTR *))(*(_QWORD *)this + 136LL))(
                                     this,
                                     &v42);
        if ( CurrentPhysicalMediaType >= 0 )
          CurrentPhysicalMediaType = (**(__int64 (__fastcall ***)(Imapi2Utility *, GUID *, struct IDiscRecorder2Ex **))this)(
                                       this,
                                       &GUID_27354132_7f64_5b0f_8f00_5d77afbe261e,
                                       &v39);
      }
    }
  }
  v14 = v39;
  if ( v39 )
  {
    if ( !LODWORD(v38.lpVtbl) )
    {
      CurrentPhysicalMediaType = Imapi2Utility::GetCurrentPhysicalMediaType(v39, &v38, v13);
      v14 = v39;
    }
    if ( CurrentPhysicalMediaType < 0 )
      goto LABEL_26;
    CurrentPhysicalMediaType = CMsftDiscInformation::Init((CMsftDiscInformation *)v43, v14);
    if ( CurrentPhysicalMediaType < 0 )
      goto LABEL_25;
    v15 = CMsftDiscInformation::get_NumberOfSessions((CMsftDiscInformation *)v43) - 1;
LABEL_17:
    VersionInformation.dwOSVersionInfoSize = 276;
    if ( GetVersionExW(&VersionInformation) )
    {
      if ( VersionInformation.dwMajorVersion > 6
        || VersionInformation.dwMajorVersion >= 6 && VersionInformation.dwMinorVersion )
      {
        started = WinSqmStartSession(&pguid, 0x110C00u, v17);
        _WinSqmDWORDEvent(v28, started, 0x14E1u, 0x10000u);
        WinSqmSetString(started, 0x8CEu, bstrString);
        WinSqmSetString(started, 0x8CFu, v41);
        WinSqmSetString(started, 0x8D0u, v42);
        _WinSqmDWORDEvent(v29, started, 0x8D1u, (unsigned int)v38.lpVtbl);
        _WinSqmDWORDEvent(v30, started, 0x8D2u, v15);
        _WinSqmDWORDEvent(v31, started, 0x8D3u, v9);
        _WinSqmDWORDEvent(v32, started, 0x8D4u, a4);
        _WinSqmDWORDEvent(v33, started, 0x14E6u, a5 / 0x3E8);
        _WinSqmDWORDEvent(v34, started, 0x14E0u, a6);
        _WinSqmDWORDEvent(v35, started, 0x8D5u, a7);
        _WinSqmDWORDEvent(v36, started, 0x8D6u, a8);
        p_pguid = started;
      }
      else
      {
        _WinSqmDWORDEvent(v16, &pguid, 0x14E1u, 0x10000u);
        WinSqmSetString(&pguid, 0x8CEu, bstrString);
        WinSqmSetString(&pguid, 0x8CFu, v41);
        WinSqmSetString(&pguid, 0x8D0u, v42);
        _WinSqmDWORDEvent(v18, &pguid, 0x8D1u, (unsigned int)v38.lpVtbl);
        _WinSqmDWORDEvent(v19, &pguid, 0x8D2u, v15);
        _WinSqmDWORDEvent(v20, &pguid, 0x8D3u, v9);
        _WinSqmDWORDEvent(v21, &pguid, 0x8D4u, a4);
        _WinSqmDWORDEvent(v22, &pguid, 0x14E6u, a5 / 0x3E8);
        _WinSqmDWORDEvent(v23, &pguid, 0x14E0u, a6);
        _WinSqmDWORDEvent(v24, &pguid, 0x8D5u, a7);
        _WinSqmDWORDEvent(v25, &pguid, 0x8D6u, a8);
        p_pguid = &pguid;
      }
      WinSqmEndSession(p_pguid);
    }
    else
    {
      CurrentPhysicalMediaType = -2147418113;
    }
LABEL_25:
    v14 = v39;
    goto LABEL_26;
  }
  v15 = -2;
  if ( CurrentPhysicalMediaType >= 0 )
    goto LABEL_17;
LABEL_26:
  if ( v14 )
  {
    ((void (__fastcall *)(struct IDiscRecorder2Ex *))v14->lpVtbl->Release)(v14);
    v39 = 0;
  }
  SysFreeString(bstrString);
  SysFreeString(v41);
  SysFreeString(v42);
  v11 = CurrentPhysicalMediaType;
LABEL_29:
  CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)v43);
  return v11;
}

```

## disassembly

```asm
0x180046bf4  push    rbp
0x180046bf6  push    rbx
0x180046bf7  push    rsi
0x180046bf8  push    rdi
0x180046bf9  push    r14
0x180046bfb  push    r15
0x180046bfd  lea     rbp, [rsp-0A8h]
0x180046c05  sub     rsp, 1A8h
0x180046c0c  mov     rax, cs:__security_cookie
0x180046c13  xor     rax, rsp
0x180046c16  mov     [rbp+0D0h+var_40], rax
0x180046c1d  mov     r15d, r9d
0x180046c20  mov     r14d, edx
0x180046c23  mov     rbx, rcx
0x180046c26  mov     dword ptr [rsp+1D0h+var_1B0.lpVtbl], r8d
0x180046c2b  xor     edx, edx; Val
0x180046c2d  mov     r8d, 114h; Size
0x180046c33  lea     rcx, [rsp+1D0h+VersionInformation]; void *
0x180046c38  call    memset_0
0x180046c3d  xorps   xmm0, xmm0
0x180046c40  movups  xmmword ptr [rsp+1D0h+pguid.Data1], xmm0
0x180046c45  mov     [rsp+1D0h+bstrString], 0
0x180046c4e  mov     [rsp+1D0h+var_198], 0
0x180046c57  mov     [rsp+1D0h+var_190], 0
0x180046c60  mov     [rsp+1D0h+var_188], 0
0x180046c69  mov     [rsp+1D0h+var_180], 0
0x180046c72  mov     [rsp+1D0h+var_1A8], 0
0x180046c7b  test    rbx, rbx
0x180046c7e  jnz     short loc_180046C8A
0x180046c80  mov     ebx, 0C0AA0003h
0x180046c85  jmp     loc_18004700C
0x180046c8a  call    ?WinSqmIsOptedIn@@YAHXZ; WinSqmIsOptedIn(void)
0x180046c8f  test    eax, eax
0x180046c91  jnz     short loc_180046C9B
0x180046c93  lea     ebx, [rax+1]
0x180046c96  jmp     loc_18004700C
0x180046c9b  lea     rcx, [rsp+1D0h+pguid]; pguid
0x180046ca0  call    cs:__imp_CoCreateGuid
0x180046ca6  mov     edi, eax
0x180046ca8  test    eax, eax
0x180046caa  js      short loc_180046D1C
0x180046cac  mov     rax, [rbx]
0x180046caf  lea     rdx, [rsp+1D0h+bstrString]
0x180046cb4  mov     rcx, rbx
0x180046cb7  mov     rax, [rax+78h]
0x180046cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cc0  mov     edi, eax
0x180046cc2  test    eax, eax
0x180046cc4  js      short loc_180046D1C
0x180046cc6  mov     rax, [rbx]
0x180046cc9  lea     rdx, [rsp+1D0h+var_198]
0x180046cce  mov     rcx, rbx
0x180046cd1  mov     rax, [rax+80h]
0x180046cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cdd  mov     edi, eax
0x180046cdf  test    eax, eax
0x180046ce1  js      short loc_180046D1C
0x180046ce3  mov     rax, [rbx]
0x180046ce6  lea     rdx, [rsp+1D0h+var_190]
0x180046ceb  mov     rcx, rbx
0x180046cee  mov     rax, [rax+88h]
0x180046cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cfa  mov     edi, eax
0x180046cfc  test    eax, eax
0x180046cfe  js      short loc_180046D1C
0x180046d00  mov     rax, [rbx]
0x180046d03  lea     r8, [rsp+1D0h+var_1A8]
0x180046d08  lea     rdx, _GUID_27354132_7f64_5b0f_8f00_5d77afbe261e
0x180046d0f  mov     rcx, rbx
0x180046d12  mov     rax, [rax]
0x180046d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d1a  mov     edi, eax
0x180046d1c  mov     rcx, [rsp+1D0h+var_1A8]; this
0x180046d21  test    rcx, rcx
0x180046d24  jz      short loc_180046D6C
0x180046d26  cmp     dword ptr [rsp+1D0h+var_1B0.lpVtbl], 0
0x180046d2b  jnz     short loc_180046D3E
0x180046d2d  lea     rdx, [rsp+1D0h+var_1B0]; struct IDiscRecorder2Ex *
0x180046d32  call    ?GetCurrentPhysicalMediaType@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAW4_IMAPI_MEDIA_PHYSICAL_TYPE@@@Z; Imapi2Utility::GetCurrentPhysicalMediaType(IDiscRecorder2Ex *,_IMAPI_MEDIA_PHYSICAL_TYPE *)
0x180046d37  mov     edi, eax
0x180046d39  mov     rcx, [rsp+1D0h+var_1A8]
0x180046d3e  test    edi, edi
0x180046d40  js      loc_180046FCF
0x180046d46  mov     rdx, rcx; struct IDiscRecorder2Ex *
0x180046d49  lea     rcx, [rsp+1D0h+var_188]; this
0x180046d4e  call    ?Init@CMsftDiscInformation@@QEAAJPEAUIDiscRecorder2Ex@@@Z; CMsftDiscInformation::Init(IDiscRecorder2Ex *)
0x180046d53  mov     edi, eax
0x180046d55  test    eax, eax
0x180046d57  js      loc_180046FCA
0x180046d5d  lea     rcx, [rsp+1D0h+var_188]; this
0x180046d62  call    ?get_NumberOfSessions@CMsftDiscInformation@@QEAAKXZ; CMsftDiscInformation::get_NumberOfSessions(void)
0x180046d67  lea     esi, [rax-1]
0x180046d6a  jmp     short loc_180046D79
0x180046d6c  mov     esi, 0FFFFFFFEh
0x180046d71  test    edi, edi
0x180046d73  js      loc_180046FCF
0x180046d79  mov     [rsp+1D0h+VersionInformation.dwOSVersionInfoSize], 114h
0x180046d81  lea     rcx, [rsp+1D0h+VersionInformation]; lpVersionInformation
0x180046d86  call    cs:__imp_GetVersionExW
0x180046d8c  test    eax, eax
0x180046d8e  jnz     short loc_180046D9A
0x180046d90  mov     edi, 8000FFFFh
0x180046d95  jmp     loc_180046FCA
0x180046d9a  cmp     [rsp+1D0h+VersionInformation.dwMajorVersion], 6
0x180046d9f  ja      loc_180046EC2
0x180046da5  jb      short loc_180046DB2
0x180046da7  cmp     [rsp+1D0h+VersionInformation.dwMinorVersion], 0
0x180046dac  ja      loc_180046EC2
0x180046db2  mov     r9d, 10000h; unsigned int
0x180046db8  mov     r8d, 14E1h; unsigned int
0x180046dbe  lea     rdx, [rsp+1D0h+pguid]; struct _GUID *
0x180046dc3  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046dc8  mov     r8, [rsp+1D0h+bstrString]; unsigned __int16 *
0x180046dcd  mov     edx, 8CEh; unsigned int
0x180046dd2  lea     rcx, [rsp+1D0h+pguid]; struct _GUID *
0x180046dd7  call    ?WinSqmSetString@@YAXPEAU_GUID@@KPEBG@Z; WinSqmSetString(_GUID *,ulong,ushort const *)
0x180046ddc  mov     r8, [rsp+1D0h+var_198]; unsigned __int16 *
0x180046de1  mov     edx, 8CFh; unsigned int
0x180046de6  lea     rcx, [rsp+1D0h+pguid]; struct _GUID *
0x180046deb  call    ?WinSqmSetString@@YAXPEAU_GUID@@KPEBG@Z; WinSqmSetString(_GUID *,ulong,ushort const *)
0x180046df0  mov     r8, [rsp+1D0h+var_190]; unsigned __int16 *
0x180046df5  mov     edx, 8D0h; unsigned int
0x180046dfa  lea     rcx, [rsp+1D0h+pguid]; struct _GUID *
0x180046dff  call    ?WinSqmSetString@@YAXPEAU_GUID@@KPEBG@Z; WinSqmSetString(_GUID *,ulong,ushort const *)
0x180046e04  mov     r9d, dword ptr [rsp+1D0h+var_1B0.lpVtbl]; unsigned int
0x180046e09  mov     r8d, 8D1h; unsigned int
0x180046e0f  lea     rdx, [rsp+1D0h+pguid]; struct _GUID *
0x180046e14  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046e19  mov     r9d, esi; unsigned int
0x180046e1c  mov     r8d, 8D2h; unsigned int
0x180046e22  lea     rdx, [rsp+1D0h+pguid]; struct _GUID *
0x180046e27  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046e2c  mov     r9d, r14d; unsigned int
0x180046e2f  mov     r8d, 8D3h; unsigned int
0x180046e35  lea     rdx, [rsp+1D0h+pguid]; struct _GUID *
0x180046e3a  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046e3f  mov     r9d, r15d; unsigned int
0x180046e42  mov     r8d, 8D4h; unsigned int
0x180046e48  lea     rdx, [rsp+1D0h+pguid]; struct _GUID *
0x180046e4d  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046e52  mov     eax, 10624DD3h
0x180046e57  mul     [rbp+0D0h+arg_20]
0x180046e5d  shr     edx, 6
0x180046e60  mov     r9d, edx; unsigned int
0x180046e63  mov     r8d, 14E6h; unsigned int
0x180046e69  lea     rdx, [rsp+1D0h+pguid]; struct _GUID *
0x180046e6e  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046e73  mov     r9d, [rbp+0D0h+arg_28]; unsigned int
0x180046e7a  mov     r8d, 14E0h; unsigned int
0x180046e80  lea     rdx, [rsp+1D0h+pguid]; struct _GUID *
0x180046e85  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046e8a  mov     r9d, [rbp+0D0h+arg_30]; unsigned int
0x180046e91  mov     r8d, 8D5h; unsigned int
0x180046e97  lea     rdx, [rsp+1D0h+pguid]; struct _GUID *
0x180046e9c  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046ea1  mov     r9d, [rbp+0D0h+arg_38]; unsigned int
0x180046ea8  mov     r8d, 8D6h; unsigned int
0x180046eae  lea     rdx, [rsp+1D0h+pguid]; struct _GUID *
0x180046eb3  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046eb8  lea     rcx, [rsp+1D0h+pguid]
0x180046ebd  jmp     loc_180046FC5
0x180046ec2  mov     edx, 110C00h; unsigned int
0x180046ec7  lea     rcx, [rsp+1D0h+pguid]; struct _GUID *
0x180046ecc  call    ?WinSqmStartSession@@YAPEAU_GUID@@PEAU1@KK@Z; WinSqmStartSession(_GUID *,ulong,ulong)
0x180046ed1  mov     rbx, rax
0x180046ed4  mov     r9d, 10000h; unsigned int
0x180046eda  mov     r8d, 14E1h; unsigned int
0x180046ee0  mov     rdx, rax; struct _GUID *
0x180046ee3  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046ee8  mov     r8, [rsp+1D0h+bstrString]; unsigned __int16 *
0x180046eed  mov     edx, 8CEh; unsigned int
0x180046ef2  mov     rcx, rbx; struct _GUID *
0x180046ef5  call    ?WinSqmSetString@@YAXPEAU_GUID@@KPEBG@Z; WinSqmSetString(_GUID *,ulong,ushort const *)
0x180046efa  mov     r8, [rsp+1D0h+var_198]; unsigned __int16 *
0x180046eff  mov     edx, 8CFh; unsigned int
0x180046f04  mov     rcx, rbx; struct _GUID *
0x180046f07  call    ?WinSqmSetString@@YAXPEAU_GUID@@KPEBG@Z; WinSqmSetString(_GUID *,ulong,ushort const *)
0x180046f0c  mov     r8, [rsp+1D0h+var_190]; unsigned __int16 *
0x180046f11  mov     edx, 8D0h; unsigned int
0x180046f16  mov     rcx, rbx; struct _GUID *
0x180046f19  call    ?WinSqmSetString@@YAXPEAU_GUID@@KPEBG@Z; WinSqmSetString(_GUID *,ulong,ushort const *)
0x180046f1e  mov     r9d, dword ptr [rsp+1D0h+var_1B0.lpVtbl]; unsigned int
0x180046f23  mov     r8d, 8D1h; unsigned int
0x180046f29  mov     rdx, rbx; struct _GUID *
0x180046f2c  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046f31  mov     r9d, esi; unsigned int
0x180046f34  mov     r8d, 8D2h; unsigned int
0x180046f3a  mov     rdx, rbx; struct _GUID *
0x180046f3d  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046f42  mov     r9d, r14d; unsigned int
0x180046f45  mov     r8d, 8D3h; unsigned int
0x180046f4b  mov     rdx, rbx; struct _GUID *
0x180046f4e  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046f53  mov     r9d, r15d; unsigned int
0x180046f56  mov     r8d, 8D4h; unsigned int
0x180046f5c  mov     rdx, rbx; struct _GUID *
0x180046f5f  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046f64  mov     eax, 10624DD3h
0x180046f69  mul     [rbp+0D0h+arg_20]
0x180046f6f  shr     edx, 6
0x180046f72  mov     r9d, edx; unsigned int
0x180046f75  mov     r8d, 14E6h; unsigned int
0x180046f7b  mov     rdx, rbx; struct _GUID *
0x180046f7e  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046f83  mov     r9d, [rbp+0D0h+arg_28]; unsigned int
0x180046f8a  mov     r8d, 14E0h; unsigned int
0x180046f90  mov     rdx, rbx; struct _GUID *
0x180046f93  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046f98  mov     r9d, [rbp+0D0h+arg_30]; unsigned int
0x180046f9f  mov     r8d, 8D5h; unsigned int
0x180046fa5  mov     rdx, rbx; struct _GUID *
0x180046fa8  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046fad  mov     r9d, [rbp+0D0h+arg_38]; unsigned int
0x180046fb4  mov     r8d, 8D6h; unsigned int
0x180046fba  mov     rdx, rbx; struct _GUID *
0x180046fbd  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180046fc2  mov     rcx, rbx; struct _GUID *
0x180046fc5  call    ?WinSqmEndSession@@YAXPEAU_GUID@@@Z; WinSqmEndSession(_GUID *)
0x180046fca  mov     rcx, [rsp+1D0h+var_1A8]
0x180046fcf  test    rcx, rcx
0x180046fd2  jz      short loc_180046FE9
0x180046fd4  mov     rax, [rcx]
0x180046fd7  mov     rax, [rax+10h]
0x180046fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fe0  mov     [rsp+1D0h+var_1A8], 0
0x180046fe9  mov     rcx, [rsp+1D0h+bstrString]; bstrString
0x180046fee  call    cs:__imp_SysFreeString
0x180046ff4  mov     rcx, [rsp+1D0h+var_198]; bstrString
0x180046ff9  call    cs:__imp_SysFreeString
0x180046fff  mov     rcx, [rsp+1D0h+var_190]; bstrString
0x180047004  call    cs:__imp_SysFreeString
0x18004700a  mov     ebx, edi
0x18004700c  lea     rcx, [rsp+1D0h+var_188]; this
0x180047011  call    ??1CMsftDiscInformation@@QEAA@XZ; CMsftDiscInformation::~CMsftDiscInformation(void)
0x180047016  mov     eax, ebx
0x180047018  mov     rcx, [rbp+0D0h+var_40]
0x18004701f  xor     rcx, rsp; StackCookie
0x180047022  call    __security_check_cookie
0x180047027  add     rsp, 1A8h
0x18004702e  pop     r15
0x180047030  pop     r14
0x180047032  pop     rdi
0x180047033  pop     rsi
0x180047034  pop     rbx
0x180047035  pop     rbp
0x180047036  retn
```
