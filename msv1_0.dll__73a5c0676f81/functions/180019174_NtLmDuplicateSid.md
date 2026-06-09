# NtLmDuplicateSid

- ea: `0x180019174`
- end: `0x18001924d`
- name: `NtLmDuplicateSid`
- size: `217`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003e6a0`
- `0x18004a1c0`

## callees

- `0x180019174`
- `0x18002f014`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18001919f`
- `ntdll!RtlLengthSid` at `0x18001919f`

## pseudocode

```c
__int64 __fastcall NtLmDuplicateSid(_QWORD *a1, void *a2)
{
  size_t v4; // rsi
  void *v5; // rax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids);
  v4 = RtlLengthSid(a2);
  v5 = (void *)((__int64 (__fastcall *)(size_t))LsaFunctions->AllocatePrivateHeap)(v4);
  *a1 = v5;
  if ( v5 )
  {
    v6 = 0;
    memcpy_0(v5, a2, v4);
LABEL_10:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_11;
  }
  v6 = -1073741670;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids);
    goto LABEL_10;
  }
LABEL_11:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
    WPP_SF_(v7[2], 19, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids);
  return v6;
}

```

## disassembly

```asm
0x180019174  push    rbx
0x180019176  push    rbp
0x180019177  push    rsi
0x180019178  push    rdi
0x180019179  sub     rsp, 28h
0x18001917d  mov     rdi, rdx
0x180019180  mov     rbx, rcx
0x180019183  mov     rcx, cs:WPP_GLOBAL_Control
0x18001918a  lea     rbp, WPP_GLOBAL_Control
0x180019191  cmp     rcx, rbp
0x180019194  jz      short loc_18001919C
0x180019196  test    byte ptr [rcx+1Ch], 8
0x18001919a  jnz     short loc_1800191E0
0x18001919c  mov     rcx, rdi; Sid
0x18001919f  call    cs:__imp_RtlLengthSid
0x1800191a5  mov     esi, eax
0x1800191a7  mov     rax, cs:LsaFunctions
0x1800191ae  mov     ecx, esi
0x1800191b0  mov     rax, [rax+180h]
0x1800191b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191bc  mov     [rbx], rax
0x1800191bf  test    rax, rax
0x1800191c2  jnz     short loc_1800191F7
0x1800191c4  mov     ebx, 0C000009Ah
0x1800191c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800191d0  cmp     rcx, rbp
0x1800191d3  jnz     short loc_180019209
0x1800191d5  mov     eax, ebx
0x1800191d7  add     rsp, 28h
0x1800191db  pop     rdi
0x1800191dc  pop     rsi
0x1800191dd  pop     rbp
0x1800191de  pop     rbx
0x1800191df  retn
0x1800191e0  mov     rcx, [rcx+10h]
0x1800191e4  lea     r8, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids
0x1800191eb  mov     edx, 11h
0x1800191f0  call    WPP_SF_
0x1800191f5  jmp     short loc_18001919C
0x1800191f7  xor     ebx, ebx
0x1800191f9  mov     r8, rsi; Size
0x1800191fc  mov     rdx, rdi; Src
0x1800191ff  mov     rcx, rax; void *
0x180019202  call    memcpy_0
0x180019207  jmp     short loc_180019224
0x180019209  test    byte ptr [rcx+1Ch], 1
0x18001920d  jz      short loc_18001922B
0x18001920f  mov     rcx, [rcx+10h]
0x180019213  lea     r8, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids
0x18001921a  mov     edx, 12h
0x18001921f  call    WPP_SF_
0x180019224  mov     rcx, cs:WPP_GLOBAL_Control
0x18001922b  cmp     rcx, rbp
0x18001922e  jz      short loc_1800191D5
0x180019230  test    byte ptr [rcx+1Ch], 8
0x180019234  jz      short loc_1800191D5
0x180019236  mov     rcx, [rcx+10h]
0x18001923a  lea     r8, WPP_3dbeeb1430a035f1b5b7d3f02ecbb357_Traceguids
0x180019241  mov     edx, 13h
0x180019246  call    WPP_SF_
0x18001924b  jmp     short loc_1800191D5
```
