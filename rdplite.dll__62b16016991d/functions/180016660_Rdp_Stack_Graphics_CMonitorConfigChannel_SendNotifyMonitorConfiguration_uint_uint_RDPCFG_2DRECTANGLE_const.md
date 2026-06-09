# Rdp::Stack::Graphics::CMonitorConfigChannel::SendNotifyMonitorConfiguration(uint,uint,_RDPCFG_2DRECTANGLE const &)

- ea: `0x180016660`
- end: `0x18001672f`
- name: `?SendNotifyMonitorConfiguration@CMonitorConfigChannel@Graphics@Stack@Rdp@@AEAAXIIAEBU_RDPCFG_2DRECTANGLE@@@Z`
- size: `207`
- prototype: `void __fastcall(Rdp::Stack::Graphics::CMonitorConfigChannel *__hidden this, unsigned int, unsigned int, const struct _RDPCFG_2DRECTANGLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016304`

## callees

- `0x18000cf28`
- `0x1800130dc`
- `0x1800135a0`
- `0x18002a010`

## string_xrefs

- `0x1800166fc`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`
- `0x1800166ed`: `Failed to send RDPCFG_PDU_CMDID_NOTIFY_MONITOR_CONFIGURATION PDU`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Rdp::Stack::Graphics::CMonitorConfigChannel::SendNotifyMonitorConfiguration(
        Rdp::Stack::Graphics::CMonitorConfigChannel *this,
        int a2,
        int a3,
        const struct _RDPCFG_2DRECTANGLE *a4)
{
  _DWORD *v8; // r8
  unsigned int v9; // eax
  char *v10; // [rsp+28h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  _DWORD *v12; // [rsp+80h] [rbp+8h] BYREF

  std::make_unique<unsigned char [0],0>(&v12, 32);
  v8 = v12;
  *v12 = 32;
  v8[1] = 4;
  v8[2] = a2;
  v8[3] = a3;
  *((_OWORD *)v8 + 1) = *(_OWORD *)a4;
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _DWORD *, __int64, int, int, int, _QWORD))(**((_QWORD **)this + 14)
                                                                                            + 24LL))(
         *((_QWORD *)this + 14),
         32,
         v8,
         2,
         1,
         32,
         3,
         0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1EB,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
    (const char *)v9,
    (int)"Failed to send RDPCFG_PDU_CMDID_NOTIFY_MONITOR_CONFIGURATION PDU",
    v10);
  v12 = 0;
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v12);
}

```

## disassembly

```asm
0x180016660  mov     rax, rsp
0x180016663  push    rbx
0x180016664  push    rbp
0x180016665  push    rsi
0x180016666  push    rdi
0x180016667  sub     rsp, 58h
0x18001666b  mov     rbp, r9
0x18001666e  mov     edi, r8d
0x180016671  mov     ebx, edx
0x180016673  mov     rsi, rcx
0x180016676  mov     edx, 20h ; ' '
0x18001667b  lea     rcx, [rax+8]
0x18001667f  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x180016684  nop
0x180016685  mov     r8, [rsp+78h+arg_0]
0x18001668d  mov     dword ptr [r8], 20h ; ' '
0x180016694  mov     dword ptr [r8+4], 4
0x18001669c  mov     [r8+8], ebx
0x1800166a0  mov     [r8+0Ch], edi
0x1800166a4  movups  xmm0, xmmword ptr [rbp+0]
0x1800166a8  movdqu  xmmword ptr [r8+10h], xmm0
0x1800166ae  mov     rcx, [rsi+70h]
0x1800166b2  mov     rax, [rcx]
0x1800166b5  mov     [rsp+78h+var_40], 0
0x1800166be  mov     [rsp+78h+var_48], 3
0x1800166c6  mov     dword ptr [rsp+78h+var_50], 20h ; ' '; char *
0x1800166ce  mov     [rsp+78h+var_58], 1
0x1800166d6  mov     edx, 20h ; ' '
0x1800166db  lea     r9d, [rdx-1Eh]
0x1800166df  mov     rax, [rax+18h]
0x1800166e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166e8  mov     rcx, [rsp+78h]; this
0x1800166ed  lea     rdx, aFailedToSendRd_2; "Failed to send RDPCFG_PDU_CMDID_NOTIFY_"...
0x1800166f4  mov     qword ptr [rsp+78h+var_58], rdx; int
0x1800166f9  mov     r9d, eax; char *
0x1800166fc  lea     r8, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180016703  mov     edx, 1EBh; void *
0x180016708  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001670d  mov     [rsp+78h+arg_0], 0
0x180016719  lea     rcx, [rsp+78h+arg_0]
0x180016721  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180016726  add     rsp, 58h
0x18001672a  pop     rdi
0x18001672b  pop     rsi
0x18001672c  pop     rbp
0x18001672d  pop     rbx
0x18001672e  retn
```
