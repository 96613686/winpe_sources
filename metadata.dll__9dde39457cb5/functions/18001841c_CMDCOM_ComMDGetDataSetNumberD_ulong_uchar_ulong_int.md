# CMDCOM::ComMDGetDataSetNumberD(ulong,uchar *,ulong *,int)

- ea: `0x18001841c`
- end: `0x1800184ef`
- name: `?ComMDGetDataSetNumberD@CMDCOM@@QEAAJKPEAEPEAKH@Z`
- size: `211`
- prototype: `int(CMDCOM *__hidden this, unsigned int, unsigned __int8 *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018400`
- `0x180018500`

## callees

- `0x180003d30`
- `0x18001841c`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800184dc`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800184dc`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001845f`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001845f`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDGetDataSetNumberD(CMDCOM *this, unsigned int a2, char *a3, unsigned int *a4, int a5)
{
  unsigned int v7; // ebx
  int ObjectFromPath; // eax
  unsigned int v9; // ecx
  struct CMDBaseObject *v11; // [rsp+40h] [rbp+8h] BYREF
  char *v12; // [rsp+50h] [rbp+18h] BYREF

  v11 = this;
  v12 = a3;
  if ( g_dwInitialized )
  {
    if ( a4 )
    {
      CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
      v11 = 0;
      ObjectFromPath = GetObjectFromPath(&v11, a2, 1, (const CHAR **)&v12, a5);
      v7 = ObjectFromPath;
      if ( ObjectFromPath < 0 )
      {
        if ( ObjectFromPath == -2147024893 && v11 )
        {
          v9 = *((_DWORD *)v11 + 52);
          if ( *((_QWORD *)v11 + 27) )
            ++v9;
          *a4 = v9;
          v7 = 0;
        }
      }
      else if ( v11 )
      {
        *a4 = *((_DWORD *)v11 + 52);
      }
      else
      {
        v7 = -2147467259;
      }
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
0x18001841c  mov     [rsp+arg_8], rbx
0x180018421  mov     [rsp+arg_0], rcx
0x180018426  push    rdi
0x180018427  sub     rsp, 30h
0x18001842b  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180018431  mov     rdi, r9
0x180018434  mov     [rsp+38h+arg_10], r8
0x180018439  mov     ebx, edx
0x18001843b  test    eax, eax
0x18001843d  jnz     short loc_180018449
0x18001843f  mov     ebx, 800CC800h
0x180018444  jmp     loc_1800184E2
0x180018449  test    rdi, rdi
0x18001844c  jnz     short loc_180018458
0x18001844e  mov     ebx, 80070057h
0x180018453  jmp     loc_1800184E2
0x180018458  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001845f  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180018465  mov     eax, [rsp+38h+arg_20]
0x180018469  lea     r9, [rsp+38h+arg_10]; char **
0x18001846e  mov     r8d, 1; unsigned int
0x180018474  mov     [rsp+38h+var_18], eax; int
0x180018478  mov     edx, ebx; unsigned int
0x18001847a  mov     [rsp+38h+arg_0], 0
0x180018483  lea     rcx, [rsp+38h+arg_0]; struct CMDBaseObject **
0x180018488  call    ?GetObjectFromPath@@YAJAEAPEAVCMDBaseObject@@KKAEAPEADH@Z; GetObjectFromPath(CMDBaseObject * &,ulong,ulong,char * &,int)
0x18001848d  mov     ebx, eax
0x18001848f  test    eax, eax
0x180018491  js      short loc_1800184AE
0x180018493  mov     rax, [rsp+38h+arg_0]
0x180018498  test    rax, rax
0x18001849b  jnz     short loc_1800184A4
0x18001849d  mov     ebx, 80004005h
0x1800184a2  jmp     short loc_1800184D5
0x1800184a4  mov     eax, [rax+0D0h]
0x1800184aa  mov     [rdi], eax
0x1800184ac  jmp     short loc_1800184D5
0x1800184ae  cmp     eax, 80070003h
0x1800184b3  jnz     short loc_1800184D5
0x1800184b5  mov     rax, [rsp+38h+arg_0]
0x1800184ba  test    rax, rax
0x1800184bd  jz      short loc_1800184D5
0x1800184bf  cmp     qword ptr [rax+0D8h], 0
0x1800184c7  mov     ecx, [rax+0D0h]
0x1800184cd  jbe     short loc_1800184D1
0x1800184cf  inc     ecx
0x1800184d1  mov     [rdi], ecx
0x1800184d3  xor     ebx, ebx
0x1800184d5  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x1800184dc  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800184e2  mov     eax, ebx
0x1800184e4  mov     rbx, [rsp+38h+arg_8]
0x1800184e9  add     rsp, 30h
0x1800184ed  pop     rdi
0x1800184ee  retn
```
