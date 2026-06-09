# CMDCOM::ComMDEnumMetaDataD(ulong,uchar *,_METADATA_RECORD *,ulong,ulong *,int)

- ea: `0x180017a70`
- end: `0x180017e1e`
- name: `?ComMDEnumMetaDataD@CMDCOM@@QEAAJKPEAEPEAU_METADATA_RECORD@@KPEAKH@Z`
- size: `942`
- prototype: `int(CMDCOM *__hidden this, unsigned int, unsigned __int8 *, struct _METADATA_RECORD *, unsigned int, unsigned int *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180017a40`
- `0x180017e30`

## callees

- `0x180001ef4`
- `0x180003d30`
- `0x1800055c0`
- `0x180007bd0`
- `0x180014ffc`
- `0x180017a70`
- `0x18003098e`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180017cc8`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180017cc8`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180017d52`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180017d52`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180017de8`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180017de8`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180017b15`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180017b15`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180017d5d`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180017d5d`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDEnumMetaDataD(
        CMDCOM *this,
        unsigned int a2,
        char *a3,
        struct _METADATA_RECORD *a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned int a7)
{
  unsigned int v7; // r12d
  int v10; // ebx
  int ObjectFromPath; // eax
  CMDBaseObject *v12; // r15
  DWORD dwMDUserType; // r9d
  DWORD dwMDAttributes; // r8d
  CMDBaseObject *v15; // rcx
  int v16; // eax
  struct CMDBaseData *v17; // rsi
  char *v18; // rax
  DWORD v19; // r8d
  char *v20; // r13
  DWORD v21; // r14d
  int inserted; // eax
  unsigned int *v23; // rax
  BOOL v24; // ebx
  unsigned int v25; // eax
  DWORD dwMDDataType; // [rsp+20h] [rbp-E0h]
  struct CMDBaseData *v28; // [rsp+40h] [rbp-C0h] BYREF
  struct CMDBaseObject *v29; // [rsp+48h] [rbp-B8h] BYREF
  char *v30; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v31; // [rsp+58h] [rbp-A8h]
  struct CMDBaseObject *v32; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v33; // [rsp+68h] [rbp-98h]
  _QWORD v34[5]; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+98h] [rbp-68h]
  __int16 v36; // [rsp+9Ch] [rbp-64h]
  _BYTE v37[128]; // [rsp+A0h] [rbp-60h] BYREF

  v7 = a7;
  v33 = a6;
  v31 = a2;
  v28 = 0;
  v32 = 0;
  v30 = a3;
  if ( g_dwInitialized )
  {
    if ( !a4 || a4->dwMDDataLen && !a4->pbMDData || (a4->dwMDAttributes & 3) == 2 || a4->dwMDDataType >= 6 )
      return (unsigned int)-2147024809;
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
    v29 = 0;
    ObjectFromPath = GetObjectFromPath(&v29, a2, 1, (const CHAR **)&v30, v7);
    v10 = ObjectFromPath;
    if ( ObjectFromPath < 0 )
    {
      if ( ObjectFromPath != -2147024893 )
        goto LABEL_35;
      v12 = v29;
      if ( !v29 || (a4->dwMDAttributes & 2) == 0 )
        goto LABEL_35;
      v16 = CMDBaseObject::EnumInheritableDataObject(v29, &a5, a4->dwMDUserType, a4->dwMDDataType, &v32, &v28);
      LODWORD(v29) = 1;
    }
    else
    {
      v12 = v29;
      if ( !v29 )
      {
        v10 = -2147467259;
LABEL_35:
        CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
        return (unsigned int)v10;
      }
      dwMDUserType = a4->dwMDUserType;
      dwMDAttributes = a4->dwMDAttributes;
      v15 = v29;
      dwMDDataType = a4->dwMDDataType;
      LODWORD(v29) = 0;
      v16 = CMDBaseObject::EnumDataObject(v15, a5, dwMDAttributes, dwMDUserType, dwMDDataType, &v32, &v28);
    }
    v10 = v16;
    if ( v16 < 0 )
      goto LABEL_35;
    v17 = v28;
    if ( !v28 )
    {
      v10 = -2147024637;
      goto LABEL_35;
    }
    v18 = (char *)(*(__int64 (__fastcall **)(struct CMDBaseData *, _QWORD, bool))(*(_QWORD *)v28 + 24LL))(
                    v28,
                    v7,
                    ((a4->dwMDAttributes >> 9) & 1) == 0);
    v19 = a4->dwMDAttributes;
    v20 = v18;
    v30 = v18;
    LODWORD(v28) = (*(__int64 (__fastcall **)(struct CMDBaseData *, _QWORD, bool))(*(_QWORD *)v17 + 32LL))(
                     v17,
                     v7,
                     (v19 & 0x200) == 0);
    v21 = (unsigned int)v28;
    if ( !v20 )
    {
      v10 = -2147024882;
      goto LABEL_35;
    }
    if ( (*((_BYTE *)v17 + 24) & a4->dwMDAttributes & 8) != 0 )
    {
      a4->pbMDData = (unsigned __int8 *)(*(__int64 (__fastcall **)(struct CMDBaseData *, _QWORD, bool))(*(_QWORD *)v17 + 24LL))(
                                          v17,
                                          v7,
                                          ((a4->dwMDAttributes >> 9) & 1) == 0);
      _InterlockedAdd((volatile signed __int32 *)v17 + 8, 1u);
      a4->dwMDDataTag = *((_DWORD *)v17 + 9);
      goto LABEL_30;
    }
    v34[0] = 0;
    v34[4] = v34;
    v35 = 32;
    v36 = 256;
    STRAU::STRAU((STRAU *)v37);
    if ( (*((_BYTE *)v17 + 24) & a4->dwMDAttributes & 0x40) != 0 )
    {
      inserted = InsertPathIntoData(
                   (struct BUFFER *)v34,
                   (struct STRAU *)v37,
                   (unsigned __int8 **)&v30,
                   (unsigned int *)&v28,
                   v17,
                   v31,
                   v32,
                   v7);
      v21 = (unsigned int)v28;
      v10 = inserted;
      if ( inserted < 0 )
        goto LABEL_29;
      v20 = v30;
    }
    if ( a4->dwMDDataLen >= v21 )
    {
      memcpy_0(a4->pbMDData, v20, v21);
      a4->dwMDDataTag = 0;
    }
    else
    {
      v23 = v33;
      v10 = -2147024774;
      a4->dwMDDataLen = 0;
      *v23 = v21;
    }
LABEL_29:
    STRAU::~STRAU((STRAU *)v37);
    BUFFER::~BUFFER((BUFFER *)v34);
    if ( v10 < 0 )
      goto LABEL_35;
LABEL_30:
    v24 = 0;
    if ( (a4->dwMDAttributes & 0x21) == 0x21 )
    {
      if ( (_DWORD)v29 )
      {
        v24 = 1;
      }
      else
      {
        v25 = (*(__int64 (__fastcall **)(struct CMDBaseData *))(*(_QWORD *)v17 + 8LL))(v17);
        v24 = CMDBaseObject::GetDataObject(v12, *((_DWORD *)v17 + 2), a4->dwMDAttributes & 0xFFFFFFFC, v25, 0) == 0;
      }
    }
    a4->dwMDAttributes = *((_DWORD *)v17 + 6) | (32 * v24);
    a4->dwMDIdentifier = *((_DWORD *)v17 + 2);
    a4->dwMDUserType = *((_DWORD *)v17 + 7);
    a4->dwMDDataType = (*(__int64 (__fastcall **)(struct CMDBaseData *))(*(_QWORD *)v17 + 8LL))(v17);
    v10 = 0;
    a4->dwMDDataLen = v21;
    goto LABEL_35;
  }
  return (unsigned int)-2146646016;
}

