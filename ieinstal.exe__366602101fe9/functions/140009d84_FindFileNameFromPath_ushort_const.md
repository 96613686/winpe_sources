# FindFileNameFromPath(ushort const *)

- ea: `0x140009d84`
- end: `0x140009def`
- name: `?FindFileNameFromPath@@YAPEAGPEBG@Z`
- size: `107`
- prototype: `unsigned __int16 *__fastcall(LPCWSTR lpsz)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140009240`
- `0x1400094a4`
- `0x14000c0fc`

## callees

- `0x140009d84`

## import_xrefs

- `USER32!CharNextW` at `0x140009dcc`
- `USER32!CharNextW` at `0x140009dcc`

## pseudocode

```c
unsigned __int16 *__fastcall FindFileNameFromPath(WCHAR *lpsz)
{
  LPWSTR v1; // rax
  WCHAR *v2; // rbx
  WCHAR i; // cx
  _WORD *v4; // rcx

  v1 = lpsz;
  v2 = lpsz;
  if ( lpsz )
  {
    for ( i = *lpsz; i; i = *v1 )
    {
      if ( i == 92 || *v1 == 58 || *v1 == 47 )
      {
        v4 = v1 + 1;
        if ( v1[1] && *v4 != 92 && *v4 != 47 )
          v2 = v1 + 1;
      }
      v1 = CharNextW(v1);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140009d84  mov     [rsp+arg_0], rbx
0x140009d89  push    rdi
0x140009d8a  sub     rsp, 20h
0x140009d8e  xor     edi, edi
0x140009d90  mov     rax, rcx
0x140009d93  mov     rbx, rcx
0x140009d96  test    rcx, rcx
0x140009d99  jz      short loc_140009DE0
0x140009d9b  movzx   ecx, word ptr [rcx]
0x140009d9e  jmp     short loc_140009DDB
0x140009da0  cmp     cx, 5Ch ; '\'
0x140009da4  jz      short loc_140009DB2
0x140009da6  cmp     word ptr [rax], 3Ah ; ':'
0x140009daa  jz      short loc_140009DB2
0x140009dac  cmp     word ptr [rax], 2Fh ; '/'
0x140009db0  jnz     short loc_140009DC9
0x140009db2  lea     rcx, [rax+2]
0x140009db6  cmp     [rcx], di
0x140009db9  jz      short loc_140009DC9
0x140009dbb  cmp     word ptr [rcx], 5Ch ; '\'
0x140009dbf  jz      short loc_140009DC9
0x140009dc1  cmp     word ptr [rcx], 2Fh ; '/'
0x140009dc5  cmovnz  rbx, rcx
0x140009dc9  mov     rcx, rax; lpsz
0x140009dcc  call    cs:__imp_CharNextW
0x140009dd3  nop     dword ptr [rax+rax+00h]
0x140009dd8  movzx   ecx, word ptr [rax]
0x140009ddb  test    cx, cx
0x140009dde  jnz     short loc_140009DA0
0x140009de0  mov     rax, rbx
0x140009de3  mov     rbx, [rsp+28h+arg_0]
0x140009de8  add     rsp, 20h
0x140009dec  pop     rdi
0x140009ded  retn
```
