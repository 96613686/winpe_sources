# CFveApiBase::GetProtectionDescriptorFromDpapiNgInfo(_FVE_DPAPI_NG_INFO const *,ushort * *)

- ea: `0x180085750`
- end: `0x180085877`
- name: `?GetProtectionDescriptorFromDpapiNgInfo@CFveApiBase@@MEBAJPEBU_FVE_DPAPI_NG_INFO@@PEAPEAG@Z`
- size: `295`
- prototype: `__int64 __fastcall(CFveApiBase *__hidden this, const struct _FVE_DPAPI_NG_INFO *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000ba30`
- `0x180037f50`
- `0x180085750`
- `0x18011f010`

## import_xrefs

- `ncrypt!NCryptGetProtectionDescriptorInfo` at `0x1800857f5`
- `ncrypt!NCryptGetProtectionDescriptorInfo` at `0x1800857f5`
- `ncrypt!NCryptUnprotectSecret` at `0x1800857cc`
- `ncrypt!NCryptUnprotectSecret` at `0x1800857cc`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x180085826`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x1801243be`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x180085826`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x1801243be`

## pseudocode

```c
__int64 __fastcall CFveApiBase::GetProtectionDescriptorFromDpapiNgInfo(
        CFveApiBase *this,
        const struct _FVE_DPAPI_NG_INFO *a2,
        unsigned __int16 **a3)
{
  int v4; // eax
  int ProtectionDescriptorInfo; // ebx
  void *lpMem; // [rsp+48h] [rbp-30h] BYREF
  __int64 v8; // [rsp+50h] [rbp-28h] BYREF
  void *v9; // [rsp+58h] [rbp-20h] BYREF
  unsigned __int64 v10; // [rsp+60h] [rbp-18h] BYREF

  v8 = 0;
  lpMem = 0;
  v9 = 0;
  LODWORD(v10) = 0;
  v4 = NCryptUnprotectSecret(&v8, 1, (char *)a2 + 8);
  ProtectionDescriptorInfo = v4;
  if ( v4 >= 0 )
  {
    ProtectionDescriptorInfo = NCryptGetProtectionDescriptorInfo(
                                 v8,
                                 &qword_18012C7E0,
                                 1,
                                 &lpMem,
                                 &qword_18012C7E0,
                                 0,
                                 &v9,
                                 &v10,
                                 v4);
    if ( ProtectionDescriptorInfo >= 0 )
    {
      *a3 = (unsigned __int16 *)lpMem;
      lpMem = 0;
    }
  }
  if ( v8 )
    NCryptCloseProtectionDescriptor();
  if ( lpMem )
    CFveApiBase::FastFree(lpMem);
  if ( v9 )
    CFveApiBase::ZeroFree(v9, (unsigned int)v10);
  return (unsigned int)ProtectionDescriptorInfo;
}

```

## disassembly

