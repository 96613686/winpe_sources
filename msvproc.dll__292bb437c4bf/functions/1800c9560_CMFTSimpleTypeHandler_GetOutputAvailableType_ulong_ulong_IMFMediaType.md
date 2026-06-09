# CMFTSimpleTypeHandler::GetOutputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x1800c9560`
- end: `0x1800c9630`
- name: `?GetOutputAvailableType@CMFTSimpleTypeHandler@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `208`
- prototype: `int(CMFTSimpleTypeHandler *__hidden this, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800c9560`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800c95d3`
- `MFPlat!MFCreateMediaType` at `0x1800c95d3`

## pseudocode

```c
__int64 __fastcall CMFTSimpleTypeHandler::GetOutputAvailableType(
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
    if ( *((_DWORD *)this + 25) || *((_QWORD *)this + 6) )
    {
      if ( *((_DWORD *)this + 8) )
      {
        v7 = 0;
        for ( i = 0; i < *((_DWORD *)this + 8); ++i )
        {
          v9 = 2LL * i;
          if ( *(_DWORD *)(*((_QWORD *)this + 5) + 16LL * i + 8) )
          {
            if ( v7 == a3 )
            {
              v6 = MFCreateMediaType(a4);
              if ( v6 >= 0 )
              {
                _mm_lfence();
                v10 = *(_QWORD *)(*((_QWORD *)this + 5) + 8 * v9);
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
0x1800c9560  push    rbx
0x1800c9562  push    rsi
0x1800c9563  push    rdi
0x1800c9564  push    r14
0x1800c9566  sub     rsp, 28h
0x1800c956a  mov     rsi, r9
0x1800c956d  mov     rdi, rcx
0x1800c9570  test    edx, edx
0x1800c9572  jz      short loc_1800C957E
0x1800c9574  mov     ebx, 0C00D36B3h
0x1800c9579  jmp     loc_1800C9624
0x1800c957e  test    rsi, rsi
0x1800c9581  jnz     short loc_1800C958D
0x1800c9583  mov     ebx, 80004003h
0x1800c9588  jmp     loc_1800C9624
0x1800c958d  cmp     dword ptr [rcx+64h], 0
0x1800c9591  jnz     short loc_1800C95A4
0x1800c9593  cmp     qword ptr [rcx+30h], 0
0x1800c9598  jnz     short loc_1800C95A4
0x1800c959a  mov     ebx, 0C00D6D60h
0x1800c959f  jmp     loc_1800C9624
0x1800c95a4  cmp     dword ptr [rcx+20h], 0
0x1800c95a8  jz      short loc_1800C961F
0x1800c95aa  xor     edx, edx
0x1800c95ac  xor     ecx, ecx
0x1800c95ae  cmp     ecx, [rdi+20h]
0x1800c95b1  jnb     short loc_1800C961F
0x1800c95b3  mov     rax, [rdi+28h]
0x1800c95b7  mov     r14d, ecx
0x1800c95ba  add     r14, r14
0x1800c95bd  cmp     dword ptr [rax+r14*8+8], 0
0x1800c95c3  jz      short loc_1800C95CC
0x1800c95c5  cmp     edx, r8d
0x1800c95c8  jz      short loc_1800C95D0
0x1800c95ca  inc     edx
0x1800c95cc  inc     ecx
0x1800c95ce  jmp     short loc_1800C95AE
0x1800c95d0  mov     rcx, rsi; ppMFType
0x1800c95d3  call    cs:__imp_MFCreateMediaType
0x1800c95d9  mov     ebx, eax
0x1800c95db  test    eax, eax
0x1800c95dd  js      short loc_1800C9624
0x1800c95df  lfence
0x1800c95e2  mov     rax, [rdi+28h]
0x1800c95e6  mov     rdx, [rsi]
0x1800c95e9  mov     rcx, [rax+r14*8]
0x1800c95ed  mov     rax, [rcx]
0x1800c95f0  mov     rax, [rax+100h]
0x1800c95f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c95fc  mov     ebx, eax
0x1800c95fe  test    eax, eax
0x1800c9600  jns     short loc_1800C9624
0x1800c9602  mov     rcx, [rsi]
0x1800c9605  test    rcx, rcx
0x1800c9608  jz      short loc_1800C9624
0x1800c960a  mov     rax, [rcx]
0x1800c960d  mov     rax, [rax+10h]
0x1800c9611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9616  mov     qword ptr [rsi], 0
0x1800c961d  jmp     short loc_1800C9624
0x1800c961f  mov     ebx, 0C00D36B9h
0x1800c9624  mov     eax, ebx
0x1800c9626  add     rsp, 28h
0x1800c962a  pop     r14
0x1800c962c  pop     rdi
0x1800c962d  pop     rsi
0x1800c962e  pop     rbx
0x1800c962f  retn
```
