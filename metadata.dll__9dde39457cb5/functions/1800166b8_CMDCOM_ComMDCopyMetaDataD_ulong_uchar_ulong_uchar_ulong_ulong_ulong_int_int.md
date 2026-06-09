# CMDCOM::ComMDCopyMetaDataD(ulong,uchar *,ulong,uchar *,ulong,ulong,ulong,int,int)

- ea: `0x1800166b8`
- end: `0x180016a65`
- name: `?ComMDCopyMetaDataD@CMDCOM@@QEAAJKPEAEK0KKKHH@Z`
- size: `941`
- prototype: `int(CMDCOM *__hidden this, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned int, int, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180016660`
- `0x180016a70`

## callees

- `0x180002d60`
- `0x1800035d0`
- `0x18000363c`
- `0x180003678`
- `0x180003850`
- `0x180003d30`
- `0x180007574`
- `0x1800147a4`
- `0x18001558c`
- `0x1800156ec`
- `0x1800166b8`
- `0x18001a0d0`

## import_xrefs

- `IisRTL!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x180016833`
- `IisRTL!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x180016833`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180016a44`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180016a44`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001674d`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001674d`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180016a4c`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180016a4c`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180016759`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180016759`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDCopyMetaDataD(
        CMDCOM *this,
        unsigned int a2,
        struct CMDHandle *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        int a9,
        int a10)
{
  int ObjectFromPathWithHandle; // ebx
  unsigned int v12; // esi
  int v13; // r15d
  unsigned int v14; // edi
  int ObjectFromPath; // eax
  CMDBaseObject *v16; // r12
  int v17; // edi
  int IsSchemaObject; // eax
  void **MainDataBuffer; // r13
  unsigned int AllDataObjects; // edi
  struct CMDHandle *HandleObject; // rax
  unsigned int v22; // edx
  int v23; // r8d
  int v24; // esi
  CMDHandle *v25; // r12
  _DWORD *v26; // rcx
  _QWORD **v27; // rdx
  _QWORD *v28; // rax
  unsigned int *v29; // rdi
  _QWORD *v30; // rdx
  int v31; // r8d
  int v32; // esi
  unsigned int v33; // r15d
  _DWORD *v34; // rcx
  _QWORD **v35; // rdx
  _QWORD *v36; // rax
  unsigned int *v37; // rdi
  _QWORD *v38; // rdx
  CMDHandle *v39; // rax
  struct CMDBaseObject *v41; // [rsp+40h] [rbp-28h] BYREF
  char *v42; // [rsp+48h] [rbp-20h] BYREF
  struct CMDHandle *v43; // [rsp+50h] [rbp-18h] BYREF
  int v44; // [rsp+B0h] [rbp+48h]
  CMDBaseObject *v46; // [rsp+C0h] [rbp+58h] BYREF
  unsigned int v47; // [rsp+C8h] [rbp+60h]

  v47 = a4;
  v42 = (char *)a5;
  v46 = 0;
  v41 = 0;
  v43 = a3;
  if ( !g_dwInitialized )
    return (unsigned int)-2146646016;
  v12 = a6;
  v13 = a9;
  if ( !a9 && (a6 & 1) != 0 )
    return (unsigned int)-2147024809;
  v14 = a6 & 2;
  if ( (a6 & 2) != 0 && (a6 & 1) == 0 )
    return (unsigned int)-2147024809;
  if ( a9 )
  {
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
    v44 = 1;
  }
  else
  {
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
    v44 = 0;
  }
  ObjectFromPath = GetObjectFromPath(&v46, a2, 2 - (v13 != 0), (const CHAR **)&v43, a10);
  ObjectFromPathWithHandle = ObjectFromPath;
  if ( ObjectFromPath < 0 )
  {
    if ( ObjectFromPath != -2147024893 )
      goto LABEL_61;
    v16 = v46;
    if ( !v46 || !v14 )
      goto LABEL_61;
    v17 = 1;
  }
  else
  {
    v16 = v46;
    if ( !v46 )
    {
      ObjectFromPathWithHandle = -2147467259;
      goto LABEL_61;
    }
    v17 = 0;
  }
  IsSchemaObject = CMDBaseObject::IsSchemaObject(v16);
  ObjectFromPathWithHandle = IsSchemaObject;
  if ( IsSchemaObject >= 0 )
  {
    MainDataBuffer = GetMainDataBuffer(IsSchemaObject == 0);
    if ( !MainDataBuffer )
    {
      ObjectFromPathWithHandle = -2147024882;
      goto LABEL_61;
    }
    AllDataObjects = CMDBaseObject::GetAllDataObjects(v16, MainDataBuffer, v12, a7, a8, v17, 0, 0);
    LODWORD(a5) = AllDataObjects;
    if ( v44 )
    {
      CReaderWriterLock3::ConvertSharedToExclusive((CReaderWriterLock3 *)&g_LockMasterResource);
      v44 = 0;
    }
    HandleObject = GetHandleObject(v47);
    v43 = HandleObject;
    if ( !HandleObject )
    {
      ObjectFromPathWithHandle = -2147024890;
LABEL_60:
      FreeMainDataBuffer(MainDataBuffer);
      goto LABEL_61;
    }
    ObjectFromPathWithHandle = GetObjectFromPathWithHandle(&v41, v22, HandleObject, 2u, &v42, a10);
    if ( ObjectFromPathWithHandle < 0 )
      goto LABEL_60;
    v24 = 0;
    if ( AllDataObjects )
    {
      v25 = v43;
      while ( 1 )
      {
        if ( ObjectFromPathWithHandle < 0 )
        {
LABEL_43:
          v16 = v46;
          break;
        }
        v26 = *MainDataBuffer;
        if ( v24 == *((_DWORD *)*MainDataBuffer + 24) + 1 && (v27 = (_QWORD **)*((_QWORD *)v26 + 13)) != 0 )
        {
          if ( *v27 != (_QWORD *)(v26 + 20) )
          {
            v26[24] = v24;
            v28 = *v27;
LABEL_39:
            *((_QWORD *)v26 + 13) = v28;
            v29 = (unsigned int *)*(v28 - 2);
            goto LABEL_40;
          }
        }
        else
        {
          v26[24] = v24;
          v30 = v26 + 20;
          v28 = (_QWORD *)*((_QWORD *)v26 + 10);
          v31 = v24;
          if ( v24 )
          {
            while ( v28 != v30 )
            {
              v28 = (_QWORD *)*v28;
              if ( !--v31 )
                goto LABEL_38;
            }
          }
          else
          {
LABEL_38:
            if ( v28 != v30 )
              goto LABEL_39;
          }
        }
        v26[24] = 0;
        v29 = 0;
        *((_QWORD *)v26 + 13) = 0;
LABEL_40:
        ObjectFromPathWithHandle = CMDBaseObject::SetDataObject(v41, (struct CMDBaseData *)v29);
        if ( ObjectFromPathWithHandle >= 0 )
          CMDHandle::SetChangeData(v25, v41, 4u, v29[2], 0);
        AllDataObjects = (unsigned int)a5;
        if ( ++v24 >= (unsigned int)a5 )
          goto LABEL_43;
      }
    }
    if ( v13 || ObjectFromPathWithHandle < 0 || (v32 = 0, !AllDataObjects) )
    {
LABEL_59:
      ++*(_DWORD *)&g_dwSystemChangeNumber;
      INCREMENT_SCHEMA_CHANGE_NUMBER(v47, v43, v42, a10);
      goto LABEL_60;
    }
    v33 = (unsigned int)a5;
    while ( 1 )
    {
      v34 = *MainDataBuffer;
      if ( v32 == *((_DWORD *)*MainDataBuffer + 24) + 1 && (v35 = (_QWORD **)*((_QWORD *)v34 + 13)) != 0 )
      {
        if ( *v35 != (_QWORD *)(v34 + 20) )
        {
          v34[24] = v32;
          v36 = *v35;
LABEL_57:
          *((_QWORD *)v34 + 13) = v36;
          v37 = (unsigned int *)*(v36 - 2);
          goto LABEL_58;
        }
      }
      else
      {
        v34[24] = v32;
        v38 = v34 + 20;
        v36 = (_QWORD *)*((_QWORD *)v34 + 10);
        v23 = v32;
        if ( v32 )
        {
          while ( v36 != v38 )
          {
            v36 = (_QWORD *)*v36;
            if ( !--v23 )
              goto LABEL_56;
          }
        }
        else
        {
LABEL_56:
          if ( v36 != v38 )
            goto LABEL_57;
        }
      }
      v34[24] = 0;
      v37 = 0;
      *((_QWORD *)v34 + 13) = 0;
LABEL_58:
      CMDBaseObject::RemoveDataObject(v16, (struct CMDBaseData *)v37, v23, 1);
      v39 = GetHandleObject(a2);
      CMDHandle::SetChangeData(v39, v16, 8u, v37[2], 0);
      if ( ++v32 >= v33 )
        goto LABEL_59;
    }
  }
LABEL_61:
  if ( v44 )
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
  else
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
  return (unsigned int)ObjectFromPathWithHandle;
}

