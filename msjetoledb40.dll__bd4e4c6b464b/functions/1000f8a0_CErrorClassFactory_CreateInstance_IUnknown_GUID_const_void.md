# CErrorClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1000f8a0`
- end: `0x1000f9ab`
- name: `?CreateInstance@CErrorClassFactory@@UAGJPAUIUnknown@@ABU_GUID@@PAPAX@Z`
- size: `267`
- prototype: `int __stdcall(CErrorClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1000ecc0`
- `0x1000f8a0`
- `0x1001c6d0`
- `0x1004ce5d`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1000f91d`
- `KERNEL32!InitializeCriticalSection` at `0x1000f91d`

## pseudocode

```c
int __stdcall CErrorClassFactory::CreateInstance(
        CErrorClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int result; // eax
  struct IUnknown *v5; // esi
  const struct _GUID *v6; // ecx
  GUID *v7; // edx
  unsigned int v8; // esi
  bool v9; // cf
  char *v10; // eax
  CError *v11; // edi
  struct IUnknown *v12; // eax
  _DWORD *v13; // eax
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  int v16; // esi

  if ( !a4 )
    return -2147024809;
  v5 = a2;
  *a4 = 0;
  if ( !a2 )
  {
LABEL_8:
    v10 = (char *)operator new(0x28u);
    v11 = (CError *)v10;
    if ( v10 )
    {
      *(_DWORD *)v10 = &CError::`vftable';
      *((_DWORD *)v10 + 1) = 0;
      *((_DWORD *)v10 + 3) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v10 + 16));
      v12 = (struct IUnknown *)v11;
      if ( v5 )
        v12 = v5;
      *((_DWORD *)v11 + 2) = v12;
      if ( v11 )
      {
        v13 = operator new(0xCu);
        if ( v13 )
        {
          *v13 = &CImpIErrorLookup::`vftable';
          v13[1] = 0;
          v13[2] = v11;
          *((_DWORD *)v11 + 3) = v13;
          result = (**(int (__thiscall ***)(_DWORD, CError *, const struct _GUID *, void **))v11)(
                     **(_DWORD **)v11,
                     v11,
                     a3,
                     a4);
          v16 = result;
          if ( result < 0 )
          {
            CError::`scalar deleting destructor'(v11, v15);
            return v16;
          }
          return result;
        }
        *((_DWORD *)v11 + 3) = 0;
        CError::`scalar deleting destructor'(v11, v14);
      }
    }
    return -2147024882;
  }
  v6 = a3;
  v7 = &IID_IUnknown;
  v8 = 12;
  while ( v6->Data1 == v7->Data1 )
  {
    v6 = (const struct _GUID *)((char *)v6 + 4);
    v7 = (GUID *)((char *)v7 + 4);
    v9 = v8 < 4;
    v8 -= 4;
    if ( v9 )
    {
      v5 = a2;
      goto LABEL_8;
    }
  }
  return -2147467262;
}

