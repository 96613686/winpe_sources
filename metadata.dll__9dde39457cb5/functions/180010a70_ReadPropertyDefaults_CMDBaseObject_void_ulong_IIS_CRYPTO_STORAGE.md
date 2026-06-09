# ReadPropertyDefaults(CMDBaseObject *,void * *,ulong *,IIS_CRYPTO_STORAGE *)

- ea: `0x180010a70`
- end: `0x180010c3a`
- name: `?ReadPropertyDefaults@@YAJPEAVCMDBaseObject@@PEAPEAXPEAKPEAVIIS_CRYPTO_STORAGE@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(struct CMDBaseObject *, void **, unsigned int *, struct IIS_CRYPTO_STORAGE *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010714`

## callees

- `0x180010a70`
- `0x18002267c`
- `0x18002e70c`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x180010bd5`
- `IisRTL!PuDbgPrintW` at `0x180010c19`
- `IisRTL!PuDbgPrintW` at `0x180010bd5`
- `IisRTL!PuDbgPrintW` at `0x180010c19`

## string_xrefs

- `0x180010ba1`: `inetsrv\iis\mb\metadata\readschema.cpp`
- `0x180010bfc`: `inetsrv\iis\mb\metadata\readschema.cpp`
- `0x180010bc9`: `[ReadPropertyDefaults] Could not read property %s:%d.\npv=%d.\ncb=%d.\n`
- `0x180010b96`: `ReadPropertyDefaults`
- `0x180010bee`: `ReadPropertyDefaults`
- `0x180010c0d`: `[ReadPropertyDefaults]*pv=%d.\n`

## pseudocode

```c
__int64 __fastcall ReadPropertyDefaults(
        struct CMDBaseObject *a1,
        void **a2,
        unsigned int *a3,
        struct IIS_CRYPTO_STORAGE *a4)
{
  unsigned int *v5; // rdx
  unsigned int MetabaseType; // eax
  __int64 v7; // r8
  struct IIS_CRYPTO_STORAGE *v8; // r9
  struct CMDBaseObject *v9; // r11
  void *v10; // rcx
  unsigned int v11; // r10d
  void *v12; // rcx
  void *v13; // rcx
  __int64 *v14; // rbx
  _BYTE *v15; // rax
  unsigned int v16; // edi
  int DataObject; // r14d
  char v18; // cl
  int v20; // [rsp+20h] [rbp-79h]
  __int64 v21; // [rsp+28h] [rbp-71h]
  unsigned int v22; // [rsp+50h] [rbp-49h] BYREF
  int v23; // [rsp+54h] [rbp-45h] BYREF
  void *v24[10]; // [rsp+60h] [rbp-39h] BYREF
  unsigned int v25[12]; // [rsp+B0h] [rbp+17h] BYREF
  int v26; // [rsp+108h] [rbp+6Fh] BYREF

  v24[7] = 0;
  v5 = (unsigned int *)a2[6];
  v24[8] = 0;
  MetabaseType = GetMetabaseType(*(_DWORD *)a2[4], *v5);
  v10 = a2[2];
  v11 = MetabaseType;
  v22 = MetabaseType;
  v24[4] = (void *)L"/Schema/Properties/Defaults";
  v24[0] = v10;
  v12 = a2[13];
  v24[2] = &v26;
  v24[5] = v12;
  v13 = a2[14];
  v24[1] = &v22;
  v23 = 0;
  v26 = 0;
  v24[6] = v13;
  if ( MetabaseType == 1 )
  {
    if ( !a2[7] )
    {
      v14 = (__int64 *)&v23;
LABEL_10:
      v16 = 4;
      goto LABEL_15;
    }
    goto LABEL_14;
  }
  if ( ((MetabaseType - 2) & 0xFFFFFFFC) != 0 || MetabaseType == 3 || (v15 = a2[7]) != 0 && *v15 )
  {
LABEL_14:
    v14 = (__int64 *)a2[7];
    v16 = *(_DWORD *)(v7 + 28);
    goto LABEL_15;
  }
  if ( v11 == 5 )
  {
    v14 = &qword_180040F50;
    goto LABEL_10;
  }
  if ( ((v11 - 2) & 0xFFFFFFFD) != 0 )
  {
    v14 = 0;
    v16 = 0;
  }
  else
  {
    v14 = (__int64 *)&qword_18003A6B0;
    v16 = 2;
  }
LABEL_15:
  v24[3] = v14;
  v25[3] = v16;
  DataObject = ReadDataObject(v9, v24, v25, v8, v20);
  if ( DataObject < 0 )
  {
    v18 = g_dwDebugFlags;
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\readschema.cpp",
        1352,
        "ReadPropertyDefaults",
        L"[ReadPropertyDefaults] Could not read property %s:%d.\npv=%d.\ncb=%d.\n",
        a2[2],
        *(_DWORD *)a2[13],
        v14,
        v16);
      v18 = g_dwDebugFlags;
    }
    if ( v14 && (v18 & 3) != 0 )
    {
      LODWORD(v21) = *(unsigned __int16 *)v14;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\readschema.cpp",
        1358,
        "ReadPropertyDefaults",
        L"[ReadPropertyDefaults]*pv=%d.\n",
        v21);
    }
  }
  return (unsigned int)DataObject;
}

