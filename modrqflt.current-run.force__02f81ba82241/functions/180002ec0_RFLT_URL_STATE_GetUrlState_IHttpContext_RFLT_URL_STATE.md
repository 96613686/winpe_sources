# RFLT_URL_STATE::GetUrlState(IHttpContext *,RFLT_URL_STATE * *)

- ea: `0x180002ec0`
- end: `0x180003079`
- name: `?GetUrlState@RFLT_URL_STATE@@SAJPEAVIHttpContext@@PEAPEAV1@@Z`
- size: `441`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct RFLT_URL_STATE **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002ab0`

## callees

- `0x180002ec0`
- `0x180005860`
- `0x180008010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180002f7b`
- `msvcrt!wcsrchr` at `0x180002f92`
- `msvcrt!wcsrchr` at `0x180002f7b`
- `msvcrt!wcsrchr` at `0x180002f92`
- `msvcrt!_wcslwr` at `0x180002fc7`
- `msvcrt!_wcslwr` at `0x180002fc7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002f56`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002f56`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002fbe`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002fbe`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002faa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002faa`

## pseudocode

```c
__int64 __fastcall RFLT_URL_STATE::GetUrlState(struct IHttpContext *a1, struct RFLT_URL_STATE **a2)
{
  int v4; // edi
  __int64 (__fastcall ***v5)(_QWORD); // rax
  __int64 v6; // r15
  _QWORD *v7; // rbx
  const wchar_t *v9; // rax
  wchar_t *v10; // rax
  wchar_t *v11; // rax
  const unsigned __int16 *v12; // rdx
  wchar_t *Str; // rax
  int v14; // eax

  v4 = 0;
  v5 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 152LL))(a1);
  v6 = (**v5)(v5);
  v7 = (_QWORD *)(**(__int64 (__fastcall ***)(__int64, void *))v6)(v6, g_pModuleContext);
  if ( v7 )
    goto LABEL_2;
  v7 = operator new(0x50u);
  if ( !v7 )
    return 2147942414LL;
  v7[1] = 0;
  *v7 = &RFLT_URL_STATE::`vftable';
  *((_DWORD *)v7 + 4) = -1;
  *((_DWORD *)v7 + 5) = 0;
  STRU::STRU((STRU *)(v7 + 3));
  v9 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a1 + 176LL))(a1, 0);
  v10 = wcsrchr(v9, 0x2Fu);
  if ( !v10 )
    v10 = (wchar_t *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a1 + 176LL))(a1, 0);
  v11 = wcsrchr(v10, 0x2Eu);
  v12 = L".";
  if ( v11 )
    v12 = v11;
  v4 = STRU::Copy((STRU *)(v7 + 3), v12);
  if ( v4 >= 0 )
  {
    Str = STRU::QueryStr((STRU *)(v7 + 3));
    _wcslwr(Str);
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD *, void *))(*(_QWORD *)v6 + 8LL))(v6, v7, g_pModuleContext);
    v4 = v14;
    if ( v14 >= 0 )
    {
LABEL_2:
      *a2 = (struct RFLT_URL_STATE *)v7;
      return (unsigned int)v4;
    }
    if ( v14 == -2147024811 )
    {
      (*(void (__fastcall **)(_QWORD *))*v7)(v7);
      v7 = (_QWORD *)(**(__int64 (__fastcall ***)(__int64, void *))v6)(v6, g_pModuleContext);
      if ( v7 )
      {
        v4 = 0;
        goto LABEL_2;
      }
      return 2147942414LL;
    }
  }
  (*(void (__fastcall **)(_QWORD *))*v7)(v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002ec0  push    rbx
0x180002ec2  push    rbp
0x180002ec3  push    rsi
0x180002ec4  push    rdi
0x180002ec5  push    r14
0x180002ec7  push    r15
0x180002ec9  sub     rsp, 28h
0x180002ecd  mov     rax, [rcx]
0x180002ed0  mov     rsi, rdx
0x180002ed3  mov     r14, rcx
0x180002ed6  xor     edi, edi
0x180002ed8  mov     rax, [rax+98h]
0x180002edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ee4  mov     rcx, rax
0x180002ee7  mov     rax, [rax]
0x180002eea  mov     rax, [rax]
0x180002eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef2  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x180002ef9  mov     r15, rax
0x180002efc  mov     rcx, r15
0x180002eff  mov     rax, [rax]
0x180002f02  mov     rax, [rax]
0x180002f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f0a  mov     rbx, rax
0x180002f0d  test    rax, rax
0x180002f10  jz      short loc_180002F24
0x180002f12  mov     [rsi], rbx
0x180002f15  mov     eax, edi
0x180002f17  add     rsp, 28h
0x180002f1b  pop     r15
0x180002f1d  pop     r14
0x180002f1f  pop     rdi
0x180002f20  pop     rsi
0x180002f21  pop     rbp
0x180002f22  pop     rbx
0x180002f23  retn
0x180002f24  mov     ecx, 50h ; 'P'; Size
0x180002f29  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002f2e  mov     rbx, rax
0x180002f31  test    rax, rax
0x180002f34  jz      loc_18000304A
0x180002f3a  lea     rax, ??_7RFLT_URL_STATE@@6B@; const RFLT_URL_STATE::`vftable'
0x180002f41  mov     [rbx+8], rdi
0x180002f45  lea     rcx, [rbx+18h]
0x180002f49  mov     [rbx], rax
0x180002f4c  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x180002f53  mov     [rbx+14h], edi
0x180002f56  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002f5c  mov     rax, [r14]
0x180002f5f  xor     edx, edx
0x180002f61  mov     rcx, r14
0x180002f64  mov     edi, 2Fh ; '/'
0x180002f69  mov     rax, [rax+0B0h]
0x180002f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f75  mov     rcx, rax; Str
0x180002f78  movzx   edx, di; Ch
0x180002f7b  call    cs:__imp_wcsrchr
0x180002f81  test    rax, rax
0x180002f84  jz      loc_180003029
0x180002f8a  mov     edx, 2Eh ; '.'; Ch
0x180002f8f  mov     rcx, rax; Str
0x180002f92  call    cs:__imp_wcsrchr
0x180002f98  test    rax, rax
0x180002f9b  lea     rdx, asc_1800097A0; "."
0x180002fa2  lea     rcx, [rbx+18h]
0x180002fa6  cmovnz  rdx, rax
0x180002faa  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002fb0  mov     edi, eax
0x180002fb2  test    eax, eax
0x180002fb4  js      loc_18000305C
0x180002fba  lea     rcx, [rbx+18h]
0x180002fbe  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180002fc4  mov     rcx, rax; String
0x180002fc7  call    cs:__imp__wcslwr
0x180002fcd  mov     rax, [r15]
0x180002fd0  mov     rdx, rbx
0x180002fd3  mov     r8, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x180002fda  mov     rcx, r15
0x180002fdd  mov     rax, [rax+8]
0x180002fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fe6  mov     edi, eax
0x180002fe8  test    eax, eax
0x180002fea  jns     loc_180002F12
0x180002ff0  cmp     eax, 80070055h
0x180002ff5  jnz     short loc_18000305C
0x180002ff7  mov     rax, [rbx]
0x180002ffa  mov     rcx, rbx
0x180002ffd  mov     rax, [rax]
0x180003000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003005  mov     rax, [r15]
0x180003008  mov     rcx, r15
0x18000300b  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x180003012  mov     rax, [rax]
0x180003015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000301a  mov     rbx, rax
0x18000301d  test    rax, rax
0x180003020  jz      short loc_18000304A
0x180003022  xor     edi, edi
0x180003024  jmp     loc_180002F12
0x180003029  mov     rax, [r14]
0x18000302c  xor     edx, edx
0x18000302e  mov     rcx, r14
0x180003031  mov     edi, 2Eh ; '.'
0x180003036  mov     rax, [rax+0B0h]
0x18000303d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003042  movzx   edx, di
0x180003045  jmp     loc_180002F8F
0x18000304a  mov     eax, 8007000Eh
0x18000304f  add     rsp, 28h
0x180003053  pop     r15
0x180003055  pop     r14
0x180003057  pop     rdi
0x180003058  pop     rsi
0x180003059  pop     rbp
0x18000305a  pop     rbx
0x18000305b  retn
0x18000305c  mov     rax, [rbx]
0x18000305f  mov     rcx, rbx
0x180003062  mov     rax, [rax]
0x180003065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000306a  mov     eax, edi
0x18000306c  add     rsp, 28h
0x180003070  pop     r15
0x180003072  pop     r14
0x180003074  pop     rdi
0x180003075  pop     rsi
0x180003076  pop     rbp
0x180003077  pop     rbx
0x180003078  retn
```
