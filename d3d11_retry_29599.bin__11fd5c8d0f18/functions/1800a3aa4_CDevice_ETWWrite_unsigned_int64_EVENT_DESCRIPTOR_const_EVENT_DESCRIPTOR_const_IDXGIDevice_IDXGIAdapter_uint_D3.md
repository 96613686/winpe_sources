# CDevice::ETWWrite(unsigned __int64,_EVENT_DESCRIPTOR const *,_EVENT_DESCRIPTOR const *,IDXGIDevice *,IDXGIAdapter *,uint,D3D10DDI_HADAPTER,unsigned __int64,uint,unsigned __int64)

- ea: `0x1800a3aa4`
- end: `0x1800a3c7f`
- name: `?ETWWrite@CDevice@@QEAAX_KPEBU_EVENT_DESCRIPTOR@@1PEAUIDXGIDevice@@PEAUIDXGIAdapter@@IUD3D10DDI_HADAPTER@@_KI5@Z`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180094fc8`

## callees

- `0x18001a140`
- `0x18002488c`
- `0x18005eb30`
- `0x1800a22f0`
- `0x1800a3aa4`
- `0x1800a9d20`
- `0x1800c395c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800a3c40`
- `ntdll!EtwEventWrite` at `0x1800a3c40`

## pseudocode

```c
void __fastcall CDevice::ETWWrite(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        const struct _EVENT_DESCRIPTOR *a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11)
{
  __int64 *v11; // rsi
  CDevice *v16; // rcx
  bool v17; // al
  unsigned int v18; // r8d
  int v19; // edx
  __int64 v20; // rdx
  __int64 v21; // rax
  int v22; // eax
  int v23; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v24; // [rsp+24h] [rbp-DCh] BYREF
  __int64 v25; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v26[26]; // [rsp+30h] [rbp-D0h] BYREF

  v11 = (__int64 *)(a1 + 1240);
  if ( (a2 & 2) != 0 )
    CPrivateDataImpl<ID3D11DeviceChild>::ETWReportName((RTL_SRWLOCK *)(a1 + 16), a2, *v11);
  if ( (a2 & 4) != 0 )
  {
    v26[2] = &a5;
    v26[0] = v11;
    v26[4] = &a6;
    v26[6] = a1 + 1260;
    v26[8] = a1 + 1280;
    v26[1] = 8;
    v26[3] = 8;
    v26[5] = 8;
    v26[7] = 4;
    v26[9] = 4;
    CDevice::DriverSupportsComputeShaderPlusRawAndStructuredBuffersViaShader4x((CDevice *)a1);
    v17 = CDevice::DriverSupportsDoublePrecisionFloatShaderOps(v16);
    v26[11] = 4;
    v26[13] = 4;
    v26[15] = 8;
    v26[10] = &v23;
    v20 = v18 & 1 | (v18 >> 1) & 2 | (4 * v17) | v19;
    v23 = v20;
    v26[12] = &a7;
    v26[17] = 8;
    v26[14] = &a8;
    v26[16] = &a9;
    v26[18] = &a10;
    v21 = *(_QWORD *)(a1 + 1080);
    v26[19] = 4;
    v25 = v21 + 40768;
    v26[20] = &v25;
    v26[22] = &a11;
    v26[21] = 8;
    v26[23] = 8;
    v22 = CDevice::DDIFlags((CDevice *)a1, v20);
    v26[25] = 4;
    v24 = v22 & 0xFFFFFF31;
    v26[24] = &v24;
    EtwEventWrite(Direct3D11EtwProviderGuid_Context, a3, 13, v26);
  }
  if ( (a2 & 0x40002) != 0 )
    CContext::ETWWrite(*(CContext **)(a1 + 1080), a2, a4);
}