```

## disassembly

```asm
0x180010a70  mov     [rsp-8+arg_0], rbx
0x180010a75  mov     [rsp-8+arg_10], rsi
0x180010a7a  push    rbp
0x180010a7b  push    rdi
0x180010a7c  push    r14
0x180010a7e  lea     rbp, [rsp-47h]
0x180010a83  sub     rsp, 0E0h
0x180010a8a  mov     rsi, rdx
0x180010a8d  mov     [rbp+57h+var_58], 0
0x180010a95  mov     rdx, [rdx+30h]
0x180010a99  mov     r11, rcx
0x180010a9c  mov     [rbp+57h+var_50], 0
0x180010aa4  mov     rcx, [rsi+20h]
0x180010aa8  mov     edx, [rdx]; unsigned int
0x180010aaa  mov     ecx, [rcx]; unsigned int
0x180010aac  call    ?GetMetabaseType@@YAKKK@Z; GetMetabaseType(ulong,ulong)
0x180010ab1  mov     rcx, [rsi+10h]
0x180010ab5  mov     r10d, eax
0x180010ab8  mov     [rbp+57h+var_A0], eax
0x180010abb  lea     rax, aSchemaProperti_2; "/Schema/Properties/Defaults"
0x180010ac2  mov     [rbp+57h+var_70], rax
0x180010ac6  lea     rax, [rbp+57h+arg_8]
0x180010aca  mov     [rbp+57h+var_90], rcx
0x180010ace  mov     rcx, [rsi+68h]
0x180010ad2  mov     [rbp+57h+var_80], rax
0x180010ad6  lea     rax, [rbp+57h+var_A0]
0x180010ada  mov     [rbp+57h+var_68], rcx
0x180010ade  mov     rcx, [rsi+70h]
0x180010ae2  mov     [rbp+57h+var_88], rax
0x180010ae6  mov     [rbp+57h+var_9C], 0
0x180010aed  mov     [rbp+57h+arg_8], 0
0x180010af4  mov     [rbp+57h+var_60], rcx
0x180010af8  cmp     r10d, 1
0x180010afc  jnz     short loc_180010B0B
0x180010afe  cmp     qword ptr [rsi+38h], 0
0x180010b03  jnz     short loc_180010B5D
0x180010b05  lea     rbx, [rbp+57h+var_9C]
0x180010b09  jmp     short loc_180010B37
0x180010b0b  lea     eax, [r10-2]
0x180010b0f  test    eax, 0FFFFFFFCh
0x180010b14  jnz     short loc_180010B5D
0x180010b16  cmp     r10d, 3
0x180010b1a  jz      short loc_180010B5D
0x180010b1c  mov     rax, [rsi+38h]
0x180010b20  test    rax, rax
0x180010b23  jz      short loc_180010B2A
0x180010b25  cmp     byte ptr [rax], 0
0x180010b28  jnz     short loc_180010B5D
0x180010b2a  cmp     r10d, 5
0x180010b2e  jnz     short loc_180010B3E
0x180010b30  lea     rbx, qword_180040F50
0x180010b37  mov     edi, 4
0x180010b3c  jmp     short loc_180010B65
0x180010b3e  lea     eax, [r10-2]
0x180010b42  test    eax, 0FFFFFFFDh
0x180010b47  jnz     short loc_180010B57
0x180010b49  lea     rbx, qword_18003A6B0
0x180010b50  mov     edi, 2
0x180010b55  jmp     short loc_180010B65
0x180010b57  xor     ebx, ebx
0x180010b59  xor     edi, edi
0x180010b5b  jmp     short loc_180010B65
0x180010b5d  mov     rbx, [rsi+38h]
0x180010b61  mov     edi, [r8+1Ch]
0x180010b65  lea     r8, [rbp+57h+var_40]; unsigned int *
0x180010b69  mov     [rbp+57h+var_78], rbx
0x180010b6d  lea     rdx, [rbp+57h+var_90]; void **
0x180010b71  mov     [rbp+57h+var_34], edi
0x180010b74  mov     rcx, r11; this
0x180010b77  call    ?ReadDataObject@@YAJPEAVCMDBaseObject@@PEAPEAXPEAKPEAVIIS_CRYPTO_STORAGE@@H@Z; ReadDataObject(CMDBaseObject *,void * *,ulong *,IIS_CRYPTO_STORAGE *,int)
0x180010b7c  mov     r14d, eax
0x180010b7f  test    eax, eax
0x180010b81  jns     loc_180010C1F
0x180010b87  mov     ecx, cs:g_dwDebugFlags
0x180010b8d  test    cl, 3
0x180010b90  jz      short loc_180010BE1
0x180010b92  mov     rcx, [rsi+68h]
0x180010b96  lea     r9, aReadpropertyde_0; "ReadPropertyDefaults"
0x180010b9d  mov     rax, [rsi+10h]
0x180010ba1  lea     rdx, aInetsrvIisMbMe_0; "inetsrv\\iis\\mb\\metadata\\readschema."...
0x180010ba8  mov     [rsp+0F0h+var_B0], edi
0x180010bac  mov     r8d, 548h
0x180010bb2  mov     [rsp+0F0h+var_B8], rbx
0x180010bb7  mov     ecx, [rcx]
0x180010bb9  mov     [rsp+0F0h+var_C0], ecx
0x180010bbd  mov     rcx, cs:g_pDebug
0x180010bc4  mov     [rsp+0F0h+var_C8], rax
0x180010bc9  lea     rax, aReadpropertyde_1; "[ReadPropertyDefaults] Could not read p"...
0x180010bd0  mov     [rsp+0F0h+var_D0], rax
0x180010bd5  call    cs:__imp_PuDbgPrintW
0x180010bdb  mov     ecx, cs:g_dwDebugFlags
0x180010be1  test    rbx, rbx
0x180010be4  jz      short loc_180010C1F
0x180010be6  test    cl, 3
0x180010be9  jz      short loc_180010C1F
0x180010beb  movzx   eax, word ptr [rbx]
0x180010bee  lea     r9, aReadpropertyde_0; "ReadPropertyDefaults"
0x180010bf5  mov     rcx, cs:g_pDebug
0x180010bfc  lea     rdx, aInetsrvIisMbMe_0; "inetsrv\\iis\\mb\\metadata\\readschema."...
0x180010c03  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180010c07  mov     r8d, 54Eh
0x180010c0d  lea     rax, aReadpropertyde; "[ReadPropertyDefaults]*pv=%d.\n"
0x180010c14  mov     [rsp+0F0h+var_D0], rax
0x180010c19  call    cs:__imp_PuDbgPrintW
0x180010c1f  lea     r11, [rsp+0F0h+var_10]
0x180010c27  mov     eax, r14d
0x180010c2a  mov     rbx, [r11+20h]
0x180010c2e  mov     rsi, [r11+30h]
0x180010c32  mov     rsp, r11
0x180010c35  pop     r14
0x180010c37  pop     rdi
0x180010c38  pop     rbp
0x180010c39  retn
```
