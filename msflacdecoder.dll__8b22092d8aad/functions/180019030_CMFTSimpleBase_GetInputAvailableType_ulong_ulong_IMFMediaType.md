# CMFTSimpleBase::GetInputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x180019030`
- end: `0x180019118`
- name: `?GetInputAvailableType@CMFTSimpleBase@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(CMFTSimpleBase *__hidden this, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180016b74`
- `0x180016f28`
- `0x180019030`
- `0x180056010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800190b0`
- `MFPlat!MFCreateMediaType` at `0x1800190b0`

## pseudocode

```c
__int64 __fastcall CMFTSimpleBase::GetInputAvailableType(
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
  if ( *((_DWORD *)this + 36) == 1 && !*((_QWORD *)this + 10) )
  {
    v8 = -1072861856;
    goto LABEL_19;
  }
  if ( !*((_DWORD *)this + 2) )
  {
    v8 = -2147467263;
    goto LABEL_19;
  }
  v9 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)this + 2) )
    {
      v8 = -1072875847;
      goto LABEL_19;
    }
    v11 = 2LL * i;
    if ( *(_DWORD *)(*((_QWORD *)this + 2) + 16LL * i + 8) )
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
    v12 = *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v11);
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
0x180019030  push    rbx
0x180019032  push    rbp
0x180019033  push    rsi
0x180019034  push    rdi
0x180019035  push    r14
0x180019037  sub     rsp, 30h
0x18001903b  mov     ebx, edx
0x18001903d  mov     rdi, rcx
0x180019040  mov     rdx, rcx; struct CMFTSimpleBase *
0x180019043  mov     rsi, r9
0x180019046  lea     rcx, [rsp+58h+var_38]; this
0x18001904b  mov     ebp, r8d
0x18001904e  call    ??0LockIt@CMFTSimpleBase@@QEAA@PEAV1@@Z; CMFTSimpleBase::LockIt::LockIt(CMFTSimpleBase *)
0x180019053  test    ebx, ebx
0x180019055  jz      short loc_180019061
0x180019057  mov     ebx, 0C00D36B3h
0x18001905c  jmp     loc_180019101
0x180019061  cmp     dword ptr [rdi+90h], 1
0x180019068  jnz     short loc_18001907B
0x18001906a  cmp     qword ptr [rdi+50h], 0
0x18001906f  jnz     short loc_18001907B
0x180019071  mov     ebx, 0C00D6D60h
0x180019076  jmp     loc_180019101
0x18001907b  cmp     dword ptr [rdi+8], 0
0x18001907f  jnz     short loc_180019088
0x180019081  mov     ebx, 80004001h
0x180019086  jmp     short loc_180019101
0x180019088  xor     edx, edx
0x18001908a  xor     ecx, ecx
0x18001908c  cmp     ecx, [rdi+8]
0x18001908f  jnb     short loc_1800190FC
0x180019091  mov     rax, [rdi+10h]
0x180019095  mov     r14d, ecx
0x180019098  add     r14, r14
0x18001909b  cmp     dword ptr [rax+r14*8+8], 0
0x1800190a1  jz      short loc_1800190A9
0x1800190a3  cmp     edx, ebp
0x1800190a5  jz      short loc_1800190AD
0x1800190a7  inc     edx
0x1800190a9  inc     ecx
0x1800190ab  jmp     short loc_18001908C
0x1800190ad  mov     rcx, rsi; ppMFType
0x1800190b0  call    cs:__imp_MFCreateMediaType
0x1800190b6  mov     ebx, eax
0x1800190b8  test    eax, eax
0x1800190ba  js      short loc_180019101
0x1800190bc  lfence
0x1800190bf  mov     rax, [rdi+10h]
0x1800190c3  mov     rdx, [rsi]
0x1800190c6  mov     rcx, [rax+r14*8]
0x1800190ca  mov     rax, [rcx]
0x1800190cd  mov     rax, [rax+100h]
0x1800190d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190d9  mov     ebx, eax
0x1800190db  test    eax, eax
0x1800190dd  jns     short loc_180019101
0x1800190df  mov     rcx, [rsi]
0x1800190e2  test    rcx, rcx
0x1800190e5  jz      short loc_180019101
0x1800190e7  mov     rax, [rcx]
0x1800190ea  mov     rax, [rax+10h]
0x1800190ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190f3  mov     qword ptr [rsi], 0
0x1800190fa  jmp     short loc_180019101
0x1800190fc  mov     ebx, 0C00D36B9h
0x180019101  lea     rcx, [rsp+58h+var_38]; this
0x180019106  call    ??1LockIt@CMFTSimpleBase@@QEAA@XZ; CMFTSimpleBase::LockIt::~LockIt(void)
0x18001910b  mov     eax, ebx
0x18001910d  add     rsp, 30h
0x180019111  pop     r14
0x180019113  pop     rdi
0x180019114  pop     rsi
0x180019115  pop     rbp
0x180019116  pop     rbx
0x180019117  retn
```
