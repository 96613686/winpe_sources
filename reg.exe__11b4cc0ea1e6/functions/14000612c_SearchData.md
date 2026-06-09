# SearchData

- ea: `0x14000612c`
- end: `0x14000638c`
- name: `SearchData`
- size: `608`
- prototype: `__int64 __fastcall(LPCWSTR lpString)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400055f8`
- `0x140005940`
- `0x140005e84`

## callees

- `0x14000612c`
- `0x14000c62c`
- `0x14000c9c0`
- `0x14000ccc4`
- `0x14000d5c4`
- `0x14000daa4`
- `0x14000e284`
- `0x14000e2f8`
- `0x14000e450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006356`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000636f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006356`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000636f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000628a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000628a`

## pseudocode

```c
__int64 __fastcall SearchData(LPCWSTR lpString, int a2, unsigned int a3, __int64 a4)
{
  const WCHAR *v4; // r14
  __int64 v5; // r12
  __int64 v6; // rbp
  _WORD *v8; // rsi
  unsigned int v9; // r15d
  void *Memory; // rax
  const WCHAR *v11; // r13
  unsigned int v12; // edi
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  unsigned int v17; // ebx
  __int64 Reason; // rax
  int v19; // ebx
  const WCHAR *v20; // r12
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // r8
  int v24; // eax
  _WORD *v25; // rax
  int v26; // eax
  const WCHAR *v27; // rdx
  DWORD v28; // ecx
  void *v30; // [rsp+70h] [rbp+8h] BYREF
  __int64 v31; // [rsp+88h] [rbp+20h]

  v31 = a4;
  v4 = lpString;
  v5 = a3;
  v6 = a4;
  v30 = 0;
  v8 = 0;
  if ( !lpString || !a4 )
  {
    v28 = 87;
    goto LABEL_38;
  }
  if ( a2 == 1 || a2 == 2 )
  {
    v9 = 0;
    v11 = lpString;
    goto LABEL_8;
  }
  v9 = 2 * a3 + 12;
  Memory = AllocateMemory(2 * v9);
  v30 = Memory;
  v8 = Memory;
  if ( Memory )
  {
    v11 = (const WCHAR *)Memory;
LABEL_8:
    v12 = 1;
    v13 = a2 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 2;
        if ( v15 && (v16 = v15 - 1) != 0 )
        {
          if ( v16 == 2 )
          {
            v19 = 0;
            StringCopyW(v8, &cwszNullString, v9);
            v20 = (const WCHAR *)((char *)v4 + v5);
            if ( v4 < v20 )
            {
              do
              {
                if ( *v4 )
                {
                  if ( v19 == 1 )
                    StringConcatW(v8, v6 + 60, v9);
                  StringConcatW(v8, v4, v9);
                  v21 = 2LL * (unsigned int)lstrlenW(v4);
                }
                else
                {
                  v19 = 1;
                  v21 = 2;
                }
                v4 = (const WCHAR *)((char *)v4 + v21);
              }
              while ( v4 < v20 );
              v6 = v31;
            }
          }
          else
          {
            StringCopyW(v8, &cwszNullString, v9);
            v17 = 0;
            if ( (_DWORD)v5 )
            {
              while ( (unsigned int)SetReason2(1, L"%02X", *((unsigned __int8 *)v4 + v17)) )
              {
                Reason = GetReason();
                StringConcatW(v8, Reason, v9);
                if ( ++v17 >= (unsigned int)v5 )
                  goto LABEL_29;
              }
              goto LABEL_33;
            }
          }
        }
        else
        {
          v22 = StringCompareW(*(PCNZWCH *)(v6 + 120), L"0x", 1, 2);
          v23 = *(unsigned int *)v4;
          if ( v22 )
            v24 = SetReason2(1, L"%d", v23);
          else
            v24 = SetReason2(1, L"0x%x", v23);
          if ( !v24 )
          {
LABEL_33:
            FreeMemory(&v30);
            v28 = 14;
LABEL_38:
            SetLastError(v28);
            return 0;
          }
          v25 = (_WORD *)GetReason();
          StringCopyW(v8, v25, v9);
        }
      }
    }
LABEL_29:
    v26 = *(_DWORD *)(v6 + 36);
    v27 = *(const WCHAR **)(v6 + 120);
    if ( *(_DWORD *)(v6 + 40) )
    {
      if ( (unsigned int)StringCompareW(v11, v27, v26 == 0, 0) )
      {
LABEL_35:
        v12 = 0;
        SetLastError(0x490u);
      }
    }
    else if ( !(unsigned int)MatchPatternEx(v11, v27, v26 != 0 ? 2 : 258) )
    {
      goto LABEL_35;
    }
    FreeMemory(&v30);
    return v12;
  }
  return 0;
}

```

