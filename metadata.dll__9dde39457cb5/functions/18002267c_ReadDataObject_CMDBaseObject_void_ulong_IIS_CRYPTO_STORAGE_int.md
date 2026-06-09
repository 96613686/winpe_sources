# ReadDataObject(CMDBaseObject *,void * *,ulong *,IIS_CRYPTO_STORAGE *,int)

- ea: `0x18002267c`
- end: `0x1800228b1`
- name: `?ReadDataObject@@YAJPEAVCMDBaseObject@@PEAPEAXPEAKPEAVIIS_CRYPTO_STORAGE@@H@Z`
- size: `565`
- prototype: `__int64 __fastcall(struct CMDBaseObject *this, void **, unsigned int *, struct IIS_CRYPTO_STORAGE *, int)`
- caller_count: `10`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18000f954`
- `0x18000fbe0`
- `0x18000ff10`
- `0x180010474`
- `0x180010580`
- `0x180010714`
- `0x180010a70`
- `0x180010c40`
- `0x180012ec0`
- `0x180021c40`

## callees

- `0x1800155dc`
- `0x180015808`
- `0x18002056c`
- `0x18002267c`
- `0x180029cf8`
- `0x18003098e`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002287e`
- `ole32!CoTaskMemFree` at `0x18002287e`
- `KERNEL32!GetLastError` at `0x1800227e7`
- `KERNEL32!GetLastError` at `0x1800227e7`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800227dd`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800227dd`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800226e9`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800226e9`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180022888`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180022888`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002280c`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022826`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002280c`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022826`

## pseudocode

