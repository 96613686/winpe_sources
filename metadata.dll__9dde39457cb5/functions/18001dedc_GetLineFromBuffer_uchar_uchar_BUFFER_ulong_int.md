# GetLineFromBuffer(uchar * &,uchar * &,BUFFER *,ulong &,int &)

- ea: `0x18001dedc`
- end: `0x18001e0b5`
- name: `?GetLineFromBuffer@@YAKAEAPEAE0PEAVBUFFER@@AEAKAEAH@Z`
- size: `473`
- prototype: `unsigned int __fastcall(unsigned __int8 **, unsigned __int8 **, struct BUFFER *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e290`

## callees

- `0x18001dedc`

## import_xrefs

- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001dfbf`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001dfbf`
- `IisRTL!PuDbgPrint` at `0x18001df44`
- `IisRTL!PuDbgPrint` at `0x18001e095`
- `IisRTL!PuDbgPrint` at `0x18001df44`
- `IisRTL!PuDbgPrint` at `0x18001e095`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001dfdf`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001e045`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001dfdf`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001e045`

## string_xrefs

- `0x18001df35`: `Entering GeLineFromBuffer, pbrNextPtr = %p, pbrEndReadData = %p\n`
- `0x18001e061`: `Leaving GeLineFromBuffer, pbrNextPter = %p, pbrEndReadData = %p\n`

## pseudocode

```c
__int64 __fastcall GetLineFromBuffer(
        unsigned __int8 **a1,
        unsigned __int8 **a2,
        struct BUFFER *a3,
        unsigned int *a4,
        int *a5)
{
  unsigned __int8 *v6; // rdi
  BUFFER *v7; // r9
  unsigned int v10; // esi
  unsigned __int64 v11; // r8
  unsigned __int8 *v12; // rcx
  unsigned __int8 *v13; // rax
  BOOL v14; // edx
  unsigned __int64 v15; // r8
  unsigned __int8 *v16; // rbp
  __int64 v17; // rbx
  _BYTE *v18; // rbx
  bool v19; // zf
  char v20; // al
  unsigned int Ptr; // eax

  v6 = *a1;
  v7 = a3;
  v10 = 38;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      1574,
      "GetLineFromBuffer",
      "Entering GeLineFromBuffer, pbrNextPtr = %p, pbrEndReadData = %p\n",
      v6,
      *a2);
    v7 = a3;
  }
  v11 = (unsigned __int64)*a2;
  v12 = *a1;
  if ( *a1 != *a2 )
  {
    v10 = 0;
    v13 = *a1;
    v14 = 0;
    if ( v11 > (unsigned __int64)v12 && *a5 )
    {
      v13 = v12 + 1;
      LOBYTE(v14) = *v12 == 0xFD;
    }
    v15 = v11 - 1;
    while ( v15 > (unsigned __int64)v13 && !v14 )
    {
      if ( *v13 == 0xFE )
        v14 = *++v13 == 0xFD;
      ++v13;
    }
    v16 = v13 + 1;
    if ( v14 )
      v16 = v13;
    if ( !BUFFER::Resize(v7, *a4 + (_DWORD)v16 - *(_DWORD *)a1) )
    {
      v10 = 8;
      goto LABEL_31;
    }
    v17 = *a4;
    v18 = (char *)BUFFER::QueryPtr(a3) + v17;
    if ( !*a5 )
      goto LABEL_20;
    v19 = *v6 == 0xFE;
    *a5 = 0;
    if ( v19 )
    {
      ++v6;
      *v18++ = -2;
      while ( 1 )
      {
LABEL_20:
        v10 = 38;
        if ( v6 >= v16 )
          goto LABEL_30;
        v20 = *v6++;
        if ( v20 != -2 )
          break;
        if ( v6 == v16 )
        {
          *a5 = 1;
        }
        else
        {
          if ( *v6 != 0xFE )
          {
            ++v6;
            v10 = 0;
            goto LABEL_30;
          }
          ++v6;
          *v18 = -2;
LABEL_28:
          ++v18;
        }
      }
      *v18 = v20;
      goto LABEL_28;
    }
    ++v6;
LABEL_30:
    Ptr = (unsigned int)BUFFER::QueryPtr(a3);
    *a1 = v6;
    *a4 = (_DWORD)v18 - Ptr;
  }
LABEL_31:
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      1632,
      "GetLineFromBuffer",
      "Leaving GeLineFromBuffer, pbrNextPter = %p, pbrEndReadData = %p\n",
      *a1,
      *a2);
  return v10;
}

```

## disassembly

