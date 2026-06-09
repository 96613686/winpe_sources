# CImporter::DoIt(ushort *,ushort const *,ulong,CMDBaseObject * *)

- ea: `0x180012ec0`
- end: `0x1800132ad`
- name: `?DoIt@CImporter@@QEAAJPEAGPEBGKPEAPEAVCMDBaseObject@@@Z`
- size: `1005`
- prototype: `__int64 __fastcall(CImporter *__hidden this, unsigned __int16 *, const unsigned __int16 *, unsigned int, struct CMDBaseObject **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180022dac`

## callees

- `0x180009bd0`
- `0x180012ec0`
- `0x1800136e0`
- `0x180013790`
- `0x180014f60`
- `0x18001f2c8`
- `0x18002267c`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180013054`
- `msvcrt!_wcsnicmp` at `0x180013054`
- `msvcrt!_wcsicmp` at `0x180013148`
- `msvcrt!_wcsicmp` at `0x180013148`
- `IisRTL!?IsValid@STRAU@@QEAAHXZ` at `0x180012f60`
- `IisRTL!?IsValid@STRAU@@QEAAHXZ` at `0x180012f60`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180012f36`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180012f36`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180012f10`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180012f10`
- `IisRTL!PuDbgPrintW` at `0x180013263`
- `IisRTL!PuDbgPrintW` at `0x180013263`

## string_xrefs

- `0x180013253`: `[ReadSomeDataFromXML] GetColumnValues failed with hr = 0x%x. Table:%s. Read row index:%d.\n`

## pseudocode

```c
__int64 __fastcall CImporter::DoIt(
        CImporter *this,
        unsigned __int16 *a2,
        wchar_t *a3,
        int a4,
        struct CMDBaseObject **a5)
{
  CImporter *v5; // r12
  int v6; // edi
  int inited; // ebx
  unsigned int v8; // edx
  struct CMDBaseObject *BaseObject; // rax
  wchar_t *v10; // rsi
  int v11; // r14d
  __int64 i; // rdx
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  int v16; // ecx
  BOOL v17; // r12d
  unsigned __int64 v18; // rcx
  int v19; // ebx
  unsigned __int16 *v20; // r14
  CImporter *v21; // rcx
  _DWORD *v22; // rax
  _BYTE *v23; // rax
  unsigned int *v25; // [rsp+20h] [rbp-C1h]
  void **v26; // [rsp+28h] [rbp-B9h]
  unsigned int v27; // [rsp+40h] [rbp-A1h]
  int v29; // [rsp+50h] [rbp-91h] BYREF
  int v30; // [rsp+54h] [rbp-8Dh]
  int v31; // [rsp+58h] [rbp-89h]
  int v32; // [rsp+5Ch] [rbp-85h]
  IIS_CRYPTO_STORAGE *v33; // [rsp+60h] [rbp-81h] BYREF
  struct CMDBaseObject *v34; // [rsp+68h] [rbp-79h] BYREF
  unsigned __int16 *v35; // [rsp+70h] [rbp-71h]
  wchar_t *String2; // [rsp+78h] [rbp-69h]
  void *v37[2]; // [rsp+80h] [rbp-61h] BYREF
  _BYTE *v38; // [rsp+90h] [rbp-51h]
  wchar_t *v39; // [rsp+98h] [rbp-49h]
  wchar_t *String1; // [rsp+A0h] [rbp-41h]
  _DWORD *v41; // [rsp+A8h] [rbp-39h]
  unsigned int *v42; // [rsp+B8h] [rbp-29h]
  _DWORD *v43; // [rsp+C0h] [rbp-21h]
  unsigned int v44[10]; // [rsp+D0h] [rbp-11h] BYREF

