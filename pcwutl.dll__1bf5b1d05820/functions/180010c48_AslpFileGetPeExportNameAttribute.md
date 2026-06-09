# AslpFileGetPeExportNameAttribute

- ea: `0x180010c48`
- end: `0x180010d08`
- name: `AslpFileGetPeExportNameAttribute`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000d258`

## callees

- `0x18000dcf4`
- `0x18000e240`
- `0x18000f334`
- `0x180010288`
- `0x180010c48`

## string_xrefs

- `0x180010cb7`: `AslStringXmlSanitize failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetPeExportNameAttribute(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rax
  int v13; // [rsp+20h] [rbp-38h]
  __int64 v14; // [rsp+70h] [rbp+18h] BYREF

  v14 = 0;
  v6 = AslFileMappingEnsure(a2, a2, a3, a4);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( *(_DWORD *)(a2 + 56) == 6 && (int)AslpFileGetExportName(&v14, a2) >= 0 )
    {
      v6 = AslStringXmlSanitize(v14);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = "AslStringXmlSanitize failed [%x]";
        v9 = 3299;
        goto LABEL_3;
      }
      *(_DWORD *)(a1 + 736) = 4;
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(v10 + 2 * v11) );
      *(_DWORD *)(a1 + 760) |= 5u;
      *(_QWORD *)(a1 + 744) = v11;
      *(_QWORD *)(a1 + 752) = v10;
    }
    else
    {
      *(_DWORD *)(a1 + 760) |= 2u;
    }
    return 0;
  }
  v8 = "AslFileMappingEnsure failed [%x]";
  v9 = 3280;
LABEL_3:
  v13 = v6;
  AslLogCallPrintf(1, "AslpFileGetPeExportNameAttribute", v9, v8, v13);
  return v7;
}

```

## disassembly

```asm
0x180010c48  push    rbx
0x180010c4a  push    rbp
0x180010c4b  push    rsi
0x180010c4c  push    rdi
0x180010c4d  sub     rsp, 38h
0x180010c51  mov     rdi, rcx
0x180010c54  xor     ebp, ebp
0x180010c56  mov     rcx, rdx
0x180010c59  mov     [rsp+58h+arg_10], rbp
0x180010c5e  mov     rsi, rdx
0x180010c61  call    AslFileMappingEnsure
0x180010c66  mov     ebx, eax
0x180010c68  test    eax, eax
0x180010c6a  jns     short loc_180010C90
0x180010c6c  lea     r9, aAslfilemapping_2; "AslFileMappingEnsure failed [%x]"
0x180010c73  mov     r8d, 0CD0h
0x180010c79  lea     rdx, aAslpfilegetpee; "AslpFileGetPeExportNameAttribute"
0x180010c80  mov     [rsp+58h+var_38], eax
0x180010c84  mov     ecx, 1
0x180010c89  call    AslLogCallPrintf
0x180010c8e  jmp     short loc_180010CFD
0x180010c90  cmp     dword ptr [rsi+38h], 6
0x180010c94  jnz     short loc_180010CF4
0x180010c96  mov     rdx, rsi
0x180010c99  lea     rcx, [rsp+58h+arg_10]
0x180010c9e  call    AslpFileGetExportName
0x180010ca3  test    eax, eax
0x180010ca5  js      short loc_180010CF4
0x180010ca7  mov     rcx, [rsp+58h+arg_10]
0x180010cac  call    AslStringXmlSanitize
0x180010cb1  mov     ebx, eax
0x180010cb3  test    eax, eax
0x180010cb5  jns     short loc_180010CC6
0x180010cb7  lea     r9, aAslstringxmlsa; "AslStringXmlSanitize failed [%x]"
0x180010cbe  mov     r8d, 0CE3h
0x180010cc4  jmp     short loc_180010C79
0x180010cc6  mov     dword ptr [rdi+2E0h], 4
0x180010cd0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010cd4  inc     rax
0x180010cd7  cmp     [rcx+rax*2], bp
0x180010cdb  jnz     short loc_180010CD4
0x180010cdd  or      dword ptr [rdi+2F8h], 5
0x180010ce4  mov     [rdi+2E8h], rax
0x180010ceb  mov     [rdi+2F0h], rcx
0x180010cf2  jmp     short loc_180010CFB
0x180010cf4  or      dword ptr [rdi+2F8h], 2
0x180010cfb  mov     ebx, ebp
0x180010cfd  mov     eax, ebx
0x180010cff  add     rsp, 38h
0x180010d03  pop     rdi
0x180010d04  pop     rsi
0x180010d05  pop     rbp
0x180010d06  pop     rbx
0x180010d07  retn
```
