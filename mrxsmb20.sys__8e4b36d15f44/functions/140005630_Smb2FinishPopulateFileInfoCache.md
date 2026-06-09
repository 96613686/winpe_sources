# Smb2FinishPopulateFileInfoCache

- ea: `0x140005630`
- end: `0x1400057ef`
- name: `Smb2FinishPopulateFileInfoCache`
- size: `447`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003a80`

## callees

- `0x140005630`
- `0x140007bd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400057d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400057d3`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140005667`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140005667`

## pseudocode

```c
__int64 __fastcall Smb2FinishPopulateFileInfoCache(__int64 a1, __int64 a2, __int64 a3, unsigned int *a4)
{
  _QWORD *Src; // rdi
  __int64 v8; // r15
  unsigned int v9; // esi
  unsigned int v10; // ecx
  int v11; // eax
  size_t Size; // [rsp+30h] [rbp-48h]

  Src = *(_QWORD **)(a2 + 2408);
  v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 120LL) + 40LL);
  v9 = SmbCeWaitForCompletionAndFinalizeExchangeEx(a2, 0, 0, 0);
  if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147483643 )
  {
    LODWORD(Size) = 56;
    v9 = 0;
    Smb2UpdateFileInfoCacheEntry((_QWORD *)a1, (struct _NAME_CACHE_CONTROL_ *)(v8 + 376), 1, 0x22u, 0, Src, Size);
    if ( a3 )
    {
      v10 = *a4;
      switch ( *(_DWORD *)(a1 + 448) )
      {
        case 4:
          if ( v10 >= 0x28 )
          {
            v10 = 40;
            *(_QWORD *)(a3 + 24) = Src[3];
            *(_QWORD *)a3 = *Src;
            *(_DWORD *)(a3 + 32) = *((_DWORD *)Src + 12);
            *(_QWORD *)(a3 + 8) = Src[1];
            *(_QWORD *)(a3 + 16) = Src[2];
          }
          else
          {
            v9 = -2147483643;
          }
          break;
        case 5:
          if ( v10 >= 0x18 )
          {
            v10 = 24;
            *(_QWORD *)a3 = Src[4];
            *(_BYTE *)(a3 + 20) = 0;
            *(_BYTE *)(a3 + 21) = (Src[6] & 0x10) != 0;
            *(_QWORD *)(a3 + 8) = Src[5];
            *(_DWORD *)(a3 + 16) = 1;
          }
          else
          {
            v9 = -2147483643;
          }
          break;
        case 0x22:
          if ( v10 >= 0x38 )
          {
            v10 = 56;
            *(_OWORD *)a3 = *(_OWORD *)Src;
            *(_OWORD *)(a3 + 16) = *((_OWORD *)Src + 1);
            *(_OWORD *)(a3 + 32) = *((_OWORD *)Src + 2);
            *(_QWORD *)(a3 + 48) = Src[6];
          }
          else
          {
            v9 = -2147483643;
          }
          break;
        case 0x23:
          if ( v10 >= 8 )
          {
            v11 = *((_DWORD *)Src + 12);
            v10 = 8;
            if ( (v11 & 0x400) != 0 )
            {
              v9 = -1073741802;
            }
            else
            {
              *(_DWORD *)a3 = v11;
              *(_DWORD *)(a3 + 4) = 0;
            }
          }
          else
          {
            v9 = -1073741789;
          }
          break;
        default:
          v9 = -1073741802;
          break;
      }
      *a4 = v10;
    }
  }
  if ( Src )
    ExFreePoolWithTag(Src, 0x6D534946u);
  return v9;
}

