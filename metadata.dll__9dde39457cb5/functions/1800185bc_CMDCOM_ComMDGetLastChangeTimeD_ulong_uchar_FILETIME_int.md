# CMDCOM::ComMDGetLastChangeTimeD(ulong,uchar *,_FILETIME *,int)

- ea: `0x1800185bc`
- end: `0x180018662`
- name: `?ComMDGetLastChangeTimeD@CMDCOM@@QEAAJKPEAEPEAU_FILETIME@@H@Z`
- size: `166`
- prototype: `int(CMDCOM *__hidden this, unsigned int, unsigned __int8 *, struct _FILETIME *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800185a0`
- `0x180018670`

## callees

- `0x180003d30`
- `0x1800185bc`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001864f`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001864f`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800185f9`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800185f9`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDGetLastChangeTimeD(
        CMDCOM *this,
        unsigned int a2,
        char *a3,
        struct _FILETIME *a4,
        int a5)
{
  unsigned int v7; // ebx
  int ObjectFromPath; // eax
  struct CMDBaseObject *v10; // [rsp+40h] [rbp+8h] BYREF
  char *v11; // [rsp+50h] [rbp+18h] BYREF

  v10 = this;
  v11 = a3;
  if ( g_dwInitialized )
  {
    if ( a4 )
    {
      CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
      v10 = 0;
      ObjectFromPath = GetObjectFromPath(&v10, a2, 1, (const CHAR **)&v11, a5);
      v7 = ObjectFromPath;
      if ( ObjectFromPath >= 0 || ObjectFromPath == -2147024893 && v10 )
        *a4 = *(struct _FILETIME *)((char *)v10 + 224);
      CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
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
  return v7;
}

```

## disassembly

```asm
0x1800185bc  mov     [rsp+arg_8], rbx
0x1800185c1  mov     [rsp+arg_0], rcx
0x1800185c6  push    rdi
0x1800185c7  sub     rsp, 30h
0x1800185cb  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x1800185d1  mov     rdi, r9
0x1800185d4  mov     [rsp+38h+arg_10], r8
0x1800185d9  mov     ebx, edx
0x1800185db  test    eax, eax
0x1800185dd  jnz     short loc_1800185E6
0x1800185df  mov     ebx, 800CC800h
0x1800185e4  jmp     short loc_180018655
0x1800185e6  test    rdi, rdi
0x1800185e9  jnz     short loc_1800185F2
0x1800185eb  mov     ebx, 80070057h
0x1800185f0  jmp     short loc_180018655
0x1800185f2  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x1800185f9  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800185ff  mov     eax, [rsp+38h+arg_20]
0x180018603  lea     r9, [rsp+38h+arg_10]; char **
0x180018608  mov     r8d, 1; unsigned int
0x18001860e  mov     [rsp+38h+var_18], eax; int
0x180018612  mov     edx, ebx; unsigned int
0x180018614  mov     [rsp+38h+arg_0], 0
0x18001861d  lea     rcx, [rsp+38h+arg_0]; struct CMDBaseObject **
0x180018622  call    ?GetObjectFromPath@@YAJAEAPEAVCMDBaseObject@@KKAEAPEADH@Z; GetObjectFromPath(CMDBaseObject * &,ulong,ulong,char * &,int)
0x180018627  mov     rdx, [rsp+38h+arg_0]
0x18001862c  mov     ebx, eax
0x18001862e  test    eax, eax
0x180018630  jns     short loc_18001863E
0x180018632  cmp     eax, 80070003h
0x180018637  jnz     short loc_180018648
0x180018639  test    rdx, rdx
0x18001863c  jz      short loc_180018648
0x18001863e  mov     rdx, [rdx+0E0h]
0x180018645  mov     [rdi], rdx
0x180018648  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001864f  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180018655  mov     eax, ebx
0x180018657  mov     rbx, [rsp+38h+arg_8]
0x18001865c  add     rsp, 30h
0x180018660  pop     rdi
0x180018661  retn
```