```

## disassembly

```asm
0x180017a70  mov     [rsp-8+arg_0], rbx
0x180017a75  push    rbp
0x180017a76  push    rsi
0x180017a77  push    rdi
0x180017a78  push    r12
0x180017a7a  push    r13
0x180017a7c  push    r14
0x180017a7e  push    r15
0x180017a80  lea     rbp, [rsp-30h]
0x180017a85  sub     rsp, 130h
0x180017a8c  mov     rax, cs:__security_cookie
0x180017a93  xor     rax, rsp
0x180017a96  mov     [rbp+60h+var_40], rax
0x180017a9a  mov     rax, [rbp+60h+arg_28]
0x180017aa1  xor     r14d, r14d
0x180017aa4  mov     r12d, [rbp+60h+arg_30]
0x180017aab  mov     rdi, r9
0x180017aae  mov     [rsp+160h+var_F8], rax
0x180017ab3  mov     ebx, edx
0x180017ab5  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180017abb  mov     [rsp+160h+var_108], edx
0x180017abf  mov     [rsp+160h+var_120], r14
0x180017ac4  mov     [rsp+160h+var_100], r14
0x180017ac9  mov     [rsp+160h+var_110], r8
0x180017ace  test    eax, eax
0x180017ad0  jnz     short loc_180017ADC
0x180017ad2  mov     ebx, 800CC800h
0x180017ad7  jmp     loc_180017DF5
0x180017adc  test    rdi, rdi
0x180017adf  jz      loc_180017DF0
0x180017ae5  cmp     [r9+10h], r14d
0x180017ae9  jz      short loc_180017AF5
0x180017aeb  cmp     [r9+18h], r14
0x180017aef  jz      loc_180017DF0
0x180017af5  mov     eax, [r9+4]
0x180017af9  and     al, 3
0x180017afb  cmp     al, 2
0x180017afd  jz      loc_180017DF0
0x180017b03  cmp     dword ptr [r9+0Ch], 6
0x180017b08  jnb     loc_180017DF0
0x180017b0e  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180017b15  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180017b1b  mov     r13d, 1
0x180017b21  mov     [rsp+160h+var_118], r14
0x180017b26  mov     r8d, r13d; unsigned int
0x180017b29  mov     dword ptr [rsp+160h+var_140], r12d; int
0x180017b2e  lea     r9, [rsp+160h+var_110]; char **
0x180017b33  mov     edx, ebx; unsigned int
0x180017b35  lea     rcx, [rsp+160h+var_118]; struct CMDBaseObject **
0x180017b3a  call    ?GetObjectFromPath@@YAJAEAPEAVCMDBaseObject@@KKAEAPEADH@Z; GetObjectFromPath(CMDBaseObject * &,ulong,ulong,char * &,int)
0x180017b3f  mov     ebx, eax
0x180017b41  test    eax, eax
0x180017b43  js      short loc_180017B91
0x180017b45  mov     r15, [rsp+160h+var_118]
0x180017b4a  test    r15, r15
0x180017b4d  jnz     short loc_180017B59
0x180017b4f  mov     ebx, 80004005h
0x180017b54  jmp     loc_180017DE1
0x180017b59  mov     r9d, [rdi+8]; unsigned int
0x180017b5d  lea     rax, [rsp+160h+var_120]
0x180017b62  mov     r8d, [rdi+4]; unsigned int
0x180017b66  mov     rcx, r15; this
0x180017b69  mov     edx, [rbp+60h+arg_20]; unsigned int
0x180017b6f  mov     [rsp+160h+var_130], rax; struct CMDBaseData **
0x180017b74  lea     rax, [rsp+160h+var_100]
0x180017b79  mov     [rsp+160h+var_138], rax; struct CMDBaseObject **
0x180017b7e  mov     eax, [rdi+0Ch]
0x180017b81  mov     dword ptr [rsp+160h+var_140], eax; unsigned int
0x180017b85  mov     dword ptr [rsp+160h+var_118], r14d
0x180017b8a  call    ?EnumDataObject@CMDBaseObject@@QEAAJKKKKPEAPEAV1@PEAPEAVCMDBaseData@@@Z; CMDBaseObject::EnumDataObject(ulong,ulong,ulong,ulong,CMDBaseObject * *,CMDBaseData * *)
0x180017b8f  jmp     short loc_180017BE4
0x180017b91  cmp     eax, 80070003h
0x180017b96  jnz     loc_180017DE1
0x180017b9c  mov     r15, [rsp+160h+var_118]
0x180017ba1  test    r15, r15
0x180017ba4  jz      loc_180017DE1
0x180017baa  test    byte ptr [rdi+4], 2
0x180017bae  jz      loc_180017DE1
0x180017bb4  mov     r9d, [rdi+0Ch]; unsigned int
0x180017bb8  lea     rax, [rsp+160h+var_120]
0x180017bbd  mov     r8d, [rdi+8]; unsigned int
0x180017bc1  lea     rdx, [rbp+60h+arg_20]; unsigned int *
0x180017bc8  mov     [rsp+160h+var_138], rax; struct CMDBaseData **
0x180017bcd  mov     rcx, r15; this
0x180017bd0  lea     rax, [rsp+160h+var_100]
0x180017bd5  mov     [rsp+160h+var_140], rax; struct CMDBaseObject **
0x180017bda  call    ?EnumInheritableDataObject@CMDBaseObject@@QEAAJAEAKKKPEAPEAV1@PEAPEAVCMDBaseData@@@Z; CMDBaseObject::EnumInheritableDataObject(ulong &,ulong,ulong,CMDBaseObject * *,CMDBaseData * *)
0x180017bdf  mov     dword ptr [rsp+160h+var_118], r13d
0x180017be4  mov     ebx, eax
0x180017be6  test    eax, eax
0x180017be8  js      loc_180017DE1
0x180017bee  mov     rsi, [rsp+160h+var_120]
0x180017bf3  test    rsi, rsi
0x180017bf6  jnz     short loc_180017C02
0x180017bf8  mov     ebx, 80070103h
0x180017bfd  jmp     loc_180017DE1
0x180017c02  mov     r8d, [rdi+4]
0x180017c06  mov     edx, r12d
0x180017c09  mov     rax, [rsi]
0x180017c0c  mov     rcx, rsi
0x180017c0f  shr     r8d, 9
0x180017c13  not     r8d
0x180017c16  and     r8d, r13d
0x180017c19  mov     rax, [rax+18h]
0x180017c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c22  mov     r8d, [rdi+4]
0x180017c26  mov     r13, rax
0x180017c29  mov     [rsp+160h+var_110], rax
0x180017c2e  mov     edx, r12d
0x180017c31  mov     rax, [rsi]
0x180017c34  mov     rcx, rsi
0x180017c37  shr     r8d, 9
0x180017c3b  not     r8d
0x180017c3e  and     r8d, 1
0x180017c42  mov     rax, [rax+20h]
0x180017c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c4b  mov     dword ptr [rsp+160h+var_120], eax
0x180017c4f  mov     r14d, eax
0x180017c52  test    r13, r13
0x180017c55  jnz     short loc_180017C61
0x180017c57  mov     ebx, 8007000Eh
0x180017c5c  jmp     loc_180017DE1
0x180017c61  mov     r8d, [rdi+4]
0x180017c65  mov     eax, r8d
0x180017c68  and     eax, [rsi+18h]
0x180017c6b  test    al, 8
0x180017c6d  jz      short loc_180017CA5
0x180017c6f  mov     rax, [rsi]
0x180017c72  mov     r13d, 1
0x180017c78  shr     r8d, 9
0x180017c7c  mov     edx, r12d
0x180017c7f  not     r8d
0x180017c82  mov     rcx, rsi
0x180017c85  and     r8d, r13d
0x180017c88  mov     rax, [rax+18h]
0x180017c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c91  mov     [rdi+18h], rax
0x180017c95  lock add [rsi+20h], r13d
0x180017c9a  mov     eax, [rsi+24h]
0x180017c9d  mov     [rdi+20h], eax
0x180017ca0  jmp     loc_180017D6D
0x180017ca5  lea     rax, [rsp+160h+var_F0]
0x180017caa  mov     [rsp+160h+var_F0], 0
0x180017cb3  lea     rcx, [rbp+60h+var_C0]
0x180017cb7  mov     [rbp+60h+var_D0], rax
0x180017cbb  mov     [rbp+60h+var_C8], 20h ; ' '
0x180017cc2  mov     [rbp+60h+var_C4], 100h
0x180017cc8  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x180017cce  mov     eax, [rdi+4]
0x180017cd1  and     eax, [rsi+18h]
0x180017cd4  test    al, 40h
0x180017cd6  jz      short loc_180017D1C
0x180017cd8  mov     rax, [rsp+160h+var_100]
0x180017cdd  lea     r9, [rsp+160h+var_120]; unsigned int *
0x180017ce2  mov     [rsp+160h+var_128], r12d; int
0x180017ce7  lea     r8, [rsp+160h+var_110]; unsigned __int8 **
0x180017cec  mov     [rsp+160h+var_130], rax; struct CMDBaseObject *
0x180017cf1  lea     rdx, [rbp+60h+var_C0]; struct STRAU *
0x180017cf5  mov     eax, [rsp+160h+var_108]
0x180017cf9  lea     rcx, [rsp+160h+var_F0]; struct BUFFER *
0x180017cfe  mov     dword ptr [rsp+160h+var_138], eax; unsigned int
0x180017d02  mov     [rsp+160h+var_140], rsi; struct CMDBaseData *
0x180017d07  call    ?InsertPathIntoData@@YAJPEAVBUFFER@@PEAVSTRAU@@PEAPEAEPEAKPEAVCMDBaseData@@KPEAVCMDBaseObject@@H@Z; InsertPathIntoData(BUFFER *,STRAU *,uchar * *,ulong *,CMDBaseData *,ulong,CMDBaseObject *,int)
0x180017d0c  mov     r14d, dword ptr [rsp+160h+var_120]
0x180017d11  mov     ebx, eax
0x180017d13  test    eax, eax
0x180017d15  js      short loc_180017D4E
0x180017d17  mov     r13, [rsp+160h+var_110]
0x180017d1c  cmp     [rdi+10h], r14d
0x180017d20  jnb     short loc_180017D38
0x180017d22  mov     rax, [rsp+160h+var_F8]
0x180017d27  mov     ebx, 8007007Ah
0x180017d2c  mov     dword ptr [rdi+10h], 0
0x180017d33  mov     [rax], r14d
0x180017d36  jmp     short loc_180017D4E
0x180017d38  mov     rcx, [rdi+18h]; void *
0x180017d3c  mov     rdx, r13; Src
0x180017d3f  mov     r8d, r14d; Size
0x180017d42  call    memcpy_0
0x180017d47  mov     dword ptr [rdi+20h], 0
0x180017d4e  lea     rcx, [rbp+60h+var_C0]
0x180017d52  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180017d58  lea     rcx, [rsp+160h+var_F0]
0x180017d5d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180017d63  test    ebx, ebx
0x180017d65  js      short loc_180017DE1
0x180017d67  mov     r13d, 1
0x180017d6d  mov     eax, [rdi+4]
0x180017d70  xor     ebx, ebx
0x180017d72  and     eax, 21h
0x180017d75  cmp     al, 21h ; '!'
0x180017d77  jnz     short loc_180017DB5
0x180017d79  cmp     dword ptr [rsp+160h+var_118], ebx
0x180017d7d  jz      short loc_180017D84
0x180017d7f  mov     ebx, r13d
0x180017d82  jmp     short loc_180017DB5
0x180017d84  mov     rax, [rsi]
0x180017d87  mov     rcx, rsi
0x180017d8a  mov     rax, [rax+8]
0x180017d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d93  mov     r8d, [rdi+4]
0x180017d97  mov     r9d, eax; unsigned int
0x180017d9a  mov     edx, [rsi+8]; unsigned int
0x180017d9d  and     r8d, 0FFFFFFFCh; unsigned int
0x180017da1  mov     rcx, r15; this
0x180017da4  mov     [rsp+160h+var_140], rbx; struct CMDBaseObject **
0x180017da9  call    ?GetDataObject@CMDBaseObject@@QEAAPEAVCMDBaseData@@KKKPEAPEAV1@@Z; CMDBaseObject::GetDataObject(ulong,ulong,ulong,CMDBaseObject * *)
0x180017dae  test    rax, rax
0x180017db1  cmovz   ebx, r13d
0x180017db5  shl     ebx, 5
0x180017db8  mov     rcx, rsi
0x180017dbb  or      ebx, [rsi+18h]
0x180017dbe  mov     [rdi+4], ebx
0x180017dc1  mov     eax, [rsi+8]
0x180017dc4  mov     [rdi], eax
0x180017dc6  mov     eax, [rsi+1Ch]
0x180017dc9  mov     [rdi+8], eax
0x180017dcc  mov     rax, [rsi]
0x180017dcf  mov     rax, [rax+8]
0x180017dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dd8  mov     [rdi+0Ch], eax
0x180017ddb  xor     ebx, ebx
0x180017ddd  mov     [rdi+10h], r14d
0x180017de1  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180017de8  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180017dee  jmp     short loc_180017DF5
0x180017df0  mov     ebx, 80070057h
0x180017df5  mov     eax, ebx
0x180017df7  mov     rcx, [rbp+60h+var_40]
0x180017dfb  xor     rcx, rsp; StackCookie
0x180017dfe  call    __security_check_cookie
0x180017e03  mov     rbx, [rsp+160h+arg_0]
0x180017e0b  add     rsp, 130h
0x180017e12  pop     r15
0x180017e14  pop     r14
0x180017e16  pop     r13
0x180017e18  pop     r12
0x180017e1a  pop     rdi
0x180017e1b  pop     rsi
0x180017e1c  pop     rbp
0x180017e1d  retn
```
