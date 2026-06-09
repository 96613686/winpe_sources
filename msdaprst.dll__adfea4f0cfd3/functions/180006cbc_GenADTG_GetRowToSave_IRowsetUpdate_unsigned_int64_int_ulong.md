# GenADTG::GetRowToSave(IRowsetUpdate *,unsigned __int64,int,ulong)

- ea: `0x180006cbc`
- end: `0x180006e6a`
- name: `?GetRowToSave@GenADTG@@QEAAXPEAUIRowsetUpdate@@_KHK@Z`
- size: `430`
- prototype: `void __fastcall(GenADTG *__hidden this, struct IRowsetUpdate *, unsigned __int64, int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180008e00`

## callees

- `0x180006cbc`
- `0x18001b008`
- `0x18002dca4`
- `0x180031010`

## pseudocode

```c
void __fastcall GenADTG::GetRowToSave(GenADTG *this, struct IRowsetUpdate *a2, __int64 a3, int a4, unsigned int a5)
{
  int v5; // ebp
  __int64 i; // rsi
  __int64 v11; // r8
  int v12; // eax
  int v13; // ebx
  unsigned int j; // r8d
  unsigned int v15; // ecx
  int v16; // eax

  v5 = 0;
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 20); i = (unsigned int)(i + 1) )
  {
    v11 = *(_QWORD *)(*((_QWORD *)this + 9) + 8 * i);
    if ( a4 )
      v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(**((_QWORD **)this + 3) + 32LL))(
              *((_QWORD *)this + 3),
              a3,
              v11,
              *((_QWORD *)this + 11));
    else
      v12 = ((__int64 (__fastcall *)(struct IRowsetUpdate *, __int64, __int64, _QWORD))a2->lpVtbl->GetOriginalData)(
              a2,
              a3,
              v11,
              *((_QWORD *)this + 12));
    v13 = v12;
    if ( v12 == -2147217887 || v12 == 265946 )
    {
      v5 = 1;
    }
    else if ( v12 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180049568[0] )
          bidTraceW(off_1800491C0[0], 1836032, off_180049568[0], (unsigned int)v12, 1793);
      }
      ThrowHR(v13);
    }
  }
  if ( v5 )
  {
    for ( j = 0; j < *((unsigned __int16 *)this + 32); ++j )
    {
      v15 = *(_DWORD *)(*(_QWORD *)(88LL * j + *((_QWORD *)this + 7) + 24) + *((_QWORD *)this + 11));
      if ( v15 <= 0xD )
      {
        v16 = 8217;
        if ( _bittest(&v16, v15) )
          continue;
      }
      if ( v15 != 8 )
      {
        if ( v15 == 2 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049560[0] )
            bidTraceW(off_1800491C0[0], 1857536, off_180049560[0], 2147749383LL, 1814);
          ThrowHR(-2147217913);
        }
LABEL_28:
        if ( (bidGblFlags & 2) != 0 && off_180049558[0] )
          bidTraceW(off_1800491C0[0], 1859584, off_180049558[0], 2147749409LL, 1816);
        ThrowHR(-2147217887);
      }
      if ( a5 != 1 )
        goto LABEL_28;
    }
  }
}

```

## disassembly

