# CopyQMPolicy

- ea: `0x180018194`
- end: `0x180018323`
- name: `CopyQMPolicy`
- size: `399`
- prototype: `__int64 __fastcall(char, __int128 *, __int64)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180018ca0`
- `0x180019034`
- `0x18001f740`
- `0x18001f930`
- `0x1800209bc`
- `0x180033c9c`
- `0x180034b38`

## callees

- `0x18000e510`
- `0x18000f570`
- `0x180017534`
- `0x1800175dc`
- `0x180018194`
- `0x180018668`
- `0x180018844`
- `0x180042ef8`

## pseudocode

```c
__int64 __fastcall CopyQMPolicy(char a1, __int128 *a2, __int64 a3)
{
  STRSAFE_LPWSTR *v3; // r14
  __int128 v5; // xmm0
  __int64 v8; // rcx
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rbp
  unsigned __int16 v13; // ax
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned int NonAHQMOffers; // eax
  __int64 v20; // [rsp+58h] [rbp+10h] BYREF

  v3 = (STRSAFE_LPWSTR *)(a3 + 16);
  *(_QWORD *)(a3 + 16) = 0;
  v5 = *a2;
  v20 = 0;
  v8 = -1;
  *(_OWORD *)a3 = v5;
  do
    ++v8;
  while ( *(_WORD *)(*((_QWORD *)a2 + 2) + 2 * v8) );
  v9 = NsuSizeTMultiply(v8, 2, &v20);
  if ( v9 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v11 = 73;
LABEL_22:
      WPP_SF_d(v10[2], v11, WPP_b879685112533572aee45ba5e3c29dd7_Traceguids, v9);
    }
  }
  else
  {
    v12 = v20;
    v9 = SPDApiBufferAllocate(v20 + 2);
    if ( v9 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v11 = 74;
        goto LABEL_22;
      }
    }
    else
    {
      v13 = StringCbCopyW(*v3, v12 + 2, *((STRSAFE_LPCWSTR *)a2 + 2));
      v9 = v13;
      if ( v13 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v11 = 75;
          goto LABEL_22;
        }
      }
      else
      {
        v14 = a3 + 40;
        *(_DWORD *)(a3 + 24) = *((_DWORD *)a2 + 8);
        v15 = a3 + 32;
        *(_DWORD *)(a3 + 28) = *((_DWORD *)a2 + 9);
        v16 = *((_QWORD *)a2 + 6);
        v17 = *((unsigned int *)a2 + 10);
        if ( (a1 & 2) != 0 )
          NonAHQMOffers = CreateNonAHQMOffers(v17, v16, v15, v14);
        else
          NonAHQMOffers = CreateQMOffers(v17, v16, v15, v14);
        v9 = NonAHQMOffers;
        if ( !NonAHQMOffers )
          return 0;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v11 = 76;
          goto LABEL_22;
        }
      }
    }
  }
  if ( *v3 )
    SPDApiBufferFree(*v3);
  return v9;
}

```

## disassembly

