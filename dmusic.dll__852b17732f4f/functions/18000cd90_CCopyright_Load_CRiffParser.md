# CCopyright::Load(CRiffParser *)

- ea: `0x18000cd90`
- end: `0x18000cf76`
- name: `?Load@CCopyright@@QEAAJPEAVCRiffParser@@@Z`
- size: `486`
- prototype: `__int64 __fastcall(CCopyright *this, struct CRiffParser *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000c5f8`
- `0x18000e178`
- `0x180014834`

## callees

- `0x1800012c4`
- `0x1800012d0`
- `0x1800016d0`
- `0x180005e08`
- `0x180006320`
- `0x18000cd90`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000ceb5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000ceb5`

## pseudocode

```c
__int64 __fastcall CCopyright::Load(CCopyright *this, struct CRiffParser *a2)
{
  unsigned __int64 v4; // rdx
  __int64 v5; // rcx
  char *v6; // rax
  int v7; // eax
  void *v8; // rax
  unsigned __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned int v12; // edi
  void *v13; // rcx
  void *v14; // rcx
  void *v16; // rcx
  void *v17; // rcx
  int v18; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v19[2]; // [rsp+38h] [rbp-31h] BYREF
  __int64 v20; // [rsp+48h] [rbp-21h]
  __int64 v21; // [rsp+50h] [rbp-19h]
  CHAR MultiByteStr[64]; // [rsp+60h] [rbp-9h] BYREF

  v20 = *((_QWORD *)a2 + 2);
  *((_QWORD *)a2 + 3) = v20;
  v18 = 0;
  *((_QWORD *)a2 + 2) = v19;
  v19[0] = 0;
  v19[1] = 0;
  v21 = 0;
  *((_DWORD *)a2 + 1) = 1;
  while ( 1 )
  {
    do
    {
      while ( 1 )
      {
        if ( !(unsigned int)CRiffParser::NextChunk(a2, &v18) )
        {
          v10 = *((_QWORD *)a2 + 2);
          if ( v10 )
          {
            v11 = *(_QWORD *)(v10 + 16);
            *((_QWORD *)a2 + 2) = v11;
            if ( v11 )
              *((_QWORD *)a2 + 3) = *(_QWORD *)(v11 + 16);
          }
          v12 = v18;
          if ( v18 < 0 )
          {
            v13 = (void *)*((_QWORD *)this + 2);
            if ( v13 )
            {
              operator delete(v13, v9);
              *((_QWORD *)this + 2) = 0;
            }
            v14 = (void *)*((_QWORD *)this + 1);
            if ( v14 )
            {
              operator delete(v14, v9);
              *((_QWORD *)this + 1) = 0;
            }
            *(_BYTE *)this = 0;
          }
          return v12;
        }
        if ( LODWORD(v19[0]) != 1296125513 )
          break;
        if ( (*(_BYTE *)this & 4) != 0 )
        {
          v8 = operator new[](0x80u);
          *((_QWORD *)this + 1) = v8;
          if ( v8 )
          {
            v18 = CRiffParser::Read(a2, MultiByteStr, 0x40u);
            MultiByteStr[63] = 0;
            if ( v18 >= 0 )
              MultiByteToWideChar(0, 0, MultiByteStr, -1, *((LPWSTR *)this + 1), 64);
          }
          else
          {
            v18 = -2147024882;
          }
        }
        *(_BYTE *)this |= 2u;
      }
    }
    while ( LODWORD(v19[0]) != 1347371849 );
    *(_BYTE *)this |= 1u;
    v4 = *(unsigned int *)(*((_QWORD *)a2 + 2) + 4LL);
    if ( (unsigned int)v4 > 0xFFFFFFF3 )
      break;
    v5 = 0;
    if ( (unsigned int)v4 >= 4 )
      v5 = (unsigned int)(v4 - 4);
    *((_DWORD *)this + 6) = v5;
    v6 = (char *)operator new[]((v5 + 15) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 2) = v6;
    if ( v6 )
    {
      v7 = CRiffParser::Read(a2, v6 + 4, *(_DWORD *)(*((_QWORD *)a2 + 2) + 4LL));
      **((_DWORD **)this + 2) = *(_DWORD *)(*((_QWORD *)a2 + 2) + 4LL);
    }
    else
    {
      v7 = -2147024882;
    }
    v18 = v7;
  }
  v16 = (void *)*((_QWORD *)this + 2);
  if ( v16 )
  {
    operator delete(v16, v4);
    *((_QWORD *)this + 2) = 0;
  }
  v17 = (void *)*((_QWORD *)this + 1);
  if ( v17 )
  {
    operator delete(v17, v4);
    *((_QWORD *)this + 1) = 0;
  }
  *(_BYTE *)this = 0;
  return 1462;
}

