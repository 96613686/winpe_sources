# GetECDefaultHeightAndWidth(ITextServices *,HDC__ *,long,long,long,long *,long *,long *)

- ea: `0x18005d0bc`
- end: `0x18005d1c9`
- name: `?GetECDefaultHeightAndWidth@@YAJPEAVITextServices@@PEAUHDC__@@JJJPEAJ22@Z`
- size: `269`
- prototype: `__int64 __usercall@<rax>(struct ITextServices *this@<rcx>, HDC@<rdx>, int@<r8d>, int@<r9d>, int, int *, int *, int *)`
- caller_count: `5`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180027b20`
- `0x18004f8e0`
- `0x180050a30`
- `0x180062394`
- `0x18006ba88`

## callees

- `0x18000b5e0`
- `0x180035b80`
- `0x180039990`
- `0x18003d714`
- `0x18003ea88`
- `0x18005d0bc`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18005d0d1`
- `KERNEL32!EnterCriticalSection` at `0x18005d0d1`
- `KERNEL32!LeaveCriticalSection` at `0x18005d1af`
- `KERNEL32!LeaveCriticalSection` at `0x18005d1af`

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
  v10 = qword_1800A6FC0;
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
0x18005d0bc  push    rbx
0x18005d0be  push    rbp
0x18005d0bf  push    rsi
0x18005d0c0  push    rdi
0x18005d0c1  push    r14
0x18005d0c3  sub     rsp, 30h
0x18005d0c7  mov     rsi, rcx
0x18005d0ca  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005d0d1  call    cs:__imp_EnterCriticalSection
0x18005d0d8  nop     dword ptr [rax+rax+00h]
0x18005d0dd  mov     ecx, [rsp+58h+arg_20]; int
0x18005d0e4  mov     r14d, 1
0x18005d0ea  mov     r8d, r14d; int
0x18005d0ed  mov     edx, r14d; int
0x18005d0f0  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18005d0f5  mov     rdi, cs:qword_1800A6FC0
0x18005d0fc  lea     rcx, [rsi+0F8h]; this
0x18005d103  or      edx, 0FFFFFFFFh; int
0x18005d106  mov     ebx, eax
0x18005d108  call    ?GetCharFormat@CTxtArray@@QEAAPEBVCCharFormat@@J@Z; CTxtArray::GetCharFormat(long)
0x18005d10d  xor     ebp, ebp
0x18005d10f  xor     r9d, r9d; HDC
0x18005d112  mov     r8d, ebx; int
0x18005d115  mov     [rsp+58h+var_38], ebp; int
0x18005d119  mov     rdx, rax; struct CCharFormat *
0x18005d11c  mov     rcx, rdi; this
0x18005d11f  call    ?GetCcs@CFontCache@@QEAAPEAVCCcs@@QEBVCCharFormat@@JPEAUHDC__@@H@Z; CFontCache::GetCcs(CCharFormat const * const,long,HDC__ *,int)
0x18005d124  mov     rbx, rax
0x18005d127  test    rax, rax
0x18005d12a  jnz     short loc_18005D130
0x18005d12c  mov     edi, ebp
0x18005d12e  jmp     short loc_18005D1A8
0x18005d130  mov     rcx, [rsp+58h+arg_28]
0x18005d138  test    rcx, rcx
0x18005d13b  jz      short loc_18005D143
0x18005d13d  movsx   eax, word ptr [rax+5Eh]
0x18005d141  mov     [rcx], eax
0x18005d143  mov     rcx, [rsp+58h+arg_30]
0x18005d14b  test    rcx, rcx
0x18005d14e  jz      short loc_18005D156
0x18005d150  movsx   eax, word ptr [rbx+62h]
0x18005d154  mov     [rcx], eax
0x18005d156  mov     rcx, [rsp+58h+arg_38]
0x18005d15e  test    rcx, rcx
0x18005d161  jz      short loc_18005D169
0x18005d163  movsx   eax, word ptr [rbx+64h]
0x18005d167  mov     [rcx], eax
0x18005d169  mov     rcx, rsi; this
0x18005d16c  call    ?fUseUIFont@CTxtEdit@@QEBA_NXZ; CTxtEdit::fUseUIFont(void)
0x18005d171  test    al, al
0x18005d173  jnz     short loc_18005D185
0x18005d175  mov     rax, [rsi+40h]
0x18005d179  mov     edx, r14d
0x18005d17c  test    dword ptr [rax+38h], 20000h
0x18005d183  jnz     short loc_18005D187
0x18005d185  mov     edx, ebp; int
0x18005d187  mov     rcx, rbx; this
0x18005d18a  call    ?AdjustFEHeight@CCcs@@QEAAFH@Z; CCcs::AdjustFEHeight(int)
0x18005d18f  movsx   edx, word ptr [rbx+5Ah]
0x18005d193  cwde
0x18005d194  lea     edi, [rdx+rax*2]
0x18005d197  movzx   edx, word ptr [rbx+0Ah]
0x18005d19b  test    dx, dx
0x18005d19e  jz      short loc_18005D1A8
0x18005d1a0  sub     dx, r14w
0x18005d1a4  mov     [rbx+0Ah], dx
0x18005d1a8  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005d1af  call    cs:__imp_LeaveCriticalSection
0x18005d1b6  nop     dword ptr [rax+rax+00h]
0x18005d1bb  mov     eax, edi
0x18005d1bd  add     rsp, 30h
0x18005d1c1  pop     r14
0x18005d1c3  pop     rdi
0x18005d1c4  pop     rsi
0x18005d1c5  pop     rbp
0x18005d1c6  pop     rbx
0x18005d1c7  retn
```
