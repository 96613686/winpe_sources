# Microsoft::Windows::MDM::OmadmClient::NetworkHandler::InitializeNetwork(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,ushort const *,ushort const *,ulong)

- ea: `0x140033860`
- end: `0x140033bf9`
- name: `?InitializeNetwork@NetworkHandler@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEAVSyncmlSessionState@2345@PEBG1K@Z`
- size: `921`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::NetworkHandler *__hidden this, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000e610`
- `0x140013404`
- `0x140031b14`
- `0x140033860`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140033a52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140033bb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140033a52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140033bb7`
- `DMCmnUtils!CopyString` at `0x140033a1b`
- `DMCmnUtils!CopyString` at `0x140033a1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::NetworkHandler::InitializeNetwork(
        Microsoft::Windows::MDM::OmadmClient::NetworkHandler *this,
        struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  __int64 v9; // r8
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // eax
  int v13; // esi
  int v14; // eax
  int v15; // edi
  int *v17; // [rsp+20h] [rbp-71h]
  int v18; // [rsp+30h] [rbp-61h] BYREF
  int v19[2]; // [rsp+38h] [rbp-59h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-51h] BYREF
  int v21; // [rsp+48h] [rbp-49h] BYREF
  __int64 v22; // [rsp+50h] [rbp-41h] BYREF
  _QWORD v23[3]; // [rsp+58h] [rbp-39h] BYREF
  int v24; // [rsp+70h] [rbp-21h]
  int *v25; // [rsp+78h] [rbp-19h]
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+80h] [rbp-11h] BYREF
  int *v27; // [rsp+90h] [rbp-1h]
  __int64 v28; // [rsp+98h] [rbp+7h]
  char v29; // [rsp+A0h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  v18 = 0;
  v23[0] = 0;
  v23[1] = "InitializeNetwork";
  v23[2] = COmaDmLogger::GetLogger();
  v24 = 2;
  v25 = &v18;
  *(_QWORD *)v19 = 0;
  v22 = 0;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    v21 = 11;
    v27 = &v21;
    v28 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)OmaDmClientFunctionEntryPointEvent,
      v9,
      2u,
      &v26);
  }
  v26.Ptr = (ULONGLONG)&v22;
  *(_QWORD *)&v26.Size = this;
  v27 = v19;
  v28 = (__int64)&v18;
  v29 = 1;
  if ( *((_QWORD *)a2 + 253) && *((_QWORD *)a2 + 252) )
  {
    v10 = v18;
    goto LABEL_40;
  }
  if ( *((_QWORD *)a2 + 252) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 112LL))(*((_QWORD *)this + 3));
  if ( *((_QWORD *)a2 + 253) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 112LL))(*((_QWORD *)this + 3));
  *((_QWORD *)a2 + 252) = 0;
  *((_QWORD *)a2 + 253) = 0;
  v17 = v19;
  v11 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, const unsigned __int16 *))(**((_QWORD **)this + 3) + 24LL))(
          *((_QWORD *)this + 3),
          a3,
          a5,
          a4);
  v18 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v23[0]) = 18041;
LABEL_12:
    HIDWORD(v23[0]) = v11;
LABEL_13:
    v10 = v11;
    goto LABEL_40;
  }
  if ( !*(_QWORD *)v19 )
    goto LABEL_13;
  if ( *((_QWORD *)a2 + 262) )
  {
    LODWORD(v17) = 4;
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, char *))(**((_QWORD **)this + 3) + 48LL))(
            *((_QWORD *)this + 3),
            *(_QWORD *)v19,
            112,
            (char *)a2 + 2092);
    v18 = v11;
    if ( v11 < 0 )
    {
      LODWORD(v23[0]) = 18074;
      goto LABEL_12;
    }
  }
  hMem = 0;
  v12 = CopyString(*((const unsigned __int16 **)a2 + 226), *((_DWORD *)a2 + 454), (unsigned __int16 **)&hMem);
  v13 = v12;
  v18 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x279,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkhandler.cpp",
      (const char *)(unsigned int)v12,
      (int)v17);
LABEL_20:
    if ( hMem )
      LocalFree(hMem);
    v10 = v13;
    goto LABEL_40;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HLOCAL, _QWORD, __int64 *))(**((_QWORD **)this + 3) + 32LL))(
          *((_QWORD *)this + 3),
          *(_QWORD *)v19,
          hMem,
          *((unsigned __int16 *)a2 + 910),
          &v22);
  v18 = v13;
  if ( v13 < 0 )
  {
    LODWORD(v23[0]) = 18036;
LABEL_25:
    HIDWORD(v23[0]) = v13;
    goto LABEL_20;
  }
  if ( !v22 )
    goto LABEL_20;
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, char *, int))(**((_QWORD **)this + 3) + 48LL))(
          *((_QWORD *)this + 3),
          *(_QWORD *)v19,
          5,
          (char *)a2 + 772,
          4);
  v18 = v13;
  if ( v13 < 0 )
  {
    LODWORD(v23[0]) = 18057;
    goto LABEL_25;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, char *, int))(**((_QWORD **)this + 3) + 48LL))(
          *((_QWORD *)this + 3),
          *(_QWORD *)v19,
          6,
          (char *)a2 + 772,
          4);
  v18 = v13;
  if ( v13 < 0 )
  {
    LODWORD(v23[0]) = 18056;
    goto LABEL_25;
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 40LL))(
         *((_QWORD *)this + 4),
         *((_QWORD *)a2 + 70))
    || !(*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 24LL))(
          *((_QWORD *)this + 4),
          *((_QWORD *)a2 + 75)) )
  {
    v15 = v18;
    goto LABEL_36;
  }
  v21 = 2;
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, int *, int))(**((_QWORD **)this + 3) + 48LL))(
          *((_QWORD *)this + 3),
          *(_QWORD *)v19,
          79,
          &v21,
          4);
  v15 = v14;
  v18 = v14;
  if ( v14 >= 0 )
  {
LABEL_36:
    *((_QWORD *)a2 + 252) = *(_QWORD *)v19;
    *((_QWORD *)a2 + 253) = v22;
    *(_QWORD *)v19 = 0;
    v22 = 0;
    goto LABEL_37;
  }
  LODWORD(v23[0]) = 18058;
  HIDWORD(v23[0]) = v14;
LABEL_37:
  if ( hMem )
    LocalFree(hMem);
  v10 = v15;
LABEL_40:
  wil::details::ScopeExitFn__lambda_4234675d26153e7defe4824a76cff253___::_ScopeExitFn__lambda_4234675d26153e7defe4824a76cff253___(&v26);
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v23);
  return v10;
}

```

