# VariantResolveDispatch(tagVARIANT *,tagVARIANT *)

- ea: `0x18000dc08`
- end: `0x18000dd4a`
- name: `?VariantResolveDispatch@@YAJPEAUtagVARIANT@@0@Z`
- size: `322`
- prototype: `HRESULT __fastcall(VARIANTARG *pvarg, VARIANTARG *pvargSrc)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000b898`
- `0x18000c5ec`

## callees

- `0x18000dc08`
- `0x1800111ae`
- `0x180012010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000dd30`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dd30`
- `OLEAUT32!__imp_VariantInit` at `0x18000dc50`
- `OLEAUT32!__imp_VariantInit` at `0x18000dc5a`
- `OLEAUT32!__imp_VariantInit` at `0x18000dc94`
- `OLEAUT32!__imp_VariantInit` at `0x18000dc50`
- `OLEAUT32!__imp_VariantInit` at `0x18000dc5a`
- `OLEAUT32!__imp_VariantInit` at `0x18000dc94`
- `OLEAUT32!__imp_VariantClear` at `0x18000dced`
- `OLEAUT32!__imp_VariantClear` at `0x18000dd40`
- `OLEAUT32!__imp_VariantClear` at `0x18000dced`
- `OLEAUT32!__imp_VariantClear` at `0x18000dd40`
- `OLEAUT32!__imp_VariantCopy` at `0x18000dc75`
- `OLEAUT32!__imp_VariantCopy` at `0x18000dc75`

## pseudocode

```c
HRESULT __fastcall VariantResolveDispatch(VARIANTARG *pvarg, VARIANTARG *pvargSrc)
{
  HRESULT result; // eax
  int v5; // eax
  int v6; // ebx
  IRecordInfo *pRecInfo; // xmm1_8
  int v8; // [rsp+20h] [rbp-49h]
  VARIANTARG pvarga; // [rsp+50h] [rbp-19h] BYREF
  __int128 v10; // [rsp+68h] [rbp-1h] BYREF
  __int64 v11; // [rsp+78h] [rbp+Fh]
  _BYTE v12[24]; // [rsp+80h] [rbp+17h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp+2Fh]

  v11 = 0;
  memset(&pvarga, 0, sizeof(pvarga));
  v10 = 0;
  memset_0(v12, 0, 0x40u);
  VariantInit(pvarg);
  VariantInit(&pvarga);
  memset_0(v12, 0, 0x40u);
  result = VariantCopy(pvarg, pvargSrc);
  if ( result >= 0 )
  {
    while ( 1 )
    {
      if ( pvarg->vt != 9 )
        return 0;
      if ( !pvarg->llVal )
      {
        v6 = -2147352573;
        goto LABEL_12;
      }
      VariantInit(&pvarga);
      LOWORD(v8) = 3;
      v5 = (*(__int64 (__fastcall **)(LONGLONG, _QWORD, GUID *, __int64, int, __int128 *, VARIANTARG *, _BYTE *, _QWORD))(*pvarg->pllVal + 48))(
             pvarg->llVal,
             0,
             &GUID_NULL,
             2048,
             v8,
             &v10,
             &pvarga,
             v12,
             0);
      v6 = v5;
      if ( v5 < 0 )
        break;
      VariantClear(pvarg);
      pRecInfo = pvarga.pRecInfo;
      *(_OWORD *)&pvarg->vt = *(_OWORD *)&pvarga.vt;
      pvarg->pRecInfo = pRecInfo;
    }
    if ( v5 == -2147352567 )
      SysFreeString(bstrString);
LABEL_12:
    VariantClear(pvarg);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18000dc08  mov     [rsp-8+arg_0], rbx
0x18000dc0d  mov     [rsp-8+arg_8], rdi
0x18000dc12  push    rbp
0x18000dc13  lea     rbp, [rsp-57h]
0x18000dc18  sub     rsp, 0C0h
0x18000dc1f  xor     eax, eax
0x18000dc21  mov     rbx, rdx
0x18000dc24  mov     rdi, rcx
0x18000dc27  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18000dc2b  xorps   xmm0, xmm0
0x18000dc2e  mov     [rbp+57h+var_48], rax
0x18000dc32  xorps   xmm1, xmm1
0x18000dc35  lea     rcx, [rbp+57h+var_40]; void *
0x18000dc39  lea     r8d, [rax+40h]; Size
0x18000dc3d  xor     edx, edx; Val
0x18000dc3f  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18000dc43  movdqu  [rbp+57h+var_58], xmm1
0x18000dc48  call    memset_0
0x18000dc4d  mov     rcx, rdi; pvarg
0x18000dc50  call    cs:__imp_VariantInit
0x18000dc56  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000dc5a  call    cs:__imp_VariantInit
0x18000dc60  xor     edx, edx; Val
0x18000dc62  lea     rcx, [rbp+57h+var_40]; void *
0x18000dc66  lea     r8d, [rdx+40h]; Size
0x18000dc6a  call    memset_0
0x18000dc6f  mov     rdx, rbx; pvargSrc
0x18000dc72  mov     rcx, rdi; pvargDest
0x18000dc75  call    cs:__imp_VariantCopy
0x18000dc7b  test    eax, eax
0x18000dc7d  js      loc_18000DD10
0x18000dc83  jmp     short loc_18000DD04
0x18000dc85  cmp     qword ptr [rdi+8], 0
0x18000dc8a  jz      loc_18000DD38
0x18000dc90  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000dc94  call    cs:__imp_VariantInit
0x18000dc9a  mov     rcx, [rdi+8]
0x18000dc9e  lea     rdx, [rbp+57h+var_40]
0x18000dca2  mov     [rsp+0C0h+var_80], 0
0x18000dcab  lea     r8, GUID_NULL
0x18000dcb2  mov     [rsp+0C0h+var_88], rdx
0x18000dcb7  mov     r9d, 800h
0x18000dcbd  lea     rdx, [rbp+57h+pvarg]
0x18000dcc1  mov     rax, [rcx]
0x18000dcc4  mov     [rsp+0C0h+var_90], rdx
0x18000dcc9  lea     rdx, [rbp+57h+var_58]
0x18000dccd  mov     [rsp+0C0h+var_98], rdx
0x18000dcd2  xor     edx, edx
0x18000dcd4  mov     [rsp+0C0h+var_A0], 3
0x18000dcdb  mov     rax, [rax+30h]
0x18000dcdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dce4  mov     ebx, eax
0x18000dce6  test    eax, eax
0x18000dce8  js      short loc_18000DD25
0x18000dcea  mov     rcx, rdi; pvarg
0x18000dced  call    cs:__imp_VariantClear
0x18000dcf3  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18000dcf7  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18000dcfc  movups  xmmword ptr [rdi], xmm0
0x18000dcff  movsd   qword ptr [rdi+10h], xmm1
0x18000dd04  cmp     word ptr [rdi], 9
0x18000dd08  jz      loc_18000DC85
0x18000dd0e  xor     eax, eax
0x18000dd10  lea     r11, [rsp+0C0h+var_s0]
0x18000dd18  mov     rbx, [r11+10h]
0x18000dd1c  mov     rdi, [r11+18h]
0x18000dd20  mov     rsp, r11
0x18000dd23  pop     rbp
0x18000dd24  retn
0x18000dd25  cmp     eax, 80020009h
0x18000dd2a  jnz     short loc_18000DD3D
0x18000dd2c  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000dd30  call    cs:__imp_SysFreeString
0x18000dd36  jmp     short loc_18000DD3D
0x18000dd38  mov     ebx, 80020003h
0x18000dd3d  mov     rcx, rdi; pvarg
0x18000dd40  call    cs:__imp_VariantClear
0x18000dd46  mov     eax, ebx
0x18000dd48  jmp     short loc_18000DD10
```
