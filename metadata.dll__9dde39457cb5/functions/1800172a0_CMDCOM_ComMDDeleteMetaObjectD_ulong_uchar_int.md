# CMDCOM::ComMDDeleteMetaObjectD(ulong,uchar *,int)

- ea: `0x1800172a0`
- end: `0x180017339`
- name: `?ComMDDeleteMetaObjectD@CMDCOM@@QEAAJKPEAEH@Z`
- size: `153`
- prototype: `int(CMDCOM *__hidden this, unsigned int, unsigned __int8 *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017290`
- `0x180017340`

## callees

- `0x180002d60`
- `0x1800172a0`
- `0x18001a0d0`
- `0x180022ed8`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180017326`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180017326`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800172d7`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800172d7`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDDeleteMetaObjectD(CMDCOM *this, unsigned int a2, char *a3, int a4)
{
  int v7; // ebx
  struct CMDHandle *HandleObject; // rax
  struct CMDHandle *v9; // rsi

  if ( g_dwInitialized )
  {
    if ( a3 )
    {
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
      HandleObject = GetHandleObject(a2);
      v9 = HandleObject;
      if ( HandleObject )
      {
        v7 = RemoveObjectFromDataBase(a2, HandleObject, a3, a4);
        if ( v7 >= 0 )
        {
          ++*(_DWORD *)&g_dwSystemChangeNumber;
          INCREMENT_SCHEMA_CHANGE_NUMBER(a2, v9, a3, a4);
        }
      }
      else
      {
        v7 = -2147024890;
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
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800172a0  push    rbx
0x1800172a2  push    rbp
0x1800172a3  push    rsi
0x1800172a4  push    rdi
0x1800172a5  push    r14
0x1800172a7  sub     rsp, 20h
0x1800172ab  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x1800172b1  mov     r14d, r9d
0x1800172b4  mov     rdi, r8
0x1800172b7  mov     ebp, edx
0x1800172b9  test    eax, eax
0x1800172bb  jnz     short loc_1800172C4
0x1800172bd  mov     ebx, 800CC800h
0x1800172c2  jmp     short loc_18001732C
0x1800172c4  test    rdi, rdi
0x1800172c7  jnz     short loc_1800172D0
0x1800172c9  mov     ebx, 80070057h
0x1800172ce  jmp     short loc_18001732C
0x1800172d0  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x1800172d7  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800172dd  mov     ecx, ebp; unsigned int
0x1800172df  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x1800172e4  mov     rsi, rax
0x1800172e7  test    rax, rax
0x1800172ea  jz      short loc_18001731A
0x1800172ec  mov     r9d, r14d; int
0x1800172ef  mov     r8, rdi; char *
0x1800172f2  mov     rdx, rax; struct CMDHandle *
0x1800172f5  mov     ecx, ebp; unsigned int
0x1800172f7  call    ?RemoveObjectFromDataBase@@YAJKPEAVCMDHandle@@PEADH@Z; RemoveObjectFromDataBase(ulong,CMDHandle *,char *,int)
0x1800172fc  mov     ebx, eax
0x1800172fe  test    eax, eax
0x180017300  js      short loc_18001731F
0x180017302  inc     cs:?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x180017308  mov     r9d, r14d; int
0x18001730b  mov     r8, rdi; char *
0x18001730e  mov     rdx, rsi; struct CMDHandle *
0x180017311  mov     ecx, ebp; unsigned int
0x180017313  call    ?INCREMENT_SCHEMA_CHANGE_NUMBER@@YAXKPEAVCMDHandle@@PEADH@Z; INCREMENT_SCHEMA_CHANGE_NUMBER(ulong,CMDHandle *,char *,int)
0x180017318  jmp     short loc_18001731F
0x18001731a  mov     ebx, 80070006h
0x18001731f  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180017326  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001732c  mov     eax, ebx
0x18001732e  add     rsp, 20h
0x180017332  pop     r14
0x180017334  pop     rdi
0x180017335  pop     rsi
0x180017336  pop     rbp
0x180017337  pop     rbx
0x180017338  retn
```
