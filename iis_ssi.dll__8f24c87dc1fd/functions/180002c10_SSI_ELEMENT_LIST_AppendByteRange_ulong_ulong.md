# SSI_ELEMENT_LIST::AppendByteRange(ulong,ulong)

- ea: `0x180002c10`
- end: `0x180002caa`
- name: `?AppendByteRange@SSI_ELEMENT_LIST@@AEAAHKK@Z`
- size: `154`
- prototype: `__int64 __fastcall(SSI_ELEMENT_LIST *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002dc0`

## callees

- `0x180001008`
- `0x180002c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c92`

## pseudocode

```c
__int64 __fastcall SSI_ELEMENT_LIST::AppendByteRange(SSI_ELEMENT_LIST *this, int a2, int a3)
{
  char *v6; // rax
  SSI_ELEMENT_LIST **v7; // rdx
  SSI_ELEMENT_LIST *v8; // rax

  v6 = (char *)operator new(0x30u);
  if ( v6 )
  {
    *((_DWORD *)v6 + 2) = 9;
    *((_QWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 4) = 0;
    *(_DWORD *)v6 = 541672787;
    *((_DWORD *)v6 + 1) = 6;
    *((_DWORD *)v6 + 6) = a2;
    *((_DWORD *)v6 + 7) = a3;
    v7 = (SSI_ELEMENT_LIST **)*((_QWORD *)this + 2);
    if ( *v7 != (SSI_ELEMENT_LIST *)((char *)this + 8) )
      __fastfail(3u);
    v8 = (SSI_ELEMENT_LIST *)(v6 + 32);
    *((_QWORD *)v8 + 1) = v7;
    *(_QWORD *)v8 = (char *)this + 8;
    *v7 = v8;
    *((_QWORD *)this + 2) = v8;
    return 1;
  }
  else
  {
    SetLastError(8u);
    return 0;
  }
}

```

## disassembly

```asm
0x180002c10  mov     [rsp+arg_0], rbx
0x180002c15  mov     [rsp+arg_8], rsi
0x180002c1a  push    rdi
0x180002c1b  sub     rsp, 20h
0x180002c1f  mov     rsi, rcx
0x180002c22  mov     ebx, r8d
0x180002c25  mov     ecx, 30h ; '0'; Size
0x180002c2a  mov     edi, edx
0x180002c2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002c31  test    rax, rax
0x180002c34  jz      short loc_180002C8D
0x180002c36  mov     dword ptr [rax+8], 9
0x180002c3d  lea     rcx, [rsi+8]
0x180002c41  mov     qword ptr [rax+10h], 0
0x180002c49  mov     qword ptr [rax+20h], 0
0x180002c51  mov     dword ptr [rax], 20494553h
0x180002c57  mov     dword ptr [rax+4], 6
0x180002c5e  mov     [rax+18h], edi
0x180002c61  mov     [rax+1Ch], ebx
0x180002c64  mov     rdx, [rcx+8]
0x180002c68  cmp     [rdx], rcx
0x180002c6b  jz      short loc_180002C74
0x180002c6d  mov     ecx, 3
0x180002c72  int     29h; Win8: RtlFailFast(ecx)
0x180002c74  add     rax, 20h ; ' '
0x180002c78  mov     [rax+8], rdx
0x180002c7c  mov     [rax], rcx
0x180002c7f  mov     [rdx], rax
0x180002c82  mov     [rcx+8], rax
0x180002c86  mov     eax, 1
0x180002c8b  jmp     short loc_180002C9A
0x180002c8d  mov     ecx, 8; dwErrCode
0x180002c92  call    cs:__imp_SetLastError
0x180002c98  xor     eax, eax
0x180002c9a  mov     rbx, [rsp+28h+arg_0]
0x180002c9f  mov     rsi, [rsp+28h+arg_8]
0x180002ca4  add     rsp, 20h
0x180002ca8  pop     rdi
0x180002ca9  retn
```
