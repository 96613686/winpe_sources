# CCAPIStm::Write(void const *,ulong,ulong *)

- ea: `0x18005ca70`
- end: `0x18005ccdc`
- name: `?Write@CCAPIStm@@UEAAJPEBXKPEAK@Z`
- size: `620`
- prototype: `__int64 __fastcall(CCAPIStm *__hidden this, const void *Src, size_t Size, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800247c8`
- `0x18005ab90`
- `0x18005ca70`
- `0x1800cc9a2`

## import_xrefs

- `CRYPT32!CryptMsgGetParam` at `0x18005cbf9`
- `CRYPT32!CryptMsgGetParam` at `0x18005cbf9`
- `CRYPT32!CryptMsgUpdate` at `0x18005cb32`
- `CRYPT32!CryptMsgUpdate` at `0x18005cb6e`
- `CRYPT32!CryptMsgUpdate` at `0x18005cbab`
- `CRYPT32!CryptMsgUpdate` at `0x18005cb32`
- `CRYPT32!CryptMsgUpdate` at `0x18005cb6e`
- `CRYPT32!CryptMsgUpdate` at `0x18005cbab`

## pseudocode

```c
__int64 __fastcall CCAPIStm::Write(CCAPIStm *this, const void *Src, size_t Size, unsigned int *a4)
{
  size_t v4; // rdi
  void *v8; // r10
  unsigned int LastError; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  const BYTE *v17; // rdx
  DWORD v18; // eax
  int v19; // ecx
  void *v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+20h] BYREF

  v4 = (unsigned int)Size;
  if ( a4 )
    *a4 = 0;
  v8 = (void *)*((_QWORD *)this + 3);
  if ( !v8 )
    return (unsigned int)-2147216364;
  v10 = *((_DWORD *)this + 3);
  if ( !v10 )
    return (unsigned int)-2147216363;
  v11 = v10 - 1;
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( !v12 )
      return (unsigned int)-2147418113;
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( !v16 )
            return (unsigned int)-2147216362;
          if ( v16 == 1 )
            return (unsigned int)-2147216361;
          return (unsigned int)-2147418113;
        }
      }
    }
  }
  v17 = (const BYTE *)*((_QWORD *)this + 18);
  if ( v17 )
  {
    v18 = *((_DWORD *)this + 38);
    if ( v18 + (unsigned int)Size < v18 )
    {
      LastError = -2147024882;
LABEL_19:
      *((_DWORD *)this + 3) = 6;
      return LastError;
    }
    if ( v18 + (unsigned int)Size > 0x1000 )
    {
      if ( !CryptMsgUpdate(v8, v17, v18, 0) )
        goto LABEL_22;
      *((_DWORD *)this + 38) = 0;
      v18 = 0;
    }
    if ( (unsigned int)v4 < 0x1000 )
    {
      memcpy_0((void *)(*((_QWORD *)this + 18) + v18), Src, v4);
      *((_DWORD *)this + 38) += v4;
    }
    else if ( !CryptMsgUpdate(*((HCRYPTMSG *)this + 3), (const BYTE *)Src, v4, 0) )
    {
LABEL_22:
      LastError = HrGetLastError();
      if ( (LastError & 0x80000000) == 0 )
        return LastError;
      goto LABEL_19;
    }
    if ( a4 )
      *a4 = v4;
    return 0;
  }
  if ( !CryptMsgUpdate(v8, (const BYTE *)Src, Size, 0) )
    goto LABEL_22;
  if ( a4 )
    *a4 = v4;
  v19 = *((_DWORD *)this + 3);
  if ( (unsigned int)(v19 - 1) > 1 )
  {
    if ( v19 != 3 )
      return 0;
LABEL_53:
    *((_DWORD *)this + 3) = 5;
    v23 = CCAPIStm::HandleEnveloped(this);
    if ( v23 < 0 )
    {
      if ( v23 != -2146889712 )
      {
        LastError = -2146644240;
        if ( v23 == -2147212268 )
          return LastError;
        if ( v23 == -2147212267 )
          v23 = -2146644240;
        LastError = v23;
        goto LABEL_19;
      }
      *((_DWORD *)this + 3) = 3;
    }
    return 0;
  }
  v20 = (void *)*((_QWORD *)this + 3);
  pvData = 0;
  pcbData = 4;
  if ( CryptMsgGetParam(v20, 1u, 0, &pvData, &pcbData) )
  {
    LastError = 0;
    *(_DWORD *)(*((_QWORD *)this + 12) + 12LL) = 0;
    v22 = *((_QWORD *)this + 12);
    switch ( pvData )
    {
      case 2:
        *(_DWORD *)(v22 + 12) |= 5u;
        break;
      case 3:
        *(_DWORD *)(v22 + 12) |= 2u;
        break;
      case 4:
        *(_DWORD *)(v22 + 12) |= 7u;
        break;
      default:
        LastError = -2146644296;
        *(_DWORD *)(v22 + 12) = pvData;
        break;
    }
    if ( (*((_BYTE *)this + 64) & 1) != 0 )
    {
      *((_DWORD *)this + 3) = 7;
      if ( (LastError & 0x80000000) != 0 )
        return LastError;
      return (unsigned int)-2147216361;
    }
    if ( pvData != 3 )
    {
      *((_DWORD *)this + 3) = 5;
      return 0;
    }
    goto LABEL_53;
  }
  v21 = HrGetLastError();
  LastError = 0;
  if ( v21 != -2146889712 )
    return v21;
  return LastError;
}

```

