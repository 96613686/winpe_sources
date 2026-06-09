# DhcpGetLinkCharacteristics

- ea: `0x1800135dc`
- end: `0x1800139de`
- name: `DhcpGetLinkCharacteristics`
- size: `1026`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `13`
- tags: ``

## callers

- `0x1800159d0`
- `0x180025c74`
- `0x18003bf98`

## callees

- `0x180006440`
- `0x180007328`
- `0x1800135dc`
- `0x18001cef0`
- `0x18001d826`
- `0x180042594`
- `0x180047e3c`
- `0x180049168`
- `0x18004c4b0`
- `0x18004d1a0`
- `0x18004d4c0`
- `0x18004d958`
- `0x18004dd28`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013925`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013985`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013925`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013985`
- `NSI!NsiGetAllParametersEx` at `0x180013738`
- `NSI!NsiGetAllParametersEx` at `0x180013738`

## pseudocode

```c
__int64 __fastcall DhcpGetLinkCharacteristics(_QWORD *a1, _QWORD *a2)
{
  void *v4; // r14
  int v5; // edx
  int v6; // r8d
  unsigned int AllParameters; // eax
  unsigned int NlInterfaceParameters; // ebx
  size_t v9; // rbx
  __int64 v10; // r14
  int v11; // r15d
  char *v12; // rax
  _QWORD *v13; // rdi
  bool v14; // zf
  void *v15; // rcx
  __int64 v16; // r8
  int v17; // edx
  int v18; // r8d
  int v20; // [rsp+20h] [rbp-E0h]
  unsigned int v21; // [rsp+70h] [rbp-90h] BYREF
  void *lpMem; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v23[2]; // [rsp+80h] [rbp-80h] BYREF
  char v24[8]; // [rsp+90h] [rbp-70h] BYREF
  int v25; // [rsp+98h] [rbp-68h]
  const NPI_MODULEID *v26; // [rsp+A0h] [rbp-60h]
  int v27; // [rsp+A8h] [rbp-58h]
  __int64 v28; // [rsp+B0h] [rbp-50h]
  _QWORD *v29; // [rsp+B8h] [rbp-48h]
  int v30; // [rsp+C0h] [rbp-40h]
  __int64 v31; // [rsp+C8h] [rbp-38h]
  int v32; // [rsp+D0h] [rbp-30h]
  _DWORD *v33; // [rsp+D8h] [rbp-28h]
  int v34; // [rsp+E0h] [rbp-20h]
  _DWORD *v35; // [rsp+E8h] [rbp-18h]
  int v36; // [rsp+F0h] [rbp-10h]
  _BYTE v37[176]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v38; // [rsp+1B0h] [rbp+B0h]
  _DWORD v39[130]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int16 v40; // [rsp+3F8h] [rbp+2F8h]
  int v41; // [rsp+3FCh] [rbp+2FCh]
  int v42; // [rsp+400h] [rbp+300h]
  __int128 v43; // [rsp+408h] [rbp+308h]
  int v44; // [rsp+420h] [rbp+320h]
  int v45; // [rsp+424h] [rbp+324h]
  _DWORD v46[137]; // [rsp+430h] [rbp+330h] BYREF
  unsigned __int16 v47; // [rsp+654h] [rbp+554h]
  char Src[94]; // [rsp+656h] [rbp+556h] BYREF
  int v49; // [rsp+6B4h] [rbp+5B4h]

  v23[0] = *a1;
  v21 = 0;
  v4 = 0;
  lpMem = 0;
  memset_0(v39, 0, 0x238u);
  memset_0(v46, 0, 0x290u);
  memset_0(v37, 0, 0xF0u);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 38, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, *a1);
  *a2 = 0;
  memset_0(v24, 0, 0x68u);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_qqLqLLLLdd(
      (unsigned int)&NPI_MS_NDIS_MODULEID,
      v5,
      v6,
      0,
      (char)&NPI_MS_NDIS_MODULEID,
      1,
      (char)v23,
      8,
      0,
      144,
      56,
      1,
      0);
  v26 = &NPI_MS_NDIS_MODULEID;
  v29 = v23;
  v25 = 0;
  v33 = v46;
  v35 = v39;
  v27 = 1;
  v30 = 8;
  v31 = 0;
  v32 = 0;
  v34 = 656;
  v36 = 568;
  v28 = 1;
  AllParameters = NsiGetAllParametersEx(v24);
  NlInterfaceParameters = AllParameters;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 11, WPP_427c3a8e92a933594072e65998df1ebc_Traceguids, AllParameters);
  if ( !NlInterfaceParameters )
  {
    NlInterfaceParameters = DhcpGetNlInterfaceParameters(a1, 1, v37);
    if ( NlInterfaceParameters )
      goto LABEL_36;
    NlInterfaceParameters = DhcpEnumIPv4Address(a1, 0, &v21, &lpMem);
    if ( NlInterfaceParameters )
      goto LABEL_12;
    v9 = v47;
    v10 = v21;
    v11 = v47 + 7;
    v12 = (char *)DhcpAlloc((v11 & 0xFFFFFFF8) + ((4 * v21 + 7) & 0xFFFFFFF8) + 96);
    v13 = v12;
    if ( !v12 )
    {
      NlInterfaceParameters = 14;
LABEL_12:
      v4 = lpMem;
      goto LABEL_34;
    }
    *((_QWORD *)v12 + 8) = v12 + 96;
    *((_QWORD *)v12 + 10) = &v12[(v11 & 0xFFFFFFF8) + 96];
    *(_QWORD *)v12 = *a1;
    *((_DWORD *)v12 + 2) = v39[0];
    *((_DWORD *)v12 + 7) = v46[0];
    *((_DWORD *)v12 + 13) = v41;
    v14 = v49 == 1;
    *((_WORD *)v12 + 30) = v9;
    *((_DWORD *)v12 + 14) = v14;
    *((_QWORD *)v12 + 11) = v38;
    *((_WORD *)v12 + 16) = v40;
    *((_DWORD *)v12 + 9) = v42 != 0;
    *(_OWORD *)(v12 + 12) = v43;
    *((_DWORD *)v12 + 11) = v44;
    *((_DWORD *)v12 + 12) = v45;
    memcpy_0(v12 + 96, Src, v9);
    v15 = (void *)v13[10];
    v16 = v10;
    *((_DWORD *)v13 + 18) = v10;
    v4 = lpMem;
    memcpy_0(v15, lpMem, 4 * v16);
    if ( *((_WORD *)v13 + 16) == 1 )
    {
      *((_BYTE *)v13 + 40) = 7;
      goto LABEL_31;
    }
    if ( *((_WORD *)v13 + 16) != 6 )
    {
      switch ( *((_WORD *)v13 + 16) )
      {
        case 9:
        case 0xF:
          *((_BYTE *)v13 + 40) = 6;
          goto LABEL_31;
        case 0x17:
          *((_BYTE *)v13 + 40) = 8;
          goto LABEL_31;
        case 0x18:
          if ( (xmmword_1800616A0 & 0x10) != 0 )
            WPP_SF_q(1028, 40, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, *a1);
          HeapFree(NtCurrentPeb()->ProcessHeap, 0, v13);
          NlInterfaceParameters = -1;
          goto LABEL_34;
      }
      if ( *((_WORD *)v13 + 16) != 71 )
      {
        if ( *((_WORD *)v13 + 16) == 144 )
        {
          *((_BYTE *)v13 + 40) = 24;
          goto LABEL_31;
        }
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_ll_guid_(
            *((unsigned __int16 *)v13 + 16) - 71,
            v17,
            v18,
            *((unsigned __int16 *)v13 + 16),
            v20,
            (__int64)v13 + 12);
      }
    }
    *((_BYTE *)v13 + 40) = 1;
LABEL_31:
    NlInterfaceParameters = 0;
    *a2 = v13;
    goto LABEL_34;
  }
  if ( (xmmword_1800616A0 & 2) == 0 )
    goto LABEL_36;
  WPP_SF_Dd(1025, 39, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, NlInterfaceParameters, NlInterfaceParameters);
LABEL_34:
  if ( v4 )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v4);
LABEL_36:
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_qD(1028, 42, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, *a1, NlInterfaceParameters);
  return NlInterfaceParameters;
}

```

