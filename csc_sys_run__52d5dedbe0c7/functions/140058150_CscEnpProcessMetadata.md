# CscEnpProcessMetadata

- ea: `0x140058150`
- end: `0x1400581c2`
- name: `CscEnpProcessMetadata`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140058150`

## import_xrefs

- `ntoskrnl!RtlEqualString` at `0x140058182`
- `ntoskrnl!RtlEqualString` at `0x140058182`

## string_xrefs

- `0x14005816e`: `c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.Common`

## pseudocode

```c
__int64 __fastcall CscEnpProcessMetadata(const STRING *a1, __int64 a2, int a3)
{
  unsigned int v5; // ebx
  int v6; // ecx
  STRING v8; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)&v8.Length = 3145775;
  v8.Buffer = "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.Common";
  v5 = 0;
  if ( RtlEqualString(a1, &v8, 1u) )
  {
    if ( a3 == 152 )
    {
      v6 = *(_DWORD *)(a2 + 12);
      if ( (v6 & 0xE) != 0 )
        *(_DWORD *)(a2 + 12) = v6 & 0xFFFFFFF1;
    }
    else
    {
      return (unsigned int)-1073741575;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140058150  mov     r11, rsp
0x140058153  mov     [r11+8], rbx
0x140058157  mov     [r11+10h], rsi
0x14005815b  push    rdi
0x14005815c  sub     rsp, 30h
0x140058160  mov     esi, r8d
0x140058163  mov     qword ptr [r11-18h], 30002Fh
0x14005816b  mov     rdi, rdx
0x14005816e  lea     rax, aC8a05bc03fa849; "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Cs"...
0x140058175  mov     r8b, 1; CaseInSensitive
0x140058178  mov     [r11-10h], rax
0x14005817c  lea     rdx, [r11-18h]; String2
0x140058180  xor     ebx, ebx
0x140058182  call    cs:__imp_RtlEqualString
0x140058189  nop     dword ptr [rax+rax+00h]
0x14005818e  test    al, al
0x140058190  jz      short loc_1400581AF
0x140058192  cmp     esi, 98h
0x140058198  jz      short loc_1400581A1
0x14005819a  mov     ebx, 0C00000F9h
0x14005819f  jmp     short loc_1400581AF
0x1400581a1  mov     ecx, [rdi+0Ch]
0x1400581a4  test    cl, 0Eh
0x1400581a7  jz      short loc_1400581AF
0x1400581a9  and     ecx, 0FFFFFFF1h
0x1400581ac  mov     [rdi+0Ch], ecx
0x1400581af  mov     rsi, [rsp+38h+arg_8]
0x1400581b4  mov     eax, ebx
0x1400581b6  mov     rbx, [rsp+38h+arg_0]
0x1400581bb  add     rsp, 30h
0x1400581bf  pop     rdi
0x1400581c0  retn
```
