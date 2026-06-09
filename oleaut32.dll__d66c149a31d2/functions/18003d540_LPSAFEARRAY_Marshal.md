# LPSAFEARRAY_Marshal

- ea: `0x18003d540`
- end: `0x18003d994`
- name: `LPSAFEARRAY_Marshal`
- size: `1108`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003d530`
- `0x180045970`

## callees

- `0x18001c6e0`
- `0x18001f440`
- `0x18002fa80`
- `0x18003d540`
- `0x1800419c0`
- `0x180042870`
- `0x180044ddc`
- `0x180044fb0`
- `0x180045970`
- `0x18004d900`
- `0x1800716f0`
- `0x18009a624`
- `0x18009c010`

## import_xrefs

- `combase!WdtpInterfacePointer_UserMarshal` at `0x18003d8c9`
- `combase!WdtpInterfacePointer_UserMarshal` at `0x18003d8c9`
- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x18003d5b6`
- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x18003d5b6`
- `RPCRT4!RpcRaiseException` at `0x18003d6a6`
- `RPCRT4!RpcRaiseException` at `0x18003d733`
- `RPCRT4!RpcRaiseException` at `0x18003d7a1`
- `RPCRT4!RpcRaiseException` at `0x18003d7bf`
- `RPCRT4!RpcRaiseException` at `0x18003d6a6`
- `RPCRT4!RpcRaiseException` at `0x18003d733`
- `RPCRT4!RpcRaiseException` at `0x18003d7a1`
- `RPCRT4!RpcRaiseException` at `0x18003d7bf`

## pseudocode

```c
unsigned __int8 *__fastcall LPSAFEARRAY_Marshal(
        unsigned int *a1,
        unsigned __int8 *a2,
        unsigned __int16 **a3,
        GUID *p_pguid)
{
  unsigned __int8 *v8; // rbx
  unsigned __int16 *v9; // rsi
  int DoesOtherSideSupportUDTMarshaling; // edx
  int v11; // edi
  unsigned __int16 v12; // ax
  int SafeArrayDiscr; // r14d
  int v14; // eax
  int v15; // r8d
  __int64 v16; // rcx
  int v17; // r12d
  GUID *Data4; // rbx
  RPC_STATUS IID; // eax
  GUID *v20; // r8
  GUID *v21; // rdi
  __int64 v22; // rdx
  unsigned __int8 *p_Data2; // rdi
  unsigned __int8 *v24; // r15
  int v25; // ebx
  int v26; // r14d
  int v27; // r14d
  int v28; // r14d
  int v29; // r14d
  RPC_STATUS RecordInfo; // eax
  void *v31; // rbx
  VARIANT *v32; // r14
  unsigned int *v33; // r13
  GUID *v34; // rax
  GUID *v35; // r14
  _QWORD *v36; // r13
  __int64 v37; // rcx
  char *v38; // r14
  unsigned int *v39; // r13
  BSTR *v40; // r8
  BSTR v41; // rcx
  unsigned int v42; // r12d
  unsigned __int8 *v43; // [rsp+30h] [rbp-88h] BYREF
  void *ppvData; // [rsp+38h] [rbp-80h] BYREF
  int v45; // [rsp+40h] [rbp-78h]
  unsigned int *v46; // [rsp+48h] [rbp-70h]
  int v47; // [rsp+50h] [rbp-68h]
  unsigned __int8 *v48; // [rsp+58h] [rbp-60h]
  unsigned __int16 *v49; // [rsp+60h] [rbp-58h]
  GUID pguid; // [rsp+68h] [rbp-50h] BYREF

  v46 = a1;
  v43 = a2;
  if ( !a3 )
    return a2;
  AlignAndZeroGap(&v43, 3u);
  v8 = v43;
  *(_DWORD *)v43 = *a3 != 0;
  v9 = *a3;
  if ( !v9 )
    return v8 + 4;
  v49 = v9;
  DoesOtherSideSupportUDTMarshaling = CoDoesOtherSideSupportUDTMarshaling(a1);
  v11 = (unsigned __int16)*((_DWORD *)v9 + 2);
  if ( DoesOtherSideSupportUDTMarshaling && *((char *)v9 + 2) < 0 )
    v11 |= *((_DWORD *)v9 - 1) << 16;
  *((_DWORD *)v8 + 1) = *v9;
  *((_WORD *)v8 + 4) = *v9;
  v12 = v9[1];
  if ( !DoesOtherSideSupportUDTMarshaling )
    v12 &= 0xFF3Fu;
  *((_WORD *)v8 + 5) = v12;
  SafeArrayDiscr = GetSafeArrayDiscr((struct tagSAFEARRAY *)v9, a1);
  if ( SafeArrayDiscr != 8 && SafeArrayDiscr != 9 )
  {
    if ( SafeArrayDiscr == 12 )
    {
      v14 = 16;
      goto LABEL_18;
    }
    if ( SafeArrayDiscr != 13 && SafeArrayDiscr != 32781 )
    {
      v14 = *((_DWORD *)v9 + 1);
      goto LABEL_18;
    }
  }
  v14 = 4;
LABEL_18:
  *((_DWORD *)v8 + 3) = v14;
  *((_DWORD *)v8 + 4) = v11;
  *((_DWORD *)v8 + 5) = SafeArrayDiscr;
  v15 = 1;
  v16 = 0;
  if ( *v9 )
  {
    do
    {
      v15 *= *(_DWORD *)&v9[4 * v16 + 12];
      v16 = (unsigned int)(v16 + 1);
    }
    while ( (int)v16 < *v9 );
  }
  v17 = v15;
  if ( SafeArrayDiscr == 36 )
    v17 = 1;
  else
    v15 = 0;
  v47 = v15;
  *((_DWORD *)v8 + 6) = v17;
  *((_DWORD *)v8 + 7) = *((_DWORD *)v9 + 4);
  Data4 = (GUID *)(v8 + 32);
  pguid = 0;
  if ( SafeArrayDiscr == 32781 )
  {
    IID = SafeArrayGetIID((SAFEARRAY *)v9, &pguid);
    if ( IID < 0 )
      RpcRaiseException(IID);
    *Data4++ = pguid;
    p_pguid = &pguid;
    SafeArrayDiscr = 13;
  }
  v20 = Data4;
  v21 = Data4;
  v22 = (unsigned int)*v9 - 1;
  if ( (int)v22 >= 0 )
  {
    do
    {
      Data4->Data1 = *(_DWORD *)&v9[4 * v22 + 12];
      *(_DWORD *)&v20->Data2 = *(_DWORD *)&v9[4 * v22 + 14];
      Data4 = (GUID *)v20->Data4;
      v22 = (unsigned int)(v22 - 1);
      v20 = (GUID *)((char *)v20 + 8);
    }
    while ( (int)v22 >= 0 );
    v21 = Data4;
  }
  Data4->Data1 = v17;
  p_Data2 = (unsigned __int8 *)&v21->Data2;
  v43 = p_Data2;
  ppvData = 0;
  if ( SafeArrayAccessData((SAFEARRAY *)v9, &ppvData) )
    RpcRaiseException(-2147418113);
  if ( SafeArrayDiscr != 2 && SafeArrayDiscr != 3 && SafeArrayDiscr != 16 )
  {
    if ( SafeArrayDiscr != 20 )
    {
      v24 = &p_Data2[4 * v17];
      v25 = 0;
      v45 = 0;
      v26 = SafeArrayDiscr - 8;
      if ( !v26 )
      {
        v38 = (char *)ppvData;
        v39 = v46;
        while ( v25 < v17 )
        {
          v40 = (BSTR *)&v38[8 * v25];
          v41 = *v40;
          *(_DWORD *)p_Data2 = *v40 != 0;
          p_Data2 += 4;
          v43 = p_Data2;
          if ( v41 )
          {
            v24 = BSTR_UserMarshal(v39, v24, v40);
            v48 = v24;
          }
          v45 = ++v25;
        }
        goto LABEL_64;
      }
      v27 = v26 - 1;
      if ( v27 )
      {
        v28 = v27 - 3;
        if ( !v28 )
        {
          v32 = (VARIANT *)ppvData;
          v33 = v46;
          while ( v25 < v17 )
          {
            *(_DWORD *)p_Data2 = 1919251285;
            p_Data2 += 4;
            v43 = p_Data2;
            v24 = VARIANT_UserMarshal(v33, v24, &v32[v25]);
            v48 = v24;
            v45 = ++v25;
          }
LABEL_64:
          v43 = v24;
          SafeArrayUnaccessData((SAFEARRAY *)v9);
          return v24;
        }
        v29 = v28 - 1;
        if ( v29 )
        {
          if ( v29 != 23 )
            RpcRaiseException(-2147024809);
          ppvData = 0;
          RecordInfo = SafeArrayGetRecordInfo((SAFEARRAY *)v9, (IRecordInfo **)&ppvData);
          if ( RecordInfo < 0 )
            RpcRaiseException(RecordInfo);
          *(_DWORD *)p_Data2 = 1919251285;
          v43 = p_Data2 + 4;
          v31 = ppvData;
          v24 = (unsigned __int8 *)BRECORD_UserMarshal(
                                     (_DWORD)v46,
                                     (int)p_Data2 + 4 * v17,
                                     v47,
                                     (_DWORD)ppvData,
                                     *((_QWORD *)v9 + 2));
          v48 = v24;
          if ( v31 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
          goto LABEL_64;
        }
      }
      else
      {
        v34 = &IID_IDispatch;
        if ( p_pguid )
          v34 = p_pguid;
        p_pguid = v34;
      }
      v35 = &IID_IUnknown;
      if ( p_pguid )
        v35 = p_pguid;
      v36 = ppvData;
      while ( v25 < v17 )
      {
        v37 = v36[v25];
        *(_DWORD *)p_Data2 = v37 != 0;
        p_Data2 += 4;
        v43 = p_Data2;
        if ( v37 )
        {
          v24 = (unsigned __int8 *)WdtpInterfacePointer_UserMarshal(v46, *v46, v24, v36[v25], v35);
          v48 = v24;
        }
        v45 = ++v25;
      }
      goto LABEL_64;
    }
    AlignAndZeroGap(&v43, 7u);
    p_Data2 = v43;
  }
  v42 = *((_DWORD *)v9 + 1) * v17;
  memcpy_0(p_Data2, ppvData, v42);
  SafeArrayUnaccessData((SAFEARRAY *)v9);
  return &p_Data2[v42];
}

```

## disassembly

```asm
0x18003d540  push    rbx
0x18003d542  push    rsi
0x18003d543  push    rdi
0x18003d544  push    r12
0x18003d546  push    r13
0x18003d548  push    r14
0x18003d54a  push    r15
0x18003d54c  sub     rsp, 80h
0x18003d553  mov     rax, cs:__security_cookie
0x18003d55a  xor     rax, rsp
0x18003d55d  mov     [rsp+0B8h+var_40], rax
0x18003d562  mov     r13, r9
0x18003d565  mov     rsi, r8
0x18003d568  mov     r14, rcx
0x18003d56b  mov     [rsp+0B8h+var_70], rcx
0x18003d570  mov     [rsp+0B8h+var_88], rdx
0x18003d575  test    r8, r8
0x18003d578  jnz     short loc_18003D582
0x18003d57a  mov     rax, rdx
0x18003d57d  jmp     loc_18003D974
0x18003d582  mov     dl, 3; unsigned __int8
0x18003d584  lea     rcx, [rsp+0B8h+var_88]; unsigned __int8 **
0x18003d589  call    ?AlignAndZeroGap@@YAXAEAPEAEE@Z; AlignAndZeroGap(uchar * &,uchar)
0x18003d58e  xor     ecx, ecx
0x18003d590  cmp     [rsi], rcx
0x18003d593  setnz   cl
0x18003d596  mov     rbx, [rsp+0B8h+var_88]
0x18003d59b  mov     [rbx], ecx
0x18003d59d  mov     rsi, [rsi]
0x18003d5a0  test    rsi, rsi
0x18003d5a3  jnz     short loc_18003D5AE
0x18003d5a5  lea     rax, [rbx+4]
0x18003d5a9  jmp     loc_18003D974
0x18003d5ae  mov     [rsp+0B8h+var_58], rsi
0x18003d5b3  mov     rcx, r14
0x18003d5b6  call    cs:__imp_CoDoesOtherSideSupportUDTMarshaling
0x18003d5bc  mov     edx, eax
0x18003d5be  mov     edi, [rsi+8]
0x18003d5c1  movzx   edi, di
0x18003d5c4  test    eax, eax
0x18003d5c6  jz      short loc_18003D5D6
0x18003d5c8  test    byte ptr [rsi+2], 80h
0x18003d5cc  jz      short loc_18003D5D6
0x18003d5ce  mov     ecx, [rsi-4]
0x18003d5d1  shl     ecx, 10h
0x18003d5d4  or      edi, ecx
0x18003d5d6  movzx   eax, word ptr [rsi]
0x18003d5d9  mov     [rbx+4], eax
0x18003d5dc  movzx   eax, word ptr [rsi]
0x18003d5df  mov     [rbx+8], ax
0x18003d5e3  movzx   eax, word ptr [rsi+2]
0x18003d5e7  test    edx, edx
0x18003d5e9  jnz     short loc_18003D5F3
0x18003d5eb  mov     ecx, 0FF3Fh
0x18003d5f0  and     ax, cx
0x18003d5f3  mov     [rbx+0Ah], ax
0x18003d5f7  mov     rdx, r14; unsigned int *
0x18003d5fa  mov     rcx, rsi; struct tagSAFEARRAY *
0x18003d5fd  call    ?GetSafeArrayDiscr@@YA?AW4tagSF_TYPE@@PEAUtagSAFEARRAY@@PEAK@Z; GetSafeArrayDiscr(tagSAFEARRAY *,ulong *)
0x18003d602  mov     r14d, eax
0x18003d605  sub     eax, 8
0x18003d608  jz      short loc_18003D62C
0x18003d60a  sub     eax, 1
0x18003d60d  jz      short loc_18003D62C
0x18003d60f  sub     eax, 3
0x18003d612  jz      short loc_18003D625
0x18003d614  sub     eax, 1
0x18003d617  jz      short loc_18003D62C
0x18003d619  cmp     eax, 8000h
0x18003d61e  jz      short loc_18003D62C
0x18003d620  mov     eax, [rsi+4]
0x18003d623  jmp     short loc_18003D631
0x18003d625  mov     eax, 10h
0x18003d62a  jmp     short loc_18003D631
0x18003d62c  mov     eax, 4
0x18003d631  mov     [rbx+0Ch], eax
0x18003d634  mov     [rbx+10h], edi
0x18003d637  mov     [rbx+14h], r14d
0x18003d63b  mov     r15d, 1
0x18003d641  mov     r8d, r15d
0x18003d644  movzx   edx, word ptr [rsi]
0x18003d647  xor     ecx, ecx
0x18003d649  test    edx, edx
0x18003d64b  jz      short loc_18003D65A
0x18003d64d  imul    r8d, [rsi+rcx*8+18h]
0x18003d653  add     ecx, r15d
0x18003d656  cmp     ecx, edx
0x18003d658  jl      short loc_18003D64D
0x18003d65a  mov     r12d, r8d
0x18003d65d  cmp     r14d, 24h ; '$'
0x18003d661  cmovz   r12d, r15d
0x18003d665  xor     eax, eax
0x18003d667  cmp     r14d, 24h ; '$'
0x18003d66b  cmovnz  r8d, eax
0x18003d66f  mov     [rsp+0B8h+var_68], r8d
0x18003d674  mov     [rbx+18h], r12d
0x18003d678  mov     eax, [rsi+10h]
0x18003d67b  mov     [rbx+1Ch], eax
0x18003d67e  add     rbx, 20h ; ' '
0x18003d682  xorps   xmm0, xmm0
0x18003d685  movups  xmmword ptr [rsp+0B8h+pguid.Data1], xmm0
0x18003d68a  cmp     r14d, 800Dh
0x18003d691  jnz     short loc_18003D6DD
0x18003d693  lea     rdx, [rsp+0B8h+pguid]; pguid
0x18003d698  mov     rcx, rsi; psa
0x18003d69b  call    SafeArrayGetIID
0x18003d6a0  test    eax, eax
0x18003d6a2  jns     short loc_18003D6AD
0x18003d6a4  mov     ecx, eax; exception
0x18003d6a6  call    cs:__imp_RpcRaiseException
0x18003d6ac  int     3; Trap to Debugger
0x18003d6ad  mov     eax, [rsp+0B8h+pguid.Data1]
0x18003d6b1  mov     [rbx], eax
0x18003d6b3  movzx   eax, [rsp+0B8h+pguid.Data2]
0x18003d6b8  mov     [rbx+4], ax
0x18003d6bc  movzx   eax, [rsp+0B8h+pguid.Data3]
0x18003d6c1  mov     [rbx+6], ax
0x18003d6c5  mov     rax, qword ptr [rsp+0B8h+pguid.Data4]
0x18003d6ca  mov     [rbx+8], rax
0x18003d6ce  add     rbx, 10h
0x18003d6d2  lea     r13, [rsp+0B8h+pguid]
0x18003d6d7  mov     r14d, 0Dh
0x18003d6dd  mov     r8, rbx
0x18003d6e0  mov     rdi, rbx
0x18003d6e3  movzx   edx, word ptr [rsi]
0x18003d6e6  sub     edx, r15d
0x18003d6e9  js      short loc_18003D708
0x18003d6eb  mov     eax, [rsi+rdx*8+18h]
0x18003d6ef  mov     [rbx], eax
0x18003d6f1  mov     eax, [rsi+rdx*8+1Ch]
0x18003d6f5  mov     [r8+4], eax
0x18003d6f9  lea     rbx, [r8+8]
0x18003d6fd  sub     edx, r15d
0x18003d700  mov     r8, rbx
0x18003d703  jns     short loc_18003D6EB
0x18003d705  mov     rdi, rbx
0x18003d708  mov     [rbx], r12d
0x18003d70b  add     rdi, 4
0x18003d70f  mov     [rsp+0B8h+var_88], rdi
0x18003d714  mov     [rsp+0B8h+ppvData], 0
0x18003d71d  lea     rdx, [rsp+0B8h+ppvData]; ppvData
0x18003d722  mov     rcx, rsi; psa
0x18003d725  call    SafeArrayAccessData
0x18003d72a  test    eax, eax
0x18003d72c  jz      short loc_18003D73A
0x18003d72e  mov     ecx, 8000FFFFh; exception
0x18003d733  call    cs:__imp_RpcRaiseException
0x18003d739  int     3; Trap to Debugger
0x18003d73a  mov     ecx, r14d
0x18003d73d  sub     ecx, 2
0x18003d740  jz      loc_18003D94E
0x18003d746  sub     ecx, r15d
0x18003d749  jz      loc_18003D94E
0x18003d74f  sub     ecx, 0Dh
0x18003d752  jz      loc_18003D94E
0x18003d758  cmp     ecx, 4
0x18003d75b  jz      loc_18003D93D
0x18003d761  movsxd  rax, r12d
0x18003d764  lea     r15, [rdi+rax*4]
0x18003d768  xor     ebx, ebx
0x18003d76a  mov     [rsp+0B8h+var_78], ebx
0x18003d76e  sub     r14d, 8
0x18003d772  jz      loc_18003D8DF
0x18003d778  sub     r14d, 1
0x18003d77c  jz      loc_18003D865
0x18003d782  sub     r14d, 3
0x18003d786  jz      loc_18003D81D
0x18003d78c  sub     r14d, 1
0x18003d790  jz      loc_18003D876
0x18003d796  cmp     r14d, 17h
0x18003d79a  jz      short loc_18003D7A7
0x18003d79c  mov     ecx, 80070057h; exception
0x18003d7a1  call    cs:__imp_RpcRaiseException
0x18003d7a7  mov     [rsp+0B8h+ppvData], rbx
0x18003d7ac  lea     rdx, [rsp+0B8h+ppvData]; prinfo
0x18003d7b1  mov     rcx, rsi; psa
0x18003d7b4  call    SafeArrayGetRecordInfo
0x18003d7b9  test    eax, eax
0x18003d7bb  jns     short loc_18003D7C6
0x18003d7bd  mov     ecx, eax; exception
0x18003d7bf  call    cs:__imp_RpcRaiseException
0x18003d7c5  nop
0x18003d7c6  mov     dword ptr [rdi], 72657355h
0x18003d7cc  lea     rax, [rdi+4]
0x18003d7d0  mov     [rsp+0B8h+var_88], rax
0x18003d7d5  mov     rax, [rsi+10h]
0x18003d7d9  mov     [rsp+0B8h+var_98], rax
0x18003d7de  mov     rbx, [rsp+0B8h+ppvData]
0x18003d7e3  mov     r9, rbx
0x18003d7e6  mov     r8d, [rsp+0B8h+var_68]
0x18003d7eb  mov     rdx, r15
0x18003d7ee  mov     rcx, [rsp+0B8h+var_70]
0x18003d7f3  call    BRECORD_UserMarshal
0x18003d7f8  mov     r15, rax
0x18003d7fb  mov     [rsp+0B8h+var_60], rax
0x18003d800  test    rbx, rbx
0x18003d803  jz      loc_18003D92B
0x18003d809  mov     rax, [rbx]
0x18003d80c  mov     rcx, rbx
0x18003d80f  mov     rax, [rax+10h]
0x18003d813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d818  jmp     loc_18003D92B
0x18003d81d  mov     r14, [rsp+0B8h+ppvData]
0x18003d822  mov     r13, [rsp+0B8h+var_70]
0x18003d827  cmp     ebx, r12d
0x18003d82a  jge     loc_18003D92B
0x18003d830  mov     dword ptr [rdi], 72657355h
0x18003d836  add     rdi, 4
0x18003d83a  mov     [rsp+0B8h+var_88], rdi
0x18003d83f  movsxd  rax, ebx
0x18003d842  lea     rcx, [rax+rax*2]
0x18003d846  lea     r8, [r14+rcx*8]; VARIANT *
0x18003d84a  mov     rdx, r15; unsigned __int8 *
0x18003d84d  mov     rcx, r13; unsigned int *
0x18003d850  call    VARIANT_UserMarshal
0x18003d855  mov     r15, rax
0x18003d858  mov     [rsp+0B8h+var_60], rax
0x18003d85d  inc     ebx
0x18003d85f  mov     [rsp+0B8h+var_78], ebx
0x18003d863  jmp     short loc_18003D827
0x18003d865  lea     rax, IID_IDispatch
0x18003d86c  test    r13, r13
0x18003d86f  cmovnz  rax, r13
0x18003d873  mov     r13, rax
0x18003d876  lea     r14, IID_IUnknown
0x18003d87d  test    r13, r13
0x18003d880  cmovnz  r14, r13
0x18003d884  mov     r13, [rsp+0B8h+ppvData]
0x18003d889  cmp     ebx, r12d
0x18003d88c  jge     loc_18003D92B
0x18003d892  movsxd  r9, ebx
0x18003d895  mov     rcx, [r13+r9*8+0]
0x18003d89a  xor     eax, eax
0x18003d89c  test    rcx, rcx
0x18003d89f  setnz   al
0x18003d8a2  mov     [rdi], eax
0x18003d8a4  add     rdi, 4
0x18003d8a8  mov     [rsp+0B8h+var_88], rdi
0x18003d8ad  test    rcx, rcx
0x18003d8b0  jz      short loc_18003D8D7
0x18003d8b2  mov     [rsp+0B8h+var_98], r14
0x18003d8b7  mov     r9, [r13+r9*8+0]
0x18003d8bc  mov     r8, r15
0x18003d8bf  mov     rax, [rsp+0B8h+var_70]
0x18003d8c4  mov     edx, [rax]
0x18003d8c6  mov     rcx, rax
0x18003d8c9  call    cs:__imp_WdtpInterfacePointer_UserMarshal
0x18003d8cf  mov     r15, rax
0x18003d8d2  mov     [rsp+0B8h+var_60], rax
0x18003d8d7  inc     ebx
0x18003d8d9  mov     [rsp+0B8h+var_78], ebx
0x18003d8dd  jmp     short loc_18003D889
0x18003d8df  mov     r14, [rsp+0B8h+ppvData]
0x18003d8e4  mov     r13, [rsp+0B8h+var_70]
0x18003d8e9  cmp     ebx, r12d
0x18003d8ec  jge     short loc_18003D92B
0x18003d8ee  movsxd  rax, ebx
0x18003d8f1  lea     r8, [r14+rax*8]; BSTR *
0x18003d8f5  mov     rcx, [r8]
0x18003d8f8  xor     eax, eax
0x18003d8fa  test    rcx, rcx
0x18003d8fd  setnz   al
0x18003d900  mov     [rdi], eax
0x18003d902  add     rdi, 4
0x18003d906  mov     [rsp+0B8h+var_88], rdi
0x18003d90b  test    rcx, rcx
0x18003d90e  jz      short loc_18003D923
0x18003d910  mov     rdx, r15; unsigned __int8 *
0x18003d913  mov     rcx, r13; unsigned int *
0x18003d916  call    BSTR_UserMarshal
0x18003d91b  mov     r15, rax
0x18003d91e  mov     [rsp+0B8h+var_60], rax
0x18003d923  inc     ebx
0x18003d925  mov     [rsp+0B8h+var_78], ebx
0x18003d929  jmp     short loc_18003D8E9
0x18003d92b  mov     [rsp+0B8h+var_88], r15
0x18003d930  mov     rcx, rsi; psa
0x18003d933  call    SafeArrayUnaccessData
0x18003d938  mov     rax, r15
0x18003d93b  jmp     short loc_18003D974
0x18003d93d  mov     dl, 7; unsigned __int8
0x18003d93f  lea     rcx, [rsp+0B8h+var_88]; unsigned __int8 **
0x18003d944  call    ?AlignAndZeroGap@@YAXAEAPEAEE@Z; AlignAndZeroGap(uchar * &,uchar)
0x18003d949  mov     rdi, [rsp+0B8h+var_88]
0x18003d94e  imul    r12d, [rsi+4]
0x18003d953  mov     ebx, r12d
0x18003d956  mov     r8d, r12d; Size
0x18003d959  mov     rdx, [rsp+0B8h+ppvData]; Src
0x18003d95e  mov     rcx, rdi; void *
0x18003d961  call    memcpy_0
0x18003d966  add     rbx, rdi
0x18003d969  mov     rcx, rsi; psa
0x18003d96c  call    SafeArrayUnaccessData
0x18003d971  mov     rax, rbx
0x18003d974  mov     rcx, [rsp+0B8h+var_40]
0x18003d979  xor     rcx, rsp; StackCookie
0x18003d97c  call    __security_check_cookie
0x18003d981  add     rsp, 80h
0x18003d988  pop     r15
0x18003d98a  pop     r14
  ... truncated ...
```
