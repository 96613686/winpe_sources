# DllGetClassObject(x,x,x)

- ea: `0x1000f4a0`
- end: `0x1000f681`
- name: `_DllGetClassObject@12`
- size: `481`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1000f4a0`
- `0x1000f690`
- `0x1000f6d0`
- `0x1001c6d0`
- `0x1004ce5d`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1000f598`
- `KERNEL32!LeaveCriticalSection` at `0x1000f625`
- `KERNEL32!LeaveCriticalSection` at `0x1000f598`
- `KERNEL32!LeaveCriticalSection` at `0x1000f625`
- `KERNEL32!EnterCriticalSection` at `0x1000f586`
- `KERNEL32!EnterCriticalSection` at `0x1000f613`
- `KERNEL32!EnterCriticalSection` at `0x1000f586`
- `KERNEL32!EnterCriticalSection` at `0x1000f613`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v3; // ebx
  const IID *v5; // esi
  GUID *v6; // edx
  const IID *v7; // ecx
  unsigned int v8; // edi
  bool v9; // cf
  const IID *v10; // ecx
  GUID *v11; // edx
  unsigned int v12; // edi
  const IID *v13; // ecx
  GUID *v14; // edx
  unsigned int v15; // edi
  const IID *v16; // ecx
  GUID *v17; // edx
  unsigned int v18; // edi
  const IID *v19; // ecx
  GUID *v20; // edx
  unsigned int v21; // edi
  CErrorClassFactory *v22; // eax
  CErrorClassFactory *v23; // edi
  unsigned int v24; // ecx
  GUID *v25; // ecx
  unsigned int v26; // edx
  CDSOClassFactory *v27; // eax
  CDSOClassFactory *v28; // edi
  unsigned int v29; // ecx

  v3 = 0;
  if ( !ppv )
    return -2147024809;
  v5 = rclsid;
  v6 = &CLSID_JOLT;
  *ppv = 0;
  v7 = rclsid;
  v8 = 12;
  while ( v7->Data1 == v6->Data1 )
  {
    v7 = (const IID *)((char *)v7 + 4);
    v6 = (GUID *)((char *)v6 + 4);
    v9 = v8 < 4;
    v8 -= 4;
    if ( v9 )
    {
LABEL_10:
      v13 = riid;
      v14 = &IID_IUnknown;
      v15 = 12;
      while ( v13->Data1 == v14->Data1 )
      {
        v13 = (const IID *)((char *)v13 + 4);
        v14 = (GUID *)((char *)v14 + 4);
        v9 = v15 < 4;
        v15 -= 4;
        if ( v9 )
        {
LABEL_17:
          v19 = rclsid;
          v20 = &CLSID_JOLTERRORINFO;
          v21 = 12;
          do
          {
            if ( v19->Data1 != v20->Data1 )
            {
              v25 = &CLSID_JOLT;
              v26 = 12;
              while ( v5->Data1 == v25->Data1 )
              {
                v5 = (const IID *)((char *)v5 + 4);
                v25 = (GUID *)((char *)v25 + 4);
                v9 = v26 < 4;
                v26 -= 4;
                if ( v9 )
                {
                  v27 = (CDSOClassFactory *)operator new(8u);
                  v28 = v27;
                  if ( !v27 )
                    return -2147024882;
                  *(_DWORD *)v27 = &CDSOClassFactory::`vftable';
                  *((_DWORD *)v27 + 1) = 0;
                  EnterCriticalSection(&g_CriticalSection);
                  _InterlockedIncrement(&g_cObj);
                  LeaveCriticalSection(&g_CriticalSection);
                  v3 = (**(int (__thiscall ***)(_DWORD, CDSOClassFactory *, const IID *const, LPVOID *))v28)(
                         **(_DWORD **)v28,
                         v28,
                         riid,
                         ppv);
                  if ( v3 < 0 )
                  {
                    CDSOClassFactory::`scalar deleting destructor'(v28, v29);
                    return v3;
                  }
                  return v3;
                }
              }
              return v3;
            }
            v19 = (const IID *)((char *)v19 + 4);
            v20 = (GUID *)((char *)v20 + 4);
            v9 = v21 < 4;
            v21 -= 4;
          }
          while ( !v9 );
          v22 = (CErrorClassFactory *)operator new(8u);
          v23 = v22;
          if ( !v22 )
            return -2147024882;
          *(_DWORD *)v22 = &CErrorClassFactory::`vftable';
          *((_DWORD *)v22 + 1) = 0;
          EnterCriticalSection(&g_CriticalSection);
          _InterlockedIncrement(&g_cObj);
          LeaveCriticalSection(&g_CriticalSection);
          v3 = (**(int (__thiscall ***)(_DWORD, CErrorClassFactory *, const IID *const, LPVOID *))v23)(
                 **(_DWORD **)v23,
                 v23,
                 riid,
                 ppv);
          if ( v3 >= 0 )
            return v3;
          CErrorClassFactory::`scalar deleting destructor'(v23, v24);
          return v3;
        }
      }
      v16 = riid;
      v17 = &IID_IClassFactory;
      v18 = 12;
      while ( v16->Data1 == v17->Data1 )
      {
        v16 = (const IID *)((char *)v16 + 4);
        v17 = (GUID *)((char *)v17 + 4);
        v9 = v18 < 4;
        v18 -= 4;
        if ( v9 )
          goto LABEL_17;
      }
      return -2147467262;
    }
  }
  v10 = rclsid;
  v11 = &CLSID_JOLTERRORINFO;
  v12 = 12;
  while ( v10->Data1 == v11->Data1 )
  {
    v10 = (const IID *)((char *)v10 + 4);
    v11 = (GUID *)((char *)v11 + 4);
    v9 = v12 < 4;
    v12 -= 4;
    if ( v9 )
      goto LABEL_10;
  }
  return -2147221231;
}

