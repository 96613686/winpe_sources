# CContext::GetDecoderBuffer(ID3D11VideoDecoder *,D3D11_VIDEO_DECODER_BUFFER_TYPE,uint *,void * *)

- ea: `0x18002c1b0`
- end: `0x18002c3bc`
- name: `?GetDecoderBuffer@CContext@@UEAAJPEAUID3D11VideoDecoder@@W4D3D11_VIDEO_DECODER_BUFFER_TYPE@@PEAIPEAPEAX@Z`
- size: `524`
- prototype: `__int64 __fastcall(CContext *__hidden this, struct ID3D11VideoDecoder *, enum D3D11_VIDEO_DECODER_BUFFER_TYPE, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18001e2a0`
- `0x18002bd20`
- `0x18002c1b0`
- `0x18002c3c4`
- `0x1800a9d20`
- `0x1801cb010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18002c39d`
- `ntdll!EtwEventWrite` at `0x18002c39d`

## pseudocode

```c
__int64 __fastcall CContext::GetDecoderBuffer(
        CContext *this,
        struct ID3D11VideoDecoder *a2,
        unsigned int a3,
        unsigned int *a4,
        void **a5)
{
  char *v9; // rbx
  char *v10; // rcx
  char *v11; // rsi
  _QWORD *v12; // rsi
  unsigned int v13; // edi
  unsigned int v15; // [rsp+30h] [rbp-71h] BYREF
  _BYTE v16[4]; // [rsp+38h] [rbp-69h] BYREF
  int v17; // [rsp+3Ch] [rbp-65h]
  unsigned int *v18; // [rsp+40h] [rbp-61h]
  void **v19; // [rsp+48h] [rbp-59h]
  char *v20; // [rsp+50h] [rbp-51h] BYREF
  struct ID3D11VideoDecoder *v21; // [rsp+58h] [rbp-49h] BYREF
  _QWORD v22[6]; // [rsp+60h] [rbp-41h] BYREF
  unsigned int *v23; // [rsp+90h] [rbp-11h]
  __int64 v24; // [rsp+98h] [rbp-9h]
  void **v25; // [rsp+A0h] [rbp-1h]
  __int64 v26; // [rsp+A8h] [rbp+7h]
  char v27; // [rsp+B0h] [rbp+Fh] BYREF

  v15 = a3;
  v21 = a2;
  v9 = (char *)this - 232;
  v20 = (char *)this - 232;
  v16[0] = 0;
  if ( dword_1802282A4
    && (qword_180228290 & 0x4000000000000000LL) != 0
    && (qword_180228298 & 0x4000000000000000LL) == qword_180228298 )
  {
    v16[0] = 1;
    v18 = a4;
    v19 = a5;
    v22[0] = &v20;
    v22[1] = 8;
    v22[2] = &v21;
    v22[3] = 8;
    v22[4] = &v15;
    v22[5] = 4;
    v24 = 4;
    if ( a4 )
      v23 = a4;
    else
      v23 = (unsigned int *)&v27;
    v26 = 8;
    if ( a5 )
      v25 = a5;
    else
      v25 = (void **)&v27;
    EtwEventWrite(Direct3D11EtwProviderGuid_Context, &ID3D11VideoContext_GetDecoderBuffer_Start, 5, v22);
  }
  if ( !a2 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this - 9) + 1248LL) + 32LL))(
      *(_QWORD *)(*((_QWORD *)this - 9) + 1248LL),
      3145777,
      0);
    v17 = -2147024809;
    CETWEvent_ID3D11VideoContext_GetDecoderBuffer::~CETWEvent_ID3D11VideoContext_GetDecoderBuffer((CETWEvent_ID3D11VideoContext_GetDecoderBuffer *)v16);
    return 2147942487LL;
  }
  if ( !*((_BYTE *)this + 3470) )
    v9 = 0;
  if ( !v9 )
  {
    v11 = 0;
LABEL_17:
    v12 = v11 + 8;
    goto LABEL_13;
  }
  v10 = 0;
  if ( *(_BYTE *)(*((_QWORD *)v9 + 20) + 256LL) )
    v10 = v9;
  v9 = v10 + 152;
  if ( !v10 )
    v9 = 0;
  v11 = v9;
  if ( !v9 )
    goto LABEL_17;
  v12 = v9 + 8;
  CLockOwnerChild<CDevice,0>::UCAddUse(*((_QWORD *)v9 + 1) + 248LL);
LABEL_13:
  v13 = ((__int64 (__fastcall *)(struct ID3D11VideoDecoder *, _QWORD, unsigned int *, void **))a2->lpVtbl[1].QueryInterface)(
          a2,
          a3,
          a4,
          a5);
  v17 = v13;
  if ( v9 )
    CLockOwnerChild<CDevice,0>::UCReleaseUse(*v12 + 248LL);
  CETWEvent_ID3D11VideoContext_GetDecoderBuffer::~CETWEvent_ID3D11VideoContext_GetDecoderBuffer((CETWEvent_ID3D11VideoContext_GetDecoderBuffer *)v16);
  return v13;
}

```

