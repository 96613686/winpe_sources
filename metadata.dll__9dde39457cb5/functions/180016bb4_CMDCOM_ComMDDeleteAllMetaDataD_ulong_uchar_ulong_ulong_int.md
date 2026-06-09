# CMDCOM::ComMDDeleteAllMetaDataD(ulong,uchar *,ulong,ulong,int)

- ea: `0x180016bb4`
- end: `0x180016dd1`
- name: `?ComMDDeleteAllMetaDataD@CMDCOM@@QEAAJKPEAEKKH@Z`
- size: `541`
- prototype: `int(CMDCOM *__hidden this, unsigned int, unsigned __int8 *, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180016b90`
- `0x180016de0`

## callees

- `0x180002d60`
- `0x1800035d0`
- `0x18000363c`
- `0x180003678`
- `0x180003d30`
- `0x180007574`
- `0x1800147a4`
- `0x18001558c`
- `0x180016bb4`
- `0x18001a0d0`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180016daf`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180016daf`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180016c16`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180016c16`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDDeleteAllMetaDataD(
        CMDCOM *this,
        unsigned int a2,
        char *a3,
        unsigned int a4,
        unsigned int a5,
        int a6)
{
  int ObjectFromPath; // edi
  unsigned int v10; // ebx
  int v11; // r13d
  int IsSchemaObject; // eax
  void **MainDataBuffer; // r14
  unsigned int AllDataObjects; // eax
  int v15; // r8d
  int v16; // ebp
  _DWORD *v17; // rdx
  _QWORD **v18; // rcx
  _QWORD *v19; // rax
  struct CMDBaseData *v20; // rdx
  _QWORD *v21; // rcx
  unsigned int v22; // ebx
  struct CMDHandle *HandleObject; // [rsp+40h] [rbp-38h]
  char *v25; // [rsp+80h] [rbp+8h] BYREF
  CMDBaseObject *v26; // [rsp+90h] [rbp+18h] BYREF

  v26 = 0;
  v25 = a3;
  if ( g_dwInitialized )
  {
    v10 = a5;
    if ( a5 >= 6 )
      return (unsigned int)-2147024809;
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
    v11 = a6;
    ObjectFromPath = GetObjectFromPath(&v26, a2, 2, (const CHAR **)&v25, a6);
    if ( ObjectFromPath < 0 )
      goto LABEL_25;
    if ( !v26 )
    {
      ObjectFromPath = -2147467259;
      goto LABEL_25;
    }
    IsSchemaObject = CMDBaseObject::IsSchemaObject(v26);
    ObjectFromPath = IsSchemaObject;
    if ( IsSchemaObject < 0 )
    {
LABEL_25:
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
      return (unsigned int)ObjectFromPath;
    }
    MainDataBuffer = GetMainDataBuffer(IsSchemaObject == 0);
    if ( !MainDataBuffer )
    {
      ObjectFromPath = -2147024882;
      goto LABEL_25;
    }
    ObjectFromPath = 0;
    HandleObject = GetHandleObject(a2);
    AllDataObjects = CMDBaseObject::GetAllDataObjects(v26, MainDataBuffer, 0, a4, v10, 0, 0, 0);
    v16 = 0;
    LODWORD(v25) = AllDataObjects;
    if ( !AllDataObjects )
      goto LABEL_24;
    while ( 1 )
    {
      v17 = *MainDataBuffer;
      if ( v16 == *((_DWORD *)*MainDataBuffer + 24) + 1 && (v18 = (_QWORD **)*((_QWORD *)v17 + 13)) != 0 )
      {
        if ( *v18 != (_QWORD *)(v17 + 20) )
        {
          v17[24] = v16;
          v19 = *v18;
LABEL_21:
          *((_QWORD *)v17 + 13) = v19;
          v20 = (struct CMDBaseData *)*(v19 - 2);
          goto LABEL_22;
        }
      }
      else
      {
        v17[24] = v16;
        v21 = v17 + 20;
        v19 = (_QWORD *)*((_QWORD *)v17 + 10);
        v15 = v16;
        if ( v16 )
        {
          while ( v19 != v21 )
          {
            v19 = (_QWORD *)*v19;
            if ( !--v15 )
              goto LABEL_20;
          }
        }
        else
        {
LABEL_20:
          if ( v19 != v21 )
            goto LABEL_21;
        }
      }
      v17[24] = 0;
      *((_QWORD *)v17 + 13) = 0;
      v20 = 0;
LABEL_22:
      v22 = *((_DWORD *)v20 + 2);
      CMDBaseObject::RemoveDataObject(v26, v20, v15, 1);
      CMDHandle::SetChangeData(HandleObject, v26, 8u, v22, 0);
      if ( ++v16 >= (unsigned int)v25 )
      {
        ++*(_DWORD *)&g_dwSystemChangeNumber;
        INCREMENT_SCHEMA_CHANGE_NUMBER(a2, HandleObject, a3, v11);
LABEL_24:
        FreeMainDataBuffer(MainDataBuffer);
        goto LABEL_25;
      }
    }
  }
  return (unsigned int)-2146646016;
}

