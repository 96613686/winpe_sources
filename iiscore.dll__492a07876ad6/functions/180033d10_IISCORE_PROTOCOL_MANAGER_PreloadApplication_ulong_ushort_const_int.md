# IISCORE_PROTOCOL_MANAGER::PreloadApplication(ulong,ushort const *,int)

- ea: `0x180033d10`
- end: `0x180033e1d`
- name: `?PreloadApplication@IISCORE_PROTOCOL_MANAGER@@UEAAJKPEBGH@Z`
- size: `269`
- prototype: `int(IISCORE_PROTOCOL_MANAGER *__hidden this, unsigned int, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001e64c`
- `0x1800338ac`
- `0x180033d10`

## import_xrefs

- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180033dcf`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180033dcf`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180033d4a`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180033d4a`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180033d6e`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180033d82`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180033d6e`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180033d82`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180033def`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180033def`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180033d3b`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180033e05`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180033d3b`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180033e05`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180033d26`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180033d91`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180033d26`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180033d91`

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
0x180033d10  push    rbx
0x180033d12  push    rbp
0x180033d13  push    rsi
0x180033d14  push    rdi
0x180033d15  sub     rsp, 38h
0x180033d19  lea     rbx, [rcx+48h]
0x180033d1d  mov     rsi, rcx
0x180033d20  mov     rcx, rbx
0x180033d23  mov     ebp, r9d
0x180033d26  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180033d2d  nop     dword ptr [rax+rax+00h]
0x180033d32  cmp     dword ptr [rsi+44h], 0
0x180033d36  jnz     short loc_180033D9D
0x180033d38  mov     rcx, rbx
0x180033d3b  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180033d42  nop     dword ptr [rax+rax+00h]
0x180033d47  mov     rcx, rbx
0x180033d4a  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180033d51  nop     dword ptr [rax+rax+00h]
0x180033d56  cmp     dword ptr [rsi+44h], 0
0x180033d5a  jnz     short loc_180033D7F
0x180033d5c  lea     rcx, [rsi-20h]; this
0x180033d60  call    ?InitializeGlobals@IISCORE_PROTOCOL_MANAGER@@QEAAJXZ; IISCORE_PROTOCOL_MANAGER::InitializeGlobals(void)
0x180033d65  mov     edi, eax
0x180033d67  test    eax, eax
0x180033d69  jns     short loc_180033D7F
0x180033d6b  mov     rcx, rbx
0x180033d6e  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180033d75  nop     dword ptr [rax+rax+00h]
0x180033d7a  jmp     loc_180033E11
0x180033d7f  mov     rcx, rbx
0x180033d82  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180033d89  nop     dword ptr [rax+rax+00h]
0x180033d8e  mov     rcx, rbx
0x180033d91  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180033d98  nop     dword ptr [rax+rax+00h]
0x180033d9d  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180033da5  jz      short loc_180033DFD
0x180033da7  mov     edx, ebp; int
0x180033da9  call    ?NotifyApplicationPreload@W3_SERVER@@QEAAJH@Z; W3_SERVER::NotifyApplicationPreload(int)
0x180033dae  mov     edi, eax
0x180033db0  test    eax, eax
0x180033db2  jns     short loc_180033E02
0x180033db4  cmp     dword ptr [rsi+40h], 0
0x180033db8  lea     rax, aW3svcWp; "W3SVC-WP"
0x180033dbf  lea     rdx, aHostablewebcor; "HostableWebCore"
0x180033dc6  cmovz   rdx, rax
0x180033dca  lea     rcx, [rsp+58h+arg_0]
0x180033dcf  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x180033dd6  nop     dword ptr [rax+rax+00h]
0x180033ddb  xor     r8d, r8d
0x180033dde  mov     [rsp+58h+var_38], edi
0x180033de2  xor     r9d, r9d
0x180033de5  lea     rcx, [rsp+58h+arg_0]
0x180033dea  mov     edx, 800008FDh
0x180033def  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180033df6  nop     dword ptr [rax+rax+00h]
0x180033dfb  jmp     short loc_180033E02
0x180033dfd  mov     edi, 80004005h
0x180033e02  mov     rcx, rbx
0x180033e05  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180033e0c  nop     dword ptr [rax+rax+00h]
0x180033e11  mov     eax, edi
0x180033e13  add     rsp, 38h
0x180033e17  pop     rdi
0x180033e18  pop     rsi
0x180033e19  pop     rbp
0x180033e1a  pop     rbx
0x180033e1b  retn
```
