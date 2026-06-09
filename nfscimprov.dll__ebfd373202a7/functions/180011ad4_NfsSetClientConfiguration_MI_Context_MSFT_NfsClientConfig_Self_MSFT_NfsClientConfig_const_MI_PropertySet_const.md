# NfsSetClientConfiguration(_MI_Context *,_MSFT_NfsClientConfig_Self *,_MSFT_NfsClientConfig const *,_MI_PropertySet const *)

- ea: `0x180011ad4`
- end: `0x180012093`
- name: `?NfsSetClientConfiguration@@YAXPEAU_MI_Context@@PEAU_MSFT_NfsClientConfig_Self@@PEBU_MSFT_NfsClientConfig@@PEBU_MI_PropertySet@@@Z`
- size: `1471`
- prototype: `void(struct _MI_Context *, struct _MSFT_NfsClientConfig_Self *, const struct _MSFT_NfsClientConfig *, const struct _MI_PropertySet *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008ed0`

## callees

- `0x1800098c4`
- `0x18000bff0`
- `0x18000e1b0`
- `0x18000f544`
- `0x18000f574`
- `0x180011874`
- `0x180011ad4`
- `0x180013a40`
- `0x18002143c`
- `0x180021598`
- `0x180022318`
- `0x18002c874`
- `0x1800321a8`
- `0x18003305c`
- `0x1800331a4`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180011ba9`
- `msvcrt!_wcsicmp` at `0x180011bff`
- `msvcrt!_wcsicmp` at `0x180011ba9`
- `msvcrt!_wcsicmp` at `0x180011bff`
- `ADVAPI32!RegSetKeyValueW` at `0x180011de5`
- `ADVAPI32!RegSetKeyValueW` at `0x180011de5`

## string_xrefs

- `0x180011e76`: `MountType`
- `0x180011fc7`: `Access`
- `0x180011e32`: `SOFTWARE\Microsoft\ClientForNFS\CurrentVersion\Users\Default\Mount`
- `0x180011e7d`: `SOFTWARE\Microsoft\ClientForNFS\CurrentVersion\Users\Default\Mount`
- `0x180011ed5`: `SOFTWARE\Microsoft\ClientForNFS\CurrentVersion\Users\Default\Mount`
- `0x180011dd0`: `Protocols`
- `0x180011e2b`: `ReadBuffer`
- `0x180011ece`: `WriteBuffer`
- `0x180011f7f`: `NFSReadDir`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall NfsSetClientConfiguration(
        struct _MI_Context *a1,
        struct _MSFT_NfsClientConfig_Self *a2,
        const struct _MSFT_NfsClientConfig *a3,
        const struct _MI_PropertySet *a4)
{
  enum _MI_Result v8; // edi
  __int16 v9; // r14
  const wchar_t *v10; // rbx
  unsigned int v11; // r8d
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // r11d
  char v18; // r10
  unsigned int v19; // edx
  unsigned int v20; // ecx
  int v21; // eax
  LSTATUS v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  int v30; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v31; // [rsp+44h] [rbp-65h] BYREF
  int v32; // [rsp+48h] [rbp-61h] BYREF
  struct _MI_ConstStringA v33; // [rsp+50h] [rbp-59h] BYREF
  _QWORD v34[2]; // [rsp+60h] [rbp-49h] BYREF
  __int16 v35; // [rsp+70h] [rbp-39h]
  struct _MI_Context *v36; // [rsp+78h] [rbp-31h]
  int v37; // [rsp+80h] [rbp-29h]
  __int64 v38; // [rsp+84h] [rbp-25h]
  struct _MSFT_NfsClientConfig_Self *v39; // [rsp+90h] [rbp-19h] BYREF
  int v40; // [rsp+98h] [rbp-11h]
  _BYTE v41[96]; // [rsp+A0h] [rbp-9h] BYREF
  unsigned int v42; // [rsp+110h] [rbp+67h] BYREF
  int Data; // [rsp+118h] [rbp+6Fh] BYREF
  unsigned int AuthType; // [rsp+128h] [rbp+7Fh] BYREF

  Data = 0;
  v31 = 0;
  v42 = 0;
  AuthType = 0;
  v30 = 0;
  v32 = 0;
  CNfsRegHive::CNfsRegHive((CNfsRegHive *)v41, 0);
  v34[0] = &CWMIContext::`vftable';
  v36 = a1;
  v34[1] = 0;
  v35 = 0;
  v38 = 0;
  v37 = 0;
  v39 = a2;
  v40 = 0;
  CLock::AcquireLock((CLock *)&v39);
  if ( a4 )
  {
    v8 = ClientPropertyToModify(a4, &v31);
    if ( v8 )
      goto LABEL_74;
    v9 = v31;
    if ( !v31 )
      goto LABEL_74;
  }
  else
  {
    v9 = 2046;
  }
  if ( *((_BYTE *)a3 + 136) && (v9 & 0x10) != 0 )
  {
    v10 = (const wchar_t *)*((_QWORD *)a3 + 16);
    if ( _wcsicmp(L"soft", v10) )
    {
      if ( _wcsicmp(L"hard", v10) )
      {
        v11 = -1073737644;
LABEL_44:
        v8 = MI_RESULT_INVALID_PARAMETER;
        CWMIContext::WriteMIError((CWMIContext *)v34, MI_RESULT_INVALID_PARAMETER, v11);
        goto LABEL_74;
      }
      v30 = 2;
    }
    else
    {
      v30 = 1;
    }
  }
  if ( *((_BYTE *)a3 + 148) )
  {
    if ( (v9 & 0x20) != 0 )
    {
      v42 = *((_DWORD *)a3 + 36);
      if ( v42 > 0xA )
      {
        v8 = MI_RESULT_INVALID_PARAMETER;
        CWMIContext::WriteMIError((CWMIContext *)v34, MI_RESULT_INVALID_PARAMETER, 0xC0001055);
        goto LABEL_74;
      }
    }
  }
  if ( *((_BYTE *)a3 + 164) )
  {
    if ( (v9 & 0x80u) != 0 )
    {
      v42 = *((_DWORD *)a3 + 40);
      if ( v42 - 1 > 0x3B )
      {
        v8 = MI_RESULT_INVALID_PARAMETER;
        CWMIContext::WriteMIError((CWMIContext *)v34, MI_RESULT_INVALID_PARAMETER, 0xC0001056, 1, 60);
        goto LABEL_74;
      }
    }
  }
  if ( *((_BYTE *)a3 + 156)
    && (v9 & 0x40) != 0
    && ((v12 = *((_DWORD *)a3 + 38), v42 = v12, v12 - 1 > 0x3FF) || ((v12 - 1) & v12) != 0)
    || *((_BYTE *)a3 + 200)
    && (v9 & 0x400) != 0
    && ((v13 = *((_DWORD *)a3 + 49), v42 = v13, v13 - 1 > 0x3FF) || ((v13 - 1) & v13) != 0) )
  {
    v11 = -1073737641;
    goto LABEL_44;
  }
  if ( *((_BYTE *)a3 + 120) && (v9 & 8) != 0 )
  {
    v14 = *((_DWORD *)a3 + 29);
    v15 = 0;
    v16 = 0;
    v17 = 1;
    v18 = 1;
    while ( v14 )
    {
      v19 = v14 / 0xA;
      v20 = v14 % 0xA;
      if ( v20 > 7 || v16 > 2 )
        v18 = 0;
      v15 += v17 * v20;
      v14 = v19;
      v17 *= 8;
      ++v16;
      if ( !v18 )
      {
        v11 = -1073737652;
        goto LABEL_44;
      }
    }
    v32 = v15;
  }
  if ( *((_BYTE *)a3 + 104) )
  {
    if ( (v9 & 2) != 0 )
    {
      v33 = *(struct _MI_ConstStringA *)((char *)a3 + 88);
      if ( !ValidateAuth(&v33) )
      {
        v11 = -1073737640;
        goto LABEL_44;
      }
    }
  }
  if ( !*((_BYTE *)a3 + 184) || (v9 & 0x100) == 0 )
    goto LABEL_80;
  v33 = *(struct _MI_ConstStringA *)((char *)a3 + 168);
  if ( !ValidateProtocols(&v33, &AuthType) )
  {
    v11 = -1073737639;
    goto LABEL_44;
  }
  v21 = Data;
  if ( (AuthType & 1) != 0 )
  {
    v21 = Data | 0x455455;
    Data |= 0x455455u;
  }
  if ( (AuthType & 2) != 0 )
    Data = v21 | 0x8AA8AA;
  v22 = RegSetKeyValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
          L"Protocols",
          4u,
          &Data,
          4u);
  v8 = MapWinErrorToMIResult(v22);
  if ( v8 == MI_RESULT_OK )
  {
LABEL_80:
    if ( !*((_BYTE *)a3 + 156)
      || (v9 & 0x40) == 0
      || (v42 = *((_DWORD *)a3 + 38) << 10,
          v23 = CNfsRegHive::SetValue(
                  (CNfsRegHive *)v41,
                  L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Mount",
                  L"ReadBuffer",
                  0,
                  4u,
                  &v42,
                  4u),
          (v8 = MapWinErrorToMIResult(v23)) == MI_RESULT_OK) )
    {
      if ( !*((_BYTE *)a3 + 136)
        || (v9 & 0x10) == 0
        || (v24 = CNfsRegHive::SetValue(
                    (CNfsRegHive *)v41,
                    L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Mount",
                    L"MountType",
                    0,
                    4u,
                    &v30,
                    4u),
            (v8 = MapWinErrorToMIResult(v24)) == MI_RESULT_OK) )
      {
        if ( !*((_BYTE *)a3 + 200)
          || (v9 & 0x400) == 0
          || (v42 = *((_DWORD *)a3 + 49) << 10,
              v25 = CNfsRegHive::SetValue(
                      (CNfsRegHive *)v41,
                      L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Mount",
                      L"WriteBuffer",
                      0,
                      4u,
                      &v42,
                      4u),
              (v8 = MapWinErrorToMIResult(v25)) == MI_RESULT_OK) )
        {
          if ( !*((_BYTE *)a3 + 104)
            || (v9 & 2) == 0
            || (v33 = *(struct _MI_ConstStringA *)((char *)a3 + 88),
                AuthType = GetAuthType(&v33),
                v26 = CNfsRegHive::SetValue(
                        (CNfsRegHive *)v41,
                        L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Auth",
                        L"SecFlavors",
                        0,
                        4u,
                        &AuthType,
                        4u),
                (v8 = MapWinErrorToMIResult(v26)) == MI_RESULT_OK) )
          {
            if ( !*((_BYTE *)a3 + 113)
              || (v9 & 4) == 0
              || (AuthType = *((_BYTE *)a3 + 112) != 1,
                  v27 = CNfsRegHive::SetValue(
                          (CNfsRegHive *)v41,
                          L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
                          L"NFSReadDir",
                          0,
                          4u,
                          &AuthType,
                          4u),
                  (v8 = MapWinErrorToMIResult(v27)) == MI_RESULT_OK) )
            {
              if ( !*((_BYTE *)a3 + 120)
                || (v9 & 8) == 0
                || (v28 = CNfsRegHive::SetValue(
                            (CNfsRegHive *)v41,
                            L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
                            L"Access",
                            0,
                            4u,
                            &v32,
                            4u),
                    (v8 = MapWinErrorToMIResult(v28)) == MI_RESULT_OK) )
              {
                v8 = NfsSetCimProperty(
                       (const struct _MI_Instance *)a3,
                       a4,
                       (struct _NFS_CIMPROPERTY_REGKEY_PAIR *)off_180054E50,
                       3u);
                if ( v8 == MI_RESULT_OK )
                {
                  v29 = NfsDeviceIoControl(L"\\\\.\\NfsRdr", 0xC0000000, 0x14C848u, 0, 0, 0, 0, 0);
                  v8 = MapWinErrorToMIResult(v29);
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_74:
  if ( a1 && a1->ft )
    ((void (__fastcall *)(struct _MI_Context *, _QWORD))a1->ft->PostResult)(a1, (unsigned int)v8);
  CLock::ReleaseLock((CLock *)&v39);
  CWMIContext::~CWMIContext((CWMIContext *)v34);
  CNfsRegHive::~CNfsRegHive((CNfsRegHive *)v41);
}

```

## disassembly

```asm
0x180011ad4  mov     [rsp-8+arg_10], rbx
0x180011ad9  push    rbp
0x180011ada  push    rsi
0x180011adb  push    rdi
0x180011adc  push    r12
0x180011ade  push    r13
0x180011ae0  push    r14
0x180011ae2  push    r15
0x180011ae4  lea     rbp, [rsp-27h]
0x180011ae9  sub     rsp, 0D0h
0x180011af0  mov     r12, r9
0x180011af3  mov     rsi, r8
0x180011af6  mov     rbx, rdx
0x180011af9  mov     r15, rcx
0x180011afc  xor     r13d, r13d
0x180011aff  mov     [rbp+57h+Data], r13d
0x180011b03  mov     [rbp+57h+var_BC], r13d
0x180011b07  mov     [rbp+57h+arg_0], r13d
0x180011b0b  mov     [rbp+57h+arg_18], r13d
0x180011b0f  mov     [rbp+57h+var_C0], r13d
0x180011b13  mov     [rbp+57h+var_B8], r13d
0x180011b17  xor     edx, edx; int
0x180011b19  lea     rcx, [rbp+57h+var_60]; this
0x180011b1d  call    ??0CNfsRegHive@@QEAA@H@Z; CNfsRegHive::CNfsRegHive(int)
0x180011b22  nop
0x180011b23  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x180011b2a  mov     [rbp+57h+var_A0], rax
0x180011b2e  mov     [rbp+57h+var_88], r15
0x180011b32  mov     [rbp+57h+var_98], r13
0x180011b36  mov     [rbp+57h+var_90], r13w
0x180011b3b  mov     [rbp+57h+var_7C], r13
0x180011b3f  mov     [rbp+57h+var_80], r13d
0x180011b43  mov     [rbp+57h+var_70], rbx
0x180011b47  mov     [rbp+57h+var_68], r13d
0x180011b4b  lea     rcx, [rbp+57h+var_70]; this
0x180011b4f  call    ?AcquireLock@CLock@@QEAAXXZ; CLock::AcquireLock(void)
0x180011b54  test    r12, r12
0x180011b57  jz      short loc_180011B7E
0x180011b59  lea     rdx, [rbp+57h+var_BC]; unsigned int *
0x180011b5d  mov     rcx, r12; struct _MI_PropertySet *
0x180011b60  call    ?ClientPropertyToModify@@YA?AW4_MI_Result@@PEBU_MI_PropertySet@@PEAK@Z; ClientPropertyToModify(_MI_PropertySet const *,ulong *)
0x180011b65  mov     edi, eax
0x180011b67  test    eax, eax
0x180011b69  jnz     loc_180012040
0x180011b6f  mov     r14d, [rbp+57h+var_BC]
0x180011b73  test    r14d, r14d
0x180011b76  jz      loc_180012040
0x180011b7c  jmp     short loc_180011B84
0x180011b7e  mov     r14d, 7FEh
0x180011b84  mov     edi, 1
0x180011b89  cmp     [rsi+88h], r13b
0x180011b90  jz      short loc_180011BB6
0x180011b92  test    r14b, 10h
0x180011b96  jz      short loc_180011BB6
0x180011b98  mov     rbx, [rsi+80h]
0x180011b9f  mov     rdx, rbx; String2
0x180011ba2  lea     rcx, aSoft; "soft"
0x180011ba9  call    cs:__imp__wcsicmp
0x180011baf  test    eax, eax
0x180011bb1  jnz     short loc_180011BF5
0x180011bb3  mov     [rbp+57h+var_C0], edi
0x180011bb6  cmp     [rsi+94h], r13b
0x180011bbd  jz      short loc_180011C1D
0x180011bbf  test    r14b, 20h
0x180011bc3  jz      short loc_180011C1D
0x180011bc5  mov     eax, [rsi+90h]
0x180011bcb  mov     [rbp+57h+arg_0], eax
0x180011bce  mov     r9d, 0Ah
0x180011bd4  cmp     eax, r9d
0x180011bd7  jbe     short loc_180011C1D
0x180011bd9  lea     ebx, [r9-6]
0x180011bdd  mov     edi, ebx
0x180011bdf  mov     r8d, 0C0001055h; unsigned int
0x180011be5  mov     edx, ebx; enum _MI_Result
0x180011be7  lea     rcx, [rbp+57h+var_A0]; this
0x180011beb  call    ?WriteMIError@CWMIContext@@UEAAXW4_MI_Result@@KZZ; CWMIContext::WriteMIError(_MI_Result,ulong,...)
0x180011bf0  jmp     loc_180012040
0x180011bf5  mov     rdx, rbx; String2
0x180011bf8  lea     rcx, aHard; "hard"
0x180011bff  call    cs:__imp__wcsicmp
0x180011c05  test    eax, eax
0x180011c07  jnz     short loc_180011C12
0x180011c09  mov     [rbp+57h+var_C0], 2
0x180011c10  jmp     short loc_180011BB6
0x180011c12  mov     r8d, 0C0001054h
0x180011c18  jmp     loc_180011D48
0x180011c1d  cmp     [rsi+0A4h], r13b
0x180011c24  jz      short loc_180011C64
0x180011c26  test    r14b, r14b
0x180011c29  jns     short loc_180011C64
0x180011c2b  mov     eax, [rsi+0A0h]
0x180011c31  mov     [rbp+57h+arg_0], eax
0x180011c34  dec     eax
0x180011c36  cmp     eax, 3Bh ; ';'
0x180011c39  jbe     short loc_180011C64
0x180011c3b  mov     ebx, 4
0x180011c40  mov     edi, ebx
0x180011c42  mov     dword ptr [rsp+100h+lpData], 3Ch ; '<'
0x180011c4a  lea     r9d, [rbx-3]
0x180011c4e  mov     r8d, 0C0001056h; unsigned int
0x180011c54  mov     edx, ebx; enum _MI_Result
0x180011c56  lea     rcx, [rbp+57h+var_A0]; this
0x180011c5a  call    ?WriteMIError@CWMIContext@@UEAAXW4_MI_Result@@KZZ; CWMIContext::WriteMIError(_MI_Result,ulong,...)
0x180011c5f  jmp     loc_180012040
0x180011c64  mov     edx, 3FFh
0x180011c69  cmp     [rsi+9Ch], r13b
0x180011c70  jz      short loc_180011C9A
0x180011c72  test    r14b, 40h
0x180011c76  jz      short loc_180011C9A
0x180011c78  mov     ecx, [rsi+98h]
0x180011c7e  mov     [rbp+57h+arg_0], ecx
0x180011c81  lea     eax, [rcx-1]
0x180011c84  cmp     eax, edx
0x180011c86  ja      short loc_180011C8F
0x180011c88  lea     eax, [rcx-1]
0x180011c8b  test    ecx, eax
0x180011c8d  jz      short loc_180011C9A
0x180011c8f  mov     r8d, 0C0001057h
0x180011c95  jmp     loc_180011D48
0x180011c9a  cmp     [rsi+0C8h], r13b
0x180011ca1  jz      short loc_180011CC1
0x180011ca3  bt      r14d, 0Ah
0x180011ca8  jnb     short loc_180011CC1
0x180011caa  mov     ecx, [rsi+0C4h]
0x180011cb0  mov     [rbp+57h+arg_0], ecx
0x180011cb3  lea     eax, [rcx-1]
0x180011cb6  cmp     eax, edx
0x180011cb8  ja      short loc_180011C8F
0x180011cba  lea     eax, [rcx-1]
0x180011cbd  test    ecx, eax
0x180011cbf  jnz     short loc_180011C8F
0x180011cc1  cmp     [rsi+78h], r13b
0x180011cc5  jz      short loc_180011D20
0x180011cc7  test    r14b, 8
0x180011ccb  jz      short loc_180011D20
0x180011ccd  mov     ecx, [rsi+74h]
0x180011cd0  mov     r8d, r13d
0x180011cd3  mov     r9d, r13d
0x180011cd6  mov     r11d, edi
0x180011cd9  mov     r10b, dil
0x180011cdc  test    ecx, ecx
0x180011cde  jz      short loc_180011D1C
0x180011ce0  mov     eax, 0CCCCCCCDh
0x180011ce5  mul     ecx
0x180011ce7  shr     edx, 3
0x180011cea  lea     eax, [rdx+rdx*4]
0x180011ced  add     eax, eax
0x180011cef  sub     ecx, eax
0x180011cf1  cmp     ecx, 7
0x180011cf4  ja      short loc_180011CFC
0x180011cf6  cmp     r9d, 2
0x180011cfa  jle     short loc_180011CFF
0x180011cfc  mov     r10b, r13b
0x180011cff  imul    ecx, r11d
0x180011d03  add     r8d, ecx
0x180011d06  mov     ecx, edx
0x180011d08  shl     r11d, 3
0x180011d0c  add     r9d, edi
0x180011d0f  test    r10b, r10b
0x180011d12  jnz     short loc_180011CDC
0x180011d14  mov     r8d, 0C000104Ch
0x180011d1a  jmp     short loc_180011D48
0x180011d1c  mov     [rbp+57h+var_B8], r8d
0x180011d20  cmp     [rsi+68h], r13b
0x180011d24  jz      short loc_180011D5F
0x180011d26  test    r14b, 2
0x180011d2a  jz      short loc_180011D5F
0x180011d2c  movups  xmm0, xmmword ptr [rsi+58h]
0x180011d30  movdqu  xmmword ptr [rbp+57h+var_B0.data], xmm0
0x180011d35  lea     rcx, [rbp+57h+var_B0]; struct _MI_ConstStringA
0x180011d39  call    ?ValidateAuth@@YAEU_MI_ConstStringA@@@Z; ValidateAuth(_MI_ConstStringA)
0x180011d3e  test    al, al
0x180011d40  jnz     short loc_180011D5F
0x180011d42  mov     r8d, 0C0001058h; unsigned int
0x180011d48  mov     ebx, 4
0x180011d4d  mov     edi, ebx
0x180011d4f  mov     edx, ebx; enum _MI_Result
0x180011d51  lea     rcx, [rbp+57h+var_A0]; this
0x180011d55  call    ?WriteMIError@CWMIContext@@UEAAXW4_MI_Result@@KZZ; CWMIContext::WriteMIError(_MI_Result,ulong,...)
0x180011d5a  jmp     loc_180012040
0x180011d5f  mov     ebx, 4
0x180011d64  cmp     [rsi+0B8h], r13b
0x180011d6b  jz      loc_180011DFC
0x180011d71  bt      r14d, 8
0x180011d76  jnb     loc_180011DFC
0x180011d7c  movups  xmm0, xmmword ptr [rsi+0A8h]
0x180011d83  movdqu  xmmword ptr [rbp+57h+var_B0.data], xmm0
0x180011d88  lea     rdx, [rbp+57h+arg_18]; unsigned int *
0x180011d8c  lea     rcx, [rbp+57h+var_B0]; struct _MI_ConstStringA
0x180011d90  call    ?ValidateProtocols@@YAEU_MI_ConstStringA@@PEAK@Z; ValidateProtocols(_MI_ConstStringA,ulong *)
0x180011d95  test    al, al
0x180011d97  jnz     short loc_180011DA1
0x180011d99  mov     r8d, 0C0001059h
0x180011d9f  jmp     short loc_180011D4D
0x180011da1  mov     eax, [rbp+57h+Data]
0x180011da4  test    byte ptr [rbp+57h+arg_18], dil
0x180011da8  jz      short loc_180011DB2
0x180011daa  or      eax, 455455h
0x180011daf  mov     [rbp+57h+Data], eax
0x180011db2  test    byte ptr [rbp+57h+arg_18], 2
0x180011db6  jz      short loc_180011DC0
0x180011db8  or      eax, 8AA8AAh
0x180011dbd  mov     [rbp+57h+Data], eax
0x180011dc0  mov     [rsp+100h+cbData], ebx; cbData
0x180011dc4  lea     rax, [rbp+57h+Data]
0x180011dc8  mov     [rsp+100h+lpData], rax; lpData
0x180011dcd  mov     r9d, ebx; dwType
0x180011dd0  lea     r8, ValueName; "Protocols"
0x180011dd7  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x180011dde  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011de5  call    cs:__imp_RegSetKeyValueW
0x180011deb  mov     ecx, eax; unsigned int
0x180011ded  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x180011df2  mov     edi, eax
0x180011df4  test    eax, eax
0x180011df6  jnz     loc_180012040
0x180011dfc  cmp     [rsi+9Ch], r13b
0x180011e03  jz      short loc_180011E53
0x180011e05  test    r14b, 40h
0x180011e09  jz      short loc_180011E53
0x180011e0b  mov     eax, [rsi+98h]
0x180011e11  shl     eax, 0Ah
0x180011e14  mov     [rbp+57h+arg_0], eax
0x180011e17  mov     [rsp+100h+var_D0], ebx; unsigned int
0x180011e1b  lea     rax, [rbp+57h+arg_0]
0x180011e1f  mov     qword ptr [rsp+100h+cbData], rax; void *
0x180011e24  mov     dword ptr [rsp+100h+lpData], ebx; unsigned int
0x180011e28  xor     r9d, r9d; unsigned __int16 *
0x180011e2b  lea     r8, aReadbuffer; "ReadBuffer"
0x180011e32  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x180011e39  lea     rcx, [rbp+57h+var_60]; this
0x180011e3d  call    ?SetValue@CNfsRegHive@@QEAAJPEBG00KPEBXK@Z; CNfsRegHive::SetValue(ushort const *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180011e42  mov     ecx, eax; unsigned int
0x180011e44  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x180011e49  mov     edi, eax
0x180011e4b  test    eax, eax
0x180011e4d  jnz     loc_180012040
0x180011e53  cmp     [rsi+88h], r13b
0x180011e5a  jz      short loc_180011E9E
0x180011e5c  test    r14b, 10h
0x180011e60  jz      short loc_180011E9E
0x180011e62  mov     [rsp+100h+var_D0], ebx; unsigned int
0x180011e66  lea     rax, [rbp+57h+var_C0]
0x180011e6a  mov     qword ptr [rsp+100h+cbData], rax; void *
0x180011e6f  mov     dword ptr [rsp+100h+lpData], ebx; unsigned int
0x180011e73  xor     r9d, r9d; unsigned __int16 *
0x180011e76  lea     r8, aMounttype; "MountType"
0x180011e7d  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x180011e84  lea     rcx, [rbp+57h+var_60]; this
0x180011e88  call    ?SetValue@CNfsRegHive@@QEAAJPEBG00KPEBXK@Z; CNfsRegHive::SetValue(ushort const *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180011e8d  mov     ecx, eax; unsigned int
0x180011e8f  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x180011e94  mov     edi, eax
0x180011e96  test    eax, eax
0x180011e98  jnz     loc_180012040
0x180011e9e  cmp     [rsi+0C8h], r13b
0x180011ea5  jz      short loc_180011EF6
0x180011ea7  bt      r14d, 0Ah
0x180011eac  jnb     short loc_180011EF6
0x180011eae  mov     eax, [rsi+0C4h]
0x180011eb4  shl     eax, 0Ah
0x180011eb7  mov     [rbp+57h+arg_0], eax
0x180011eba  mov     [rsp+100h+var_D0], ebx; unsigned int
0x180011ebe  lea     rax, [rbp+57h+arg_0]
0x180011ec2  mov     qword ptr [rsp+100h+cbData], rax; void *
0x180011ec7  mov     dword ptr [rsp+100h+lpData], ebx; unsigned int
0x180011ecb  xor     r9d, r9d; unsigned __int16 *
0x180011ece  lea     r8, aWritebuffer; "WriteBuffer"
0x180011ed5  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x180011edc  lea     rcx, [rbp+57h+var_60]; this
0x180011ee0  call    ?SetValue@CNfsRegHive@@QEAAJPEBG00KPEBXK@Z; CNfsRegHive::SetValue(ushort const *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180011ee5  mov     ecx, eax; unsigned int
0x180011ee7  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x180011eec  mov     edi, eax
0x180011eee  test    eax, eax
0x180011ef0  jnz     loc_180012040
0x180011ef6  cmp     [rsi+68h], r13b
0x180011efa  jz      short loc_180011F53
0x180011efc  test    r14b, 2
0x180011f00  jz      short loc_180011F53
0x180011f02  movups  xmm0, xmmword ptr [rsi+58h]
0x180011f06  movdqu  xmmword ptr [rbp+57h+var_B0.data], xmm0
0x180011f0b  lea     rcx, [rbp+57h+var_B0]; struct _MI_ConstStringA
0x180011f0f  call    ?GetAuthType@@YAHU_MI_ConstStringA@@@Z; GetAuthType(_MI_ConstStringA)
0x180011f14  mov     [rbp+57h+arg_18], eax
0x180011f17  mov     [rsp+100h+var_D0], ebx; unsigned int
0x180011f1b  lea     rax, [rbp+57h+arg_18]
0x180011f1f  mov     qword ptr [rsp+100h+cbData], rax; void *
0x180011f24  mov     dword ptr [rsp+100h+lpData], ebx; unsigned int
0x180011f28  xor     r9d, r9d; unsigned __int16 *
0x180011f2b  lea     r8, aSecflavors; "SecFlavors"
0x180011f32  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x180011f39  lea     rcx, [rbp+57h+var_60]; this
0x180011f3d  call    ?SetValue@CNfsRegHive@@QEAAJPEBG00KPEBXK@Z; CNfsRegHive::SetValue(ushort const *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180011f42  mov     ecx, eax; unsigned int
0x180011f44  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x180011f49  mov     edi, eax
0x180011f4b  test    eax, eax
0x180011f4d  jnz     loc_180012040
0x180011f53  cmp     [rsi+71h], r13b
  ... truncated ...
```
