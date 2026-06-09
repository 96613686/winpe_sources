# CPropertySetStream::_ComparePropertyNames(void const *,void const *,int,ulong,long *)

- ea: `0x180025db8`
- end: `0x180025f09`
- name: `?_ComparePropertyNames@CPropertySetStream@@AEBAEPEBX0HKPEAJ@Z`
- size: `337`
- prototype: `unsigned __int8 __usercall@<al>(CPropertySetStream *__hidden this@<rcx>, PCNZWCH lpString1@<rdx>, char *@<r8>, int@<r9d>, unsigned int, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180025c28`
- `0x180025f10`

## callees

- `0x180025db8`
- `0x18005aa7c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e59`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025e16`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025e16`

## pseudocode

```c
unsigned __int8 __fastcall CPropertySetStream::_ComparePropertyNames(
        CPropertySetStream *this,
        const char *lpString1,
        char *a3,
        __int64 a4,
        unsigned int a5,
        unsigned __int16 *a6)
{
  int *v6; // rdi
  unsigned __int16 *v7; // rbp
  unsigned __int16 *v8; // rsi
  const char *lpString2; // r14
  unsigned __int16 v11; // r9
  int v12; // r14d
  signed int LastError; // eax
  unsigned int v15; // r8d
  unsigned __int16 *v16; // [rsp+50h] [rbp+8h] BYREF

  v6 = (int *)a6;
  v7 = 0;
  v8 = 0;
  a6 = 0;
  v16 = 0;
  lpString2 = a3;
  *v6 = 0;
  v11 = *((_WORD *)this + 8);
  if ( v11 != 1200 )
  {
    CPropertySetStream::_MultiByteToWideChar(this, lpString1, (unsigned int)a3, v11, &a6, v6);
    if ( *v6 >= 0 )
    {
      CPropertySetStream::_MultiByteToWideChar(this, lpString2, v15, *((_WORD *)this + 8), &v16, v6);
      if ( *v6 >= 0 )
      {
        v7 = a6;
        v8 = v16;
        lpString1 = (const char *)a6;
        lpString2 = (const char *)v16;
        goto LABEL_2;
      }
      (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 4) + 8LL))(*((_QWORD *)this + 4), a6);
    }
    return 0;
  }
LABEL_2:
  v12 = CompareStringW(
          *((_DWORD *)this + 5),
          (*((_BYTE *)this + 24) & 1) == 0,
          (PCNZWCH)lpString1,
          -1,
          (PCNZWCH)lpString2,
          -1);
  if ( v7 )
    (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 4) + 8LL))(*((_QWORD *)this + 4), v7);
  if ( v8 )
    (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 4) + 8LL))(*((_QWORD *)this + 4), v8);
  if ( v12 != 2 )
  {
    if ( !v12 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *v6 = LastError;
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180025db8  mov     rax, rsp
0x180025dbb  mov     [rax+10h], rbx
0x180025dbf  mov     [rax+18h], rbp
0x180025dc3  push    rsi
0x180025dc4  push    rdi
0x180025dc5  push    r14
0x180025dc7  sub     rsp, 30h
0x180025dcb  mov     rdi, [rsp+48h+arg_28]
0x180025dd0  xor     ebp, ebp
0x180025dd2  xor     esi, esi
0x180025dd4  mov     [rax+30h], rbp
0x180025dd8  mov     [rax+8], rsi
0x180025ddc  mov     r14, r8
0x180025ddf  mov     eax, 4B0h
0x180025de4  mov     rbx, rcx
0x180025de7  mov     dword ptr [rdi], 0
0x180025ded  movzx   r9d, word ptr [rcx+10h]; unsigned __int16
0x180025df2  cmp     r9w, ax
0x180025df6  jnz     short loc_180025E6F
0x180025df8  mov     ecx, [rbx+14h]; Locale
0x180025dfb  or      r9d, 0FFFFFFFFh; cchCount1
0x180025dff  test    byte ptr [rbx+18h], 1
0x180025e03  mov     r8, rdx; lpString1
0x180025e06  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x180025e0b  mov     [rsp+48h+lpString2], r14; lpString2
0x180025e10  jnz     short loc_180025E55
0x180025e12  lea     edx, [r9+2]; dwCmpFlags
0x180025e16  call    cs:__imp_CompareStringW
0x180025e1c  mov     r14d, eax
0x180025e1f  test    rbp, rbp
0x180025e22  jnz     loc_180025ED9
0x180025e28  test    rsi, rsi
0x180025e2b  jnz     loc_180025EF1
0x180025e31  cmp     r14d, 2
0x180025e35  jz      short loc_180025E51
0x180025e37  test    r14d, r14d
0x180025e3a  jz      short loc_180025E59
0x180025e3c  xor     al, al
0x180025e3e  mov     rbx, [rsp+48h+arg_8]
0x180025e43  mov     rbp, [rsp+48h+arg_10]
0x180025e48  add     rsp, 30h
0x180025e4c  pop     r14
0x180025e4e  pop     rdi
0x180025e4f  pop     rsi
0x180025e50  retn
0x180025e51  mov     al, 1
0x180025e53  jmp     short loc_180025E3E
0x180025e55  xor     edx, edx
0x180025e57  jmp     short loc_180025E16
0x180025e59  call    cs:__imp_GetLastError
0x180025e5f  test    eax, eax
0x180025e61  jle     short loc_180025E6B
0x180025e63  movzx   eax, ax
0x180025e66  or      eax, 80070000h
0x180025e6b  mov     [rdi], eax
0x180025e6d  jmp     short loc_180025E3C
0x180025e6f  lea     rax, [rsp+48h+arg_28]
0x180025e74  mov     qword ptr [rsp+48h+cchCount2], rdi; int *
0x180025e79  mov     [rsp+48h+lpString2], rax; unsigned __int16 **
0x180025e7e  call    ?_MultiByteToWideChar@CPropertySetStream@@AEBAXPEBDKGPEAPEAGPEAJ@Z; CPropertySetStream::_MultiByteToWideChar(char const *,ulong,ushort,ushort * *,long *)
0x180025e83  cmp     [rdi], esi
0x180025e85  jl      short loc_180025E3C
0x180025e87  movzx   r9d, word ptr [rbx+10h]; unsigned __int16
0x180025e8c  lea     rax, [rsp+48h+arg_0]
0x180025e91  mov     qword ptr [rsp+48h+cchCount2], rdi; int *
0x180025e96  mov     rdx, r14; char *
0x180025e99  mov     rcx, rbx; this
0x180025e9c  mov     [rsp+48h+lpString2], rax; unsigned __int16 **
0x180025ea1  call    ?_MultiByteToWideChar@CPropertySetStream@@AEBAXPEBDKGPEAPEAGPEAJ@Z; CPropertySetStream::_MultiByteToWideChar(char const *,ulong,ushort,ushort * *,long *)
0x180025ea6  cmp     [rdi], esi
0x180025ea8  jge     short loc_180025EC4
0x180025eaa  mov     rcx, [rbx+20h]
0x180025eae  mov     rdx, [rsp+48h+arg_28]
0x180025eb3  mov     rax, [rcx]
0x180025eb6  mov     rax, [rax+8]
0x180025eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ebf  jmp     loc_180025E3C
0x180025ec4  mov     rbp, [rsp+48h+arg_28]
0x180025ec9  mov     rsi, [rsp+48h+arg_0]
0x180025ece  mov     rdx, rbp
0x180025ed1  mov     r14, rsi
0x180025ed4  jmp     loc_180025DF8
0x180025ed9  mov     rcx, [rbx+20h]
0x180025edd  mov     rdx, rbp
0x180025ee0  mov     rax, [rcx]
0x180025ee3  mov     rax, [rax+8]
0x180025ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025eec  jmp     loc_180025E28
0x180025ef1  mov     rcx, [rbx+20h]
0x180025ef5  mov     rdx, rsi
0x180025ef8  mov     r8, [rcx]
0x180025efb  mov     rax, [r8+8]
0x180025eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f04  jmp     loc_180025E31
```
