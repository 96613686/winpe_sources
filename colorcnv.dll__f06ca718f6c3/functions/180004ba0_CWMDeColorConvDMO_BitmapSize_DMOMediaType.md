# CWMDeColorConvDMO::BitmapSize(_DMOMediaType *)

- ea: `0x180004ba0`
- end: `0x180004d42`
- name: `?BitmapSize@CWMDeColorConvDMO@@AEAAKPEAU_DMOMediaType@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(CWMDeColorConvDMO *this, struct _DMOMediaType *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180003e30`
- `0x1800046c0`
- `0x180004710`
- `0x18000d120`

## callees

- `0x180004a68`
- `0x180004ba0`
- `0x180004dcc`
- `0x180029fb4`

## pseudocode

```c
__int64 __fastcall CWMDeColorConvDMO::BitmapSize(CWMDeColorConvDMO *this, struct _DMOMediaType *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rax
  int v6; // edx
  CWMDeColorConvDMO *v7; // rcx
  __int64 result; // rax
  __int64 v9; // rax
  int v10; // edx
  int v11; // ecx
  unsigned int v12; // edx
  unsigned int v13; // edx
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // edx
  __int64 v17; // rax
  __int64 v18; // rax

  v4 = (_QWORD *)((char *)a2 + 44);
  v5 = *(_QWORD *)((char *)a2 + 44) - *(_QWORD *)&FORMAT_VideoInfo.Data1;
  if ( !v5 )
    v5 = *(_QWORD *)((char *)a2 + 52) - *(_QWORD *)FORMAT_VideoInfo.Data4;
  if ( v5 )
  {
    v14 = *v4 - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
    if ( *v4 == *(_QWORD *)&FORMAT_VideoInfo2.Data1 )
      v14 = *(_QWORD *)((char *)a2 + 52) - *(_QWORD *)FORMAT_VideoInfo2.Data4;
    if ( v14 )
      memcmp_0(v4, &FORMAT_MFVideoFormat, 0x10u);
  }
  if ( (unsigned int)UseDIBSIZE(*((_DWORD *)a2 + 4)) )
  {
    switch ( v6 )
    {
      case 0:
        v9 = *((_QWORD *)a2 + 10);
LABEL_11:
        v10 = *(_DWORD *)(v9 + 52) * *(unsigned __int16 *)(v9 + 62);
        v11 = *(_DWORD *)(v9 + 56);
LABEL_12:
        v12 = ((unsigned int)(v10 + 31) >> 3) & 0x1FFFFFFC;
        goto LABEL_13;
      case 1:
        v17 = *((_QWORD *)a2 + 10);
        v10 = *(_DWORD *)(v17 + 76) * *(unsigned __int16 *)(v17 + 86);
        v11 = *(_DWORD *)(v17 + 80);
        goto LABEL_12;
      case 2:
        if ( CWMDeColorConvDMO::getVIH(
               v7,
               a2,
               *((struct tagVIDEOINFOHEADER **)this + 148),
               *((_DWORD *)this + 298),
               (struct tagVIDEOINFOHEADER **)this + 147) < 0 )
          return 0xFFFFFFFFLL;
        v9 = *((_QWORD *)this + 148);
        goto LABEL_11;
    }
    return 0;
  }
  if ( v6 )
  {
    if ( v6 == 1 )
    {
      v18 = *((_QWORD *)a2 + 10);
      v16 = *(_DWORD *)(v18 + 76) * *(unsigned __int16 *)(v18 + 86);
      v11 = *(_DWORD *)(v18 + 80);
      goto LABEL_26;
    }
    if ( v6 != 2 )
      return 0;
    if ( CWMDeColorConvDMO::getVIH(
           v7,
           a2,
           *((struct tagVIDEOINFOHEADER **)this + 148),
           *((_DWORD *)this + 298),
           (struct tagVIDEOINFOHEADER **)this + 147) < 0 )
      return 0xFFFFFFFFLL;
    v15 = *((_QWORD *)this + 148);
  }
  else
  {
    v15 = *((_QWORD *)a2 + 10);
  }
  v16 = *(_DWORD *)(v15 + 52) * *(unsigned __int16 *)(v15 + 62);
  v11 = *(_DWORD *)(v15 + 56);
LABEL_26:
  v12 = (unsigned int)(v16 + 7) >> 3;
LABEL_13:
  v13 = v11 * v12;
  result = -v13;
  if ( v11 >= 0 )
    return v13;
  return result;
}

```

## disassembly

