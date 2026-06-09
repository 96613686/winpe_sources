# MotionTurboJpeg::CMJPGMFTTypeHandler::UpdateAvaliableTypesForNewFormat(uint,uint)

- ea: `0x180042f08`
- end: `0x18004308b`
- name: `?UpdateAvaliableTypesForNewFormat@CMJPGMFTTypeHandler@MotionTurboJpeg@@QEAAJII@Z`
- size: `387`
- prototype: `__int64 __fastcall(MotionTurboJpeg::CMJPGMFTTypeHandler *this, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001ef40`

## callees

- `0x180014b14`
- `0x18001b320`
- `0x180042f08`
- `0x180044454`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall MotionTurboJpeg::CMJPGMFTTypeHandler::UpdateAvaliableTypesForNewFormat(
        MotionTurboJpeg::CMJPGMFTTypeHandler *this,
        __int64 a2,
        unsigned int a3)
{
  __int64 v3; // r12
  __int64 v5; // r13
  __int64 *v6; // rcx
  __int64 result; // rax
  unsigned int v8; // r8d
  unsigned int v9; // edi
  double v10; // xmm3_8
  double v11; // xmm2_8
  int v12; // r8d
  int v13; // r9d
  unsigned int v14; // r14d
  unsigned int v15; // ecx
  unsigned __int64 v16; // rsi
  __int64 v17; // rcx
  __int64 v18; // rcx
  _DWORD v19[4]; // [rsp+40h] [rbp-10h] BYREF
  int v20; // [rsp+90h] [rbp+40h] BYREF
  int v21; // [rsp+A8h] [rbp+58h] BYREF

  v3 = a3;
  v5 = (unsigned int)a2;
  v6 = (__int64 *)*((_QWORD *)this + 6);
  v21 = 0;
  v20 = 0;
  result = MFGetAttribute2UINT32asUINT64(v6, a2, &v21, &v20);
  v9 = result;
  if ( (int)result >= 0 )
  {
    v10 = (double)v20 / (double)(int)v3 * 10000.0;
    v11 = (double)v21 / (double)(int)v5 * 10000.0;
    v13 = MotionTurboJpeg::gcd((MotionTurboJpeg *)(unsigned int)(int)v10, (int)v11, v8);
    v14 = 0;
    v15 = (int)(v10 / (double)v13);
    if ( *((_DWORD *)this + 8) )
    {
      v16 = v15 | ((unsigned __int64)(unsigned int)(int)(v11 / (double)v13) << 32);
      do
      {
        v17 = *(_QWORD *)(*((_QWORD *)this + 5) + 16LL * v14);
        v9 = (*(__int64 (__fastcall **)(__int64, const GUID *, unsigned __int64))(*(_QWORD *)v17 + 176LL))(
               v17,
               &MF_MT_PIXEL_ASPECT_RATIO,
               v16);
        if ( v9 )
          break;
        v18 = *(_QWORD *)(*((_QWORD *)this + 5) + 16LL * v14);
        v9 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v18 + 176LL))(
               v18,
               &MF_MT_FRAME_SIZE,
               v3 | (v5 << 32));
        if ( v9 )
          break;
        ++v14;
      }
      while ( v14 < *((_DWORD *)this + 8) );
    }
    *((_DWORD *)this + 28) = v5;
    *((_DWORD *)this + 29) = v3;
    if ( (unsigned int)dword_18009C028 > 5 )
    {
      v21 = *((_DWORD *)this + 29);
      v19[0] = *((_DWORD *)this + 28);
      v20 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v15,
        (unsigned int)word_180093EA2,
        v12,
        v13,
        (__int64)v19,
        (__int64)&v21,
        (__int64)&v20);
    }
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180042f08  mov     [rsp-38h+arg_8], rbx
0x180042f0d  push    rbp
0x180042f0e  push    rsi
0x180042f0f  push    rdi
0x180042f10  push    r12
0x180042f12  push    r13
0x180042f14  push    r14
0x180042f16  push    r15
0x180042f18  mov     rbp, rsp
0x180042f1b  sub     rsp, 50h
0x180042f1f  mov     r12d, r8d
0x180042f22  lea     r9, [rbp+arg_0]
0x180042f26  mov     rbx, rcx
0x180042f29  mov     r13d, edx
0x180042f2c  mov     rcx, [rcx+30h]
0x180042f30  lea     r8, [rbp+arg_18]
0x180042f34  xor     esi, esi
0x180042f36  mov     [rbp+arg_18], esi
0x180042f39  mov     [rbp+arg_0], esi
0x180042f3c  call    MFGetAttribute2UINT32asUINT64
0x180042f41  mov     edi, eax
0x180042f43  test    eax, eax
0x180042f45  js      loc_180043073
0x180042f4b  mov     eax, [rbp+arg_0]
0x180042f4e  xorps   xmm3, xmm3
0x180042f51  xorps   xmm0, xmm0
0x180042f54  xorps   xmm2, xmm2
0x180042f57  cvtsi2sd xmm0, r12
0x180042f5c  cvtsi2sd xmm3, rax
0x180042f61  mov     eax, [rbp+arg_18]
0x180042f64  cvtsi2sd xmm2, rax
0x180042f69  divsd   xmm3, xmm0
0x180042f6d  xorps   xmm0, xmm0
0x180042f70  mulsd   xmm3, cs:__real@40c3880000000000
0x180042f78  cvtsi2sd xmm0, r13
0x180042f7d  cvttsd2si ecx, xmm3; this
0x180042f81  divsd   xmm2, xmm0
0x180042f85  mulsd   xmm2, cs:__real@40c3880000000000
0x180042f8d  cvttsd2si edx, xmm2; unsigned int
0x180042f91  call    ?gcd@MotionTurboJpeg@@YAIII@Z; MotionTurboJpeg::gcd(uint,uint)
0x180042f96  xorps   xmm0, xmm0
0x180042f99  mov     r9d, eax
0x180042f9c  mov     r14d, esi
0x180042f9f  cvtsi2sd xmm0, r9
0x180042fa4  divsd   xmm2, xmm0
0x180042fa8  divsd   xmm3, xmm0
0x180042fac  cvttsd2si eax, xmm2
0x180042fb0  cvttsd2si ecx, xmm3
0x180042fb4  cmp     [rbx+20h], esi
0x180042fb7  jbe     short loc_180043028
0x180042fb9  mov     esi, eax
0x180042fbb  shl     rsi, 20h
0x180042fbf  mov     eax, ecx
0x180042fc1  or      rsi, rax
0x180042fc4  mov     rax, [rbx+28h]
0x180042fc8  lea     rdx, MF_MT_PIXEL_ASPECT_RATIO
0x180042fcf  mov     r15d, r14d
0x180042fd2  mov     r8, rsi
0x180042fd5  add     r15, r15
0x180042fd8  mov     rcx, [rax+r15*8]
0x180042fdc  mov     rax, [rcx]
0x180042fdf  mov     rax, [rax+0B0h]
0x180042fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042feb  mov     edi, eax
0x180042fed  test    eax, eax
0x180042fef  jnz     short loc_180043028
0x180042ff1  mov     rax, [rbx+28h]
0x180042ff5  lea     rdx, MF_MT_FRAME_SIZE
0x180042ffc  mov     r8, r13
0x180042fff  shl     r8, 20h
0x180043003  or      r8, r12
0x180043006  mov     rcx, [rax+r15*8]
0x18004300a  mov     r9, [rcx]
0x18004300d  mov     rax, [r9+0B0h]
0x180043014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043019  mov     edi, eax
0x18004301b  test    eax, eax
0x18004301d  jnz     short loc_180043028
0x18004301f  inc     r14d
0x180043022  cmp     r14d, [rbx+20h]
0x180043026  jb      short loc_180042FC4
0x180043028  mov     [rbx+70h], r13d
0x18004302c  mov     [rbx+74h], r12d
0x180043030  mov     eax, cs:dword_18009C028
0x180043036  cmp     eax, 5
0x180043039  jbe     short loc_180043071
0x18004303b  mov     eax, [rbx+74h]
0x18004303e  lea     rdx, word_180093EA2
0x180043045  mov     [rbp+arg_18], eax
0x180043048  mov     eax, [rbx+70h]
0x18004304b  mov     [rbp+var_10], eax
0x18004304e  lea     rax, [rbp+arg_0]
0x180043052  mov     [rsp+50h+var_20], rax
0x180043057  lea     rax, [rbp+arg_18]
0x18004305b  mov     [rsp+50h+var_28], rax
0x180043060  lea     rax, [rbp+var_10]
0x180043064  mov     [rsp+50h+var_30], rax
0x180043069  mov     [rbp+arg_0], edi
0x18004306c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180043071  mov     eax, edi
0x180043073  mov     rbx, [rsp+50h+arg_8]
0x18004307b  add     rsp, 50h
0x18004307f  pop     r15
0x180043081  pop     r14
0x180043083  pop     r13
0x180043085  pop     r12
0x180043087  pop     rdi
0x180043088  pop     rsi
0x180043089  pop     rbp
0x18004308a  retn
```
