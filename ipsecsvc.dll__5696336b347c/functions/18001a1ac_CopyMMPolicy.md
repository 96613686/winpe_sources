# CopyMMPolicy

- ea: `0x18001a1ac`
- end: `0x18001a323`
- name: `CopyMMPolicy`
- size: `375`
- prototype: `__int64 __fastcall(__int128 *, __int64)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001aa4c`
- `0x18001ad9c`
- `0x180025320`
- `0x1800255e0`
- `0x1800269a0`

## callees

- `0x18000e510`
- `0x18000f570`
- `0x180017534`
- `0x1800175dc`
- `0x18001a1ac`
- `0x18001a664`
- `0x180042ef8`

## pseudocode

```c
__int64 __fastcall CopyMMPolicy(__int128 *a1, __int64 a2)
{
  __int128 v2; // xmm0
  __int64 v5; // rax
  __int64 v6; // rcx
  unsigned int v7; // eax
  unsigned int v8; // edi
  STRSAFE_LPWSTR *v9; // rbx
  __int64 v10; // r14
  unsigned int MMOffers; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned __int16 v14; // ax
  __int64 v15; // r9
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF

  v2 = *a1;
  v17 = 0;
  *(_OWORD *)a2 = v2;
  v5 = *((_QWORD *)a1 + 2);
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(v5 + 2 * v6) );
  v7 = NsuSizeTMultiply(v6, 2, &v17);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_3b22585727a234aeebb3c3c9670a017a_Traceguids, v7);
    v9 = (STRSAFE_LPWSTR *)(a2 + 16);
    goto LABEL_22;
  }
  v10 = v17;
  v9 = (STRSAFE_LPWSTR *)(a2 + 16);
  MMOffers = SPDApiBufferAllocate(v17 + 2);
  v8 = MMOffers;
  if ( MMOffers )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v13 = 66;
LABEL_20:
      v15 = MMOffers;
      goto LABEL_21;
    }
  }
  else
  {
    v14 = StringCbCopyW(*v9, v10 + 2, *((STRSAFE_LPCWSTR *)a1 + 2));
    v8 = v14;
    if ( v14 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v13 = 67;
        v15 = v14;
LABEL_21:
        WPP_SF_d(v12[2], v13, WPP_3b22585727a234aeebb3c3c9670a017a_Traceguids, v15);
      }
    }
    else
    {
      *(_DWORD *)(a2 + 24) = *((_DWORD *)a1 + 8);
      *(_DWORD *)(a2 + 28) = *((_DWORD *)a1 + 9);
      MMOffers = CreateMMOffers(*((unsigned int *)a1 + 10), *((_QWORD *)a1 + 6), a2 + 32, a2 + 40);
      v8 = MMOffers;
      if ( !MMOffers )
        return 0;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v13 = 68;
        goto LABEL_20;
      }
    }
  }
LABEL_22:
  if ( *v9 )
    SPDApiBufferFree(*v9);
  return v8;
}

```

## disassembly

