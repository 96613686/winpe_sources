# CGenerateMSI::_AddCabinet(ushort const *,ushort const *)

- ea: `0x18002e304`
- end: `0x18002e420`
- name: `?_AddCabinet@CGenerateMSI@@QEAAJPEBG0@Z`
- size: `284`
- prototype: `__int64 __fastcall(CGenerateMSI *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002d400`

## callees

- `0x18002e304`

## import_xrefs

- `msi!__imp_MsiCloseHandle` at `0x18002e351`
- `msi!__imp_MsiCloseHandle` at `0x18002e35d`
- `msi!__imp_MsiCloseHandle` at `0x18002e3eb`
- `msi!__imp_MsiCloseHandle` at `0x18002e401`
- `msi!__imp_MsiCloseHandle` at `0x18002e351`
- `msi!__imp_MsiCloseHandle` at `0x18002e35d`
- `msi!__imp_MsiCloseHandle` at `0x18002e3eb`
- `msi!__imp_MsiCloseHandle` at `0x18002e401`
- `msi!__imp_MsiCreateRecord` at `0x18002e38a`
- `msi!__imp_MsiCreateRecord` at `0x18002e38a`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002e332`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002e332`
- `msi!__imp_MsiRecordSetStreamW` at `0x18002e3bf`
- `msi!__imp_MsiRecordSetStreamW` at `0x18002e3bf`
- `msi!__imp_MsiRecordSetStringW` at `0x18002e3ab`
- `msi!__imp_MsiRecordSetStringW` at `0x18002e3ab`
- `msi!__imp_MsiViewExecute` at `0x18002e37b`
- `msi!__imp_MsiViewExecute` at `0x18002e37b`
- `msi!__imp_MsiViewModify` at `0x18002e3d9`
- `msi!__imp_MsiViewModify` at `0x18002e3d9`

## string_xrefs

- `0x18002e39d`: `complus.cab`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CGenerateMSI::_AddCabinet(
        CGenerateMSI *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  MSIHANDLE v3; // ecx
  MSIHANDLE v5; // edi
  signed int v6; // eax
  unsigned int v7; // ebx
  bool v8; // cc
  MSIHANDLE Record; // eax
  const unsigned __int16 *hAny; // [rsp+38h] [rbp+10h] BYREF

  hAny = a2;
  v3 = *((_DWORD *)this + 16);
  LODWORD(hAny) = 0;
  v5 = 0;
  v6 = MsiDatabaseOpenViewW(v3, L"SELECT * FROM `_Streams`", (MSIHANDLE *)&hAny);
  v7 = v6;
  v8 = v6 <= 0;
  if ( !v6 )
  {
    v6 = MsiViewExecute((MSIHANDLE)hAny, 0);
    v7 = v6;
    v8 = v6 <= 0;
    if ( !v6 )
    {
      Record = MsiCreateRecord(2u);
      v5 = Record;
      if ( !Record )
      {
        v7 = -2147418113;
        goto LABEL_4;
      }
      v6 = MsiRecordSetStringW(Record, 1u, L"complus.cab");
      v7 = v6;
      v8 = v6 <= 0;
      if ( !v6 )
      {
        v6 = MsiRecordSetStreamW(v5, 2u, a3);
        v7 = v6;
        v8 = v6 <= 0;
        if ( !v6 )
        {
          v6 = MsiViewModify((MSIHANDLE)hAny, MSIMODIFY_INSERT, v5);
          v7 = v6;
          v8 = v6 <= 0;
          if ( !v6 )
          {
            v6 = MsiCloseHandle(v5);
            v5 = 0;
            v7 = v6;
            v8 = v6 <= 0;
            if ( !v6 )
            {
              v6 = MsiCloseHandle((MSIHANDLE)hAny);
              LODWORD(hAny) = 0;
              if ( !v6 )
                return v7;
              if ( v6 <= 0 )
              {
                v7 = v6;
                goto LABEL_4;
              }
              goto LABEL_3;
            }
          }
        }
      }
    }
  }
  if ( !v8 )
LABEL_3:
    v7 = (unsigned __int16)v6 | 0x80070000;
LABEL_4:
  if ( (_DWORD)hAny )
    MsiCloseHandle((MSIHANDLE)hAny);
  if ( v5 )
    MsiCloseHandle(v5);
  return v7;
}

