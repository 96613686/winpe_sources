# ReadLargestMetaID(CMDBaseObject *,IIS_CRYPTO_STORAGE *)

- ea: `0x180010580`
- end: `0x18001070c`
- name: `?ReadLargestMetaID@@YAJPEAVCMDBaseObject@@PEAVIIS_CRYPTO_STORAGE@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(struct CMDBaseObject *this, struct IIS_CRYPTO_STORAGE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180021c40`

## callees

- `0x180010580`
- `0x18002267c`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18001069c`
- `IisRTL!PuDbgPrintW` at `0x18001069c`

## string_xrefs

- `0x18001059f`: `IIsConfigObject`
- `0x180010683`: `[SetLargestMetaID] Unable to read largest meta id from the meta tables. GetColumnValues failed with hr = 0x%x. Will default it to %d.\n`
- `0x18001066d`: `ReadLargestMetaID`
- `0x180010678`: `inetsrv\iis\mb\metadata\readschema.cpp`

## pseudocode

```c
__int64 __fastcall ReadLargestMetaID(struct CMDBaseObject *this, struct IIS_CRYPTO_STORAGE *a2)
{
  __int64 v4; // rcx
  int v5; // ecx
  __int64 v7; // [rsp+28h] [rbp-71h]
  int v8; // [rsp+30h] [rbp-69h]
  int v9; // [rsp+40h] [rbp-59h] BYREF
  int v10; // [rsp+44h] [rbp-55h] BYREF
  int v11; // [rsp+48h] [rbp-51h] BYREF
  int v12; // [rsp+4Ch] [rbp-4Dh] BYREF
  int v13; // [rsp+50h] [rbp-49h] BYREF
  _DWORD *v14; // [rsp+58h] [rbp-41h] BYREF
  const wchar_t *v15; // [rsp+60h] [rbp-39h] BYREF
  void *v16[10]; // [rsp+70h] [rbp-29h] BYREF
  unsigned int v17[12]; // [rsp+C0h] [rbp+27h] BYREF
  int v18; // [rsp+110h] [rbp+77h] BYREF
  unsigned int v19; // [rsp+118h] [rbp+7Fh] BYREF

  v14 = 0;
  v15 = L"IIsConfigObject";
  v18 = 130000;
  v10 = 1004;
  v11 = 0;
  v12 = 1;
  v13 = 1;
  v9 = 5;
  v19 = 0;
  v4 = *((_QWORD *)g_pGlobalISTHelper + 8);
  v16[7] = 0;
  v16[8] = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t **, unsigned int *))(*(_QWORD *)v4 + 24LL))(
         v4,
         0,
         &v15,
         &v19);
  if ( v5 < 0
    || (v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, int *, _QWORD, _DWORD **))(**((_QWORD **)g_pGlobalISTHelper
                                                                                             + 8)
                                                                                          + 32LL))(
               *((_QWORD *)g_pGlobalISTHelper + 8),
               v19,
               1,
               &v9,
               0,
               &v14),
        v5 < 0) )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v8 = v18;
      LODWORD(v7) = v5;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\readschema.cpp",
        570,
        "ReadLargestMetaID",
        L"[SetLargestMetaID] Unable to read largest meta id from the meta tables. GetColumnValues failed with hr = 0x%x. W"
         "ill default it to %d.\n",
        v7,
        v8);
    }
  }
  else
  {
    v18 = *v14 + 1;
  }
  v16[0] = 0;
  v16[4] = (void *)L"/Schema";
  v17[3] = 4;
  v16[5] = &v10;
  v16[2] = &v11;
  v16[6] = &v12;
  v16[1] = &v13;
  v16[3] = &v18;
  return ReadDataObject(this, (unsigned __int16 **)v16, v17, a2);
}

