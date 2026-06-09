# DiscpCopyiSNSServerInfoObject

- ea: `0x18000be3c`
- end: `0x18000bef4`
- name: `DiscpCopyiSNSServerInfoObject`
- size: `184`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000befc`

## callees

- `0x18000325c`
- `0x18000be3c`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x18000be94`
- `ISCSIUM!DiscpAllocMemory` at `0x18000be94`
- `ISCSIUM!DiscpFreeMemory` at `0x18000beb9`
- `ISCSIUM!DiscpFreeMemory` at `0x18000beb9`

## pseudocode

```c
__int64 __fastcall DiscpCopyiSNSServerInfoObject(__int64 a1)
{
  const wchar_t *v2; // rdi
  _WORD *v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rsi
  __int64 v6; // rax
  __int64 v7; // r11

  if ( !a1 )
    return 0;
  v2 = (const wchar_t *)(a1 + 34);
  if ( a1 == -34 )
    return 0;
  v3 = (_WORD *)(a1 + 34);
  v4 = 0x7FFFFFFF;
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v4;
  }
  while ( v4 );
  v5 = (0x7FFFFFFF - v4) & -(__int64)(v4 != 0);
  if ( !v4 )
    return 0;
  v6 = DiscpAllocMemory((unsigned int)(2 * v5 + 40));
  v7 = v6;
  if ( v6 )
  {
    if ( StringCchCopyW((STRSAFE_LPWSTR)(v6 + 34), v5 + 1, v2) >= 0 )
    {
      *(_QWORD *)(v7 + 8) = v7;
      *(_QWORD *)v7 = v7;
      *(_QWORD *)(v7 + 16) = *(_QWORD *)(a1 + 16);
      *(_QWORD *)(v7 + 24) = *(_QWORD *)(a1 + 24);
      *(_WORD *)(v7 + 32) = *(_WORD *)(a1 + 32);
    }
    else
    {
      DiscpFreeMemory(v7);
      return 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000be3c  push    rbx
0x18000be3e  push    rbp
0x18000be3f  push    rsi
0x18000be40  push    rdi
0x18000be41  sub     rsp, 28h
0x18000be45  xor     ebp, ebp
0x18000be47  mov     rbx, rcx
0x18000be4a  test    rcx, rcx
0x18000be4d  jz      loc_18000BEE9
0x18000be53  lea     rdi, [rcx+22h]
0x18000be57  test    rdi, rdi
0x18000be5a  jz      loc_18000BEE9
0x18000be60  mov     edx, 7FFFFFFFh
0x18000be65  mov     rax, rdi
0x18000be68  mov     ecx, edx
0x18000be6a  cmp     [rax], bp
0x18000be6d  jz      short loc_18000BE79
0x18000be6f  add     rax, 2
0x18000be73  sub     rcx, 1
0x18000be77  jnz     short loc_18000BE6A
0x18000be79  sub     rdx, rcx
0x18000be7c  mov     rax, rcx
0x18000be7f  neg     rax
0x18000be82  sbb     rsi, rsi
0x18000be85  and     rsi, rdx
0x18000be88  test    rcx, rcx
0x18000be8b  jz      short loc_18000BEE9
0x18000be8d  lea     ecx, ds:28h[rsi*2]
0x18000be94  call    cs:__imp_DiscpAllocMemory
0x18000be9a  mov     r11, rax
0x18000be9d  test    rax, rax
0x18000bea0  jz      short loc_18000BEE4
0x18000bea2  lea     rdx, [rsi+1]; cchDest
0x18000bea6  mov     r8, rdi; pszSrc
0x18000bea9  lea     rcx, [rax+22h]; pszDest
0x18000bead  call    StringCchCopyW
0x18000beb2  test    eax, eax
0x18000beb4  jns     short loc_18000BEC4
0x18000beb6  mov     rcx, r11
0x18000beb9  call    cs:__imp_DiscpFreeMemory
0x18000bebf  mov     r11, rbp
0x18000bec2  jmp     short loc_18000BEE4
0x18000bec4  mov     [r11+8], r11
0x18000bec8  mov     [r11], r11
0x18000becb  mov     rax, [rbx+10h]
0x18000becf  mov     [r11+10h], rax
0x18000bed3  mov     rax, [rbx+18h]
0x18000bed7  mov     [r11+18h], rax
0x18000bedb  movzx   eax, word ptr [rbx+20h]
0x18000bedf  mov     [r11+20h], ax
0x18000bee4  mov     rax, r11
0x18000bee7  jmp     short loc_18000BEEB
0x18000bee9  xor     eax, eax
0x18000beeb  add     rsp, 28h
0x18000beef  pop     rdi
0x18000bef0  pop     rsi
0x18000bef1  pop     rbp
0x18000bef2  pop     rbx
0x18000bef3  retn
```
