# JoltProperties::AddProperty(JoltProperty *)

- ea: `0x1001f8e0`
- end: `0x1001fad4`
- name: `?AddProperty@JoltProperties@@QAEJPAVJoltProperty@@@Z`
- size: `500`
- prototype: `int __thiscall(JoltProperties *__hidden this, struct JoltProperty *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x100148a0`

## callees

- `0x1001c6d0`
- `0x1001f8e0`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`
- `0x1004d8cb`

## import_xrefs

- `OLEAUT32!__imp__VariantCopy@8` at `0x1001f9a1`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1001fa54`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1001f9a1`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1001fa54`

## pseudocode

```c
HRESULT __thiscall JoltProperties::AddProperty(JoltProperties *this, const VARIANTARG *a2)
{
  int v3; // ecx
  unsigned int v4; // esi
  int v5; // eax
  bool v6; // cf
  size_t v7; // eax
  unsigned int *v8; // eax
  void (__thiscall ***v9)(_DWORD, int); // edi
  unsigned int v10; // ecx
  _DWORD *v11; // eax
  int v12; // ecx
  int v13; // esi
  HRESULT result; // eax
  void (__thiscall ***v15)(_DWORD, int); // eax
  _DWORD *v16; // esi
  int v17; // edi
  _DWORD *Block; // [esp+10h] [ebp-1Ch]
  unsigned int v19; // [esp+14h] [ebp-18h]
  HRESULT v20; // [esp+1Ch] [ebp-10h]

  v3 = *((_DWORD *)this + 2);
  if ( v3 != *((_DWORD *)this + 3) )
  {
    v16 = (_DWORD *)((char *)this + 16);
    goto LABEL_21;
  }
  v4 = v3 + 16;
  v5 = 48 * (v3 + 16);
  if ( !is_mul_ok(0x30u, v3 + 16) )
    v5 = -1;
  v6 = __CFADD__(v5, 4);
  v7 = v5 + 4;
  if ( v6 )
    v7 = -1;
  v8 = (unsigned int *)operator new(v7);
  if ( !v8 )
  {
    v9 = 0;
    goto LABEL_19;
  }
  v9 = (void (__thiscall ***)(_DWORD, int))(v8 + 1);
  *v8 = v4;
  `eh vector constructor iterator'(
    v8 + 1,
    0x30u,
    v4,
    (void (__thiscall *)(void *))JoltProperty::JoltProperty,
    (void (__thiscall *)(void *))JoltColumnProperty::~JoltColumnProperty);
  if ( !v9 )
  {
LABEL_19:
    result = -2147024882;
    v16 = (_DWORD *)((char *)this + 16);
    v20 = -2147024882;
    goto LABEL_24;
  }
  v10 = 0;
  v19 = 0;
  if ( *((_DWORD *)this + 2) )
  {
    v11 = (_DWORD *)((char *)this + 16);
    while ( 1 )
    {
      v12 = 12 * v10;
      v13 = v12 * 4 + *v11;
      v9[v12 + 2] = *(void (__thiscall ***)(_DWORD, int))(v13 + 8);
      Block = &v9[v12];
      result = VariantCopy((VARIANTARG *)&v9[v12 + 4], (const VARIANTARG *)(v13 + 16));
      v20 = result;
      if ( result < 0 )
        break;
      Block[8] = *(_DWORD *)(v13 + 32);
      Block[10] = *(_DWORD *)(v13 + 40);
      Block[9] = *(_DWORD *)(v13 + 36);
      v11 = (_DWORD *)((char *)this + 16);
      v10 = v19 + 1;
      v19 = v10;
      if ( v10 >= *((_DWORD *)this + 2) )
        goto LABEL_12;
    }
    v16 = (_DWORD *)((char *)this + 16);
    goto LABEL_24;
  }
