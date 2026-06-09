# CMFTSimpleTypeHandler::GetInputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x180008fd0`
- end: `0x180009095`
- name: `?GetInputAvailableType@CMFTSimpleTypeHandler@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `197`
- prototype: `int(CMFTSimpleTypeHandler *__hidden this, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008fd0`
- `0x18001e010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18000904c`
- `MFPlat!MFCreateMediaType` at `0x18000904c`

## pseudocode

```c
__int64 __fastcall CMFTSimpleTypeHandler::GetInputAvailableType(
        CMFTSimpleTypeHandler *this,
        int a2,
        int a3,
        struct IMFMediaType **a4)
{
  HRESULT v6; // ebx
  unsigned int v7; // ecx
  unsigned int v8; // eax
  int v9; // edx
  __int64 v10; // r14
  __int64 v12; // rcx

  if ( a2 )
    return (unsigned int)-1072875853;
  if ( !a4 )
    return (unsigned int)-2147467261;
  if ( *((_DWORD *)this + 25) == 1 && !*((_QWORD *)this + 10) )
    return (unsigned int)-1072861856;
  v7 = *((_DWORD *)this + 4);
  if ( !v7 )
    return (unsigned int)-1072875847;
  v8 = 0;
  v9 = 0;
  while ( 1 )
  {
    v10 = 2LL * v8;
    if ( *(_DWORD *)(*((_QWORD *)this + 3) + 16LL * v8 + 8) )
      break;
LABEL_13:
    if ( ++v8 >= v7 )
      return (unsigned int)-1072875847;
  }
  if ( v9 != a3 )
  {
    ++v9;
    goto LABEL_13;
  }
  v6 = MFCreateMediaType(a4);
  if ( v6 >= 0 )
  {
    v12 = *(_QWORD *)(*((_QWORD *)this + 3) + 8 * v10);
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 256LL))(v12, *a4);
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

```

## disassembly

```asm
0x180008fd0  push    rbx
0x180008fd2  push    rsi
0x180008fd3  push    rdi
0x180008fd4  push    r14
0x180008fd6  sub     rsp, 28h
0x180008fda  mov     rdi, r9
0x180008fdd  mov     r9d, r8d
0x180008fe0  mov     rsi, rcx
0x180008fe3  test    edx, edx
0x180008fe5  jz      short loc_180008FEE
0x180008fe7  mov     ebx, 0C00D36B3h
0x180008fec  jmp     short loc_18000903D
0x180008fee  test    rdi, rdi
0x180008ff1  jnz     short loc_180008FFA
0x180008ff3  mov     ebx, 80004003h
0x180008ff8  jmp     short loc_18000903D
0x180008ffa  cmp     dword ptr [rcx+64h], 1
0x180008ffe  jnz     short loc_18000900E
0x180009000  cmp     qword ptr [rcx+50h], 0
0x180009005  jnz     short loc_18000900E
0x180009007  mov     ebx, 0C00D6D60h
0x18000900c  jmp     short loc_18000903D
0x18000900e  mov     ecx, [rcx+10h]
0x180009011  test    ecx, ecx
0x180009013  jz      short loc_180009038
0x180009015  mov     r8, [rsi+18h]
0x180009019  xor     eax, eax
0x18000901b  xor     edx, edx
0x18000901d  mov     r14d, eax
0x180009020  add     r14, r14
0x180009023  cmp     dword ptr [r8+r14*8+8], 0
0x180009029  jz      short loc_180009032
0x18000902b  cmp     edx, r9d
0x18000902e  jz      short loc_180009049
0x180009030  inc     edx
0x180009032  inc     eax
0x180009034  cmp     eax, ecx
0x180009036  jb      short loc_18000901D
0x180009038  mov     ebx, 0C00D36B9h
0x18000903d  mov     eax, ebx
0x18000903f  add     rsp, 28h
0x180009043  pop     r14
0x180009045  pop     rdi
0x180009046  pop     rsi
0x180009047  pop     rbx
0x180009048  retn
0x180009049  mov     rcx, rdi; ppMFType
0x18000904c  call    cs:__imp_MFCreateMediaType
0x180009052  mov     ebx, eax
0x180009054  test    eax, eax
0x180009056  js      short loc_18000903D
0x180009058  mov     rax, [rsi+18h]
0x18000905c  mov     rdx, [rdi]
0x18000905f  mov     rcx, [rax+r14*8]
0x180009063  mov     rax, [rcx]
0x180009066  mov     rax, [rax+100h]
0x18000906d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009072  mov     ebx, eax
0x180009074  test    eax, eax
0x180009076  jns     short loc_18000903D
0x180009078  mov     rcx, [rdi]
0x18000907b  test    rcx, rcx
0x18000907e  jz      short loc_18000903D
0x180009080  mov     rax, [rcx]
0x180009083  mov     rax, [rax+10h]
0x180009087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000908c  mov     qword ptr [rdi], 0
0x180009093  jmp     short loc_18000903D
```
