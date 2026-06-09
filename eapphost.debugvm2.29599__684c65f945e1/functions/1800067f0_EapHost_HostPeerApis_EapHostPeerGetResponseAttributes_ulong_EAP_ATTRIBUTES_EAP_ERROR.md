# EapHost::HostPeerApis::EapHostPeerGetResponseAttributes(ulong,_EAP_ATTRIBUTES *,_EAP_ERROR * *)

- ea: `0x1800067f0`
- end: `0x180006966`
- name: `?EapHostPeerGetResponseAttributes@HostPeerApis@EapHost@@UEAAJKPEAU_EAP_ATTRIBUTES@@PEAPEAU_EAP_ERROR@@@Z`
- size: `374`
- prototype: `__int64 __fastcall(EapHost::HostPeerApis *__hidden this, unsigned int, struct _EAP_ATTRIBUTES *, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180003a4c`
- `0x180003fec`
- `0x1800067f0`
- `0x180009dec`
- `0x18000a09c`
- `0x18001e0a0`
- `0x1800251b0`
- `0x18002ed84`

## string_xrefs

- `0x1800068be`: `com_ref:Assign`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EapHost::HostPeerApis::EapHostPeerGetResponseAttributes(
        EapHost::HostPeerApis *this,
        unsigned int a2,
        struct _EAP_ATTRIBUTES *a3,
        struct _EAP_ERROR **a4)
{
  struct _EAP_ATTRIBUTES v5; // xmm1
  int *v6; // r9
  const ATL::CAtlException *v8; // [rsp+30h] [rbp-68h] BYREF
  const EapHost::EapException *v9; // [rsp+38h] [rbp-60h] BYREF
  const Exception *v10; // [rsp+40h] [rbp-58h] BYREF
  struct _EAP_ATTRIBUTES v11; // [rsp+48h] [rbp-50h] BYREF
  __int64 v12; // [rsp+58h] [rbp-40h]
  __int128 v13; // [rsp+60h] [rbp-38h] BYREF
  __int64 v14; // [rsp+70h] [rbp-28h]
  _DWORD v15[2]; // [rsp+78h] [rbp-20h] BYREF
  __int64 v16; // [rsp+80h] [rbp-18h]
  struct _EAP_ERROR *v18; // [rsp+B0h] [rbp+18h] BYREF
  const struct Exception *v19; // [rsp+B8h] [rbp+20h]

  v19 = (const struct Exception *)a4;
  LODWORD(v18) = 0;
  v13 = 0;
  v14 = 0;
  v15[1] = 0;
  v15[0] = 0;
  v16 = 0;
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids, a2);
  }
  if ( a3 )
  {
    *a3 = 0;
    try
    {
      EapHost::Peer::Host::GetAttributes(EapHost::HostPeerApis::pHost, a2, (struct EapHost::AutoAttributes *)&v13);
      v11 = 0;
      v12 = 1;
      if ( !Copy<TaskAllocator>((__int64)&v11, v15) )
        LowMemoryError::Throw(L"com_ref:Assign");
      v5 = v11;
      v11 = 0;
      v12 = 1;
      *a3 = v5;
      Free<TaskAllocator>(&v11.dwNumberOfAttributes);
    }
    catch ( std::bad_alloc )
    {
      LODWORD(v18) = -2147024882;
      if ( v19 )
        *(_QWORD *)v19 = 0;
    }
    catch ( const ATL::CAtlException *v8 )
    {
      LODWORD(v18) = *(_DWORD *)v8;
      if ( v19 )
        *(_QWORD *)v19 = 0;
    }
    catch ( const EapHost::EapException *v9 )
    {
      EapHost::EapException2EapErrorOle(v9, v19, &v18, v6);
    }
    catch ( const Exception *v10 )
    {
      EapHost::Exception2EapErrorOle(v10, v19, &v18, v6);
    }
  }
  else
  {
    LODWORD(v18) = -2147024809;
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_ddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids,
      (unsigned int)v18,
      a2,
      v14);
  }
  EapHost::AutoAttributes::~AutoAttributes((EapHost::AutoAttributes *)&v13);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800067f0  mov     rax, rsp