## disassembly

```asm
0x140033860  push    rbp
0x140033862  push    rbx
0x140033863  push    rsi
0x140033864  push    rdi
0x140033865  push    r12
0x140033867  push    r14
0x140033869  push    r15
0x14003386b  lea     rbp, [rsp-1Fh]
0x140033870  sub     rsp, 0B0h
0x140033877  mov     rax, cs:__security_cookie
0x14003387e  xor     rax, rsp
0x140033881  mov     [rbp+4Fh+var_38], rax
0x140033885  mov     r14, r9
0x140033888  mov     rsi, r8
0x14003388b  mov     rbx, rdx
0x14003388e  mov     rdi, rcx
0x140033891  xor     r15d, r15d
0x140033894  mov     [rbp+4Fh+var_B0], r15d
0x140033898  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14003389d  mov     [rbp+4Fh+var_88], r15
0x1400338a1  lea     rcx, aInitializenetw; "InitializeNetwork"
0x1400338a8  mov     [rbp+4Fh+var_80], rcx
0x1400338ac  mov     [rbp+4Fh+var_78], rax
0x1400338b0  mov     [rbp+4Fh+var_70], 2
0x1400338b7  lea     rax, [rbp+4Fh+var_B0]
0x1400338bb  mov     [rbp+4Fh+var_68], rax
0x1400338bf  mov     qword ptr [rbp+4Fh+var_A8], r15
0x1400338c3  mov     [rbp+4Fh+var_90], r15
0x1400338c7  lea     r12d, [r15+4]
0x1400338cb  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x1400338d2  jz      short loc_140033907
0x1400338d4  mov     [rbp+4Fh+var_98], 0Bh
0x1400338db  lea     rax, [rbp+4Fh+var_98]
0x1400338df  mov     [rbp+4Fh+var_50], rax
0x1400338e3  mov     [rbp+4Fh+var_48], r12
0x1400338e7  lea     rax, [rbp+4Fh+var_60]
0x1400338eb  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1400338f0  lea     r9d, [r15+2]
0x1400338f4  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x1400338fb  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x140033902  call    McGenEventWrite_EventWriteTransfer
0x140033907  lea     rax, [rbp+4Fh+var_90]
0x14003390b  mov     [rbp+4Fh+var_60], rax
0x14003390f  mov     [rbp+4Fh+var_58], rdi
0x140033913  lea     rax, [rbp+4Fh+var_A8]
0x140033917  mov     [rbp+4Fh+var_50], rax
0x14003391b  lea     rax, [rbp+4Fh+var_B0]
0x14003391f  mov     [rbp+4Fh+var_48], rax
0x140033923  mov     [rbp+4Fh+var_40], 1
0x140033927  cmp     [rbx+7E8h], r15
0x14003392e  jz      short loc_140033941
0x140033930  cmp     [rbx+7E0h], r15
0x140033937  jz      short loc_140033941
0x140033939  mov     ebx, [rbp+4Fh+var_B0]
0x14003393c  jmp     loc_140033BC5
0x140033941  mov     rdx, [rbx+7E0h]
0x140033948  test    rdx, rdx
0x14003394b  jz      short loc_14003395D
0x14003394d  mov     rcx, [rdi+18h]
0x140033951  mov     rax, [rcx]
0x140033954  mov     rax, [rax+70h]
0x140033958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003395d  mov     rdx, [rbx+7E8h]
0x140033964  test    rdx, rdx
0x140033967  jz      short loc_140033979
0x140033969  mov     rcx, [rdi+18h]
0x14003396d  mov     rax, [rcx]
0x140033970  mov     rax, [rax+70h]
0x140033974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033979  mov     [rbx+7E0h], r15
0x140033980  mov     [rbx+7E8h], r15
0x140033987  mov     rcx, [rdi+18h]
0x14003398b  mov     rax, [rcx]
0x14003398e  lea     rdx, [rbp+4Fh+var_A8]
0x140033992  mov     qword ptr [rsp+0E0h+var_C0], rdx; int
0x140033997  mov     r9, r14
0x14003399a  mov     r8d, [rbp+4Fh+arg_20]
0x14003399e  mov     rdx, rsi
0x1400339a1  mov     rax, [rax+18h]
0x1400339a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400339aa  mov     [rbp+4Fh+var_B0], eax
0x1400339ad  test    eax, eax
0x1400339af  jns     short loc_1400339C2
0x1400339b1  mov     dword ptr [rbp+4Fh+var_88], 4679h
0x1400339b8  mov     dword ptr [rbp+4Fh+var_88+4], eax
0x1400339bb  mov     ebx, eax
0x1400339bd  jmp     loc_140033BC5
0x1400339c2  mov     rdx, qword ptr [rbp+4Fh+var_A8]
0x1400339c6  test    rdx, rdx
0x1400339c9  jz      short loc_1400339BB
0x1400339cb  cmp     [rbx+830h], r15
0x1400339d2  jz      short loc_140033A06
0x1400339d4  mov     rcx, [rdi+18h]
0x1400339d8  mov     rax, [rcx]
0x1400339db  lea     r9, [rbx+82Ch]
0x1400339e2  mov     [rsp+0E0h+var_C0], r12d
0x1400339e7  mov     r8d, 70h ; 'p'
0x1400339ed  mov     rax, [rax+30h]
0x1400339f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400339f6  mov     [rbp+4Fh+var_B0], eax
0x1400339f9  test    eax, eax
0x1400339fb  jns     short loc_140033A06
0x1400339fd  mov     dword ptr [rbp+4Fh+var_88], 469Ah
0x140033a04  jmp     short loc_1400339B8
0x140033a06  mov     [rbp+4Fh+hMem], r15
0x140033a0a  lea     r8, [rbp+4Fh+hMem]
0x140033a0e  mov     edx, [rbx+718h]
0x140033a14  mov     rcx, [rbx+710h]
0x140033a1b  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x140033a22  nop     dword ptr [rax+rax+00h]
0x140033a27  mov     esi, eax
0x140033a29  mov     [rbp+4Fh+var_B0], eax
0x140033a2c  test    eax, eax
0x140033a2e  jns     short loc_140033A65
0x140033a30  mov     rcx, [rbp+57h]; this
0x140033a34  mov     r9d, eax; char *
0x140033a37  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140033a3e  mov     edx, 279h; void *
0x140033a43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140033a48  nop
0x140033a49  mov     rcx, [rbp+4Fh+hMem]; hMem
0x140033a4d  test    rcx, rcx
0x140033a50  jz      short loc_140033A5E
0x140033a52  call    cs:__imp_LocalFree
0x140033a59  nop     dword ptr [rax+rax+00h]
0x140033a5e  mov     ebx, esi
0x140033a60  jmp     loc_140033BC5
0x140033a65  mov     rcx, [rdi+18h]
0x140033a69  mov     rax, [rcx]
0x140033a6c  lea     rdx, [rbp+4Fh+var_90]
0x140033a70  mov     qword ptr [rsp+0E0h+var_C0], rdx
0x140033a75  movzx   r9d, word ptr [rbx+71Ch]
0x140033a7d  mov     r8, [rbp+4Fh+hMem]
0x140033a81  mov     rdx, qword ptr [rbp+4Fh+var_A8]
0x140033a85  mov     rax, [rax+20h]
0x140033a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033a8e  mov     esi, eax
0x140033a90  mov     [rbp+4Fh+var_B0], eax
0x140033a93  test    eax, eax
0x140033a95  jns     short loc_140033AA3
0x140033a97  mov     dword ptr [rbp+4Fh+var_88], 4674h
0x140033a9e  mov     dword ptr [rbp+4Fh+var_88+4], esi
0x140033aa1  jmp     short loc_140033A49
0x140033aa3  cmp     [rbp+4Fh+var_90], r15
0x140033aa7  jz      short loc_140033A49
0x140033aa9  mov     rcx, [rdi+18h]
0x140033aad  lea     r14, [rbx+304h]
0x140033ab4  mov     rax, [rcx]
0x140033ab7  mov     [rsp+0E0h+var_C0], r12d
0x140033abc  mov     r9, r14
0x140033abf  mov     r8d, 5
0x140033ac5  mov     rdx, qword ptr [rbp+4Fh+var_A8]
0x140033ac9  mov     rax, [rax+30h]
0x140033acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033ad2  mov     esi, eax
0x140033ad4  mov     [rbp+4Fh+var_B0], eax
0x140033ad7  test    eax, eax
0x140033ad9  jns     short loc_140033AE4
0x140033adb  mov     dword ptr [rbp+4Fh+var_88], 4689h
0x140033ae2  jmp     short loc_140033A9E
0x140033ae4  mov     rcx, [rdi+18h]
0x140033ae8  mov     rax, [rcx]
0x140033aeb  mov     [rsp+0E0h+var_C0], r12d
0x140033af0  mov     r9, r14
0x140033af3  mov     r8d, 6
0x140033af9  mov     rdx, qword ptr [rbp+4Fh+var_A8]
0x140033afd  mov     rax, [rax+30h]
0x140033b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033b06  mov     esi, eax
0x140033b08  mov     [rbp+4Fh+var_B0], eax
0x140033b0b  test    eax, eax
0x140033b0d  jns     short loc_140033B18
0x140033b0f  mov     dword ptr [rbp+4Fh+var_88], 4688h
0x140033b16  jmp     short loc_140033A9E
0x140033b18  mov     rcx, [rdi+20h]
0x140033b1c  mov     rax, [rcx]
0x140033b1f  mov     rdx, [rbx+230h]
0x140033b26  mov     rax, [rax+28h]
0x140033b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033b2f  test    eax, eax
0x140033b31  jnz     short loc_140033B8D
0x140033b33  mov     rcx, [rdi+20h]
0x140033b37  mov     rax, [rcx]
0x140033b3a  mov     rdx, [rbx+258h]
0x140033b41  mov     rax, [rax+18h]
0x140033b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033b4a  test    eax, eax
0x140033b4c  jz      short loc_140033B8D
0x140033b4e  mov     [rbp+4Fh+var_98], 2
0x140033b55  mov     rcx, [rdi+18h]
0x140033b59  mov     rax, [rcx]
0x140033b5c  mov     [rsp+0E0h+var_C0], r12d
0x140033b61  lea     r9, [rbp+4Fh+var_98]
0x140033b65  mov     r8d, 4Fh ; 'O'
0x140033b6b  mov     rdx, qword ptr [rbp+4Fh+var_A8]
0x140033b6f  mov     rax, [rax+30h]
0x140033b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033b78  mov     edi, eax
0x140033b7a  mov     [rbp+4Fh+var_B0], eax
0x140033b7d  test    eax, eax
0x140033b7f  jns     short loc_140033B90
0x140033b81  mov     dword ptr [rbp+4Fh+var_88], 468Ah
0x140033b88  mov     dword ptr [rbp+4Fh+var_88+4], eax
0x140033b8b  jmp     short loc_140033BAE
0x140033b8d  mov     edi, [rbp+4Fh+var_B0]
0x140033b90  mov     rax, qword ptr [rbp+4Fh+var_A8]
0x140033b94  mov     [rbx+7E0h], rax
0x140033b9b  mov     rax, [rbp+4Fh+var_90]
0x140033b9f  mov     [rbx+7E8h], rax
0x140033ba6  mov     qword ptr [rbp+4Fh+var_A8], r15
0x140033baa  mov     [rbp+4Fh+var_90], r15
0x140033bae  mov     rcx, [rbp+4Fh+hMem]; hMem
0x140033bb2  test    rcx, rcx
0x140033bb5  jz      short loc_140033BC3
0x140033bb7  call    cs:__imp_LocalFree
0x140033bbe  nop     dword ptr [rax+rax+00h]
0x140033bc3  mov     ebx, edi
0x140033bc5  lea     rcx, [rbp+4Fh+var_60]
0x140033bc9  call    wil__details__ScopeExitFn__lambda_4234675d26153e7defe4824a76cff253______ScopeExitFn__lambda_4234675d26153e7defe4824a76cff253___
0x140033bce  nop
0x140033bcf  lea     rcx, [rbp+4Fh+var_88]; this
0x140033bd3  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x140033bd8  mov     eax, ebx
0x140033bda  mov     rcx, [rbp+4Fh+var_38]
0x140033bde  xor     rcx, rsp; StackCookie
0x140033be1  call    __security_check_cookie
0x140033be6  add     rsp, 0B0h
0x140033bed  pop     r15
0x140033bef  pop     r14
0x140033bf1  pop     r12
0x140033bf3  pop     rdi
0x140033bf4  pop     rsi
0x140033bf5  pop     rbx
0x140033bf6  pop     rbp
0x140033bf7  retn
```