```c
__int64 __fastcall ReadDataObject(
        struct CMDBaseObject *this,
        unsigned __int16 **a2,
        unsigned int *a3,
        struct IIS_CRYPTO_STORAGE *a4)
{
  DWORD *v8; // rax
  _BYTE *v9; // rsi
  unsigned int v10; // edx
  DWORD v11; // ecx
  DWORD *v12; // rax
  DWORD v13; // r9d
  DWORD *v14; // rax
  DWORD v15; // ecx
  DWORD *v16; // rax
  DWORD v17; // ecx
  unsigned __int16 *v18; // rax
  int v19; // edi
  __int64 v20; // rax
  signed int LastError; // eax
  void *Ptr; // rax
  unsigned __int16 *v24; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v25; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v26; // [rsp+48h] [rbp-B8h]
  size_t Size; // [rsp+50h] [rbp-B0h] BYREF
  void *Src; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  int v30; // [rsp+68h] [rbp-98h] BYREF
  struct _METADATA_RECORD v31; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v32[56]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 v33[256]; // [rsp+D0h] [rbp-30h] BYREF

  *(&v31.dwMDDataLen + 1) = 0;
  *(_QWORD *)&v31.dwMDDataTag = 0;
  Src = 0;
  memset_0(v33, 0, sizeof(v33));
  BUFFER::BUFFER((BUFFER *)v32, v33, 0x100u);
  v8 = (DWORD *)a2[5];
  v9 = 0;
  v10 = a3[3];
  LODWORD(Size) = 0;
  pv = 0;
  v11 = *v8;
  v12 = (DWORD *)a2[2];
  v31.dwMDIdentifier = v11;
  v13 = *v12;
  v14 = (DWORD *)a2[6];
  v31.dwMDAttributes = v13;
  v15 = *v14;
  v16 = (DWORD *)a2[1];
  v31.dwMDUserType = v15;
  v17 = *v16;
  v18 = a2[3];
  Src = v18;
  v31.dwMDDataType = v17;
  LODWORD(Size) = v10;
  if ( (v13 & 4) != 0 && a4 )
  {
    if ( v10 )
    {
      v19 = IISCryptoCloneBlobFromRawData(&pv, v18, v10);
      if ( v19 < 0 )
      {
        v9 = pv;
      }
      else
      {
        v20 = *(_QWORD *)a4;
        v30 = 0;
        v9 = pv;
        v19 = (*(__int64 (__fastcall **)(struct IIS_CRYPTO_STORAGE *, void **, size_t *, int *, LPVOID))(v20 + 8))(
                a4,
                &Src,
                &Size,
                &v30,
                pv);
        if ( v19 >= 0 )
        {
LABEL_16:
          v31.pbMDData = (unsigned __int8 *)Src;
          v31.dwMDDataLen = Size;
          pv = (LPVOID)*((_QWORD *)this + 28);
          v19 = CMDBaseObject::SetDataObject(this, &v31, 1);
          CMDBaseObject::SetLastChangeTime(this, (struct _FILETIME *)&pv);
          goto LABEL_18;
        }
      }
    }
    else
    {
      v19 = -2147024883;
    }
    LogEvent(g_pEventLog, 0x8002C83E, 2u, v13, v19, a2[4], *a2, v24, v25, v26);
    goto LABEL_18;
  }
  if ( BUFFER::Resize((BUFFER *)v32, v10) )
  {
    Ptr = BUFFER::QueryPtr((BUFFER *)v32);
    memcpy_0(Ptr, Src, (unsigned int)Size);
    Src = BUFFER::QueryPtr((BUFFER *)v32);
    goto LABEL_16;
  }
  LastError = GetLastError();
  v19 = LastError;
  if ( LastError > 0 )
    v19 = (unsigned __int16)LastError | 0x80070000;
  if ( v19 >= 0 )
    goto LABEL_16;
LABEL_18:
  if ( v9 )
  {
    *v9 = 88;
    CoTaskMemFree(v9);
  }
  BUFFER::~BUFFER((BUFFER *)v32);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18002267c  push    rbp
0x18002267e  push    rbx
0x18002267f  push    rsi
0x180022680  push    rdi
0x180022681  push    r13
0x180022683  push    r14
0x180022685  push    r15
0x180022687  lea     rbp, [rsp-0E0h]
0x18002268f  sub     rsp, 1E0h
0x180022696  mov     rax, cs:__security_cookie
0x18002269d  xor     rax, rsp
0x1800226a0  mov     [rbp+110h+var_40], rax
0x1800226a7  mov     rbx, r8
0x1800226aa  mov     dword ptr [rbp+110h+var_1A0+14h], 0
0x1800226b1  mov     r14, rdx
0x1800226b4  mov     qword ptr [rbp+110h+var_1A0.dwMDDataTag], 0
0x1800226bc  mov     r13, rcx
0x1800226bf  mov     [rsp+210h+Src], 0
0x1800226c8  mov     edi, 100h
0x1800226cd  lea     rcx, [rbp+110h+var_140]; void *
0x1800226d1  mov     r8d, edi; Size
0x1800226d4  xor     edx, edx; Val
0x1800226d6  mov     r15, r9
0x1800226d9  call    memset_0
0x1800226de  mov     r8d, edi
0x1800226e1  lea     rdx, [rbp+110h+var_140]
0x1800226e5  lea     rcx, [rbp+110h+var_178]
0x1800226e9  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x1800226ef  mov     rax, [r14+28h]
0x1800226f3  xor     esi, esi
0x1800226f5  mov     edx, [rbx+0Ch]
0x1800226f8  mov     dword ptr [rsp+210h+Size], 0
0x180022700  mov     [rsp+210h+pv], rsi
0x180022705  mov     ecx, [rax]
0x180022707  mov     rax, [r14+10h]
0x18002270b  mov     [rsp+210h+var_1A0.dwMDIdentifier], ecx
0x18002270f  mov     r9d, [rax]; unsigned int
0x180022712  mov     rax, [r14+30h]
0x180022716  mov     [rsp+210h+var_1A0.dwMDAttributes], r9d
0x18002271b  mov     ecx, [rax]
0x18002271d  mov     rax, [r14+8]
0x180022721  mov     [rsp+210h+var_1A0.dwMDUserType], ecx
0x180022725  mov     ecx, [rax]
0x180022727  mov     rax, [r14+18h]
0x18002272b  mov     [rsp+210h+Src], rax
0x180022730  mov     [rsp+210h+var_1A0.dwMDDataType], ecx
0x180022734  mov     dword ptr [rsp+210h+Size], edx
0x180022738  test    r9b, 4
0x18002273c  jz      loc_1800227D9
0x180022742  test    r15, r15
0x180022745  jz      loc_1800227D9
0x18002274b  test    edx, edx
0x18002274d  jz      short loc_1800227A3
0x18002274f  mov     r8d, edx
0x180022752  lea     rcx, [rsp+210h+pv]
0x180022757  mov     rdx, rax
0x18002275a  call    IISCryptoCloneBlobFromRawData
0x18002275f  mov     edi, eax
0x180022761  test    eax, eax
0x180022763  js      short loc_18002279C
0x180022765  mov     rax, [r15]
0x180022768  lea     r9, [rsp+210h+var_1A8]
0x18002276d  mov     [rsp+210h+var_1A8], esi
0x180022771  lea     r8, [rsp+210h+Size]
0x180022776  mov     rsi, [rsp+210h+pv]
0x18002277b  lea     rdx, [rsp+210h+Src]
0x180022780  mov     rcx, r15
0x180022783  mov     qword ptr [rsp+210h+var_1F0], rsi
0x180022788  mov     rax, [rax+8]
0x18002278c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022791  mov     edi, eax
0x180022793  test    eax, eax
0x180022795  js      short loc_1800227A8
0x180022797  jmp     loc_180022831
0x18002279c  mov     rsi, [rsp+210h+pv]
0x1800227a1  jmp     short loc_1800227A8
0x1800227a3  mov     edi, 8007000Dh
0x1800227a8  mov     rax, [r14]
0x1800227ab  mov     edx, 8002C83Eh; unsigned int
0x1800227b0  mov     rcx, cs:?g_pEventLog@@3PEAUICatalogErrorLogger2@@EA; struct ICatalogErrorLogger2 *
0x1800227b7  mov     r8d, 2; unsigned int
0x1800227bd  mov     [rsp+210h+var_1E0], rax; unsigned __int16 *
0x1800227c2  mov     rax, [r14+20h]
0x1800227c6  mov     [rsp+210h+var_1E8], rax; unsigned __int16 *
0x1800227cb  mov     dword ptr [rsp+210h+var_1F0], edi; char
0x1800227cf  call    ?LogEvent@@YAJPEAUICatalogErrorLogger2@@KKKKPEAG1111@Z; LogEvent(ICatalogErrorLogger2 *,ulong,ulong,ulong,ulong,ushort *,ushort *,ushort *,ushort *,ushort *)
0x1800227d4  jmp     loc_180022873
0x1800227d9  lea     rcx, [rbp+110h+var_178]
0x1800227dd  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800227e3  test    al, al
0x1800227e5  jnz     short loc_180022802
0x1800227e7  call    cs:__imp_GetLastError
0x1800227ed  mov     edi, eax
0x1800227ef  test    eax, eax
0x1800227f1  jle     short loc_1800227FC
0x1800227f3  movzx   edi, ax
0x1800227f6  or      edi, 80070000h
0x1800227fc  test    edi, edi
0x1800227fe  js      short loc_180022873
0x180022800  jmp     short loc_180022831
0x180022802  mov     ebx, dword ptr [rsp+210h+Size]
0x180022806  lea     rcx, [rbp+110h+var_178]
0x18002280a  xor     edi, edi
0x18002280c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180022812  mov     rdx, [rsp+210h+Src]; Src
0x180022817  mov     r8d, ebx; Size
0x18002281a  mov     rcx, rax; void *
0x18002281d  call    memcpy_0
0x180022822  lea     rcx, [rbp+110h+var_178]
0x180022826  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002282c  mov     [rsp+210h+Src], rax
0x180022831  mov     rax, [rsp+210h+Src]
0x180022836  mov     [rbp+110h+var_1A0.pbMDData], rax
0x18002283a  mov     eax, dword ptr [rsp+210h+Size]
0x18002283e  mov     [rbp+110h+var_1A0.dwMDDataLen], eax
0x180022841  test    edi, edi
0x180022843  js      short loc_180022873
0x180022845  mov     rax, [r13+0E0h]
0x18002284c  lea     rdx, [rsp+210h+var_1A0]; struct _METADATA_RECORD *
0x180022851  mov     r8d, 1; int
0x180022857  mov     [rsp+210h+pv], rax
0x18002285c  mov     rcx, r13; this
0x18002285f  call    ?SetDataObject@CMDBaseObject@@QEAAJPEAU_METADATA_RECORD@@H@Z; CMDBaseObject::SetDataObject(_METADATA_RECORD *,int)
0x180022864  lea     rdx, [rsp+210h+pv]; struct _FILETIME *
0x180022869  mov     rcx, r13; this
0x18002286c  mov     edi, eax
0x18002286e  call    ?SetLastChangeTime@CMDBaseObject@@QEAAXPEAU_FILETIME@@@Z; CMDBaseObject::SetLastChangeTime(_FILETIME *)
0x180022873  test    rsi, rsi
0x180022876  jz      short loc_180022884
0x180022878  mov     rcx, rsi; pv
0x18002287b  mov     byte ptr [rsi], 58h ; 'X'
0x18002287e  call    cs:__imp_CoTaskMemFree
0x180022884  lea     rcx, [rbp+110h+var_178]
0x180022888  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002288e  mov     eax, edi
0x180022890  mov     rcx, [rbp+110h+var_40]
0x180022897  xor     rcx, rsp; StackCookie
0x18002289a  call    __security_check_cookie
0x18002289f  add     rsp, 1E0h
0x1800228a6  pop     r15
0x1800228a8  pop     r14
0x1800228aa  pop     r13
0x1800228ac  pop     rdi
0x1800228ad  pop     rsi
0x1800228ae  pop     rbx
0x1800228af  pop     rbp
0x1800228b0  retn
```