0x1800067f3  mov     [rax+8], rbx
0x1800067f7  mov     [rax+20h], r9
0x1800067fb  mov     [rax+10h], edx
0x1800067fe  push    rdi
0x1800067ff  sub     rsp, 90h
0x180006806  mov     rdi, r8
0x180006809  mov     r9d, edx
0x18000680c  mov     dword ptr [rax+18h], 0
0x180006813  xorps   xmm0, xmm0
0x180006816  movdqu  xmmword ptr [rax-38h], xmm0
0x18000681b  mov     qword ptr [rax-28h], 0
0x180006823  movups  xmmword ptr [rax-20h], xmm0
0x180006827  mov     dword ptr [rax-20h], 0
0x18000682e  mov     qword ptr [rax-18h], 0
0x180006836  lea     rbx, WPP_GLOBAL_Control
0x18000683d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006844  cmp     rcx, rbx
0x180006847  jz      short loc_180006864
0x180006849  test    byte ptr [rcx+1Ch], 4
0x18000684d  jz      short loc_180006864
0x18000684f  mov     edx, 24h ; '$'
0x180006854  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x18000685b  mov     rcx, [rcx+10h]
0x18000685f  call    WPP_SF_d
0x180006864  test    rdi, rdi
0x180006867  jnz     short loc_180006879
0x180006869  mov     dword ptr [rsp+98h+arg_10], 80070057h
0x180006874  jmp     loc_180006901
0x180006879  xorps   xmm0, xmm0
0x18000687c  movups  xmmword ptr [rdi], xmm0
0x18000687f  lea     r8, [rsp+98h+var_38]; struct EapHost::AutoAttributes *
0x180006884  mov     edx, [rsp+98h+arg_8]; unsigned int
0x18000688b  mov     rcx, cs:?pHost@HostPeerApis@EapHost@@0V?$unique_ptr@VHost@Peer@EapHost@@U?$default_delete@VHost@Peer@EapHost@@@std@@@std@@A; this
0x180006892  call    ?GetAttributes@Host@Peer@EapHost@@QEAAXIAEAVAutoAttributes@3@@Z; EapHost::Peer::Host::GetAttributes(uint,EapHost::AutoAttributes &)
0x180006897  xorps   xmm0, xmm0
0x18000689a  xor     eax, eax
0x18000689c  movups  [rsp+98h+var_50], xmm0
0x1800068a1  mov     [rsp+98h+var_40], rax
0x1800068a6  mov     byte ptr [rsp+98h+var_40], 1
0x1800068ab  lea     rdx, [rsp+98h+var_20]
0x1800068b0  lea     rcx, [rsp+98h+var_50]
0x1800068b5  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_ATTRIBUTES@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_ATTRIBUTES &,_EAP_ATTRIBUTES const &)
0x1800068ba  test    al, al
0x1800068bc  jnz     short loc_1800068CA
0x1800068be  lea     rcx, aComRefAssign; "com_ref:Assign"
0x1800068c5  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x1800068ca  movups  xmm1, [rsp+98h+var_50]
0x1800068cf  xorps   xmm0, xmm0
0x1800068d2  xor     eax, eax
0x1800068d4  movups  [rsp+98h+var_50], xmm0
0x1800068d9  mov     [rsp+98h+var_40], rax
0x1800068de  mov     byte ptr [rsp+98h+var_40], 1
0x1800068e3  movdqu  xmmword ptr [rdi], xmm1
0x1800068e7  lea     rcx, [rsp+98h+var_50]
0x1800068ec  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z; Free<TaskAllocator>(_EAP_ATTRIBUTES &)
0x1800068f1  nop
0x1800068f2  jmp     short loc_180006901
0x1800068f4  jmp     short loc_1800068FA
0x1800068f6  jmp     short loc_1800068FA
0x1800068f8  jmp     short $+2
0x1800068fa  lea     rbx, WPP_GLOBAL_Control
0x180006901  mov     rcx, cs:WPP_GLOBAL_Control
0x180006908  cmp     rcx, rbx
0x18000690b  jz      short loc_180006944
0x18000690d  test    byte ptr [rcx+1Ch], 4
0x180006911  jz      short loc_180006944
0x180006913  mov     edx, 25h ; '%'
0x180006918  mov     eax, dword ptr [rsp+98h+var_28]
0x18000691c  mov     [rsp+98h+var_70], eax
0x180006920  mov     eax, [rsp+98h+arg_8]
0x180006927  mov     [rsp+98h+var_78], eax
0x18000692b  mov     r9d, dword ptr [rsp+98h+arg_10]
0x180006933  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x18000693a  mov     rcx, [rcx+10h]
0x18000693e  call    WPP_SF_ddd
0x180006943  nop
0x180006944  lea     rcx, [rsp+98h+var_38]; this
0x180006949  call    ??1AutoAttributes@EapHost@@QEAA@XZ; EapHost::AutoAttributes::~AutoAttributes(void)
0x18000694e  mov     eax, dword ptr [rsp+98h+arg_10]
0x180006955  mov     rbx, [rsp+98h+arg_0]
0x18000695d  add     rsp, 90h
0x180006964  pop     rdi
0x180006965  retn
```