```

## disassembly

```asm
0x1000f8a0  mov     edi, edi
0x1000f8a2  push    ebp
0x1000f8a3  mov     ebp, esp
0x1000f8a5  push    ecx
0x1000f8a6  push    ebx
0x1000f8a7  mov     ebx, [ebp+arg_C]
0x1000f8aa  test    ebx, ebx
0x1000f8ac  jnz     short loc_1000F8BA
0x1000f8ae  mov     eax, 80070057h
0x1000f8b3  pop     ebx
0x1000f8b4  mov     esp, ebp
0x1000f8b6  pop     ebp
0x1000f8b7  retn    10h
0x1000f8ba  push    esi
0x1000f8bb  mov     esi, [ebp+arg_4]
0x1000f8be  mov     dword ptr [ebx], 0
0x1000f8c4  test    esi, esi
0x1000f8c6  jz      short loc_1000F8ED
0x1000f8c8  mov     ecx, [ebp+arg_8]
0x1000f8cb  mov     edx, offset _IID_IUnknown
0x1000f8d0  mov     esi, 0Ch
0x1000f8d5  mov     eax, [ecx]
0x1000f8d7  cmp     eax, [edx]
0x1000f8d9  jnz     loc_1000F981
0x1000f8df  add     ecx, 4
0x1000f8e2  add     edx, 4
0x1000f8e5  sub     esi, 4
0x1000f8e8  jnb     short loc_1000F8D5
0x1000f8ea  mov     esi, [ebp+arg_4]
0x1000f8ed  push    edi
0x1000f8ee  push    28h ; '('; Size
0x1000f8f0  call    ??2@YAPAXI@Z; operator new(uint)
0x1000f8f5  mov     edi, eax
0x1000f8f7  add     esp, 4
0x1000f8fa  mov     [ebp+var_4], edi
0x1000f8fd  test    edi, edi
0x1000f8ff  jz      loc_1000F99D
0x1000f905  lea     ecx, [edi+10h]
0x1000f908  mov     dword ptr [edi], offset ??_7CError@@6B@; const CError::`vftable'
0x1000f90e  push    ecx; lpCriticalSection
0x1000f90f  mov     dword ptr [edi+4], 0
0x1000f916  mov     dword ptr [edi+0Ch], 0
0x1000f91d  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x1000f923  test    esi, esi
0x1000f925  mov     eax, edi
0x1000f927  cmovnz  eax, esi
0x1000f92a  mov     [edi+8], eax
0x1000f92d  test    edi, edi
0x1000f92f  jz      short loc_1000F99D
0x1000f931  push    0Ch; Size
0x1000f933  call    ??2@YAPAXI@Z; operator new(uint)
0x1000f938  add     esp, 4
0x1000f93b  mov     [ebp+var_4], eax
0x1000f93e  test    eax, eax
0x1000f940  jz      short loc_1000F98E
0x1000f942  mov     dword ptr [eax], offset ??_7CImpIErrorLookup@@6B@; const CImpIErrorLookup::`vftable'
0x1000f948  mov     dword ptr [eax+4], 0
0x1000f94f  mov     [eax+8], edi
0x1000f952  mov     [edi+0Ch], eax
0x1000f955  mov     eax, [edi]
0x1000f957  push    ebx
0x1000f958  push    [ebp+arg_8]
0x1000f95b  mov     esi, [eax]
0x1000f95d  mov     ecx, esi
0x1000f95f  push    edi
0x1000f960  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000f966  call    esi
0x1000f968  mov     esi, eax
0x1000f96a  test    esi, esi
0x1000f96c  jns     short loc_1000F9A2
0x1000f96e  push    ecx; unsigned int
0x1000f96f  mov     ecx, edi; this
0x1000f971  call    ??_GCError@@QAEPAXI@Z; CError::`scalar deleting destructor'(uint)
0x1000f976  pop     edi
0x1000f977  mov     eax, esi
0x1000f979  pop     esi
0x1000f97a  pop     ebx
0x1000f97b  mov     esp, ebp
0x1000f97d  pop     ebp
0x1000f97e  retn    10h
0x1000f981  pop     esi
0x1000f982  mov     eax, 80004002h
0x1000f987  pop     ebx
0x1000f988  mov     esp, ebp
0x1000f98a  pop     ebp
0x1000f98b  retn    10h
0x1000f98e  push    ecx; unsigned int
0x1000f98f  mov     ecx, edi; this
0x1000f991  mov     dword ptr [edi+0Ch], 0
0x1000f998  call    ??_GCError@@QAEPAXI@Z; CError::`scalar deleting destructor'(uint)
0x1000f99d  mov     eax, 8007000Eh
0x1000f9a2  pop     edi
0x1000f9a3  pop     esi
0x1000f9a4  pop     ebx
0x1000f9a5  mov     esp, ebp
0x1000f9a7  pop     ebp
0x1000f9a8  retn    10h
```
