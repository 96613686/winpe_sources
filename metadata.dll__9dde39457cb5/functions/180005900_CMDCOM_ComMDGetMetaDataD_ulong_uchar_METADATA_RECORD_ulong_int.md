# CMDCOM::ComMDGetMetaDataD(ulong,uchar *,_METADATA_RECORD *,ulong *,int)

- ea: `0x180005900`
- end: `0x180005ccf`
- name: `?ComMDGetMetaDataD@CMDCOM@@QEAAJKPEAEPEAU_METADATA_RECORD@@PEAKH@Z`
- size: `975`
- prototype: `int(CMDCOM *__hidden this, unsigned int, unsigned __int8 *, struct _METADATA_RECORD *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800058d0`
- `0x180018690`

## callees

- `0x180001ef4`
- `0x1800022a4`
- `0x180003760`
- `0x180003d30`
- `0x1800055c0`
- `0x180005900`
- `0x18003098e`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180005b60`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180005b60`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180005bea`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180005bea`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800059b0`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800059b0`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180005bf5`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180005bf5`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDGetMetaDataD(
        CMDCOM *this,
        unsigned int a2,
        char *a3,
        struct _METADATA_RECORD *a4,
        unsigned int *a5,
        unsigned int a6)
{
  int ObjectFromPath; // eax
  int v10; // edi
  CMDBaseObject *v11; // r15
  DWORD dwMDDataType; // r9d
  DWORD dwMDAttributes; // r8d
  CMDBaseObject *v14; // rcx
  DWORD dwMDIdentifier; // edx
  struct CMDBaseData *DataObject; // rsi
  DWORD v17; // edi
  DWORD v18; // r14d
  struct CMDBaseData *DataObjectByType; // rax
  CMDBaseObject *v20; // rcx
  char *v21; // rax
  DWORD v22; // r8d
  char *v23; // r14
  DWORD v24; // r12d
  int inserted; // eax
  unsigned int *v26; // rax
  BOOL v27; // r14d
  unsigned int v28; // eax
  int v29; // edx
  CMDBaseObject *v30; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v31; // [rsp+48h] [rbp-B8h] BYREF
  struct CMDBaseObject *v32; // [rsp+50h] [rbp-B0h] BYREF
  char *v33; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v34; // [rsp+60h] [rbp-A0h]
  unsigned int *v35; // [rsp+68h] [rbp-98h]
  _QWORD v36[5]; // [rsp+70h] [rbp-90h] BYREF
  int v37; // [rsp+98h] [rbp-68h]
  __int16 v38; // [rsp+9Ch] [rbp-64h]
  _BYTE v39[128]; // [rsp+A0h] [rbp-60h] BYREF

  v35 = a5;
  v34 = a2;
  v32 = 0;
  v33 = a3;
  if ( !g_dwInitialized )
    return 2148321280LL;
  if ( !a4 || a4->dwMDDataLen && !a4->pbMDData || (a4->dwMDAttributes & 3) == 2 || a4->dwMDDataType >= 6 )
    return 2147942487LL;
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
  v30 = 0;
  ObjectFromPath = GetObjectFromPath(&v30, a2, 1, (const CHAR **)&v33, a6);
  v10 = ObjectFromPath;
  if ( ObjectFromPath >= 0 )
  {
    v11 = v30;
    if ( !v30 )
    {
      v10 = -2147467259;
      goto LABEL_41;
    }
    dwMDDataType = a4->dwMDDataType;
    dwMDAttributes = a4->dwMDAttributes;
    v14 = v30;
    dwMDIdentifier = a4->dwMDIdentifier;
    LODWORD(v30) = 0;
    DataObject = CMDBaseObject::GetDataObject(v14, dwMDIdentifier, dwMDAttributes, dwMDDataType, &v32);
LABEL_21:
    if ( DataObject )
    {
      v21 = (char *)(*(__int64 (__fastcall **)(struct CMDBaseData *, _QWORD, bool))(*(_QWORD *)DataObject + 24LL))(
                      DataObject,
                      a6,
                      (a4->dwMDAttributes & 0x200) == 0);
      v22 = a4->dwMDAttributes;
      v23 = v21;
      v33 = v21;
      v31 = (*(__int64 (__fastcall **)(struct CMDBaseData *, _QWORD, bool))(*(_QWORD *)DataObject + 32LL))(
              DataObject,
              a6,
              (v22 & 0x200) == 0);
      v24 = v31;
      if ( v23 )
      {
        if ( ((unsigned __int8)a4->dwMDAttributes & *((_BYTE *)DataObject + 24) & 8) != 0 )
        {
          a4->pbMDData = (unsigned __int8 *)(*(__int64 (__fastcall **)(struct CMDBaseData *, _QWORD, bool))(*(_QWORD *)DataObject + 24LL))(
                                              DataObject,
                                              a6,
                                              (a4->dwMDAttributes & 0x200) == 0);
          _InterlockedIncrement((volatile signed __int32 *)DataObject + 8);
          a4->dwMDDataTag = *((_DWORD *)DataObject + 9);
        }
        else
        {
          v36[0] = 0;
          v36[4] = v36;
          v37 = 32;
          v38 = 256;
          STRAU::STRAU((STRAU *)v39);
          if ( (a4->dwMDAttributes & *((_BYTE *)DataObject + 24) & 0x40) != 0 )
          {
            inserted = InsertPathIntoData(
                         (struct BUFFER *)v36,
                         (struct STRAU *)v39,
                         (unsigned __int8 **)&v33,
                         &v31,
                         DataObject,
                         v34,
                         v32,
                         a6);
            v23 = v33;
            v10 = inserted;
            v24 = v31;
          }
          if ( v10 >= 0 )
          {
            if ( a4->dwMDDataLen >= v24 )
            {
              memcpy_0(a4->pbMDData, v23, v24);
              a4->dwMDDataTag = 0;
            }
            else
            {
              v26 = v35;
              v10 = -2147024774;
              a4->dwMDDataLen = 0;
              *v26 = v24;
            }
          }
          STRAU::~STRAU((STRAU *)v39);
          BUFFER::~BUFFER((BUFFER *)v36);
        }
        if ( v10 >= 0 )
        {
          v27 = 0;
          if ( (a4->dwMDAttributes & 0x21) == 0x21 )
          {
            if ( (_DWORD)v30 )
            {
              v27 = 1;
            }
            else
            {
              v28 = (*(__int64 (__fastcall **)(struct CMDBaseData *))(*(_QWORD *)DataObject + 8LL))(DataObject);
              v27 = CMDBaseObject::GetDataObject(v11, a4->dwMDIdentifier, a4->dwMDAttributes & 0xFFFFFFFC, v28, 0) == 0;
            }
          }
          a4->dwMDAttributes = *((_DWORD *)DataObject + 6) | (32 * v27);
          a4->dwMDUserType = *((_DWORD *)DataObject + 7);
          a4->dwMDDataType = (*(__int64 (__fastcall **)(struct CMDBaseData *))(*(_QWORD *)DataObject + 8LL))(DataObject);
          a4->dwMDDataLen = v24;
        }
      }
      else
      {
        v10 = -2147024882;
      }
    }
    else
    {
      v10 = -2146646015;
    }
    goto LABEL_41;
  }
  if ( ObjectFromPath == -2147024893 )
  {
    v11 = v30;
    if ( v30 )
    {
      if ( (a4->dwMDAttributes & 2) != 0 )
      {
        v17 = a4->dwMDDataType;
        v18 = a4->dwMDIdentifier;
        DataObjectByType = CMDBaseObject::GetDataObjectByType(v30, a4->dwMDIdentifier, v17);
        DataObject = DataObjectByType;
        if ( DataObjectByType )
        {
          if ( (*((_BYTE *)DataObjectByType + 24) & 1) != 0 )
          {
            v32 = v11;
LABEL_20:
            v10 = 0;
            LODWORD(v30) = 1;
            goto LABEL_21;
          }
          DataObject = 0;
        }
        v20 = (CMDBaseObject *)*((_QWORD *)v11 + 23);
        if ( v20 )
          DataObject = CMDBaseObject::GetInheritableDataObject(v20, v18, v17, &v32);
        goto LABEL_20;
      }
    }
  }
LABEL_41:
  while ( 1 )
  {
    v29 = g_LockMasterResource;
    if ( v29 == _InterlockedCompareExchange(&g_LockMasterResource, g_LockMasterResource - 1, g_LockMasterResource) )
      break;
    _mm_pause();
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180005900  push    rbp
0x180005902  push    rbx
0x180005903  push    rdi
0x180005904  push    r12
0x180005906  push    r13
0x180005908  lea     rbp, [rsp-40h]
0x18000590d  sub     rsp, 140h
0x180005914  mov     rax, cs:__security_cookie
0x18000591b  xor     rax, rsp
0x18000591e  mov     [rbp+60h+var_40], rax
0x180005922  mov     rax, [rbp+60h+arg_20]
0x180005929  xor     r12d, r12d
0x18000592c  mov     r13d, [rbp+60h+arg_28]
0x180005933  mov     rbx, r9
0x180005936  mov     [rsp+160h+var_F8], rax
0x18000593b  mov     edi, edx
0x18000593d  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180005943  mov     [rsp+160h+var_100], edx
0x180005947  mov     [rsp+160h+var_110], r12
0x18000594c  mov     [rsp+160h+var_108], r8
0x180005951  test    eax, eax
0x180005953  jnz     short loc_18000595F
0x180005955  mov     eax, 800CC800h
0x18000595a  jmp     loc_180005CB4
0x18000595f  test    rbx, rbx
0x180005962  jz      loc_180005CAF
0x180005968  cmp     [r9+10h], r12d
0x18000596c  jz      short loc_180005978
0x18000596e  cmp     [r9+18h], r12
0x180005972  jz      loc_180005CAF
0x180005978  mov     eax, [r9+4]
0x18000597c  and     al, 3
0x18000597e  cmp     al, 2
0x180005980  jz      loc_180005CAF
0x180005986  cmp     dword ptr [r9+0Ch], 6
0x18000598b  jnb     loc_180005CAF
0x180005991  mov     [rsp+160h+arg_0], rsi
0x180005999  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x1800059a0  mov     [rsp+160h+var_28], r14
0x1800059a8  mov     [rsp+160h+var_30], r15
0x1800059b0  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800059b6  lea     r9, [rsp+160h+var_108]; char **
0x1800059bb  mov     [rsp+160h+var_120], r12
0x1800059c0  mov     r8d, 1; unsigned int
0x1800059c6  mov     dword ptr [rsp+160h+var_140], r13d; int
0x1800059cb  mov     edx, edi; unsigned int
0x1800059cd  lea     rcx, [rsp+160h+var_120]; struct CMDBaseObject **
0x1800059d2  call    ?GetObjectFromPath@@YAJAEAPEAVCMDBaseObject@@KKAEAPEADH@Z; GetObjectFromPath(CMDBaseObject * &,ulong,ulong,char * &,int)
0x1800059d7  mov     edi, eax
0x1800059d9  test    eax, eax
0x1800059db  js      short loc_180005A17
0x1800059dd  mov     r15, [rsp+160h+var_120]
0x1800059e2  test    r15, r15
0x1800059e5  jnz     short loc_1800059F1
0x1800059e7  mov     edi, 80004005h
0x1800059ec  jmp     loc_180005C78
0x1800059f1  mov     r9d, [rbx+0Ch]; unsigned int
0x1800059f5  lea     rax, [rsp+160h+var_110]
0x1800059fa  mov     r8d, [rbx+4]; unsigned int
0x1800059fe  mov     rcx, r15; this
0x180005a01  mov     edx, [rbx]; unsigned int
0x180005a03  mov     [rsp+160h+var_140], rax; struct CMDBaseObject **
0x180005a08  mov     dword ptr [rsp+160h+var_120], r12d
0x180005a0d  call    ?GetDataObject@CMDBaseObject@@QEAAPEAVCMDBaseData@@KKKPEAPEAV1@@Z; CMDBaseObject::GetDataObject(ulong,ulong,ulong,CMDBaseObject * *)
0x180005a12  mov     rsi, rax
0x180005a15  jmp     short loc_180005A89
0x180005a17  cmp     eax, 80070003h
0x180005a1c  jnz     loc_180005C78
0x180005a22  mov     r15, [rsp+160h+var_120]
0x180005a27  test    r15, r15
0x180005a2a  jz      loc_180005C78
0x180005a30  test    byte ptr [rbx+4], 2
0x180005a34  jz      loc_180005C78
0x180005a3a  mov     edi, [rbx+0Ch]
0x180005a3d  mov     rcx, r15; this
0x180005a40  mov     r14d, [rbx]
0x180005a43  mov     r8d, edi; unsigned int
0x180005a46  mov     edx, r14d; unsigned int
0x180005a49  call    ?GetDataObjectByType@CMDBaseObject@@AEAAPEAVCMDBaseData@@KK@Z; CMDBaseObject::GetDataObjectByType(ulong,ulong)
0x180005a4e  mov     rsi, rax
0x180005a51  test    rax, rax
0x180005a54  jz      short loc_180005A5F
0x180005a56  test    byte ptr [rax+18h], 1
0x180005a5a  jnz     short loc_180005A98
0x180005a5c  mov     rsi, r12
0x180005a5f  mov     rcx, [r15+0B8h]; this
0x180005a66  test    rcx, rcx
0x180005a69  jz      short loc_180005A7E
0x180005a6b  lea     r9, [rsp+160h+var_110]; struct CMDBaseObject **
0x180005a70  mov     r8d, edi; unsigned int
0x180005a73  mov     edx, r14d; unsigned int
0x180005a76  call    ?GetInheritableDataObject@CMDBaseObject@@QEAAPEAVCMDBaseData@@KKPEAPEAV1@@Z; CMDBaseObject::GetInheritableDataObject(ulong,ulong,CMDBaseObject * *)
0x180005a7b  mov     rsi, rax
0x180005a7e  mov     edi, r12d
0x180005a81  mov     dword ptr [rsp+160h+var_120], 1
0x180005a89  test    rsi, rsi
0x180005a8c  jnz     short loc_180005A9F
0x180005a8e  mov     edi, 800CC801h
0x180005a93  jmp     loc_180005C78
0x180005a98  mov     [rsp+160h+var_110], r15
0x180005a9d  jmp     short loc_180005A7E
0x180005a9f  mov     r8d, [rbx+4]
0x180005aa3  mov     edx, r13d
0x180005aa6  mov     rax, [rsi]
0x180005aa9  mov     rcx, rsi
0x180005aac  shr     r8d, 9
0x180005ab0  not     r8d
0x180005ab3  and     r8d, 1
0x180005ab7  mov     rax, [rax+18h]
0x180005abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ac0  mov     r8d, [rbx+4]
0x180005ac4  mov     r14, rax
0x180005ac7  mov     [rsp+160h+var_108], rax
0x180005acc  mov     edx, r13d
0x180005acf  mov     rax, [rsi]
0x180005ad2  mov     rcx, rsi
0x180005ad5  shr     r8d, 9
0x180005ad9  not     r8d
0x180005adc  and     r8d, 1
0x180005ae0  mov     rax, [rax+20h]
0x180005ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ae9  mov     [rsp+160h+var_118], eax
0x180005aed  mov     r12d, eax
0x180005af0  test    r14, r14
0x180005af3  jnz     short loc_180005AFF
0x180005af5  mov     edi, 8007000Eh
0x180005afa  jmp     loc_180005C78
0x180005aff  mov     eax, [rsi+18h]
0x180005b02  mov     r8d, [rbx+4]
0x180005b06  and     eax, r8d
0x180005b09  test    al, 8
0x180005b0b  jz      short loc_180005B3D
0x180005b0d  mov     rax, [rsi]
0x180005b10  mov     edx, r13d
0x180005b13  shr     r8d, 9
0x180005b17  mov     rcx, rsi
0x180005b1a  not     r8d
0x180005b1d  and     r8d, 1
0x180005b21  mov     rax, [rax+18h]
0x180005b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b2a  mov     [rbx+18h], rax
0x180005b2e  lock inc dword ptr [rsi+20h]
0x180005b32  mov     eax, [rsi+24h]
0x180005b35  mov     [rbx+20h], eax
0x180005b38  jmp     loc_180005BFB
0x180005b3d  lea     rax, [rsp+160h+var_F0]
0x180005b42  mov     [rsp+160h+var_F0], 0
0x180005b4b  lea     rcx, [rbp+60h+var_C0]
0x180005b4f  mov     [rbp+60h+var_D0], rax
0x180005b53  mov     [rbp+60h+var_C8], 20h ; ' '
0x180005b5a  mov     [rbp+60h+var_C4], 100h
0x180005b60  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x180005b66  mov     eax, [rsi+18h]
0x180005b69  and     eax, [rbx+4]
0x180005b6c  test    al, 40h
0x180005b6e  jz      short loc_180005BB0
0x180005b70  mov     rax, [rsp+160h+var_110]
0x180005b75  lea     r9, [rsp+160h+var_118]; unsigned int *
0x180005b7a  mov     [rsp+160h+var_128], r13d; int
0x180005b7f  lea     r8, [rsp+160h+var_108]; unsigned __int8 **
0x180005b84  mov     [rsp+160h+var_130], rax; struct CMDBaseObject *
0x180005b89  lea     rdx, [rbp+60h+var_C0]; struct STRAU *
0x180005b8d  mov     eax, [rsp+160h+var_100]
0x180005b91  lea     rcx, [rsp+160h+var_F0]; struct BUFFER *
0x180005b96  mov     [rsp+160h+var_138], eax; unsigned int
0x180005b9a  mov     [rsp+160h+var_140], rsi; struct CMDBaseData *
0x180005b9f  call    ?InsertPathIntoData@@YAJPEAVBUFFER@@PEAVSTRAU@@PEAPEAEPEAKPEAVCMDBaseData@@KPEAVCMDBaseObject@@H@Z; InsertPathIntoData(BUFFER *,STRAU *,uchar * *,ulong *,CMDBaseData *,ulong,CMDBaseObject *,int)
0x180005ba4  mov     r14, [rsp+160h+var_108]
0x180005ba9  mov     edi, eax
0x180005bab  mov     r12d, [rsp+160h+var_118]
0x180005bb0  test    edi, edi
0x180005bb2  js      short loc_180005BE6
0x180005bb4  cmp     [rbx+10h], r12d
0x180005bb8  jnb     short loc_180005BD0
0x180005bba  mov     rax, [rsp+160h+var_F8]
0x180005bbf  mov     edi, 8007007Ah
0x180005bc4  mov     dword ptr [rbx+10h], 0
0x180005bcb  mov     [rax], r12d
0x180005bce  jmp     short loc_180005BE6
0x180005bd0  mov     rcx, [rbx+18h]; void *
0x180005bd4  mov     rdx, r14; Src
0x180005bd7  mov     r8d, r12d; Size
0x180005bda  call    memcpy_0
0x180005bdf  mov     dword ptr [rbx+20h], 0
0x180005be6  lea     rcx, [rbp+60h+var_C0]
0x180005bea  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180005bf0  lea     rcx, [rsp+160h+var_F0]
0x180005bf5  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180005bfb  test    edi, edi
0x180005bfd  js      short loc_180005C78
0x180005bff  mov     eax, [rbx+4]
0x180005c02  xor     r14d, r14d
0x180005c05  and     eax, 21h
0x180005c08  cmp     al, 21h ; '!'
0x180005c0a  jnz     short loc_180005C50
0x180005c0c  cmp     dword ptr [rsp+160h+var_120], r14d
0x180005c11  jz      short loc_180005C1B
0x180005c13  mov     r14d, 1
0x180005c19  jmp     short loc_180005C50
0x180005c1b  mov     rax, [rsi]
0x180005c1e  mov     rcx, rsi
0x180005c21  mov     rax, [rax+8]
0x180005c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c2a  mov     r8d, [rbx+4]
0x180005c2e  mov     r9d, eax; unsigned int
0x180005c31  mov     edx, [rbx]; unsigned int
0x180005c33  and     r8d, 0FFFFFFFCh; unsigned int
0x180005c37  mov     rcx, r15; this
0x180005c3a  mov     [rsp+160h+var_140], r14; struct CMDBaseObject **
0x180005c3f  call    ?GetDataObject@CMDBaseObject@@QEAAPEAVCMDBaseData@@KKKPEAPEAV1@@Z; CMDBaseObject::GetDataObject(ulong,ulong,ulong,CMDBaseObject * *)
0x180005c44  test    rax, rax
0x180005c47  mov     eax, 1
0x180005c4c  cmovz   r14d, eax
0x180005c50  shl     r14d, 5
0x180005c54  mov     rcx, rsi
0x180005c57  or      r14d, [rsi+18h]
0x180005c5b  mov     [rbx+4], r14d
0x180005c5f  mov     eax, [rsi+1Ch]
0x180005c62  mov     [rbx+8], eax
0x180005c65  mov     rax, [rsi]
0x180005c68  mov     rax, [rax+8]
0x180005c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c71  mov     [rbx+0Ch], eax
0x180005c74  mov     [rbx+10h], r12d
0x180005c78  mov     r15, [rsp+160h+var_30]
0x180005c80  mov     r14, [rsp+160h+var_28]
0x180005c88  mov     rsi, [rsp+160h+arg_0]
0x180005c90  mov     edx, cs:?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180005c96  mov     eax, edx
0x180005c98  lea     ecx, [rdx-1]
0x180005c9b  lock cmpxchg cs:?g_LockMasterResource@@3VCReaderWriterLock3@@A, ecx; CReaderWriterLock3 g_LockMasterResource
0x180005ca3  cmp     edx, eax
0x180005ca5  jz      short loc_180005CAB
0x180005ca7  pause
0x180005ca9  jmp     short loc_180005C90
0x180005cab  mov     eax, edi
0x180005cad  jmp     short loc_180005CB4
0x180005caf  mov     eax, 80070057h
0x180005cb4  mov     rcx, [rbp+60h+var_40]
0x180005cb8  xor     rcx, rsp; StackCookie
0x180005cbb  call    __security_check_cookie
0x180005cc0  add     rsp, 140h
0x180005cc7  pop     r13
0x180005cc9  pop     r12
0x180005ccb  pop     rdi
0x180005ccc  pop     rbx
0x180005ccd  pop     rbp
0x180005cce  retn
```
