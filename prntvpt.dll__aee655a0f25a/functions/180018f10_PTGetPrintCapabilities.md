# PTGetPrintCapabilities

- ea: `0x180018f10`
- end: `0x180019049`
- name: `PTGetPrintCapabilities`
- size: `313`
- prototype: `HRESULT __stdcall(HPTPROVIDER hProvider, IStream *pPrintTicket, IStream *pCapabilities, BSTR *pbstrErrorMessage)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800056e0`
- `0x18000af4c`
- `0x18000f970`
- `0x180018cd0`
- `0x180018d08`
- `0x180018f10`
- `0x180023010`

## import_xrefs

- `IppCommon!IppTryGetPcFromCache` at `0x180018f9d`
- `IppCommon!IppTryGetPcFromCache` at `0x180018f9d`

## pseudocode

```c
HRESULT __stdcall PTGetPrintCapabilities(
        HPTPROVIDER hProvider,
        IStream *pPrintTicket,
        IStream *pCapabilities,
        BSTR *pbstrErrorMessage)
{
  __int64 v7; // rcx
  struct CPrintTicketHandle *v8; // rbx
  __int64 v9; // r8
  __int64 v10; // r9
  HRESULT v12; // esi
  int PcFromCache; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rcx
  OLECHAR *Ptr; // rdx
  int v19; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v8 = CPrintTicketHandle::ConvertHandle(hProvider, 0);
  if ( !v8 )
    return -2147024890;
  if ( !pCapabilities )
    return -2147024809;
  if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      v7,
      (const EVENT_DESCRIPTOR *)&DocPerf_PrintTicket_GetPrintCapabilities_Start,
      v9,
      v10,
      &v20);
  LOBYTE(v19) = 0;
  if ( !*((_DWORD *)v8 + 10) )
    goto LABEL_11;
  v12 = 0;
  PcFromCache = IppTryGetPcFromCache(*((_QWORD *)v8 + 6), 0, pPrintTicket, pCapabilities);
  if ( PcFromCache < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x448, v15, (const char *)(unsigned int)PcFromCache, (int)&v19);
  if ( !(_BYTE)v19 )
  {
LABEL_11:
    v17 = *((_QWORD *)v8 + 3);
    v20.Ptr = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, IStream *, IStream *, struct _EVENT_DATA_DESCRIPTOR *))(*(_QWORD *)v17 + 48LL))(
            v17,
            pPrintTicket,
            pCapabilities,
            &v20);
    if ( pbstrErrorMessage )
    {
      Ptr = 0;
      if ( v20.Ptr )
      {
        Ptr = (OLECHAR *)v20.Ptr;
        v20.Ptr = 0;
      }
      *pbstrErrorMessage = Ptr;
    }
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v20);
  }
  if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      v14,
      (const EVENT_DESCRIPTOR *)&DocPerf_PrintTicket_GetPrintCapabilities_Stop,
      v15,
      v16,
      &v20);
  return v12;
}

```

## disassembly

```asm
0x180018f10  push    rbx
0x180018f12  push    rbp
0x180018f13  push    rsi
0x180018f14  push    rdi
0x180018f15  push    r14
0x180018f17  sub     rsp, 50h
0x180018f1b  mov     rax, cs:__security_cookie
0x180018f22  xor     rax, rsp
0x180018f25  mov     [rsp+78h+var_30], rax
0x180018f2a  mov     rbp, rdx
0x180018f2d  mov     r14, r9
0x180018f30  xor     edx, edx; int
0x180018f32  mov     rdi, r8
0x180018f35  call    ?ConvertHandle@CPrintTicketHandle@@SAPEAV1@PEAUHPTPROVIDER__@@H@Z; CPrintTicketHandle::ConvertHandle(HPTPROVIDER__ *,int)
0x180018f3a  mov     rbx, rax
0x180018f3d  test    rax, rax
0x180018f40  jnz     short loc_180018F4C
0x180018f42  mov     eax, 80070006h
0x180018f47  jmp     loc_180019031
0x180018f4c  test    rdi, rdi
0x180018f4f  jnz     short loc_180018F5B
0x180018f51  mov     eax, 80070057h
0x180018f56  jmp     loc_180019031
0x180018f5b  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x180018f62  jz      short loc_180018F7A
0x180018f64  lea     rax, [rsp+78h+var_40]
0x180018f69  lea     rdx, DocPerf_PrintTicket_GetPrintCapabilities_Start; int
0x180018f70  mov     [rsp+78h+var_58], rax; PEVENT_DATA_DESCRIPTOR
0x180018f75  call    McGenEventWrite_EventWriteTransfer
0x180018f7a  mov     byte ptr [rsp+78h+var_48], 0
0x180018f7f  cmp     dword ptr [rbx+28h], 0
0x180018f83  jz      short loc_180018FC0
0x180018f85  mov     rcx, [rbx+30h]
0x180018f89  lea     rax, [rsp+78h+var_48]
0x180018f8e  mov     r9, rdi
0x180018f91  mov     [rsp+78h+var_58], rax; int
0x180018f96  mov     r8, rbp
0x180018f99  xor     edx, edx
0x180018f9b  xor     esi, esi
0x180018f9d  call    cs:__imp_IppTryGetPcFromCache
0x180018fa3  test    eax, eax
0x180018fa5  jns     short loc_180018FB9
0x180018fa7  mov     rcx, [rsp+78h]; this
0x180018fac  mov     r9d, eax; char *
0x180018faf  mov     edx, 448h; void *
0x180018fb4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018fb9  cmp     byte ptr [rsp+78h+var_48], sil
0x180018fbe  jnz     short loc_180019010
0x180018fc0  mov     rcx, [rbx+18h]
0x180018fc4  lea     r9, [rsp+78h+var_40]
0x180018fc9  mov     [rsp+78h+var_40.Ptr], 0
0x180018fd2  mov     r8, rdi
0x180018fd5  mov     rdx, rbp
0x180018fd8  mov     rax, [rcx]
0x180018fdb  mov     rax, [rax+30h]
0x180018fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fe4  mov     esi, eax
0x180018fe6  test    r14, r14
0x180018fe9  jz      short loc_180019006
0x180018feb  mov     rcx, [rsp+78h+var_40.Ptr]
0x180018ff0  xor     edx, edx
0x180018ff2  test    rcx, rcx
0x180018ff5  jz      short loc_180019003
0x180018ff7  mov     rdx, rcx
0x180018ffa  mov     [rsp+78h+var_40.Ptr], 0
0x180019003  mov     [r14], rdx
0x180019006  lea     rcx, [rsp+78h+var_40]
0x18001900b  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180019010  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x180019017  jz      short loc_18001902F
0x180019019  lea     rax, [rsp+78h+var_40]
0x18001901e  lea     rdx, DocPerf_PrintTicket_GetPrintCapabilities_Stop; int
0x180019025  mov     [rsp+78h+var_58], rax; PEVENT_DATA_DESCRIPTOR
0x18001902a  call    McGenEventWrite_EventWriteTransfer
0x18001902f  mov     eax, esi
0x180019031  mov     rcx, [rsp+78h+var_30]
0x180019036  xor     rcx, rsp; StackCookie
0x180019039  call    __security_check_cookie
0x18001903e  add     rsp, 50h
0x180019042  pop     r14
0x180019044  pop     rdi
0x180019045  pop     rsi
0x180019046  pop     rbp
0x180019047  pop     rbx
0x180019048  retn
```
