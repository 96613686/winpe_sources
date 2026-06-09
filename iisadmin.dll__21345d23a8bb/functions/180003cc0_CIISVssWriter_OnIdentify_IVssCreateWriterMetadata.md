# CIISVssWriter::OnIdentify(IVssCreateWriterMetadata *)

- ea: `0x180003cc0`
- end: `0x180003e71`
- name: `?OnIdentify@CIISVssWriter@@UEAA_NPEAVIVssCreateWriterMetadata@@@Z`
- size: `433`
- prototype: `bool __fastcall(CIISVssWriter *__hidden this, struct IVssCreateWriterMetadata *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003cc0`
- `0x180005010`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180003e57`
- `IisRTL!PuDbgPrint` at `0x180003e57`

## string_xrefs

- `0x180003e4b`: `inetsrv\iis\mb\iisadmin\mdwriter.cxx`
- `0x180003d2c`: `Error AddComponent().  hr = %x\n`
- `0x180003e44`: `CIISVssWriter::OnIdentify`
- `0x180003d3b`: `MetaBase.XML`
- `0x180003d4a`: `%windir%\system32\inetsrv`
- `0x180003dae`: `%windir%\system32\inetsrv`
- `0x180003d9f`: `MBSchema.XML`

## pseudocode

```c
char __fastcall CIISVssWriter::OnIdentify(CIISVssWriter *this, struct IVssCreateWriterMetadata *a2)
{
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  __int64 v8; // [rsp+28h] [rbp-50h]
  __int64 v9; // [rsp+28h] [rbp-50h]
  __int64 v10; // [rsp+28h] [rbp-50h]
  char v11; // [rsp+38h] [rbp-40h]
  __int64 v12; // [rsp+38h] [rbp-40h]
  __int64 v13; // [rsp+38h] [rbp-40h]
  char v14; // [rsp+40h] [rbp-38h]
  char v15; // [rsp+48h] [rbp-30h]
  char v16; // [rsp+50h] [rbp-28h]

  v16 = 0;
  v15 = 0;
  v14 = 0;
  v11 = 0;
  v3 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, _QWORD, const wchar_t *, _QWORD, _QWORD, _DWORD, char, char, char, char, _DWORD))(*(_QWORD *)a2 + 16LL))(
         a2,
         2,
         0,
         L"IISMETABASE",
         0,
         0,
         0,
         v11,
         v14,
         v15,
         v16,
         0);
  if ( v3 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v8) = v3;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\iisadmin\\mdwriter.cxx",
        162,
        "CIISVssWriter::OnIdentify",
        "Error AddComponent().  hr = %x\n",
        v8);
    }
    return 0;
  }
  LODWORD(v12) = 3855;
  LOBYTE(v8) = 0;
  v4 = (*(__int64 (**)(struct IVssCreateWriterMetadata *, _QWORD, const wchar_t *, const wchar_t *, ...))(*(_QWORD *)a2 + 40LL))(
         a2,
         0,
         L"IISMETABASE",
         L"%windir%\\system32\\inetsrv",
         L"MetaBase.XML",
         v8,
         0,
         v12);
  if ( v4 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v9) = v4;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\iisadmin\\mdwriter.cxx",
        177,
        "CIISVssWriter::OnIdentify",
        "Error AddFilesToFileGroup().  hr = %x\n",
        v9);
    }
    return 0;
  }
  LODWORD(v13) = 3855;
  LOBYTE(v9) = 0;
  v5 = (*(__int64 (**)(struct IVssCreateWriterMetadata *, _QWORD, const wchar_t *, const wchar_t *, ...))(*(_QWORD *)a2 + 40LL))(
         a2,
         0,
         L"IISMETABASE",
         L"%windir%\\system32\\inetsrv",
         L"MBSchema.XML",
         v9,
         0,
         v13);
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v10) = v5;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\iisadmin\\mdwriter.cxx",
        192,
        "CIISVssWriter::OnIdentify",
        "Error AddFilesToFileGroup().  hr = %x\n",
        v10);
    }
    return 0;
  }
  v6 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, _QWORD))(*(_QWORD *)a2 + 48LL))(a2, 6, 0);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v10) = v6;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\iisadmin\\mdwriter.cxx",
        208,
        "CIISVssWriter::OnIdentify",
        "Error setting restore method.  hr = %x\n",
        v10);
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180003cc0  mov     [rsp+arg_0], rbx
0x180003cc5  push    rdi
0x180003cc6  sub     rsp, 70h
0x180003cca  mov     rax, [rdx]
0x180003ccd  lea     r9, aIismetabase; "IISMETABASE"
0x180003cd4  xor     edi, edi
0x180003cd6  mov     rbx, rdx
0x180003cd9  mov     [rsp+78h+var_20], edi
0x180003cdd  xor     r8d, r8d
0x180003ce0  mov     [rsp+78h+var_28], dil
0x180003ce5  mov     rcx, rbx
0x180003ce8  mov     rax, [rax+10h]
0x180003cec  mov     [rsp+78h+var_30], dil
0x180003cf1  lea     edx, [rdi+2]
0x180003cf4  mov     [rsp+78h+var_38], dil
0x180003cf9  mov     byte ptr [rsp+78h+var_40], dil
0x180003cfe  mov     dword ptr [rsp+78h+var_48], edi
0x180003d02  mov     [rsp+78h+var_50], rdi
0x180003d07  mov     [rsp+78h+var_58], rdi
0x180003d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d11  test    eax, eax
0x180003d13  jns     short loc_180003D38
0x180003d15  test    byte ptr cs:g_dwDebugFlags, 3
0x180003d1c  jz      loc_180003E5D
0x180003d22  mov     dword ptr [rsp+78h+var_50], eax
0x180003d26  mov     r8d, 0A2h
0x180003d2c  lea     rax, aErrorAddcompon; "Error AddComponent().  hr = %x\n"
0x180003d33  jmp     loc_180003E3D
0x180003d38  mov     rax, [rbx]
0x180003d3b  lea     rcx, aMetabaseXml; "MetaBase.XML"
0x180003d42  mov     dword ptr [rsp+78h+var_40], 0F0Fh
0x180003d4a  lea     r9, aWindirSystem32; "%windir%\\system32\\inetsrv"
0x180003d51  mov     [rsp+78h+var_48], rdi
0x180003d56  lea     r8, aIismetabase; "IISMETABASE"
0x180003d5d  mov     byte ptr [rsp+78h+var_50], dil
0x180003d62  xor     edx, edx
0x180003d64  mov     rax, [rax+28h]
0x180003d68  mov     [rsp+78h+var_58], rcx
0x180003d6d  mov     rcx, rbx
0x180003d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d75  test    eax, eax
0x180003d77  jns     short loc_180003D9C
0x180003d79  test    byte ptr cs:g_dwDebugFlags, 3
0x180003d80  jz      loc_180003E5D
0x180003d86  mov     dword ptr [rsp+78h+var_50], eax
0x180003d8a  mov     r8d, 0B1h
0x180003d90  lea     rax, aErrorAddfilest; "Error AddFilesToFileGroup().  hr = %x\n"
0x180003d97  jmp     loc_180003E3D
0x180003d9c  mov     rax, [rbx]
0x180003d9f  lea     rcx, aMbschemaXml; "MBSchema.XML"
0x180003da6  mov     dword ptr [rsp+78h+var_40], 0F0Fh
0x180003dae  lea     r9, aWindirSystem32; "%windir%\\system32\\inetsrv"
0x180003db5  mov     [rsp+78h+var_48], rdi
0x180003dba  lea     r8, aIismetabase; "IISMETABASE"
0x180003dc1  mov     byte ptr [rsp+78h+var_50], dil
0x180003dc6  xor     edx, edx
0x180003dc8  mov     rax, [rax+28h]
0x180003dcc  mov     [rsp+78h+var_58], rcx
0x180003dd1  mov     rcx, rbx
0x180003dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dd9  test    eax, eax
0x180003ddb  jns     short loc_180003DF9
0x180003ddd  test    byte ptr cs:g_dwDebugFlags, 3
0x180003de4  jz      short loc_180003E5D
0x180003de6  mov     dword ptr [rsp+78h+var_50], eax
0x180003dea  mov     r8d, 0C0h
0x180003df0  lea     rax, aErrorAddfilest; "Error AddFilesToFileGroup().  hr = %x\n"
0x180003df7  jmp     short loc_180003E3D
0x180003df9  mov     rax, [rbx]
0x180003dfc  xor     r9d, r9d
0x180003dff  mov     byte ptr [rsp+78h+var_50], 1
0x180003e04  xor     r8d, r8d
0x180003e07  mov     rcx, rbx
0x180003e0a  mov     dword ptr [rsp+78h+var_58], 1
0x180003e12  mov     rax, [rax+30h]
0x180003e16  lea     edx, [r9+6]
0x180003e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e1f  test    eax, eax
0x180003e21  jns     short loc_180003E61
0x180003e23  test    byte ptr cs:g_dwDebugFlags, 3
0x180003e2a  jz      short loc_180003E5D
0x180003e2c  mov     dword ptr [rsp+78h+var_50], eax
0x180003e30  mov     r8d, 0D0h
0x180003e36  lea     rax, aErrorSettingRe; "Error setting restore method.  hr = %x"...
0x180003e3d  mov     rcx, cs:g_pDebug
0x180003e44  lea     r9, aCiisvsswriterO; "CIISVssWriter::OnIdentify"
0x180003e4b  lea     rdx, aInetsrvIisMbIi; "inetsrv\\iis\\mb\\iisadmin\\mdwriter.cx"...
0x180003e52  mov     [rsp+78h+var_58], rax
0x180003e57  call    cs:__imp_PuDbgPrint
0x180003e5d  xor     al, al
0x180003e5f  jmp     short loc_180003E63
0x180003e61  mov     al, 1
0x180003e63  mov     rbx, [rsp+78h+arg_0]
0x180003e6b  add     rsp, 70h
0x180003e6f  pop     rdi
0x180003e70  retn
```
