# DdmSstpDevice::ValidateAuthInfo(DdmDevice *,ulong,uchar *)

- ea: `0x18004b5a4`
- end: `0x18004ba1e`
- name: `?ValidateAuthInfo@DdmSstpDevice@@AEAAKPEAVDdmDevice@@KPEAE@Z`
- size: `1146`
- prototype: `unsigned int __fastcall(DdmSstpDevice *__hidden this, struct DdmDevice *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004af30`

## callees

- `0x18000108c`
- `0x180002ba6`
- `0x180007b7c`
- `0x18004b5a4`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18004b720`
- `KERNEL32!HeapAlloc` at `0x18004b720`
- `KERNEL32!HeapFree` at `0x18004b8fa`
- `KERNEL32!HeapFree` at `0x18004b922`
- `KERNEL32!HeapFree` at `0x18004b8fa`
- `KERNEL32!HeapFree` at `0x18004b922`

## string_xrefs

- `0x18004b628`: `ValidateAuthInfo : Admin Dll callback  is configured`
- `0x18004b673`: `ValidateAuthInfo : Skipping version 1 Admin Dll callback `

## pseudocode

```c
_BOOL8 __fastcall DdmSstpDevice::ValidateAuthInfo(
        DdmSstpDevice *this,
        struct DdmDevice *a2,
        __int64 a3,
        unsigned __int8 *a4)
{
  unsigned int v4; // r14d
  bool v6; // bl
  unsigned int v7; // r13d
  _BYTE *v8; // r12
  __int64 v9; // r15
  unsigned __int16 v10; // r14
  char *v11; // rax
  __int64 v12; // r8
  char *v13; // rsi
  const void *v14; // rdx
  int v15; // eax
  __int64 v16; // r8
  int v17; // ecx
  _OWORD *v18; // rax
  __int64 v19; // rdx
  _OWORD *v20; // rcx
  __int128 v21; // xmm1
  int v23; // [rsp+30h] [rbp-50h] BYREF
  _DWORD Size[3]; // [rsp+34h] [rbp-4Ch]
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+40h] [rbp-40h] BYREF
  const wchar_t *v26; // [rsp+50h] [rbp-30h]
  __int64 v27; // [rsp+58h] [rbp-28h]
  int *v28; // [rsp+60h] [rbp-20h]
  __int64 v29; // [rsp+68h] [rbp-18h]

  *((_DWORD *)a2 + 33) &= ~0x20000u;
  LOWORD(v4) = a3;
  *(_QWORD *)&Size[1] = a4;
  Size[0] = a3;
  if ( !a4 || !(_DWORD)a3 )
    return 0;
  v6 = 0;
  v7 = 0;
  if ( !dword_1800C8568 )
  {
LABEL_26:
    HeapFree(hHeap, 0, *(LPVOID *)&Size[1]);
    return v6;
  }
  while ( 1 )
  {
    v8 = qword_1800C8560;
    v9 = 168LL * v7;
    LOBYTE(v23) = byte_1800C8404 & 0x10;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v27 = 106;
      v26 = L"ValidateAuthInfo : Admin Dll callback  is configured";
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
        a3,
        2u,
        &v25);
    }
    if ( v8[v9 + 8] == 1 )
    {
      LOBYTE(v23) = byte_1800C8404 & 0x10;
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v27 = 116;
        v26 = L"ValidateAuthInfo : Skipping version 1 Admin Dll callback ";
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
          a3,
          2u,
          &v25);
      }
      goto LABEL_25;
    }
    if ( *(_QWORD *)&v8[v9 + 160] )
      break;
