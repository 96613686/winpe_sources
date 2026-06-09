# Rdp::Stack::Graphics::CMonitorConfigChannel::ProcessCapsAdvertise(uint,void const *)

- ea: `0x1800161b8`
- end: `0x1800162fb`
- name: `?ProcessCapsAdvertise@CMonitorConfigChannel@Graphics@Stack@Rdp@@AEAAXIPEBX@Z`
- size: `323`
- prototype: `void __fastcall(Rdp::Stack::Graphics::CMonitorConfigChannel *__hidden this, unsigned int, const void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180015fa0`

## callees

- `0x18000cf28`
- `0x1800130dc`
- `0x1800135a0`
- `0x180015d80`
- `0x1800161b8`
- `0x18002a010`

## string_xrefs

- `0x1800161f7`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`
- `0x18001626c`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`
- `0x1800162c9`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Rdp::Stack::Graphics::CMonitorConfigChannel::ProcessCapsAdvertise(
        Rdp::Stack::Graphics::CMonitorConfigChannel *this,
        unsigned int a2,
        const void *a3)
{
  char *v4; // r14
  unsigned int v5; // eax
  unsigned int v6; // edi
  __int64 v7; // rax
  unsigned int v8; // edi
  unsigned int *v9; // rbx
  unsigned int Confirm; // eax
  unsigned int v11; // eax
  char *v12; // [rsp+28h] [rbp-40h]
  char *v13; // [rsp+28h] [rbp-40h]
  char *v14; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int *v16; // [rsp+70h] [rbp+8h] BYREF
  __int64 v17; // [rsp+88h] [rbp+20h] BYREF

  v4 = (char *)this + 88;
  v5 = (**((__int64 (__fastcall ***)(char *, const void *, _QWORD))this + 11))((char *)this + 88, a3, a2);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xC9,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
    (const char *)v5,
    (int)"ParseAdvertise failed",
    v12);
  v6 = 0;
  v17 = 0;
  v7 = *((_QWORD *)this + 12);
  if ( v7 )
  {
    v6 = *(_DWORD *)(v7 + 8);
    v17 = v6;
  }
  v8 = v6 + 8;
  std::make_unique<unsigned char [0],0>(&v16, v8);
  v9 = v16;
  *v16 = v8;
  v9[1] = 2;
  Confirm = CCapsServerImpl<Rdp::Stack::Graphics::CMonitorCfgServerCapsBase>::GetConfirm(v4, v9 + 2, &v17);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xE2,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
    (const char *)Confirm,
    (int)"m_ServerCaps.GetConfirm failed",
    v13);
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *, __int64, int, unsigned int, int, _QWORD))(**((_QWORD **)this + 14) + 24LL))(
          *((_QWORD *)this + 14),
          v8,
          v9,
          2,
          1,
          v8,
          3,
          0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xF0,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
    (const char *)v11,
    (int)"Failed to send RDPCFG_PDU_CMDID_CAPSCONFIRM PDU",
    v14);
  v16 = 0;
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v16);
}

```

## disassembly

```asm
0x1800161b8  mov     [rsp+arg_8], rbx
0x1800161bd  push    rsi
0x1800161be  push    rdi
0x1800161bf  push    r14
0x1800161c1  sub     rsp, 50h
0x1800161c5  mov     r9, r8
0x1800161c8  mov     rsi, rcx
0x1800161cb  lea     r14, [rcx+58h]
0x1800161cf  mov     rax, [r14]
0x1800161d2  mov     r8d, edx
0x1800161d5  mov     rdx, r9
0x1800161d8  mov     rcx, r14
0x1800161db  mov     rax, [rax]
0x1800161de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161e3  mov     rcx, [rsp+68h]; this
0x1800161e8  lea     rdx, aParseadvertise; "ParseAdvertise failed"
0x1800161ef  mov     qword ptr [rsp+68h+var_48], rdx; int
0x1800161f4  mov     r9d, eax; char *
0x1800161f7  lea     r8, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x1800161fe  mov     edx, 0C9h; void *
0x180016203  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180016208  xor     edi, edi
0x18001620a  mov     [rsp+68h+arg_18], rdi
0x180016212  mov     rax, [rsi+60h]
0x180016216  test    rax, rax
0x180016219  jz      short loc_180016226
0x18001621b  mov     edi, [rax+8]
0x18001621e  mov     [rsp+68h+arg_18], rdi
0x180016226  add     edi, 8
0x180016229  mov     edx, edi
0x18001622b  lea     rcx, [rsp+68h+arg_0]
0x180016230  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x180016235  nop
0x180016236  mov     rbx, [rsp+68h+arg_0]
0x18001623b  mov     [rbx], edi
0x18001623d  mov     dword ptr [rbx+4], 2
0x180016244  lea     rdx, [rbx+8]
0x180016248  lea     r8, [rsp+68h+arg_18]
0x180016250  mov     rcx, r14
0x180016253  call    ?GetConfirm@?$CCapsServerImpl@VCMonitorCfgServerCapsBase@Graphics@Stack@Rdp@@@@QEAAJPEAXPEA_K@Z; CCapsServerImpl<Rdp::Stack::Graphics::CMonitorCfgServerCapsBase>::GetConfirm(void *,unsigned __int64 *)
0x180016258  mov     rcx, [rsp+68h]; this
0x18001625d  lea     rdx, aMServercapsGet; "m_ServerCaps.GetConfirm failed"
0x180016264  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180016269  mov     r9d, eax; char *
0x18001626c  lea     r8, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180016273  mov     edx, 0E2h; void *
0x180016278  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001627d  mov     rcx, [rsi+70h]
0x180016281  mov     rax, [rcx]
0x180016284  mov     [rsp+68h+var_30], 0
0x18001628d  mov     [rsp+68h+var_38], 3
0x180016295  mov     dword ptr [rsp+68h+var_40], edi; char *
0x180016299  mov     [rsp+68h+var_48], 1
0x1800162a1  mov     r9d, 2
0x1800162a7  mov     r8, rbx
0x1800162aa  mov     edx, edi
0x1800162ac  mov     rax, [rax+18h]
0x1800162b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162b5  mov     rcx, [rsp+68h]; this
0x1800162ba  lea     rdx, aFailedToSendRd_1; "Failed to send RDPCFG_PDU_CMDID_CAPSCON"...
0x1800162c1  mov     qword ptr [rsp+68h+var_48], rdx; int
0x1800162c6  mov     r9d, eax; char *
0x1800162c9  lea     r8, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x1800162d0  mov     edx, 0F0h; void *
0x1800162d5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800162da  mov     [rsp+68h+arg_0], 0
0x1800162e3  lea     rcx, [rsp+68h+arg_0]
0x1800162e8  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x1800162ed  mov     rbx, [rsp+68h+arg_8]
0x1800162f2  add     rsp, 50h
0x1800162f6  pop     r14
0x1800162f8  pop     rdi
0x1800162f9  pop     rsi
0x1800162fa  retn
```