```

## disassembly

```asm
0x18002e304  mov     rax, rsp
0x18002e307  mov     [rax+8], rbx
0x18002e30b  mov     [rax+18h], rsi
0x18002e30f  mov     [rax+10h], rdx
0x18002e313  push    rdi
0x18002e314  sub     rsp, 20h
0x18002e318  mov     ecx, [rcx+40h]; hDatabase
0x18002e31b  lea     rdx, szQuery; "SELECT * FROM `_Streams`"
0x18002e322  mov     rsi, r8
0x18002e325  mov     dword ptr [rax+10h], 0
0x18002e32c  lea     r8, [rax+10h]; phView
0x18002e330  xor     edi, edi
0x18002e332  call    cs:__imp_MsiDatabaseOpenViewW
0x18002e338  mov     ebx, eax
0x18002e33a  test    eax, eax
0x18002e33c  jz      short loc_18002E375
0x18002e33e  jle     short loc_18002E349
0x18002e340  movzx   ebx, ax
0x18002e343  or      ebx, 80070000h
0x18002e349  mov     ecx, dword ptr [rsp+28h+hAny]; hAny
0x18002e34d  test    ecx, ecx
0x18002e34f  jz      short loc_18002E357
0x18002e351  call    cs:__imp_MsiCloseHandle
0x18002e357  test    edi, edi
0x18002e359  jz      short loc_18002E363
0x18002e35b  mov     ecx, edi; hAny
0x18002e35d  call    cs:__imp_MsiCloseHandle
0x18002e363  mov     rsi, [rsp+28h+arg_10]
0x18002e368  mov     eax, ebx
0x18002e36a  mov     rbx, [rsp+28h+arg_0]
0x18002e36f  add     rsp, 20h
0x18002e373  pop     rdi
0x18002e374  retn
0x18002e375  mov     ecx, dword ptr [rsp+28h+hAny]; hView
0x18002e379  xor     edx, edx; hRecord
0x18002e37b  call    cs:__imp_MsiViewExecute
0x18002e381  mov     ebx, eax
0x18002e383  test    eax, eax
0x18002e385  jnz     short loc_18002E33E
0x18002e387  lea     ecx, [rax+2]; cParams
0x18002e38a  call    cs:__imp_MsiCreateRecord
0x18002e390  mov     edi, eax
0x18002e392  test    eax, eax
0x18002e394  jnz     short loc_18002E39D
0x18002e396  mov     ebx, 8000FFFFh
0x18002e39b  jmp     short loc_18002E349
0x18002e39d  lea     r8, szValue; "complus.cab"
0x18002e3a4  mov     edx, 1; iField
0x18002e3a9  mov     ecx, edi; hRecord
0x18002e3ab  call    cs:__imp_MsiRecordSetStringW
0x18002e3b1  mov     ebx, eax
0x18002e3b3  test    eax, eax
0x18002e3b5  jnz     short loc_18002E33E
0x18002e3b7  mov     r8, rsi; szFilePath
0x18002e3ba  lea     edx, [rax+2]; iField
0x18002e3bd  mov     ecx, edi; hRecord
0x18002e3bf  call    cs:__imp_MsiRecordSetStreamW
0x18002e3c5  mov     ebx, eax
0x18002e3c7  test    eax, eax
0x18002e3c9  jnz     loc_18002E33E
0x18002e3cf  mov     ecx, dword ptr [rsp+28h+hAny]; hView
0x18002e3d3  lea     edx, [rax+1]; eModifyMode
0x18002e3d6  mov     r8d, edi; hRecord
0x18002e3d9  call    cs:__imp_MsiViewModify
0x18002e3df  mov     ebx, eax
0x18002e3e1  test    eax, eax
0x18002e3e3  jnz     loc_18002E33E
0x18002e3e9  mov     ecx, edi; hAny
0x18002e3eb  call    cs:__imp_MsiCloseHandle
0x18002e3f1  xor     edi, edi
0x18002e3f3  mov     ebx, eax
0x18002e3f5  test    eax, eax
0x18002e3f7  jnz     loc_18002E33E
0x18002e3fd  mov     ecx, dword ptr [rsp+28h+hAny]; hAny
0x18002e401  call    cs:__imp_MsiCloseHandle
0x18002e407  mov     dword ptr [rsp+28h+hAny], ebx
0x18002e40b  test    eax, eax
0x18002e40d  jz      loc_18002E363
0x18002e413  jg      loc_18002E340
0x18002e419  mov     ebx, eax
0x18002e41b  jmp     loc_18002E349
```
