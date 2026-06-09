# CCommand::CachePropertyInError(_GUID,JoltProperty *)

- ea: `0x100148a0`
- end: `0x10014a66`
- name: `?CachePropertyInError@CCommand@@QAEJU_GUID@@PAVJoltProperty@@@Z`
- size: `454`
- prototype: `int __thiscall(CCommand *__hidden this, struct _GUID, struct JoltProperty *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1004cc50`

## callees

- `0x100148a0`
- `0x10014a70`
- `0x1001c6d0`
- `0x1001f8e0`
- `0x1004ce5d`

## pseudocode

```c
HRESULT __thiscall CCommand::CachePropertyInError(CCommand *this, const VARIANTARG *a2, struct _GUID a3)
{
  _DWORD *v4; // ebx
  _DWORD *v5; // eax
  int v6; // edi
  int v7; // eax
  __int128 v8; // xmm0
  __int128 *v9; // edx
  unsigned int v10; // esi
  struct _GUID *v11; // eax
  bool v12; // cf
  CCommand *v13; // esi
  char *v15; // eax
  char *v16; // ecx
  int v17; // eax
  HRESULT v18; // ebx
  void (__thiscall ***v19)(int, int); // eax
  int v20; // eax
  JoltProperties *v21; // ecx
  __int128 v22; // [esp+10h] [ebp-24h] BYREF
  char *v23; // [esp+20h] [ebp-14h]
  int v24; // [esp+24h] [ebp-10h]
  int v25; // [esp+28h] [ebp-Ch]
  CCommand *v26; // [esp+2Ch] [ebp-8h]

  v25 = 0;
  v26 = this;
  v24 = 0;
  v4 = (_DWORD *)*((_DWORD *)this + 68);
  if ( !v4 )
  {
    v5 = operator new(0x14u);
    v4 = v5;
    v25 = (int)v5;
    if ( !v5 )
    {
      *((_DWORD *)this + 68) = 0;
      return -2147024882;
    }
    v5[1] = 0;
    v5[2] = 0;
    v5[3] = 0;
    *v5 = &CRowsetProperties::`vftable';
    v5[4] = 0;
    *((_DWORD *)this + 68) = v5;
    v25 = 1;
  }
  v6 = 0;
  while ( 1 )
  {
    v7 = v4[v6 + 2];
    if ( !v7 )
      break;
    v8 = *(_OWORD *)(v7 + 20);
    v9 = &v22;
    v10 = 12;
    v11 = &a3;
    v22 = v8;
    while ( *(_DWORD *)v9 == v11->Data1 )
    {
      v9 = (__int128 *)((char *)v9 + 4);
      v11 = (struct _GUID *)((char *)v11 + 4);
      v12 = v10 < 4;
      v10 -= 4;
      if ( v12 )
      {
        v13 = v26;
        goto LABEL_19;
      }
    }
    if ( (unsigned int)++v6 >= 2 )
    {
      v13 = v26;
      goto LABEL_19;
    }
  }
  v15 = (char *)operator new(0x28u);
  v16 = v15;
  v23 = v15;
  if ( v15 )
  {
    *(_DWORD *)v15 = &JoltProperties::`vftable';
    *((_DWORD *)v15 + 1) = 0;
    *((_DWORD *)v15 + 2) = 0;
    *((_DWORD *)v15 + 3) = 0;
    *((_DWORD *)v15 + 4) = 0;
    *((_DWORD *)v15 + 9) = 0;
    *(GUID *)(v15 + 20) = DBPROPSET_ROWSET;
  }
  else
  {
    v16 = 0;
  }
  v13 = v26;
  *(_DWORD *)(*((_DWORD *)v26 + 68) + 4 * v6 + 8) = v16;
  v17 = *(_DWORD *)(*((_DWORD *)v13 + 68) + 4 * v6 + 8);
  if ( !v17 )
  {
    v18 = -2147024882;
    goto LABEL_20;
  }
  v24 = 1;
  *(struct _GUID *)(v17 + 20) = a3;
LABEL_19:
  v18 = JoltProperties::AddProperty(*(JoltProperties **)(*((_DWORD *)v13 + 68) + 4 * v6 + 8), a2);
  if ( v18 >= 0 )
    return v18;
LABEL_20:
  if ( v25 == 1 )
  {
    v19 = (void (__thiscall ***)(int, int))*((_DWORD *)v13 + 68);
    v25 = (int)v19;
    if ( v19 )
    {
      (**v19)(v25, 1);
      v13 = v26;
    }
    *((_DWORD *)v13 + 68) = 0;
  }
  if ( v24 == 1 )
  {
    v20 = *((_DWORD *)v13 + 68);
    v21 = *(JoltProperties **)(v20 + 4 * v6 + 8);
    if ( v21 )
      JoltProperties::`scalar deleting destructor'(v21, *(_DWORD *)(v20 + 4 * v6 + 8));
    *(_DWORD *)(*((_DWORD *)v13 + 68) + 4 * v6 + 8) = 0;
  }
  return v18;
}

