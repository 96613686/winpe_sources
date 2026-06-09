# CMFTSimpleTypeHandler::GetInputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x180045230`
- end: `0x180045300`
- name: `?GetInputAvailableType@CMFTSimpleTypeHandler@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(CMFTSimpleTypeHandler *this, int, int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180045230`
- `0x180070010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800452a3`
- `MFPlat!MFCreateMediaType` at `0x1800452a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMFTSimpleTypeHandler::GetInputAvailableType(
        CMFTSimpleTypeHandler *this,
        int a2,
        int a3,
        struct IMFMediaType **a4)
{
  HRESULT v6; // ebx
  int v7; // edx
  unsigned int i; // ecx
  __int64 v9; // r14
  __int64 v10; // rcx

  if ( a2 )
  {
    return (unsigned int)-1072875853;
  }
  else if ( a4 )
  {
    if ( *((_DWORD *)this + 25) != 1 || *((_QWORD *)this + 10) )
    {
      if ( *((_DWORD *)this + 4) )
      {
        v7 = 0;
        for ( i = 0; i < *((_DWORD *)this + 4); ++i )
        {
          v9 = 2LL * i;
          if ( *(_DWORD *)(*((_QWORD *)this + 3) + 16LL * i + 8) )
          {
            if ( v7 == a3 )
            {
              v6 = MFCreateMediaType(a4);
              if ( v6 >= 0 )
              {
                _mm_lfence();
                v10 = *(_QWORD *)(*((_QWORD *)this + 3) + 8 * v9);
                v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 256LL))(v10, *a4);
                if ( v6 < 0 )
                {
                  if ( *a4 )
                  {
                    ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
                    *a4 = 0;
                  }
                }
              }
              return (unsigned int)v6;
            }
            ++v7;
          }
        }
      }
      return (unsigned int)-1072875847;
    }
    else
    {
      return (unsigned int)-1072861856;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
}

```

## disassembly

```asm
0x180045230  push    rbx
0x180045232  push    rsi
0x180045233  push    rdi
0x180045234  push    r14
0x180045236  sub     rsp, 28h
0x18004523a  mov     rdi, r9
0x18004523d  mov     rsi, rcx
0x180045240  test    edx, edx
0x180045242  jz      short loc_18004524E
0x180045244  mov     ebx, 0C00D36B3h
0x180045249  jmp     loc_1800452F4
0x18004524e  test    rdi, rdi
0x180045251  jnz     short loc_18004525D
0x180045253  mov     ebx, 80004003h
0x180045258  jmp     loc_1800452F4
0x18004525d  cmp     dword ptr [rcx+64h], 1
0x180045261  jnz     short loc_180045274
0x180045263  cmp     qword ptr [rcx+50h], 0
0x180045268  jnz     short loc_180045274
0x18004526a  mov     ebx, 0C00D6D60h
0x18004526f  jmp     loc_1800452F4
0x180045274  cmp     dword ptr [rcx+10h], 0
0x180045278  jz      short loc_1800452EF
0x18004527a  xor     edx, edx
0x18004527c  xor     ecx, ecx
0x18004527e  cmp     ecx, [rsi+10h]
0x180045281  jnb     short loc_1800452EF
0x180045283  mov     rax, [rsi+18h]
0x180045287  mov     r14d, ecx
0x18004528a  add     r14, r14
0x18004528d  cmp     dword ptr [rax+r14*8+8], 0
0x180045293  jz      short loc_18004529C
0x180045295  cmp     edx, r8d
0x180045298  jz      short loc_1800452A0
0x18004529a  inc     edx
0x18004529c  inc     ecx
0x18004529e  jmp     short loc_18004527E
0x1800452a0  mov     rcx, rdi; ppMFType
0x1800452a3  call    cs:__imp_MFCreateMediaType
0x1800452a9  mov     ebx, eax
0x1800452ab  test    eax, eax
0x1800452ad  js      short loc_1800452F4
0x1800452af  lfence
0x1800452b2  mov     rax, [rsi+18h]
0x1800452b6  mov     rdx, [rdi]
0x1800452b9  mov     rcx, [rax+r14*8]
0x1800452bd  mov     rax, [rcx]
0x1800452c0  mov     rax, [rax+100h]
0x1800452c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452cc  mov     ebx, eax
0x1800452ce  test    eax, eax
0x1800452d0  jns     short loc_1800452F4
0x1800452d2  mov     rcx, [rdi]
0x1800452d5  test    rcx, rcx
0x1800452d8  jz      short loc_1800452F4
0x1800452da  mov     rax, [rcx]
0x1800452dd  mov     rax, [rax+10h]
0x1800452e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452e6  mov     qword ptr [rdi], 0
0x1800452ed  jmp     short loc_1800452F4
0x1800452ef  mov     ebx, 0C00D36B9h
0x1800452f4  mov     eax, ebx
0x1800452f6  add     rsp, 28h
0x1800452fa  pop     r14
0x1800452fc  pop     rdi
0x1800452fd  pop     rsi
0x1800452fe  pop     rbx
0x1800452ff  retn
```