LABEL_25:
    if ( ++v7 >= dword_1800C8568 )
      goto LABEL_26;
  }
  LOBYTE(v23) = byte_1800C8404 & 0x10;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v27 = 150;
    v26 = L"ValidateAuthInfo : lpfnRASValidatePreAuthenticatedConnectionEx  is present";
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
      a3,
      2u,
      &v25);
  }
  v10 = v4 + 575;
  if ( v10 >= 0x240u )
  {
    v11 = (char *)HeapAlloc(hHeap, 8u, v10);
    v13 = v11;
    if ( !v11 )
    {
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v27 = 134;
        v26 = L"ValidateAuthInfo : unable to allocate memory for AuthValidationEx ";
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
          v12,
          2u,
          &v25);
      }
      return v6;
    }
    memset_0(v11, 0, v10);
    v14 = *(const void **)&Size[1];
    *((_WORD *)v13 + 1) = v10;
    v4 = Size[0];
    *(_WORD *)v13 = 1025;
    *((_QWORD *)v13 + 1) = *((_QWORD *)a2 + 15);
    *((_DWORD *)v13 + 141) = v4;
    memcpy_0(v13 + 568, v14, v4);
    v15 = (*(__int64 (__fastcall **)(char *))&v8[v9 + 160])(v13);
    v17 = *((_DWORD *)a2 + 33);
    v6 = v15 == 1;
    if ( v15 != 1 )
    {
      *((_DWORD *)a2 + 33) = v17 & 0xFFFDFFFF;
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v27 = 104;
        v26 = L"ValidateAuthInfo : clearing   DEV_OBJ_ALLOW_NO_AUTH";
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
          v16,
          2u,
          &v25);
      }
      goto LABEL_26;
    }
    v18 = v13 + 16;
    v19 = 4;
    *((_DWORD *)a2 + 33) = v17 | 0x20000;
    v20 = (_OWORD *)((char *)a2 + 168);
    do
    {
      *v20 = *v18;
      v20[1] = v18[1];
      v20[2] = v18[2];
      v20[3] = v18[3];
      v20[4] = v18[4];
      v20[5] = v18[5];
      v20[6] = v18[6];
      v21 = v18[7];
      v18 += 8;
      v20[7] = v21;
      v20 += 8;
      --v19;
    }
    while ( v19 );
    *(_WORD *)v20 = *(_WORD *)v18;
    *(_OWORD *)((char *)a2 + 682) = *(_OWORD *)(v13 + 530);
    *(_OWORD *)((char *)a2 + 698) = *(_OWORD *)(v13 + 546);
    *((_WORD *)a2 + 340) = 0;
    *((_WORD *)a2 + 356) = 0;
    LOBYTE(v23) = byte_1800C8404 & 0x10;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v27 = 106;
      v26 = L"ValidateAuthInfo :  setting   no auth in device obj ";
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
        128,
        2u,
        &v25);
    }
    if ( (*((_DWORD *)a2 + 33) & 0x20000) != 0
      && (unsigned int)dword_1800C7720 > 5
      && (qword_1800C7730 & 0x400000000000LL) != 0
      && (qword_1800C7738 & 0x400000000000LL) == qword_1800C7738 )
    {
      v23 = 1;
      v28 = &v23;
      v29 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_1800C7720, (unsigned __int8 *)byte_1800BD349, 0, 0, 3u, &v25);
    }
    HeapFree(hHeap, 0, v13);
    goto LABEL_25;
  }
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v27 = 46;
    v26 = L"AuthInfoSize too large";
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
      a3,
      2u,
      &v25);
  }
  return 0;
}

