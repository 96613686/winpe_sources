# GenADTG::GetHRowsToStream(unsigned __int64 *,unsigned __int64 * *,ulong * *,unsigned __int64)

- ea: `0x1800068c8`
- end: `0x180006c54`
- name: `?GetHRowsToStream@GenADTG@@AEAAXPEA_KPEAPEA_KPEAPEAK_K@Z`
- size: `908`
- prototype: `void __fastcall(GenADTG *__hidden this, unsigned __int64 *, unsigned __int64 **, unsigned int **, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800060ec`
- `0x180008e00`

## callees

- `0x1800068c8`
- `0x18001b008`
- `0x18002dca4`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180006ba1`
- `ole32!CoTaskMemFree` at `0x180006bb8`
- `ole32!CoTaskMemFree` at `0x180006ba1`
- `ole32!CoTaskMemFree` at `0x180006bb8`
- `ole32!CoTaskMemAlloc` at `0x180006ab0`
- `ole32!CoTaskMemAlloc` at `0x180006ab0`

## pseudocode

```c
void __fastcall GenADTG::GetHRowsToStream(
        GenADTG *this,
        unsigned __int64 *a2,
        LPVOID *a3,
        LPVOID *a4,
        unsigned __int64 a5)
{
  __int64 v6; // r15
  bool v10; // cf
  unsigned int v11; // eax
  int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  LPVOID v15; // rcx
  unsigned int *v16; // rax
  int v17; // eax
  int v18; // ebx
  unsigned int v19; // ebx

  v6 = *((_QWORD *)this + 5);
  if ( !*((_DWORD *)this + 69) && v6 )
  {
    v10 = *((_DWORD *)this + 48) != 0;
    *((_DWORD *)this + 69) = 1;
    v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, unsigned __int64 *, LPVOID *, LPVOID *))(*(_QWORD *)v6 + 56LL))(
            v6,
            a5,
            v10 ? 7 : 4,
            a2,
            a3,
            a4);
    v12 = v11;
    if ( v11 == -2147024809 )
    {
      if ( *((_DWORD *)this + 71) != 1 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1800494D0[0] )
            bidTraceW(off_1800491C0[0], 2400256, off_1800494D0[0], 2147500037LL, 2344);
        }
        ThrowHR(-2147467259);
      }
LABEL_11:
      if ( (bidGblFlags & 2) != 0 && off_1800494C8[0] )
        bidTraceW(off_1800491C0[0], 2406400, off_1800494C8[0], v11, 2350);
      ThrowHR(v12);
    }
    if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147467263 )
      goto LABEL_11;
  }
  if ( !*((_DWORD *)this + 48) && !*a2 )
  {
    v13 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD, __int64, unsigned __int64 *, LPVOID *))(**((_QWORD **)this + 4) + 16LL))(
            *((_QWORD *)this + 4),
            a5,
            0,
            1,
            a2,
            a3);
    v14 = v13;
    if ( v13 == -2147024809 )
    {
      if ( *((_DWORD *)this + 71) != 1 )
        v14 = -2147467259;
LABEL_21:
      if ( (bidGblFlags & 2) != 0 && off_1800494C0[0] )
        bidTraceW(off_1800491C0[0], 2426880, off_1800494C0[0], v14, 2370);
      ThrowHR(v14);
    }
    if ( v13 < 0 )
      goto LABEL_21;
    if ( v6 )
    {
      if ( *a3 && *a2 )
      {
        v15 = *a4;
        if ( !*a4 )
        {
          v16 = (unsigned int *)CoTaskMemAlloc((unsigned int)(4 * *(_DWORD *)a2));
          *a4 = v16;
          v15 = v16;
          if ( !v16 )
          {
            if ( (bidGblFlags & 2) != 0 && off_1800494B8[0] )
              bidTraceW(off_1800491C0[0], 2438144, off_1800494B8[0], 2147942414LL, 2381);
            ThrowHR(-2147024882);
          }
        }
        v17 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, LPVOID, LPVOID))(*(_QWORD *)v6 + 64LL))(
                v6,
                a5,
                *a2,
                *a3,
                v15);
        v18 = v17;
        if ( v17 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800494B0[0] )
            bidTraceW(off_1800491C0[0], 2444288, off_1800494B0[0], (unsigned int)v17, 2387);
          ThrowHR(v18);
        }
        if ( *(_DWORD *)*a4 == 1 )
