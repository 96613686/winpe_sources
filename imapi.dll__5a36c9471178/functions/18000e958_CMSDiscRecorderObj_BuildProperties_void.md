# CMSDiscRecorderObj::BuildProperties(void)

- ea: `0x18000e958`
- end: `0x18000ec7c`
- name: `?BuildProperties@CMSDiscRecorderObj@@AEAAJXZ`
- size: `804`
- prototype: `__int64 __fastcall(CMSDiscRecorderObj *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18000f850`

## callees

- `0x180001144`
- `0x18000115c`
- `0x180007bac`
- `0x180007bd4`
- `0x18000e958`
- `0x180010d40`
- `0x180010db8`
- `0x1800133d8`
- `0x180018500`
- `0x180019010`

## string_xrefs

- `0x18000eb94`: `MaxWriteSpeed`
- `0x18000eb88`: `WriteSpeed`

## pseudocode

```c
__int64 __fastcall CMSDiscRecorderObj::BuildProperties(CMSDiscRecorderObj *this)
{
  int v1; // r13d
  CIPropertyStorageWrapper *v3; // rax
  CIPropertyStorageWrapper *v4; // rcx
  int v6; // r12d
  __int16 v7; // r15
  int v8; // eax
  __int64 v9; // rcx
  int v10; // edi
  void *v11; // rbx
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+34h] [rbp-CCh] BYREF
  int v14; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+3Ch] [rbp-C4h] BYREF
  int v16[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+60h] [rbp-A0h]
  const wchar_t *v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+70h] [rbp-90h]
  const wchar_t *v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+80h] [rbp-80h]
  const wchar_t *v24; // [rsp+88h] [rbp-78h]
  int v25; // [rsp+90h] [rbp-70h]
  const wchar_t *v26; // [rsp+98h] [rbp-68h]
  __int16 v27; // [rsp+A0h] [rbp-60h] BYREF
  int v28; // [rsp+A8h] [rbp-58h]
  __int16 v29; // [rsp+B8h] [rbp-48h]
  int v30; // [rsp+C0h] [rbp-40h]
  __int16 v31; // [rsp+D0h] [rbp-30h]
  int v32; // [rsp+D8h] [rbp-28h]
  __int16 v33; // [rsp+E8h] [rbp-18h]
  __int16 v34; // [rsp+F0h] [rbp-10h]
  __int16 v35; // [rsp+100h] [rbp+0h]
  int v36; // [rsp+108h] [rbp+8h]

  v1 = 0;
  v14 = 0;
  v12 = 0;
  v13 = 0;
  v15 = 0;
  v16[0] = 0;
  v3 = (CIPropertyStorageWrapper *)operator new(0x30u);
  if ( v3 )
    v4 = CIPropertyStorageWrapper::CIPropertyStorageWrapper(v3);
  else
    v4 = 0;
  *((_QWORD *)this + 17) = v4;
  if ( v4 )
  {
    (*(void (__fastcall **)(CIPropertyStorageWrapper *))(*(_QWORD *)v4 + 8LL))(v4);
    if ( (int)WriterGetProperty((char *)this + 80, 1, &v14) >= 0 )
    {
      v6 = v14;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 53, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids);
      v6 = 1;
    }
    if ( (int)WriterGetProperty((char *)this + 80, 2, &v12) < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 54, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids);
      v6 = 1;
      v12 = 1;
    }
    if ( (int)WriterGetProperty((char *)this + 80, 3, &v13) < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 55, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids);
      v13 = 150;
    }
    if ( (int)WriterGetProperty((char *)this + 80, 4, &v15) >= 0 )
    {
      v1 = v15;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 56, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids);
    }
    v7 = -1;
    if ( (int)WriterGetProperty((char *)this + 80, 5, v16) >= 0 )
    {
      v8 = v16[0];
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 57, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids);
      v8 = -1;
    }
    v28 = v6;
    v17 = 0;
    v18 = L"WriteSpeed";
    v20 = L"MaxWriteSpeed";
    v30 = v12;
    v22 = L"AudioGapSize";
    v32 = v13;
    v24 = L"BufferUnderrunFreeCapable";
    v33 = 11;
    v27 = 3;
    v19 = 0;
    v29 = 3;
    v21 = 0;
    v31 = 3;
    v23 = 0;
    if ( !v1 )
      v7 = 0;
    v35 = 3;
    v26 = L"EnableBufferUnderrunFree";
    v9 = *((_QWORD *)this + 17);
    v36 = v8;
    v34 = v7;
    v25 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, int *, __int16 *, int))(*(_QWORD *)v9 + 32LL))(
            v9,
            5,
            &v17,
            &v27,
            2);
    if ( v10 < 0 )
    {
      v11 = (void *)*((_QWORD *)this + 17);
      if ( v11 )
      {
        CIPropertyStorageWrapper::~CIPropertyStorageWrapper(*((CIPropertyStorageWrapper **)this + 17));
        operator delete(v11);
      }
      *((_QWORD *)this + 17) = 0;
    }
    return (unsigned int)v10;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 52, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids, 2147942414LL);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000e958  push    rbp
0x18000e95a  push    rbx
0x18000e95b  push    rsi
0x18000e95c  push    rdi
0x18000e95d  push    r12
0x18000e95f  push    r13
0x18000e961  push    r14
0x18000e963  push    r15
0x18000e965  lea     rbp, [rsp-38h]
0x18000e96a  sub     rsp, 138h
0x18000e971  mov     rax, cs:__security_cookie
0x18000e978  xor     rax, rsp
0x18000e97b  mov     [rbp+70h+var_50], rax
0x18000e97f  xor     r13d, r13d
0x18000e982  mov     r14, rcx
0x18000e985  mov     [rsp+170h+var_138], r13d
0x18000e98a  mov     [rsp+170h+var_140], r13d
0x18000e98f  mov     [rsp+170h+var_13C], r13d
0x18000e994  lea     ecx, [r13+30h]; Size
0x18000e998  mov     [rsp+170h+var_134], r13d
0x18000e99d  mov     [rsp+170h+var_130], r13d
0x18000e9a2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e9a7  test    rax, rax
0x18000e9aa  jz      short loc_18000E9B9
0x18000e9ac  mov     rcx, rax; this
0x18000e9af  call    ??0CIPropertyStorageWrapper@@QEAA@XZ; CIPropertyStorageWrapper::CIPropertyStorageWrapper(void)
0x18000e9b4  mov     rcx, rax
0x18000e9b7  jmp     short loc_18000E9BC
0x18000e9b9  mov     rcx, r13
0x18000e9bc  mov     [r14+88h], rcx
0x18000e9c3  test    rcx, rcx
0x18000e9c6  jnz     short loc_18000EA08
0x18000e9c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9cf  lea     rdi, WPP_GLOBAL_Control
0x18000e9d6  cmp     rcx, rdi
0x18000e9d9  jz      short loc_18000E9FE
0x18000e9db  mov     ebx, 1
0x18000e9e0  test    [rcx+44h], bl
0x18000e9e3  jz      short loc_18000E9FE
0x18000e9e5  mov     rcx, [rcx+38h]
0x18000e9e9  lea     edx, [rbx+33h]
0x18000e9ec  mov     r9d, 8007000Eh
0x18000e9f2  lea     r8, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids
0x18000e9f9  call    WPP_SF_d
0x18000e9fe  mov     eax, 8007000Eh
0x18000ea03  jmp     loc_18000EC5C
0x18000ea08  mov     rax, [rcx]
0x18000ea0b  mov     rax, [rax+8]
0x18000ea0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea14  lea     r15, [r14+50h]
0x18000ea18  mov     ebx, 1
0x18000ea1d  mov     edx, ebx
0x18000ea1f  lea     r8, [rsp+170h+var_138]
0x18000ea24  mov     rcx, r15
0x18000ea27  call    WriterGetProperty
0x18000ea2c  lea     rdi, WPP_GLOBAL_Control
0x18000ea33  lea     rsi, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids
0x18000ea3a  test    eax, eax
0x18000ea3c  jns     short loc_18000EA63
0x18000ea3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea45  cmp     rcx, rdi
0x18000ea48  jz      short loc_18000EA5E
0x18000ea4a  test    [rcx+44h], bl
0x18000ea4d  jz      short loc_18000EA5E
0x18000ea4f  mov     rcx, [rcx+38h]
0x18000ea53  lea     edx, [rbx+34h]
0x18000ea56  mov     r8, rsi
0x18000ea59  call    WPP_SF_
0x18000ea5e  mov     r12d, ebx
0x18000ea61  jmp     short loc_18000EA68
0x18000ea63  mov     r12d, [rsp+170h+var_138]
0x18000ea68  lea     r8, [rsp+170h+var_140]
0x18000ea6d  mov     edx, 2
0x18000ea72  mov     rcx, r15
0x18000ea75  call    WriterGetProperty
0x18000ea7a  test    eax, eax
0x18000ea7c  jns     short loc_18000EAA9
0x18000ea7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea85  cmp     rcx, rdi
0x18000ea88  jz      short loc_18000EAA0
0x18000ea8a  test    [rcx+44h], bl
0x18000ea8d  jz      short loc_18000EAA0
0x18000ea8f  mov     rcx, [rcx+38h]
0x18000ea93  mov     edx, 36h ; '6'
0x18000ea98  mov     r8, rsi
0x18000ea9b  call    WPP_SF_
0x18000eaa0  mov     r12d, ebx
0x18000eaa3  mov     [rsp+170h+var_140], ebx
0x18000eaa7  jmp     short loc_18000EAB1
0x18000eaa9  mov     eax, [rsp+170h+var_140]
0x18000eaad  mov     [rsp+170h+var_140], eax
0x18000eab1  lea     r8, [rsp+170h+var_13C]
0x18000eab6  mov     edx, 3
0x18000eabb  mov     rcx, r15
0x18000eabe  call    WriterGetProperty
0x18000eac3  test    eax, eax
0x18000eac5  jns     short loc_18000EAF3
0x18000eac7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eace  cmp     rcx, rdi
0x18000ead1  jz      short loc_18000EAE9
0x18000ead3  test    [rcx+44h], bl
0x18000ead6  jz      short loc_18000EAE9
0x18000ead8  mov     rcx, [rcx+38h]
0x18000eadc  mov     edx, 37h ; '7'
0x18000eae1  mov     r8, rsi
0x18000eae4  call    WPP_SF_
0x18000eae9  mov     [rsp+170h+var_13C], 96h
0x18000eaf1  jmp     short loc_18000EAFB
0x18000eaf3  mov     eax, [rsp+170h+var_13C]
0x18000eaf7  mov     [rsp+170h+var_13C], eax
0x18000eafb  lea     r8, [rsp+170h+var_134]
0x18000eb00  mov     edx, 4
0x18000eb05  mov     rcx, r15
0x18000eb08  call    WriterGetProperty
0x18000eb0d  test    eax, eax
0x18000eb0f  jns     short loc_18000EB35
0x18000eb11  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb18  cmp     rcx, rdi
0x18000eb1b  jz      short loc_18000EB3A
0x18000eb1d  test    [rcx+44h], bl
0x18000eb20  jz      short loc_18000EB3A
0x18000eb22  mov     rcx, [rcx+38h]
0x18000eb26  mov     edx, 38h ; '8'
0x18000eb2b  mov     r8, rsi
0x18000eb2e  call    WPP_SF_
0x18000eb33  jmp     short loc_18000EB3A
0x18000eb35  mov     r13d, [rsp+170h+var_134]
0x18000eb3a  lea     r8, [rsp+170h+var_130]
0x18000eb3f  mov     edx, 5
0x18000eb44  mov     rcx, r15
0x18000eb47  call    WriterGetProperty
0x18000eb4c  or      r15d, 0FFFFFFFFh
0x18000eb50  test    eax, eax
0x18000eb52  jns     short loc_18000EB7A
0x18000eb54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb5b  cmp     rcx, rdi
0x18000eb5e  jz      short loc_18000EB75
0x18000eb60  test    [rcx+44h], bl
0x18000eb63  jz      short loc_18000EB75
0x18000eb65  mov     rcx, [rcx+38h]
0x18000eb69  lea     edx, [r15+3Ah]
0x18000eb6d  mov     r8, rsi
0x18000eb70  call    WPP_SF_
0x18000eb75  mov     eax, r15d
0x18000eb78  jmp     short loc_18000EB7E
0x18000eb7a  mov     eax, [rsp+170h+var_130]
0x18000eb7e  xor     esi, esi
0x18000eb80  mov     [rbp+70h+var_C8], r12d
0x18000eb84  mov     [rsp+170h+var_120], esi
0x18000eb88  lea     rcx, aWritespeed; "WriteSpeed"
0x18000eb8f  mov     [rsp+170h+var_118], rcx
0x18000eb94  lea     rcx, aMaxwritespeed; "MaxWriteSpeed"
0x18000eb9b  mov     [rsp+170h+var_108], rcx
0x18000eba0  mov     ecx, [rsp+170h+var_140]
0x18000eba4  lea     edx, [rsi+3]
0x18000eba7  mov     [rbp+70h+var_B0], ecx
0x18000ebaa  lea     rcx, aAudiogapsize; "AudioGapSize"
0x18000ebb1  mov     [rsp+170h+var_F8], rcx
0x18000ebb6  mov     ecx, [rsp+170h+var_13C]
0x18000ebba  mov     [rbp+70h+var_98], ecx
0x18000ebbd  lea     rcx, aBufferunderrun; "BufferUnderrunFreeCapable"
0x18000ebc4  mov     [rbp+70h+var_E8], rcx
0x18000ebc8  lea     ecx, [rsi+0Bh]
0x18000ebcb  mov     [rbp+70h+var_88], cx
0x18000ebcf  mov     [rbp+70h+var_D0], dx
0x18000ebd3  mov     [rsp+170h+var_110], esi
0x18000ebd7  mov     [rbp+70h+var_B8], dx
0x18000ebdb  mov     [rsp+170h+var_100], esi
0x18000ebdf  mov     [rbp+70h+var_A0], dx
0x18000ebe3  mov     [rbp+70h+var_F0], esi
0x18000ebe6  test    r13d, r13d
0x18000ebe9  jnz     short loc_18000EBEE
0x18000ebeb  mov     r15d, esi
0x18000ebee  mov     [rbp+70h+var_70], dx
0x18000ebf2  lea     rcx, aEnablebufferun; "EnableBufferUnderrunFree"
0x18000ebf9  mov     [rbp+70h+var_D8], rcx
0x18000ebfd  lea     r9, [rbp+70h+var_D0]
0x18000ec01  mov     rcx, [r14+88h]
0x18000ec08  lea     r8, [rsp+170h+var_120]
0x18000ec0d  mov     [rbp+70h+var_68], eax
0x18000ec10  mov     edx, 5
0x18000ec15  mov     [rbp+70h+var_80], r15w
0x18000ec1a  mov     [rbp+70h+var_E0], esi
0x18000ec1d  mov     rax, [rcx]
0x18000ec20  mov     [rsp+170h+var_150], 2
0x18000ec28  mov     rax, [rax+20h]
0x18000ec2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec31  mov     edi, eax
0x18000ec33  test    eax, eax
0x18000ec35  jns     short loc_18000EC5A
0x18000ec37  mov     rbx, [r14+88h]
0x18000ec3e  test    rbx, rbx
0x18000ec41  jz      short loc_18000EC53
0x18000ec43  mov     rcx, rbx; this
0x18000ec46  call    ??1CIPropertyStorageWrapper@@QEAA@XZ; CIPropertyStorageWrapper::~CIPropertyStorageWrapper(void)
0x18000ec4b  mov     rcx, rbx; Block
0x18000ec4e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ec53  mov     [r14+88h], rsi
0x18000ec5a  mov     eax, edi
0x18000ec5c  mov     rcx, [rbp+70h+var_50]
0x18000ec60  xor     rcx, rsp; StackCookie
0x18000ec63  call    __security_check_cookie
0x18000ec68  add     rsp, 138h
0x18000ec6f  pop     r15
0x18000ec71  pop     r14
0x18000ec73  pop     r13
0x18000ec75  pop     r12
0x18000ec77  pop     rdi
0x18000ec78  pop     rsi
0x18000ec79  pop     rbx
0x18000ec7a  pop     rbp
0x18000ec7b  retn
```
