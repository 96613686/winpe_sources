# ReadDataObject(CMDBaseObject *,BUFFER *,ulong,IIS_CRYPTO_STORAGE *,int)

- ea: `0x1800228b8`
- end: `0x180022ab2`
- name: `?ReadDataObject@@YAJPEAVCMDBaseObject@@PEAVBUFFER@@KPEAVIIS_CRYPTO_STORAGE@@H@Z`
- size: `506`
- prototype: `__int64 __usercall@<rax>(struct CMDBaseObject *this@<rcx>, struct BUFFER *@<rdx>, unsigned int@<r8d>, struct IIS_CRYPTO_STORAGE *@<r9>, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180021330`

## callees

- `0x1800155dc`
- `0x180015808`
- `0x1800228b8`
- `0x180029cf8`
- `0x18003098e`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180022a80`
- `ole32!CoTaskMemFree` at `0x180022a80`
- `KERNEL32!GetLastError` at `0x1800229ea`
- `KERNEL32!GetLastError` at `0x1800229ea`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800229e0`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800229e0`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002292f`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002292f`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180022a8b`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180022a8b`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800228fe`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022a13`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022a2e`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800228fe`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022a13`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022a2e`

## pseudocode

```c
__int64 __fastcall ReadDataObject(
        struct CMDBaseObject *this,
        struct BUFFER *a2,
        unsigned int a3,
        struct IIS_CRYPTO_STORAGE *a4,
        int a5)
{
  char *Ptr; // rbx
  _BYTE *v9; // rdi
  int v10; // ebx
  unsigned int v11; // edx
  DWORD v12; // ecx
  DWORD v13; // eax
  _DWORD *v14; // rbx
  __int64 v15; // rax
  signed int LastError; // eax
  void *v17; // rax
  void *v18; // rax
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  void *Src; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+48h] [rbp-B8h] BYREF
  struct _METADATA_RECORD v24; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[56]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 v26[256]; // [rsp+B0h] [rbp-50h] BYREF

  *(&v24.dwMDDataLen + 1) = 0;
  *(_QWORD *)&v24.dwMDDataTag = 0;
  Src = 0;
  Ptr = (char *)BUFFER::QueryPtr(a2);
  memset_0(v26, 0, sizeof(v26));
  BUFFER::BUFFER((BUFFER *)v25, v26, 0x100u);
  v9 = 0;
  LODWORD(Size) = 0;
  pv = 0;
  if ( a3 < 0x11 )
  {
    v10 = -2147024883;
    goto LABEL_17;
  }
  v11 = a3 - 17;
  v12 = *(_DWORD *)(Ptr + 5);
  v24.dwMDIdentifier = *(_DWORD *)(Ptr + 1);
  v24.dwMDUserType = *(_DWORD *)(Ptr + 9);
  v13 = *(_DWORD *)(Ptr + 13);
  v14 = Ptr + 17;
  v24.dwMDAttributes = v12;
  v24.dwMDDataType = v13;
  Src = v14;
  LODWORD(Size) = a3 - 17;
  if ( (v12 & 4) != 0 && a4 )
  {
    v10 = IISCryptoCloneBlobFromRawData(&pv, v14, v11);
    if ( v10 < 0 )
    {
      v9 = pv;
      goto LABEL_15;
    }
    v15 = *(_QWORD *)a4;
    v23 = 0;
    v9 = pv;
    v10 = (*(__int64 (__fastcall **)(struct IIS_CRYPTO_STORAGE *, void **, size_t *, int *, LPVOID))(v15 + 8))(
            a4,
            &Src,
            &Size,
            &v23,
            pv);
  }
  else
  {
    if ( BUFFER::Resize((BUFFER *)v25, v11) )
    {
      v18 = BUFFER::QueryPtr((BUFFER *)v25);
      memcpy_0(v18, Src, (unsigned int)Size);
      v17 = BUFFER::QueryPtr((BUFFER *)v25);
      Src = v17;
      goto LABEL_14;
    }
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v10 < 0 )
    goto LABEL_15;
  v17 = Src;
