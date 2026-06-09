# RdpDWMDirectWindowContext::~RdpDWMDirectWindowContext(void)

- ea: `0x18000cb08`
- end: `0x18000cc4a`
- name: `??1RdpDWMDirectWindowContext@@MEAA@XZ`
- size: `322`
- prototype: `void __fastcall(RdpDWMDirectWindowContext *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000cc60`

## callees

- `0x180001bfc`
- `0x18000cae4`
- `0x18000cb08`
- `0x18000dd74`
- `0x18000f08c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cbce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cbce`
- `GDI32!SelectObject` at `0x18000cb97`
- `GDI32!SelectObject` at `0x18000cb97`
- `GDI32!DeleteDC` at `0x18000cbb7`
- `GDI32!DeleteDC` at `0x18000cbb7`
- `GDI32!DeleteObject` at `0x18000cba5`
- `GDI32!DeleteObject` at `0x18000cbeb`
- `GDI32!DeleteObject` at `0x18000cba5`
- `GDI32!DeleteObject` at `0x18000cbeb`

## pseudocode

```c
void __fastcall RdpDWMDirectWindowContext::~RdpDWMDirectWindowContext(
        RdpDWMDirectWindowContext *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  HDC v5; // rcx
  void *v6; // rdx
  HGDIOBJ v7; // rax
  void *v8; // rcx
  __int64 i; // rdi
  void *v10; // rcx
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF
  const char *v12; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)this = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 1) = &RdpDWMDirectWindowContext::`vftable'{for `CTSObject'};
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v11 = *((_QWORD *)this + 8);
    v12 = "Deleting window context";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)this,
      (__int64)byte_180039A71,
      a3,
      a4,
      (const unsigned __int16 **)&v12,
      (__int64)&v11);
  }
  if ( *((_QWORD *)this + 82) && *((_DWORD *)this + 26) )
    RdpDWMDirectWindowContext::DestroySurface(this);
  v5 = (HDC)*((_QWORD *)this + 7);
  if ( v5 )
  {
    v6 = (void *)*((_QWORD *)this + 10);
    if ( v6 )
    {
      v7 = SelectObject(v5, v6);
      if ( v7 )
        DeleteObject(v7);
      *((_QWORD *)this + 10) = 0;
    }
    DeleteDC(*((HDC *)this + 7));
    *((_QWORD *)this + 7) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 12);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 12) = 0;
  }
  for ( i = 0; i != 3; ++i )
  {
    v10 = (void *)*((_QWORD *)this + i + 88);
    if ( v10 )
      DeleteObject(v10);
  }
  *((_DWORD *)this + 192) = 0;
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease((char *)this + 664);
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease((char *)this + 656);
  TSRegisteredObject<RdpDWMDirectWindowContext,64>::~TSRegisteredObject<RdpDWMDirectWindowContext,64>((char *)this + 48);
  *(_QWORD *)this = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_DWORD *)this + 7) |= 8u;
  *((_QWORD *)this + 1) = &CTSObject::`vftable';
}

```

## disassembly

```asm
0x18000cb08  mov     r11, rsp
0x18000cb0b  mov     [r11+18h], rbx
0x18000cb0f  mov     [r11+20h], rsi
0x18000cb13  push    rdi
0x18000cb14  sub     rsp, 30h
0x18000cb18  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x18000cb1f  mov     rbx, rcx
0x18000cb22  mov     [rcx], rax
0x18000cb25  lea     rax, ??_7RdpDWMDirectWindowContext@@6BCTSObject@@@; const RdpDWMDirectWindowContext::`vftable'{for `CTSObject'}
0x18000cb2c  mov     [rcx+8], rax
0x18000cb30  mov     eax, cs:dword_180044008
0x18000cb36  cmp     eax, 5
0x18000cb39  jbe     short loc_18000CB6A
0x18000cb3b  mov     rax, [rcx+40h]
0x18000cb3f  lea     rdx, byte_180039A71
0x18000cb46  mov     [r11+8], rax
0x18000cb4a  lea     rax, aDeletingWindow; "Deleting window context"
0x18000cb51  mov     [r11+10h], rax
0x18000cb55  lea     rax, [r11+8]
0x18000cb59  mov     [r11-10h], rax
0x18000cb5d  lea     rax, [r11+10h]
0x18000cb61  mov     [r11-18h], rax
0x18000cb65  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000cb6a  lea     rsi, [rbx+290h]
0x18000cb71  cmp     qword ptr [rsi], 0
0x18000cb75  jz      short loc_18000CB85
0x18000cb77  cmp     dword ptr [rbx+68h], 0
0x18000cb7b  jz      short loc_18000CB85
0x18000cb7d  mov     rcx, rbx; this
0x18000cb80  call    ?DestroySurface@RdpDWMDirectWindowContext@@QEAAJXZ; RdpDWMDirectWindowContext::DestroySurface(void)
0x18000cb85  mov     rcx, [rbx+38h]; hdc
0x18000cb89  test    rcx, rcx
0x18000cb8c  jz      short loc_18000CBC5
0x18000cb8e  mov     rdx, [rbx+50h]; h
0x18000cb92  test    rdx, rdx
0x18000cb95  jz      short loc_18000CBB3
0x18000cb97  call    cs:__imp_SelectObject
0x18000cb9d  test    rax, rax
0x18000cba0  jz      short loc_18000CBAB
0x18000cba2  mov     rcx, rax; ho
0x18000cba5  call    cs:__imp_DeleteObject
0x18000cbab  mov     qword ptr [rbx+50h], 0
0x18000cbb3  mov     rcx, [rbx+38h]; hdc
0x18000cbb7  call    cs:__imp_DeleteDC
0x18000cbbd  mov     qword ptr [rbx+38h], 0
0x18000cbc5  mov     rcx, [rbx+60h]; hObject
0x18000cbc9  test    rcx, rcx
0x18000cbcc  jz      short loc_18000CBDC
0x18000cbce  call    cs:__imp_CloseHandle
0x18000cbd4  mov     qword ptr [rbx+60h], 0
0x18000cbdc  xor     edi, edi
0x18000cbde  mov     rcx, [rbx+rdi*8+2C0h]; ho
0x18000cbe6  test    rcx, rcx
0x18000cbe9  jz      short loc_18000CBF1
0x18000cbeb  call    cs:__imp_DeleteObject
0x18000cbf1  inc     rdi
0x18000cbf4  cmp     rdi, 3
0x18000cbf8  jnz     short loc_18000CBDE
0x18000cbfa  lea     rcx, [rbx+298h]
0x18000cc01  mov     dword ptr [rbx+300h], 0
0x18000cc0b  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x18000cc10  mov     rcx, rsi
0x18000cc13  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x18000cc18  lea     rcx, [rbx+30h]
0x18000cc1c  call    ??1?$TSRegisteredObject@VRdpDWMDirectWindowContext@@$0EA@@@QEAA@XZ; TSRegisteredObject<RdpDWMDirectWindowContext,64>::~TSRegisteredObject<RdpDWMDirectWindowContext,64>(void)
0x18000cc21  mov     rsi, [rsp+38h+arg_18]
0x18000cc26  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x18000cc2d  mov     [rbx], rax
0x18000cc30  lea     rax, ??_7CTSObject@@6B@; const CTSObject::`vftable'
0x18000cc37  or      dword ptr [rbx+1Ch], 8
0x18000cc3b  mov     [rbx+8], rax
0x18000cc3f  mov     rbx, [rsp+38h+arg_10]
0x18000cc44  add     rsp, 30h
0x18000cc48  pop     rdi
0x18000cc49  retn
```
