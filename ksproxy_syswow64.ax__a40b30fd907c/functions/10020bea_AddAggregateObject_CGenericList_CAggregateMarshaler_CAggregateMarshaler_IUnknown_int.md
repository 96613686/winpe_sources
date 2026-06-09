# AddAggregateObject(CGenericList<CAggregateMarshaler> *,CAggregateMarshaler *,IUnknown *,int)

- ea: `0x10020bea`
- end: `0x10020ce0`
- name: `?AddAggregateObject@@YGJPAV?$CGenericList@VCAggregateMarshaler@@@@PAVCAggregateMarshaler@@PAUIUnknown@@H@Z`
- size: `246`
- prototype: `HRESULT __fastcall(CBaseList *, int, IUnknown *pUnkOuter, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x10020ce6`
- `0x10020e70`
- `0x10021163`
- `0x1002168c`

## callees

- `0x10020bea`
- `0x1002d510`
- `0x1002ff0f`
- `0x1003af9d`

## import_xrefs

- `ole32!CoCreateInstance` at `0x10020c15`
- `ole32!CoCreateInstance` at `0x10020c15`

## pseudocode

```c
HRESULT __fastcall AddAggregateObject(CBaseList *a1, int a2, IUnknown *pUnkOuter, int a4)
{
  CBaseList::CNode *m_pFirst; // edx
  HRESULT Instance; // ebx
  _DWORD *m_pObject; // ecx
  int v8; // esi
  int v9; // esi
  int v10; // ecx

  m_pFirst = a1->m_pFirst;
LABEL_2:
  while ( m_pFirst )
  {
    m_pObject = m_pFirst->m_pObject;
    v8 = 0;
    m_pFirst = m_pFirst->m_pNext;
    while ( *(_DWORD *)(a2 + 4 * v8) == m_pObject[v8] )
    {
      if ( ++v8 == 4 )
      {
        v9 = 0;
        while ( *(_DWORD *)(a2 + 4 * v9 + 16) == m_pObject[v9 + 4] )
        {
          if ( ++v9 == 4 )
          {
            if ( !m_pObject )
              goto LABEL_3;
            Instance = -2147024713;
            if ( m_pObject[10] )
            {
              if ( !m_pObject[11] )
              {
                m_pObject[11] = 1;
                v10 = m_pObject[9];
                if ( v10 )
                  (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v10 + 28))(*(_DWORD *)(*(_DWORD *)v10 + 28), v10);
              }
            }
            goto LABEL_18;
          }
        }
        goto LABEL_2;
      }
    }
  }
LABEL_3:
  Instance = CoCreateInstance(
               (const IID *const)(a2 + 16),
               pUnkOuter,
               0x401u,
               &_GUID_00000000_0000_0000_c000_000000000046,
               (LPVOID *)(a2 + 32));
  if ( Instance < 0 )
  {
LABEL_18:
    operator delete((void *)a2, 0x30u);
  }
  else
  {
    if ( (***(int (__thiscall ****)(_DWORD, _DWORD, GUID *, int))(a2 + 32))(
           ***(_DWORD ***)(a2 + 32),
           *(_DWORD *)(a2 + 32),
           &_GUID_56a868af_0ad4_11ce_b03a_0020af0ba770,
           a2 + 36) >= 0 )
      (*(void (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)(a2 + 36) + 8))(
        *(_DWORD *)(**(_DWORD **)(a2 + 36) + 8),
        *(_DWORD *)(a2 + 36));
    *(_DWORD *)(a2 + 40) = a4;
    *(_DWORD *)(a2 + 44) = a4;
    CBaseList::AddTailI(a1, (void *)a2);
  }
  return Instance;
}

```

## disassembly

