# AslpFileGetPeExportNameAttribute

- ea: `0x14000e0c4`
- end: `0x14000e184`
- name: `AslpFileGetPeExportNameAttribute`
- size: `192`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000c630`

## callees

- `0x140007074`
- `0x140009c14`
- `0x14000bde8`
- `0x14000d704`
- `0x14000e0c4`

## string_xrefs

- `0x14000e133`: `AslStringXmlSanitize failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetPeExportNameAttribute(__int64 a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rax
  int v11; // [rsp+20h] [rbp-38h]
  __int64 v12; // [rsp+70h] [rbp+18h] BYREF

  v12 = 0;
  v4 = AslFileMappingEnsure(a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( *(_DWORD *)(a2 + 56) == 6 && (int)AslpFileGetExportName(&v12, a2) >= 0 )
    {
      v4 = AslStringXmlSanitize(v12);
      v5 = v4;
      if ( v4 < 0 )
      {
        v6 = "AslStringXmlSanitize failed [%x]";
        v7 = 3299;
        goto LABEL_3;
      }
      *(_DWORD *)(a1 + 736) = 4;
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(v8 + 2 * v9) );
      *(_DWORD *)(a1 + 760) |= 5u;
      *(_QWORD *)(a1 + 744) = v9;
      *(_QWORD *)(a1 + 752) = v8;
    }
    else
    {
      *(_DWORD *)(a1 + 760) |= 2u;
    }
    return 0;
  }
  v6 = "AslFileMappingEnsure failed [%x]";
  v7 = 3280;
LABEL_3:
  v11 = v4;
  AslLogCallPrintf(1, "AslpFileGetPeExportNameAttribute", v7, v6, v11);
  return v5;
}

```

## disassembly

```asm
0x14000e0c4  push    rbx
0x14000e0c6  push    rbp
0x14000e0c7  push    rsi
0x14000e0c8  push    rdi
0x14000e0c9  sub     rsp, 38h
0x14000e0cd  mov     rdi, rcx
0x14000e0d0  xor     ebp, ebp
0x14000e0d2  mov     rcx, rdx
0x14000e0d5  mov     [rsp+58h+arg_10], rbp
0x14000e0da  mov     rsi, rdx
0x14000e0dd  call    AslFileMappingEnsure
0x14000e0e2  mov     ebx, eax
0x14000e0e4  test    eax, eax
0x14000e0e6  jns     short loc_14000E10C
0x14000e0e8  lea     r9, aAslfilemapping_1; "AslFileMappingEnsure failed [%x]"
0x14000e0ef  mov     r8d, 0CD0h
0x14000e0f5  lea     rdx, aAslpfilegetpee; "AslpFileGetPeExportNameAttribute"
0x14000e0fc  mov     [rsp+58h+var_38], eax
0x14000e100  mov     ecx, 1
0x14000e105  call    AslLogCallPrintf
0x14000e10a  jmp     short loc_14000E179
0x14000e10c  cmp     dword ptr [rsi+38h], 6
0x14000e110  jnz     short loc_14000E170
0x14000e112  mov     rdx, rsi
0x14000e115  lea     rcx, [rsp+58h+arg_10]
0x14000e11a  call    AslpFileGetExportName
0x14000e11f  test    eax, eax
0x14000e121  js      short loc_14000E170
0x14000e123  mov     rcx, [rsp+58h+arg_10]
0x14000e128  call    AslStringXmlSanitize
0x14000e12d  mov     ebx, eax
0x14000e12f  test    eax, eax
0x14000e131  jns     short loc_14000E142
0x14000e133  lea     r9, aAslstringxmlsa; "AslStringXmlSanitize failed [%x]"
0x14000e13a  mov     r8d, 0CE3h
0x14000e140  jmp     short loc_14000E0F5
0x14000e142  mov     dword ptr [rdi+2E0h], 4
0x14000e14c  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000e150  inc     rax
0x14000e153  cmp     [rcx+rax*2], bp
0x14000e157  jnz     short loc_14000E150
0x14000e159  or      dword ptr [rdi+2F8h], 5
0x14000e160  mov     [rdi+2E8h], rax
0x14000e167  mov     [rdi+2F0h], rcx
0x14000e16e  jmp     short loc_14000E177
0x14000e170  or      dword ptr [rdi+2F8h], 2
0x14000e177  mov     ebx, ebp
0x14000e179  mov     eax, ebx
0x14000e17b  add     rsp, 38h
0x14000e17f  pop     rdi
0x14000e180  pop     rsi
0x14000e181  pop     rbp
0x14000e182  pop     rbx
0x14000e183  retn
```
