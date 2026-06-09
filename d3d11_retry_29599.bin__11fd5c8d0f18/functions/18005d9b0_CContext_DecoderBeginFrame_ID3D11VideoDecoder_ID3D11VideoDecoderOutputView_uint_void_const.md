# CContext::DecoderBeginFrame(ID3D11VideoDecoder *,ID3D11VideoDecoderOutputView *,uint,void const *)

- ea: `0x18005d9b0`
- end: `0x18005db6d`
- name: `?DecoderBeginFrame@CContext@@UEAAJPEAUID3D11VideoDecoder@@PEAUID3D11VideoDecoderOutputView@@IPEBX@Z`
- size: `445`
- prototype: `__int64 __fastcall(CContext *__hidden this, struct ID3D11VideoDecoder *, struct ID3D11VideoDecoderOutputView *, unsigned int, const void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x18002bd20`
- `0x18002cee0`
- `0x18002d174`
- `0x18005d9b0`
- `0x18005db74`
- `0x18005dbe0`
- `0x1800a9d20`
- `0x1801cb010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18005db62`
- `ntdll!EtwEventWrite` at `0x18005db62`

## pseudocode

```c
__int64 __fastcall CContext::DecoderBeginFrame(
        CContext *this,
        struct ID3D11VideoDecoder *a2,
        struct ID3D11VideoDecoderOutputView *a3,
        int a4,
        struct CDevice *a5)
{
  __int64 v9; // rdx
  unsigned int v10; // ebx
  char v12[4]; // [rsp+40h] [rbp-81h] BYREF
  int v13; // [rsp+44h] [rbp-7Dh]
  int v14; // [rsp+48h] [rbp-79h] BYREF
  struct CDevice *v15; // [rsp+50h] [rbp-71h] BYREF
  __int64 v16; // [rsp+58h] [rbp-69h]
  char *v17; // [rsp+60h] [rbp-61h] BYREF
  struct ID3D11VideoDecoder *v18; // [rsp+68h] [rbp-59h] BYREF
  struct ID3D11VideoDecoderOutputView *v19; // [rsp+70h] [rbp-51h] BYREF
  _QWORD v20[10]; // [rsp+80h] [rbp-41h] BYREF

  v15 = a5;
  v14 = a4;
  v19 = a3;
  v18 = a2;
  v17 = (char *)this - 232;
  v12[0] = 0;
  if ( dword_1802282A4
    && (qword_180228290 & 0x4000000000000000LL) != 0
    && (qword_180228298 & 0x4000000000000000LL) == qword_180228298 )
  {
    v12[0] = 1;
    v20[0] = &v17;
    v20[1] = 8;
    v20[2] = &v18;
    v20[3] = 8;
    v20[4] = &v19;
    v20[5] = 8;
    v20[6] = &v14;
    v20[7] = 4;
    v20[8] = &v15;
    v20[9] = 8;
    EtwEventWrite(Direct3D11EtwProviderGuid_Context, &ID3D11VideoContext_DecoderBeginFrame_Start, 5, v20);
  }
  v9 = *((_QWORD *)this - 9);
  if ( a2 )
  {
    CDDISync::CObjectAndSingleThreadedLowFreqLock::CObjectAndSingleThreadedLowFreqLock(
      (CDDISync::CObjectAndSingleThreadedLowFreqLock *)&v15,
      *(struct CContext **)(v9 + 1080));
    v10 = CDecodeContext::BeginFrame((CDecodeContext *)a2, (unsigned __int64)a3, a5, a4, 0, 0, 0);
    v13 = v10;
    if ( v16 )
    {
      CLockOwnerChild<CDevice,0>::UCReleaseUse(v16 + 248);
    }
    else if ( v15 )
    {
      CDDISync::CSingleThreadedLowFreqLock::Leave(v15);
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(v9 + 1248) + 32LL))(
      *(_QWORD *)(v9 + 1248),
      3145784,
      0);
    v10 = -2147024809;
    v13 = -2147024809;
  }
  CETWEvent_ID3D11VideoContext_DecoderBeginFrame::~CETWEvent_ID3D11VideoContext_DecoderBeginFrame((CETWEvent_ID3D11VideoContext_DecoderBeginFrame *)v12);
  return v10;
}

```

## disassembly

