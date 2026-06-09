# CCheckBase::_SetState(HCSTATE const *,bool)

- ea: `0x1800019f0`
- end: `0x180001e93`
- name: `?_SetState@CCheckBase@@IEAAJPEBUHCSTATE@@_N@Z`
- size: `1187`
- prototype: `__int64 __fastcall(CCheckBase *__hidden this, const struct HCSTATE *, bool)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180001320`
- `0x1800015b0`
- `0x1800085b0`

## callees

- `0x1800019f0`
- `0x180001ea0`
- `0x18000206c`
- `0x1800020a0`
- `0x180002170`
- `0x180002300`
- `0x180004fc8`
- `0x180009458`
- `0x180009b04`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001bf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001bf7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001b0d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001b0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001b9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001b9d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180001bcc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180001bcc`
- `COMCTL32!__imp_DPA_Create` at `0x180001d6e`
- `COMCTL32!__imp_DPA_Create` at `0x180001d6e`
- `COMCTL32!__imp_DPA_InsertPtr` at `0x180001cd1`
- `COMCTL32!__imp_DPA_InsertPtr` at `0x180001e09`
- `COMCTL32!__imp_DPA_InsertPtr` at `0x180001cd1`
- `COMCTL32!__imp_DPA_InsertPtr` at `0x180001e09`

## pseudocode

```c
__int64 __fastcall CCheckBase::_SetState(RTL_SRWLOCK *this, const struct HCSTATE *a2, char a3)
{
  int v3; // ebx
  HDPA *i; // r13
  void *v7; // rax
  __int64 v8; // rcx
  HDPA *v9; // r14
  int StringHelper; // ebx
  unsigned __int16 **v11; // r15
  CDescriptionAndIcon *v12; // rax
  CDescriptionAndIcon *v13; // rax
  unsigned __int16 **v14; // rsi
  _DWORD *v15; // r12
  HDPA *v16; // rsi
  PVOID Ptr; // rcx
  PVOID v18; // rcx
  PVOID v19; // rcx
  PVOID v20; // rcx
  PVOID v22; // rcx
  _QWORD *v23; // rax
  _DWORD *v24; // rsi
  __int64 v25; // rsi
  __int64 v26; // rbx
  CCommand *v27; // rax
  CCommand *v28; // rax
  CCommand *v29; // r14
  int inserted; // eax
  _QWORD *v31; // r14
  HDPA v32; // rax
  const struct HCNOTIFICATION *v33; // rcx
  void *v34; // r14
  HDPA *v35; // [rsp+68h] [rbp+10h] BYREF
  char v36; // [rsp+70h] [rbp+18h]
  void *p; // [rsp+78h] [rbp+20h] BYREF

  v36 = a3;
  v3 = *((_DWORD *)a2 + 8);
  i = 0;
  if ( v3 )
  {
    v7 = operator new(0x18u);
    if ( v7 )
    {
      v9 = (HDPA *)CCommandCollection<CCommand>::CCommandCollection<CCommand>(v7);
      if ( v9 )
      {
        v32 = DPA_Create(v3);
        v9[2] = v32;
        if ( v32 )
        {
          StringHelper = 0;
          v25 = 0;
          for ( i = v9; (unsigned int)v25 < *((_DWORD *)a2 + 8); v25 = (unsigned int)(v25 + 1) )
          {
            if ( StringHelper < 0 )
              break;
            v26 = *((_QWORD *)a2 + 5);
            v27 = (CCommand *)operator new(0x30u);
            if ( v27 && (v28 = CCommand::CCommand(v27), (v29 = v28) != 0) )
            {
              StringHelper = (*(__int64 (__fastcall **)(CCommand *, __int64))(*(_QWORD *)v28 + 8LL))(
                               v28,
                               v26 + 24 * v25);
              if ( StringHelper >= 0 )
              {
                inserted = DPA_InsertPtr(i[2], 0x7FFFFFFF, v29);
                v31 = (_QWORD *)((char *)v29 + 32);
                if ( inserted == -1 )
                {
                  StringHelper = -2147024882;
                }
                else
                {
                  StringHelper = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v31 + 8LL))(v31);
                }
                (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
              }
              else
              {
                (*(void (__fastcall **)(_QWORD *))(*((_QWORD *)v29 + 4) + 16LL))((_QWORD *)v29 + 4);
              }
            }
            else
            {
              StringHelper = -2147024882;
            }
          }
LABEL_5:
          v11 = 0;
          if ( StringHelper < 0 )
            goto LABEL_12;
          goto LABEL_6;
        }
        (*((void (__fastcall **)(HDPA *))*v9 + 2))(v9);
      }
    }
    StringHelper = -2147024882;
    goto LABEL_5;
  }
  v11 = 0;
