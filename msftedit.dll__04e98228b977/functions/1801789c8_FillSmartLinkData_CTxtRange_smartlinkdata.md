# FillSmartLinkData(CTxtRange &,_smartlinkdata *)

- ea: `0x1801789c8`
- end: `0x180178c33`
- name: `?FillSmartLinkData@@YAJAEAVCTxtRange@@PEAU_smartlinkdata@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(struct CTxtRange *this, struct _smartlinkdata *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800996c0`

## callees

- `0x18003ec20`
- `0x1800436a0`
- `0x180043f84`
- `0x1800440f0`
- `0x180098b78`
- `0x180119a64`
- `0x18013ce80`
- `0x1801789c8`
- `0x180179478`
- `0x1801795e4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180178b38`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180178b83`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180178bcf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180178b38`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180178b83`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180178bcf`

## pseudocode

```c
__int64 __fastcall FillSmartLinkData(struct CTxtRange *this, struct _smartlinkdata *a2)
{
  char v2; // r13
  int v6; // ebx
  int v7; // r15d
  unsigned int v8; // edx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // r14
  unsigned int HiddentText; // esi
  __m128i v12; // xmm1
  char v13; // r12
  int v14; // r14d
  char v15; // [rsp+30h] [rbp-40h]
  int v16; // [rsp+34h] [rbp-3Ch] BYREF
  int v17; // [rsp+38h] [rbp-38h] BYREF
  __int128 v18; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+50h] [rbp-20h]
  WCHAR String1[2]; // [rsp+58h] [rbp-18h] BYREF

  v2 = 0;
  if ( !a2 )
    return 2147942487LL;
  v16 = *(_DWORD *)a2;
  v17 = 0;
  *(_DWORD *)String1 = 0;
  if ( !(unsigned int)CTxtRange::GetURLInstruction(this, &v16, &v17, (int *)String1) )
    return 1;
  v6 = v17 - v16;
  v7 = *(_DWORD *)String1;
  v8 = v17 - v16;
  *((_DWORD *)a2 + 1) = *(_DWORD *)String1;
  v9 = CW32System::SysAllocStringLen(0, v8);
  *((_QWORD *)a2 + 3) = v9;
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  HiddentText = 0;
  CTxtRange::SetCp(this, v16, 0);
  v12 = (__m128i)*((unsigned __int64 *)this + 5);
  v18 = *(_OWORD *)((char *)this + 24);
  v19 = v12.m128i_i64[0];
  CTxtPtr::Move((CTxtPtr *)&v18, v16 - _mm_cvtsi128_si32(v12));
  CTxtPtr::GetText((CTxtPtr *)&v18, v6, v10);
  v15 = 0;
  v13 = 0;
  CTxtPtr::Move((CTxtPtr *)&v18, v6 - v19 + v16 + 1);
  do
  {
    v14 = v19;
    if ( (int)v19 >= v7 )
      break;
    if ( CTxtPtr::GetChar((CTxtPtr *)&v18) == 32 )
    {
      while ( v14 < v7 )
      {
        CTxtPtr::Move((CTxtPtr *)&v18, 1);
        if ( CTxtPtr::GetChar((CTxtPtr *)&v18) != 32 )
          break;
        v14 = v19;
      }
    }
    CTxtPtr::GetText((CTxtPtr *)&v18, 4, String1);
    if ( v15 || CompareStringOrdinal(String1, 3, L"-ID", 3, 1) != 2 )
    {
      if ( v2 || CompareStringOrdinal(String1, 3, L"-TY", 3, 1) != 2 )
      {
        if ( v13 || CompareStringOrdinal(String1, 4, L"-AT ", 4, 1) != 2 )
          return 1;
        v13 = 1;
        CTxtPtr::Move((CTxtPtr *)&v18, 4);
        HiddentText = GetHiddentText((struct CTxtPtr *)&v18, v7, (unsigned __int16 **)a2 + 4);
      }
      else
      {
        v2 = 1;
        CTxtPtr::Move((CTxtPtr *)&v18, 3);
        *((_DWORD *)a2 + 3) = GetCurrentWord((struct CTxtPtr *)&v18);
      }
    }
    else
    {
      v15 = 1;
      CTxtPtr::Move((CTxtPtr *)&v18, 3);
      *((_DWORD *)a2 + 4) = GetCurrentWord((struct CTxtPtr *)&v18);
    }
  }
  while ( !HiddentText );
  return HiddentText;
}

```

## disassembly

