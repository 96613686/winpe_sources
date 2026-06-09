# CTxtPtr::CTxtFinder::FindChar(ushort,CTxtIStream &)

- ea: `0x18003dccc`
- end: `0x18003de68`
- name: `?FindChar@CTxtFinder@CTxtPtr@@AEAAJGAEAVCTxtIStream@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(CTxtPtr::CTxtFinder *__hidden this, unsigned __int16, struct CTxtIStream *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18008390c`

## callees

- `0x18003dccc`
- `0x18003de70`
- `0x18008f3bc`
- `0x1800903d4`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18003dd76`
- `KERNEL32!CompareStringW` at `0x18003dd76`
- `KERNEL32!CompareStringA` at `0x18003dde1`
- `KERNEL32!CompareStringA` at `0x18003dde1`

## pseudocode

```c
__int64 __fastcall CTxtPtr::CTxtFinder::FindChar(
        CTxtPtr::CTxtFinder *this,
        unsigned __int16 a2,
        __int64 (__fastcall **a3)(struct CTxtIStream *))
{
  int v3; // esi
  int v5; // edi
  WCHAR v7; // ax
  unsigned __int16 v8; // r14
  int v9; // r15d
  bool v10; // zf
  WCHAR String1; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR String2; // [rsp+38h] [rbp-C8h] BYREF
  PCNZCH lpString2[66]; // [rsp+40h] [rbp-C0h] BYREF
  int cchCount2; // [rsp+250h] [rbp+150h]
  PCNZCH lpString1[66]; // [rsp+260h] [rbp+160h] BYREF
  int cchCount1; // [rsp+470h] [rbp+370h]

  v3 = *(_DWORD *)this;
  v5 = a2;
  while ( *(_DWORD *)this )
  {
    --*(_DWORD *)this;
    v7 = a3[4]((struct CTxtIStream *)a3);
    v8 = v7;
    if ( *((_DWORD *)this + 2) && (unsigned int)(v5 - 55296) > 0x7FF )
    {
      String2 = v7;
      String1 = v5;
      if ( CW32System::_dwPlatformId == 1 )
      {
        CStrIn::CStrIn((CStrIn *)lpString1, &String1, 1, 0);
        CStrIn::CStrIn((CStrIn *)lpString2, &String2, 1, 0);
        v9 = CompareStringA(0x400u, 0x20001u, lpString1[0], cchCount1, lpString2[0], cchCount2);
        CConvertStr::Free((CConvertStr *)lpString2);
        CConvertStr::Free((CConvertStr *)lpString1);
      }
      else
      {
        v9 = CompareStringW(0x400u, 0x20001u, &String1, 1, &String2, 1);
      }
      v10 = v9 == 2;
    }
    else
    {
      v10 = (_WORD)v5 == v7;
    }
    if ( v10 || !*((_DWORD *)this + 3) && (unsigned int)CW32System::IsAlef(v5) && (unsigned int)CW32System::IsAlef(v8) )
      return (unsigned int)(v3 - *(_DWORD *)this);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18003dccc  push    rbp
0x18003dcce  push    rbx
0x18003dccf  push    rsi
0x18003dcd0  push    rdi
0x18003dcd1  push    r13
0x18003dcd3  push    r14
0x18003dcd5  push    r15
0x18003dcd7  lea     rbp, [rsp-390h]
0x18003dcdf  sub     rsp, 490h
0x18003dce6  mov     rax, cs:__security_cookie
0x18003dced  xor     rax, rsp
0x18003dcf0  mov     [rbp+3C0h+var_40], rax
0x18003dcf7  mov     esi, [rcx]
0x18003dcf9  mov     r13, r8
0x18003dcfc  movzx   edi, dx
0x18003dcff  mov     rbx, rcx
0x18003dd02  mov     eax, [rbx]
0x18003dd04  test    eax, eax
0x18003dd06  jz      loc_18003DE43
0x18003dd0c  dec     eax
0x18003dd0e  mov     rcx, r13
0x18003dd11  mov     [rbx], eax
0x18003dd13  mov     rax, [r13+20h]
0x18003dd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd1c  cmp     dword ptr [rbx+8], 0
0x18003dd20  movzx   r14d, ax
0x18003dd24  jz      loc_18003DE0C
0x18003dd2a  lea     ecx, [rdi-0D800h]
0x18003dd30  cmp     ecx, 7FFh
0x18003dd36  jbe     loc_18003DE0C
0x18003dd3c  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18003dd43  mov     [rsp+4C0h+String2], ax
0x18003dd48  mov     [rsp+4C0h+String1], di
0x18003dd4d  jz      short loc_18003DD87
0x18003dd4f  lea     rax, [rsp+4C0h+String2]
0x18003dd54  mov     [rsp+4C0h+cchCount2], 1; cchCount2
0x18003dd5c  mov     r9d, 1; cchCount1
0x18003dd62  mov     [rsp+4C0h+lpString2], rax; lpString2
0x18003dd67  lea     r8, [rsp+4C0h+String1]; lpString1
0x18003dd6c  mov     edx, 20001h; dwCmpFlags
0x18003dd71  mov     ecx, 400h; Locale
0x18003dd76  call    cs:__imp_CompareStringW
0x18003dd7d  nop     dword ptr [rax+rax+00h]
0x18003dd82  mov     r15d, eax
0x18003dd85  jmp     short loc_18003DE06
0x18003dd87  xor     r9d, r9d; unsigned int
0x18003dd8a  lea     rdx, [rsp+4C0h+String1]; unsigned __int16 *
0x18003dd8f  lea     rcx, [rbp+3C0h+lpString1]; this
0x18003dd96  lea     r8d, [r9+1]; int
0x18003dd9a  call    ??0CStrIn@@QEAA@PEBGHI@Z; CStrIn::CStrIn(ushort const *,int,uint)
0x18003dd9f  xor     r9d, r9d; unsigned int
0x18003dda2  lea     rdx, [rsp+4C0h+String2]; unsigned __int16 *
0x18003dda7  lea     rcx, [rsp+4C0h+var_480]; this
0x18003ddac  lea     r8d, [r9+1]; int
0x18003ddb0  call    ??0CStrIn@@QEAA@PEBGHI@Z; CStrIn::CStrIn(ushort const *,int,uint)
0x18003ddb5  mov     rcx, [rsp+4C0h+var_480]
0x18003ddba  mov     edx, 20001h; dwCmpFlags
0x18003ddbf  mov     eax, [rbp+3C0h+var_270]
0x18003ddc5  mov     r9d, [rbp+3C0h+cchCount1]; cchCount1
0x18003ddcc  mov     r8, [rbp+3C0h+lpString1]; lpString1
0x18003ddd3  mov     [rsp+4C0h+cchCount2], eax; cchCount2
0x18003ddd7  mov     [rsp+4C0h+lpString2], rcx; lpString2
0x18003dddc  mov     ecx, 400h; Locale
0x18003dde1  call    cs:__imp_CompareStringA
0x18003dde8  nop     dword ptr [rax+rax+00h]
0x18003dded  lea     rcx, [rsp+4C0h+var_480]; this
0x18003ddf2  mov     r15d, eax
0x18003ddf5  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x18003ddfa  lea     rcx, [rbp+3C0h+lpString1]; this
0x18003de01  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x18003de06  cmp     r15d, 2
0x18003de0a  jmp     short loc_18003DE10
0x18003de0c  cmp     di, r14w
0x18003de10  jz      short loc_18003DE3D
0x18003de12  cmp     dword ptr [rbx+0Ch], 0
0x18003de16  jnz     loc_18003DD02
0x18003de1c  movzx   ecx, di; unsigned __int16
0x18003de1f  call    ?IsAlef@CW32System@@SAHG@Z; CW32System::IsAlef(ushort)
0x18003de24  test    eax, eax
0x18003de26  jz      loc_18003DD02
0x18003de2c  movzx   ecx, r14w; unsigned __int16
0x18003de30  call    ?IsAlef@CW32System@@SAHG@Z; CW32System::IsAlef(ushort)
0x18003de35  test    eax, eax
0x18003de37  jz      loc_18003DD02
0x18003de3d  sub     esi, [rbx]
0x18003de3f  mov     eax, esi
0x18003de41  jmp     short loc_18003DE46
0x18003de43  or      eax, 0FFFFFFFFh
0x18003de46  mov     rcx, [rbp+3C0h+var_40]
0x18003de4d  xor     rcx, rsp; StackCookie
0x18003de50  call    __security_check_cookie
0x18003de55  add     rsp, 490h
0x18003de5c  pop     r15
0x18003de5e  pop     r14
0x18003de60  pop     r13
0x18003de62  pop     rdi
0x18003de63  pop     rsi
0x18003de64  pop     rbx
0x18003de65  pop     rbp
0x18003de66  retn
```