LABEL_6:
  v12 = (CDescriptionAndIcon *)operator new(0x20u);
  if ( v12 && (v13 = CDescriptionAndIcon::CDescriptionAndIcon(v12), (v14 = (unsigned __int16 **)v13) != 0) )
  {
    StringHelper = LoadStringHelper(*((_QWORD *)a2 + 2), 0, (unsigned __int16 **)v13 + 2);
    if ( StringHelper >= 0 )
      StringHelper = LoadStringHelper(*((_QWORD *)a2 + 3), 1, v14 + 3);
    if ( StringHelper < 0 )
      (*((void (__fastcall **)(unsigned __int16 **))*v14 + 2))(v14);
    else
      v11 = v14;
  }
  else
  {
    StringHelper = -2147024882;
  }
LABEL_12:
  v15 = 0;
  if ( StringHelper >= 0 )
  {
    v23 = operator new(0x30u);
    v24 = v23;
    if ( v23 )
    {
      v23[2] = 0;
      v23[3] = 0;
      v23[4] = 0;
      *v23 = &CStatus::`vftable'{for `IHCStatus'};
      v23[1] = &CStatus::`vftable'{for `CCommandImpl'};
      v23[5] = 1;
      _InterlockedIncrement(&g_cLocks);
      StringHelper = CCommandImpl::_Initialize((CCommandImpl *)(v23 + 1), (PVOID *)a2 + 6);
      if ( StringHelper >= 0 )
      {
        v15 = v24;
        v24[11] = *((unsigned __int8 *)a2 + 72);
      }
      else
      {
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v24 + 16LL))(v24);
      }
    }
    else
    {
      StringHelper = -2147024882;
    }
  }
  v16 = 0;
  v35 = 0;
  if ( StringHelper < 0 )
    goto LABEL_14;
  if ( *((_QWORD *)a2 + 1) )
  {
    StringHelper = CNotificationCollection<CNotification>::s_CreateInstance(v8, &v35);
    if ( StringHelper < 0
      || (v33 = (const struct HCNOTIFICATION *)*((_QWORD *)a2 + 1),
          p = 0,
          StringHelper = CNotification::s_CreateInstance(v33, (struct CNotification **)&p),
          StringHelper < 0) )
    {
      v16 = v35;
    }
    else
    {
      v16 = v35;
      v34 = p;
      if ( DPA_InsertPtr(v35[2], 0x7FFFFFFF, p) == -1 )
      {
        StringHelper = -2147024882;
      }
      else
      {
        StringHelper = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v34 + 8LL))(v34);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)v34 + 16LL))(v34);
      if ( StringHelper >= 0 )
        goto LABEL_24;
    }
LABEL_14:
    if ( v11 )
      (*((void (__fastcall **)(unsigned __int16 **))*v11 + 2))(v11);
    if ( i )
      (*((void (__fastcall **)(HDPA *))*i + 2))(i);
    if ( v15 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v16 )
      (*((void (__fastcall **)(HDPA *))*v16 + 2))(v16);
    return (unsigned int)StringHelper;
  }