```asm
0x180018194  mov     [rsp+arg_0], rbx
0x180018199  mov     [rsp+arg_10], rbp
0x18001819e  push    rsi
0x18001819f  push    rdi
0x1800181a0  push    r12
0x1800181a2  push    r14
0x1800181a4  push    r15
0x1800181a6  sub     rsp, 20h
0x1800181aa  xor     r12d, r12d
0x1800181ad  lea     r14, [r8+10h]
0x1800181b1  mov     [r14], r12
0x1800181b4  mov     r15d, ecx
0x1800181b7  movups  xmm0, xmmword ptr [rdx]
0x1800181ba  mov     rsi, r8
0x1800181bd  mov     [rsp+48h+arg_8], r12
0x1800181c2  mov     rdi, rdx
0x1800181c5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800181c9  movdqu  xmmword ptr [r8], xmm0
0x1800181ce  mov     rax, [rdx+10h]
0x1800181d2  inc     rcx
0x1800181d5  cmp     [rax+rcx*2], r12w
0x1800181da  jnz     short loc_1800181D2
0x1800181dc  lea     r8, [rsp+48h+arg_8]
0x1800181e1  mov     edx, 2
0x1800181e6  call    NsuSizeTMultiply
0x1800181eb  mov     ebx, eax
0x1800181ed  test    eax, eax
0x1800181ef  jz      short loc_18001821C
0x1800181f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181f8  lea     rax, WPP_GLOBAL_Control
0x1800181ff  cmp     rcx, rax
0x180018202  jz      loc_1800182F9
0x180018208  test    byte ptr [rcx+1Ch], 10h
0x18001820c  jz      loc_1800182F9
0x180018212  mov     edx, 49h ; 'I'
0x180018217  jmp     loc_1800182E6
0x18001821c  mov     rbp, [rsp+48h+arg_8]
0x180018221  mov     rdx, r14
0x180018224  lea     rcx, [rbp+2]; Size
0x180018228  call    SPDApiBufferAllocate
0x18001822d  mov     ebx, eax
0x18001822f  test    eax, eax
0x180018231  jz      short loc_18001825E
0x180018233  mov     rcx, cs:WPP_GLOBAL_Control
0x18001823a  lea     rax, WPP_GLOBAL_Control
0x180018241  cmp     rcx, rax
0x180018244  jz      loc_1800182F9
0x18001824a  test    byte ptr [rcx+1Ch], 10h
0x18001824e  jz      loc_1800182F9
0x180018254  mov     edx, 4Ah ; 'J'
0x180018259  jmp     loc_1800182E6
0x18001825e  mov     r8, [rdi+10h]; pszSrc
0x180018262  lea     rdx, [rbp+2]; cbDest
0x180018266  mov     rcx, [r14]; pszDest
0x180018269  call    StringCbCopyW
0x18001826e  movzx   ebx, ax
0x180018271  test    ebx, ebx
0x180018273  jz      short loc_180018295
0x180018275  mov     rcx, cs:WPP_GLOBAL_Control
0x18001827c  lea     rax, WPP_GLOBAL_Control
0x180018283  cmp     rcx, rax
0x180018286  jz      short loc_1800182F9
0x180018288  test    byte ptr [rcx+1Ch], 10h
0x18001828c  jz      short loc_1800182F9
0x18001828e  mov     edx, 4Bh ; 'K'
0x180018293  jmp     short loc_1800182E6
0x180018295  mov     eax, [rdi+20h]
0x180018298  lea     r9, [rsi+28h]
0x18001829c  mov     [rsi+18h], eax
0x18001829f  lea     r8, [rsi+20h]
0x1800182a3  mov     eax, [rdi+24h]
0x1800182a6  mov     [rsi+1Ch], eax
0x1800182a9  mov     rdx, [rdi+30h]
0x1800182ad  mov     ecx, [rdi+28h]
0x1800182b0  test    r15b, 2
0x1800182b4  jz      short loc_1800182BD
0x1800182b6  call    CreateNonAHQMOffers
0x1800182bb  jmp     short loc_1800182C2
0x1800182bd  call    CreateQMOffers
0x1800182c2  mov     ebx, eax
0x1800182c4  test    eax, eax
0x1800182c6  jz      short loc_18001830A
0x1800182c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182cf  lea     rax, WPP_GLOBAL_Control
0x1800182d6  cmp     rcx, rax
0x1800182d9  jz      short loc_1800182F9
0x1800182db  test    byte ptr [rcx+1Ch], 10h
0x1800182df  jz      short loc_1800182F9
0x1800182e1  mov     edx, 4Ch ; 'L'
0x1800182e6  mov     rcx, [rcx+10h]
0x1800182ea  lea     r8, WPP_b879685112533572aee45ba5e3c29dd7_Traceguids
0x1800182f1  mov     r9d, ebx
0x1800182f4  call    WPP_SF_d
0x1800182f9  mov     rcx, [r14]
0x1800182fc  test    rcx, rcx
0x1800182ff  jz      short loc_180018306
0x180018301  call    SPDApiBufferFree
0x180018306  mov     eax, ebx
0x180018308  jmp     short loc_18001830C
0x18001830a  xor     eax, eax
0x18001830c  mov     rbx, [rsp+48h+arg_0]
0x180018311  mov     rbp, [rsp+48h+arg_10]
0x180018316  add     rsp, 20h
0x18001831a  pop     r15
0x18001831c  pop     r14
0x18001831e  pop     r12
0x180018320  pop     rdi
0x180018321  pop     rsi
0x180018322  retn
```
