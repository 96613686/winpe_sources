# CMDCOM::ComMDSetMetaDataD(ulong,uchar *,_METADATA_RECORD *,int)

- ea: `0x180019d8c`
- end: `0x180019f13`
- name: `?ComMDSetMetaDataD@CMDCOM@@QEAAJKPEAEPEAU_METADATA_RECORD@@H@Z`
- size: `391`
- prototype: `int(CMDCOM *__hidden this, unsigned int, unsigned __int8 *, struct _METADATA_RECORD *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180019d70`
- `0x180019f20`

## callees

- `0x180002d60`
- `0x180003850`
- `0x180003d30`
- `0x1800147a4`
- `0x1800155dc`
- `0x180019d8c`
- `0x18001a0d0`
- `0x18001aeb4`
- `0x180027710`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180019efa`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180019efa`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180019ded`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180019ded`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDSetMetaDataD(
        CMDCOM *this,
        unsigned int a2,
        char *a3,
        struct _METADATA_RECORD *a4,
        int a5)
{
  int ObjectFromPathWithHandle; // ebx
  int v9; // edi
  unsigned int v10; // edx
  struct CMDHandle *HandleObject; // rsi
  struct CMDBaseObject *v13; // [rsp+60h] [rbp+8h] BYREF
  char *v14; // [rsp+70h] [rbp+18h] BYREF

  v14 = a3;
  v13 = 0;
  if ( g_dwInitialized )
  {
    v9 = a5;
    ObjectFromPathWithHandle = ValidateData(a4, a5);
    if ( ObjectFromPathWithHandle >= 0 )
    {
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
      HandleObject = GetHandleObject(a2);
      if ( HandleObject )
      {
        ObjectFromPathWithHandle = GetObjectFromPathWithHandle(&v13, v10, HandleObject, 2u, &v14, v9);
        if ( (int)(ObjectFromPathWithHandle + 0x80000000) < 0 || ObjectFromPathWithHandle == -2147024893 )
        {
          if ( ObjectFromPathWithHandle != -2147024893
            || (v14 = a3,
                ObjectFromPathWithHandle = AddObjectToDataBase(a2, HandleObject, a3, v9),
                ObjectFromPathWithHandle >= 0)
            && (++*(_DWORD *)&g_dwSystemChangeNumber,
                INCREMENT_SCHEMA_CHANGE_NUMBER(a2, HandleObject, a3, v9),
                ObjectFromPathWithHandle = GetObjectFromPath(&v13, a2, 2, (const CHAR **)&v14, v9),
                ObjectFromPathWithHandle >= 0) )
          {
            ObjectFromPathWithHandle = CMDBaseObject::SetDataObject(v13, a4, v9);
            if ( ObjectFromPathWithHandle >= 0 )
            {
              ++*(_DWORD *)&g_dwSystemChangeNumber;
              INCREMENT_SCHEMA_CHANGE_NUMBER(a2, HandleObject, a3, v9);
              ObjectFromPathWithHandle = CMDHandle::SetChangeData(HandleObject, v13, 4u, a4->dwMDIdentifier, 0);
            }
          }
        }
      }
      else
      {
        ObjectFromPathWithHandle = -2147024890;
      }
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
    }
  }
  else
  {
    return (unsigned int)-2146646016;
  }
  return (unsigned int)ObjectFromPathWithHandle;
}

