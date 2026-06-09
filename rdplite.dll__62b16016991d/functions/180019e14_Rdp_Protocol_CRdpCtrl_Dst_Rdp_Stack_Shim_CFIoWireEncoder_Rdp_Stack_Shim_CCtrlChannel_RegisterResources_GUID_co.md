# Rdp::Protocol::CRdpCtrl_Dst<Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>>::RegisterResources(_GUID const &,unsigned __int64,uint,Rdp::Avenc::AVENC_SHARED_RESOURCE const *)

- ea: `0x180019e14`
- end: `0x180019eff`
- name: `?RegisterResources@?$CRdpCtrl_Dst@V?$CFIoWireEncoder@VCCtrlChannel@Shim@Stack@Rdp@@@Shim@Stack@Rdp@@@Protocol@Rdp@@QEAAXAEBU_GUID@@_KIPEBUAVENC_SHARED_RESOURCE@Avenc@3@@Z`
- size: `235`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180021400`

## callees

- `0x18000cea4`
- `0x18000edbc`
- `0x180019290`
- `0x180019e14`

## string_xrefs

- `0x180019e42`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpCtrl/RdpCtrl.h`
- `0x180019e80`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpCtrl/RdpCtrl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Protocol::CRdpCtrl_Dst<Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>>::RegisterResources(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5)
{
  __int64 v5; // rbx
  __int64 v10; // rbx
  __int128 v11; // xmm0
  __int64 result; // rax
  __int64 v13; // rdx
  const char *v14; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = a4 - 1;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x242,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpCtrl/RdpCtrl.h",
    (const char *)0x80070057LL,
    (unsigned int)v5 > 7,
    (bool)"Invalid number of shared resources",
    v14);
  v10 = Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>::EnsureBuffer(a1, 8 * v5 + 52);
  wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
    (_DWORD)retaddr,
    583,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpCtrl/RdpCtrl.h",
    -2147024882,
    v10);
  *(_DWORD *)(v10 + 8) = 5;
  *(_DWORD *)v10 = 52;
  v11 = *a2;
  *(_QWORD *)(v10 + 28) = a3;
  *(_DWORD *)(v10 + 40) = a4;
  *(_OWORD *)(v10 + 12) = v11;
  result = *(_DWORD *)(a5 + 24) != 0;
  v13 = 0;
  for ( *(_DWORD *)(v10 + 36) = result; (unsigned int)v13 < a4; v13 = (unsigned int)(v13 + 1) )
  {
    result = *(_QWORD *)(32LL * (unsigned int)v13 + a5 + 8);
    *(_QWORD *)(v10 + 8 * v13 + 44) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180019e14  push    rbx
0x180019e16  push    rbp
0x180019e17  push    rsi
0x180019e18  push    rdi
0x180019e19  push    r14
0x180019e1b  push    r15
0x180019e1d  sub     rsp, 38h
0x180019e21  mov     r15, [rsp+68h+arg_20]
0x180019e29  lea     ebx, [r9-1]
0x180019e2d  mov     rsi, rdx
0x180019e30  mov     r14d, r9d
0x180019e33  lea     rdx, aInvalidNumberO; "Invalid number of shared resources"
0x180019e3a  mov     rbp, r8
0x180019e3d  mov     qword ptr [rsp+68h+var_40], rdx; bool
0x180019e42  lea     r8, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180019e49  mov     rdi, rcx
0x180019e4c  cmp     ebx, 7
0x180019e4f  mov     rcx, [rsp+68h]; this
0x180019e54  mov     r9d, 80070057h; char *
0x180019e5a  setnbe  al
0x180019e5d  mov     edx, 242h; void *
0x180019e62  mov     [rsp+68h+var_48], al; char
0x180019e66  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180019e6b  lea     rdx, ds:34h[rbx*8]
0x180019e73  mov     rcx, rdi
0x180019e76  call    ?EnsureBuffer@?$CFIoWireEncoder@VCCtrlChannel@Shim@Stack@Rdp@@@Shim@Stack@Rdp@@QEAAPEAX_K@Z; Rdp::Stack::Shim::CFIoWireEncoder<Rdp::Stack::Shim::CCtrlChannel>::EnsureBuffer(unsigned __int64)
0x180019e7b  mov     rcx, [rsp+68h]
0x180019e80  lea     r8, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180019e87  mov     rbx, rax
0x180019e8a  mov     r9d, 8007000Eh
0x180019e90  lea     rax, aUnableToEnsure_0; "Unable to ensure RDPCTRL_DST_REGISTER_R"...
0x180019e97  mov     edx, 247h
0x180019e9c  mov     qword ptr [rsp+68h+var_40], rax
0x180019ea1  mov     qword ptr [rsp+68h+var_48], rbx
0x180019ea6  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x180019eab  xor     eax, eax
0x180019ead  mov     dword ptr [rbx+8], 5
0x180019eb4  mov     dword ptr [rbx], 34h ; '4'
0x180019eba  movups  xmm0, xmmword ptr [rsi]
0x180019ebd  mov     [rbx+1Ch], rbp
0x180019ec1  mov     [rbx+28h], r14d
0x180019ec5  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x180019eca  cmp     [r15+18h], eax
0x180019ece  setnz   al
0x180019ed1  xor     edx, edx
0x180019ed3  mov     [rbx+24h], eax
0x180019ed6  test    r14d, r14d
0x180019ed9  jz      short loc_180019EF2
0x180019edb  mov     eax, edx
0x180019edd  shl     rax, 5
0x180019ee1  mov     rax, [rax+r15+8]
0x180019ee6  mov     [rbx+rdx*8+2Ch], rax
0x180019eeb  inc     edx
0x180019eed  cmp     edx, r14d
0x180019ef0  jb      short loc_180019EDB
0x180019ef2  add     rsp, 38h
0x180019ef6  pop     r15
0x180019ef8  pop     r14
0x180019efa  pop     rdi
0x180019efb  pop     rsi
0x180019efc  pop     rbp
0x180019efd  pop     rbx
0x180019efe  retn
```
