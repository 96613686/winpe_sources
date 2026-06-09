# DafMakeAepId

- ea: `0x140019940`
- end: `0x140019ac2`
- name: `DafMakeAepId`
- size: `386`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140019330`
- `0x140019410`
- `0x1400195e0`
- `0x140019840`

## callees

- `0x140009060`
- `0x140009090`
- `0x14000a8ac`
- `0x1400137f8`
- `0x140019940`

## pseudocode

```c
__int64 __fastcall DafMakeAepId(unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned __int16 *v6; // rdi
  unsigned __int16 *v7; // rax
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned __int16 *v12; // rax
  __int64 v13; // r9
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rax
  SIZE_T v16; // rsi
  unsigned __int16 *v17; // rax

  v6 = 0;
  if ( !a1 )
  {
    v9 = -2147024809;
    goto LABEL_26;
  }
  v7 = a1;
  v8 = 0x7FFFFFFF;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v8;
  }
  while ( v8 );
  v9 = v8 == 0 ? 0x80070057 : 0;
  if ( v8 )
  {
    v10 = (2 * (0x7FFFFFFF - v8)) & -(__int64)(v8 != 0);
    if ( a2 )
    {
      v11 = 0x7FFFFFFF;
      v12 = a2;
      do
      {
        if ( !*v12 )
          break;
        ++v12;
        --v11;
      }
      while ( v11 );
      v9 = v11 == 0 ? 0x80070057 : 0;
      if ( v11 )
      {
        v13 = (2 * (0x7FFFFFFF - v11)) & -(__int64)(v11 != 0);
LABEL_14:
        if ( !v9 )
        {
          v14 = 0x7FFFFFFF;
          v15 = L"#";
          do
          {
            if ( !*v15 )
              break;
            ++v15;
            --v14;
          }
          while ( v14 );
          v9 = v14 == 0 ? 0x80070057 : 0;
          if ( v14 )
          {
            v16 = v13 + 2 + v10 + (-(__int64)(v14 != 0) & (2 * (0x7FFFFFFF - v14)));
            v17 = (unsigned __int16 *)DAF_user_alloc(v16);
            v6 = v17;
            if ( v17 )
            {
              v9 = StringCbCopyW(v17, v16, a1);
              if ( v9 || (v9 = StringCbCatW(v6, v16, L"#")) != 0 || (v9 = StringCbCatW(v6, v16, a2)) != 0 )
              {
                MIDL_user_free(v6);
                v6 = 0;
              }
            }
            else
            {
              v9 = -2147024882;
            }
          }
        }
        goto LABEL_26;
      }
    }
    else
    {
      v9 = -2147024809;
    }
    v13 = 0;
    goto LABEL_14;
  }
LABEL_26:
  *a3 = v6;
  return v9;
}

