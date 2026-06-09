# CKernCache::Init(HFONT__ *)

- ea: `0x18018c68c`
- end: `0x18018c82e`
- name: `?Init@CKernCache@@AEAAXPEAUHFONT__@@@Z`
- size: `418`
- prototype: `void __fastcall(CKernCache *__hidden this, HFONT h)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18012aa54`

## callees

- `0x180038c24`
- `0x1800f0cb8`
- `0x18013ce80`
- `0x18013d250`
- `0x18013d25c`
- `0x18013dce6`
- `0x1801515b0`
- `0x18018c55c`
- `0x18018c68c`
- `0x1801eb63c`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x18018c6ea`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x18018c6ea`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18018c72e`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18018c7e7`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18018c72e`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18018c7e7`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x18018c710`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x18018c710`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18018c7f6`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18018c7f6`

## pseudocode

```c
void __fastcall CKernCache::Init(CKernCache *this, HFONT h)
{
  HDC ScreenDC; // rax
  HDC v5; // rbp
  HFONT v6; // rax
  HFONT v7; // rsi
  HGDIOBJ v8; // r15
  signed int KerningPairs; // eax
  unsigned __int64 v10; // rdi
  int PrimeLessThan; // ebx
  struct tagKERNINGPAIR *v12; // r14
  unsigned __int64 v13; // rdx
  int v14; // r12d
  __int64 v15; // rbx
  LOGFONTW pv; // [rsp+20h] [rbp-A8h] BYREF

  ScreenDC = CW32System::GetScreenDC();
  *((_DWORD *)this + 8) = 2;
  v5 = ScreenDC;
  memset_0(&pv, 0, sizeof(pv));
  if ( GetObjectW(h, 92, &pv) )
  {
    pv.lfHeight = -2048;
    pv.lfCharSet = 0;
    v6 = CreateFontIndirectW(&pv);
    v7 = v6;
    if ( v6 )
    {
      v8 = SelectObject(v5, v6);
      KerningPairs = CW32System::GetKerningPairs(v5, 0, 0);
      v10 = KerningPairs;
      if ( KerningPairs )
      {
        PrimeLessThan = FindPrimeLessThan(5 * KerningPairs / 2);
        if ( PrimeLessThan )
        {
          v12 = (struct tagKERNINGPAIR *)operator new[](saturated_mul(v10, 8u));
          CW32System::GetKerningPairs(v5, v10, v12);
          CArrayBase::ArAdd(this, PrimeLessThan, 0);
          v14 = 0;
          if ( (int)v10 > 0 )
          {
            v15 = 0;
            do
            {
              CKernCache::Add(this, v12[v15].wFirst, v12[v15].wSecond, v12[v15].iKernAmount);
              ++v14;
              ++v15;
            }
            while ( v14 < (int)v10 );
          }
          operator delete(v12, v13);
          *((_DWORD *)this + 8) = 1;
        }
      }
      if ( v8 )
        SelectObject(v5, v8);
      DeleteObject(v7);
    }
  }
}

```

## disassembly

