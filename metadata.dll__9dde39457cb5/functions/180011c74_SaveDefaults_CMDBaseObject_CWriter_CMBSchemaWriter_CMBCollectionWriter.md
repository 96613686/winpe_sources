# SaveDefaults(CMDBaseObject *,CWriter *,CMBSchemaWriter * *,CMBCollectionWriter * *)

- ea: `0x180011c74`
- end: `0x180011e6e`
- name: `?SaveDefaults@@YAJPEAVCMDBaseObject@@PEAVCWriter@@PEAPEAVCMBSchemaWriter@@PEAPEAVCMBCollectionWriter@@@Z`
- size: `506`
- prototype: `int(struct CMDBaseObject *, struct CWriter *, struct CMBSchemaWriter **, struct CMBCollectionWriter **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800120b4`

## callees

- `0x180004290`
- `0x180007bd0`
- `0x180011658`
- `0x180011a38`
- `0x180011c74`
- `0x18002f630`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x180011e19`
- `IisRTL!PuDbgPrintW` at `0x180011e55`
- `IisRTL!PuDbgPrintW` at `0x180011e19`
- `IisRTL!PuDbgPrintW` at `0x180011e55`

## string_xrefs

- `0x180011d31`: `IIsConfigObject`
- `0x180011e31`: `[SaveSchema] Unable to open /Schema/Properties/Defaults. GetChildObject failed with hr = 0x%x.\n`
- `0x180011e0d`: `[SaveSchema] Error while saving defaults tree. GetPropertyWriter for ID:%d failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall SaveDefaults(
        struct CMDBaseObject *a1,
        struct CWriter *a2,
        struct CMBSchemaWriter **a3,
        struct CMBCollectionWriter **a4)
{
  struct CMBSchemaWriter **v5; // rdi
  unsigned int v7; // r14d
  CMDBaseObject *ChildObject; // rax
  int CollectionWriter; // ebx
  CMDBaseObject *v10; // r15
  unsigned int *v11; // rsi
  unsigned int v12; // edx
  int MBPropertyWriter; // eax
  int v14; // eax
  struct CMBPropertyWriter *v15; // rbx
  int v16; // edi
  __int64 v17; // rax
  struct CMDBaseObject **v19; // [rsp+28h] [rbp-40h]
  int v20; // [rsp+28h] [rbp-40h]
  struct CMDBaseData **v21; // [rsp+30h] [rbp-38h]
  struct CMBPropertyWriter *v22; // [rsp+40h] [rbp-28h] BYREF
  struct CMDBaseData *v23; // [rsp+48h] [rbp-20h] BYREF
  char *v24; // [rsp+50h] [rbp-18h] BYREF

  LODWORD(v22) = 0;
  v5 = a3;
  v23 = 0;
  v24 = (char *)L"Defaults";
  v7 = 1;
  ChildObject = CMDBaseObject::GetChildObject(a1, &v24, (int *)&v22, 1);
  CollectionWriter = (int)v22;
  v10 = ChildObject;
  if ( (int)v22 >= 0 && ChildObject )
  {
    CollectionWriter = CMDBaseObject::EnumDataObject(ChildObject, 0, 0, 0, 0, 0, &v23);
    if ( CollectionWriter >= 0 )
    {
      while ( 1 )
      {
        v11 = (unsigned int *)v23;
        CollectionWriter = 0;
        if ( !v23 )
          break;
        v12 = *((_DWORD *)v23 + 2);
        v22 = 0;
        if ( (unsigned int)PropertyNotInShippedSchema(a2, v12) )
        {
          if ( !*a4 )
          {
            CollectionWriter = GetCollectionWriter(a2, v5, a4, L"IIsConfigObject", 0, 0);
            if ( CollectionWriter < 0 )
              return (unsigned int)CollectionWriter;
          }
          MBPropertyWriter = CMBCollectionWriter::GetMBPropertyWriter(*a4, v11[2], &v22);
          CollectionWriter = MBPropertyWriter;
          if ( MBPropertyWriter < 0 )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
            {
              LODWORD(v21) = MBPropertyWriter;
              LODWORD(v19) = v11[2];
              PuDbgPrintW(
                g_pDebug,
                "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
                2111,
                "SaveDefaults",
                L"[SaveSchema] Error while saving defaults tree. GetPropertyWriter for ID:%d failed with hr = 0x%x.\n",
                v19,
                v21);
            }
            return (unsigned int)CollectionWriter;
          }
          v14 = (*(__int64 (__fastcall **)(unsigned int *, __int64))(*(_QWORD *)v11 + 32LL))(v11, 1);
          v15 = v22;
          v16 = v14;
          v17 = (*(__int64 (__fastcall **)(unsigned int *, __int64))(*(_QWORD *)v11 + 24LL))(v11, 1);
          *((_DWORD *)v15 + 8) = v16;
          v5 = a3;
          *((_QWORD *)v15 + 3) = v17;
        }
        CollectionWriter = CMDBaseObject::EnumDataObject(v10, v7, 0, 0, 0, 0, &v23);
        if ( CollectionWriter < 0 )
          return (unsigned int)CollectionWriter;
        ++v7;
      }
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    v20 = (int)v22;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
      2067,
      "SaveDefaults",
      L"[SaveSchema] Unable to open /Schema/Properties/Defaults. GetChildObject failed with hr = 0x%x.\n",
      v20);
  }
  return (unsigned int)CollectionWriter;
}