```

## disassembly

```asm
0x1800166b8  mov     [rsp-40h+arg_18], r9d
0x1800166bd  mov     [rsp-40h+arg_8], edx
0x1800166c1  mov     [rsp-40h+arg_0], rcx
0x1800166c6  push    rbp
0x1800166c7  push    rbx
0x1800166c8  push    rsi
0x1800166c9  push    rdi
0x1800166ca  push    r12
0x1800166cc  push    r13
0x1800166ce  push    r14
0x1800166d0  push    r15
0x1800166d2  mov     rbp, rsp
0x1800166d5  sub     rsp, 68h
0x1800166d9  mov     rax, [rbp+arg_20]
0x1800166dd  mov     ebx, edx
0x1800166df  mov     [rbp+var_20], rax
0x1800166e3  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x1800166e9  mov     [rbp+arg_10], 0
0x1800166f1  mov     [rbp+var_28], 0
0x1800166f9  mov     [rbp+var_18], r8
0x1800166fd  test    eax, eax
0x1800166ff  jnz     short loc_18001670B
0x180016701  mov     ebx, 800CC800h
0x180016706  jmp     loc_180016A52
0x18001670b  mov     esi, [rbp+arg_28]
0x18001670e  mov     r13d, 1
0x180016714  mov     r15d, [rbp+arg_40]
0x18001671b  mov     eax, esi
0x18001671d  and     eax, r13d
0x180016720  test    r15d, r15d
0x180016723  jnz     short loc_180016729
0x180016725  test    eax, eax
0x180016727  jnz     short loc_180016734
0x180016729  mov     edi, esi
0x18001672b  and     edi, 2
0x18001672e  jz      short loc_18001673E
0x180016730  test    eax, eax
0x180016732  jnz     short loc_18001673E
0x180016734  mov     ebx, 80070057h
0x180016739  jmp     loc_180016A52
0x18001673e  lea     r14, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180016745  mov     rcx, r14
0x180016748  test    r15d, r15d
0x18001674b  jz      short loc_180016759
0x18001674d  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180016753  mov     dword ptr [rbp+arg_0], r13d
0x180016757  jmp     short loc_180016766
0x180016759  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001675f  mov     dword ptr [rbp+arg_0], 0
0x180016766  mov     eax, r15d
0x180016769  lea     r9, [rbp+var_18]; char **
0x18001676d  neg     eax
0x18001676f  lea     rcx, [rbp+arg_10]; struct CMDBaseObject **
0x180016773  mov     eax, [rbp+arg_48]
0x180016779  mov     edx, ebx; unsigned int
0x18001677b  sbb     r8d, r8d
0x18001677e  mov     dword ptr [rsp+68h+var_48], eax; int
0x180016782  add     r8d, 2; unsigned int
0x180016786  call    ?GetObjectFromPath@@YAJAEAPEAVCMDBaseObject@@KKAEAPEADH@Z; GetObjectFromPath(CMDBaseObject * &,ulong,ulong,char * &,int)
0x18001678b  mov     ebx, eax
0x18001678d  test    eax, eax
0x18001678f  js      short loc_1800167A8
0x180016791  mov     r12, [rbp+arg_10]
0x180016795  test    r12, r12
0x180016798  jnz     short loc_1800167A4
0x18001679a  mov     ebx, 80004005h
0x18001679f  jmp     loc_180016A3B
0x1800167a4  xor     edi, edi
0x1800167a6  jmp     short loc_1800167CB
0x1800167a8  cmp     eax, 80070003h
0x1800167ad  jnz     loc_180016A3B
0x1800167b3  mov     r12, [rbp+arg_10]
0x1800167b7  test    r12, r12
0x1800167ba  jz      loc_180016A3B
0x1800167c0  test    edi, edi
0x1800167c2  jz      loc_180016A3B
0x1800167c8  mov     edi, r13d
0x1800167cb  mov     rcx, r12; this
0x1800167ce  call    ?IsSchemaObject@CMDBaseObject@@QEAAJXZ; CMDBaseObject::IsSchemaObject(void)
0x1800167d3  mov     ebx, eax
0x1800167d5  test    eax, eax
0x1800167d7  js      loc_180016A3B
0x1800167dd  xor     ecx, ecx
0x1800167df  test    eax, eax
0x1800167e1  setz    cl; int
0x1800167e4  call    ?GetMainDataBuffer@@YAPEAPEAXH@Z; GetMainDataBuffer(int)
0x1800167e9  xor     ebx, ebx
0x1800167eb  mov     r13, rax
0x1800167ee  test    rax, rax
0x1800167f1  jnz     short loc_1800167FD
0x1800167f3  mov     ebx, 8007000Eh
0x1800167f8  jmp     loc_180016A3B
0x1800167fd  mov     eax, [rbp+arg_38]
0x180016803  mov     r8d, esi; unsigned int
0x180016806  mov     r9d, [rbp+arg_30]; unsigned int
0x18001680a  mov     rdx, r13; void **
0x18001680d  mov     [rsp+68h+var_30], rbx; unsigned int *
0x180016812  mov     rcx, r12; this
0x180016815  mov     [rsp+68h+var_38], ebx; int
0x180016819  mov     [rsp+68h+var_40], edi; int
0x18001681d  mov     dword ptr [rsp+68h+var_48], eax; unsigned int
0x180016821  call    ?GetAllDataObjects@CMDBaseObject@@QEAAKPEAPEAXKKKHHPEAK@Z; CMDBaseObject::GetAllDataObjects(void * *,ulong,ulong,ulong,int,int,ulong *)
0x180016826  mov     edi, eax
0x180016828  mov     dword ptr [rbp+arg_20], eax
0x18001682b  cmp     dword ptr [rbp+arg_0], ebx
0x18001682e  jz      short loc_18001683C
0x180016830  mov     rcx, r14
0x180016833  call    cs:__imp_?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ConvertSharedToExclusive(void)
0x180016839  mov     dword ptr [rbp+arg_0], ebx
0x18001683c  mov     ecx, [rbp+arg_18]; unsigned int
0x18001683f  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x180016844  mov     [rbp+var_18], rax
0x180016848  test    rax, rax
0x18001684b  jnz     short loc_180016857
0x18001684d  mov     ebx, 80070006h
0x180016852  jmp     loc_180016A33
0x180016857  mov     ecx, [rbp+arg_48]
0x18001685d  mov     r9d, 2; unsigned int
0x180016863  mov     [rsp+68h+var_40], ecx; int
0x180016867  mov     r8, rax; struct CMDHandle *
0x18001686a  lea     rcx, [rbp+var_20]
0x18001686e  mov     [rsp+68h+var_48], rcx; char **
0x180016873  lea     rcx, [rbp+var_28]; struct CMDBaseObject **
0x180016877  call    ?GetObjectFromPathWithHandle@@YAJAEAPEAVCMDBaseObject@@KPEAVCMDHandle@@KAEAPEADH@Z; GetObjectFromPathWithHandle(CMDBaseObject * &,ulong,CMDHandle *,ulong,char * &,int)
0x18001687c  xor     r9d, r9d
0x18001687f  mov     ebx, eax
0x180016881  test    eax, eax
0x180016883  js      loc_180016A33
0x180016889  mov     esi, r9d
0x18001688c  test    edi, edi
0x18001688e  jz      loc_180016944
0x180016894  mov     r12, [rbp+var_18]
0x180016898  test    ebx, ebx
0x18001689a  js      loc_180016940
0x1800168a0  mov     rcx, [r13+0]
0x1800168a4  mov     eax, [rcx+60h]
0x1800168a7  inc     eax
0x1800168a9  cmp     esi, eax
0x1800168ab  jnz     short loc_1800168D4
0x1800168ad  mov     rdx, [rcx+68h]
0x1800168b1  test    rdx, rdx
0x1800168b4  jz      short loc_1800168D4
0x1800168b6  lea     rax, [rcx+50h]
0x1800168ba  cmp     [rdx], rax
0x1800168bd  jz      short loc_1800168C7
0x1800168bf  mov     [rcx+60h], esi
0x1800168c2  mov     rax, [rdx]
0x1800168c5  jmp     short loc_1800168F8
0x1800168c7  mov     [rcx+60h], r9d
0x1800168cb  mov     rdi, r9
0x1800168ce  mov     [rcx+68h], r9
0x1800168d2  jmp     short loc_180016900
0x1800168d4  mov     [rcx+60h], esi
0x1800168d7  lea     rdx, [rcx+50h]
0x1800168db  mov     rax, [rdx]
0x1800168de  mov     r8d, esi
0x1800168e1  test    esi, esi
0x1800168e3  jz      short loc_1800168F3
0x1800168e5  cmp     rax, rdx
0x1800168e8  jz      short loc_1800168C7
0x1800168ea  mov     rax, [rax]
0x1800168ed  add     r8d, 0FFFFFFFFh
0x1800168f1  jnz     short loc_1800168E5
0x1800168f3  cmp     rax, rdx
0x1800168f6  jz      short loc_1800168C7
0x1800168f8  mov     [rcx+68h], rax
0x1800168fc  mov     rdi, [rax-10h]
0x180016900  mov     rcx, [rbp+var_28]; this
0x180016904  mov     rdx, rdi; struct CMDBaseData *
0x180016907  call    ?SetDataObject@CMDBaseObject@@QEAAJPEAVCMDBaseData@@@Z; CMDBaseObject::SetDataObject(CMDBaseData *)
0x18001690c  xor     r9d, r9d
0x18001690f  mov     ebx, eax
0x180016911  test    eax, eax
0x180016913  js      short loc_180016933
0x180016915  mov     rdx, [rbp+var_28]; struct CMDBaseObject *
0x180016919  mov     r8d, 4; unsigned int
0x18001691f  mov     [rsp+68h+var_48], r9; unsigned __int16 *
0x180016924  mov     rcx, r12; this
0x180016927  mov     r9d, [rdi+8]; unsigned int
0x18001692b  call    ?SetChangeData@CMDHandle@@QEAAJPEAVCMDBaseObject@@KKPEAG@Z; CMDHandle::SetChangeData(CMDBaseObject *,ulong,ulong,ushort *)
0x180016930  xor     r9d, r9d
0x180016933  mov     edi, dword ptr [rbp+arg_20]
0x180016936  inc     esi
0x180016938  cmp     esi, edi
0x18001693a  jb      loc_180016898
0x180016940  mov     r12, [rbp+arg_10]
0x180016944  test    r15d, r15d
0x180016947  jnz     loc_180016A16
0x18001694d  test    ebx, ebx
0x18001694f  js      loc_180016A16
0x180016955  mov     esi, r9d
0x180016958  test    edi, edi
0x18001695a  jz      loc_180016A16
0x180016960  mov     r15d, dword ptr [rbp+arg_20]
0x180016964  mov     r14d, [rbp+arg_8]
0x180016968  jmp     short loc_18001696D
0x18001696a  xor     r9d, r9d
0x18001696d  mov     rcx, [r13+0]
0x180016971  mov     eax, [rcx+60h]
0x180016974  inc     eax
0x180016976  cmp     esi, eax
0x180016978  jnz     short loc_1800169A1
0x18001697a  mov     rdx, [rcx+68h]
0x18001697e  test    rdx, rdx
0x180016981  jz      short loc_1800169A1
0x180016983  lea     rax, [rcx+50h]
0x180016987  cmp     [rdx], rax
0x18001698a  jz      short loc_180016994
0x18001698c  mov     [rcx+60h], esi
0x18001698f  mov     rax, [rdx]
0x180016992  jmp     short loc_1800169C5
0x180016994  mov     [rcx+60h], r9d
0x180016998  mov     rdi, r9
0x18001699b  mov     [rcx+68h], r9
0x18001699f  jmp     short loc_1800169CD
0x1800169a1  mov     [rcx+60h], esi
0x1800169a4  lea     rdx, [rcx+50h]
0x1800169a8  mov     rax, [rdx]
0x1800169ab  mov     r8d, esi
0x1800169ae  test    esi, esi
0x1800169b0  jz      short loc_1800169C0
0x1800169b2  cmp     rax, rdx
0x1800169b5  jz      short loc_180016994
0x1800169b7  mov     rax, [rax]
0x1800169ba  add     r8d, 0FFFFFFFFh; int
0x1800169be  jnz     short loc_1800169B2
0x1800169c0  cmp     rax, rdx
0x1800169c3  jz      short loc_180016994
0x1800169c5  mov     [rcx+68h], rax
0x1800169c9  mov     rdi, [rax-10h]
0x1800169cd  mov     r9d, 1; int
0x1800169d3  mov     rdx, rdi; struct CMDBaseData *
0x1800169d6  mov     rcx, r12; this
0x1800169d9  call    ?RemoveDataObject@CMDBaseObject@@QEAAJPEAVCMDBaseData@@HH@Z; CMDBaseObject::RemoveDataObject(CMDBaseData *,int,int)
0x1800169de  mov     ecx, r14d; unsigned int
0x1800169e1  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x1800169e6  mov     r9d, [rdi+8]; unsigned int
0x1800169ea  mov     r8d, 8; unsigned int
0x1800169f0  mov     rdx, r12; struct CMDBaseObject *
0x1800169f3  mov     [rsp+68h+var_48], 0; unsigned __int16 *
0x1800169fc  mov     rcx, rax; this
0x1800169ff  call    ?SetChangeData@CMDHandle@@QEAAJPEAVCMDBaseObject@@KKPEAG@Z; CMDHandle::SetChangeData(CMDBaseObject *,ulong,ulong,ushort *)
0x180016a04  inc     esi
0x180016a06  cmp     esi, r15d
0x180016a09  jb      loc_18001696A
0x180016a0f  lea     r14, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180016a16  inc     cs:?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x180016a1c  mov     r9d, [rbp+arg_48]; int
0x180016a23  mov     r8, [rbp+var_20]; char *
0x180016a27  mov     rdx, [rbp+var_18]; struct CMDHandle *
0x180016a2b  mov     ecx, [rbp+arg_18]; unsigned int
0x180016a2e  call    ?INCREMENT_SCHEMA_CHANGE_NUMBER@@YAXKPEAVCMDHandle@@PEADH@Z; INCREMENT_SCHEMA_CHANGE_NUMBER(ulong,CMDHandle *,char *,int)
0x180016a33  mov     rcx, r13; Block
0x180016a36  call    ?FreeMainDataBuffer@@YAXPEAPEAX@Z; FreeMainDataBuffer(void * *)
0x180016a3b  cmp     dword ptr [rbp+arg_0], 0
0x180016a3f  mov     rcx, r14
0x180016a42  jz      short loc_180016A4C
0x180016a44  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180016a4a  jmp     short loc_180016A52
0x180016a4c  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180016a52  mov     eax, ebx
0x180016a54  add     rsp, 68h
0x180016a58  pop     r15
0x180016a5a  pop     r14
0x180016a5c  pop     r13
0x180016a5e  pop     r12
0x180016a60  pop     rdi
0x180016a61  pop     rsi
0x180016a62  pop     rbx
0x180016a63  pop     rbp
0x180016a64  retn
```
