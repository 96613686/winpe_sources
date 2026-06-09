# GetClientMPPEKeys

- ea: `0x180009dc0`
- end: `0x18000a4b4`
- name: `GetClientMPPEKeys`
- size: `1780`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18000b9b4`

## callees

- `0x180003bd0`
- `0x180006a20`
- `0x180009dc0`
- `0x18000a900`
- `0x18000abc0`
- `0x18000b610`
- `0x180011414`
- `0x180013b20`
- `0x18001e468`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a234`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a2db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a234`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a2db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2ea`
- `bcrypt!BCryptDestroyHash` at `0x180009fa2`
- `bcrypt!BCryptDestroyHash` at `0x18000a092`
- `bcrypt!BCryptDestroyHash` at `0x18000a186`
- `bcrypt!BCryptDestroyHash` at `0x180009fa2`
- `bcrypt!BCryptDestroyHash` at `0x18000a092`
- `bcrypt!BCryptDestroyHash` at `0x18000a186`
- `bcrypt!BCryptHashData` at `0x180009f21`
- `bcrypt!BCryptHashData` at `0x180009f46`
- `bcrypt!BCryptHashData` at `0x180009f6b`
- `bcrypt!BCryptHashData` at `0x180009fec`
- `bcrypt!BCryptHashData` at `0x18000a011`
- `bcrypt!BCryptHashData` at `0x18000a036`
- `bcrypt!BCryptHashData` at `0x18000a05b`
- `bcrypt!BCryptHashData` at `0x18000a0e0`
- `bcrypt!BCryptHashData` at `0x18000a105`
- `bcrypt!BCryptHashData` at `0x18000a12a`
- `bcrypt!BCryptHashData` at `0x18000a14f`
- `bcrypt!BCryptHashData` at `0x180009f21`
- `bcrypt!BCryptHashData` at `0x180009f46`
- `bcrypt!BCryptHashData` at `0x180009f6b`
- `bcrypt!BCryptHashData` at `0x180009fec`
- `bcrypt!BCryptHashData` at `0x18000a011`
- `bcrypt!BCryptHashData` at `0x18000a036`
- `bcrypt!BCryptHashData` at `0x18000a05b`
- `bcrypt!BCryptHashData` at `0x18000a0e0`
- `bcrypt!BCryptHashData` at `0x18000a105`
- `bcrypt!BCryptHashData` at `0x18000a12a`
- `bcrypt!BCryptHashData` at `0x18000a14f`
- `bcrypt!BCryptFinishHash` at `0x180009f8d`
- `bcrypt!BCryptFinishHash` at `0x18000a07d`
- `bcrypt!BCryptFinishHash` at `0x18000a171`
- `bcrypt!BCryptFinishHash` at `0x180009f8d`
- `bcrypt!BCryptFinishHash` at `0x18000a07d`
- `bcrypt!BCryptFinishHash` at `0x18000a171`
- `bcrypt!BCryptCreateHash` at `0x180009eff`
- `bcrypt!BCryptCreateHash` at `0x180009fca`
- `bcrypt!BCryptCreateHash` at `0x18000a0be`
- `bcrypt!BCryptCreateHash` at `0x180009eff`
- `bcrypt!BCryptCreateHash` at `0x180009fca`
- `bcrypt!BCryptCreateHash` at `0x18000a0be`

## string_xrefs

- `0x18000a11a`: `On the client side, this is the receive key; on the server side, it is the send key.`

## pseudocode

