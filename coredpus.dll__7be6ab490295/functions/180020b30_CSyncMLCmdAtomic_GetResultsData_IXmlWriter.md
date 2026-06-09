# CSyncMLCmdAtomic::GetResultsData(IXmlWriter *)

- ea: `0x180020b30`
- end: `0x180020cc4`
- name: `?GetResultsData@CSyncMLCmdAtomic@@UEAAJPEAUIXmlWriter@@@Z`
- size: `404`
- prototype: `int(CSyncMLCmdAtomic *__hidden this, struct IXmlWriter *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002590`
- `0x180002a00`
- `0x1800034d0`
- `0x180003cd0`
- `0x1800043c0`
- `0x180020798`
- `0x180020b30`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdAtomic::GetResultsData(
        CSyncMLCmdAtomic *this,
        struct IXmlWriter *a2,
        __int64 a3,
        __int64 a4)
{
  HRESULT v6; // esi
  unsigned int v7; // r14d
  __int64 v8; // rdi
  unsigned int CmdPreExecHresult; // ebp
  __int64 v10; // rsi
  int v11; // eax
  CSyncMLCmd *v12; // rcx
  int OmadmStatusCode; // esi
  int v14; // r14d
  const unsigned __int16 *ElementName; // rcx
  int v16; // r8d
  __int64 i; // rbp
  __int64 v18; // rcx
  int v20; // [rsp+A8h] [rbp+10h] BYREF

  if ( a2 )
  {
    v7 = 0;
    v8 = (__int64)(*((_QWORD *)this + 5) - *((_QWORD *)this + 4)) >> 3;
    CmdPreExecHresult = CSyncMLCmd::GetCmdPreExecHresult(this);
    if ( (CmdPreExecHresult & 0x80000000) == 0 )
    {
      v10 = 0;
      if ( (int)v8 > 0 )
      {
        while ( 1 )
        {
          v11 = CSyncMLCmd::GetCmdPreExecHresult(*(CSyncMLCmd **)(*((_QWORD *)this + 4) + 8 * v10));
          v20 = v11;
          if ( v11 < 0 )
            break;
          if ( (unsigned int)CSyncMLCmd::GetFirstFailedItemHresult(v12, &v20) )
          {
            v11 = v20;
            break;
          }
          v10 = (unsigned int)(v10 + 1);
          if ( (int)v10 >= (int)v8 )
          {
            v11 = v20;
            goto LABEL_11;
          }
        }
        v7 = 1;
LABEL_11:
        if ( v11 < 0 )
        {
          CmdPreExecHresult = v11;
          if ( *((int *)this + 15) >= 0 )
            *((_DWORD *)this + 15) = v11;
        }
      }
    }
    OmadmStatusCode = GetOmadmStatusCode(CmdPreExecHresult, *((unsigned int *)this + 23), v7, CmdPreExecHresult);
    v14 = *(_DWORD *)(*((_QWORD *)this + 10) + 44LL);
    if ( *((_DWORD *)this + 23) == 73 )
      ElementName = (const unsigned __int16 *)*((_QWORD *)this + 14);
    else
      ElementName = (const unsigned __int16 *)GetElementName(*((unsigned int *)this + 23));
    v16 = CSyncMLDPU::s_dwCurrClientCmdID++;
    v6 = AddStatus(
           a2,
           OmadmStatusCode,
           v16,
           CSyncMLDPU::s_dwCurrServerMsgID,
           *((const unsigned __int16 **)this + 13),
           ElementName,
           0,
           0,
           0,
           0,
           CmdPreExecHresult,
           v14);
    if ( v6 >= 0 )
    {
      for ( i = 0; (int)i < (int)v8; i = (unsigned int)(i + 1) )
      {
        v18 = *(_QWORD *)(*((_QWORD *)this + 4) + 8 * i);
        v6 = (*(__int64 (__fastcall **)(__int64, struct IXmlWriter *))(*(_QWORD *)v18 + 32LL))(v18, a2);
        if ( v6 < 0 )
          break;
      }
    }
  }
  else
  {
    v6 = -2147467261;
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v20 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)&byte_180036F1F,
      a3,
      a4,
      (__int64)&v20);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180020b30  push    rbx