```asm
0x10020bea  mov     edi, edi
0x10020bec  push    ebp
0x10020bed  mov     ebp, esp
0x10020bef  push    ecx
0x10020bf0  push    ebx
0x10020bf1  mov     eax, ecx
0x10020bf3  push    esi
0x10020bf4  push    edi
0x10020bf5  mov     edi, edx
0x10020bf7  mov     [ebp+var_4], eax
0x10020bfa  mov     edx, [eax]
0x10020bfc  test    edx, edx
0x10020bfe  jnz     short loc_10020C6A
0x10020c00  lea     esi, [edi+20h]
0x10020c03  push    esi; ppv
0x10020c04  push    offset __GUID_00000000_0000_0000_c000_000000000046; riid
0x10020c09  push    401h; dwClsContext
0x10020c0e  push    [ebp+pUnkOuter]; pUnkOuter
0x10020c11  lea     eax, [edi+10h]
0x10020c14  push    eax; rclsid
0x10020c15  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x10020c1b  mov     ebx, eax
0x10020c1d  test    ebx, ebx
0x10020c1f  js      loc_10020CCD
0x10020c25  mov     edx, [esi]
0x10020c27  lea     eax, [edi+24h]
0x10020c2a  push    eax
0x10020c2b  push    offset __GUID_56a868af_0ad4_11ce_b03a_0020af0ba770
0x10020c30  push    edx
0x10020c31  mov     ecx, [edx]
0x10020c33  mov     esi, [ecx]
0x10020c35  mov     ecx, esi; this
0x10020c37  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10020c3d  call    esi
0x10020c3f  test    eax, eax
0x10020c41  js      short loc_10020C56
0x10020c43  mov     eax, [edi+24h]
0x10020c46  push    eax
0x10020c47  mov     ecx, [eax]
0x10020c49  mov     esi, [ecx+8]
0x10020c4c  mov     ecx, esi; this
0x10020c4e  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10020c54  call    esi
0x10020c56  mov     eax, [ebp+arg_4]
0x10020c59  mov     ecx, [ebp+var_4]; this
0x10020c5c  push    edi; void *
0x10020c5d  mov     [edi+28h], eax
0x10020c60  mov     [edi+2Ch], eax
0x10020c63  call    ?AddTailI@CBaseList@@IAEPAU__POSITION@@PAX@Z; CBaseList::AddTailI(void *)
0x10020c68  jmp     short loc_10020CD7
0x10020c6a  mov     ecx, [edx+8]
0x10020c6d  xor     esi, esi
0x10020c6f  mov     edx, [edx+4]
0x10020c72  mov     eax, [edi+esi*4]
0x10020c75  cmp     eax, [ecx+esi*4]
0x10020c78  jnz     short loc_10020BFC
0x10020c7a  inc     esi
0x10020c7b  cmp     esi, 4
0x10020c7e  jnz     short loc_10020C72
0x10020c80  xor     esi, esi
0x10020c82  mov     eax, [edi+esi*4+10h]
0x10020c86  cmp     eax, [ecx+esi*4+10h]
0x10020c8a  jnz     loc_10020BFC
0x10020c90  inc     esi
0x10020c91  cmp     esi, 4
0x10020c94  jnz     short loc_10020C82
0x10020c96  test    ecx, ecx
0x10020c98  jz      loc_10020C00
0x10020c9e  cmp     dword ptr [ecx+28h], 0
0x10020ca2  mov     ebx, 800700B7h
0x10020ca7  jz      short loc_10020CCD
0x10020ca9  cmp     dword ptr [ecx+2Ch], 0
0x10020cad  jnz     short loc_10020CCD
0x10020caf  mov     dword ptr [ecx+2Ch], 1
0x10020cb6  mov     ecx, [ecx+24h]
0x10020cb9  test    ecx, ecx
0x10020cbb  jz      short loc_10020CCD
0x10020cbd  mov     eax, [ecx]
0x10020cbf  push    ecx
0x10020cc0  mov     esi, [eax+1Ch]
0x10020cc3  mov     ecx, esi; this
0x10020cc5  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10020ccb  call    esi
0x10020ccd  push    30h ; '0'; unsigned int
0x10020ccf  push    edi; Block
0x10020cd0  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10020cd5  pop     ecx
0x10020cd6  pop     ecx
0x10020cd7  pop     edi
0x10020cd8  pop     esi
0x10020cd9  mov     eax, ebx
0x10020cdb  pop     ebx
0x10020cdc  leave
0x10020cdd  retn    8
```
