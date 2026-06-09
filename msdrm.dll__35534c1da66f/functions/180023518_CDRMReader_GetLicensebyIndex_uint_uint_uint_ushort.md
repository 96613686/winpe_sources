# CDRMReader::GetLicensebyIndex(uint,uint,uint *,ushort * *)

- ea: `0x180023518`
- end: `0x180023983`
- name: `?GetLicensebyIndex@CDRMReader@@QEAAJIIPEAIPEAPEAG@Z`
- size: `1131`
- prototype: `__int64 __usercall@<rax>(CDRMReader *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int *@<r9>, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001bba0`

## callees

- `0x180001244`
- `0x180004654`
- `0x180015438`
- `0x180022c8c`
- `0x180023400`
- `0x18002348c`
- `0x180023518`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023949`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023949`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023549`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023549`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CDRMReader::GetLicensebyIndex(
        CDRMReader *this,
        unsigned int a2,
        __int16 a3,
        unsigned int *a4,
        unsigned __int16 **a5)
{
  __int64 v7; // rdi
  signed int LicenseCache; // ebx
  int v10; // r15d
  unsigned int v11; // edx
  __int64 v12; // r12
  __int64 v13; // r9
  int v14; // r14d
  unsigned int v15; // ecx
  __int64 v16; // r14
  __int64 v17; // r15
  _WORD *v18; // rax
  __int64 v19; // rcx
  unsigned int v20; // esi
  __int64 v21; // r8
  unsigned __int64 v22; // rcx
  signed __int64 v23; // rdi
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // rcx
  unsigned __int16 *v27; // rax
  unsigned int v28; // r8d
  int v29; // ecx
  __int64 v31; // r14
  _WORD *v32; // rax
  __int64 v33; // rcx
  unsigned int v34; // esi
  __int64 v35; // r8
  unsigned __int64 v36; // rcx
  signed __int64 v37; // rdi
  unsigned __int64 v38; // rcx
  unsigned __int64 v39; // rax
  unsigned __int64 v40; // rcx
  unsigned __int16 *v41; // rax
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+70h] [rbp+8h]

  v7 = a2;
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( !a4 || !a5 )
    goto LABEL_86;
  if ( !(_DWORD)v7 )
  {
    if ( *((_DWORD *)this + 78) )
    {
      if ( (a3 & 0x60) != 0 )
      {
        LicenseCache = CDRMReader::DeleteEULCache(this);
        if ( LicenseCache < 0 )
          goto LABEL_87;
        *((_DWORD *)this + 78) = 0;
      }
    }
    else if ( *((_DWORD *)this + 79) && (a3 & 0xC00) != 0 )
    {
      LicenseCache = CDRMReader::DeleteRevocationListCache(this);
      if ( LicenseCache < 0 )
        goto LABEL_87;
      *((_DWORD *)this + 79) = 0;
    }
  }
  v10 = a3 & 0x20;
  if ( (a3 & 0x20) == 0 && (a3 & 0x40) == 0 )
  {
    if ( (a3 & 0x400) != 0 || (a3 & 0x800) != 0 )
    {
      if ( !*((_QWORD *)this + 35) )
      {
        LicenseCache = CDRMReader::CreateLicenseCache(this, a3);
        if ( LicenseCache < 0 )
          goto LABEL_87;
      }
      v11 = *((_DWORD *)this + 72);
      if ( (unsigned int)v7 >= v11 )
        goto LABEL_28;
      v12 = *((_QWORD *)this + 35);
      if ( !v12 || !*(_QWORD *)(v12 + 8 * v7) )
        goto LABEL_28;
      if ( (a3 & 0x400) == 0 )
        v12 = *((_QWORD *)this + 37);
      v13 = *((_QWORD *)this + 38);
      v14 = a3 & 0x1000;
LABEL_52:
      v28 = 0;
      if ( (_DWORD)v7 )
      {
        while ( 1 )
        {
          v29 = *(_DWORD *)(v13 + 4LL * v28);
          if ( v29 == -1 )
            break;
          if ( v14 )
          {
            if ( !v29 )
              break;
          }
          else if ( v29 )
          {
            break;
          }
LABEL_59:
          if ( (unsigned int)v7 >= v11 )
            goto LABEL_28;
          if ( ++v28 >= (unsigned int)v7 )
          {
LABEL_63:
            while ( !(v14 ? *(_DWORD *)(v13 + 4 * v7) == 1 : *(_DWORD *)(v13 + 4 * v7) == 0) )
            {
              v7 = (unsigned int)(v7 + 1);
              if ( (unsigned int)v7 >= v11 )
                goto LABEL_28;
            }
            _mm_lfence();
            v31 = (unsigned int)v7;
            v32 = *(_WORD **)(v12 + 8 * v7);
            v33 = -1;
            do
              ++v33;
            while ( v32[v33] );
            try
            {
              v34 = v33 + 1;
              if ( !v32 )
              {
                LicenseCache = -2147024809;
                goto LABEL_97;
              }
              v35 = 0x7FFFFFFF;
              do
              {
                if ( !*v32 )
                  break;
                ++v32;
                --v35;
              }
              while ( v35 );
              LicenseCache = v35 == 0 ? 0x80070057 : 0;
              v36 = (0x7FFFFFFF - v35) & -(__int64)(v35 != 0);
              if ( !v35 )
                goto LABEL_97;
              v37 = v36 + 1;
              if ( v36 + 1 < v36 )
                SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v36);
              v38 = HIDWORD(v37);
              if ( v37 < 0 )
                SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v38);
              v39 = 2LL * (unsigned int)v37;
              v40 = v38 << 33;
              if ( v40 + v39 < v39 )
                SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v40);
              if ( v40 + v39 )
              {
                v41 = (unsigned __int16 *)operator new(saturated_mul(v37, 2u));
                *a5 = v41;
                if ( !v41 )
                {
                  LicenseCache = -2147024882;
                  goto LABEL_97;
                }
                LicenseCache = StringCchCopyW(v41, v37, *(unsigned __int16 **)(v12 + 8 * v31));
                if ( LicenseCache < 0 )
                  goto LABEL_97;
              }
              *a4 = v34;
            }
            catch ( SafeIntException )
            {
              LicenseCache = -2147467259;
              goto LABEL_87;
            }
LABEL_97:
            goto LABEL_87;
          }
        }
        v7 = (unsigned int)(v7 + 1);
        goto LABEL_59;
      }
      if ( v11 )
        goto LABEL_63;
