# SsprMICHandshakeMessages

- ea: `0x180021fa4`
- end: `0x180022156`
- name: `SsprMICHandshakeMessages`
- size: `434`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800157b0`
- `0x1800268dc`

## callees

- `0x180021fa4`
- `0x18002ee7c`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x1800220fe`
- `bcrypt!BCryptFinishHash` at `0x1800220fe`
- `bcrypt!BCryptDestroyHash` at `0x180022145`
- `bcrypt!BCryptDestroyHash` at `0x180022145`
- `bcrypt!BCryptHashData` at `0x180022025`
- `bcrypt!BCryptHashData` at `0x18002206f`
- `bcrypt!BCryptHashData` at `0x1800220be`
- `bcrypt!BCryptHashData` at `0x180022025`
- `bcrypt!BCryptHashData` at `0x18002206f`
- `bcrypt!BCryptHashData` at `0x1800220be`
- `bcrypt!BCryptCreateHash` at `0x180021fe0`
- `bcrypt!BCryptCreateHash` at `0x180021fe0`

## pseudocode

```c
__int64 __fastcall SsprMICHandshakeMessages(
        UCHAR *a1,
        ULONG a2,
        UCHAR *a3,
        ULONG a4,
        UCHAR *pbInput,
        ULONG cbInput,
        UCHAR *a7,
        UCHAR *pbOutput)
{
  NTSTATUS v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-38h] BYREF

  hHash = 0;
  v11 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x91, &hHash, 0, 0, a1, 0x10u, 0);
  if ( v11 >= 0 )
  {
    v11 = BCryptHashData(hHash, a3, a2, 0);
    if ( v11 >= 0 )
    {
      v11 = BCryptHashData(hHash, pbInput, a4, 0);
      if ( v11 >= 0 )
      {
        v11 = BCryptHashData(hHash, a7, cbInput, 0);
        if ( v11 >= 0 )
        {
          v11 = BCryptFinishHash(hHash, pbOutput, 0x10u, 0);
          if ( v11 < 0 )
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v13 = 31;
              goto LABEL_21;
            }
          }
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 30;
            goto LABEL_21;
          }
        }
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 29;
          goto LABEL_21;
        }
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 28;
        goto LABEL_21;
      }
    }
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 27;
LABEL_21:
      WPP_SF_d(v12[2], v13, WPP_2467158bb6003f4dc4982d488f18e69e_Traceguids, (unsigned int)v11);
    }
  }
  if ( hHash )
    BCryptDestroyHash(hHash);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180021fa4  mov     rax, rsp
0x180021fa7  push    rbx
0x180021fa8  push    rbp
0x180021fa9  push    rsi
0x180021faa  push    rdi
0x180021fab  sub     rsp, 58h
0x180021faf  mov     dword ptr [rax-48h], 0
0x180021fb6  mov     edi, r9d
0x180021fb9  mov     dword ptr [rax-50h], 10h
0x180021fc0  mov     rsi, r8
0x180021fc3  mov     [rax-58h], rcx
0x180021fc7  mov     ebp, edx
0x180021fc9  mov     ecx, 91h; hAlgorithm
0x180021fce  mov     qword ptr [rax-38h], 0
0x180021fd6  xor     r9d, r9d; cbHashObject
0x180021fd9  lea     rdx, [rax-38h]; phHash
0x180021fdd  xor     r8d, r8d; pbHashObject
0x180021fe0  call    cs:__imp_BCryptCreateHash
0x180021fe6  mov     ebx, eax
0x180021fe8  test    eax, eax
0x180021fea  jns     short loc_180022017
0x180021fec  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ff3  lea     rax, WPP_GLOBAL_Control
0x180021ffa  cmp     rcx, rax
0x180021ffd  jz      loc_18002213B
0x180022003  test    byte ptr [rcx+1Ch], 1
0x180022007  jz      loc_18002213B
0x18002200d  mov     edx, 1Bh
0x180022012  jmp     loc_180022128
0x180022017  mov     rcx, [rsp+78h+hHash]; hHash
0x18002201c  xor     r9d, r9d; dwFlags
0x18002201f  mov     r8d, ebp; cbInput
0x180022022  mov     rdx, rsi; pbInput
0x180022025  call    cs:__imp_BCryptHashData
0x18002202b  mov     ebx, eax
0x18002202d  test    eax, eax
0x18002202f  jns     short loc_18002205C
0x180022031  mov     rcx, cs:WPP_GLOBAL_Control
0x180022038  lea     rax, WPP_GLOBAL_Control
0x18002203f  cmp     rcx, rax
0x180022042  jz      loc_18002213B
0x180022048  test    byte ptr [rcx+1Ch], 1
0x18002204c  jz      loc_18002213B
0x180022052  mov     edx, 1Ch
0x180022057  jmp     loc_180022128
0x18002205c  mov     rdx, [rsp+78h+pbInput]; pbInput
0x180022064  xor     r9d, r9d; dwFlags
0x180022067  mov     rcx, [rsp+78h+hHash]; hHash
0x18002206c  mov     r8d, edi; cbInput
0x18002206f  call    cs:__imp_BCryptHashData
0x180022075  mov     ebx, eax
0x180022077  test    eax, eax
0x180022079  jns     short loc_1800220A6
0x18002207b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022082  lea     rax, WPP_GLOBAL_Control
0x180022089  cmp     rcx, rax
0x18002208c  jz      loc_18002213B
0x180022092  test    byte ptr [rcx+1Ch], 1
0x180022096  jz      loc_18002213B
0x18002209c  mov     edx, 1Dh
0x1800220a1  jmp     loc_180022128
0x1800220a6  mov     r8d, [rsp+78h+cbInput]; cbInput
0x1800220ae  xor     r9d, r9d; dwFlags
0x1800220b1  mov     rdx, [rsp+78h+arg_30]; pbInput
0x1800220b9  mov     rcx, [rsp+78h+hHash]; hHash
0x1800220be  call    cs:__imp_BCryptHashData
0x1800220c4  mov     ebx, eax
0x1800220c6  test    eax, eax
0x1800220c8  jns     short loc_1800220EA
0x1800220ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220d1  lea     rax, WPP_GLOBAL_Control
0x1800220d8  cmp     rcx, rax
0x1800220db  jz      short loc_18002213B
0x1800220dd  test    byte ptr [rcx+1Ch], 1
0x1800220e1  jz      short loc_18002213B
0x1800220e3  mov     edx, 1Eh
0x1800220e8  jmp     short loc_180022128
0x1800220ea  mov     rdx, [rsp+78h+pbOutput]; pbOutput
0x1800220f2  xor     r9d, r9d; dwFlags
0x1800220f5  mov     rcx, [rsp+78h+hHash]; hHash
0x1800220fa  lea     r8d, [r9+10h]; cbOutput
0x1800220fe  call    cs:__imp_BCryptFinishHash
0x180022104  mov     ebx, eax
0x180022106  test    eax, eax
0x180022108  jns     short loc_18002213B
0x18002210a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022111  lea     rax, WPP_GLOBAL_Control
0x180022118  cmp     rcx, rax
0x18002211b  jz      short loc_18002213B
0x18002211d  test    byte ptr [rcx+1Ch], 1
0x180022121  jz      short loc_18002213B
0x180022123  mov     edx, 1Fh
0x180022128  mov     rcx, [rcx+10h]
0x18002212c  lea     r8, WPP_2467158bb6003f4dc4982d488f18e69e_Traceguids
0x180022133  mov     r9d, ebx
0x180022136  call    WPP_SF_d
0x18002213b  mov     rcx, [rsp+78h+hHash]; hHash
0x180022140  test    rcx, rcx
0x180022143  jz      short loc_18002214B
0x180022145  call    cs:__imp_BCryptDestroyHash
0x18002214b  mov     eax, ebx
0x18002214d  add     rsp, 58h
0x180022151  pop     rdi
0x180022152  pop     rsi
0x180022153  pop     rbp
0x180022154  pop     rbx
0x180022155  retn
```
