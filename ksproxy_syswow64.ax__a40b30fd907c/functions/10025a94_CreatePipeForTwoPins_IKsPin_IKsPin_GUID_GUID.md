# CreatePipeForTwoPins(IKsPin *,IKsPin *,_GUID,_GUID)

- ea: `0x10025a94`
- end: `0x10025d16`
- name: `?CreatePipeForTwoPins@@YGHPAUIKsPin@@0U_GUID@@1@Z`
- size: `642`
- prototype: `BOOL __userpurge@<eax>(_DWORD **@<edx>, _DWORD **@<ecx>, __int64, struct _GUID, struct _GUID)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x10022cf8`
- `0x100294a0`
- `0x1002a46f`

## callees

- `0x1000665f`
- `0x10006689`
- `0x10025833`
- `0x1002599d`
- `0x10025a94`
- `0x10026a0a`
- `0x10026e32`
- `0x1002861d`
- `0x10029c63`
- `0x1002d510`

## pseudocode

```c
BOOL __userpurge CreatePipeForTwoPins@<eax>(
        _DWORD **a1@<edx>,
        _DWORD **a2@<ecx>,
        __int64 a3,
        struct _GUID a4,
        struct _GUID a5)
{
  int v8; // edi
  unsigned int v9; // ecx
  int v10; // esi
  struct IKsPin *v11; // ecx
  struct _GUID v12; // [esp-18h] [ebp-38h]
  struct _GUID v13; // [esp-10h] [ebp-30h]
  struct _GUID v14; // [esp-10h] [ebp-30h]
  unsigned int *v15; // [esp+0h] [ebp-20h]
  unsigned int v16; // [esp+0h] [ebp-20h]
  enum KS_LogicalMemoryType *v17; // [esp+4h] [ebp-1Ch]
  unsigned int v18; // [esp+4h] [ebp-1Ch]
  int v20; // [esp+Ch] [ebp-14h]
  unsigned int v21; // [esp+10h] [ebp-10h] BYREF
  int v22; // [esp+14h] [ebp-Ch] BYREF
  int v23; // [esp+18h] [ebp-8h] BYREF
  _DWORD **v24; // [esp+1Ch] [ebp-4h] BYREF

  v23 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_qq(
      0x7Fu,
      &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids,
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (char)a2,
      (char)a1);
  if ( ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, unsigned int *))**a2)(
         **a2,
         a2,
         &_GUID_e539cd90_a8b4_11d1_8189_00a0c9062802,
         &v21) < 0 )
  {
    v21 = 0;
    return 0;
  }
  (*(void (__thiscall **)(_DWORD, unsigned int))(*(_DWORD *)v21 + 8))(*(_DWORD *)(*(_DWORD *)v21 + 8), v21);
  if ( ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, int *))**a1)(
         **a1,
         a1,
         &_GUID_e539cd90_a8b4_11d1_8189_00a0c9062802,
         &v22) < 0 )
  {
    v22 = 0;
    return 0;
  }
  (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v22 + 8))(*(_DWORD *)(*(_DWORD *)v22 + 8), v22);
  v8 = CreatePipe(a1, &v24);
  if ( v8 >= 0 )
  {
    v8 = InitializePipe(v24);
    if ( v8 >= 0 )
    {
      v8 = ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, int *))**v24)(
             **v24,
             v24,
             &_GUID_56a8689c_0ad4_11ce_b03a_0020af0ba770,
             &v23);
      if ( v8 >= 0 )
      {
        (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v23 + 8))(*(_DWORD *)(*(_DWORD *)v23 + 8), v23);
        if ( !((int (__thiscall *)(_DWORD, _DWORD **, _DWORD))(*a1)[10])((*a1)[10], a1, 0) )
          ((void (__thiscall *)(_DWORD, _DWORD **, int))(*a1)[11])((*a1)[11], a1, v23);
        (*(void (__thiscall **)(_DWORD, int, _DWORD **))(*(_DWORD *)v22 + 28))(
          *(_DWORD *)(*(_DWORD *)v22 + 28),
          v22,
          v24);
        if ( !((int (__thiscall *)(_DWORD, _DWORD **, _DWORD))(*a2)[10])((*a2)[10], a2, 0) )
          ((void (__thiscall *)(_DWORD, _DWORD **, int))(*a2)[11])((*a2)[11], a2, v23);
        (*(void (__thiscall **)(_DWORD, unsigned int, _DWORD **))(*(_DWORD *)v21 + 28))(
          *(_DWORD *)(*(_DWORD *)v21 + 28),
          v21,
          v24);
        v20 = ((int (__thiscall *)(_DWORD, _DWORD **))(*v24)[7])((*v24)[7], v24);
        *(_QWORD *)(v20 + 32) = a3;
        *(_QWORD *)(v20 + 40) = *(_QWORD *)&a4.Data1;
        *(_QWORD *)(v20 + 16) = *(_QWORD *)a4.Data4;
        *(_QWORD *)(v20 + 24) = *(_QWORD *)&a5.Data1;
        *(_QWORD *)&v13.Data1 = a3;
        *(_QWORD *)v13.Data4 = *(_QWORD *)&a4.Data1;
        if ( IsHostSystemBus(v13) )
        {
          *(_QWORD *)&v14.Data1 = *(_QWORD *)a4.Data4;
          *(_QWORD *)v14.Data4 = *(_QWORD *)&a5.Data1;
          v10 = v20;
          GetLogicalMemoryTypeFromMemoryType(v14, (unsigned int)v15, v17);
        }
        else
        {
          v10 = v20;
          *(_DWORD *)(v20 + 176) = 4;
        }
        *(_DWORD *)(v10 + 248) = 2;
        *(_QWORD *)v12.Data4 = *(_QWORD *)a4.Data4;
        *(_QWORD *)&v12.Data1 = v9 | 0x100000000LL;
        AssignPipeAllocatorHandler((struct IKsPin *)2, 0, v12, a5.Data1, *(struct IKsPin ***)&a5.Data2, v15, (int)v17);
        v8 = ResolvePipeDimensions(v11, v16, v18);
        ((void (__thiscall *)(_DWORD, _DWORD **))(*v24)[2])((*v24)[2], v24);
      }
      else
      {
        v23 = 0;
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_q(0x80u, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), v8);
  return v8 >= 0;
}

```