LABEL_24:
  AcquireSRWLockExclusive(this + 2);
  Ptr = this[23].Ptr;
  if ( Ptr )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
  v18 = this[24].Ptr;
  this[23].Ptr = v11;
  if ( v18 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v18 + 16LL))(v18);
  v19 = this[25].Ptr;
  this[24].Ptr = i;
  if ( v19 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v19 + 16LL))(v19);
  v20 = this[22].Ptr;
  this[25].Ptr = v15;
  if ( v20 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v20 + 16LL))(v20);
  this[22].Ptr = v16;
  LODWORD(this[26].Ptr) = *(unsigned __int8 *)a2;
  HIDWORD(this[26].Ptr) = *((unsigned __int8 *)a2 + 1);
  ReleaseSRWLockExclusive(this + 2);
  if ( v36 )
  {
    AcquireSRWLockShared(this + 2);
    v22 = this[27].Ptr;
    if ( v22 )
      (*(void (__fastcall **)(PVOID, RTL_SRWLOCK *))(*(_QWORD *)v22 + 24LL))(v22, this);
    ReleaseSRWLockShared(this + 2);
  }
  return (unsigned int)StringHelper;
}

```

## disassembly

```asm
0x1800019f0  mov     [rsp+arg_0], rbx
0x1800019f5  mov     [rsp+arg_10], r8b
0x1800019fa  push    rbp
0x1800019fb  push    rsi
0x1800019fc  push    rdi
0x1800019fd  push    r12
0x1800019ff  push    r13
0x180001a01  push    r14
0x180001a03  push    r15
0x180001a05  sub     rsp, 20h
0x180001a09  mov     ebx, [rdx+20h]
0x180001a0c  xor     r13d, r13d
0x180001a0f  mov     rbp, rdx
0x180001a12  mov     rdi, rcx
0x180001a15  test    ebx, ebx
0x180001a17  jz      loc_180001C05
0x180001a1d  mov     ecx, 18h; Size
0x180001a22  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001a27  test    rax, rax
0x180001a2a  jz      short loc_180001A40
0x180001a2c  mov     rcx, rax
0x180001a2f  call    ??0?$CCommandCollection@VCCommand@@@@IEAA@XZ; CCommandCollection<CCommand>::CCommandCollection<CCommand>(void)
0x180001a34  mov     r14, rax
0x180001a37  test    rax, rax
0x180001a3a  jnz     loc_180001D6C
0x180001a40  mov     ebx, 8007000Eh
0x180001a45  xor     r15d, r15d
0x180001a48  test    ebx, ebx
0x180001a4a  js      short loc_180001A93
0x180001a4c  mov     ecx, 20h ; ' '; Size
0x180001a51  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001a56  test    rax, rax
0x180001a59  jz      loc_180001C3E
0x180001a5f  mov     rcx, rax; this
0x180001a62  call    ??0CDescriptionAndIcon@@AEAA@XZ; CDescriptionAndIcon::CDescriptionAndIcon(void)
0x180001a67  mov     rsi, rax
0x180001a6a  test    rax, rax
0x180001a6d  jz      loc_180001C3E
0x180001a73  mov     rcx, [rbp+10h]; uID
0x180001a77  lea     r8, [rax+10h]; unsigned __int16 **
0x180001a7b  xor     edx, edx; bool
0x180001a7d  call    ?LoadStringHelper@@YAJPEBG_NPEAPEAG@Z; LoadStringHelper(ushort const *,bool,ushort * *)
0x180001a82  mov     ebx, eax
0x180001a84  test    eax, eax
0x180001a86  jns     loc_180001D9B
0x180001a8c  test    ebx, ebx
0x180001a8e  js      short loc_180001AE5
0x180001a90  mov     r15, rsi
0x180001a93  xor     r12d, r12d
0x180001a96  test    ebx, ebx
0x180001a98  jns     loc_180001C0D
0x180001a9e  xor     esi, esi
0x180001aa0  mov     [rsp+58h+arg_8], rsi
0x180001aa5  test    ebx, ebx
0x180001aa7  jns     loc_180001DC0
0x180001aad  test    r15, r15
0x180001ab0  jnz     loc_180001E55
0x180001ab6  test    r13, r13
0x180001ab9  jnz     loc_180001E69
0x180001abf  test    r12, r12
0x180001ac2  jnz     loc_180001E7E
0x180001ac8  test    rsi, rsi
0x180001acb  jz      loc_180001BB0
0x180001ad1  mov     rax, [rsi]
0x180001ad4  mov     rcx, rsi
0x180001ad7  mov     rax, [rax+10h]
0x180001adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ae0  jmp     loc_180001BB0
0x180001ae5  mov     rax, [rsi]
0x180001ae8  mov     rcx, rsi
0x180001aeb  mov     rax, [rax+10h]
0x180001aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001af4  jmp     short loc_180001A93
0x180001af6  mov     rax, [r14]
0x180001af9  mov     rcx, r14
0x180001afc  mov     rax, [rax+10h]
0x180001b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b05  test    ebx, ebx
0x180001b07  js      short loc_180001AAD
0x180001b09  lea     rcx, [rdi+10h]; SRWLock
0x180001b0d  call    cs:__imp_AcquireSRWLockExclusive
0x180001b14  nop     dword ptr [rax+rax+00h]
0x180001b19  mov     rcx, [rdi+0B8h]
0x180001b20  test    rcx, rcx
0x180001b23  jz      short loc_180001B31
0x180001b25  mov     rax, [rcx]
0x180001b28  mov     rax, [rax+10h]
0x180001b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b31  mov     rcx, [rdi+0C0h]
0x180001b38  mov     [rdi+0B8h], r15
0x180001b3f  test    rcx, rcx
0x180001b42  jz      short loc_180001B50
0x180001b44  mov     rax, [rcx]
0x180001b47  mov     rax, [rax+10h]
0x180001b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b50  mov     rcx, [rdi+0C8h]
0x180001b57  mov     [rdi+0C0h], r13
0x180001b5e  test    rcx, rcx
0x180001b61  jnz     loc_180001C2D
0x180001b67  mov     rcx, [rdi+0B0h]
0x180001b6e  mov     [rdi+0C8h], r12
0x180001b75  test    rcx, rcx
0x180001b78  jnz     loc_180001E44
0x180001b7e  mov     [rdi+0B0h], rsi
0x180001b85  lea     rcx, [rdi+10h]; SRWLock
0x180001b89  movzx   eax, byte ptr [rbp+0]
0x180001b8d  mov     [rdi+0D0h], eax
0x180001b93  movzx   eax, byte ptr [rbp+1]
0x180001b97  mov     [rdi+0D4h], eax
0x180001b9d  call    cs:__imp_ReleaseSRWLockExclusive
0x180001ba4  nop     dword ptr [rax+rax+00h]
0x180001ba9  cmp     [rsp+58h+arg_10], 0
0x180001bae  jnz     short loc_180001BC8
0x180001bb0  mov     eax, ebx
0x180001bb2  mov     rbx, [rsp+58h+arg_0]
0x180001bb7  add     rsp, 20h
0x180001bbb  pop     r15
0x180001bbd  pop     r14
0x180001bbf  pop     r13
0x180001bc1  pop     r12
0x180001bc3  pop     rdi
0x180001bc4  pop     rsi
0x180001bc5  pop     rbp
0x180001bc6  retn
0x180001bc8  lea     rcx, [rdi+10h]; SRWLock
0x180001bcc  call    cs:__imp_AcquireSRWLockShared
0x180001bd3  nop     dword ptr [rax+rax+00h]
0x180001bd8  mov     rcx, [rdi+0D8h]
0x180001bdf  test    rcx, rcx
0x180001be2  jz      short loc_180001BF3
0x180001be4  mov     rax, [rcx]
0x180001be7  mov     rdx, rdi
0x180001bea  mov     rax, [rax+18h]
0x180001bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bf3  lea     rcx, [rdi+10h]; SRWLock
0x180001bf7  call    cs:__imp_ReleaseSRWLockShared
0x180001bfe  nop     dword ptr [rax+rax+00h]
0x180001c03  jmp     short loc_180001BB0
0x180001c05  xor     r15d, r15d
0x180001c08  jmp     loc_180001A4C
0x180001c0d  mov     ecx, 30h ; '0'; Size
0x180001c12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001c17  mov     rsi, rax
0x180001c1a  test    rax, rax
0x180001c1d  jnz     loc_180001D16
0x180001c23  mov     ebx, 8007000Eh
0x180001c28  jmp     loc_180001A9E
0x180001c2d  mov     rax, [rcx]
0x180001c30  mov     rax, [rax+10h]
0x180001c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c39  jmp     loc_180001B67
0x180001c3e  mov     ebx, 8007000Eh
0x180001c43  jmp     loc_180001A93
0x180001c48  xor     ebx, ebx
0x180001c4a  xor     esi, esi
0x180001c4c  mov     r13, r14
0x180001c4f  cmp     [rbp+20h], ebx
0x180001c52  jbe     loc_180001A45
0x180001c58  test    ebx, ebx
0x180001c5a  js      loc_180001A45
0x180001c60  mov     rbx, [rbp+28h]
0x180001c64  mov     ecx, 30h ; '0'; Size
0x180001c69  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001c6e  test    rax, rax
0x180001c71  jz      loc_180001D0F
0x180001c77  mov     rcx, rax; this
0x180001c7a  call    ??0CCommand@@AEAA@XZ; CCommand::CCommand(void)
0x180001c7f  mov     r14, rax
0x180001c82  test    rax, rax
0x180001c85  jz      loc_180001D0F
0x180001c8b  mov     rax, [rax]
0x180001c8e  lea     rdx, [rsi+rsi*2]
0x180001c92  lea     rdx, [rbx+rdx*8]
0x180001c96  mov     rcx, r14
0x180001c99  mov     rax, [rax+8]
0x180001c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ca2  mov     ebx, eax
0x180001ca4  test    eax, eax
0x180001ca6  jns     short loc_180001CC5
0x180001ca8  mov     rax, [r14+20h]
0x180001cac  lea     rcx, [r14+20h]
0x180001cb0  mov     rax, [rax+10h]
0x180001cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cb9  inc     esi
0x180001cbb  cmp     esi, [rbp+20h]
0x180001cbe  jb      short loc_180001C58
0x180001cc0  jmp     loc_180001A45
0x180001cc5  mov     rcx, [r13+10h]; hdpa
0x180001cc9  mov     r8, r14; p
0x180001ccc  mov     edx, 7FFFFFFFh; i
0x180001cd1  call    cs:__imp_DPA_InsertPtr
0x180001cd8  nop     dword ptr [rax+rax+00h]
0x180001cdd  add     r14, 20h ; ' '
0x180001ce1  cmp     eax, 0FFFFFFFFh
0x180001ce4  jz      short loc_180001D08
0x180001ce6  mov     rax, [r14]
0x180001ce9  xor     ebx, ebx
0x180001ceb  mov     rcx, r14
0x180001cee  mov     rax, [rax+8]
0x180001cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cf7  mov     rax, [r14]
0x180001cfa  mov     rcx, r14
0x180001cfd  mov     rax, [rax+10h]
0x180001d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d06  jmp     short loc_180001CB9
0x180001d08  mov     ebx, 8007000Eh
0x180001d0d  jmp     short loc_180001CF7
0x180001d0f  mov     ebx, 8007000Eh
0x180001d14  jmp     short loc_180001CB9
0x180001d16  lea     rcx, [rax+8]; this
0x180001d1a  mov     [rcx+8], r12
0x180001d1e  lea     rax, ??_7CStatus@@6BIHCStatus@@@; const CStatus::`vftable'{for `IHCStatus'}
0x180001d25  mov     [rcx+10h], r12
0x180001d29  mov     [rcx+18h], r12
0x180001d2d  mov     [rsi], rax
0x180001d30  lea     rax, ??_7CStatus@@6BCCommandImpl@@@; const CStatus::`vftable'{for `CCommandImpl'}
0x180001d37  mov     [rcx], rax
0x180001d3a  mov     qword ptr [rsi+28h], 1
0x180001d42  lock inc cs:?g_cLocks@@3JA; long g_cLocks
0x180001d49  lea     rdx, [rbp+30h]; struct HCCOMMAND *
0x180001d4d  call    ?_Initialize@CCommandImpl@@MEAAJPEBUHCCOMMAND@@@Z; CCommandImpl::_Initialize(HCCOMMAND const *)
0x180001d52  mov     ebx, eax
0x180001d54  test    eax, eax
0x180001d56  jns     short loc_180001DB1
0x180001d58  mov     rax, [rsi]
0x180001d5b  mov     rcx, rsi
0x180001d5e  mov     rax, [rax+10h]
0x180001d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d67  jmp     loc_180001A9E
0x180001d6c  mov     ecx, ebx; cItemGrow
0x180001d6e  call    cs:__imp_DPA_Create
0x180001d75  nop     dword ptr [rax+rax+00h]
0x180001d7a  mov     [r14+10h], rax
0x180001d7e  test    rax, rax
0x180001d81  jnz     loc_180001C48
0x180001d87  mov     rax, [r14]
0x180001d8a  mov     rcx, r14
0x180001d8d  mov     rax, [rax+10h]
0x180001d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d96  jmp     loc_180001A40
0x180001d9b  mov     rcx, [rbp+18h]; uID
0x180001d9f  lea     r8, [rsi+18h]; unsigned __int16 **
0x180001da3  mov     dl, 1; bool
0x180001da5  call    ?LoadStringHelper@@YAJPEBG_NPEAPEAG@Z; LoadStringHelper(ushort const *,bool,ushort * *)
0x180001daa  mov     ebx, eax
0x180001dac  jmp     loc_180001A8C
0x180001db1  movzx   eax, byte ptr [rbp+48h]
0x180001db5  mov     r12, rsi
0x180001db8  mov     [rsi+2Ch], eax
0x180001dbb  jmp     loc_180001A9E
0x180001dc0  cmp     [rbp+8], rsi
0x180001dc4  jz      loc_180001B09
0x180001dca  lea     rdx, [rsp+58h+arg_8]
0x180001dcf  call    ?s_CreateInstance@?$CNotificationCollection@VCNotification@@@@SAJKPEAPEAV1@@Z; CNotificationCollection<CNotification>::s_CreateInstance(ulong,CNotificationCollection<CNotification> * *)
0x180001dd4  mov     ebx, eax
0x180001dd6  test    eax, eax
0x180001dd8  js      short loc_180001E3A
0x180001dda  mov     rcx, [rbp+8]; struct HCNOTIFICATION *
0x180001dde  lea     rdx, [rsp+58h+p]; struct CNotification **
0x180001de3  mov     [rsp+58h+p], rsi
0x180001de8  call    ?s_CreateInstance@CNotification@@SAJPEBUHCNOTIFICATION@@PEAPEAV1@@Z; CNotification::s_CreateInstance(HCNOTIFICATION const *,CNotification * *)
0x180001ded  mov     ebx, eax
0x180001def  test    eax, eax
0x180001df1  js      short loc_180001E3A
0x180001df3  mov     rsi, [rsp+58h+arg_8]
0x180001df8  mov     edx, 7FFFFFFFh; i
0x180001dfd  mov     r14, [rsp+58h+p]
0x180001e02  mov     r8, r14; p
0x180001e05  mov     rcx, [rsi+10h]; hdpa
0x180001e09  call    cs:__imp_DPA_InsertPtr
0x180001e10  nop     dword ptr [rax+rax+00h]
0x180001e15  cmp     eax, 0FFFFFFFFh
0x180001e18  jz      short loc_180001E30
0x180001e1a  mov     rax, [r14]
0x180001e1d  xor     ebx, ebx
0x180001e1f  mov     rcx, r14
0x180001e22  mov     rax, [rax+8]
0x180001e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e2b  jmp     loc_180001AF6
0x180001e30  mov     ebx, 8007000Eh
0x180001e35  jmp     loc_180001AF6
0x180001e3a  mov     rsi, [rsp+58h+arg_8]
0x180001e3f  jmp     loc_180001AAD
0x180001e44  mov     rax, [rcx]
0x180001e47  mov     rax, [rax+10h]
0x180001e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e50  jmp     loc_180001B7E
0x180001e55  mov     rax, [r15]
0x180001e58  mov     rcx, r15
0x180001e5b  mov     rax, [rax+10h]
0x180001e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e64  jmp     loc_180001AB6
0x180001e69  mov     rax, [r13+0]
0x180001e6d  mov     rcx, r13
0x180001e70  mov     rax, [rax+10h]
0x180001e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e79  jmp     loc_180001ABF
0x180001e7e  mov     rax, [r12]
0x180001e82  mov     rcx, r12
0x180001e85  mov     rax, [rax+10h]
  ... truncated ...
```
