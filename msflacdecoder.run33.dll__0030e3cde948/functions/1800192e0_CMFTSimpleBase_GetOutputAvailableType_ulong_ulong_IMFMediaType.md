# CMFTSimpleBase::GetOutputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x1800192e0`
- end: `0x1800193c8`
- name: `?GetOutputAvailableType@CMFTSimpleBase@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(CMFTSimpleBase *__hidden this, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180016b74`
- `0x180016f28`
- `0x1800192e0`
- `0x180056010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180019360`
- `MFPlat!MFCreateMediaType` at `0x180019360`

## pseudocode

```c
__int64 __fastcall CMFTSimpleBase::GetOutputAvailableType(
        CMFTSimpleBase *this,
        int a2,
        int a3,
        struct IMFMediaType **a4)
{
  HRESULT v8; // ebx
  int v9; // edx
  unsigned int i; // ecx
  __int64 v11; // r14
  __int64 v12; // rcx
  _BYTE v14[56]; // [rsp+20h] [rbp-38h] BYREF

  CMFTSimpleBase::LockIt::LockIt((CMFTSimpleBase::LockIt *)v14, this);
  if ( a2 )
  {
    v8 = -1072875853;
    goto LABEL_19;
  }
  if ( !*((_DWORD *)this + 36) && !*((_QWORD *)this + 5) )
  {
    v8 = -1072861856;
    goto LABEL_19;
  }
  if ( !*((_DWORD *)this + 6) )
  {
    v8 = -2147467263;
    goto LABEL_19;
  }
  v9 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)this + 6) )
    {
      v8 = -1072875847;
      goto LABEL_19;
    }
    v11 = 2LL * i;
    if ( *(_DWORD *)(*((_QWORD *)this + 4) + 16LL * i + 8) )
      break;
LABEL_13:
    ;
  }
  if ( v9 != a3 )
  {
    ++v9;
    goto LABEL_13;
  }
  v8 = MFCreateMediaType(a4);
  if ( v8 >= 0 )
  {
    _mm_lfence();
    v12 = *(_QWORD *)(*((_QWORD *)this + 4) + 8 * v11);
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 256LL))(v12, *a4);
    if ( v8 < 0 )
    {
      if ( *a4 )
      {
        ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
        *a4 = 0;
      }
    }
  }
LABEL_19:
  CMFTSimpleBase::LockIt::~LockIt((CMFTSimpleBase::LockIt *)v14);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800192e0  push    rbx
0x1800192e2  push    rbp
0x1800192e3  push    rsi
0x1800192e4  push    rdi
0x1800192e5  push    r14
0x1800192e7  sub     rsp, 30h
0x1800192eb  mov     ebx, edx
0x1800192ed  mov     rdi, rcx
0x1800192f0  mov     rdx, rcx; struct CMFTSimpleBase *
0x1800192f3  mov     rsi, r9
0x1800192f6  lea     rcx, [rsp+58h+var_38]; this
0x1800192fb  mov     ebp, r8d
0x1800192fe  call    ??0LockIt@CMFTSimpleBase@@QEAA@PEAV1@@Z; CMFTSimpleBase::LockIt::LockIt(CMFTSimpleBase *)
0x180019303  test    ebx, ebx
0x180019305  jz      short loc_180019311
0x180019307  mov     ebx, 0C00D36B3h
0x18001930c  jmp     loc_1800193B1
0x180019311  cmp     dword ptr [rdi+90h], 0
0x180019318  jnz     short loc_18001932B
0x18001931a  cmp     qword ptr [rdi+28h], 0
0x18001931f  jnz     short loc_18001932B
0x180019321  mov     ebx, 0C00D6D60h
0x180019326  jmp     loc_1800193B1
0x18001932b  cmp     dword ptr [rdi+18h], 0
0x18001932f  jnz     short loc_180019338
0x180019331  mov     ebx, 80004001h
0x180019336  jmp     short loc_1800193B1
0x180019338  xor     edx, edx
0x18001933a  xor     ecx, ecx
0x18001933c  cmp     ecx, [rdi+18h]
0x18001933f  jnb     short loc_1800193AC
0x180019341  mov     rax, [rdi+20h]
0x180019345  mov     r14d, ecx
0x180019348  add     r14, r14
0x18001934b  cmp     dword ptr [rax+r14*8+8], 0
0x180019351  jz      short loc_180019359
0x180019353  cmp     edx, ebp
0x180019355  jz      short loc_18001935D
0x180019357  inc     edx
0x180019359  inc     ecx
0x18001935b  jmp     short loc_18001933C
0x18001935d  mov     rcx, rsi; ppMFType
0x180019360  call    cs:__imp_MFCreateMediaType
0x180019366  mov     ebx, eax
0x180019368  test    eax, eax
0x18001936a  js      short loc_1800193B1
0x18001936c  lfence
0x18001936f  mov     rax, [rdi+20h]
0x180019373  mov     rdx, [rsi]
0x180019376  mov     rcx, [rax+r14*8]
0x18001937a  mov     rax, [rcx]
0x18001937d  mov     rax, [rax+100h]
0x180019384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019389  mov     ebx, eax
0x18001938b  test    eax, eax
0x18001938d  jns     short loc_1800193B1
0x18001938f  mov     rcx, [rsi]
0x180019392  test    rcx, rcx
0x180019395  jz      short loc_1800193B1
0x180019397  mov     rax, [rcx]
0x18001939a  mov     rax, [rax+10h]
0x18001939e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193a3  mov     qword ptr [rsi], 0
0x1800193aa  jmp     short loc_1800193B1
0x1800193ac  mov     ebx, 0C00D36B9h
0x1800193b1  lea     rcx, [rsp+58h+var_38]; this
0x1800193b6  call    ??1LockIt@CMFTSimpleBase@@QEAA@XZ; CMFTSimpleBase::LockIt::~LockIt(void)
0x1800193bb  mov     eax, ebx
0x1800193bd  add     rsp, 30h
0x1800193c1  pop     r14
0x1800193c3  pop     rdi
0x1800193c4  pop     rsi
0x1800193c5  pop     rbp
0x1800193c6  pop     rbx
0x1800193c7  retn
```