## disassembly

```asm
0x18002c1b0  push    rbp
0x18002c1b2  push    rbx
0x18002c1b3  push    rsi
0x18002c1b4  push    rdi
0x18002c1b5  push    r12
0x18002c1b7  push    r14
0x18002c1b9  push    r15
0x18002c1bb  lea     rbp, [rsp-1Fh]
0x18002c1c0  sub     rsp, 0C0h
0x18002c1c7  mov     rax, cs:__security_cookie
0x18002c1ce  xor     rax, rsp
0x18002c1d1  mov     [rbp+4Fh+var_38], rax
0x18002c1d5  mov     r12, r9
0x18002c1d8  mov     r14d, r8d
0x18002c1db  mov     rdi, rdx
0x18002c1de  mov     rsi, rcx
0x18002c1e1  mov     r15, [rbp+4Fh+arg_20]
0x18002c1e5  mov     [rbp+4Fh+var_C0], r8d
0x18002c1e9  mov     [rbp+4Fh+var_98], rdx
0x18002c1ed  lea     rbx, [rcx-0E8h]
0x18002c1f4  mov     [rbp+4Fh+var_A0], rbx
0x18002c1f8  mov     [rbp+4Fh+var_B8], 0
0x18002c1fc  cmp     cs:dword_1802282A4, 0
0x18002c203  jz      short loc_18002C21C
0x18002c205  mov     rdx, 4000000000000000h
0x18002c20f  test    cs:qword_180228290, rdx
0x18002c216  jnz     loc_18002C310
0x18002c21c  test    rdi, rdi
0x18002c21f  jz      loc_18002C2DA
0x18002c225  xor     eax, eax
0x18002c227  cmp     [rsi+0D8Eh], al
0x18002c22d  cmovz   rbx, rax
0x18002c231  test    rbx, rbx
0x18002c234  jz      loc_18002C2D2
0x18002c23a  mov     rax, [rbx+0A0h]
0x18002c241  xor     ecx, ecx
0x18002c243  cmp     [rax+100h], cl
0x18002c249  cmovnz  rcx, rbx
0x18002c24d  lea     rbx, [rcx+98h]
0x18002c254  xor     eax, eax
0x18002c256  test    rcx, rcx
0x18002c259  cmovz   rbx, rax
0x18002c25d  mov     rsi, rbx
0x18002c260  test    rbx, rbx
0x18002c263  jz      short loc_18002C2D4
0x18002c265  lea     rsi, [rbx+8]
0x18002c269  mov     rcx, [rsi]
0x18002c26c  add     rcx, 0F8h
0x18002c273  call    ?UCAddUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCAddUse(void)
0x18002c278  mov     rax, [rdi]
0x18002c27b  mov     r9, r15
0x18002c27e  mov     r8, r12
0x18002c281  mov     edx, r14d
0x18002c284  mov     rcx, rdi
0x18002c287  mov     rax, [rax+48h]
0x18002c28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c290  mov     edi, eax
0x18002c292  mov     [rbp+4Fh+var_B4], eax
0x18002c295  test    rbx, rbx
0x18002c298  jz      short loc_18002C2A9
0x18002c29a  mov     rcx, [rsi]
0x18002c29d  add     rcx, 0F8h
0x18002c2a4  call    ?UCReleaseUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCReleaseUse(void)
0x18002c2a9  lea     rcx, [rbp+4Fh+var_B8]; this
0x18002c2ad  call    ??1CETWEvent_ID3D11VideoContext_GetDecoderBuffer@@QEAA@XZ; CETWEvent_ID3D11VideoContext_GetDecoderBuffer::~CETWEvent_ID3D11VideoContext_GetDecoderBuffer(void)
0x18002c2b2  mov     eax, edi
0x18002c2b4  mov     rcx, [rbp+4Fh+var_38]
0x18002c2b8  xor     rcx, rsp; StackCookie
0x18002c2bb  call    __security_check_cookie
0x18002c2c0  add     rsp, 0C0h
0x18002c2c7  pop     r15
0x18002c2c9  pop     r14
0x18002c2cb  pop     r12
0x18002c2cd  pop     rdi
0x18002c2ce  pop     rsi
0x18002c2cf  pop     rbx
0x18002c2d0  pop     rbp
0x18002c2d1  retn
0x18002c2d2  xor     esi, esi
0x18002c2d4  add     rsi, 8
0x18002c2d8  jmp     short loc_18002C278
0x18002c2da  mov     rax, [rsi-48h]
0x18002c2de  mov     rcx, [rax+4E0h]
0x18002c2e5  mov     rax, [rcx]
0x18002c2e8  xor     r8d, r8d
0x18002c2eb  mov     edx, 300031h
0x18002c2f0  mov     rax, [rax+20h]
0x18002c2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2f9  mov     [rbp+4Fh+var_B4], 80070057h
0x18002c300  lea     rcx, [rbp+4Fh+var_B8]; this
0x18002c304  call    ??1CETWEvent_ID3D11VideoContext_GetDecoderBuffer@@QEAA@XZ; CETWEvent_ID3D11VideoContext_GetDecoderBuffer::~CETWEvent_ID3D11VideoContext_GetDecoderBuffer(void)
0x18002c309  mov     eax, 80070057h
0x18002c30e  jmp     short loc_18002C2B4
0x18002c310  mov     rax, cs:qword_180228298
0x18002c317  and     rax, rdx
0x18002c31a  cmp     rax, cs:qword_180228298
0x18002c321  jnz     loc_18002C21C
0x18002c327  mov     [rbp+4Fh+var_B8], 1
0x18002c32b  mov     [rbp+4Fh+var_B0], r12
0x18002c32f  mov     [rbp+4Fh+var_A8], r15
0x18002c333  lea     rax, [rbp+4Fh+var_A0]
0x18002c337  mov     [rbp+4Fh+var_90], rax
0x18002c33b  mov     [rbp+4Fh+var_88], 8
0x18002c343  lea     rax, [rbp+4Fh+var_98]
0x18002c347  mov     [rbp+4Fh+var_80], rax
0x18002c34b  mov     [rbp+4Fh+var_78], 8
0x18002c353  lea     rax, [rbp+4Fh+var_C0]
0x18002c357  mov     [rbp+4Fh+var_70], rax
0x18002c35b  mov     [rbp+4Fh+var_68], 4
0x18002c363  mov     [rbp+4Fh+var_58], 4
0x18002c36b  test    r12, r12
0x18002c36e  jz      short loc_18002C3A8
0x18002c370  mov     [rbp+4Fh+var_60], r12
0x18002c374  mov     [rbp+4Fh+var_48], 8
0x18002c37c  test    r15, r15
0x18002c37f  jz      short loc_18002C3B2
0x18002c381  mov     [rbp+4Fh+var_50], r15
0x18002c385  lea     r9, [rbp+4Fh+var_90]
0x18002c389  mov     r8d, 5
0x18002c38f  lea     rdx, ID3D11VideoContext_GetDecoderBuffer_Start
0x18002c396  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x18002c39d  call    cs:__imp_EtwEventWrite
0x18002c3a3  jmp     loc_18002C21C
0x18002c3a8  lea     rax, [rbp+4Fh+var_40]
0x18002c3ac  mov     [rbp+4Fh+var_60], rax
0x18002c3b0  jmp     short loc_18002C374
0x18002c3b2  lea     rax, [rbp+4Fh+var_40]
0x18002c3b6  mov     [rbp+4Fh+var_50], rax
0x18002c3ba  jmp     short loc_18002C385
```
