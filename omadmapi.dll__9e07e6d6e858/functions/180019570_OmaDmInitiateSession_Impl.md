# OmaDmInitiateSession_Impl

- ea: `0x180019570`
- end: `0x18001967d`
- name: `OmaDmInitiateSession_Impl`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001d7f0`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x180019570`
- `0x180019684`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800195cd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800195cd`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800195ed`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800195ed`

## pseudocode

```c
HRESULT __fastcall OmaDmInitiateSession_Impl(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        WCHAR **a8,
        unsigned int a9,
        int a10,
        int a11)
{
  HRESULT result; // eax
  GUID pguid; // [rsp+60h] [rbp-D8h] BYREF
  OLECHAR sz[64]; // [rsp+70h] [rbp-C8h] BYREF

  pguid = 0;
  memset_0(sz, 0, sizeof(sz));
  result = CoCreateGuid(&pguid);
  if ( result >= 0 )
  {
    if ( StringFromGUID2(&pguid, sz, 64) > 0 )
      return OmaDmInitiateSession_Internal(a1, a2, sz, a3, a4, a5, a6, a7, a8, a9, a10, a11);
    else
      return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x180019570  push    rbx
0x180019572  push    rbp
0x180019573  push    rsi
0x180019574  push    rdi
0x180019575  push    r14
0x180019577  push    r15
0x180019579  sub     rsp, 108h
0x180019580  mov     rax, cs:__security_cookie
0x180019587  xor     rax, rsp
0x18001958a  mov     [rsp+138h+var_48], rax
0x180019592  mov     r14, [rsp+138h+arg_20]
0x18001959a  mov     esi, r8d
0x18001959d  mov     r15, [rsp+138h+arg_38]
0x1800195a5  mov     rdi, rdx
0x1800195a8  mov     rbx, rcx
0x1800195ab  xorps   xmm0, xmm0
0x1800195ae  xor     edx, edx; Val
0x1800195b0  lea     rcx, [rsp+138h+sz]; void *
0x1800195b5  mov     r8d, 80h; Size
0x1800195bb  mov     ebp, r9d
0x1800195be  movups  xmmword ptr [rsp+138h+pguid.Data1], xmm0
0x1800195c3  call    memset_0
0x1800195c8  lea     rcx, [rsp+138h+pguid]; pguid
0x1800195cd  call    cs:__imp_CoCreateGuid
0x1800195d4  nop     dword ptr [rax+rax+00h]
0x1800195d9  test    eax, eax
0x1800195db  js      short loc_18001965C
0x1800195dd  mov     r8d, 40h ; '@'; cchMax
0x1800195e3  lea     rdx, [rsp+138h+sz]; lpsz
0x1800195e8  lea     rcx, [rsp+138h+pguid]; rguid
0x1800195ed  call    cs:__imp_StringFromGUID2
0x1800195f4  nop     dword ptr [rax+rax+00h]
0x1800195f9  test    eax, eax
0x1800195fb  jg      short loc_180019604
0x1800195fd  mov     eax, 80070057h
0x180019602  jmp     short loc_18001965C
0x180019604  mov     eax, [rsp+138h+arg_50]
0x18001960b  lea     r8, [rsp+138h+sz]
0x180019610  mov     [rsp+138h+var_E0], eax; int
0x180019614  mov     r9d, esi
0x180019617  mov     eax, [rsp+138h+arg_48]
0x18001961e  mov     rdx, rdi
0x180019621  mov     [rsp+138h+var_E8], eax; int
0x180019625  mov     rcx, rbx; unsigned __int16 *
0x180019628  mov     eax, [rsp+138h+arg_40]
0x18001962f  mov     [rsp+138h+var_F0], eax; unsigned int
0x180019633  mov     eax, [rsp+138h+arg_30]
0x18001963a  mov     [rsp+138h+var_F8], r15; __int64
0x18001963f  mov     [rsp+138h+var_100], eax; int
0x180019643  mov     eax, [rsp+138h+arg_28]
0x18001964a  mov     [rsp+138h+var_108], eax; unsigned int
0x18001964e  mov     [rsp+138h+var_110], r14; __int64
0x180019653  mov     [rsp+138h+var_118], ebp; unsigned int
0x180019657  call    OmaDmInitiateSession_Internal
0x18001965c  mov     rcx, [rsp+138h+var_48]
0x180019664  xor     rcx, rsp; StackCookie
0x180019667  call    __security_check_cookie
0x18001966c  add     rsp, 108h
0x180019673  pop     r15
0x180019675  pop     r14
0x180019677  pop     rdi
0x180019678  pop     rsi
0x180019679  pop     rbp
0x18001967a  pop     rbx
0x18001967b  retn
```
