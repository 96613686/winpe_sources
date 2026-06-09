# D3D12CreateLayeredDevice(uint,void const *,unsigned __int64,ID3D12LayeredDevice *,_GUID const &,void * *)

- ea: `0x180001a60`
- end: `0x180001c90`
- name: `?D3D12CreateLayeredDevice@@YAJIPEBX_KPEAUID3D12LayeredDevice@@AEBU_GUID@@PEAPEAX@Z`
- size: `560`
- prototype: `__int64 __fastcall(unsigned int, const void *, unsigned __int64, struct ID3D12LayeredDevice *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001a60`
- `0x180001c98`
- `0x180001d70`
- `0x180001da0`
- `0x180008b98`
- `0x18000aa60`
- `0x18000b410`
- `0x18000b81c`
- `0x18000be84`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall D3D12CreateLayeredDevice(
        int a1,
        _QWORD *a2,
        __int64 a3,
        struct ID3D12LayeredDevice *a4,
        const struct _GUID *a5,
        void **a6)
{
  __int64 LayeredDeviceSize; // rsi
  unsigned __int64 v11; // rcx
  NOutermost::CDevice *v12; // rcx
  __int64 result; // rax
  void *v14; // [rsp+30h] [rbp-E8h] BYREF
  _QWORD v15[2]; // [rsp+38h] [rbp-E0h] BYREF
  _com_error *v16; // [rsp+48h] [rbp-D0h] BYREF
  void **v17; // [rsp+50h] [rbp-C8h] BYREF
  int v18; // [rsp+58h] [rbp-C0h]
  __int128 v19; // [rsp+60h] [rbp-B8h]
  void **v20; // [rsp+70h] [rbp-A8h] BYREF
  int v21; // [rsp+78h] [rbp-A0h]
  __int128 v22; // [rsp+80h] [rbp-98h]
  void **pExceptionObject; // [rsp+90h] [rbp-88h] BYREF
  int v24; // [rsp+98h] [rbp-80h]
  __int128 v25; // [rsp+A0h] [rbp-78h]
  __int128 v26; // [rsp+B0h] [rbp-68h]
  __int128 v27; // [rsp+C0h] [rbp-58h]
  __int128 v28; // [rsp+D0h] [rbp-48h]

  try
  {
    if ( !a6 )
      ThrowFailure(-2147418113);
    if ( !a2 || a3 != 48 || !a2[2] || !a2[3] )
    {
      pExceptionObject = &_com_error::`vftable';
      v24 = -2147418113;
      v25 = 0;
      throw (_com_error *)&pExceptionObject;
    }
    if ( a1 )
    {
      v20 = &_com_error::`vftable';
      v21 = -2147418113;
      v22 = 0;
      throw (_com_error *)&v20;
    }
    if ( *a2 || a2[1] || a4 )
    {
      v17 = &_com_error::`vftable';
      v18 = -2147024809;
      v19 = 0;
      throw (_com_error *)&v17;
    }
    LayeredDeviceSize = D3D12CoreGetLayeredDeviceSize(a2);
    v11 = LayeredDeviceSize + 128;
    if ( (unsigned __int64)(LayeredDeviceSize + 128) < 0x80 )
      v11 = -1;
    v12 = (NOutermost::CDevice *)operator new[](v11);
    v15[1] = v12;
    v26 = *(_OWORD *)a2;
    v27 = *((_OWORD *)a2 + 1);
    v28 = *((_OWORD *)a2 + 2);
    *(_QWORD *)&v26 = (char *)v12 + 128;
    *((_QWORD *)&v26 + 1) = LayeredDeviceSize;
    v15[0] = 0;
    if ( !v12 )
    {
      v14 = operator new[](0x80u);
      std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>(v15, &v14);
      std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v14);
      v12 = (NOutermost::CDevice *)v15[0];
    }
    TComObject<NOutermost::CDevice>::TComObject<NOutermost::CDevice>(v12, a6);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( _com_error *v16 )
  {
    return *((unsigned int *)v16 + 2);
  }
  return result;
}

```

## disassembly

```asm
0x180001a60  mov     [rsp+arg_0], rbx
0x180001a65  push    rsi
0x180001a66  push    rdi
0x180001a67  push    r12
0x180001a69  push    r14
0x180001a6b  push    r15
0x180001a6d  sub     rsp, 0F0h
0x180001a74  mov     rax, cs:__security_cookie
0x180001a7b  xor     rax, rsp
0x180001a7e  mov     [rsp+118h+var_38], rax
0x180001a86  mov     r15, r9
0x180001a89  mov     rsi, r8
0x180001a8c  mov     rbx, rdx
0x180001a8f  mov     r14d, ecx
0x180001a92  mov     r12, [rsp+118h+arg_20]
0x180001a9a  mov     rdi, [rsp+118h+arg_28]
0x180001aa2  test    rdi, rdi
0x180001aa5  jz      loc_180001C3E
0x180001aab  test    rbx, rbx
0x180001aae  jnz     short loc_180001AEA
0x180001ab0  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180001ab7  mov     [rsp+118h+pExceptionObject], rax
0x180001abf  mov     [rsp+118h+var_80], 8000FFFFh
0x180001aca  xorps   xmm0, xmm0
0x180001acd  movdqu  [rsp+118h+var_78], xmm0
0x180001ad6  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180001add  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180001ae5  call    _CxxThrowException_0
0x180001aea  mov     edx, 30h ; '0'
0x180001aef  cmp     rsi, rdx
0x180001af2  jnz     short loc_180001AB0
0x180001af4  cmp     qword ptr [rbx+10h], 0
0x180001af9  jz      short loc_180001AB0
0x180001afb  cmp     qword ptr [rbx+18h], 0
0x180001b00  jz      short loc_180001AB0
0x180001b02  test    r14d, r14d
0x180001b05  jnz     loc_180001BDE
0x180001b0b  cmp     qword ptr [rbx], 0
0x180001b0f  jnz     loc_180001C10
0x180001b15  cmp     qword ptr [rbx+8], 0
0x180001b1a  jnz     loc_180001C10
0x180001b20  test    r15, r15
0x180001b23  jnz     loc_180001C10
0x180001b29  mov     rcx, rbx
0x180001b2c  call    D3D12CoreGetLayeredDeviceSize
0x180001b31  mov     rsi, rax
0x180001b34  lea     rcx, [rax+80h]
0x180001b3b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001b3f  mov     r14d, 80h
0x180001b45  cmp     rcx, r14
0x180001b48  cmovb   rcx, rax; unsigned __int64
0x180001b4c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180001b51  mov     rcx, rax; this
0x180001b54  mov     [rsp+118h+var_D8], rax
0x180001b59  movups  xmm0, xmmword ptr [rbx]
0x180001b5c  movups  [rsp+118h+var_68], xmm0
0x180001b64  movups  xmm1, xmmword ptr [rbx+10h]
0x180001b68  movups  [rsp+118h+var_58], xmm1
0x180001b70  movups  xmm0, xmmword ptr [rbx+20h]
0x180001b74  movups  [rsp+118h+var_48], xmm0
0x180001b7c  sub     rax, 0FFFFFFFFFFFFFF80h
0x180001b80  mov     qword ptr [rsp+118h+var_68], rax
0x180001b88  mov     qword ptr [rsp+118h+var_68+8], rsi
0x180001b90  mov     [rsp+118h+var_E0], r15
0x180001b95  test    rcx, rcx
0x180001b98  jz      loc_180001C4D
0x180001b9e  mov     [rsp+118h+var_F8], rdi; void **
0x180001ba3  mov     r9, r12
0x180001ba6  lea     r8, [rsp+118h+var_68]
0x180001bae  call    ??0?$TComObject@VCDevice@NOutermost@@@@QEAA@PEAXAEBUTConstructorArgs@CDevice@NOutermost@@AEBU_GUID@@PEAPEAX@Z; TComObject<NOutermost::CDevice>::TComObject<NOutermost::CDevice>(void *,NOutermost::CDevice::TConstructorArgs const &,_GUID const &,void * *)
0x180001bb3  nop
0x180001bb4  xor     eax, eax
0x180001bb6  mov     rcx, [rsp+118h+var_38]
0x180001bbe  xor     rcx, rsp; StackCookie
0x180001bc1  call    __security_check_cookie
0x180001bc6  mov     rbx, [rsp+118h+arg_0]
0x180001bce  add     rsp, 0F0h
0x180001bd5  pop     r15
0x180001bd7  pop     r14
0x180001bd9  pop     r12
0x180001bdb  pop     rdi
0x180001bdc  pop     rsi
0x180001bdd  retn
0x180001bde  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180001be5  mov     [rsp+118h+var_A8], rax
0x180001bea  mov     [rsp+118h+var_A0], 8000FFFFh
0x180001bf2  xorps   xmm0, xmm0
0x180001bf5  movdqu  [rsp+118h+var_98], xmm0
0x180001bfe  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180001c05  lea     rcx, [rsp+118h+var_A8]; pExceptionObject
0x180001c0a  call    _CxxThrowException_0
0x180001c10  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180001c17  mov     [rsp+118h+var_C8], rax
0x180001c1c  mov     [rsp+118h+var_C0], 80070057h
0x180001c24  xorps   xmm0, xmm0
0x180001c27  movdqu  [rsp+118h+var_B8], xmm0
0x180001c2d  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180001c34  lea     rcx, [rsp+118h+var_C8]; pExceptionObject
0x180001c39  call    _CxxThrowException_0
0x180001c3e  mov     ecx, 8000FFFFh; int
0x180001c43  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180001c48  jmp     loc_180001AAB
0x180001c4d  mov     rcx, r14; unsigned __int64
0x180001c50  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180001c55  mov     [rsp+118h+var_E8], rax
0x180001c5a  lea     rdx, [rsp+118h+var_E8]
0x180001c5f  lea     rcx, [rsp+118h+var_E0]
0x180001c64  call    ??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0]> &&)
0x180001c69  lea     rcx, [rsp+118h+var_E8]
0x180001c6e  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180001c73  mov     rcx, [rsp+118h+var_E0]
0x180001c78  jmp     loc_180001B9E
0x180001c7d  mov     eax, 8007000Eh
0x180001c82  jmp     loc_180001BB6
0x180001c87  mov     eax, dword ptr [rsp+118h+var_E8]
0x180001c8b  jmp     loc_180001BB6
```