## disassembly

```asm
0x18005ca70  mov     [rsp+arg_8], rbx
0x18005ca75  push    rbp
0x18005ca76  push    rsi
0x18005ca77  push    rdi
0x18005ca78  sub     rsp, 30h
0x18005ca7c  mov     edi, r8d
0x18005ca7f  mov     rsi, r9
0x18005ca82  mov     rbp, rdx
0x18005ca85  mov     rbx, rcx
0x18005ca88  test    r9, r9
0x18005ca8b  jz      short loc_18005CA94
0x18005ca8d  mov     dword ptr [r9], 0
0x18005ca94  mov     r10, [rcx+18h]
0x18005ca98  test    r10, r10
0x18005ca9b  jnz     short loc_18005CAA7
0x18005ca9d  mov     ecx, 80041414h
0x18005caa2  jmp     loc_18005CCCD
0x18005caa7  mov     ecx, [rcx+0Ch]
0x18005caaa  test    ecx, ecx
0x18005caac  jz      loc_18005CCC8
0x18005cab2  sub     ecx, 1
0x18005cab5  jz      short loc_18005CAF3
0x18005cab7  sub     ecx, 1
0x18005caba  jz      short loc_18005CAE9
0x18005cabc  sub     ecx, 1
0x18005cabf  jz      short loc_18005CAF3
0x18005cac1  sub     ecx, 1
0x18005cac4  jz      short loc_18005CAF3
0x18005cac6  sub     ecx, 1
0x18005cac9  jz      short loc_18005CAF3
0x18005cacb  sub     ecx, 1
0x18005cace  jz      short loc_18005CADF
0x18005cad0  cmp     ecx, 1
0x18005cad3  jnz     short loc_18005CAE9
0x18005cad5  mov     ecx, 80041417h
0x18005cada  jmp     loc_18005CCCD
0x18005cadf  mov     ecx, 80041416h
0x18005cae4  jmp     loc_18005CCCD
0x18005cae9  mov     ecx, 8000FFFFh
0x18005caee  jmp     loc_18005CCCD
0x18005caf3  mov     rdx, [rbx+90h]; pbData
0x18005cafa  test    rdx, rdx
0x18005cafd  jz      loc_18005CB9F
0x18005cb03  mov     eax, [rbx+98h]
0x18005cb09  lea     ecx, [rax+rdi]
0x18005cb0c  cmp     ecx, eax
0x18005cb0e  jnb     short loc_18005CB21
0x18005cb10  mov     ecx, 8007000Eh
0x18005cb15  mov     dword ptr [rbx+0Ch], 6
0x18005cb1c  jmp     loc_18005CCCD
0x18005cb21  cmp     ecx, 1000h
0x18005cb27  jbe     short loc_18005CB59
0x18005cb29  xor     r9d, r9d; fFinal
0x18005cb2c  mov     r8d, eax; cbData
0x18005cb2f  mov     rcx, r10; hCryptMsg
0x18005cb32  call    cs:__imp_CryptMsgUpdate
0x18005cb38  test    eax, eax
0x18005cb3a  jnz     short loc_18005CB4D
0x18005cb3c  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18005cb41  mov     ecx, eax
0x18005cb43  test    eax, eax
0x18005cb45  jns     loc_18005CCCD
0x18005cb4b  jmp     short loc_18005CB15
0x18005cb4d  mov     dword ptr [rbx+98h], 0
0x18005cb57  xor     eax, eax
0x18005cb59  mov     rdx, rbp; Src
0x18005cb5c  cmp     edi, 1000h
0x18005cb62  jb      short loc_18005CB7A
0x18005cb64  mov     rcx, [rbx+18h]; hCryptMsg
0x18005cb68  xor     r9d, r9d; fFinal
0x18005cb6b  mov     r8d, edi; cbData
0x18005cb6e  call    cs:__imp_CryptMsgUpdate
0x18005cb74  test    eax, eax
0x18005cb76  jnz     short loc_18005CB91
0x18005cb78  jmp     short loc_18005CB3C
0x18005cb7a  mov     ecx, eax
0x18005cb7c  mov     r8, rdi; Size
0x18005cb7f  add     rcx, [rbx+90h]; void *
0x18005cb86  call    memcpy_0
0x18005cb8b  add     [rbx+98h], edi
0x18005cb91  test    rsi, rsi
0x18005cb94  jz      short loc_18005CB98
0x18005cb96  mov     [rsi], edi
0x18005cb98  xor     ecx, ecx
0x18005cb9a  jmp     loc_18005CCCD
0x18005cb9f  xor     r9d, r9d; fFinal
0x18005cba2  mov     r8d, edi; cbData
0x18005cba5  mov     rdx, rbp; pbData
0x18005cba8  mov     rcx, r10; hCryptMsg
0x18005cbab  call    cs:__imp_CryptMsgUpdate
0x18005cbb1  test    eax, eax
0x18005cbb3  jz      short loc_18005CB3C
0x18005cbb5  test    rsi, rsi
0x18005cbb8  jz      short loc_18005CBBC
0x18005cbba  mov     [rsi], edi
0x18005cbbc  mov     ecx, [rbx+0Ch]
0x18005cbbf  mov     edi, 5
0x18005cbc4  lea     eax, [rcx-1]
0x18005cbc7  cmp     eax, 1
0x18005cbca  ja      loc_18005CC7E
0x18005cbd0  mov     rcx, [rbx+18h]; hCryptMsg
0x18005cbd4  lea     rax, [rsp+48h+arg_18]
0x18005cbd9  lea     r9, [rsp+48h+pvData]; pvData
0x18005cbde  mov     [rsp+48h+pcbData], rax; pcbData
0x18005cbe3  xor     r8d, r8d; dwIndex
0x18005cbe6  mov     [rsp+48h+pvData], 0
0x18005cbee  lea     edx, [rdi-4]; dwParamType
0x18005cbf1  mov     [rsp+48h+arg_18], 4
0x18005cbf9  call    cs:__imp_CryptMsgGetParam
0x18005cbff  test    eax, eax
0x18005cc01  jnz     short loc_18005CC17
0x18005cc03  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18005cc08  xor     ecx, ecx
0x18005cc0a  cmp     eax, 80091010h
0x18005cc0f  cmovnz  ecx, eax
0x18005cc12  jmp     loc_18005CCCD
0x18005cc17  mov     rax, [rbx+60h]
0x18005cc1b  xor     ecx, ecx
0x18005cc1d  mov     dword ptr [rax+0Ch], 0
0x18005cc24  mov     r8d, [rsp+48h+pvData]
0x18005cc29  mov     edx, r8d
0x18005cc2c  mov     rax, [rbx+60h]
0x18005cc30  sub     edx, 2
0x18005cc33  jz      short loc_18005CC56
0x18005cc35  sub     edx, 1
0x18005cc38  jz      short loc_18005CC50
0x18005cc3a  cmp     edx, 1
0x18005cc3d  jz      short loc_18005CC4A
0x18005cc3f  mov     ecx, 800CCEB8h
0x18005cc44  mov     [rax+0Ch], r8d
0x18005cc48  jmp     short loc_18005CC59
0x18005cc4a  or      dword ptr [rax+0Ch], 7
0x18005cc4e  jmp     short loc_18005CC59
0x18005cc50  or      dword ptr [rax+0Ch], 2
0x18005cc54  jmp     short loc_18005CC59
0x18005cc56  or      [rax+0Ch], edi
0x18005cc59  test    byte ptr [rbx+40h], 1
0x18005cc5d  jz      short loc_18005CC6F
0x18005cc5f  mov     dword ptr [rbx+0Ch], 7
0x18005cc66  test    ecx, ecx
0x18005cc68  js      short loc_18005CCCD
0x18005cc6a  jmp     loc_18005CAD5
0x18005cc6f  cmp     [rsp+48h+pvData], 3
0x18005cc74  jz      short loc_18005CC87
0x18005cc76  mov     [rbx+0Ch], edi
0x18005cc79  jmp     loc_18005CB98
0x18005cc7e  cmp     ecx, 3
0x18005cc81  jnz     loc_18005CB98
0x18005cc87  mov     rcx, rbx; this
0x18005cc8a  mov     [rbx+0Ch], edi
0x18005cc8d  call    ?HandleEnveloped@CCAPIStm@@AEAAJXZ; CCAPIStm::HandleEnveloped(void)
0x18005cc92  test    eax, eax
0x18005cc94  jns     loc_18005CB98
0x18005cc9a  cmp     eax, 80091010h
0x18005cc9f  jnz     short loc_18005CCAD
0x18005cca1  mov     dword ptr [rbx+0Ch], 3
0x18005cca8  jmp     loc_18005CB98
0x18005ccad  mov     ecx, 800CCEF0h
0x18005ccb2  cmp     eax, 80042414h
0x18005ccb7  jz      short loc_18005CCCD
0x18005ccb9  cmp     eax, 80042415h
0x18005ccbe  cmovz   eax, ecx
0x18005ccc1  mov     ecx, eax
0x18005ccc3  jmp     loc_18005CB15
0x18005ccc8  mov     ecx, 80041415h
0x18005cccd  mov     rbx, [rsp+48h+arg_8]
0x18005ccd2  mov     eax, ecx
0x18005ccd4  add     rsp, 30h
0x18005ccd8  pop     rdi
0x18005ccd9  pop     rsi
0x18005ccda  pop     rbp
0x18005ccdb  retn
```
