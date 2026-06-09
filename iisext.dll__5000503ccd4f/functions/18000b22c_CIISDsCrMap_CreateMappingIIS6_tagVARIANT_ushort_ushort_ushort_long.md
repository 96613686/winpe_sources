# CIISDsCrMap::CreateMappingIIS6(tagVARIANT,ushort *,ushort *,ushort *,long)

- ea: `0x18000b22c`
- end: `0x18000b69d`
- name: `?CreateMappingIIS6@CIISDsCrMap@@AEAAJUtagVARIANT@@PEAG11J@Z`
- size: `1137`
- prototype: `__int64 __fastcall(CIISDsCrMap *this, VARIANTARG *pvargSrc, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000ac50`

## callees

- `0x18000a8e0`
- `0x18000b22c`
- `0x18000b898`
- `0x18000bb84`
- `0x18000cba0`
- `0x18000d210`
- `0x18000d6d8`
- `0x1800111e0`
- `0x180012010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000b672`
- `KERNEL32!LocalFree` at `0x18000b672`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b3ce`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b40e`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b445`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b592`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b5d1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b606`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b3ce`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b40e`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b445`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b592`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b5d1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000b606`
- `IisRTL!PuDbgPrint` at `0x18000b2fb`
- `IisRTL!PuDbgPrint` at `0x18000b38d`
- `IisRTL!PuDbgPrint` at `0x18000b2fb`
- `IisRTL!PuDbgPrint` at `0x18000b38d`

## string_xrefs

- `0x18000b2e9`: `Invalid cert passed to CreateMapping() 0x%x\n`
- `0x18000b2d7`: `CIISDsCrMap::CreateMappingIIS6`
- `0x18000b374`: `CIISDsCrMap::CreateMappingIIS6`

## pseudocode