  v5 = this;
  v6 = 0;
  v34 = 0;
  v33 = 0;
  v30 = a4;
  String2 = a3;
  v35 = a2;
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
  inited = InitSessionKey(*((struct ISimpleTableRead2 **)v5 + 1), &v33, *((char **)v5 + 5), 0);
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
  if ( inited < 0 )
  {
LABEL_50:
    if ( *a5 )
    {
      (**(void (__fastcall ***)(_QWORD, __int64))*a5)(*a5, 1);
      *a5 = 0;
    }
    goto LABEL_52;
  }
  BaseObject = CMDBaseObject::CreateBaseObject(L"Thenamedoesntmatter");
  *a5 = BaseObject;
  if ( !BaseObject || !STRAU::IsValid((struct CMDBaseObject *)((char *)BaseObject + 8)) )
  {
    inited = -2147024882;
    if ( *a5 )
      (**(void (__fastcall ***)(_QWORD, __int64))*a5)(*a5, 1);
    goto LABEL_50;
  }
  v32 = 0;
  v10 = 0;
  memset_0(v37, 0, 0x48u);
  v11 = 3;
  v27 = -1;
  for ( i = 0; ; i = (unsigned int)(v31 + 1) )
  {
    v13 = *((_QWORD *)v5 + 1);
    v26 = v37;
    v31 = i;
    v25 = v44;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v13 + 32LL))(v13, i, 9);
    inited = v14;
    if ( v14 == -2145318890 )
      break;
    if ( v14 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v26) = v14;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\importer.cpp",
          227,
          "CImporter::DoIt",
          L"[ReadSomeDataFromXML] GetColumnValues failed with hr = 0x%x. Table:%s. Read row index:%d.\n",
          v26,
          L"MBProperty",
          v31);
      }
      goto LABEL_50;
    }
    v15 = *String1;
    v16 = 46 - v15;
    if ( v15 == 46 )
      v16 = -String1[1];
    if ( v16 )
    {
      v17 = 1;
      if ( *v41 == 9989 )
        v17 = *(_WORD *)v37[0] != 35;
      v18 = v27;
      if ( v27 == *v42 )
      {
        if ( v6 )
          goto LABEL_55;
        v22 = v43;
        v19 = 0;
        goto LABEL_34;
      }
      v19 = 1;
      v27 = *v42;
      v6 = 0;
      v10 = String1;
      v34 = *a5;
      if ( *v43 == 65 && !_wcsnicmp(String1, L"inherited:", 0xAu) )
        v10 += 10;
      v20 = v35;
      v29 = 0;
      if ( !CImporter::IsChild((CImporter *)v18, v35, v10, &v29) )
      {
        if ( !CImporter::IsChild(v21, v10, v20, &v29) )
        {
          v11 = 3;
          goto LABEL_22;
        }
        v11 = 2;
        goto LABEL_27;
      }
      v11 = v29 == 0;
      v18 = v29 == 0;
      if ( !v29 )
      {
        v18 = (unsigned int)(v18 - 1);
        if ( (_DWORD)v18 )
        {
          if ( (_DWORD)v18 != 1 )
            goto LABEL_22;
LABEL_27:
          if ( (v30 & 1) == 0 )
            goto LABEL_22;
        }
        else if ( (v30 & 2) != 0 )
        {
          goto LABEL_22;
        }
        v22 = v43;
        if ( *v43 == 65 )
        {
LABEL_29:
          if ( (v30 & 1) == 0 )
          {
LABEL_22:
            v6 = 1;
LABEL_55:
            v5 = this;
            continue;
          }
LABEL_34:
          if ( *v22 == 65 )
          {
            v23 = v38;
            if ( (*v38 & 1) == 0 )
              goto LABEL_55;
LABEL_43:
            if ( v11 == 2 && (*v23 & 1) == 0 )
              goto LABEL_55;
LABEL_45:
            if ( v19 )
            {
              if ( v11 != 2 )
              {
                inited = CImporter::ReadMetaObject((CImporter *)v18, v35, *a5, v10, &v34);
                if ( inited < 0 )
                  goto LABEL_50;
              }
            }
            if ( v17 )
            {
              inited = ReadDataObject(v34, v37, v44, v33, (int)v25);
              if ( inited < 0 )
                goto LABEL_50;
            }
            goto LABEL_55;
          }
        }
        if ( !v11 )
        {
LABEL_38:
          if ( *v41 != 1002 )
            goto LABEL_45;
          v18 = (unsigned __int64)v39;
          if ( !v39 || !*String2 )
            goto LABEL_45;
          if ( _wcsicmp(v39, String2) )
          {
            inited = -2147023727;
            goto LABEL_50;
          }
        }
        v23 = v38;
        goto LABEL_43;
      }
      v22 = v43;
      if ( *v43 == 65 )
        goto LABEL_29;
      v32 = 1;
      goto LABEL_38;
    }
  }
  if ( !v32 )
  {
    inited = -2147024893;
    goto LABEL_50;
  }
  inited = 0;
