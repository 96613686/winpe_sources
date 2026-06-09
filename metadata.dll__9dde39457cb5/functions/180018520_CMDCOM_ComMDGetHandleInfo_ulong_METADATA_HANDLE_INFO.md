# CMDCOM::ComMDGetHandleInfo(ulong,_METADATA_HANDLE_INFO *)

- ea: `0x180018520`
- end: `0x180018593`
- name: `?ComMDGetHandleInfo@CMDCOM@@UEAAJKPEAU_METADATA_HANDLE_INFO@@@Z`
- size: `115`
- prototype: `int(CMDCOM *__hidden this, unsigned int, struct _METADATA_HANDLE_INFO *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002d60`
- `0x180018520`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180018580`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180018580`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180018553`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180018553`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDGetHandleInfo(CMDCOM *this, unsigned int a2, struct _METADATA_HANDLE_INFO *a3)
{
  unsigned int v5; // ebx
  struct CMDHandle *HandleObject; // rax

  if ( g_dwInitialized )
  {
    if ( a3 )
    {
      CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
      HandleObject = GetHandleObject(a2);
      if ( HandleObject )
      {
        v5 = 0;
        a3->dwMDPermissions = *((_DWORD *)HandleObject + 3);
        a3->dwMDSystemChangeNumber = *((_DWORD *)HandleObject + 4);
      }
      else
      {
        v5 = -2147024890;
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
  return v5;
}

```

## disassembly

```asm
0x180018520  mov     [rsp+arg_0], rbx
0x180018525  push    rdi
0x180018526  sub     rsp, 20h
0x18001852a  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180018530  mov     rdi, r8
0x180018533  mov     ebx, edx
0x180018535  test    eax, eax
0x180018537  jnz     short loc_180018540
0x180018539  mov     ebx, 800CC800h
0x18001853e  jmp     short loc_180018586
0x180018540  test    rdi, rdi
0x180018543  jnz     short loc_18001854C
0x180018545  mov     ebx, 80070057h
0x18001854a  jmp     short loc_180018586
0x18001854c  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180018553  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180018559  mov     ecx, ebx; unsigned int
0x18001855b  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x180018560  test    rax, rax
0x180018563  jnz     short loc_18001856C
0x180018565  mov     ebx, 80070006h
0x18001856a  jmp     short loc_180018579
0x18001856c  mov     edx, [rax+0Ch]
0x18001856f  xor     ebx, ebx
0x180018571  mov     [rdi], edx
0x180018573  mov     edx, [rax+10h]
0x180018576  mov     [rdi+4], edx
0x180018579  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180018580  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180018586  mov     eax, ebx
0x180018588  mov     rbx, [rsp+28h+arg_0]
0x18001858d  add     rsp, 20h
0x180018591  pop     rdi
0x180018592  retn
```
