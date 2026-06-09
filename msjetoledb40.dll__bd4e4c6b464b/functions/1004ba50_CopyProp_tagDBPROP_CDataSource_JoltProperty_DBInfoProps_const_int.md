# CopyProp(tagDBPROP *,CDataSource *,JoltProperty *,DBInfoProps const *,int)

- ea: `0x1004ba50`
- end: `0x1004bb90`
- name: `?CopyProp@@YGJPAUtagDBPROP@@PAVCDataSource@@PAVJoltProperty@@PBUDBInfoProps@@H@Z`
- size: `320`
- prototype: `int __stdcall(struct tagDBPROP *, struct CDataSource *, struct JoltProperty *, const struct DBInfoProps *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1004bbb0`
- `0x1004c660`

## callees

- `0x1001c6d0`
- `0x1004ba50`

## import_xrefs

- `OLEAUT32!__imp__SysAllocString@4` at `0x1004bb75`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1004bb75`
- `OLEAUT32!__imp__VariantInit@4` at `0x1004ba6b`
- `OLEAUT32!__imp__VariantInit@4` at `0x1004bace`
- `OLEAUT32!__imp__VariantInit@4` at `0x1004ba6b`
- `OLEAUT32!__imp__VariantInit@4` at `0x1004bace`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1004baa2`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1004baa2`

## pseudocode

```c
int __userpurge CopyProp@<eax>(
        int a1@<edx>,
        int a2@<ecx>,
        struct tagDBPROP *a3,
        struct CDataSource *a4,
        struct JoltProperty *a5,
        const struct DBInfoProps *a6,
        int a7)
{
  VARIANTARG *v8; // esi
  int result; // eax
  struct CDataSource *v10; // edi
  VARTYPE v11; // ax
  BSTR v12; // eax
  int v14; // [esp+10h] [ebp-4h]

  v14 = 0;
  v8 = (VARIANTARG *)(a2 + 36);
  VariantInit((VARIANTARG *)(a2 + 36));
  if ( a5 == (struct JoltProperty *)1 )
  {
    if ( !a3 )
    {
      result = 0;
      *(_DWORD *)a2 = *(_DWORD *)a4;
      *(_DWORD *)(a2 + 4) = 0;
      *(_DWORD *)(a2 + 8) = 1;
LABEL_12:
      *(DBID *)(a2 + 12) = DB_NULLID;
      return result;
    }
    VariantCopy(v8, (const VARIANTARG *)(&a3->colid.uGuid.pguid + 1));
    v10 = *(struct CDataSource **)&a3->vValue.vt;
    *(_DWORD *)(a2 + 4) = (a3->vValue.decVal.Hi32 & 2) == 0;
LABEL_11:
    *(_DWORD *)a2 = *(_DWORD *)v10;
    result = v14;
    *(_DWORD *)(a2 + 8) = 0;
    goto LABEL_12;
  }
  v10 = a4;
  *(_DWORD *)(a2 + 4) = 0;
  if ( *((_DWORD *)a4 + 3) )
  {
    VariantInit(v8);
    result = (*((int (__thiscall **)(_DWORD, int, int))a4 + 3))(*((_DWORD *)a4 + 3), a1, a2 + 36);
    v14 = result;
    if ( result < 0 )
      return result;
    *(_WORD *)(a2 + 36) = *((_WORD *)a4 + 2);
    goto LABEL_11;
  }
  switch ( *((_WORD *)a4 + 2) )
  {
    case 2:
    case 0xB:
      *(_WORD *)(a2 + 44) = *((_WORD *)a4 + 4);
      v11 = *((_WORD *)a4 + 2);
      goto LABEL_10;
    case 3:
      *(_DWORD *)(a2 + 44) = *((_DWORD *)a4 + 2);
      v11 = *((_WORD *)a4 + 2);
      goto LABEL_10;
    case 8:
      v8->vt = *((_WORD *)a4 + 2);
      if ( !*((_DWORD *)a4 + 4) )
      {
        v11 = 0;
LABEL_10:
        v8->vt = v11;
        goto LABEL_11;
      }
      v8->vt = 8;
      v12 = SysAllocString(*((const OLECHAR **)a4 + 4));
      *(_DWORD *)(a2 + 44) = v12;
      if ( v12 )
        goto LABEL_11;
      result = -2147024882;
      break;
    default:
      goto LABEL_11;
  }
  return result;
}

