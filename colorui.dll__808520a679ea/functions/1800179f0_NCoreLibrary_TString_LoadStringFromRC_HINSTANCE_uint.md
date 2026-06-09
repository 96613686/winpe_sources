# NCoreLibrary::TString::LoadStringFromRC(HINSTANCE__ *,uint)

- ea: `0x1800179f0`
- end: `0x180017aaa`
- name: `?LoadStringFromRC@TString@NCoreLibrary@@QEAAJPEAUHINSTANCE__@@I@Z`
- size: `186`
- prototype: `__int64 __fastcall(NCoreLibrary::TString *this, HINSTANCE, UINT)`
- caller_count: `26`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000bd60`
- `0x18000bee0`
- `0x18000d060`
- `0x18000d338`
- `0x18000d7dc`
- `0x18000de80`
- `0x18000e7ac`
- `0x18000e9d8`
- `0x18000ed10`
- `0x18000f074`
- `0x18000ffe0`
- `0x180010404`
- `0x180010780`
- `0x180011514`
- `0x180011a34`
- `0x180011fb4`
- `0x180012228`
- `0x180012bd0`
- `0x180012e80`
- `0x180013580`
- `0x180014a30`
- `0x180014b78`
- `0x180015c5c`
- `0x180015cc8`
- `0x180015ecc`
- `0x180016a70`

## callees

- `0x180001334`
- `0x18000134c`
- `0x1800179f0`

## import_xrefs

- `USER32!LoadStringW` at `0x180017a1b`
- `USER32!LoadStringW` at `0x180017a1b`

## pseudocode

```c
__int64 __fastcall NCoreLibrary::TString::LoadStringFromRC(NCoreLibrary::TString *this, HINSTANCE a2, UINT a3)
{
  size_t v5; // rcx
  int v7; // edi
  int StringW; // eax
  __int64 v9; // rax
  WCHAR *v10; // rax
  WCHAR *v11; // rbx
  __int16 *v13; // rcx

  v5 = 2048;
  v7 = 1024;
  while ( 1 )
  {
    v10 = (WCHAR *)operator new(v5);
    v11 = v10;
    if ( !v10 )
      return 2147942414LL;
    StringW = LoadStringW(a2, a3, v10, v7);
    if ( !StringW )
    {
      operator delete(v11);
      return 2147500037LL;
    }
    if ( v7 - StringW > 1 )
      break;
    operator delete(v11);
    v7 += 1024;
    v9 = 2LL * v7;
    if ( !is_mul_ok(v7, 2u) )
      v9 = -1;
    v5 = v9;
  }
  v13 = (__int16 *)*((_QWORD *)this + 1);
  if ( v13 != (__int16 *)&NCoreLibrary::TString::gszNullState && v13 != &word_180021DD6 )
    operator delete(v13);
  *((_QWORD *)this + 1) = v11;
  return 0;
}

```

## disassembly

```asm
0x1800179f0  push    rbx
0x1800179f2  push    rbp
0x1800179f3  push    rsi
0x1800179f4  push    rdi
0x1800179f5  push    r14
0x1800179f7  sub     rsp, 20h
0x1800179fb  mov     rsi, rcx
0x1800179fe  mov     ebp, r8d
0x180017a01  mov     ecx, 800h
0x180017a06  mov     r14, rdx
0x180017a09  mov     edi, 400h
0x180017a0e  jmp     short loc_180017A55
0x180017a10  mov     r9d, edi; cchBufferMax
0x180017a13  mov     r8, rbx; lpBuffer
0x180017a16  mov     edx, ebp; uID
0x180017a18  mov     rcx, r14; hInstance
0x180017a1b  call    cs:__imp_LoadStringW
0x180017a21  test    eax, eax
0x180017a23  jz      short loc_180017A9B
0x180017a25  mov     ecx, edi
0x180017a27  sub     ecx, eax
0x180017a29  cmp     ecx, 1
0x180017a2c  jg      short loc_180017A72
0x180017a2e  mov     rcx, rbx; Block
0x180017a31  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017a36  add     edi, 400h
0x180017a3c  mov     eax, 2
0x180017a41  movsxd  rcx, edi
0x180017a44  mul     rcx
0x180017a47  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180017a4e  cmovb   rax, rcx
0x180017a52  mov     rcx, rax; Size
0x180017a55  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017a5a  mov     rbx, rax
0x180017a5d  test    rax, rax
0x180017a60  jnz     short loc_180017A10
0x180017a62  mov     eax, 8007000Eh
0x180017a67  add     rsp, 20h
0x180017a6b  pop     r14
0x180017a6d  pop     rdi
0x180017a6e  pop     rsi
0x180017a6f  pop     rbp
0x180017a70  pop     rbx
0x180017a71  retn
0x180017a72  mov     rcx, [rsi+8]; Block
0x180017a76  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180017a7d  cmp     rcx, rax
0x180017a80  jz      short loc_180017A93
0x180017a82  lea     rax, word_180021DD6
0x180017a89  cmp     rcx, rax
0x180017a8c  jz      short loc_180017A93
0x180017a8e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017a93  mov     [rsi+8], rbx
0x180017a97  xor     eax, eax
0x180017a99  jmp     short loc_180017A67
0x180017a9b  mov     rcx, rbx; Block
0x180017a9e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017aa3  mov     eax, 80004005h
0x180017aa8  jmp     short loc_180017A67
```