```c
__int64 __fastcall GetClientMPPEKeys(__int64 a1, __int64 a2)
{
  _QWORD *v4; // r9
  __int64 v5; // rcx
  unsigned int v6; // r12d
  unsigned int i; // edx
  unsigned __int8 **Next; // rax
  unsigned __int8 *v9; // rbx
  __int128 v10; // xmm6
  _DWORD *v11; // rax
  _QWORD *v12; // r14
  void *v14; // rsi
  void *v15; // r15
  DWORD LastError; // edi
  _DWORD *v17; // rax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  __int128 v21; // xmm0
  int v22; // ebx
  __int128 v23; // xmm1
  __int64 v24; // rax
  _DWORD *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // r8
  __int128 v28; // xmm0
  __int64 v29; // rax
  __int128 v30; // xmm1
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  _DWORD *v33; // rcx
  unsigned int v34; // ebx
  __int64 v35; // r8
  void *v36; // rcx
  PUCHAR pbSecret; // [rsp+20h] [rbp-79h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-59h] BYREF
  __int64 v39; // [rsp+48h] [rbp-51h]
  _OWORD v40[2]; // [rsp+50h] [rbp-49h] BYREF
  UCHAR v41[24]; // [rsp+78h] [rbp-21h] BYREF
  UCHAR pbOutput[24]; // [rsp+90h] [rbp-9h] BYREF

  v39 = 0;
  memset(v40, 0, sizeof(v40));
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *(_QWORD *)(a2 + 288);
  v6 = 0;
  if ( v5 )
  {
    for ( i = 0; ; ++i )
    {
      Next = (unsigned __int8 **)(v5 + 16LL * i);
      if ( !*(_DWORD *)Next )
        break;
      if ( *(_DWORD *)Next == 26 )
        goto LABEL_9;
    }
  }
  Next = 0;
LABEL_9:
  phHash = Next;
  while ( Next )
  {
    if ( *((_DWORD *)Next + 1) >= 8u )
    {
      v9 = Next[1];
      if ( v9[3] + (*v9 << 24) + (v9[2] << 8) + (v9[1] << 16) == 311 && v9[4] == 12 )
      {
        phHash = 0;
        if ( v4 != &WPP_GLOBAL_Control )
          WPP_SF_(v4[2], 35, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids);
        if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &phHash, 0, 0, 0, 0, 0) < 0 )
          __fastfail(7u);
        if ( BCryptHashData(phHash, v9 + 14, 0x10u, 0) < 0 )
          __fastfail(7u);
        if ( BCryptHashData(phHash, (PUCHAR)(a2 + 304), 0x18u, 0) < 0 )
          __fastfail(7u);
        if ( BCryptHashData(phHash, KeyMagic1, 0x1Bu, 0) < 0 )
          __fastfail(7u);
        if ( BCryptFinishHash(phHash, pbOutput, 0x14u, 0) < 0 )
          __fastfail(7u);
        BCryptDestroyHash(phHash);
        phHash = 0;
        if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &phHash, 0, 0, 0, 0, 0) < 0 )
          __fastfail(7u);
        if ( BCryptHashData(phHash, pbOutput, 0x10u, 0) < 0 )
          __fastfail(7u);
        if ( BCryptHashData(phHash, &SHSpad1, 0x28u, 0) < 0 )
          __fastfail(7u);
        if ( BCryptHashData(phHash, &KeyMagic2, 0x54u, 0) < 0 )
          __fastfail(7u);
        if ( BCryptHashData(phHash, &SHSpad2, 0x28u, 0) < 0 )
          __fastfail(7u);
        if ( BCryptFinishHash(phHash, v41, 0x14u, 0) < 0 )
          __fastfail(7u);
        BCryptDestroyHash(phHash);
        v10 = *(_OWORD *)v41;
        phHash = 0;
        if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &phHash, 0, 0, 0, 0, 0) < 0 )
          __fastfail(7u);
        if ( BCryptHashData(phHash, pbOutput, 0x10u, 0) < 0 )
          __fastfail(7u);
        if ( BCryptHashData(phHash, &SHSpad1, 0x28u, 0) < 0 )
          __fastfail(7u);
        if ( BCryptHashData(phHash, KeyMagic3, 0x54u, 0) < 0 )
          __fastfail(7u);
        if ( BCryptHashData(phHash, &SHSpad2, 0x28u, 0) < 0 )
          __fastfail(7u);
        if ( BCryptFinishHash(phHash, v41, 0x14u, 0) < 0 )
          __fastfail(7u);
        BCryptDestroyHash(phHash);
        v11 = (_DWORD *)RasAuthAttributeCopyWithAlloc(*(_QWORD *)(a2 + 288), 2);
        v12 = v11;
        if ( !v11 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
          return 8;
        }
        v14 = 0;
        v15 = 0;
        LOWORD(v40[0]) = 9233;
        BYTE4(v40[0]) = 16;
        *(_OWORD *)((char *)v40 + 5) = *(_OWORD *)v41;
        if ( !*v11 )
        {
          LastError = 8;
          goto LABEL_60;
        }
        v17 = LocalAlloc(0x40u, 0x29u);
        v12[1] = v17;
        if ( v17 )
        {
          v21 = v40[0];
          v22 = v39;
          v23 = v40[1];
          *v17 = 922812416;
          v24 = v12[1];
          *(_OWORD *)(v24 + 4) = v21;
          *(_OWORD *)(v24 + 20) = v23;
          *(_DWORD *)(v24 + 36) = v22;
          *((_DWORD *)v12 + 1) = 40;
          *(_DWORD *)v12 = 26;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError )
          {
LABEL_60:
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
            {
              v19 = 90;
              v20 = LastError;
              goto LABEL_62;
            }
            goto LABEL_90;
          }
          v22 = v39;
        }
        LOBYTE(v40[0]) = 16;
        *(_OWORD *)((char *)v40 + 5) = v10;
        if ( !*((_DWORD *)v12 + 4) )
        {
          LastError = 8;
          v20 = 8;
          goto LABEL_69;
        }
        v25 = LocalAlloc(0x40u, 0x29u);
        v12[3] = v25;
        if ( v25 )
        {
          v28 = v40[0];
          *v25 = 922812416;
          LastError = 0;
          v29 = v12[3];
          v30 = v40[1];
          *(_OWORD *)(v29 + 4) = v28;
          *(_OWORD *)(v29 + 20) = v30;
          *(_DWORD *)(v29 + 36) = v22;
          *((_DWORD *)v12 + 5) = 40;
          *((_DWORD *)v12 + 4) = 26;
        }
        else
        {
          LastError = GetLastError();
          v20 = LastError;
          if ( LastError )
          {
LABEL_69:
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
            {
              v19 = 91;
LABEL_62:
              WPP_SF_d(v18[2], v19, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids, v20);
            }
LABEL_90:
            RasAuthAttributeDestroy(v12);
            if ( v15 )
              RasAuthAttributeDestroy(v15);
            if ( LastError && v14 )
              RasAuthAttributeDestroy(v14);
            return LastError;
          }
        }
        v15 = (void *)RasAuthAttributeRemoveVSA(v26, v12, v27, v20);
        if ( v15 )
        {
          v33 = *(_DWORD **)(a1 + 1336);
          v34 = 0;
          if ( *v33 )
          {
            do
              ++v34;
            while ( v33[4 * v34] );
          }
          v14 = (void *)RasAuthAttributeCopyWithAlloc(v15, v34);
          if ( v14 )
          {
            while ( v6 < v34 )
            {
              v35 = *(_QWORD *)(a1 + 1336) + 16LL * v6;
              LODWORD(pbSecret) = *(_DWORD *)(v35 + 4);
              LastError = RasAuthAttributeInsert(
                            v6,
                            (int)v14,
                            *(_DWORD *)v35,
                            0,
                            (size_t)pbSecret,
                            *(LPCWCH *)(v35 + 8));
              if ( LastError )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
                goto LABEL_90;
              }
              ++v6;
            }
            v36 = *(void **)(a1 + 1336);
            if ( v36 )
              RasAuthAttributeDestroy(v36);
            *(_QWORD *)(a1 + 1336) = v14;
            goto LABEL_90;
          }
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            v32 = 93;
LABEL_75:
            WPP_SF_(v31[2], v32, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
          }
        }
        else
        {
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            v32 = 92;
            goto LABEL_75;
          }
        }
        LastError = 8;
        goto LABEL_90;
      }
    }
    Next = (unsigned __int8 **)RasAuthAttributeGetNext(&phHash, 26);
  }
  if ( v4 != &WPP_GLOBAL_Control )
    WPP_SF_(v4[2], 87, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
  return 1168;
}

```

