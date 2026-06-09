# CMFTSimpleTypeHandler::GetOutputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x1800091d0`
- end: `0x180009295`
- name: `?GetOutputAvailableType@CMFTSimpleTypeHandler@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `197`
- prototype: `int(CMFTSimpleTypeHandler *__hidden this, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800091d0`
- `0x18001e010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18000924c`
- `MFPlat!MFCreateMediaType` at `0x18000924c`

## pseudocode

```c
__int64 __fastcall CMFTSimpleTypeHandler::GetOutputAvailableType(
        CMFTSimpleTypeHandler *this,
        int a2,
        int a3,
        struct IMFMediaType **a4)
{
  HRESULT v7; // ebx
  unsigned int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // ecx
  int v11; // edx
  __int64 v12; // r14
  __int64 v14; // rcx

  if ( a2 )
    return (unsigned int)-1072875853;
  if ( !a4 )
    return (unsigned int)-2147467261;
  if ( !*((_DWORD *)this + 25) && !*((_QWORD *)this + 6) )
    return (unsigned int)-1072861856;
  v8 = *((_DWORD *)this + 8);
  if ( !v8 )
    return (unsigned int)-1072875847;
  v9 = *((_QWORD *)this + 5);
  v10 = 0;
  v11 = 0;
  while ( 1 )
  {
    v12 = 2LL * v10;
    if ( *(_DWORD *)(v9 + 16LL * v10 + 8) )
      break;
LABEL_13:
    if ( ++v10 >= v8 )
      return (unsigned int)-1072875847;
  }
  if ( v11 != a3 )
  {
    ++v11;
    goto LABEL_13;
  }
  v7 = MFCreateMediaType(a4);
  if ( v7 >= 0 )
  {
    v14 = *(_QWORD *)(*((_QWORD *)this + 5) + 8 * v12);
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 256LL))(v14, *a4);
    if ( v7 < 0 )
    {
      if ( *a4 )
      {
        ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
        *a4 = 0;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800091d0  push    rbx
0x1800091d2  push    rsi
0x1800091d3  push    rdi
0x1800091d4  push    r14
0x1800091d6  sub     rsp, 28h
0x1800091da  mov     rsi, r9
0x1800091dd  mov     r9d, r8d
0x1800091e0  mov     rdi, rcx
0x1800091e3  test    edx, edx
0x1800091e5  jz      short loc_1800091EE
0x1800091e7  mov     ebx, 0C00D36B3h
0x1800091ec  jmp     short loc_18000923D
0x1800091ee  test    rsi, rsi
0x1800091f1  jnz     short loc_1800091FA
0x1800091f3  mov     ebx, 80004003h
0x1800091f8  jmp     short loc_18000923D
0x1800091fa  cmp     dword ptr [rcx+64h], 0
0x1800091fe  jnz     short loc_18000920E
0x180009200  cmp     qword ptr [rcx+30h], 0
0x180009205  jnz     short loc_18000920E
0x180009207  mov     ebx, 0C00D6D60h
0x18000920c  jmp     short loc_18000923D
0x18000920e  mov     eax, [rcx+20h]
0x180009211  test    eax, eax
0x180009213  jz      short loc_180009238
0x180009215  mov     r8, [rdi+28h]
0x180009219  xor     ecx, ecx
0x18000921b  xor     edx, edx
0x18000921d  mov     r14d, ecx
0x180009220  add     r14, r14
0x180009223  cmp     dword ptr [r8+r14*8+8], 0
0x180009229  jz      short loc_180009232
0x18000922b  cmp     edx, r9d
0x18000922e  jz      short loc_180009249
0x180009230  inc     edx
0x180009232  inc     ecx
0x180009234  cmp     ecx, eax
0x180009236  jb      short loc_18000921D
0x180009238  mov     ebx, 0C00D36B9h
0x18000923d  mov     eax, ebx
0x18000923f  add     rsp, 28h
0x180009243  pop     r14
0x180009245  pop     rdi
0x180009246  pop     rsi
0x180009247  pop     rbx
0x180009248  retn
0x180009249  mov     rcx, rsi; ppMFType
0x18000924c  call    cs:__imp_MFCreateMediaType
0x180009252  mov     ebx, eax
0x180009254  test    eax, eax
0x180009256  js      short loc_18000923D
0x180009258  mov     rax, [rdi+28h]
0x18000925c  mov     rdx, [rsi]
0x18000925f  mov     rcx, [rax+r14*8]
0x180009263  mov     rax, [rcx]
0x180009266  mov     rax, [rax+100h]
0x18000926d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009272  mov     ebx, eax
0x180009274  test    eax, eax
0x180009276  jns     short loc_18000923D
0x180009278  mov     rcx, [rsi]
0x18000927b  test    rcx, rcx
0x18000927e  jz      short loc_18000923D
0x180009280  mov     rax, [rcx]
0x180009283  mov     rax, [rax+10h]
0x180009287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000928c  mov     qword ptr [rsi], 0
0x180009293  jmp     short loc_18000923D
```
