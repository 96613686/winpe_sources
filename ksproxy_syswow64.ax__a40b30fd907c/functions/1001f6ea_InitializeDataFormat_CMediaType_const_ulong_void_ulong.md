# InitializeDataFormat(CMediaType const *,ulong,void * *,ulong *)

- ea: `0x1001f6ea`
- end: `0x1001f840`
- name: `?InitializeDataFormat@@YGJPBVCMediaType@@KPAPAXPAK@Z`
- size: `342`
- prototype: `int __userpurge@<eax>(SIZE_T@<edx>, int@<ecx>, const struct CMediaType *, unsigned int *, void **, unsigned int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x10010350`
- `0x1001a8f0`
- `0x1001b660`
- `0x1001f846`
- `0x10020593`
- `0x1002151c`

## callees

- `0x1001f6ea`
- `0x1002d510`
- `0x1003bcf8`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1001f793`
- `ole32!CoTaskMemAlloc` at `0x1001f793`

## pseudocode

```c
int __userpurge InitializeDataFormat@<eax>(
        SIZE_T a1@<edx>,
        int a2@<ecx>,
        const struct CMediaType *a3,
        unsigned int *a4,
        void **a5,
        unsigned int *a6)
{
  SIZE_T v7; // esi
  _DWORD *v8; // ecx
  _DWORD **v9; // edx
  unsigned int v10; // eax
  unsigned int v11; // edx
  SIZE_T v12; // eax
  char *v13; // eax
  char *v15; // ebx
  int v16; // eax
  int v18; // [esp+14h] [ebp-8h] BYREF
  void *Src; // [esp+18h] [ebp-4h] BYREF

  v7 = a1;
  v8 = 0;
  Src = 0;
  v9 = *(_DWORD ***)(a2 + 60);
  if ( v9 )
  {
    if ( ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, int *))**v9)(
           **v9,
           v9,
           &_GUID_d559999a_a4c3_11d2_876a_00a0c9223196,
           &v18) >= 0 )
    {
      (*(void (__thiscall **)(_DWORD, int, void **))(*(_DWORD *)v18 + 12))(*(_DWORD *)(*(_DWORD *)v18 + 12), v18, &Src);
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v18 + 8))(*(_DWORD *)(*(_DWORD *)v18 + 8), v18);
    }
    v7 = a1;
    v8 = Src;
  }
  v10 = *(_DWORD *)(a2 + 64) + 64;
  if ( *(_DWORD *)(a2 + 64) >= 0xFFFFFFC0 )
    goto LABEL_19;
  *a4 = v10;
  if ( !v8 )
    goto LABEL_10;
  if ( v10 + 7 < v10 || (v11 = (v10 + 7) & 0xFFFFFFF8, v10 = v11 + *v8, v10 < v11) )
  {
LABEL_19:
    *a4 = -1;
    return -2147024362;
  }
  *a4 = v10;
LABEL_10:
  v12 = v7 + v10;
  if ( v12 < v7 )
    return -2147024362;
  v13 = (char *)CoTaskMemAlloc(v12);
  a3->majortype.Data1 = (unsigned int)v13;
  if ( !v13 )
    return -2147024882;
  v15 = &v13[v7];
  *(_DWORD *)v15 = *(_DWORD *)(a2 + 64) + 64;
  *((_DWORD *)v15 + 1) = *(_DWORD *)(a2 + 36) != 0;
  if ( *(_DWORD *)(a2 + 32) )
    v16 = *(_DWORD *)(a2 + 40);
  else
    v16 = 0;
  *((_DWORD *)v15 + 2) = v16;
  *((_DWORD *)v15 + 3) = 0;
  *((_DWORD *)v15 + 4) = *(_DWORD *)a2;
  *((_DWORD *)v15 + 5) = *(_DWORD *)(a2 + 4);
  *((_DWORD *)v15 + 6) = *(_DWORD *)(a2 + 8);
  *((_DWORD *)v15 + 7) = *(_DWORD *)(a2 + 12);
  *((_DWORD *)v15 + 8) = *(_DWORD *)(a2 + 16);
  *((_DWORD *)v15 + 9) = *(_DWORD *)(a2 + 20);
  *((_DWORD *)v15 + 10) = *(_DWORD *)(a2 + 24);
  *((_DWORD *)v15 + 11) = *(_DWORD *)(a2 + 28);
  *((_DWORD *)v15 + 12) = *(_DWORD *)(a2 + 44);
  *((_DWORD *)v15 + 13) = *(_DWORD *)(a2 + 48);
  *((_DWORD *)v15 + 14) = *(_DWORD *)(a2 + 52);
  *((_DWORD *)v15 + 15) = *(_DWORD *)(a2 + 56);
  memcpy(v15 + 64, *(const void **)(a2 + 68), *(_DWORD *)(a2 + 64));
  if ( Src )
  {
    *((_DWORD *)v15 + 1) |= 2u;
    memcpy(&v15[(*(_DWORD *)v15 + 7) & 0xFFFFFFF8], Src, *(_DWORD *)Src);
  }
  return 0;
}