LABEL_12:
  v15 = (void (__thiscall ***)(_DWORD, int))*((_DWORD *)this + 4);
  v16 = (_DWORD *)((char *)this + 16);
  if ( !v15 )
    goto LABEL_17;
  if ( !*(v15 - 1) )
  {
    operator delete(v15 - 1);
LABEL_17:
    v3 = *((_DWORD *)this + 2);
    *v16 = v9;
    *((_DWORD *)this + 3) = v3 + 16;
    goto LABEL_21;
  }
  (**v15)(v15, 3);
  v3 = *((_DWORD *)this + 2);
  v16 = (_DWORD *)((char *)this + 16);
  *((_DWORD *)this + 4) = v9;
  *((_DWORD *)this + 3) = v3 + 16;
LABEL_21:
  v17 = *v16 + 48 * v3;
  *(_DWORD *)(v17 + 8) = a2->lVal;
  result = VariantCopy((VARIANTARG *)(v17 + 16), a2 + 1);
  v20 = result;
  if ( result >= 0 )
  {
    *(_DWORD *)(v17 + 32) = *(_DWORD *)&a2[2].vt;
    *(_DWORD *)(v17 + 40) = a2[2].lVal;
    *(_DWORD *)(v17 + 36) = a2[2].decVal.Hi32;
    ++*((_DWORD *)this + 2);
    return result;
  }
  v9 = 0;
LABEL_24:
  if ( (void (__thiscall ***)(_DWORD, int))*v16 == v9 && v9 )
  {
    if ( *(v9 - 1) )
      (**v9)(v9, 3);
    else
      operator delete(v9 - 1);
    return v20;
  }
  return result;
}

