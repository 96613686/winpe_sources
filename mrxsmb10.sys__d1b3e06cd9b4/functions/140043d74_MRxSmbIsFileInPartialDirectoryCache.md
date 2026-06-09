# MRxSmbIsFileInPartialDirectoryCache

- ea: `0x140043d74`
- end: `0x140043f2a`
- name: `MRxSmbIsFileInPartialDirectoryCache`
- size: `438`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400439e0`
- `0x14004b1b0`
- `0x14004f5e0`

## callees

- `0x140016174`
- `0x140016ee0`
- `0x1400438ac`
- `0x140043d74`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140043daf`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140043daf`

## pseudocode

```c
char __fastcall MRxSmbIsFileInPartialDirectoryCache(__int64 a1, __int64 a2, _BYTE *a3, __int64 a4)
{
  __int64 v4; // rbp
  int v5; // r15d
  const void *v8; // r12
  WCHAR v9; // r10
  int v10; // ebx
  int v11; // r8d
  unsigned int *i; // rdi
  __int64 v14; // rax
  __int64 v15; // rax
  void *Buf1[2]; // [rsp+30h] [rbp-48h] BYREF

  v4 = *(_QWORD *)(a1 + 40);
  v5 = a2;
  *(_OWORD *)Buf1 = 0;
  MRxSmbCreateSuffix(a2, Buf1);
  v8 = Buf1[1];
  v9 = RtlUpcaseUnicodeChar(*(_WORD *)Buf1[1]);
  if ( (unsigned __int16)(v9 - 65) > 0x19u )
  {
    if ( (unsigned __int16)(v9 - 48) > 9u )
    {
      switch ( v9 )
      {
        case '$':
          v10 = 0x10000000;
          break;
        case '@':
          v10 = 0x20000000;
          break;
        case '_':
          v10 = 0x8000000;
          break;
        default:
          v10 = 0x4000000;
          if ( v9 != 126 )
            v10 = 0x80000000;
          break;
      }
    }
    else
    {
      v10 = 0x40000000;
    }
  }
  else
  {
    v10 = 1 << (v9 - 65);
  }
  v11 = *(_DWORD *)(v4 + 4);
  if ( (v11 & v10) != 0 )
  {
    *a3 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_ZDD(WPP_GLOBAL_Control->AttachedDevice, 26, v11, v5, v11, v10);
    return 0;
  }
  else
  {
    for ( i = (unsigned int *)(v4 + 4256);
          i[15] != LOWORD(Buf1[0]) || memcmp(v8, (char *)i + 94, LOWORD(Buf1[0]));
          i = (unsigned int *)((char *)i + v14) )
    {
      v14 = *i;
      if ( !(_DWORD)v14 )
        return 0;
    }
    if ( a4 )
    {
      v15 = *((_QWORD *)i + 1);
      if ( v15 )
      {
        *(_QWORD *)a4 = v15;
        *(_QWORD *)(a4 + 8) = *((_QWORD *)i + 2);
        *(_QWORD *)(a4 + 16) = *((_QWORD *)i + 3);
        *(_QWORD *)(a4 + 24) = *((_QWORD *)i + 4);
        *(_DWORD *)(a4 + 32) = i[14];
      }
      else
      {
        *a3 = 0;
      }
    }
    else
    {
      *((_QWORD *)i + 1) = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_ZDD(WPP_GLOBAL_Control->AttachedDevice, 27, *(_DWORD *)(v4 + 4), v5, *(_DWORD *)(v4 + 4), v10);
      }
    }
    return 1;
  }
}

