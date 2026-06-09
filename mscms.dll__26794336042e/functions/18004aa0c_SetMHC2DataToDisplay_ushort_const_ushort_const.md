# SetMHC2DataToDisplay(ushort const *,ushort const *)

- ea: `0x18004aa0c`
- end: `0x18004ad6e`
- name: `?SetMHC2DataToDisplay@@YAJPEBG0@Z`
- size: `866`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180046450`
- `0x180047f20`

## callees

- `0x180001164`
- `0x18001582c`
- `0x18001f614`
- `0x18002e5f0`
- `0x18002f2f4`
- `0x180048b80`
- `0x18004aa0c`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigSetDeviceInfo` at `0x18004ac45`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigSetDeviceInfo` at `0x18004ac45`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18004aad7`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18004aad7`

## pseudocode

```c
__int64 __fastcall SetMHC2DataToDisplay(const unsigned __int16 *a1, WCHAR *lpFileName)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // ebx
  LUID adapterId; // rbx
  UINT32 id; // esi
  LONG DeviceInfo; // eax
  bool v11; // sf
  int v12; // eax
  int v13; // edx
  int v14; // eax
  int v15; // edx
  int v16; // eax
  int v18; // [rsp+80h] [rbp-80h] BYREF
  int v19; // [rsp+84h] [rbp-7Ch] BYREF
  int v20; // [rsp+88h] [rbp-78h] BYREF
  int v21; // [rsp+8Ch] [rbp-74h] BYREF
  int v22; // [rsp+90h] [rbp-70h] BYREF
  int v23; // [rsp+94h] [rbp-6Ch] BYREF
  int v24; // [rsp+98h] [rbp-68h] BYREF
  int v25; // [rsp+9Ch] [rbp-64h] BYREF
  int v26; // [rsp+A0h] [rbp-60h] BYREF
  int v27; // [rsp+A4h] [rbp-5Ch] BYREF
  int v28; // [rsp+A8h] [rbp-58h] BYREF
  int v29; // [rsp+ACh] [rbp-54h] BYREF
  __int128 v30; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+D0h] [rbp-30h]
  struct DISPLAYCONFIG_PATH_INFO v33; // [rsp+E0h] [rbp-20h] BYREF
  DISPLAYCONFIG_DEVICE_INFO_HEADER setPacket; // [rsp+130h] [rbp+30h] BYREF
  int v35; // [rsp+144h] [rbp+44h]
  int v36; // [rsp+148h] [rbp+48h]
  int v37; // [rsp+14Ch] [rbp+4Ch]
  int v38; // [rsp+150h] [rbp+50h]
  int v39; // [rsp+154h] [rbp+54h]
  int v40; // [rsp+158h] [rbp+58h]
  int v41; // [rsp+15Ch] [rbp+5Ch]
  int v42; // [rsp+160h] [rbp+60h]
  int v43; // [rsp+164h] [rbp+64h]
  int v44; // [rsp+168h] [rbp+68h]
  int v45; // [rsp+16Ch] [rbp+6Ch]
  _BYTE requestPacket[32]; // [rsp+180h] [rbp+80h] BYREF
  int v47; // [rsp+1A0h] [rbp+A0h]

  v32 = 0;
  v47 = 0;
  v30 = 0;
  v31 = 0;
  memset(requestPacket, 0, sizeof(requestPacket));
  memset_0(&setPacket, 0, 0x44u);
  memset_0(&v33, 0, sizeof(v33));
  if ( !a1 || !lpFileName )
    goto LABEL_20;
  v7 = InternalTranslateICMNameToPath(a1, &v33);
  if ( v7 < 0 )
    goto LABEL_21;
  adapterId = v33.targetInfo.adapterId;
  id = v33.targetInfo.id;
  *(LUID *)&requestPacket[8] = v33.targetInfo.adapterId;
  *(_QWORD *)requestPacket = 0x240000000FLL;
  *(_DWORD *)&requestPacket[16] = v33.targetInfo.id;
  DeviceInfo = DisplayConfigGetDeviceInfo((DISPLAYCONFIG_DEVICE_INFO_HEADER *)requestPacket);
  v11 = DeviceInfo < 0;
  if ( DeviceInfo > 0 )
    v11 = 1;
  if ( !v11 )
  {
    GetCalibrationDataFromProfile(lpFileName, (struct CalibrationData *)&v30);
    if ( (_QWORD)v31 )
    {
      v12 = (int)(float)(*(float *)(v31 + 12) * 1048576.0);
      v35 = v12;
      v13 = (int)(float)(*(float *)(v31 + 16) * 1048576.0);
      v36 = v13;
      if ( (unsigned int)(v13 + v12) > 0x100000 && (unsigned int)(v13 + v12 - 0x100000) < 0xA )
      {
        v35 = 0x100000 - v13;
        v36 = 0x100000 - v12;
      }
      v14 = (int)(float)(*(float *)(v31 + 24) * 1048576.0);
      v37 = v14;
      v15 = (int)(float)(*(float *)(v31 + 28) * 1048576.0);
      v38 = v15;
      if ( (unsigned int)(v15 + v14) > 0x100000 && (unsigned int)(v15 + v14 - 0x100000) < 0xA )
      {
        v37 = 0x100000 - v15;
        v38 = 0x100000 - v14;
      }
      v39 = (int)(float)(*(float *)(v31 + 36) * 1048576.0);
      v40 = (int)(float)(*(float *)(v31 + 40) * 1048576.0);
      v41 = (int)(float)(*(float *)v31 * 1048576.0);
      v42 = (int)(float)(*(float *)(v31 + 4) * 1048576.0);
      v43 = (int)(float)(*(float *)(v31 + 52) * 10000.0);
      v44 = (int)(float)(*(float *)(v31 + 56) * 10000.0);
      v45 = (int)(float)(*(float *)(v31 + 48) * 10000.0);
    }
    setPacket.type = -16;
    setPacket.size = 68;
    setPacket.adapterId = adapterId;
    setPacket.id = id;
    v16 = DisplayConfigSetDeviceInfo(&setPacket);
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    if ( v16 < 0 )
      v16 = -2147024809;
    v7 = v16;
  }
  else
  {
LABEL_20:
    v7 = -2147024809;
  }
