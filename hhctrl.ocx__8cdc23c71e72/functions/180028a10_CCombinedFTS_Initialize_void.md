# CCombinedFTS::Initialize(void)

- ea: `0x180028a10`
- end: `0x180028c30`
- name: `?Initialize@CCombinedFTS@@QEAAJXZ`
- size: `544`
- prototype: `__int64 __fastcall(CCombinedFTS *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800295cc`

## callees

- `0x18000d5bc`
- `0x180028a10`
- `0x180061b98`
- `0x180078010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180028acc`
- `ole32!CoCreateInstance` at `0x180028af6`
- `ole32!CoCreateInstance` at `0x180028b9e`
- `ole32!CoCreateInstance` at `0x180028acc`
- `ole32!CoCreateInstance` at `0x180028af6`
- `ole32!CoCreateInstance` at `0x180028b9e`

## pseudocode

```c
__int64 __fastcall CCombinedFTS::Initialize(CCombinedFTS *this, __int64 a2, __int64 a3, int a4)
{
  __int64 v4; // rax
  const char *QueryName; // rax
  __int16 v7; // ax
  bool v8; // cc
  int v9; // eax
  int v10; // eax
  _QWORD *v11; // rsi
  _QWORD *v12; // r14
  LPVOID *ppv; // rbx
  int v14; // eax
  unsigned int v15; // ecx

  v4 = *((_QWORD *)this + 2);
  if ( v4 && *(_DWORD *)(v4 + 32) )
    QueryName = *(const char **)(*(_QWORD *)(v4 + 24) + 40LL);
  else
    QueryName = CExTitle::GetQueryName(*((CExTitle **)this + 1));
  if ( !QueryName )
    return 2147500037LL;
  HHMultiByteToWideChar(0, 0, QueryName, a4, (LPWSTR)this + 44, 260);
  v7 = *((_WORD *)this + 41) & 0x3FF;
  if ( v7 == 4 || (v8 = (unsigned __int16)(v7 - 17) <= 1u, v9 = 0, v8) )
    v9 = 1;
  *((_DWORD *)this + 21) = v9;
  v10 = 589824;
  if ( *((_DWORD *)this + 8) != 1033 )
    v10 = 0x80000;
  *((_DWORD *)this + 7) = v10;
  if ( !*((_WORD *)this + 44) )
    return 2147500037LL;
  v11 = (_QWORD *)((char *)this + 48);
  if ( CoCreateInstance(&CLSID_IITIndexLocal, 0, 1u, &IID_IITIndex, (LPVOID *)this + 6) < 0 )
    return 2147500037LL;
  v12 = (_QWORD *)((char *)this + 72);
  if ( CoCreateInstance(&CLSID_IITDatabaseLocal, 0, 1u, &IID_IITDatabase, (LPVOID *)this + 9) < 0 )
    return 2147500037LL;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, char *, _QWORD))(*(_QWORD *)*v12 + 24LL))(*v12, 0, (char *)this + 88, 0) < 0 )
    return 2147500037LL;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, const wchar_t *, __int64))(*(_QWORD *)*v11 + 24LL))(
         *v11,
         *v12,
         L"ftiMain",
         1) < 0 )
    return 2147500037LL;
  if ( (*(int (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v11 + 56LL))(*v11, (char *)this + 56) < 0 )
    return 2147500037LL;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 7) + 40LL))(
         *((_QWORD *)this + 7),
         *((unsigned int *)this + 7)) < 0 )
    return 2147500037LL;
  ppv = (LPVOID *)((char *)this + 64);
  if ( !*ppv && CoCreateInstance(&CLSID_IITResultSet, 0, 1u, &IID_IITResultSet, ppv) < 0 )
    return 2147500037LL;
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*ppv + 200LL))(*ppv);
  if ( (*(int (__fastcall **)(LPVOID, __int64, _QWORD, __int64))(*(_QWORD *)*ppv + 48LL))(*ppv, 1, 0, 1) < 0
    || (*(int (__fastcall **)(LPVOID, __int64, _QWORD, __int64))(*(_QWORD *)*ppv + 48LL))(*ppv, 504, 0, 1) < 0 )
  {
    return 2147500037LL;
  }
  v14 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64))(*(_QWORD *)*ppv + 48LL))(*ppv, 502, 0, 1);
  v15 = 0;
  if ( v14 < 0 )
    return (unsigned int)-2147467259;
  return v15;
}

```

