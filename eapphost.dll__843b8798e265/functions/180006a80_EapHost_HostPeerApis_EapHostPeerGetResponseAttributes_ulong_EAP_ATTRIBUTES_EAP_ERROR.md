# EapHost::HostPeerApis::EapHostPeerGetResponseAttributes(ulong,_EAP_ATTRIBUTES *,_EAP_ERROR * *)

- ea: `0x180006a80`
- end: `0x180006bf7`
- name: `?EapHostPeerGetResponseAttributes@HostPeerApis@EapHost@@UEAAJKPEAU_EAP_ATTRIBUTES@@PEAPEAU_EAP_ERROR@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(EapHost::HostPeerApis *__hidden this, unsigned int, struct _EAP_ATTRIBUTES *, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180003b00`
- `0x1800040f4`
- `0x180006a80`
- `0x18000a24c`
- `0x18000a528`
- `0x18001ebb8`
- `0x180025ebc`
- `0x18002fe84`

## string_xrefs

- `0x180006b4e`: `com_ref:Assign`

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
0x180006a80  mov     rax, rsp
0x180006a83  mov     [rax+8], rbx
0x180006a87  mov     [rax+20h], r9
0x180006a8b  mov     [rax+10h], edx
0x180006a8e  push    rdi
0x180006a8f  sub     rsp, 90h
0x180006a96  mov     rdi, r8
0x180006a99  mov     r9d, edx
0x180006a9c  mov     dword ptr [rax+18h], 0
0x180006aa3  xorps   xmm0, xmm0
0x180006aa6  movdqu  xmmword ptr [rax-38h], xmm0
0x180006aab  mov     qword ptr [rax-28h], 0
0x180006ab3  movups  xmmword ptr [rax-20h], xmm0
0x180006ab7  mov     dword ptr [rax-20h], 0
0x180006abe  mov     qword ptr [rax-18h], 0
0x180006ac6  lea     rbx, WPP_GLOBAL_Control
0x180006acd  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ad4  cmp     rcx, rbx
0x180006ad7  jz      short loc_180006AF4
0x180006ad9  test    byte ptr [rcx+1Ch], 4
0x180006add  jz      short loc_180006AF4
0x180006adf  mov     edx, 24h ; '$'
0x180006ae4  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180006aeb  mov     rcx, [rcx+10h]
0x180006aef  call    WPP_SF_d
0x180006af4  test    rdi, rdi
0x180006af7  jnz     short loc_180006B09
0x180006af9  mov     dword ptr [rsp+98h+arg_10], 80070057h
0x180006b04  jmp     loc_180006B91
0x180006b09  xorps   xmm0, xmm0
0x180006b0c  movups  xmmword ptr [rdi], xmm0
0x180006b0f  lea     r8, [rsp+98h+var_38]; struct EapHost::AutoAttributes *
0x180006b14  mov     edx, [rsp+98h+arg_8]; unsigned int
0x180006b1b  mov     rcx, cs:?pHost@HostPeerApis@EapHost@@0V?$unique_ptr@VHost@Peer@EapHost@@U?$default_delete@VHost@Peer@EapHost@@@std@@@std@@A; this
0x180006b22  call    ?GetAttributes@Host@Peer@EapHost@@QEAAXIAEAVAutoAttributes@3@@Z; EapHost::Peer::Host::GetAttributes(uint,EapHost::AutoAttributes &)
0x180006b27  xorps   xmm0, xmm0
0x180006b2a  xor     eax, eax
0x180006b2c  movups  [rsp+98h+var_50], xmm0
0x180006b31  mov     [rsp+98h+var_40], rax
0x180006b36  mov     byte ptr [rsp+98h+var_40], 1
0x180006b3b  lea     rdx, [rsp+98h+var_20]
0x180006b40  lea     rcx, [rsp+98h+var_50]
0x180006b45  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_ATTRIBUTES@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_ATTRIBUTES &,_EAP_ATTRIBUTES const &)
0x180006b4a  test    al, al
0x180006b4c  jnz     short loc_180006B5A
0x180006b4e  lea     rcx, aComRefAssign; "com_ref:Assign"
0x180006b55  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x180006b5a  movups  xmm1, [rsp+98h+var_50]
0x180006b5f  xorps   xmm0, xmm0
0x180006b62  xor     eax, eax
0x180006b64  movups  [rsp+98h+var_50], xmm0
0x180006b69  mov     [rsp+98h+var_40], rax
0x180006b6e  mov     byte ptr [rsp+98h+var_40], 1
0x180006b73  movdqu  xmmword ptr [rdi], xmm1
0x180006b77  lea     rcx, [rsp+98h+var_50]
0x180006b7c  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z; Free<TaskAllocator>(_EAP_ATTRIBUTES &)
0x180006b81  nop
0x180006b82  jmp     short loc_180006B91
0x180006b84  jmp     short loc_180006B8A
0x180006b86  jmp     short loc_180006B8A
0x180006b88  jmp     short $+2
0x180006b8a  lea     rbx, WPP_GLOBAL_Control
0x180006b91  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b98  cmp     rcx, rbx
0x180006b9b  jz      short loc_180006BD4
0x180006b9d  test    byte ptr [rcx+1Ch], 4
0x180006ba1  jz      short loc_180006BD4
0x180006ba3  mov     edx, 25h ; '%'
0x180006ba8  mov     eax, dword ptr [rsp+98h+var_28]
0x180006bac  mov     [rsp+98h+var_70], eax
0x180006bb0  mov     eax, [rsp+98h+arg_8]
0x180006bb7  mov     [rsp+98h+var_78], eax
0x180006bbb  mov     r9d, dword ptr [rsp+98h+arg_10]
0x180006bc3  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180006bca  mov     rcx, [rcx+10h]
0x180006bce  call    WPP_SF_ddd
0x180006bd3  nop
0x180006bd4  lea     rcx, [rsp+98h+var_38]; this
0x180006bd9  call    ??1AutoAttributes@EapHost@@QEAA@XZ; EapHost::AutoAttributes::~AutoAttributes(void)
0x180006bde  mov     eax, dword ptr [rsp+98h+arg_10]
0x180006be5  mov     rbx, [rsp+98h+arg_0]
0x180006bed  add     rsp, 90h
0x180006bf4  pop     rdi
0x180006bf5  retn
```
