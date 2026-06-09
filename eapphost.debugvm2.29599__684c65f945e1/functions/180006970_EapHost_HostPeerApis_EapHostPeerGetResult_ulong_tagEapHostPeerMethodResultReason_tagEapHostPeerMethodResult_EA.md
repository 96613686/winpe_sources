# EapHost::HostPeerApis::EapHostPeerGetResult(ulong,tagEapHostPeerMethodResultReason,tagEapHostPeerMethodResult *,_EAP_ERROR * *)

- ea: `0x180006970`
- end: `0x180006c1d`
- name: `?EapHostPeerGetResult@HostPeerApis@EapHost@@UEAAJKW4tagEapHostPeerMethodResultReason@@PEAUtagEapHostPeerMethodResult@@PEAPEAU_EAP_ERROR@@@Z`
- size: `685`
- prototype: `__int64 __fastcall(EapHost::HostPeerApis *__hidden this, unsigned int, enum tagEapHostPeerMethodResultReason, struct tagEapHostPeerMethodResult *, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18000343c`
- `0x180003dbc`
- `0x180003f14`
- `0x180003f70`
- `0x180003fa4`
- `0x1800040d0`
- `0x180006970`
- `0x1800072cc`
- `0x180009bec`
- `0x18000a050`
- `0x18000a0f4`
- `0x180025b18`
- `0x18002ed84`

## string_xrefs

