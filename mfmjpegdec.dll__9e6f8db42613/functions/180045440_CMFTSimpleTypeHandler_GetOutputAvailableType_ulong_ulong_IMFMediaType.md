# CMFTSimpleTypeHandler::GetOutputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x180045440`
- end: `0x180045510`
- name: `?GetOutputAvailableType@CMFTSimpleTypeHandler@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(CMFTSimpleTypeHandler *this, int, int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180045440`
- `0x180070010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800454b3`
- `MFPlat!MFCreateMediaType` at `0x1800454b3`

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
0x180045440  push    rbx
0x180045442  push    rsi
0x180045443  push    rdi
0x180045444  push    r14
0x180045446  sub     rsp, 28h
0x18004544a  mov     rsi, r9
0x18004544d  mov     rdi, rcx
0x180045450  test    edx, edx
0x180045452  jz      short loc_18004545E
0x180045454  mov     ebx, 0C00D36B3h
0x180045459  jmp     loc_180045504
0x18004545e  test    rsi, rsi
0x180045461  jnz     short loc_18004546D
0x180045463  mov     ebx, 80004003h
0x180045468  jmp     loc_180045504
0x18004546d  cmp     dword ptr [rcx+64h], 0
0x180045471  jnz     short loc_180045484
0x180045473  cmp     qword ptr [rcx+30h], 0
0x180045478  jnz     short loc_180045484
0x18004547a  mov     ebx, 0C00D6D60h
0x18004547f  jmp     loc_180045504
0x180045484  cmp     dword ptr [rcx+20h], 0
0x180045488  jz      short loc_1800454FF
0x18004548a  xor     edx, edx
0x18004548c  xor     ecx, ecx
0x18004548e  cmp     ecx, [rdi+20h]
0x180045491  jnb     short loc_1800454FF
0x180045493  mov     rax, [rdi+28h]
0x180045497  mov     r14d, ecx
0x18004549a  add     r14, r14
0x18004549d  cmp     dword ptr [rax+r14*8+8], 0
0x1800454a3  jz      short loc_1800454AC
0x1800454a5  cmp     edx, r8d
0x1800454a8  jz      short loc_1800454B0
0x1800454aa  inc     edx
0x1800454ac  inc     ecx
0x1800454ae  jmp     short loc_18004548E
0x1800454b0  mov     rcx, rsi; ppMFType
0x1800454b3  call    cs:__imp_MFCreateMediaType
0x1800454b9  mov     ebx, eax
0x1800454bb  test    eax, eax
0x1800454bd  js      short loc_180045504
0x1800454bf  lfence
0x1800454c2  mov     rax, [rdi+28h]
0x1800454c6  mov     rdx, [rsi]
0x1800454c9  mov     rcx, [rax+r14*8]
0x1800454cd  mov     rax, [rcx]
0x1800454d0  mov     rax, [rax+100h]
0x1800454d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454dc  mov     ebx, eax
0x1800454de  test    eax, eax
0x1800454e0  jns     short loc_180045504
0x1800454e2  mov     rcx, [rsi]
0x1800454e5  test    rcx, rcx
0x1800454e8  jz      short loc_180045504
0x1800454ea  mov     rax, [rcx]
0x1800454ed  mov     rax, [rax+10h]
0x1800454f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454f6  mov     qword ptr [rsi], 0
0x1800454fd  jmp     short loc_180045504
0x1800454ff  mov     ebx, 0C00D36B9h
0x180045504  mov     eax, ebx
0x180045506  add     rsp, 28h
0x18004550a  pop     r14
0x18004550c  pop     rdi
0x18004550d  pop     rsi
0x18004550e  pop     rbx
0x18004550f  retn
```
