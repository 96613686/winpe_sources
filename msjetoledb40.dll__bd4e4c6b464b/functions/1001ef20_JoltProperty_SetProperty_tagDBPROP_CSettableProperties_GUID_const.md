# JoltProperty::SetProperty(tagDBPROP *,CSettableProperties *,_GUID const &)

- ea: `0x1001ef20`
- end: `0x1001f121`
- name: `?SetProperty@JoltProperty@@UAEJPAUtagDBPROP@@PAVCSettableProperties@@ABU_GUID@@@Z`
- size: `513`
- prototype: `int __thiscall(JoltProperty *__hidden this, struct tagDBPROP *, struct CSettableProperties *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1001f130`

## callees

- `0x1001c6d0`
- `0x1001ef20`
- `0x10025630`
- `0x1004d420`

## import_xrefs

- `OLEAUT32!__imp__VariantCopy@8` at `0x1001f09e`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1001f09e`

## pseudocode

```c
HRESULT __userpurge JoltProperty::SetProperty@<eax>(
        JoltProperty *this@<ecx>,
        int a2@<ebp>,
        struct tagVARIANT *a3@<edi>,
        struct tagVARIANT *a4@<esi>,
        struct tagDBPROP *a5,
        struct CSettableProperties *a6,
        const struct _GUID *a7)
{
  struct tagDBPROP *v7; // eax
  DBPROPOPTIONS dwOptions; // esi
  HRESULT v9; // edx
  DBPROPSTATUS *p_dwStatus; // esi
  DBPROPSTATUS *v11; // edi
  int dwPropertyID; // esi
  const GUID *v14; // edx
  __int128 *v15; // esi
  bool v16; // cf
  struct tagDBPROP *v17; // esi
  int v18; // ecx
  unsigned int v19; // eax
  int v20; // ecx
  bool v21; // zf
  int IsEqualVariants; // eax
  VARTYPE vt; // [esp-48h] [ebp-54h]
  VARIANTARG *v26; // [esp-40h] [ebp-4Ch]
  __int16 v27; // [esp-30h] [ebp-3Ch]
  unsigned int v29; // [esp-28h] [ebp-34h] BYREF
  struct tagDBPROP *v30; // [esp-24h] [ebp-30h]
  __int128 v31; // [esp-20h] [ebp-2Ch] BYREF
  int v32; // [esp+0h] [ebp-Ch]
  void *v33; // [esp+4h] [ebp-8h]
  void *retaddr; // [esp+Ch] [ebp+0h]

  v32 = a2;
  v33 = retaddr;
  v7 = a5;
  dwOptions = a5->dwOptions;
  v9 = 0;
  v30 = a5;
  if ( dwOptions >= 2 )
  {
    p_dwStatus = &a5->dwStatus;
    v9 = -2147217887;
    a5->dwStatus = 3;
    goto LABEL_9;
  }
  v11 = &a5->dwStatus;
  a5->dwStatus = 0;
  vt = a5->vValue.vt;
  if ( !vt )
  {
    if ( (*((_DWORD *)this + 8) & 0x400) != 0 )
    {
      v9 = (*(int (__thiscall **)(JoltProperty *, _DWORD))(*(_DWORD *)this + 12))(this, *((_DWORD *)this + 9));
      p_dwStatus = &a5->dwStatus;
      if ( v9 < 0 )
      {
LABEL_8:
        v7 = v30;
        goto LABEL_9;
      }
      *((_DWORD *)this + 10) |= 1u;
    }
    p_dwStatus = &a5->dwStatus;
    goto LABEL_8;
  }
  v26 = (VARIANTARG *)((char *)this + 16);
  v27 = *((_WORD *)this + 8);
  v7 = v30;
  v31 = (__int128)*a7;
  dwPropertyID = v30->dwPropertyID;
  if ( v30->dwPropertyID == 27 )
  {
    v14 = &DBPROPSET_COLUMN;
    v29 = 12;
    v15 = &v31;
    while ( v14->Data1 == *(_DWORD *)v15 )
    {
      v14 = (const GUID *)((char *)v14 + 4);
      v15 = (__int128 *)((char *)v15 + 4);
      v16 = v29 < 4;
      v29 -= 4;
      if ( v16 )
        goto LABEL_16;
    }
    v7 = v30;
    v9 = 0;
    dwPropertyID = 27;
  }
  v11 = &v7->dwStatus;
  if ( v27 == vt || dwPropertyID == 27 )
  {
LABEL_16:
    if ( (*((_DWORD *)this + 8) & 0x400) != 0 )
    {
      v29 = 2;
      if ( !a6
        || (*(int (__thiscall **)(struct CSettableProperties *, const struct _GUID *, struct tagDBPROP *, unsigned int *))(*(_DWORD *)a6 + 8))(
             a6,
             a7,
             v30,
             &v29) )
      {
        v9 = VariantCopy(v26, &a5->vValue);
        p_dwStatus = v11;
        if ( v9 >= 0 )
        {
          v17 = v30;
          v18 = *((_DWORD *)this + 10) | 1;
          *((_DWORD *)this + 10) = v18;
          v19 = v18 & 0xFFFFFFFD;
          v20 = v18 | 2;
          v21 = v17->dwOptions == 0;
          p_dwStatus = v11;
          if ( !v21 )
            v20 = v19;
          *((_DWORD *)this + 10) = v20;
        }
      }
      else
      {
        p_dwStatus = v11;
        *v11 = v29;
        v9 = 0;
      }
      goto LABEL_8;
    }
    p_dwStatus = v11;
    IsEqualVariants = fIsEqualVariants(a3, a4);
    v9 = 0;
    v21 = IsEqualVariants == 0;
    v7 = v30;
    if ( v21 )
      *v11 = 6;
  }
  else
  {
    *v11 = 2;
    p_dwStatus = &v7->dwStatus;
  }
LABEL_9:
  if ( !*p_dwStatus )
    return v9;
  if ( v7->dwOptions == 1 )
    return 265946;
  return -2147217887;
}