```

## disassembly

```asm
0x1001f8e0  mov     edi, edi
0x1001f8e2  push    ebp
0x1001f8e3  mov     ebp, esp
0x1001f8e5  push    0FFFFFFFFh
0x1001f8e7  push    offset ?AddProperty@JoltProperties@@QAEJPAVJoltProperty@@@Z_SEH
0x1001f8ec  mov     eax, large fs:0
0x1001f8f2  push    eax
0x1001f8f3  sub     esp, 10h
0x1001f8f6  push    ebx
0x1001f8f7  push    esi
0x1001f8f8  push    edi
0x1001f8f9  mov     eax, ___security_cookie
0x1001f8fe  xor     eax, ebp
0x1001f900  push    eax
0x1001f901  lea     eax, [ebp+var_C]
0x1001f904  mov     large fs:0, eax
0x1001f90a  mov     ebx, ecx
0x1001f90c  mov     ecx, [ebx+8]
0x1001f90f  cmp     ecx, [ebx+0Ch]
0x1001f912  jnz     loc_1001FA38
0x1001f918  lea     esi, [ecx+10h]
0x1001f91b  mov     ecx, 30h ; '0'
0x1001f920  mov     eax, esi
0x1001f922  mul     ecx
0x1001f924  mov     ecx, 0FFFFFFFFh
0x1001f929  cmovb   eax, ecx
0x1001f92c  add     eax, 4
0x1001f92f  cmovb   eax, ecx
0x1001f932  push    eax; Size
0x1001f933  call    ??2@YAPAXI@Z; operator new(uint)
0x1001f938  add     esp, 4
0x1001f93b  mov     [ebp+Block], eax
0x1001f93e  mov     [ebp+var_4], 0
0x1001f945  test    eax, eax
0x1001f947  jz      loc_1001FA29
0x1001f94d  push    offset ??1JoltColumnProperty@@UAE@XZ; void (__thiscall *)(void *)
0x1001f952  push    offset ??0JoltProperty@@QAE@XZ; void (__thiscall *)(void *)
0x1001f957  push    esi; unsigned int
0x1001f958  lea     edi, [eax+4]
0x1001f95b  mov     [eax], esi
0x1001f95d  push    30h ; '0'; unsigned int
0x1001f95f  push    edi; void *
0x1001f960  call    ??_L@YGXPAXIIP6EX0@Z1@Z; `eh vector constructor iterator'(void *,uint,uint,void (*)(void *),void (*)(void *))
0x1001f965  test    edi, edi
0x1001f967  jz      loc_1001FA2B
0x1001f96d  xor     ecx, ecx
0x1001f96f  mov     [ebp+var_18], ecx
0x1001f972  cmp     [ebx+8], ecx
0x1001f975  jbe     short loc_1001F9D2
0x1001f977  lea     eax, [ebx+10h]
0x1001f97a  mov     [ebp+var_14], eax
0x1001f97d  nop     dword ptr [eax]
0x1001f980  mov     esi, [eax]
0x1001f982  lea     ecx, [ecx+ecx*2]
0x1001f985  shl     ecx, 4
0x1001f988  add     esi, ecx
0x1001f98a  lea     edx, [ecx+edi]
0x1001f98d  mov     eax, [esi+8]
0x1001f990  mov     [ecx+edi+8], eax
0x1001f994  lea     eax, [esi+10h]
0x1001f997  push    eax; pvargSrc
0x1001f998  lea     eax, [edi+10h]
0x1001f99b  mov     [ebp+Block], edx
0x1001f99e  add     eax, ecx
0x1001f9a0  push    eax; pvargDest
0x1001f9a1  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x1001f9a7  mov     [ebp+var_10], eax
0x1001f9aa  test    eax, eax
0x1001f9ac  js      short loc_1001FA0E
0x1001f9ae  mov     ecx, [ebp+Block]
0x1001f9b1  mov     eax, [esi+20h]
0x1001f9b4  mov     [ecx+20h], eax
0x1001f9b7  mov     eax, [esi+28h]
0x1001f9ba  mov     [ecx+28h], eax
0x1001f9bd  mov     eax, [esi+24h]
0x1001f9c0  mov     [ecx+24h], eax
0x1001f9c3  lea     eax, [ebx+10h]
0x1001f9c6  mov     ecx, [ebp+var_18]
0x1001f9c9  inc     ecx
0x1001f9ca  mov     [ebp+var_18], ecx
0x1001f9cd  cmp     ecx, [ebx+8]
0x1001f9d0  jb      short loc_1001F980
0x1001f9d2  mov     eax, [ebx+10h]
0x1001f9d5  lea     esi, [ebx+10h]
0x1001f9d8  mov     [ebp+var_14], esi
0x1001f9db  mov     [ebp+Block], eax
0x1001f9de  test    eax, eax
0x1001f9e0  jz      short loc_1001FA1C
0x1001f9e2  cmp     dword ptr [eax-4], 0
0x1001f9e6  lea     ecx, [eax-4]
0x1001f9e9  jz      short loc_1001FA13
0x1001f9eb  mov     eax, [eax]
0x1001f9ed  push    3
0x1001f9ef  mov     esi, [eax]
0x1001f9f1  mov     ecx, esi
0x1001f9f3  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001f9f9  mov     ecx, [ebp+Block]
0x1001f9fc  call    esi
0x1001f9fe  mov     ecx, [ebx+8]
0x1001fa01  mov     esi, [ebp+var_14]
0x1001fa04  lea     eax, [ecx+10h]
0x1001fa07  mov     [esi], edi
0x1001fa09  mov     [ebx+0Ch], eax
0x1001fa0c  jmp     short loc_1001FA3B
0x1001fa0e  mov     esi, [ebp+var_14]
0x1001fa11  jmp     short loc_1001FA8F
0x1001fa13  push    ecx; Block
0x1001fa14  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001fa19  add     esp, 4
0x1001fa1c  mov     ecx, [ebx+8]
0x1001fa1f  mov     [esi], edi
0x1001fa21  lea     eax, [ecx+10h]
0x1001fa24  mov     [ebx+0Ch], eax
0x1001fa27  jmp     short loc_1001FA3B
0x1001fa29  xor     edi, edi
0x1001fa2b  mov     eax, 8007000Eh
0x1001fa30  lea     esi, [ebx+10h]
0x1001fa33  mov     [ebp+var_10], eax
0x1001fa36  jmp     short loc_1001FA8F
0x1001fa38  lea     esi, [ebx+10h]
0x1001fa3b  lea     edi, [ecx+ecx*2]
0x1001fa3e  mov     ecx, [ebp+arg_0]
0x1001fa41  shl     edi, 4
0x1001fa44  add     edi, [esi]
0x1001fa46  mov     eax, [ecx+8]
0x1001fa49  mov     [edi+8], eax
0x1001fa4c  lea     eax, [ecx+10h]
0x1001fa4f  push    eax; pvargSrc
0x1001fa50  lea     eax, [edi+10h]
0x1001fa53  push    eax; pvargDest
0x1001fa54  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x1001fa5a  mov     [ebp+var_10], eax
0x1001fa5d  test    eax, eax
0x1001fa5f  js      short loc_1001FA8D
0x1001fa61  mov     edx, [ebp+arg_0]
0x1001fa64  mov     ecx, [edx+20h]
0x1001fa67  mov     [edi+20h], ecx
0x1001fa6a  mov     ecx, [edx+28h]
0x1001fa6d  mov     [edi+28h], ecx
0x1001fa70  mov     ecx, [edx+24h]
0x1001fa73  mov     [edi+24h], ecx
0x1001fa76  inc     dword ptr [ebx+8]
0x1001fa79  mov     ecx, [ebp+var_C]
0x1001fa7c  mov     large fs:0, ecx
0x1001fa83  pop     ecx
0x1001fa84  pop     edi
0x1001fa85  pop     esi
0x1001fa86  pop     ebx
0x1001fa87  mov     esp, ebp
0x1001fa89  pop     ebp
0x1001fa8a  retn    4
0x1001fa8d  xor     edi, edi
0x1001fa8f  cmp     [esi], edi
0x1001fa91  jnz     short loc_1001FAC0
0x1001fa93  test    edi, edi
0x1001fa95  jz      short loc_1001FAC0
0x1001fa97  cmp     dword ptr [edi-4], 0
0x1001fa9b  lea     eax, [edi-4]
0x1001fa9e  jz      short loc_1001FAB4
0x1001faa0  mov     eax, [edi]
0x1001faa2  push    3
0x1001faa4  mov     esi, [eax]
0x1001faa6  mov     ecx, esi
0x1001faa8  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001faae  mov     ecx, edi
0x1001fab0  call    esi
0x1001fab2  jmp     short loc_1001FABD
0x1001fab4  push    eax; Block
0x1001fab5  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001faba  add     esp, 4
0x1001fabd  mov     eax, [ebp+var_10]
0x1001fac0  mov     ecx, [ebp+var_C]
0x1001fac3  mov     large fs:0, ecx
0x1001faca  pop     ecx
0x1001facb  pop     edi
0x1001facc  pop     esi
0x1001facd  pop     ebx
0x1001face  mov     esp, ebp
0x1001fad0  pop     ebp
0x1001fad1  retn    4
0x1004e790  mov     eax, [ebp+Block]
0x1004e793  push    eax; Block
0x1004e794  call    ??3@YAXPAX@Z; operator delete(void *)
0x1004e799  pop     ecx
0x1004e79a  retn
0x1004e7a0  nop
0x1004e7a1  nop
0x1004e7a2  mov     edx, [esp-4+arg_4]
0x1004e7a6  lea     eax, [edx+0Ch]
0x1004e7a9  mov     ecx, [edx-20h]
0x1004e7ac  xor     ecx, eax; StackCookie
0x1004e7ae  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e7b3  mov     eax, offset stru_1004FB0C
0x1004e7b8  jmp     ___CxxFrameHandler3
```
