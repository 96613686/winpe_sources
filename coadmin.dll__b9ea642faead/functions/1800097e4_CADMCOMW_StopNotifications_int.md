# CADMCOMW::StopNotifications(int)

- ea: `0x1800097e4`
- end: `0x180009918`
- name: `?StopNotifications@CADMCOMW@@AEAAJH@Z`
- size: `308`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000455c`
- `0x1800068d4`
- `0x18000dba8`

## callees

- `0x1800084a0`
- `0x1800097e4`
- `0x180010010`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009822`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800098b6`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009822`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800098b6`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009814`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000989d`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009814`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000989d`

## pseudocode

```c
__int64 __fastcall CADMCOMW::StopNotifications(CADMCOMW *this, int a2)
{
  __int64 v2; // rsi
  int v3; // ebp
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF

  v2 = *((_QWORD *)this + 11);
  v3 = 0;
  v8 = 0;
  v9 = 0;
  if ( v2 )
  {
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v2 + 20));
    *(_QWORD *)(v2 + 8) = 0;
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v2 + 20));
  }
  if ( *((_DWORD *)this + 24) )
  {
    v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 4);
    if ( v6 )
    {
      v3 = (**v6)(v6, &IID_IConnectionPointContainer, &v8);
      if ( v3 >= 0 )
      {
        v3 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v8 + 32LL))(v8, &IID_IMDCOMSINK_W, &v9);
        if ( v3 >= 0 )
        {
          v3 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 48LL))(v9, *((unsigned int *)this + 24));
          *((_DWORD *)this + 24) = 0;
        }
      }
    }
  }
  CReaderWriterLock3::WriteLock((CADMCOMW *)((char *)this + 848));
  if ( !*((_DWORD *)this + 220) )
    *((_DWORD *)this + 221) = 0;
  CReaderWriterLock3::WriteUnlock((CADMCOMW *)((char *)this + 848));
  if ( a2 )
    CADMCOMW::RemoveAllPendingNotifications(this, 1);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v8 = 0;
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800097e4  mov     rax, rsp
0x1800097e7  mov     [rax+10h], rbx
0x1800097eb  mov     [rax+20h], rbp
0x1800097ef  push    rsi
0x1800097f0  push    rdi
0x1800097f1  push    r14
0x1800097f3  sub     rsp, 20h
0x1800097f7  mov     rsi, [rcx+58h]
0x1800097fb  xor     ebp, ebp
0x1800097fd  mov     [rax+8], rbp
0x180009801  mov     r14d, edx
0x180009804  mov     [rax+18h], rbp
0x180009808  mov     rdi, rcx
0x18000980b  test    rsi, rsi
0x18000980e  jz      short loc_180009828
0x180009810  lea     rcx, [rsi+14h]
0x180009814  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000981a  lea     rcx, [rsi+14h]
0x18000981e  mov     [rsi+8], rbp
0x180009822  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180009828  cmp     [rdi+60h], ebp
0x18000982b  jz      short loc_180009893
0x18000982d  mov     rcx, [rdi+20h]
0x180009831  test    rcx, rcx
0x180009834  jz      short loc_180009893
0x180009836  mov     rax, [rcx]
0x180009839  lea     r8, [rsp+38h+arg_0]
0x18000983e  lea     rdx, IID_IConnectionPointContainer
0x180009845  mov     rax, [rax]
0x180009848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000984d  mov     ebp, eax
0x18000984f  test    eax, eax
0x180009851  js      short loc_180009893
0x180009853  mov     rcx, [rsp+38h+arg_0]
0x180009858  lea     r8, [rsp+38h+arg_10]
0x18000985d  lea     rdx, IID_IMDCOMSINK_W
0x180009864  mov     rax, [rcx]
0x180009867  mov     rax, [rax+20h]
0x18000986b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009870  mov     ebp, eax
0x180009872  test    eax, eax
0x180009874  js      short loc_180009893
0x180009876  mov     rcx, [rsp+38h+arg_10]
0x18000987b  mov     edx, [rdi+60h]
0x18000987e  mov     rax, [rcx]
0x180009881  mov     rax, [rax+30h]
0x180009885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000988a  mov     ebp, eax
0x18000988c  mov     dword ptr [rdi+60h], 0
0x180009893  lea     rbx, [rdi+350h]
0x18000989a  mov     rcx, rbx
0x18000989d  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800098a3  mov     eax, [rdi+370h]
0x1800098a9  test    eax, eax
0x1800098ab  jnz     short loc_1800098B3
0x1800098ad  mov     [rdi+374h], eax
0x1800098b3  mov     rcx, rbx
0x1800098b6  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800098bc  test    r14d, r14d
0x1800098bf  jz      short loc_1800098CE
0x1800098c1  mov     edx, 1; int
0x1800098c6  mov     rcx, rdi; this
0x1800098c9  call    ?RemoveAllPendingNotifications@CADMCOMW@@QEAAJH@Z; CADMCOMW::RemoveAllPendingNotifications(int)
0x1800098ce  mov     rcx, [rsp+38h+arg_0]
0x1800098d3  test    rcx, rcx
0x1800098d6  jz      short loc_1800098ED
0x1800098d8  mov     rax, [rcx]
0x1800098db  mov     rax, [rax+10h]
0x1800098df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098e4  mov     [rsp+38h+arg_0], 0
0x1800098ed  mov     rcx, [rsp+38h+arg_10]
0x1800098f2  test    rcx, rcx
0x1800098f5  jz      short loc_180009903
0x1800098f7  mov     rax, [rcx]
0x1800098fa  mov     rax, [rax+10h]
0x1800098fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009903  mov     rbx, [rsp+38h+arg_8]
0x180009908  mov     eax, ebp
0x18000990a  mov     rbp, [rsp+38h+arg_18]
0x18000990f  add     rsp, 20h
0x180009913  pop     r14
0x180009915  pop     rdi
0x180009916  pop     rsi
0x180009917  retn
```
