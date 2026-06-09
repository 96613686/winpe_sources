# CMDCOM::ComMDDeleteMetaDataD(ulong,uchar *,ulong,ulong,int)

- ea: `0x180017104`
- end: `0x180017252`
- name: `?ComMDDeleteMetaDataD@CMDCOM@@QEAAJKPEAEKKH@Z`
- size: `334`
- prototype: `int(CMDCOM *__hidden this, unsigned int, unsigned __int8 *, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800170e0`
- `0x180017260`

## callees

- `0x180002d60`
- `0x180003850`
- `0x1800055c0`
- `0x1800147a4`
- `0x18001558c`
- `0x180017104`
- `0x18001a0d0`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180017239`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180017239`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001715d`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001715d`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDDeleteMetaDataD(
        CMDCOM *this,
        unsigned int a2,
        char *a3,
        unsigned int a4,
        unsigned int a5,
        int a6)
{
  int ObjectFromPathWithHandle; // ebx
  unsigned int v10; // edx
  struct CMDHandle *HandleObject; // rdi
  int v12; // r15d
  CMDBaseObject *v13; // rbx
  struct CMDBaseData *DataObject; // rax
  int v15; // r8d
  struct CMDBaseObject *v17; // [rsp+60h] [rbp+8h] BYREF
  char *v18; // [rsp+70h] [rbp+18h] BYREF

  v18 = a3;
  v17 = 0;
  if ( g_dwInitialized )
  {
    if ( a5 < 6 )
    {
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
      HandleObject = GetHandleObject(a2);
      if ( HandleObject )
      {
        v12 = a6;
        ObjectFromPathWithHandle = GetObjectFromPathWithHandle(&v17, v10, HandleObject, 2u, &v18, a6);
        if ( ObjectFromPathWithHandle >= 0 )
        {
          v13 = v17;
          if ( v17 )
          {
            DataObject = CMDBaseObject::GetDataObject(v17, a4, 0, a5, 0);
            if ( DataObject )
            {
              CMDBaseObject::RemoveDataObject(v13, DataObject, v15, 1);
              ++*(_DWORD *)&g_dwSystemChangeNumber;
              CMDHandle::SetChangeData(HandleObject, v13, 8u, a4, 0);
              INCREMENT_SCHEMA_CHANGE_NUMBER(a2, HandleObject, a3, v12);
              ObjectFromPathWithHandle = 0;
            }
            else
            {
              ObjectFromPathWithHandle = -2146646015;
            }
          }
          else
          {
            ObjectFromPathWithHandle = -2147024893;
          }
        }
      }
      else
      {
        ObjectFromPathWithHandle = -2147024890;
      }
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
    }
    else
    {
      return (unsigned int)-2147024809;
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
0x180017104  mov     rax, rsp
0x180017107  mov     [rax+10h], rbx
0x18001710b  mov     [rax+8], rcx
0x18001710f  push    rbp
0x180017110  push    rsi
0x180017111  push    rdi
0x180017112  push    r14
0x180017114  push    r15
0x180017116  sub     rsp, 30h
0x18001711a  mov     [rax+18h], r8
0x18001711e  mov     r14d, r9d
0x180017121  mov     qword ptr [rax+8], 0
0x180017129  mov     rbp, r8
0x18001712c  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180017132  mov     esi, edx
0x180017134  test    eax, eax
0x180017136  jnz     short loc_180017142
0x180017138  mov     ebx, 800CC800h
0x18001713d  jmp     loc_18001723F
0x180017142  cmp     [rsp+58h+arg_20], 6
0x18001714a  jb      short loc_180017156
0x18001714c  mov     ebx, 80070057h
0x180017151  jmp     loc_18001723F
0x180017156  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001715d  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180017163  mov     ecx, esi; unsigned int
0x180017165  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x18001716a  mov     rdi, rax
0x18001716d  test    rax, rax
0x180017170  jnz     short loc_18001717C
0x180017172  mov     ebx, 80070006h
0x180017177  jmp     loc_180017232
0x18001717c  mov     r15d, [rsp+58h+arg_28]
0x180017184  lea     rax, [rsp+58h+arg_10]
0x180017189  mov     [rsp+58h+var_30], r15d; int
0x18001718e  lea     rcx, [rsp+58h+arg_0]; struct CMDBaseObject **
0x180017193  mov     r9d, 2; unsigned int
0x180017199  mov     [rsp+58h+var_38], rax; char **
0x18001719e  mov     r8, rdi; struct CMDHandle *
0x1800171a1  call    ?GetObjectFromPathWithHandle@@YAJAEAPEAVCMDBaseObject@@KPEAVCMDHandle@@KAEAPEADH@Z; GetObjectFromPathWithHandle(CMDBaseObject * &,ulong,CMDHandle *,ulong,char * &,int)
0x1800171a6  mov     ebx, eax
0x1800171a8  test    eax, eax
0x1800171aa  js      loc_180017232
0x1800171b0  mov     rbx, [rsp+58h+arg_0]
0x1800171b5  test    rbx, rbx
0x1800171b8  jnz     short loc_1800171C1
0x1800171ba  mov     ebx, 80070003h
0x1800171bf  jmp     short loc_180017232
0x1800171c1  mov     r9d, [rsp+58h+arg_20]; unsigned int
0x1800171c9  xor     r8d, r8d; unsigned int
0x1800171cc  mov     edx, r14d; unsigned int
0x1800171cf  mov     [rsp+58h+var_38], 0; struct CMDBaseObject **
0x1800171d8  mov     rcx, rbx; this
0x1800171db  call    ?GetDataObject@CMDBaseObject@@QEAAPEAVCMDBaseData@@KKKPEAPEAV1@@Z; CMDBaseObject::GetDataObject(ulong,ulong,ulong,CMDBaseObject * *)
0x1800171e0  test    rax, rax
0x1800171e3  jz      short loc_18001722D
0x1800171e5  mov     r9d, 1; int
0x1800171eb  mov     rdx, rax; struct CMDBaseData *
0x1800171ee  mov     rcx, rbx; this
0x1800171f1  call    ?RemoveDataObject@CMDBaseObject@@QEAAJPEAVCMDBaseData@@HH@Z; CMDBaseObject::RemoveDataObject(CMDBaseData *,int,int)
0x1800171f6  inc     cs:?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x1800171fc  mov     r9d, r14d; unsigned int
0x1800171ff  mov     r8d, 8; unsigned int
0x180017205  mov     [rsp+58h+var_38], 0; unsigned __int16 *
0x18001720e  mov     rdx, rbx; struct CMDBaseObject *
0x180017211  mov     rcx, rdi; this
0x180017214  call    ?SetChangeData@CMDHandle@@QEAAJPEAVCMDBaseObject@@KKPEAG@Z; CMDHandle::SetChangeData(CMDBaseObject *,ulong,ulong,ushort *)
0x180017219  mov     r9d, r15d; int
0x18001721c  mov     r8, rbp; char *
0x18001721f  mov     rdx, rdi; struct CMDHandle *
0x180017222  mov     ecx, esi; unsigned int
0x180017224  call    ?INCREMENT_SCHEMA_CHANGE_NUMBER@@YAXKPEAVCMDHandle@@PEADH@Z; INCREMENT_SCHEMA_CHANGE_NUMBER(ulong,CMDHandle *,char *,int)
0x180017229  xor     ebx, ebx
0x18001722b  jmp     short loc_180017232
0x18001722d  mov     ebx, 800CC801h
0x180017232  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180017239  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001723f  mov     eax, ebx
0x180017241  mov     rbx, [rsp+58h+arg_8]
0x180017246  add     rsp, 30h
0x18001724a  pop     r15
0x18001724c  pop     r14
0x18001724e  pop     rdi
0x18001724f  pop     rsi
0x180017250  pop     rbp
0x180017251  retn
```
