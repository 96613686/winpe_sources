# LuafvPreQueryOpen

- ea: `0x140018700`
- end: `0x14001879d`
- name: `LuafvPreQueryOpen`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14001860c`
- `0x140018700`
- `0x1400187b0`

## pseudocode

```c
__int64 __fastcall LuafvPreQueryOpen(struct _FLT_CALLBACK_DATA *a1)
{
  unsigned int v2; // ebx
  int v3; // eax
  NTSTATUS v4; // edi
  _DWORD v6[6]; // [rsp+20h] [rbp-18h] BYREF
  char v7; // [rsp+58h] [rbp+20h] BYREF

  v7 = 0;
  v2 = 1;
  v6[0] = 0;
  if ( !DisableVirt )
  {
    v3 = LuafvQueryVirtualizationCaller(a1, &v7, v6);
    v4 = v3;
    if ( v3 < 0 )
    {
      LuafvLogFileError(a1, 0, &LuafvQueryVirtualizationFailed, (unsigned int)v3);
      if ( v4 == -1073741670 || v4 == -1073741773 )
      {
        a1->IoStatus.Status = v4;
        v2 = 4;
        a1->IoStatus.Information = 0;
      }
    }
    else if ( v7 && (v6[0] & 1) == 0 )
    {
      return 6;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140018700  mov     rax, rsp
0x140018703  mov     [rax+8], rbx
0x140018707  mov     [rax+10h], rsi
0x14001870b  push    rdi
0x14001870c  sub     rsp, 30h
0x140018710  cmp     cs:DisableVirt, 0
0x140018717  mov     rsi, rcx
0x14001871a  mov     byte ptr [rax+20h], 0
0x14001871e  mov     ebx, 1
0x140018723  mov     dword ptr [rax-18h], 0
0x14001872a  jnz     short loc_140018746
0x14001872c  lea     r8, [rax-18h]
0x140018730  lea     rdx, [rax+20h]
0x140018734  call    LuafvQueryVirtualizationCaller
0x140018739  mov     edi, eax
0x14001873b  test    eax, eax
0x14001873d  js      short loc_140018767
0x14001873f  cmp     [rsp+38h+arg_18], 0
0x140018744  jnz     short loc_140018759
0x140018746  mov     rsi, [rsp+38h+arg_8]
0x14001874b  mov     eax, ebx
0x14001874d  mov     rbx, [rsp+38h+arg_0]
0x140018752  add     rsp, 30h
0x140018756  pop     rdi
0x140018757  retn
0x140018759  test    byte ptr [rsp+38h+var_18], bl
0x14001875d  mov     eax, 6
0x140018762  cmovz   ebx, eax
0x140018765  jmp     short loc_140018746
0x140018767  mov     r9d, edi
0x14001876a  lea     r8, LuafvQueryVirtualizationFailed
0x140018771  xor     edx, edx
0x140018773  mov     rcx, rsi
0x140018776  call    LuafvLogFileError
0x14001877b  cmp     edi, 0C000009Ah
0x140018781  jz      short loc_14001878B
0x140018783  cmp     edi, 0C0000033h
0x140018789  jnz     short loc_140018746
0x14001878b  mov     [rsi+18h], edi
0x14001878e  mov     ebx, 4
0x140018793  mov     qword ptr [rsi+20h], 0
0x14001879b  jmp     short loc_140018746
```
