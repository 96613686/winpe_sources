# ATL::CComBSTR::operator+=(ushort const *)

- ea: `0x180004848`
- end: `0x180004965`
- name: `??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z`
- size: `285`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004d50`
- `0x18000ef90`

## callees

- `0x180002ac4`
- `0x180004848`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800048d2`
- `msvcrt!memcpy_s` at `0x180004900`
- `msvcrt!memcpy_s` at `0x1800048d2`
- `msvcrt!memcpy_s` at `0x180004900`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800048a1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800048a1`
- `OLEAUT32!__imp_SysFreeString` at `0x180004929`
- `OLEAUT32!__imp_SysFreeString` at `0x180004929`
- `OLEAUT32!__imp_SysStringLen` at `0x180004887`
- `OLEAUT32!__imp_SysStringLen` at `0x1800048b6`
- `OLEAUT32!__imp_SysStringLen` at `0x180004887`
- `OLEAUT32!__imp_SysStringLen` at `0x1800048b6`

## pseudocode

```c
const void **__fastcall ATL::CComBSTR::operator+=(const void **a1, _WORD *a2)
{
  __int64 v4; // rbx
  OLECHAR *v5; // rcx
  signed int v6; // eax
  __int64 v7; // r14
  signed int v8; // ebp
  BSTR v9; // rsi
  errno_t v10; // eax
  errno_t v11; // eax

  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    v5 = (OLECHAR *)*a1;
    if ( !v5 || (_DWORD)v4 )
    {
      v6 = SysStringLen(v5);
      v7 = v6;
      v8 = v6 + v4;
      if ( v6 + (int)v4 >= v6 )
      {
        v9 = SysAllocStringLen(0, v8);
        if ( v9 )
        {
          if ( SysStringLen((BSTR)*a1) )
          {
            v10 = memcpy_s(v9, 2LL * v8, *a1, 2 * v7);
            if ( v10 )
            {
              if ( v10 == 12 )
                goto LABEL_21;
              if ( v10 == 22 || v10 == 34 )
                goto LABEL_23;
              if ( v10 != 80 )
                goto LABEL_22;
            }
          }
          v11 = memcpy_s(&v9[v7], 2LL * (int)v4, a2, 2LL * (int)v4);
          if ( !v11 )
          {
LABEL_19:
            v9[v8] = 0;
            SysFreeString((BSTR)*a1);
            *a1 = v9;
            return a1;
          }
          if ( v11 != 12 )
          {
            if ( v11 != 22 && v11 != 34 )
            {
              if ( v11 == 80 )
                goto LABEL_19;
LABEL_22:
              ATL::AtlThrowImpl(-2147467259);
            }
LABEL_23:
            ATL::AtlThrowImpl(-2147024809);
          }
        }
      }
LABEL_21:
      ATL::AtlThrowImpl(-2147024882);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180004848  push    rbx
0x18000484a  push    rbp
0x18000484b  push    rsi
0x18000484c  push    rdi
0x18000484d  push    r12
0x18000484f  push    r14
0x180004851  push    r15
0x180004853  sub     rsp, 20h
0x180004857  xor     r12d, r12d
0x18000485a  mov     r15, rdx
0x18000485d  mov     rdi, rcx
0x180004860  test    rdx, rdx
0x180004863  jz      loc_180004932
0x180004869  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000486d  inc     rbx
0x180004870  cmp     [rdx+rbx*2], r12w
0x180004875  jnz     short loc_18000486D
0x180004877  mov     rcx, [rcx]; pbstr
0x18000487a  test    rcx, rcx
0x18000487d  jz      short loc_180004887
0x18000487f  test    ebx, ebx
0x180004881  jz      loc_180004932
0x180004887  call    cs:__imp_SysStringLen
0x18000488d  movsxd  r14, eax
0x180004890  lea     ebp, [r14+rbx]
0x180004894  cmp     ebp, r14d
0x180004897  jl      loc_180004944
0x18000489d  mov     edx, ebp; ui
0x18000489f  xor     ecx, ecx; strIn
0x1800048a1  call    cs:__imp_SysAllocStringLen
0x1800048a7  mov     rsi, rax
0x1800048aa  test    rax, rax
0x1800048ad  jz      loc_180004944
0x1800048b3  mov     rcx, [rdi]; pbstr
0x1800048b6  call    cs:__imp_SysStringLen
0x1800048bc  test    eax, eax
0x1800048be  jz      short loc_1800048F0
0x1800048c0  mov     r8, [rdi]; Source
0x1800048c3  mov     r9, r14
0x1800048c6  movsxd  rdx, ebp
0x1800048c9  add     r9, r9; SourceSize
0x1800048cc  add     rdx, rdx; DestinationSize
0x1800048cf  mov     rcx, rsi; Destination
0x1800048d2  call    cs:__imp_memcpy_s
0x1800048d8  test    eax, eax
0x1800048da  jz      short loc_1800048F0
0x1800048dc  cmp     eax, 0Ch
0x1800048df  jz      short loc_180004944
0x1800048e1  cmp     eax, 16h
0x1800048e4  jz      short loc_18000495A
0x1800048e6  cmp     eax, 22h ; '"'
0x1800048e9  jz      short loc_18000495A
0x1800048eb  cmp     eax, 50h ; 'P'
0x1800048ee  jnz     short loc_18000494F
0x1800048f0  movsxd  rdx, ebx
0x1800048f3  lea     rcx, [rsi+r14*2]; Destination
0x1800048f7  add     rdx, rdx; DestinationSize
0x1800048fa  mov     r8, r15; Source
0x1800048fd  mov     r9, rdx; SourceSize
0x180004900  call    cs:__imp_memcpy_s
0x180004906  test    eax, eax
0x180004908  jz      short loc_18000491E
0x18000490a  cmp     eax, 0Ch
0x18000490d  jz      short loc_180004944
0x18000490f  cmp     eax, 16h
0x180004912  jz      short loc_18000495A
0x180004914  cmp     eax, 22h ; '"'
0x180004917  jz      short loc_18000495A
0x180004919  cmp     eax, 50h ; 'P'
0x18000491c  jnz     short loc_18000494F
0x18000491e  movsxd  rcx, ebp
0x180004921  mov     [rsi+rcx*2], r12w
0x180004926  mov     rcx, [rdi]; bstrString
0x180004929  call    cs:__imp_SysFreeString
0x18000492f  mov     [rdi], rsi
0x180004932  mov     rax, rdi
0x180004935  add     rsp, 20h
0x180004939  pop     r15
0x18000493b  pop     r14
0x18000493d  pop     r12
0x18000493f  pop     rdi
0x180004940  pop     rsi
0x180004941  pop     rbp
0x180004942  pop     rbx
0x180004943  retn
0x180004944  mov     ecx, 8007000Eh; int
0x180004949  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000494f  mov     ecx, 80004005h; int
0x180004954  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000495a  mov     ecx, 80070057h; int
0x18000495f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
