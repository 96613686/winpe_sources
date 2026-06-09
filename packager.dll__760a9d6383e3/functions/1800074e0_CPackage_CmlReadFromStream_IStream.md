# CPackage::CmlReadFromStream(IStream *)

- ea: `0x1800074e0`
- end: `0x1800075bb`
- name: `?CmlReadFromStream@CPackage@@IEAAJPEAUIStream@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(void **this, struct IStream *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180009fa0`

## callees

- `0x1800074e0`
- `0x18000a6ec`
- `0x18000a718`
- `0x18000aef4`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180007587`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180007587`

## pseudocode

```c
__int64 __fastcall CPackage::CmlReadFromStream(void **this, struct IStream *a2)
{
  int v4; // ebx
  _DWORD *v5; // rax
  int v6; // ecx
  WCHAR *v7; // rdx
  unsigned __int16 v9[8]; // [rsp+30h] [rbp-228h] BYREF
  CHAR pszSrc[512]; // [rsp+40h] [rbp-218h] BYREF

  v9[0] = 0;
  v4 = ((__int64 (__fastcall *)(struct IStream *, unsigned __int16 *, __int64))a2->lpVtbl->Read)(a2, v9, 2);
  if ( v4 >= 0 )
  {
    v4 = StringReadFromStream(a2, pszSrc, 0x1F4u);
    if ( v4 >= 0 )
    {
      operator delete(this[15]);
      v5 = operator new(0x3ECu);
      this[15] = v5;
      if ( v5 )
      {
        v6 = v9[0];
        *v5 = v9[0];
        v7 = (WCHAR *)this[15];
        *((_DWORD *)this + 33) = v6;
        SHAnsiToUnicode(pszSrc, v7 + 2, 500);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800074e0  mov     [rsp+arg_10], rbx
0x1800074e5  mov     [rsp+arg_18], rsi
0x1800074ea  push    rdi
0x1800074eb  sub     rsp, 250h
0x1800074f2  mov     rax, cs:__security_cookie
0x1800074f9  xor     rax, rsp
0x1800074fc  mov     [rsp+258h+var_18], rax
0x180007504  xor     eax, eax
0x180007506  mov     rsi, rdx
0x180007509  mov     [rsp+258h+var_228], ax
0x18000750e  xor     r9d, r9d
0x180007511  mov     rax, [rdx]
0x180007514  mov     rdi, rcx
0x180007517  lea     rdx, [rsp+258h+var_228]
0x18000751c  mov     rcx, rsi
0x18000751f  lea     r8d, [r9+2]
0x180007523  mov     rax, [rax+18h]
0x180007527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000752c  mov     ebx, eax
0x18000752e  test    eax, eax
0x180007530  js      short loc_180007594
0x180007532  mov     r8d, 1F4h; unsigned int
0x180007538  lea     rdx, [rsp+258h+pszSrc]; char *
0x18000753d  mov     rcx, rsi; struct IStream *
0x180007540  call    ?StringReadFromStream@@YAJPEAUIStream@@PEADI@Z; StringReadFromStream(IStream *,char *,uint)
0x180007545  mov     ebx, eax
0x180007547  test    eax, eax
0x180007549  js      short loc_180007594
0x18000754b  mov     rcx, [rdi+78h]; lpMem
0x18000754f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007554  mov     ecx, 3ECh; unsigned __int64
0x180007559  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000755e  mov     [rdi+78h], rax
0x180007562  test    rax, rax
0x180007565  jz      short loc_18000758F
0x180007567  movzx   ecx, [rsp+258h+var_228]
0x18000756c  mov     r8d, 1F4h; cwchBuf
0x180007572  mov     [rax], ecx
0x180007574  mov     rdx, [rdi+78h]
0x180007578  mov     [rdi+84h], ecx
0x18000757e  add     rdx, 4; pwszDst
0x180007582  lea     rcx, [rsp+258h+pszSrc]; pszSrc
0x180007587  call    cs:__imp_SHAnsiToUnicode
0x18000758d  jmp     short loc_180007594
0x18000758f  mov     ebx, 8007000Eh
0x180007594  mov     eax, ebx
0x180007596  mov     rcx, [rsp+258h+var_18]
0x18000759e  xor     rcx, rsp; StackCookie
0x1800075a1  call    __security_check_cookie
0x1800075a6  lea     r11, [rsp+258h+var_8]
0x1800075ae  mov     rbx, [r11+20h]
0x1800075b2  mov     rsi, [r11+28h]
0x1800075b6  mov     rsp, r11
0x1800075b9  pop     rdi
0x1800075ba  retn
```
