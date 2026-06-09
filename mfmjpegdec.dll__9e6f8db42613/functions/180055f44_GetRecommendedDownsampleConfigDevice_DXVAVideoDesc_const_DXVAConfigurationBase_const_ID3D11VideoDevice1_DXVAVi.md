# GetRecommendedDownsampleConfigDevice(DXVAVideoDesc const &,DXVAConfigurationBase const &,ID3D11VideoDevice1 *,DXVAVideoDesc &)

- ea: `0x180055f44`
- end: `0x180056128`
- name: `?GetRecommendedDownsampleConfigDevice@@YAJAEBUDXVAVideoDesc@@AEBUDXVAConfigurationBase@@PEAUID3D11VideoDevice1@@AEAU1@@Z`
- size: `484`
- prototype: `__int64 __fastcall(const struct DXVAVideoDesc *, const struct DXVAConfigurationBase *, struct ID3D11VideoDevice1 *, struct DXVAVideoDesc *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050aa0`

## callees

- `0x180024220`
- `0x18004aae4`
- `0x180055f44`
- `0x1800562c8`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall GetRecommendedDownsampleConfigDevice(
        const struct DXVAVideoDesc *a1,
        const struct DXVAConfigurationBase *a2,
        struct ID3D11VideoDevice1 *a3,
        struct DXVAVideoDesc *a4)
{
  char *v4; // r15
  HRESULT (__stdcall *GetVideoDecoderCaps)(ID3D11VideoDevice1 *, const GUID *, UINT, UINT, const DXGI_RATIONAL *, UINT, const GUID *, UINT *); // rax
  __int64 v10; // r9
  __int64 v12; // r8
  unsigned int v13; // ebx
  int v14; // ecx
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // rcx
  struct ID3D11VideoDevice1Vtbl *lpVtbl; // rax
  unsigned int v19; // eax
  __int64 v20; // r8
  __int64 v21; // rdx
  int v22; // eax
  __int128 v23; // xmm1
  unsigned int v25; // [rsp+60h] [rbp-69h] BYREF
  __int128 v26; // [rsp+68h] [rbp-61h]
  __int128 v27; // [rsp+78h] [rbp-51h]
  __int128 v28; // [rsp+A0h] [rbp-29h] BYREF
  int v29; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v30; // [rsp+B4h] [rbp-15h]
  int v31; // [rsp+BCh] [rbp-Dh]
  int v32; // [rsp+C0h] [rbp-9h]
  int v33; // [rsp+C4h] [rbp-5h]
  int v34; // [rsp+C8h] [rbp-1h]

  v4 = (char *)a1 + 40;
  GetVideoDecoderCaps = a3->lpVtbl->GetVideoDecoderCaps;
  v10 = *((unsigned int *)a1 + 1);
  v12 = *(unsigned int *)a1;
  v13 = 1;
  v25 = 0;
  if ( ((int (__fastcall *)(struct ID3D11VideoDevice1 *, char *, __int64, __int64, char *, _DWORD, _QWORD, unsigned int *))GetVideoDecoderCaps)(
         a3,
         (char *)a1 + 12,
         v12,
         v10,
         v4,
         0,
         0,
         &v25) >= 0
    && (v25 & 1) != 0 )
  {
    v14 = *((_DWORD *)a1 + 3);
    v15 = *((unsigned int *)a1 + 7);
    v31 = *((_DWORD *)a1 + 6);
    v32 = *(_DWORD *)a1;
    v33 = *((_DWORD *)a1 + 1);
    v16 = *((_DWORD *)a1 + 2);
    v29 = v14;
    v17 = *((_QWORD *)a1 + 2);
    v34 = v16;
    lpVtbl = a3->lpVtbl;
    v30 = v17;
    v28 = 0;
    v19 = ((__int64 (__fastcall *)(struct ID3D11VideoDevice1 *, int *, __int64, char *, char *, __int128 *))lpVtbl->RecommendVideoDecoderDownsampleParameters)(
            a3,
            &v29,
            v15,
            (char *)a2 + 16,
            v4,
            &v28);
    v20 = DWORD2(v28);
    v21 = (unsigned int)v28;
    v13 = v19;
    v22 = DWORD1(v28);
    HIDWORD(v26) = 0;
    v27 = 0;
    LODWORD(v26) = v28;
    *(_QWORD *)((char *)&v26 + 4) = *(_QWORD *)((char *)&v28 + 4);
    HIDWORD(v27) = HIDWORD(v28);
    v23 = v27;
    *(_OWORD *)a4 = v26;
    *((_OWORD *)a4 + 1) = v23;
    *((_OWORD *)a4 + 2) = 0;
    *((_DWORD *)a4 + 12) = 0;
    if ( g_wppLevels >= 8u )
    {
      WPP_SF_Dddddddq(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v20, v13, v32, v33, v34, v21, v22, v20);
      LODWORD(v20) = DWORD2(v28);
      v22 = DWORD1(v28);
      LODWORD(v21) = v28;
    }
    if ( !v13 && (_DWORD)v21 && v22 && (v32 != (_DWORD)v21 || v33 != v22 || (_DWORD)v20 != v34) )
      return 0;
  }
  if ( g_wppLevels >= 8u )
    WPP_SF_ddq(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_82cc44148043321fca842372e90a2d52_Traceguids, v25, v13, 0);
  return v13;
}