LABEL_28:
      LicenseCache = -2147168461;
      goto LABEL_87;
    }
LABEL_86:
    LicenseCache = -2147024809;
    goto LABEL_87;
  }
  if ( !*((_QWORD *)this + 31) )
  {
    LicenseCache = CDRMReader::CreateLicenseCache(this, a3);
    if ( LicenseCache < 0 )
      goto LABEL_87;
  }
  v14 = a3 & 0x1000;
  v11 = *((_DWORD *)this + 64);
  if ( v14 )
  {
    if ( (unsigned int)v7 >= v11 )
      goto LABEL_28;
    goto LABEL_47;
  }
  v15 = *((_DWORD *)this + 60);
  if ( (unsigned int)v7 >= v15 + v11 )
    goto LABEL_28;
  if ( (unsigned int)v7 >= v15 )
  {
    v7 = (unsigned int)v7 - v15;
LABEL_47:
    v12 = *((_QWORD *)this + 31);
    if ( !v12 || !*(_QWORD *)(v12 + 8 * v7) )
      goto LABEL_28;
    if ( !v10 )
      v12 = *((_QWORD *)this + 33);
    v13 = *((_QWORD *)this + 34);
    goto LABEL_52;
  }
  v16 = v7;
  v17 = *(_QWORD *)((char *)this + (-(__int64)(v10 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 232);
  v18 = *(_WORD **)(v17 + 8 * v7);
  v19 = -1;
  do
    ++v19;
  while ( v18[v19] );
  v20 = v19 + 1;
  if ( !v18 )
  {
    LicenseCache = -2147024809;
    goto LABEL_87;
  }
  v21 = 0x7FFFFFFF;
  do
  {
    if ( !*v18 )
      break;
    ++v18;
    --v21;
  }
  while ( v21 );
  LicenseCache = v21 == 0 ? 0x80070057 : 0;
  v22 = (0x7FFFFFFF - v21) & -(__int64)(v21 != 0);
  if ( v21 )
  {
    v23 = v22 + 1;
    if ( v22 + 1 < v22 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v22);
    v24 = HIDWORD(v23);
    if ( v23 < 0 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v24);
    v25 = 2LL * (unsigned int)v23;
    v26 = v24 << 33;
    if ( v26 + v25 < v25 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v26);
    if ( v26 + v25 )
    {
      v27 = (unsigned __int16 *)operator new(saturated_mul(v23, 2u));
      *a5 = v27;
      if ( !v27 )
      {
        LicenseCache = -2147024882;
        goto LABEL_87;
      }
      LicenseCache = StringCchCopyW(v27, v23, *(unsigned __int16 **)(v17 + 8 * v16));
      if ( LicenseCache < 0 )
        goto LABEL_87;
    }
    *a4 = v20;
  }
LABEL_87:
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)LicenseCache;
}

