# FindCompatiblePinFactoryIdentifier(IKsPin *,IKsPin *,ulong,KSIDENTIFIER *)

- ea: `0x1001fd03`
- end: `0x1001fe5c`
- name: `?FindCompatiblePinFactoryIdentifier@@YGJPAUIKsPin@@0KPAUKSIDENTIFIER@@@Z`
- size: `345`
- prototype: `int __stdcall(struct IKsPin *, struct IKsPin *, unsigned int, struct KSIDENTIFIER *)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x100115a5`
- `0x10011c70`
- `0x100150a0`
- `0x10015b70`
- `0x1001a8f0`
- `0x1001fe62`
- `0x1001feac`

## callees

- `0x1001fcc6`
- `0x1001fd03`
- `0x1002d510`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1001fd7f`
- `ole32!CoTaskMemFree` at `0x1001fe00`
- `ole32!CoTaskMemFree` at `0x1001fe4d`
- `ole32!CoTaskMemFree` at `0x1001fd7f`
- `ole32!CoTaskMemFree` at `0x1001fe00`
- `ole32!CoTaskMemFree` at `0x1001fe4d`

## pseudocode

```c
int __userpurge FindCompatiblePinFactoryIdentifier@<eax>(
        int *a1@<edx>,
        int *a2@<ecx>,
        struct IKsPin *a3,
        struct IKsPin *a4,
        unsigned int a5,
        struct KSIDENTIFIER *a6)
{
  int v6; // esi
  int v8; // eax
  int Identifier; // ebx
  GUID *v10; // esi
  int v11; // ebx
  int v12; // eax
  int v13; // edi
  GUID *v15; // edi
  GUID *v16; // esi
  int v17; // eax
  GUID *v18; // ecx
  struct KSIDENTIFIER *v19; // [esp-4h] [ebp-3Ch]
  struct KSIDENTIFIER *v20; // [esp+0h] [ebp-38h]
  struct KSIDENTIFIER *v21; // [esp+0h] [ebp-38h]
  unsigned int v22; // [esp+4h] [ebp-34h]
  unsigned int v23; // [esp+4h] [ebp-34h]
  GUID v24; // [esp+10h] [ebp-28h] BYREF
  int v25; // [esp+20h] [ebp-18h]
  int v26; // [esp+24h] [ebp-14h]
  _DWORD *v27; // [esp+2Ch] [ebp-Ch]
  LPVOID v28; // [esp+30h] [ebp-8h] BYREF
  LPVOID pv; // [esp+34h] [ebp-4h] BYREF

  v6 = *a2;
  if ( a3 == (struct IKsPin *)6 )
    v8 = (*(int (__thiscall **)(_DWORD, int *, LPVOID *))(v6 + 12))(*(_DWORD *)(v6 + 12), a2, &pv);
  else
    v8 = (*(int (__thiscall **)(_DWORD, int *, LPVOID *))(v6 + 16))(*(_DWORD *)(v6 + 16), a2, &pv);
  Identifier = v8;
  if ( v8 >= 0 )
  {
    v10 = (GUID *)((char *)pv + 8);
    if ( a1 )
    {
      v11 = *a1;
      if ( a3 == (struct IKsPin *)6 )
        v12 = (*(int (__thiscall **)(_DWORD, int *, LPVOID *))(v11 + 12))(*(_DWORD *)(v11 + 12), a1, &v28);
      else
        v12 = (*(int (__thiscall **)(_DWORD, int *, LPVOID *))(v11 + 16))(*(_DWORD *)(v11 + 16), a1, &v28);
      v13 = v12;
      if ( v12 < 0 )
      {
        CoTaskMemFree(pv);
        return v13;
      }
      Identifier = -2147467259;
      v15 = (GUID *)((char *)v28 + 8);
      v27 = pv;
      if ( *((_DWORD *)pv + 1) )
      {
        while ( *((_DWORD *)v28 + 1) )
        {
          Identifier = FindIdentifier(*((struct KSIDENTIFIER **)v28 + 1), v20, v22);
          if ( Identifier >= 0 )
            goto LABEL_18;
          v10 = (GUID *)((char *)v10 + 24);
          --v27[1];
          Identifier = FindIdentifier(*((struct KSIDENTIFIER **)pv + 1), v21, v23);
          if ( Identifier >= 0 )
          {
            v10 = v15;
LABEL_18:
            qmemcpy(a4, v10, 0x18u);
            break;
          }
          v15 = (GUID *)((char *)v15 + 24);
          --*((_DWORD *)v28 + 1);
          v27 = pv;
          if ( !*((_DWORD *)pv + 1) )
            break;
        }
      }
      CoTaskMemFree(v28);
    }
    else
    {
      if ( a3 == (struct IKsPin *)5 )
      {
        v19 = (struct KSIDENTIFIER *)*((_DWORD *)pv + 1);
        v24 = _GUID_1a8766a0_62ce_11cf_a5d6_28db04c10000;
        v16 = (GUID *)((char *)pv + 8);
        v25 = 0;
        v26 = 0;
        v17 = FindIdentifier(v19, v20, v22);
        v18 = &v24;
        if ( v17 < 0 )
          v18 = v16;
        v10 = v18;
      }
      qmemcpy(a4, v10, 0x18u);
    }
    CoTaskMemFree(pv);
  }
  return Identifier;
}

