# CopyAndConfigureContact(IContactPool *,ushort const *,IContactPool *,ushort const *,ushort const *)

- ea: `0x18007436c`
- end: `0x18007483b`
- name: `?CopyAndConfigureContact@@YAJPEAUIContactPool@@PEBG011@Z`
- size: `1231`
- prototype: `__int64 __fastcall(struct IContactPool *, const unsigned __int16 *, struct IContactPool *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180049f90`
- `0x180074de8`

## callees

- `0x180003cf0`
- `0x18000c6bc`
- `0x180070f24`
- `0x18007436c`
- `0x180074844`
- `0x1800749b0`
- `0x180081dd0`
- `0x180085010`

## string_xrefs

- `0x1800743eb`: `com\complus\dtc\shared\util\copycontact.cpp`
- `0x180074455`: `com\complus\dtc\shared\util\copycontact.cpp`
- `0x1800746b9`: `com\complus\dtc\shared\util\copycontact.cpp`
- `0x1800747ba`: `com\complus\dtc\shared\util\copycontact.cpp`
- `0x1800747f1`: `com\complus\dtc\shared\util\copycontact.cpp`
- `0x1800743d0`: `CopyAndConfigureContact`
- `0x18007443a`: `CopyAndConfigureContact`
- `0x18007448e`: `CopyAndConfigureContact`
- `0x1800744c4`: `CopyAndConfigureContact`
- `0x180074502`: `CopyAndConfigureContact`
- `0x180074535`: `CopyAndConfigureContact`
- `0x18007456d`: `CopyAndConfigureContact`
- `0x1800745a4`: `CopyAndConfigureContact`
- `0x1800745db`: `CopyAndConfigureContact`
- `0x180074611`: `CopyAndConfigureContact`
- `0x18007464a`: `CopyAndConfigureContact`
- `0x180074681`: `CopyAndConfigureContact`
- `0x18007469a`: `CopyAndConfigureContact`
- `0x1800744f5`: `Dest Create failed`
- `0x180074597`: `Source GetServiceId failed`
- `0x1800745ce`: `Dest SetServiceId failed`
- `0x180074604`: `Dest WriteW failed`
- `0x1800747ae`: `WARNING: We deleted the %s contact, but were unable to copy the new contact (%s) to replace it. DTC's configuration may be corrupt. The operation that failed must be retried.`

## pseudocode

