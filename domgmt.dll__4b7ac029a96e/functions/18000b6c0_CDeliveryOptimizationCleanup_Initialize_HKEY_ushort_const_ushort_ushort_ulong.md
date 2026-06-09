# CDeliveryOptimizationCleanup::Initialize(HKEY__ *,ushort const *,ushort * *,ushort * *,ulong *)

- ea: `0x18000b6c0`
- end: `0x18000b7d5`
- name: `?Initialize@CDeliveryOptimizationCleanup@@UEAAJPEAUHKEY__@@PEBGPEAPEAG2PEAK@Z`
- size: `277`
- prototype: `__int64 __fastcall(CDeliveryOptimizationCleanup *this, HKEY, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001ba0`
- `0x180005964`
- `0x18000b6c0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000b78d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000b78d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b777`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b777`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsSameRootW` at `0x18000b7a4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsSameRootW` at `0x18000b7a4`

## pseudocode

```c
__int64 __fastcall CDeliveryOptimizationCleanup::Initialize(
        CDeliveryOptimizationCleanup *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  LPVOID *v9; // rbx
  __int64 v10; // rcx
  HRESULT Instance; // ecx
  int ppv; // [rsp+20h] [rbp-248h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  if ( !a3 )
  {
    v6 = 10;
LABEL_3:
    v7 = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\management\\cleanup.cpp",
      (const char *)v7,
      ppv);
    return v7;
  }
  if ( !*a3 )
  {
    v7 = -2147024809;
    v6 = 11;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v6 = 12;
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v6 = 13;
    goto LABEL_3;
  }
  *a5 = 0;
  *a4 = 0;
  v9 = (LPVOID *)((char *)this + 16);
  v10 = *((_QWORD *)this + 2);
  if ( v10 )
  {
    *v9 = 0;
    (*(void (__fastcall **)(__int64, HKEY))(*(_QWORD *)v10 + 16LL))(v10, a2);
  }
  Instance = CoCreateInstance(
               &GUID_5b99fa76_721c_423c_adac_56d03c8a8007,
               0,
               4u,
               &GUID_6692fd56_3b9b_433a_ac04_3ffb442556dd,
               v9);
  if ( Instance >= 0 )
  {
    if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
      return (unsigned int)-2147024774;
    else
      return !PathIsSameRootW(Buffer, a3);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000b6c0  push    rbx
0x18000b6c2  push    rsi
0x18000b6c3  push    rdi
0x18000b6c4  sub     rsp, 250h
0x18000b6cb  mov     rax, cs:__security_cookie
0x18000b6d2  xor     rax, rsp
0x18000b6d5  mov     [rsp+268h+var_28], rax
0x18000b6dd  mov     rdi, r8
0x18000b6e0  mov     rax, [rsp+268h+arg_20]
0x18000b6e8  xor     esi, esi
0x18000b6ea  test    r8, r8
0x18000b6ed  jnz     short loc_18000B715
0x18000b6ef  lea     edx, [rsi+0Ah]; void *
0x18000b6f2  mov     ebx, 80004003h
0x18000b6f7  lea     r8, aOnecoreEnduser_2; "onecore\\enduser\\deliveryoptimization"...
0x18000b6fe  mov     r9d, ebx; char *
0x18000b701  mov     rcx, [rsp+268h]; this
0x18000b709  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b70e  mov     eax, ebx
0x18000b710  jmp     loc_18000B7BA
0x18000b715  cmp     [r8], si
0x18000b719  jnz     short loc_18000B727
0x18000b71b  mov     ebx, 80070057h
0x18000b720  mov     edx, 0Bh
0x18000b725  jmp     short loc_18000B6F7
0x18000b727  test    r9, r9
0x18000b72a  jnz     short loc_18000B732
0x18000b72c  lea     edx, [r9+0Ch]
0x18000b730  jmp     short loc_18000B6F2
0x18000b732  test    rax, rax
0x18000b735  jnz     short loc_18000B73C
0x18000b737  lea     edx, [rax+0Dh]
0x18000b73a  jmp     short loc_18000B6F2
0x18000b73c  mov     [rax], rsi
0x18000b73f  mov     [r9], rsi
0x18000b742  lea     rbx, [rcx+10h]
0x18000b746  mov     rcx, [rbx]
0x18000b749  test    rcx, rcx
0x18000b74c  jz      short loc_18000B75E
0x18000b74e  mov     [rbx], rsi
0x18000b751  mov     rax, [rcx]
0x18000b754  mov     rax, [rax+10h]
0x18000b758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b75d  nop
0x18000b75e  mov     qword ptr [rsp+268h+ppv], rbx; ppv
0x18000b763  lea     r9, _GUID_6692fd56_3b9b_433a_ac04_3ffb442556dd; riid
0x18000b76a  xor     edx, edx; pUnkOuter
0x18000b76c  lea     r8d, [rdx+4]; dwClsContext
0x18000b770  lea     rcx, _GUID_5b99fa76_721c_423c_adac_56d03c8a8007; rclsid
0x18000b777  call    cs:__imp_CoCreateInstance
0x18000b77d  mov     ecx, eax
0x18000b77f  test    eax, eax
0x18000b781  js      short loc_18000B7B8
0x18000b783  mov     edx, 104h; uSize
0x18000b788  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x18000b78d  call    cs:__imp_GetSystemDirectoryW
0x18000b793  dec     eax
0x18000b795  cmp     eax, 102h
0x18000b79a  ja      short loc_18000B7B3
0x18000b79c  mov     rdx, rdi; pszPath2
0x18000b79f  lea     rcx, [rsp+268h+Buffer]; pszPath1
0x18000b7a4  call    cs:__imp_PathIsSameRootW
0x18000b7aa  mov     ecx, esi
0x18000b7ac  test    eax, eax
0x18000b7ae  setz    cl
0x18000b7b1  jmp     short loc_18000B7B8
0x18000b7b3  mov     ecx, 8007007Ah
0x18000b7b8  mov     eax, ecx
0x18000b7ba  mov     rcx, [rsp+268h+var_28]
0x18000b7c2  xor     rcx, rsp; StackCookie
0x18000b7c5  call    __security_check_cookie
0x18000b7ca  add     rsp, 250h
0x18000b7d1  pop     rdi
0x18000b7d2  pop     rsi
0x18000b7d3  pop     rbx
0x18000b7d4  retn
```
