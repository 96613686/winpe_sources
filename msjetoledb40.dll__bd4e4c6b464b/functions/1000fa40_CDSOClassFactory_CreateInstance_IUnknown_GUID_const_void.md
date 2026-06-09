# CDSOClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1000fa40`
- end: `0x1000fc53`
- name: `?CreateInstance@CDSOClassFactory@@UAGJPAUIUnknown@@ABU_GUID@@PAPAX@Z`
- size: `531`
- prototype: `int __stdcall(CDSOClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1000fa40`
- `0x10017b50`
- `0x1001c6d0`
- `0x1004ce5d`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1000fb53`
- `KERNEL32!InitializeCriticalSection` at `0x1000fb53`

## pseudocode

```c
HRESULT __stdcall CDSOClassFactory::CreateInstance(
        CDSOClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT result; // eax
  struct IUnknown *v5; // esi
  const struct _GUID *v6; // ecx
  GUID *v7; // edx
  unsigned int v8; // esi
  bool v9; // cf
  char *v10; // eax
  CDataSource *v11; // edi
  struct IUnknown *v12; // eax
  HRESULT v13; // eax
  int v14; // esi
  int v15; // ebx
  HRESULT v16; // [esp+4h] [ebp-4h]

  if ( !a4 )
    return -2147024809;
  v5 = a2;
  *a4 = 0;
  if ( a2 )
  {
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
    return -2147217886;
  }
  else
  {
LABEL_8:
    v10 = (char *)operator new(0xA8u);
    v11 = (CDataSource *)v10;
    if ( !v10 )
      return -2147024882;
    *(_DWORD *)v10 = &CDataSource::`vftable';
    *((_DWORD *)v10 + 1) = 0;
    *((_DWORD *)v10 + 3) = 0;
    *((_DWORD *)v10 + 4) = 0;
    *((_DWORD *)v10 + 5) = 0;
    *((_DWORD *)v10 + 6) = 0;
    *((_DWORD *)v10 + 7) = 0;
    *((_DWORD *)v10 + 8) = 0;
    *((_DWORD *)v10 + 9) = 0;
    *((_DWORD *)v10 + 10) = 0;
    *((_DWORD *)v10 + 11) = 0;
    *((_DWORD *)v10 + 12) = 0;
    *((_DWORD *)v10 + 13) = 0;
    *((_DWORD *)v10 + 14) = 0;
    *((_DWORD *)v10 + 15) = 0;
    *((_DWORD *)v10 + 16) = &CSecuritySession::`vftable';
    *((_DWORD *)v10 + 17) = -1;
    *((_DWORD *)v10 + 18) = -1;
    *((_DWORD *)v10 + 19) = -1;
    *((_DWORD *)v10 + 20) = 0;
    *((_DWORD *)v10 + 22) = 0;
    *((_DWORD *)v10 + 21) = 0;
    *((_DWORD *)v10 + 23) = 0;
    *((_DWORD *)v10 + 24) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v10 + 100));
    *((_DWORD *)v11 + 31) = 0;
    *((_DWORD *)v11 + 32) = 0;
    v12 = (struct IUnknown *)v11;
    *((_DWORD *)v11 + 34) = 0;
    if ( v5 )
      v12 = v5;
    *((_DWORD *)v11 + 35) = 0;
    *((_DWORD *)v11 + 36) = -1;
    *((_DWORD *)v11 + 37) = -1;
    *((_DWORD *)v11 + 39) = 0;
    *((_DWORD *)v11 + 40) = 0;
    *((_DWORD *)v11 + 41) = 0;
    *((_DWORD *)v11 + 38) = &CDBInitProperties::`vftable';
    *((_DWORD *)v11 + 2) = v12;
    if ( v11 )
    {
      v13 = CDataSource::FInit(v11);
      v14 = *(_DWORD *)v11;
      v16 = v13;
      if ( v13 >= 0 )
      {
        result = (*(int (__thiscall **)(_DWORD, CDataSource *, const struct _GUID *, void **))v14)(
                   *(_DWORD *)v14,
                   v11,
                   a3,
                   a4);
        v15 = result;
        if ( result < 0 )
        {
          if ( result == -2147418113 )
            v15 = -2147467262;
          (*(void (__thiscall **)(CDataSource *, int))(*(_DWORD *)v11 + 12))(v11, 1);
          return v15;
        }
      }
      else
      {
        (*(void (__thiscall **)(CDataSource *, int))(v14 + 12))(v11, 1);
        return v16;
      }
    }
    else
    {
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1000fa40  mov     edi, edi
0x1000fa42  push    ebp
0x1000fa43  mov     ebp, esp
0x1000fa45  push    ecx
0x1000fa46  push    ebx
0x1000fa47  mov     ebx, [ebp+arg_C]
0x1000fa4a  test    ebx, ebx
0x1000fa4c  jnz     short loc_1000FA5A
0x1000fa4e  mov     eax, 80070057h
0x1000fa53  pop     ebx
0x1000fa54  mov     esp, ebp
0x1000fa56  pop     ebp
0x1000fa57  retn    10h
0x1000fa5a  push    esi
0x1000fa5b  mov     esi, [ebp+arg_4]
0x1000fa5e  mov     dword ptr [ebx], 0
0x1000fa64  test    esi, esi
0x1000fa66  jz      short loc_1000FA8D
0x1000fa68  mov     ecx, [ebp+arg_8]
0x1000fa6b  mov     edx, offset _IID_IUnknown
0x1000fa70  mov     esi, 0Ch
0x1000fa75  mov     eax, [ecx]
0x1000fa77  cmp     eax, [edx]
0x1000fa79  jnz     loc_1000FBF5
0x1000fa7f  add     ecx, 4
0x1000fa82  add     edx, 4
0x1000fa85  sub     esi, 4
0x1000fa88  jnb     short loc_1000FA75
0x1000fa8a  mov     esi, [ebp+arg_4]
0x1000fa8d  push    edi
0x1000fa8e  push    0A8h; Size
0x1000fa93  call    ??2@YAPAXI@Z; operator new(uint)
0x1000fa98  mov     edi, eax
0x1000fa9a  add     esp, 4
0x1000fa9d  mov     [ebp+var_4], edi
0x1000faa0  test    edi, edi
0x1000faa2  jz      loc_1000FC45
0x1000faa8  mov     dword ptr [edi], offset ??_7CDataSource@@6B@; const CDataSource::`vftable'
0x1000faae  lea     eax, [edi+64h]
0x1000fab1  mov     dword ptr [edi+4], 0
0x1000fab8  mov     dword ptr [edi+0Ch], 0
0x1000fabf  mov     dword ptr [edi+10h], 0
0x1000fac6  mov     dword ptr [edi+14h], 0
0x1000facd  mov     dword ptr [edi+18h], 0
0x1000fad4  mov     dword ptr [edi+1Ch], 0
0x1000fadb  mov     dword ptr [edi+20h], 0
0x1000fae2  mov     dword ptr [edi+24h], 0
0x1000fae9  mov     dword ptr [edi+28h], 0
0x1000faf0  mov     dword ptr [edi+2Ch], 0
0x1000faf7  mov     dword ptr [edi+30h], 0
0x1000fafe  mov     dword ptr [edi+34h], 0
0x1000fb05  mov     dword ptr [edi+38h], 0
0x1000fb0c  mov     dword ptr [edi+3Ch], 0
0x1000fb13  mov     dword ptr [edi+40h], offset ??_7CSecuritySession@@6B@; const CSecuritySession::`vftable'
0x1000fb1a  mov     dword ptr [edi+44h], 0FFFFFFFFh
0x1000fb21  mov     dword ptr [edi+48h], 0FFFFFFFFh
0x1000fb28  mov     dword ptr [edi+4Ch], 0FFFFFFFFh
0x1000fb2f  mov     dword ptr [edi+50h], 0
0x1000fb36  mov     dword ptr [edi+58h], 0
0x1000fb3d  mov     dword ptr [edi+54h], 0
0x1000fb44  mov     dword ptr [edi+5Ch], 0
0x1000fb4b  push    eax; lpCriticalSection
0x1000fb4c  mov     dword ptr [edi+60h], 0
0x1000fb53  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x1000fb59  mov     dword ptr [edi+7Ch], 0
0x1000fb60  test    esi, esi
0x1000fb62  mov     dword ptr [edi+80h], 0
0x1000fb6c  mov     eax, edi
0x1000fb6e  mov     dword ptr [edi+88h], 0
0x1000fb78  cmovnz  eax, esi
0x1000fb7b  mov     dword ptr [edi+8Ch], 0
0x1000fb85  mov     dword ptr [edi+90h], 0FFFFFFFFh
0x1000fb8f  mov     dword ptr [edi+94h], 0FFFFFFFFh
0x1000fb99  mov     dword ptr [edi+9Ch], 0
0x1000fba3  mov     dword ptr [edi+0A0h], 0
0x1000fbad  mov     dword ptr [edi+0A4h], 0
0x1000fbb7  mov     dword ptr [edi+98h], offset ??_7CDBInitProperties@@6B@; const CDBInitProperties::`vftable'
0x1000fbc1  mov     [edi+8], eax
0x1000fbc4  test    edi, edi
0x1000fbc6  jz      short loc_1000FC45
0x1000fbc8  mov     ecx, edi; this
0x1000fbca  call    ?FInit@CDataSource@@QAEJXZ; CDataSource::FInit(void)
0x1000fbcf  mov     esi, [edi]
0x1000fbd1  mov     [ebp+var_4], eax
0x1000fbd4  test    eax, eax
0x1000fbd6  jns     short loc_1000FC02
0x1000fbd8  mov     esi, [esi+0Ch]
0x1000fbdb  mov     ecx, esi
0x1000fbdd  push    1
0x1000fbdf  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000fbe5  mov     ecx, edi
0x1000fbe7  call    esi
0x1000fbe9  mov     eax, [ebp+var_4]
0x1000fbec  pop     edi
0x1000fbed  pop     esi
0x1000fbee  pop     ebx
0x1000fbef  mov     esp, ebp
0x1000fbf1  pop     ebp
0x1000fbf2  retn    10h
0x1000fbf5  pop     esi
0x1000fbf6  mov     eax, 80040E22h
0x1000fbfb  pop     ebx
0x1000fbfc  mov     esp, ebp
0x1000fbfe  pop     ebp
0x1000fbff  retn    10h
0x1000fc02  mov     esi, [esi]
0x1000fc04  mov     ecx, esi
0x1000fc06  push    ebx
0x1000fc07  push    [ebp+arg_8]
0x1000fc0a  push    edi
0x1000fc0b  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000fc11  call    esi
0x1000fc13  mov     ebx, eax
0x1000fc15  test    ebx, ebx
0x1000fc17  jns     short loc_1000FC4A
0x1000fc19  mov     ecx, [edi]
0x1000fc1b  mov     eax, 80004002h
0x1000fc20  cmp     ebx, 8000FFFFh
0x1000fc26  push    1
0x1000fc28  cmovz   ebx, eax
0x1000fc2b  mov     esi, [ecx+0Ch]
0x1000fc2e  mov     ecx, esi
0x1000fc30  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000fc36  mov     ecx, edi
0x1000fc38  call    esi
0x1000fc3a  pop     edi
0x1000fc3b  pop     esi
0x1000fc3c  mov     eax, ebx
0x1000fc3e  pop     ebx
0x1000fc3f  mov     esp, ebp
0x1000fc41  pop     ebp
0x1000fc42  retn    10h
0x1000fc45  mov     eax, 8007000Eh
0x1000fc4a  pop     edi
0x1000fc4b  pop     esi
0x1000fc4c  pop     ebx
0x1000fc4d  mov     esp, ebp
0x1000fc4f  pop     ebp
0x1000fc50  retn    10h
```
