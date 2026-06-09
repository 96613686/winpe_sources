# CTSThread::EndProcessingEvents(void)

- ea: `0x180024d20`
- end: `0x180024e24`
- name: `?EndProcessingEvents@CTSThread@@UEAAJXZ`
- size: `260`
- prototype: `__int64 __fastcall(CTSThread *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800010f8`
- `0x18001a5f4`
- `0x180024728`
- `0x180024d20`
- `0x180027b6c`
- `0x180027b98`

## string_xrefs

- `0x180024de2`: `Thread initialized but not running. Bail destroy`

## pseudocode

```c
__int64 __fastcall CTSThread::EndProcessingEvents(CTSThread *this)
{
  CTSReaderWriterLock *v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int v6; // r11d
  const char *v8; // [rsp+40h] [rbp+8h] BYREF

  v2 = (CTSThread *)((char *)this + 148);
  CTSReaderWriterLock::WriteLock((CTSThread *)((char *)this + 148));
  v5 = *((unsigned int *)this + 20);
  if ( (_DWORD)v5 == 1 || (_DWORD)v5 == 6 )
  {
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v8 = "Thread initialized but not running. Bail destroy";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v3,
        (__int64)qword_18003FC78,
        v4,
        v5,
        (const unsigned __int16 **)&v8);
    }
    *((_DWORD *)this + 20) = 6;
  }
  else if ( (unsigned int)(v5 - 2) <= 1 )
  {
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v8 = "Stopping event processing";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v3,
        (__int64)&byte_18003FC57,
        v4,
        v5,
        (const unsigned __int16 **)&v8);
    }
    *((_DWORD *)this + 20) = 6;
    CTSThread::DiscardAllQueueEvents(this);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_903e1551464439edae082eb88b6439cd_Traceguids, v5);
  }
  CTSReaderWriterLock::WriteUnlock(v2);
  return v6;
}

```

## disassembly

```asm
0x180024d20  mov     [rsp+arg_8], rbx
0x180024d25  push    rdi
0x180024d26  sub     rsp, 30h
0x180024d2a  mov     rbx, rcx
0x180024d2d  lea     rdi, [rcx+94h]
0x180024d34  mov     rcx, rdi; this
0x180024d37  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x180024d3c  mov     r9d, [rbx+50h]
0x180024d40  cmp     r9d, 1
0x180024d44  jz      loc_180024DD7
0x180024d4a  cmp     r9d, 6
0x180024d4e  jz      loc_180024DD7
0x180024d54  lea     eax, [r9-2]
0x180024d58  cmp     eax, 1
0x180024d5b  jbe     short loc_180024D99
0x180024d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d64  lea     rax, WPP_GLOBAL_Control
0x180024d6b  cmp     rcx, rax
0x180024d6e  jz      short loc_180024D91
0x180024d70  test    byte ptr [rcx+1Ch], 1
0x180024d74  jz      short loc_180024D91
0x180024d76  cmp     byte ptr [rcx+19h], 1
0x180024d7a  jb      short loc_180024D91
0x180024d7c  mov     rcx, [rcx+10h]
0x180024d80  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180024d87  mov     edx, 27h ; '''
0x180024d8c  call    WPP_SF_D
0x180024d91  mov     r11d, 8000FFFFh
0x180024d97  jmp     short loc_180024E0E
0x180024d99  mov     eax, cs:dword_180044008
0x180024d9f  cmp     eax, 4
0x180024da2  jbe     short loc_180024DC6
0x180024da4  lea     rax, aStoppingEventP; "Stopping event processing"
0x180024dab  mov     [rsp+38h+arg_0], rax
0x180024db0  lea     rdx, byte_18003FC57
0x180024db7  lea     rax, [rsp+38h+arg_0]
0x180024dbc  mov     [rsp+38h+var_18], rax
0x180024dc1  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180024dc6  mov     rcx, rbx; this
0x180024dc9  mov     dword ptr [rbx+50h], 6
0x180024dd0  call    ?DiscardAllQueueEvents@CTSThread@@IEAAJXZ; CTSThread::DiscardAllQueueEvents(void)
0x180024dd5  jmp     short loc_180024E0B
0x180024dd7  mov     eax, cs:dword_180044008
0x180024ddd  cmp     eax, 4
0x180024de0  jbe     short loc_180024E04
0x180024de2  lea     rax, aThreadInitiali; "Thread initialized but not running. Bai"...
0x180024de9  mov     [rsp+38h+arg_0], rax
0x180024dee  lea     rdx, qword_18003FC78
0x180024df5  lea     rax, [rsp+38h+arg_0]
0x180024dfa  mov     [rsp+38h+var_18], rax
0x180024dff  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180024e04  mov     dword ptr [rbx+50h], 6
0x180024e0b  xor     r11d, r11d
0x180024e0e  mov     rcx, rdi; this
0x180024e11  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x180024e16  mov     rbx, [rsp+38h+arg_8]
0x180024e1b  mov     eax, r11d
0x180024e1e  add     rsp, 30h
0x180024e22  pop     rdi
0x180024e23  retn
```