```

## disassembly

```asm
0x1000f4a0  mov     edi, edi
0x1000f4a2  push    ebp
0x1000f4a3  mov     ebp, esp
0x1000f4a5  mov     eax, [ebp+ppv]
0x1000f4a8  push    ebx
0x1000f4a9  xor     ebx, ebx
0x1000f4ab  test    eax, eax
0x1000f4ad  jnz     short loc_1000F4BB
0x1000f4af  mov     ebx, 80070057h
0x1000f4b4  mov     eax, ebx
0x1000f4b6  pop     ebx
0x1000f4b7  pop     ebp
0x1000f4b8  retn    0Ch
0x1000f4bb  push    esi
0x1000f4bc  mov     esi, [ebp+rclsid]
0x1000f4bf  mov     edx, offset ?CLSID_JOLT@@3U_GUID@@B; _GUID const CLSID_JOLT
0x1000f4c4  push    edi
0x1000f4c5  mov     [eax], ebx
0x1000f4c7  mov     ecx, esi
0x1000f4c9  mov     edi, 0Ch
0x1000f4ce  mov     edi, edi
0x1000f4d0  mov     eax, [ecx]
0x1000f4d2  cmp     eax, [edx]
0x1000f4d4  jnz     short loc_1000F4E3
0x1000f4d6  add     ecx, 4
0x1000f4d9  add     edx, 4
0x1000f4dc  sub     edi, 4
0x1000f4df  jnb     short loc_1000F4D0
0x1000f4e1  jmp     short loc_1000F505
0x1000f4e3  mov     ecx, esi
0x1000f4e5  mov     edx, offset ?CLSID_JOLTERRORINFO@@3U_GUID@@B; _GUID const CLSID_JOLTERRORINFO
0x1000f4ea  mov     edi, 0Ch
0x1000f4ef  nop
0x1000f4f0  mov     eax, [ecx]
0x1000f4f2  cmp     eax, [edx]
0x1000f4f4  jnz     loc_1000F673
0x1000f4fa  add     ecx, 4
0x1000f4fd  add     edx, 4
0x1000f500  sub     edi, 4
0x1000f503  jnb     short loc_1000F4F0
0x1000f505  mov     ecx, [ebp+riid]
0x1000f508  mov     edx, offset _IID_IUnknown
0x1000f50d  mov     edi, 0Ch
0x1000f512  mov     eax, [ecx]
0x1000f514  cmp     eax, [edx]
0x1000f516  jnz     short loc_1000F525
0x1000f518  add     ecx, 4
0x1000f51b  add     edx, 4
0x1000f51e  sub     edi, 4
0x1000f521  jnb     short loc_1000F512
0x1000f523  jmp     short loc_1000F547
0x1000f525  mov     ecx, [ebp+riid]
0x1000f528  mov     edx, offset _IID_IClassFactory
0x1000f52d  mov     edi, 0Ch
0x1000f532  mov     eax, [ecx]
0x1000f534  cmp     eax, [edx]
0x1000f536  jnz     loc_1000F665
0x1000f53c  add     ecx, 4
0x1000f53f  add     edx, 4
0x1000f542  sub     edi, 4
0x1000f545  jnb     short loc_1000F532
0x1000f547  mov     ecx, esi
0x1000f549  mov     edx, offset ?CLSID_JOLTERRORINFO@@3U_GUID@@B; _GUID const CLSID_JOLTERRORINFO
0x1000f54e  mov     edi, 0Ch
0x1000f553  mov     eax, [ecx]
0x1000f555  cmp     eax, [edx]
0x1000f557  jnz     short loc_1000F5CE
0x1000f559  add     ecx, 4
0x1000f55c  add     edx, 4
0x1000f55f  sub     edi, 4
0x1000f562  jnb     short loc_1000F553
0x1000f564  push    8; Size
0x1000f566  call    ??2@YAPAXI@Z; operator new(uint)
0x1000f56b  mov     edi, eax
0x1000f56d  add     esp, 4
0x1000f570  test    edi, edi
0x1000f572  jz      loc_1000F657
0x1000f578  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000f57d  mov     dword ptr [edi], offset ??_7CErrorClassFactory@@6B@; const CErrorClassFactory::`vftable'
0x1000f583  mov     [edi+4], ebx
0x1000f586  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000f58c  lock inc ?g_cObj@@3JA; long g_cObj
0x1000f593  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000f598  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000f59e  push    [ebp+ppv]
0x1000f5a1  mov     eax, [edi]
0x1000f5a3  push    [ebp+riid]
0x1000f5a6  push    edi
0x1000f5a7  mov     esi, [eax]
0x1000f5a9  mov     ecx, esi
0x1000f5ab  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000f5b1  call    esi
0x1000f5b3  mov     ebx, eax
0x1000f5b5  test    ebx, ebx
0x1000f5b7  jns     loc_1000F678
0x1000f5bd  push    ecx; unsigned int
0x1000f5be  mov     ecx, edi; this
0x1000f5c0  call    ??_GCErrorClassFactory@@QAEPAXI@Z; CErrorClassFactory::`scalar deleting destructor'(uint)
0x1000f5c5  pop     edi
0x1000f5c6  pop     esi
0x1000f5c7  mov     eax, ebx
0x1000f5c9  pop     ebx
0x1000f5ca  pop     ebp
0x1000f5cb  retn    0Ch
0x1000f5ce  mov     ecx, offset ?CLSID_JOLT@@3U_GUID@@B; _GUID const CLSID_JOLT
0x1000f5d3  mov     edx, 0Ch
0x1000f5d8  nop     dword ptr [eax+eax+00000000h]
0x1000f5e0  mov     eax, [esi]
0x1000f5e2  cmp     eax, [ecx]
0x1000f5e4  jnz     loc_1000F678
0x1000f5ea  add     esi, 4
0x1000f5ed  add     ecx, 4
0x1000f5f0  sub     edx, 4
0x1000f5f3  jnb     short loc_1000F5E0
0x1000f5f5  push    8; Size
0x1000f5f7  call    ??2@YAPAXI@Z; operator new(uint)
0x1000f5fc  mov     edi, eax
0x1000f5fe  add     esp, 4
0x1000f601  test    edi, edi
0x1000f603  jz      short loc_1000F657
0x1000f605  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000f60a  mov     dword ptr [edi], offset ??_7CDSOClassFactory@@6B@; const CDSOClassFactory::`vftable'
0x1000f610  mov     [edi+4], ebx
0x1000f613  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000f619  lock inc ?g_cObj@@3JA; long g_cObj
0x1000f620  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000f625  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000f62b  push    [ebp+ppv]
0x1000f62e  mov     eax, [edi]
0x1000f630  push    [ebp+riid]
0x1000f633  push    edi
0x1000f634  mov     esi, [eax]
0x1000f636  mov     ecx, esi
0x1000f638  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000f63e  call    esi
0x1000f640  mov     ebx, eax
0x1000f642  test    ebx, ebx
0x1000f644  jns     short loc_1000F678
0x1000f646  push    ecx; unsigned int
0x1000f647  mov     ecx, edi; this
0x1000f649  call    ??_GCDSOClassFactory@@QAEPAXI@Z; CDSOClassFactory::`scalar deleting destructor'(uint)
0x1000f64e  pop     edi
0x1000f64f  pop     esi
0x1000f650  mov     eax, ebx
0x1000f652  pop     ebx
0x1000f653  pop     ebp
0x1000f654  retn    0Ch
0x1000f657  pop     edi
0x1000f658  mov     ebx, 8007000Eh
0x1000f65d  pop     esi
0x1000f65e  mov     eax, ebx
0x1000f660  pop     ebx
0x1000f661  pop     ebp
0x1000f662  retn    0Ch
0x1000f665  pop     edi
0x1000f666  mov     ebx, 80004002h
0x1000f66b  pop     esi
0x1000f66c  mov     eax, ebx
0x1000f66e  pop     ebx
0x1000f66f  pop     ebp
0x1000f670  retn    0Ch
0x1000f673  mov     ebx, 80040111h
0x1000f678  pop     edi
0x1000f679  pop     esi
0x1000f67a  mov     eax, ebx
0x1000f67c  pop     ebx
0x1000f67d  pop     ebp
0x1000f67e  retn    0Ch
```
