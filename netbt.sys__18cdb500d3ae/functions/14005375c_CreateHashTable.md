# CreateHashTable

- ea: `0x14005375c`
- end: `0x140053821`
- name: `CreateHashTable`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400533a4`

## callees

- `0x140040294`
- `0x14005375c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005379f`
- `ntoskrnl!ExAllocatePool2` at `0x14005379f`

## pseudocode

```c
__int64 __fastcall CreateHashTable(__int64 a1, int a2, int a3)
{
  unsigned __int64 v3; // r9
  __int64 Pool2; // rax
  unsigned int i; // edx
  __int64 v9; // rcx
  _QWORD *v10; // rcx

  v3 = 16LL * (unsigned int)(a2 - 1);
  if ( v3 > 0xFFFFFFFF || (int)v3 + 24 < (unsigned int)v3 )
    return 3221225621LL;
  Pool2 = ExAllocatePool2(64, (unsigned int)(v3 + 24), 825254478);
  *(_QWORD *)a1 = Pool2;
  if ( Pool2 )
  {
    for ( i = 0; (int)i < a2; *v10 = v10 )
    {
      v9 = 16LL * i++;
      v10 = (_QWORD *)(*(_QWORD *)a1 + 8LL + v9);
      v10[1] = v10;
    }
    *(_DWORD *)(*(_QWORD *)a1 + 4LL) = a3;
    **(_DWORD **)a1 = a2;
    return 0;
  }
  else
  {
    if ( (BYTE1(xmmword_140038420) & 8) != 0 )
      WPP_SF_(1035, 10, WPP_ea3294f46db239813d82e8111ee47aa3_Traceguids);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14005375c  mov     [rsp+arg_0], rbx
0x140053761  mov     [rsp+arg_8], rsi
0x140053766  push    rdi
0x140053767  sub     rsp, 20h
0x14005376b  lea     r9d, [rdx-1]
0x14005376f  mov     eax, 0FFFFFFFFh
0x140053774  shl     r9, 4
0x140053778  mov     esi, r8d
0x14005377b  mov     ebx, edx
0x14005377d  mov     rdi, rcx
0x140053780  cmp     r9, rax
0x140053783  ja      loc_14005380B
0x140053789  lea     eax, [r9+18h]
0x14005378d  cmp     eax, r9d
0x140053790  jb      short loc_14005380B
0x140053792  mov     edx, eax
0x140053794  mov     ecx, 40h ; '@'
0x140053799  mov     r8d, 3130624Eh
0x14005379f  call    cs:__imp_ExAllocatePool2
0x1400537a6  nop     dword ptr [rax+rax+00h]
0x1400537ab  mov     [rdi], rax
0x1400537ae  test    rax, rax
0x1400537b1  jz      short loc_1400537E5
0x1400537b3  xor     edx, edx
0x1400537b5  test    ebx, ebx
0x1400537b7  jle     short loc_1400537D6
0x1400537b9  mov     rax, [rdi]
0x1400537bc  mov     ecx, edx
0x1400537be  add     rax, 8
0x1400537c2  shl     rcx, 4
0x1400537c6  inc     edx
0x1400537c8  add     rcx, rax
0x1400537cb  mov     [rcx+8], rcx
0x1400537cf  mov     [rcx], rcx
0x1400537d2  cmp     edx, ebx
0x1400537d4  jl      short loc_1400537B9
0x1400537d6  mov     rax, [rdi]
0x1400537d9  mov     [rax+4], esi
0x1400537dc  mov     rax, [rdi]
0x1400537df  mov     [rax], ebx
0x1400537e1  xor     eax, eax
0x1400537e3  jmp     short loc_140053810
0x1400537e5  test    byte ptr cs:xmmword_140038420+1, 8
0x1400537ec  jz      short loc_140053804
0x1400537ee  mov     edx, 0Ah
0x1400537f3  lea     r8, WPP_ea3294f46db239813d82e8111ee47aa3_Traceguids
0x1400537fa  mov     ecx, 40Bh
0x1400537ff  call    WPP_SF_
0x140053804  mov     eax, 0C000009Ah
0x140053809  jmp     short loc_140053810
0x14005380b  mov     eax, 0C0000095h
0x140053810  mov     rbx, [rsp+28h+arg_0]
0x140053815  mov     rsi, [rsp+28h+arg_8]
0x14005381a  add     rsp, 20h
0x14005381e  pop     rdi
0x14005381f  retn
```