```

## disassembly

```asm
0x180019d8c  mov     rax, rsp
0x180019d8f  mov     [rax+10h], rbx
0x180019d93  mov     [rax+8], rcx
0x180019d97  push    rbp
0x180019d98  push    rsi
0x180019d99  push    rdi
0x180019d9a  push    r14
0x180019d9c  push    r15
0x180019d9e  sub     rsp, 30h
0x180019da2  mov     [rax+18h], r8
0x180019da6  mov     r15, r9
0x180019da9  mov     qword ptr [rax+8], 0
0x180019db1  mov     rbp, r8
0x180019db4  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180019dba  mov     r14d, edx
0x180019dbd  test    eax, eax
0x180019dbf  jnz     short loc_180019DCB
0x180019dc1  mov     ebx, 800CC800h
0x180019dc6  jmp     loc_180019F00
0x180019dcb  mov     edi, [rsp+58h+arg_20]
0x180019dd2  mov     rcx, r15; struct _METADATA_RECORD *
0x180019dd5  mov     edx, edi; int
0x180019dd7  call    ?ValidateData@@YAJPEAU_METADATA_RECORD@@H@Z; ValidateData(_METADATA_RECORD *,int)
0x180019ddc  mov     ebx, eax
0x180019dde  test    eax, eax
0x180019de0  js      loc_180019F00
0x180019de6  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180019ded  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180019df3  mov     ecx, r14d; unsigned int
0x180019df6  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x180019dfb  mov     rsi, rax
0x180019dfe  test    rax, rax
0x180019e01  jnz     short loc_180019E0D
0x180019e03  mov     ebx, 80070006h
0x180019e08  jmp     loc_180019EF3
0x180019e0d  lea     rax, [rsp+58h+arg_10]
0x180019e12  mov     [rsp+58h+var_30], edi; int
0x180019e16  mov     r9d, 2; unsigned int
0x180019e1c  mov     [rsp+58h+var_38], rax; char **
0x180019e21  mov     r8, rsi; struct CMDHandle *
0x180019e24  lea     rcx, [rsp+58h+arg_0]; struct CMDBaseObject **
0x180019e29  call    ?GetObjectFromPathWithHandle@@YAJAEAPEAVCMDBaseObject@@KPEAVCMDHandle@@KAEAPEADH@Z; GetObjectFromPathWithHandle(CMDBaseObject * &,ulong,CMDHandle *,ulong,char * &,int)
0x180019e2e  mov     ecx, 80000000h
0x180019e33  mov     ebx, eax
0x180019e35  add     eax, ecx
0x180019e37  mov     edx, 80070003h
0x180019e3c  test    ecx, eax
0x180019e3e  jnz     short loc_180019E48
0x180019e40  cmp     ebx, edx
0x180019e42  jnz     loc_180019EF3
0x180019e48  cmp     ebx, edx
0x180019e4a  jnz     short loc_180019EA5
0x180019e4c  mov     r9d, edi; int
0x180019e4f  mov     [rsp+58h+arg_10], rbp
0x180019e54  mov     r8, rbp; char *
0x180019e57  mov     rdx, rsi; struct CMDHandle *
0x180019e5a  mov     ecx, r14d; unsigned int
0x180019e5d  call    ?AddObjectToDataBase@@YAJKPEAVCMDHandle@@PEADH@Z; AddObjectToDataBase(ulong,CMDHandle *,char *,int)
0x180019e62  mov     ebx, eax
0x180019e64  test    eax, eax
0x180019e66  js      loc_180019EF3
0x180019e6c  inc     cs:?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x180019e72  mov     r9d, edi; int
0x180019e75  mov     r8, rbp; char *
0x180019e78  mov     rdx, rsi; struct CMDHandle *
0x180019e7b  mov     ecx, r14d; unsigned int
0x180019e7e  call    ?INCREMENT_SCHEMA_CHANGE_NUMBER@@YAXKPEAVCMDHandle@@PEADH@Z; INCREMENT_SCHEMA_CHANGE_NUMBER(ulong,CMDHandle *,char *,int)
0x180019e83  lea     r9, [rsp+58h+arg_10]; char **
0x180019e88  mov     dword ptr [rsp+58h+var_38], edi; int
0x180019e8c  mov     r8d, 2; unsigned int
0x180019e92  lea     rcx, [rsp+58h+arg_0]; struct CMDBaseObject **
0x180019e97  mov     edx, r14d; unsigned int
0x180019e9a  call    ?GetObjectFromPath@@YAJAEAPEAVCMDBaseObject@@KKAEAPEADH@Z; GetObjectFromPath(CMDBaseObject * &,ulong,ulong,char * &,int)
0x180019e9f  mov     ebx, eax
0x180019ea1  test    eax, eax
0x180019ea3  js      short loc_180019EF3
0x180019ea5  mov     rcx, [rsp+58h+arg_0]; this
0x180019eaa  mov     r8d, edi; int
0x180019ead  mov     rdx, r15; struct _METADATA_RECORD *
0x180019eb0  call    ?SetDataObject@CMDBaseObject@@QEAAJPEAU_METADATA_RECORD@@H@Z; CMDBaseObject::SetDataObject(_METADATA_RECORD *,int)
0x180019eb5  mov     ebx, eax
0x180019eb7  test    eax, eax
0x180019eb9  js      short loc_180019EF3
0x180019ebb  inc     cs:?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x180019ec1  mov     r9d, edi; int
0x180019ec4  mov     r8, rbp; char *
0x180019ec7  mov     rdx, rsi; struct CMDHandle *
0x180019eca  mov     ecx, r14d; unsigned int
0x180019ecd  call    ?INCREMENT_SCHEMA_CHANGE_NUMBER@@YAXKPEAVCMDHandle@@PEADH@Z; INCREMENT_SCHEMA_CHANGE_NUMBER(ulong,CMDHandle *,char *,int)
0x180019ed2  mov     r9d, [r15]; unsigned int
0x180019ed5  mov     r8d, 4; unsigned int
0x180019edb  mov     rdx, [rsp+58h+arg_0]; struct CMDBaseObject *
0x180019ee0  mov     rcx, rsi; this
0x180019ee3  mov     [rsp+58h+var_38], 0; unsigned __int16 *
0x180019eec  call    ?SetChangeData@CMDHandle@@QEAAJPEAVCMDBaseObject@@KKPEAG@Z; CMDHandle::SetChangeData(CMDBaseObject *,ulong,ulong,ushort *)
0x180019ef1  mov     ebx, eax
0x180019ef3  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180019efa  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180019f00  mov     eax, ebx
0x180019f02  mov     rbx, [rsp+58h+arg_8]
0x180019f07  add     rsp, 30h
0x180019f0b  pop     r15
0x180019f0d  pop     r14
0x180019f0f  pop     rdi
0x180019f10  pop     rsi
0x180019f11  pop     rbp
0x180019f12  retn
```
