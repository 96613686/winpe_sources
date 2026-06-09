# Rdp::Stack::Graphics::CMonitorConfig::CMonitorConfig(uint,tagTS_MONITOR_DEF const &,tagTS_MONITOR_ATTRIBUTES const &,tagTS_MONITOR_VAIL_ATTRIBUTES const &,IPropertyStore *)

- ea: `0x180016b1c`
- end: `0x180016cd9`
- name: `??0CMonitorConfig@Graphics@Stack@Rdp@@QEAA@IAEBUtagTS_MONITOR_DEF@@AEBUtagTS_MONITOR_ATTRIBUTES@@AEBUtagTS_MONITOR_VAIL_ATTRIBUTES@@PEAUIPropertyStore@@@Z`
- size: `445`
- prototype: `Rdp::Stack::Graphics::CMonitorConfig *__fastcall(Rdp::Stack::Graphics::CMonitorConfig *this, int, const struct tagTS_MONITOR_DEF *, const struct tagTS_MONITOR_ATTRIBUTES *, const struct tagTS_MONITOR_VAIL_ATTRIBUTES *, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c0f0`

## callees

- `0x180004154`
- `0x18000a0e4`
- `0x180016a90`
- `0x180016b1c`
- `0x180017808`

## pseudocode

```c
Rdp::Stack::Graphics::CMonitorConfig *__fastcall Rdp::Stack::Graphics::CMonitorConfig::CMonitorConfig(
        Rdp::Stack::Graphics::CMonitorConfig *this,
        int a2,
        const struct tagTS_MONITOR_DEF *a3,
        const struct tagTS_MONITOR_ATTRIBUTES *a4,
        const struct tagTS_MONITOR_VAIL_ATTRIBUTES *a5,
        struct IPropertyStore *a6)
{
  int v10; // eax
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // eax
  __int64 v15; // rdx
  int v16; // r8d

  Rdp::Utils::Com::ComObject<Rdp::Stack::Graphics::CMonitorConfig,Rdp::Stack::IMonitorConfig>::ComObject<Rdp::Stack::Graphics::CMonitorConfig,Rdp::Stack::IMonitorConfig>();
  *(_QWORD *)this = &Rdp::Stack::Graphics::CMonitorConfig::`vftable'{for `Rdp::Utils::Com::IUnknownBase'};
  *((_QWORD *)this + 10) = &Rdp::Stack::Graphics::CMonitorConfig::`vftable'{for `Rdp::Stack::IMonitorConfig'};
  wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
    (char *)this + 88,
    a6);
  *((_QWORD *)this + 12) = 0;
  *(_OWORD *)((char *)this + 104) = 0;
  *(_OWORD *)((char *)this + 120) = 0;
  *(_OWORD *)((char *)this + 136) = 0;
  *(_OWORD *)((char *)this + 152) = 0;
  *(_OWORD *)((char *)this + 168) = 0;
  *(_OWORD *)((char *)this + 184) = 0;
  memset_0((char *)this + 200, 0, 0x4Cu);
  *(_QWORD *)((char *)this + 276) = 0;
  *((_DWORD *)this + 71) = 0;
  *((_OWORD *)this + 18) = 0;
  *((_OWORD *)this + 19) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_DWORD *)this + 29) = a2;
  *((_DWORD *)this + 32) = *(_DWORD *)a3;
  *((_DWORD *)this + 33) = *((_DWORD *)a3 + 1);
  *((_DWORD *)this + 34) = *((_DWORD *)a3 + 2) - *(_DWORD *)a3 + 1;
  v10 = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1) + 1;
  *((_DWORD *)this + 41) = 1;
  *((_DWORD *)this + 35) = v10;
  v11 = *((_DWORD *)a4 + 2);
  if ( !v11 )
    goto LABEL_8;
  v12 = v11 - 90;
  if ( !v12 )
  {
    *((_DWORD *)this + 37) = 90;
    goto LABEL_9;
  }
  v13 = v12 - 90;
  if ( !v13 )
  {
    *((_DWORD *)this + 37) = 180;
    goto LABEL_9;
  }
  if ( v13 != 90 )
  {
LABEL_8:
    *((_DWORD *)this + 37) = 0;
    goto LABEL_9;
  }
  *((_DWORD *)this + 37) = 270;
