# AsyncProcessSecurityContext(void *,_KsecIoctlIpcFunctionCall *)

- ea: `0x1400049c8`
- end: `0x140004ca3`
- name: `?AsyncProcessSecurityContext@@YAXPEAXPEAU_KsecIoctlIpcFunctionCall@@@Z`
- size: `731`
- prototype: `void __fastcall(void *, struct _KsecIoctlIpcFunctionCall *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140004d80`

## callees

- `0x140001010`
- `0x1400014c0`
- `0x1400020c0`
- `0x140002a02`
- `0x1400049c8`
- `0x140005044`

## import_xrefs

- `SspiSrv!SspirProcessSecurityContext` at `0x140004c30`
- `SspiSrv!SspirProcessSecurityContext` at `0x140004c30`

## pseudocode

```c
void __fastcall AsyncProcessSecurityContext(void *a1, struct _KsecIoctlIpcFunctionCall *a2)
{
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rcx
  char *v7; // rcx
  unsigned __int64 v8; // rax
  unsigned int i; // ecx
  __int64 v10; // rax
  __int64 v11; // r9
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  char *v15; // rcx
  unsigned __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // r14
  __int64 v19; // r15
  unsigned int v20; // ecx
  __int64 v21; // r8
  unsigned int v22; // edx
  __int64 v23; // r9
  __int64 v24; // r8
  __int128 *v25; // r10
  int v26; // eax
  int v27; // edx
  int v28; // eax
  __int64 v29; // rdx
  __int128 v30; // [rsp+B0h] [rbp-80h] BYREF
  __int128 v31; // [rsp+C0h] [rbp-70h] BYREF
  __int128 v32; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v33; // [rsp+E0h] [rbp-50h] BYREF
  int v34; // [rsp+E8h] [rbp-48h] BYREF
  __int128 *v35; // [rsp+F0h] [rbp-40h]
  char v36[8]; // [rsp+F8h] [rbp-38h] BYREF
  __int128 *v37; // [rsp+100h] [rbp-30h]
  char v38[8]; // [rsp+108h] [rbp-28h] BYREF
  char v39[16]; // [rsp+110h] [rbp-20h] BYREF
  char v40[8]; // [rsp+120h] [rbp-10h] BYREF
  char v41[8]; // [rsp+128h] [rbp-8h] BYREF

  if ( !gLsapSspiExtension || !*(_QWORD *)(gLsapSspiExtension + 56) )
  {
    v29 = 3221225659LL;
    goto LABEL_42;
  }
  v4 = *((unsigned int *)a2 + 10);
  if ( (unsigned int)v4 < 0x78 )
    goto LABEL_40;
  v5 = *((_QWORD *)a2 + 7);
  if ( v4 < v5 )
    goto LABEL_40;
  if ( v5 )
  {
    *((_QWORD *)a2 + 7) = (char *)a2 + v5;
    LODWORD(v4) = *((_DWORD *)a2 + 10);
  }
  v6 = *((_QWORD *)a2 + 13);
  if ( (unsigned int)v4 < v6 )
    goto LABEL_40;
  if ( !v6 )
    goto LABEL_19;
  v7 = (char *)a2 + v6;
  *((_QWORD *)a2 + 13) = v7;
  if ( !v7 )
    goto LABEL_19;
  v8 = *((_QWORD *)v7 + 1);
  if ( (unsigned int)v4 < v8 )
  {
LABEL_40:
    v29 = 3221225507LL;
LABEL_42:
    SendStatusOnlyResponse(a2, v29);
    return;
  }
  if ( v8 )
    *((_QWORD *)v7 + 1) = (char *)a2 + v8;
  for ( i = 0; ; ++i )
  {
    v10 = *((_QWORD *)a2 + 13);
    if ( i >= *(_DWORD *)(v10 + 4) )
      break;
    v11 = *(_QWORD *)(v10 + 8);
    v12 = *(_QWORD *)(v11 + 16LL * i + 8);
    if ( *((unsigned int *)a2 + 10) < v12 )
      goto LABEL_40;
    if ( v12 )
      *(_QWORD *)(v11 + 16LL * i + 8) = (char *)a2 + v12;
  }
LABEL_19:
  v13 = *((_QWORD *)a2 + 14);
  v14 = *((unsigned int *)a2 + 10);
  if ( v14 < v13 )
    goto LABEL_40;
  if ( v13 )
  {
    v15 = (char *)a2 + v13;
    *((_QWORD *)a2 + 14) = v15;
    if ( v15 )
    {
      v16 = *((_QWORD *)v15 + 1);
      if ( v14 >= v16 )
      {
        if ( v16 )
          *((_QWORD *)v15 + 1) = (char *)a2 + v16;
        goto LABEL_25;
      }
      goto LABEL_40;
    }
  }
LABEL_25:
  v17 = *((_QWORD *)a2 + 13);
  v18 = 0;
  v19 = 0;
  if ( v17 )
  {
    v20 = *(_DWORD *)(v17 + 4);
    if ( v20 )
    {
      v21 = *(_QWORD *)(v17 + 8);
      v22 = 0;
      v23 = 0;
      do
      {
        if ( *(_DWORD *)(v21 + 16 * v23 + 4) == 129 )
        {
          v18 = *(_QWORD *)(v21 + 16 * v23 + 8);
        }
        else if ( *(_DWORD *)(v21 + 16 * v23 + 4) == 130 )
        {
          v19 = *(_QWORD *)(v21 + 16 * v23 + 8);
        }
        ++v22;
        ++v23;
      }
      while ( v22 < v20 );
    }
  }
  v32 = 0;
  v30 = 0;
  v31 = 0;
  memset_0(&v34, 0, 0x48u);
  v24 = *((_QWORD *)a2 + 14);
  v25 = &v32;
  v35 = &v30;
  v37 = &v31;
  if ( v17 )
    v25 = (__int128 *)v17;
  v33 = *(_QWORD *)a2;
  v26 = SspirProcessSecurityContext(
          a1,
          (char *)a2 + 16,
          v38,
          ((unsigned __int64)a2 + 48) & -(__int64)(*((_QWORD *)a2 + 7) != 0),
          (char *)a2 + 64,
          (char *)a2 + 80,
          *((_DWORD *)a2 + 24),
          *((_DWORD *)a2 + 25),
          v18,
          v19,
          v25,
          v24,
          &v30,
          v36,
          &v31,
          v39,
          v40,
          v41,
          &v34,
          0,
          0);
  v27 = v34;
  if ( v26 < 0 )
    v27 = v26;
  v34 = v27;
  v28 = MarshalAndSendProcessSecurityContextResult((__int64)&v33);
  if ( v28 < 0 )
    SendStatusOnlyResponse(a2, (unsigned int)v28);
  CleanUpAfterProcessSecurityContext(&v30, &v33);
}

```

