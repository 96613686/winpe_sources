# NCryptFreeObject

- ea: `0x18000c700`
- end: `0x18000c8cf`
- name: `NCryptFreeObject`
- size: `463`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_HANDLE hObject)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18000fb20`

## callees

- `0x18000a770`
- `0x18000a790`
- `0x18000c700`
- `0x18000c8e0`
- `0x18000cb50`
- `0x18000d02c`
- `0x180014978`
- `0x180020010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000c8c4`
- `ntdll!RtlFreeHeap` at `0x18000c8c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c76e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c76e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c760`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c760`

## string_xrefs

- `0x18000c811`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000c866`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptFreeObject(NCRYPT_HANDLE hObject)
{
  NCRYPT_KEY_HANDLE *v1; // rdx
  NCryptKeyName **v2; // r8
  NCryptAlgorithmName **v3; // r9
  PVOID *v5; // rcx
  void *v6; // rdi
  HANDLE ProcessHeap; // rax
  unsigned int v8; // edi
  _QWORD *v9; // rcx
  char v11; // [rsp+30h] [rbp-18h]
  BYTE *v12; // [rsp+70h] [rbp+28h]
  DWORD v13; // [rsp+78h] [rbp+30h]
  DWORD *v14; // [rsp+80h] [rbp+38h]

  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), v1, v2, hObject);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !hObject )
    goto LABEL_22;
  if ( *(_DWORD *)hObject == 1145307137 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(hObject + 4));
    DereferenceProvider(hObject);
    DereferenceProvider(hObject);
    goto LABEL_14;
  }
  if ( *(_DWORD *)hObject == 1145307138 )
  {
    v6 = (void *)_InterlockedExchange64((volatile __int64 *)(hObject + 40), 0);
    EtwLogNCryptCertInUse(v6);
    if ( v6 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v6);
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)(hObject + 8) + 104LL))(
           *(_QWORD *)(*(_QWORD *)(hObject + 8) + 272LL),
           *(_QWORD *)(hObject + 16));
    if ( v8 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = -21;
LABEL_19:
        WPP_SF_sDsd(
          v9[2],
          (_DWORD)v1,
          (_DWORD)v2,
          (unsigned int)"Status",
          v8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
          v11);
        return NormalizeNteStatus(v8, v1, v2, v3, v12, v13, v14);
      }
      return NormalizeNteStatus(v8, v1, v2, v3, v12, v13, v14);
    }
    DereferenceProvider(*(_QWORD *)(hObject + 8));
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)hObject);
LABEL_14:
    v8 = 0;
    return NormalizeNteStatus(v8, v1, v2, v3, v12, v13, v14);
  }
  if ( *(_DWORD *)hObject != 1145307139 )
  {
LABEL_22:
    v8 = -2146893786;
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        (unsigned int)v5[2],
        (_DWORD)v1,
        (_DWORD)v2,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        211);
    return NormalizeNteStatus(v8, v1, v2, v3, v12, v13, v14);
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)(hObject + 8) + 224LL))(
         *(_QWORD *)(*(_QWORD *)(hObject + 8) + 272LL),
         *(_QWORD *)(hObject + 16));
  if ( !v8 )
  {
    DereferenceProvider(*(_QWORD *)(hObject + 8));
    MSCryptFree(hObject);
    v8 = 0;
    return NormalizeNteStatus(v8, v1, v2, v3, v12, v13, v14);
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = -5;
    goto LABEL_19;
  }
  return NormalizeNteStatus(v8, v1, v2, v3, v12, v13, v14);
}

```

## disassembly