```

## disassembly

```asm
0x180055f44  push    rbp
0x180055f46  push    rbx
0x180055f47  push    rsi
0x180055f48  push    rdi
0x180055f49  push    r12
0x180055f4b  push    r13
0x180055f4d  push    r14
0x180055f4f  push    r15
0x180055f51  lea     rbp, [rsp-1Fh]
0x180055f56  sub     rsp, 0E8h
0x180055f5d  mov     rax, cs:__security_cookie
0x180055f64  xor     rax, rsp
0x180055f67  mov     [rbp+57h+var_50], rax
0x180055f6b  mov     rax, [r8]
0x180055f6e  lea     r15, [rcx+28h]
0x180055f72  mov     rdi, rcx
0x180055f75  mov     r12, rdx
0x180055f78  xor     edx, edx
0x180055f7a  lea     rcx, [rbp+57h+var_C0]
0x180055f7e  mov     [rsp+120h+var_E8], rcx
0x180055f83  mov     rsi, r8
0x180055f86  mov     rax, [rax+0A8h]
0x180055f8d  mov     r13, r9
0x180055f90  mov     r9d, [rdi+4]
0x180055f94  mov     rcx, rsi
0x180055f97  mov     r8d, [rdi]
0x180055f9a  mov     ebx, 1
0x180055f9f  mov     [rsp+120h+var_F0], rdx
0x180055fa4  mov     dword ptr [rsp+120h+var_F8], edx
0x180055fa8  mov     [rbp+57h+var_C0], edx
0x180055fab  lea     rdx, [rdi+0Ch]
0x180055faf  mov     [rsp+120h+var_100], r15
0x180055fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fb9  test    eax, eax
0x180055fbb  js      loc_1800560D0
0x180055fc1  test    byte ptr [rbp+57h+var_C0], bl
0x180055fc4  jz      loc_1800560D0
0x180055fca  mov     eax, [rdi+18h]
0x180055fcd  lea     r9, [r12+10h]
0x180055fd2  mov     ecx, [rdi+0Ch]
0x180055fd5  lea     rdx, [rbp+57h+var_70]
0x180055fd9  mov     r8d, [rdi+1Ch]
0x180055fdd  xorps   xmm0, xmm0
0x180055fe0  mov     [rbp+57h+var_64], eax
0x180055fe3  mov     eax, [rdi]
0x180055fe5  mov     [rbp+57h+var_60], eax
0x180055fe8  mov     eax, [rdi+4]
0x180055feb  mov     [rbp+57h+var_5C], eax
0x180055fee  mov     eax, [rdi+8]
0x180055ff1  mov     [rbp+57h+var_70], ecx
0x180055ff4  mov     rcx, [rdi+10h]
0x180055ff8  mov     [rbp+57h+var_58], eax
0x180055ffb  mov     rax, [rsi]
0x180055ffe  mov     [rbp+57h+var_6C], rcx
0x180056002  lea     rcx, [rbp+57h+var_80]
0x180056006  mov     [rsp+120h+var_F8], rcx
0x18005600b  mov     rcx, rsi
0x18005600e  movups  [rbp+57h+var_80], xmm0
0x180056012  mov     rax, [rax+0B8h]
0x180056019  mov     [rsp+120h+var_100], r15
0x18005601e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056023  mov     r8d, dword ptr [rbp+57h+var_80+8]
0x180056027  xorps   xmm2, xmm2
0x18005602a  mov     edx, dword ptr [rbp+57h+var_80]
0x18005602d  mov     ebx, eax
0x18005602f  mov     eax, dword ptr [rbp+57h+var_80+4]
0x180056032  xor     r9d, r9d
0x180056035  mov     ecx, dword ptr [rbp+57h+var_80+0Ch]
0x180056038  movups  [rbp+57h+var_B8], xmm2
0x18005603c  mov     dword ptr [rbp+57h+var_B8+8], r8d
0x180056040  movups  [rbp+57h+var_A8], xmm2
0x180056044  mov     dword ptr [rbp+57h+var_B8], edx
0x180056047  mov     dword ptr [rbp+57h+var_B8+4], eax
0x18005604a  movups  xmm0, [rbp+57h+var_B8]
0x18005604e  mov     dword ptr [rbp+57h+var_A8+0Ch], ecx
0x180056051  movups  xmm1, [rbp+57h+var_A8]
0x180056055  movups  xmmword ptr [r13+0], xmm0
0x18005605a  movups  xmmword ptr [r13+10h], xmm1
0x18005605f  movups  xmmword ptr [r13+20h], xmm2
0x180056064  mov     [r13+30h], r9d
0x180056068  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x18005606f  jb      short loc_1800560B0
0x180056071  mov     rcx, cs:WPP_GLOBAL_Control
0x180056078  mov     r9d, ebx
0x18005607b  mov     [rsp+120h+var_D8], r8d
0x180056080  mov     [rsp+120h+var_E0], eax
0x180056084  mov     eax, [rbp+57h+var_58]
0x180056087  mov     rcx, [rcx+10h]
0x18005608b  mov     dword ptr [rsp+120h+var_E8], edx
0x18005608f  mov     dword ptr [rsp+120h+var_F0], eax
0x180056093  mov     eax, [rbp+57h+var_5C]
0x180056096  mov     dword ptr [rsp+120h+var_F8], eax
0x18005609a  mov     eax, [rbp+57h+var_60]
0x18005609d  mov     dword ptr [rsp+120h+var_100], eax
0x1800560a1  call    WPP_SF_Dddddddq
0x1800560a6  mov     r8d, dword ptr [rbp+57h+var_80+8]
0x1800560aa  mov     eax, dword ptr [rbp+57h+var_80+4]
0x1800560ad  mov     edx, dword ptr [rbp+57h+var_80]
0x1800560b0  test    ebx, ebx
0x1800560b2  jnz     short loc_1800560D0
0x1800560b4  test    edx, edx
0x1800560b6  jz      short loc_1800560D0
0x1800560b8  test    eax, eax
0x1800560ba  jz      short loc_1800560D0
0x1800560bc  cmp     [rbp+57h+var_60], edx
0x1800560bf  jnz     short loc_1800560CC
0x1800560c1  cmp     [rbp+57h+var_5C], eax
0x1800560c4  jnz     short loc_1800560CC
0x1800560c6  cmp     r8d, [rbp+57h+var_58]
0x1800560ca  jz      short loc_1800560D0
0x1800560cc  xor     eax, eax
0x1800560ce  jmp     short loc_180056108
0x1800560d0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1800560d7  jb      short loc_180056106
0x1800560d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800560e0  lea     r8, WPP_82cc44148043321fca842372e90a2d52_Traceguids
0x1800560e7  mov     r9d, [rbp+57h+var_C0]
0x1800560eb  mov     edx, 0Dh
0x1800560f0  mov     [rsp+120h+var_F8], 0
0x1800560f9  mov     dword ptr [rsp+120h+var_100], ebx
0x1800560fd  mov     rcx, [rcx+10h]
0x180056101  call    WPP_SF_ddq
0x180056106  mov     eax, ebx
0x180056108  mov     rcx, [rbp+57h+var_50]
0x18005610c  xor     rcx, rsp; StackCookie
0x18005610f  call    __security_check_cookie
0x180056114  add     rsp, 0E8h
0x18005611b  pop     r15
0x18005611d  pop     r14
0x18005611f  pop     r13
0x180056121  pop     r12
0x180056123  pop     rdi
0x180056124  pop     rsi
0x180056125  pop     rbx
0x180056126  pop     rbp
0x180056127  retn
```
