# FatCommonClose

- ea: `0x140025bb8`
- end: `0x1400260c5`
- name: `FatCommonClose`
- size: `1293`
- prototype: `__int64 __fastcall(int, int, int, int, BOOLEAN Wait, char, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400260d0`
- `0x140026390`
- `0x1400438e0`

## callees

- `0x140006350`
- `0x14000c680`
- `0x140025bb8`
- `0x1400466c8`
- `0x14004814c`
- `0x140048184`

## import_xrefs

- `ntoskrnl!CcUninitializeCacheMap` at `0x140025e3a`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140025f65`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140025e3a`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140025f65`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140025e26`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140025f51`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140025e26`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140025f51`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025c67`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140026039`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005ba67`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025c67`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140026039`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005ba67`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025c99`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002601c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140026072`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400260b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ba40`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005baa3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005badf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025c99`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002601c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140026072`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400260b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ba40`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005baa3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005badf`
- `ntoskrnl!KeBugCheckEx` at `0x140025d35`
- `ntoskrnl!KeBugCheckEx` at `0x140025d35`
- `ntoskrnl!ObfDereferenceObject` at `0x140025e54`
- `ntoskrnl!ObfDereferenceObject` at `0x140025f7f`
- `ntoskrnl!ObfDereferenceObject` at `0x140025e54`
- `ntoskrnl!ObfDereferenceObject` at `0x140025f7f`

## pseudocode