0x180020b32  push    rbp
0x180020b33  push    rsi
0x180020b34  push    rdi
0x180020b35  push    r14
0x180020b37  push    r15
0x180020b39  sub     rsp, 68h
0x180020b3d  mov     r15, rdx
0x180020b40  mov     rbx, rcx
0x180020b43  test    rdx, rdx
0x180020b46  jnz     short loc_180020B52
0x180020b48  mov     esi, 80004003h
0x180020b4d  jmp     loc_180020C82
0x180020b52  mov     rdi, [rcx+28h]
0x180020b56  xor     r14d, r14d
0x180020b59  sub     rdi, [rcx+20h]
0x180020b5d  sar     rdi, 3
0x180020b61  call    ?GetCmdPreExecHresult@CSyncMLCmd@@QEBAJXZ; CSyncMLCmd::GetCmdPreExecHresult(void)
0x180020b66  mov     ebp, eax
0x180020b68  test    eax, eax
0x180020b6a  js      short loc_180020BC6
0x180020b6c  xor     esi, esi
0x180020b6e  test    edi, edi
0x180020b70  jle     short loc_180020BC6
0x180020b72  mov     rax, [rbx+20h]
0x180020b76  mov     rcx, [rax+rsi*8]; this
0x180020b7a  call    ?GetCmdPreExecHresult@CSyncMLCmd@@QEBAJXZ; CSyncMLCmd::GetCmdPreExecHresult(void)
0x180020b7f  mov     [rsp+98h+arg_8], eax
0x180020b86  test    eax, eax
0x180020b88  js      short loc_180020BB1
0x180020b8a  lea     rdx, [rsp+98h+arg_8]; int *
0x180020b92  call    ?GetFirstFailedItemHresult@CSyncMLCmd@@QEAAHPEAJ@Z; CSyncMLCmd::GetFirstFailedItemHresult(long *)
0x180020b97  test    eax, eax
0x180020b99  jnz     short loc_180020BAA
0x180020b9b  inc     esi
0x180020b9d  cmp     esi, edi
0x180020b9f  jl      short loc_180020B72
0x180020ba1  mov     eax, [rsp+98h+arg_8]
0x180020ba8  jmp     short loc_180020BB7
0x180020baa  mov     eax, [rsp+98h+arg_8]
0x180020bb1  mov     r14d, 1
0x180020bb7  test    eax, eax
0x180020bb9  jns     short loc_180020BC6
0x180020bbb  cmp     dword ptr [rbx+3Ch], 0
0x180020bbf  mov     ebp, eax
0x180020bc1  jl      short loc_180020BC6
0x180020bc3  mov     [rbx+3Ch], eax
0x180020bc6  mov     edx, [rbx+5Ch]
0x180020bc9  mov     r9d, ebp
0x180020bcc  mov     r8d, r14d
0x180020bcf  mov     ecx, ebp
0x180020bd1  call    GetOmadmStatusCode
0x180020bd6  cmp     dword ptr [rbx+5Ch], 49h ; 'I'
0x180020bda  mov     esi, eax
0x180020bdc  mov     rax, [rbx+50h]
0x180020be0  mov     r14d, [rax+2Ch]
0x180020be4  jnz     short loc_180020BEC
0x180020be6  mov     rcx, [rbx+70h]
0x180020bea  jmp     short loc_180020BF7
0x180020bec  mov     ecx, [rbx+5Ch]
0x180020bef  call    GetElementName
0x180020bf4  mov     rcx, rax
0x180020bf7  mov     r8d, cs:?s_dwCurrClientCmdID@CSyncMLDPU@@0KA; unsigned int
0x180020bfe  mov     edx, esi; unsigned int
0x180020c00  mov     r9d, cs:?s_dwCurrServerMsgID@CSyncMLDPU@@0KA; unsigned int
0x180020c07  mov     [rsp+98h+var_40], r14d; int
0x180020c0c  mov     [rsp+98h+var_48], ebp; int
0x180020c10  mov     [rsp+98h+var_50], 0; unsigned int
0x180020c18  lea     eax, [r8+1]
0x180020c1c  mov     [rsp+98h+var_58], 0; struct CSyncMLItem **
0x180020c25  mov     [rsp+98h+var_60], 0; unsigned __int16 *
0x180020c2e  mov     cs:?s_dwCurrClientCmdID@CSyncMLDPU@@0KA, eax; ulong CSyncMLDPU::s_dwCurrClientCmdID
0x180020c34  mov     rax, [rbx+68h]
0x180020c38  mov     [rsp+98h+var_68], 0; unsigned __int16 *
0x180020c41  mov     [rsp+98h+var_70], rcx; unsigned __int16 *
0x180020c46  mov     rcx, r15; struct IXmlWriter *
0x180020c49  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x180020c4e  call    ?AddStatus@@YAJPEAUIXmlWriter@@KKKPEBG111PEAPEAVCSyncMLItem@@KJH@Z; AddStatus(IXmlWriter *,ulong,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,CSyncMLItem * *,ulong,long,int)
0x180020c53  mov     esi, eax
0x180020c55  test    eax, eax
0x180020c57  js      short loc_180020C82
0x180020c59  xor     ebp, ebp
0x180020c5b  test    edi, edi
0x180020c5d  jle     short loc_180020C82
0x180020c5f  mov     rax, [rbx+20h]
0x180020c63  mov     rdx, r15
0x180020c66  mov     rcx, [rax+rbp*8]
0x180020c6a  mov     rax, [rcx]
0x180020c6d  mov     rax, [rax+20h]
0x180020c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c76  mov     esi, eax
0x180020c78  test    eax, eax
0x180020c7a  js      short loc_180020C82
0x180020c7c  inc     ebp
0x180020c7e  cmp     ebp, edi
0x180020c80  jl      short loc_180020C5F
0x180020c82  mov     eax, cs:dword_18003E048
0x180020c88  cmp     eax, 5
0x180020c8b  jbe     short loc_180020CB4
0x180020c8d  lea     rax, [rsp+98h+arg_8]
0x180020c95  mov     [rsp+98h+arg_8], esi
0x180020c9c  lea     rdx, byte_180036F1F
0x180020ca3  mov     [rsp+98h+var_78], rax
0x180020ca8  lea     rcx, dword_18003E048
0x180020caf  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180020cb4  mov     eax, esi
0x180020cb6  add     rsp, 68h
0x180020cba  pop     r15
0x180020cbc  pop     r14
0x180020cbe  pop     rdi
0x180020cbf  pop     rsi
0x180020cc0  pop     rbp
0x180020cc1  pop     rbx
0x180020cc2  retn
```