```

## disassembly

```asm
0x180016bb4  mov     rax, rsp
0x180016bb7  mov     [rax+10h], rbx
0x180016bbb  mov     [rax+20h], rbp
0x180016bbf  mov     [rax+8], rcx
0x180016bc3  push    rdi
0x180016bc4  push    r12
0x180016bc6  push    r13
0x180016bc8  push    r14
0x180016bca  push    r15
0x180016bcc  sub     rsp, 50h
0x180016bd0  mov     qword ptr [rax+18h], 0
0x180016bd8  mov     ebp, r9d
0x180016bdb  mov     [rax+8], r8
0x180016bdf  mov     r12, r8
0x180016be2  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180016be8  mov     r15d, edx
0x180016beb  test    eax, eax
0x180016bed  jnz     short loc_180016BF9
0x180016bef  mov     edi, 800CC800h
0x180016bf4  jmp     loc_180016DB5
0x180016bf9  mov     ebx, [rsp+78h+arg_20]
0x180016c00  cmp     ebx, 6
0x180016c03  jb      short loc_180016C0F
0x180016c05  mov     edi, 80070057h
0x180016c0a  jmp     loc_180016DB5
0x180016c0f  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180016c16  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180016c1c  mov     r13d, [rsp+78h+arg_28]
0x180016c24  lea     r9, [rsp+78h+arg_0]; char **
0x180016c2c  mov     r8d, 2; unsigned int
0x180016c32  mov     dword ptr [rsp+78h+var_58], r13d; int
0x180016c37  mov     edx, r15d; unsigned int
0x180016c3a  lea     rcx, [rsp+78h+arg_10]; struct CMDBaseObject **
0x180016c42  call    ?GetObjectFromPath@@YAJAEAPEAVCMDBaseObject@@KKAEAPEADH@Z; GetObjectFromPath(CMDBaseObject * &,ulong,ulong,char * &,int)
0x180016c47  mov     edi, eax
0x180016c49  test    eax, eax
0x180016c4b  js      loc_180016DA8
0x180016c51  cmp     [rsp+78h+arg_10], 0
0x180016c5a  jnz     short loc_180016C66
0x180016c5c  mov     edi, 80004005h
0x180016c61  jmp     loc_180016DA8
0x180016c66  mov     rcx, [rsp+78h+arg_10]; this
0x180016c6e  call    ?IsSchemaObject@CMDBaseObject@@QEAAJXZ; CMDBaseObject::IsSchemaObject(void)
0x180016c73  mov     edi, eax
0x180016c75  test    eax, eax
0x180016c77  js      loc_180016DA8
0x180016c7d  xor     ecx, ecx
0x180016c7f  test    eax, eax
0x180016c81  setz    cl; int
0x180016c84  call    ?GetMainDataBuffer@@YAPEAPEAXH@Z; GetMainDataBuffer(int)
0x180016c89  mov     r14, rax
0x180016c8c  test    rax, rax
0x180016c8f  jnz     short loc_180016C9B
0x180016c91  mov     edi, 8007000Eh
0x180016c96  jmp     loc_180016DA8
0x180016c9b  mov     ecx, r15d; unsigned int
0x180016c9e  xor     edi, edi
0x180016ca0  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x180016ca5  mov     rcx, [rsp+78h+arg_10]; this
0x180016cad  mov     r9d, ebp; unsigned int
0x180016cb0  mov     [rsp+78h+var_38], rax
0x180016cb5  xor     r8d, r8d; unsigned int
0x180016cb8  xor     eax, eax
0x180016cba  mov     rdx, r14; void **
0x180016cbd  mov     [rsp+78h+var_40], rax; unsigned int *
0x180016cc2  mov     [rsp+78h+var_48], eax; int
0x180016cc6  mov     [rsp+78h+var_50], eax; int
0x180016cca  mov     dword ptr [rsp+78h+var_58], ebx; unsigned int
0x180016cce  call    ?GetAllDataObjects@CMDBaseObject@@QEAAKPEAPEAXKKKHHPEAK@Z; CMDBaseObject::GetAllDataObjects(void * *,ulong,ulong,ulong,int,int,ulong *)
0x180016cd3  xor     ebp, ebp
0x180016cd5  mov     dword ptr [rsp+78h+arg_0], eax
0x180016cdc  test    eax, eax
0x180016cde  jz      loc_180016DA0
0x180016ce4  mov     rdx, [r14]
0x180016ce7  mov     ecx, [rdx+60h]
0x180016cea  inc     ecx
0x180016cec  cmp     ebp, ecx
0x180016cee  jnz     short loc_180016D15
0x180016cf0  mov     rcx, [rdx+68h]
0x180016cf4  test    rcx, rcx
0x180016cf7  jz      short loc_180016D15
0x180016cf9  lea     rax, [rdx+50h]
0x180016cfd  cmp     [rcx], rax
0x180016d00  jz      short loc_180016D0A
0x180016d02  mov     [rdx+60h], ebp
0x180016d05  mov     rax, [rcx]
0x180016d08  jmp     short loc_180016D39
0x180016d0a  mov     [rdx+60h], edi
0x180016d0d  mov     [rdx+68h], rdi
0x180016d11  xor     edx, edx
0x180016d13  jmp     short loc_180016D41
0x180016d15  mov     [rdx+60h], ebp
0x180016d18  lea     rcx, [rdx+50h]
0x180016d1c  mov     rax, [rcx]
0x180016d1f  mov     r8d, ebp
0x180016d22  test    ebp, ebp
0x180016d24  jz      short loc_180016D34
0x180016d26  cmp     rax, rcx
0x180016d29  jz      short loc_180016D0A
0x180016d2b  mov     rax, [rax]
0x180016d2e  add     r8d, 0FFFFFFFFh; int
0x180016d32  jnz     short loc_180016D26
0x180016d34  cmp     rax, rcx
0x180016d37  jz      short loc_180016D0A
0x180016d39  mov     [rdx+68h], rax
0x180016d3d  mov     rdx, [rax-10h]; struct CMDBaseData *
0x180016d41  mov     rcx, [rsp+78h+arg_10]; this
0x180016d49  mov     r9d, 1; int
0x180016d4f  mov     ebx, [rdx+8]
0x180016d52  call    ?RemoveDataObject@CMDBaseObject@@QEAAJPEAVCMDBaseData@@HH@Z; CMDBaseObject::RemoveDataObject(CMDBaseData *,int,int)
0x180016d57  mov     rdx, [rsp+78h+arg_10]; struct CMDBaseObject *
0x180016d5f  mov     r9d, ebx; unsigned int
0x180016d62  mov     rbx, [rsp+78h+var_38]
0x180016d67  mov     r8d, 8; unsigned int
0x180016d6d  mov     rcx, rbx; this
0x180016d70  mov     [rsp+78h+var_58], rdi; unsigned __int16 *
0x180016d75  call    ?SetChangeData@CMDHandle@@QEAAJPEAVCMDBaseObject@@KKPEAG@Z; CMDHandle::SetChangeData(CMDBaseObject *,ulong,ulong,ushort *)
0x180016d7a  inc     ebp
0x180016d7c  cmp     ebp, dword ptr [rsp+78h+arg_0]
0x180016d83  jb      loc_180016CE4
0x180016d89  inc     cs:?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x180016d8f  mov     r9d, r13d; int
0x180016d92  mov     r8, r12; char *
0x180016d95  mov     rdx, rbx; struct CMDHandle *
0x180016d98  mov     ecx, r15d; unsigned int
0x180016d9b  call    ?INCREMENT_SCHEMA_CHANGE_NUMBER@@YAXKPEAVCMDHandle@@PEADH@Z; INCREMENT_SCHEMA_CHANGE_NUMBER(ulong,CMDHandle *,char *,int)
0x180016da0  mov     rcx, r14; Block
0x180016da3  call    ?FreeMainDataBuffer@@YAXPEAPEAX@Z; FreeMainDataBuffer(void * *)
0x180016da8  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180016daf  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180016db5  lea     r11, [rsp+78h+var_28]
0x180016dba  mov     eax, edi
0x180016dbc  mov     rbx, [r11+38h]
0x180016dc0  mov     rbp, [r11+48h]
0x180016dc4  mov     rsp, r11
0x180016dc7  pop     r15
0x180016dc9  pop     r14
0x180016dcb  pop     r13
0x180016dcd  pop     r12
0x180016dcf  pop     rdi
0x180016dd0  retn
```
