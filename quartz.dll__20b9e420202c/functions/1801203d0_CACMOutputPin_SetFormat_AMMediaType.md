# CACMOutputPin::SetFormat(_AMMediaType *)

- ea: `0x1801203d0`
- end: `0x18012059c`
- name: `?SetFormat@CACMOutputPin@@UEAAJPEAU_AMMediaType@@@Z`
- size: `460`
- prototype: `int(CACMOutputPin *__hidden this, struct _AMMediaType *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18002f03c`
- `0x18005caf4`
- `0x18005cb4c`
- `0x18011eeb0`
- `0x1801203d0`
- `0x18015bb98`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18012057d`
- `KERNEL32!LeaveCriticalSection` at `0x18012057d`
- `KERNEL32!EnterCriticalSection` at `0x180120413`
- `KERNEL32!EnterCriticalSection` at `0x180120413`
- `ole32!CoTaskMemFree` at `0x1801204ed`
- `ole32!CoTaskMemFree` at `0x1801204ed`
- `ole32!CoTaskMemAlloc` at `0x1801204fd`
- `ole32!CoTaskMemAlloc` at `0x1801204fd`

## pseudocode

```c
__int64 __fastcall CACMOutputPin::SetFormat(CACMOutputPin *this, struct _AMMediaType *a2)
{
  char v2; // bl
  CACMOutputPin *v6; // r14
  __int64 v7; // r15
  int *v8; // r8
  __int64 v9; // rax
  unsigned int v10; // ebx
  bool v11; // bp
  __int64 v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // rax
  struct _AMMediaType v15; // [rsp+20h] [rbp-98h] BYREF

  v2 = 0;
  if ( !a2 )
    return 2147500035LL;
  v6 = (CACMOutputPin *)((char *)this - 248);
  v7 = *((_QWORD *)this + 1);
  EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 136));
  v9 = *((_QWORD *)this + 1);
  if ( *(_DWORD *)(v9 + 40) )
  {
    v10 = -2147220956;
  }
  else
  {
    if ( *(_QWORD *)(*(_QWORD *)(v9 + 216) + 48LL) )
    {
      v11 = 0;
      if ( *((_QWORD *)this - 25) )
      {
        CMediaType::CMediaType((CMediaType *)&v15, a2, v8);
        v2 = 1;
        if ( (unsigned int)CMediaType::operator==((char *)this - 144, &v15) )
          v11 = 1;
      }
      if ( (v2 & 1) != 0 )
        FreeMediaType(&v15);
      if ( !v11 )
      {
        v10 = CACMOutputPin::CheckMediaType(v6, (const struct CMediaType *)a2);
        if ( v10 )
          goto LABEL_23;
        v12 = *((_QWORD *)this - 25);
        if ( v12 && (*(unsigned int (__fastcall **)(__int64, struct _AMMediaType *))(*(_QWORD *)v12 + 88LL))(v12, a2) )
        {
          v10 = -2147220992;
          goto LABEL_23;
        }
        v13 = *((unsigned __int16 *)a2->pbFormat + 8) + 18;
        CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 1) + 288LL));
        *(_QWORD *)(*((_QWORD *)this + 1) + 288LL) = CoTaskMemAlloc(v13);
        v14 = *((_QWORD *)this + 1);
        if ( !*(_QWORD *)(v14 + 288) )
        {
          v10 = -2147024882;
          goto LABEL_23;
        }
        *(_DWORD *)(v14 + 296) = v13;
        memcpy_0(*(void **)(*((_QWORD *)this + 1) + 288LL), a2->pbFormat, v13);
        if ( *((_QWORD *)this - 25) )
          (*(void (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(*((_QWORD *)this + 1) + 96LL) + 64LL))(
            *(_QWORD *)(*((_QWORD *)this + 1) + 96LL),
            ((unsigned __int64)this - 224) & -(__int64)(v6 != 0));
      }
      v10 = 0;
      goto LABEL_23;
    }
    v10 = -2147220983;
  }
LABEL_23:
  LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 136));
  return v10;
}

