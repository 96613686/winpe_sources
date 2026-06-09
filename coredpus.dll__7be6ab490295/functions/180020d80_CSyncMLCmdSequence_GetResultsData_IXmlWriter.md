# CSyncMLCmdSequence::GetResultsData(IXmlWriter *)

- ea: `0x180020d80`
- end: `0x180020ebe`
- name: `?GetResultsData@CSyncMLCmdSequence@@UEAAJPEAUIXmlWriter@@@Z`
- size: `318`
- prototype: `int(CSyncMLCmdSequence *__hidden this, struct IXmlWriter *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180002590`
- `0x180002a00`
- `0x1800034d0`
- `0x180003cd0`
- `0x1800043c0`
- `0x180020d80`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdSequence::GetResultsData(
        const unsigned __int16 **this,
        struct IXmlWriter *a2,
        __int64 a3,
        __int64 a4)
{
  HRESULT v6; // edi
  __int64 v7; // rcx
  unsigned int CmdPreExecHresult; // edi
  int OmadmStatusCode; // esi
  int v10; // ebp
  const unsigned __int16 *ElementName; // rcx
  int v12; // r8d
  __int64 v13; // rbp
  __int64 v14; // rsi
  __int64 v15; // rcx
  HRESULT v17; // [rsp+88h] [rbp+10h] BYREF

  if ( a2 )
  {
    CmdPreExecHresult = CSyncMLCmd::GetCmdPreExecHresult((CSyncMLCmd *)this);
    OmadmStatusCode = GetOmadmStatusCode(CmdPreExecHresult, *(unsigned int *)(v7 + 92), 0, 0);
    v10 = *((_DWORD *)this[10] + 11);
    if ( *((_DWORD *)this + 23) == 73 )
      ElementName = this[14];
    else
      ElementName = (const unsigned __int16 *)GetElementName(*((unsigned int *)this + 23));
    v12 = CSyncMLDPU::s_dwCurrClientCmdID++;
    v6 = AddStatus(
           a2,
           OmadmStatusCode,
           v12,
           CSyncMLDPU::s_dwCurrServerMsgID,
           this[13],
           ElementName,
           0,
           0,
           0,
           0,
           CmdPreExecHresult,
           v10);
    if ( v6 >= 0 )
    {
      v13 = 0;
      v14 = ((char *)this[5] - (char *)this[4]) >> 3;
      if ( (int)v14 > 0 )
      {
        do
        {
          v15 = *(_QWORD *)&this[4][4 * v13];
          v6 = (*(__int64 (__fastcall **)(__int64, struct IXmlWriter *))(*(_QWORD *)v15 + 32LL))(v15, a2);
          if ( v6 < 0 )
            break;
          v13 = (unsigned int)(v13 + 1);
        }
        while ( (int)v13 < (int)v14 );
      }
    }
  }
  else
  {
    v6 = -2147467261;
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v17 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)qword_1800367F0,
      a3,
      a4,
      (__int64)&v17);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180020d80  mov     [rsp+arg_0], rbx