## disassembly

```asm
0x1400049c8  mov     [rsp-8+arg_10], rbx
0x1400049cd  mov     [rsp-8+arg_18], rsi
0x1400049d2  push    rbp
0x1400049d3  push    rdi
0x1400049d4  push    r12
0x1400049d6  push    r14
0x1400049d8  push    r15
0x1400049da  lea     rbp, [rsp-10h]
0x1400049df  sub     rsp, 140h
0x1400049e6  mov     rax, cs:__security_cookie
0x1400049ed  xor     rax, rsp
0x1400049f0  mov     [rbp+30h+var_30], rax
0x1400049f4  mov     rax, cs:gLsapSspiExtension
0x1400049fb  mov     rdi, rdx
0x1400049fe  mov     r12, rcx
0x140004a01  test    rax, rax
0x140004a04  jz      loc_140004C6E
0x140004a0a  cmp     qword ptr [rax+38h], 0
0x140004a0f  jz      loc_140004C6E
0x140004a15  mov     edx, [rdx+28h]
0x140004a18  cmp     edx, 78h ; 'x'
0x140004a1b  jb      loc_140004C67
0x140004a21  lea     rsi, [rdi+30h]
0x140004a25  mov     rcx, [rsi+8]
0x140004a29  cmp     rdx, rcx
0x140004a2c  jb      loc_140004C67
0x140004a32  test    rcx, rcx
0x140004a35  jz      short loc_140004A42
0x140004a37  lea     rax, [rcx+rdi]
0x140004a3b  mov     [rsi+8], rax
0x140004a3f  mov     edx, [rdi+28h]
0x140004a42  mov     rcx, [rdi+68h]
0x140004a46  mov     r8d, edx
0x140004a49  cmp     r8, rcx
0x140004a4c  jb      loc_140004C67
0x140004a52  test    rcx, rcx
0x140004a55  jz      short loc_140004AB3
0x140004a57  add     rcx, rdi
0x140004a5a  mov     [rdi+68h], rcx
0x140004a5e  test    rcx, rcx
0x140004a61  jz      short loc_140004AB3
0x140004a63  mov     rax, [rcx+8]
0x140004a67  cmp     r8, rax
0x140004a6a  jb      loc_140004C67
0x140004a70  test    rax, rax
0x140004a73  jz      short loc_140004A7C
0x140004a75  add     rax, rdi
0x140004a78  mov     [rcx+8], rax
0x140004a7c  xor     ecx, ecx
0x140004a7e  mov     rax, [rdi+68h]
0x140004a82  cmp     ecx, [rax+4]
0x140004a85  jnb     short loc_140004AB3
0x140004a87  mov     r9, [rax+8]
0x140004a8b  mov     eax, [rdi+28h]
0x140004a8e  mov     edx, ecx
0x140004a90  add     rdx, rdx
0x140004a93  mov     r8, [r9+rdx*8+8]
0x140004a98  cmp     rax, r8
0x140004a9b  jb      loc_140004C67
0x140004aa1  test    r8, r8
0x140004aa4  jz      short loc_140004AAF
0x140004aa6  lea     rax, [r8+rdi]
0x140004aaa  mov     [r9+rdx*8+8], rax
0x140004aaf  inc     ecx
0x140004ab1  jmp     short loc_140004A7E
0x140004ab3  mov     rcx, [rdi+70h]
0x140004ab7  mov     edx, [rdi+28h]
0x140004aba  cmp     rdx, rcx
0x140004abd  jb      loc_140004C67
0x140004ac3  test    rcx, rcx
0x140004ac6  jz      short loc_140004AED
0x140004ac8  add     rcx, rdi
0x140004acb  mov     [rdi+70h], rcx
0x140004acf  test    rcx, rcx
0x140004ad2  jz      short loc_140004AED
0x140004ad4  mov     rax, [rcx+8]
0x140004ad8  cmp     rdx, rax
0x140004adb  jb      loc_140004C67
0x140004ae1  test    rax, rax
0x140004ae4  jz      short loc_140004AED
0x140004ae6  add     rax, rdi
0x140004ae9  mov     [rcx+8], rax
0x140004aed  mov     rbx, [rdi+68h]
0x140004af1  xor     r14d, r14d
0x140004af4  xor     r15d, r15d
0x140004af7  test    rbx, rbx
0x140004afa  jz      short loc_140004B3D
0x140004afc  mov     ecx, [rbx+4]
0x140004aff  test    ecx, ecx
0x140004b01  jz      short loc_140004B3D
0x140004b03  mov     r8, [rbx+8]
0x140004b07  xor     edx, edx
0x140004b09  xor     r9d, r9d
0x140004b0c  mov     rax, r9
0x140004b0f  add     rax, rax
0x140004b12  cmp     dword ptr [r8+rax*8+4], 81h
0x140004b1b  jnz     short loc_140004B24
0x140004b1d  mov     r14, [r8+rax*8+8]
0x140004b22  jmp     short loc_140004B34
0x140004b24  cmp     dword ptr [r8+rax*8+4], 82h
0x140004b2d  jnz     short loc_140004B34
0x140004b2f  mov     r15, [r8+rax*8+8]
0x140004b34  inc     edx
0x140004b36  inc     r9
0x140004b39  cmp     edx, ecx
0x140004b3b  jb      short loc_140004B0C
0x140004b3d  xorps   xmm0, xmm0
0x140004b40  lea     rcx, [rbp+30h+var_78]; void *
0x140004b44  xor     edx, edx; Val
0x140004b46  xorps   xmm1, xmm1
0x140004b49  movups  [rbp+30h+var_90], xmm0
0x140004b4d  movups  [rbp+30h+var_B0], xmm1
0x140004b51  lea     r8d, [rdx+48h]; Size
0x140004b55  movups  [rbp+30h+var_A0], xmm0
0x140004b59  call    memset_0
0x140004b5e  mov     r8, [rdi+70h]
0x140004b62  lea     rax, [rbp+30h+var_B0]
0x140004b66  mov     [rsp+160h+var_C0], 0
0x140004b72  lea     r11, [rdi+50h]
0x140004b76  mov     [rsp+160h+var_C8], 0
0x140004b82  lea     r10, [rbp+30h+var_90]
0x140004b86  mov     [rbp+30h+var_70], rax
0x140004b8a  lea     rdx, [rdi+10h]
0x140004b8e  test    rbx, rbx
0x140004b91  lea     rax, [rbp+30h+var_A0]
0x140004b95  mov     [rbp+30h+var_60], rax
0x140004b99  mov     rcx, r12
0x140004b9c  mov     rax, [rdi]
0x140004b9f  cmovnz  r10, rbx
0x140004ba3  mov     [rbp+30h+var_80], rax
0x140004ba7  lea     rbx, [rdi+40h]
0x140004bab  mov     rax, [rdi+38h]
0x140004baf  neg     rax
0x140004bb2  lea     rax, [rbp+30h+var_78]
0x140004bb6  mov     [rsp+160h+var_D0], rax
0x140004bbe  sbb     r9, r9
0x140004bc1  lea     rax, [rbp+30h+var_38]
0x140004bc5  and     r9, rsi
0x140004bc8  mov     [rsp+160h+var_D8], rax
0x140004bd0  lea     rax, [rbp+30h+var_40]
0x140004bd4  mov     [rsp+160h+var_E0], rax
0x140004bdc  lea     rax, [rbp+30h+var_50]
0x140004be0  mov     [rsp+160h+var_E8], rax
0x140004be5  lea     rax, [rbp+30h+var_A0]
0x140004be9  mov     [rsp+160h+var_F0], rax
0x140004bee  lea     rax, [rbp+30h+var_68]
0x140004bf2  mov     [rsp+160h+var_F8], rax
0x140004bf7  lea     rax, [rbp+30h+var_B0]
0x140004bfb  mov     [rsp+160h+var_100], rax
0x140004c00  mov     eax, [rdi+64h]
0x140004c03  mov     [rsp+160h+var_108], r8
0x140004c08  lea     r8, [rbp+30h+var_58]
0x140004c0c  mov     [rsp+160h+var_110], r10
0x140004c11  mov     [rsp+160h+var_118], r15
0x140004c16  mov     [rsp+160h+var_120], r14
0x140004c1b  mov     [rsp+160h+var_128], eax
0x140004c1f  mov     eax, [rdi+60h]
0x140004c22  mov     [rsp+160h+var_130], eax
0x140004c26  mov     [rsp+160h+var_138], r11
0x140004c2b  mov     [rsp+160h+var_140], rbx
0x140004c30  call    cs:__imp_SspirProcessSecurityContext
0x140004c36  mov     edx, [rbp+30h+var_78]
0x140004c39  lea     rcx, [rbp+30h+var_80]
0x140004c3d  test    eax, eax
0x140004c3f  cmovs   edx, eax
0x140004c42  mov     [rbp+30h+var_78], edx
0x140004c45  call    MarshalAndSendProcessSecurityContextResult
0x140004c4a  test    eax, eax
0x140004c4c  jns     short loc_140004C58
0x140004c4e  mov     edx, eax
0x140004c50  mov     rcx, rdi
0x140004c53  call    SendStatusOnlyResponse
0x140004c58  lea     rdx, [rbp+30h+var_80]
0x140004c5c  lea     rcx, [rbp+30h+var_B0]
0x140004c60  call    CleanUpAfterProcessSecurityContext
0x140004c65  jmp     short loc_140004C7B
0x140004c67  mov     edx, 0C0000023h
0x140004c6c  jmp     short loc_140004C73
0x140004c6e  mov     edx, 0C00000BBh
0x140004c73  mov     rcx, rdi
0x140004c76  call    SendStatusOnlyResponse
0x140004c7b  mov     rcx, [rbp+30h+var_30]
0x140004c7f  xor     rcx, rsp; StackCookie
0x140004c82  call    __security_check_cookie
0x140004c87  lea     r11, [rsp+160h+var_20]
0x140004c8f  mov     rbx, [r11+40h]
0x140004c93  mov     rsi, [r11+48h]
0x140004c97  mov     rsp, r11
0x140004c9a  pop     r15
0x140004c9c  pop     r14
0x140004c9e  pop     r12
0x140004ca0  pop     rdi
0x140004ca1  pop     rbp
0x140004ca2  retn
```