```asm
0x180085750  mov     r11, rsp
0x180085753  mov     [r11+8], rbx
0x180085757  mov     [r11+20h], rdi
0x18008575b  push    r14
0x18008575d  sub     rsp, 70h
0x180085761  mov     rax, cs:__security_cookie
0x180085768  xor     rax, rsp
0x18008576b  mov     [rsp+78h+var_10], rax
0x180085770  mov     rdi, r8
0x180085773  mov     qword ptr [r11-28h], 0
0x18008577b  mov     qword ptr [r11-30h], 0
0x180085783  lea     r8, [rdx+8]
0x180085787  movzx   r9d, word ptr [rdx+4]
0x18008578c  sub     r9d, 8
0x180085790  mov     qword ptr [r11-20h], 0
0x180085798  mov     dword ptr [rsp+78h+var_18], 0
0x1800857a0  lea     rax, [r11-18h]
0x1800857a4  mov     [r11-40h], rax
0x1800857a8  lea     rax, [r11-20h]
0x1800857ac  mov     [r11-48h], rax
0x1800857b0  mov     qword ptr [r11-50h], 0
0x1800857b8  lea     r14, qword_18012C7E0
0x1800857bf  mov     [r11-58h], r14
0x1800857c3  mov     edx, 1
0x1800857c8  lea     rcx, [r11-28h]
0x1800857cc  call    cs:__imp_NCryptUnprotectSecret
0x1800857d3  nop     dword ptr [rax+rax+00h]
0x1800857d8  mov     ebx, eax
0x1800857da  mov     [rsp+78h+var_38], eax
0x1800857de  test    eax, eax
0x1800857e0  js      short loc_18008581C
0x1800857e2  lea     r9, [rsp+78h+lpMem]
0x1800857e7  mov     r8d, 1
0x1800857ed  mov     rdx, r14
0x1800857f0  mov     rcx, [rsp+78h+var_28]
0x1800857f5  call    cs:__imp_NCryptGetProtectionDescriptorInfo
0x1800857fc  nop     dword ptr [rax+rax+00h]
0x180085801  mov     ebx, eax
0x180085803  mov     [rsp+78h+var_38], eax
0x180085807  test    eax, eax
0x180085809  js      short loc_18008581C
0x18008580b  mov     rax, [rsp+78h+lpMem]
0x180085810  mov     [rdi], rax
0x180085813  mov     [rsp+78h+lpMem], 0
0x18008581c  mov     rcx, [rsp+78h+var_28]
0x180085821  test    rcx, rcx
0x180085824  jz      short loc_180085832
0x180085826  call    cs:__imp_NCryptCloseProtectionDescriptor
0x18008582d  nop     dword ptr [rax+rax+00h]
0x180085832  mov     rcx, [rsp+78h+lpMem]; lpMem
0x180085837  test    rcx, rcx
0x18008583a  jz      short loc_180085841
0x18008583c  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180085841  mov     rcx, [rsp+78h+var_20]; lpMem
0x180085846  test    rcx, rcx
0x180085849  jz      short loc_180085854
0x18008584b  mov     edx, dword ptr [rsp+78h+var_18]; unsigned __int64
0x18008584f  call    ?ZeroFree@CFveApiBase@@SAJPEAX_K@Z; CFveApiBase::ZeroFree(void *,unsigned __int64)
0x180085854  mov     eax, ebx
0x180085856  mov     rcx, [rsp+78h+var_10]
0x18008585b  xor     rcx, rsp; StackCookie
0x18008585e  call    __security_check_cookie
0x180085863  lea     r11, [rsp+78h+var_8]
0x180085868  mov     rbx, [r11+10h]
0x18008586c  mov     rdi, [r11+28h]
0x180085870  mov     rsp, r11
0x180085873  pop     r14
0x180085875  retn
0x1801243ac  push    rbp
0x1801243ae  sub     rsp, 40h
0x1801243b2  mov     rbp, rdx
0x1801243b5  mov     rcx, [rbp+50h]
0x1801243b9  test    rcx, rcx
0x1801243bc  jz      short loc_1801243CB
0x1801243be  call    cs:__imp_NCryptCloseProtectionDescriptor
0x1801243c5  nop     dword ptr [rax+rax+00h]
0x1801243ca  nop
0x1801243cb  mov     rcx, [rbp+48h]; lpMem
0x1801243cf  test    rcx, rcx
0x1801243d2  jz      short loc_1801243DA
0x1801243d4  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x1801243d9  nop
0x1801243da  mov     rcx, [rbp+58h]; lpMem
0x1801243de  test    rcx, rcx
0x1801243e1  jz      short loc_1801243EC
0x1801243e3  mov     edx, [rbp+60h]; unsigned __int64
0x1801243e6  call    ?ZeroFree@CFveApiBase@@SAJPEAX_K@Z; CFveApiBase::ZeroFree(void *,unsigned __int64)
0x1801243eb  nop
0x1801243ec  add     rsp, 40h
0x1801243f0  pop     rbp
0x1801243f1  retn
```
