# TextLogRequestLogFileRename

- ea: `0x1800057a8`
- end: `0x18000589a`
- name: `TextLogRequestLogFileRename`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x1800063bc`

## callees

- `0x180004e0c`
- `0x1800057a8`
- `0x1800070cc`

## pseudocode

```c
__int64 __fastcall TextLogRequestLogFileRename(__int64 a1)
{
  unsigned int v1; // edi
  unsigned int v2; // esi
  unsigned int v3; // edx
  __int64 v4; // rbx
  __int64 v5; // rdi
  unsigned int v6; // ebp
  unsigned int v7; // ecx
  __int64 v9; // rbx
  __int128 v10; // [rsp+20h] [rbp-48h] BYREF
  int v11; // [rsp+30h] [rbp-38h]

  v11 = 0;
  v1 = 0;
  v2 = 0;
  v10 = 0;
  v3 = 0;
  v4 = a1;
  while ( (unsigned int)TextLogEnumerateOpenSections(a1, v3, (__int64)&v10) )
  {
    ++v1;
    if ( DWORD1(v10) || (v11 & 0x10000) == 0 )
      ++v2;
    v3 = v1;
    a1 = v4;
  }
  v5 = *(_QWORD *)(v4 + 32);
  if ( !v2 )
  {
    *(_DWORD *)(v5 + 28) = 0;
    v6 = 1;
    *(_DWORD *)(*(_QWORD *)(v4 + 32) + 32LL) = 0;
    *(_DWORD *)(*(_QWORD *)(v4 + 32) + 48LL) = 0;
    return v6;
  }
  v6 = 0;
  if ( *(_DWORD *)(v4 + 24) - *(_DWORD *)(v4 + 16) < (unsigned int)(*(_DWORD *)(v5 + 8) + 0x40000) )
    goto LABEL_15;
  v7 = *(_DWORD *)(v5 + 28);
  if ( !v7 )
  {
LABEL_11:
    *(_DWORD *)(v5 + 28) = v2;
    *(_DWORD *)(v5 + 32) = 0;
LABEL_16:
    *(_DWORD *)(v5 + 48) = 0;
    return v6;
  }
  if ( v2 == v7 )
  {
    if ( ++*(_DWORD *)(v5 + 48) < 4u )
      return v6;
    v6 = 1;
LABEL_15:
    *(_QWORD *)(v5 + 28) = 0;
    goto LABEL_16;
  }
  if ( v2 <= v7 )
    goto LABEL_11;
  if ( !*(_DWORD *)(v5 + 32) || *(_DWORD *)(v5 + 32) < v2 - v7 )
  {
    *(_DWORD *)(v5 + 32) = v2 - v7;
    *(_QWORD *)(v5 + 40) = pSetupGetTickCount();
    return v6;
  }
  v9 = *(_QWORD *)(v5 + 40);
  if ( pSetupGetTickCount() - v9 > 0x493E0 )
    goto LABEL_11;
  return v6;
}

```

## disassembly

```asm
0x1800057a8  push    rbx
0x1800057aa  push    rbp
0x1800057ab  push    rsi
0x1800057ac  push    rdi
0x1800057ad  push    r14
0x1800057af  sub     rsp, 40h
0x1800057b3  xor     r14d, r14d
0x1800057b6  xor     eax, eax
0x1800057b8  xorps   xmm0, xmm0
0x1800057bb  mov     [rsp+68h+var_38], eax
0x1800057bf  mov     edi, r14d
0x1800057c2  mov     esi, r14d
0x1800057c5  movups  [rsp+68h+var_48], xmm0
0x1800057ca  xor     edx, edx
0x1800057cc  mov     rbx, rcx
0x1800057cf  jmp     short loc_1800057E8
0x1800057d1  inc     edi
0x1800057d3  cmp     dword ptr [rsp+68h+var_48+4], r14d
0x1800057d8  jnz     short loc_1800057E1
0x1800057da  test    byte ptr [rsp+68h+var_38+2], 1
0x1800057df  jnz     short loc_1800057E3
0x1800057e1  inc     esi
0x1800057e3  mov     edx, edi
0x1800057e5  mov     rcx, rbx
0x1800057e8  lea     r8, [rsp+68h+var_48]
0x1800057ed  call    TextLogEnumerateOpenSections
0x1800057f2  test    eax, eax
0x1800057f4  jnz     short loc_1800057D1
0x1800057f6  mov     rdi, [rbx+20h]
0x1800057fa  test    esi, esi
0x1800057fc  jnz     short loc_180005817
0x1800057fe  mov     [rdi+1Ch], r14d
0x180005802  lea     ebp, [rsi+1]
0x180005805  mov     rax, [rbx+20h]
0x180005809  mov     [rax+20h], r14d
0x18000580d  mov     rax, [rbx+20h]
0x180005811  mov     [rax+30h], r14d
0x180005815  jmp     short loc_180005856
0x180005817  mov     ecx, [rbx+18h]
0x18000581a  mov     ebp, r14d
0x18000581d  mov     eax, [rdi+8]
0x180005820  sub     ecx, [rbx+10h]
0x180005823  add     eax, 40000h
0x180005828  cmp     ecx, eax
0x18000582a  jb      short loc_18000584E
0x18000582c  mov     ecx, [rdi+1Ch]
0x18000582f  test    ecx, ecx
0x180005831  jnz     short loc_18000583C
0x180005833  mov     [rdi+1Ch], esi
0x180005836  mov     [rdi+20h], r14d
0x18000583a  jmp     short loc_180005852
0x18000583c  cmp     esi, ecx
0x18000583e  jnz     short loc_180005863
0x180005840  inc     dword ptr [rdi+30h]
0x180005843  cmp     dword ptr [rdi+30h], 4
0x180005847  jb      short loc_180005856
0x180005849  mov     ebp, 1
0x18000584e  mov     [rdi+1Ch], r14
0x180005852  mov     [rdi+30h], r14d
0x180005856  mov     eax, ebp
0x180005858  add     rsp, 40h
0x18000585c  pop     r14
0x18000585e  pop     rdi
0x18000585f  pop     rsi
0x180005860  pop     rbp
0x180005861  pop     rbx
0x180005862  retn
0x180005863  jbe     short loc_180005833
0x180005865  cmp     [rdi+20h], r14d
0x180005869  jz      short loc_18000588A
0x18000586b  mov     eax, esi
0x18000586d  sub     eax, ecx
0x18000586f  cmp     [rdi+20h], eax
0x180005872  jb      short loc_18000588A
0x180005874  mov     rbx, [rdi+28h]
0x180005878  call    pSetupGetTickCount
0x18000587d  sub     rax, rbx
0x180005880  cmp     rax, 493E0h
0x180005886  jbe     short loc_180005856
0x180005888  jmp     short loc_180005833
0x18000588a  sub     esi, ecx
0x18000588c  mov     [rdi+20h], esi
0x18000588f  call    pSetupGetTickCount
0x180005894  mov     [rdi+28h], rax
0x180005898  jmp     short loc_180005856
```