## disassembly

```asm
0x14000612c  mov     [rsp+arg_8], rbx
0x140006131  mov     [rsp+arg_18], r9
0x140006136  push    rbp
0x140006137  push    rsi
0x140006138  push    rdi
0x140006139  push    r12
0x14000613b  push    r13
0x14000613d  push    r14
0x14000613f  push    r15
0x140006141  sub     rsp, 30h
0x140006145  mov     r14, rcx
0x140006148  mov     r12d, r8d
0x14000614b  xor     ecx, ecx
0x14000614d  mov     rbp, r9
0x140006150  mov     [rsp+68h+arg_0], rcx
0x140006155  mov     ebx, edx
0x140006157  mov     esi, ecx
0x140006159  test    r14, r14
0x14000615c  jz      loc_14000636A
0x140006162  test    r9, r9
0x140006165  jz      loc_14000636A
0x14000616b  mov     eax, edx
0x14000616d  sub     eax, 1
0x140006170  jz      short loc_1400061A0
0x140006172  cmp     eax, 1
0x140006175  jz      short loc_1400061A0
0x140006177  lea     r15d, ds:0Ch[r12*2]
0x14000617f  lea     ecx, [r15+r15]; dwBytes
0x140006183  call    AllocateMemory
0x140006188  xor     ecx, ecx
0x14000618a  mov     [rsp+68h+arg_0], rax
0x14000618f  mov     rsi, rax
0x140006192  test    rax, rax
0x140006195  jz      loc_140006375
0x14000619b  mov     r13, rax
0x14000619e  jmp     short loc_1400061A6
0x1400061a0  mov     r15d, ecx
0x1400061a3  mov     r13, r14
0x1400061a6  mov     edi, 1
0x1400061ab  mov     [rsp+68h+var_48], r13
0x1400061b0  sub     ebx, edi
0x1400061b2  jz      loc_1400062F1
0x1400061b8  sub     ebx, edi
0x1400061ba  jz      loc_1400062F1
0x1400061c0  sub     ebx, 2
0x1400061c3  jz      loc_1400062AC
0x1400061c9  sub     ebx, edi
0x1400061cb  jz      loc_1400062AC
0x1400061d1  lea     rdx, cwszNullString
0x1400061d8  mov     r8d, r15d
0x1400061db  cmp     ebx, 2
0x1400061de  jz      short loc_140006231
0x1400061e0  mov     rcx, rsi
0x1400061e3  call    StringCopyW
0x1400061e8  xor     eax, eax
0x1400061ea  mov     ebx, eax
0x1400061ec  test    r12d, r12d
0x1400061ef  jz      loc_1400062F1
0x1400061f5  mov     eax, ebx
0x1400061f7  lea     rdx, a02x; "%02X"
0x1400061fe  mov     ecx, edi
0x140006200  movzx   r8d, byte ptr [rax+r14]
0x140006205  call    SetReason2
0x14000620a  test    eax, eax
0x14000620c  jz      loc_140006329
0x140006212  call    GetReason
0x140006217  mov     rdx, rax
0x14000621a  mov     r8d, r15d
0x14000621d  mov     rcx, rsi
0x140006220  call    StringConcatW
0x140006225  add     ebx, edi
0x140006227  cmp     ebx, r12d
0x14000622a  jb      short loc_1400061F5
0x14000622c  jmp     loc_1400062F1
0x140006231  mov     ebx, ecx
0x140006233  lea     rax, [rbp+3Ch]
0x140006237  mov     rcx, rsi
0x14000623a  mov     [rsp+68h+var_40], rax
0x14000623f  call    StringCopyW
0x140006244  add     r12, r14
0x140006247  cmp     r14, r12
0x14000624a  jnb     loc_1400062F1
0x140006250  mov     rbp, [rsp+68h+var_40]
0x140006255  xor     r13d, r13d
0x140006258  cmp     [r14], r13w
0x14000625c  jnz     short loc_140006267
0x14000625e  mov     ebx, edi
0x140006260  mov     eax, 2
0x140006265  jmp     short loc_140006295
0x140006267  cmp     ebx, edi
0x140006269  jnz     short loc_140006279
0x14000626b  mov     r8d, r15d
0x14000626e  mov     rdx, rbp
0x140006271  mov     rcx, rsi
0x140006274  call    StringConcatW
0x140006279  mov     r8d, r15d
0x14000627c  mov     rdx, r14
0x14000627f  mov     rcx, rsi
0x140006282  call    StringConcatW
0x140006287  mov     rcx, r14; lpString
0x14000628a  call    cs:__imp_lstrlenW
0x140006290  mov     eax, eax
0x140006292  add     rax, rax
0x140006295  add     r14, rax
0x140006298  cmp     r14, r12
0x14000629b  jb      short loc_140006258
0x14000629d  mov     rbp, [rsp+68h+arg_18]
0x1400062a5  mov     r13, [rsp+68h+var_48]
0x1400062aa  jmp     short loc_1400062F1
0x1400062ac  mov     rcx, [rbp+78h]; lpString1
0x1400062b0  lea     rdx, a0x; "0x"
0x1400062b7  mov     r9d, 2
0x1400062bd  mov     r8d, edi
0x1400062c0  call    StringCompareW
0x1400062c5  mov     r8d, [r14]
0x1400062c8  mov     ecx, edi
0x1400062ca  test    eax, eax
0x1400062cc  jnz     short loc_140006320
0x1400062ce  lea     rdx, a0xX; "0x%x"
0x1400062d5  call    SetReason2
0x1400062da  test    eax, eax
0x1400062dc  jz      short loc_140006329
0x1400062de  call    GetReason
0x1400062e3  mov     rdx, rax
0x1400062e6  mov     r8d, r15d
0x1400062e9  mov     rcx, rsi
0x1400062ec  call    StringCopyW
0x1400062f1  mov     eax, [rbp+24h]
0x1400062f4  xor     esi, esi
0x1400062f6  mov     rcx, r13; lpString1
0x1400062f9  mov     rdx, [rbp+78h]; lpString2
0x1400062fd  cmp     [rbp+28h], esi
0x140006300  jnz     short loc_14000633A
0x140006302  neg     eax
0x140006304  sbb     r8d, r8d
0x140006307  and     r8d, 0FFFFFF00h
0x14000630e  add     r8d, 102h
0x140006315  call    MatchPatternEx
0x14000631a  test    eax, eax
0x14000631c  jnz     short loc_14000635C
0x14000631e  jmp     short loc_14000634F
0x140006320  lea     rdx, aD; "%d"
0x140006327  jmp     short loc_1400062D5
0x140006329  lea     rcx, [rsp+68h+arg_0]
0x14000632e  call    FreeMemory
0x140006333  mov     ecx, 0Eh
0x140006338  jmp     short loc_14000636F
0x14000633a  test    eax, eax
0x14000633c  mov     r8d, esi
0x14000633f  setz    r8b
0x140006343  xor     r9d, r9d
0x140006346  call    StringCompareW
0x14000634b  test    eax, eax
0x14000634d  jz      short loc_14000635C
0x14000634f  mov     ecx, 490h; dwErrCode
0x140006354  mov     edi, esi
0x140006356  call    cs:__imp_SetLastError
0x14000635c  lea     rcx, [rsp+68h+arg_0]
0x140006361  call    FreeMemory
0x140006366  mov     eax, edi
0x140006368  jmp     short loc_140006377
0x14000636a  mov     ecx, 57h ; 'W'; dwErrCode
0x14000636f  call    cs:__imp_SetLastError
0x140006375  xor     eax, eax
0x140006377  mov     rbx, [rsp+68h+arg_8]
0x14000637c  add     rsp, 30h
0x140006380  pop     r15
0x140006382  pop     r14
0x140006384  pop     r13
0x140006386  pop     r12
0x140006388  pop     rdi
0x140006389  pop     rsi
0x14000638a  pop     rbp
0x14000638b  retn
```
