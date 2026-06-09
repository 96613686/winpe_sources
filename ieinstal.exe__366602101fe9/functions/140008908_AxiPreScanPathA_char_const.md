# AxiPreScanPathA(char const *)

- ea: `0x140008908`
- end: `0x14000897c`
- name: `?AxiPreScanPathA@@YAJPEBD@Z`
- size: `116`
- prototype: `__int64 __fastcall(const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140008a0c`

## callees

- `0x140008908`
- `0x140009c48`

## import_xrefs

- `msvcrt!iscntrl` at `0x140008950`
- `msvcrt!iscntrl` at `0x140008950`

## pseudocode

```c
__int64 __fastcall AxiPreScanPathA(const char *a1)
{
  __int64 result; // rax
  __int64 i; // rbx
  unsigned int v4; // edx
  __int64 v5; // rcx
  __int64 v6; // rdx
  int v7; // eax

  result = 0;
  if ( a1 )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v4 = a1[i];
      result = 0;
      if ( !a1[i] )
        return result;
      v5 = v4;
      v6 = v4 - 34;
      if ( (_DWORD)v6
        && (v6 = (unsigned int)(v6 - 8), (_DWORD)v6)
        && (v6 = (unsigned int)(v6 - 18), (_DWORD)v6)
        && (v6 = (unsigned int)(v6 - 2), (_DWORD)v6)
        && (v6 = (unsigned int)(v6 - 1), (_DWORD)v6)
        && (_DWORD)v6 != 61 )
      {
        if ( (unsigned int)v5 >= 0x80 )
          continue;
        v7 = iscntrl(v5);
      }
      else
      {
        v7 = FilenameDisallowCharacter(v5, v6);
      }
      if ( v7 )
        return 2147942487LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140008908  mov     [rsp+arg_0], rbx
0x14000890d  push    rdi
0x14000890e  sub     rsp, 20h
0x140008912  xor     eax, eax
0x140008914  mov     rdi, rcx
0x140008917  test    rcx, rcx
0x14000891a  jz      short loc_140008970
0x14000891c  xor     ebx, ebx
0x14000891e  movsx   edx, byte ptr [rbx+rdi]
0x140008922  xor     eax, eax
0x140008924  test    dl, dl
0x140008926  jz      short loc_140008970
0x140008928  mov     ecx, edx; C
0x14000892a  sub     edx, 22h ; '"'
0x14000892d  jz      short loc_14000895E
0x14000892f  sub     edx, 8
0x140008932  jz      short loc_14000895E
0x140008934  sub     edx, 12h
0x140008937  jz      short loc_14000895E
0x140008939  sub     edx, 2
0x14000893c  jz      short loc_14000895E
0x14000893e  sub     edx, 1
0x140008941  jz      short loc_14000895E
0x140008943  cmp     edx, 3Dh ; '='
0x140008946  jz      short loc_14000895E
0x140008948  cmp     ecx, 80h
0x14000894e  jnb     short loc_140008967
0x140008950  call    cs:__imp_iscntrl
0x140008957  nop     dword ptr [rax+rax+00h]
0x14000895c  jmp     short loc_140008963
0x14000895e  call    FilenameDisallowCharacter
0x140008963  test    eax, eax
0x140008965  jnz     short loc_14000896B
0x140008967  inc     ebx
0x140008969  jmp     short loc_14000891E
0x14000896b  mov     eax, 80070057h
0x140008970  mov     rbx, [rsp+28h+arg_0]
0x140008975  add     rsp, 20h
0x140008979  pop     rdi
0x14000897a  retn
```
