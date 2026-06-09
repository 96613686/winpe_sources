# CreatePinHandle(KSIDENTIFIER &,KSIDENTIFIER &,void *,CMediaType *,CKsProxy *,ulong,ulong,void * *)

- ea: `0x180035d90`
- end: `0x180035ef3`
- name: `?CreatePinHandle@@YAJAEAUKSIDENTIFIER@@0PEAXPEAVCMediaType@@PEAVCKsProxy@@KKPEAPEAX@Z`
- size: `355`
- prototype: `__int64 __fastcall(struct KSIDENTIFIER *, struct KSIDENTIFIER *, void *, struct CMediaType *, struct CKsProxy *, ULONG, ACCESS_MASK DesiredAccess, void **ConnectionHandle)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x18001aaf0`
- `0x180026de0`
- `0x1800275c0`
- `0x180028584`
- `0x180029ad0`
- `0x18002b6e0`
- `0x180030890`

## callees

- `0x180002b58`
- `0x18001bbf8`
- `0x1800248d4`
- `0x180035d90`
- `0x180045010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180035e69`
- `KERNEL32!Sleep` at `0x180035e69`
- `ole32!CoTaskMemFree` at `0x180035ed7`
- `ole32!CoTaskMemFree` at `0x180035ed7`
- `ksuser!KsCreatePin` at `0x180035e51`
- `ksuser!KsCreatePin` at `0x180035e51`

## pseudocode

```c
__int64 __fastcall CreatePinHandle(
        struct KSIDENTIFIER *a1,
        struct KSIDENTIFIER *a2,
        void *a3,
        struct CMediaType *a4,
        struct CKsProxy *a5,
        ULONG a6,
        ACCESS_MASK DesiredAccess,
        void **ConnectionHandle)
{
  __int64 result; // rax
  PKSPIN_CONNECT v12; // rdi
  __int64 v13; // xmm1_8
  int v14; // esi
  void *v15; // rax
  signed int Pin; // ebx
  unsigned int v17; // [rsp+20h] [rbp-48h] BYREF
  PKSPIN_CONNECT Connect; // [rsp+28h] [rbp-40h] BYREF

  Connect = 0;
  v17 = 0;
  result = InitializeDataFormat(a4, 0x48u, (void **)&Connect, &v17);
  if ( (int)result >= 0 )
  {
    v12 = Connect;
    Connect->Interface.0 = a1->0;
    v13 = *(_QWORD *)&a1->Id;
    v14 = 0;
    *(_QWORD *)&v12->Interface.Id = v13;
    v12->Medium = *a2;
    v12->PinId = a6;
    v12->PinToHandle = a3;
    v12->Priority.PriorityClass = 0x40000000;
    v12->Priority.PrioritySubClass = 0x40000000;
    do
    {
      v15 = a5->KsGetObjectHandle(&a5->IKsObject);
      Pin = KsCreatePin(v15, v12, DesiredAccess, ConnectionHandle);
      if ( Pin != 21 )
        break;
      Sleep(0x3E8u);
      ++v14;
    }
    while ( v14 < 5 );
    if ( Pin > 0 )
      Pin = (unsigned __int16)Pin | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids,
        (unsigned int)Pin);
    if ( Pin < 0 )
      *ConnectionHandle = 0;
    else
      Pin = CKsProxy::SetPinSyncSource(a5, *ConnectionHandle);
    CoTaskMemFree(v12);
    return (unsigned int)Pin;
  }
  return result;
}

```

## disassembly