```asm
0x180004ba0  mov     [rsp+arg_0], rbx
0x180004ba5  push    rdi
0x180004ba6  sub     rsp, 30h
0x180004baa  mov     rbx, rcx
0x180004bad  mov     rdi, rdx
0x180004bb0  lea     rcx, [rdx+2Ch]; Buf1
0x180004bb4  mov     rax, [rcx]
0x180004bb7  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x180004bbe  jnz     short loc_180004BCB
0x180004bc0  mov     rax, [rcx+8]
0x180004bc4  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180004bcb  test    rax, rax
0x180004bce  jnz     loc_180004C5D
0x180004bd4  xor     edx, edx
0x180004bd6  mov     ecx, [rdi+10h]; unsigned int
0x180004bd9  call    ?UseDIBSIZE@@YAHK@Z; UseDIBSIZE(ulong)
0x180004bde  test    eax, eax
0x180004be0  jz      loc_180004C9D
0x180004be6  test    edx, edx
0x180004be8  jz      short loc_180004C2B
0x180004bea  cmp     edx, 1
0x180004bed  jz      loc_180004D17
0x180004bf3  cmp     edx, 2
0x180004bf6  jnz     loc_180004D10
0x180004bfc  mov     r9d, [rbx+4A8h]; unsigned int
0x180004c03  lea     rax, [rbx+498h]
0x180004c0a  mov     r8, [rbx+4A0h]; struct tagVIDEOINFOHEADER *
0x180004c11  mov     rdx, rdi; struct _DMOMediaType *
0x180004c14  mov     [rsp+38h+var_18], rax; struct tagVIDEOINFOHEADER **
0x180004c19  call    ?getVIH@CWMDeColorConvDMO@@AEAAJPEBU_DMOMediaType@@PEAUtagVIDEOINFOHEADER@@KPEAPEAU3@@Z; CWMDeColorConvDMO::getVIH(_DMOMediaType const *,tagVIDEOINFOHEADER *,ulong,tagVIDEOINFOHEADER * *)
0x180004c1e  test    eax, eax
0x180004c20  jns     loc_180004CFA
0x180004c26  or      eax, 0FFFFFFFFh
0x180004c29  jmp     short loc_180004C52
0x180004c2b  mov     rax, [rdi+50h]
0x180004c2f  movzx   edx, word ptr [rax+3Eh]
0x180004c33  imul    edx, [rax+34h]
0x180004c37  mov     ecx, [rax+38h]
0x180004c3a  add     edx, 1Fh
0x180004c3d  shr     edx, 3
0x180004c40  and     edx, 1FFFFFFCh
0x180004c46  imul    edx, ecx
0x180004c49  mov     eax, edx
0x180004c4b  neg     eax
0x180004c4d  test    ecx, ecx
0x180004c4f  cmovns  eax, edx
0x180004c52  mov     rbx, [rsp+38h+arg_0]
0x180004c57  add     rsp, 30h
0x180004c5b  pop     rdi
0x180004c5c  retn
0x180004c5d  mov     rax, [rcx]
0x180004c60  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180004c67  jnz     short loc_180004C74
0x180004c69  mov     rax, [rcx+8]
0x180004c6d  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180004c74  test    rax, rax
0x180004c77  jz      loc_180004D06
0x180004c7d  mov     r8d, 10h; Size
0x180004c83  lea     rdx, FORMAT_MFVideoFormat; Buf2
0x180004c8a  call    memcmp_0
0x180004c8f  neg     eax
0x180004c91  sbb     edx, edx
0x180004c93  neg     edx
0x180004c95  add     edx, 2
0x180004c98  jmp     loc_180004BD6
0x180004c9d  test    edx, edx
0x180004c9f  jz      loc_180004D2B
0x180004ca5  cmp     edx, 1
0x180004ca8  jz      loc_180004D31
0x180004cae  cmp     edx, 2
0x180004cb1  jnz     short loc_180004D10
0x180004cb3  mov     r9d, [rbx+4A8h]; unsigned int
0x180004cba  lea     rax, [rbx+498h]
0x180004cc1  mov     r8, [rbx+4A0h]; struct tagVIDEOINFOHEADER *
0x180004cc8  mov     rdx, rdi; struct _DMOMediaType *
0x180004ccb  mov     [rsp+38h+var_18], rax; struct tagVIDEOINFOHEADER **
0x180004cd0  call    ?getVIH@CWMDeColorConvDMO@@AEAAJPEBU_DMOMediaType@@PEAUtagVIDEOINFOHEADER@@KPEAPEAU3@@Z; CWMDeColorConvDMO::getVIH(_DMOMediaType const *,tagVIDEOINFOHEADER *,ulong,tagVIDEOINFOHEADER * *)
0x180004cd5  test    eax, eax
0x180004cd7  js      loc_180004C26
0x180004cdd  mov     rax, [rbx+4A0h]
0x180004ce4  movzx   edx, word ptr [rax+3Eh]
0x180004ce8  imul    edx, [rax+34h]
0x180004cec  mov     ecx, [rax+38h]
0x180004cef  add     edx, 7
0x180004cf2  shr     edx, 3
0x180004cf5  jmp     loc_180004C46
0x180004cfa  mov     rax, [rbx+4A0h]
0x180004d01  jmp     loc_180004C2F
0x180004d06  mov     edx, 1
0x180004d0b  jmp     loc_180004BD6
0x180004d10  xor     eax, eax
0x180004d12  jmp     loc_180004C52
0x180004d17  mov     rax, [rdi+50h]
0x180004d1b  movzx   edx, word ptr [rax+56h]
0x180004d1f  imul    edx, [rax+4Ch]
0x180004d23  mov     ecx, [rax+50h]
0x180004d26  jmp     loc_180004C3A
0x180004d2b  mov     rax, [rdi+50h]
0x180004d2f  jmp     short loc_180004CE4
0x180004d31  mov     rax, [rdi+50h]
0x180004d35  movzx   edx, word ptr [rax+56h]
0x180004d39  imul    edx, [rax+4Ch]
0x180004d3d  mov     ecx, [rax+50h]
0x180004d40  jmp     short loc_180004CEF
```
