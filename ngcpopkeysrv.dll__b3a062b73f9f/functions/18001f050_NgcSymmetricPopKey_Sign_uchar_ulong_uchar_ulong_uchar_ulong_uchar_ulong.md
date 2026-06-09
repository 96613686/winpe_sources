# NgcSymmetricPopKey::Sign(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18001f050`
- end: `0x18001f1ca`
- name: `?Sign@NgcSymmetricPopKey@@UEAAJPEAEK0K0KPEAPEAEPEAK@Z`
- size: `378`
- prototype: `__int64 __fastcall(NgcSymmetricPopKey *this, unsigned __int8 *, int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180004de0`
- `0x18000b0fc`
- `0x180011f94`
- `0x180013270`
- `0x18001368c`
- `0x18001f050`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f19a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f19a`
- `bcrypt!BCryptHash` at `0x18001f16a`
- `bcrypt!BCryptHash` at `0x18001f16a`

## string_xrefs

- `0x18001f0c4`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\symmetricpopkeybase.cpp`
- `0x18001f17c`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\symmetricpopkeybase.cpp`

## pseudocode

```c
__int64 __fastcall NgcSymmetricPopKey::Sign(
        NgcSymmetricPopKey *this,
        unsigned __int8 *a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 **a8,
        unsigned int *a9)
{
  int v13; // ebx
  __int64 v14; // rdx
  __int64 result; // rax
  unsigned __int8 *v16; // rbx
  int v17; // eax
  unsigned int v18; // edi
  unsigned int v19; // [rsp+20h] [rbp-98h]
  HLOCAL hMem; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v21[32]; // [rsp+48h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( !CanUseTpmTransportKey(1)
    && (*(unsigned __int8 (__fastcall **)(NgcSymmetricPopKey *))(*(_QWORD *)this + 56LL))(this) )
  {
    v13 = -2146893792;
    v14 = 27;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\symmetricpopkeybase.cpp",
      (const char *)(unsigned int)v13,
      v19);
    return (unsigned int)v13;
  }
  v19 = a7;
  v13 = (*(__int64 (__fastcall **)(NgcSymmetricPopKey *, unsigned __int8 *, _QWORD, unsigned __int8 *))(*(_QWORD *)this + 48LL))(
          this,
          a4,
          a5,
          a6);
  if ( v13 < 0 )
  {
    v14 = 36;
    goto LABEL_4;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, 32);
  v16 = (unsigned __int8 *)hMem;
  if ( !hMem )
  {
    v13 = -2147024882;
    v14 = 40;
    goto LABEL_4;
  }
  v17 = BCryptHash(177, v21, 32, a2);
  if ( v17 >= 0 )
  {
    *a8 = v16;
    result = 0;
    *a9 = 32;
  }
  else
  {
    v18 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x31,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\symmetricpopkeybase.cpp",
            (const char *)(unsigned int)v17,
            a3);
    if ( v16 )
      LocalFree(v16);
    return v18;
  }
  return result;
}

