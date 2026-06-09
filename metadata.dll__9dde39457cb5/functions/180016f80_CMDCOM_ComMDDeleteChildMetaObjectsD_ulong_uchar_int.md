# CMDCOM::ComMDDeleteChildMetaObjectsD(ulong,uchar *,int)

- ea: `0x180016f80`
- end: `0x1800170b0`
- name: `?ComMDDeleteChildMetaObjectsD@CMDCOM@@QEAAJKPEAEH@Z`
- size: `304`
- prototype: `int(CMDCOM *__hidden this, unsigned int, unsigned __int8 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180016f70`
- `0x1800170c0`

## callees

- `0x180002d60`
- `0x180003850`
- `0x1800053f0`
- `0x1800147a4`
- `0x1800154b8`
- `0x180016f80`
- `0x18001a0d0`
- `0x180031010`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180017094`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180017094`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180016fc7`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180016fc7`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDDeleteChildMetaObjectsD(CMDCOM *this, unsigned int a2, char *a3, int a4)
{
  int ObjectFromPathWithHandle; // ebx
  unsigned int v8; // edx
  struct CMDHandle *HandleObject; // rsi
  struct CMDBaseObject *v10; // rax
  struct CMDBaseObject *v11; // rbx
  CMDBaseObject *v13; // [rsp+50h] [rbp+8h] BYREF
  char *v14; // [rsp+60h] [rbp+18h] BYREF

  v14 = a3;
  v13 = 0;
  if ( g_dwInitialized )
  {
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
    HandleObject = GetHandleObject(a2);
    if ( HandleObject )
    {
      ObjectFromPathWithHandle = GetObjectFromPathWithHandle(&v13, v8, HandleObject, 2u, &v14, a4);
      if ( ObjectFromPathWithHandle >= 0 )
      {
        if ( v13 )
        {
          while ( 1 )
          {
            v10 = CMDBaseObject::EnumChildObject(v13, 0);
            v11 = v10;
            if ( !v10 )
              break;
            CMDBaseObject::RemoveChildObject(v13, v10);
            if ( CMDHandle::SetChangeData(HandleObject, v11, 1u, 0, 0) < 0 && v11 )
              (**(void (__fastcall ***)(struct CMDBaseObject *, __int64))v11)(v11, 1);
          }
          ++*(_DWORD *)&g_dwSystemChangeNumber;
          INCREMENT_SCHEMA_CHANGE_NUMBER(a2, HandleObject, a3, a4);
          ObjectFromPathWithHandle = 0;
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
    return (unsigned int)-2146646016;
  }
  return (unsigned int)ObjectFromPathWithHandle;
}

```

## disassembly

```asm
0x180016f80  mov     rax, rsp
0x180016f83  mov     [rax+10h], rbx
0x180016f87  mov     [rax+20h], rbp
0x180016f8b  mov     [rax+8], rcx
0x180016f8f  push    rsi
0x180016f90  push    r14
0x180016f92  push    r15
0x180016f94  sub     rsp, 30h
0x180016f98  mov     [rax+18h], r8
0x180016f9c  mov     r15d, r9d
0x180016f9f  mov     qword ptr [rax+8], 0
0x180016fa7  mov     r14, r8
0x180016faa  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180016fb0  mov     ebp, edx
0x180016fb2  test    eax, eax
0x180016fb4  jnz     short loc_180016FC0
0x180016fb6  mov     ebx, 800CC800h
0x180016fbb  jmp     loc_18001709A
0x180016fc0  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180016fc7  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180016fcd  mov     ecx, ebp; unsigned int
0x180016fcf  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x180016fd4  mov     rsi, rax
0x180016fd7  test    rax, rax
0x180016fda  jnz     short loc_180016FE6
0x180016fdc  mov     ebx, 80070006h
0x180016fe1  jmp     loc_18001708D
0x180016fe6  lea     rax, [rsp+48h+arg_10]
0x180016feb  mov     [rsp+48h+var_20], r15d; int
0x180016ff0  mov     r9d, 2; unsigned int
0x180016ff6  mov     [rsp+48h+var_28], rax; char **
0x180016ffb  mov     r8, rsi; struct CMDHandle *
0x180016ffe  lea     rcx, [rsp+48h+arg_0]; struct CMDBaseObject **
0x180017003  call    ?GetObjectFromPathWithHandle@@YAJAEAPEAVCMDBaseObject@@KPEAVCMDHandle@@KAEAPEADH@Z; GetObjectFromPathWithHandle(CMDBaseObject * &,ulong,CMDHandle *,ulong,char * &,int)
0x180017008  mov     ebx, eax
0x18001700a  test    eax, eax
0x18001700c  js      short loc_18001708D
0x18001700e  cmp     [rsp+48h+arg_0], 0
0x180017014  jnz     short loc_180017061
0x180017016  mov     ebx, 80070003h
0x18001701b  jmp     short loc_18001708D
0x18001701d  mov     rcx, [rsp+48h+arg_0]; this
0x180017022  mov     rdx, rbx; struct CMDBaseObject *
0x180017025  call    ?RemoveChildObject@CMDBaseObject@@QEAAJPEAV1@@Z; CMDBaseObject::RemoveChildObject(CMDBaseObject *)
0x18001702a  xor     r9d, r9d; unsigned int
0x18001702d  mov     [rsp+48h+var_28], 0; unsigned __int16 *
0x180017036  mov     rdx, rbx; struct CMDBaseObject *
0x180017039  mov     rcx, rsi; this
0x18001703c  lea     r8d, [r9+1]; unsigned int
0x180017040  call    ?SetChangeData@CMDHandle@@QEAAJPEAVCMDBaseObject@@KKPEAG@Z; CMDHandle::SetChangeData(CMDBaseObject *,ulong,ulong,ushort *)
0x180017045  test    eax, eax
0x180017047  jns     short loc_180017061
0x180017049  test    rbx, rbx
0x18001704c  jz      short loc_180017061
0x18001704e  mov     rax, [rbx]
0x180017051  mov     edx, 1
0x180017056  mov     rcx, rbx
0x180017059  mov     rax, [rax]
0x18001705c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017061  mov     rcx, [rsp+48h+arg_0]; this
0x180017066  xor     edx, edx; unsigned int
0x180017068  call    ?EnumChildObject@CMDBaseObject@@QEAAPEAV1@K@Z; CMDBaseObject::EnumChildObject(ulong)
0x18001706d  mov     rbx, rax
0x180017070  test    rax, rax
0x180017073  jnz     short loc_18001701D
0x180017075  inc     cs:?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x18001707b  mov     r9d, r15d; int
0x18001707e  mov     r8, r14; char *
0x180017081  mov     rdx, rsi; struct CMDHandle *
0x180017084  mov     ecx, ebp; unsigned int
0x180017086  call    ?INCREMENT_SCHEMA_CHANGE_NUMBER@@YAXKPEAVCMDHandle@@PEADH@Z; INCREMENT_SCHEMA_CHANGE_NUMBER(ulong,CMDHandle *,char *,int)
0x18001708b  xor     ebx, ebx
0x18001708d  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180017094  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001709a  mov     rbp, [rsp+48h+arg_18]
0x18001709f  mov     eax, ebx
0x1800170a1  mov     rbx, [rsp+48h+arg_8]
0x1800170a6  add     rsp, 30h
0x1800170aa  pop     r15
0x1800170ac  pop     r14
0x1800170ae  pop     rsi
0x1800170af  retn
```