LABEL_9:
  *((_DWORD *)this + 44) = *((_DWORD *)a4 + 3);
  *((_DWORD *)this + 45) = *((_DWORD *)a4 + 4);
  *((_DWORD *)this + 48) = *(_DWORD *)a4;
  *((_DWORD *)this + 49) = *((_DWORD *)a4 + 1);
  v14 = *(_DWORD *)a5;
  v15 = *((unsigned int *)a5 + 2);
  v16 = *((_DWORD *)a5 + 3);
  *((_DWORD *)this + 75) = *((_DWORD *)a5 + 1);
  *((_DWORD *)this + 74) = v14;
  *((_DWORD *)this + 76) = v15;
  *((_DWORD *)this + 77) = v16;
  *((_DWORD *)this + 78) = *((_DWORD *)a5 + 4);
  *((_DWORD *)this + 79) = *((_DWORD *)a5 + 5);
  *((_DWORD *)this + 25) = 142;
  Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig(this, v15, v16, (int)a5);
  return this;
}

```

## disassembly

```asm
0x180016b1c  push    rbx
0x180016b1e  push    rsi
0x180016b1f  push    rdi
0x180016b20  push    r14
0x180016b22  sub     rsp, 28h
0x180016b26  mov     r14, r9
0x180016b29  mov     rdi, r8
0x180016b2c  mov     ebx, edx
0x180016b2e  mov     rsi, rcx
0x180016b31  call    ??0?$ComObject@VCMonitorConfig@Graphics@Stack@Rdp@@UIMonitorConfig@34@@Com@Utils@Rdp@@IEAA@XZ; Rdp::Utils::Com::ComObject<Rdp::Stack::Graphics::CMonitorConfig,Rdp::Stack::IMonitorConfig>::ComObject<Rdp::Stack::Graphics::CMonitorConfig,Rdp::Stack::IMonitorConfig>(void)
0x180016b36  mov     rdx, [rsp+48h+arg_28]
0x180016b3b  lea     rax, ??_7CMonitorConfig@Graphics@Stack@Rdp@@6BIUnknownBase@Com@Utils@3@@; const Rdp::Stack::Graphics::CMonitorConfig::`vftable'{for `Rdp::Utils::Com::IUnknownBase'}
0x180016b42  mov     [rsi], rax
0x180016b45  lea     rcx, [rsi+58h]
0x180016b49  lea     rax, ??_7CMonitorConfig@Graphics@Stack@Rdp@@6BIMonitorConfig@23@@; const Rdp::Stack::Graphics::CMonitorConfig::`vftable'{for `Rdp::Stack::IMonitorConfig'}
0x180016b50  mov     [rsi+50h], rax
0x180016b54  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180016b59  mov     qword ptr [rsi+60h], 0
0x180016b61  lea     rcx, [rsi+0C8h]; void *
0x180016b68  xorps   xmm1, xmm1
0x180016b6b  xorps   xmm0, xmm0
0x180016b6e  movups  xmmword ptr [rsi+68h], xmm0
0x180016b72  xor     edx, edx; Val
0x180016b74  movups  xmmword ptr [rsi+78h], xmm1
0x180016b78  movups  xmmword ptr [rsi+88h], xmm1
0x180016b7f  lea     r8d, [rdx+4Ch]; Size
0x180016b83  movups  xmmword ptr [rsi+98h], xmm1
0x180016b8a  movups  xmmword ptr [rsi+0A8h], xmm0
0x180016b91  movups  xmmword ptr [rsi+0B8h], xmm1
0x180016b98  call    memset_0
0x180016b9d  xor     eax, eax
0x180016b9f  xorps   xmm0, xmm0
0x180016ba2  mov     [rsi+114h], rax
0x180016ba9  mov     [rsi+11Ch], eax
0x180016baf  movups  xmmword ptr [rsi+120h], xmm0
0x180016bb6  movups  xmmword ptr [rsi+130h], xmm0
0x180016bbd  mov     [rsi+140h], rax
0x180016bc4  mov     [rsi+148h], rax
0x180016bcb  mov     [rsi+150h], rax
0x180016bd2  mov     [rsi+158h], rax
0x180016bd9  mov     [rsi+74h], ebx
0x180016bdc  mov     eax, [rdi]
0x180016bde  mov     [rsi+80h], eax
0x180016be4  mov     eax, [rdi+4]
0x180016be7  mov     [rsi+84h], eax
0x180016bed  mov     eax, [rdi+8]
0x180016bf0  sub     eax, [rdi]
0x180016bf2  inc     eax
0x180016bf4  mov     [rsi+88h], eax
0x180016bfa  mov     eax, [rdi+0Ch]
0x180016bfd  sub     eax, [rdi+4]
0x180016c00  inc     eax
0x180016c02  mov     dword ptr [rsi+0A4h], 1
0x180016c0c  mov     [rsi+8Ch], eax
0x180016c12  mov     ecx, [r14+8]
0x180016c16  test    ecx, ecx
0x180016c18  jz      short loc_180016C4B
0x180016c1a  mov     eax, 5Ah ; 'Z'
0x180016c1f  sub     ecx, eax
0x180016c21  jz      short loc_180016C43
0x180016c23  sub     ecx, eax
0x180016c25  jz      short loc_180016C37
0x180016c27  cmp     ecx, eax
0x180016c29  jnz     short loc_180016C4B
0x180016c2b  mov     dword ptr [rsi+94h], 10Eh
0x180016c35  jmp     short loc_180016C55
0x180016c37  mov     dword ptr [rsi+94h], 0B4h
0x180016c41  jmp     short loc_180016C55
0x180016c43  mov     [rsi+94h], eax
0x180016c49  jmp     short loc_180016C55
0x180016c4b  mov     dword ptr [rsi+94h], 0
0x180016c55  mov     eax, [r14+0Ch]
0x180016c59  mov     r9, [rsp+48h+arg_20]
0x180016c5e  mov     [rsi+0B0h], eax
0x180016c64  mov     eax, [r14+10h]
0x180016c68  mov     [rsi+0B4h], eax
0x180016c6e  mov     eax, [r14]
0x180016c71  mov     [rsi+0C0h], eax
0x180016c77  mov     eax, [r14+4]
0x180016c7b  mov     [rsi+0C4h], eax
0x180016c81  mov     ecx, [r9+4]
0x180016c85  mov     eax, [r9]
0x180016c88  mov     edx, [r9+8]
0x180016c8c  mov     r8d, [r9+0Ch]
0x180016c90  mov     [rsi+12Ch], ecx
0x180016c96  mov     rcx, rsi; this
0x180016c99  mov     [rsi+128h], eax
0x180016c9f  mov     [rsi+130h], edx
0x180016ca5  mov     [rsi+134h], r8d
0x180016cac  mov     eax, [r9+10h]
0x180016cb0  mov     [rsi+138h], eax
0x180016cb6  mov     eax, [r9+14h]
0x180016cba  mov     [rsi+13Ch], eax
0x180016cc0  mov     dword ptr [rsi+64h], 8Eh
0x180016cc7  call    ?ValidateAndFixMonitorConfig@CMonitorConfig@Graphics@Stack@Rdp@@AEAAXXZ; Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig(void)
0x180016ccc  mov     rax, rsi
0x180016ccf  add     rsp, 28h
0x180016cd3  pop     r14
0x180016cd5  pop     rdi
0x180016cd6  pop     rsi
0x180016cd7  pop     rbx
0x180016cd8  retn
```