```c
__int64 __fastcall FatCommonClose(__int64 a1, __int64 a2, __int64 a3, int a4, BOOLEAN Wait, char a6, _BYTE *a7)
{
  ULONG_PTR v7; // rsi
  int v12; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  char v15; // r12
  _DWORD *v16; // r14
  char v17; // r13
  __int64 v18; // rcx
  struct _FILE_OBJECT *v19; // rsi
  _WORD *v20; // rdi
  struct _FILE_OBJECT *v21; // r15
  __int64 v22; // rcx
  _BYTE *v23; // rdi
  struct _ERESOURCE *v24; // r15
  __int64 v25; // r9
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+38h] [rbp-F0h] BYREF
  struct _ERESOURCE *v27; // [rsp+48h] [rbp-E0h]
  struct _IO_STATUS_BLOCK v28; // [rsp+50h] [rbp-D8h] BYREF
  _QWORD v29[25]; // [rsp+60h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+138h] [rbp+10h] BYREF
  __int64 v31; // [rsp+140h] [rbp+18h] BYREF
  char v32; // [rsp+148h] [rbp+20h]

  v31 = a3;
  v30 = a2;
  v7 = a4;
  if ( a7 )
    *a7 = 0;
  if ( a4 == 1 )
    return 0;
  memset(v29, 0, 0x90u);
  LODWORD(v29[0]) = 9438472;
  LOBYTE(v29[8]) = 2;
  v29[7] = a1;
  v12 = HIDWORD(v29[8]);
  if ( Wait )
    v12 = 2;
  HIDWORD(v29[8]) = v12;
  v27 = (struct _ERESOURCE *)(a1 + 520);
  if ( ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 520), Wait) )
  {
    if ( (*(_DWORD *)(a1 + 200) & 0x200) != 0 && *(_QWORD *)(a1 + 784) != a2 )
    {
      ExReleaseResourceLite((PERESOURCE)(a1 + 520));
      return 259;
    }
    v15 = 0;
    v32 = 0;
    v16 = (_DWORD *)(a1 + 272);
    if ( (*(_DWORD *)(a1 + 200) & 0x80u) == 0 )
    {
      _InterlockedOr((volatile signed __int32 *)(a1 + 200), 0x80u);
      v17 = 0;
      ++*v16;
    }
    else
    {
      v17 = 1;
    }
    v18 = (unsigned int)(v7 - 2);
    if ( (_DWORD)v7 == 2 || (v18 = (unsigned int)(v7 - 3), (_DWORD)v7 == 3) )
    {
      if ( *(_WORD *)a2 == 1283 && *(_QWORD *)(a2 + 320) == a2 + 320 && *(_DWORD *)(a2 + 232) == 1 )
      {
        v19 = *(struct _FILE_OBJECT **)(a2 + 344);
        if ( v19 )
        {
          if ( (*(_DWORD *)(a1 + 200) & 0x1000000) != 0 )
          {
            IoStatus = 0;
            CcCoherencyFlushAndPurgeCache(v19->SectionObjectPointer, 0, 0, &IoStatus, 0);
          }
          CcUninitializeCacheMap(v19, 0, 0);
          *(_QWORD *)(a2 + 344) = 0;
          ObfDereferenceObject(v19);
        }
      }
      --*(_DWORD *)(a2 + 232);
      --*v16;
      if ( (*(_DWORD *)(a3 + 4) & 0x80u) != 0 )
        --*(_DWORD *)(a1 + 276);
      FatDeleteCcb(v18, &v31, v13, v14);
      goto LABEL_42;
    }
    switch ( (_DWORD)v7 )
    {
      case 4:
        --*(_DWORD *)(a1 + 240);
        --*v16;
        if ( (*(_DWORD *)(a3 + 4) & 0x80u) != 0 )
          --*(_DWORD *)(a1 + 276);
        FatDeleteCcb((unsigned int)(v7 - 4), &v31, v13, v14);
        break;
      case 5:
        goto LABEL_28;
      case 6:
        _InterlockedDecrement((volatile signed __int32 *)(a2 + 336));
        _InterlockedDecrement((volatile signed __int32 *)(a1 + 280));
        if ( *(_WORD *)a2 == 1284 )
          _InterlockedDecrement((volatile signed __int32 *)(a1 + 284));
        if ( !v17 )
          goto LABEL_42;
        break;
      case 7:
LABEL_28:
        _InterlockedDecrement((volatile signed __int32 *)(a1 + 280));
        _InterlockedDecrement((volatile signed __int32 *)(a1 + 284));
        break;
      default:
        if ( (unsigned int)(v7 - 8) >= 2 )
          KeBugCheckEx(0x23u, 0x5048Fu, v7, 0, 0);
        --*(_DWORD *)(a2 + 232);
        _InterlockedDecrement((volatile signed __int32 *)(a1 + 280));
LABEL_42:
        if ( *(_WORD *)a2 == 1282 && !*(_DWORD *)(a2 + 232)
          || *(_WORD *)a2 == 1283
          && *(_QWORD *)(a2 + 320) == a2 + 320
          && !*(_DWORD *)(a2 + 232)
          && !*(_DWORD *)(a2 + 336) )
        {
          v20 = *(_WORD **)(a2 + 176);
          _InterlockedOr((volatile signed __int32 *)(a1 + 200), 0x100u);
          FatDeleteFcb(1282, &v30);
          while ( *v20 == 1283 )
          {
            if ( *((_WORD **)v20 + 40) != v20 + 160 )
              break;
            if ( *((_DWORD *)v20 + 58) )
              break;
            v21 = (struct _FILE_OBJECT *)*((_QWORD *)v20 + 43);
            if ( !v21 )
              break;
            if ( (*(_DWORD *)(a1 + 200) & 0x1000000) != 0 )
            {
              v28 = 0;
              CcCoherencyFlushAndPurgeCache(v21->SectionObjectPointer, 0, 0, &v28, 0);
            }
            CcUninitializeCacheMap(v21, 0, 0);
            *((_QWORD *)v20 + 43) = 0;
            ObfDereferenceObject(v21);
            if ( *((_DWORD *)v20 + 84) )
              break;
            IoStatus.Pointer = v20;
            v20 = (_WORD *)*((_QWORD *)v20 + 22);
            _InterlockedOr((volatile signed __int32 *)(a1 + 200), 0x100u);
            FatDeleteFcb(v22, &IoStatus);
          }
        }
        v15 = v32;
        break;
    }
    if ( v17 )
    {
      v24 = v27;
    }
    else
    {
      if ( *v16 == 1 && *(_DWORD *)(a1 + 204) != 1 && (*(_DWORD *)(a1 + 200) & 0x80000) == 0 && (v23 = a7) != 0 && a6 )
      {
        v24 = (struct _ERESOURCE *)(a1 + 520);
        ExReleaseResourceLite((PERESOURCE)(a1 + 520));
        HIDWORD(v29[8]) |= 2u;
        ExAcquireResourceExclusiveLite(&Resource, 1u);
        FatAcquireExclusiveVcb_Real(v29, a1, 0, v25);
        --*v16;
        v15 = FatCheckForDismount(v29, a1, 0);
        ExReleaseResourceLite(&Resource);
        *v23 = v15;
      }
      else
      {
        --*v16;
        v24 = (struct _ERESOURCE *)(a1 + 520);
      }
      if ( v15 )
        return 0;
      _InterlockedAnd((volatile signed __int32 *)(a1 + 200), 0xFFFFFF7F);
    }
    if ( !v15 )
      ExReleaseResourceLite(v24);
    return 0;
  }
  return 259;
}

```