- `0x180006a52`: `com_ref:Assign`

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
  if ( !v8 && !v19 && (byte_18004E841 & 1) != 0 )
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
0x180006970  mov     rax, rsp
0x180006973  mov     [rax+8], rbx
0x180006977  mov     [rax+18h], rsi
0x18000697b  mov     [rax+10h], edx
0x18000697e  push    rdi
0x18000697f  push    r14
0x180006981  push    r15
0x180006983  sub     rsp, 150h
0x18000698a  movaps  xmmword ptr [rax-28h], xmm6
0x18000698e  movaps  xmmword ptr [rax-38h], xmm7
0x180006992  movaps  xmmword ptr [rax-48h], xmm8
0x180006997  movaps  xmmword ptr [rax-58h], xmm9
0x18000699c  movaps  xmmword ptr [rax-68h], xmm10
0x1800069a1  mov     r14, r9
0x1800069a4  mov     esi, r8d
0x1800069a7  mov     r15d, edx
0x1800069aa  xor     ebx, ebx
0x1800069ac  mov     [rax+20h], ebx
0x1800069af  xor     edx, edx; Val
0x1800069b1  lea     r8d, [rbx+48h]; Size
0x1800069b5  lea     rcx, [rsp+168h+var_128]; void *
0x1800069ba  call    memset_0
0x1800069bf  nop
0x1800069c0  lea     rdi, WPP_GLOBAL_Control
0x1800069c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069ce  cmp     rcx, rdi
0x1800069d1  jz      short loc_1800069F3
0x1800069d3  test    byte ptr [rcx+1Ch], 4
0x1800069d7  jz      short loc_1800069F3
0x1800069d9  lea     edx, [rbx+1Eh]
0x1800069dc  mov     dword ptr [rsp+168h+var_148], esi
0x1800069e0  mov     r9d, r15d
0x1800069e3  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x1800069ea  mov     rcx, [rcx+10h]
0x1800069ee  call    WPP_SF_dd
0x1800069f3  test    r14, r14
0x1800069f6  jnz     short loc_180006A02
0x1800069f8  mov     ebx, 80070057h
0x1800069fd  jmp     loc_180006AE1
0x180006a02  lea     r9, [rsp+168h+var_128]
0x180006a07  mov     r8d, esi
0x180006a0a  mov     edx, [rsp+168h+arg_8]
0x180006a11  mov     rcx, cs:?pHost@HostPeerApis@EapHost@@0V?$unique_ptr@VHost@Peer@EapHost@@U?$default_delete@VHost@Peer@EapHost@@@std@@@std@@A; std::unique_ptr<EapHost::Peer::Host> EapHost::HostPeerApis::pHost
0x180006a18  call    ?GetResult@Host@Peer@EapHost@@QEAAXIW4tagEapHostPeerMethodResultReason@@AEAV?$crt_ref@UtagEapHostPeerMethodResult@@@@@Z; EapHost::Peer::Host::GetResult(uint,tagEapHostPeerMethodResultReason,crt_ref<tagEapHostPeerMethodResult> &)
0x180006a1d  mov     esi, 50h ; 'P'
0x180006a22  mov     r8d, esi; Size
0x180006a25  xor     edx, edx; Val
0x180006a27  lea     rcx, [rsp+168h+var_D8]; void *
0x180006a2f  call    memset_0
0x180006a34  mov     [rsp+168h+var_90], 1
0x180006a3c  lea     rdx, [rsp+168h+var_128]
0x180006a41  lea     rcx, [rsp+168h+var_D8]; void *
0x180006a49  call    ??$Copy@VTaskAllocator@@@@YA_NAEAUtagEapHostPeerMethodResult@@AEBU0@@Z; Copy<TaskAllocator>(tagEapHostPeerMethodResult &,tagEapHostPeerMethodResult const &)
0x180006a4e  test    al, al
0x180006a50  jnz     short loc_180006A5E
0x180006a52  lea     rcx, aComRefAssign; "com_ref:Assign"
0x180006a59  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x180006a5e  movaps  xmm6, [rsp+168h+var_D8]
0x180006a66  movaps  xmm7, [rsp+168h+var_C8]
0x180006a6e  movaps  xmm8, [rsp+168h+var_B8]
0x180006a77  movaps  xmm9, [rsp+168h+var_A8]
0x180006a80  movsd   xmm10, [rsp+168h+var_98]
0x180006a8a  mov     r8, rsi; Size
0x180006a8d  xor     edx, edx; Val
0x180006a8f  lea     rcx, [rsp+168h+var_D8]; void *
0x180006a97  call    memset_0
0x180006a9c  mov     [rsp+168h+var_90], 1
0x180006aa4  movups  xmmword ptr [r14], xmm6
0x180006aa8  movups  xmmword ptr [r14+10h], xmm7
0x180006aad  movups  xmmword ptr [r14+20h], xmm8
0x180006ab2  movups  xmmword ptr [r14+30h], xmm9
0x180006ab7  movsd   qword ptr [r14+40h], xmm10
0x180006abd  lea     rcx, [rsp+168h+var_D8]; void *
0x180006ac5  call    ??$Free@VTaskAllocator@@@@YAXAEAUtagEapHostPeerMethodResult@@@Z; Free<TaskAllocator>(tagEapHostPeerMethodResult &)
0x180006aca  nop
0x180006acb  jmp     short loc_180006AE1
0x180006acd  jmp     short loc_180006AD3
0x180006acf  jmp     short loc_180006AD3
0x180006ad1  jmp     short $+2
0x180006ad3  mov     ebx, dword ptr [rsp+168h+arg_18]
0x180006ada  lea     rdi, WPP_GLOBAL_Control
0x180006ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ae8  cmp     rcx, rdi
0x180006aeb  jz      short loc_180006B26
0x180006aed  test    byte ptr [rcx+1Ch], 4
0x180006af1  jz      short loc_180006B26
0x180006af3  mov     edx, 1Fh
0x180006af8  mov     eax, [rsp+168h+var_124]
0x180006afc  mov     [rsp+168h+var_138], eax
0x180006b00  mov     eax, [rsp+168h+var_128]
0x180006b04  mov     dword ptr [rsp+168h+var_140], eax
0x180006b08  mov     eax, [rsp+168h+arg_8]
0x180006b0f  mov     dword ptr [rsp+168h+var_148], eax
0x180006b13  mov     r9d, ebx
0x180006b16  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180006b1d  mov     rcx, [rcx+10h]
0x180006b21  call    WPP_SF_dddd
0x180006b26  test    ebx, ebx
0x180006b28  jnz     short loc_180006B83
0x180006b2a  cmp     [rsp+168h+var_128], ebx
0x180006b2e  jnz     short loc_180006B83
0x180006b30  test    cs:byte_18004E841, 1
0x180006b37  jz      short loc_180006B83
0x180006b39  mov     rax, [rsp+168h+var_E8]
0x180006b41  test    rax, rax
0x180006b44  jz      short loc_180006B4C
0x180006b46  mov     rdx, [rax+50h]
0x180006b4a  jmp     short loc_180006B4E
0x180006b4c  xor     edx, edx
0x180006b4e  test    rax, rax
0x180006b51  jz      short loc_180006B59
0x180006b53  mov     rcx, [rax+48h]
0x180006b57  jmp     short loc_180006B5B
0x180006b59  xor     ecx, ecx
0x180006b5b  mov     rax, [rsp+168h+var_F0]
0x180006b60  test    rax, rax
0x180006b63  jz      short loc_180006B6B
0x180006b65  mov     r9, [rax+18h]
0x180006b69  jmp     short loc_180006B6E
0x180006b6b  xor     r9d, r9d
0x180006b6e  mov     [rsp+168h+var_140], rdx
0x180006b73  mov     [rsp+168h+var_148], rcx
0x180006b78  mov     r8d, [rsp+168h+var_124]
0x180006b7d  call    McTemplateU0qzzz_EtwEventWriteTransfer
0x180006b82  nop
0x180006b83  mov     rcx, [rsp+168h+var_118]; void *
0x180006b88  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006b8d  mov     rcx, [rsp+168h+var_108]; void *
0x180006b92  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006b97  mov     rcx, [rsp+168h+var_100]
0x180006b9c  test    rcx, rcx
0x180006b9f  jz      short loc_180006BB0
0x180006ba1  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z; Free<HeapAllocator>(_EAP_ATTRIBUTES &)
0x180006ba6  mov     rcx, [rsp+168h+var_100]; void *
0x180006bab  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006bb0  mov     rcx, [rsp+168h+var_F0]
0x180006bb5  test    rcx, rcx
0x180006bb8  jz      short loc_180006BC9
0x180006bba  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x180006bbf  mov     rcx, [rsp+168h+var_F0]; void *
0x180006bc4  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006bc9  mov     rcx, [rsp+168h+var_E8]; void *
0x180006bd1  test    rcx, rcx
0x180006bd4  jz      short loc_180006BE9
0x180006bd6  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<HeapAllocator>(_EAP_ERROR &)
0x180006bdb  mov     rcx, [rsp+168h+var_E8]; void *
0x180006be3  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006be8  nop
0x180006be9  mov     eax, ebx
0x180006beb  lea     r11, [rsp+168h+var_18]
0x180006bf3  mov     rbx, [r11+20h]
0x180006bf7  mov     rsi, [r11+30h]
0x180006bfb  movaps  xmm6, xmmword ptr [r11-10h]
0x180006c00  movaps  xmm7, xmmword ptr [r11-20h]
0x180006c05  movaps  xmm8, xmmword ptr [r11-30h]
0x180006c0a  movaps  xmm9, xmmword ptr [r11-40h]
0x180006c0f  movaps  xmm10, xmmword ptr [r11-50h]
0x180006c14  mov     rsp, r11
0x180006c17  pop     r15
0x180006c19  pop     r14
0x180006c1b  pop     rdi
0x180006c1c  retn
```