```

## disassembly

```asm
0x1004ba50  mov     edi, edi
0x1004ba52  push    ebp
0x1004ba53  mov     ebp, esp
0x1004ba55  sub     esp, 8
0x1004ba58  push    ebx
0x1004ba59  mov     ebx, ecx
0x1004ba5b  mov     [ebp+var_8], edx
0x1004ba5e  push    esi
0x1004ba5f  push    edi
0x1004ba60  mov     [ebp+var_4], 0
0x1004ba67  lea     esi, [ebx+24h]
0x1004ba6a  push    esi; pvarg
0x1004ba6b  call    ds:__imp__VariantInit@4; VariantInit(x)
0x1004ba71  mov     eax, [ebp+arg_8]
0x1004ba74  mov     edi, [ebp+arg_0]
0x1004ba77  cmp     eax, 1
0x1004ba7a  jnz     short loc_1004BABD
0x1004ba7c  test    edi, edi
0x1004ba7e  jnz     short loc_1004BA98
0x1004ba80  mov     eax, [ebp+arg_4]
0x1004ba83  mov     ecx, [eax]
0x1004ba85  xor     eax, eax
0x1004ba87  mov     [ebx], ecx
0x1004ba89  mov     [ebx+4], edi
0x1004ba8c  mov     dword ptr [ebx+8], 1
0x1004ba93  jmp     loc_1004BB2E
0x1004ba98  cmp     eax, 1
0x1004ba9b  jnz     short loc_1004BABD
0x1004ba9d  lea     eax, [edi+10h]
0x1004baa0  push    eax; pvargSrc
0x1004baa1  push    esi; pvargDest
0x1004baa2  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x1004baa8  mov     eax, [ebp+arg_0]
0x1004baab  mov     edi, [edi+24h]
0x1004baae  mov     eax, [eax+28h]
0x1004bab1  shr     eax, 1
0x1004bab3  not     eax
0x1004bab5  and     eax, 1
0x1004bab8  mov     [ebx+4], eax
0x1004babb  jmp     short def_1004BB0C; jumptable 1004BB0C default case, cases 4-7,9,10
0x1004babd  mov     edi, [ebp+arg_4]
0x1004bac0  mov     dword ptr [ebx+4], 0
0x1004bac7  cmp     dword ptr [edi+0Ch], 0
0x1004bacb  jz      short loc_1004BAF9
0x1004bacd  push    esi; pvarg
0x1004bace  call    ds:__imp__VariantInit@4; VariantInit(x)
0x1004bad4  mov     esi, [edi+0Ch]
0x1004bad7  lea     eax, [ebx+24h]
0x1004bada  push    eax
0x1004badb  push    [ebp+var_8]
0x1004bade  mov     ecx, esi
0x1004bae0  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004bae6  call    esi
0x1004bae8  mov     [ebp+var_4], eax
0x1004baeb  test    eax, eax
0x1004baed  js      short loc_1004BB46
0x1004baef  mov     ax, [edi+4]
0x1004baf3  mov     [ebx+24h], ax
0x1004baf7  jmp     short def_1004BB0C; jumptable 1004BB0C default case, cases 4-7,9,10
0x1004baf9  movzx   ecx, word ptr [edi+4]
0x1004bafd  lea     eax, [ecx-2]; switch 10 cases
0x1004bb00  cmp     eax, 9
0x1004bb03  ja      short def_1004BB0C; jumptable 1004BB0C default case, cases 4-7,9,10
0x1004bb05  movzx   eax, ds:byte_1004BBA0[eax]
0x1004bb0c  jmp     ds:jpt_1004BB0C[eax*4]; switch jump
0x1004bb13  mov     eax, [edi+8]; jumptable 1004BB0C case 3
0x1004bb16  mov     [ebx+2Ch], eax
0x1004bb19  mov     ax, [edi+4]
0x1004bb1d  mov     [esi], ax
0x1004bb20  mov     eax, [edi]; jumptable 1004BB0C default case, cases 4-7,9,10
0x1004bb22  mov     [ebx], eax
0x1004bb24  mov     eax, [ebp+var_4]
0x1004bb27  mov     dword ptr [ebx+8], 0
0x1004bb2e  movups  xmm0, xmmword ptr ds:_DB_NULLID.uGuid
0x1004bb35  movups  xmmword ptr [ebx+0Ch], xmm0
0x1004bb39  movq    xmm0, qword ptr ds:_DB_NULLID.eKind
0x1004bb41  movq    qword ptr [ebx+1Ch], xmm0
0x1004bb46  pop     edi
0x1004bb47  pop     esi
0x1004bb48  pop     ebx
0x1004bb49  mov     esp, ebp
0x1004bb4b  pop     ebp
0x1004bb4c  retn    0Ch
0x1004bb4f  movzx   eax, word ptr [edi+8]; jumptable 1004BB0C cases 2,11
0x1004bb53  mov     [ebx+2Ch], ax
0x1004bb57  movzx   eax, word ptr [edi+4]
0x1004bb5b  jmp     short loc_1004BB1D
0x1004bb5d  mov     [esi], cx; jumptable 1004BB0C case 8
0x1004bb60  cmp     dword ptr [edi+10h], 0
0x1004bb64  jnz     short loc_1004BB6A
0x1004bb66  xor     eax, eax
0x1004bb68  jmp     short loc_1004BB1D
0x1004bb6a  mov     eax, 8
0x1004bb6f  mov     [esi], ax
0x1004bb72  push    dword ptr [edi+10h]; psz
0x1004bb75  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x1004bb7b  mov     [ebx+2Ch], eax
0x1004bb7e  test    eax, eax
0x1004bb80  jnz     short def_1004BB0C; jumptable 1004BB0C default case, cases 4-7,9,10
0x1004bb82  pop     edi
0x1004bb83  pop     esi
0x1004bb84  mov     eax, 8007000Eh
0x1004bb89  pop     ebx
0x1004bb8a  mov     esp, ebp
0x1004bb8c  pop     ebp
0x1004bb8d  retn    0Ch
```