```

## disassembly

```asm
0x180010580  mov     [rsp-8+arg_0], rbx
0x180010585  mov     [rsp-8+arg_8], rdi
0x18001058a  push    rbp
0x18001058b  lea     rbp, [rsp-57h]
0x180010590  sub     rsp, 0F0h
0x180010597  mov     [rbp+57h+var_98], 0
0x18001059f  lea     rax, aIisconfigobjec; "IIsConfigObject"
0x1800105a6  mov     [rbp+57h+var_90], rax
0x1800105aa  lea     r9, [rbp+57h+arg_18]
0x1800105ae  mov     rax, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x1800105b5  lea     r8, [rbp+57h+var_90]
0x1800105b9  mov     [rbp+57h+arg_10], 1FBD0h
0x1800105c0  mov     rdi, rcx
0x1800105c3  mov     [rbp+57h+var_AC], 3ECh
0x1800105ca  mov     rbx, rdx
0x1800105cd  mov     [rbp+57h+var_A8], 0
0x1800105d4  xor     edx, edx
0x1800105d6  mov     [rbp+57h+var_A4], 1
0x1800105dd  mov     [rbp+57h+var_A0], 1
0x1800105e4  mov     [rbp+57h+var_B0], 5
0x1800105eb  mov     [rbp+57h+arg_18], 0
0x1800105f2  mov     rcx, [rax+40h]
0x1800105f6  mov     [rbp+57h+var_48], 0
0x1800105fe  mov     [rbp+57h+var_40], 0
0x180010606  mov     rax, [rcx]
0x180010609  mov     rax, [rax+18h]
0x18001060d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010612  mov     ecx, eax
0x180010614  test    eax, eax
0x180010616  js      short loc_180010661
0x180010618  mov     rax, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x18001061f  lea     rdx, [rbp+57h+var_98]
0x180010623  mov     [rsp+0F0h+var_C8], rdx
0x180010628  lea     r9, [rbp+57h+var_B0]
0x18001062c  mov     edx, [rbp+57h+arg_18]
0x18001062f  mov     r8d, 1
0x180010635  mov     qword ptr [rsp+0F0h+var_D0], 0
0x18001063e  mov     rcx, [rax+40h]
0x180010642  mov     rax, [rcx]
0x180010645  mov     rax, [rax+20h]
0x180010649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001064e  mov     ecx, eax
0x180010650  test    eax, eax
0x180010652  js      short loc_180010661
0x180010654  mov     rax, [rbp+57h+var_98]
0x180010658  mov     ecx, [rax]
0x18001065a  inc     ecx
0x18001065c  mov     [rbp+57h+arg_10], ecx
0x18001065f  jmp     short loc_1800106A2
0x180010661  test    byte ptr cs:g_dwDebugFlags, 3
0x180010668  jz      short loc_1800106A2
0x18001066a  mov     eax, [rbp+57h+arg_10]
0x18001066d  lea     r9, aReadlargestmet; "ReadLargestMetaID"
0x180010674  mov     [rsp+0F0h+var_C0], eax
0x180010678  lea     rdx, aInetsrvIisMbMe_0; "inetsrv\\iis\\mb\\metadata\\readschema."...
0x18001067f  mov     dword ptr [rsp+0F0h+var_C8], ecx
0x180010683  lea     rax, aSetlargestmeta; "[SetLargestMetaID] Unable to read large"...
0x18001068a  mov     rcx, cs:g_pDebug
0x180010691  mov     r8d, 23Ah
0x180010697  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x18001069c  call    cs:__imp_PuDbgPrintW
0x1800106a2  lea     rax, aSchema_3; "/Schema"
0x1800106a9  mov     [rbp+57h+var_80], 0
0x1800106b1  mov     [rbp+57h+var_60], rax
0x1800106b5  lea     r8, [rbp+57h+var_30]; unsigned int *
0x1800106b9  lea     rax, [rbp+57h+var_AC]
0x1800106bd  mov     [rbp+57h+var_24], 4
0x1800106c4  mov     [rbp+57h+var_58], rax
0x1800106c8  lea     rdx, [rbp+57h+var_80]; void **
0x1800106cc  lea     rax, [rbp+57h+var_A8]
0x1800106d0  mov     r9, rbx; struct IIS_CRYPTO_STORAGE *
0x1800106d3  mov     [rbp+57h+var_70], rax
0x1800106d7  mov     rcx, rdi; this
0x1800106da  lea     rax, [rbp+57h+var_A4]
0x1800106de  mov     [rbp+57h+var_50], rax
0x1800106e2  lea     rax, [rbp+57h+var_A0]
0x1800106e6  mov     [rbp+57h+var_78], rax
0x1800106ea  lea     rax, [rbp+57h+arg_10]
0x1800106ee  mov     [rbp+57h+var_68], rax
0x1800106f2  call    ?ReadDataObject@@YAJPEAVCMDBaseObject@@PEAPEAXPEAKPEAVIIS_CRYPTO_STORAGE@@H@Z; ReadDataObject(CMDBaseObject *,void * *,ulong *,IIS_CRYPTO_STORAGE *,int)
0x1800106f7  lea     r11, [rsp+0F0h+var_s0]
0x1800106ff  mov     rbx, [r11+10h]
0x180010703  mov     rdi, [r11+18h]
0x180010707  mov     rsp, r11
0x18001070a  pop     rbp
0x18001070b  retn
```
