# Dfdll::CString::Append(char const *,uint)

- ea: `0x1800020d4`
- end: `0x180002237`
- name: `?Append@CString@Dfdll@@QEAAJPEBDI@Z`
- size: `355`
- prototype: `__int64 __fastcall(Dfdll::CString *__hidden this, LPCCH lpMultiByteStr, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180002558`

## callees

- `0x180001fc8`
- `0x1800020d4`
- `0x180002238`
- `0x180012b30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002139`
- `KERNEL32!GetLastError` at `0x1800021b3`
- `KERNEL32!GetLastError` at `0x180002139`
- `KERNEL32!GetLastError` at `0x1800021b3`
- `KERNEL32!MultiByteToWideChar` at `0x18000212f`
- `KERNEL32!MultiByteToWideChar` at `0x1800021a9`
- `KERNEL32!MultiByteToWideChar` at `0x18000212f`
- `KERNEL32!MultiByteToWideChar` at `0x1800021a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CString::Append(Dfdll::CString *this, LPCCH lpMultiByteStr, unsigned int a3)
{
  int v5; // ebx
  unsigned int v6; // edi
  LPCCH v7; // rax
  signed int v8; // eax
  signed int v9; // eax
  const struct std::nothrow_t *v10; // rdx
  unsigned int v11; // ebx
  signed int LastError; // eax
  const struct std::nothrow_t *v13; // rdx
  const struct std::nothrow_t *v14; // rdx
  void **v16; // [rsp+30h] [rbp-20h] BYREF
  LPWSTR lpWideCharStr; // [rsp+38h] [rbp-18h]
  unsigned int cchWideChar; // [rsp+40h] [rbp-10h]

  if ( lpMultiByteStr )
  {
    v6 = 0;
    if ( a3 )
    {
      v7 = lpMultiByteStr;
      do
      {
        if ( !*v7 )
          break;
        ++v6;
        ++v7;
      }
      while ( v6 < a3 );
    }
    v8 = MultiByteToWideChar(0, 0, lpMultiByteStr, v6, 0, 0);
    if ( v8 > 0 )
    {
      lpWideCharStr = 0;
      cchWideChar = 0;
      v16 = &Dfdll::CBuffer<unsigned short>::`vftable';
      v5 = Dfdll::CBufferBase::Allocate((Dfdll::CBufferBase *)&v16, v8);
      if ( v5 >= 0 )
      {
        v11 = cchWideChar;
        if ( MultiByteToWideChar(0, 0, lpMultiByteStr, v6, lpWideCharStr, cchWideChar) )
        {
          v5 = Dfdll::CString::Append(this, (struct std::nothrow_t *)lpWideCharStr, v11);
          if ( v5 >= 0 )
          {
            v5 = 0;
            v16 = &Dfdll::CBuffer<unsigned short>::`vftable';
            if ( lpWideCharStr )
              operator delete(lpWideCharStr, v14);
          }
          else
          {
            v16 = &Dfdll::CBuffer<unsigned short>::`vftable';
            if ( lpWideCharStr )
              operator delete(lpWideCharStr, v14);
          }
        }
        else
        {
          LastError = GetLastError();
          v5 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v5 = LastError;
          v16 = &Dfdll::CBuffer<unsigned short>::`vftable';
          if ( lpWideCharStr )
            operator delete(lpWideCharStr, v13);
        }
      }
      else
      {
        v16 = &Dfdll::CBuffer<unsigned short>::`vftable';
        if ( lpWideCharStr )
          operator delete(lpWideCharStr, v10);
      }
    }
    else
    {
      v9 = GetLastError();
      v5 = (unsigned __int16)v9 | 0x80070000;
      if ( v9 <= 0 )
        return (unsigned int)v9;
    }
  }
  else
  {
    return 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800020d4  mov     [rsp-18h+arg_0], rbx
0x1800020d9  mov     [rsp-18h+arg_8], rsi
0x1800020de  mov     [rsp-18h+arg_10], rdi
0x1800020e3  push    rbp
0x1800020e4  push    r12
0x1800020e6  push    r14
0x1800020e8  mov     rbp, rsp
0x1800020eb  sub     rsp, 50h
0x1800020ef  mov     rsi, rdx
0x1800020f2  mov     r14, rcx
0x1800020f5  test    rdx, rdx
0x1800020f8  jnz     short loc_180002101
0x1800020fa  xor     ebx, ebx
0x1800020fc  jmp     loc_18000221B
0x180002101  xor     edi, edi
0x180002103  test    r8d, r8d
0x180002106  jz      short loc_18000211A
0x180002108  mov     rax, rsi
0x18000210b  cmp     byte ptr [rax], 0
0x18000210e  jz      short loc_18000211A
0x180002110  inc     edi
0x180002112  inc     rax
0x180002115  cmp     edi, r8d
0x180002118  jb      short loc_18000210B
0x18000211a  and     [rsp+50h+cchWideChar], 0
0x18000211f  and     [rsp+50h+lpWideCharStr], 0
0x180002125  mov     r9d, edi; cbMultiByte
0x180002128  mov     r8, rsi; lpMultiByteStr
0x18000212b  xor     edx, edx; dwFlags
0x18000212d  xor     ecx, ecx; CodePage
0x18000212f  call    cs:__imp_MultiByteToWideChar
0x180002135  test    eax, eax
0x180002137  jg      short loc_180002152
0x180002139  call    cs:__imp_GetLastError
0x18000213f  movzx   ebx, ax
0x180002142  or      ebx, 80070000h
0x180002148  test    eax, eax
0x18000214a  cmovle  ebx, eax
0x18000214d  jmp     loc_18000221B
0x180002152  and     [rbp+var_18], 0
0x180002157  and     [rbp+var_10], 0
0x18000215b  lea     r12, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180002162  mov     [rbp+var_20], r12
0x180002166  mov     edx, eax; unsigned int
0x180002168  lea     rcx, [rbp+var_20]; this
0x18000216c  call    ?Allocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Allocate(uint)
0x180002171  mov     ebx, eax
0x180002173  test    eax, eax
0x180002175  jns     short loc_18000218F
0x180002177  mov     [rbp+var_20], r12
0x18000217b  mov     rcx, [rbp+var_18]; void *
0x18000217f  test    rcx, rcx
0x180002182  jz      short loc_18000218A
0x180002184  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002189  nop
0x18000218a  jmp     loc_18000221B
0x18000218f  mov     ebx, [rbp+var_10]
0x180002192  mov     [rsp+50h+cchWideChar], ebx; cchWideChar
0x180002196  mov     rax, [rbp+var_18]
0x18000219a  mov     [rsp+50h+lpWideCharStr], rax; lpWideCharStr
0x18000219f  mov     r9d, edi; cbMultiByte
0x1800021a2  mov     r8, rsi; lpMultiByteStr
0x1800021a5  xor     edx, edx; dwFlags
0x1800021a7  xor     ecx, ecx; CodePage
0x1800021a9  call    cs:__imp_MultiByteToWideChar
0x1800021af  test    eax, eax
0x1800021b1  jnz     short loc_1800021DC
0x1800021b3  call    cs:__imp_GetLastError
0x1800021b9  movzx   ebx, ax
0x1800021bc  or      ebx, 80070000h
0x1800021c2  test    eax, eax
0x1800021c4  cmovle  ebx, eax
0x1800021c7  mov     [rbp+var_20], r12
0x1800021cb  mov     rcx, [rbp+var_18]; void *
0x1800021cf  test    rcx, rcx
0x1800021d2  jz      short loc_1800021DA
0x1800021d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800021d9  nop
0x1800021da  jmp     short loc_18000221B
0x1800021dc  mov     r8d, ebx; unsigned int
0x1800021df  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x1800021e3  mov     rcx, r14; this
0x1800021e6  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x1800021eb  mov     ebx, eax
0x1800021ed  test    eax, eax
0x1800021ef  jns     short loc_180002206
0x1800021f1  mov     [rbp+var_20], r12
0x1800021f5  mov     rcx, [rbp+var_18]; void *
0x1800021f9  test    rcx, rcx
0x1800021fc  jz      short loc_180002204
0x1800021fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002203  nop
0x180002204  jmp     short loc_18000221B
0x180002206  xor     ebx, ebx
0x180002208  mov     [rbp+var_20], r12
0x18000220c  mov     rcx, [rbp+var_18]; void *
0x180002210  test    rcx, rcx
0x180002213  jz      short loc_18000221B
0x180002215  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000221a  nop
0x18000221b  mov     eax, ebx
0x18000221d  lea     r11, [rsp+50h+var_s0]
0x180002222  mov     rbx, [r11+20h]
0x180002226  mov     rsi, [r11+28h]
0x18000222a  mov     rdi, [r11+30h]
0x18000222e  mov     rsp, r11
0x180002231  pop     r14
0x180002233  pop     r12
0x180002235  pop     rbp
0x180002236  retn
```
