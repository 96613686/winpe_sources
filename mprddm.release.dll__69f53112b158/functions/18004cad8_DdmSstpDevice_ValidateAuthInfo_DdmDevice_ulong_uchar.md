# DdmSstpDevice::ValidateAuthInfo(DdmDevice *,ulong,uchar *)

- ea: `0x18004cad8`
- end: `0x18004cf94`
- name: `?ValidateAuthInfo@DdmSstpDevice@@AEAAKPEAVDdmDevice@@KPEAE@Z`
- size: `1212`
- prototype: `_BOOL8 __fastcall(DdmSstpDevice *this, struct DdmDevice *, __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004c440`

## callees

- `0x18000108c`
- `0x180002be6`
- `0x180007c0c`
- `0x18004cad8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18004cc50`
- `KERNEL32!HeapAlloc` at `0x18004cc50`
- `KERNEL32!HeapFree` at `0x18004ce2a`
- `KERNEL32!HeapFree` at `0x18004ceb9`
- `KERNEL32!HeapFree` at `0x18004ce2a`
- `KERNEL32!HeapFree` at `0x18004ceb9`

## string_xrefs

- `0x18004cb5c`: `ValidateAuthInfo : Admin Dll callback  is configured`
- `0x18004cba4`: `ValidateAuthInfo : Skipping version 1 Admin Dll callback `

## pseudocode

```c
_BOOL8 __fastcall DdmSstpDevice::ValidateAuthInfo(
        DdmSstpDevice *this,
        struct DdmDevice *a2,
        __int64 a3,
        unsigned __int8 *a4)
{
  unsigned __int8 *v4; // r13
  __int16 v5; // r15
  bool v7; // di
  unsigned int v8; // r12d
  char *v9; // r14
  unsigned __int16 v10; // r15
  char *v11; // rax
  __int64 v12; // r8
  char *v13; // rsi
  int v14; // eax
  int v15; // ecx
  _OWORD *v16; // rax
  __int64 v17; // rdx
  _OWORD *v18; // rcx
  __int128 v19; // xmm1
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v23; // rax
  unsigned int Size; // [rsp+30h] [rbp-50h]
  int Size_4; // [rsp+34h] [rbp-4Ch] BYREF
  void *Src; // [rsp+38h] [rbp-48h]
  _BYTE v27[16]; // [rsp+40h] [rbp-40h] BYREF
  const wchar_t *v28; // [rsp+50h] [rbp-30h]
  __int64 v29; // [rsp+58h] [rbp-28h]
  int *p_Size_4; // [rsp+60h] [rbp-20h]
  __int64 v31; // [rsp+68h] [rbp-18h]

  *((_DWORD *)a2 + 33) &= ~0x20000u;
  Src = a4;
  v4 = a4;
  Size = a3;
  v5 = a3;
  v7 = 0;
  if ( !a4 || !(_DWORD)a3 )
    return 0;
  v8 = 0;
  if ( !dword_1800CF568 )
  {
LABEL_31:
    HeapFree(hHeap, 0, v4);
    return v7;
  }
  while ( 1 )
  {
    v9 = (char *)qword_1800CF560 + 168 * v8;
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v29 = 106;
      v28 = L"ValidateAuthInfo : Admin Dll callback  is configured";
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, a3, 2, v27);
    }
    if ( v9[8] == 1 )
    {
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v29 = 116;
        v28 = L"ValidateAuthInfo : Skipping version 1 Admin Dll callback ";
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, a3, 2, v27);
      }
      goto LABEL_25;
    }
    if ( *((_QWORD *)v9 + 20) )
      break;
LABEL_25:
    if ( ++v8 >= dword_1800CF568 )
      goto LABEL_31;
  }
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v29 = 150;
    v28 = L"ValidateAuthInfo : lpfnRASValidatePreAuthenticatedConnectionEx  is present";
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, a3, 2, v27);
  }
  v10 = v5 + 575;
  if ( v10 >= 0x240u )
  {
    v11 = (char *)HeapAlloc(hHeap, 8u, v10);
    v13 = v11;
    if ( !v11 )
    {
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v21 = -1;
        do
          ++v21;
        while ( aValidateauthin_1[v21] );
        v28 = L"ValidateAuthInfo : unable to allocate memory for AuthValidationEx ";
        v29 = (unsigned int)(2 * v21 + 2);
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v12, 2, v27);
      }
      return v7;
    }
    memset_0(v11, 0, v10);
    v4 = (unsigned __int8 *)Src;
    *((_WORD *)v13 + 1) = v10;
    v5 = Size;
    *(_WORD *)v13 = 1025;
    *((_QWORD *)v13 + 1) = *((_QWORD *)a2 + 15);
    *((_DWORD *)v13 + 141) = Size;
    memcpy_0(v13 + 568, v4, Size);
    v14 = (*((__int64 (__fastcall **)(char *))v9 + 20))(v13);
    v15 = *((_DWORD *)a2 + 33);
    v7 = v14 == 1;
    if ( v14 != 1 )
    {
      *((_DWORD *)a2 + 33) = v15 & 0xFFFDFFFF;
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        v20 = -1;
        do
          ++v20;
        while ( aValidateauthin[v20] );
        v28 = L"ValidateAuthInfo : clearing   DEV_OBJ_ALLOW_NO_AUTH";
        v29 = (unsigned int)(2 * v20 + 2);
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, 0, 2, v27);
      }
      goto LABEL_31;
    }
    v16 = v13 + 16;
    v17 = 4;
    *((_DWORD *)a2 + 33) = v15 | 0x20000;
    v18 = (_OWORD *)((char *)a2 + 168);
    do
    {
      *v18 = *v16;
      v18[1] = v16[1];
      v18[2] = v16[2];
      v18[3] = v16[3];
      v18[4] = v16[4];
      v18[5] = v16[5];
      v18[6] = v16[6];
      v18 += 8;
      v19 = v16[7];
      v16 += 8;
      *(v18 - 1) = v19;
      --v17;
    }
    while ( v17 );
    *(_WORD *)v18 = *(_WORD *)v16;
    *(_OWORD *)((char *)a2 + 682) = *(_OWORD *)(v13 + 530);
    *(_OWORD *)((char *)a2 + 698) = *(_OWORD *)(v13 + 546);
    *((_WORD *)a2 + 340) = 0;
    *((_WORD *)a2 + 356) = 0;
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v29 = 106;
      v28 = L"ValidateAuthInfo :  setting   no auth in device obj ";
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, 128, 2, v27);
    }
    if ( (*((_DWORD *)a2 + 33) & 0x20000) != 0
      && (unsigned int)dword_1800CE720 > 5
      && (qword_1800CE730 & 0x400000000000LL) != 0
      && (qword_1800CE738 & 0x400000000000LL) == qword_1800CE738 )
    {
      Size_4 = 1;
      p_Size_4 = &Size_4;
      v31 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_1800CE720, byte_1800C3FF9, 0, 0, 3, v27);
    }
    HeapFree(hHeap, 0, v13);
    goto LABEL_25;
  }
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v23 = -1;
    do
      ++v23;
    while ( aAuthinfosizeTo[v23] );
    v28 = L"AuthInfoSize too large";
    v29 = (unsigned int)(2 * v23 + 2);
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, a3, 2, v27);
  }
  return 0;
}

```