```

## disassembly

```asm
0x1001f6ea  mov     edi, edi
0x1001f6ec  push    ebp
0x1001f6ed  mov     ebp, esp
0x1001f6ef  sub     esp, 10h
0x1001f6f2  push    ebx
0x1001f6f3  mov     ebx, [ebp+arg_4]
0x1001f6f6  push    esi
0x1001f6f7  push    edi
0x1001f6f8  mov     edi, ecx
0x1001f6fa  mov     esi, edx
0x1001f6fc  xor     ecx, ecx
0x1001f6fe  mov     [ebp+var_C], esi
0x1001f701  mov     [ebp+Src], ecx
0x1001f704  mov     edx, [edi+3Ch]
0x1001f707  test    edx, edx
0x1001f709  jz      short loc_1001F757
0x1001f70b  mov     eax, [edx]
0x1001f70d  mov     esi, [eax]
0x1001f70f  lea     eax, [ebp+var_8]
0x1001f712  push    eax
0x1001f713  push    offset __GUID_d559999a_a4c3_11d2_876a_00a0c9223196
0x1001f718  push    edx
0x1001f719  mov     ecx, esi; this
0x1001f71b  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001f721  call    esi
0x1001f723  test    eax, eax
0x1001f725  js      short loc_1001F751
0x1001f727  mov     eax, [ebp+var_8]
0x1001f72a  lea     edx, [ebp+Src]
0x1001f72d  push    edx
0x1001f72e  push    eax
0x1001f72f  mov     ecx, [eax]
0x1001f731  mov     esi, [ecx+0Ch]
0x1001f734  mov     ecx, esi; this
0x1001f736  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001f73c  call    esi
0x1001f73e  mov     eax, [ebp+var_8]
0x1001f741  push    eax
0x1001f742  mov     ecx, [eax]
0x1001f744  mov     esi, [ecx+8]
0x1001f747  mov     ecx, esi; this
0x1001f749  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001f74f  call    esi
0x1001f751  mov     esi, [ebp+var_C]
0x1001f754  mov     ecx, [ebp+Src]
0x1001f757  mov     eax, [edi+40h]
0x1001f75a  add     eax, 40h ; '@'
0x1001f75d  cmp     eax, 40h ; '@'
0x1001f760  jb      loc_1001F82E
0x1001f766  mov     [ebx], eax
0x1001f768  test    ecx, ecx
0x1001f76a  jz      short loc_1001F788
0x1001f76c  lea     edx, [eax+7]
0x1001f76f  cmp     edx, eax
0x1001f771  jb      loc_1001F82E
0x1001f777  mov     eax, [ecx]
0x1001f779  and     edx, 0FFFFFFF8h
0x1001f77c  add     eax, edx
0x1001f77e  cmp     eax, edx
0x1001f780  jb      loc_1001F82E
0x1001f786  mov     [ebx], eax
0x1001f788  add     eax, esi
0x1001f78a  cmp     eax, esi
0x1001f78c  jb      loc_1001F834
0x1001f792  push    eax; cb
0x1001f793  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1001f799  mov     ecx, [ebp+arg_0]
0x1001f79c  mov     [ecx], eax
0x1001f79e  test    eax, eax
0x1001f7a0  jnz     short loc_1001F7AC
0x1001f7a2  mov     eax, 8007000Eh
0x1001f7a7  jmp     loc_1001F839
0x1001f7ac  mov     ecx, edi
0x1001f7ae  lea     ebx, [eax+esi]
0x1001f7b1  xor     edx, edx
0x1001f7b3  mov     eax, [ecx+40h]
0x1001f7b6  add     eax, 40h ; '@'
0x1001f7b9  mov     [ebx], eax
0x1001f7bb  xor     eax, eax
0x1001f7bd  cmp     [ecx+24h], edx
0x1001f7c0  setnz   al
0x1001f7c3  mov     [ebx+4], eax
0x1001f7c6  cmp     [ecx+20h], edx
0x1001f7c9  jz      short loc_1001F7D0
0x1001f7cb  mov     eax, [ecx+28h]
0x1001f7ce  jmp     short loc_1001F7D2
0x1001f7d0  mov     eax, edx
0x1001f7d2  mov     [ebx+8], eax
0x1001f7d5  lea     edi, [ebx+10h]
0x1001f7d8  mov     [ebx+0Ch], edx
0x1001f7db  lea     eax, [ebx+40h]
0x1001f7de  mov     esi, ecx
0x1001f7e0  movsd
0x1001f7e1  movsd
0x1001f7e2  movsd
0x1001f7e3  movsd
0x1001f7e4  lea     esi, [ecx+10h]
0x1001f7e7  lea     edi, [ebx+20h]
0x1001f7ea  movsd
0x1001f7eb  movsd
0x1001f7ec  movsd
0x1001f7ed  movsd
0x1001f7ee  lea     esi, [ecx+2Ch]
0x1001f7f1  lea     edi, [ebx+30h]
0x1001f7f4  movsd
0x1001f7f5  movsd
0x1001f7f6  movsd
0x1001f7f7  movsd
0x1001f7f8  push    dword ptr [ecx+40h]; Size
0x1001f7fb  push    dword ptr [ecx+44h]; Src
0x1001f7fe  push    eax; void *
0x1001f7ff  call    _memcpy
0x1001f804  add     esp, 0Ch
0x1001f807  cmp     [ebp+Src], 0
0x1001f80b  jz      short loc_1001F82A
0x1001f80d  or      dword ptr [ebx+4], 2
0x1001f811  mov     eax, [ebp+Src]
0x1001f814  push    dword ptr [eax]; Size
0x1001f816  push    eax; Src
0x1001f817  mov     eax, [ebx]
0x1001f819  add     eax, 7
0x1001f81c  and     eax, 0FFFFFFF8h
0x1001f81f  add     eax, ebx
0x1001f821  push    eax; void *
0x1001f822  call    _memcpy
0x1001f827  add     esp, 0Ch
0x1001f82a  xor     eax, eax
0x1001f82c  jmp     short loc_1001F839
0x1001f82e  mov     dword ptr [ebx], 0FFFFFFFFh
0x1001f834  mov     eax, 80070216h
0x1001f839  pop     edi
0x1001f83a  pop     esi
0x1001f83b  pop     ebx
0x1001f83c  leave
0x1001f83d  retn    8
```
