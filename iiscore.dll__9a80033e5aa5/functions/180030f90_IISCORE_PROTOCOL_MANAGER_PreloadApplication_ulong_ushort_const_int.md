# IISCORE_PROTOCOL_MANAGER::PreloadApplication(ulong,ushort const *,int)

- ea: `0x180030f90`
- end: `0x180031063`
- name: `?PreloadApplication@IISCORE_PROTOCOL_MANAGER@@UEAAJKPEBGH@Z`
- size: `211`
- prototype: `int(IISCORE_PROTOCOL_MANAGER *__hidden this, unsigned int, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001ccec`
- `0x180030bac`
- `0x180030f90`

## import_xrefs

- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180031028`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180031028`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180030fbe`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180030fbe`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180030fdc`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180030fe7`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180030fdc`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180030fe7`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180031042`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180031042`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180030fb5`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180031052`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180030fb5`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180031052`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180030fa6`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180030ff0`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180030fa6`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180030ff0`

## pseudocode

```c
__int64 __fastcall IISCORE_PROTOCOL_MANAGER::PreloadApplication(
        IISCORE_PROTOCOL_MANAGER *this,
        __int64 a2,
        const unsigned __int16 *a3,
        int a4)
{
  CReaderWriterLock3 *v4; // rbx
  W3_SERVER *v7; // rcx
  signed int v8; // edi
  const unsigned __int16 *v9; // rdx
  char v11; // [rsp+60h] [rbp+8h] BYREF

  v4 = (IISCORE_PROTOCOL_MANAGER *)((char *)this + 72);
  CReaderWriterLock3::ReadLock((IISCORE_PROTOCOL_MANAGER *)((char *)this + 72));
  if ( !*((_DWORD *)this + 17) )
  {
    CReaderWriterLock3::ReadUnlock(v4);
    CReaderWriterLock3::WriteLock(v4);
    if ( !*((_DWORD *)this + 17) )
    {
      v8 = IISCORE_PROTOCOL_MANAGER::InitializeGlobals((IISCORE_PROTOCOL_MANAGER *)((char *)this - 32));
      if ( v8 < 0 )
      {
        CReaderWriterLock3::WriteUnlock(v4);
        return (unsigned int)v8;
      }
    }
    CReaderWriterLock3::WriteUnlock(v4);
    CReaderWriterLock3::ReadLock(v4);
  }
  if ( g_pW3Server )
  {
    v8 = W3_SERVER::NotifyApplicationPreload(v7, a4);
    if ( v8 < 0 )
    {
      v9 = L"HostableWebCore";
      if ( !*((_DWORD *)this + 16) )
        v9 = L"W3SVC-WP";
      EVENT_LOG::EVENT_LOG((EVENT_LOG *)&v11, v9);
      EVENT_LOG::LogEvent((EVENT_LOG *)&v11, 0x800008FD, 0, 0, v8);
    }
  }
  else
  {
    v8 = -2147467259;
  }
  CReaderWriterLock3::ReadUnlock(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180030f90  push    rbx
0x180030f92  push    rbp
0x180030f93  push    rsi
0x180030f94  push    rdi
0x180030f95  sub     rsp, 38h
0x180030f99  lea     rbx, [rcx+48h]
0x180030f9d  mov     rsi, rcx
0x180030fa0  mov     rcx, rbx
0x180030fa3  mov     ebp, r9d
0x180030fa6  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180030fac  cmp     dword ptr [rsi+44h], 0
0x180030fb0  jnz     short loc_180030FF6
0x180030fb2  mov     rcx, rbx
0x180030fb5  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180030fbb  mov     rcx, rbx
0x180030fbe  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180030fc4  cmp     dword ptr [rsi+44h], 0
0x180030fc8  jnz     short loc_180030FE4
0x180030fca  lea     rcx, [rsi-20h]; this
0x180030fce  call    ?InitializeGlobals@IISCORE_PROTOCOL_MANAGER@@QEAAJXZ; IISCORE_PROTOCOL_MANAGER::InitializeGlobals(void)
0x180030fd3  mov     edi, eax
0x180030fd5  test    eax, eax
0x180030fd7  jns     short loc_180030FE4
0x180030fd9  mov     rcx, rbx
0x180030fdc  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180030fe2  jmp     short loc_180031058
0x180030fe4  mov     rcx, rbx
0x180030fe7  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180030fed  mov     rcx, rbx
0x180030ff0  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180030ff6  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180030ffe  jz      short loc_18003104A
0x180031000  mov     edx, ebp; int
0x180031002  call    ?NotifyApplicationPreload@W3_SERVER@@QEAAJH@Z; W3_SERVER::NotifyApplicationPreload(int)
0x180031007  mov     edi, eax
0x180031009  test    eax, eax
0x18003100b  jns     short loc_18003104F
0x18003100d  cmp     dword ptr [rsi+40h], 0
0x180031011  lea     rax, aW3svcWp; "W3SVC-WP"
0x180031018  lea     rdx, aHostablewebcor; "HostableWebCore"
0x18003101f  cmovz   rdx, rax
0x180031023  lea     rcx, [rsp+58h+arg_0]
0x180031028  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x18003102e  xor     r8d, r8d
0x180031031  mov     [rsp+58h+var_38], edi
0x180031035  xor     r9d, r9d
0x180031038  lea     rcx, [rsp+58h+arg_0]
0x18003103d  mov     edx, 800008FDh
0x180031042  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180031048  jmp     short loc_18003104F
0x18003104a  mov     edi, 80004005h
0x18003104f  mov     rcx, rbx
0x180031052  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180031058  mov     eax, edi
0x18003105a  add     rsp, 38h
0x18003105e  pop     rdi
0x18003105f  pop     rsi
0x180031060  pop     rbp
0x180031061  pop     rbx
0x180031062  retn
```
