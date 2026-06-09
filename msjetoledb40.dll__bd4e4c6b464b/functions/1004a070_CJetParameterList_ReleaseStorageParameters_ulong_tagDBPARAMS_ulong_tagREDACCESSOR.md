# CJetParameterList::ReleaseStorageParameters(ulong,tagDBPARAMS *,ulong,tagREDACCESSOR *)

- ea: `0x1004a070`
- end: `0x1004a10b`
- name: `?ReleaseStorageParameters@CJetParameterList@@QAEJKPAUtagDBPARAMS@@KPAUtagREDACCESSOR@@@Z`
- size: `155`
- prototype: `int __thiscall(CJetParameterList *__hidden this, unsigned int, struct tagDBPARAMS *, unsigned int, struct tagREDACCESSOR *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1004a120`

## callees

- `0x1001c6d0`
- `0x1004a070`

## pseudocode

```c
int __thiscall CJetParameterList::ReleaseStorageParameters(
        CJetParameterList *this,
        unsigned int a2,
        struct tagDBPARAMS *a3,
        unsigned int a4,
        struct tagREDACCESSOR *a5)
{
  unsigned int v5; // edx
  CJetParameterList *v6; // eax
  unsigned int i; // ebx
  int v8; // eax
  unsigned int j; // ecx
  _DWORD *v10; // edi
  int v11; // eax
  _DWORD *v12; // ecx
  int v13; // edx

  v5 = a2;
  v6 = this;
  for ( i = a2; ; ++i )
  {
    v8 = *(_DWORD *)v6;
    for ( j = 0; v8; ++j )
      v8 = *(_DWORD *)(v8 + 40);
    if ( i > j )
      break;
    v10 = 0;
    v11 = 52 * v5;
    v12 = 0;
    v13 = *((_DWORD *)a5 + 13 * v5 + 17);
    if ( (v13 & 1) != 0 )
      v12 = (char *)a3->pData + *(_DWORD *)((char *)a5 + v11 + 44);
    if ( (v13 & 4) != 0 )
      v10 = (char *)a3->pData + *(_DWORD *)((char *)a5 + v11 + 52);
    if ( *(_WORD *)((char *)a5 + v11 + 88) == 13 )
    {
      if ( v12 )
        (*(void (__thiscall **)(_DWORD, _DWORD))(*(_DWORD *)*v12 + 8))(*(_DWORD *)(*(_DWORD *)*v12 + 8), *v12);
      if ( v10 )
        *v10 = 0;
    }
    v6 = this;
    v5 = a2;
  }
  return 0;
}

```

## disassembly

```asm
0x1004a070  mov     edi, edi
0x1004a072  push    ebp
0x1004a073  mov     ebp, esp
0x1004a075  push    ecx
0x1004a076  mov     edx, [ebp+arg_0]
0x1004a079  mov     eax, ecx
0x1004a07b  push    ebx
0x1004a07c  push    esi
0x1004a07d  push    edi
0x1004a07e  mov     [ebp+var_4], eax
0x1004a081  mov     ebx, edx
0x1004a083  mov     eax, [eax]
0x1004a085  xor     ecx, ecx
0x1004a087  test    eax, eax
0x1004a089  jz      short loc_1004A098
0x1004a08b  nop     dword ptr [eax+eax+00h]
0x1004a090  mov     eax, [eax+28h]
0x1004a093  inc     ecx
0x1004a094  test    eax, eax
0x1004a096  jnz     short loc_1004A090
0x1004a098  cmp     ebx, ecx
0x1004a09a  ja      short loc_1004A100
0x1004a09c  mov     esi, [ebp+arg_C]
0x1004a09f  xor     edi, edi
0x1004a0a1  imul    eax, edx, 34h ; '4'
0x1004a0a4  xor     ecx, ecx
0x1004a0a6  mov     edx, [eax+esi+44h]
0x1004a0aa  test    dl, 1
0x1004a0ad  jz      short loc_1004A0BA
0x1004a0af  mov     ecx, [eax+esi+2Ch]
0x1004a0b3  mov     esi, [ebp+arg_4]
0x1004a0b6  add     ecx, [esi]
0x1004a0b8  jmp     short loc_1004A0BD
0x1004a0ba  mov     esi, [ebp+arg_4]
0x1004a0bd  test    dl, 4
0x1004a0c0  mov     edx, [ebp+arg_C]
0x1004a0c3  jz      short loc_1004A0CB
0x1004a0c5  mov     edi, [eax+edx+34h]
0x1004a0c9  add     edi, [esi]
0x1004a0cb  mov     esi, 0Dh
0x1004a0d0  cmp     si, [eax+edx+58h]
0x1004a0d5  jnz     short loc_1004A0F7
0x1004a0d7  test    ecx, ecx
0x1004a0d9  jz      short loc_1004A0ED
0x1004a0db  mov     eax, [ecx]
0x1004a0dd  push    eax
0x1004a0de  mov     ecx, [eax]
0x1004a0e0  mov     esi, [ecx+8]
0x1004a0e3  mov     ecx, esi
0x1004a0e5  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004a0eb  call    esi
0x1004a0ed  test    edi, edi
0x1004a0ef  jz      short loc_1004A0F7
0x1004a0f1  mov     dword ptr [edi], 0
0x1004a0f7  mov     eax, [ebp+var_4]
0x1004a0fa  inc     ebx
0x1004a0fb  mov     edx, [ebp+arg_0]
0x1004a0fe  jmp     short loc_1004A083
0x1004a100  pop     edi
0x1004a101  pop     esi
0x1004a102  xor     eax, eax
0x1004a104  pop     ebx
0x1004a105  mov     esp, ebp
0x1004a107  pop     ebp
0x1004a108  retn    10h
```