LABEL_21:
  if ( (unsigned int)dword_18009E080 > 5 )
  {
    v18 = v45;
    v19 = v44;
    v20 = v43;
    v21 = v42;
    v22 = v41;
    v23 = v40;
    v24 = v39;
    v25 = v38;
    v26 = v37;
    v27 = v36;
    v28 = v35;
    v29 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v4,
      (__int64)&unk_180091840,
      v5,
      v6,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)&v18);
  }
  DeleteCalibrationData((struct CalibrationData *)&v30, 1, 1, 1);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004aa0c  mov     [rsp-8+arg_10], rbx
0x18004aa11  push    rbp
0x18004aa12  push    rsi
0x18004aa13  push    rdi
0x18004aa14  lea     rbp, [rsp-0B0h]
0x18004aa1c  sub     rsp, 1B0h
0x18004aa23  mov     rax, cs:__security_cookie
0x18004aa2a  xor     rax, rsp
0x18004aa2d  mov     [rbp+0C0h+var_18], rax
0x18004aa34  xor     eax, eax
0x18004aa36  xorps   xmm0, xmm0
0x18004aa39  xorps   xmm1, xmm1
0x18004aa3c  mov     [rbp+0C0h+var_F0], rax
0x18004aa40  mov     rdi, rdx
0x18004aa43  mov     [rbp+0C0h+var_20], eax
0x18004aa49  mov     rbx, rcx
0x18004aa4c  xor     edx, edx; Val
0x18004aa4e  lea     r8d, [rax+44h]; Size
0x18004aa52  lea     rcx, [rbp+0C0h+setPacket]; void *
0x18004aa56  movups  [rbp+0C0h+var_110], xmm0
0x18004aa5a  movups  [rbp+0C0h+var_100], xmm0
0x18004aa5e  movups  xmmword ptr [rbp+0C0h+requestPacket], xmm1
0x18004aa65  movups  xmmword ptr [rbp+0C0h+requestPacket+10h], xmm1
0x18004aa6c  call    memset_0
0x18004aa71  xor     edx, edx; Val
0x18004aa73  lea     rcx, [rbp+0C0h+var_E0]; void *
0x18004aa77  lea     r8d, [rdx+48h]; Size
0x18004aa7b  call    memset_0
0x18004aa80  test    rbx, rbx
0x18004aa83  jz      loc_18004AC65
0x18004aa89  test    rdi, rdi
0x18004aa8c  jz      loc_18004AC65
0x18004aa92  lea     rdx, [rbp+0C0h+var_E0]; struct DISPLAYCONFIG_PATH_INFO *
0x18004aa96  mov     rcx, rbx; unsigned __int16 *
0x18004aa99  call    ?InternalTranslateICMNameToPath@@YAJPEBGPEAUDISPLAYCONFIG_PATH_INFO@@@Z; InternalTranslateICMNameToPath(ushort const *,DISPLAYCONFIG_PATH_INFO *)
0x18004aa9e  mov     ebx, eax
0x18004aaa0  test    eax, eax
0x18004aaa2  js      loc_18004AC6A
0x18004aaa8  mov     rbx, qword ptr [rbp+0C0h+var_E0.targetInfo.adapterId.LowPart]
0x18004aaac  lea     rcx, [rbp+0C0h+requestPacket]; requestPacket
0x18004aab3  mov     esi, [rbp+0C0h+var_E0.targetInfo.id]
0x18004aab6  mov     qword ptr [rbp+0C0h+requestPacket+8], rbx
0x18004aabd  mov     dword ptr [rbp+0C0h+requestPacket], 0Fh
0x18004aac7  mov     dword ptr [rbp+0C0h+requestPacket+4], 24h ; '$'
0x18004aad1  mov     dword ptr [rbp+0C0h+requestPacket+10h], esi
0x18004aad7  call    cs:__imp_DisplayConfigGetDeviceInfo
0x18004aadd  test    eax, eax
0x18004aadf  jle     short loc_18004AAEB
0x18004aae1  movzx   eax, ax
0x18004aae4  or      eax, 80070000h
0x18004aae9  test    eax, eax
0x18004aaeb  js      loc_18004AC65
0x18004aaf1  xor     r8d, r8d
0x18004aaf4  lea     rdx, [rbp+0C0h+var_110]; struct CalibrationData *
0x18004aaf8  cmp     [rbp+0C0h+var_20], 1
0x18004aaff  mov     rcx, rdi; lpFileName
0x18004ab02  setz    r8b; int
0x18004ab06  call    ?GetCalibrationDataFromProfile@@YAJPEBGPEAUCalibrationData@@H@Z; GetCalibrationDataFromProfile(ushort const *,CalibrationData *,int)
0x18004ab0b  mov     rcx, qword ptr [rbp+0C0h+var_100]
0x18004ab0f  test    rcx, rcx
0x18004ab12  jz      loc_18004AC2C
0x18004ab18  movss   xmm0, dword ptr [rcx+0Ch]
0x18004ab1d  mov     r9d, 100000h
0x18004ab23  movss   xmm2, cs:__real@49800000
0x18004ab2b  mulss   xmm0, xmm2
0x18004ab2f  cvttss2si rax, xmm0
0x18004ab34  mov     [rbp+0C0h+var_7C], eax
0x18004ab37  movss   xmm0, dword ptr [rcx+10h]
0x18004ab3c  mulss   xmm0, xmm2
0x18004ab40  cvttss2si rdx, xmm0
0x18004ab45  mov     [rbp+0C0h+var_78], edx
0x18004ab48  lea     r8d, [rdx+rax]
0x18004ab4c  cmp     r8d, r9d
0x18004ab4f  jbe     short loc_18004AB6A
0x18004ab51  add     r8d, 0FFF00000h
0x18004ab58  cmp     r8d, 0Ah
0x18004ab5c  jnb     short loc_18004AB6A
0x18004ab5e  sub     eax, r8d
0x18004ab61  sub     edx, r8d
0x18004ab64  mov     [rbp+0C0h+var_7C], eax
0x18004ab67  mov     [rbp+0C0h+var_78], edx
0x18004ab6a  movss   xmm0, dword ptr [rcx+18h]
0x18004ab6f  mulss   xmm0, xmm2
0x18004ab73  cvttss2si rax, xmm0
0x18004ab78  mov     [rbp+0C0h+var_74], eax
0x18004ab7b  movss   xmm1, dword ptr [rcx+1Ch]
0x18004ab80  mulss   xmm1, xmm2
0x18004ab84  cvttss2si rdx, xmm1
0x18004ab89  mov     [rbp+0C0h+var_70], edx
0x18004ab8c  lea     r8d, [rdx+rax]
0x18004ab90  cmp     r8d, r9d
0x18004ab93  jbe     short loc_18004ABAE
0x18004ab95  add     r8d, 0FFF00000h
0x18004ab9c  cmp     r8d, 0Ah
0x18004aba0  jnb     short loc_18004ABAE
0x18004aba2  sub     eax, r8d
0x18004aba5  sub     edx, r8d
0x18004aba8  mov     [rbp+0C0h+var_74], eax
0x18004abab  mov     [rbp+0C0h+var_70], edx
0x18004abae  movss   xmm0, dword ptr [rcx+24h]
0x18004abb3  mulss   xmm0, xmm2
0x18004abb7  cvttss2si rax, xmm0
0x18004abbc  mov     [rbp+0C0h+var_6C], eax
0x18004abbf  movss   xmm1, dword ptr [rcx+28h]
0x18004abc4  mulss   xmm1, xmm2
0x18004abc8  cvttss2si rax, xmm1
0x18004abcd  mov     [rbp+0C0h+var_68], eax
0x18004abd0  movss   xmm0, dword ptr [rcx]
0x18004abd4  mulss   xmm0, xmm2
0x18004abd8  cvttss2si rax, xmm0
0x18004abdd  mov     [rbp+0C0h+var_64], eax
0x18004abe0  movss   xmm1, dword ptr [rcx+4]
0x18004abe5  mulss   xmm1, xmm2
0x18004abe9  movss   xmm2, cs:__real@461c4000
0x18004abf1  cvttss2si rax, xmm1
0x18004abf6  mov     [rbp+0C0h+var_60], eax
0x18004abf9  movss   xmm0, dword ptr [rcx+34h]
0x18004abfe  mulss   xmm0, xmm2
0x18004ac02  cvttss2si rax, xmm0
0x18004ac07  mov     [rbp+0C0h+var_5C], eax
0x18004ac0a  movss   xmm0, dword ptr [rcx+38h]
0x18004ac0f  mulss   xmm0, xmm2
0x18004ac13  cvttss2si rax, xmm0
0x18004ac18  mov     [rbp+0C0h+var_58], eax
0x18004ac1b  movss   xmm1, dword ptr [rcx+30h]
0x18004ac20  mulss   xmm1, xmm2
0x18004ac24  cvttss2si rax, xmm1
0x18004ac29  mov     [rbp+0C0h+var_54], eax
0x18004ac2c  lea     rcx, [rbp+0C0h+setPacket]; setPacket
0x18004ac30  mov     [rbp+0C0h+setPacket.type], 0FFFFFFF0h
0x18004ac37  mov     [rbp+0C0h+setPacket.size], 44h ; 'D'
0x18004ac3e  mov     qword ptr [rbp+0C0h+setPacket.adapterId.LowPart], rbx
0x18004ac42  mov     [rbp+0C0h+setPacket.id], esi
0x18004ac45  call    cs:__imp_DisplayConfigSetDeviceInfo
0x18004ac4b  test    eax, eax
0x18004ac4d  jle     short loc_18004AC57
0x18004ac4f  movzx   eax, ax
0x18004ac52  or      eax, 80070000h
0x18004ac57  mov     ebx, 80070057h
0x18004ac5c  test    eax, eax
0x18004ac5e  cmovs   eax, ebx
0x18004ac61  mov     ebx, eax
0x18004ac63  jmp     short loc_18004AC6A
0x18004ac65  mov     ebx, 80070057h
0x18004ac6a  mov     eax, cs:dword_18009E080
0x18004ac70  cmp     eax, 5
0x18004ac73  jbe     loc_18004AD36
0x18004ac79  mov     eax, [rbp+0C0h+var_54]
0x18004ac7c  lea     rdx, unk_180091840
0x18004ac83  mov     [rbp+0C0h+var_140], eax
0x18004ac86  mov     eax, [rbp+0C0h+var_58]
0x18004ac89  mov     [rbp+0C0h+var_13C], eax
0x18004ac8c  mov     eax, [rbp+0C0h+var_5C]
0x18004ac8f  mov     [rbp+0C0h+var_138], eax
0x18004ac92  mov     eax, [rbp+0C0h+var_60]
0x18004ac95  mov     [rbp+0C0h+var_134], eax
0x18004ac98  mov     eax, [rbp+0C0h+var_64]
0x18004ac9b  mov     [rbp+0C0h+var_130], eax
0x18004ac9e  mov     eax, [rbp+0C0h+var_68]
0x18004aca1  mov     [rbp+0C0h+var_12C], eax
0x18004aca4  mov     eax, [rbp+0C0h+var_6C]
0x18004aca7  mov     [rbp+0C0h+var_128], eax
0x18004acaa  mov     eax, [rbp+0C0h+var_70]
0x18004acad  mov     [rbp+0C0h+var_124], eax
0x18004acb0  mov     eax, [rbp+0C0h+var_74]
0x18004acb3  mov     [rbp+0C0h+var_120], eax
0x18004acb6  mov     eax, [rbp+0C0h+var_78]
0x18004acb9  mov     [rbp+0C0h+var_11C], eax
0x18004acbc  mov     eax, [rbp+0C0h+var_7C]
0x18004acbf  mov     [rbp+0C0h+var_118], eax
0x18004acc2  lea     rax, [rbp+0C0h+var_140]
0x18004acc6  mov     [rsp+1C0h+var_148], rax
0x18004accb  lea     rax, [rbp+0C0h+var_13C]
0x18004accf  mov     [rsp+1C0h+var_150], rax
0x18004acd4  lea     rax, [rbp+0C0h+var_138]
0x18004acd8  mov     [rsp+1C0h+var_158], rax
0x18004acdd  lea     rax, [rbp+0C0h+var_134]
0x18004ace1  mov     [rsp+1C0h+var_160], rax
0x18004ace6  lea     rax, [rbp+0C0h+var_130]
0x18004acea  mov     [rsp+1C0h+var_168], rax
0x18004acef  lea     rax, [rbp+0C0h+var_12C]
0x18004acf3  mov     [rsp+1C0h+var_170], rax
0x18004acf8  lea     rax, [rbp+0C0h+var_128]
0x18004acfc  mov     [rsp+1C0h+var_178], rax
0x18004ad01  lea     rax, [rbp+0C0h+var_124]
0x18004ad05  mov     [rsp+1C0h+var_180], rax
0x18004ad0a  lea     rax, [rbp+0C0h+var_120]
0x18004ad0e  mov     [rsp+1C0h+var_188], rax
0x18004ad13  lea     rax, [rbp+0C0h+var_11C]
0x18004ad17  mov     [rsp+1C0h+var_190], rax
0x18004ad1c  lea     rax, [rbp+0C0h+var_118]
0x18004ad20  mov     [rsp+1C0h+var_198], rax
0x18004ad25  lea     rax, [rbp+0C0h+var_114]
0x18004ad29  mov     [rsp+1C0h+var_1A0], rax
0x18004ad2e  mov     [rbp+0C0h+var_114], ebx
0x18004ad31  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33333333333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004ad36  mov     edx, 1; int
0x18004ad3b  lea     rcx, [rbp+0C0h+var_110]; struct CalibrationData *
0x18004ad3f  mov     r9d, edx; int
0x18004ad42  mov     r8d, edx; int
0x18004ad45  call    ?DeleteCalibrationData@@YAXPEAUCalibrationData@@HHH@Z; DeleteCalibrationData(CalibrationData *,int,int,int)
0x18004ad4a  mov     eax, ebx
0x18004ad4c  mov     rcx, [rbp+0C0h+var_18]
0x18004ad53  xor     rcx, rsp; StackCookie
0x18004ad56  call    __security_check_cookie
0x18004ad5b  mov     rbx, [rsp+1C0h+arg_10]
0x18004ad63  add     rsp, 1B0h
0x18004ad6a  pop     rdi
0x18004ad6b  pop     rsi
0x18004ad6c  pop     rbp
0x18004ad6d  retn
```