```

## disassembly

```asm
0x180011c74  mov     [rsp-40h+arg_10], r8
0x180011c79  push    rbp
0x180011c7a  push    rbx
0x180011c7b  push    rsi
0x180011c7c  push    rdi
0x180011c7d  push    r12
0x180011c7f  push    r13
0x180011c81  push    r14
0x180011c83  push    r15
0x180011c85  mov     rbp, rsp
0x180011c88  sub     rsp, 68h
0x180011c8c  xor     esi, esi
0x180011c8e  lea     rax, aDefaults; "Defaults"
0x180011c95  mov     r12, r9
0x180011c98  mov     dword ptr [rbp+var_28], esi
0x180011c9b  mov     rdi, r8
0x180011c9e  mov     [rbp+var_20], rsi
0x180011ca2  mov     r13, rdx
0x180011ca5  mov     [rbp+var_18], rax
0x180011ca9  lea     r14d, [rsi+1]
0x180011cad  mov     r9d, r14d; int
0x180011cb0  lea     r8, [rbp+var_28]; int *
0x180011cb4  lea     rdx, [rbp+var_18]; char **
0x180011cb8  call    ?GetChildObject@CMDBaseObject@@QEAAPEAV1@AEAPEADPEAJH@Z; CMDBaseObject::GetChildObject(char * &,long *,int)
0x180011cbd  mov     ebx, dword ptr [rbp+var_28]
0x180011cc0  mov     r15, rax
0x180011cc3  test    ebx, ebx
0x180011cc5  js      loc_180011E21
0x180011ccb  test    rax, rax
0x180011cce  jz      loc_180011E21
0x180011cd4  lea     rax, [rbp+var_20]
0x180011cd8  xor     r9d, r9d; unsigned int
0x180011cdb  mov     [rsp+68h+var_38], rax; struct CMDBaseData **
0x180011ce0  xor     r8d, r8d; unsigned int
0x180011ce3  mov     [rsp+68h+var_40], rsi; struct CMDBaseObject **
0x180011ce8  xor     edx, edx; unsigned int
0x180011cea  mov     rcx, r15; this
0x180011ced  mov     [rsp+68h+var_48], esi; unsigned int
0x180011cf1  call    ?EnumDataObject@CMDBaseObject@@QEAAJKKKKPEAPEAV1@PEAPEAVCMDBaseData@@@Z; CMDBaseObject::EnumDataObject(ulong,ulong,ulong,ulong,CMDBaseObject * *,CMDBaseData * *)
0x180011cf6  mov     ebx, eax
0x180011cf8  test    eax, eax
0x180011cfa  js      loc_180011E5B
0x180011d00  mov     rsi, [rbp+var_20]
0x180011d04  xor     ebx, ebx
0x180011d06  test    rsi, rsi
0x180011d09  jz      loc_180011E5B
0x180011d0f  mov     edx, [rsi+8]; unsigned int
0x180011d12  mov     rcx, r13; struct CWriter *
0x180011d15  mov     [rbp+var_28], rbx
0x180011d19  call    ?PropertyNotInShippedSchema@@YAHPEAVCWriter@@K@Z; PropertyNotInShippedSchema(CWriter *,ulong)
0x180011d1e  test    eax, eax
0x180011d20  jz      loc_180011DA9
0x180011d26  cmp     [r12], rbx
0x180011d2a  jnz     short loc_180011D54
0x180011d2c  mov     [rsp+68h+var_40], rbx; unsigned __int16 *
0x180011d31  lea     r9, aIisconfigobjec; "IIsConfigObject"
0x180011d38  mov     r8, r12; struct CMBCollectionWriter **
0x180011d3b  mov     [rsp+68h+var_48], ebx; int
0x180011d3f  mov     rdx, rdi; struct CMBSchemaWriter **
0x180011d42  mov     rcx, r13; struct CWriter *
0x180011d45  call    ?GetCollectionWriter@@YAJPEAVCWriter@@PEAPEAVCMBSchemaWriter@@PEAPEAVCMBCollectionWriter@@PEBGH3@Z; GetCollectionWriter(CWriter *,CMBSchemaWriter * *,CMBCollectionWriter * *,ushort const *,int,ushort const *)
0x180011d4a  mov     ebx, eax
0x180011d4c  test    eax, eax
0x180011d4e  js      loc_180011E5B
0x180011d54  mov     edx, [rsi+8]; unsigned int
0x180011d57  lea     r8, [rbp+var_28]; struct CMBPropertyWriter **
0x180011d5b  mov     rcx, [r12]; this
0x180011d5f  call    ?GetMBPropertyWriter@CMBCollectionWriter@@QEAAJKPEAPEAVCMBPropertyWriter@@@Z; CMBCollectionWriter::GetMBPropertyWriter(ulong,CMBPropertyWriter * *)
0x180011d64  mov     ebx, eax
0x180011d66  test    eax, eax
0x180011d68  js      short loc_180011DDE
0x180011d6a  mov     rax, [rsi]
0x180011d6d  xor     r8d, r8d
0x180011d70  mov     rcx, rsi
0x180011d73  mov     rax, [rax+20h]
0x180011d77  lea     edx, [r8+1]
0x180011d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d80  mov     rbx, [rbp+var_28]
0x180011d84  mov     edi, eax
0x180011d86  mov     rax, [rsi]
0x180011d89  xor     r8d, r8d
0x180011d8c  mov     rcx, rsi
0x180011d8f  mov     rax, [rax+18h]
0x180011d93  lea     edx, [r8+1]
0x180011d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d9c  mov     [rbx+20h], edi
0x180011d9f  mov     rdi, [rbp+arg_10]
0x180011da3  mov     [rbx+18h], rax
0x180011da7  xor     ebx, ebx
0x180011da9  lea     rax, [rbp+var_20]
0x180011dad  xor     r9d, r9d; unsigned int
0x180011db0  mov     [rsp+68h+var_38], rax; struct CMDBaseData **
0x180011db5  xor     r8d, r8d; unsigned int
0x180011db8  mov     [rsp+68h+var_40], rbx; struct CMDBaseObject **
0x180011dbd  mov     edx, r14d; unsigned int
0x180011dc0  mov     rcx, r15; this
0x180011dc3  mov     [rsp+68h+var_48], ebx; unsigned int
0x180011dc7  call    ?EnumDataObject@CMDBaseObject@@QEAAJKKKKPEAPEAV1@PEAPEAVCMDBaseData@@@Z; CMDBaseObject::EnumDataObject(ulong,ulong,ulong,ulong,CMDBaseObject * *,CMDBaseData * *)
0x180011dcc  mov     ebx, eax
0x180011dce  test    eax, eax
0x180011dd0  js      loc_180011E5B
0x180011dd6  inc     r14d
0x180011dd9  jmp     loc_180011D00
0x180011dde  test    byte ptr cs:g_dwDebugFlags, 3
0x180011de5  jz      short loc_180011E5B
0x180011de7  mov     rcx, cs:g_pDebug
0x180011dee  lea     r9, aSavedefaults; "SaveDefaults"
0x180011df5  mov     dword ptr [rsp+68h+var_38], eax
0x180011df9  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x180011e00  mov     eax, [rsi+8]
0x180011e03  mov     r8d, 83Fh
0x180011e09  mov     dword ptr [rsp+68h+var_40], eax
0x180011e0d  lea     rax, aSaveschemaErro_9; "[SaveSchema] Error while saving default"...
0x180011e14  mov     qword ptr [rsp+68h+var_48], rax
0x180011e19  call    cs:__imp_PuDbgPrintW
0x180011e1f  jmp     short loc_180011E5B
0x180011e21  test    byte ptr cs:g_dwDebugFlags, 3
0x180011e28  jz      short loc_180011E5B
0x180011e2a  mov     rcx, cs:g_pDebug
0x180011e31  lea     rax, aSaveschemaUnab_2; "[SaveSchema] Unable to open /Schema/Pro"...
0x180011e38  mov     dword ptr [rsp+68h+var_40], ebx
0x180011e3c  lea     r9, aSavedefaults; "SaveDefaults"
0x180011e43  mov     r8d, 813h
0x180011e49  mov     qword ptr [rsp+68h+var_48], rax
0x180011e4e  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x180011e55  call    cs:__imp_PuDbgPrintW
0x180011e5b  mov     eax, ebx
0x180011e5d  add     rsp, 68h
0x180011e61  pop     r15
0x180011e63  pop     r14
0x180011e65  pop     r13
0x180011e67  pop     r12
0x180011e69  pop     rdi
0x180011e6a  pop     rsi
0x180011e6b  pop     rbx
0x180011e6c  pop     rbp
0x180011e6d  retn
```