## disassembly

```asm
0x18004cad8  mov     [rsp-38h+arg_0], rbx
0x18004cadd  push    rbp
0x18004cade  push    rsi
0x18004cadf  push    rdi
0x18004cae0  push    r12
0x18004cae2  push    r13
0x18004cae4  push    r14
0x18004cae6  push    r15
0x18004cae8  mov     rbp, rsp
0x18004caeb  sub     rsp, 80h
0x18004caf2  mov     rax, cs:__security_cookie
0x18004caf9  xor     rax, rsp
0x18004cafc  mov     [rbp+var_10], rax
0x18004cb00  btr     dword ptr [rdx+84h], 11h
0x18004cb08  xor     ecx, ecx
0x18004cb0a  mov     [rbp+Src], r9
0x18004cb0e  mov     r13, r9
0x18004cb11  mov     dword ptr [rbp+Size], r8d
0x18004cb15  mov     r15d, r8d
0x18004cb18  mov     rbx, rdx
0x18004cb1b  mov     dil, cl
0x18004cb1e  test    r9, r9
0x18004cb21  jz      loc_18004CF6A
0x18004cb27  test    r8d, r8d
0x18004cb2a  jz      loc_18004CF6A
0x18004cb30  cmp     cs:dword_1800CF568, ecx
0x18004cb36  mov     r12d, ecx
0x18004cb39  jbe     loc_18004CEAD
0x18004cb3f  lea     esi, [rcx+2]
0x18004cb42  mov     eax, r12d
0x18004cb45  imul    r14, rax, 0A8h
0x18004cb4c  add     r14, cs:qword_1800CF560
0x18004cb53  test    cs:byte_1800CF404, 10h
0x18004cb5a  jz      short loc_18004CB90
0x18004cb5c  lea     rax, aValidateauthin_2; "ValidateAuthInfo : Admin Dll callback  "...
0x18004cb63  mov     [rbp+var_28], 6Ah ; 'j'
0x18004cb6b  mov     [rbp+var_30], rax
0x18004cb6f  lea     rdx, RasDdmTraceInfo
0x18004cb76  lea     rax, [rbp+var_40]
0x18004cb7a  mov     r9d, esi
0x18004cb7d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004cb84  mov     [rsp+80h+var_60], rax
0x18004cb89  call    McGenEventWrite_EventWriteTransfer
0x18004cb8e  xor     ecx, ecx
0x18004cb90  cmp     byte ptr [r14+8], 1
0x18004cb95  jnz     short loc_18004CBDB
0x18004cb97  test    cs:byte_1800CF404, 10h
0x18004cb9e  jz      loc_18004CE3B
0x18004cba4  lea     rax, aValidateauthin_4; "ValidateAuthInfo : Skipping version 1 A"...
0x18004cbab  mov     [rbp+var_28], 74h ; 't'
0x18004cbb3  mov     [rbp+var_30], rax
0x18004cbb7  lea     rdx, RasDdmTraceInfo
0x18004cbbe  lea     rax, [rbp+var_40]
0x18004cbc2  mov     r9d, esi
0x18004cbc5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004cbcc  mov     [rsp+80h+var_60], rax
0x18004cbd1  call    McGenEventWrite_EventWriteTransfer
0x18004cbd6  jmp     loc_18004CE3B
0x18004cbdb  cmp     [r14+0A0h], rcx
0x18004cbe2  jz      loc_18004CE3B
0x18004cbe8  test    cs:byte_1800CF404, 10h
0x18004cbef  jz      short loc_18004CC25
0x18004cbf1  lea     rax, aValidateauthin_3; "ValidateAuthInfo : lpfnRASValidatePreAu"...
0x18004cbf8  mov     [rbp+var_28], 96h
0x18004cc00  mov     [rbp+var_30], rax
0x18004cc04  lea     rdx, RasDdmTraceInfo
0x18004cc0b  lea     rax, [rbp+var_40]
0x18004cc0f  mov     r9d, esi
0x18004cc12  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004cc19  mov     [rsp+80h+var_60], rax
0x18004cc1e  call    McGenEventWrite_EventWriteTransfer
0x18004cc23  xor     ecx, ecx
0x18004cc25  mov     eax, 23Fh
0x18004cc2a  add     r15w, ax
0x18004cc2e  mov     eax, 240h
0x18004cc33  cmp     r15w, ax
0x18004cc37  jb      loc_18004CF1D
0x18004cc3d  mov     rcx, cs:hHeap; hHeap
0x18004cc44  mov     edx, 8; dwFlags
0x18004cc49  movzx   r13d, r15w
0x18004cc4d  mov     r8d, r13d; dwBytes
0x18004cc50  call    cs:__imp_HeapAlloc
0x18004cc57  nop     dword ptr [rax+rax+00h]
0x18004cc5c  xor     ecx, ecx
0x18004cc5e  mov     rsi, rax
0x18004cc61  test    rax, rax
0x18004cc64  jz      loc_18004CEC7
0x18004cc6a  mov     r8d, r13d; Size
0x18004cc6d  xor     edx, edx; Val
0x18004cc6f  mov     rcx, rax; void *
0x18004cc72  call    memset_0
0x18004cc77  mov     r13, [rbp+Src]
0x18004cc7b  mov     [rsi+2], r15w
0x18004cc80  mov     rdx, r13; Src
0x18004cc83  mov     r15d, dword ptr [rbp+Size]
0x18004cc87  mov     word ptr [rsi], 401h
0x18004cc8c  mov     r8d, r15d; Size
0x18004cc8f  mov     rcx, [rbx+78h]
0x18004cc93  mov     [rsi+8], rcx
0x18004cc97  lea     rcx, [rsi+238h]; void *
0x18004cc9e  mov     [rsi+234h], r15d
0x18004cca5  call    memcpy_0
0x18004ccaa  mov     rax, [r14+0A0h]
0x18004ccb1  mov     rcx, rsi
0x18004ccb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ccb9  mov     ecx, [rbx+84h]
0x18004ccbf  cmp     eax, 1
0x18004ccc2  setz    dil
0x18004ccc6  jnz     loc_18004CE4E
0x18004cccc  mov     r14d, 20000h
0x18004ccd2  lea     rax, [rsi+10h]
0x18004ccd6  or      ecx, r14d
0x18004ccd9  mov     edx, 4
0x18004ccde  mov     [rbx+84h], ecx
0x18004cce4  lea     rcx, [rbx+0A8h]
0x18004cceb  lea     r8d, [rdx+7Ch]
0x18004ccef  movups  xmm0, xmmword ptr [rax]
0x18004ccf2  movups  xmmword ptr [rcx], xmm0
0x18004ccf5  movups  xmm1, xmmword ptr [rax+10h]
0x18004ccf9  movups  xmmword ptr [rcx+10h], xmm1
0x18004ccfd  movups  xmm0, xmmword ptr [rax+20h]
0x18004cd01  movups  xmmword ptr [rcx+20h], xmm0
0x18004cd05  movups  xmm1, xmmword ptr [rax+30h]
0x18004cd09  movups  xmmword ptr [rcx+30h], xmm1
0x18004cd0d  movups  xmm0, xmmword ptr [rax+40h]
0x18004cd11  movups  xmmword ptr [rcx+40h], xmm0
0x18004cd15  movups  xmm1, xmmword ptr [rax+50h]
0x18004cd19  movups  xmmword ptr [rcx+50h], xmm1
0x18004cd1d  movups  xmm0, xmmword ptr [rax+60h]
0x18004cd21  movups  xmmword ptr [rcx+60h], xmm0
0x18004cd25  add     rcx, r8
0x18004cd28  movups  xmm1, xmmword ptr [rax+70h]
0x18004cd2c  add     rax, r8
0x18004cd2f  movups  xmmword ptr [rcx-10h], xmm1
0x18004cd33  sub     rdx, 1
0x18004cd37  jnz     short loc_18004CCEF
0x18004cd39  movzx   eax, word ptr [rax]
0x18004cd3c  mov     [rcx], ax
0x18004cd3f  movups  xmm0, xmmword ptr [rsi+212h]
0x18004cd46  movups  xmmword ptr [rbx+2AAh], xmm0
0x18004cd4d  movups  xmm1, xmmword ptr [rsi+222h]
0x18004cd54  movups  xmmword ptr [rbx+2BAh], xmm1
0x18004cd5b  mov     [rbx+2A8h], dx
0x18004cd62  mov     [rbx+2C8h], dx
0x18004cd69  test    cs:byte_1800CF404, 10h
0x18004cd70  jz      short loc_18004CDA5
0x18004cd72  lea     rax, aValidateauthin_0; "ValidateAuthInfo :  setting   no auth i"...
0x18004cd79  mov     [rbp+var_28], 6Ah ; 'j'
0x18004cd81  mov     [rbp+var_30], rax
0x18004cd85  lea     r9d, [rdx+2]
0x18004cd89  lea     rax, [rbp+var_40]
0x18004cd8d  lea     rdx, RasDdmTraceInfo
0x18004cd94  mov     [rsp+80h+var_60], rax
0x18004cd99  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004cda0  call    McGenEventWrite_EventWriteTransfer
0x18004cda5  test    [rbx+84h], r14d
0x18004cdac  jz      short loc_18004CE1E
0x18004cdae  cmp     cs:dword_1800CE720, 5
0x18004cdb5  jbe     short loc_18004CE1E
0x18004cdb7  mov     r8, 400000000000h
0x18004cdc1  test    cs:qword_1800CE730, r8
0x18004cdc8  jz      short loc_18004CE1E
0x18004cdca  mov     rax, cs:qword_1800CE738
0x18004cdd1  and     rax, r8
0x18004cdd4  cmp     rax, cs:qword_1800CE738
0x18004cddb  jnz     short loc_18004CE1E
0x18004cddd  lea     rax, [rbp+Size+4]
0x18004cde1  mov     dword ptr [rbp+Size+4], 1
0x18004cde8  mov     [rbp+var_20], rax
0x18004cdec  lea     rdx, byte_1800C3FF9
0x18004cdf3  lea     rax, [rbp+var_40]
0x18004cdf7  mov     [rbp+var_18], 4
0x18004cdff  mov     [rsp+80h+var_58], rax
0x18004ce04  lea     rcx, dword_1800CE720
0x18004ce0b  xor     r9d, r9d
0x18004ce0e  mov     dword ptr [rsp+80h+var_60], 3
0x18004ce16  xor     r8d, r8d
0x18004ce19  call    _tlgWriteTransfer_EventWriteTransfer
0x18004ce1e  mov     rcx, cs:hHeap; hHeap
0x18004ce25  mov     r8, rsi; lpMem
0x18004ce28  xor     edx, edx; dwFlags
0x18004ce2a  call    cs:__imp_HeapFree
0x18004ce31  nop     dword ptr [rax+rax+00h]
0x18004ce36  mov     esi, 2
0x18004ce3b  inc     r12d
0x18004ce3e  cmp     r12d, cs:dword_1800CF568
0x18004ce45  jnb     short loc_18004CEAD
0x18004ce47  xor     ecx, ecx
0x18004ce49  jmp     loc_18004CB42
0x18004ce4e  btr     ecx, 11h
0x18004ce52  mov     [rbx+84h], ecx
0x18004ce58  test    cs:byte_1800CF404, 10h
0x18004ce5f  jz      short loc_18004CEAD
0x18004ce61  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004ce65  lea     rcx, aValidateauthin; "ValidateAuthInfo : clearing   DEV_OBJ_A"...
0x18004ce6c  xor     r8d, r8d
0x18004ce6f  inc     rax
0x18004ce72  cmp     [rcx+rax*2], r8w
0x18004ce77  jnz     short loc_18004CE6F
0x18004ce79  lea     eax, ds:2[rax*2]
0x18004ce80  mov     [rbp+var_30], rcx
0x18004ce84  mov     dword ptr [rbp+var_28], eax
0x18004ce87  lea     rdx, RasDdmTraceInfo
0x18004ce8e  lea     rax, [rbp+var_40]
0x18004ce92  mov     dword ptr [rbp+var_28+4], r8d
0x18004ce96  mov     r9d, 2
0x18004ce9c  mov     [rsp+80h+var_60], rax
0x18004cea1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004cea8  call    McGenEventWrite_EventWriteTransfer
0x18004cead  mov     rcx, cs:hHeap; hHeap
0x18004ceb4  mov     r8, r13; lpMem
0x18004ceb7  xor     edx, edx; dwFlags
0x18004ceb9  call    cs:__imp_HeapFree
0x18004cec0  nop     dword ptr [rax+rax+00h]
0x18004cec5  jmp     short loc_18004CF17
0x18004cec7  test    cs:byte_1800CF404, 10h
0x18004cece  jz      short loc_18004CF17
0x18004ced0  lea     rdx, aValidateauthin_1; "ValidateAuthInfo : unable to allocate m"...
0x18004ced7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004cedb  inc     rax
0x18004cede  cmp     [rdx+rax*2], cx
0x18004cee2  jnz     short loc_18004CEDB
0x18004cee4  lea     eax, ds:2[rax*2]
0x18004ceeb  mov     [rbp+var_30], rdx
0x18004ceef  mov     dword ptr [rbp+var_28], eax
0x18004cef2  lea     rdx, RasDdmTraceInfo
0x18004cef9  lea     rax, [rbp+var_40]
0x18004cefd  mov     dword ptr [rbp+var_28+4], ecx
0x18004cf00  mov     r9d, 2
0x18004cf06  mov     [rsp+80h+var_60], rax
0x18004cf0b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004cf12  call    McGenEventWrite_EventWriteTransfer
0x18004cf17  movzx   eax, dil
0x18004cf1b  jmp     short loc_18004CF6C
0x18004cf1d  test    cs:byte_1800CF404, 10h
0x18004cf24  jz      short loc_18004CF6A
0x18004cf26  lea     rdx, aAuthinfosizeTo; "AuthInfoSize too large"
0x18004cf2d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004cf31  inc     rax
0x18004cf34  cmp     [rdx+rax*2], cx
0x18004cf38  jnz     short loc_18004CF31
0x18004cf3a  lea     eax, ds:2[rax*2]
0x18004cf41  mov     [rbp+var_30], rdx
0x18004cf45  mov     dword ptr [rbp+var_28], eax
0x18004cf48  lea     rdx, RasDdmTraceInfo
0x18004cf4f  lea     rax, [rbp+var_40]
0x18004cf53  mov     dword ptr [rbp+var_28+4], ecx
0x18004cf56  mov     r9d, esi
0x18004cf59  mov     [rsp+80h+var_60], rax
0x18004cf5e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004cf65  call    McGenEventWrite_EventWriteTransfer
0x18004cf6a  xor     eax, eax
0x18004cf6c  mov     rcx, [rbp+var_10]
0x18004cf70  xor     rcx, rsp; StackCookie
0x18004cf73  call    __security_check_cookie
0x18004cf78  mov     rbx, [rsp+80h+arg_0]
0x18004cf80  add     rsp, 80h
0x18004cf87  pop     r15
0x18004cf89  pop     r14
0x18004cf8b  pop     r13
0x18004cf8d  pop     r12
0x18004cf8f  pop     rdi
0x18004cf90  pop     rsi
0x18004cf91  pop     rbp
0x18004cf92  retn
```
