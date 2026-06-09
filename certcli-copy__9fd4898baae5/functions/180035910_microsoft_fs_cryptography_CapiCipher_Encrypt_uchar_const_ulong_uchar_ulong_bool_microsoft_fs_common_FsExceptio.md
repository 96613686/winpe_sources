# microsoft::fs::cryptography::CapiCipher::Encrypt(uchar const *,ulong,uchar *,ulong *,bool,microsoft::fs::common::FsException *)

- ea: `0x180035910`
- end: `0x180035af1`
- name: `?Encrypt@CapiCipher@cryptography@fs@microsoft@@UEAAXPEBEKPEAEPEAK_NPEAVFsException@common@34@@Z`
- size: `481`
- prototype: `void(microsoft::fs::cryptography::CapiCipher *__hidden this, const unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int *, bool, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180002306`
- `0x180019448`
- `0x18002e5e4`
- `0x18002eff0`
- `0x180030fa0`
- `0x180035910`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a80`

## string_xrefs

- `0x180035960`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x1800359a4`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180035a23`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180035a9e`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`

## pseudocode

```c
void __fastcall microsoft::fs::cryptography::CapiCipher::Encrypt(
        microsoft::fs::cryptography::CapiCipher *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int *a5,
        bool a6,
        struct microsoft::fs::common::FsException *a7)
{
  size_t v8; // rsi
  unsigned int v12; // r8d
  unsigned int v13; // r12d
  int v14; // eax
  struct microsoft::fs::common::FsException *v15; // r8
  DWORD LastError; // eax
  int v17; // eax
  const struct microsoft::fs::common::FsException *v18; // rax
  const microsoft::fs::common::FsException *v19; // [rsp+40h] [rbp-138h] BYREF
  _QWORD v20[6]; // [rsp+48h] [rbp-130h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+78h] [rbp-100h] BYREF
  _BYTE v22[48]; // [rsp+A8h] [rbp-D0h] BYREF
  _BYTE v23[48]; // [rsp+D8h] [rbp-A0h] BYREF
  _BYTE v24[112]; // [rsp+108h] [rbp-70h] BYREF