```

## disassembly

```asm
0x1801203d0  push    rbx
0x1801203d2  push    rbp
0x1801203d3  push    rsi
0x1801203d4  push    rdi
0x1801203d5  push    r14
0x1801203d7  push    r15
0x1801203d9  sub     rsp, 88h
0x1801203e0  xor     ebx, ebx
0x1801203e2  mov     rsi, rdx
0x1801203e5  mov     [rsp+0B8h+arg_8], ebx
0x1801203ec  mov     rdi, rcx
0x1801203ef  test    rdx, rdx
0x1801203f2  jnz     short loc_1801203FE
0x1801203f4  mov     eax, 80004003h
0x1801203f9  jmp     loc_18012058B
0x1801203fe  lea     r14, [rcx-0F8h]
0x180120405  mov     r15, [r14+100h]
0x18012040c  lea     rcx, [r15+88h]; lpCriticalSection
0x180120413  call    cs:__imp_EnterCriticalSection
0x18012041a  nop     dword ptr [rax+rax+00h]
0x18012041f  mov     rax, [rdi+8]
0x180120423  cmp     [rax+28h], ebx
0x180120426  jz      short loc_180120432
0x180120428  mov     ebx, 80040224h
0x18012042d  jmp     loc_180120576
0x180120432  mov     rax, [rax+0D8h]
0x180120439  cmp     [rax+30h], rbx
0x18012043d  jnz     short loc_180120449
0x18012043f  mov     ebx, 80040209h
0x180120444  jmp     loc_180120576
0x180120449  cmp     [rdi-0C8h], rbx
0x180120450  jz      short loc_18012047E
0x180120452  mov     rdx, rsi; struct _AMMediaType *
0x180120455  lea     rcx, [rsp+0B8h+var_98]; this
0x18012045a  call    ??0CMediaType@@QEAA@AEBU_AMMediaType@@PEAJ@Z; CMediaType::CMediaType(_AMMediaType const &,long *)
0x18012045f  lea     rcx, [rdi-90h]
0x180120466  lea     rdx, [rsp+0B8h+var_98]
0x18012046b  call    ??8CMediaType@@QEBAHAEBV0@@Z; CMediaType::operator==(CMediaType const &)
0x180120470  mov     ebx, 1
0x180120475  test    eax, eax
0x180120477  jz      short loc_18012047E
0x180120479  mov     bpl, bl
0x18012047c  jmp     short loc_180120481
0x18012047e  xor     bpl, bpl
0x180120481  test    bl, 1
0x180120484  jz      short loc_180120490
0x180120486  lea     rcx, [rsp+0B8h+var_98]; struct _AMMediaType *
0x18012048b  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180120490  test    bpl, bpl
0x180120493  jnz     loc_180120574
0x180120499  mov     rdx, rsi; struct CMediaType *
0x18012049c  mov     rcx, r14; this
0x18012049f  call    ?CheckMediaType@CACMOutputPin@@UEAAJPEBVCMediaType@@@Z; CACMOutputPin::CheckMediaType(CMediaType const *)
0x1801204a4  mov     ebx, eax
0x1801204a6  test    eax, eax
0x1801204a8  jnz     loc_180120576
0x1801204ae  mov     rcx, [rdi-0C8h]
0x1801204b5  test    rcx, rcx
0x1801204b8  jz      short loc_1801204D7
0x1801204ba  mov     rax, [rcx]
0x1801204bd  mov     rdx, rsi
0x1801204c0  mov     rax, [rax+58h]
0x1801204c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801204c9  test    eax, eax
0x1801204cb  jz      short loc_1801204D7
0x1801204cd  mov     ebx, 80040200h
0x1801204d2  jmp     loc_180120576
0x1801204d7  mov     rax, [rsi+50h]
0x1801204db  mov     rcx, [rdi+8]
0x1801204df  movzx   ebx, word ptr [rax+10h]
0x1801204e3  mov     rcx, [rcx+120h]; pv
0x1801204ea  add     ebx, 12h
0x1801204ed  call    cs:__imp_CoTaskMemFree
0x1801204f4  nop     dword ptr [rax+rax+00h]
0x1801204f9  mov     ecx, ebx; cb
0x1801204fb  mov     ebp, ebx
0x1801204fd  call    cs:__imp_CoTaskMemAlloc
0x180120504  nop     dword ptr [rax+rax+00h]
0x180120509  mov     rcx, [rdi+8]
0x18012050d  mov     [rcx+120h], rax
0x180120514  mov     rax, [rdi+8]
0x180120518  cmp     qword ptr [rax+120h], 0
0x180120520  jnz     short loc_180120529
0x180120522  mov     ebx, 8007000Eh
0x180120527  jmp     short loc_180120576
0x180120529  mov     [rax+128h], ebx
0x18012052f  mov     r8, rbp; Size
0x180120532  mov     rcx, [rdi+8]
0x180120536  mov     rdx, [rsi+50h]; Src
0x18012053a  mov     rcx, [rcx+120h]; void *
0x180120541  call    memcpy_0
0x180120546  cmp     qword ptr [rdi-0C8h], 0
0x18012054e  jz      short loc_180120574
0x180120550  mov     rax, [rdi+8]
0x180120554  neg     r14
0x180120557  sbb     rdx, rdx
0x18012055a  mov     rcx, [rax+60h]
0x18012055e  lea     rax, [rdi-0E0h]
0x180120565  and     rdx, rax
0x180120568  mov     r8, [rcx]
0x18012056b  mov     rax, [r8+40h]
0x18012056f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120574  xor     ebx, ebx
0x180120576  lea     rcx, [r15+88h]; lpCriticalSection
0x18012057d  call    cs:__imp_LeaveCriticalSection
0x180120584  nop     dword ptr [rax+rax+00h]
0x180120589  mov     eax, ebx
0x18012058b  add     rsp, 88h
0x180120592  pop     r15
0x180120594  pop     r14
0x180120596  pop     rdi
0x180120597  pop     rsi
0x180120598  pop     rbp
0x180120599  pop     rbx
0x18012059a  retn
```