```asm
0x18000c700  mov     [rsp+arg_0], rbx
0x18000c705  mov     [rsp+arg_8], rsi
0x18000c70a  push    rdi
0x18000c70b  sub     rsp, 40h
0x18000c70f  mov     rbx, rcx
0x18000c712  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c719  lea     rsi, WPP_GLOBAL_Control
0x18000c720  cmp     rcx, rsi
0x18000c723  jz      short loc_18000C72F
0x18000c725  test    byte ptr [rcx+1Ch], 4
0x18000c729  jnz     loc_18000C87C
0x18000c72f  test    rbx, rbx
0x18000c732  jz      loc_18000C84E
0x18000c738  cmp     dword ptr [rbx], 44440001h
0x18000c73e  jz      short loc_18000C7BA
0x18000c740  mov     eax, [rbx]
0x18000c742  cmp     eax, 44440002h
0x18000c747  jnz     loc_18000C847
0x18000c74d  xor     edi, edi
0x18000c74f  xchg    rdi, [rbx+28h]
0x18000c753  mov     rcx, rdi
0x18000c756  call    EtwLogNCryptCertInUse
0x18000c75b  test    rdi, rdi
0x18000c75e  jz      short loc_18000C774
0x18000c760  call    cs:__imp_GetProcessHeap
0x18000c766  mov     r8, rdi; lpMem
0x18000c769  xor     edx, edx; dwFlags
0x18000c76b  mov     rcx, rax; hHeap
0x18000c76e  call    cs:__imp_HeapFree
0x18000c774  mov     rcx, [rbx+8]
0x18000c778  mov     rdx, [rbx+10h]
0x18000c77c  mov     rax, [rcx+68h]
0x18000c780  mov     rcx, [rcx+110h]
0x18000c787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c78c  mov     edi, eax
0x18000c78e  test    eax, eax
0x18000c790  jz      loc_18000C8A9
0x18000c796  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c79d  cmp     rcx, rsi
0x18000c7a0  jz      loc_18000C831
0x18000c7a6  test    byte ptr [rcx+1Ch], 1
0x18000c7aa  jz      loc_18000C831
0x18000c7b0  mov     dword ptr [rsp+48h+var_18], 8EBh
0x18000c7b8  jmp     short loc_18000C811
0x18000c7ba  lock inc dword ptr [rbx+4]
0x18000c7be  mov     rcx, rbx
0x18000c7c1  call    DereferenceProvider
0x18000c7c6  mov     rcx, rbx
0x18000c7c9  call    DereferenceProvider
0x18000c7ce  xor     edi, edi
0x18000c7d0  jmp     short loc_18000C831
0x18000c7d2  mov     rcx, [rbx+8]
0x18000c7d6  mov     rdx, [rbx+10h]
0x18000c7da  mov     rax, [rcx+0E0h]
0x18000c7e1  mov     rcx, [rcx+110h]
0x18000c7e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7ed  mov     edi, eax
0x18000c7ef  test    eax, eax
0x18000c7f1  jz      loc_18000C894
0x18000c7f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7fe  cmp     rcx, rsi
0x18000c801  jz      short loc_18000C831
0x18000c803  test    byte ptr [rcx+1Ch], 1
0x18000c807  jz      short loc_18000C831
0x18000c809  mov     dword ptr [rsp+48h+var_18], 8FBh
0x18000c811  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c818  mov     [rsp+48h+var_20], rax
0x18000c81d  mov     [rsp+48h+var_28], edi
0x18000c821  mov     rcx, [rcx+10h]
0x18000c825  lea     r9, aStatus; "Status"
0x18000c82c  call    WPP_SF_sDsd
0x18000c831  mov     ecx, edi
0x18000c833  mov     rbx, [rsp+48h+arg_0]
0x18000c838  mov     rsi, [rsp+48h+arg_8]
0x18000c83d  add     rsp, 40h
0x18000c841  pop     rdi
0x18000c842  jmp     NormalizeNteStatus
0x18000c847  cmp     eax, 44440003h
0x18000c84c  jz      short loc_18000C7D2
0x18000c84e  mov     edi, 80090026h
0x18000c853  cmp     rcx, rsi
0x18000c856  jz      short loc_18000C831
0x18000c858  test    byte ptr [rcx+1Ch], 1
0x18000c85c  jz      short loc_18000C831
0x18000c85e  mov     dword ptr [rsp+48h+var_18], 8D3h
0x18000c866  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c86d  mov     [rsp+48h+var_20], rax
0x18000c872  mov     [rsp+48h+var_28], 80090026h
0x18000c87a  jmp     short loc_18000C821
0x18000c87c  mov     rcx, [rcx+10h]
0x18000c880  mov     r9, rbx
0x18000c883  call    WPP_SF_P
0x18000c888  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c88f  jmp     loc_18000C72F
0x18000c894  mov     rcx, [rbx+8]
0x18000c898  call    DereferenceProvider
0x18000c89d  mov     rcx, rbx
0x18000c8a0  call    MSCryptFree
0x18000c8a5  xor     edi, edi
0x18000c8a7  jmp     short loc_18000C831
0x18000c8a9  mov     rcx, [rbx+8]
0x18000c8ad  call    DereferenceProvider
0x18000c8b2  mov     rcx, gs:60h
0x18000c8bb  mov     r8, rbx; P
0x18000c8be  xor     edx, edx; Flags
0x18000c8c0  mov     rcx, [rcx+30h]; HeapHandle
0x18000c8c4  call    cs:__imp_RtlFreeHeap
0x18000c8ca  jmp     loc_18000C7CE
```