  v8 = a3;
  try
  {
    if ( a7 )
      (*(void (__fastcall **)(struct microsoft::fs::common::FsException *))(*(_QWORD *)a7 + 8LL))(a7);
    if ( !a2 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0xD9u,
        L"pbPlainText",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( !a5 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v22,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0xDBu,
        L"pcbCipherText",
        -2147024809);
      throw (microsoft::fs::common::FsException *)v22;
    }
  }
  catch ( const microsoft::fs::common::FsException *v19 )
  {
    if ( !a7 )
      throw;
    microsoft::fs::common::FsException::assign(a7, v19);
    return;
  }
  catch ( ... )
  {
    if ( !a7 )
      throw;
    v18 = (const struct microsoft::fs::common::FsException *)microsoft::fs::common::FsException::FsException(
                                                               (microsoft::fs::common::FsException *)v20,
                                                               L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
                                                               0x10Du,
                                                               &psz,
                                                               -2147467259,
                                                               L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(a7, v18);
    v20[0] = &microsoft::fs::common::FsException::`vftable';
    operator delete[]((void *)v20[1]);
    operator delete[]((void *)v20[2]);
    operator delete[]((void *)v20[3]);
    operator delete[]((void *)v20[5]);
    return;
  }
  if ( a4 )
  {
    v13 = *a5;
    if ( a2 != a4 )
    {
      if ( v13 < (unsigned int)v8 )
      {
        v14 = HR_FROM_WIN32(0x80090004);
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v23,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
          0xF0u,
          L"*pcbCipherText >= cbPlainText",
          v14);
        throw (microsoft::fs::common::FsException *)v23;
      }
      memcpy_0(a4, a2, v8);
    }
    *a5 = v8;
    if ( !(unsigned int)fsCryptEncrypt(*((_QWORD *)this + 6), (unsigned __int64)a2, a6, (unsigned int)a4, a4, a5, v13) )
    {
      LastError = GetLastError();
      v17 = HR_FROM_WIN32(LastError);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v24,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0xFDu,
        L"CryptEncrypt( m_hKey, 0, fFinal ? TRUE : FALSE, 0, pbCipherText, pcbCipherText, cbCipherTextMax)",
        v17);
      throw (microsoft::fs::common::FsException *)v24;
    }
    if ( *((_DWORD *)this + 6) == 41984 )
      microsoft::fs::cryptography::CryptoUtil::IToOs(a4, *a5, v15);
  }
  else
  {
    v12 = *((_DWORD *)this + 5);
    if ( v12 )
      *a5 = v12 + v12 + v8 - 1 - (v12 + (_DWORD)v8 - 1) % v12;
    else
      *a5 = 1;
  }
}

```

## disassembly

```asm
0x180035910  push    rbx
0x180035912  push    rsi
0x180035913  push    rdi
0x180035914  push    r12
0x180035916  push    r14
0x180035918  push    r15
0x18003591a  sub     rsp, 148h
0x180035921  mov     rdi, r9
0x180035924  mov     esi, r8d
0x180035927  mov     r15, rdx
0x18003592a  mov     r14, rcx
0x18003592d  mov     rcx, [rsp+178h+arg_30]
0x180035935  test    rcx, rcx
0x180035938  jz      short loc_180035946
0x18003593a  mov     rax, [rcx]
0x18003593d  mov     rax, [rax+8]
0x180035941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035946  test    r15, r15
0x180035949  jnz     short loc_180035982
0x18003594b  mov     dword ptr [rsp+178h+var_158], 80070057h; int
0x180035953  lea     r9, aPbplaintext; "pbPlainText"
0x18003595a  mov     r8d, 0D9h; unsigned int
0x180035960  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035967  lea     rcx, [rsp+178h+pExceptionObject]; this
0x18003596c  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180035971  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180035978  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x18003597d  call    _CxxThrowException_0
0x180035982  mov     rbx, [rsp+178h+arg_20]
0x18003598a  test    rbx, rbx
0x18003598d  jnz     short loc_1800359CC
0x18003598f  mov     dword ptr [rsp+178h+var_158], 80070057h; int
0x180035997  lea     r9, aPcbciphertext; "pcbCipherText"
0x18003599e  mov     r8d, 0DBh; unsigned int
0x1800359a4  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800359ab  lea     rcx, [rsp+178h+var_D0]; this
0x1800359b3  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800359b8  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800359bf  lea     rcx, [rsp+178h+var_D0]; pExceptionObject
0x1800359c7  call    _CxxThrowException_0
0x1800359cc  test    rdi, rdi
0x1800359cf  jnz     short loc_1800359FB
0x1800359d1  mov     r8d, [r14+14h]
0x1800359d5  test    r8d, r8d
0x1800359d8  jnz     short loc_1800359E2
0x1800359da  mov     dword ptr [rbx], 1
0x1800359e0  jmp     short loc_1800359F6
0x1800359e2  lea     ecx, [rsi-1]
0x1800359e5  add     ecx, r8d
0x1800359e8  xor     edx, edx
0x1800359ea  mov     eax, ecx
0x1800359ec  div     r8d
0x1800359ef  sub     ecx, edx
0x1800359f1  add     ecx, r8d
0x1800359f4  mov     [rbx], ecx
0x1800359f6  jmp     loc_180035ADF
0x1800359fb  mov     r12d, [rbx]
0x1800359fe  cmp     r15, rdi
0x180035a01  jz      short loc_180035A59
0x180035a03  cmp     r12d, esi
0x180035a06  jnb     short loc_180035A4B
0x180035a08  mov     ecx, 80090004h; unsigned int
0x180035a0d  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180035a12  mov     dword ptr [rsp+178h+var_158], eax; int
0x180035a16  lea     r9, aPcbciphertextC; "*pcbCipherText >= cbPlainText"
0x180035a1d  mov     r8d, 0F0h; unsigned int
0x180035a23  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035a2a  lea     rcx, [rsp+178h+var_A0]; this
0x180035a32  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180035a37  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180035a3e  lea     rcx, [rsp+178h+var_A0]; pExceptionObject
0x180035a46  call    _CxxThrowException_0
0x180035a4b  mov     r8, rsi; Size
0x180035a4e  mov     rdx, r15; Src
0x180035a51  mov     rcx, rdi; void *
0x180035a54  call    memcpy_0
0x180035a59  mov     [rbx], esi
0x180035a5b  movzx   r8d, [rsp+178h+arg_28]; int
0x180035a64  mov     [rsp+178h+var_148], r12d; DWORD
0x180035a69  mov     [rsp+178h+var_150], rbx; DWORD *
0x180035a6e  mov     [rsp+178h+var_158], rdi; BYTE *
0x180035a73  mov     rcx, [r14+30h]; unsigned __int64
0x180035a77  call    ?fsCryptEncrypt@@YAH_K0HKPEAEPEAKK@Z; fsCryptEncrypt(unsigned __int64,unsigned __int64,int,ulong,uchar *,ulong *,ulong)
0x180035a7c  test    eax, eax
0x180035a7e  jnz     short loc_180035AC6
0x180035a80  call    cs:__imp_GetLastError
0x180035a86  mov     ecx, eax; unsigned int
0x180035a88  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180035a8d  mov     dword ptr [rsp+178h+var_158], eax; int
0x180035a91  lea     r9, aCryptencryptMH; "CryptEncrypt( m_hKey, 0, fFinal ? TRUE "...
0x180035a98  mov     r8d, 0FDh; unsigned int
0x180035a9e  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035aa5  lea     rcx, [rsp+178h+var_70]; this
0x180035aad  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180035ab2  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180035ab9  lea     rcx, [rsp+178h+var_70]; pExceptionObject
0x180035ac1  call    _CxxThrowException_0
0x180035ac6  cmp     dword ptr [r14+18h], 0A400h
0x180035ace  jnz     short loc_180035ADB
0x180035ad0  mov     edx, [rbx]; unsigned int
0x180035ad2  mov     rcx, rdi; unsigned __int8 *
0x180035ad5  call    ?IToOs@CryptoUtil@cryptography@fs@microsoft@@SAXPEAEKPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::IToOs(uchar *,ulong,microsoft::fs::common::FsException *)
0x180035ada  nop
0x180035adb  jmp     short loc_180035ADF
0x180035add  jmp     short $+2
0x180035adf  add     rsp, 148h
0x180035ae6  pop     r15
0x180035ae8  pop     r14
0x180035aea  pop     r12
0x180035aec  pop     rdi
0x180035aed  pop     rsi
0x180035aee  pop     rbx
0x180035aef  retn
```
