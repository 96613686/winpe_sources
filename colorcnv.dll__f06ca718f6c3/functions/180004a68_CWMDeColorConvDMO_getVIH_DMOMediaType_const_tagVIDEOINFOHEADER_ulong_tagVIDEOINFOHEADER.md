# CWMDeColorConvDMO::getVIH(_DMOMediaType const *,tagVIDEOINFOHEADER *,ulong,tagVIDEOINFOHEADER * *)

- ea: `0x180004a68`
- end: `0x180004b99`
- name: `?getVIH@CWMDeColorConvDMO@@AEAAJPEBU_DMOMediaType@@PEAUtagVIDEOINFOHEADER@@KPEAPEAU3@@Z`
- size: `305`
- prototype: `__int64 __fastcall(CWMDeColorConvDMO *this, const struct _DMOMediaType *, struct tagVIDEOINFOHEADER *, unsigned int, struct tagVIDEOINFOHEADER **)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800040b0`
- `0x180004710`
- `0x180004ba0`
- `0x18000cbb0`
- `0x18000d350`
- `0x18000e160`

## callees

- `0x180004a68`
- `0x180004e18`
- `0x18000f148`
- `0x180029fc0`

## pseudocode

```c
__int64 __fastcall CWMDeColorConvDMO::getVIH(
        CWMDeColorConvDMO *this,
        const struct _DMOMediaType *a2,
        struct tagVIDEOINFOHEADER *a3,
        unsigned int a4,
        struct tagVIDEOINFOHEADER **a5)
{
  __int64 v5; // rsi
  struct tagVIDEOINFOHEADER *v6; // rbx
  struct tagVIDEOINFOHEADER **v7; // rdi
  __int64 v8; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  const void *v13; // rbp
  size_t v14; // r8
  CWMDeColorConvDMO *v15; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v16; // [rsp+48h] [rbp+10h] BYREF

  v15 = this;
  v5 = a4;
  v6 = a3;
  if ( !a2 )
    return 2147500035LL;
  if ( !a3 )
    return 2147500035LL;
  v7 = a5;
  if ( !a5 )
    return 2147500035LL;
  v8 = *(_QWORD *)((char *)a2 + 44) - *(_QWORD *)&FORMAT_VideoInfo.Data1;
  if ( !v8 )
    v8 = *(_QWORD *)((char *)a2 + 52) - *(_QWORD *)FORMAT_VideoInfo.Data4;
  if ( !v8 )
  {
    v6 = (struct tagVIDEOINFOHEADER *)*((_QWORD *)a2 + 10);
LABEL_8:
    *v7 = v6;
    return 0;
  }
  v10 = *(_QWORD *)((char *)a2 + 44) - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
  if ( !v10 )
    v10 = *(_QWORD *)((char *)a2 + 52) - *(_QWORD *)FORMAT_VideoInfo2.Data4;
  if ( v10 )
  {
    v11 = *(_QWORD *)((char *)a2 + 44) - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
    if ( !v11 )
      v11 = *(_QWORD *)((char *)a2 + 52) - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
    if ( !v11 )
    {
      ConvertMFVideoFormatToVIH3(a3, *((struct _MFVIDEOFORMAT **)a2 + 10));
      goto LABEL_8;
    }
  }
  else
  {
    v12 = *((_QWORD *)a2 + 10);
    LODWORD(v15) = 0;
    v13 = (const void *)(v12 + 72);
    a3->rcSource = *(RECT *)v12;
    a3->rcTarget = *(RECT *)(v12 + 16);
    a3->dwBitRate = *(_DWORD *)(v12 + 32);
    a3->dwBitErrorRate = *(_DWORD *)(v12 + 36);
    a3->AvgTimePerFrame = *(_QWORD *)(v12 + 40);
    if ( (unsigned int)ComputeBitMapInfoHeaderSize(
                         (const struct tagBITMAPINFOHEADER *)(v12 + 72),
                         (unsigned int *)&v15,
                         &v16) )
    {
      v14 = (unsigned int)v15;
      if ( v5 + 40 < (unsigned __int64)(unsigned int)v15 )
        v14 = (unsigned int)(v5 + 40);
      memcpy_0(&v6->bmiHeader, v13, v14);
      goto LABEL_8;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180004a68  mov     [rsp+arg_10], rbx
0x180004a6d  mov     [rsp+arg_0], rcx
0x180004a72  push    rbp
0x180004a73  push    rsi
0x180004a74  push    rdi
0x180004a75  sub     rsp, 20h
0x180004a79  mov     esi, r9d
0x180004a7c  mov     rbx, r8
0x180004a7f  test    rdx, rdx
0x180004a82  jz      loc_180004B21
0x180004a88  test    rbx, rbx
0x180004a8b  jz      loc_180004B21
0x180004a91  mov     rdi, [rsp+38h+arg_20]
0x180004a96  test    rdi, rdi
0x180004a99  jz      loc_180004B21
0x180004a9f  mov     rax, [rdx+2Ch]
0x180004aa3  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x180004aaa  jnz     short loc_180004AB7
0x180004aac  mov     rax, [rdx+34h]
0x180004ab0  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180004ab7  test    rax, rax
0x180004aba  jnz     short loc_180004AD2
0x180004abc  mov     rbx, [rdx+50h]
0x180004ac0  mov     [rdi], rbx
0x180004ac3  xor     eax, eax
0x180004ac5  mov     rbx, [rsp+38h+arg_10]
0x180004aca  add     rsp, 20h
0x180004ace  pop     rdi
0x180004acf  pop     rsi
0x180004ad0  pop     rbp
0x180004ad1  retn
0x180004ad2  mov     rax, [rdx+2Ch]
0x180004ad6  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180004add  jnz     short loc_180004AEA
0x180004adf  mov     rax, [rdx+34h]
0x180004ae3  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180004aea  test    rax, rax
0x180004aed  jz      short loc_180004B28
0x180004aef  mov     rax, [rdx+2Ch]
0x180004af3  sub     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180004afa  jnz     short loc_180004B07
0x180004afc  mov     rax, [rdx+34h]
0x180004b00  sub     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180004b07  test    rax, rax
0x180004b0a  jnz     short loc_180004B1A
0x180004b0c  mov     rdx, [rdx+50h]; struct _MFVIDEOFORMAT *
0x180004b10  mov     rcx, rbx; struct tagVIDEOINFOHEADER *
0x180004b13  call    ?ConvertMFVideoFormatToVIH3@@YAJPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH3(tagVIDEOINFOHEADER *,_MFVIDEOFORMAT *)
0x180004b18  jmp     short loc_180004AC0
0x180004b1a  mov     eax, 80004005h
0x180004b1f  jmp     short loc_180004AC5
0x180004b21  mov     eax, 80004003h
0x180004b26  jmp     short loc_180004AC5
0x180004b28  mov     rcx, [rdx+50h]
0x180004b2c  lea     rdx, [rsp+38h+arg_0]; unsigned int *
0x180004b31  mov     dword ptr [rsp+38h+arg_0], 0
0x180004b39  movups  xmm0, xmmword ptr [rcx]
0x180004b3c  lea     rbp, [rcx+48h]
0x180004b40  movdqu  xmmword ptr [r8], xmm0
0x180004b45  movups  xmm1, xmmword ptr [rcx+10h]
0x180004b49  movdqu  xmmword ptr [r8+10h], xmm1
0x180004b4f  mov     eax, [rcx+20h]
0x180004b52  mov     [r8+20h], eax
0x180004b56  mov     eax, [rcx+24h]
0x180004b59  mov     [r8+24h], eax
0x180004b5d  mov     rax, [rcx+28h]
0x180004b61  mov     rcx, rbp; struct tagBITMAPINFOHEADER *
0x180004b64  mov     [r8+28h], rax
0x180004b68  lea     r8, [rsp+38h+arg_8]; unsigned int *
0x180004b6d  call    ?ComputeBitMapInfoHeaderSize@@YAHPEBUtagBITMAPINFOHEADER@@PEAI1@Z; ComputeBitMapInfoHeaderSize(tagBITMAPINFOHEADER const *,uint *,uint *)
0x180004b72  test    eax, eax
0x180004b74  jz      short loc_180004B1A
0x180004b76  mov     r8d, dword ptr [rsp+38h+arg_0]
0x180004b7b  lea     rcx, [rsi+28h]
0x180004b7f  cmp     rcx, r8
0x180004b82  jnb     short loc_180004B88
0x180004b84  lea     r8d, [rsi+28h]; Size
0x180004b88  lea     rcx, [rbx+30h]; void *
0x180004b8c  mov     rdx, rbp; Src
0x180004b8f  call    memcpy_0
0x180004b94  jmp     loc_180004AC0
```