```

## disassembly

```asm
0x1800a3aa4  push    rbp
0x1800a3aa6  push    rbx
0x1800a3aa7  push    rsi
0x1800a3aa8  push    rdi
0x1800a3aa9  push    r12
0x1800a3aab  push    r14
0x1800a3aad  push    r15
0x1800a3aaf  lea     rbp, [rsp-10h]
0x1800a3ab4  sub     rsp, 110h
0x1800a3abb  mov     rax, cs:__security_cookie
0x1800a3ac2  xor     rax, rsp
0x1800a3ac5  mov     [rbp+40h+var_40], rax
0x1800a3ac9  lea     rsi, [rcx+4D8h]
0x1800a3ad0  mov     r14, r9
0x1800a3ad3  mov     r15, r8
0x1800a3ad6  mov     rbx, rdx
0x1800a3ad9  mov     rdi, rcx
0x1800a3adc  test    dl, 2
0x1800a3adf  jz      short loc_1800A3AED
0x1800a3ae1  mov     r8, [rsi]
0x1800a3ae4  add     rcx, 10h
0x1800a3ae8  call    ?ETWReportName@?$CPrivateDataImpl@UID3D11DeviceChild@@@@QEAAXPEBU_EVENT_DESCRIPTOR@@PEBX@Z; CPrivateDataImpl<ID3D11DeviceChild>::ETWReportName(_EVENT_DESCRIPTOR const *,void const *)
0x1800a3aed  mov     r12d, 4
0x1800a3af3  test    r12b, bl
0x1800a3af6  jz      loc_1800A3C46
0x1800a3afc  mov     r8d, [rdi+50Ch]
0x1800a3b03  lea     rax, [rbp+40h+arg_20]
0x1800a3b07  mov     [rsp+140h+var_100], rax
0x1800a3b0c  mov     rcx, rdi; this
0x1800a3b0f  lea     rax, [rbp+40h+arg_28]
0x1800a3b13  mov     [rsp+140h+var_110], rsi
0x1800a3b18  mov     [rsp+140h+var_F0], rax
0x1800a3b1d  lea     rax, [rdi+4ECh]
0x1800a3b24  mov     [rsp+140h+var_E0], rax
0x1800a3b29  lea     rax, [rdi+500h]
0x1800a3b30  mov     [rsp+140h+var_D0], rax
0x1800a3b35  mov     [rsp+140h+var_108], 8
0x1800a3b3e  mov     [rsp+140h+var_F8], 8
0x1800a3b47  mov     [rsp+140h+var_E8], 8
0x1800a3b50  mov     [rsp+140h+var_D8], r12
0x1800a3b55  mov     [rsp+140h+var_C8], r12
0x1800a3b5a  call    ?DriverSupportsComputeShaderPlusRawAndStructuredBuffersViaShader4x@CDevice@@QEBA_NXZ; CDevice::DriverSupportsComputeShaderPlusRawAndStructuredBuffersViaShader4x(void)
0x1800a3b5f  movzx   edx, al
0x1800a3b62  shl     edx, 3
0x1800a3b65  call    ?DriverSupportsDoublePrecisionFloatShaderOps@CDevice@@QEBA_NXZ; CDevice::DriverSupportsDoublePrecisionFloatShaderOps(void)
0x1800a3b6a  movzx   ecx, al
0x1800a3b6d  mov     eax, r8d
0x1800a3b70  shr     eax, 1
0x1800a3b72  and     r8d, 1
0x1800a3b76  and     eax, 2
0x1800a3b79  shl     ecx, 2
0x1800a3b7c  or      edx, ecx
0x1800a3b7e  mov     [rbp+40h+var_B8], r12
0x1800a3b82  or      edx, eax
0x1800a3b84  mov     [rbp+40h+var_A8], r12
0x1800a3b88  lea     rax, [rsp+140h+var_120]
0x1800a3b8d  mov     [rbp+40h+var_98], 8
0x1800a3b95  mov     [rbp+40h+var_C0], rax
0x1800a3b99  or      edx, r8d
0x1800a3b9c  lea     rax, [rbp+40h+arg_30]
0x1800a3ba3  mov     [rsp+140h+var_120], edx
0x1800a3ba7  mov     [rbp+40h+var_B0], rax
0x1800a3bab  mov     rcx, rdi; this
0x1800a3bae  lea     rax, [rbp+40h+arg_38]
0x1800a3bb5  mov     [rbp+40h+var_88], 8
0x1800a3bbd  mov     [rbp+40h+var_A0], rax
0x1800a3bc1  lea     rax, [rbp+40h+arg_40]
0x1800a3bc8  mov     [rbp+40h+var_90], rax
0x1800a3bcc  lea     rax, [rbp+40h+arg_48]
0x1800a3bd3  mov     [rbp+40h+var_80], rax
0x1800a3bd7  mov     rax, [rdi+438h]
0x1800a3bde  add     rax, 9F40h
0x1800a3be4  mov     [rbp+40h+var_78], r12
0x1800a3be8  mov     [rsp+140h+var_118], rax
0x1800a3bed  lea     rax, [rsp+140h+var_118]
0x1800a3bf2  mov     [rbp+40h+var_70], rax
0x1800a3bf6  lea     rax, [rbp+40h+arg_50]
0x1800a3bfd  mov     [rbp+40h+var_60], rax
0x1800a3c01  mov     [rbp+40h+var_68], 8
0x1800a3c09  mov     [rbp+40h+var_58], 8
0x1800a3c11  call    ?DDIFlags@CDevice@@QEBAIXZ; CDevice::DDIFlags(void)
0x1800a3c16  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x1800a3c1d  lea     r9, [rsp+140h+var_110]
0x1800a3c22  and     eax, 0FFFFFF31h
0x1800a3c27  mov     [rbp+40h+var_48], r12
0x1800a3c2b  mov     [rsp+140h+var_11C], eax
0x1800a3c2f  lea     r8d, [r12+9]
0x1800a3c34  lea     rax, [rsp+140h+var_11C]
0x1800a3c39  mov     rdx, r15
0x1800a3c3c  mov     [rbp+40h+var_50], rax
0x1800a3c40  call    cs:__imp_EtwEventWrite
0x1800a3c46  test    rbx, 40002h
0x1800a3c4d  jz      short loc_1800A3C61
0x1800a3c4f  mov     rcx, [rdi+438h]; this
0x1800a3c56  mov     r8, r14; struct _EVENT_DESCRIPTOR *
0x1800a3c59  mov     rdx, rbx; unsigned __int64
0x1800a3c5c  call    ?ETWWrite@CContext@@QEAAX_KPEBU_EVENT_DESCRIPTOR@@@Z; CContext::ETWWrite(unsigned __int64,_EVENT_DESCRIPTOR const *)
0x1800a3c61  mov     rcx, [rbp+40h+var_40]
0x1800a3c65  xor     rcx, rsp; StackCookie
0x1800a3c68  call    __security_check_cookie
0x1800a3c6d  add     rsp, 110h
0x1800a3c74  pop     r15
0x1800a3c76  pop     r14
0x1800a3c78  pop     r12
0x1800a3c7a  pop     rdi
0x1800a3c7b  pop     rsi
0x1800a3c7c  pop     rbx
0x1800a3c7d  pop     rbp
0x1800a3c7e  retn
```
