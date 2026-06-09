# CSpellerGlobalState::AddNewInputMethod(ulong,Microsoft::WRL::Wrappers::HString *)

- ea: `0x180114790`
- end: `0x180114909`
- name: `?AddNewInputMethod@CSpellerGlobalState@@QEAAJKPEAVHString@Wrappers@WRL@Microsoft@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(CSpellerGlobalState *__hidden this, unsigned int, struct Microsoft::WRL::Wrappers::HString *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800d7998`
- `0x180274b8c`
- `0x1802773c0`

## callees

- `0x1800facf0`
- `0x180114790`
- `0x18013d268`
- `0x18013dcda`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011487a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801148e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011487a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801148e3`

## pseudocode

```c
__int64 __fastcall CSpellerGlobalState::AddNewInputMethod(CSpellerGlobalState *this, int a2, HSTRING *p_string)
{
  __int64 v3; // r10
  unsigned int v7; // r8d
  int v8; // ebp
  char v9; // r9
  int i; // edx
  _DWORD *v11; // r11
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  void *v14; // r14
  HSTRING v15; // rbx
  __int64 v16; // rbx
  unsigned int v17; // edi
  unsigned int v18; // eax
  HSTRING string; // [rsp+50h] [rbp+8h] BYREF

  v3 = *((_QWORD *)this + 4);
  v7 = *(_DWORD *)(v3 + 4);
  if ( !v7 )
    goto LABEL_11;
  v8 = 0;
  v9 = 0;
  for ( i = 0; i < v7; ++i )
  {
    if ( i < 0 || i >= v7 )
      v11 = 0;
    else
      v11 = *(_DWORD **)((unsigned int)(*(_DWORD *)(v3 + 8) * i) + *(_QWORD *)(v3 + 16));
    if ( *v11 == a2 )
      v9 = 1;
  }
  if ( !v9 )
  {
LABEL_11:
    string = 0;
    if ( !p_string )
    {
      v12 = *((_QWORD *)this + 37);
      v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v12 + 56LL);
      WindowsDeleteString(0);
      string = 0;
      v8 = v13(v12, &string);
      if ( v8 < 0 )
      {
LABEL_18:
        WindowsDeleteString(string);
        return (unsigned int)v8;
      }
      p_string = &string;
    }
    v14 = operator new(0x10u);
    *(_DWORD *)v14 = a2;
    *((_QWORD *)v14 + 1) = 0;
    v15 = *p_string;
    *p_string = 0;
    WindowsDeleteString(*((HSTRING *)v14 + 1));
    *((_QWORD *)v14 + 1) = v15;
    v16 = *((_QWORD *)this + 4);
    v17 = *(_DWORD *)(v16 + 4);
    v8 = CSpellArray<CSpellCheckScripts *>::EnsureSize(v16, v17 + 1);
    if ( !v8 )
    {
      v18 = *(_DWORD *)(v16 + 4);
      if ( v17 < v18 )
        memmove_0(
          (void *)(*(_QWORD *)(v16 + 16) + (v17 + 1) * *(_DWORD *)(v16 + 8)),
          (const void *)(*(_QWORD *)(v16 + 16) + v17 * *(_DWORD *)(v16 + 8)),
          *(_DWORD *)(v16 + 8) * (v18 - v17));
      *(_QWORD *)(*(_DWORD *)(v16 + 8) * v17 + *(_QWORD *)(v16 + 16)) = v14;
      ++*(_DWORD *)(v16 + 4);
    }
    goto LABEL_18;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180114790  mov     [rsp+arg_8], rbx
0x180114795  mov     [rsp+arg_10], rbp
0x18011479a  push    rsi
0x18011479b  push    rdi
0x18011479c  push    r13
0x18011479e  push    r14
0x1801147a0  push    r15
0x1801147a2  sub     rsp, 20h
0x1801147a6  mov     r10, [rcx+20h]
0x1801147aa  mov     rdi, r8
0x1801147ad  mov     r15d, edx
0x1801147b0  mov     rsi, rcx
0x1801147b3  mov     r13d, 1
0x1801147b9  mov     r8d, [r10+4]
0x1801147bd  test    r8d, r8d
0x1801147c0  jz      short loc_180114802
0x1801147c2  xor     ebp, ebp
0x1801147c4  xor     r9b, r9b
0x1801147c7  xor     edx, edx
0x1801147c9  test    edx, edx
0x1801147cb  js      short loc_1801147E3
0x1801147cd  cmp     edx, r8d
0x1801147d0  jnb     short loc_1801147E3
0x1801147d2  mov     rax, [r10+10h]
0x1801147d6  mov     ecx, edx
0x1801147d8  imul    ecx, [r10+8]
0x1801147dd  mov     r11, [rcx+rax]
0x1801147e1  jmp     short loc_1801147E6
0x1801147e3  xor     r11d, r11d
0x1801147e6  cmp     [r11], r15d
0x1801147e9  movzx   r9d, r9b
0x1801147ed  cmovz   r9d, r13d
0x1801147f1  add     edx, r13d
0x1801147f4  cmp     edx, r8d
0x1801147f7  jb      short loc_1801147C9
0x1801147f9  test    r9b, r9b
0x1801147fc  jnz     loc_1801148EF
0x180114802  mov     [rsp+48h+string], 0
0x18011480b  test    rdi, rdi
0x18011480e  jnz     short loc_180114854
0x180114810  mov     rdi, [rsi+128h]
0x180114817  xor     ecx, ecx; string
0x180114819  mov     rax, [rdi]
0x18011481c  mov     rbx, [rax+38h]
0x180114820  call    cs:__imp_WindowsDeleteString
0x180114827  nop     dword ptr [rax+rax+00h]
0x18011482c  lea     rdx, [rsp+48h+string]
0x180114831  mov     [rsp+48h+string], 0
0x18011483a  mov     rcx, rdi
0x18011483d  mov     rax, rbx
0x180114840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114845  mov     ebp, eax
0x180114847  test    eax, eax
0x180114849  js      loc_1801148DE
0x18011484f  lea     rdi, [rsp+48h+string]
0x180114854  mov     ecx, 10h; Size
0x180114859  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18011485e  mov     r14, rax
0x180114861  mov     [rax], r15d
0x180114864  mov     qword ptr [rax+8], 0
0x18011486c  mov     rbx, [rdi]
0x18011486f  mov     qword ptr [rdi], 0
0x180114876  mov     rcx, [rax+8]; string
0x18011487a  call    cs:__imp_WindowsDeleteString
0x180114881  nop     dword ptr [rax+rax+00h]
0x180114886  mov     [r14+8], rbx
0x18011488a  mov     rbx, [rsi+20h]
0x18011488e  mov     rcx, rbx
0x180114891  mov     edi, [rbx+4]
0x180114894  lea     r15d, [rdi+1]
0x180114898  mov     edx, r15d
0x18011489b  call    ?EnsureSize@?$CSpellArray@PEAVCSpellCheckScripts@@@@AEAAJJ@Z; CSpellArray<CSpellCheckScripts *>::EnsureSize(long)
0x1801148a0  mov     ebp, eax
0x1801148a2  test    eax, eax
0x1801148a4  jnz     short loc_1801148DE
0x1801148a6  mov     eax, [rbx+4]
0x1801148a9  cmp     edi, eax
0x1801148ab  jnb     short loc_1801148CE
0x1801148ad  mov     ecx, [rbx+8]
0x1801148b0  sub     eax, edi
0x1801148b2  mov     edx, ecx
0x1801148b4  imul    eax, ecx
0x1801148b7  imul    edx, edi
0x1801148ba  imul    ecx, r15d
0x1801148be  mov     r8d, eax; Size
0x1801148c1  add     rdx, [rbx+10h]; Src
0x1801148c5  add     rcx, [rbx+10h]; void *
0x1801148c9  call    memmove_0
0x1801148ce  imul    edi, [rbx+8]
0x1801148d2  mov     rax, [rbx+10h]
0x1801148d6  mov     [rdi+rax], r14
0x1801148da  add     [rbx+4], r13d
0x1801148de  mov     rcx, [rsp+48h+string]; string
0x1801148e3  call    cs:__imp_WindowsDeleteString
0x1801148ea  nop     dword ptr [rax+rax+00h]
0x1801148ef  mov     rbx, [rsp+48h+arg_8]
0x1801148f4  mov     eax, ebp
0x1801148f6  mov     rbp, [rsp+48h+arg_10]
0x1801148fb  add     rsp, 20h
0x1801148ff  pop     r15
0x180114901  pop     r14
0x180114903  pop     r13
0x180114905  pop     rdi
0x180114906  pop     rsi
0x180114907  retn
```