```

## disassembly

```asm
0x18000cd90  mov     [rsp-8+arg_10], rbx
0x18000cd95  push    rbp
0x18000cd96  push    rsi
0x18000cd97  push    rdi
0x18000cd98  lea     rbp, [rsp-47h]
0x18000cd9d  sub     rsp, 0B0h
0x18000cda4  mov     rax, cs:__security_cookie
0x18000cdab  xor     rax, rsp
0x18000cdae  mov     [rbp+57h+var_20], rax
0x18000cdb2  mov     rax, [rdx+10h]
0x18000cdb6  xor     esi, esi
0x18000cdb8  mov     [rbp+57h+var_78], rax
0x18000cdbc  mov     rdi, rdx
0x18000cdbf  mov     [rdx+18h], rax
0x18000cdc3  mov     rbx, rcx
0x18000cdc6  lea     rax, [rbp+57h+var_88]
0x18000cdca  mov     [rbp+57h+var_90], esi
0x18000cdcd  mov     [rdx+10h], rax
0x18000cdd1  mov     [rbp+57h+var_88], rsi
0x18000cdd5  mov     [rbp+57h+var_80], rsi
0x18000cdd9  mov     [rbp+57h+var_70], rsi
0x18000cddd  mov     dword ptr [rdx+4], 1
0x18000cde4  jmp     loc_18000CEC7
0x18000cde9  cmp     dword ptr [rbp+57h+var_88], 4D414E49h
0x18000cdf0  jz      short loc_18000CE63
0x18000cdf2  cmp     dword ptr [rbp+57h+var_88], 504F4349h
0x18000cdf9  jnz     loc_18000CEC7
0x18000cdff  or      byte ptr [rbx], 1
0x18000ce02  mov     rax, [rdi+10h]
0x18000ce06  mov     edx, [rax+4]; unsigned __int64
0x18000ce09  cmp     edx, 0FFFFFFF3h
0x18000ce0c  ja      loc_18000CF48
0x18000ce12  cmp     edx, 4
0x18000ce15  lea     eax, [rdx-4]
0x18000ce18  mov     ecx, esi
0x18000ce1a  cmovnb  ecx, eax
0x18000ce1d  mov     [rbx+18h], ecx
0x18000ce20  add     rcx, 0Fh
0x18000ce24  and     rcx, 0FFFFFFFFFFFFFFF8h; unsigned __int64
0x18000ce28  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ce2d  mov     [rbx+10h], rax
0x18000ce31  test    rax, rax
0x18000ce34  jz      short loc_18000CE59
0x18000ce36  mov     r8, [rdi+10h]
0x18000ce3a  lea     rdx, [rax+4]; void *
0x18000ce3e  mov     rcx, rdi; this
0x18000ce41  mov     r8d, [r8+4]; unsigned int
0x18000ce45  call    ?Read@CRiffParser@@QEAAJPEAXK@Z; CRiffParser::Read(void *,ulong)
0x18000ce4a  mov     rcx, [rdi+10h]
0x18000ce4e  mov     rdx, [rbx+10h]
0x18000ce52  mov     ecx, [rcx+4]
0x18000ce55  mov     [rdx], ecx
0x18000ce57  jmp     short loc_18000CE5E
0x18000ce59  mov     eax, 8007000Eh
0x18000ce5e  mov     [rbp+57h+var_90], eax
0x18000ce61  jmp     short loc_18000CEC7
0x18000ce63  test    byte ptr [rbx], 4
0x18000ce66  jz      short loc_18000CEC4
0x18000ce68  mov     ecx, 80h; unsigned __int64
0x18000ce6d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ce72  mov     [rbx+8], rax
0x18000ce76  test    rax, rax
0x18000ce79  jz      short loc_18000CEBD
0x18000ce7b  mov     r8d, 40h ; '@'; unsigned int
0x18000ce81  lea     rdx, [rbp+57h+MultiByteStr]; void *
0x18000ce85  mov     rcx, rdi; this
0x18000ce88  call    ?Read@CRiffParser@@QEAAJPEAXK@Z; CRiffParser::Read(void *,ulong)
0x18000ce8d  mov     [rbp+57h+var_90], eax
0x18000ce90  mov     [rbp+57h+var_21], sil
0x18000ce94  test    eax, eax
0x18000ce96  js      short loc_18000CEC4
0x18000ce98  mov     rax, [rbx+8]
0x18000ce9c  lea     r8, [rbp+57h+MultiByteStr]; lpMultiByteStr
0x18000cea0  mov     [rsp+0C0h+cchWideChar], 40h ; '@'; cchWideChar
0x18000cea8  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000ceac  xor     edx, edx; dwFlags
0x18000ceae  mov     [rsp+0C0h+lpWideCharStr], rax; lpWideCharStr
0x18000ceb3  xor     ecx, ecx; CodePage
0x18000ceb5  call    cs:__imp_MultiByteToWideChar
0x18000cebb  jmp     short loc_18000CEC4
0x18000cebd  mov     [rbp+57h+var_90], 8007000Eh
0x18000cec4  or      byte ptr [rbx], 2
0x18000cec7  lea     rdx, [rbp+57h+var_90]; int *
0x18000cecb  mov     rcx, rdi; this
0x18000cece  call    ?NextChunk@CRiffParser@@QEAAHPEAJ@Z; CRiffParser::NextChunk(long *)
0x18000ced3  test    eax, eax
0x18000ced5  jnz     loc_18000CDE9
0x18000cedb  mov     rax, [rdi+10h]
0x18000cedf  test    rax, rax
0x18000cee2  jz      short loc_18000CEF9
0x18000cee4  mov     rax, [rax+10h]
0x18000cee8  mov     [rdi+10h], rax
0x18000ceec  test    rax, rax
0x18000ceef  jz      short loc_18000CEF9
0x18000cef1  mov     rax, [rax+10h]
0x18000cef5  mov     [rdi+18h], rax
0x18000cef9  mov     edi, [rbp+57h+var_90]
0x18000cefc  test    edi, edi
0x18000cefe  jns     short loc_18000CF27
0x18000cf00  mov     rcx, [rbx+10h]; void *
0x18000cf04  test    rcx, rcx
0x18000cf07  jz      short loc_18000CF12
0x18000cf09  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cf0e  mov     [rbx+10h], rsi
0x18000cf12  mov     rcx, [rbx+8]; void *
0x18000cf16  test    rcx, rcx
0x18000cf19  jz      short loc_18000CF24
0x18000cf1b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cf20  mov     [rbx+8], rsi
0x18000cf24  mov     [rbx], sil
0x18000cf27  mov     eax, edi
0x18000cf29  mov     rcx, [rbp+57h+var_20]
0x18000cf2d  xor     rcx, rsp; StackCookie
0x18000cf30  call    __security_check_cookie
0x18000cf35  mov     rbx, [rsp+0C0h+arg_10]
0x18000cf3d  add     rsp, 0B0h
0x18000cf44  pop     rdi
0x18000cf45  pop     rsi
0x18000cf46  pop     rbp
0x18000cf47  retn
0x18000cf48  mov     rcx, [rbx+10h]; void *
0x18000cf4c  test    rcx, rcx
0x18000cf4f  jz      short loc_18000CF5A
0x18000cf51  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cf56  mov     [rbx+10h], rsi
0x18000cf5a  mov     rcx, [rbx+8]; void *
0x18000cf5e  test    rcx, rcx
0x18000cf61  jz      short loc_18000CF6C
0x18000cf63  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cf68  mov     [rbx+8], rsi
0x18000cf6c  mov     [rbx], sil
0x18000cf6f  mov     eax, 5B6h
0x18000cf74  jmp     short loc_18000CF29
```