LABEL_52:
  if ( v33 )
    IIS_CRYPTO_STORAGE::`scalar deleting destructor'(v33, v8);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180012ec0  push    rbp
0x180012ec2  push    rbx
0x180012ec3  push    rsi
0x180012ec4  push    rdi
0x180012ec5  push    r12
0x180012ec7  push    r14
0x180012ec9  push    r15
0x180012ecb  lea     rbp, [rsp-1Fh]
0x180012ed0  sub     rsp, 100h
0x180012ed7  mov     rax, cs:__security_cookie
0x180012ede  xor     rax, rsp
0x180012ee1  mov     [rbp+4Fh+var_38], rax
0x180012ee5  mov     r15, [rbp+4Fh+arg_20]
0x180012ee9  mov     r12, rcx
0x180012eec  mov     [rsp+130h+var_E8], rcx
0x180012ef1  xor     edi, edi
0x180012ef3  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180012efa  mov     [rbp+4Fh+var_C8], rdi
0x180012efe  mov     [rsp+130h+var_D0], rdi
0x180012f03  mov     [rsp+130h+var_DC], r9d
0x180012f08  mov     [rbp+4Fh+String2], r8
0x180012f0c  mov     [rbp+4Fh+var_C0], rdx
0x180012f10  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180012f16  mov     r8, [r12+28h]; char *
0x180012f1b  lea     rdx, [rsp+130h+var_D0]; struct IIS_CRYPTO_STORAGE **
0x180012f20  mov     rcx, [r12+8]; struct ISimpleTableRead2 *
0x180012f25  xor     r9d, r9d; int
0x180012f28  call    ?InitSessionKey@@YAJPEAUISimpleTableRead2@@PEAPEAVIIS_CRYPTO_STORAGE@@PEADH@Z; InitSessionKey(ISimpleTableRead2 *,IIS_CRYPTO_STORAGE * *,char *,int)
0x180012f2d  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180012f34  mov     ebx, eax
0x180012f36  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180012f3c  test    ebx, ebx
0x180012f3e  js      loc_1800131B4
0x180012f44  lea     rcx, aThenamedoesntm; "Thenamedoesntmatter"
0x180012f4b  call    ?CreateBaseObject@CMDBaseObject@@SAPEAV1@PEAG@Z; CMDBaseObject::CreateBaseObject(ushort *)
0x180012f50  mov     [r15], rax
0x180012f53  test    rax, rax
0x180012f56  jz      loc_180013287
0x180012f5c  lea     rcx, [rax+8]
0x180012f60  call    cs:__imp_?IsValid@STRAU@@QEAAHXZ; STRAU::IsValid(void)
0x180012f66  test    eax, eax
0x180012f68  jz      loc_180013287
0x180012f6e  xor     edx, edx; Val
0x180012f70  mov     [rsp+130h+var_D4], edi
0x180012f74  lea     r8d, [rdi+48h]; Size
0x180012f78  mov     esi, edi
0x180012f7a  lea     rcx, [rbp+4Fh+var_B0]; void *
0x180012f7e  call    memset_0
0x180012f83  or      eax, 0FFFFFFFFh
0x180012f86  lea     r14d, [rdi+3]
0x180012f8a  mov     [rsp+130h+var_F0], eax
0x180012f8e  xor     edx, edx
0x180012f90  mov     rcx, [r12+8]
0x180012f95  lea     r8, [rbp+4Fh+var_B0]
0x180012f99  mov     [rsp+130h+var_108], r8
0x180012f9e  xor     r9d, r9d
0x180012fa1  lea     r8, [rbp+4Fh+var_60]
0x180012fa5  mov     [rsp+130h+var_D8], edx
0x180012fa9  mov     [rsp+130h+var_110], r8
0x180012fae  mov     rax, [rcx]
0x180012fb1  lea     r8d, [r9+9]
0x180012fb5  mov     rax, [rax+20h]
0x180012fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fbe  mov     ebx, eax
0x180012fc0  cmp     eax, 80210816h
0x180012fc5  jz      loc_18001326E
0x180012fcb  xor     r8d, r8d
0x180012fce  test    eax, eax
0x180012fd0  js      loc_18001321B
0x180012fd6  mov     rdx, [rbp+4Fh+String1]
0x180012fda  lea     ecx, [r8+2Eh]
0x180012fde  movzx   eax, word ptr [rdx]
0x180012fe1  sub     ecx, eax
0x180012fe3  jnz     short loc_180012FEF
0x180012fe5  movzx   eax, word ptr [rdx+2]
0x180012fe9  movzx   ecx, r8w
0x180012fed  sub     ecx, eax
0x180012fef  test    ecx, ecx
0x180012ff1  jz      loc_180013209
0x180012ff7  mov     rax, [rbp+4Fh+var_88]
0x180012ffb  mov     r12d, 1
0x180013001  cmp     dword ptr [rax], 2705h
0x180013007  jnz     short loc_180013015
0x180013009  mov     rax, [rbp+4Fh+var_B0]
0x18001300d  cmp     word ptr [rax], 23h ; '#'
0x180013011  cmovz   r12d, r8d
0x180013015  mov     rax, [rbp+4Fh+var_78]
0x180013019  mov     ecx, [rsp+130h+var_F0]
0x18001301d  cmp     ecx, [rax]
0x18001301f  jz      loc_1800130FA
0x180013025  mov     eax, [rax]
0x180013027  mov     ebx, 1
0x18001302c  mov     [rsp+130h+var_F0], eax
0x180013030  mov     edi, r8d
0x180013033  mov     rax, [r15]
0x180013036  mov     rsi, rdx
0x180013039  mov     [rbp+4Fh+var_C8], rax
0x18001303d  mov     rax, [rbp+4Fh+var_70]
0x180013041  cmp     dword ptr [rax], 41h ; 'A'
0x180013044  jnz     short loc_180013065
0x180013046  lea     r8d, [rbx+9]; MaxCount
0x18001304a  mov     rcx, rsi; String1
0x18001304d  lea     rdx, ?sm_wszInheritedPropertiesLocationPrefix@CImporter@@2QBGB; "inherited:"
0x180013054  call    cs:__imp__wcsnicmp
0x18001305a  xor     r8d, r8d
0x18001305d  test    eax, eax
0x18001305f  jnz     short loc_180013065
0x180013061  add     rsi, 14h
0x180013065  mov     r14, [rbp+4Fh+var_C0]
0x180013069  lea     r9, [rsp+130h+var_E0]; int *
0x18001306e  mov     [rsp+130h+var_E0], r8d
0x180013073  mov     rdx, r14; unsigned __int16 *
0x180013076  mov     r8, rsi; unsigned __int16 *
0x180013079  call    ?IsChild@CImporter@@AEAAHPEBG0PEAH@Z; CImporter::IsChild(ushort const *,ushort const *,int *)
0x18001307e  xor     r8d, r8d
0x180013081  test    eax, eax
0x180013083  jz      short loc_1800130C0
0x180013085  cmp     [rsp+130h+var_E0], r8d
0x18001308a  mov     r14d, r8d
0x18001308d  setz    r14b
0x180013091  mov     ecx, r14d
0x180013094  test    r14d, r14d
0x180013097  jz      short loc_1800130B1
0x180013099  sub     ecx, ebx
0x18001309b  jz      short loc_1800130A3
0x18001309d  cmp     ecx, ebx
0x18001309f  jz      short loc_1800130DB
0x1800130a1  jmp     short loc_1800130AA
0x1800130a3  test    byte ptr [rsp+130h+var_DC], 2
0x1800130a8  jz      short loc_1800130E1
0x1800130aa  mov     edi, ebx
0x1800130ac  jmp     loc_180013204
0x1800130b1  mov     rax, [rbp+4Fh+var_70]
0x1800130b5  cmp     dword ptr [rax], 41h ; 'A'
0x1800130b8  jz      short loc_1800130EA
0x1800130ba  mov     [rsp+130h+var_D4], ebx
0x1800130be  jmp     short loc_180013126
0x1800130c0  lea     r9, [rsp+130h+var_E0]; int *
0x1800130c5  mov     r8, r14; unsigned __int16 *
0x1800130c8  mov     rdx, rsi; unsigned __int16 *
0x1800130cb  call    ?IsChild@CImporter@@AEAAHPEBG0PEAH@Z; CImporter::IsChild(ushort const *,ushort const *,int *)
0x1800130d0  xor     r8d, r8d
0x1800130d3  test    eax, eax
0x1800130d5  jz      short loc_1800130F2
0x1800130d7  lea     r14d, [r8+2]
0x1800130db  test    byte ptr [rsp+130h+var_DC], bl
0x1800130df  jz      short loc_1800130AA
0x1800130e1  mov     rax, [rbp+4Fh+var_70]
0x1800130e5  cmp     dword ptr [rax], 41h ; 'A'
0x1800130e8  jnz     short loc_180013121
0x1800130ea  test    byte ptr [rsp+130h+var_DC], bl
0x1800130ee  jnz     short loc_18001310D
0x1800130f0  jmp     short loc_1800130AA
0x1800130f2  mov     r14d, 3
0x1800130f8  jmp     short loc_1800130AA
0x1800130fa  mov     [rsp+130h+var_F0], ecx
0x1800130fe  test    edi, edi
0x180013100  jnz     loc_180013200
0x180013106  mov     rax, [rbp+4Fh+var_70]
0x18001310a  mov     ebx, r8d
0x18001310d  cmp     dword ptr [rax], 41h ; 'A'
0x180013110  jnz     short loc_180013121
0x180013112  mov     rax, [rbp+4Fh+var_A0]
0x180013116  test    byte ptr [rax], 1
0x180013119  jz      loc_180013204
0x18001311f  jmp     short loc_18001315A
0x180013121  test    r14d, r14d
0x180013124  jnz     short loc_180013156
0x180013126  mov     rax, [rbp+4Fh+var_88]
0x18001312a  cmp     dword ptr [rax], 3EAh
0x180013130  jnz     short loc_180013169
0x180013132  mov     rcx, [rbp+4Fh+var_98]; String1
0x180013136  test    rcx, rcx
0x180013139  jz      short loc_180013169
0x18001313b  mov     rax, [rbp+4Fh+String2]
0x18001313f  cmp     [rax], r8w
0x180013143  jz      short loc_180013169
0x180013145  mov     rdx, rax; String2
0x180013148  call    cs:__imp__wcsicmp
0x18001314e  test    eax, eax
0x180013150  jnz     loc_180013214
0x180013156  mov     rax, [rbp+4Fh+var_A0]
0x18001315a  cmp     r14d, 2
0x18001315e  jnz     short loc_180013169
0x180013160  test    byte ptr [rax], 1
0x180013163  jz      loc_180013204
0x180013169  test    ebx, ebx
0x18001316b  jz      short loc_180013191
0x18001316d  cmp     r14d, 2
0x180013171  jz      short loc_180013191
0x180013173  mov     r8, [r15]; struct CMDBaseObject *
0x180013176  lea     rax, [rbp+4Fh+var_C8]
0x18001317a  mov     rdx, [rbp+4Fh+var_C0]; unsigned __int16 *
0x18001317e  mov     r9, rsi; unsigned __int16 *
0x180013181  mov     [rsp+130h+var_110], rax; int
0x180013186  call    ?ReadMetaObject@CImporter@@AEAAJPEBGPEAVCMDBaseObject@@0PEAPEAV2@@Z; CImporter::ReadMetaObject(ushort const *,CMDBaseObject *,ushort const *,CMDBaseObject * *)
0x18001318b  mov     ebx, eax
0x18001318d  test    eax, eax
0x18001318f  js      short loc_1800131B2
0x180013191  test    r12d, r12d
0x180013194  jz      short loc_180013204
0x180013196  mov     r9, [rsp+130h+var_D0]; struct IIS_CRYPTO_STORAGE *
0x18001319b  lea     r8, [rbp+4Fh+var_60]; unsigned int *
0x18001319f  mov     rcx, [rbp+4Fh+var_C8]; this
0x1800131a3  lea     rdx, [rbp+4Fh+var_B0]; void **
0x1800131a7  call    ?ReadDataObject@@YAJPEAVCMDBaseObject@@PEAPEAXPEAKPEAVIIS_CRYPTO_STORAGE@@H@Z; ReadDataObject(CMDBaseObject *,void * *,ulong *,IIS_CRYPTO_STORAGE *,int)
0x1800131ac  mov     ebx, eax
0x1800131ae  test    eax, eax
0x1800131b0  jns     short loc_180013204
0x1800131b2  xor     edi, edi
0x1800131b4  mov     rcx, [r15]
0x1800131b7  test    rcx, rcx
0x1800131ba  jz      short loc_1800131CF
0x1800131bc  mov     rax, [rcx]
0x1800131bf  mov     edx, 1
0x1800131c4  mov     rax, [rax]
0x1800131c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131cc  mov     [r15], rdi
0x1800131cf  cmp     [rsp+130h+var_D0], rdi
0x1800131d4  jz      short loc_1800131E0
0x1800131d6  mov     rcx, [rsp+130h+var_D0]; this
0x1800131db  call    ??_GIIS_CRYPTO_STORAGE@@QEAAPEAXI@Z; IIS_CRYPTO_STORAGE::`scalar deleting destructor'(uint)
0x1800131e0  mov     eax, ebx
0x1800131e2  mov     rcx, [rbp+4Fh+var_38]
0x1800131e6  xor     rcx, rsp; StackCookie
0x1800131e9  call    __security_check_cookie
0x1800131ee  add     rsp, 100h
0x1800131f5  pop     r15
0x1800131f7  pop     r14
0x1800131f9  pop     r12
0x1800131fb  pop     rdi
0x1800131fc  pop     rsi
0x1800131fd  pop     rbx
0x1800131fe  pop     rbp
0x1800131ff  retn
0x180013200  mov     [rsp+130h+var_F0], ecx
0x180013204  mov     r12, [rsp+130h+var_E8]
0x180013209  mov     edx, [rsp+130h+var_D8]
0x18001320d  inc     edx
0x18001320f  jmp     loc_180012F90
0x180013214  mov     ebx, 80070491h
0x180013219  jmp     short loc_1800131B2
0x18001321b  test    byte ptr cs:g_dwDebugFlags, 3
0x180013222  jz      short loc_1800131B2
0x180013224  mov     eax, [rsp+130h+var_D8]
0x180013228  lea     r9, aCimporterDoit; "CImporter::DoIt"
0x18001322f  mov     rcx, cs:g_pDebug
0x180013236  lea     rdx, aInetsrvIisMbMe_6; "inetsrv\\iis\\mb\\metadata\\importer.cp"...
0x18001323d  mov     [rsp+130h+var_F8], eax
0x180013241  mov     r8d, 0E3h
0x180013247  lea     rax, aMbproperty_0; "MBProperty"
0x18001324e  mov     [rsp+130h+var_100], rax
0x180013253  lea     rax, aReadsomedatafr_0; "[ReadSomeDataFromXML] GetColumnValues f"...
0x18001325a  mov     dword ptr [rsp+130h+var_108], ebx
0x18001325e  mov     [rsp+130h+var_110], rax
0x180013263  call    cs:__imp_PuDbgPrintW
0x180013269  jmp     loc_1800131B2
0x18001326e  xor     edi, edi
0x180013270  cmp     [rsp+130h+var_D4], edi
0x180013274  jnz     short loc_180013280
0x180013276  mov     ebx, 80070003h
0x18001327b  jmp     loc_1800131B4
0x180013280  mov     ebx, edi
0x180013282  jmp     loc_1800131CF
0x180013287  mov     rcx, [r15]
0x18001328a  mov     ebx, 8007000Eh
0x18001328f  test    rcx, rcx
0x180013292  jz      loc_1800131B4
0x180013298  mov     rax, [rcx]
0x18001329b  mov     edx, 1
0x1800132a0  mov     rax, [rax]
0x1800132a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132a8  jmp     loc_1800131B4
```
