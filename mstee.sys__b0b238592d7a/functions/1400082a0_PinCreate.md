# PinCreate

- ea: `0x1400082a0`
- end: `0x140008802`
- name: `PinCreate`
- size: `1378`
- prototype: `__int64 __fastcall(struct _KSPIN *PointerToPointerToItem)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400011a0`
- `0x1400011e0`
- `0x1400015c0`
- `0x1400082a0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000834c`
- `ntoskrnl!RtlCompareMemory` at `0x14000834c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400084d7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400085f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400084d7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400085f2`
- `ntoskrnl!ExFreePool` at `0x14000855d`
- `ntoskrnl!ExFreePool` at `0x140008799`
- `ntoskrnl!ExFreePool` at `0x14000855d`
- `ntoskrnl!ExFreePool` at `0x140008799`
- `ks!KsPinGetNextSiblingPin` at `0x14000831f`
- `ks!KsPinGetNextSiblingPin` at `0x140008746`
- `ks!KsPinGetNextSiblingPin` at `0x14000831f`
- `ks!KsPinGetNextSiblingPin` at `0x140008746`
- `ks!KsPinGetConnectedPinInterface` at `0x140008375`
- `ks!KsPinGetConnectedPinInterface` at `0x140008375`
- `ks!_KsEdit` at `0x14000844c`
- `ks!_KsEdit` at `0x14000871f`
- `ks!_KsEdit` at `0x14000844c`
- `ks!_KsEdit` at `0x14000871f`
- `ks!KsFilterGetFirstChildPin` at `0x1400082ee`
- `ks!KsFilterGetFirstChildPin` at `0x140008308`
- `ks!KsFilterGetFirstChildPin` at `0x1400086f3`
- `ks!KsFilterGetFirstChildPin` at `0x140008776`
- `ks!KsFilterGetFirstChildPin` at `0x1400082ee`
- `ks!KsFilterGetFirstChildPin` at `0x140008308`
- `ks!KsFilterGetFirstChildPin` at `0x1400086f3`
- `ks!KsFilterGetFirstChildPin` at `0x140008776`
- `ks!KsPinGetParentFilter` at `0x1400082d1`
- `ks!KsPinGetParentFilter` at `0x1400082d1`

## pseudocode

