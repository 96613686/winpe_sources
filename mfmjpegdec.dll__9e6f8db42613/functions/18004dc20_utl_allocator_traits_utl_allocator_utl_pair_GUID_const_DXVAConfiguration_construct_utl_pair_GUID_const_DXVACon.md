# utl::allocator_traits<utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>>::construct<utl::pair<_GUID const,DXVAConfiguration>,utl::pair<_GUID const,DXVAConfiguration> const &>(utl::allocator<utl::pair<_GUID const,DXVAConfiguration>> &,utl::pair<_GUID const,DXVAConfiguration> *,utl::pair<_GUID const,DXVAConfiguration> const &)

- ea: `0x18004dc20`
- end: `0x18004dc84`
- name: `??$construct@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@AEBU12@@?$allocator_traits@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@utl@@@utl@@SA_NAEAV?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@1@PEAU?$pair@$$CBU_GUID@@UDXVAConfiguration@@@1@AEBU31@@Z`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004dbc0`

## callees

- `0x180024bf4`
- `0x18004b128`
- `0x18004dc8c`
- `0x18004e380`

## pseudocode

```c
char __fastcall utl::allocator_traits<utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>>::construct<utl::pair<_GUID const,DXVAConfiguration>,utl::pair<_GUID const,DXVAConfiguration> const &>(
        __int64 a1,
        _OWORD *a2,
        _OWORD *a3)
{
  DXVAConfiguration *v3; // rbx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = a1;
  v3 = (DXVAConfiguration *)(a2 + 1);
  *a2 = *a3;
  memset_0(a2 + 1, 0, 0x2C8u);
  DXVAConfiguration::DXVAConfiguration(v3);
  v6 = 0;
  LOBYTE(v3) = DXVAConfiguration::assign(v3, (const struct DXVAConfiguration *)(a3 + 1));
  utl::_DestroyOnExit<DXVAConfiguration>::~_DestroyOnExit<DXVAConfiguration>(&v6);
  return (char)v3;
}

```

## disassembly

```asm
0x18004dc20  mov     [rsp+arg_8], rbx
0x18004dc25  mov     [rsp+arg_0], rcx
0x18004dc2a  push    rdi
0x18004dc2b  sub     rsp, 20h
0x18004dc2f  movups  xmm0, xmmword ptr [r8]
0x18004dc33  lea     rbx, [rdx+10h]
0x18004dc37  mov     rdi, r8
0x18004dc3a  mov     r8d, 2C8h; Size
0x18004dc40  mov     rcx, rbx; void *
0x18004dc43  movdqu  xmmword ptr [rdx], xmm0
0x18004dc47  xor     edx, edx; Val
0x18004dc49  call    memset_0
0x18004dc4e  mov     rcx, rbx; this
0x18004dc51  call    ??0DXVAConfiguration@@QEAA@XZ; DXVAConfiguration::DXVAConfiguration(void)
0x18004dc56  lea     rdx, [rdi+10h]; struct DXVAConfiguration *
0x18004dc5a  mov     [rsp+28h+arg_0], 0
0x18004dc63  mov     rcx, rbx; this
0x18004dc66  call    ?assign@DXVAConfiguration@@QEAA_NAEBU1@@Z; DXVAConfiguration::assign(DXVAConfiguration const &)
0x18004dc6b  lea     rcx, [rsp+28h+arg_0]
0x18004dc70  mov     bl, al
0x18004dc72  call    ??1?$_DestroyOnExit@UDXVAConfiguration@@@utl@@QEAA@XZ; utl::_DestroyOnExit<DXVAConfiguration>::~_DestroyOnExit<DXVAConfiguration>(void)
0x18004dc77  mov     al, bl
0x18004dc79  mov     rbx, [rsp+28h+arg_8]
0x18004dc7e  add     rsp, 20h
0x18004dc82  pop     rdi
0x18004dc83  retn
```