## disassembly

```asm
0x140025bb8  mov     [rsp+arg_10], r8
0x140025bbd  mov     [rsp+arg_8], rdx
0x140025bc2  mov     [rsp+arg_0], rcx
0x140025bc7  push    rbx
0x140025bc8  push    rsi
0x140025bc9  push    rdi
0x140025bca  push    r12
0x140025bcc  push    r13
0x140025bce  push    r14
0x140025bd0  push    r15
0x140025bd2  sub     rsp, 0F0h
0x140025bd9  movsxd  rsi, r9d
0x140025bdc  mov     r15, r8
0x140025bdf  mov     rdi, rdx
0x140025be2  mov     rbx, rcx
0x140025be5  mov     rax, [rsp+128h+arg_30]
0x140025bed  test    rax, rax
0x140025bf0  jz      short loc_140025BF5
0x140025bf2  mov     byte ptr [rax], 0
0x140025bf5  cmp     esi, 1
0x140025bf8  jnz     short loc_140025C10
0x140025bfa  xor     eax, eax
0x140025bfc  add     rsp, 0F0h
0x140025c03  pop     r15
0x140025c05  pop     r14
0x140025c07  pop     r13
0x140025c09  pop     r12
0x140025c0b  pop     rdi
0x140025c0c  pop     rsi
0x140025c0d  pop     rbx
0x140025c0e  retn
0x140025c10  xor     edx, edx; Val
0x140025c12  mov     r8d, 90h; Size
0x140025c18  lea     rcx, [rsp+128h+var_C8]; void *
0x140025c1d  call    memset
0x140025c22  mov     [rsp+128h+var_C8], 900508h
0x140025c2a  mov     ecx, 2
0x140025c2f  mov     [rsp+128h+var_88], cl
0x140025c36  mov     [rsp+128h+var_90], rbx
0x140025c3e  mov     eax, [rsp+128h+var_84]
0x140025c45  mov     dl, [rsp+128h+Wait]; Wait
0x140025c4c  test    dl, dl
0x140025c4e  cmovnz  eax, ecx
0x140025c51  mov     [rsp+128h+var_84], eax
0x140025c58  lea     r14, [rbx+208h]
0x140025c5f  mov     [rsp+128h+var_E0], r14
0x140025c64  mov     rcx, r14; Resource
0x140025c67  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140025c6e  nop     dword ptr [rax+rax+00h]
0x140025c73  test    al, al
0x140025c75  jnz     short loc_140025C81
0x140025c77  mov     eax, 103h
0x140025c7c  jmp     loc_140025BFC
0x140025c81  mov     eax, [rbx+0C8h]
0x140025c87  bt      eax, 9
0x140025c8b  jnb     short loc_140025CA7
0x140025c8d  cmp     [rbx+310h], rdi
0x140025c94  jz      short loc_140025CA7
0x140025c96  mov     rcx, r14; Resource
0x140025c99  call    cs:__imp_ExReleaseResourceLite
0x140025ca0  nop     dword ptr [rax+rax+00h]
0x140025ca5  jmp     short loc_140025C77
0x140025ca7  xor     r12b, r12b
0x140025caa  mov     [rsp+128h+arg_18], r12b
0x140025cb2  mov     [rsp+128h+var_F8], r12b
0x140025cb7  mov     eax, [rbx+0C8h]
0x140025cbd  lea     r14, [rbx+110h]
0x140025cc4  test    al, al
0x140025cc6  jns     short loc_140025CCD
0x140025cc8  mov     r13b, 1
0x140025ccb  jmp     short loc_140025CDE
0x140025ccd  lock or dword ptr [rbx+0C8h], 80h
0x140025cd8  xor     r13b, r13b
0x140025cdb  inc     dword ptr [r14]
0x140025cde  mov     [rsp+128h+var_F7], r13b
0x140025ce3  mov     ecx, esi
0x140025ce5  sub     ecx, 2
0x140025ce8  jz      loc_140025DCB
0x140025cee  sub     ecx, 1
0x140025cf1  jz      loc_140025DCB
0x140025cf7  sub     ecx, 1
0x140025cfa  jz      loc_140025D9F
0x140025d00  sub     ecx, 1
0x140025d03  jz      loc_140025D89
0x140025d09  sub     ecx, 1
0x140025d0c  jz      short loc_140025D53
0x140025d0e  sub     ecx, 1
0x140025d11  jz      short loc_140025D89
0x140025d13  sub     ecx, 1
0x140025d16  jz      short loc_140025D41
0x140025d18  cmp     ecx, 1
0x140025d1b  jz      short loc_140025D41
0x140025d1d  mov     r8, rsi; BugCheckParameter2
0x140025d20  mov     [rsp+128h+BugCheckParameter4], 0; BugCheckParameter4
0x140025d29  xor     r9d, r9d; BugCheckParameter3
0x140025d2c  mov     edx, 5048Fh; BugCheckParameter1
0x140025d31  lea     ecx, [r9+23h]; BugCheckCode
0x140025d35  call    cs:__imp_KeBugCheckEx
0x140025d41  or      esi, 0FFFFFFFFh
0x140025d44  add     [rdi+0E8h], esi
0x140025d4a  lock dec dword ptr [rbx+118h]
0x140025d51  jmp     short loc_140025D7E
0x140025d53  lock dec dword ptr [rdi+150h]
0x140025d5a  lock dec dword ptr [rbx+118h]
0x140025d61  mov     eax, 504h
0x140025d66  cmp     [rdi], ax
0x140025d69  jnz     short loc_140025D72
0x140025d6b  lock dec dword ptr [rbx+11Ch]
0x140025d72  or      esi, 0FFFFFFFFh
0x140025d75  test    r13b, r13b
0x140025d78  jnz     loc_140025FCB
0x140025d7e  mov     r12d, 503h
0x140025d84  jmp     loc_140025E87
0x140025d89  lock dec dword ptr [rbx+118h]
0x140025d90  lock dec dword ptr [rbx+11Ch]
0x140025d97  or      esi, 0FFFFFFFFh
0x140025d9a  jmp     loc_140025FCB
0x140025d9f  or      esi, 0FFFFFFFFh
0x140025da2  add     [rbx+0F0h], esi
0x140025da8  add     [r14], esi
0x140025dab  mov     eax, [r15+4]
0x140025daf  test    al, al
0x140025db1  jns     short loc_140025DB9
0x140025db3  add     [rbx+114h], esi
0x140025db9  lea     rdx, [rsp+128h+arg_10]
0x140025dc1  call    FatDeleteCcb
0x140025dc6  jmp     loc_140025FCB
0x140025dcb  mov     r12d, 503h
0x140025dd1  cmp     [rdi], r12w
0x140025dd5  jnz     loc_140025E60
0x140025ddb  lea     rax, [rdi+140h]
0x140025de2  cmp     [rax], rax
0x140025de5  jnz     short loc_140025E60
0x140025de7  cmp     dword ptr [rdi+0E8h], 1
0x140025dee  jnz     short loc_140025E60
0x140025df0  mov     rsi, [rdi+158h]
0x140025df7  test    rsi, rsi
0x140025dfa  jz      short loc_140025E60
0x140025dfc  mov     eax, [rbx+0C8h]
0x140025e02  bt      eax, 18h
0x140025e06  jnb     short loc_140025E32
0x140025e08  xorps   xmm0, xmm0
0x140025e0b  movups  xmmword ptr [rsp+128h+IoStatus], xmm0
0x140025e10  mov     dword ptr [rsp+128h+BugCheckParameter4], 0; Flags
0x140025e18  lea     r9, [rsp+128h+IoStatus]; IoStatus
0x140025e1d  xor     r8d, r8d; Length
0x140025e20  xor     edx, edx; FileOffset
0x140025e22  mov     rcx, [rsi+28h]; SectionObjectPointer
0x140025e26  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x140025e2d  nop     dword ptr [rax+rax+00h]
0x140025e32  xor     r8d, r8d; UninitializeEvent
0x140025e35  xor     edx, edx; TruncateSize
0x140025e37  mov     rcx, rsi; FileObject
0x140025e3a  call    cs:__imp_CcUninitializeCacheMap
0x140025e41  nop     dword ptr [rax+rax+00h]
0x140025e46  mov     qword ptr [rdi+158h], 0
0x140025e51  mov     rcx, rsi; Object
0x140025e54  call    cs:__imp_ObfDereferenceObject
0x140025e5b  nop     dword ptr [rax+rax+00h]
0x140025e60  or      esi, 0FFFFFFFFh
0x140025e63  add     [rdi+0E8h], esi
0x140025e69  add     [r14], esi
0x140025e6c  mov     eax, [r15+4]
0x140025e70  test    al, al
0x140025e72  jns     short loc_140025E7A
0x140025e74  add     [rbx+114h], esi
0x140025e7a  lea     rdx, [rsp+128h+arg_10]
0x140025e82  call    FatDeleteCcb
0x140025e87  movzx   eax, word ptr [rdi]
0x140025e8a  mov     ecx, 502h
0x140025e8f  cmp     ax, cx
0x140025e92  jnz     short loc_140025E9D
0x140025e94  cmp     dword ptr [rdi+0E8h], 0
0x140025e9b  jz      short loc_140025ED1
0x140025e9d  cmp     ax, r12w
0x140025ea1  jnz     loc_140025FC3
0x140025ea7  lea     rax, [rdi+140h]
0x140025eae  cmp     [rax], rax
0x140025eb1  jnz     loc_140025FC3
0x140025eb7  cmp     dword ptr [rdi+0E8h], 0
0x140025ebe  jnz     loc_140025FC3
0x140025ec4  cmp     dword ptr [rdi+150h], 0
0x140025ecb  jnz     loc_140025FC3
0x140025ed1  mov     rdi, [rdi+0B0h]
0x140025ed8  lock or dword ptr [rbx+0C8h], 100h
0x140025ee3  lea     rdx, [rsp+128h+arg_8]
0x140025eeb  call    FatDeleteFcb
0x140025ef0  cmp     [rdi], r12w
0x140025ef4  jnz     loc_140025FC3
0x140025efa  lea     rax, [rdi+140h]
0x140025f01  cmp     [rax], rax
0x140025f04  jnz     loc_140025FC3
0x140025f0a  cmp     dword ptr [rdi+0E8h], 0
0x140025f11  jnz     loc_140025FC3
0x140025f17  mov     r15, [rdi+158h]
0x140025f1e  test    r15, r15
0x140025f21  jz      loc_140025FC3
0x140025f27  mov     eax, [rbx+0C8h]
0x140025f2d  bt      eax, 18h
0x140025f31  jnb     short loc_140025F5D
0x140025f33  xorps   xmm0, xmm0
0x140025f36  movups  xmmword ptr [rsp+128h+var_D8], xmm0
0x140025f3b  mov     dword ptr [rsp+128h+BugCheckParameter4], 0; Flags
0x140025f43  lea     r9, [rsp+128h+var_D8]; IoStatus
0x140025f48  xor     r8d, r8d; Length
0x140025f4b  xor     edx, edx; FileOffset
0x140025f4d  mov     rcx, [r15+28h]; SectionObjectPointer
0x140025f51  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x140025f58  nop     dword ptr [rax+rax+00h]
0x140025f5d  xor     r8d, r8d; UninitializeEvent
0x140025f60  xor     edx, edx; TruncateSize
0x140025f62  mov     rcx, r15; FileObject
0x140025f65  call    cs:__imp_CcUninitializeCacheMap
0x140025f6c  nop     dword ptr [rax+rax+00h]
0x140025f71  mov     qword ptr [rdi+158h], 0
0x140025f7c  mov     rcx, r15; Object
0x140025f7f  call    cs:__imp_ObfDereferenceObject
0x140025f86  nop     dword ptr [rax+rax+00h]
0x140025f8b  cmp     dword ptr [rdi+150h], 0
0x140025f92  jnz     short loc_140025FC3
0x140025f94  mov     qword ptr [rsp+128h+IoStatus], 0
0x140025f9d  mov     qword ptr [rsp+128h+IoStatus], rdi
0x140025fa2  mov     rdi, [rdi+0B0h]
0x140025fa9  lock or dword ptr [rbx+0C8h], 100h
0x140025fb4  lea     rdx, [rsp+128h+IoStatus]
0x140025fb9  call    FatDeleteFcb
0x140025fbe  jmp     loc_140025EF0
0x140025fc3  mov     r12b, [rsp+128h+arg_18]
0x140025fcb  test    r13b, r13b
0x140025fce  jnz     loc_1400260A3
0x140025fd4  cmp     dword ptr [r14], 1
0x140025fd8  jnz     loc_140026083
0x140025fde  cmp     dword ptr [rbx+0CCh], 1
0x140025fe5  jz      loc_140026083
0x140025feb  mov     eax, [rbx+0C8h]
0x140025ff1  bt      eax, 13h
0x140025ff5  jb      loc_140026083
0x140025ffb  mov     rdi, [rsp+128h+arg_30]
0x140026003  test    rdi, rdi
0x140026006  jz      short loc_140026083
0x140026008  cmp     [rsp+128h+arg_28], r13b
0x140026010  jz      short loc_140026083
0x140026012  lea     r15, [rbx+208h]
0x140026019  mov     rcx, r15; Resource
0x14002601c  call    cs:__imp_ExReleaseResourceLite
0x140026023  nop     dword ptr [rax+rax+00h]
0x140026028  or      [rsp+128h+var_84], 2
0x140026030  mov     dl, 1; Wait
0x140026032  lea     rcx, Resource; Resource
0x140026039  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140026040  nop     dword ptr [rax+rax+00h]
0x140026045  xor     r8d, r8d
0x140026048  mov     rdx, rbx
0x14002604b  lea     rcx, [rsp+128h+var_C8]
0x140026050  call    FatAcquireExclusiveVcb_Real
0x140026055  add     [r14], esi
0x140026058  xor     r8d, r8d
0x14002605b  mov     rdx, rbx
0x14002605e  lea     rcx, [rsp+128h+var_C8]
0x140026063  call    FatCheckForDismount
0x140026068  mov     r12b, al
0x14002606b  lea     rcx, Resource; Resource
0x140026072  call    cs:__imp_ExReleaseResourceLite
0x140026079  nop     dword ptr [rax+rax+00h]
0x14002607e  mov     [rdi], r12b
0x140026081  jmp     short loc_14002608D
0x140026083  add     [r14], esi
0x140026086  lea     r15, [rbx+208h]
0x14002608d  test    r12b, r12b
0x140026090  jnz     loc_140025BFA
0x140026096  lock and dword ptr [rbx+0C8h], 0FFFFFF7Fh
0x1400260a1  jmp     short loc_1400260A8
0x1400260a3  mov     r15, [rsp+128h+var_E0]
0x1400260a8  test    r12b, r12b
0x1400260ab  jnz     loc_140025BFA
0x1400260b1  mov     rcx, r15; Resource
0x1400260b4  call    cs:__imp_ExReleaseResourceLite
0x1400260bb  nop     dword ptr [rax+rax+00h]
0x1400260c0  jmp     loc_140025BFA
0x14005b9d9  push    rbx
0x14005b9db  push    rbp
0x14005b9dc  push    rsi
0x14005b9dd  push    rdi
0x14005b9de  sub     rsp, 38h
0x14005b9e2  mov     rbp, rdx
0x14005b9e5  mov     rdi, [rbp+130h]
0x14005b9ec  cmp     byte ptr [rbp+31h], 0
0x14005b9f0  jnz     loc_14005BAD2
0x14005b9f6  cmp     dword ptr [rdi+110h], 1
0x14005b9fd  jnz     loc_14005BAB3
0x14005ba03  cmp     dword ptr [rdi+0CCh], 1
0x14005ba0a  jz      loc_14005BAB3
0x14005ba10  mov     eax, [rdi+0C8h]
0x14005ba16  bt      eax, 13h
0x14005ba1a  jb      loc_14005BAB3
0x14005ba20  mov     rsi, [rbp+160h]
0x14005ba27  test    rsi, rsi
0x14005ba2a  jz      loc_14005BAB3
0x14005ba30  cmp     byte ptr [rbp+158h], 0
0x14005ba37  jz      short loc_14005BAB3
  ... truncated ...
```
