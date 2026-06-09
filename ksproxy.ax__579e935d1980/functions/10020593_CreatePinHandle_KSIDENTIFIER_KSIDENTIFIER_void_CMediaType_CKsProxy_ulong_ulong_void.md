# CreatePinHandle(KSIDENTIFIER &,KSIDENTIFIER &,void *,CMediaType *,CKsProxy *,ulong,ulong,void * *)

- ea: `0x10020593`
- end: `0x1002069d`
- name: `?CreatePinHandle@@YGJAAUKSIDENTIFIER@@0PAXPAVCMediaType@@PAVCKsProxy@@KKPAPAX@Z`
- size: `266`
- prototype: `int __stdcall(struct KSIDENTIFIER *, struct KSIDENTIFIER *, void *, struct CMediaType *, struct CKsProxy *, unsigned int, unsigned int, void **)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x100113e0`
- `0x100115a5`
- `0x10011c70`
- `0x10014ed0`
- `0x100150a0`
- `0x10015b70`
- `0x1001a8f0`

## callees

- `0x1000665f`
- `0x1001f6ea`
- `0x10020593`
- `0x10020b2b`
- `0x1002d510`

## import_xrefs

- `KERNEL32!Sleep` at `0x1002061f`
- `KERNEL32!Sleep` at `0x1002061f`
- `ole32!CoTaskMemFree` at `0x1002068e`
- `ole32!CoTaskMemFree` at `0x1002068e`
- `ksuser!KsCreatePin` at `0x1002060d`
- `ksuser!KsCreatePin` at `0x1002060d`

## pseudocode

```c
int __userpurge CreatePinHandle@<eax>(
        const void *a1@<edx>,
        const void *a2@<ecx>,
        struct KSIDENTIFIER *a3,
        struct KSIDENTIFIER *a4,
        _DWORD *a5,
        struct CMediaType *a6,
        struct CKsProxy *DesiredAccess,
        void **ConnectionHandle,
        unsigned int a9,
        void **a10)
{
  int result; // eax
  PKSPIN_CONNECT v13; // edx
  int v14; // ebx
  char *v15; // ecx
  void *v16; // eax
  signed int Pin; // edi
  signed int v18; // esi
  void **v19; // [esp+0h] [ebp-18h]
  void *v20; // [esp+0h] [ebp-18h]
  unsigned int *v21; // [esp+4h] [ebp-14h]
  void *v22; // [esp+4h] [ebp-14h]
  unsigned int v23; // [esp+10h] [ebp-8h] BYREF
  PKSPIN_CONNECT Connect; // [esp+14h] [ebp-4h] BYREF

  result = InitializeDataFormat((const struct CMediaType *)&Connect, (unsigned int)&v23, v19, v21);
  if ( result >= 0 )
  {
    v13 = Connect;
    qmemcpy(Connect, a2, 0x18u);
    qmemcpy(&v13->Medium, a1, sizeof(v13->Medium));
    v14 = 0;
    v13->PinId = (ULONG)a6;
    v15 = (char *)(a5 + 27);
    v13->PinToHandle = a3;
    v13->Priority.PriorityClass = 0x40000000;
    v13->Priority.PrioritySubClass = 0x40000000;
    v23 = (unsigned int)(a5 + 27);
    do
    {
      v16 = (void *)(*(int (__thiscall **)(_DWORD, char *))(*(_DWORD *)v15 + 12))(*(_DWORD *)(*(_DWORD *)v15 + 12), v15);
      Pin = KsCreatePin(v16, Connect, (ACCESS_MASK)DesiredAccess, ConnectionHandle);
      if ( Pin != 21 )
        break;
      Sleep(0x3E8u);
      v15 = (char *)v23;
      ++v14;
    }
    while ( v14 < 5 );
    v18 = (unsigned __int16)Pin | 0x80070000;
    if ( Pin <= 0 )
      v18 = Pin;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(0x19u, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), v18);
    if ( v18 < 0 )
    {
      *ConnectionHandle = 0;
    }
    else if ( a5[56] )
    {
      v18 = SetSyncSource(v20, v22);
    }
    else
    {
      v18 = 0;
    }
    CoTaskMemFree(Connect);
    return v18;
  }
  return result;
}

```

## disassembly

