# HrConvFromVTVERSIONEDSTREAM(tagPROPVARIANT *,tagPROPVARIANT const *,ushort)

- ea: `0x180051960`
- end: `0x180051a76`
- name: `?HrConvFromVTVERSIONEDSTREAM@@YAJPEAUtagPROPVARIANT@@PEBU1@G@Z`
- size: `278`
- prototype: `__int64 __fastcall(struct tagPROPVARIANT *, const struct tagPROPVARIANT *, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180051b64`

## callees

- `0x180050d44`
- `0x180051960`
- `0x1800522d0`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180051a50`
- `OLEAUT32!__imp_SysFreeString` at `0x180051a50`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800519fb`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800519fb`

## pseudocode

```c
__int64 __fastcall HrConvFromVTVERSIONEDSTREAM(struct tagPROPVARIANT *a1, const struct tagPROPVARIANT *a2, __int16 a3)
{
  unsigned int ValFromUNK; // ebx
  SAFEARRAY *v6; // rax
  LARGE_INTEGER v7; // rcx
  _OWORD *pvData; // rax
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int64 i; // rcx
  __int64 v12; // rax
  struct tagPROPVARIANT v14; // [rsp+20h] [rbp-58h] BYREF
  BSTR bstrString[2]; // [rsp+38h] [rbp-40h] BYREF
  _OWORD v16[3]; // [rsp+48h] [rbp-30h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+B8h] [rbp+40h] BYREF

  rgsabound = 0;
  memset(&v14, 0, sizeof(v14));
  *(_OWORD *)bstrString = 0;
  memset(v16, 0, 32);
  if ( a3 == 8204 )
  {
    v14.vt = 72;
    v14.hVal.QuadPart = a2->hVal.QuadPart;
    ValFromUNK = HrCLSIDToStr((struct tagPROPVARIANT *)bstrString, &v14, 8u);
    if ( !ValFromUNK )
    {
      ValFromUNK = HrGetValFromUNK(
                     (struct tagPROPVARIANT *)((char *)v16 + 8),
                     *(struct IUnknown **)(a2->hVal.QuadPart + 16),
                     0xDu);
      if ( !ValFromUNK )
      {
        rgsabound = (SAFEARRAYBOUND)2LL;
        v6 = SafeArrayCreate(0xCu, 1u, &rgsabound);
        v7.QuadPart = (LONGLONG)v6;
        if ( v6 )
        {
          pvData = v6->pvData;
          v9 = v16[0];
          *pvData = *(_OWORD *)bstrString;
          v10 = v16[1];
          pvData[1] = v9;
          pvData[2] = v10;
          a1->hVal = v7;
          for ( i = 0; i != 2; ++i )
          {
            v12 = 3 * i;
            bstrString[v12 + 1] = 0;
          }
        }
        else
        {
          ValFromUNK = -2147024882;
        }
      }
    }
  }
  else
  {
    ValFromUNK = -2147352571;
  }
  if ( bstrString[1] )
    SysFreeString(bstrString[1]);
  if ( *(_QWORD *)&v16[1] )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v16[1] + 16LL))(*(_QWORD *)&v16[1]);
  return ValFromUNK;
}