## disassembly

```asm
0x1800135dc  mov     [rsp-8+arg_10], rbx
0x1800135e1  mov     [rsp-8+arg_18], rsi
0x1800135e6  push    rbp
0x1800135e7  push    rdi
0x1800135e8  push    r12
0x1800135ea  push    r14
0x1800135ec  push    r15
0x1800135ee  lea     rbp, [rsp-5D0h]
0x1800135f6  sub     rsp, 6D0h
0x1800135fd  mov     rax, cs:__security_cookie
0x180013604  xor     rax, rsp
0x180013607  mov     [rbp+5F0h+var_30], rax
0x18001360e  mov     rax, [rcx]
0x180013611  mov     r12, rdx
0x180013614  mov     rsi, rcx
0x180013617  mov     [rbp+5F0h+var_670], rax
0x18001361b  mov     r15d, 238h
0x180013621  mov     [rsp+6F0h+var_680], 0
0x180013629  xor     r14d, r14d
0x18001362c  lea     rcx, [rbp+5F0h+var_500]; void *
0x180013633  mov     r8d, r15d; Size
0x180013636  mov     [rsp+6F0h+lpMem], r14
0x18001363b  xor     edx, edx; Val
0x18001363d  call    memset_0
0x180013642  xor     edx, edx; Val
0x180013644  lea     r8d, [r15+58h]; Size
0x180013648  lea     rcx, [rbp+5F0h+var_2C0]; void *
0x18001364f  call    memset_0
0x180013654  xor     edx, edx; Val
0x180013656  lea     rcx, [rbp+5F0h+var_5F0]; void *
0x18001365a  mov     r8d, 0F0h; Size
0x180013660  call    memset_0
0x180013665  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001366c  jz      short loc_180013686
0x18001366e  mov     r9, [rsi]
0x180013671  lea     edx, [r14+26h]
0x180013675  mov     ecx, 404h
0x18001367a  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x180013681  call    WPP_SF_q
0x180013686  xor     edx, edx; Val
0x180013688  mov     [r12], r14
0x18001368c  lea     rcx, [rbp+5F0h+var_660]; void *
0x180013690  lea     r8d, [rdx+68h]; Size
0x180013694  call    memset_0
0x180013699  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800136a0  lea     rcx, NPI_MS_NDIS_MODULEID
0x1800136a7  mov     edi, 1
0x1800136ac  lea     ebx, [rdi+7]
0x1800136af  jz      short loc_1800136F1
0x1800136b1  mov     [rsp+6F0h+var_690], r14d
0x1800136b6  lea     rax, [rbp+5F0h+var_670]
0x1800136ba  mov     [rsp+6F0h+var_698], edi
0x1800136be  xor     r9d, r9d
0x1800136c1  mov     [rsp+6F0h+var_6A0], r15d
0x1800136c6  mov     [rsp+6F0h+var_6A8], 290h
0x1800136ce  mov     [rsp+6F0h+var_6B0], r14d
0x1800136d3  mov     [rsp+6F0h+var_6B8], ebx
0x1800136d7  mov     [rsp+6F0h+var_6C0], rax
0x1800136dc  mov     dword ptr [rsp+6F0h+var_6C8], edi
0x1800136e0  mov     [rsp+6F0h+var_6D0], rcx
0x1800136e5  call    WPP_SF_qqLqLLLLdd
0x1800136ea  lea     rcx, NPI_MS_NDIS_MODULEID
0x1800136f1  lea     rax, [rbp+5F0h+var_670]
0x1800136f5  mov     [rbp+5F0h+var_650], rcx
0x1800136f9  mov     [rbp+5F0h+var_638], rax
0x1800136fd  lea     rcx, [rbp+5F0h+var_660]
0x180013701  lea     rax, [rbp+5F0h+var_2C0]
0x180013708  mov     [rbp+5F0h+var_658], r14d
0x18001370c  mov     [rbp+5F0h+var_618], rax
0x180013710  lea     rax, [rbp+5F0h+var_500]
0x180013717  mov     [rbp+5F0h+var_608], rax
0x18001371b  mov     [rbp+5F0h+var_648], edi
0x18001371e  mov     [rbp+5F0h+var_630], ebx
0x180013721  mov     [rbp+5F0h+var_628], r14
0x180013725  mov     [rbp+5F0h+var_620], r14d
0x180013729  mov     [rbp+5F0h+var_610], 290h
0x180013730  mov     [rbp+5F0h+var_600], r15d
0x180013734  mov     [rbp+5F0h+var_640], rdi
0x180013738  call    cs:__imp_NsiGetAllParametersEx
0x18001373e  mov     ebx, eax
0x180013740  test    byte ptr cs:xmmword_1800616A0, 10h
0x180013747  jz      short loc_180013762
0x180013749  mov     edx, 0Bh
0x18001374e  lea     r8, WPP_427c3a8e92a933594072e65998df1ebc_Traceguids
0x180013755  mov     ecx, 404h
0x18001375a  mov     r9d, eax
0x18001375d  call    WPP_SF_D
0x180013762  test    ebx, ebx
0x180013764  jnz     loc_180013948
0x18001376a  lea     r8, [rbp+5F0h+var_5F0]
0x18001376e  mov     edx, edi
0x180013770  mov     rcx, rsi
0x180013773  call    DhcpGetNlInterfaceParameters
0x180013778  mov     ebx, eax
0x18001377a  test    eax, eax
0x18001377c  jnz     loc_18001398B
0x180013782  lea     r9, [rsp+6F0h+lpMem]
0x180013787  xor     edx, edx
0x180013789  lea     r8, [rsp+6F0h+var_680]
0x18001378e  mov     rcx, rsi
0x180013791  call    DhcpEnumIPv4Address
0x180013796  mov     ebx, eax
0x180013798  test    eax, eax
0x18001379a  jnz     short loc_1800137D5
0x18001379c  movzx   ebx, [rbp+5F0h+var_9C]
0x1800137a3  mov     edx, 0FFFFFFF8h
0x1800137a8  mov     r14d, [rsp+6F0h+var_680]
0x1800137ad  lea     r15d, [rbx+7]
0x1800137b1  lea     ecx, ds:7[r14*4]
0x1800137b9  mov     eax, r15d
0x1800137bc  and     ecx, edx
0x1800137be  and     eax, edx
0x1800137c0  add     ecx, 60h ; '`'
0x1800137c3  add     ecx, eax
0x1800137c5  call    DhcpAlloc
0x1800137ca  mov     rdi, rax
0x1800137cd  test    rax, rax
0x1800137d0  jnz     short loc_1800137DF
0x1800137d2  lea     ebx, [rax+0Eh]
0x1800137d5  mov     r14, [rsp+6F0h+lpMem]
0x1800137da  jmp     loc_18001396E
0x1800137df  lea     rcx, [rax+60h]; void *
0x1800137e3  mov     r8, rbx; Size
0x1800137e6  mov     [rax+40h], rcx
0x1800137ea  lea     rdx, [rbp+5F0h+Src]; Src
0x1800137f1  mov     eax, r15d
0x1800137f4  lea     r15, [rdi+0Ch]
0x1800137f8  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800137fc  add     rax, 60h ; '`'
0x180013800  add     rax, rdi
0x180013803  mov     [rdi+50h], rax
0x180013807  mov     rax, [rsi]
0x18001380a  mov     [rdi], rax
0x18001380d  mov     eax, [rbp+5F0h+var_500]
0x180013813  mov     [rdi+8], eax
0x180013816  mov     eax, [rbp+5F0h+var_2C0]
0x18001381c  mov     [rdi+1Ch], eax
0x18001381f  mov     eax, [rbp+5F0h+var_2F4]
0x180013825  mov     [rdi+34h], eax
0x180013828  xor     eax, eax
0x18001382a  cmp     [rbp+5F0h+var_3C], 1
0x180013831  mov     [rdi+3Ch], bx
0x180013835  setz    al
0x180013838  mov     [rdi+38h], eax
0x18001383b  mov     rax, [rbp+5F0h+var_540]
0x180013842  mov     [rdi+58h], rax
0x180013846  movzx   eax, [rbp+5F0h+var_2F8]
0x18001384d  mov     [rdi+20h], ax
0x180013851  xor     eax, eax
0x180013853  cmp     [rbp+5F0h+var_2F0], eax
0x180013859  setnz   al
0x18001385c  mov     [rdi+24h], eax
0x18001385f  movups  xmm0, [rbp+5F0h+var_2E8]
0x180013866  movdqu  xmmword ptr [r15], xmm0
0x18001386b  mov     eax, [rbp+5F0h+var_2D0]
0x180013871  mov     [rdi+2Ch], eax
0x180013874  mov     eax, [rbp+5F0h+var_2CC]
0x18001387a  mov     [rdi+30h], eax
0x18001387d  call    memcpy_0
0x180013882  mov     rcx, [rdi+50h]; void *
0x180013886  mov     r8, r14
0x180013889  mov     [rdi+48h], r14d
0x18001388d  mov     r14, [rsp+6F0h+lpMem]
0x180013892  mov     rdx, r14; Src
0x180013895  shl     r8, 2; Size
0x180013899  call    memcpy_0
0x18001389e  movzx   r9d, word ptr [rdi+20h]
0x1800138a3  mov     ecx, r9d
0x1800138a6  sub     ecx, 1
0x1800138a9  jz      loc_18001393C
0x1800138af  sub     ecx, 5
0x1800138b2  jz      short loc_1800138E5
0x1800138b4  sub     ecx, 3
0x1800138b7  jz      short loc_180013936
0x1800138b9  sub     ecx, 6
0x1800138bc  jz      short loc_180013936
0x1800138be  sub     ecx, 8
0x1800138c1  jz      short loc_180013930
0x1800138c3  sub     ecx, 1
0x1800138c6  jz      short loc_1800138F1
0x1800138c8  sub     ecx, 2Fh ; '/'
0x1800138cb  jz      short loc_1800138E5
0x1800138cd  cmp     ecx, 49h ; 'I'
0x1800138d0  jz      short loc_1800138EB
0x1800138d2  test    byte ptr cs:xmmword_1800616A0, 2
0x1800138d9  jz      short loc_1800138E5
0x1800138db  mov     [rsp+6F0h+var_6C8], r15
0x1800138e0  call    WPP_SF_ll_guid_
0x1800138e5  mov     byte ptr [rdi+28h], 1
0x1800138e9  jmp     short loc_180013940
0x1800138eb  mov     byte ptr [rdi+28h], 18h
0x1800138ef  jmp     short loc_180013940
0x1800138f1  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800138f8  jz      short loc_180013913
0x1800138fa  mov     r9, [rsi]
0x1800138fd  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x180013904  mov     edx, 28h ; '('
0x180013909  mov     ecx, 404h
0x18001390e  call    WPP_SF_q
0x180013913  mov     rcx, gs:60h
0x18001391c  mov     r8, rdi; lpMem
0x18001391f  xor     edx, edx; dwFlags
0x180013921  mov     rcx, [rcx+30h]; hHeap
0x180013925  call    cs:__imp_HeapFree
0x18001392b  or      ebx, 0FFFFFFFFh
0x18001392e  jmp     short loc_18001396E
0x180013930  mov     byte ptr [rdi+28h], 8
0x180013934  jmp     short loc_180013940
0x180013936  mov     byte ptr [rdi+28h], 6
0x18001393a  jmp     short loc_180013940
0x18001393c  mov     byte ptr [rdi+28h], 7
0x180013940  xor     ebx, ebx
0x180013942  mov     [r12], rdi
0x180013946  jmp     short loc_18001396E
0x180013948  test    byte ptr cs:xmmword_1800616A0, 2
0x18001394f  jz      short loc_18001398B
0x180013951  mov     edx, 27h ; '''
0x180013956  mov     dword ptr [rsp+6F0h+var_6D0], ebx
0x18001395a  mov     ecx, 401h
0x18001395f  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x180013966  mov     r9d, ebx
0x180013969  call    WPP_SF_Dd
0x18001396e  test    r14, r14
0x180013971  jz      short loc_18001398B
0x180013973  mov     rcx, gs:60h
0x18001397c  mov     r8, r14; lpMem
0x18001397f  xor     edx, edx; dwFlags
0x180013981  mov     rcx, [rcx+30h]; hHeap
0x180013985  call    cs:__imp_HeapFree
0x18001398b  test    byte ptr cs:xmmword_1800616A0, 10h
0x180013992  jz      short loc_1800139B1
0x180013994  mov     r9, [rsi]
0x180013997  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x18001399e  mov     edx, 2Ah ; '*'
0x1800139a3  mov     dword ptr [rsp+6F0h+var_6D0], ebx
0x1800139a7  mov     ecx, 404h
0x1800139ac  call    WPP_SF_qD
0x1800139b1  mov     eax, ebx
0x1800139b3  mov     rcx, [rbp+5F0h+var_30]
0x1800139ba  xor     rcx, rsp; StackCookie
0x1800139bd  call    __security_check_cookie
0x1800139c2  lea     r11, [rsp+6F0h+var_20]
0x1800139ca  mov     rbx, [r11+40h]
0x1800139ce  mov     rsi, [r11+48h]
0x1800139d2  mov     rsp, r11
0x1800139d5  pop     r15
0x1800139d7  pop     r14
0x1800139d9  pop     r12
0x1800139db  pop     rdi
0x1800139dc  pop     rbp
0x1800139dd  retn
```