```

## disassembly

```asm
0x140019940  push    rbx
0x140019942  push    rbp
0x140019943  push    rsi
0x140019944  push    rdi
0x140019945  push    r12
0x140019947  push    r14
0x140019949  push    r15
0x14001994b  sub     rsp, 20h
0x14001994f  xor     r12d, r12d
0x140019952  mov     r15, r8
0x140019955  mov     r14, rdx
0x140019958  mov     rbp, rcx
0x14001995b  mov     edi, r12d
0x14001995e  test    rcx, rcx
0x140019961  jz      loc_140019AA9
0x140019967  mov     r10d, 7FFFFFFFh
0x14001996d  mov     rax, rcx
0x140019970  mov     r9d, r10d
0x140019973  cmp     [rax], r12w
0x140019977  jz      short loc_140019983
0x140019979  add     rax, 2
0x14001997d  sub     r9, 1
0x140019981  jnz     short loc_140019973
0x140019983  mov     rax, r9
0x140019986  mov     ecx, 80070057h
0x14001998b  neg     rax
0x14001998e  sbb     ebx, ebx
0x140019990  not     ebx
0x140019992  and     ebx, ecx
0x140019994  test    r9, r9
0x140019997  jz      loc_140019AAE
0x14001999d  mov     rax, r10
0x1400199a0  sub     rax, r9
0x1400199a3  add     rax, rax
0x1400199a6  neg     r9
0x1400199a9  sbb     r8, r8
0x1400199ac  and     r8, rax
0x1400199af  test    r14, r14
0x1400199b2  jz      short loc_1400199EF
0x1400199b4  mov     rdx, r10
0x1400199b7  mov     rax, r14
0x1400199ba  cmp     [rax], r12w
0x1400199be  jz      short loc_1400199CA
0x1400199c0  add     rax, 2
0x1400199c4  sub     rdx, 1
0x1400199c8  jnz     short loc_1400199BA
0x1400199ca  mov     rax, rdx
0x1400199cd  neg     rax
0x1400199d0  sbb     ebx, ebx
0x1400199d2  not     ebx
0x1400199d4  and     ebx, ecx
0x1400199d6  test    rdx, rdx
0x1400199d9  jz      short loc_1400199F1
0x1400199db  mov     rax, r10
0x1400199de  sub     rax, rdx
0x1400199e1  add     rax, rax
0x1400199e4  neg     rdx
0x1400199e7  sbb     r9, r9
0x1400199ea  and     r9, rax
0x1400199ed  jmp     short loc_1400199F4
0x1400199ef  mov     ebx, ecx
0x1400199f1  mov     r9, r12
0x1400199f4  test    ebx, ebx
0x1400199f6  jnz     loc_140019AAE
0x1400199fc  mov     rdx, r10
0x1400199ff  lea     rax, asc_140024788; "#"
0x140019a06  cmp     [rax], r12w
0x140019a0a  jz      short loc_140019A16
0x140019a0c  add     rax, 2
0x140019a10  sub     rdx, 1
0x140019a14  jnz     short loc_140019A06
0x140019a16  mov     rax, rdx
0x140019a19  neg     rax
0x140019a1c  sbb     ebx, ebx
0x140019a1e  not     ebx
0x140019a20  and     ebx, ecx
0x140019a22  test    rdx, rdx
0x140019a25  jz      loc_140019AAE
0x140019a2b  sub     r10, rdx
0x140019a2e  neg     rdx
0x140019a31  sbb     rax, rax
0x140019a34  add     r9, 2
0x140019a38  lea     rsi, [r10+r10]
0x140019a3c  and     rsi, rax
0x140019a3f  add     rsi, r8
0x140019a42  add     rsi, r9
0x140019a45  mov     rcx, rsi
0x140019a48  call    DAF_user_alloc
0x140019a4d  mov     rdi, rax
0x140019a50  test    rax, rax
0x140019a53  jnz     short loc_140019A5C
0x140019a55  mov     ebx, 8007000Eh
0x140019a5a  jmp     short loc_140019AAE
0x140019a5c  mov     r8, rbp; unsigned __int16 *
0x140019a5f  mov     rdx, rsi; unsigned __int64
0x140019a62  mov     rcx, rdi; unsigned __int16 *
0x140019a65  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140019a6a  mov     ebx, eax
0x140019a6c  test    eax, eax
0x140019a6e  jnz     short loc_140019A9C
0x140019a70  lea     r8, asc_140024788; "#"
0x140019a77  mov     rdx, rsi; unsigned __int64
0x140019a7a  mov     rcx, rdi; unsigned __int16 *
0x140019a7d  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140019a82  mov     ebx, eax
0x140019a84  test    eax, eax
0x140019a86  jnz     short loc_140019A9C
0x140019a88  mov     r8, r14; unsigned __int16 *
0x140019a8b  mov     rdx, rsi; unsigned __int64
0x140019a8e  mov     rcx, rdi; unsigned __int16 *
0x140019a91  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140019a96  mov     ebx, eax
0x140019a98  test    eax, eax
0x140019a9a  jz      short loc_140019AAE
0x140019a9c  mov     rcx, rdi; void *
0x140019a9f  call    MIDL_user_free
0x140019aa4  mov     rdi, r12
0x140019aa7  jmp     short loc_140019AAE
0x140019aa9  mov     ebx, 80070057h
0x140019aae  mov     [r15], rdi
0x140019ab1  mov     eax, ebx
0x140019ab3  add     rsp, 20h
0x140019ab7  pop     r15
0x140019ab9  pop     r14
0x140019abb  pop     r12
0x140019abd  pop     rdi
0x140019abe  pop     rsi
0x140019abf  pop     rbp
0x140019ac0  pop     rbx
0x140019ac1  retn
```
