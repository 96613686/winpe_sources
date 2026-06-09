# CCCListViewCtrl::DefaultCompare(__int64,__int64,__int64)

- ea: `0x1400a0700`
- end: `0x1400a09b8`
- name: `?DefaultCompare@CCCListViewCtrl@@KAH_J00@Z`
- size: `696`
- prototype: `static int(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140026af0`

## callees

- `0x140028d30`
- `0x1400598b4`
- `0x140062455`
- `0x1400a0700`
- `0x1400e9e10`
- `0x1400f3010`

## import_xrefs

- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x1400a07a5`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x1400a07b1`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x1400a07a5`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x1400a07b1`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400a0919`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400a0925`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400a099f`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400a09ab`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400a0919`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400a0925`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400a099f`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x1400a09ab`
- `MFC42u!__imp_??4CString@@QEAAAEBV0@PEBD@Z` at `0x1400a084d`
- `MFC42u!__imp_??4CString@@QEAAAEBV0@PEBD@Z` at `0x1400a08cd`
- `MFC42u!__imp_??4CString@@QEAAAEBV0@PEBD@Z` at `0x1400a084d`
- `MFC42u!__imp_??4CString@@QEAAAEBV0@PEBD@Z` at `0x1400a08cd`
- `MFC42u!__imp_??4CString@@QEAAAEBV0@PEBG@Z` at `0x1400a083e`
- `MFC42u!__imp_??4CString@@QEAAAEBV0@PEBG@Z` at `0x1400a08be`
- `MFC42u!__imp_??4CString@@QEAAAEBV0@PEBG@Z` at `0x1400a083e`
- `MFC42u!__imp_??4CString@@QEAAAEBV0@PEBG@Z` at `0x1400a08be`
- `msvcrt!_wcsicmp` at `0x1400a0980`
- `msvcrt!_wcsicmp` at `0x1400a0980`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1400a0964`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1400a0964`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCCListViewCtrl::DefaultCompare(__int64 a1, __int64 a2, __int64 a3)
{
  struct CResultItem *v6; // r14
  struct CResultItem *v7; // rax
  unsigned int v8; // ebx
  __int64 v10; // rbx
  unsigned int v11; // edi
  __int64 v12; // r14
  unsigned int v13; // r14d
  unsigned int v14; // ebx
  int v15; // eax
  int v16; // eax
  PCNZWCH lpString2; // [rsp+30h] [rbp-D0h] BYREF
  PCNZWCH lpString1; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v19[6]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v20; // [rsp+58h] [rbp-A8h]
  int v21; // [rsp+60h] [rbp-A0h]
  __int64 v22; // [rsp+68h] [rbp-98h]
  _BYTE v23[528]; // [rsp+A0h] [rbp-60h] BYREF

  if ( !a3 )
    return 0;
  v6 = CResultItem::FromHandle(a1);
  v7 = CResultItem::FromHandle(a2);
  if ( !v6 || !v7 )
    return 0;
  if ( (*((_DWORD *)v6 + 6) == 60102025) != (*((_DWORD *)v7 + 6) == 60102025) )
  {
    v8 = -1;
    if ( *((_DWORD *)v6 + 6) != 60102025 )
      v8 = 1;
    if ( !*(_DWORD *)a3 )
      return -v8;
    return v8;
  }
  v10 = *(_QWORD *)(a3 + 184);
  if ( !v10 )
    return 0;
  CString::CString(&lpString1);
  CString::CString(&lpString2);
  memset_0(v19, 0, 0x58u);
  v11 = 1;
  v19[0] = 1;
  v19[2] = *(_DWORD *)(a3 + 8);
  v21 = 260;
  v20 = v23;
  v12 = *(_QWORD *)(a3 + 200);
  if ( v12 )
  {
    v22 = a1;
    memset_0(v23, 0, 0x20Au);
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, _DWORD *))(*(_QWORD *)v10 + 56LL))(v10, v12, v19);
    if ( v13 )
    {
      CString::operator=(&lpString1, &dword_14010FC0C);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, WPP_bf2b9f813cf4358b795ac1814230b624_Traceguids, v13);
    }
    else
    {
      CString::operator=(&lpString1, v20);
    }
    v22 = a2;
    memset_0(v23, 0, 0x20Au);
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *))(*(_QWORD *)v10 + 56LL))(
            v10,
            *(_QWORD *)(a3 + 200),
            v19);
    if ( v14 )
    {
      CString::operator=(&lpString2, &dword_14010FC0C);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_bf2b9f813cf4358b795ac1814230b624_Traceguids, v14);
    }
    else
    {
      CString::operator=(&lpString2, v20);
    }
  }
  if ( !*((_DWORD *)lpString1 - 2) && !*((_DWORD *)lpString2 - 2) )
  {
    CString::~CString(&lpString2);
    CString::~CString(&lpString1);
    return 0;
  }
  v15 = CompareStringW(0x400u, 1u, lpString1, -1, lpString2, -1) - 1;
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( v16 )
    {
      if ( v16 != 1 )
        v11 = _wcsicmp(lpString1, lpString2);
    }
    else
    {
      v11 = 0;
    }
  }
  else
  {
    v11 = -1;
  }
  if ( !*(_DWORD *)a3 )
    v11 = -v11;
  CString::~CString(&lpString2);
  CString::~CString(&lpString1);
  return v11;
}

