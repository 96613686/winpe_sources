# CDX11DecodeCore::CreateNewDecodeDevice(DXVAVideoDesc const &,D3D11_VIDEO_DECODER_CONFIG const &)

- ea: `0x180050700`
- end: `0x180050a8e`
- name: `?CreateNewDecodeDevice@CDX11DecodeCore@@MEAAJAEBUDXVAVideoDesc@@AEBUD3D11_VIDEO_DECODER_CONFIG@@@Z`
- size: `910`
- prototype: `__int64 __fastcall(CDX11DecodeCore *__hidden this, const struct DXVAVideoDesc *, const struct D3D11_VIDEO_DECODER_CONFIG *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180024220`
- `0x18004a11c`
- `0x18004d92c`
- `0x18004e2f8`
- `0x180050700`
- `0x1800525bc`
- `0x1800527ac`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDX11DecodeCore::CreateNewDecodeDevice(
        CDX11DecodeCore *this,
        const struct DXVAVideoDesc *a2,
        const struct D3D11_VIDEO_DECODER_CONFIG *a3)
{
  const struct D3D11_VIDEO_DECODER_CONFIG *v3; // r13
  const struct DXVAVideoDesc *v4; // r14
  CDX11DecodeCore *v5; // rsi
  const struct _GUID *v6; // rbx
  unsigned __int8 v7; // r9
  unsigned __int64 v8; // xmm0_8
  unsigned int v9; // ebx
  bool IsDXVAProfileInBlockList; // al
  unsigned __int8 v11; // r9
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __m128i *, const struct D3D11_VIDEO_DECODER_CONFIG *, char *); // rbx
  __int64 v17; // [rsp+D0h] [rbp-80h] BYREF
  __int32 v18; // [rsp+D8h] [rbp-78h]
  CDX11DecodeCore *v19; // [rsp+E0h] [rbp-70h]
  __m128i v20[2]; // [rsp+E8h] [rbp-68h] BYREF
  const struct D3D11_VIDEO_DECODER_CONFIG *v21; // [rsp+108h] [rbp-48h]
  const struct DXVAVideoDesc *v22; // [rsp+110h] [rbp-40h]
  const struct _GUID *v23; // [rsp+118h] [rbp-38h]
  __m128i v24[2]; // [rsp+120h] [rbp-30h] BYREF

  v3 = a3;
  v21 = a3;
  v4 = a2;
  v22 = a2;
  v5 = this;
  v19 = this;
  v17 = 0;
  memset((char *)v20[0].m128i_i64 + 4, 0, 24);
  v20[1].m128i_i32[2] = *((_DWORD *)a2 + 2);
  v6 = (const struct _GUID *)((char *)a2 + 12);
  v23 = (const struct _GUID *)((char *)a2 + 12);
  v18 = *((_DWORD *)a2 + 3);
  v20[0].m128i_i32[0] = v18;
  *(__int64 *)((char *)v20[0].m128i_i64 + 4) = *((_QWORD *)a2 + 2);
  v20[0].m128i_i32[3] = *((_DWORD *)a2 + 6);
  v20[1].m128i_i64[0] = *(_QWORD *)a2;
  v24[0] = v20[0];
  *(__m128i *)((char *)v24 + 12) = *(__m128i *)((char *)v20 + 12);
  v7 = g_wppLevels;
  if ( g_wppLevels >= 4u )
  {
    v8 = _mm_srli_si128(v20[0], 8).m128i_u64[0];
    v3 = v21;
    WPP_SF_LDDDDDDDDDDLDDDDDDDDDDq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      HIWORD(v20[0].m128i_i64[0]),
      (unsigned __int8)v8,
      v18,
      v20[0].m128i_i8[4],
      v20[0].m128i_i8[6],
      v8,
      SBYTE1(v8),
      SBYTE2(v8),
      SBYTE3(v8),
      SBYTE4(v8),
      SBYTE5(v8),
      SBYTE6(v8),
      SHIBYTE(v8),
      v21->guidConfigBitstreamEncryption.Data1,
      v21->guidConfigBitstreamEncryption.Data2,
      v21->guidConfigBitstreamEncryption.Data3,
      v21->guidConfigBitstreamEncryption.Data4[0],
      v21->guidConfigBitstreamEncryption.Data4[1],
      v21->guidConfigBitstreamEncryption.Data4[2],
      v21->guidConfigBitstreamEncryption.Data4[3],
      v21->guidConfigBitstreamEncryption.Data4[4],
      a3->guidConfigBitstreamEncryption.Data4[5],
      a3->guidConfigBitstreamEncryption.Data4[6],
      a3->guidConfigBitstreamEncryption.Data4[7],
      (char)v19);
    v7 = g_wppLevels;
    v5 = v19;
    v4 = v22;
    v6 = v23;
  }
  if ( !*((_QWORD *)v5 + 6) )
  {
    v9 = -2147467259;
LABEL_15:
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v17);
    return v9;
  }
  if ( v7 >= 8u )
    WPP_SF_qdq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      *((_QWORD *)v5 + 7),
      *((unsigned __int16 *)v5 + 81) >> 15,
      v5);
  IsDXVAProfileInBlockList = _TestMockIsDXVAProfileInBlockList(v6);
  if ( !IsDXVAProfileInBlockList && *(_DWORD *)v4 <= 0x7FFFFFFFu && *((_DWORD *)v4 + 1) <= 0x7FFFFFFFu )
  {
    v9 = 0;
    if ( *((_BYTE *)v5 + 432) || *((_QWORD *)v5 + 7) && *((__int16 *)v5 + 81) < 0 )
      goto LABEL_16;
    v12 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)v5 + 6);
    v13 = **v12;
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v17);
    v9 = v13(v12, &GUID_10ec4d5b_975a_4689_b9e4_d0aac30fe333, &v17);
    if ( !v9 )
    {
      v14 = v17;
      v15 = *(__int64 (__fastcall **)(__int64, __m128i *, const struct D3D11_VIDEO_DECODER_CONFIG *, char *))(*(_QWORD *)v17 + 24LL);
      Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)v5 + 7);
      v9 = v15(v14, v24, v3, (char *)v5 + 56);
      if ( !v9 )
      {
LABEL_16:
        *(_OWORD *)((char *)v5 + 164) = *(_OWORD *)v4;
        *(_OWORD *)((char *)v5 + 180) = *((_OWORD *)v4 + 1);
        *(_OWORD *)((char *)v5 + 196) = *((_OWORD *)v4 + 2);
        *((_DWORD *)v5 + 53) = *((_DWORD *)v4 + 12);
      }
    }
    goto LABEL_15;
  }
  if ( v11 >= 8u )
    WPP_SF_dddddq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      &WPP_aec28197ab9b3fb808bb48be54c28540_Traceguids,
      *(unsigned int *)v4,
      *((_DWORD *)v4 + 1),
      0x7FFFFFFF,
      0x7FFFFFFF,
      IsDXVAProfileInBlockList,
      v5);
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v17);
  return 2147483661LL;
}

