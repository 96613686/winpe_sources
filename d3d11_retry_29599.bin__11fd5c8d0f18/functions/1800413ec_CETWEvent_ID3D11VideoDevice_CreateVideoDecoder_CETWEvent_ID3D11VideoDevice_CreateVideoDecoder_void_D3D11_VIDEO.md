# CETWEvent_ID3D11VideoDevice_CreateVideoDecoder::CETWEvent_ID3D11VideoDevice_CreateVideoDecoder(void *,D3D11_VIDEO_DECODER_DESC const *,D3D11_VIDEO_DECODER_CONFIG const *,ID3D11VideoDecoder * *)

- ea: `0x1800413ec`
- end: `0x1800414fe`
- name: `??0CETWEvent_ID3D11VideoDevice_CreateVideoDecoder@@QEAA@PEAXPEBUD3D11_VIDEO_DECODER_DESC@@PEBUD3D11_VIDEO_DECODER_CONFIG@@PEAPEAUID3D11VideoDecoder@@@Z`
- size: `274`
- prototype: `CETWEvent_ID3D11VideoDevice_CreateVideoDecoder *__fastcall(CETWEvent_ID3D11VideoDevice_CreateVideoDecoder *__hidden this, void *, const struct D3D11_VIDEO_DECODER_DESC *, const struct D3D11_VIDEO_DECODER_CONFIG *, struct ID3D11VideoDecoder **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180041290`

## callees

- `0x1800413ec`
- `0x1800a9d20`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800414d5`
- `ntdll!EtwEventWrite` at `0x1800414d5`

## pseudocode

```c
CETWEvent_ID3D11VideoDevice_CreateVideoDecoder *__fastcall CETWEvent_ID3D11VideoDevice_CreateVideoDecoder::CETWEvent_ID3D11VideoDevice_CreateVideoDecoder(
        CETWEvent_ID3D11VideoDevice_CreateVideoDecoder *this,
        void *a2,
        const struct D3D11_VIDEO_DECODER_DESC *a3,
        const struct D3D11_VIDEO_DECODER_CONFIG *a4,
        struct ID3D11VideoDecoder **a5)
{
  struct ID3D11VideoDecoder **v7; // rax
  _QWORD v8[2]; // [rsp+20h] [rbp-E0h] BYREF
  const struct D3D11_VIDEO_DECODER_DESC *v9; // [rsp+30h] [rbp-D0h]
  __int64 v10; // [rsp+38h] [rbp-C8h]
  const struct D3D11_VIDEO_DECODER_CONFIG *v11; // [rsp+40h] [rbp-C0h]
  __int64 v12; // [rsp+48h] [rbp-B8h]
  struct ID3D11VideoDecoder **v13; // [rsp+50h] [rbp-B0h]
  __int64 v14; // [rsp+58h] [rbp-A8h]
  char v15; // [rsp+60h] [rbp-A0h] BYREF
  char v16; // [rsp+68h] [rbp-98h] BYREF
  char v17; // [rsp+90h] [rbp-70h] BYREF
  void *v18; // [rsp+128h] [rbp+28h] BYREF

  v18 = a2;
  *(_BYTE *)this = 0;
  if ( dword_1802282A4
    && (qword_180228290 & 0x4000000000000000LL) != 0
    && (qword_180228298 & 0x4000000000000000LL) == qword_180228298 )
  {
    v7 = a5;
    *((_QWORD *)this + 1) = a5;
    *(_BYTE *)this = 1;
    v8[0] = &v18;
    v8[1] = 8;
    v10 = 28;
    if ( a3 )
      v9 = a3;
    else
      v9 = (const struct D3D11_VIDEO_DECODER_DESC *)&v16;
    v12 = 100;
    if ( a4 )
      v11 = a4;
    else
      v11 = (const struct D3D11_VIDEO_DECODER_CONFIG *)&v17;
    v14 = 8;
    if ( !v7 )
      v7 = (struct ID3D11VideoDecoder **)&v15;
    v13 = v7;
    EtwEventWrite(Direct3D11EtwProviderGuid_Context, &ID3D11VideoDevice_CreateVideoDecoder_Start, 4, v8);
  }
  return this;
}

```

## disassembly

```asm
0x1800413ec  mov     [rsp-8+arg_10], rbx
0x1800413f1  mov     [rsp-8+arg_8], rdx
0x1800413f6  push    rbp
0x1800413f7  lea     rbp, [rsp-10h]
0x1800413fc  sub     rsp, 110h
0x180041403  mov     rax, cs:__security_cookie
0x18004140a  xor     rax, rsp
0x18004140d  mov     [rbp+10h+var_10], rax
0x180041411  xor     edx, edx
0x180041413  mov     rbx, rcx
0x180041416  mov     [rcx], dl
0x180041418  cmp     cs:dword_1802282A4, edx
0x18004141e  jnz     short loc_180041440
0x180041420  mov     rax, rbx
0x180041423  mov     rcx, [rbp+10h+var_10]
0x180041427  xor     rcx, rsp; StackCookie
0x18004142a  call    __security_check_cookie
0x18004142f  mov     rbx, [rsp+110h+arg_10]
0x180041437  add     rsp, 110h
0x18004143e  pop     rbp
0x18004143f  retn
0x180041440  mov     r10, 4000000000000000h
0x18004144a  test    cs:qword_180228290, r10
0x180041451  jz      short loc_180041420
0x180041453  mov     rax, cs:qword_180228298
0x18004145a  and     rax, r10
0x18004145d  cmp     rax, cs:qword_180228298
0x180041464  jnz     short loc_180041420
0x180041466  mov     rax, [rbp+10h+arg_20]
0x18004146a  mov     [rcx+8], rax
0x18004146e  mov     byte ptr [rcx], 1
0x180041471  lea     rcx, [rbp+10h+arg_8]
0x180041475  mov     [rsp+110h+var_F0], rcx
0x18004147a  mov     [rsp+110h+var_E8], 8
0x180041483  mov     [rsp+110h+var_D8], 1Ch
0x18004148c  test    r8, r8
0x18004148f  jz      short loc_1800414E0
0x180041491  mov     [rsp+110h+var_E0], r8
0x180041496  mov     [rsp+110h+var_C8], 64h ; 'd'
0x18004149f  test    r9, r9
0x1800414a2  jz      short loc_1800414EC
0x1800414a4  mov     [rsp+110h+var_D0], r9
0x1800414a9  mov     [rsp+110h+var_B8], 8
0x1800414b2  test    rax, rax
0x1800414b5  jz      short loc_1800414F7
0x1800414b7  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x1800414be  lea     r9, [rsp+110h+var_F0]
0x1800414c3  mov     r8d, 4
0x1800414c9  mov     [rsp+110h+var_C0], rax
0x1800414ce  lea     rdx, ID3D11VideoDevice_CreateVideoDecoder_Start
0x1800414d5  call    cs:__imp_EtwEventWrite
0x1800414db  jmp     loc_180041420
0x1800414e0  lea     rcx, [rsp+110h+var_A8]
0x1800414e5  mov     [rsp+110h+var_E0], rcx
0x1800414ea  jmp     short loc_180041496
0x1800414ec  lea     rcx, [rbp+10h+var_80]
0x1800414f0  mov     [rsp+110h+var_D0], rcx
0x1800414f5  jmp     short loc_1800414A9
0x1800414f7  lea     rax, [rsp+110h+var_B0]
0x1800414fc  jmp     short loc_1800414B7
```
