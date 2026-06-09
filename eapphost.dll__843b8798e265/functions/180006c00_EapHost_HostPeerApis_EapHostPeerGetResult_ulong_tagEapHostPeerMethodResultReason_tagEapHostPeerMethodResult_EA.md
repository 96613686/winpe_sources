# EapHost::HostPeerApis::EapHostPeerGetResult(ulong,tagEapHostPeerMethodResultReason,tagEapHostPeerMethodResult *,_EAP_ERROR * *)

- ea: `0x180006c00`
- end: `0x180006eae`
- name: `?EapHostPeerGetResult@HostPeerApis@EapHost@@UEAAJKW4tagEapHostPeerMethodResultReason@@PEAUtagEapHostPeerMethodResult@@PEAPEAU_EAP_ERROR@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(EapHost::HostPeerApis *__hidden this, unsigned int, enum tagEapHostPeerMethodResultReason, struct tagEapHostPeerMethodResult *, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800034cc`
- `0x180003ea0`
- `0x180004018`
- `0x180004074`
- `0x1800040a8`
- `0x180004204`
- `0x180006c00`
- `0x180007564`
- `0x18000a040`
- `0x18000a4d4`
- `0x18000a588`
- `0x180026850`
- `0x18002fe84`

## string_xrefs

- `0x180006ce2`: `com_ref:Assign`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EapHost::HostPeerApis::EapHostPeerGetResult(
        EapHost::HostPeerApis *this,
        unsigned int a2,
        enum tagEapHostPeerMethodResultReason a3,
        struct tagEapHostPeerMethodResult *a4,
        struct _EAP_ERROR **a5)
{
  unsigned int v8; // ebx
  __int128 v9; // xmm6
  __int128 v10; // xmm7
  __int128 v11; // xmm8
  __int128 v12; // xmm9
  EAP_ERROR *v13; // xmm10_8
  int *v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r9
  int v19; // [rsp+40h] [rbp-128h] BYREF
  int v20; // [rsp+44h] [rbp-124h]
  void *v21; // [rsp+50h] [rbp-118h]
  void *v22; // [rsp+60h] [rbp-108h]
  void *v23; // [rsp+68h] [rbp-100h]
  void *v24; // [rsp+78h] [rbp-F0h]
  void *v25; // [rsp+80h] [rbp-E8h]
  _OWORD v26[4]; // [rsp+90h] [rbp-D8h] BYREF
  EAP_ERROR *v27; // [rsp+D0h] [rbp-98h]
  char v28; // [rsp+D8h] [rbp-90h]
  const ATL::CAtlException *v29; // [rsp+E0h] [rbp-88h] BYREF
  const EapHost::EapException *v30; // [rsp+E8h] [rbp-80h] BYREF
  const Exception *v31; // [rsp+F0h] [rbp-78h] BYREF
  struct _EAP_ERROR *v33; // [rsp+188h] [rbp+20h] BYREF