```asm
0x1801789c8  mov     [rsp-38h+arg_10], rbx
0x1801789cd  push    rbp
0x1801789ce  push    rsi
0x1801789cf  push    rdi
0x1801789d0  push    r12
0x1801789d2  push    r13
0x1801789d4  push    r14
0x1801789d6  push    r15
0x1801789d8  mov     rbp, rsp
0x1801789db  sub     rsp, 70h
0x1801789df  mov     rax, cs:__security_cookie
0x1801789e6  xor     rax, rsp
0x1801789e9  mov     [rbp+var_10], rax
0x1801789ed  xor     r13d, r13d
0x1801789f0  mov     rdi, rdx
0x1801789f3  mov     r12, rcx
0x1801789f6  test    rdx, rdx
0x1801789f9  jnz     short loc_180178A05
0x1801789fb  mov     eax, 80070057h
0x180178a00  jmp     loc_180178C0E
0x180178a05  mov     eax, [rdx]
0x180178a07  lea     r9, [rbp+String1]; int *
0x180178a0b  lea     rdx, [rbp+var_3C]; int *
0x180178a0f  mov     [rbp+var_3C], eax
0x180178a12  lea     r8, [rbp+var_38]; int *
0x180178a16  mov     [rbp+var_38], r13d
0x180178a1a  mov     dword ptr [rbp+String1], r13d
0x180178a1e  call    ?GetURLInstruction@CTxtRange@@QEAAHAEAJ0PEAJ@Z; CTxtRange::GetURLInstruction(long &,long &,long *)
0x180178a23  test    eax, eax
0x180178a25  jnz     short loc_180178A31
0x180178a27  mov     eax, 1
0x180178a2c  jmp     loc_180178C0E
0x180178a31  mov     ebx, [rbp+var_38]
0x180178a34  xor     ecx, ecx; unsigned __int16 *
0x180178a36  sub     ebx, [rbp+var_3C]
0x180178a39  mov     r15d, dword ptr [rbp+String1]
0x180178a3d  mov     edx, ebx; unsigned int
0x180178a3f  mov     [rdi+4], r15d
0x180178a43  call    ?SysAllocStringLen@CW32System@@SAPEAGPEBGI@Z; CW32System::SysAllocStringLen(ushort const *,uint)
0x180178a48  mov     [rdi+18h], rax
0x180178a4c  mov     r14, rax
0x180178a4f  test    rax, rax
0x180178a52  jnz     short loc_180178A5E
0x180178a54  mov     eax, 8007000Eh
0x180178a59  jmp     loc_180178C0E
0x180178a5e  mov     edx, [rbp+var_3C]; int
0x180178a61  xor     r8d, r8d; int
0x180178a64  mov     rcx, r12; this
0x180178a67  mov     esi, r13d
0x180178a6a  call    ?SetCp@CTxtRange@@QEAAJJH@Z; CTxtRange::SetCp(long,int)
0x180178a6f  movsd   xmm1, qword ptr [r12+28h]
0x180178a76  lea     rcx, [rbp+var_30]; this
0x180178a7a  mov     edx, [rbp+var_3C]
0x180178a7d  movups  xmm0, xmmword ptr [r12+18h]
0x180178a83  movd    eax, xmm1
0x180178a87  movups  [rbp+var_30], xmm0
0x180178a8b  sub     edx, eax; int
0x180178a8d  movsd   [rbp+var_20], xmm1
0x180178a92  call    ?Move@CTxtPtr@@QEAAJJ@Z; CTxtPtr::Move(long)
0x180178a97  mov     r8, r14; unsigned __int16 *
0x180178a9a  lea     rcx, [rbp+var_30]; this
0x180178a9e  mov     edx, ebx; int
0x180178aa0  call    ?GetText@CTxtPtr@@QEBAJJPEAG@Z; CTxtPtr::GetText(long,ushort *)
0x180178aa5  mov     edx, [rbp+var_3C]
0x180178aa8  lea     rcx, [rbp+var_30]; this
0x180178aac  sub     ebx, dword ptr [rbp+var_20]
0x180178aaf  inc     edx
0x180178ab1  add     edx, ebx; int
0x180178ab3  mov     [rbp+var_40], r13b
0x180178ab7  xor     r12b, r12b
0x180178aba  call    ?Move@CTxtPtr@@QEAAJJ@Z; CTxtPtr::Move(long)
0x180178abf  mov     ebx, 1
0x180178ac4  mov     r14d, dword ptr [rbp+var_20]
0x180178ac8  cmp     r14d, r15d
0x180178acb  jge     loc_180178C0C
0x180178ad1  lea     rcx, [rbp+var_30]; this
0x180178ad5  call    ?GetChar@CTxtPtr@@QEBAGXZ; CTxtPtr::GetChar(void)
0x180178ada  cmp     ax, 20h ; ' '
0x180178ade  jnz     short loc_180178B05
0x180178ae0  cmp     r14d, r15d
0x180178ae3  jge     short loc_180178B05
0x180178ae5  mov     edx, ebx; int
0x180178ae7  lea     rcx, [rbp+var_30]; this
0x180178aeb  call    ?Move@CTxtPtr@@QEAAJJ@Z; CTxtPtr::Move(long)
0x180178af0  lea     rcx, [rbp+var_30]; this
0x180178af4  call    ?GetChar@CTxtPtr@@QEBAGXZ; CTxtPtr::GetChar(void)
0x180178af9  cmp     ax, 20h ; ' '
0x180178afd  jnz     short loc_180178B05
0x180178aff  mov     r14d, dword ptr [rbp+var_20]
0x180178b03  jmp     short loc_180178AE0
0x180178b05  lea     r8, [rbp+String1]; unsigned __int16 *
0x180178b09  mov     edx, 4; int
0x180178b0e  lea     rcx, [rbp+var_30]; this
0x180178b12  call    ?GetText@CTxtPtr@@QEBAJJPEAG@Z; CTxtPtr::GetText(long,ushort *)
0x180178b17  cmp     [rbp+var_40], 0
0x180178b1b  mov     r14d, 3
0x180178b21  jnz     short loc_180178B69
0x180178b23  mov     r9d, r14d; cchCount2
0x180178b26  mov     [rsp+70h+bIgnoreCase], ebx; bIgnoreCase
0x180178b2a  lea     r8, String2; "-ID"
0x180178b31  mov     edx, r14d; cchCount1
0x180178b34  lea     rcx, [rbp+String1]; lpString1
0x180178b38  call    cs:__imp_CompareStringOrdinal
0x180178b3f  nop     dword ptr [rax+rax+00h]
0x180178b44  cmp     eax, 2
0x180178b47  jnz     short loc_180178B69
0x180178b49  mov     edx, r14d; int
0x180178b4c  mov     [rbp+var_40], bl
0x180178b4f  lea     rcx, [rbp+var_30]; this
0x180178b53  call    ?Move@CTxtPtr@@QEAAJJ@Z; CTxtPtr::Move(long)
0x180178b58  lea     rcx, [rbp+var_30]; this
0x180178b5c  call    ?GetCurrentWord@@YAKAEAVCTxtPtr@@@Z; GetCurrentWord(CTxtPtr &)
0x180178b61  mov     [rdi+10h], eax
0x180178b64  jmp     loc_180178C00
0x180178b69  test    r13b, r13b
0x180178b6c  jnz     short loc_180178BB1
0x180178b6e  mov     r9d, r14d; cchCount2
0x180178b71  mov     [rsp+70h+bIgnoreCase], ebx; bIgnoreCase
0x180178b75  lea     r8, aTy_0; "-TY"
0x180178b7c  mov     edx, r14d; cchCount1
0x180178b7f  lea     rcx, [rbp+String1]; lpString1
0x180178b83  call    cs:__imp_CompareStringOrdinal
0x180178b8a  nop     dword ptr [rax+rax+00h]
0x180178b8f  cmp     eax, 2
0x180178b92  jnz     short loc_180178BB1
0x180178b94  mov     edx, r14d; int
0x180178b97  lea     rcx, [rbp+var_30]; this
0x180178b9b  mov     r13b, bl
0x180178b9e  call    ?Move@CTxtPtr@@QEAAJJ@Z; CTxtPtr::Move(long)
0x180178ba3  lea     rcx, [rbp+var_30]; this
0x180178ba7  call    ?GetCurrentWord@@YAKAEAVCTxtPtr@@@Z; GetCurrentWord(CTxtPtr &)
0x180178bac  mov     [rdi+0Ch], eax
0x180178baf  jmp     short loc_180178C00
0x180178bb1  test    r12b, r12b
0x180178bb4  jnz     short loc_180178C0A
0x180178bb6  mov     esi, 4
0x180178bbb  mov     [rsp+70h+bIgnoreCase], ebx; bIgnoreCase
0x180178bbf  mov     r9d, esi; cchCount2
0x180178bc2  lea     r8, aAt_0; "-AT "
0x180178bc9  mov     edx, esi; cchCount1
0x180178bcb  lea     rcx, [rbp+String1]; lpString1
0x180178bcf  call    cs:__imp_CompareStringOrdinal
0x180178bd6  nop     dword ptr [rax+rax+00h]
0x180178bdb  cmp     eax, 2
0x180178bde  jnz     short loc_180178C0A
0x180178be0  mov     edx, esi; int
0x180178be2  lea     rcx, [rbp+var_30]; this
0x180178be6  mov     r12b, bl
0x180178be9  call    ?Move@CTxtPtr@@QEAAJJ@Z; CTxtPtr::Move(long)
0x180178bee  lea     r8, [rdi+20h]; unsigned __int16 **
0x180178bf2  mov     edx, r15d; int
0x180178bf5  lea     rcx, [rbp+var_30]; this
0x180178bf9  call    ?GetHiddentText@@YAJAEAVCTxtPtr@@JAEAPEAG@Z; GetHiddentText(CTxtPtr &,long,ushort * &)
0x180178bfe  mov     esi, eax
0x180178c00  test    esi, esi
0x180178c02  jz      loc_180178AC4
0x180178c08  jmp     short loc_180178C0C
0x180178c0a  mov     esi, ebx
0x180178c0c  mov     eax, esi
0x180178c0e  mov     rcx, [rbp+var_10]
0x180178c12  xor     rcx, rsp; StackCookie
0x180178c15  call    __security_check_cookie
0x180178c1a  mov     rbx, [rsp+70h+arg_10]
0x180178c22  add     rsp, 70h
0x180178c26  pop     r15
0x180178c28  pop     r14
0x180178c2a  pop     r13
0x180178c2c  pop     r12
0x180178c2e  pop     rdi
0x180178c2f  pop     rsi
0x180178c30  pop     rbp
0x180178c31  retn
```