```c
__int64 __fastcall PinCreate(struct _KSPIN *PointerToPointerToItem)
{
  PKSFILTER ParentFilter; // rdi
  PKSPIN FirstChildPin; // rbx
  struct _KSPIN *v4; // rax
  _DWORD *p_FormatSize; // r14
  _DWORD *v6; // rdx
  char v7; // r15
  PVOID *p_StreamHeaderSize; // r14
  int v9; // eax
  ULONG v10; // eax
  ULONG StreamHeaderSize; // eax
  NTSTATUS v12; // ebx
  unsigned int v13; // ebx
  unsigned int *PoolWithTag; // rax
  unsigned int *v15; // r14
  __int64 v16; // r8
  unsigned int v17; // edx
  __int64 v18; // rax
  _OWORD *v19; // rax
  _OWORD *v20; // rdx
  const GUID *v21; // rax
  int v22; // ecx
  ULONG v23; // r15d
  PKSPIN i; // rax
  struct _KSPIN *v25; // r14
  ULONG j; // esi
  PKSPIN v27; // rdx
  SIZE_T NumberOfBytes; // [rsp+40h] [rbp-39h] BYREF
  PVOID Interface; // [rsp+48h] [rbp-31h] BYREF
  GUID v31; // [rsp+50h] [rbp-29h] BYREF
  int v32; // [rsp+60h] [rbp-19h]
  int v33; // [rsp+64h] [rbp-15h]
  __int128 v34; // [rsp+68h] [rbp-11h] BYREF
  __int64 v35; // [rsp+78h] [rbp-1h]

  Interface = 0;
  ParentFilter = KsPinGetParentFilter(PointerToPointerToItem);
  FirstChildPin = KsFilterGetFirstChildPin(ParentFilter, PointerToPointerToItem->Id ^ 1);
  if ( FirstChildPin )
    goto LABEL_6;
  v4 = KsFilterGetFirstChildPin(ParentFilter, PointerToPointerToItem->Id);
  FirstChildPin = v4;
  if ( v4 == PointerToPointerToItem )
    FirstChildPin = KsPinGetNextSiblingPin(v4);
  if ( FirstChildPin )
  {
LABEL_6:
    p_FormatSize = &PointerToPointerToItem->ConnectionFormat->FormatSize;
    v6 = &FirstChildPin->ConnectionFormat->FormatSize;
    if ( *p_FormatSize != *v6
      || *p_FormatSize != RtlCompareMemory(PointerToPointerToItem->ConnectionFormat, v6, (unsigned int)*p_FormatSize) )
    {
      return 3221225485LL;
    }
  }
  v7 = 0;
  if ( KsPinGetConnectedPinInterface(PointerToPointerToItem, &IID_IKsControl, &Interface) < 0 )
  {
    Interface = 0;
    if ( FirstChildPin )
      StreamHeaderSize = FirstChildPin->StreamHeaderSize;
    else
      StreamHeaderSize = 0;
    PointerToPointerToItem->StreamHeaderSize = StreamHeaderSize;
  }
  else
  {
    LODWORD(NumberOfBytes) = 0;
    p_StreamHeaderSize = (PVOID *)&PointerToPointerToItem->StreamHeaderSize;
    v31 = KSPROPSETID_StreamInterface;
    v32 = 0;
    v33 = 1;
    v9 = (*(__int64 (__fastcall **)(PVOID, GUID *, __int64, ULONG *, int, SIZE_T *))(*(_QWORD *)Interface + 24LL))(
           Interface,
           &v31,
           24,
           &PointerToPointerToItem->StreamHeaderSize,
           4,
           &NumberOfBytes);
    if ( v9 == -1073741275 || v9 == -1073741264 )
    {
      if ( FirstChildPin )
        v10 = FirstChildPin->StreamHeaderSize;
      else
        v10 = 0;
LABEL_19:
      *(_DWORD *)p_StreamHeaderSize = v10;
      goto LABEL_24;
    }
    if ( v9 >= 0 )
    {
      *(_DWORD *)p_StreamHeaderSize += 56;
      if ( FirstChildPin )
      {
        v10 = FirstChildPin->StreamHeaderSize;
        if ( !v10 || v10 < *(_DWORD *)p_StreamHeaderSize )
        {
          v7 = 1;
          goto LABEL_24;
        }
        goto LABEL_19;
      }
    }
  }
LABEL_24:
  if ( !PointerToPointerToItem->Context )
  {
    if ( !Interface )
    {
      v12 = 0;
      goto LABEL_52;
    }
    LODWORD(NumberOfBytes) = 0;
    v32 = 6;
    v31 = KSPROPSETID_Connection;
    v33 = 1;
    if ( (*(unsigned int (__fastcall **)(PVOID, GUID *, __int64))(*(_QWORD *)Interface + 24LL))(Interface, &v31, 24) == -2147483643 )
    {
      v13 = NumberOfBytes;
      PoolWithTag = (unsigned int *)ExAllocatePoolWithTag((POOL_TYPE)1025, (unsigned int)NumberOfBytes, 0x4554534Du);
      v15 = PoolWithTag;
      if ( !ExPoolZeroingNativelySupported && PoolWithTag )
        memset(PoolWithTag, 0, v13);
      ParentFilter->Context = v15;
      if ( v15 )
      {
        v12 = (*(__int64 (__fastcall **)(PVOID, GUID *, __int64, unsigned int *, _DWORD, SIZE_T *))(*(_QWORD *)Interface
                                                                                                  + 24LL))(
                Interface,
                &v31,
                24,
                v15,
                NumberOfBytes,
                &NumberOfBytes);
        if ( v12 < 0 )
        {
LABEL_36:
          ExFreePool(ParentFilter->Context);
          ParentFilter->Context = 0;
          goto LABEL_47;
        }
        v16 = *v15;
        if ( (unsigned int)NumberOfBytes != 88 * v16 + 24 )
        {
          v12 = -1073741823;
          goto LABEL_36;
        }
        v17 = 0;
        if ( (_DWORD)v16 )
        {
          do
          {
            v18 = v17++;
            v15[22 * v18 + 16] |= 0x80000081;
          }
          while ( v17 < *v15 );
        }
LABEL_47:
        if ( ParentFilter->Context )
          v7 = 1;
        if ( v12 < 0 )
          goto LABEL_66;
LABEL_52:
        if ( v7 )
        {
          v23 = 0;
          while ( v23 < ParentFilter->Descriptor->PinDescriptorsCount )
          {
            for ( i = KsFilterGetFirstChildPin(ParentFilter, v23); ; i = KsPinGetNextSiblingPin(v25) )
            {
              v25 = i;
              if ( !i || v12 < 0 )
                break;
              v12 = _KsEdit(i->Bag, (PVOID *)i, 0x88u, 0x88u, 0x4554534Du);
              if ( v12 >= 0 )
                v25->Descriptor->AllocatorFraming = (const KSALLOCATOR_FRAMING_EX *)ParentFilter->Context;
              v25->StreamHeaderSize = PointerToPointerToItem->StreamHeaderSize;
            }
            ++v23;
            if ( v12 < 0 )
            {
              for ( j = 0; j < ParentFilter->Descriptor->PinDescriptorsCount; ++j )
              {
                v27 = KsFilterGetFirstChildPin(ParentFilter, j);
                if ( v27 )
                {
                  while ( 1 )
                  {
                    while ( v27->Descriptor->AllocatorFraming != ParentFilter->Context )
                      ;
                    v27->Descriptor->AllocatorFraming = (const KSALLOCATOR_FRAMING_EX *)&AllocatorFraming;
                  }
                }
              }
              ExFreePool(ParentFilter->Context);
              ParentFilter->Context = 0;
              goto LABEL_66;
            }
          }
        }
        goto LABEL_66;
      }
    }
    else
    {
      v32 = 3;
      v35 = 0;
      v34 = 0;
      v12 = (*(__int64 (__fastcall **)(PVOID, GUID *, __int64, __int128 *, int, SIZE_T *))(*(_QWORD *)Interface + 24LL))(
              Interface,
              &v31,
              24,
              &v34,
              24,
              &NumberOfBytes);
      if ( v12 < 0 )
      {
        v12 = 0;
        goto LABEL_47;
      }
      v19 = ExAllocatePoolWithTag(PagedPool, 0x70u, 0x4554534Du);
      ParentFilter->Context = v19;
      v20 = v19;
      if ( v19 )
      {
        *v19 = AllocatorFraming;
        v19[1] = xmmword_1400090A0;
        v19[2] = xmmword_1400090B0;
        v19[3] = xmmword_1400090C0;
        v19[4] = xmmword_1400090D0;
        v19[5] = xmmword_1400090E0;
        v19[6] = xmmword_1400090F0;
        v21 = &KSMEMORY_TYPE_KERNEL_NONPAGED;
        if ( (BYTE4(v34) & 1) != 0 )
          v21 = &KSMEMORY_TYPE_KERNEL_PAGED;
        *(GUID *)((char *)v20 + 24) = *v21;
        *((_DWORD *)v20 + 16) = v34 | 0x80000081;
        *((_DWORD *)v20 + 17) = DWORD2(v34);
        *((_DWORD *)v20 + 18) = v35;
        *((_DWORD *)v20 + 23) = HIDWORD(v34);
        *((_DWORD *)v20 + 24) = HIDWORD(v34);
        v22 = -((int)v34 >= 0);
        *((_DWORD *)v20 + 26) = v22;
        *((_DWORD *)v20 + 27) = v22;
        goto LABEL_47;
      }
    }
    v12 = -1073741670;
    goto LABEL_47;
  }
  v12 = _KsEdit(PointerToPointerToItem->Bag, (PVOID *)PointerToPointerToItem, 0x88u, 0x88u, 0x4554534Du);
  if ( v12 >= 0 )
  {
    PointerToPointerToItem->Descriptor->AllocatorFraming = (const KSALLOCATOR_FRAMING_EX *)PointerToPointerToItem->Context;
    goto LABEL_52;
  }
LABEL_66:
  if ( Interface )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)Interface + 16LL))(Interface);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400082a0  push    rbp
0x1400082a2  push    rbx
0x1400082a3  push    rsi
0x1400082a4  push    rdi
0x1400082a5  push    r12
0x1400082a7  push    r13
0x1400082a9  push    r14
0x1400082ab  push    r15
0x1400082ad  lea     rbp, [rsp-1Fh]
0x1400082b2  sub     rsp, 98h
0x1400082b9  mov     rax, cs:__security_cookie
0x1400082c0  xor     rax, rsp
0x1400082c3  mov     [rbp+57h+var_50], rax
0x1400082c7  xor     r12d, r12d
0x1400082ca  mov     rsi, rcx
0x1400082cd  mov     [rbp+57h+Interface], r12
0x1400082d1  call    cs:__imp_KsPinGetParentFilter
0x1400082d8  nop     dword ptr [rax+rax+00h]
0x1400082dd  mov     edx, [rsi+18h]
0x1400082e0  lea     r13d, [r12+1]
0x1400082e5  xor     edx, r13d; PinId
0x1400082e8  mov     rcx, rax; Filter
0x1400082eb  mov     rdi, rax
0x1400082ee  call    cs:__imp_KsFilterGetFirstChildPin
0x1400082f5  nop     dword ptr [rax+rax+00h]
0x1400082fa  mov     rbx, rax
0x1400082fd  test    rax, rax
0x140008300  jnz     short loc_140008333
0x140008302  mov     edx, [rsi+18h]; PinId
0x140008305  mov     rcx, rdi; Filter
0x140008308  call    cs:__imp_KsFilterGetFirstChildPin
0x14000830f  nop     dword ptr [rax+rax+00h]
0x140008314  mov     rbx, rax
0x140008317  cmp     rax, rsi
0x14000831a  jnz     short loc_14000832E
0x14000831c  mov     rcx, rax; Pin
0x14000831f  call    cs:__imp_KsPinGetNextSiblingPin
0x140008326  nop     dword ptr [rax+rax+00h]
0x14000832b  mov     rbx, rax
0x14000832e  test    rbx, rbx
0x140008331  jz      short loc_140008364
0x140008333  mov     r14, [rsi+60h]
0x140008337  mov     rdx, [rbx+60h]; Source2
0x14000833b  mov     eax, [r14]
0x14000833e  cmp     eax, [rdx]
0x140008340  jnz     loc_1400087DC
0x140008346  mov     r8d, eax; Length
0x140008349  mov     rcx, r14; Source1
0x14000834c  call    cs:__imp_RtlCompareMemory
0x140008353  nop     dword ptr [rax+rax+00h]
0x140008358  mov     ecx, [r14]
0x14000835b  cmp     rcx, rax
0x14000835e  jnz     loc_1400087DC
0x140008364  lea     r8, [rbp+57h+Interface]; Interface
0x140008368  mov     rcx, rsi; Pin
0x14000836b  lea     rdx, IID_IKsControl; InterfaceId
0x140008372  mov     r15b, r12b
0x140008375  call    cs:__imp_KsPinGetConnectedPinInterface
0x14000837c  nop     dword ptr [rax+rax+00h]
0x140008381  test    eax, eax
0x140008383  js      loc_140008415
0x140008389  movups  xmm0, xmmword ptr cs:KSPROPSETID_StreamInterface.Data1
0x140008390  mov     rcx, [rbp+57h+Interface]
0x140008394  lea     rdx, [rbp+57h+NumberOfBytes]
0x140008398  mov     dword ptr [rbp+57h+NumberOfBytes], r12d
0x14000839c  lea     r14, [rsi+70h]
0x1400083a0  movdqu  [rbp+57h+var_80], xmm0
0x1400083a5  mov     [rbp+57h+var_70], r12d
0x1400083a9  mov     r9, r14
0x1400083ac  mov     [rbp+57h+var_6C], r13d
0x1400083b0  mov     r8d, 18h
0x1400083b6  mov     rax, [rcx]
0x1400083b9  mov     [rsp+0D0h+var_A8], rdx
0x1400083be  lea     rdx, [rbp+57h+var_80]
0x1400083c2  mov     [rsp+0D0h+Tag], 4
0x1400083ca  mov     rax, [rax+18h]
0x1400083ce  call    _guard_dispatch_icall
0x1400083d3  cmp     eax, 0C0000225h
0x1400083d8  jz      short loc_140008403
0x1400083da  cmp     eax, 0C0000230h
0x1400083df  jz      short loc_140008403
0x1400083e1  test    eax, eax
0x1400083e3  js      short loc_140008429
0x1400083e5  add     dword ptr [r14], 38h ; '8'
0x1400083e9  mov     ecx, [r14]
0x1400083ec  test    rbx, rbx
0x1400083ef  jz      short loc_140008429
0x1400083f1  mov     eax, [rbx+70h]
0x1400083f4  test    eax, eax
0x1400083f6  jnz     short loc_1400083FD
0x1400083f8  mov     r15b, r13b
0x1400083fb  jmp     short loc_140008429
0x1400083fd  cmp     eax, ecx
0x1400083ff  jnb     short loc_140008410
0x140008401  jmp     short loc_1400083F8
0x140008403  test    rbx, rbx
0x140008406  jz      short loc_14000840D
0x140008408  mov     eax, [rbx+70h]
0x14000840b  jmp     short loc_140008410
0x14000840d  mov     eax, r12d
0x140008410  mov     [r14], eax
0x140008413  jmp     short loc_140008429
0x140008415  mov     [rbp+57h+Interface], r12
0x140008419  test    rbx, rbx
0x14000841c  jz      short loc_140008423
0x14000841e  mov     eax, [rbx+70h]
0x140008421  jmp     short loc_140008426
0x140008423  mov     eax, r12d
0x140008426  mov     [rsi+70h], eax
0x140008429  mov     eax, 88h
0x14000842e  mov     r14d, 4554534Dh
0x140008434  cmp     [rsi+10h], r12
0x140008438  jz      short loc_140008472
0x14000843a  mov     rcx, [rsi+8]; ObjectBag
0x14000843e  mov     r9d, eax; OldSize
0x140008441  mov     r8d, eax; NewSize
0x140008444  mov     [rsp+0D0h+Tag], r14d; Tag
0x140008449  mov     rdx, rsi; PointerToPointerToItem
0x14000844c  call    cs:__imp__KsEdit
0x140008453  nop     dword ptr [rax+rax+00h]
0x140008458  mov     ebx, eax
0x14000845a  test    eax, eax
0x14000845c  js      loc_1400087A9
0x140008462  mov     rdx, [rsi]
0x140008465  mov     rcx, [rsi+10h]
0x140008469  mov     [rdx+78h], rcx
0x14000846d  jmp     loc_1400086D4
0x140008472  mov     rcx, [rbp+57h+Interface]
0x140008476  test    rcx, rcx
0x140008479  jz      loc_1400086D1
0x14000847f  movups  xmm0, xmmword ptr cs:KSPROPSETID_Connection.Data1
0x140008486  mov     dword ptr [rbp+57h+NumberOfBytes], r12d
0x14000848a  lea     rdx, [rbp+57h+NumberOfBytes]
0x14000848e  mov     [rbp+57h+var_70], 6
0x140008495  xor     r9d, r9d
0x140008498  movdqu  [rbp+57h+var_80], xmm0
0x14000849d  mov     [rbp+57h+var_6C], r13d
0x1400084a1  mov     rax, [rcx]
0x1400084a4  mov     [rsp+0D0h+var_A8], rdx
0x1400084a9  lea     r8d, [r9+18h]
0x1400084ad  lea     rdx, [rbp+57h+var_80]
0x1400084b1  mov     [rsp+0D0h+Tag], r12d
0x1400084b6  mov     rax, [rax+18h]
0x1400084ba  call    _guard_dispatch_icall
0x1400084bf  cmp     eax, 80000005h
0x1400084c4  jnz     loc_14000859A
0x1400084ca  mov     ebx, dword ptr [rbp+57h+NumberOfBytes]
0x1400084cd  mov     r8d, r14d; Tag
0x1400084d0  mov     edx, ebx; NumberOfBytes
0x1400084d2  mov     ecx, 401h; PoolType
0x1400084d7  call    cs:__imp_ExAllocatePoolWithTag
0x1400084de  nop     dword ptr [rax+rax+00h]
0x1400084e3  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x1400084ea  mov     r14, rax
0x1400084ed  jnz     short loc_140008501
0x1400084ef  test    rax, rax
0x1400084f2  jz      short loc_140008501
0x1400084f4  mov     r8d, ebx; Size
0x1400084f7  xor     edx, edx; Val
0x1400084f9  mov     rcx, rax; void *
0x1400084fc  call    memset
0x140008501  mov     [rdi+10h], r14
0x140008505  test    r14, r14
0x140008508  jz      loc_1400086B1
0x14000850e  mov     rcx, [rbp+57h+Interface]
0x140008512  lea     rdx, [rbp+57h+NumberOfBytes]
0x140008516  mov     [rsp+0D0h+var_A8], rdx
0x14000851b  mov     r9, r14
0x14000851e  mov     edx, dword ptr [rbp+57h+NumberOfBytes]
0x140008521  mov     r8d, 18h
0x140008527  mov     [rsp+0D0h+Tag], edx
0x14000852b  lea     rdx, [rbp+57h+var_80]
0x14000852f  mov     rax, [rcx]
0x140008532  mov     rax, [rax+18h]
0x140008536  call    _guard_dispatch_icall
0x14000853b  mov     ebx, eax
0x14000853d  test    eax, eax
0x14000853f  js      short loc_140008559
0x140008541  mov     r8d, [r14]
0x140008544  mov     eax, dword ptr [rbp+57h+NumberOfBytes]
0x140008547  imul    rcx, r8, 58h ; 'X'
0x14000854b  add     rcx, 18h
0x14000854f  cmp     rax, rcx
0x140008552  jz      short loc_140008572
0x140008554  mov     ebx, 0C0000001h
0x140008559  mov     rcx, [rdi+10h]; P
0x14000855d  call    cs:__imp_ExFreePool
0x140008564  nop     dword ptr [rax+rax+00h]
0x140008569  mov     [rdi+10h], r12
0x14000856d  jmp     loc_1400086BB
0x140008572  mov     edx, r12d
0x140008575  test    r8d, r8d
0x140008578  jz      loc_1400086BB
0x14000857e  mov     eax, edx
0x140008580  add     edx, r13d
0x140008583  imul    rcx, rax, 58h ; 'X'
0x140008587  or      dword ptr [rcx+r14+40h], 80000081h
0x140008590  cmp     edx, [r14]
0x140008593  jb      short loc_14000857E
0x140008595  jmp     loc_1400086BB
0x14000859a  mov     rcx, [rbp+57h+Interface]
0x14000859e  lea     rdx, [rbp+57h+NumberOfBytes]
0x1400085a2  xor     eax, eax
0x1400085a4  mov     [rbp+57h+var_70], 3
0x1400085ab  mov     [rbp+57h+var_58], rax
0x1400085af  lea     r9, [rbp+57h+var_68]
0x1400085b3  mov     [rsp+0D0h+var_A8], rdx
0x1400085b8  xorps   xmm0, xmm0
0x1400085bb  movups  [rbp+57h+var_68], xmm0
0x1400085bf  mov     rax, [rcx]
0x1400085c2  lea     rdx, [rbp+57h+var_80]
0x1400085c6  mov     r8d, 18h
0x1400085cc  mov     [rsp+0D0h+Tag], 18h
0x1400085d4  mov     rax, [rax+18h]
0x1400085d8  call    _guard_dispatch_icall
0x1400085dd  mov     ebx, eax
0x1400085df  test    eax, eax
0x1400085e1  js      loc_1400086B8
0x1400085e7  mov     r8d, r14d; Tag
0x1400085ea  mov     edx, 70h ; 'p'; NumberOfBytes
0x1400085ef  mov     ecx, r13d; PoolType
0x1400085f2  call    cs:__imp_ExAllocatePoolWithTag
0x1400085f9  nop     dword ptr [rax+rax+00h]
0x1400085fe  mov     [rdi+10h], rax
0x140008602  mov     rdx, rax
0x140008605  test    rax, rax
0x140008608  jz      loc_1400086B1
0x14000860e  movaps  xmm0, cs:AllocatorFraming
0x140008615  lea     rcx, KSMEMORY_TYPE_KERNEL_PAGED
0x14000861c  movups  xmmword ptr [rax], xmm0
0x14000861f  movaps  xmm1, cs:xmmword_1400090A0
0x140008626  movups  xmmword ptr [rax+10h], xmm1
0x14000862a  movaps  xmm0, cs:xmmword_1400090B0
0x140008631  movups  xmmword ptr [rax+20h], xmm0
0x140008635  movaps  xmm1, cs:xmmword_1400090C0
0x14000863c  movups  xmmword ptr [rax+30h], xmm1
0x140008640  movaps  xmm0, cs:xmmword_1400090D0
0x140008647  movups  xmmword ptr [rax+40h], xmm0
0x14000864b  movaps  xmm1, cs:xmmword_1400090E0
0x140008652  movups  xmmword ptr [rax+50h], xmm1
0x140008656  movaps  xmm0, cs:xmmword_1400090F0
0x14000865d  movups  xmmword ptr [rax+60h], xmm0
0x140008661  test    byte ptr [rbp+57h+var_68+4], r13b
0x140008665  lea     rax, KSMEMORY_TYPE_KERNEL_NONPAGED
0x14000866c  cmovnz  rax, rcx
0x140008670  movups  xmm0, xmmword ptr [rax]
0x140008673  movdqu  xmmword ptr [rdx+18h], xmm0
0x140008678  mov     eax, dword ptr [rbp+57h+var_68]
0x14000867b  or      eax, 80000081h
0x140008680  mov     [rdx+40h], eax
0x140008683  mov     eax, dword ptr [rbp+57h+var_68+8]
0x140008686  mov     [rdx+44h], eax
0x140008689  mov     eax, dword ptr [rbp+57h+var_58]
0x14000868c  mov     [rdx+48h], eax
0x14000868f  mov     eax, dword ptr [rbp+57h+var_68+0Ch]
0x140008692  mov     [rdx+5Ch], eax
0x140008695  mov     eax, dword ptr [rbp+57h+var_68+0Ch]
0x140008698  mov     [rdx+60h], eax
0x14000869b  mov     eax, dword ptr [rbp+57h+var_68]
0x14000869e  and     eax, 80000000h
0x1400086a3  neg     eax
0x1400086a5  sbb     ecx, ecx
0x1400086a7  not     ecx
0x1400086a9  mov     [rdx+68h], ecx
0x1400086ac  mov     [rdx+6Ch], ecx
0x1400086af  jmp     short loc_1400086BB
0x1400086b1  mov     ebx, 0C000009Ah
0x1400086b6  jmp     short loc_1400086BB
0x1400086b8  mov     ebx, r12d
0x1400086bb  cmp     [rdi+10h], r12
0x1400086bf  movzx   r15d, r15b
0x1400086c3  cmovnz  r15d, r13d
0x1400086c7  test    ebx, ebx
0x1400086c9  js      loc_1400087A9
0x1400086cf  jmp     short loc_1400086D4
0x1400086d1  mov     ebx, r12d
0x1400086d4  test    r15b, r15b
0x1400086d7  jz      loc_1400087A9
0x1400086dd  mov     r15d, r12d
0x1400086e0  mov     rax, [rdi]
0x1400086e3  cmp     r15d, [rax+20h]
0x1400086e7  jnb     loc_1400087A9
0x1400086ed  mov     edx, r15d; PinId
0x1400086f0  mov     rcx, rdi; Filter
0x1400086f3  call    cs:__imp_KsFilterGetFirstChildPin
0x1400086fa  nop     dword ptr [rax+rax+00h]
0x1400086ff  jmp     short loc_140008752
0x140008701  test    ebx, ebx
0x140008703  js      short loc_14000875A
0x140008705  mov     rcx, [r14+8]; ObjectBag
0x140008709  mov     eax, 88h
0x14000870e  mov     r9d, eax; OldSize
0x140008711  mov     [rsp+0D0h+Tag], 4554534Dh; Tag
0x140008719  mov     r8d, eax; NewSize
0x14000871c  mov     rdx, r14; PointerToPointerToItem
0x14000871f  call    cs:__imp__KsEdit
0x140008726  nop     dword ptr [rax+rax+00h]
0x14000872b  mov     ebx, eax
0x14000872d  test    eax, eax
0x14000872f  js      short loc_14000873C
  ... truncated ...
```