  v8 = 0;
  LODWORD(v33) = 0;
  memset_0(&v19, 0, 0x48u);
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids, a2, a3);
  }
  if ( a4 )
  {
    try
    {
      EapHost::Peer::Host::GetResult();
      memset_0(v26, 0, 0x50u);
      v28 = 1;
      if ( !Copy<TaskAllocator>(v26, (__int64)&v19) )
        LowMemoryError::Throw(L"com_ref:Assign");
      v9 = v26[0];
      v10 = v26[1];
      v11 = v26[2];
      v12 = v26[3];
      v13 = v27;
      memset_0(v26, 0, 0x50u);
      v28 = 1;
      *(_OWORD *)&a4->fIsSuccess = v9;
      *(_OWORD *)&a4->pConnectionData = v10;
      *(_OWORD *)&a4->pUserData = v11;
      *(_OWORD *)&a4->isolationState = v12;
      a4->pEapError = v13;
      Free<TaskAllocator>((LPVOID *)v26);
    }
    catch ( std::bad_alloc )
    {
      LODWORD(v33) = -2147024882;
      if ( a5 )
        *a5 = 0;
      v8 = (unsigned int)v33;
    }
    catch ( const ATL::CAtlException *v29 )
    {
      LODWORD(v33) = *(_DWORD *)v29;
      if ( a5 )
        *a5 = 0;
      v8 = (unsigned int)v33;
    }
    catch ( const EapHost::EapException *v30 )
    {
      EapHost::EapException2EapErrorOle(v30, (const struct EapHost::EapException *)a5, &v33, v14);
      v8 = (unsigned int)v33;
    }
    catch ( const Exception *v31 )
    {
      EapHost::Exception2EapErrorOle(v31, (const struct Exception *)a5, &v33, v14);
      v8 = (unsigned int)v33;
    }
  }
  else
  {
    v8 = -2147024809;
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_dddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids,
      v8,
      a2,
      v19,
      v20);
  }
  if ( !v8 && !v19 && (byte_18004F981 & 1) != 0 )
  {
    if ( v25 )
      v15 = *((_QWORD *)v25 + 10);
    else
      v15 = 0;
    if ( v25 )
      v16 = *((_QWORD *)v25 + 9);
    else
      v16 = 0;
    if ( v24 )
      v17 = *((_QWORD *)v24 + 3);
    else
      LODWORD(v17) = 0;
    McTemplateU0qzzz_EtwEventWriteTransfer(v16, v15, v20, v17, v16, v15);
  }
  HeapAllocator::Free(v21);
  HeapAllocator::Free(v22);
  if ( v23 )
  {
    Free<HeapAllocator>();
    HeapAllocator::Free(v23);
  }
  if ( v24 )
  {
    Free<HeapAllocator>(v24);
    HeapAllocator::Free(v24);
  }
  if ( v25 )
  {
    Free<HeapAllocator>(v25);
    HeapAllocator::Free(v25);
  }
  return v8;
}

