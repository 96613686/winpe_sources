# GetPinFramingFromCache(IKsPin *,KSALLOCATOR_FRAMING_EX * *,FRAMING_PROP *,FRAMING_CACHE_OPS)

- ea: `0x10025d1d`
- end: `0x1002608e`
- name: `?GetPinFramingFromCache@@YGHPAUIKsPin@@PAPAUKSALLOCATOR_FRAMING_EX@@PAW4FRAMING_PROP@@W4FRAMING_CACHE_OPS@@@Z`
- size: `881`
- prototype: `int __stdcall(struct IKsPin *, struct KSALLOCATOR_FRAMING_EX **, enum FRAMING_PROP *, enum FRAMING_CACHE_OPS)`
- caller_count: `16`
- callee_count: `11`
- tags: ``

## callers

- `0x10012740`
- `0x100224d5`
- `0x10022cf8`
- `0x1002343f`
- `0x10023d3c`
- `0x10024280`
- `0x100263d6`
- `0x10026750`
- `0x10026b9d`
- `0x10026ef0`
- `0x10028230`
- `0x10028ad1`
- `0x100294a0`
- `0x1002a40e`
- `0x1002a5bd`
- `0x1002b288`

## callees

- `0x100064e5`
- `0x1001ef85`
- `0x100219b6`
- `0x10021a03`
- `0x10025d1d`
- `0x10026094`
- `0x1002616f`
- `0x10026203`
- `0x1002d510`
- `0x1003a6fd`
- `0x1003aba0`

## pseudocode