```

## disassembly

```asm
0x140005630  push    rbx
0x140005632  push    rbp
0x140005633  push    rsi
0x140005634  push    rdi
0x140005635  push    r14
0x140005637  push    r15
0x140005639  sub     rsp, 48h
0x14000563d  mov     rax, [rcx+38h]
0x140005641  mov     r11, rdx
0x140005644  mov     rdi, [rdx+968h]
0x14000564b  mov     r14, r9
0x14000564e  mov     rbx, r8
0x140005651  mov     rbp, rcx
0x140005654  xor     r9d, r9d
0x140005657  xor     r8d, r8d
0x14000565a  mov     r10, [rax+78h]
0x14000565e  xor     edx, edx
0x140005660  mov     rcx, r11
0x140005663  mov     r15, [r10+28h]
0x140005667  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x14000566e  nop     dword ptr [rax+rax+00h]
0x140005673  mov     esi, eax
0x140005675  mov     eax, 80000000h
0x14000567a  lea     edx, [rsi+rax]
0x14000567d  test    eax, edx
0x14000567f  jnz     short loc_14000568D
0x140005681  cmp     esi, 80000005h
0x140005687  jnz     loc_1400057C6
0x14000568d  mov     dword ptr [rsp+78h+Size], 38h ; '8'; Size
0x140005695  lea     rdx, [r15+178h]; int
0x14000569c  xor     esi, esi
0x14000569e  mov     [rsp+78h+Src], rdi; Src
0x1400056a3  mov     r9d, 22h ; '"'; int
0x1400056a9  mov     [rsp+78h+var_58], esi; int
0x1400056ad  mov     r8d, 1; int
0x1400056b3  mov     rcx, rbp; int
0x1400056b6  call    Smb2UpdateFileInfoCacheEntry
0x1400056bb  test    rbx, rbx
0x1400056be  jz      loc_1400057C6
0x1400056c4  mov     edx, [rbp+1C0h]
0x1400056ca  mov     ecx, [r14]
0x1400056cd  sub     edx, 4
0x1400056d0  jz      loc_14000578E
0x1400056d6  sub     edx, 1
0x1400056d9  jz      short loc_140005756
0x1400056db  sub     edx, 1Dh
0x1400056de  jz      short loc_140005720
0x1400056e0  cmp     edx, 1
0x1400056e3  jz      short loc_1400056EF
0x1400056e5  mov     esi, 0C0000016h
0x1400056ea  jmp     loc_1400057C3
0x1400056ef  cmp     ecx, 8
0x1400056f2  jnb     short loc_1400056FE
0x1400056f4  mov     esi, 0C0000023h
0x1400056f9  jmp     loc_1400057C3
0x1400056fe  mov     eax, [rdi+30h]
0x140005701  mov     ecx, 8
0x140005706  bt      eax, 0Ah
0x14000570a  jnb     short loc_140005716
0x14000570c  mov     esi, 0C0000016h
0x140005711  jmp     loc_1400057C3
0x140005716  mov     [rbx], eax
0x140005718  mov     [rbx+4], esi
0x14000571b  jmp     loc_1400057C3
0x140005720  cmp     ecx, 38h ; '8'
0x140005723  jnb     short loc_14000572F
0x140005725  mov     esi, 80000005h
0x14000572a  jmp     loc_1400057C3
0x14000572f  movups  xmm0, xmmword ptr [rdi]
0x140005732  mov     ecx, 38h ; '8'
0x140005737  movups  xmmword ptr [rbx], xmm0
0x14000573a  movups  xmm1, xmmword ptr [rdi+10h]
0x14000573e  movups  xmmword ptr [rbx+10h], xmm1
0x140005742  movups  xmm0, xmmword ptr [rdi+20h]
0x140005746  movups  xmmword ptr [rbx+20h], xmm0
0x14000574a  movsd   xmm1, qword ptr [rdi+30h]
0x14000574f  movsd   qword ptr [rbx+30h], xmm1
0x140005754  jmp     short loc_1400057C3
0x140005756  cmp     ecx, 18h
0x140005759  jnb     short loc_140005762
0x14000575b  mov     esi, 80000005h
0x140005760  jmp     short loc_1400057C3
0x140005762  mov     rax, [rdi+20h]
0x140005766  mov     ecx, 18h
0x14000576b  mov     [rbx], rax
0x14000576e  mov     [rbx+14h], sil
0x140005772  mov     eax, [rdi+30h]
0x140005775  shr     eax, 4
0x140005778  and     al, 1
0x14000577a  mov     [rbx+15h], al
0x14000577d  mov     rax, [rdi+28h]
0x140005781  mov     [rbx+8], rax
0x140005785  mov     dword ptr [rbx+10h], 1
0x14000578c  jmp     short loc_1400057C3
0x14000578e  cmp     ecx, 28h ; '('
0x140005791  jnb     short loc_14000579A
0x140005793  mov     esi, 80000005h
0x140005798  jmp     short loc_1400057C3
0x14000579a  mov     rax, [rdi+18h]
0x14000579e  mov     ecx, 28h ; '('
0x1400057a3  mov     [rbx+18h], rax
0x1400057a7  mov     rax, [rdi]
0x1400057aa  mov     [rbx], rax
0x1400057ad  mov     eax, [rdi+30h]
0x1400057b0  mov     [rbx+20h], eax
0x1400057b3  mov     rax, [rdi+8]
0x1400057b7  mov     [rbx+8], rax
0x1400057bb  mov     rax, [rdi+10h]
0x1400057bf  mov     [rbx+10h], rax
0x1400057c3  mov     [r14], ecx
0x1400057c6  test    rdi, rdi
0x1400057c9  jz      short loc_1400057DF
0x1400057cb  mov     edx, 6D534946h; Tag
0x1400057d0  mov     rcx, rdi; P
0x1400057d3  call    cs:__imp_ExFreePoolWithTag
0x1400057da  nop     dword ptr [rax+rax+00h]
0x1400057df  mov     eax, esi
0x1400057e1  add     rsp, 48h
0x1400057e5  pop     r15
0x1400057e7  pop     r14
0x1400057e9  pop     rdi
0x1400057ea  pop     rsi
0x1400057eb  pop     rbp
0x1400057ec  pop     rbx
0x1400057ed  retn
```