```

## disassembly

```asm
0x1001ef20  mov     edi, edi
0x1001ef22  push    ebx
0x1001ef23  mov     ebx, esp
0x1001ef25  sub     esp, 8
0x1001ef28  and     esp, 0FFFFFFF0h
0x1001ef2b  add     esp, 4
0x1001ef2e  push    ebp
0x1001ef2f  mov     ebp, [ebx+4]
0x1001ef32  mov     [esp+0Ch+var_8], ebp
0x1001ef36  mov     ebp, esp
0x1001ef38  sub     esp, 48h
0x1001ef3b  mov     eax, ___security_cookie
0x1001ef40  xor     eax, ebp
0x1001ef42  mov     [ebp-4], eax
0x1001ef45  mov     eax, [ebx+8]
0x1001ef48  mov     edx, [ebx+0Ch]
0x1001ef4b  mov     [ebp-38h], edx
0x1001ef4e  mov     edx, [ebx+10h]
0x1001ef51  push    esi; struct tagVARIANT *
0x1001ef52  mov     esi, [eax+4]
0x1001ef55  mov     [ebp-34h], edx
0x1001ef58  xor     edx, edx
0x1001ef5a  mov     [ebp-2Ch], ecx
0x1001ef5d  mov     [ebp-24h], eax
0x1001ef60  push    edi; struct tagVARIANT *
0x1001ef61  test    esi, esi
0x1001ef63  jz      short loc_1001EF7A
0x1001ef65  cmp     esi, 1
0x1001ef68  jz      short loc_1001EF7A
0x1001ef6a  lea     esi, [eax+8]
0x1001ef6d  mov     edx, 80040E21h
0x1001ef72  mov     dword ptr [esi], 3
0x1001ef78  jmp     short loc_1001EFC6
0x1001ef7a  lea     edi, [eax+8]
0x1001ef7d  add     eax, 24h ; '$'
0x1001ef80  mov     [edi], edx
0x1001ef82  mov     [ebp-3Ch], eax
0x1001ef85  movzx   eax, word ptr [eax]
0x1001ef88  mov     esi, eax
0x1001ef8a  mov     [ebp-48h], esi
0x1001ef8d  xor     esi, esi
0x1001ef8f  cmp     si, ax
0x1001ef92  jnz     short loc_1001EFE5
0x1001ef94  test    dword ptr [ecx+20h], 400h
0x1001ef9b  jz      short loc_1001EFC1
0x1001ef9d  mov     eax, [ecx]
0x1001ef9f  push    dword ptr [ecx+24h]
0x1001efa2  mov     esi, [eax+0Ch]
0x1001efa5  mov     ecx, esi
0x1001efa7  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001efad  mov     ecx, [ebp-2Ch]
0x1001efb0  call    esi
0x1001efb2  mov     edx, eax
0x1001efb4  mov     esi, edi
0x1001efb6  test    edx, edx
0x1001efb8  js      short loc_1001EFC3
0x1001efba  mov     eax, [ebp-2Ch]
0x1001efbd  or      dword ptr [eax+28h], 1
0x1001efc1  mov     esi, edi
0x1001efc3  mov     eax, [ebp-24h]
0x1001efc6  cmp     dword ptr [esi], 0
0x1001efc9  jz      loc_1001F10A
0x1001efcf  mov     eax, [eax+4]
0x1001efd2  sub     eax, 1
0x1001efd5  jz      loc_1001F103
0x1001efdb  mov     eax, 80040E21h
0x1001efe0  jmp     loc_1001F10C
0x1001efe5  lea     eax, [ecx+10h]
0x1001efe8  mov     [ebp-40h], eax
0x1001efeb  movzx   eax, word ptr [eax]
0x1001efee  mov     [ebp-30h], eax
0x1001eff1  mov     eax, [ebp-34h]
0x1001eff4  movups  xmm0, xmmword ptr [eax]
0x1001eff7  mov     eax, [ebp-24h]
0x1001effa  movups  xmmword ptr [ebp-20h], xmm0
0x1001effe  mov     esi, [eax]
0x1001f000  mov     [ebp-44h], esi
0x1001f003  cmp     esi, 1Bh
0x1001f006  jnz     short loc_1001F07A
0x1001f008  mov     edx, offset _DBPROPSET_COLUMN
0x1001f00d  mov     dword ptr [ebp-28h], 0Ch
0x1001f014  lea     esi, [ebp-20h]
0x1001f017  mov     eax, [edx]
0x1001f019  cmp     eax, [esi]
0x1001f01b  jnz     short loc_1001F072
0x1001f01d  add     edx, 4
0x1001f020  add     esi, 4
0x1001f023  sub     dword ptr [ebp-28h], 4
0x1001f027  jnb     short loc_1001F017
0x1001f029  test    dword ptr [ecx+20h], 400h
0x1001f030  jz      loc_1001F0DE
0x1001f036  mov     eax, [ebp-38h]
0x1001f039  mov     dword ptr [ebp-28h], 2
0x1001f040  test    eax, eax
0x1001f042  jz      short loc_1001F098
0x1001f044  mov     eax, [eax]
0x1001f046  mov     esi, [eax+8]
0x1001f049  lea     eax, [ebp-28h]
0x1001f04c  push    eax
0x1001f04d  push    dword ptr [ebp-24h]
0x1001f050  mov     ecx, esi
0x1001f052  push    dword ptr [ebp-34h]
0x1001f055  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001f05b  mov     ecx, [ebp-38h]
0x1001f05e  call    esi
0x1001f060  test    eax, eax
0x1001f062  jnz     short loc_1001F098
0x1001f064  mov     eax, [ebp-28h]
0x1001f067  mov     esi, edi
0x1001f069  mov     [edi], eax
0x1001f06b  xor     edx, edx
0x1001f06d  jmp     loc_1001EFC3
0x1001f072  mov     eax, [ebp-24h]
0x1001f075  xor     edx, edx
0x1001f077  mov     esi, [ebp-44h]
0x1001f07a  mov     edi, [ebp-48h]
0x1001f07d  cmp     [ebp-30h], di
0x1001f081  lea     edi, [eax+8]
0x1001f084  jz      short loc_1001F029
0x1001f086  cmp     esi, 1Bh
0x1001f089  jz      short loc_1001F029
0x1001f08b  mov     dword ptr [edi], 2
0x1001f091  mov     esi, edi
0x1001f093  jmp     loc_1001EFC6
0x1001f098  push    dword ptr [ebp-3Ch]; pvargSrc
0x1001f09b  push    dword ptr [ebp-40h]; pvargDest
0x1001f09e  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x1001f0a4  mov     edx, eax
0x1001f0a6  mov     esi, edi
0x1001f0a8  mov     [ebp-30h], edx
0x1001f0ab  test    edx, edx
0x1001f0ad  js      loc_1001EFC3
0x1001f0b3  mov     edx, [ebp-2Ch]
0x1001f0b6  mov     esi, [ebp-24h]
0x1001f0b9  mov     ecx, [edx+28h]
0x1001f0bc  or      ecx, 1
0x1001f0bf  mov     [edx+28h], ecx
0x1001f0c2  mov     eax, ecx
0x1001f0c4  and     eax, 0FFFFFFFDh
0x1001f0c7  or      ecx, 2
0x1001f0ca  cmp     dword ptr [esi+4], 0
0x1001f0ce  mov     esi, edi
0x1001f0d0  cmovnz  ecx, eax
0x1001f0d3  mov     [edx+28h], ecx
0x1001f0d6  mov     edx, [ebp-30h]
0x1001f0d9  jmp     loc_1001EFC3
0x1001f0de  mov     edx, [ebp-3Ch]
0x1001f0e1  mov     esi, edi
0x1001f0e3  mov     ecx, [ebp-40h]
0x1001f0e6  call    ?fIsEqualVariants@@YGHAAUtagVARIANT@@0@Z; fIsEqualVariants(tagVARIANT &,tagVARIANT &)
0x1001f0eb  xor     edx, edx
0x1001f0ed  test    eax, eax
0x1001f0ef  mov     eax, [ebp-24h]
0x1001f0f2  jnz     loc_1001EFC6
0x1001f0f8  mov     dword ptr [edi], 6
0x1001f0fe  jmp     loc_1001EFC6
0x1001f103  mov     eax, 40EDAh
0x1001f108  jmp     short loc_1001F10C
0x1001f10a  mov     eax, edx
0x1001f10c  mov     ecx, [ebp-4]
0x1001f10f  pop     edi
0x1001f110  xor     ecx, ebp; StackCookie
0x1001f112  pop     esi
0x1001f113  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001f118  mov     esp, ebp
0x1001f11a  pop     ebp
0x1001f11b  mov     esp, ebx
0x1001f11d  pop     ebx
0x1001f11e  retn    0Ch
```