```asm
0x18005d9b0  push    rbp
0x18005d9b2  push    rbx
0x18005d9b3  push    rsi
0x18005d9b4  push    rdi
0x18005d9b5  push    r14
0x18005d9b7  push    r15
0x18005d9b9  lea     rbp, [rsp-27h]
0x18005d9be  sub     rsp, 0E8h
0x18005d9c5  mov     rax, cs:__security_cookie
0x18005d9cc  xor     rax, rsp
0x18005d9cf  mov     [rbp+4Fh+var_40], rax
0x18005d9d3  mov     r14d, r9d
0x18005d9d6  mov     rsi, r8
0x18005d9d9  mov     rbx, rdx
0x18005d9dc  mov     rdi, rcx
0x18005d9df  mov     r15, [rbp+4Fh+arg_20]
0x18005d9e3  mov     [rbp+4Fh+var_C0], r15
0x18005d9e7  mov     [rbp+4Fh+var_C8], r9d
0x18005d9eb  mov     [rbp+4Fh+var_A0], r8
0x18005d9ef  mov     [rbp+4Fh+var_A8], rdx
0x18005d9f3  lea     rax, [rcx-0E8h]
0x18005d9fa  mov     [rbp+4Fh+var_B0], rax
0x18005d9fe  mov     [rsp+110h+var_D0], 0
0x18005da03  cmp     cs:dword_1802282A4, 0
0x18005da0a  jz      short loc_18005DA23
0x18005da0c  mov     rdx, 4000000000000000h
0x18005da16  test    cs:qword_180228290, rdx
0x18005da1d  jnz     loc_18005DADE
0x18005da23  mov     rdx, [rdi-48h]
0x18005da27  test    rbx, rbx
0x18005da2a  jz      short loc_18005DAA9
0x18005da2c  mov     rdx, [rdx+438h]; struct CContext *
0x18005da33  lea     rcx, [rbp+4Fh+var_C0]; this
0x18005da37  call    ??0CObjectAndSingleThreadedLowFreqLock@CDDISync@@QEAA@PEAVCContext@@@Z; CDDISync::CObjectAndSingleThreadedLowFreqLock::CObjectAndSingleThreadedLowFreqLock(CContext *)
0x18005da3c  mov     [rsp+110h+var_E0], 0; struct ID3D11Buffer **
0x18005da45  mov     [rsp+110h+var_E8], 0; unsigned int *
0x18005da4e  mov     [rsp+110h+var_F0], 0; unsigned int
0x18005da56  mov     r9d, r14d; unsigned int
0x18005da59  mov     r8, r15; void *
0x18005da5c  mov     rdx, rsi; struct ID3D11VideoDecoderOutputView *
0x18005da5f  mov     rcx, rbx; this
0x18005da62  call    ?BeginFrame@CDecodeContext@@UEAAJPEAUID3D11VideoDecoderOutputView@@PEBXIIPEBIPEBQEAUID3D11Buffer@@@Z; CDecodeContext::BeginFrame(ID3D11VideoDecoderOutputView *,void const *,uint,uint,uint const *,ID3D11Buffer * const *)
0x18005da67  mov     ebx, eax
0x18005da69  mov     [rbp+4Fh+var_CC], eax
0x18005da6c  mov     rcx, [rbp+4Fh+var_B8]
0x18005da70  test    rcx, rcx
0x18005da73  jz      short loc_18005DACE
0x18005da75  add     rcx, 0F8h
0x18005da7c  call    ?UCReleaseUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCReleaseUse(void)
0x18005da81  lea     rcx, [rsp+110h+var_D0]; this
0x18005da86  call    ??1CETWEvent_ID3D11VideoContext_DecoderBeginFrame@@QEAA@XZ; CETWEvent_ID3D11VideoContext_DecoderBeginFrame::~CETWEvent_ID3D11VideoContext_DecoderBeginFrame(void)
0x18005da8b  mov     eax, ebx
0x18005da8d  mov     rcx, [rbp+4Fh+var_40]
0x18005da91  xor     rcx, rsp; StackCookie
0x18005da94  call    __security_check_cookie
0x18005da99  add     rsp, 0E8h
0x18005daa0  pop     r15
0x18005daa2  pop     r14
0x18005daa4  pop     rdi
0x18005daa5  pop     rsi
0x18005daa6  pop     rbx
0x18005daa7  pop     rbp
0x18005daa8  retn
0x18005daa9  mov     rcx, [rdx+4E0h]
0x18005dab0  mov     rax, [rcx]
0x18005dab3  xor     r8d, r8d
0x18005dab6  mov     edx, 300038h
0x18005dabb  mov     rax, [rax+20h]
0x18005dabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dac4  mov     ebx, 80070057h
0x18005dac9  mov     [rbp+4Fh+var_CC], ebx
0x18005dacc  jmp     short loc_18005DA81
0x18005dace  mov     rcx, [rbp+4Fh+var_C0]; struct CDevice *
0x18005dad2  test    rcx, rcx
0x18005dad5  jz      short loc_18005DA81
0x18005dad7  call    ?Leave@CSingleThreadedLowFreqLock@CDDISync@@SAXPEAVCDevice@@@Z; CDDISync::CSingleThreadedLowFreqLock::Leave(CDevice *)
0x18005dadc  jmp     short loc_18005DA81
0x18005dade  mov     rax, cs:qword_180228298
0x18005dae5  and     rax, rdx
0x18005dae8  cmp     rax, cs:qword_180228298
0x18005daef  jnz     loc_18005DA23
0x18005daf5  mov     [rsp+110h+var_D0], 1
0x18005dafa  lea     rax, [rbp+4Fh+var_B0]
0x18005dafe  mov     [rbp+4Fh+var_90], rax
0x18005db02  mov     [rbp+4Fh+var_88], 8
0x18005db0a  lea     rax, [rbp+4Fh+var_A8]
0x18005db0e  mov     [rbp+4Fh+var_80], rax
0x18005db12  mov     [rbp+4Fh+var_78], 8
0x18005db1a  lea     rax, [rbp+4Fh+var_A0]
0x18005db1e  mov     [rbp+4Fh+var_70], rax
0x18005db22  mov     [rbp+4Fh+var_68], 8
0x18005db2a  lea     rax, [rbp+4Fh+var_C8]
0x18005db2e  mov     [rbp+4Fh+var_60], rax
0x18005db32  mov     [rbp+4Fh+var_58], 4
0x18005db3a  lea     rax, [rbp+4Fh+var_C0]
0x18005db3e  mov     [rbp+4Fh+var_50], rax
0x18005db42  mov     [rbp+4Fh+var_48], 8
0x18005db4a  lea     r9, [rbp+4Fh+var_90]
0x18005db4e  mov     r8d, 5
0x18005db54  lea     rdx, ID3D11VideoContext_DecoderBeginFrame_Start
0x18005db5b  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x18005db62  call    cs:__imp_EtwEventWrite
0x18005db68  jmp     loc_18005DA23
```