```c
int __userpurge GetPinFramingFromCache@<eax>(
        int **a1@<edx>,
        int (__thiscall ***a2)(_DWORD, _DWORD, GUID *, int *)@<ecx>,
        struct IKsPin *a3,
        struct KSALLOCATOR_FRAMING_EX **a4,
        enum FRAMING_PROP *a5,
        enum FRAMING_CACHE_OPS a6)
{
  struct IKsPin *v6; // ebx
  int (__thiscall *v7)(_DWORD, _DWORD, GUID *, int *); // esi
  int **v8; // edi
  int v10; // edi
  int v11; // eax
  int v12; // edi
  int v13; // eax
  int *v14; // eax
  int v15; // edi
  int v16; // eax
  int *v17; // eax
  int v18; // ebx
  int v19; // edi
  int v20; // eax
  void *v21; // [esp+40h] [ebp-48h]
  struct KSALLOCATOR_FRAMING_EX *v22; // [esp+40h] [ebp-48h]
  struct KSALLOCATOR_FRAMING_EX *v23; // [esp+40h] [ebp-48h]
  struct KSALLOCATOR_FRAMING_EX **v24; // [esp+44h] [ebp-44h]
  struct KSALLOCATOR_FRAMING *v25; // [esp+44h] [ebp-44h]
  struct KSALLOCATOR_FRAMING *v26; // [esp+44h] [ebp-44h]
  int v27; // [esp+4Ch] [ebp-3Ch] BYREF
  int v28; // [esp+50h] [ebp-38h] BYREF
  int **v29; // [esp+54h] [ebp-34h]
  char v30[4]; // [esp+58h] [ebp-30h]
  char v31[4]; // [esp+5Ch] [ebp-2Ch]
  char v32[4]; // [esp+60h] [ebp-28h]
  char v33[4]; // [esp+64h] [ebp-24h]
  struct IKsPin *v34; // [esp+68h] [ebp-20h]
  char v35[4]; // [esp+6Ch] [ebp-1Ch]
  char v36[4]; // [esp+70h] [ebp-18h]
  char v37[4]; // [esp+74h] [ebp-14h]
  char v38[4]; // [esp+78h] [ebp-10h]
  char v39[8]; // [esp+7Ch] [ebp-Ch]

  v6 = a3;
  v7 = **a2;
  v8 = a1;
  *(_DWORD *)v30 = a2;
  v29 = a1;
  v34 = a3;
  if ( v7(v7, a2, &_GUID_e539cd90_a8b4_11d1_8189_00a0c9062802, &v27) < 0 )
  {
    v27 = 0;
    return 0;
  }
  (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v27 + 8))(*(_DWORD *)(*(_DWORD *)v27 + 8), v27);
  if ( !a4
    || ((*(void (__thiscall **)(_DWORD, int, int **, struct IKsPin *, struct KSALLOCATOR_FRAMING_EX **))(*(_DWORD *)v27 + 12))(
          *(_DWORD *)(*(_DWORD *)v27 + 12),
          v27,
          v8,
          a3,
          a4),
        !a3->__vftable) )
  {
    if ( (***(int (__thiscall ****)(_DWORD, _DWORD, GUID *, int *))v30)(
           ***(_DWORD ***)v30,
           *(_DWORD *)v30,
           &_GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1,
           &v28) < 0 )
    {
      v28 = 0;
      return 0;
    }
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v28 + 8))(*(_DWORD *)(*(_DWORD *)v28 + 8), v28);
    if ( !v28 )
      return 0;
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v28 + 12))(*(_DWORD *)(*(_DWORD *)v28 + 12), v28);
    if ( GetAllocatorFramingEx(v21, v24) >= 0 )
    {
      a3->__vftable = (IKsPin_vtbl *)3;
      SetDefaultFramingExItems(v22);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_26:
        if ( v6->__vftable != (IKsPin_vtbl *)1 )
          ValidateFramingEx(v23);
        goto LABEL_28;
      }
      v17 = *v8;
      v18 = **v8;
      *(_DWORD *)v30 = (*v8)[16];
      *(_DWORD *)v31 = v17[18];
      *(_DWORD *)v32 = v17[24];
      *(_DWORD *)v33 = v17[17];
      v19 = (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v27 + 48))(*(_DWORD *)(*(_DWORD *)v27 + 48), v27);
      v20 = (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v27 + 52))(*(_DWORD *)(*(_DWORD *)v27 + 52), v27);
      WPP_SF_SSdddDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, v19, v33[0], v32[0], v31[0], v30[0], v18);
      v6 = v34;
    }
    else
    {
      if ( GetAllocatorFraming(v22, v25) >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v27 + 48))(*(_DWORD *)(*(_DWORD *)v27 + 48), v27);
          v13 = (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v27 + 52))(*(_DWORD *)(*(_DWORD *)v27 + 52), v27);
          WPP_SF_SSdddDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v12, v37[0], v38[0], v39[0], v35[0], v36[0]);
          v8 = v29;
        }
        a3->__vftable = (IKsPin_vtbl *)2;
        v14 = (int *)operator new(0x70u);
        *v8 = v14;
        if ( !v14 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v27 + 48))(*(_DWORD *)(*(_DWORD *)v27 + 48), v27);
            v16 = (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v27 + 52))(*(_DWORD *)(*(_DWORD *)v27 + 52), v27);
            WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v15);
          }
          return 0;
        }
        GetFramingExFromFraming(v23, v26);
        goto LABEL_26;
      }
      a3->__vftable = (IKsPin_vtbl *)1;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_28:
        if ( a4 )
          (*(void (__thiscall **)(_DWORD, int, int *, struct IKsPin *, int))(*(_DWORD *)v27 + 16))(
            *(_DWORD *)(*(_DWORD *)v27 + 16),
            v27,
            *v8,
            v6,
            2);
        (*(void (__thiscall **)(_DWORD, int, int *, struct IKsPin *, int))(*(_DWORD *)v27 + 16))(
          *(_DWORD *)(*(_DWORD *)v27 + 16),
          v27,
          *v8,
          v6,
          1);
        return 1;
      }
      v10 = (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v27 + 48))(*(_DWORD *)(*(_DWORD *)v27 + 48), v27);
      v11 = (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v27 + 52))(*(_DWORD *)(*(_DWORD *)v27 + 52), v27);
      WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v10);
    }
    v8 = v29;
    goto LABEL_26;
  }
  return 1;
}

```

## disassembly