```asm
0x18018c68c  mov     [rsp+arg_10], rbx
0x18018c691  push    rbp
0x18018c692  push    rsi
0x18018c693  push    rdi
0x18018c694  push    r12
0x18018c696  push    r13
0x18018c698  push    r14
0x18018c69a  push    r15
0x18018c69c  sub     rsp, 90h
0x18018c6a3  mov     rax, cs:__security_cookie
0x18018c6aa  xor     rax, rsp
0x18018c6ad  mov     [rsp+0C8h+var_48], rax
0x18018c6b5  mov     rbx, rdx
0x18018c6b8  mov     r13, rcx
0x18018c6bb  call    ?GetScreenDC@CW32System@@SAPEAUHDC__@@XZ; CW32System::GetScreenDC(void)
0x18018c6c0  mov     r14d, 2
0x18018c6c6  lea     rcx, [rsp+0C8h+pv]; void *
0x18018c6cb  xor     edx, edx; Val
0x18018c6cd  mov     [r13+20h], r14d
0x18018c6d1  mov     rbp, rax
0x18018c6d4  lea     edi, [r14+5Ah]
0x18018c6d8  mov     r8d, edi; Size
0x18018c6db  call    memset_0
0x18018c6e0  lea     r8, [rsp+0C8h+pv]; pv
0x18018c6e5  mov     edx, edi; c
0x18018c6e7  mov     rcx, rbx; h
0x18018c6ea  call    cs:__imp_GetObjectW
0x18018c6f1  nop     dword ptr [rax+rax+00h]
0x18018c6f6  test    eax, eax
0x18018c6f8  jz      loc_18018C802
0x18018c6fe  lea     rcx, [rsp+0C8h+pv]; lplf
0x18018c703  mov     [rsp+0C8h+pv], 0FFFFF800h
0x18018c70b  mov     [rsp+0C8h+var_91], 0
0x18018c710  call    cs:__imp_CreateFontIndirectW
0x18018c717  nop     dword ptr [rax+rax+00h]
0x18018c71c  mov     rsi, rax
0x18018c71f  test    rax, rax
0x18018c722  jz      loc_18018C802
0x18018c728  mov     rdx, rax; h
0x18018c72b  mov     rcx, rbp; hdc
0x18018c72e  call    cs:__imp_SelectObject
0x18018c735  nop     dword ptr [rax+rax+00h]
0x18018c73a  xor     r8d, r8d; struct tagKERNINGPAIR *
0x18018c73d  xor     edx, edx; unsigned int
0x18018c73f  mov     rcx, rbp; HDC
0x18018c742  mov     r15, rax
0x18018c745  call    ?GetKerningPairs@CW32System@@SAKPEAUHDC__@@KPEAUtagKERNINGPAIR@@@Z; CW32System::GetKerningPairs(HDC__ *,ulong,tagKERNINGPAIR *)
0x18018c74a  movsxd  rdi, eax
0x18018c74d  test    eax, eax
0x18018c74f  jz      loc_18018C7DC
0x18018c755  lea     eax, [rdi+rdi*4]
0x18018c758  cdq
0x18018c759  idiv    r14d
0x18018c75c  mov     ecx, eax; int
0x18018c75e  call    ?FindPrimeLessThan@@YAHH@Z; FindPrimeLessThan(int)
0x18018c763  mov     ebx, eax
0x18018c765  test    eax, eax
0x18018c767  jz      short loc_18018C7DC
0x18018c769  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18018c770  lea     eax, [r14+6]
0x18018c774  mul     rdi
0x18018c777  cmovb   rax, rcx
0x18018c77b  mov     rcx, rax; unsigned __int64
0x18018c77e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18018c783  mov     r8, rax; struct tagKERNINGPAIR *
0x18018c786  mov     edx, edi; unsigned int
0x18018c788  mov     rcx, rbp; HDC
0x18018c78b  mov     r14, rax
0x18018c78e  call    ?GetKerningPairs@CW32System@@SAKPEAUHDC__@@KPEAUtagKERNINGPAIR@@@Z; CW32System::GetKerningPairs(HDC__ *,ulong,tagKERNINGPAIR *)
0x18018c793  xor     r8d, r8d; int *
0x18018c796  mov     edx, ebx; int
0x18018c798  mov     rcx, r13; this
0x18018c79b  call    ?ArAdd@CArrayBase@@IEAAPEAXJPEAJ@Z; CArrayBase::ArAdd(long,long *)
0x18018c7a0  xor     r12d, r12d
0x18018c7a3  test    edi, edi
0x18018c7a5  jle     short loc_18018C7CC
0x18018c7a7  xor     ebx, ebx
0x18018c7a9  mov     r9d, [r14+rbx*8+4]; int
0x18018c7ae  mov     rcx, r13; this
0x18018c7b1  movzx   r8d, word ptr [r14+rbx*8+2]; unsigned __int16
0x18018c7b7  movzx   edx, word ptr [r14+rbx*8]; unsigned __int16
0x18018c7bc  call    ?Add@CKernCache@@AEAAXGGJ@Z; CKernCache::Add(ushort,ushort,long)
0x18018c7c1  inc     r12d
0x18018c7c4  inc     rbx
0x18018c7c7  cmp     r12d, edi
0x18018c7ca  jl      short loc_18018C7A9
0x18018c7cc  mov     rcx, r14; void *
0x18018c7cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18018c7d4  mov     dword ptr [r13+20h], 1
0x18018c7dc  test    r15, r15
0x18018c7df  jz      short loc_18018C7F3
0x18018c7e1  mov     rdx, r15; h
0x18018c7e4  mov     rcx, rbp; hdc
0x18018c7e7  call    cs:__imp_SelectObject
0x18018c7ee  nop     dword ptr [rax+rax+00h]
0x18018c7f3  mov     rcx, rsi; ho
0x18018c7f6  call    cs:__imp_DeleteObject
0x18018c7fd  nop     dword ptr [rax+rax+00h]
0x18018c802  mov     rcx, [rsp+0C8h+var_48]
0x18018c80a  xor     rcx, rsp; StackCookie
0x18018c80d  call    __security_check_cookie
0x18018c812  mov     rbx, [rsp+0C8h+arg_10]
0x18018c81a  add     rsp, 90h
0x18018c821  pop     r15
0x18018c823  pop     r14
0x18018c825  pop     r13
0x18018c827  pop     r12
0x18018c829  pop     rdi
0x18018c82a  pop     rsi
0x18018c82b  pop     rbp
0x18018c82c  retn
```
