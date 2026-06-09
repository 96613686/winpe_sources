# CMFTSimpleTypeHandler::GetInputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x180019fb0`
- end: `0x18001a0cd`
- name: `?GetInputAvailableType@CMFTSimpleTypeHandler@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `285`
- prototype: `int(CMFTSimpleTypeHandler *__hidden this, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180019fb0`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18001a027`
- `MFPlat!MFCreateMediaType` at `0x18001a027`

## pseudocode

```c
__int64 __fastcall CMFTSimpleTypeHandler::GetInputAvailableType(
        CMFTSimpleTypeHandler *this,
        int a2,
        int a3,
        struct IMFMediaType **a4)
{
  unsigned int v7; // edx
  int v8; // r8d
  unsigned int i; // eax
  __int64 v10; // rbx
  HRESULT v11; // esi
  __int64 v13; // rcx

  if ( a2 )
    return (unsigned int)-1072875853;
  if ( !a4 )
    return (unsigned int)-2147467261;
  if ( *((_DWORD *)this + 25) == 1 && !*((_QWORD *)this + 10) )
    return (unsigned int)-1072861856;
  v7 = *((_DWORD *)this + 4);
  if ( !v7 )
    return 3222091449LL;
  v8 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= v7 )
      return (unsigned int)-1072875847;
    v10 = 2LL * i;
    if ( *(_DWORD *)(*((_QWORD *)this + 3) + 16LL * i + 8) )
      break;
LABEL_10:
    ;
  }
  if ( v8 != a3 )
  {
    ++v8;
    goto LABEL_10;
  }
  v11 = MFCreateMediaType(a4);
  if ( v11 >= 0 )
  {
    _mm_lfence();
    v13 = *(_QWORD *)(*((_QWORD *)this + 3) + 8 * v10);
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 256LL))(v13, *a4);
    if ( v11 < 0 )
    {
      if ( *a4 )
      {
        ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
        *a4 = 0;
      }
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180019fb0  mov     [rsp+arg_8], rsi
0x180019fb5  mov     [rsp+arg_10], rdi
0x180019fba  push    r14
0x180019fbc  sub     rsp, 20h
0x180019fc0  mov     r14, r9
0x180019fc3  mov     r10d, r8d
0x180019fc6  mov     rdi, rcx
0x180019fc9  test    edx, edx
0x180019fcb  jnz     loc_18001A0AA
0x180019fd1  test    r9, r9
0x180019fd4  jz      loc_18001A0B1
0x180019fda  cmp     dword ptr [rcx+64h], 1
0x180019fde  jz      loc_18001A0B8
0x180019fe4  mov     edx, [rcx+10h]
0x180019fe7  test    edx, edx
0x180019fe9  jz      loc_18001A092
0x180019fef  xor     r8d, r8d
0x180019ff2  mov     [rsp+28h+arg_0], rbx
0x180019ff7  xor     eax, eax
0x180019ff9  nop     dword ptr [rax+00000000h]
0x18001a000  cmp     eax, edx
0x18001a002  jnb     loc_18001A08B
0x18001a008  mov     rcx, [rdi+18h]
0x18001a00c  mov     ebx, eax
0x18001a00e  add     rbx, rbx
0x18001a011  cmp     dword ptr [rcx+rbx*8+8], 0
0x18001a016  jz      short loc_18001A020
0x18001a018  cmp     r8d, r10d
0x18001a01b  jz      short loc_18001A024
0x18001a01d  inc     r8d
0x18001a020  inc     eax
0x18001a022  jmp     short loc_18001A000
0x18001a024  mov     rcx, r14; ppMFType
0x18001a027  call    cs:__imp_MFCreateMediaType
0x18001a02d  mov     esi, eax
0x18001a02f  test    eax, eax
0x18001a031  jns     short loc_18001A04B
0x18001a033  mov     rbx, [rsp+28h+arg_0]
0x18001a038  mov     eax, esi
0x18001a03a  mov     rsi, [rsp+28h+arg_8]
0x18001a03f  mov     rdi, [rsp+28h+arg_10]
0x18001a044  add     rsp, 20h
0x18001a048  pop     r14
0x18001a04a  retn
0x18001a04b  lfence
0x18001a04e  mov     rax, [rdi+18h]
0x18001a052  mov     rdx, [r14]
0x18001a055  mov     rcx, [rax+rbx*8]
0x18001a059  mov     rax, [rcx]
0x18001a05c  mov     rax, [rax+100h]
0x18001a063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a068  mov     esi, eax
0x18001a06a  test    eax, eax
0x18001a06c  jns     short loc_18001A033
0x18001a06e  mov     rcx, [r14]
0x18001a071  test    rcx, rcx
0x18001a074  jz      short loc_18001A033
0x18001a076  mov     rax, [rcx]
0x18001a079  mov     rax, [rax+10h]
0x18001a07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a082  mov     qword ptr [r14], 0
0x18001a089  jmp     short loc_18001A033
0x18001a08b  mov     esi, 0C00D36B9h
0x18001a090  jmp     short loc_18001A033
0x18001a092  mov     rdi, [rsp+28h+arg_10]
0x18001a097  mov     esi, 0C00D36B9h
0x18001a09c  mov     eax, esi
0x18001a09e  mov     rsi, [rsp+28h+arg_8]
0x18001a0a3  add     rsp, 20h
0x18001a0a7  pop     r14
0x18001a0a9  retn
0x18001a0aa  mov     esi, 0C00D36B3h
0x18001a0af  jmp     short loc_18001A038
0x18001a0b1  mov     esi, 80004003h
0x18001a0b6  jmp     short loc_18001A038
0x18001a0b8  cmp     qword ptr [rcx+50h], 0
0x18001a0bd  jnz     loc_180019FE4
0x18001a0c3  mov     esi, 0C00D6D60h
0x18001a0c8  jmp     loc_18001A038
```