LABEL_14:
  v24.pbMDData = (unsigned __int8 *)v17;
  v24.dwMDDataLen = Size;
  pv = (LPVOID)*((_QWORD *)this + 28);
  v10 = CMDBaseObject::SetDataObject(this, &v24, a5);
  CMDBaseObject::SetLastChangeTime(this, (struct _FILETIME *)&pv);
LABEL_15:
  if ( v9 )
  {
    *v9 = 88;
    CoTaskMemFree(v9);
  }
LABEL_17:
  BUFFER::~BUFFER((BUFFER *)v25);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800228b8  push    rbp
0x1800228ba  push    rbx
0x1800228bb  push    rsi
0x1800228bc  push    rdi
0x1800228bd  push    r14
0x1800228bf  push    r15
0x1800228c1  lea     rbp, [rsp-0C8h]
0x1800228c9  sub     rsp, 1C8h
0x1800228d0  mov     rax, cs:__security_cookie
0x1800228d7  xor     rax, rsp
0x1800228da  mov     [rbp+0F0h+var_40], rax
0x1800228e1  mov     r14, rcx
0x1800228e4  mov     dword ptr [rsp+1F0h+var_1A0+14h], 0
0x1800228ec  mov     rcx, rdx
0x1800228ef  mov     qword ptr [rsp+1F0h+var_1A0.dwMDDataTag], 0
0x1800228f8  mov     rsi, r9
0x1800228fb  mov     r15d, r8d
0x1800228fe  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180022904  mov     edi, 100h
0x180022909  mov     [rsp+1F0h+Src], 0
0x180022912  mov     r8d, edi; Size
0x180022915  lea     rcx, [rbp+0F0h+var_140]; void *
0x180022919  xor     edx, edx; Val
0x18002291b  mov     rbx, rax
0x18002291e  call    memset_0
0x180022923  mov     r8d, edi
0x180022926  lea     rdx, [rbp+0F0h+var_140]
0x18002292a  lea     rcx, [rsp+1F0h+var_178]
0x18002292f  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180022935  xor     edi, edi
0x180022937  mov     dword ptr [rsp+1F0h+Size], 0
0x18002293f  mov     [rsp+1F0h+pv], rdi
0x180022944  cmp     r15d, 11h
0x180022948  jnb     short loc_180022954
0x18002294a  mov     ebx, 8007000Dh
0x18002294f  jmp     loc_180022A86
0x180022954  mov     eax, [rbx+1]
0x180022957  lea     edx, [r15-11h]
0x18002295b  mov     ecx, [rbx+5]
0x18002295e  mov     [rsp+1F0h+var_1A0.dwMDIdentifier], eax
0x180022962  mov     eax, [rbx+9]
0x180022965  mov     [rsp+1F0h+var_1A0.dwMDUserType], eax
0x180022969  mov     eax, [rbx+0Dh]
0x18002296c  add     rbx, 11h
0x180022970  mov     [rsp+1F0h+var_1A0.dwMDAttributes], ecx
0x180022974  mov     [rsp+1F0h+var_1A0.dwMDDataType], eax
0x180022978  mov     [rsp+1F0h+Src], rbx
0x18002297d  mov     dword ptr [rsp+1F0h+Size], edx
0x180022981  test    cl, 4
0x180022984  jz      short loc_1800229DB
0x180022986  test    rsi, rsi
0x180022989  jz      short loc_1800229DB
0x18002298b  mov     r8d, edx
0x18002298e  lea     rcx, [rsp+1F0h+pv]
0x180022993  mov     rdx, rbx
0x180022996  call    IISCryptoCloneBlobFromRawData
0x18002299b  mov     ebx, eax
0x18002299d  test    eax, eax
0x18002299f  js      short loc_1800229D1
0x1800229a1  mov     rax, [rsi]
0x1800229a4  lea     r9, [rsp+1F0h+var_1A8]
0x1800229a9  mov     [rsp+1F0h+var_1A8], edi
0x1800229ad  lea     r8, [rsp+1F0h+Size]
0x1800229b2  mov     rdi, [rsp+1F0h+pv]
0x1800229b7  lea     rdx, [rsp+1F0h+Src]
0x1800229bc  mov     rcx, rsi
0x1800229bf  mov     [rsp+1F0h+var_1D0], rdi
0x1800229c4  mov     rax, [rax+8]
0x1800229c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229cd  mov     ebx, eax
0x1800229cf  jmp     short loc_1800229FF
0x1800229d1  mov     rdi, [rsp+1F0h+pv]
0x1800229d6  jmp     loc_180022A75
0x1800229db  lea     rcx, [rsp+1F0h+var_178]
0x1800229e0  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800229e6  test    al, al
0x1800229e8  jnz     short loc_180022A0A
0x1800229ea  call    cs:__imp_GetLastError
0x1800229f0  mov     ebx, eax
0x1800229f2  test    eax, eax
0x1800229f4  jle     short loc_1800229FF
0x1800229f6  movzx   ebx, ax
0x1800229f9  or      ebx, 80070000h
0x1800229ff  test    ebx, ebx
0x180022a01  js      short loc_180022A75
0x180022a03  mov     rax, [rsp+1F0h+Src]
0x180022a08  jmp     short loc_180022A39
0x180022a0a  mov     ebx, dword ptr [rsp+1F0h+Size]
0x180022a0e  lea     rcx, [rsp+1F0h+var_178]
0x180022a13  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180022a19  mov     rdx, [rsp+1F0h+Src]; Src
0x180022a1e  mov     r8d, ebx; Size
0x180022a21  mov     rcx, rax; void *
0x180022a24  call    memcpy_0
0x180022a29  lea     rcx, [rsp+1F0h+var_178]
0x180022a2e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180022a34  mov     [rsp+1F0h+Src], rax
0x180022a39  mov     r8d, [rbp+0F0h+arg_20]; int
0x180022a40  lea     rdx, [rsp+1F0h+var_1A0]; struct _METADATA_RECORD *
0x180022a45  mov     [rsp+1F0h+var_1A0.pbMDData], rax
0x180022a4a  mov     rcx, r14; this
0x180022a4d  mov     eax, dword ptr [rsp+1F0h+Size]
0x180022a51  mov     [rsp+1F0h+var_1A0.dwMDDataLen], eax
0x180022a55  mov     rax, [r14+0E0h]
0x180022a5c  mov     [rsp+1F0h+pv], rax
0x180022a61  call    ?SetDataObject@CMDBaseObject@@QEAAJPEAU_METADATA_RECORD@@H@Z; CMDBaseObject::SetDataObject(_METADATA_RECORD *,int)
0x180022a66  lea     rdx, [rsp+1F0h+pv]; struct _FILETIME *
0x180022a6b  mov     rcx, r14; this
0x180022a6e  mov     ebx, eax
0x180022a70  call    ?SetLastChangeTime@CMDBaseObject@@QEAAXPEAU_FILETIME@@@Z; CMDBaseObject::SetLastChangeTime(_FILETIME *)
0x180022a75  test    rdi, rdi
0x180022a78  jz      short loc_180022A86
0x180022a7a  mov     rcx, rdi; pv
0x180022a7d  mov     byte ptr [rdi], 58h ; 'X'
0x180022a80  call    cs:__imp_CoTaskMemFree
0x180022a86  lea     rcx, [rsp+1F0h+var_178]
0x180022a8b  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180022a91  mov     eax, ebx
0x180022a93  mov     rcx, [rbp+0F0h+var_40]
0x180022a9a  xor     rcx, rsp; StackCookie
0x180022a9d  call    __security_check_cookie
0x180022aa2  add     rsp, 1C8h
0x180022aa9  pop     r15
0x180022aab  pop     r14
0x180022aad  pop     rdi
0x180022aae  pop     rsi
0x180022aaf  pop     rbx
0x180022ab0  pop     rbp
0x180022ab1  retn
```