```asm
0x18001dedc  mov     r11, rsp
0x18001dedf  mov     [r11+10h], rbx
0x18001dee3  mov     [r11+18h], r8
0x18001dee7  push    rbp
0x18001dee8  push    rsi
0x18001dee9  push    rdi
0x18001deea  push    r12
0x18001deec  push    r13
0x18001deee  push    r14
0x18001def0  push    r15
0x18001def2  sub     rsp, 40h
0x18001def6  test    byte ptr cs:g_dwDebugFlags, 3
0x18001defd  mov     r13, r9
0x18001df00  mov     rdi, [rcx]
0x18001df03  mov     r9, r8
0x18001df06  mov     r12, rdx
0x18001df09  mov     r14, rcx
0x18001df0c  mov     esi, 26h ; '&'
0x18001df11  jz      short loc_18001DF52
0x18001df13  mov     rax, [rdx]
0x18001df16  lea     r9, aGetlinefrombuf; "GetLineFromBuffer"
0x18001df1d  mov     rcx, cs:g_pDebug
0x18001df24  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001df2b  mov     [r11-48h], rax
0x18001df2f  mov     r8d, 626h
0x18001df35  lea     rax, aEnteringGeline; "Entering GeLineFromBuffer, pbrNextPtr ="...
0x18001df3c  mov     [r11-50h], rdi
0x18001df40  mov     [r11-58h], rax
0x18001df44  call    cs:__imp_PuDbgPrint
0x18001df4a  mov     r9, [rsp+78h+arg_10]
0x18001df52  mov     r8, [r12]
0x18001df56  mov     rcx, [r14]
0x18001df59  cmp     rcx, r8
0x18001df5c  jz      loc_18001E054
0x18001df62  mov     r15, [rsp+78h+arg_20]
0x18001df6a  xor     esi, esi
0x18001df6c  mov     rax, rcx
0x18001df6f  mov     edx, esi
0x18001df71  cmp     r8, rcx
0x18001df74  jbe     short loc_18001DF85
0x18001df76  cmp     [r15], esi
0x18001df79  jz      short loc_18001DF85
0x18001df7b  cmp     byte ptr [rcx], 0FDh
0x18001df7e  lea     rax, [rcx+1]
0x18001df82  setz    dl
0x18001df85  dec     r8
0x18001df88  mov     ecx, 1
0x18001df8d  jmp     short loc_18001DFA4
0x18001df8f  test    edx, edx
0x18001df91  jnz     short loc_18001DFA9
0x18001df93  cmp     byte ptr [rax], 0FEh
0x18001df96  jnz     short loc_18001DFA1
0x18001df98  add     rax, rcx
0x18001df9b  cmp     byte ptr [rax], 0FDh
0x18001df9e  cmovz   edx, ecx
0x18001dfa1  add     rax, rcx
0x18001dfa4  cmp     r8, rax
0x18001dfa7  ja      short loc_18001DF8F
0x18001dfa9  test    edx, edx
0x18001dfab  lea     rbp, [rax+1]
0x18001dfaf  mov     rcx, r9
0x18001dfb2  cmovnz  rbp, rax
0x18001dfb6  mov     edx, ebp
0x18001dfb8  sub     edx, [r14]
0x18001dfbb  add     edx, [r13+0]
0x18001dfbf  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18001dfc5  test    al, al
0x18001dfc7  jnz     short loc_18001DFD3
0x18001dfc9  mov     esi, 8
0x18001dfce  jmp     loc_18001E054
0x18001dfd3  mov     rcx, [rsp+78h+arg_10]
0x18001dfdb  mov     ebx, [r13+0]
0x18001dfdf  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001dfe5  add     rbx, rax
0x18001dfe8  cmp     [r15], esi
0x18001dfeb  jz      short loc_18001DFFE
0x18001dfed  cmp     byte ptr [rdi], 0FEh
0x18001dff0  mov     [r15], esi
0x18001dff3  jnz     short loc_18001E015
0x18001dff5  inc     rdi
0x18001dff8  mov     byte ptr [rbx], 0FEh
0x18001dffb  inc     rbx
0x18001dffe  mov     esi, 26h ; '&'
0x18001e003  cmp     rdi, rbp
0x18001e006  jnb     short loc_18001E03D
0x18001e008  mov     al, [rdi]
0x18001e00a  inc     rdi
0x18001e00d  cmp     al, 0FEh
0x18001e00f  jz      short loc_18001E01A
0x18001e011  mov     [rbx], al
0x18001e013  jmp     short loc_18001E033
0x18001e015  inc     rdi
0x18001e018  jmp     short loc_18001E03D
0x18001e01a  cmp     rdi, rbp
0x18001e01d  jnz     short loc_18001E028
0x18001e01f  mov     dword ptr [r15], 1
0x18001e026  jmp     short loc_18001DFFE
0x18001e028  cmp     byte ptr [rdi], 0FEh
0x18001e02b  jnz     short loc_18001E038
0x18001e02d  inc     rdi
0x18001e030  mov     byte ptr [rbx], 0FEh
0x18001e033  inc     rbx
0x18001e036  jmp     short loc_18001DFFE
0x18001e038  inc     rdi
0x18001e03b  xor     esi, esi
0x18001e03d  mov     rcx, [rsp+78h+arg_10]
0x18001e045  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001e04b  sub     ebx, eax
0x18001e04d  mov     [r14], rdi
0x18001e050  mov     [r13+0], ebx
0x18001e054  test    byte ptr cs:g_dwDebugFlags, 3
0x18001e05b  jz      short loc_18001E09B
0x18001e05d  mov     rcx, [r12]
0x18001e061  lea     rax, aLeavingGelinef; "Leaving GeLineFromBuffer, pbrNextPter ="...
0x18001e068  mov     [rsp+78h+var_48], rcx
0x18001e06d  lea     r9, aGetlinefrombuf; "GetLineFromBuffer"
0x18001e074  mov     rcx, [r14]
0x18001e077  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001e07e  mov     [rsp+78h+var_50], rcx
0x18001e083  mov     r8d, 660h
0x18001e089  mov     rcx, cs:g_pDebug
0x18001e090  mov     [rsp+78h+var_58], rax
0x18001e095  call    cs:__imp_PuDbgPrint
0x18001e09b  mov     rbx, [rsp+78h+arg_8]
0x18001e0a3  mov     eax, esi
0x18001e0a5  add     rsp, 40h
0x18001e0a9  pop     r15
0x18001e0ab  pop     r14
0x18001e0ad  pop     r13
0x18001e0af  pop     r12
0x18001e0b1  pop     rdi
0x18001e0b2  pop     rsi
0x18001e0b3  pop     rbp
0x18001e0b4  retn
```