```

## disassembly

```asm
0x180006c00  mov     rax, rsp
0x180006c03  mov     [rax+8], rbx
0x180006c07  mov     [rax+18h], rsi
0x180006c0b  mov     [rax+10h], edx
0x180006c0e  push    rdi
0x180006c0f  push    r14
0x180006c11  push    r15
0x180006c13  sub     rsp, 150h
0x180006c1a  movaps  xmmword ptr [rax-28h], xmm6
0x180006c1e  movaps  xmmword ptr [rax-38h], xmm7
0x180006c22  movaps  xmmword ptr [rax-48h], xmm8
0x180006c27  movaps  xmmword ptr [rax-58h], xmm9
0x180006c2c  movaps  xmmword ptr [rax-68h], xmm10
0x180006c31  mov     r14, r9
0x180006c34  mov     esi, r8d
0x180006c37  mov     r15d, edx
0x180006c3a  xor     ebx, ebx
0x180006c3c  mov     [rax+20h], ebx
0x180006c3f  xor     edx, edx; Val
0x180006c41  lea     r8d, [rbx+48h]; Size
0x180006c45  lea     rcx, [rsp+168h+var_128]; void *
0x180006c4a  call    memset_0
0x180006c4f  nop
0x180006c50  lea     rdi, WPP_GLOBAL_Control
0x180006c57  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c5e  cmp     rcx, rdi
0x180006c61  jz      short loc_180006C83
0x180006c63  test    byte ptr [rcx+1Ch], 4
0x180006c67  jz      short loc_180006C83
0x180006c69  lea     edx, [rbx+1Eh]
0x180006c6c  mov     dword ptr [rsp+168h+var_148], esi
0x180006c70  mov     r9d, r15d
0x180006c73  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180006c7a  mov     rcx, [rcx+10h]
0x180006c7e  call    WPP_SF_dd
0x180006c83  test    r14, r14
0x180006c86  jnz     short loc_180006C92
0x180006c88  mov     ebx, 80070057h
0x180006c8d  jmp     loc_180006D71
0x180006c92  lea     r9, [rsp+168h+var_128]
0x180006c97  mov     r8d, esi
0x180006c9a  mov     edx, [rsp+168h+arg_8]
0x180006ca1  mov     rcx, cs:?pHost@HostPeerApis@EapHost@@0V?$unique_ptr@VHost@Peer@EapHost@@U?$default_delete@VHost@Peer@EapHost@@@std@@@std@@A; std::unique_ptr<EapHost::Peer::Host> EapHost::HostPeerApis::pHost
0x180006ca8  call    ?GetResult@Host@Peer@EapHost@@QEAAXIW4tagEapHostPeerMethodResultReason@@AEAV?$crt_ref@UtagEapHostPeerMethodResult@@@@@Z; EapHost::Peer::Host::GetResult(uint,tagEapHostPeerMethodResultReason,crt_ref<tagEapHostPeerMethodResult> &)
0x180006cad  mov     esi, 50h ; 'P'
0x180006cb2  mov     r8d, esi; Size
0x180006cb5  xor     edx, edx; Val
0x180006cb7  lea     rcx, [rsp+168h+var_D8]; void *
0x180006cbf  call    memset_0
0x180006cc4  mov     [rsp+168h+var_90], 1
0x180006ccc  lea     rdx, [rsp+168h+var_128]
0x180006cd1  lea     rcx, [rsp+168h+var_D8]; void *
0x180006cd9  call    ??$Copy@VTaskAllocator@@@@YA_NAEAUtagEapHostPeerMethodResult@@AEBU0@@Z; Copy<TaskAllocator>(tagEapHostPeerMethodResult &,tagEapHostPeerMethodResult const &)
0x180006cde  test    al, al
0x180006ce0  jnz     short loc_180006CEE
0x180006ce2  lea     rcx, aComRefAssign; "com_ref:Assign"
0x180006ce9  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x180006cee  movaps  xmm6, [rsp+168h+var_D8]
0x180006cf6  movaps  xmm7, [rsp+168h+var_C8]
0x180006cfe  movaps  xmm8, [rsp+168h+var_B8]
0x180006d07  movaps  xmm9, [rsp+168h+var_A8]
0x180006d10  movsd   xmm10, [rsp+168h+var_98]
0x180006d1a  mov     r8, rsi; Size
0x180006d1d  xor     edx, edx; Val
0x180006d1f  lea     rcx, [rsp+168h+var_D8]; void *
0x180006d27  call    memset_0
0x180006d2c  mov     [rsp+168h+var_90], 1
0x180006d34  movups  xmmword ptr [r14], xmm6
0x180006d38  movups  xmmword ptr [r14+10h], xmm7
0x180006d3d  movups  xmmword ptr [r14+20h], xmm8
0x180006d42  movups  xmmword ptr [r14+30h], xmm9
0x180006d47  movsd   qword ptr [r14+40h], xmm10
0x180006d4d  lea     rcx, [rsp+168h+var_D8]; void *
0x180006d55  call    ??$Free@VTaskAllocator@@@@YAXAEAUtagEapHostPeerMethodResult@@@Z; Free<TaskAllocator>(tagEapHostPeerMethodResult &)
0x180006d5a  nop
0x180006d5b  jmp     short loc_180006D71
0x180006d5d  jmp     short loc_180006D63
0x180006d5f  jmp     short loc_180006D63
0x180006d61  jmp     short $+2
0x180006d63  mov     ebx, dword ptr [rsp+168h+arg_18]
0x180006d6a  lea     rdi, WPP_GLOBAL_Control
0x180006d71  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d78  cmp     rcx, rdi
0x180006d7b  jz      short loc_180006DB6
0x180006d7d  test    byte ptr [rcx+1Ch], 4
0x180006d81  jz      short loc_180006DB6
0x180006d83  mov     edx, 1Fh
0x180006d88  mov     eax, [rsp+168h+var_124]
0x180006d8c  mov     [rsp+168h+var_138], eax
0x180006d90  mov     eax, [rsp+168h+var_128]
0x180006d94  mov     dword ptr [rsp+168h+var_140], eax
0x180006d98  mov     eax, [rsp+168h+arg_8]
0x180006d9f  mov     dword ptr [rsp+168h+var_148], eax
0x180006da3  mov     r9d, ebx
0x180006da6  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180006dad  mov     rcx, [rcx+10h]
0x180006db1  call    WPP_SF_dddd
0x180006db6  test    ebx, ebx
0x180006db8  jnz     short loc_180006E13
0x180006dba  cmp     [rsp+168h+var_128], ebx
0x180006dbe  jnz     short loc_180006E13
0x180006dc0  test    cs:byte_18004F981, 1
0x180006dc7  jz      short loc_180006E13
0x180006dc9  mov     rax, [rsp+168h+var_E8]
0x180006dd1  test    rax, rax
0x180006dd4  jz      short loc_180006DDC
0x180006dd6  mov     rdx, [rax+50h]
0x180006dda  jmp     short loc_180006DDE
0x180006ddc  xor     edx, edx
0x180006dde  test    rax, rax
0x180006de1  jz      short loc_180006DE9
0x180006de3  mov     rcx, [rax+48h]
0x180006de7  jmp     short loc_180006DEB
0x180006de9  xor     ecx, ecx
0x180006deb  mov     rax, [rsp+168h+var_F0]
0x180006df0  test    rax, rax
0x180006df3  jz      short loc_180006DFB
0x180006df5  mov     r9, [rax+18h]
0x180006df9  jmp     short loc_180006DFE
0x180006dfb  xor     r9d, r9d
0x180006dfe  mov     [rsp+168h+var_140], rdx
0x180006e03  mov     [rsp+168h+var_148], rcx
0x180006e08  mov     r8d, [rsp+168h+var_124]
0x180006e0d  call    McTemplateU0qzzz_EtwEventWriteTransfer
0x180006e12  nop
0x180006e13  mov     rcx, [rsp+168h+var_118]; void *
0x180006e18  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006e1d  mov     rcx, [rsp+168h+var_108]; void *
0x180006e22  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006e27  mov     rcx, [rsp+168h+var_100]
0x180006e2c  test    rcx, rcx
0x180006e2f  jz      short loc_180006E40
0x180006e31  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z; Free<HeapAllocator>(_EAP_ATTRIBUTES &)
0x180006e36  mov     rcx, [rsp+168h+var_100]; void *
0x180006e3b  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006e40  mov     rcx, [rsp+168h+var_F0]
0x180006e45  test    rcx, rcx
0x180006e48  jz      short loc_180006E59
0x180006e4a  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x180006e4f  mov     rcx, [rsp+168h+var_F0]; void *
0x180006e54  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006e59  mov     rcx, [rsp+168h+var_E8]; void *
0x180006e61  test    rcx, rcx
0x180006e64  jz      short loc_180006E79
0x180006e66  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<HeapAllocator>(_EAP_ERROR &)
0x180006e6b  mov     rcx, [rsp+168h+var_E8]; void *
0x180006e73  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006e78  nop
0x180006e79  mov     eax, ebx
0x180006e7b  lea     r11, [rsp+168h+var_18]
0x180006e83  mov     rbx, [r11+20h]
0x180006e87  mov     rsi, [r11+30h]
0x180006e8b  movaps  xmm6, xmmword ptr [r11-10h]
0x180006e90  movaps  xmm7, xmmword ptr [r11-20h]
0x180006e95  movaps  xmm8, xmmword ptr [r11-30h]
0x180006e9a  movaps  xmm9, xmmword ptr [r11-40h]
0x180006e9f  movaps  xmm10, xmmword ptr [r11-50h]
0x180006ea4  mov     rsp, r11
0x180006ea7  pop     r15
0x180006ea9  pop     r14
0x180006eab  pop     rdi
0x180006eac  retn
```