```

## disassembly

```asm
0x100148a0  mov     edi, edi
0x100148a2  push    ebp
0x100148a3  mov     ebp, esp
0x100148a5  sub     esp, 28h
0x100148a8  push    ebx
0x100148a9  push    esi
0x100148aa  mov     esi, ecx
0x100148ac  mov     [ebp+var_C], 0
0x100148b3  push    edi
0x100148b4  mov     [ebp+var_8], esi
0x100148b7  mov     [ebp+var_10], 0
0x100148be  mov     ebx, [esi+110h]
0x100148c4  test    ebx, ebx
0x100148c6  jnz     short loc_1001490A
0x100148c8  push    14h; Size
0x100148ca  call    ??2@YAPAXI@Z; operator new(uint)
0x100148cf  mov     ebx, eax
0x100148d1  add     esp, 4
0x100148d4  mov     [ebp+var_C], ebx
0x100148d7  test    ebx, ebx
0x100148d9  jz      short loc_10014949
0x100148db  mov     dword ptr [ebx+4], 0
0x100148e2  mov     dword ptr [ebx+8], 0
0x100148e9  mov     dword ptr [ebx+0Ch], 0
0x100148f0  mov     dword ptr [ebx], offset ??_7CRowsetProperties@@6B@; const CRowsetProperties::`vftable'
0x100148f6  mov     dword ptr [ebx+10h], 0
0x100148fd  mov     [esi+110h], ebx
0x10014903  mov     [ebp+var_C], 1
0x1001490a  xor     edi, edi
0x1001490c  nop     dword ptr [eax+00h]
0x10014910  mov     eax, [ebx+edi*4+8]
0x10014914  test    eax, eax
0x10014916  jz      short loc_1001496C
0x10014918  movups  xmm0, xmmword ptr [eax+14h]
0x1001491c  lea     edx, [ebp+var_24]
0x1001491f  mov     esi, 0Ch
0x10014924  lea     eax, [ebp+arg_0.Data2]
0x10014927  movups  [ebp+var_24], xmm0
0x1001492b  nop     dword ptr [eax+eax+00h]
0x10014930  mov     ecx, [edx]
0x10014932  cmp     ecx, [eax]
0x10014934  jnz     short loc_10014961
0x10014936  add     edx, 4
0x10014939  add     eax, 4
0x1001493c  sub     esi, 4
0x1001493f  jnb     short loc_10014930
0x10014941  mov     esi, [ebp+var_8]
0x10014944  jmp     loc_100149E8
0x10014949  mov     dword ptr [esi+110h], 0
0x10014953  mov     eax, 8007000Eh
0x10014958  pop     edi
0x10014959  pop     esi
0x1001495a  pop     ebx
0x1001495b  mov     esp, ebp
0x1001495d  pop     ebp
0x1001495e  retn    14h
0x10014961  inc     edi
0x10014962  cmp     edi, 2
0x10014965  jb      short loc_10014910
0x10014967  mov     esi, [ebp+var_8]
0x1001496a  jmp     short loc_100149E8
0x1001496c  push    28h ; '('; Size
0x1001496e  call    ??2@YAPAXI@Z; operator new(uint)
0x10014973  mov     ecx, eax
0x10014975  add     esp, 4
0x10014978  mov     [ebp+var_14], ecx
0x1001497b  test    ecx, ecx
0x1001497d  jz      short loc_100149B5
0x1001497f  mov     dword ptr [ecx], offset ??_7JoltProperties@@6B@; const JoltProperties::`vftable'
0x10014985  mov     dword ptr [ecx+4], 0
0x1001498c  mov     dword ptr [ecx+8], 0
0x10014993  mov     dword ptr [ecx+0Ch], 0
0x1001499a  mov     dword ptr [ecx+10h], 0
0x100149a1  movups  xmm0, xmmword ptr ds:_DBPROPSET_ROWSET.Data1
0x100149a8  mov     dword ptr [ecx+24h], 0
0x100149af  movups  xmmword ptr [ecx+14h], xmm0
0x100149b3  jmp     short loc_100149B7
0x100149b5  xor     ecx, ecx
0x100149b7  mov     esi, [ebp+var_8]
0x100149ba  mov     eax, [esi+110h]
0x100149c0  mov     [eax+edi*4+8], ecx
0x100149c4  mov     eax, [esi+110h]
0x100149ca  mov     eax, [eax+edi*4+8]
0x100149ce  test    eax, eax
0x100149d0  jnz     short loc_100149D9
0x100149d2  mov     ebx, 8007000Eh
0x100149d7  jmp     short loc_10014A00
0x100149d9  movups  xmm0, xmmword ptr [ebp+arg_0.Data2]
0x100149dd  mov     [ebp+var_10], 1
0x100149e4  movups  xmmword ptr [eax+14h], xmm0
0x100149e8  mov     eax, [esi+110h]
0x100149ee  push    [ebp+arg_0.Data1]; struct JoltProperty *
0x100149f1  mov     ecx, [eax+edi*4+8]; this
0x100149f5  call    ?AddProperty@JoltProperties@@QAEJPAVJoltProperty@@@Z; JoltProperties::AddProperty(JoltProperty *)
0x100149fa  mov     ebx, eax
0x100149fc  test    ebx, ebx
0x100149fe  jns     short loc_10014A5B
0x10014a00  cmp     [ebp+var_C], 1
0x10014a04  jnz     short loc_10014A33
0x10014a06  mov     eax, [esi+110h]
0x10014a0c  mov     [ebp+var_C], eax
0x10014a0f  test    eax, eax
0x10014a11  jz      short loc_10014A29
0x10014a13  mov     eax, [eax]
0x10014a15  push    1
0x10014a17  mov     esi, [eax]
0x10014a19  mov     ecx, esi
0x10014a1b  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10014a21  mov     ecx, [ebp+var_C]
0x10014a24  call    esi
0x10014a26  mov     esi, [ebp+var_8]
0x10014a29  mov     dword ptr [esi+110h], 0
0x10014a33  cmp     [ebp+var_10], 1
0x10014a37  jnz     short loc_10014A5B
0x10014a39  mov     eax, [esi+110h]
0x10014a3f  mov     ecx, [eax+edi*4+8]; this
0x10014a43  test    ecx, ecx
0x10014a45  jz      short loc_10014A4D
0x10014a47  push    ecx; unsigned int
0x10014a48  call    ??_GJoltProperties@@QAEPAXI@Z; JoltProperties::`scalar deleting destructor'(uint)
0x10014a4d  mov     eax, [esi+110h]
0x10014a53  mov     dword ptr [eax+edi*4+8], 0
0x10014a5b  pop     edi
0x10014a5c  pop     esi
0x10014a5d  mov     eax, ebx
0x10014a5f  pop     ebx
0x10014a60  mov     esp, ebp
0x10014a62  pop     ebp
0x10014a63  retn    14h
```