```asm
0x18001a1ac  push    rbx
0x18001a1ae  push    rbp
0x18001a1af  push    rsi
0x18001a1b0  push    rdi
0x18001a1b1  push    r14
0x18001a1b3  push    r15
0x18001a1b5  sub     rsp, 28h
0x18001a1b9  movups  xmm0, xmmword ptr [rcx]
0x18001a1bc  xor     r15d, r15d
0x18001a1bf  mov     rbp, rcx
0x18001a1c2  mov     rsi, rdx
0x18001a1c5  mov     [rsp+58h+arg_0], r15
0x18001a1ca  movdqu  xmmword ptr [rdx], xmm0
0x18001a1ce  mov     rax, [rcx+10h]
0x18001a1d2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001a1d6  inc     rcx
0x18001a1d9  cmp     [rax+rcx*2], r15w
0x18001a1de  jnz     short loc_18001A1D6
0x18001a1e0  lea     r8, [rsp+58h+arg_0]
0x18001a1e5  mov     edx, 2
0x18001a1ea  call    NsuSizeTMultiply
0x18001a1ef  mov     edi, eax
0x18001a1f1  test    eax, eax
0x18001a1f3  jz      short loc_18001A22F
0x18001a1f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1fc  lea     rdx, WPP_GLOBAL_Control
0x18001a203  cmp     rcx, rdx
0x18001a206  jz      short loc_18001A226
0x18001a208  test    byte ptr [rcx+1Ch], 10h
0x18001a20c  jz      short loc_18001A226
0x18001a20e  mov     rcx, [rcx+10h]
0x18001a212  lea     r8, WPP_3b22585727a234aeebb3c3c9670a017a_Traceguids
0x18001a219  mov     edx, 41h ; 'A'
0x18001a21e  mov     r9d, eax
0x18001a221  call    WPP_SF_d
0x18001a226  lea     rbx, [rsi+10h]
0x18001a22a  jmp     loc_18001A303
0x18001a22f  mov     r14, [rsp+58h+arg_0]
0x18001a234  lea     rbx, [rsi+10h]
0x18001a238  mov     rdx, rbx
0x18001a23b  lea     rcx, [r14+2]; Size
0x18001a23f  call    SPDApiBufferAllocate
0x18001a244  mov     edi, eax
0x18001a246  test    eax, eax
0x18001a248  jz      short loc_18001A272
0x18001a24a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a251  lea     rdx, WPP_GLOBAL_Control
0x18001a258  cmp     rcx, rdx
0x18001a25b  jz      loc_18001A303
0x18001a261  test    byte ptr [rcx+1Ch], 10h
0x18001a265  jz      loc_18001A303
0x18001a26b  mov     edx, 42h ; 'B'
0x18001a270  jmp     short loc_18001A2F0
0x18001a272  mov     r8, [rbp+10h]; pszSrc
0x18001a276  lea     rdx, [r14+2]; cbDest
0x18001a27a  mov     rcx, [rbx]; pszDest
0x18001a27d  call    StringCbCopyW
0x18001a282  movzx   edi, ax
0x18001a285  test    edi, edi
0x18001a287  jz      short loc_18001A2AC
0x18001a289  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a290  lea     rdx, WPP_GLOBAL_Control
0x18001a297  cmp     rcx, rdx
0x18001a29a  jz      short loc_18001A303
0x18001a29c  test    byte ptr [rcx+1Ch], 10h
0x18001a2a0  jz      short loc_18001A303
0x18001a2a2  mov     edx, 43h ; 'C'
0x18001a2a7  mov     r9d, edi
0x18001a2aa  jmp     short loc_18001A2F3
0x18001a2ac  mov     eax, [rbp+20h]
0x18001a2af  lea     r9, [rsi+28h]
0x18001a2b3  mov     [rsi+18h], eax
0x18001a2b6  lea     r8, [rsi+20h]
0x18001a2ba  mov     eax, [rbp+24h]
0x18001a2bd  mov     [rsi+1Ch], eax
0x18001a2c0  mov     rdx, [rbp+30h]
0x18001a2c4  mov     ecx, [rbp+28h]
0x18001a2c7  call    CreateMMOffers
0x18001a2cc  mov     edi, eax
0x18001a2ce  test    eax, eax
0x18001a2d0  jz      short loc_18001A314
0x18001a2d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a2d9  lea     rdx, WPP_GLOBAL_Control
0x18001a2e0  cmp     rcx, rdx
0x18001a2e3  jz      short loc_18001A303
0x18001a2e5  test    byte ptr [rcx+1Ch], 10h
0x18001a2e9  jz      short loc_18001A303
0x18001a2eb  mov     edx, 44h ; 'D'
0x18001a2f0  mov     r9d, eax
0x18001a2f3  mov     rcx, [rcx+10h]
0x18001a2f7  lea     r8, WPP_3b22585727a234aeebb3c3c9670a017a_Traceguids
0x18001a2fe  call    WPP_SF_d
0x18001a303  mov     rcx, [rbx]
0x18001a306  test    rcx, rcx
0x18001a309  jz      short loc_18001A310
0x18001a30b  call    SPDApiBufferFree
0x18001a310  mov     eax, edi
0x18001a312  jmp     short loc_18001A316
0x18001a314  xor     eax, eax
0x18001a316  add     rsp, 28h
0x18001a31a  pop     r15
0x18001a31c  pop     r14
0x18001a31e  pop     rdi
0x18001a31f  pop     rsi
0x18001a320  pop     rbp
0x18001a321  pop     rbx
0x18001a322  retn
```