```

## disassembly

```asm
0x180023518  mov     [rsp+arg_18], r9
0x18002351d  push    rbx
0x18002351e  push    rsi
0x18002351f  push    rdi
0x180023520  push    r12
0x180023522  push    r13
0x180023524  push    r14
0x180023526  push    r15
0x180023528  sub     rsp, 30h
0x18002352c  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x180023535  mov     r12, r9
0x180023538  mov     r14d, r8d
0x18002353b  mov     edi, edx
0x18002353d  mov     rsi, rcx
0x180023540  add     rcx, 58h ; 'X'; lpCriticalSection
0x180023544  mov     [rsp+68h+lpCriticalSection], rcx
0x180023549  call    cs:__imp_EnterCriticalSection
0x18002354f  nop
0x180023550  xor     r11d, r11d
0x180023553  test    r12, r12
0x180023556  jz      loc_18002393F
0x18002355c  mov     r13, [rsp+68h+arg_20]
0x180023564  test    r13, r13
0x180023567  jz      loc_18002393F
0x18002356d  test    edi, edi
0x18002356f  jnz     short loc_1800235CC
0x180023571  cmp     [rsi+138h], r11d
0x180023578  jz      short loc_18002359E
0x18002357a  test    r14b, 60h
0x18002357e  jz      short loc_1800235CC
0x180023580  mov     rcx, rsi; this
0x180023583  call    ?DeleteEULCache@CDRMReader@@QEAAJXZ; CDRMReader::DeleteEULCache(void)
0x180023588  mov     ebx, eax
0x18002358a  xor     r11d, r11d
0x18002358d  test    eax, eax
0x18002358f  js      loc_180023944
0x180023595  mov     [rsi+138h], r11d
0x18002359c  jmp     short loc_1800235CC
0x18002359e  cmp     [rsi+13Ch], r11d
0x1800235a5  jz      short loc_1800235CC
0x1800235a7  test    r14d, 0C00h
0x1800235ae  jz      short loc_1800235CC
0x1800235b0  mov     rcx, rsi; this
0x1800235b3  call    ?DeleteRevocationListCache@CDRMReader@@QEAAJXZ; CDRMReader::DeleteRevocationListCache(void)
0x1800235b8  mov     ebx, eax
0x1800235ba  xor     r11d, r11d
0x1800235bd  test    eax, eax
0x1800235bf  js      loc_180023944
0x1800235c5  mov     [rsi+13Ch], r11d
0x1800235cc  mov     r15d, r14d
0x1800235cf  and     r15d, 20h
0x1800235d3  jnz     short loc_18002364E
0x1800235d5  test    r14b, 40h
0x1800235d9  jnz     short loc_18002364E
0x1800235db  mov     r15d, r14d
0x1800235de  and     r15d, 400h
0x1800235e5  jnz     short loc_1800235F2
0x1800235e7  bt      r14d, 0Bh
0x1800235ec  jnb     loc_18002393F
0x1800235f2  cmp     [rsi+118h], r11
0x1800235f9  jnz     short loc_180023613
0x1800235fb  mov     edx, r14d; unsigned int
0x1800235fe  mov     rcx, rsi; this
0x180023601  call    ?CreateLicenseCache@CDRMReader@@AEAAJIH@Z; CDRMReader::CreateLicenseCache(uint,int)
0x180023606  mov     ebx, eax
0x180023608  xor     r11d, r11d
0x18002360b  test    eax, eax
0x18002360d  js      loc_180023944
0x180023613  mov     edx, [rsi+120h]
0x180023619  cmp     edi, edx
0x18002361b  jnb     short loc_18002368F
0x18002361d  mov     r12, [rsi+118h]
0x180023624  test    r12, r12
0x180023627  jz      short loc_18002368F
0x180023629  cmp     [r12+rdi*8], r11
0x18002362d  jz      short loc_18002368F
0x18002362f  test    r15d, r15d
0x180023632  jnz     short loc_18002363B
0x180023634  mov     r12, [rsi+128h]
0x18002363b  mov     r9, [rsi+130h]
0x180023642  and     r14d, 1000h
0x180023649  jmp     loc_1800237EC
0x18002364e  cmp     [rsi+0F8h], r11
0x180023655  jnz     short loc_18002366F
0x180023657  mov     edx, r14d; unsigned int
0x18002365a  mov     rcx, rsi; this
0x18002365d  call    ?CreateLicenseCache@CDRMReader@@AEAAJIH@Z; CDRMReader::CreateLicenseCache(uint,int)
0x180023662  mov     ebx, eax
0x180023664  xor     r11d, r11d
0x180023667  test    eax, eax
0x180023669  js      loc_180023944
0x18002366f  and     r14d, 1000h
0x180023676  mov     edx, [rsi+100h]
0x18002367c  jnz     loc_1800237B7
0x180023682  mov     ecx, [rsi+0F0h]
0x180023688  lea     eax, [rcx+rdx]
0x18002368b  cmp     edi, eax
0x18002368d  jb      short loc_180023699
0x18002368f  mov     ebx, 8004CF33h
0x180023694  jmp     loc_180023944
0x180023699  cmp     edi, ecx
0x18002369b  jnb     loc_1800237B3
0x1800236a1  neg     r15d
0x1800236a4  sbb     rax, rax
0x1800236a7  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800236ab  mov     r14, rdi
0x1800236ae  mov     r15, [rax+rsi+0E8h]
0x1800236b6  mov     rax, [r15+rdi*8]
0x1800236ba  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800236be  mov     rcx, r10
0x1800236c1  inc     rcx
0x1800236c4  cmp     [rax+rcx*2], r11w
0x1800236c9  jnz     short loc_1800236C1
0x1800236cb  lea     esi, [rcx+1]
0x1800236ce  test    rax, rax
0x1800236d1  jz      loc_1800237A0
0x1800236d7  mov     edx, 7FFFFFFFh
0x1800236dc  mov     r8d, edx
0x1800236df  cmp     [rax], r11w
0x1800236e3  jz      short loc_1800236EF
0x1800236e5  add     rax, 2
0x1800236e9  sub     r8, 1
0x1800236ed  jnz     short loc_1800236DF
0x1800236ef  mov     rax, r8
0x1800236f2  neg     rax
0x1800236f5  sbb     ecx, ecx
0x1800236f7  not     ecx
0x1800236f9  mov     ebx, 80070057h
0x1800236fe  and     ebx, ecx
0x180023700  mov     rax, r8
0x180023703  sub     rdx, r8
0x180023706  neg     rax
0x180023709  sbb     rcx, rcx
0x18002370c  and     rcx, rdx
0x18002370f  test    r8, r8
0x180023712  jz      loc_1800237A5
0x180023718  lea     rdi, [rcx+1]
0x18002371c  cmp     rdi, rcx
0x18002371f  jb      loc_180023961
0x180023725  mov     rcx, rdi
0x180023728  shr     rcx, 20h
0x18002372c  mov     rax, rcx
0x18002372f  shr     rax, 1Fh
0x180023733  test    eax, eax
0x180023735  jnz     loc_180023967
0x18002373b  mov     eax, edi
0x18002373d  add     rax, rax
0x180023740  shl     rcx, 21h
0x180023744  lea     rdx, [rcx+rax]
0x180023748  cmp     rdx, rax
0x18002374b  jb      loc_18002396C
0x180023751  test    rdx, rdx
0x180023754  jz      short loc_180023797
0x180023756  mov     eax, 2
0x18002375b  mul     rdi
0x18002375e  cmovb   rax, r10
0x180023762  mov     rcx, rax; Size
0x180023765  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002376a  mov     [r13+0], rax
0x18002376e  test    rax, rax
0x180023771  jnz     short loc_18002377D
0x180023773  mov     ebx, 8007000Eh
0x180023778  jmp     loc_180023944
0x18002377d  mov     r8, [r15+r14*8]; unsigned __int16 *
0x180023781  mov     rdx, rdi; unsigned __int64
0x180023784  mov     rcx, rax; unsigned __int16 *
0x180023787  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002378c  mov     ebx, eax
0x18002378e  test    eax, eax
0x180023790  jns     short loc_180023797
0x180023792  jmp     loc_180023944
0x180023797  mov     [r12], esi
0x18002379b  jmp     loc_180023944
0x1800237a0  mov     ebx, 80070057h
0x1800237a5  jmp     loc_180023944
0x1800237aa  mov     ebx, [rsp+68h+arg_8]
0x1800237ae  jmp     loc_180023944
0x1800237b3  sub     edi, ecx
0x1800237b5  jmp     short loc_1800237BF
0x1800237b7  cmp     edi, edx
0x1800237b9  jnb     loc_18002368F
0x1800237bf  mov     r12, [rsi+0F8h]
0x1800237c6  test    r12, r12
0x1800237c9  jz      loc_18002368F
0x1800237cf  cmp     [r12+rdi*8], r11
0x1800237d3  jz      loc_18002368F
0x1800237d9  test    r15d, r15d
0x1800237dc  jnz     short loc_1800237E5
0x1800237de  mov     r12, [rsi+108h]
0x1800237e5  mov     r9, [rsi+110h]
0x1800237ec  mov     r8d, r11d
0x1800237ef  test    edi, edi
0x1800237f1  jz      short loc_180023826
0x1800237f3  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800237f7  mov     eax, r8d
0x1800237fa  mov     ecx, [r9+rax*4]
0x1800237fe  cmp     ecx, r10d
0x180023801  jz      short loc_180023812
0x180023803  test    r14d, r14d
0x180023806  jz      short loc_18002380E
0x180023808  test    ecx, ecx
0x18002380a  jnz     short loc_180023814
0x18002380c  jmp     short loc_180023812
0x18002380e  test    ecx, ecx
0x180023810  jz      short loc_180023814
0x180023812  inc     edi
0x180023814  cmp     edi, edx
0x180023816  jnb     loc_18002368F
0x18002381c  inc     r8d
0x18002381f  cmp     r8d, edi
0x180023822  jb      short loc_1800237F7
0x180023824  jmp     short loc_180023832
0x180023826  cmp     edi, edx
0x180023828  jnb     loc_18002368F
0x18002382e  or      r10, 0FFFFFFFFFFFFFFFFh
0x180023832  test    r14d, r14d
0x180023835  jz      short loc_18002383E
0x180023837  cmp     dword ptr [r9+rdi*4], 1
0x18002383c  jmp     short loc_180023842
0x18002383e  cmp     [r9+rdi*4], r11d
0x180023842  jz      short loc_18002384F
0x180023844  inc     edi
0x180023846  cmp     edi, edx
0x180023848  jb      short loc_180023832
0x18002384a  jmp     loc_18002368F
0x18002384f  lfence
0x180023852  mov     r14d, edi
0x180023855  mov     rax, [r12+rdi*8]
0x180023859  mov     rcx, r10
0x18002385c  inc     rcx
0x18002385f  cmp     [rax+rcx*2], r11w
0x180023864  jnz     short loc_18002385C
0x180023866  lea     esi, [rcx+1]
0x180023869  test    rax, rax
0x18002386c  jz      loc_180023938
0x180023872  mov     edx, 7FFFFFFFh
0x180023877  mov     r8d, edx
0x18002387a  cmp     [rax], r11w
0x18002387e  jz      short loc_18002388A
0x180023880  add     rax, 2
0x180023884  sub     r8, 1
0x180023888  jnz     short loc_18002387A
0x18002388a  mov     rax, r8
0x18002388d  neg     rax
0x180023890  sbb     ecx, ecx
0x180023892  not     ecx
0x180023894  mov     ebx, 80070057h
0x180023899  and     ebx, ecx
0x18002389b  mov     rax, r8
0x18002389e  sub     rdx, r8
0x1800238a1  neg     rax
0x1800238a4  sbb     rcx, rcx
0x1800238a7  and     rcx, rdx
0x1800238aa  test    r8, r8
0x1800238ad  jz      loc_18002393D
0x1800238b3  lea     rdi, [rcx+1]
0x1800238b7  cmp     rdi, rcx
0x1800238ba  jb      loc_180023972
0x1800238c0  mov     rcx, rdi
0x1800238c3  shr     rcx, 20h
0x1800238c7  mov     rax, rcx
0x1800238ca  shr     rax, 1Fh
0x1800238ce  test    eax, eax
0x1800238d0  jnz     loc_180023977
0x1800238d6  mov     eax, edi
0x1800238d8  add     rax, rax
0x1800238db  shl     rcx, 21h
0x1800238df  lea     rdx, [rcx+rax]
0x1800238e3  cmp     rdx, rax
0x1800238e6  jb      loc_18002397C
0x1800238ec  test    rdx, rdx
0x1800238ef  jz      short loc_18002392C
0x1800238f1  mov     eax, 2
0x1800238f6  mul     rdi
0x1800238f9  cmovb   rax, r10
0x1800238fd  mov     rcx, rax; Size
0x180023900  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023905  mov     [r13+0], rax
0x180023909  test    rax, rax
0x18002390c  jnz     short loc_180023915
0x18002390e  mov     ebx, 8007000Eh
0x180023913  jmp     short loc_180023944
0x180023915  mov     r8, [r12+r14*8]; unsigned __int16 *
0x180023919  mov     rdx, rdi; unsigned __int64
0x18002391c  mov     rcx, rax; unsigned __int16 *
0x18002391f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023924  mov     ebx, eax
0x180023926  test    eax, eax
0x180023928  jns     short loc_18002392C
0x18002392a  jmp     short loc_180023944
0x18002392c  mov     rax, [rsp+68h+arg_18]
0x180023934  mov     [rax], esi
0x180023936  jmp     short loc_180023944
0x180023938  mov     ebx, 80070057h
0x18002393d  jmp     short loc_180023944
0x18002393f  mov     ebx, 80070057h
0x180023944  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x180023949  call    cs:__imp_LeaveCriticalSection
0x18002394f  mov     eax, ebx
0x180023951  add     rsp, 30h
  ... truncated ...
```