```

## disassembly

```asm
0x18001f050  push    rbx
0x18001f052  push    rbp
0x18001f053  push    rsi
0x18001f054  push    rdi
0x18001f055  push    r12
0x18001f057  push    r13
0x18001f059  push    r14
0x18001f05b  push    r15
0x18001f05d  sub     rsp, 78h
0x18001f061  mov     rax, cs:__security_cookie
0x18001f068  xor     rax, rsp
0x18001f06b  mov     [rsp+0B8h+var_50], rax
0x18001f070  mov     r12, [rsp+0B8h+arg_28]
0x18001f078  mov     rbx, rcx
0x18001f07b  mov     rdi, [rsp+0B8h+arg_38]
0x18001f083  mov     cl, 1; bool
0x18001f085  mov     rsi, [rsp+0B8h+arg_40]
0x18001f08d  mov     r15, r9
0x18001f090  mov     r14d, r8d
0x18001f093  mov     rbp, rdx
0x18001f096  call    ?CanUseTpmTransportKey@@YA_N_N@Z; CanUseTpmTransportKey(bool)
0x18001f09b  test    al, al
0x18001f09d  jnz     short loc_18001F0DA
0x18001f09f  mov     rax, [rbx]
0x18001f0a2  mov     rcx, rbx
0x18001f0a5  mov     rax, [rax+38h]
0x18001f0a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0ae  test    al, al
0x18001f0b0  jz      short loc_18001F0DA
0x18001f0b2  mov     ebx, 80090020h
0x18001f0b7  mov     edx, 1Bh; void *
0x18001f0bc  mov     rcx, [rsp+0B8h]; this
0x18001f0c4  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001f0cb  mov     r9d, ebx; char *
0x18001f0ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f0d3  mov     eax, ebx
0x18001f0d5  jmp     loc_18001F1AC
0x18001f0da  mov     r8d, [rsp+0B8h+arg_30]
0x18001f0e2  lea     rcx, [rsp+0B8h+var_70]
0x18001f0e7  mov     rax, [rbx]
0x18001f0ea  mov     r13d, 20h ; ' '
0x18001f0f0  mov     [rsp+0B8h+var_88], r13d
0x18001f0f5  mov     r9, r12
0x18001f0f8  mov     [rsp+0B8h+var_90], rcx
0x18001f0fd  mov     rdx, r15
0x18001f100  mov     [rsp+0B8h+var_98], r8d
0x18001f105  mov     rcx, rbx
0x18001f108  mov     r8d, [rsp+0B8h+arg_20]
0x18001f110  mov     rax, [rax+30h]
0x18001f114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f119  mov     ebx, eax
0x18001f11b  test    eax, eax
0x18001f11d  jns     short loc_18001F125
0x18001f11f  lea     edx, [r13+4]
0x18001f123  jmp     short loc_18001F0BC
0x18001f125  mov     rdx, r13
0x18001f128  lea     rcx, [rsp+0B8h+hMem]
0x18001f12d  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18001f132  mov     rbx, [rsp+0B8h+hMem]
0x18001f137  test    rbx, rbx
0x18001f13a  jnz     short loc_18001F14B
0x18001f13c  mov     ebx, 8007000Eh
0x18001f141  mov     edx, 28h ; '('
0x18001f146  jmp     loc_18001F0BC
0x18001f14b  mov     [rsp+0B8h+var_88], r13d
0x18001f150  lea     rdx, [rsp+0B8h+var_70]
0x18001f155  mov     [rsp+0B8h+var_90], rbx
0x18001f15a  mov     r9, rbp
0x18001f15d  mov     r8d, r13d
0x18001f160  mov     [rsp+0B8h+var_98], r14d; int
0x18001f165  mov     ecx, 0B1h
0x18001f16a  call    cs:__imp_BCryptHash
0x18001f170  test    eax, eax
0x18001f172  jns     short loc_18001F1A4
0x18001f174  mov     rcx, [rsp+0B8h]; this
0x18001f17c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001f183  mov     r9d, eax; char *
0x18001f186  mov     edx, 31h ; '1'; void *
0x18001f18b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001f190  mov     edi, eax
0x18001f192  test    rbx, rbx
0x18001f195  jz      short loc_18001F1A0
0x18001f197  mov     rcx, rbx; hMem
0x18001f19a  call    cs:__imp_LocalFree
0x18001f1a0  mov     eax, edi
0x18001f1a2  jmp     short loc_18001F1AC
0x18001f1a4  mov     [rdi], rbx
0x18001f1a7  xor     eax, eax
0x18001f1a9  mov     [rsi], r13d
0x18001f1ac  mov     rcx, [rsp+0B8h+var_50]
0x18001f1b1  xor     rcx, rsp; StackCookie
0x18001f1b4  call    __security_check_cookie
0x18001f1b9  add     rsp, 78h
0x18001f1bd  pop     r15
0x18001f1bf  pop     r14
0x18001f1c1  pop     r13
0x18001f1c3  pop     r12
0x18001f1c5  pop     rdi
0x18001f1c6  pop     rsi
0x18001f1c7  pop     rbp
0x18001f1c8  pop     rbx
0x18001f1c9  retn
```