```

## disassembly

```asm
0x180050700  mov     [rsp-38h+arg_18], rbx
0x180050705  push    rbp
0x180050706  push    rsi
0x180050707  push    rdi
0x180050708  push    r12
0x18005070a  push    r13
0x18005070c  push    r14
0x18005070e  push    r15
0x180050710  mov     rbp, rsp
0x180050713  sub     rsp, 150h
0x18005071a  mov     rax, cs:__security_cookie
0x180050721  xor     rax, rsp
0x180050724  mov     [rbp+var_10], rax
0x180050728  mov     r13, r8
0x18005072b  mov     [rbp+var_48], r8
0x18005072f  mov     r14, rdx
0x180050732  mov     [rbp+var_40], rdx
0x180050736  mov     rsi, rcx
0x180050739  mov     [rbp+var_70], rcx
0x18005073d  xor     r12d, r12d
0x180050740  mov     [rbp+var_80], r12
0x180050744  xorps   xmm0, xmm0
0x180050747  xor     eax, eax
0x180050749  movups  [rbp+var_68+4], xmm0
0x18005074d  mov     [rbp+var_54], rax
0x180050751  mov     eax, [rdx+8]
0x180050754  mov     dword ptr [rbp+var_54+4], eax
0x180050757  lea     rbx, [rdx+0Ch]
0x18005075b  mov     [rbp+var_38], rbx
0x18005075f  mov     eax, [rbx]
0x180050761  mov     [rbp+var_78], eax
0x180050764  mov     dword ptr [rbp+var_68], eax
0x180050767  mov     rax, [rbx+4]
0x18005076b  mov     qword ptr [rbp+var_68+4], rax
0x18005076f  mov     eax, [rbx+0Ch]
0x180050772  mov     dword ptr [rbp+var_68+0Ch], eax
0x180050775  mov     eax, [rdx]
0x180050777  mov     [rbp-58h], eax
0x18005077a  mov     eax, [rdx+4]
0x18005077d  mov     dword ptr [rbp+var_54], eax
0x180050780  movups  xmm1, [rbp+var_68]
0x180050784  movups  [rbp+var_30], xmm1
0x180050788  movups  xmm0, [rbp+var_68+0Ch]
0x18005078c  movups  [rbp+var_30+0Ch], xmm0
0x180050790  mov     r9b, cs:?g_wppLevels@@3UMFWppLevels@@A; MFWppLevels g_wppLevels
0x180050797  cmp     r9b, 4
0x18005079b  jb      loc_1800508F3
0x1800507a1  movzx   r9d, byte ptr [r8+0Fh]
0x1800507a6  movzx   r12d, byte ptr [r8+0Eh]
0x1800507ab  movzx   r13d, byte ptr [r8+0Dh]
0x1800507b0  movdqa  xmm0, xmm1
0x1800507b4  psrldq  xmm0, 8
0x1800507b9  movq    rcx, xmm0
0x1800507be  mov     r15, rcx
0x1800507c1  shr     r15, 38h
0x1800507c5  mov     rax, rcx
0x1800507c8  shr     rax, 30h
0x1800507cc  movzx   r14d, al
0x1800507d0  mov     rax, rcx
0x1800507d3  shr     rax, 28h
0x1800507d7  movzx   esi, al
0x1800507da  mov     rax, rcx
0x1800507dd  shr     rax, 20h
0x1800507e1  movzx   edi, al
0x1800507e4  mov     rax, rcx
0x1800507e7  shr     rax, 18h
0x1800507eb  movzx   ebx, al
0x1800507ee  mov     rax, rcx
0x1800507f1  shr     rax, 10h
0x1800507f5  movzx   r11d, al
0x1800507f9  mov     rax, rcx
0x1800507fc  shr     rax, 8
0x180050800  movzx   r10d, al
0x180050804  movzx   r8d, cl
0x180050808  movq    rax, xmm1
0x18005080d  mov     rdx, rax
0x180050810  shr     rdx, 30h
0x180050814  shr     rax, 20h
0x180050818  movzx   ecx, ax
0x18005081b  mov     rax, [rbp+var_70]
0x18005081f  mov     [rsp+150h+var_88], rax
0x180050827  mov     [rsp+150h+var_90], r9d
0x18005082f  mov     [rsp+150h+var_98], r12d
0x180050837  mov     [rsp+150h+var_A0], r13d
0x18005083f  mov     r13, [rbp+var_48]
0x180050843  movzx   eax, byte ptr [r13+0Ch]
0x180050848  mov     [rsp+150h+var_A8], eax
0x18005084f  movzx   eax, byte ptr [r13+0Bh]
0x180050854  mov     [rsp+150h+var_B0], eax
0x18005085b  movzx   eax, byte ptr [r13+0Ah]
0x180050860  mov     [rsp+150h+var_B8], eax
0x180050867  movzx   eax, byte ptr [r13+9]
0x18005086c  mov     [rsp+150h+var_C0], eax
0x180050873  movzx   eax, byte ptr [r13+8]
0x180050878  mov     [rsp+150h+var_C8], eax
0x18005087f  movzx   eax, word ptr [r13+6]
0x180050884  mov     [rsp+150h+var_D0], eax
0x18005088b  movzx   eax, word ptr [r13+4]
0x180050890  mov     [rsp+150h+var_D8], eax
0x180050894  mov     eax, [r13+0]
0x180050898  mov     [rsp+150h+var_E0], eax
0x18005089c  mov     [rsp+150h+var_E8], r15d
0x1800508a1  mov     [rsp+150h+var_F0], r14d
0x1800508a6  mov     [rsp+150h+var_F8], esi
0x1800508aa  mov     [rsp+150h+var_100], edi
0x1800508ae  mov     [rsp+150h+var_108], ebx
0x1800508b2  mov     dword ptr [rsp+150h+var_110], r11d
0x1800508b7  mov     [rsp+150h+var_118], r10d
0x1800508bc  mov     [rsp+150h+var_120], r8d
0x1800508c1  mov     dword ptr [rsp+150h+var_128], edx
0x1800508c5  mov     [rsp+150h+var_130], ecx
0x1800508c9  mov     r9d, [rbp+var_78]
0x1800508cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800508d4  mov     rcx, [rcx+10h]
0x1800508d8  call    WPP_SF_LDDDDDDDDDDLDDDDDDDDDDq
0x1800508dd  mov     r9b, cs:?g_wppLevels@@3UMFWppLevels@@A; MFWppLevels g_wppLevels
0x1800508e4  mov     rsi, [rbp+var_70]
0x1800508e8  mov     r14, [rbp+var_40]
0x1800508ec  mov     rbx, [rbp+var_38]
0x1800508f0  xor     r12d, r12d
0x1800508f3  cmp     [rsi+30h], r12
0x1800508f7  jnz     short loc_180050903
0x1800508f9  mov     ebx, 80004005h
0x1800508fe  jmp     loc_1800509DB
0x180050903  cmp     r9b, 8
0x180050907  jb      short loc_180050937
0x180050909  movzx   eax, word ptr [rsi+0A2h]
0x180050910  shr     eax, 0Fh
0x180050913  mov     [rsp+150h+var_128], rsi
0x180050918  mov     [rsp+150h+var_130], eax
0x18005091c  mov     r9, [rsi+38h]
0x180050920  mov     rcx, cs:WPP_GLOBAL_Control
0x180050927  mov     rcx, [rcx+10h]
0x18005092b  call    WPP_SF_qdq
0x180050930  mov     r9b, cs:?g_wppLevels@@3UMFWppLevels@@A; MFWppLevels g_wppLevels
0x180050937  mov     rcx, rbx; struct _GUID *
0x18005093a  call    ?_TestMockIsDXVAProfileInBlockList@@YA_NAEBU_GUID@@@Z; _TestMockIsDXVAProfileInBlockList(_GUID const &)
0x18005093f  mov     ecx, 7FFFFFFFh
0x180050944  test    al, al
0x180050946  jnz     loc_180050A17
0x18005094c  cmp     [r14], ecx
0x18005094f  ja      loc_180050A17
0x180050955  cmp     [r14+4], ecx
0x180050959  ja      loc_180050A17
0x18005095f  mov     ebx, r12d
0x180050962  cmp     [rsi+1B0h], r12b
0x180050969  jnz     short loc_1800509E8
0x18005096b  lea     r15, [rsi+38h]
0x18005096f  cmp     [r15], r12
0x180050972  jz      short loc_18005097E
0x180050974  cmp     [rsi+0A2h], r12w
0x18005097c  jl      short loc_1800509E8
0x18005097e  mov     rdi, [rsi+30h]
0x180050982  mov     rax, [rdi]
0x180050985  mov     rbx, [rax]
0x180050988  lea     rcx, [rbp+var_80]
0x18005098c  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180050991  lea     r8, [rbp+var_80]
0x180050995  lea     rdx, _GUID_10ec4d5b_975a_4689_b9e4_d0aac30fe333
0x18005099c  mov     rcx, rdi
0x18005099f  mov     rax, rbx
0x1800509a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509a7  mov     ebx, eax
0x1800509a9  test    eax, eax
0x1800509ab  jnz     short loc_1800509DB
0x1800509ad  mov     rdi, [rbp+var_80]
0x1800509b1  mov     rax, [rdi]
0x1800509b4  mov     rbx, [rax+18h]
0x1800509b8  mov     rcx, r15
0x1800509bb  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x1800509c0  mov     r9, r15
0x1800509c3  mov     r8, r13
0x1800509c6  lea     rdx, [rbp+var_30]
0x1800509ca  mov     rcx, rdi
0x1800509cd  mov     rax, rbx
0x1800509d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509d5  mov     ebx, eax
0x1800509d7  test    eax, eax
0x1800509d9  jz      short loc_1800509E8
0x1800509db  lea     rcx, [rbp+var_80]
0x1800509df  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x1800509e4  mov     eax, ebx
0x1800509e6  jmp     short loc_180050A67
0x1800509e8  movups  xmm0, xmmword ptr [r14]
0x1800509ec  movups  xmmword ptr [rsi+0A4h], xmm0
0x1800509f3  movups  xmm1, xmmword ptr [r14+10h]
0x1800509f8  movups  xmmword ptr [rsi+0B4h], xmm1
0x1800509ff  movups  xmm0, xmmword ptr [r14+20h]
0x180050a04  movups  xmmword ptr [rsi+0C4h], xmm0
0x180050a0b  mov     eax, [r14+30h]
0x180050a0f  mov     [rsi+0D4h], eax
0x180050a15  jmp     short loc_1800509DB
0x180050a17  cmp     r9b, 8
0x180050a1b  jb      short loc_180050A59
0x180050a1d  movzx   eax, al
0x180050a20  mov     edx, 2Ah ; '*'
0x180050a25  mov     [rsp+150h+var_110], rsi
0x180050a2a  mov     [rsp+150h+var_118], eax
0x180050a2e  mov     [rsp+150h+var_120], ecx
0x180050a32  mov     dword ptr [rsp+150h+var_128], ecx
0x180050a36  mov     eax, [r14+4]
0x180050a3a  mov     [rsp+150h+var_130], eax
0x180050a3e  mov     r9d, [r14]
0x180050a41  lea     r8, WPP_aec28197ab9b3fb808bb48be54c28540_Traceguids
0x180050a48  mov     rcx, cs:WPP_GLOBAL_Control
0x180050a4f  mov     rcx, [rcx+10h]
0x180050a53  call    WPP_SF_dddddq
0x180050a58  nop
0x180050a59  lea     rcx, [rbp+var_80]
0x180050a5d  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180050a62  mov     eax, 8000000Dh
0x180050a67  mov     rcx, [rbp+var_10]
0x180050a6b  xor     rcx, rsp; StackCookie
0x180050a6e  call    __security_check_cookie
0x180050a73  mov     rbx, [rsp+150h+arg_18]
0x180050a7b  add     rsp, 150h
0x180050a82  pop     r15
0x180050a84  pop     r14
0x180050a86  pop     r13
0x180050a88  pop     r12
0x180050a8a  pop     rdi
0x180050a8b  pop     rsi
0x180050a8c  pop     rbp
0x180050a8d  retn
```