```asm
0x180006cbc  push    rbx
0x180006cbe  push    rbp
0x180006cbf  push    rsi
0x180006cc0  push    rdi
0x180006cc1  push    r12
0x180006cc3  push    r14
0x180006cc5  push    r15
0x180006cc7  sub     rsp, 30h
0x180006ccb  xor     ebp, ebp
0x180006ccd  mov     r14d, r9d
0x180006cd0  xor     esi, esi
0x180006cd2  mov     r15, r8
0x180006cd5  mov     r12, rdx
0x180006cd8  mov     rdi, rcx
0x180006cdb  cmp     esi, [rdi+50h]
0x180006cde  jnb     loc_180006D78
0x180006ce4  mov     r8, [rdi+48h]
0x180006ce8  mov     rdx, r15
0x180006ceb  mov     r8, [r8+rsi*8]
0x180006cef  test    r14d, r14d
0x180006cf2  jz      short loc_180006D05
0x180006cf4  mov     rcx, [rdi+18h]
0x180006cf8  mov     r9, [rdi+58h]
0x180006cfc  mov     rax, [rcx]
0x180006cff  mov     rax, [rax+20h]
0x180006d03  jmp     short loc_180006D14
0x180006d05  mov     rax, [r12]
0x180006d09  mov     rcx, r12
0x180006d0c  mov     r9, [rdi+60h]
0x180006d10  mov     rax, [rax+30h]
0x180006d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d19  mov     ebx, eax
0x180006d1b  cmp     eax, 80040E21h
0x180006d20  jz      short loc_180006D29
0x180006d22  cmp     eax, 40EDAh
0x180006d27  jnz     short loc_180006D30
0x180006d29  mov     ebp, 1
0x180006d2e  jmp     short loc_180006D34
0x180006d30  test    ebx, ebx
0x180006d32  js      short loc_180006D38
0x180006d34  inc     esi
0x180006d36  jmp     short loc_180006CDB
0x180006d38  test    byte ptr cs:_bidGblFlags, 2
0x180006d3f  jz      short loc_180006D70
0x180006d41  mov     rax, cs:off_180049568; "<GenADTG::GetRowToSave|ADO|ERR>  HRESUL"...
0x180006d48  test    rax, rax
0x180006d4b  jz      short loc_180006D70
0x180006d4d  mov     r8, cs:off_180049568; "<GenADTG::GetRowToSave|ADO|ERR>  HRESUL"...
0x180006d54  mov     r9d, ebx
0x180006d57  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180006d5e  mov     edx, 1C0400h
0x180006d63  mov     [rsp+68h+var_48], 701h
0x180006d6b  call    _bidTraceW
0x180006d70  mov     ecx, ebx; int
0x180006d72  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180006d78  test    ebp, ebp
0x180006d7a  jz      loc_180006E5A
0x180006d80  movzx   r9d, word ptr [rdi+40h]
0x180006d85  xor     r8d, r8d
0x180006d88  cmp     r8d, r9d
0x180006d8b  jnb     loc_180006E5A
0x180006d91  mov     eax, r8d
0x180006d94  imul    rcx, rax, 58h ; 'X'
0x180006d98  mov     rax, [rdi+38h]
0x180006d9c  mov     rdx, [rcx+rax+18h]
0x180006da1  mov     rax, [rdi+58h]
0x180006da5  mov     ecx, [rdx+rax]
0x180006da8  cmp     ecx, 0Dh
0x180006dab  ja      short loc_180006DB7
0x180006dad  mov     eax, 2019h
0x180006db2  bt      eax, ecx
0x180006db5  jb      short loc_180006DC6
0x180006db7  cmp     ecx, 8
0x180006dba  jnz     short loc_180006DCB
0x180006dbc  cmp     [rsp+68h+arg_20], 1
0x180006dc4  jnz     short loc_180006E14
0x180006dc6  inc     r8d
0x180006dc9  jmp     short loc_180006D88
0x180006dcb  cmp     ecx, 2
0x180006dce  jnz     short loc_180006E14
0x180006dd0  test    byte ptr cs:_bidGblFlags, cl
0x180006dd6  mov     ebx, 80040E07h
0x180006ddb  jz      short loc_180006E0C
0x180006ddd  mov     rax, cs:off_180049560; "<GenADTG::GetRowToSave|ADO|ERR>  HRESUL"...
0x180006de4  test    rax, rax
0x180006de7  jz      short loc_180006E0C
0x180006de9  mov     r8, cs:off_180049560; "<GenADTG::GetRowToSave|ADO|ERR>  HRESUL"...
0x180006df0  mov     r9d, ebx
0x180006df3  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180006dfa  mov     edx, 1C5800h
0x180006dff  mov     [rsp+68h+var_48], 716h
0x180006e07  call    _bidTraceW
0x180006e0c  mov     ecx, ebx; int
0x180006e0e  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180006e14  test    byte ptr cs:_bidGblFlags, 2
0x180006e1b  jz      short loc_180006E4F
0x180006e1d  mov     rax, cs:off_180049558; "<GenADTG::GetRowToSave|ADO|ERR>  HRESUL"...
0x180006e24  test    rax, rax
0x180006e27  jz      short loc_180006E4F
0x180006e29  mov     r8, cs:off_180049558; "<GenADTG::GetRowToSave|ADO|ERR>  HRESUL"...
0x180006e30  mov     r9d, 80040E21h
0x180006e36  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180006e3d  mov     edx, 1C6000h
0x180006e42  mov     [rsp+68h+var_48], 718h
0x180006e4a  call    _bidTraceW
0x180006e4f  mov     ecx, 80040E21h; int
0x180006e54  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180006e5a  add     rsp, 30h
0x180006e5e  pop     r15
0x180006e60  pop     r14
0x180006e62  pop     r12
0x180006e64  pop     rdi
0x180006e65  pop     rsi
0x180006e66  pop     rbp
0x180006e67  pop     rbx
0x180006e68  retn
```