0x180020d85  mov     [rsp+arg_10], rbp
0x180020d8a  push    rsi
0x180020d8b  push    rdi
0x180020d8c  push    r14
0x180020d8e  sub     rsp, 60h
0x180020d92  mov     r14, rdx
0x180020d95  mov     rbx, rcx
0x180020d98  test    rdx, rdx
0x180020d9b  jnz     short loc_180020DA7
0x180020d9d  mov     edi, 80004003h
0x180020da2  jmp     loc_180020E74
0x180020da7  call    ?GetCmdPreExecHresult@CSyncMLCmd@@QEBAJXZ; CSyncMLCmd::GetCmdPreExecHresult(void)
0x180020dac  mov     edx, [rcx+5Ch]
0x180020daf  xor     r9d, r9d
0x180020db2  mov     ecx, eax
0x180020db4  xor     r8d, r8d
0x180020db7  mov     edi, eax
0x180020db9  call    GetOmadmStatusCode
0x180020dbe  cmp     dword ptr [rbx+5Ch], 49h ; 'I'
0x180020dc2  mov     esi, eax
0x180020dc4  mov     rax, [rbx+50h]
0x180020dc8  mov     ebp, [rax+2Ch]
0x180020dcb  jnz     short loc_180020DD3
0x180020dcd  mov     rcx, [rbx+70h]
0x180020dd1  jmp     short loc_180020DDE
0x180020dd3  mov     ecx, [rbx+5Ch]
0x180020dd6  call    GetElementName
0x180020ddb  mov     rcx, rax
0x180020dde  mov     r8d, cs:?s_dwCurrClientCmdID@CSyncMLDPU@@0KA; unsigned int
0x180020de5  mov     edx, esi; unsigned int
0x180020de7  mov     r9d, cs:?s_dwCurrServerMsgID@CSyncMLDPU@@0KA; unsigned int
0x180020dee  mov     [rsp+78h+var_20], ebp; int
0x180020df2  mov     [rsp+78h+var_28], edi; int
0x180020df6  mov     [rsp+78h+var_30], 0; unsigned int
0x180020dfe  lea     eax, [r8+1]
0x180020e02  mov     [rsp+78h+var_38], 0; struct CSyncMLItem **
0x180020e0b  mov     [rsp+78h+var_40], 0; unsigned __int16 *
0x180020e14  mov     cs:?s_dwCurrClientCmdID@CSyncMLDPU@@0KA, eax; ulong CSyncMLDPU::s_dwCurrClientCmdID
0x180020e1a  mov     rax, [rbx+68h]
0x180020e1e  mov     [rsp+78h+var_48], 0; unsigned __int16 *
0x180020e27  mov     [rsp+78h+var_50], rcx; unsigned __int16 *
0x180020e2c  mov     rcx, r14; struct IXmlWriter *
0x180020e2f  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x180020e34  call    ?AddStatus@@YAJPEAUIXmlWriter@@KKKPEBG111PEAPEAVCSyncMLItem@@KJH@Z; AddStatus(IXmlWriter *,ulong,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,CSyncMLItem * *,ulong,long,int)
0x180020e39  mov     edi, eax
0x180020e3b  test    eax, eax
0x180020e3d  js      short loc_180020E74
0x180020e3f  mov     rsi, [rbx+28h]
0x180020e43  xor     ebp, ebp
0x180020e45  sub     rsi, [rbx+20h]
0x180020e49  sar     rsi, 3
0x180020e4d  test    esi, esi
0x180020e4f  jle     short loc_180020E74
0x180020e51  mov     rax, [rbx+20h]
0x180020e55  mov     rdx, r14
0x180020e58  mov     rcx, [rax+rbp*8]
0x180020e5c  mov     rax, [rcx]
0x180020e5f  mov     rax, [rax+20h]
0x180020e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e68  mov     edi, eax
0x180020e6a  test    eax, eax
0x180020e6c  js      short loc_180020E74
0x180020e6e  inc     ebp
0x180020e70  cmp     ebp, esi
0x180020e72  jl      short loc_180020E51
0x180020e74  mov     eax, cs:dword_18003E048
0x180020e7a  cmp     eax, 5
0x180020e7d  jbe     short loc_180020EA6
0x180020e7f  lea     rax, [rsp+78h+arg_8]
0x180020e87  mov     [rsp+78h+arg_8], edi
0x180020e8e  lea     rdx, qword_1800367F0
0x180020e95  mov     [rsp+78h+var_58], rax
0x180020e9a  lea     rcx, dword_18003E048
0x180020ea1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180020ea6  lea     r11, [rsp+78h+var_18]
0x180020eab  mov     eax, edi
0x180020ead  mov     rbx, [r11+20h]
0x180020eb1  mov     rbp, [r11+30h]
0x180020eb5  mov     rsp, r11
0x180020eb8  pop     r14
0x180020eba  pop     rdi
0x180020ebb  pop     rsi
0x180020ebc  retn
```
