# Windows::ApplicationModel::Resources::Core::CResourceCandidate::get_ValueAsString(HSTRING__ * *)

- ea: `0x18004e7d0`
- end: `0x18004eb45`
- name: `?get_ValueAsString@CResourceCandidate@Core@Resources@ApplicationModel@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `885`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Resources::Core::CResourceCandidate *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002c8d0`
- `0x18002cfd0`
- `0x18004e7d0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e9c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ea6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e9c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ea6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e9d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ea78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e9d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ea78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e9b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e9e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e9b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e9e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004e99f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004e99f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceCandidate::get_ValueAsString(
        Windows::ApplicationModel::Resources::Core::CResourceCandidate *this,
        HSTRING *a2)
{
  __int64 v3; // rbx
  int v4; // eax
  char v5; // r14
  LPVOID *v6; // rax
  _DWORD *v7; // rcx
  LPVOID v8; // r8
  int v9; // edx
  WCHAR *v10; // rsi
  _DWORD *v11; // rcx
  void *v12; // rbx
  HSTRING v13; // rbx
  unsigned __int64 v14; // rdx
  HRESULT v15; // edi
  HANDLE v16; // rax
  WCHAR *v18; // rcx
  int v19; // edi
  HANDLE ProcessHeap; // rax
  int v21; // [rsp+20h] [rbp-50h]
  LPVOID **p_p_lpMem; // [rsp+20h] [rbp-50h]
  int v23; // [rsp+20h] [rbp-50h]
  int v24; // [rsp+40h] [rbp-30h] BYREF
  LPVOID *p_lpMem; // [rsp+48h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-20h] BYREF
  int v27; // [rsp+58h] [rbp-18h]
  __int64 v28; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  HSTRING string; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int16 v31; // [rsp+B8h] [rbp+48h] BYREF
  unsigned __int16 v32; // [rsp+C0h] [rbp+50h] BYREF
  unsigned int v33; // [rsp+C8h] [rbp+58h] BYREF

  *a2 = 0;
  v3 = *((_QWORD *)this + 10);
  if ( *(_QWORD *)(v3 + 56) != (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v3 + 16) + 112LL))(*(_QWORD *)(v3 + 16)) )
  {
    v15 = -2147009761;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresolvedinstanceinternal.cpp",
      (const char *)0x80073B1FLL,
      v21);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresolvedinstanceinternal.cpp",
      (const char *)0x80073B1FLL,
      v23);
    return (unsigned int)v15;
  }
  lpMem = 0;
  v27 = 0;
  v28 = 0;
  p_lpMem = &lpMem;
  v24 = 0;
  LOBYTE(string) = 0;
  v33 = 0;
  v32 = 0;
  v31 = 0;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, HSTRING *, unsigned int *, unsigned __int16 *, unsigned __int16 *, int *))(**(_QWORD **)(v3 + 24) + 72LL))(
         *(_QWORD *)(v3 + 24),
         *(unsigned int *)(v3 + 32),
         &string,
         &v33,
         &v32,
         &v31,
         &v24) < 0 )
    goto LABEL_47;
  if ( (_BYTE)string )
  {
    if ( (unsigned __int8)string != 1 )
    {
LABEL_47:
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
      return (unsigned int)-2147023728;
    }
    LODWORD(p_p_lpMem) = v24;
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(v3 + 24) + 96LL))(
           *(_QWORD *)(v3 + 24),
           (unsigned __int16)v33 | (v32 << 16),
           HIWORD(v33),
           v31);
  }
  else
  {
    p_p_lpMem = &p_lpMem;
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(v3 + 24) + 88LL))(
           *(_QWORD *)(v3 + 24),
           v33,
           v31,
           (unsigned int)v24);
  }
  v5 = 1;
  if ( v4 < 0 )
    goto LABEL_47;
  v6 = p_lpMem;
  if ( p_lpMem && ((v7 = p_lpMem + 1, *p_lpMem) || !*v7) && (*v7 || !*p_lpMem) )
  {
    v8 = p_lpMem[2];
    v9 = 0;
    if ( v8 )
    {
      LOBYTE(v9) = v8 != *p_lpMem;
      ++v9;
    }
    if ( v9 == 1 )
    {
      v10 = (WCHAR *)*p_lpMem;
      v11 = p_lpMem + 1;
      if ( !*p_lpMem && *v11 || !*v11 && v10 || !v10 || !*v11 )
      {
        v15 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x58,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresolvedinstanceinternal.cpp",
          (const char *)0x80070057LL,
          (int)p_p_lpMem);
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
        return (unsigned int)v15;
      }
      p_lpMem[2] = 0;
      *v6 = 0;
      *v11 = 0;
      goto LABEL_18;
    }
  }
  else
  {
    v7 = p_lpMem + 1;
    if ( !p_lpMem )
      goto LABEL_53;
  }
  if ( (*p_lpMem || !*v7) && (*v7 || !*p_lpMem) )
  {
    v18 = (WCHAR *)p_lpMem[2];
    v19 = 0;
    goto LABEL_44;
  }
LABEL_53:
  v18 = 0;
  v19 = -2147024809;
LABEL_44:
  v5 = 0;
  v10 = 0;
  if ( v19 >= 0 )
    v10 = v18;
LABEL_18:
  v12 = lpMem;
  if ( (lpMem || !v27) && (v27 || !lpMem) )
  {
    v28 = 0;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
    }
  }
  v13 = 0;
  if ( v10 )
  {
    string = 0;
    v14 = -1;
    do
      ++v14;
    while ( v10[v14] );
    if ( v14 > 0xFFFFFFFF )
    {
      v15 = -2147024362;
    }
    else
    {
      v15 = WindowsCreateString(v10, v14, &string);
      if ( v15 >= 0 )
      {
        v13 = string;
        WindowsDeleteString(0);
      }
    }
    if ( v15 >= 0 )
    {
      *a2 = v13;
      v13 = 0;
    }
  }
  else
  {
    v15 = -2147467261;
  }
  if ( v5 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v10);
  }
  if ( v13 )
    WindowsDeleteString(v13);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18004e7d0  push    rbp
0x18004e7d2  push    rbx
0x18004e7d3  push    rsi
0x18004e7d4  push    rdi
0x18004e7d5  push    r12
0x18004e7d7  push    r14
0x18004e7d9  push    r15
0x18004e7db  mov     rbp, rsp
0x18004e7de  sub     rsp, 70h
0x18004e7e2  mov     r15, rdx
0x18004e7e5  xor     r12d, r12d
0x18004e7e8  mov     [rdx], r12
0x18004e7eb  mov     rbx, [rcx+50h]
0x18004e7ef  mov     rcx, [rbx+10h]
0x18004e7f3  mov     rax, [rcx]
0x18004e7f6  mov     rax, [rax+70h]
0x18004e7fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7ff  cmp     [rbx+38h], rax
0x18004e803  jnz     loc_18004EAEF
0x18004e809  mov     [rbp+lpMem], r12
0x18004e80d  mov     [rbp+var_18], r12d
0x18004e811  mov     [rbp+var_10], r12
0x18004e815  lea     rax, [rbp+lpMem]
0x18004e819  mov     [rbp+var_28], rax
0x18004e81d  mov     [rbp+var_30], r12d
0x18004e821  mov     byte ptr [rbp+string], r12b
0x18004e825  mov     [rbp+arg_18], r12d
0x18004e829  mov     [rbp+arg_10], r12w
0x18004e82e  mov     [rbp+arg_8], r12w
0x18004e833  mov     rcx, [rbx+18h]
0x18004e837  mov     rax, [rcx]
0x18004e83a  lea     rdx, [rbp+var_30]
0x18004e83e  mov     [rsp+70h+var_40], rdx
0x18004e843  lea     rdx, [rbp+arg_8]
0x18004e847  mov     [rsp+70h+var_48], rdx
0x18004e84c  lea     rdx, [rbp+arg_10]
0x18004e850  mov     qword ptr [rsp+70h+var_50], rdx
0x18004e855  lea     r9, [rbp+arg_18]
0x18004e859  lea     r8, [rbp+string]
0x18004e85d  mov     edx, [rbx+20h]
0x18004e860  mov     rax, [rax+48h]
0x18004e864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e869  test    eax, eax
0x18004e86b  js      loc_18004EA44
0x18004e871  movzx   ecx, byte ptr [rbp+string]
0x18004e875  test    ecx, ecx
0x18004e877  jz      loc_18004EAC5
0x18004e87d  cmp     ecx, 1
0x18004e880  jnz     loc_18004EA44
0x18004e886  mov     rcx, [rbx+18h]
0x18004e88a  mov     r9, [rcx]
0x18004e88d  mov     r8d, [rbp+arg_18]
0x18004e891  shr     r8d, 10h
0x18004e895  movzx   edx, [rbp+arg_10]
0x18004e899  shl     edx, 10h
0x18004e89c  movzx   eax, word ptr [rbp+arg_18]
0x18004e8a0  or      edx, eax
0x18004e8a2  mov     rax, [r9+60h]
0x18004e8a6  lea     r9, [rbp+var_28]
0x18004e8aa  mov     [rsp+70h+var_48], r9
0x18004e8af  mov     r9d, [rbp+var_30]
0x18004e8b3  mov     [rsp+70h+var_50], r9d; int
0x18004e8b8  movzx   r9d, [rbp+arg_8]
0x18004e8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8c2  shr     eax, 1Fh
0x18004e8c5  mov     r14d, 1
0x18004e8cb  xor     al, r14b
0x18004e8ce  jz      loc_18004EA44
0x18004e8d4  mov     rax, [rbp+var_28]
0x18004e8d8  test    rax, rax
0x18004e8db  jz      loc_18004EA03
0x18004e8e1  lea     rcx, [rax+8]
0x18004e8e5  cmp     [rax], r12
0x18004e8e8  jz      loc_18004EA54
0x18004e8ee  cmp     [rcx], r12d
0x18004e8f1  jz      loc_18004EA5F
0x18004e8f7  mov     r8, [rax+10h]
0x18004e8fb  mov     edx, r12d
0x18004e8fe  test    r8, r8
0x18004e901  jz      short loc_18004E90C
0x18004e903  cmp     r8, [rax]
0x18004e906  setnz   dl
0x18004e909  add     edx, r14d
0x18004e90c  cmp     edx, r14d
0x18004e90f  jnz     loc_18004EA10
0x18004e915  mov     rsi, [rax]
0x18004e918  lea     rcx, [rax+8]
0x18004e91c  test    rsi, rsi
0x18004e91f  jz      loc_18004EB29
0x18004e925  cmp     [rcx], r12d
0x18004e928  jz      loc_18004EB37
0x18004e92e  test    rsi, rsi
0x18004e931  jz      loc_18004EA83
0x18004e937  cmp     [rcx], r12d
0x18004e93a  jz      loc_18004EA83
0x18004e940  mov     [rax+10h], r12
0x18004e944  mov     [rax], r12
0x18004e947  mov     [rcx], r12d
0x18004e94a  mov     rbx, [rbp+lpMem]
0x18004e94e  mov     eax, [rbp+var_18]
0x18004e951  test    rbx, rbx
0x18004e954  jnz     short loc_18004E95A
0x18004e956  test    eax, eax
0x18004e958  jnz     short loc_18004E970
0x18004e95a  test    eax, eax
0x18004e95c  jnz     short loc_18004E963
0x18004e95e  test    rbx, rbx
0x18004e961  jnz     short loc_18004E970
0x18004e963  mov     [rbp+var_10], r12
0x18004e967  test    rbx, rbx
0x18004e96a  jnz     loc_18004EA6A
0x18004e970  mov     rbx, r12
0x18004e973  test    rsi, rsi
0x18004e976  jz      loc_18004EABB
0x18004e97c  mov     [rbp+string], r12
0x18004e980  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004e984  inc     rdx; length
0x18004e987  cmp     [rsi+rdx*2], r12w
0x18004e98c  jnz     short loc_18004E984
0x18004e98e  mov     eax, 0FFFFFFFFh
0x18004e993  cmp     rdx, rax
0x18004e996  ja      short loc_18004E9FC
0x18004e998  lea     r8, [rbp+string]; string
0x18004e99c  mov     rcx, rsi; sourceString
0x18004e99f  call    cs:__imp_WindowsCreateString
0x18004e9a5  mov     edi, eax
0x18004e9a7  test    eax, eax
0x18004e9a9  js      short loc_18004E9B8
0x18004e9ab  mov     rbx, [rbp+string]
0x18004e9af  xor     ecx, ecx; string
0x18004e9b1  call    cs:__imp_WindowsDeleteString
0x18004e9b7  nop
0x18004e9b8  test    edi, edi
0x18004e9ba  js      short loc_18004E9C2
0x18004e9bc  mov     [r15], rbx
0x18004e9bf  mov     rbx, r12
0x18004e9c2  test    r14b, r14b
0x18004e9c5  jz      short loc_18004E9DC
0x18004e9c7  call    cs:__imp_GetProcessHeap
0x18004e9cd  mov     r8, rsi; lpMem
0x18004e9d0  xor     edx, edx; dwFlags
0x18004e9d2  mov     rcx, rax; hHeap
0x18004e9d5  call    cs:__imp_HeapFree
0x18004e9db  nop
0x18004e9dc  test    rbx, rbx
0x18004e9df  jz      short loc_18004E9EB
0x18004e9e1  mov     rcx, rbx; string
0x18004e9e4  call    cs:__imp_WindowsDeleteString
0x18004e9ea  nop
0x18004e9eb  mov     eax, edi
0x18004e9ed  add     rsp, 70h
0x18004e9f1  pop     r15
0x18004e9f3  pop     r14
0x18004e9f5  pop     r12
0x18004e9f7  pop     rdi
0x18004e9f8  pop     rsi
0x18004e9f9  pop     rbx
0x18004e9fa  pop     rbp
0x18004e9fb  retn
0x18004e9fc  mov     edi, 80070216h
0x18004ea01  jmp     short loc_18004E9B8
0x18004ea03  lea     rcx, [rax+8]
0x18004ea07  test    rax, rax
0x18004ea0a  jz      loc_18004EAAE
0x18004ea10  cmp     [rax], r12
0x18004ea13  jnz     short loc_18004EA1E
0x18004ea15  cmp     [rcx], r12d
0x18004ea18  ja      loc_18004EAAE
0x18004ea1e  cmp     [rcx], r12d
0x18004ea21  jnz     short loc_18004EA2C
0x18004ea23  cmp     [rax], r12
0x18004ea26  jnz     loc_18004EAAE
0x18004ea2c  mov     rcx, [rax+10h]
0x18004ea30  mov     edi, r12d
0x18004ea33  mov     r14b, r12b
0x18004ea36  mov     rsi, r12
0x18004ea39  test    edi, edi
0x18004ea3b  cmovns  rsi, rcx
0x18004ea3f  jmp     loc_18004E94A
0x18004ea44  lea     rcx, [rbp+var_28]; this
0x18004ea48  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18004ea4d  mov     edi, 80070490h
0x18004ea52  jmp     short loc_18004E9EB
0x18004ea54  cmp     [rcx], r12d
0x18004ea57  jbe     loc_18004E8EE
0x18004ea5d  jmp     short loc_18004EA03
0x18004ea5f  cmp     [rax], r12
0x18004ea62  jz      loc_18004E8F7
0x18004ea68  jmp     short loc_18004EA03
0x18004ea6a  call    cs:__imp_GetProcessHeap
0x18004ea70  mov     rcx, rax; hHeap
0x18004ea73  mov     r8, rbx; lpMem
0x18004ea76  xor     edx, edx; dwFlags
0x18004ea78  call    cs:__imp_HeapFree
0x18004ea7e  jmp     loc_18004E970
0x18004ea83  mov     rcx, [rbp+38h]; this
0x18004ea87  mov     edi, 80070057h
0x18004ea8c  mov     r9d, edi; char *
0x18004ea8f  lea     r8, aOnecoreuapBase_33; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x18004ea96  mov     edx, 58h ; 'X'; void *
0x18004ea9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eaa0  lea     rcx, [rbp+var_28]; this
0x18004eaa4  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18004eaa9  jmp     loc_18004E9EB
0x18004eaae  mov     rcx, r12
0x18004eab1  mov     edi, 80070057h
0x18004eab6  jmp     loc_18004EA33
0x18004eabb  mov     edi, 80004003h
0x18004eac0  jmp     loc_18004E9C2
0x18004eac5  mov     rcx, [rbx+18h]
0x18004eac9  mov     rax, [rcx]
0x18004eacc  movzx   r8d, [rbp+arg_8]
0x18004ead1  lea     rdx, [rbp+var_28]
0x18004ead5  mov     qword ptr [rsp+70h+var_50], rdx
0x18004eada  mov     r9d, [rbp+var_30]
0x18004eade  mov     edx, [rbp+arg_18]
0x18004eae1  mov     rax, [rax+58h]
0x18004eae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eaea  jmp     loc_18004E8C2
0x18004eaef  mov     rcx, [rbp+38h]; this
0x18004eaf3  mov     edi, 80073B1Fh
0x18004eaf8  mov     r9d, edi; char *
0x18004eafb  lea     r8, aOnecoreuapBase_33; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x18004eb02  mov     edx, 1E2h; void *
0x18004eb07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eb0c  mov     rcx, [rbp+38h]; this
0x18004eb10  mov     r9d, edi; char *
0x18004eb13  lea     r8, aOnecoreuapBase_33; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x18004eb1a  mov     edx, 4Dh ; 'M'; void *
0x18004eb1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eb24  jmp     loc_18004E9EB
0x18004eb29  cmp     [rcx], r12d
0x18004eb2c  ja      loc_18004EA83
0x18004eb32  jmp     loc_18004E925
0x18004eb37  test    rsi, rsi
0x18004eb3a  jnz     loc_18004EA83
0x18004eb40  jmp     loc_18004E92E
```