```asm
0x180035d90  push    rbx
0x180035d92  push    rbp
0x180035d93  push    rsi
0x180035d94  push    rdi
0x180035d95  push    r14
0x180035d97  push    r15
0x180035d99  sub     rsp, 38h
0x180035d9d  mov     rax, r9
0x180035da0  mov     [rsp+68h+Connect], 0
0x180035da9  mov     rbp, r8
0x180035dac  mov     [rsp+68h+var_48], 0
0x180035db4  mov     rbx, rdx
0x180035db7  lea     r9, [rsp+68h+var_48]; unsigned int *
0x180035dbc  mov     rsi, rcx
0x180035dbf  lea     r8, [rsp+68h+Connect]; void **
0x180035dc4  mov     rcx, rax; struct CMediaType *
0x180035dc7  mov     edx, 48h ; 'H'; unsigned int
0x180035dcc  call    ?InitializeDataFormat@@YAJPEBVCMediaType@@KPEAPEAXPEAK@Z; InitializeDataFormat(CMediaType const *,ulong,void * *,ulong *)
0x180035dd1  test    eax, eax
0x180035dd3  js      loc_180035EE5
0x180035dd9  movups  xmm0, xmmword ptr [rsi]
0x180035ddc  mov     rdi, [rsp+68h+Connect]
0x180035de1  mov     eax, [rsp+68h+arg_28]
0x180035de8  mov     r14, [rsp+68h+ConnectionHandle]
0x180035df0  movups  xmmword ptr [rdi], xmm0
0x180035df3  movsd   xmm1, qword ptr [rsi+10h]
0x180035df8  xor     esi, esi
0x180035dfa  movsd   qword ptr [rdi+10h], xmm1
0x180035dff  movups  xmm0, xmmword ptr [rbx]
0x180035e02  movups  xmmword ptr [rdi+18h], xmm0
0x180035e06  movsd   xmm1, qword ptr [rbx+10h]
0x180035e0b  movsd   qword ptr [rdi+28h], xmm1
0x180035e10  mov     [rdi+30h], eax
0x180035e13  mov     eax, 40000000h
0x180035e18  mov     [rdi+38h], rbp
0x180035e1c  mov     rbp, [rsp+68h+arg_20]
0x180035e24  mov     [rdi+40h], eax
0x180035e27  mov     [rdi+44h], eax
0x180035e2a  lea     r15, [rbp+0A8h]
0x180035e31  mov     rax, [r15]
0x180035e34  mov     rcx, r15
0x180035e37  mov     rax, [rax+18h]
0x180035e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e40  mov     r8d, [rsp+68h+DesiredAccess]; DesiredAccess
0x180035e48  mov     r9, r14; ConnectionHandle
0x180035e4b  mov     rdx, rdi; Connect
0x180035e4e  mov     rcx, rax; FilterHandle
0x180035e51  call    cs:__imp_KsCreatePin
0x180035e58  nop     dword ptr [rax+rax+00h]
0x180035e5d  mov     ebx, eax
0x180035e5f  cmp     eax, 15h
0x180035e62  jnz     short loc_180035E7C
0x180035e64  mov     ecx, 3E8h; dwMilliseconds
0x180035e69  call    cs:__imp_Sleep
0x180035e70  nop     dword ptr [rax+rax+00h]
0x180035e75  inc     esi
0x180035e77  cmp     esi, 5
0x180035e7a  jl      short loc_180035E31
0x180035e7c  test    ebx, ebx
0x180035e7e  jle     short loc_180035E89
0x180035e80  movzx   ebx, bx
0x180035e83  or      ebx, 80070000h
0x180035e89  mov     rcx, cs:WPP_GLOBAL_Control
0x180035e90  lea     rax, WPP_GLOBAL_Control
0x180035e97  cmp     rcx, rax
0x180035e9a  jz      short loc_180035EBA
0x180035e9c  cmp     byte ptr [rcx+19h], 2
0x180035ea0  jb      short loc_180035EBA
0x180035ea2  mov     rcx, [rcx+10h]
0x180035ea6  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x180035ead  mov     edx, 19h
0x180035eb2  mov     r9d, ebx
0x180035eb5  call    WPP_SF_d
0x180035eba  test    ebx, ebx
0x180035ebc  js      short loc_180035ECD
0x180035ebe  mov     rdx, [r14]; void *
0x180035ec1  mov     rcx, rbp; this
0x180035ec4  call    ?SetPinSyncSource@CKsProxy@@QEAAJPEAX@Z; CKsProxy::SetPinSyncSource(void *)
0x180035ec9  mov     ebx, eax
0x180035ecb  jmp     short loc_180035ED4
0x180035ecd  mov     qword ptr [r14], 0
0x180035ed4  mov     rcx, rdi; pv
0x180035ed7  call    cs:__imp_CoTaskMemFree
0x180035ede  nop     dword ptr [rax+rax+00h]
0x180035ee3  mov     eax, ebx
0x180035ee5  add     rsp, 38h
0x180035ee9  pop     r15
0x180035eeb  pop     r14
0x180035eed  pop     rdi
0x180035eee  pop     rsi
0x180035eef  pop     rbp
0x180035ef0  pop     rbx
0x180035ef1  retn
```
