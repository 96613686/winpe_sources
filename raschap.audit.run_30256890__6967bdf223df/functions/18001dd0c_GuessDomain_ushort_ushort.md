# GuessDomain(ushort *,ushort * *)

- ea: `0x18001dd0c`
- end: `0x18001dda7`
- name: `?GuessDomain@@YAKPEAGPEAPEAG@Z`
- size: `155`
- prototype: `unsigned int __fastcall(PCNZWCH lpString1, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001e120`

## callees

- `0x18001da68`
- `0x18001dbfc`
- `0x18001dc64`
- `0x18001dd0c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dd66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dd66`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001dd5b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001dd5b`

## pseudocode

```c
__int64 __fastcall GuessDomain(PCNZWCH lpString1, unsigned __int16 **a2)
{
  WCHAR *v4; // rdi
  int v5; // ebx
  __int64 result; // rax
  unsigned __int16 *v7; // [rsp+50h] [rbp+18h] BYREF
  PCNZWCH lpString2; // [rsp+58h] [rbp+20h] BYREF

  v7 = 0;
  lpString2 = 0;
  if ( (unsigned int)GetBuiltInAdministrator((unsigned __int16 **)&lpString2)
    || (v4 = (WCHAR *)lpString2, v5 = CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, -1), LocalFree(v4), v5 != 2) )
  {
    LODWORD(result) = GetDefaultDomain(&v7);
  }
  else
  {
    LODWORD(result) = GetMachineName(&v7);
  }
  if ( !(_DWORD)result )
    *a2 = v7;
  return (unsigned int)result;
}

```

## disassembly

```asm
0x18001dd0c  mov     rax, rsp
0x18001dd0f  mov     [rax+8], rbx
0x18001dd13  mov     [rax+10h], rsi
0x18001dd17  push    rdi
0x18001dd18  sub     rsp, 30h
0x18001dd1c  mov     rbx, rcx
0x18001dd1f  mov     qword ptr [rax+18h], 0
0x18001dd27  lea     rcx, [rax+20h]; unsigned __int16 **
0x18001dd2b  mov     qword ptr [rax+20h], 0
0x18001dd33  mov     rsi, rdx
0x18001dd36  call    ?GetBuiltInAdministrator@@YAKPEAPEAG@Z; GetBuiltInAdministrator(ushort * *)
0x18001dd3b  test    eax, eax
0x18001dd3d  jnz     short loc_18001DD7D
0x18001dd3f  mov     rdi, [rsp+38h+arg_18]
0x18001dd44  lea     edx, [rax+1]; dwCmpFlags
0x18001dd47  or      r9d, 0FFFFFFFFh; cchCount1
0x18001dd4b  lea     ecx, [rax+7Fh]; Locale
0x18001dd4e  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x18001dd53  mov     r8, rbx; lpString1
0x18001dd56  mov     [rsp+38h+lpString2], rdi; lpString2
0x18001dd5b  call    cs:__imp_CompareStringW
0x18001dd61  mov     rcx, rdi; hMem
0x18001dd64  mov     ebx, eax
0x18001dd66  call    cs:__imp_LocalFree
0x18001dd6c  lea     rcx, [rsp+38h+arg_10]; unsigned __int16 **
0x18001dd71  cmp     ebx, 2
0x18001dd74  jnz     short loc_18001DD82
0x18001dd76  call    ?GetMachineName@@YAKPEAPEAG@Z; GetMachineName(ushort * *)
0x18001dd7b  jmp     short loc_18001DD87
0x18001dd7d  lea     rcx, [rsp+38h+arg_10]; unsigned __int16 **
0x18001dd82  call    ?GetDefaultDomain@@YAKPEAPEAG@Z; GetDefaultDomain(ushort * *)
0x18001dd87  mov     ecx, eax
0x18001dd89  test    eax, eax
0x18001dd8b  jnz     short loc_18001DD95
0x18001dd8d  mov     rax, [rsp+38h+arg_10]
0x18001dd92  mov     [rsi], rax
0x18001dd95  mov     rbx, [rsp+38h+arg_0]
0x18001dd9a  mov     eax, ecx
0x18001dd9c  mov     rsi, [rsp+38h+arg_8]
0x18001dda1  add     rsp, 30h
0x18001dda5  pop     rdi
0x18001dda6  retn
```