```

## disassembly

```asm
0x140043d74  push    rbx
0x140043d76  push    rbp
0x140043d77  push    rsi
0x140043d78  push    rdi
0x140043d79  push    r12
0x140043d7b  push    r14
0x140043d7d  push    r15
0x140043d7f  sub     rsp, 40h
0x140043d83  mov     rbp, [rcx+28h]
0x140043d87  mov     r15, rdx
0x140043d8a  xorps   xmm0, xmm0
0x140043d8d  lea     rdx, [rsp+78h+Buf1]
0x140043d92  mov     rcx, r15
0x140043d95  mov     rsi, r9
0x140043d98  mov     r14, r8
0x140043d9b  movups  xmmword ptr [rsp+78h+Buf1], xmm0
0x140043da0  call    MRxSmbCreateSuffix
0x140043da5  mov     r12, [rsp+78h+Buf1+8]
0x140043daa  movzx   ecx, word ptr [r12]; SourceCharacter
0x140043daf  call    cs:__imp_RtlUpcaseUnicodeChar
0x140043db6  nop     dword ptr [rax+rax+00h]
0x140043dbb  movzx   r10d, ax
0x140043dbf  lea     ecx, [r10-41h]
0x140043dc3  cmp     cx, 19h
0x140043dc7  ja      short loc_140043DD6
0x140043dc9  lea     ecx, [r10-41h]
0x140043dcd  mov     ebx, 1
0x140043dd2  shl     ebx, cl
0x140043dd4  jmp     short loc_140043E23
0x140043dd6  lea     eax, [r10-30h]
0x140043dda  cmp     ax, 9
0x140043dde  ja      short loc_140043DE7
0x140043de0  mov     ebx, 40000000h
0x140043de5  jmp     short loc_140043E23
0x140043de7  cmp     r10w, 24h ; '$'
0x140043dec  jz      short loc_140043E1E
0x140043dee  cmp     r10w, 40h ; '@'
0x140043df3  jz      short loc_140043E17
0x140043df5  cmp     r10w, 5Fh ; '_'
0x140043dfa  jz      short loc_140043E10
0x140043dfc  cmp     r10w, 7Eh ; '~'
0x140043e01  mov     ebx, 4000000h
0x140043e06  mov     eax, 80000000h
0x140043e0b  cmovnz  ebx, eax
0x140043e0e  jmp     short loc_140043E23
0x140043e10  mov     ebx, 8000000h
0x140043e15  jmp     short loc_140043E23
0x140043e17  mov     ebx, 20000000h
0x140043e1c  jmp     short loc_140043E23
0x140043e1e  mov     ebx, 10000000h
0x140043e23  mov     r8d, [rbp+4]
0x140043e27  test    ebx, r8d
0x140043e2a  jz      short loc_140043E78
0x140043e2c  mov     byte ptr [r14], 0
0x140043e30  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140043e37  lea     rax, WPP_GLOBAL_Control
0x140043e3e  cmp     rcx, rax
0x140043e41  jz      short loc_140043E66
0x140043e43  test    dword ptr [rcx+2Ch], 200h
0x140043e4a  jz      short loc_140043E66
0x140043e4c  mov     rcx, [rcx+18h]
0x140043e50  mov     edx, 1Ah
0x140043e55  mov     [rsp+78h+var_50], ebx
0x140043e59  mov     r9, r15
0x140043e5c  mov     [rsp+78h+var_58], r8d
0x140043e61  call    WPP_SF_ZDD
0x140043e66  xor     al, al
0x140043e68  add     rsp, 40h
0x140043e6c  pop     r15
0x140043e6e  pop     r14
0x140043e70  pop     r12
0x140043e72  pop     rdi
0x140043e73  pop     rsi
0x140043e74  pop     rbp
0x140043e75  pop     rbx
0x140043e76  retn
0x140043e78  lea     rdi, [rbp+10A0h]
0x140043e7f  movzx   eax, word ptr [rsp+78h+Buf1]
0x140043e84  cmp     [rdi+3Ch], eax
0x140043e87  jnz     short loc_140043E9F
0x140043e89  movzx   r8d, word ptr [rsp+78h+Buf1]; Size
0x140043e8f  lea     rdx, [rdi+5Eh]; Buf2
0x140043e93  mov     rcx, r12; Buf1
0x140043e96  call    memcmp
0x140043e9b  test    eax, eax
0x140043e9d  jz      short loc_140043EAA
0x140043e9f  mov     eax, [rdi]
0x140043ea1  test    eax, eax
0x140043ea3  jz      short loc_140043E66
0x140043ea5  add     rdi, rax
0x140043ea8  jmp     short loc_140043E7F
0x140043eaa  test    rsi, rsi
0x140043ead  jz      short loc_140043EE1
0x140043eaf  mov     rax, [rdi+8]
0x140043eb3  test    rax, rax
0x140043eb6  jz      short loc_140043EDB
0x140043eb8  mov     [rsi], rax
0x140043ebb  mov     rax, [rdi+10h]
0x140043ebf  mov     [rsi+8], rax
0x140043ec3  mov     rax, [rdi+18h]
0x140043ec7  mov     [rsi+10h], rax
0x140043ecb  mov     rax, [rdi+20h]
0x140043ecf  mov     [rsi+18h], rax
0x140043ed3  mov     eax, [rdi+38h]
0x140043ed6  mov     [rsi+20h], eax
0x140043ed9  jmp     short loc_140043F23
0x140043edb  mov     byte ptr [r14], 0
0x140043edf  jmp     short loc_140043F23
0x140043ee1  mov     qword ptr [rdi+8], 0
0x140043ee9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140043ef0  lea     rax, WPP_GLOBAL_Control
0x140043ef7  cmp     rcx, rax
0x140043efa  jz      short loc_140043F23
0x140043efc  test    dword ptr [rcx+2Ch], 200h
0x140043f03  jz      short loc_140043F23
0x140043f05  mov     r8d, [rbp+4]
0x140043f09  mov     edx, 1Bh
0x140043f0e  mov     rcx, [rcx+18h]
0x140043f12  mov     r9, r15
0x140043f15  mov     [rsp+78h+var_50], ebx
0x140043f19  mov     [rsp+78h+var_58], r8d
0x140043f1e  call    WPP_SF_ZDD
0x140043f23  mov     al, 1
0x140043f25  jmp     loc_140043E68
```