```

## disassembly

```asm
0x180051960  push    rbp
0x180051962  push    rbx
0x180051963  push    rsi
0x180051964  push    rdi
0x180051965  mov     rbp, rsp
0x180051968  sub     rsp, 78h
0x18005196c  xor     eax, eax
0x18005196e  xorps   xmm0, xmm0
0x180051971  mov     qword ptr [rbp+var_58+10h], rax
0x180051975  mov     rdi, rdx
0x180051978  mov     qword ptr [rbp+rgsabound.cElements], rax
0x18005197c  mov     rsi, rcx
0x18005197f  mov     eax, 200Ch
0x180051984  movups  xmmword ptr [rbp+var_58], xmm0
0x180051988  movups  xmmword ptr [rbp+bstrString], xmm0
0x18005198c  movups  xmmword ptr [rbp+var_30], xmm0
0x180051990  movups  xmmword ptr [rbp+var_30+10h], xmm0
0x180051994  cmp     r8w, ax
0x180051998  jz      short loc_1800519A4
0x18005199a  mov     ebx, 80020005h
0x18005199f  jmp     loc_180051A47
0x1800519a4  mov     eax, 48h ; 'H'
0x1800519a9  lea     rcx, [rbp+bstrString]; struct tagPROPVARIANT *
0x1800519ad  mov     word ptr [rbp+var_58], ax
0x1800519b1  mov     r8d, 8; unsigned __int16
0x1800519b7  mov     rax, [rdx+8]
0x1800519bb  lea     rdx, [rbp+var_58]; struct tagPROPVARIANT *
0x1800519bf  mov     qword ptr [rbp+var_58+8], rax
0x1800519c3  call    ?HrCLSIDToStr@@YAJPEAUtagPROPVARIANT@@PEBU1@G@Z; HrCLSIDToStr(tagPROPVARIANT *,tagPROPVARIANT const *,ushort)
0x1800519c8  mov     ebx, eax
0x1800519ca  test    eax, eax
0x1800519cc  jnz     short loc_180051A47
0x1800519ce  mov     rdx, [rdi+8]
0x1800519d2  lea     r8d, [rax+0Dh]; unsigned __int16
0x1800519d6  lea     rcx, [rbp+var_30+8]; struct tagPROPVARIANT *
0x1800519da  mov     rdx, [rdx+10h]; struct IUnknown *
0x1800519de  call    ?HrGetValFromUNK@@YAJPEAUtagPROPVARIANT@@PEAUIUnknown@@G@Z; HrGetValFromUNK(tagPROPVARIANT *,IUnknown *,ushort)
0x1800519e3  mov     ebx, eax
0x1800519e5  test    eax, eax
0x1800519e7  jnz     short loc_180051A47
0x1800519e9  lea     ecx, [rax+0Ch]; vt
0x1800519ec  mov     qword ptr [rbp+rgsabound.cElements], 2
0x1800519f4  lea     r8, [rbp+rgsabound]; rgsabound
0x1800519f8  lea     edx, [rax+1]; cDims
0x1800519fb  call    cs:__imp_SafeArrayCreate
0x180051a01  mov     rcx, rax
0x180051a04  test    rax, rax
0x180051a07  jnz     short loc_180051A10
0x180051a09  mov     ebx, 8007000Eh
0x180051a0e  jmp     short loc_180051A47
0x180051a10  mov     rax, [rax+10h]
0x180051a14  movups  xmm0, xmmword ptr [rbp+bstrString]
0x180051a18  movups  xmm1, xmmword ptr [rbp+var_30]
0x180051a1c  movups  xmmword ptr [rax], xmm0
0x180051a1f  movups  xmm0, xmmword ptr [rbp+var_30+10h]
0x180051a23  movups  xmmword ptr [rax+10h], xmm1
0x180051a27  movups  xmmword ptr [rax+20h], xmm0
0x180051a2b  mov     [rsi+8], rcx
0x180051a2f  xor     ecx, ecx
0x180051a31  lea     rax, [rcx+rcx*2]
0x180051a35  inc     rcx
0x180051a38  mov     [rbp+rax*8+bstrString+8], 0
0x180051a41  cmp     rcx, 2
0x180051a45  jnz     short loc_180051A31
0x180051a47  mov     rcx, [rbp+bstrString+8]; bstrString
0x180051a4b  test    rcx, rcx
0x180051a4e  jz      short loc_180051A56
0x180051a50  call    cs:__imp_SysFreeString
0x180051a56  mov     rcx, qword ptr [rbp+var_30+10h]
0x180051a5a  test    rcx, rcx
0x180051a5d  jz      short loc_180051A6B
0x180051a5f  mov     rax, [rcx]
0x180051a62  mov     rax, [rax+10h]
0x180051a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a6b  mov     eax, ebx
0x180051a6d  add     rsp, 78h
0x180051a71  pop     rdi
0x180051a72  pop     rsi
0x180051a73  pop     rbx
0x180051a74  pop     rbp
0x180051a75  retn
```