```asm
0x10020593  mov     edi, edi
0x10020595  push    ebp
0x10020596  mov     ebp, esp
0x10020598  sub     esp, 0Ch
0x1002059b  lea     eax, [ebp+var_8]
0x1002059e  push    ebx
0x1002059f  push    esi; void *
0x100205a0  push    edi; void *
0x100205a1  push    eax; unsigned int
0x100205a2  lea     eax, [ebp+Connect]
0x100205a5  mov     ebx, edx
0x100205a7  push    eax; struct CMediaType *
0x100205a8  push    40h ; '@'
0x100205aa  mov     esi, ecx
0x100205ac  mov     ecx, [ebp+arg_4]
0x100205af  pop     edx
0x100205b0  call    ?InitializeDataFormat@@YGJPBVCMediaType@@KPAPAXPAK@Z; InitializeDataFormat(CMediaType const *,ulong,void * *,ulong *)
0x100205b5  test    eax, eax
0x100205b7  js      loc_10020696
0x100205bd  mov     edx, [ebp+Connect]
0x100205c0  mov     edi, edx
0x100205c2  mov     eax, [ebp+arg_C]
0x100205c5  push    6
0x100205c7  pop     ecx
0x100205c8  rep movsd
0x100205ca  push    6
0x100205cc  mov     esi, ebx
0x100205ce  lea     edi, [edx+18h]
0x100205d1  pop     ecx
0x100205d2  rep movsd
0x100205d4  mov     ecx, [ebp+arg_8]
0x100205d7  xor     ebx, ebx
0x100205d9  mov     [edx+30h], eax
0x100205dc  add     ecx, 6Ch ; 'l'
0x100205df  mov     eax, [ebp+arg_0]
0x100205e2  mov     [edx+34h], eax
0x100205e5  mov     eax, 40000000h
0x100205ea  mov     [edx+38h], eax
0x100205ed  mov     [edx+3Ch], eax
0x100205f0  mov     [ebp+var_8], ecx
0x100205f3  mov     eax, [ecx]
0x100205f5  push    ecx
0x100205f6  mov     esi, [eax+0Ch]
0x100205f9  mov     ecx, esi; this
0x100205fb  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10020601  call    esi
0x10020603  push    [ebp+ConnectionHandle]; ConnectionHandle
0x10020606  push    [ebp+DesiredAccess]; DesiredAccess
0x10020609  push    [ebp+Connect]; Connect
0x1002060c  push    eax; FilterHandle
0x1002060d  call    ds:__imp__KsCreatePin@16; KsCreatePin(x,x,x,x)
0x10020613  mov     edi, eax
0x10020615  cmp     edi, 15h
0x10020618  jnz     short loc_1002062E
0x1002061a  push    3E8h; dwMilliseconds
0x1002061f  call    ds:__imp__Sleep@4; Sleep(x)
0x10020625  mov     ecx, [ebp+var_8]
0x10020628  inc     ebx
0x10020629  cmp     ebx, 5
0x1002062c  jl      short loc_100205F3
0x1002062e  movzx   esi, di
0x10020631  or      esi, 80070000h
0x10020637  test    edi, edi
0x10020639  cmovle  esi, edi
0x1002063c  mov     eax, _WPP_GLOBAL_Control
0x10020641  cmp     eax, offset _WPP_GLOBAL_Control
0x10020646  jz      short loc_10020662
0x10020648  cmp     byte ptr [eax+19h], 2
0x1002064c  jb      short loc_10020662
0x1002064e  push    esi; char
0x1002064f  push    dword ptr [eax+14h]
0x10020652  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x10020657  push    dword ptr [eax+10h]; LoggerHandle
0x1002065a  push    19h
0x1002065c  pop     ecx; MessageNumber
0x1002065d  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x10020662  mov     eax, [ebp+ConnectionHandle]
0x10020665  test    esi, esi
0x10020667  js      short loc_10020685
0x10020669  mov     edx, [ebp+arg_8]
0x1002066c  mov     edx, [edx+0E0h]
0x10020672  test    edx, edx
0x10020674  jz      short loc_10020681
0x10020676  mov     ecx, [eax]
0x10020678  call    ?SetSyncSource@@YGJPAX0@Z; SetSyncSource(void *,void *)
0x1002067d  mov     esi, eax
0x1002067f  jmp     short loc_1002068B
0x10020681  xor     esi, esi
0x10020683  jmp     short loc_1002068B
0x10020685  mov     dword ptr [eax], 0
0x1002068b  push    [ebp+Connect]; pv
0x1002068e  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10020694  mov     eax, esi
0x10020696  pop     edi
0x10020697  pop     esi
0x10020698  pop     ebx
0x10020699  leave
0x1002069a  retn    18h
```