```

## disassembly

```asm
0x1400a0700  push    rbp
0x1400a0702  push    rbx
0x1400a0703  push    rsi
0x1400a0704  push    rdi
0x1400a0705  push    r12
0x1400a0707  push    r14
0x1400a0709  push    r15
0x1400a070b  lea     rbp, [rsp-1C0h]
0x1400a0713  sub     rsp, 2C0h
0x1400a071a  mov     rax, cs:__security_cookie
0x1400a0721  xor     rax, rsp
0x1400a0724  mov     [rbp+1F0h+var_40], rax
0x1400a072b  mov     rsi, r8
0x1400a072e  mov     r12, rdx
0x1400a0731  mov     r15, rcx
0x1400a0734  test    r8, r8
0x1400a0737  jz      loc_1400A092B
0x1400a073d  call    ?FromHandle@CResultItem@@SAPEAV1@_J@Z; CResultItem::FromHandle(__int64)
0x1400a0742  mov     r14, rax
0x1400a0745  mov     rcx, r12; __int64
0x1400a0748  call    ?FromHandle@CResultItem@@SAPEAV1@_J@Z; CResultItem::FromHandle(__int64)
0x1400a074d  test    r14, r14
0x1400a0750  jz      loc_1400A092B
0x1400a0756  test    rax, rax
0x1400a0759  jz      loc_1400A092B
0x1400a075f  mov     edx, 3951589h
0x1400a0764  cmp     [rax+18h], edx
0x1400a0767  setz    cl
0x1400a076a  cmp     [r14+18h], edx
0x1400a076e  setz    al
0x1400a0771  cmp     al, cl
0x1400a0773  jz      short loc_1400A0790
0x1400a0775  or      ebx, 0FFFFFFFFh
0x1400a0778  lea     edi, [rbx+2]
0x1400a077b  cmp     [r14+18h], edx
0x1400a077f  cmovnz  ebx, edi
0x1400a0782  cmp     dword ptr [rsi], 0
0x1400a0785  jnz     short loc_1400A0789
0x1400a0787  neg     ebx
0x1400a0789  mov     eax, ebx
0x1400a078b  jmp     loc_1400A092D
0x1400a0790  mov     rbx, [rsi+0B8h]
0x1400a0797  test    rbx, rbx
0x1400a079a  jz      loc_1400A092B
0x1400a07a0  lea     rcx, [rsp+2F0h+lpString1]
0x1400a07a5  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x1400a07ab  nop
0x1400a07ac  lea     rcx, [rsp+2F0h+var_2C0]
0x1400a07b1  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x1400a07b7  nop
0x1400a07b8  xor     edx, edx; Val
0x1400a07ba  lea     r8d, [rdx+58h]; Size
0x1400a07be  lea     rcx, [rsp+2F0h+var_2B0]; void *
0x1400a07c3  call    memset_0
0x1400a07c8  mov     edi, 1
0x1400a07cd  mov     [rsp+2F0h+var_2B0], edi
0x1400a07d1  mov     eax, [rsi+8]
0x1400a07d4  mov     [rsp+2F0h+var_2A8], eax
0x1400a07d8  mov     [rsp+2F0h+var_290], 104h
0x1400a07e0  lea     rax, [rbp+1F0h+var_250]
0x1400a07e4  mov     [rsp+2F0h+var_298], rax
0x1400a07e9  mov     r14, [rsi+0C8h]
0x1400a07f0  test    r14, r14
0x1400a07f3  jz      loc_1400A08FD
0x1400a07f9  mov     [rsp+2F0h+var_288], r15
0x1400a07fe  xor     edx, edx; Val
0x1400a0800  mov     r8d, 20Ah; Size
0x1400a0806  lea     rcx, [rbp+1F0h+var_250]; void *
0x1400a080a  call    memset_0
0x1400a080f  mov     rax, [rbx]
0x1400a0812  lea     r8, [rsp+2F0h+var_2B0]
0x1400a0817  mov     rdx, r14
0x1400a081a  mov     rcx, rbx
0x1400a081d  mov     rax, [rax+38h]
0x1400a0821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a0826  mov     r14d, eax
0x1400a0829  lea     r15, WPP_GLOBAL_Control
0x1400a0830  lea     rcx, [rsp+2F0h+lpString1]
0x1400a0835  test    eax, eax
0x1400a0837  jnz     short loc_1400A0846
0x1400a0839  mov     rdx, [rsp+2F0h+var_298]
0x1400a083e  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x1400a0844  jmp     short loc_1400A087D
0x1400a0846  lea     rdx, dword_14010FC0C
0x1400a084d  call    cs:__imp_??4CString@@QEAAAEBV0@PEBD@Z; CString::operator=(char const *)
0x1400a0853  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a085a  cmp     rcx, r15
0x1400a085d  jz      short loc_1400A087D
0x1400a085f  cmp     byte ptr [rcx+19h], 2
0x1400a0863  jb      short loc_1400A087D
0x1400a0865  mov     edx, 18h
0x1400a086a  mov     r9d, r14d
0x1400a086d  lea     r8, WPP_bf2b9f813cf4358b795ac1814230b624_Traceguids
0x1400a0874  mov     rcx, [rcx+10h]
0x1400a0878  call    WPP_SF_d
0x1400a087d  mov     [rsp+2F0h+var_288], r12
0x1400a0882  xor     edx, edx; Val
0x1400a0884  mov     r8d, 20Ah; Size
0x1400a088a  lea     rcx, [rbp+1F0h+var_250]; void *
0x1400a088e  call    memset_0
0x1400a0893  mov     rax, [rbx]
0x1400a0896  lea     r8, [rsp+2F0h+var_2B0]
0x1400a089b  mov     rdx, [rsi+0C8h]
0x1400a08a2  mov     rcx, rbx
0x1400a08a5  mov     rax, [rax+38h]
0x1400a08a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a08ae  mov     ebx, eax
0x1400a08b0  lea     rcx, [rsp+2F0h+var_2C0]
0x1400a08b5  test    eax, eax
0x1400a08b7  jnz     short loc_1400A08C6
0x1400a08b9  mov     rdx, [rsp+2F0h+var_298]
0x1400a08be  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x1400a08c4  jmp     short loc_1400A08FD
0x1400a08c6  lea     rdx, dword_14010FC0C
0x1400a08cd  call    cs:__imp_??4CString@@QEAAAEBV0@PEBD@Z; CString::operator=(char const *)
0x1400a08d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a08da  cmp     rcx, r15
0x1400a08dd  jz      short loc_1400A08FD
0x1400a08df  cmp     byte ptr [rcx+19h], 2
0x1400a08e3  jb      short loc_1400A08FD
0x1400a08e5  mov     edx, 19h
0x1400a08ea  mov     r9d, ebx
0x1400a08ed  lea     r8, WPP_bf2b9f813cf4358b795ac1814230b624_Traceguids
0x1400a08f4  mov     rcx, [rcx+10h]
0x1400a08f8  call    WPP_SF_d
0x1400a08fd  mov     rax, [rsp+2F0h+var_2C0]
0x1400a0902  mov     r8, [rsp+2F0h+lpString1]; lpString1
0x1400a0907  cmp     dword ptr [r8-8], 0
0x1400a090c  jnz     short loc_1400A094E
0x1400a090e  cmp     dword ptr [rax-8], 0
0x1400a0912  jnz     short loc_1400A094E
0x1400a0914  lea     rcx, [rsp+2F0h+var_2C0]
0x1400a0919  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1400a091f  nop
0x1400a0920  lea     rcx, [rsp+2F0h+lpString1]
0x1400a0925  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1400a092b  xor     eax, eax
0x1400a092d  mov     rcx, [rbp+1F0h+var_40]
0x1400a0934  xor     rcx, rsp; StackCookie
0x1400a0937  call    __security_check_cookie
0x1400a093c  add     rsp, 2C0h
0x1400a0943  pop     r15
0x1400a0945  pop     r14
0x1400a0947  pop     r12
0x1400a0949  pop     rdi
0x1400a094a  pop     rsi
0x1400a094b  pop     rbx
0x1400a094c  pop     rbp
0x1400a094d  retn
0x1400a094e  or      ebx, 0FFFFFFFFh
0x1400a0951  mov     [rsp+2F0h+cchCount2], ebx; cchCount2
0x1400a0955  mov     [rsp+2F0h+lpString2], rax; lpString2
0x1400a095a  mov     r9d, ebx; cchCount1
0x1400a095d  mov     edx, edi; dwCmpFlags
0x1400a095f  mov     ecx, 400h; Locale
0x1400a0964  call    cs:__imp_CompareStringW
0x1400a096a  sub     eax, edi
0x1400a096c  jz      short loc_1400A098E
0x1400a096e  sub     eax, edi
0x1400a0970  jz      short loc_1400A098A
0x1400a0972  cmp     eax, edi
0x1400a0974  jz      short loc_1400A0990
0x1400a0976  mov     rdx, [rsp+2F0h+var_2C0]; String2
0x1400a097b  mov     rcx, [rsp+2F0h+lpString1]; String1
0x1400a0980  call    cs:__imp__wcsicmp
0x1400a0986  mov     edi, eax
0x1400a0988  jmp     short loc_1400A0990
0x1400a098a  xor     edi, edi
0x1400a098c  jmp     short loc_1400A0990
0x1400a098e  mov     edi, ebx
0x1400a0990  mov     eax, edi
0x1400a0992  neg     eax
0x1400a0994  cmp     dword ptr [rsi], 0
0x1400a0997  cmovz   edi, eax
0x1400a099a  lea     rcx, [rsp+2F0h+var_2C0]
0x1400a099f  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1400a09a5  nop
0x1400a09a6  lea     rcx, [rsp+2F0h+lpString1]
0x1400a09ab  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1400a09b1  mov     eax, edi
0x1400a09b3  jmp     loc_1400A092D
```