```

## disassembly

```asm
0x18004b5a4  mov     [rsp-38h+arg_0], rbx
0x18004b5a9  push    rbp
0x18004b5aa  push    rsi
0x18004b5ab  push    rdi
0x18004b5ac  push    r12
0x18004b5ae  push    r13
0x18004b5b0  push    r14
0x18004b5b2  push    r15
0x18004b5b4  mov     rbp, rsp
0x18004b5b7  sub     rsp, 80h
0x18004b5be  mov     rax, cs:__security_cookie
0x18004b5c5  xor     rax, rsp
0x18004b5c8  mov     [rbp+var_10], rax
0x18004b5cc  btr     dword ptr [rdx+84h], 11h
0x18004b5d4  mov     r14d, r8d
0x18004b5d7  mov     qword ptr [rbp+Size+4], r9
0x18004b5db  mov     rdi, rdx
0x18004b5de  mov     dword ptr [rbp+Size], r8d
0x18004b5e2  test    r9, r9
0x18004b5e5  jz      loc_18004B9F5
0x18004b5eb  test    r8d, r8d
0x18004b5ee  jz      loc_18004B9F5
0x18004b5f4  xor     bl, bl
0x18004b5f6  xor     r13d, r13d
0x18004b5f9  cmp     cs:dword_1800C8568, r13d
0x18004b600  jbe     loc_18004B915
0x18004b606  lea     esi, [r13+2]
0x18004b60a  mov     r12, cs:qword_1800C8560
0x18004b611  mov     eax, r13d
0x18004b614  imul    r15, rax, 0A8h
0x18004b61b  mov     al, cs:byte_1800C8404
0x18004b621  and     al, 10h
0x18004b623  mov     byte ptr [rbp+var_50], al
0x18004b626  jz      short loc_18004B65A
0x18004b628  lea     rax, aValidateauthin_2; "ValidateAuthInfo : Admin Dll callback  "...
0x18004b62f  mov     [rbp+var_28], 6Ah ; 'j'
0x18004b637  mov     [rbp+var_30], rax
0x18004b63b  lea     rdx, RasDdmTraceInfo
0x18004b642  lea     rax, [rbp+var_40]
0x18004b646  mov     r9d, esi
0x18004b649  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004b650  mov     [rsp+80h+var_60], rax
0x18004b655  call    McGenEventWrite_EventWriteTransfer
0x18004b65a  cmp     byte ptr [r15+r12+8], 1
0x18004b660  jnz     short loc_18004B6AA
0x18004b662  mov     al, cs:byte_1800C8404
0x18004b668  and     al, 10h
0x18004b66a  mov     byte ptr [rbp+var_50], al
0x18004b66d  jz      loc_18004B905
0x18004b673  lea     rax, aValidateauthin_4; "ValidateAuthInfo : Skipping version 1 A"...
0x18004b67a  mov     [rbp+var_28], 74h ; 't'
0x18004b682  mov     [rbp+var_30], rax
0x18004b686  lea     rdx, RasDdmTraceInfo
0x18004b68d  lea     rax, [rbp+var_40]
0x18004b691  mov     r9d, esi
0x18004b694  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004b69b  mov     [rsp+80h+var_60], rax
0x18004b6a0  call    McGenEventWrite_EventWriteTransfer
0x18004b6a5  jmp     loc_18004B905
0x18004b6aa  cmp     qword ptr [r15+r12+0A0h], 0
0x18004b6b3  jz      loc_18004B905
0x18004b6b9  mov     al, cs:byte_1800C8404
0x18004b6bf  and     al, 10h
0x18004b6c1  mov     byte ptr [rbp+var_50], al
0x18004b6c4  jz      short loc_18004B6F8
0x18004b6c6  lea     rax, aValidateauthin_3; "ValidateAuthInfo : lpfnRASValidatePreAu"...
0x18004b6cd  mov     [rbp+var_28], 96h
0x18004b6d5  mov     [rbp+var_30], rax
0x18004b6d9  lea     rdx, RasDdmTraceInfo
0x18004b6e0  lea     rax, [rbp+var_40]
0x18004b6e4  mov     r9d, esi
0x18004b6e7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004b6ee  mov     [rsp+80h+var_60], rax
0x18004b6f3  call    McGenEventWrite_EventWriteTransfer
0x18004b6f8  mov     eax, 23Fh
0x18004b6fd  add     r14w, ax
0x18004b701  mov     eax, 240h
0x18004b706  cmp     r14w, ax
0x18004b70a  jb      loc_18004B9BA
0x18004b710  mov     rcx, cs:hHeap; hHeap
0x18004b717  mov     edx, 8; dwFlags
0x18004b71c  movzx   r8d, r14w; dwBytes
0x18004b720  call    cs:__imp_HeapAlloc
0x18004b726  mov     rsi, rax
0x18004b729  test    rax, rax
0x18004b72c  jz      loc_18004B977
0x18004b732  movzx   r8d, r14w; Size
0x18004b736  xor     edx, edx; Val
0x18004b738  mov     rcx, rax; void *
0x18004b73b  call    memset_0
0x18004b740  mov     rdx, qword ptr [rbp+Size+4]; Src
0x18004b744  mov     [rsi+2], r14w
0x18004b749  mov     r14d, dword ptr [rbp+Size]
0x18004b74d  mov     word ptr [rsi], 401h
0x18004b752  mov     r8d, r14d; Size
0x18004b755  mov     rcx, [rdi+78h]
0x18004b759  mov     [rsi+8], rcx
0x18004b75d  lea     rcx, [rsi+238h]; void *
0x18004b764  mov     [rsi+234h], r14d
0x18004b76b  call    memcpy_0
0x18004b770  mov     rax, [r15+r12+0A0h]
0x18004b778  mov     rcx, rsi
0x18004b77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b780  mov     ecx, [rdi+84h]
0x18004b786  cmp     eax, 1
0x18004b789  setz    bl
0x18004b78c  jnz     loc_18004B92D
0x18004b792  mov     r15d, 20000h
0x18004b798  lea     rax, [rsi+10h]
0x18004b79c  or      ecx, r15d
0x18004b79f  mov     edx, 4
0x18004b7a4  mov     [rdi+84h], ecx
0x18004b7aa  lea     rcx, [rdi+0A8h]
0x18004b7b1  lea     r8d, [rdx+7Ch]
0x18004b7b5  movups  xmm0, xmmword ptr [rax]
0x18004b7b8  movups  xmmword ptr [rcx], xmm0
0x18004b7bb  movups  xmm1, xmmword ptr [rax+10h]
0x18004b7bf  movups  xmmword ptr [rcx+10h], xmm1
0x18004b7c3  movups  xmm0, xmmword ptr [rax+20h]
0x18004b7c7  movups  xmmword ptr [rcx+20h], xmm0
0x18004b7cb  movups  xmm1, xmmword ptr [rax+30h]
0x18004b7cf  movups  xmmword ptr [rcx+30h], xmm1
0x18004b7d3  movups  xmm0, xmmword ptr [rax+40h]
0x18004b7d7  movups  xmmword ptr [rcx+40h], xmm0
0x18004b7db  movups  xmm1, xmmword ptr [rax+50h]
0x18004b7df  movups  xmmword ptr [rcx+50h], xmm1
0x18004b7e3  movups  xmm0, xmmword ptr [rax+60h]
0x18004b7e7  movups  xmmword ptr [rcx+60h], xmm0
0x18004b7eb  movups  xmm1, xmmword ptr [rax+70h]
0x18004b7ef  add     rax, r8
0x18004b7f2  movups  xmmword ptr [rcx+70h], xmm1
0x18004b7f6  add     rcx, r8
0x18004b7f9  sub     rdx, 1
0x18004b7fd  jnz     short loc_18004B7B5
0x18004b7ff  movzx   eax, word ptr [rax]
0x18004b802  mov     [rcx], ax
0x18004b805  xor     eax, eax
0x18004b807  movups  xmm0, xmmword ptr [rsi+212h]
0x18004b80e  movups  xmmword ptr [rdi+2AAh], xmm0
0x18004b815  movups  xmm1, xmmword ptr [rsi+222h]
0x18004b81c  movups  xmmword ptr [rdi+2BAh], xmm1
0x18004b823  mov     [rdi+2A8h], ax
0x18004b82a  mov     [rdi+2C8h], ax
0x18004b831  mov     al, cs:byte_1800C8404
0x18004b837  and     al, 10h
0x18004b839  mov     byte ptr [rbp+var_50], al
0x18004b83c  jz      short loc_18004B871
0x18004b83e  lea     rax, aValidateauthin_0; "ValidateAuthInfo :  setting   no auth i"...
0x18004b845  mov     [rbp+var_28], 6Ah ; 'j'
0x18004b84d  mov     [rbp+var_30], rax
0x18004b851  lea     r9d, [rdx+2]
0x18004b855  lea     rax, [rbp+var_40]
0x18004b859  lea     rdx, RasDdmTraceInfo
0x18004b860  mov     [rsp+80h+var_60], rax
0x18004b865  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004b86c  call    McGenEventWrite_EventWriteTransfer
0x18004b871  test    [rdi+84h], r15d
0x18004b878  jz      short loc_18004B8EE
0x18004b87a  mov     eax, cs:dword_1800C7720
0x18004b880  cmp     eax, 5
0x18004b883  jbe     short loc_18004B8EE
0x18004b885  mov     rcx, cs:qword_1800C7738
0x18004b88c  mov     rdx, 400000000000h
0x18004b896  mov     rax, cs:qword_1800C7730
0x18004b89d  test    rdx, rax
0x18004b8a0  jz      short loc_18004B8EE
0x18004b8a2  mov     rax, rcx
0x18004b8a5  and     rax, rdx
0x18004b8a8  cmp     rax, rcx
0x18004b8ab  jnz     short loc_18004B8EE
0x18004b8ad  lea     rax, [rbp+var_50]
0x18004b8b1  mov     [rbp+var_50], 1
0x18004b8b8  mov     [rbp+var_20], rax
0x18004b8bc  lea     rdx, byte_1800BD349
0x18004b8c3  lea     rax, [rbp+var_40]
0x18004b8c7  mov     [rbp+var_18], 4
0x18004b8cf  mov     [rsp+80h+var_58], rax
0x18004b8d4  lea     rcx, dword_1800C7720
0x18004b8db  xor     r9d, r9d
0x18004b8de  mov     dword ptr [rsp+80h+var_60], 3
0x18004b8e6  xor     r8d, r8d
0x18004b8e9  call    _tlgWriteTransfer_EventWriteTransfer
0x18004b8ee  mov     rcx, cs:hHeap; hHeap
0x18004b8f5  mov     r8, rsi; lpMem
0x18004b8f8  xor     edx, edx; dwFlags
0x18004b8fa  call    cs:__imp_HeapFree
0x18004b900  mov     esi, 2
0x18004b905  inc     r13d
0x18004b908  cmp     r13d, cs:dword_1800C8568
0x18004b90f  jb      loc_18004B60A
0x18004b915  mov     r8, qword ptr [rbp+Size+4]; lpMem
0x18004b919  xor     edx, edx; dwFlags
0x18004b91b  mov     rcx, cs:hHeap; hHeap
0x18004b922  call    cs:__imp_HeapFree
0x18004b928  jmp     loc_18004B9B5
0x18004b92d  btr     ecx, 11h
0x18004b931  mov     [rdi+84h], ecx
0x18004b937  test    cs:byte_1800C8404, 10h
0x18004b93e  jz      short loc_18004B915
0x18004b940  lea     rax, aValidateauthin; "ValidateAuthInfo : clearing   DEV_OBJ_A"...
0x18004b947  mov     [rbp+var_28], 68h ; 'h'
0x18004b94f  mov     [rbp+var_30], rax
0x18004b953  lea     rdx, RasDdmTraceInfo
0x18004b95a  lea     rax, [rbp+var_40]
0x18004b95e  mov     r9d, 2
0x18004b964  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004b96b  mov     [rsp+80h+var_60], rax
0x18004b970  call    McGenEventWrite_EventWriteTransfer
0x18004b975  jmp     short loc_18004B915
0x18004b977  test    cs:byte_1800C8404, 10h
0x18004b97e  jz      short loc_18004B9B5
0x18004b980  lea     rax, aValidateauthin_1; "ValidateAuthInfo : unable to allocate m"...
0x18004b987  mov     [rbp+var_28], 86h
0x18004b98f  mov     [rbp+var_30], rax
0x18004b993  lea     rdx, RasDdmTraceInfo
0x18004b99a  lea     rax, [rbp+var_40]
0x18004b99e  mov     r9d, 2
0x18004b9a4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004b9ab  mov     [rsp+80h+var_60], rax
0x18004b9b0  call    McGenEventWrite_EventWriteTransfer
0x18004b9b5  movzx   eax, bl
0x18004b9b8  jmp     short loc_18004B9F7
0x18004b9ba  test    cs:byte_1800C8404, 10h
0x18004b9c1  jz      short loc_18004B9F5
0x18004b9c3  lea     rax, aAuthinfosizeTo; "AuthInfoSize too large"
0x18004b9ca  mov     [rbp+var_28], 2Eh ; '.'
0x18004b9d2  mov     [rbp+var_30], rax
0x18004b9d6  lea     rdx, RasDdmTraceInfo
0x18004b9dd  lea     rax, [rbp+var_40]
0x18004b9e1  mov     r9d, esi
0x18004b9e4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004b9eb  mov     [rsp+80h+var_60], rax
0x18004b9f0  call    McGenEventWrite_EventWriteTransfer
0x18004b9f5  xor     eax, eax
0x18004b9f7  mov     rcx, [rbp+var_10]
0x18004b9fb  xor     rcx, rsp; StackCookie
0x18004b9fe  call    __security_check_cookie
0x18004ba03  mov     rbx, [rsp+80h+arg_0]
0x18004ba0b  add     rsp, 80h
0x18004ba12  pop     r15
0x18004ba14  pop     r14
0x18004ba16  pop     r13
0x18004ba18  pop     r12
0x18004ba1a  pop     rdi
0x18004ba1b  pop     rsi
0x18004ba1c  pop     rbp
0x18004ba1d  retn
```