```c
__int64 __fastcall CIISDsCrMap::CreateMappingIIS6(
        CIISDsCrMap *this,
        VARIANTARG *pvargSrc,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6)
{
  OLECHAR *v9; // r12
  int BlobFromVariant; // eax
  unsigned int v11; // r9d
  unsigned __int8 *v12; // rsi
  int v13; // ebx
  DWORD v14; // r15d
  int CertificateHashString; // eax
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  IRecordInfo *pRecInfo; // xmm1_8
  int v19; // r12d
  int v20; // eax
  unsigned __int8 *v21; // r14
  UINT v22; // eax
  unsigned __int8 *v23; // rbx
  UINT v24; // eax
  UINT v25; // eax
  unsigned int v26; // r8d
  unsigned int v27; // r8d
  UINT v28; // eax
  UINT v29; // eax
  UINT v30; // eax
  DWORD cbCertEncoded; // [rsp+30h] [rbp-D0h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-C8h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  BSTR v35; // [rsp+48h] [rbp-B8h]
  struct tagVARIANT v36; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v37[48]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v38[264]; // [rsp+D0h] [rbp-30h] BYREF

  v35 = a4;
  pbstr = a5;
  hMem = 0;
  cbCertEncoded = 0;
  v9 = a4;
  BlobFromVariant = GetBlobFromVariant(pvargSrc, (unsigned __int8 **)&hMem, &cbCertEncoded);
  v12 = (unsigned __int8 *)hMem;
  v13 = BlobFromVariant;
  if ( BlobFromVariant < 0 )
    goto LABEL_29;
  v14 = cbCertEncoded;
  CertificateHashString = GetCertificateHashString((BYTE *)hMem, cbCertEncoded, v37, v11);
  v13 = CertificateHashString;
  if ( CertificateHashString < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\admin\\adsi\\iisext\\crmap.cxx",
        286,
        "CIISDsCrMap::CreateMappingIIS6",
        "Invalid cert passed to CreateMapping() 0x%x\n",
        CertificateHashString);
    goto LABEL_29;
  }
  if ( CIISDsCrMap::OpenMd(this, L"Cert11/Mappings", v16) < 0 )
  {
    v21 = (unsigned __int8 *)pbstr;
  }
  else
  {
    pRecInfo = pvargSrc->pRecInfo;
    v19 = 0;
    *(_OWORD *)&v36.vt = *(_OWORD *)&pvargSrc->vt;
    v36.pRecInfo = pRecInfo;
    v13 = CIISDsCrMap::Locate(this, 1, &v36, v38);
    if ( v13 < 0 )
    {
      v21 = (unsigned __int8 *)pbstr;
    }
    else
    {
      v19 = 1;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\admin\\adsi\\iisext\\crmap.cxx",
          317,
          "CIISDsCrMap::CreateMappingIIS6",
          "Replacing old 1-1 cert mapping with new mapping\n");
      v20 = CIISDsCrMap::SetMdData(this, v38, 0x821u, 1u, 4u, (unsigned __int8 *)&a6);
      v21 = (unsigned __int8 *)pbstr;
      v13 = v20;
      if ( v20 >= 0 )
      {
        v22 = SysStringLen(pbstr);
        v13 = CIISDsCrMap::SetMdData(this, v38, 0x820u, 2u, 2 * v22 + 2, v21);
        if ( v13 >= 0 )
        {
          v23 = (unsigned __int8 *)v35;
          v24 = SysStringLen(v35);
          v13 = CIISDsCrMap::SetMdData(this, v38, 0x82Du, 2u, 2 * v24 + 2, v23);
          if ( v13 >= 0 )
          {
            v25 = SysStringLen(a3);
            v13 = CIISDsCrMap::SetMdData(this, v38, 0x81Fu, 2u, 2 * v25 + 2, (unsigned __int8 *)a3);
            if ( v13 >= 0 )
              v13 = CIISDsCrMap::SetMdData(this, v38, 0x81Eu, 3u, v14, v12);
          }
        }
      }
    }
    CIISDsCrMap::CloseMd(this, v13 >= 0);
    if ( v19 )
      goto LABEL_29;
    v9 = v35;
  }
  v13 = CIISDsCrMap::OpenMd(this, L"Cert11/Mappings", v17);
  if ( v13 == -2147024893 )
  {
    v13 = CIISDsCrMap::OpenMd(this, (unsigned __int16 *)&::hMem, v26);
    if ( v13 < 0 )
      goto LABEL_29;
    (*(void (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *))(**((_QWORD **)this + 7) + 24LL))(
      *((_QWORD *)this + 7),
      *((unsigned int *)this + 16),
      L"Cert11/Mappings");
    CIISDsCrMap::CloseMd(this, 0);
    v13 = CIISDsCrMap::OpenMd(this, L"Cert11/Mappings", v27);
  }
  if ( v13 >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 7) + 24LL))(
            *((_QWORD *)this + 7),
            *((unsigned int *)this + 16),
            v37);
    if ( v13 >= 0 )
    {
      v13 = CIISDsCrMap::SetMdData(this, v37, 0x821u, 1u, 4u, (unsigned __int8 *)&a6);
      if ( v13 >= 0 )
      {
        v28 = SysStringLen((BSTR)v21);
        v13 = CIISDsCrMap::SetMdData(this, v37, 0x820u, 2u, 2 * v28 + 2, v21);
        if ( v13 >= 0 )
        {
          v29 = SysStringLen(v9);
          v13 = CIISDsCrMap::SetMdData(this, v37, 0x82Du, 2u, 2 * v29 + 2, (unsigned __int8 *)v9);
          if ( v13 >= 0 )
          {
            v30 = SysStringLen(a3);
            v13 = CIISDsCrMap::SetMdData(this, v37, 0x81Fu, 2u, 2 * v30 + 2, (unsigned __int8 *)a3);
            if ( v13 >= 0 )
              v13 = CIISDsCrMap::SetMdData(this, v37, 0x81Eu, 3u, v14, v12);
          }
        }
      }
    }
    CIISDsCrMap::CloseMd(this, v13 >= 0);
  }
LABEL_29:
  if ( v12 )
    LocalFree(v12);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000b22c  push    rbp
0x18000b22e  push    rbx
0x18000b22f  push    rsi
0x18000b230  push    rdi
0x18000b231  push    r12
0x18000b233  push    r13
0x18000b235  push    r14
0x18000b237  push    r15
0x18000b239  lea     rbp, [rsp-1F8h]
0x18000b241  sub     rsp, 2F8h
0x18000b248  mov     rax, cs:__security_cookie
0x18000b24f  xor     rax, rsp
0x18000b252  mov     [rbp+230h+var_50], rax
0x18000b259  mov     rax, [rbp+230h+arg_20]
0x18000b260  mov     r14, rdx
0x18000b263  mov     r13, r8
0x18000b266  mov     [rsp+330h+var_2E8], r9
0x18000b26b  mov     rdi, rcx
0x18000b26e  mov     [rsp+330h+pbstr], rax
0x18000b273  mov     rcx, r14; pvargSrc
0x18000b276  mov     [rsp+330h+hMem], 0
0x18000b27f  lea     r8, [rsp+330h+cbCertEncoded]; unsigned int *
0x18000b284  mov     [rsp+330h+cbCertEncoded], 0
0x18000b28c  lea     rdx, [rsp+330h+hMem]; unsigned __int8 **
0x18000b291  mov     r12, r9
0x18000b294  call    ?GetBlobFromVariant@@YAJPEAUtagVARIANT@@PEAPEAEPEAK@Z; GetBlobFromVariant(tagVARIANT *,uchar * *,ulong *)
0x18000b299  mov     rsi, [rsp+330h+hMem]
0x18000b29e  mov     ebx, eax
0x18000b2a0  test    eax, eax
0x18000b2a2  js      loc_18000B66A
0x18000b2a8  mov     r15d, [rsp+330h+cbCertEncoded]
0x18000b2ad  lea     r8, [rsp+330h+var_2C0]; unsigned __int16 *
0x18000b2b2  mov     edx, r15d; cbCertEncoded
0x18000b2b5  mov     rcx, rsi; pbCertEncoded
0x18000b2b8  call    ?GetCertificateHashString@@YAJPEAEKPEAGK@Z; GetCertificateHashString(uchar *,ulong,ushort *,ulong)
0x18000b2bd  mov     ebx, eax
0x18000b2bf  test    eax, eax
0x18000b2c1  jns     short loc_18000B306
0x18000b2c3  test    byte ptr cs:g_dwDebugFlags, 3
0x18000b2ca  jz      loc_18000B66A
0x18000b2d0  mov     rcx, cs:g_pDebug
0x18000b2d7  lea     r9, aCiisdscrmapCre; "CIISDsCrMap::CreateMappingIIS6"
0x18000b2de  mov     dword ptr [rsp+330h+var_308], eax
0x18000b2e2  lea     rdx, aInetsrvIisAdmi; "inetsrv\\iis\\admin\\adsi\\iisext\\crma"...
0x18000b2e9  lea     rax, aInvalidCertPas; "Invalid cert passed to CreateMapping() "...
0x18000b2f0  mov     r8d, 11Eh
0x18000b2f6  mov     qword ptr [rsp+330h+var_310], rax
0x18000b2fb  call    cs:__imp_PuDbgPrint
0x18000b301  jmp     loc_18000B66A
0x18000b306  lea     rdx, aCert11Mappings; "Cert11/Mappings"
0x18000b30d  mov     rcx, rdi; this
0x18000b310  call    ?OpenMd@CIISDsCrMap@@QEAAJPEAGK@Z; CIISDsCrMap::OpenMd(ushort *,ulong)
0x18000b315  test    eax, eax
0x18000b317  js      loc_18000B4C3
0x18000b31d  movaps  xmm0, xmmword ptr [r14]
0x18000b321  lea     r9, [rbp+230h+var_260]; unsigned __int16 *
0x18000b325  movsd   xmm1, qword ptr [r14+10h]
0x18000b32b  lea     r8, [rsp+330h+var_2E0]; struct tagVARIANT
0x18000b330  xor     r12d, r12d
0x18000b333  movaps  xmmword ptr [rsp+330h+var_2E0], xmm0
0x18000b338  mov     rcx, rdi; this
0x18000b33b  movsd   qword ptr [rsp+330h+var_2E0+10h], xmm1
0x18000b341  lea     edx, [r12+1]; int
0x18000b346  call    ?Locate@CIISDsCrMap@@QEAAJJUtagVARIANT@@PEAG@Z; CIISDsCrMap::Locate(long,tagVARIANT,ushort *)
0x18000b34b  mov     ebx, eax
0x18000b34d  test    eax, eax
0x18000b34f  js      loc_18000B49F
0x18000b355  test    byte ptr cs:g_dwDebugFlags, 3
0x18000b35c  lea     ebx, [r12+1]
0x18000b361  mov     r12d, ebx
0x18000b364  jz      short loc_18000B393
0x18000b366  mov     rcx, cs:g_pDebug
0x18000b36d  lea     rax, aReplacingOld11; "Replacing old 1-1 cert mapping with new"...
0x18000b374  lea     r9, aCiisdscrmapCre; "CIISDsCrMap::CreateMappingIIS6"
0x18000b37b  mov     qword ptr [rsp+330h+var_310], rax
0x18000b380  mov     r8d, 13Dh
0x18000b386  lea     rdx, aInetsrvIisAdmi; "inetsrv\\iis\\admin\\adsi\\iisext\\crma"...
0x18000b38d  call    cs:__imp_PuDbgPrint
0x18000b393  lea     rax, [rbp+230h+arg_28]
0x18000b39a  mov     r9d, ebx; unsigned int
0x18000b39d  mov     [rsp+330h+var_308], rax; unsigned __int8 *
0x18000b3a2  lea     rdx, [rbp+230h+var_260]; unsigned __int16 *
0x18000b3a6  mov     r8d, 821h; unsigned int
0x18000b3ac  mov     [rsp+330h+var_310], 4; unsigned int
0x18000b3b4  mov     rcx, rdi; this
0x18000b3b7  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000b3bc  mov     r14, [rsp+330h+pbstr]
0x18000b3c1  mov     ebx, eax
0x18000b3c3  test    eax, eax
0x18000b3c5  js      loc_18000B4A4
0x18000b3cb  mov     rcx, r14; pbstr
0x18000b3ce  call    cs:__imp_SysStringLen
0x18000b3d4  mov     [rsp+330h+var_308], r14; unsigned __int8 *
0x18000b3d9  lea     rdx, [rbp+230h+var_260]; unsigned __int16 *
0x18000b3dd  mov     r9d, 2; unsigned int
0x18000b3e3  mov     r8d, 820h; unsigned int
0x18000b3e9  mov     rcx, rdi; this
0x18000b3ec  lea     eax, ds:2[rax*2]
0x18000b3f3  mov     [rsp+330h+var_310], eax; unsigned int
0x18000b3f7  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000b3fc  mov     ebx, eax
0x18000b3fe  test    eax, eax
0x18000b400  js      loc_18000B4A4
0x18000b406  mov     rbx, [rsp+330h+var_2E8]
0x18000b40b  mov     rcx, rbx; pbstr
0x18000b40e  call    cs:__imp_SysStringLen
0x18000b414  mov     [rsp+330h+var_308], rbx; unsigned __int8 *
0x18000b419  lea     rdx, [rbp+230h+var_260]; unsigned __int16 *
0x18000b41d  mov     r9d, 2; unsigned int
0x18000b423  mov     r8d, 82Dh; unsigned int
0x18000b429  mov     rcx, rdi; this
0x18000b42c  lea     eax, ds:2[rax*2]
0x18000b433  mov     [rsp+330h+var_310], eax; unsigned int
0x18000b437  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000b43c  mov     ebx, eax
0x18000b43e  test    eax, eax
0x18000b440  js      short loc_18000B4A4
0x18000b442  mov     rcx, r13; pbstr
0x18000b445  call    cs:__imp_SysStringLen
0x18000b44b  mov     [rsp+330h+var_308], r13; unsigned __int8 *
0x18000b450  lea     rdx, [rbp+230h+var_260]; unsigned __int16 *
0x18000b454  mov     r9d, 2; unsigned int
0x18000b45a  mov     r8d, 81Fh; unsigned int
0x18000b460  mov     rcx, rdi; this
0x18000b463  lea     eax, ds:2[rax*2]
0x18000b46a  mov     [rsp+330h+var_310], eax; unsigned int
0x18000b46e  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000b473  mov     ebx, eax
0x18000b475  test    eax, eax
0x18000b477  js      short loc_18000B4A4
0x18000b479  mov     [rsp+330h+var_308], rsi; unsigned __int8 *
0x18000b47e  lea     rdx, [rbp+230h+var_260]; unsigned __int16 *
0x18000b482  mov     r9d, 3; unsigned int
0x18000b488  mov     [rsp+330h+var_310], r15d; unsigned int
0x18000b48d  mov     r8d, 81Eh; unsigned int
0x18000b493  mov     rcx, rdi; this
0x18000b496  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000b49b  mov     ebx, eax
0x18000b49d  jmp     short loc_18000B4A4
0x18000b49f  mov     r14, [rsp+330h+pbstr]
0x18000b4a4  mov     edx, ebx
0x18000b4a6  mov     rcx, rdi; this
0x18000b4a9  not     edx
0x18000b4ab  shr     edx, 1Fh; int
0x18000b4ae  call    ?CloseMd@CIISDsCrMap@@QEAAJH@Z; CIISDsCrMap::CloseMd(int)
0x18000b4b3  test    r12d, r12d
0x18000b4b6  jnz     loc_18000B66A
0x18000b4bc  mov     r12, [rsp+330h+var_2E8]
0x18000b4c1  jmp     short loc_18000B4C8
0x18000b4c3  mov     r14, [rsp+330h+pbstr]
0x18000b4c8  lea     rdx, aCert11Mappings; "Cert11/Mappings"
0x18000b4cf  mov     rcx, rdi; this
0x18000b4d2  call    ?OpenMd@CIISDsCrMap@@QEAAJPEAGK@Z; CIISDsCrMap::OpenMd(ushort *,ulong)
0x18000b4d7  mov     ebx, eax
0x18000b4d9  cmp     eax, 80070003h
0x18000b4de  jnz     short loc_18000B52E
0x18000b4e0  lea     rdx, hMem; unsigned __int16 *
0x18000b4e7  mov     rcx, rdi; this
0x18000b4ea  call    ?OpenMd@CIISDsCrMap@@QEAAJPEAGK@Z; CIISDsCrMap::OpenMd(ushort *,ulong)
0x18000b4ef  mov     ebx, eax
0x18000b4f1  test    eax, eax
0x18000b4f3  js      loc_18000B66A
0x18000b4f9  mov     rcx, [rdi+38h]
0x18000b4fd  lea     r8, aCert11Mappings; "Cert11/Mappings"
0x18000b504  mov     edx, [rdi+40h]
0x18000b507  mov     rax, [rcx]
0x18000b50a  mov     rax, [rax+18h]
0x18000b50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b513  xor     edx, edx; int
0x18000b515  mov     rcx, rdi; this
0x18000b518  call    ?CloseMd@CIISDsCrMap@@QEAAJH@Z; CIISDsCrMap::CloseMd(int)
0x18000b51d  lea     rdx, aCert11Mappings; "Cert11/Mappings"
0x18000b524  mov     rcx, rdi; this
0x18000b527  call    ?OpenMd@CIISDsCrMap@@QEAAJPEAGK@Z; CIISDsCrMap::OpenMd(ushort *,ulong)
0x18000b52c  mov     ebx, eax
0x18000b52e  test    ebx, ebx
0x18000b530  js      loc_18000B66A
0x18000b536  mov     rcx, [rdi+38h]
0x18000b53a  lea     r8, [rsp+330h+var_2C0]
0x18000b53f  mov     edx, [rdi+40h]
0x18000b542  mov     rax, [rcx]
0x18000b545  mov     rax, [rax+18h]
0x18000b549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b54e  mov     ebx, eax
0x18000b550  test    eax, eax
0x18000b552  js      loc_18000B65B
0x18000b558  lea     rax, [rbp+230h+arg_28]
0x18000b55f  mov     r9d, 1; unsigned int
0x18000b565  mov     [rsp+330h+var_308], rax; unsigned __int8 *
0x18000b56a  lea     rdx, [rsp+330h+var_2C0]; unsigned __int16 *
0x18000b56f  mov     r8d, 821h; unsigned int
0x18000b575  mov     [rsp+330h+var_310], 4; unsigned int
0x18000b57d  mov     rcx, rdi; this
0x18000b580  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000b585  mov     ebx, eax
0x18000b587  test    eax, eax
0x18000b589  js      loc_18000B65B
0x18000b58f  mov     rcx, r14; pbstr
0x18000b592  call    cs:__imp_SysStringLen
0x18000b598  mov     [rsp+330h+var_308], r14; unsigned __int8 *
0x18000b59d  lea     rdx, [rsp+330h+var_2C0]; unsigned __int16 *
0x18000b5a2  mov     r14d, 2
0x18000b5a8  mov     r8d, 820h; unsigned int
0x18000b5ae  mov     r9d, r14d; unsigned int
0x18000b5b1  mov     rcx, rdi; this
0x18000b5b4  lea     eax, ds:2[rax*2]
0x18000b5bb  mov     [rsp+330h+var_310], eax; unsigned int
0x18000b5bf  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000b5c4  mov     ebx, eax
0x18000b5c6  test    eax, eax
0x18000b5c8  js      loc_18000B65B
0x18000b5ce  mov     rcx, r12; pbstr
0x18000b5d1  call    cs:__imp_SysStringLen
0x18000b5d7  mov     [rsp+330h+var_308], r12; unsigned __int8 *
0x18000b5dc  lea     rdx, [rsp+330h+var_2C0]; unsigned __int16 *
0x18000b5e1  mov     r9d, r14d; unsigned int
0x18000b5e4  mov     r8d, 82Dh; unsigned int
0x18000b5ea  mov     rcx, rdi; this
0x18000b5ed  lea     eax, ds:2[rax*2]
0x18000b5f4  mov     [rsp+330h+var_310], eax; unsigned int
0x18000b5f8  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000b5fd  mov     ebx, eax
0x18000b5ff  test    eax, eax
0x18000b601  js      short loc_18000B65B
0x18000b603  mov     rcx, r13; pbstr
0x18000b606  call    cs:__imp_SysStringLen
0x18000b60c  mov     [rsp+330h+var_308], r13; unsigned __int8 *
0x18000b611  lea     rdx, [rsp+330h+var_2C0]; unsigned __int16 *
0x18000b616  mov     r9d, r14d; unsigned int
0x18000b619  mov     r8d, 81Fh; unsigned int
0x18000b61f  mov     rcx, rdi; this
0x18000b622  lea     eax, ds:2[rax*2]
0x18000b629  mov     [rsp+330h+var_310], eax; unsigned int
0x18000b62d  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000b632  mov     ebx, eax
0x18000b634  test    eax, eax
0x18000b636  js      short loc_18000B65B
0x18000b638  mov     [rsp+330h+var_308], rsi; unsigned __int8 *
0x18000b63d  lea     r9d, [r14+1]; unsigned int
0x18000b641  mov     r8d, 81Eh; unsigned int
0x18000b647  mov     [rsp+330h+var_310], r15d; unsigned int
0x18000b64c  lea     rdx, [rsp+330h+var_2C0]; unsigned __int16 *
0x18000b651  mov     rcx, rdi; this
0x18000b654  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000b659  mov     ebx, eax
0x18000b65b  mov     edx, ebx
0x18000b65d  mov     rcx, rdi; this
0x18000b660  not     edx
0x18000b662  shr     edx, 1Fh; int
0x18000b665  call    ?CloseMd@CIISDsCrMap@@QEAAJH@Z; CIISDsCrMap::CloseMd(int)
0x18000b66a  test    rsi, rsi
0x18000b66d  jz      short loc_18000B678
0x18000b66f  mov     rcx, rsi; hMem
0x18000b672  call    cs:__imp_LocalFree
0x18000b678  mov     eax, ebx
0x18000b67a  mov     rcx, [rbp+230h+var_50]
0x18000b681  xor     rcx, rsp; StackCookie
0x18000b684  call    __security_check_cookie
0x18000b689  add     rsp, 2F8h
0x18000b690  pop     r15
0x18000b692  pop     r14
0x18000b694  pop     r13
0x18000b696  pop     r12
0x18000b698  pop     rdi
0x18000b699  pop     rsi
0x18000b69a  pop     rbx
0x18000b69b  pop     rbp
0x18000b69c  retn
```
