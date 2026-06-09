# GetECDefaultHeightAndWidth(ITextServices *,HDC__ *,long,long,long,long *,long *,long *)

- ea: `0x18005ba50`
- end: `0x18005bb50`
- name: `?GetECDefaultHeightAndWidth@@YAJPEAVITextServices@@PEAUHDC__@@JJJPEAJ22@Z`
- size: `256`
- prototype: `__int64 __usercall@<rax>(struct ITextServices *this@<rcx>, HDC@<rdx>, int@<r8d>, int@<r9d>, int, int *, int *, int *)`
- caller_count: `5`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002cfd0`
- `0x18004e640`
- `0x18004f6e0`
- `0x180060b40`
- `0x180069e28`

## callees

- `0x18000b440`
- `0x18002c900`
- `0x180038bd0`
- `0x18003d134`
- `0x18003dbb4`
- `0x18005ba50`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18005ba65`
- `KERNEL32!EnterCriticalSection` at `0x18005ba65`
- `KERNEL32!LeaveCriticalSection` at `0x18005bb3d`
- `KERNEL32!LeaveCriticalSection` at `0x18005bb3d`

## pseudocode

```c
__int64 __fastcall GetECDefaultHeightAndWidth(
        struct ITextServices *this,
        HDC a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int *a6,
        int *a7,
        int *a8)
{
  int v9; // eax
  CFontCache *v10; // rdi
  int v11; // ebx
  __m128i *CharFormat; // rax
  __int16 *Ccs; // rax
  __int16 *v14; // rbx
  unsigned int v15; // edi
  int v16; // edx
  __int16 v17; // dx

  EnterCriticalSection(&g_CriticalSection);
  v9 = CW32System::MulDiv(a5, 1, 1);
  v10 = qword_1800A3EE0;
  v11 = v9;
  CharFormat = (__m128i *)CTxtArray::GetCharFormat((struct ITextServices *)((char *)this + 248), -1);
  Ccs = (__int16 *)CFontCache::GetCcs(v10, CharFormat, v11, 0, 0);
  v14 = Ccs;
  if ( Ccs )
  {
    if ( a6 )
      *a6 = Ccs[47];
    if ( a7 )
      *a7 = Ccs[49];
    if ( a8 )
      *a8 = Ccs[50];
    if ( CTxtEdit::fUseUIFont(this) || (v16 = 1, (*(_DWORD *)(*((_QWORD *)this + 8) + 56LL) & 0x20000) == 0) )
      v16 = 0;
    v15 = v14[45] + 2 * CCcs::AdjustFEHeight((CCcs *)v14, v16);
    v17 = v14[5];
    if ( v17 )
      v14[5] = v17 - 1;
  }
  else
  {
    v15 = 0;
  }
  LeaveCriticalSection(&g_CriticalSection);
  return v15;
}

```

## disassembly

```asm
0x18005ba50  push    rbx
0x18005ba52  push    rbp
0x18005ba53  push    rsi
0x18005ba54  push    rdi
0x18005ba55  push    r14
0x18005ba57  sub     rsp, 30h
0x18005ba5b  mov     rsi, rcx
0x18005ba5e  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005ba65  call    cs:__imp_EnterCriticalSection
0x18005ba6b  mov     ecx, [rsp+58h+arg_20]; int
0x18005ba72  mov     r14d, 1
0x18005ba78  mov     r8d, r14d; int
0x18005ba7b  mov     edx, r14d; int
0x18005ba7e  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18005ba83  mov     rdi, cs:qword_1800A3EE0
0x18005ba8a  lea     rcx, [rsi+0F8h]; this
0x18005ba91  or      edx, 0FFFFFFFFh; int
0x18005ba94  mov     ebx, eax
0x18005ba96  call    ?GetCharFormat@CTxtArray@@QEAAPEBVCCharFormat@@J@Z; CTxtArray::GetCharFormat(long)
0x18005ba9b  xor     ebp, ebp
0x18005ba9d  xor     r9d, r9d; HDC
0x18005baa0  mov     r8d, ebx; int
0x18005baa3  mov     [rsp+58h+var_38], ebp; int
0x18005baa7  mov     rdx, rax; struct CCharFormat *
0x18005baaa  mov     rcx, rdi; this
0x18005baad  call    ?GetCcs@CFontCache@@QEAAPEAVCCcs@@QEBVCCharFormat@@JPEAUHDC__@@H@Z; CFontCache::GetCcs(CCharFormat const * const,long,HDC__ *,int)
0x18005bab2  mov     rbx, rax
0x18005bab5  test    rax, rax
0x18005bab8  jnz     short loc_18005BABE
0x18005baba  mov     edi, ebp
0x18005babc  jmp     short loc_18005BB36
0x18005babe  mov     rcx, [rsp+58h+arg_28]
0x18005bac6  test    rcx, rcx
0x18005bac9  jz      short loc_18005BAD1
0x18005bacb  movsx   eax, word ptr [rax+5Eh]
0x18005bacf  mov     [rcx], eax
0x18005bad1  mov     rcx, [rsp+58h+arg_30]
0x18005bad9  test    rcx, rcx
0x18005badc  jz      short loc_18005BAE4
0x18005bade  movsx   eax, word ptr [rbx+62h]
0x18005bae2  mov     [rcx], eax
0x18005bae4  mov     rcx, [rsp+58h+arg_38]
0x18005baec  test    rcx, rcx
0x18005baef  jz      short loc_18005BAF7
0x18005baf1  movsx   eax, word ptr [rbx+64h]
0x18005baf5  mov     [rcx], eax
0x18005baf7  mov     rcx, rsi; this
0x18005bafa  call    ?fUseUIFont@CTxtEdit@@QEBA_NXZ; CTxtEdit::fUseUIFont(void)
0x18005baff  test    al, al
0x18005bb01  jnz     short loc_18005BB13
0x18005bb03  mov     rax, [rsi+40h]
0x18005bb07  mov     edx, r14d
0x18005bb0a  test    dword ptr [rax+38h], 20000h
0x18005bb11  jnz     short loc_18005BB15
0x18005bb13  mov     edx, ebp; int
0x18005bb15  mov     rcx, rbx; this
0x18005bb18  call    ?AdjustFEHeight@CCcs@@QEAAFH@Z; CCcs::AdjustFEHeight(int)
0x18005bb1d  movsx   edx, word ptr [rbx+5Ah]
0x18005bb21  cwde
0x18005bb22  lea     edi, [rdx+rax*2]
0x18005bb25  movzx   edx, word ptr [rbx+0Ah]
0x18005bb29  test    dx, dx
0x18005bb2c  jz      short loc_18005BB36
0x18005bb2e  sub     dx, r14w
0x18005bb32  mov     [rbx+0Ah], dx
0x18005bb36  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005bb3d  call    cs:__imp_LeaveCriticalSection
0x18005bb43  mov     eax, edi
0x18005bb45  add     rsp, 30h
0x18005bb49  pop     r14
0x18005bb4b  pop     rdi
0x18005bb4c  pop     rsi
0x18005bb4d  pop     rbp
0x18005bb4e  pop     rbx
0x18005bb4f  retn
```