## disassembly

```asm
0x180028a10  push    rbx
0x180028a12  push    rbp
0x180028a13  push    rsi
0x180028a14  push    rdi
0x180028a15  push    r14
0x180028a17  push    r15
0x180028a19  sub     rsp, 38h
0x180028a1d  mov     rax, [rcx+10h]
0x180028a21  xor     ebp, ebp
0x180028a23  mov     rbx, rcx
0x180028a26  test    rax, rax
0x180028a29  jz      short loc_180028A3A
0x180028a2b  cmp     [rax+20h], ebp
0x180028a2e  jz      short loc_180028A3A
0x180028a30  mov     rax, [rax+18h]
0x180028a34  mov     rax, [rax+28h]
0x180028a38  jmp     short loc_180028A43
0x180028a3a  mov     rcx, [rcx+8]; this
0x180028a3e  call    ?GetQueryName@CExTitle@@QEAAPEBDXZ; CExTitle::GetQueryName(void)
0x180028a43  test    rax, rax
0x180028a46  jz      loc_180028C1E
0x180028a4c  lea     rdi, [rbx+58h]
0x180028a50  mov     [rsp+68h+var_40], 104h; int
0x180028a58  mov     r8, rax; char *
0x180028a5b  mov     [rsp+68h+ppv], rdi; LPWSTR
0x180028a60  xor     edx, edx; unsigned int
0x180028a62  xor     ecx, ecx; unsigned int
0x180028a64  call    ?HHMultiByteToWideChar@@YAHIKPEBDHPEAGH@Z; HHMultiByteToWideChar(uint,ulong,char const *,int,ushort *,int)
0x180028a69  mov     eax, 3FFh
0x180028a6e  mov     r15d, 1
0x180028a74  and     ax, [rbx+52h]
0x180028a78  cmp     ax, 4
0x180028a7c  jz      short loc_180028A8A
0x180028a7e  sub     ax, 11h
0x180028a82  cmp     ax, r15w
0x180028a86  mov     eax, ebp
0x180028a88  ja      short loc_180028A8D
0x180028a8a  mov     eax, r15d
0x180028a8d  mov     [rbx+54h], eax
0x180028a90  mov     ecx, 80000h
0x180028a95  cmp     dword ptr [rbx+20h], 409h
0x180028a9c  mov     eax, 90000h
0x180028aa1  cmovnz  eax, ecx
0x180028aa4  mov     [rbx+1Ch], eax
0x180028aa7  cmp     [rdi], bp
0x180028aaa  jz      loc_180028C1E
0x180028ab0  lea     rsi, [rbx+30h]
0x180028ab4  mov     r8d, r15d; dwClsContext
0x180028ab7  lea     r9, IID_IITIndex; riid
0x180028abe  mov     [rsp+68h+ppv], rsi; ppv
0x180028ac3  xor     edx, edx; pUnkOuter
0x180028ac5  lea     rcx, CLSID_IITIndexLocal; rclsid
0x180028acc  call    cs:__imp_CoCreateInstance
0x180028ad2  test    eax, eax
0x180028ad4  js      loc_180028C1E
0x180028ada  lea     r14, [rbx+48h]
0x180028ade  mov     r8d, r15d; dwClsContext
0x180028ae1  lea     r9, IID_IITDatabase; riid
0x180028ae8  mov     [rsp+68h+ppv], r14; ppv
0x180028aed  xor     edx, edx; pUnkOuter
0x180028aef  lea     rcx, CLSID_IITDatabaseLocal; rclsid
0x180028af6  call    cs:__imp_CoCreateInstance
0x180028afc  test    eax, eax
0x180028afe  js      loc_180028C1E
0x180028b04  mov     rcx, [r14]
0x180028b07  xor     r9d, r9d
0x180028b0a  mov     r8, rdi
0x180028b0d  xor     edx, edx
0x180028b0f  mov     rax, [rcx]
0x180028b12  mov     rax, [rax+18h]
0x180028b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b1b  test    eax, eax
0x180028b1d  js      loc_180028C1E
0x180028b23  mov     rcx, [rsi]
0x180028b26  lea     r8, aFtimain; "ftiMain"
0x180028b2d  mov     rdx, [r14]
0x180028b30  mov     r9d, r15d
0x180028b33  mov     rax, [rcx]
0x180028b36  mov     rax, [rax+18h]
0x180028b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b3f  test    eax, eax
0x180028b41  js      loc_180028C1E
0x180028b47  mov     rcx, [rsi]
0x180028b4a  lea     rdx, [rbx+38h]
0x180028b4e  mov     rax, [rcx]
0x180028b51  mov     rax, [rax+38h]
0x180028b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b5a  test    eax, eax
0x180028b5c  js      loc_180028C1E
0x180028b62  mov     rcx, [rbx+38h]
0x180028b66  mov     edx, [rbx+1Ch]
0x180028b69  mov     rax, [rcx]
0x180028b6c  mov     rax, [rax+28h]
0x180028b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b75  test    eax, eax
0x180028b77  js      loc_180028C1E
0x180028b7d  add     rbx, 40h ; '@'
0x180028b81  cmp     [rbx], rbp
0x180028b84  jnz     short loc_180028BA8
0x180028b86  lea     r9, IID_IITResultSet; riid
0x180028b8d  mov     [rsp+68h+ppv], rbx; ppv
0x180028b92  mov     r8d, r15d; dwClsContext
0x180028b95  lea     rcx, CLSID_IITResultSet; rclsid
0x180028b9c  xor     edx, edx; pUnkOuter
0x180028b9e  call    cs:__imp_CoCreateInstance
0x180028ba4  test    eax, eax
0x180028ba6  js      short loc_180028C1E
0x180028ba8  mov     rcx, [rbx]
0x180028bab  mov     rax, [rcx]
0x180028bae  mov     rax, [rax+0C8h]
0x180028bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bba  mov     rcx, [rbx]
0x180028bbd  mov     r9d, r15d
0x180028bc0  xor     r8d, r8d
0x180028bc3  mov     edx, r15d
0x180028bc6  mov     rax, [rcx]
0x180028bc9  mov     rax, [rax+30h]
0x180028bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bd2  test    eax, eax
0x180028bd4  js      short loc_180028C1E
0x180028bd6  mov     rcx, [rbx]
0x180028bd9  mov     r9d, r15d
0x180028bdc  xor     r8d, r8d
0x180028bdf  mov     edx, 1F8h
0x180028be4  mov     rax, [rcx]
0x180028be7  mov     rax, [rax+30h]
0x180028beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bf0  test    eax, eax
0x180028bf2  js      short loc_180028C1E
0x180028bf4  mov     rcx, [rbx]
0x180028bf7  mov     r9d, r15d
0x180028bfa  xor     r8d, r8d
0x180028bfd  mov     edx, 1F6h
0x180028c02  mov     rax, [rcx]
0x180028c05  mov     rax, [rax+30h]
0x180028c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c0e  test    eax, eax
0x180028c10  mov     ecx, ebp
0x180028c12  mov     edx, 80004005h
0x180028c17  cmovs   ecx, edx
0x180028c1a  mov     eax, ecx
0x180028c1c  jmp     short loc_180028C23
0x180028c1e  mov     eax, 80004005h
0x180028c23  add     rsp, 38h
0x180028c27  pop     r15
0x180028c29  pop     r14
0x180028c2b  pop     rdi
0x180028c2c  pop     rsi
0x180028c2d  pop     rbp
0x180028c2e  pop     rbx
0x180028c2f  retn
```
