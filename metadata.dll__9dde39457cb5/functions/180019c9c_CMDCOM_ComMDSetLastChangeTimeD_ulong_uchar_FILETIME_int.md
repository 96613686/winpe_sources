# CMDCOM::ComMDSetLastChangeTimeD(ulong,uchar *,_FILETIME *,int)

- ea: `0x180019c9c`
- end: `0x180019d41`
- name: `?ComMDSetLastChangeTimeD@CMDCOM@@QEAAJKPEAEPEAU_FILETIME@@H@Z`
- size: `165`
- prototype: `int(CMDCOM *__hidden this, unsigned int, unsigned __int8 *, struct _FILETIME *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019c80`
- `0x180019d50`

## callees

- `0x180003d30`
- `0x180015808`
- `0x180019c9c`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180019d2e`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180019d2e`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180019ce1`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180019ce1`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDSetLastChangeTimeD(
        CMDCOM *this,
        unsigned int a2,
        char *a3,
        struct _FILETIME *a4,
        int a5)
{
  int ObjectFromPath; // ebx
  CMDBaseObject *v9; // [rsp+40h] [rbp+8h] BYREF
  char *v10; // [rsp+50h] [rbp+18h] BYREF

  v10 = a3;
  v9 = 0;
  if ( g_dwInitialized )
  {
    if ( a4 )
    {
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
      ObjectFromPath = GetObjectFromPath(&v9, a2, 2, (const CHAR **)&v10, a5);
      if ( ObjectFromPath >= 0 )
      {
        if ( v9 )
        {
          CMDBaseObject::SetLastChangeTime(v9, a4);
          ObjectFromPath = 0;
        }
        else
        {
          ObjectFromPath = -2147024893;
        }
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
  return (unsigned int)ObjectFromPath;
}

```

## disassembly

```asm
0x180019c9c  mov     rax, rsp
0x180019c9f  mov     [rax+10h], rbx
0x180019ca3  mov     [rax+8], rcx
0x180019ca7  push    rdi
0x180019ca8  sub     rsp, 30h
0x180019cac  mov     [rax+18h], r8
0x180019cb0  mov     rdi, r9
0x180019cb3  mov     qword ptr [rax+8], 0
0x180019cbb  mov     ebx, edx
0x180019cbd  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180019cc3  test    eax, eax
0x180019cc5  jnz     short loc_180019CCE
0x180019cc7  mov     ebx, 800CC800h
0x180019ccc  jmp     short loc_180019D34
0x180019cce  test    rdi, rdi
0x180019cd1  jnz     short loc_180019CDA
0x180019cd3  mov     ebx, 80070057h
0x180019cd8  jmp     short loc_180019D34
0x180019cda  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180019ce1  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180019ce7  mov     eax, [rsp+38h+arg_20]
0x180019ceb  lea     r9, [rsp+38h+arg_10]; char **
0x180019cf0  mov     r8d, 2; unsigned int
0x180019cf6  mov     [rsp+38h+var_18], eax; int
0x180019cfa  mov     edx, ebx; unsigned int
0x180019cfc  lea     rcx, [rsp+38h+arg_0]; struct CMDBaseObject **
0x180019d01  call    ?GetObjectFromPath@@YAJAEAPEAVCMDBaseObject@@KKAEAPEADH@Z; GetObjectFromPath(CMDBaseObject * &,ulong,ulong,char * &,int)
0x180019d06  mov     ebx, eax
0x180019d08  test    eax, eax
0x180019d0a  js      short loc_180019D27
0x180019d0c  mov     rcx, [rsp+38h+arg_0]; this
0x180019d11  test    rcx, rcx
0x180019d14  jnz     short loc_180019D1D
0x180019d16  mov     ebx, 80070003h
0x180019d1b  jmp     short loc_180019D27
0x180019d1d  mov     rdx, rdi; struct _FILETIME *
0x180019d20  call    ?SetLastChangeTime@CMDBaseObject@@QEAAXPEAU_FILETIME@@@Z; CMDBaseObject::SetLastChangeTime(_FILETIME *)
0x180019d25  xor     ebx, ebx
0x180019d27  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180019d2e  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180019d34  mov     eax, ebx
0x180019d36  mov     rbx, [rsp+38h+arg_8]
0x180019d3b  add     rsp, 30h
0x180019d3f  pop     rdi
0x180019d40  retn
```