```c
__int64 __fastcall CopyAndConfigureContact(
        struct IContactPool *a1,
        wchar_t *a2,
        struct IContactPool *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  char v9; // r13
  int v10; // ebx
  const wchar_t *v11; // rax
  __int64 v12; // r9
  void *v13; // r9
  size_t Size; // [rsp+28h] [rbp-A9h]
  size_t Sizea; // [rsp+28h] [rbp-A9h]
  void *Src; // [rsp+38h] [rbp-99h]
  __int64 v18; // [rsp+50h] [rbp-81h] BYREF
  __int64 v19; // [rsp+58h] [rbp-79h] BYREF
  int v20; // [rsp+60h] [rbp-71h] BYREF
  __int64 v21; // [rsp+68h] [rbp-69h] BYREF
  __int64 v22; // [rsp+70h] [rbp-61h] BYREF
  __int128 v23; // [rsp+78h] [rbp-59h] BYREF
  __int128 v24; // [rsp+88h] [rbp-49h] BYREF
  unsigned __int16 *v25[3]; // [rsp+98h] [rbp-39h] BYREF
  unsigned __int16 v26[16]; // [rsp+B0h] [rbp-21h] BYREF

  v19 = 0;
  v18 = 0;
  v21 = 0;
  v22 = 0;
  v20 = 0;
  v9 = 0;
  v23 = 0;
  v24 = 0;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\copycontact.cpp",
    226,
    L"CopyAndConfigureContact",
    0,
    L"in");
  v10 = (*(__int64 (__fastcall **)(struct IContactPool *, _QWORD, wchar_t *, GUID *, __int64 *))(*(_QWORD *)a1 + 32LL))(
          a1,
          0,
          a2,
          &IID_IProperties,
          &v19);
  if ( v10 < 0 )
  {
    LODWORD(Size) = v10;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\copycontact.cpp",
      237,
      L"CopyAndConfigureContact",
      Size,
      L"Source GetIdentityW (%s) failed",
      a2);
    goto LABEL_27;
  }
  v10 = EraseContact(a3, a4);
  if ( v10 >= 0 )
  {
    v9 = 1;
    v10 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v19 + 24LL))(v19, &v23);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(struct IContactPool *, __int128 *, GUID *, __int64 *))(*(_QWORD *)a3 + 56LL))(
              a3,
              &v23,
              &IID_IProperties,
              &v18);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v18 + 56LL))(v18, a4);
        if ( v10 >= 0 )
        {
          if ( a5
            && (v10 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v18 + 88LL))(v18, a5),
                v10 < 0) )
          {
            v11 = L"Dest SetHostW failed";
            v12 = 276;
          }
          else
          {
            v10 = (*(__int64 (__fastcall **)(__int64, __int128 *, int *))(*(_QWORD *)v19 + 112LL))(v19, &v24, &v20);
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v18 + 120LL))(v18, &v24, 1);
              if ( v10 >= 0 )
              {
                v10 = (*(__int64 (__fastcall **)(struct IContactPool *, __int64, _QWORD))(*(_QWORD *)a3 + 64LL))(
                        a3,
                        v18,
                        0);
                if ( v10 >= 0 )
                {
                  v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(v19, &IID_ICustomProperties, &v21);
                  if ( v10 >= 0 )
                  {
                    v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v18)(
                            v18,
                            &IID_ICustomProperties,
                            &v22);
                    if ( v10 >= 0 )
                    {
                      v10 = ReplicateCustomProperties(a2);
                      if ( v10 >= 0 )
                        goto LABEL_27;
                      v11 = L"ReplicateCustomProperties failed";
                      v12 = 323;
                    }
                    else
                    {
                      v11 = L"Dest QI failed";
                      v12 = 314;
                    }
                  }
                  else
                  {
                    v11 = L"Source QI failed";
                    v12 = 306;
                  }
                }
                else
                {
                  v11 = L"Dest WriteW failed";
                  v12 = 298;
                }
              }
              else
              {
                v11 = L"Dest SetServiceId failed";
                v12 = 291;
              }
            }
            else
            {
              v11 = L"Source GetServiceId failed";
              v12 = 284;
            }
          }
        }
        else
        {
          v11 = L"Dest SetDescription failed";
          v12 = 267;
        }
      }
      else
      {
        v11 = L"Dest Create failed";
        v12 = 260;
      }
    }
    else
    {
      v11 = L"Source GetContactId failed";
      v12 = 253;
    }
  }
  else
  {
    v11 = L"EraseContact failed";
    v12 = 244;
  }
  LODWORD(Size) = v10;
  TraceStringInline(
    7,
    1,
    L"com\\complus\\dtc\\shared\\util\\copycontact.cpp",
    v12,
    L"CopyAndConfigureContact",
    Size,
    v11);
LABEL_27:
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v9 && v10 < 0 )
  {
    memset(v26, 0, 30);
    StringCchPrintfW(v26, 0xFu, L"0x%08X", (unsigned int)v10);
    v25[2] = v26;
    v25[0] = (unsigned __int16 *)a4;
    LODWORD(Size) = 0;
    v25[1] = a2;
    DtcWriteToEventLoggerExW(2u, 1u, 0x40001002u, v13, 3u, Size, (const unsigned __int16 **)v25, 0, 1);
    LODWORD(Sizea) = v10;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\copycontact.cpp",
      358,
      L"CopyAndConfigureContact",
      Sizea,
      L"WARNING: We deleted the %s contact, but were unable to copy the new contact (%s) to replace it. DTC's configuratio"
       "n may be corrupt. The operation that failed must be retried.",
      a4,
      a2);
  }
  LODWORD(Src) = v10;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\copycontact.cpp",
    361,
    L"CopyAndConfigureContact",
    0,
    L"out (0x%08x)",
    Src);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18007436c  push    rbp
0x18007436e  push    rbx
0x18007436f  push    rsi
0x180074370  push    rdi
0x180074371  push    r12
0x180074373  push    r13
0x180074375  push    r14
0x180074377  push    r15
0x180074379  lea     rbp, [rsp-17h]
0x18007437e  sub     rsp, 0E8h
0x180074385  mov     rax, cs:__security_cookie
0x18007438c  xor     rax, rsp
0x18007438f  mov     [rbp+4Fh+var_50], rax
0x180074393  mov     r14, [rbp+4Fh+arg_20]
0x180074397  lea     rax, aIn; "in"
0x18007439e  xor     edi, edi
0x1800743a0  mov     [rsp+120h+var_F0], rax
0x1800743a5  mov     r12, r9
0x1800743a8  mov     [rsp+120h+Size], rdi
0x1800743ad  mov     rsi, r8
0x1800743b0  mov     [rbp+4Fh+var_C8], rdi
0x1800743b4  mov     r15, rdx
0x1800743b7  mov     [rsp+120h+var_D0], rdi
0x1800743bc  mov     rbx, rcx
0x1800743bf  mov     [rbp+4Fh+var_B8], rdi
0x1800743c3  xorps   xmm0, xmm0
0x1800743c6  mov     [rbp+4Fh+var_B0], rdi
0x1800743ca  xorps   xmm1, xmm1
0x1800743cd  mov     [rbp+4Fh+var_C0], edi
0x1800743d0  lea     rax, aCopyandconfigu; "CopyAndConfigureContact"
0x1800743d7  mov     r9d, 0E2h
0x1800743dd  lea     edx, [rdi+6]
0x1800743e0  mov     qword ptr [rsp+120h+var_100], rax
0x1800743e5  lea     ecx, [rdi+7]
0x1800743e8  mov     r13b, dil
0x1800743eb  lea     r8, aComComplusDtcS_14; "com\\complus\\dtc\\shared\\util\\copyco"...
0x1800743f2  movups  [rbp+4Fh+var_A8], xmm0
0x1800743f6  movups  [rbp+4Fh+var_98], xmm1
0x1800743fa  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800743ff  mov     rax, [rbx]
0x180074402  lea     rcx, [rbp+4Fh+var_C8]
0x180074406  mov     qword ptr [rsp+120h+var_100], rcx
0x18007440b  lea     r9, IID_IProperties
0x180074412  mov     r8, r15
0x180074415  xor     edx, edx
0x180074417  mov     rcx, rbx
0x18007441a  mov     rax, [rax+20h]
0x18007441e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074423  mov     ebx, eax
0x180074425  test    eax, eax
0x180074427  jns     short loc_18007446B
0x180074429  mov     [rsp+120h+Src], r15
0x18007442e  lea     rax, aSourceGetident; "Source GetIdentityW (%s) failed"
0x180074435  mov     [rsp+120h+var_F0], rax
0x18007443a  lea     rsi, aCopyandconfigu; "CopyAndConfigureContact"
0x180074441  mov     edi, 1
0x180074446  mov     dword ptr [rsp+120h+Size], ebx
0x18007444a  mov     r9d, 0EDh
0x180074450  mov     qword ptr [rsp+120h+var_100], rsi
0x180074455  lea     r8, aComComplusDtcS_14; "com\\complus\\dtc\\shared\\util\\copyco"...
0x18007445c  mov     edx, edi
0x18007445e  lea     ecx, [rdi+6]
0x180074461  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180074466  jmp     loc_1800746D5
0x18007446b  mov     rdx, r12; unsigned __int16 *
0x18007446e  mov     rcx, rsi; struct IContactPool *
0x180074471  call    ?EraseContact@@YAJPEAUIContactPool@@PEBG@Z; EraseContact(IContactPool *,ushort const *)
0x180074476  mov     ebx, eax
0x180074478  mov     edi, 1
0x18007447d  test    eax, eax
0x18007447f  jns     short loc_18007449A
0x180074481  lea     rax, aErasecontactFa; "EraseContact failed"
0x180074488  mov     r9d, 0F4h
0x18007448e  lea     rsi, aCopyandconfigu; "CopyAndConfigureContact"
0x180074495  jmp     loc_1800746B4
0x18007449a  mov     rcx, [rbp+4Fh+var_C8]
0x18007449e  lea     rdx, [rbp+4Fh+var_A8]
0x1800744a2  mov     r13b, dil
0x1800744a5  mov     rax, [rcx]
0x1800744a8  mov     rax, [rax+18h]
0x1800744ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800744b1  mov     ebx, eax
0x1800744b3  test    eax, eax
0x1800744b5  jns     short loc_1800744D0
0x1800744b7  lea     rax, aSourceGetconta; "Source GetContactId failed"
0x1800744be  mov     r9d, 0FDh
0x1800744c4  lea     rsi, aCopyandconfigu; "CopyAndConfigureContact"
0x1800744cb  jmp     loc_1800746B4
0x1800744d0  mov     rax, [rsi]
0x1800744d3  lea     r9, [rsp+120h+var_D0]
0x1800744d8  lea     r8, IID_IProperties
0x1800744df  mov     rcx, rsi
0x1800744e2  lea     rdx, [rbp+4Fh+var_A8]
0x1800744e6  mov     rax, [rax+38h]
0x1800744ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800744ef  mov     ebx, eax
0x1800744f1  test    eax, eax
0x1800744f3  jns     short loc_18007450E
0x1800744f5  lea     rax, aDestCreateFail; "Dest Create failed"
0x1800744fc  mov     r9d, 104h
0x180074502  lea     rsi, aCopyandconfigu; "CopyAndConfigureContact"
0x180074509  jmp     loc_1800746B4
0x18007450e  mov     rcx, [rsp+120h+var_D0]
0x180074513  mov     rdx, r12
0x180074516  mov     rax, [rcx]
0x180074519  mov     rax, [rax+38h]
0x18007451d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074522  mov     ebx, eax
0x180074524  test    eax, eax
0x180074526  jns     short loc_180074541
0x180074528  lea     rax, aDestSetdescrip; "Dest SetDescription failed"
0x18007452f  mov     r9d, 10Bh
0x180074535  lea     rsi, aCopyandconfigu; "CopyAndConfigureContact"
0x18007453c  jmp     loc_1800746B4
0x180074541  test    r14, r14
0x180074544  jz      short loc_180074579
0x180074546  mov     rcx, [rsp+120h+var_D0]
0x18007454b  mov     rdx, r14
0x18007454e  mov     rax, [rcx]
0x180074551  mov     rax, [rax+58h]
0x180074555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007455a  mov     ebx, eax
0x18007455c  test    eax, eax
0x18007455e  jns     short loc_180074579
0x180074560  lea     rax, aDestSethostwFa; "Dest SetHostW failed"
0x180074567  mov     r9d, 114h
0x18007456d  lea     rsi, aCopyandconfigu; "CopyAndConfigureContact"
0x180074574  jmp     loc_1800746B4
0x180074579  mov     rcx, [rbp+4Fh+var_C8]
0x18007457d  lea     r8, [rbp+4Fh+var_C0]
0x180074581  lea     rdx, [rbp+4Fh+var_98]
0x180074585  mov     rax, [rcx]
0x180074588  mov     rax, [rax+70h]
0x18007458c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074591  mov     ebx, eax
0x180074593  test    eax, eax
0x180074595  jns     short loc_1800745B0
0x180074597  lea     rax, aSourceGetservi; "Source GetServiceId failed"
0x18007459e  mov     r9d, 11Ch
0x1800745a4  lea     rsi, aCopyandconfigu; "CopyAndConfigureContact"
0x1800745ab  jmp     loc_1800746B4
0x1800745b0  mov     rcx, [rsp+120h+var_D0]
0x1800745b5  lea     rdx, [rbp+4Fh+var_98]
0x1800745b9  mov     r8d, edi
0x1800745bc  mov     rax, [rcx]
0x1800745bf  mov     rax, [rax+78h]
0x1800745c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800745c8  mov     ebx, eax
0x1800745ca  test    eax, eax
0x1800745cc  jns     short loc_1800745E7
0x1800745ce  lea     rax, aDestSetservice; "Dest SetServiceId failed"
0x1800745d5  mov     r9d, 123h
0x1800745db  lea     rsi, aCopyandconfigu; "CopyAndConfigureContact"
0x1800745e2  jmp     loc_1800746B4
0x1800745e7  mov     rax, [rsi]
0x1800745ea  xor     r8d, r8d
0x1800745ed  mov     rdx, [rsp+120h+var_D0]
0x1800745f2  mov     rcx, rsi
0x1800745f5  mov     rax, [rax+40h]
0x1800745f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800745fe  mov     ebx, eax
0x180074600  test    eax, eax
0x180074602  jns     short loc_18007461D
0x180074604  lea     rax, aDestWritewFail; "Dest WriteW failed"
0x18007460b  mov     r9d, 12Ah
0x180074611  lea     rsi, aCopyandconfigu; "CopyAndConfigureContact"
0x180074618  jmp     loc_1800746B4
0x18007461d  mov     rcx, [rbp+4Fh+var_C8]
0x180074621  lea     r8, [rbp+4Fh+var_B8]
0x180074625  lea     rdx, IID_ICustomProperties
0x18007462c  mov     rax, [rcx]
0x18007462f  mov     rax, [rax]
0x180074632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074637  mov     ebx, eax
0x180074639  test    eax, eax
0x18007463b  jns     short loc_180074653
0x18007463d  lea     rax, aSourceQiFailed; "Source QI failed"
0x180074644  mov     r9d, 132h
0x18007464a  lea     rsi, aCopyandconfigu; "CopyAndConfigureContact"
0x180074651  jmp     short loc_1800746B4
0x180074653  mov     rcx, [rsp+120h+var_D0]
0x180074658  lea     r8, [rbp+4Fh+var_B0]
0x18007465c  lea     rdx, IID_ICustomProperties
0x180074663  mov     rax, [rcx]
0x180074666  mov     rax, [rax]
0x180074669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007466e  mov     ebx, eax
0x180074670  test    eax, eax
0x180074672  jns     short loc_18007468A
0x180074674  lea     rax, aDestQiFailed; "Dest QI failed"
0x18007467b  mov     r9d, 13Ah
0x180074681  lea     rsi, aCopyandconfigu; "CopyAndConfigureContact"
0x180074688  jmp     short loc_1800746B4
0x18007468a  mov     r8, [rbp+4Fh+var_B0]
0x18007468e  mov     rcx, r15; String2
0x180074691  mov     rdx, [rbp+4Fh+var_B8]
0x180074695  call    ReplicateCustomProperties
0x18007469a  lea     rsi, aCopyandconfigu; "CopyAndConfigureContact"
0x1800746a1  mov     ebx, eax
0x1800746a3  test    eax, eax
0x1800746a5  jns     short loc_1800746D5
0x1800746a7  lea     rax, aReplicatecusto_1; "ReplicateCustomProperties failed"
0x1800746ae  mov     r9d, 143h
0x1800746b4  mov     [rsp+120h+var_F0], rax
0x1800746b9  lea     r8, aComComplusDtcS_14; "com\\complus\\dtc\\shared\\util\\copyco"...
0x1800746c0  mov     dword ptr [rsp+120h+Size], ebx
0x1800746c4  mov     edx, edi
0x1800746c6  mov     ecx, 7
0x1800746cb  mov     qword ptr [rsp+120h+var_100], rsi
0x1800746d0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800746d5  mov     rcx, [rsp+120h+var_D0]
0x1800746da  test    rcx, rcx
0x1800746dd  jz      short loc_1800746EB
0x1800746df  mov     rax, [rcx]
0x1800746e2  mov     rax, [rax+10h]
0x1800746e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800746eb  mov     rcx, [rbp+4Fh+var_C8]
0x1800746ef  test    rcx, rcx
0x1800746f2  jz      short loc_180074700
0x1800746f4  mov     rax, [rcx]
0x1800746f7  mov     rax, [rax+10h]
0x1800746fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074700  mov     rcx, [rbp+4Fh+var_B8]
0x180074704  test    rcx, rcx
0x180074707  jz      short loc_180074715
0x180074709  mov     rax, [rcx]
0x18007470c  mov     rax, [rax+10h]
0x180074710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074715  mov     rcx, [rbp+4Fh+var_B0]
0x180074719  test    rcx, rcx
0x18007471c  jz      short loc_18007472A
0x18007471e  mov     rax, [rcx]
0x180074721  mov     rax, [rax+10h]
0x180074725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007472a  test    r13b, r13b
0x18007472d  jz      loc_1800747E1
0x180074733  test    ebx, ebx
0x180074735  jns     loc_1800747E1
0x18007473b  xor     eax, eax
0x18007473d  lea     r8, a0x08x; "0x%08X"
0x180074744  xorps   xmm0, xmm0
0x180074747  mov     [rbp+4Fh+var_70], ax
0x18007474b  movups  xmmword ptr [rbp+4Fh+var_6E], xmm0
0x18007474f  mov     r9d, ebx
0x180074752  lea     rcx, [rbp+4Fh+var_70]; unsigned __int16 *
0x180074756  lea     edx, [rax+0Fh]; unsigned __int64
0x180074759  movups  xmmword ptr [rbp+4Fh+var_6E+0Ch], xmm0
0x18007475d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180074762  mov     [rsp+120h+var_E0], edi; int
0x180074766  lea     rax, [rbp+4Fh+var_70]
0x18007476a  mov     [rsp+120h+Src], 0; Src
0x180074773  mov     edx, edi; unsigned __int16
0x180074775  mov     [rbp+4Fh+var_78], rax
0x180074779  mov     ecx, 2; unsigned __int16
0x18007477e  lea     rax, [rbp+4Fh+var_88]
0x180074782  mov     [rbp+4Fh+var_88], r12
0x180074786  mov     [rsp+120h+var_F0], rax; unsigned __int16 **
0x18007478b  mov     r8d, 40001002h; unsigned int
0x180074791  mov     dword ptr [rsp+120h+Size], 0; Size
0x180074799  mov     [rsp+120h+var_100], 3; unsigned __int16
0x1800747a0  mov     [rbp+4Fh+var_80], r15
0x1800747a4  call    ?DtcWriteToEventLoggerExW@@YAJGGKPEAXGKPEAPEBG0H@Z; DtcWriteToEventLoggerExW(ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *,int)
0x1800747a9  mov     qword ptr [rsp+120h+var_E0], r15
0x1800747ae  lea     rax, aWarningWeDelet; "WARNING: We deleted the %s contact, but"...
0x1800747b5  mov     [rsp+120h+Src], r12
0x1800747ba  lea     r8, aComComplusDtcS_14; "com\\complus\\dtc\\shared\\util\\copyco"...
0x1800747c1  mov     [rsp+120h+var_F0], rax
0x1800747c6  mov     r9d, 166h
0x1800747cc  mov     dword ptr [rsp+120h+Size], ebx
0x1800747d0  mov     edx, edi
0x1800747d2  mov     ecx, 7
0x1800747d7  mov     qword ptr [rsp+120h+var_100], rsi
0x1800747dc  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800747e1  mov     dword ptr [rsp+120h+Src], ebx
0x1800747e5  lea     rax, aOut0x08x; "out (0x%08x)"
0x1800747ec  mov     [rsp+120h+var_F0], rax
0x1800747f1  lea     r8, aComComplusDtcS_14; "com\\complus\\dtc\\shared\\util\\copyco"...
0x1800747f8  mov     edx, 6
0x1800747fd  mov     [rsp+120h+Size], 0
0x180074806  mov     r9d, 169h
0x18007480c  mov     qword ptr [rsp+120h+var_100], rsi
0x180074811  lea     ecx, [rdx+1]
0x180074814  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180074819  mov     eax, ebx
0x18007481b  mov     rcx, [rbp+4Fh+var_50]
0x18007481f  xor     rcx, rsp; StackCookie
0x180074822  call    __security_check_cookie
0x180074827  add     rsp, 0E8h
0x18007482e  pop     r15
0x180074830  pop     r14
0x180074832  pop     r13
0x180074834  pop     r12
0x180074836  pop     rdi
0x180074837  pop     rsi
0x180074838  pop     rbx
0x180074839  pop     rbp
0x18007483a  retn
```