```

## disassembly

```asm
0x1001fd03  mov     edi, edi
0x1001fd05  push    ebp
0x1001fd06  mov     ebp, esp
0x1001fd08  sub     esp, 2Ch
0x1001fd0b  lea     eax, [ebp+pv]
0x1001fd0e  cmp     [ebp+arg_0], 6
0x1001fd12  push    ebx
0x1001fd13  push    esi; unsigned int
0x1001fd14  mov     esi, [ecx]
0x1001fd16  push    edi; struct KSIDENTIFIER *
0x1001fd17  push    eax
0x1001fd18  mov     edi, edx
0x1001fd1a  push    ecx
0x1001fd1b  jnz     short loc_1001FD2B
0x1001fd1d  mov     ecx, [esi+0Ch]; this
0x1001fd20  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001fd26  call    dword ptr [esi+0Ch]
0x1001fd29  jmp     short loc_1001FD37
0x1001fd2b  mov     ecx, [esi+10h]; this
0x1001fd2e  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001fd34  call    dword ptr [esi+10h]
0x1001fd37  mov     ebx, eax
0x1001fd39  test    ebx, ebx
0x1001fd3b  js      loc_1001FE53
0x1001fd41  mov     eax, [ebp+pv]
0x1001fd44  lea     esi, [eax+8]
0x1001fd47  test    edi, edi
0x1001fd49  jz      loc_1001FE08
0x1001fd4f  cmp     [ebp+arg_0], 6
0x1001fd53  lea     eax, [ebp+var_8]
0x1001fd56  mov     ebx, [edi]
0x1001fd58  push    eax
0x1001fd59  push    edi
0x1001fd5a  jnz     short loc_1001FD6A
0x1001fd5c  mov     ecx, [ebx+0Ch]; this
0x1001fd5f  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001fd65  call    dword ptr [ebx+0Ch]
0x1001fd68  jmp     short loc_1001FD76
0x1001fd6a  mov     ecx, [ebx+10h]; this
0x1001fd6d  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001fd73  call    dword ptr [ebx+10h]
0x1001fd76  mov     edi, eax
0x1001fd78  test    edi, edi
0x1001fd7a  jns     short loc_1001FD8C
0x1001fd7c  push    [ebp+pv]; pv
0x1001fd7f  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001fd85  mov     eax, edi
0x1001fd87  jmp     loc_1001FE55
0x1001fd8c  mov     ecx, [ebp+pv]
0x1001fd8f  mov     ebx, 80004005h
0x1001fd94  mov     edi, [ebp+var_8]
0x1001fd97  add     edi, 8
0x1001fd9a  mov     [ebp+var_C], ecx
0x1001fd9d  cmp     dword ptr [ecx+4], 0
0x1001fda1  jz      short loc_1001FDFD
0x1001fda3  mov     eax, [ebp+var_8]
0x1001fda6  cmp     dword ptr [eax+4], 0
0x1001fdaa  jz      short loc_1001FDFD
0x1001fdac  push    dword ptr [eax+4]; struct KSIDENTIFIER *
0x1001fdaf  mov     edx, edi
0x1001fdb1  mov     ecx, esi
0x1001fdb3  call    ?FindIdentifier@@YGJPAUKSIDENTIFIER@@0K@Z; FindIdentifier(KSIDENTIFIER *,KSIDENTIFIER *,ulong)
0x1001fdb8  mov     ebx, eax
0x1001fdba  test    ebx, ebx
0x1001fdbc  jns     short loc_1001FDF5
0x1001fdbe  mov     eax, [ebp+var_C]
0x1001fdc1  add     esi, 18h
0x1001fdc4  mov     edx, esi
0x1001fdc6  mov     ecx, edi
0x1001fdc8  dec     dword ptr [eax+4]
0x1001fdcb  mov     eax, [ebp+pv]
0x1001fdce  push    dword ptr [eax+4]; struct KSIDENTIFIER *
0x1001fdd1  call    ?FindIdentifier@@YGJPAUKSIDENTIFIER@@0K@Z; FindIdentifier(KSIDENTIFIER *,KSIDENTIFIER *,ulong)
0x1001fdd6  mov     ebx, eax
0x1001fdd8  test    ebx, ebx
0x1001fdda  jns     short loc_1001FDF3
0x1001fddc  mov     eax, [ebp+var_8]
0x1001fddf  add     edi, 18h
0x1001fde2  dec     dword ptr [eax+4]
0x1001fde5  mov     eax, [ebp+pv]
0x1001fde8  mov     [ebp+var_C], eax
0x1001fdeb  cmp     dword ptr [eax+4], 0
0x1001fdef  jnz     short loc_1001FDA3
0x1001fdf1  jmp     short loc_1001FDFD
0x1001fdf3  mov     esi, edi
0x1001fdf5  mov     edi, [ebp+arg_4]
0x1001fdf8  push    6
0x1001fdfa  pop     ecx
0x1001fdfb  rep movsd
0x1001fdfd  push    [ebp+var_8]; pv
0x1001fe00  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001fe06  jmp     short loc_1001FE4A
0x1001fe08  cmp     [ebp+arg_0], 5
0x1001fe0c  jnz     short loc_1001FE42
0x1001fe0e  push    dword ptr [eax+4]; struct KSIDENTIFIER *
0x1001fe11  mov     esi, offset __GUID_1a8766a0_62ce_11cf_a5d6_28db04c10000
0x1001fe16  lea     edi, [ebp+var_28]
0x1001fe19  lea     ecx, [ebp+var_28]
0x1001fe1c  movsd
0x1001fe1d  movsd
0x1001fe1e  movsd
0x1001fe1f  movsd
0x1001fe20  lea     esi, [eax+8]
0x1001fe23  mov     [ebp+var_18], 0
0x1001fe2a  mov     edx, esi
0x1001fe2c  mov     [ebp+var_14], 0
0x1001fe33  call    ?FindIdentifier@@YGJPAUKSIDENTIFIER@@0K@Z; FindIdentifier(KSIDENTIFIER *,KSIDENTIFIER *,ulong)
0x1001fe38  test    eax, eax
0x1001fe3a  lea     ecx, [ebp+var_28]
0x1001fe3d  cmovs   ecx, esi
0x1001fe40  mov     esi, ecx
0x1001fe42  mov     edi, [ebp+arg_4]
0x1001fe45  push    6
0x1001fe47  pop     ecx
0x1001fe48  rep movsd
0x1001fe4a  push    [ebp+pv]; pv
0x1001fe4d  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001fe53  mov     eax, ebx
0x1001fe55  pop     edi
0x1001fe56  pop     esi
0x1001fe57  pop     ebx
0x1001fe58  leave
0x1001fe59  retn    8
```