LABEL_40:
          *((_DWORD *)this + 70) = 1;
      }
      else if ( !*((_DWORD *)this + 70) )
      {
        CoTaskMemFree(*a4);
        *a4 = 0;
        CoTaskMemFree(*a3);
        *a3 = 0;
        v19 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64, unsigned __int64 *, LPVOID *, LPVOID *))(*(_QWORD *)v6 + 56LL))(
                v6,
                a5,
                1,
                a2,
                a3,
                a4);
        if ( (int)(v19 + 0x80000000) >= 0 && v19 != -2147467263 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800494A8[0] )
            bidTraceW(off_1800491C0[0], 2467840, off_1800494A8[0], v19, 2410);
          ThrowHR(v19);
        }
        goto LABEL_40;
      }
    }
  }
}

```

## disassembly

```asm
0x1800068c8  push    rbx
0x1800068ca  push    rbp
0x1800068cb  push    rsi
0x1800068cc  push    rdi
0x1800068cd  push    r14
0x1800068cf  push    r15
0x1800068d1  sub     rsp, 48h
0x1800068d5  cmp     dword ptr [rcx+114h], 0
0x1800068dc  mov     r14, r9
0x1800068df  mov     r15, [rcx+28h]
0x1800068e3  mov     rbp, r8
0x1800068e6  mov     rsi, rdx
0x1800068e9  mov     rdi, rcx
0x1800068ec  jnz     loc_1800069E6
0x1800068f2  test    r15, r15
0x1800068f5  jz      loc_1800069E6
0x1800068fb  mov     eax, [rdi+0C0h]
0x180006901  neg     eax
0x180006903  mov     dword ptr [rcx+114h], 1
0x18000690d  mov     rcx, [r15]
0x180006910  sbb     r8d, r8d
0x180006913  mov     [rsp+78h+var_50], r9
0x180006918  and     r8d, 3
0x18000691c  mov     [rsp+78h+var_58], rbp
0x180006921  mov     r9, rdx
0x180006924  add     r8d, 4
0x180006928  mov     rax, [rcx+38h]
0x18000692c  mov     rcx, r15
0x18000692f  mov     rdx, [rsp+78h+arg_20]
0x180006937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000693c  mov     ebx, eax
0x18000693e  cmp     eax, 80070057h
0x180006943  jnz     short loc_180006993
0x180006945  cmp     dword ptr [rdi+11Ch], 1
0x18000694c  jz      short loc_1800069A6
0x18000694e  test    byte ptr cs:_bidGblFlags, 2
0x180006955  mov     ebx, 80004005h
0x18000695a  jz      short loc_18000698B
0x18000695c  mov     rax, cs:off_1800494D0; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x180006963  test    rax, rax
0x180006966  jz      short loc_18000698B
0x180006968  mov     r8, cs:off_1800494D0; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x18000696f  mov     r9d, ebx
0x180006972  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180006979  mov     edx, 24A000h
0x18000697e  mov     dword ptr [rsp+78h+var_58], 928h
0x180006986  call    _bidTraceW
0x18000698b  mov     ecx, ebx; int
0x18000698d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180006993  mov     ecx, 80000000h
0x180006998  add     eax, ecx
0x18000699a  test    ecx, eax
0x18000699c  jnz     short loc_1800069E6
0x18000699e  cmp     ebx, 80004001h
0x1800069a4  jz      short loc_1800069E6
0x1800069a6  test    byte ptr cs:_bidGblFlags, 2
0x1800069ad  jz      short loc_1800069DE
0x1800069af  mov     rax, cs:off_1800494C8; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x1800069b6  test    rax, rax
0x1800069b9  jz      short loc_1800069DE
0x1800069bb  mov     r8, cs:off_1800494C8; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x1800069c2  mov     r9d, ebx
0x1800069c5  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800069cc  mov     edx, 24B800h
0x1800069d1  mov     dword ptr [rsp+78h+var_58], 92Eh
0x1800069d9  call    _bidTraceW
0x1800069de  mov     ecx, ebx; int
0x1800069e0  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800069e6  cmp     dword ptr [rdi+0C0h], 0
0x1800069ed  jnz     loc_180006B87
0x1800069f3  cmp     qword ptr [rsi], 0
0x1800069f7  jnz     loc_180006B87
0x1800069fd  mov     rcx, [rdi+20h]
0x180006a01  mov     r9d, 1
0x180006a07  mov     rdx, [rsp+78h+arg_20]
0x180006a0f  xor     r8d, r8d
0x180006a12  mov     [rsp+78h+var_50], rbp
0x180006a17  mov     [rsp+78h+var_58], rsi
0x180006a1c  mov     rax, [rcx]
0x180006a1f  mov     rax, [rax+10h]
0x180006a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a28  mov     ebx, eax
0x180006a2a  cmp     eax, 80070057h
0x180006a2f  jnz     short loc_180006A41
0x180006a31  cmp     dword ptr [rdi+11Ch], 1
0x180006a38  jz      short loc_180006A45
0x180006a3a  mov     ebx, 80004005h
0x180006a3f  jmp     short loc_180006A45
0x180006a41  test    eax, eax
0x180006a43  jns     short loc_180006A85
0x180006a45  test    byte ptr cs:_bidGblFlags, 2
0x180006a4c  jz      short loc_180006A7D
0x180006a4e  mov     rax, cs:off_1800494C0; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x180006a55  test    rax, rax
0x180006a58  jz      short loc_180006A7D
0x180006a5a  mov     r8, cs:off_1800494C0; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x180006a61  mov     r9d, ebx
0x180006a64  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180006a6b  mov     edx, 250800h
0x180006a70  mov     dword ptr [rsp+78h+var_58], 942h
0x180006a78  call    _bidTraceW
0x180006a7d  mov     ecx, ebx; int
0x180006a7f  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180006a85  test    r15, r15
0x180006a88  jz      loc_180006B87
0x180006a8e  cmp     qword ptr [rbp+0], 0
0x180006a93  jz      loc_180006B95
0x180006a99  cmp     qword ptr [rsi], 0
0x180006a9d  jz      loc_180006B95
0x180006aa3  mov     rcx, [r14]
0x180006aa6  test    rcx, rcx
0x180006aa9  jnz     short loc_180006B0C
0x180006aab  mov     ecx, [rsi]
0x180006aad  shl     ecx, 2; cb
0x180006ab0  call    cs:__imp_CoTaskMemAlloc
0x180006ab7  nop     dword ptr [rax+rax+00h]
0x180006abc  mov     [r14], rax
0x180006abf  mov     rcx, rax
0x180006ac2  test    rax, rax
0x180006ac5  jnz     short loc_180006B0C
0x180006ac7  test    byte ptr cs:_bidGblFlags, 2
0x180006ace  mov     ebx, 8007000Eh
0x180006ad3  jz      short loc_180006B04
0x180006ad5  mov     rax, cs:off_1800494B8; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x180006adc  test    rax, rax
0x180006adf  jz      short loc_180006B04
0x180006ae1  mov     r8, cs:off_1800494B8; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x180006ae8  mov     r9d, ebx
0x180006aeb  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180006af2  mov     edx, 253400h
0x180006af7  mov     dword ptr [rsp+78h+var_58], 94Dh
0x180006aff  call    _bidTraceW
0x180006b04  mov     ecx, ebx; int
0x180006b06  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180006b0c  mov     rax, [r15]
0x180006b0f  mov     r9, [rbp+0]
0x180006b13  mov     r8, [rsi]
0x180006b16  mov     rdx, [rsp+78h+arg_20]
0x180006b1e  mov     rax, [rax+40h]
0x180006b22  mov     [rsp+78h+var_58], rcx
0x180006b27  mov     rcx, r15
0x180006b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b2f  mov     ebx, eax
0x180006b31  test    eax, eax
0x180006b33  jns     short loc_180006B75
0x180006b35  test    byte ptr cs:_bidGblFlags, 2
0x180006b3c  jz      short loc_180006B6D
0x180006b3e  mov     rcx, cs:off_1800494B0; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x180006b45  test    rcx, rcx
0x180006b48  jz      short loc_180006B6D
0x180006b4a  mov     r8, cs:off_1800494B0; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x180006b51  mov     r9d, eax
0x180006b54  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180006b5b  mov     edx, 254C00h
0x180006b60  mov     dword ptr [rsp+78h+var_58], 953h
0x180006b68  call    _bidTraceW
0x180006b6d  mov     ecx, ebx; int
0x180006b6f  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180006b75  mov     rax, [r14]
0x180006b78  cmp     dword ptr [rax], 1
0x180006b7b  jnz     short loc_180006B87
0x180006b7d  mov     dword ptr [rdi+118h], 1
0x180006b87  add     rsp, 48h
0x180006b8b  pop     r15
0x180006b8d  pop     r14
0x180006b8f  pop     rdi
0x180006b90  pop     rsi
0x180006b91  pop     rbp
0x180006b92  pop     rbx
0x180006b93  retn
0x180006b95  cmp     dword ptr [rdi+118h], 0
0x180006b9c  jnz     short loc_180006B87
0x180006b9e  mov     rcx, [r14]; pv
0x180006ba1  call    cs:__imp_CoTaskMemFree
0x180006ba8  nop     dword ptr [rax+rax+00h]
0x180006bad  mov     qword ptr [r14], 0
0x180006bb4  mov     rcx, [rbp+0]; pv
0x180006bb8  call    cs:__imp_CoTaskMemFree
0x180006bbf  nop     dword ptr [rax+rax+00h]
0x180006bc4  mov     rdx, [rsp+78h+arg_20]
0x180006bcc  mov     r9, rsi
0x180006bcf  mov     qword ptr [rbp+0], 0
0x180006bd7  mov     r8d, 1
0x180006bdd  mov     rax, [r15]
0x180006be0  mov     rcx, r15
0x180006be3  mov     [rsp+78h+var_50], r14
0x180006be8  mov     [rsp+78h+var_58], rbp
0x180006bed  mov     rax, [rax+38h]
0x180006bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf6  mov     ebx, eax
0x180006bf8  mov     eax, 80000000h
0x180006bfd  lea     ecx, [rbx+rax]
0x180006c00  test    eax, ecx
0x180006c02  jnz     loc_180006B7D
0x180006c08  cmp     ebx, 80004001h
0x180006c0e  jz      loc_180006B7D
0x180006c14  test    byte ptr cs:_bidGblFlags, 2
0x180006c1b  jz      short loc_180006C4C
0x180006c1d  mov     rcx, cs:off_1800494A8; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x180006c24  test    rcx, rcx
0x180006c27  jz      short loc_180006C4C
0x180006c29  mov     r8, cs:off_1800494A8; "<GenADTG::GetHRowsToStream|ADO|ERR>  HR"...
0x180006c30  mov     r9d, ebx
0x180006c33  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180006c3a  mov     edx, 25A800h
0x180006c3f  mov     dword ptr [rsp+78h+var_58], 96Ah
0x180006c47  call    _bidTraceW
0x180006c4c  mov     ecx, ebx; int
0x180006c4e  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