## disassembly

```asm
0x180009dc0  push    rbp
0x180009dc2  push    rsi
0x180009dc3  push    rdi
0x180009dc4  push    r12
0x180009dc6  push    r13
0x180009dc8  lea     rbp, [rsp-37h]
0x180009dcd  sub     rsp, 0D0h
0x180009dd4  mov     rax, cs:__security_cookie
0x180009ddb  xor     rax, rsp
0x180009dde  mov     [rbp+57h+var_48], rax
0x180009de2  xorps   xmm0, xmm0
0x180009de5  xor     eax, eax
0x180009de7  mov     [rbp+57h+var_A8], rax
0x180009deb  mov     rdi, rdx
0x180009dee  movups  [rbp+57h+var_A0], xmm0
0x180009df2  mov     r13, rcx
0x180009df5  movups  [rbp+57h+var_90], xmm0
0x180009df9  mov     r9, cs:WPP_GLOBAL_Control
0x180009e00  lea     rsi, WPP_GLOBAL_Control
0x180009e07  cmp     r9, rsi
0x180009e0a  jz      short loc_180009E28
0x180009e0c  mov     rcx, [r9+10h]
0x180009e10  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x180009e17  mov     edx, 56h ; 'V'
0x180009e1c  call    WPP_SF_
0x180009e21  mov     r9, cs:WPP_GLOBAL_Control
0x180009e28  mov     rcx, [rdi+120h]
0x180009e2f  xor     r12d, r12d
0x180009e32  test    rcx, rcx
0x180009e35  jz      short loc_180009E55
0x180009e37  mov     edx, r12d
0x180009e3a  mov     eax, edx
0x180009e3c  shl     rax, 4
0x180009e40  add     rax, rcx
0x180009e43  mov     r8d, [rax]
0x180009e46  test    r8d, r8d
0x180009e49  jz      short loc_180009E55
0x180009e4b  cmp     r8d, 1Ah
0x180009e4f  jz      short loc_180009E58
0x180009e51  inc     edx
0x180009e53  jmp     short loc_180009E3A
0x180009e55  mov     rax, r12
0x180009e58  mov     [rbp+57h+phHash], rax
0x180009e5c  mov     [rsp+0F0h+arg_10], rbx
0x180009e64  test    rax, rax
0x180009e67  jz      loc_18000A490
0x180009e6d  cmp     dword ptr [rax+4], 8
0x180009e71  jb      short loc_180009EA3
0x180009e73  mov     rbx, [rax+8]
0x180009e77  movzx   ecx, byte ptr [rbx+1]
0x180009e7b  movzx   eax, byte ptr [rbx+2]
0x180009e7f  shl     eax, 8
0x180009e82  shl     ecx, 10h
0x180009e85  add     ecx, eax
0x180009e87  movzx   eax, byte ptr [rbx]
0x180009e8a  shl     eax, 18h
0x180009e8d  add     ecx, eax
0x180009e8f  movzx   eax, byte ptr [rbx+3]
0x180009e93  add     ecx, eax
0x180009e95  cmp     ecx, 137h
0x180009e9b  jnz     short loc_180009EA3
0x180009e9d  cmp     byte ptr [rbx+4], 0Ch
0x180009ea1  jz      short loc_180009EB3
0x180009ea3  mov     edx, 1Ah
0x180009ea8  lea     rcx, [rbp+57h+phHash]
0x180009eac  call    RasAuthAttributeGetNext
0x180009eb1  jmp     short loc_180009E64
0x180009eb3  mov     [rsp+0F0h+var_28], r14
0x180009ebb  movaps  [rsp+0F0h+var_40], xmm6
0x180009ec3  mov     [rbp+57h+phHash], r12
0x180009ec7  cmp     r9, rsi
0x180009eca  jz      short loc_180009EE1
0x180009ecc  mov     rcx, [r9+10h]
0x180009ed0  lea     r8, WPP_1d8da19463c23936661cbdcc27f434e2_Traceguids
0x180009ed7  mov     edx, 23h ; '#'
0x180009edc  call    WPP_SF_
0x180009ee1  mov     [rsp+0F0h+dwFlags], r12d; dwFlags
0x180009ee6  lea     rdx, [rbp+57h+phHash]; phHash
0x180009eea  mov     [rsp+0F0h+cbSecret], r12d; cbSecret
0x180009eef  xor     r9d, r9d; cbHashObject
0x180009ef2  xor     r8d, r8d; pbHashObject
0x180009ef5  mov     [rsp+0F0h+pbSecret], r12; pbSecret
0x180009efa  mov     ecx, 31h ; '1'; hAlgorithm
0x180009eff  call    cs:__imp_BCryptCreateHash
0x180009f05  test    eax, eax
0x180009f07  jns     short loc_180009F10
0x180009f09  mov     ecx, 7
0x180009f0e  int     29h; Win8: RtlFailFast(ecx)
0x180009f10  mov     rcx, [rbp+57h+phHash]; hHash
0x180009f14  lea     rdx, [rbx+0Eh]; pbInput
0x180009f18  xor     r9d, r9d; dwFlags
0x180009f1b  mov     r8d, 10h; cbInput
0x180009f21  call    cs:__imp_BCryptHashData
0x180009f27  test    eax, eax
0x180009f29  jns     short loc_180009F32
0x180009f2b  mov     ecx, 7
0x180009f30  int     29h; Win8: RtlFailFast(ecx)
0x180009f32  mov     rcx, [rbp+57h+phHash]; hHash
0x180009f36  lea     rdx, [rdi+130h]; pbInput
0x180009f3d  xor     r9d, r9d; dwFlags
0x180009f40  mov     r8d, 18h; cbInput
0x180009f46  call    cs:__imp_BCryptHashData
0x180009f4c  test    eax, eax
0x180009f4e  jns     short loc_180009F57
0x180009f50  mov     ecx, 7
0x180009f55  int     29h; Win8: RtlFailFast(ecx)
0x180009f57  mov     rcx, [rbp+57h+phHash]; hHash
0x180009f5b  lea     rdx, KeyMagic1; "This is the MPPE Master Key"
0x180009f62  xor     r9d, r9d; dwFlags
0x180009f65  mov     r8d, 1Bh; cbInput
0x180009f6b  call    cs:__imp_BCryptHashData
0x180009f71  test    eax, eax
0x180009f73  jns     short loc_180009F7C
0x180009f75  mov     ecx, 7
0x180009f7a  int     29h; Win8: RtlFailFast(ecx)
0x180009f7c  mov     rcx, [rbp+57h+phHash]; hHash
0x180009f80  lea     rdx, [rbp+57h+pbOutput]; pbOutput
0x180009f84  xor     r9d, r9d; dwFlags
0x180009f87  mov     r8d, 14h; cbOutput
0x180009f8d  call    cs:__imp_BCryptFinishHash
0x180009f93  test    eax, eax
0x180009f95  jns     short loc_180009F9E
0x180009f97  mov     ecx, 7
0x180009f9c  int     29h; Win8: RtlFailFast(ecx)
0x180009f9e  mov     rcx, [rbp+57h+phHash]; hHash
0x180009fa2  call    cs:__imp_BCryptDestroyHash
0x180009fa8  mov     [rsp+0F0h+dwFlags], r12d; dwFlags
0x180009fad  lea     rdx, [rbp+57h+phHash]; phHash
0x180009fb1  mov     [rsp+0F0h+cbSecret], r12d; cbSecret
0x180009fb6  xor     r9d, r9d; cbHashObject
0x180009fb9  xor     r8d, r8d; pbHashObject
0x180009fbc  mov     [rsp+0F0h+pbSecret], r12; pbSecret
0x180009fc1  mov     ecx, 31h ; '1'; hAlgorithm
0x180009fc6  mov     [rbp+57h+phHash], r12
0x180009fca  call    cs:__imp_BCryptCreateHash
0x180009fd0  test    eax, eax
0x180009fd2  jns     short loc_180009FDB
0x180009fd4  mov     ecx, 7
0x180009fd9  int     29h; Win8: RtlFailFast(ecx)
0x180009fdb  mov     rcx, [rbp+57h+phHash]; hHash
0x180009fdf  lea     rdx, [rbp+57h+pbOutput]; pbInput
0x180009fe3  xor     r9d, r9d; dwFlags
0x180009fe6  mov     r8d, 10h; cbInput
0x180009fec  call    cs:__imp_BCryptHashData
0x180009ff2  test    eax, eax
0x180009ff4  jns     short loc_180009FFD
0x180009ff6  mov     ecx, 7
0x180009ffb  int     29h; Win8: RtlFailFast(ecx)
0x180009ffd  mov     rcx, [rbp+57h+phHash]; hHash
0x18000a001  lea     rdx, SHSpad1; pbInput
0x18000a008  xor     r9d, r9d; dwFlags
0x18000a00b  mov     r8d, 28h ; '('; cbInput
0x18000a011  call    cs:__imp_BCryptHashData
0x18000a017  test    eax, eax
0x18000a019  jns     short loc_18000A022
0x18000a01b  mov     ecx, 7
0x18000a020  int     29h; Win8: RtlFailFast(ecx)
0x18000a022  mov     rcx, [rbp+57h+phHash]; hHash
0x18000a026  lea     rdx, KeyMagic2; pbInput
0x18000a02d  xor     r9d, r9d; dwFlags
0x18000a030  mov     r8d, 54h ; 'T'; cbInput
0x18000a036  call    cs:__imp_BCryptHashData
0x18000a03c  test    eax, eax
0x18000a03e  jns     short loc_18000A047
0x18000a040  mov     ecx, 7
0x18000a045  int     29h; Win8: RtlFailFast(ecx)
0x18000a047  mov     rcx, [rbp+57h+phHash]; hHash
0x18000a04b  lea     rdx, SHSpad2; pbInput
0x18000a052  xor     r9d, r9d; dwFlags
0x18000a055  mov     r8d, 28h ; '('; cbInput
0x18000a05b  call    cs:__imp_BCryptHashData
0x18000a061  test    eax, eax
0x18000a063  jns     short loc_18000A06C
0x18000a065  mov     ecx, 7
0x18000a06a  int     29h; Win8: RtlFailFast(ecx)
0x18000a06c  mov     rcx, [rbp+57h+phHash]; hHash
0x18000a070  lea     rdx, [rbp+57h+var_78]; pbOutput
0x18000a074  xor     r9d, r9d; dwFlags
0x18000a077  mov     r8d, 14h; cbOutput
0x18000a07d  call    cs:__imp_BCryptFinishHash
0x18000a083  test    eax, eax
0x18000a085  jns     short loc_18000A08E
0x18000a087  mov     ecx, 7
0x18000a08c  int     29h; Win8: RtlFailFast(ecx)
0x18000a08e  mov     rcx, [rbp+57h+phHash]; hHash
0x18000a092  call    cs:__imp_BCryptDestroyHash
0x18000a098  movups  xmm6, xmmword ptr [rbp+57h+var_78]
0x18000a09c  mov     [rsp+0F0h+dwFlags], r12d; dwFlags
0x18000a0a1  lea     rdx, [rbp+57h+phHash]; phHash
0x18000a0a5  mov     [rsp+0F0h+cbSecret], r12d; cbSecret
0x18000a0aa  xor     r9d, r9d; cbHashObject
0x18000a0ad  xor     r8d, r8d; pbHashObject
0x18000a0b0  mov     [rsp+0F0h+pbSecret], r12; pbSecret
0x18000a0b5  mov     ecx, 31h ; '1'; hAlgorithm
0x18000a0ba  mov     [rbp+57h+phHash], r12
0x18000a0be  call    cs:__imp_BCryptCreateHash
0x18000a0c4  test    eax, eax
0x18000a0c6  jns     short loc_18000A0CF
0x18000a0c8  mov     ecx, 7
0x18000a0cd  int     29h; Win8: RtlFailFast(ecx)
0x18000a0cf  mov     rcx, [rbp+57h+phHash]; hHash
0x18000a0d3  lea     rdx, [rbp+57h+pbOutput]; pbInput
0x18000a0d7  xor     r9d, r9d; dwFlags
0x18000a0da  mov     r8d, 10h; cbInput
0x18000a0e0  call    cs:__imp_BCryptHashData
0x18000a0e6  test    eax, eax
0x18000a0e8  jns     short loc_18000A0F1
0x18000a0ea  mov     ecx, 7
0x18000a0ef  int     29h; Win8: RtlFailFast(ecx)
0x18000a0f1  mov     rcx, [rbp+57h+phHash]; hHash
0x18000a0f5  lea     rdx, SHSpad1; pbInput
0x18000a0fc  xor     r9d, r9d; dwFlags
0x18000a0ff  mov     r8d, 28h ; '('; cbInput
0x18000a105  call    cs:__imp_BCryptHashData
0x18000a10b  test    eax, eax
0x18000a10d  jns     short loc_18000A116
0x18000a10f  mov     ecx, 7
0x18000a114  int     29h; Win8: RtlFailFast(ecx)
0x18000a116  mov     rcx, [rbp+57h+phHash]; hHash
0x18000a11a  lea     rdx, KeyMagic3; "On the client side, this is the receive"...
0x18000a121  xor     r9d, r9d; dwFlags
0x18000a124  mov     r8d, 54h ; 'T'; cbInput
0x18000a12a  call    cs:__imp_BCryptHashData
0x18000a130  test    eax, eax
0x18000a132  jns     short loc_18000A13B
0x18000a134  mov     ecx, 7
0x18000a139  int     29h; Win8: RtlFailFast(ecx)
0x18000a13b  mov     rcx, [rbp+57h+phHash]; hHash
0x18000a13f  lea     rdx, SHSpad2; pbInput
0x18000a146  xor     r9d, r9d; dwFlags
0x18000a149  mov     r8d, 28h ; '('; cbInput
0x18000a14f  call    cs:__imp_BCryptHashData
0x18000a155  test    eax, eax
0x18000a157  jns     short loc_18000A160
0x18000a159  mov     ecx, 7
0x18000a15e  int     29h; Win8: RtlFailFast(ecx)
0x18000a160  mov     rcx, [rbp+57h+phHash]; hHash
0x18000a164  lea     rdx, [rbp+57h+var_78]; pbOutput
0x18000a168  xor     r9d, r9d; dwFlags
0x18000a16b  mov     r8d, 14h; cbOutput
0x18000a171  call    cs:__imp_BCryptFinishHash
0x18000a177  test    eax, eax
0x18000a179  jns     short loc_18000A182
0x18000a17b  mov     ecx, 7
0x18000a180  int     29h; Win8: RtlFailFast(ecx)
0x18000a182  mov     rcx, [rbp+57h+phHash]; hHash
0x18000a186  call    cs:__imp_BCryptDestroyHash
0x18000a18c  mov     rcx, [rdi+120h]
0x18000a193  mov     edx, 2
0x18000a198  call    RasAuthAttributeCopyWithAlloc
0x18000a19d  mov     r14, rax
0x18000a1a0  test    rax, rax
0x18000a1a3  jnz     short loc_18000A1FE
0x18000a1a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1ac  cmp     rcx, rsi
0x18000a1af  jz      short loc_18000A1C6
0x18000a1b1  mov     rcx, [rcx+10h]
0x18000a1b5  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x18000a1bc  mov     edx, 59h ; 'Y'
0x18000a1c1  call    WPP_SF_
0x18000a1c6  mov     eax, 8
0x18000a1cb  mov     r14, [rsp+0F0h+var_28]
0x18000a1d3  movaps  xmm6, [rsp+0F0h+var_40]
0x18000a1db  mov     rbx, [rsp+0F0h+arg_10]
0x18000a1e3  mov     rcx, [rbp+57h+var_48]
0x18000a1e7  xor     rcx, rsp; StackCookie
0x18000a1ea  call    __security_check_cookie
0x18000a1ef  add     rsp, 0D0h
0x18000a1f6  pop     r13
0x18000a1f8  pop     r12
0x18000a1fa  pop     rdi
0x18000a1fb  pop     rsi
0x18000a1fc  pop     rbp
0x18000a1fd  retn
0x18000a1fe  mov     rsi, r12
0x18000a201  mov     [rsp+0F0h+var_30], r15
0x18000a209  mov     r15, r12
0x18000a20c  mov     word ptr [rbp+57h+var_A0], 2411h
0x18000a212  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x18000a216  mov     byte ptr [rbp+57h+var_A0+4], 10h
0x18000a21a  movups  [rbp+57h+var_A0+5], xmm0
0x18000a21e  cmp     [rax], r12d
0x18000a221  jnz     short loc_18000A22A
0x18000a223  mov     edi, 8
0x18000a228  jmp     short loc_18000A24F
0x18000a22a  mov     edx, 29h ; ')'; uBytes
0x18000a22f  mov     ecx, 40h ; '@'; uFlags
0x18000a234  call    cs:__imp_LocalAlloc
0x18000a23a  mov     [r14+8], rax
0x18000a23e  test    rax, rax
0x18000a241  jnz     short loc_18000A283
0x18000a243  call    cs:__imp_GetLastError
0x18000a249  mov     edi, eax
0x18000a24b  test    eax, eax
0x18000a24d  jz      short loc_18000A2B5
0x18000a24f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a256  lea     rax, WPP_GLOBAL_Control
0x18000a25d  cmp     rcx, rax
0x18000a260  jz      loc_18000A45B
0x18000a266  mov     edx, 5Ah ; 'Z'
  ... truncated ...
```