```asm
0x10025d1d  mov     edi, edi
0x10025d1f  push    ebp
0x10025d20  mov     ebp, esp
0x10025d22  and     esp, 0FFFFFFF8h
0x10025d25  sub     esp, 3Ch
0x10025d28  mov     eax, ___security_cookie
0x10025d2d  xor     eax, esp
0x10025d2f  mov     [esp+3Ch+var_4], eax
0x10025d33  mov     eax, [ecx]
0x10025d35  push    ebx
0x10025d36  mov     ebx, [ebp+arg_0]
0x10025d39  push    esi; struct KSALLOCATOR_FRAMING *
0x10025d3a  mov     esi, [eax]
0x10025d3c  lea     eax, [esp+44h+var_3C]
0x10025d40  push    edi; struct KSALLOCATOR_FRAMING_EX *
0x10025d41  push    eax
0x10025d42  push    offset __GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x10025d47  mov     edi, edx
0x10025d49  mov     dword ptr [esp+50h+var_30], ecx
0x10025d4d  push    ecx
0x10025d4e  mov     ecx, esi; this
0x10025d50  mov     [esp+54h+var_34], edi
0x10025d54  mov     [esp+54h+var_20], ebx
0x10025d58  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025d5e  call    esi
0x10025d60  test    eax, eax
0x10025d62  jns     short loc_10025D82
0x10025d64  mov     [esp+48h+var_3C], 0
0x10025d6c  xor     eax, eax
0x10025d6e  mov     ecx, [esp+48h+var_4]
0x10025d72  pop     edi
0x10025d73  pop     esi
0x10025d74  pop     ebx
0x10025d75  xor     ecx, esp; StackCookie
0x10025d77  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10025d7c  mov     esp, ebp
0x10025d7e  pop     ebp
0x10025d7f  retn    8
0x10025d82  mov     eax, [esp+48h+var_3C]
0x10025d86  push    eax
0x10025d87  mov     ecx, [eax]
0x10025d89  mov     esi, [ecx+8]
0x10025d8c  mov     ecx, esi; this
0x10025d8e  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025d94  call    esi
0x10025d96  cmp     [ebp+arg_4], 0
0x10025d9a  jz      short loc_10025DBD
0x10025d9c  mov     eax, [esp+48h+var_3C]
0x10025da0  push    [ebp+arg_4]
0x10025da3  push    ebx
0x10025da4  mov     esi, [eax]
0x10025da6  push    edi
0x10025da7  push    eax
0x10025da8  mov     ecx, [esi+0Ch]; this
0x10025dab  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025db1  call    dword ptr [esi+0Ch]
0x10025db4  cmp     dword ptr [ebx], 0
0x10025db7  jnz     loc_10026086
0x10025dbd  mov     ecx, dword ptr [esp+48h+var_30]
0x10025dc1  mov     eax, [ecx]
0x10025dc3  mov     esi, [eax]
0x10025dc5  lea     eax, [esp+48h+var_38]
0x10025dc9  push    eax
0x10025dca  push    offset __GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1
0x10025dcf  push    ecx
0x10025dd0  mov     ecx, esi; this
0x10025dd2  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025dd8  call    esi
0x10025dda  test    eax, eax
0x10025ddc  jns     short loc_10025DE8
0x10025dde  mov     [esp+48h+var_38], 0
0x10025de6  jmp     short loc_10025D6C
0x10025de8  mov     eax, [esp+48h+var_38]
0x10025dec  push    eax
0x10025ded  mov     ecx, [eax]
0x10025def  mov     esi, [ecx+8]
0x10025df2  mov     ecx, esi; this
0x10025df4  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025dfa  call    esi
0x10025dfc  mov     ecx, [esp+48h+var_38]
0x10025e00  test    ecx, ecx
0x10025e02  jz      loc_10025D6C
0x10025e08  mov     eax, [ecx]
0x10025e0a  push    ecx
0x10025e0b  mov     esi, [eax+0Ch]
0x10025e0e  mov     ecx, esi; this
0x10025e10  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025e16  call    esi
0x10025e18  mov     esi, eax
0x10025e1a  mov     edx, edi
0x10025e1c  mov     ecx, esi
0x10025e1e  call    ?GetAllocatorFramingEx@@YGJPAXPAPAUKSALLOCATOR_FRAMING_EX@@@Z; GetAllocatorFramingEx(void *,KSALLOCATOR_FRAMING_EX * *)
0x10025e23  test    eax, eax
0x10025e25  jns     loc_10025F99
0x10025e2b  lea     edx, [esp+48h+var_1C]
0x10025e2f  mov     ecx, esi
0x10025e31  call    ?GetAllocatorFraming@@YGJPAXPAUKSALLOCATOR_FRAMING@@@Z; GetAllocatorFraming(void *,KSALLOCATOR_FRAMING *)
0x10025e36  test    eax, eax
0x10025e38  jns     short loc_10025EA5
0x10025e3a  mov     dword ptr [ebx], 1
0x10025e40  mov     eax, _WPP_GLOBAL_Control
0x10025e45  cmp     eax, offset _WPP_GLOBAL_Control
0x10025e4a  jz      loc_10026042
0x10025e50  cmp     byte ptr [eax+19h], 2
0x10025e54  jb      loc_10026042
0x10025e5a  mov     eax, [esp+48h+var_3C]
0x10025e5e  push    eax
0x10025e5f  mov     ecx, [eax]
0x10025e61  mov     esi, [ecx+30h]
0x10025e64  mov     ecx, esi; this
0x10025e66  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025e6c  call    esi
0x10025e6e  mov     ecx, [esp+48h+var_3C]
0x10025e72  mov     edi, eax
0x10025e74  push    ecx
0x10025e75  mov     edx, [ecx]
0x10025e77  mov     esi, [edx+34h]
0x10025e7a  mov     ecx, esi; this
0x10025e7c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025e82  call    esi
0x10025e84  push    edi; int
0x10025e85  push    eax; int
0x10025e86  mov     eax, _WPP_GLOBAL_Control
0x10025e8b  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x10025e90  mov     ecx, 81h
0x10025e95  push    dword ptr [eax+14h]
0x10025e98  push    dword ptr [eax+10h]; LoggerHandle
0x10025e9b  call    _WPP_SF_SS@24; WPP_SF_SS(x,x,x,x,x,x)
0x10025ea0  jmp     loc_10026032
0x10025ea5  mov     eax, _WPP_GLOBAL_Control
0x10025eaa  cmp     eax, offset _WPP_GLOBAL_Control
0x10025eaf  jz      short loc_10025F10
0x10025eb1  cmp     byte ptr [eax+19h], 2
0x10025eb5  jb      short loc_10025F10
0x10025eb7  mov     eax, [esp+48h+var_3C]
0x10025ebb  push    eax
0x10025ebc  mov     ecx, [eax]
0x10025ebe  mov     esi, [ecx+30h]
0x10025ec1  mov     ecx, esi; this
0x10025ec3  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025ec9  call    esi
0x10025ecb  mov     ecx, [esp+48h+var_3C]
0x10025ecf  mov     edi, eax
0x10025ed1  push    ecx
0x10025ed2  mov     edx, [ecx]
0x10025ed4  mov     esi, [edx+34h]
0x10025ed7  mov     ecx, esi; this
0x10025ed9  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025edf  call    esi
0x10025ee1  push    dword ptr [esp+48h+var_18]; char
0x10025ee5  mov     ecx, 82h
0x10025eea  push    dword ptr [esp+4Ch+var_1C]; char
0x10025eee  push    dword ptr [esp+50h+var_C]; char
0x10025ef2  push    dword ptr [esp+54h+var_10]; char
0x10025ef6  push    dword ptr [esp+58h+var_14]; char
0x10025efa  push    edi; int
0x10025efb  push    eax; int
0x10025efc  mov     eax, _WPP_GLOBAL_Control
0x10025f01  push    dword ptr [eax+14h]
0x10025f04  push    dword ptr [eax+10h]; LoggerHandle
0x10025f07  call    _WPP_SF_SSdddDd@44; WPP_SF_SSdddDd(x,x,x,x,x,x,x,x,x,x,x)
0x10025f0c  mov     edi, [esp+48h+var_34]
0x10025f10  push    70h ; 'p'; Size
0x10025f12  mov     dword ptr [ebx], 2
0x10025f18  call    ??2@YAPAXI@Z; operator new(uint)
0x10025f1d  mov     [edi], eax
0x10025f1f  pop     ecx
0x10025f20  test    eax, eax
0x10025f22  jnz     short loc_10025F89
0x10025f24  mov     eax, _WPP_GLOBAL_Control
0x10025f29  cmp     eax, offset _WPP_GLOBAL_Control
0x10025f2e  jz      loc_10025D6C
0x10025f34  cmp     byte ptr [eax+19h], 2
0x10025f38  jb      loc_10025D6C
0x10025f3e  mov     eax, [esp+48h+var_3C]
0x10025f42  push    eax
0x10025f43  mov     ecx, [eax]
0x10025f45  mov     esi, [ecx+30h]
0x10025f48  mov     ecx, esi; this
0x10025f4a  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025f50  call    esi
0x10025f52  mov     ecx, [esp+48h+var_3C]
0x10025f56  mov     edi, eax
0x10025f58  push    ecx
0x10025f59  mov     edx, [ecx]
0x10025f5b  mov     esi, [edx+34h]
0x10025f5e  mov     ecx, esi; this
0x10025f60  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025f66  call    esi
0x10025f68  push    edi; int
0x10025f69  push    eax; int
0x10025f6a  mov     eax, _WPP_GLOBAL_Control
0x10025f6f  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x10025f74  mov     ecx, 83h
0x10025f79  push    dword ptr [eax+14h]
0x10025f7c  push    dword ptr [eax+10h]; LoggerHandle
0x10025f7f  call    _WPP_SF_SS@24; WPP_SF_SS(x,x,x,x,x,x)
0x10025f84  jmp     loc_10025D6C
0x10025f89  lea     edx, [esp+48h+var_1C]
0x10025f8d  mov     ecx, eax
0x10025f8f  call    ?GetFramingExFromFraming@@YGHPAUKSALLOCATOR_FRAMING_EX@@PAUKSALLOCATOR_FRAMING@@@Z; GetFramingExFromFraming(KSALLOCATOR_FRAMING_EX *,KSALLOCATOR_FRAMING *)
0x10025f94  jmp     loc_10026036
0x10025f99  mov     dword ptr [ebx], 3
0x10025f9f  mov     ecx, [edi]
0x10025fa1  call    ?SetDefaultFramingExItems@@YGXPAUKSALLOCATOR_FRAMING_EX@@@Z; SetDefaultFramingExItems(KSALLOCATOR_FRAMING_EX *)
0x10025fa6  mov     eax, _WPP_GLOBAL_Control
0x10025fab  cmp     eax, offset _WPP_GLOBAL_Control
0x10025fb0  jz      loc_10026036
0x10025fb6  cmp     byte ptr [eax+19h], 2
0x10025fba  jb      short loc_10026036
0x10025fbc  mov     eax, [edi]
0x10025fbe  mov     ecx, [eax+40h]
0x10025fc1  mov     ebx, [eax]
0x10025fc3  mov     dword ptr [esp+48h+var_30], ecx
0x10025fc7  mov     ecx, [eax+48h]
0x10025fca  mov     dword ptr [esp+48h+var_2C], ecx
0x10025fce  mov     ecx, [eax+60h]
0x10025fd1  mov     dword ptr [esp+48h+var_28], ecx
0x10025fd5  mov     ecx, [eax+44h]
0x10025fd8  mov     eax, [esp+48h+var_3C]
0x10025fdc  mov     dword ptr [esp+48h+var_24], ecx
0x10025fe0  push    eax
0x10025fe1  mov     ecx, [eax]
0x10025fe3  mov     esi, [ecx+30h]
0x10025fe6  mov     ecx, esi; this
0x10025fe8  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025fee  call    esi
0x10025ff0  mov     ecx, [esp+48h+var_3C]
0x10025ff4  mov     edi, eax
0x10025ff6  push    ecx
0x10025ff7  mov     edx, [ecx]
0x10025ff9  mov     esi, [edx+34h]
0x10025ffc  mov     ecx, esi; this
0x10025ffe  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10026004  call    esi
0x10026006  push    ebx; char
0x10026007  push    dword ptr [esp+4Ch+var_30]; char
0x1002600b  mov     ecx, 84h
0x10026010  push    dword ptr [esp+50h+var_2C]; char
0x10026014  push    dword ptr [esp+54h+var_28]; char
0x10026018  push    dword ptr [esp+58h+var_24]; char
0x1002601c  push    edi; int
0x1002601d  push    eax; int
0x1002601e  mov     eax, _WPP_GLOBAL_Control
0x10026023  push    dword ptr [eax+14h]
0x10026026  push    dword ptr [eax+10h]; LoggerHandle
0x10026029  call    _WPP_SF_SSdddDd@44; WPP_SF_SSdddDd(x,x,x,x,x,x,x,x,x,x,x)
0x1002602e  mov     ebx, [esp+48h+var_20]
0x10026032  mov     edi, [esp+48h+var_34]
0x10026036  cmp     dword ptr [ebx], 1
0x10026039  jz      short loc_10026042
0x1002603b  mov     ecx, [edi]
0x1002603d  call    ?ValidateFramingEx@@YGXPAUKSALLOCATOR_FRAMING_EX@@@Z; ValidateFramingEx(KSALLOCATOR_FRAMING_EX *)
0x10026042  cmp     [ebp+arg_4], 0
0x10026046  jz      short loc_1002606E
0x10026048  mov     eax, [esp+48h+var_3C]
0x1002604c  push    2
0x1002604e  push    ebx
0x1002604f  push    dword ptr [edi]
0x10026051  mov     esi, [eax]
0x10026053  push    eax
0x10026054  mov     ecx, [esi+10h]; this
0x10026057  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002605d  call    dword ptr [esi+10h]
0x10026060  mov     eax, [esp+48h+var_3C]
0x10026064  push    1
0x10026066  push    ebx
0x10026067  push    dword ptr [edi]
0x10026069  mov     esi, [eax]
0x1002606b  push    eax
0x1002606c  jmp     short loc_1002607A
0x1002606e  mov     ecx, [esp+48h+var_3C]
0x10026072  push    1
0x10026074  push    ebx
0x10026075  push    dword ptr [edi]
0x10026077  mov     esi, [ecx]
0x10026079  push    ecx
0x1002607a  mov     ecx, [esi+10h]; this
0x1002607d  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10026083  call    dword ptr [esi+10h]
0x10026086  xor     eax, eax
0x10026088  inc     eax
0x10026089  jmp     loc_10025D6E
```