## disassembly

```asm
0x10025a94  mov     edi, edi
0x10025a96  push    ebp
0x10025a97  mov     ebp, esp
0x10025a99  sub     esp, 14h
0x10025a9c  push    ebx
0x10025a9d  push    esi; unsigned int
0x10025a9e  push    edi; unsigned int
0x10025a9f  mov     edi, edx
0x10025aa1  mov     [ebp+var_8], 0
0x10025aa8  mov     [ebp+var_14], edi
0x10025aab  mov     ebx, ecx
0x10025aad  mov     eax, _WPP_GLOBAL_Control
0x10025ab2  cmp     eax, offset _WPP_GLOBAL_Control
0x10025ab7  jz      short loc_10025AD4
0x10025ab9  cmp     byte ptr [eax+19h], 2
0x10025abd  jb      short loc_10025AD4
0x10025abf  push    edi; char
0x10025ac0  push    ebx; char
0x10025ac1  push    dword ptr [eax+14h]
0x10025ac4  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x10025ac9  push    dword ptr [eax+10h]; struct _GUID
0x10025acc  push    7Fh
0x10025ace  pop     ecx; MessageNumber
0x10025acf  call    _WPP_SF_qq@24; WPP_SF_qq(x,x,x,x,x,x)
0x10025ad4  mov     eax, [ebx]
0x10025ad6  mov     esi, [eax]
0x10025ad8  lea     eax, [ebp+var_10]
0x10025adb  push    eax
0x10025adc  push    offset __GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x10025ae1  push    ebx
0x10025ae2  mov     ecx, esi; this
0x10025ae4  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025aea  call    esi
0x10025aec  test    eax, eax
0x10025aee  jns     short loc_10025AF9
0x10025af0  mov     [ebp+var_10], 0
0x10025af7  jmp     short loc_10025B2F
0x10025af9  mov     eax, [ebp+var_10]
0x10025afc  push    eax
0x10025afd  mov     ecx, [eax]
0x10025aff  mov     esi, [ecx+8]
0x10025b02  mov     ecx, esi; this
0x10025b04  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025b0a  call    esi
0x10025b0c  mov     eax, [edi]
0x10025b0e  mov     esi, [eax]
0x10025b10  lea     eax, [ebp+var_C]
0x10025b13  push    eax
0x10025b14  push    offset __GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x10025b19  push    edi
0x10025b1a  mov     ecx, esi; this
0x10025b1c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025b22  call    esi
0x10025b24  test    eax, eax
0x10025b26  jns     short loc_10025B36
0x10025b28  mov     [ebp+var_C], 0
0x10025b2f  xor     eax, eax
0x10025b31  jmp     loc_10025D0F
0x10025b36  mov     eax, [ebp+var_C]
0x10025b39  push    eax
0x10025b3a  mov     ecx, [eax]
0x10025b3c  mov     esi, [ecx+8]
0x10025b3f  mov     ecx, esi; this
0x10025b41  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025b47  call    esi
0x10025b49  lea     edx, [ebp+var_4]
0x10025b4c  mov     ecx, edi
0x10025b4e  call    ?CreatePipe@@YGJPAUIKsPin@@PAPAUIKsAllocatorEx@@@Z; CreatePipe(IKsPin *,IKsAllocatorEx * *)
0x10025b53  mov     edi, eax
0x10025b55  test    edi, edi
0x10025b57  js      loc_10025CE0
0x10025b5d  mov     ecx, [ebp+var_4]
0x10025b60  call    ?InitializePipe@@YGJPAUIKsAllocatorEx@@H@Z; InitializePipe(IKsAllocatorEx *,int)
0x10025b65  mov     edi, eax
0x10025b67  test    edi, edi
0x10025b69  js      loc_10025CE0
0x10025b6f  mov     ecx, [ebp+var_4]
0x10025b72  mov     eax, [ecx]
0x10025b74  mov     esi, [eax]
0x10025b76  lea     eax, [ebp+var_8]
0x10025b79  push    eax
0x10025b7a  push    offset __GUID_56a8689c_0ad4_11ce_b03a_0020af0ba770
0x10025b7f  push    ecx
0x10025b80  mov     ecx, esi; this
0x10025b82  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025b88  call    esi
0x10025b8a  mov     edi, eax
0x10025b8c  test    edi, edi
0x10025b8e  jns     short loc_10025B9C
0x10025b90  mov     [ebp+var_8], 0
0x10025b97  jmp     loc_10025CE0
0x10025b9c  mov     eax, [ebp+var_8]
0x10025b9f  push    eax
0x10025ba0  mov     ecx, [eax]
0x10025ba2  mov     esi, [ecx+8]
0x10025ba5  mov     ecx, esi; this
0x10025ba7  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025bad  call    esi
0x10025baf  mov     edi, [ebp+var_14]
0x10025bb2  push    0
0x10025bb4  push    edi
0x10025bb5  mov     eax, [edi]
0x10025bb7  mov     esi, [eax+28h]
0x10025bba  mov     ecx, esi; this
0x10025bbc  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025bc2  call    esi
0x10025bc4  test    eax, eax
0x10025bc6  jnz     short loc_10025BDB
0x10025bc8  mov     eax, [edi]
0x10025bca  push    [ebp+var_8]
0x10025bcd  push    edi
0x10025bce  mov     esi, [eax+2Ch]
0x10025bd1  mov     ecx, esi; this
0x10025bd3  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025bd9  call    esi
0x10025bdb  mov     eax, [ebp+var_C]
0x10025bde  push    [ebp+var_4]
0x10025be1  push    eax
0x10025be2  mov     ecx, [eax]
0x10025be4  mov     esi, [ecx+1Ch]
0x10025be7  mov     ecx, esi; this
0x10025be9  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025bef  call    esi
0x10025bf1  mov     eax, [ebx]
0x10025bf3  push    0
0x10025bf5  push    ebx
0x10025bf6  mov     esi, [eax+28h]
0x10025bf9  mov     ecx, esi; this
0x10025bfb  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025c01  call    esi
0x10025c03  test    eax, eax
0x10025c05  jnz     short loc_10025C1A
0x10025c07  mov     eax, [ebx]
0x10025c09  push    [ebp+var_8]
0x10025c0c  push    ebx
0x10025c0d  mov     esi, [eax+2Ch]
0x10025c10  mov     ecx, esi; this
0x10025c12  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025c18  call    esi
0x10025c1a  mov     eax, [ebp+var_10]
0x10025c1d  push    [ebp+var_4]
0x10025c20  push    eax; unsigned int
0x10025c21  mov     ecx, [eax]
0x10025c23  mov     esi, [ecx+1Ch]
0x10025c26  mov     ecx, esi; this
0x10025c28  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025c2e  call    esi
0x10025c30  mov     eax, [ebp+var_4]
0x10025c33  push    eax
0x10025c34  mov     ecx, [eax]
0x10025c36  mov     esi, [ecx+1Ch]
0x10025c39  mov     ecx, esi; this
0x10025c3b  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025c41  call    esi
0x10025c43  lea     esi, [ebp+arg_0]
0x10025c46  mov     [ebp+var_14], eax
0x10025c49  sub     esp, 10h
0x10025c4c  lea     edi, [eax+20h]
0x10025c4f  movsd
0x10025c50  movsd
0x10025c51  movsd
0x10025c52  movsd
0x10025c53  lea     edi, [eax+10h]
0x10025c56  lea     esi, [ebp+arg_10]
0x10025c59  movsd
0x10025c5a  movsd
0x10025c5b  movsd
0x10025c5c  movsd
0x10025c5d  mov     edi, esp
0x10025c5f  lea     esi, [ebp+arg_0]
0x10025c62  movsd
0x10025c63  movsd
0x10025c64  movsd
0x10025c65  movsd
0x10025c66  call    ?IsHostSystemBus@@YGHU_GUID@@@Z; IsHostSystemBus(_GUID)
0x10025c6b  test    eax, eax
0x10025c6d  jnz     short loc_10025C7E
0x10025c6f  mov     esi, [ebp+var_14]
0x10025c72  mov     dword ptr [esi+0B0h], 4
0x10025c7c  jmp     short loc_10025C9B
0x10025c7e  sub     esp, 10h
0x10025c81  lea     esi, [ebp+arg_10]
0x10025c84  mov     edi, esp
0x10025c86  push    20h ; ' '
0x10025c88  movsd
0x10025c89  pop     ecx
0x10025c8a  movsd
0x10025c8b  movsd
0x10025c8c  movsd
0x10025c8d  mov     esi, [ebp+var_14]
0x10025c90  lea     edx, [esi+0B0h]
0x10025c96  call    ?GetLogicalMemoryTypeFromMemoryType@@YGHU_GUID@@KPAW4KS_LogicalMemoryType@@@Z; GetLogicalMemoryTypeFromMemoryType(_GUID,ulong,KS_LogicalMemoryType *)
0x10025c9b  push    2; struct IKsPin **
0x10025c9d  pop     eax
0x10025c9e  sub     esp, 10h
0x10025ca1  mov     [esi+0F8h], eax
0x10025ca7  mov     edi, esp
0x10025ca9  lea     esi, [ebp+arg_10]
0x10025cac  push    1
0x10025cae  movsd
0x10025caf  push    ecx; struct _GUID
0x10025cb0  push    0; unsigned int
0x10025cb2  push    eax; struct IKsPin *
0x10025cb3  movsd
0x10025cb4  mov     ecx, ebx
0x10025cb6  push    4
0x10025cb8  pop     edx
0x10025cb9  movsd
0x10025cba  movsd
0x10025cbb  call    ?AssignPipeAllocatorHandler@@YGHPAUIKsPin@@KU_GUID@@KPAPAU1@PAKH@Z; AssignPipeAllocatorHandler(IKsPin *,ulong,_GUID,ulong,IKsPin * *,ulong *,int)
0x10025cc0  push    ecx; struct IKsPin *
0x10025cc1  push    4
0x10025cc3  pop     edx
0x10025cc4  mov     ecx, ebx
0x10025cc6  call    ?ResolvePipeDimensions@@YGJPAUIKsPin@@KK@Z; ResolvePipeDimensions(IKsPin *,ulong,ulong)
0x10025ccb  mov     edi, eax
0x10025ccd  mov     eax, [ebp+var_4]
0x10025cd0  push    eax
0x10025cd1  mov     ecx, [eax]
0x10025cd3  mov     esi, [ecx+8]
0x10025cd6  mov     ecx, esi; this
0x10025cd8  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10025cde  call    esi
0x10025ce0  mov     eax, _WPP_GLOBAL_Control
0x10025ce5  cmp     eax, offset _WPP_GLOBAL_Control
0x10025cea  jz      short loc_10025D08
0x10025cec  cmp     byte ptr [eax+19h], 2
0x10025cf0  jb      short loc_10025D08
0x10025cf2  push    edi; char
0x10025cf3  push    dword ptr [eax+14h]
0x10025cf6  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x10025cfb  mov     ecx, 80h; MessageNumber
0x10025d00  push    dword ptr [eax+10h]; LoggerHandle
0x10025d03  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x10025d08  xor     eax, eax
0x10025d0a  test    edi, edi
0x10025d0c  setns   al
0x10025d0f  pop     edi
0x10025d10  pop     esi
0x10025d11  pop     ebx
0x10025d12  leave
0x10025d13  retn    20h ; ' '
```
