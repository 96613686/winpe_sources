# CSetForegroundWindowHelper::RegHotKey(void)

- ea: `0x1800471f4`
- end: `0x18004728b`
- name: `?RegHotKey@CSetForegroundWindowHelper@@AEAAHXZ`
- size: `151`
- prototype: `__int64 __fastcall(CSetForegroundWindowHelper *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800476bc`

## callees

- `0x1800471f4`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x180047210`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x180047210`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18004726a`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18004726a`
- `USER32!RegisterHotKey` at `0x18004723f`
- `USER32!RegisterHotKey` at `0x18004723f`

## pseudocode

```c
__int64 __fastcall CSetForegroundWindowHelper::RegHotKey(CSetForegroundWindowHelper *this)
{
  ATOM v1; // cx
  unsigned __int16 v2; // ax
  int v3; // ebx
  __int64 result; // rax

  if ( word_1800619C8 )
    return 1;
  v1 = GlobalAddAtomW(L"MSAASetFocusHotKey");
  word_1800619C8 = v1;
  v2 = word_1800619CA;
  v3 = 0;
  while ( v3 < 20 )
  {
    if ( RegisterHotKey(g_GetFocus, v1, 0, v2) )
      return 1;
    ++v3;
    v2 = word_1800619CA - 1;
    v1 = word_1800619C8;
    --word_1800619CA;
  }
  GlobalDeleteAtom(v1);
  result = 0;
  word_1800619C8 = 0;
  return result;
}

```

## disassembly

```asm
0x1800471f4  mov     [rsp+arg_0], rbx
0x1800471f9  push    rdi
0x1800471fa  sub     rsp, 20h
0x1800471fe  xor     edi, edi
0x180047200  cmp     cs:word_1800619C8, di
0x180047207  jnz     short loc_18004727B
0x180047209  lea     rcx, aMsaasetfocusho; "MSAASetFocusHotKey"
0x180047210  call    cs:__imp_GlobalAddAtomW
0x180047216  movzx   ecx, ax; nAtom
0x180047219  mov     cs:word_1800619C8, ax
0x180047220  movzx   eax, cs:word_1800619CA
0x180047227  mov     ebx, edi
0x180047229  cmp     ebx, 14h
0x18004722c  jge     short loc_18004726A
0x18004722e  movzx   edx, cx; id
0x180047231  xor     r8d, r8d; fsModifiers
0x180047234  mov     rcx, cs:?g_GetFocus@@3VCSetForegroundWindowHelper@@A; hWnd
0x18004723b  movzx   r9d, ax; vk
0x18004723f  call    cs:__imp_RegisterHotKey
0x180047245  test    eax, eax
0x180047247  jnz     short loc_18004727B
0x180047249  movzx   eax, cs:word_1800619CA
0x180047250  mov     ecx, 0FFFFh
0x180047255  inc     ebx
0x180047257  add     ax, cx
0x18004725a  movzx   ecx, cs:word_1800619C8
0x180047261  mov     cs:word_1800619CA, ax
0x180047268  jmp     short loc_180047229
0x18004726a  call    cs:__imp_GlobalDeleteAtom
0x180047270  xor     eax, eax
0x180047272  mov     cs:word_1800619C8, di
0x180047279  jmp     short loc_180047280
0x18004727b  mov     eax, 1
0x180047280  mov     rbx, [rsp+28h+arg_0]
0x180047285  add     rsp, 20h
0x180047289  pop     rdi
0x18004728a  retn
```
