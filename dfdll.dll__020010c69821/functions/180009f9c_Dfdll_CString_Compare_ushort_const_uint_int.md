# Dfdll::CString::Compare(ushort const *,uint,int &)

- ea: `0x180009f9c`
- end: `0x18000a040`
- name: `?Compare@CString@Dfdll@@QEAAJPEBGIAEAH@Z`
- size: `164`
- prototype: `int(Dfdll::CString *__hidden this, const unsigned __int16 *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a21c`

## callees

- `0x180009f9c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a002`
- `KERNEL32!GetLastError` at `0x18000a002`
- `KERNEL32!CompareStringW` at `0x180009ff6`
- `KERNEL32!CompareStringW` at `0x180009ff6`

## pseudocode

```c
__int64 __fastcall Dfdll::CString::Compare(
        Dfdll::CString *this,
        const unsigned __int16 *lpString2,
        unsigned int a3,
        int *a4)
{
  unsigned int v6; // ecx
  unsigned int cchCount2; // eax
  const unsigned __int16 *v8; // rcx
  int v9; // ecx
  signed int LastError; // eax
  int v11; // eax

  if ( lpString2 )
  {
    cchCount2 = 0;
    if ( a3 )
    {
      v8 = lpString2;
      do
      {
        if ( !*v8 )
          break;
        ++cchCount2;
        ++v8;
      }
      while ( cchCount2 < a3 );
    }
    v9 = CompareStringW(0x400u, 0, *((PCNZWCH *)this + 2), *((_DWORD *)this + 8), lpString2, cchCount2);
    if ( v9 )
    {
      if ( v9 == 2 )
      {
        *a4 = 0;
      }
      else
      {
        v11 = -1;
        if ( v9 == 3 )
          v11 = 1;
        *a4 = v11;
      }
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v6 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        return (unsigned int)LastError;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180009f9c  mov     [rsp+arg_0], rbx
0x180009fa1  mov     [rsp+arg_8], rsi
0x180009fa6  push    rdi
0x180009fa7  sub     rsp, 30h
0x180009fab  xor     edi, edi
0x180009fad  mov     rbx, r9
0x180009fb0  mov     r10, rcx
0x180009fb3  test    rdx, rdx
0x180009fb6  jnz     short loc_180009FBF
0x180009fb8  mov     ecx, 80070057h
0x180009fbd  jmp     short loc_18000A02E
0x180009fbf  mov     eax, edi
0x180009fc1  mov     esi, 1
0x180009fc6  test    r8d, r8d
0x180009fc9  jz      short loc_180009FDE
0x180009fcb  mov     rcx, rdx
0x180009fce  cmp     [rcx], di
0x180009fd1  jz      short loc_180009FDE
0x180009fd3  add     eax, esi
0x180009fd5  add     rcx, 2
0x180009fd9  cmp     eax, r8d
0x180009fdc  jb      short loc_180009FCE
0x180009fde  mov     r9d, [r10+20h]; cchCount1
0x180009fe2  mov     ecx, 400h; Locale
0x180009fe7  mov     r8, [r10+10h]; lpString1
0x180009feb  mov     [rsp+38h+cchCount2], eax; cchCount2
0x180009fef  mov     [rsp+38h+lpString2], rdx; lpString2
0x180009ff4  xor     edx, edx; dwCmpFlags
0x180009ff6  call    cs:__imp_CompareStringW
0x180009ffc  mov     ecx, eax
0x180009ffe  test    eax, eax
0x18000a000  jnz     short loc_18000A018
0x18000a002  call    cs:__imp_GetLastError
0x18000a008  movzx   ecx, ax
0x18000a00b  or      ecx, 80070000h
0x18000a011  test    eax, eax
0x18000a013  cmovle  ecx, eax
0x18000a016  jmp     short loc_18000A02E
0x18000a018  cmp     ecx, 2
0x18000a01b  jnz     short loc_18000A021
0x18000a01d  mov     [rbx], edi
0x18000a01f  jmp     short loc_18000A02C
0x18000a021  or      eax, 0FFFFFFFFh
0x18000a024  cmp     ecx, 3
0x18000a027  cmovz   eax, esi
0x18000a02a  mov     [rbx], eax
0x18000a02c  mov     ecx, edi
0x18000a02e  mov     rbx, [rsp+38h+arg_0]
0x18000a033  mov     eax, ecx
0x18000a035  mov     rsi, [rsp+38h+arg_8]
0x18000a03a  add     rsp, 30h
0x18000a03e  pop     rdi
0x18000a03f  retn
```
