# HsmpDbgBreakOnOpen

- ea: `0x140007bb0`
- end: `0x140007d55`
- name: `HsmpDbgBreakOnOpen`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14005aaf0`

## callees

- `0x140007bb0`
- `0x140008c44`
- `0x14000ddc8`
- `0x140042e60`
- `0x14005c600`
- `0x14005ccb0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140007d21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007d39`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007d21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007d39`
- `ntoskrnl!ExAllocatePool2` at `0x140007c93`
- `ntoskrnl!ExAllocatePool2` at `0x140007c93`

## string_xrefs

- `0x140007d09`: `BreakOnOpen`

## pseudocode

```c
__int64 __fastcall HsmpDbgBreakOnOpen(__int64 a1, _BYTE *a2, struct _FLT_CALLBACK_DATA *a3)
{
  int v4; // edi
  int v5; // edx
  int v6; // ecx
  PVOID v8; // rcx
  WCHAR *Pool2; // rsi
  __int64 v10; // rax
  _WORD *v11; // rdx
  int i; // ecx
  __int128 v13; // [rsp+30h] [rbp-28h] BYREF
  __int64 v14; // [rsp+40h] [rbp-18h]
  int v15; // [rsp+68h] [rbp+10h] BYREF
  PVOID P; // [rsp+78h] [rbp+20h] BYREF

  v4 = 0;
  v14 = 0;
  if ( (dword_140028E50 & 0x20) != 0 )
    v4 = dword_140029088;
  v13 = 0;
  if ( (dword_140028E50 & 1) != 0 )
  {
    HsmpFillOutAttributionInformation(a1, *(_QWORD *)(a1 + 16), a3, (__int64)&v13);
    v15 = v4;
    P = 0;
    if ( (int)HsmOsLocateProcessImageName(&v13, &P) >= 0 )
    {
      v8 = P;
      if ( !P )
        goto LABEL_4;
      if ( !*((_QWORD *)P + 1) || !*(_WORD *)P )
        goto LABEL_27;
      Pool2 = (WCHAR *)ExAllocatePool2(64, 256, 1649701704);
      if ( Pool2 )
      {
        v10 = *(unsigned __int16 *)P;
        v11 = (_WORD *)(*((_QWORD *)P + 1) + v10 - 2);
        for ( i = *(unsigned __int16 *)P; i > 0; i -= 2 )
        {
          if ( *v11 == 92 )
          {
            if ( i == (_DWORD)v10 )
              goto LABEL_25;
            ++v11;
            break;
          }
          --v11;
        }
        if ( v11 && RtlStringCchPrintfW(Pool2, 0x80u, L"%s\\%s", &_DEBUG, v11) >= 0 )
        {
          HsmpGetRegDword(Pool2, L"BreakOnOpen", &v15);
          v4 = v15;
        }
LABEL_25:
        ExFreePoolWithTag(Pool2, 0x62547348u);
      }
    }
    v8 = P;
LABEL_27:
    if ( v8 )
      ExFreePoolWithTag(v8, 0);
  }
LABEL_4:
  v5 = (a2[74] != 0) | 2;
  if ( !a2[75] )
    v5 = a2[74] != 0;
  v6 = v5 | 4;
  if ( !a2[76] )
    v6 = v5;
  if ( (v6 & v4) != 0 )
    __debugbreak();
  return HsmpCleanupAttributionInformation(&v13);
}

```

## disassembly

```asm
0x140007bb0  sub     rsp, 58h
0x140007bb4  xor     eax, eax
0x140007bb6  mov     [rsp+58h+arg_0], rbx
0x140007bbb  mov     [rsp+58h+var_8], rdi
0x140007bc0  mov     rbx, rdx
0x140007bc3  mov     edx, cs:dword_140028E50
0x140007bc9  xor     edi, edi
0x140007bcb  test    dl, 20h
0x140007bce  mov     [rsp+58h+var_18], rax
0x140007bd3  xorps   xmm0, xmm0
0x140007bd6  cmovnz  edi, cs:dword_140029088
0x140007bdd  movups  [rsp+58h+var_28], xmm0
0x140007be2  test    dl, 1
0x140007be5  jnz     short loc_140007C29
0x140007be7  xor     ecx, ecx
0x140007be9  cmp     [rbx+4Ah], cl
0x140007bec  setnz   cl
0x140007bef  mov     edx, ecx
0x140007bf1  or      edx, 2
0x140007bf4  cmp     byte ptr [rbx+4Bh], 0
0x140007bf8  cmovz   edx, ecx
0x140007bfb  mov     ecx, edx
0x140007bfd  or      ecx, 4
0x140007c00  cmp     byte ptr [rbx+4Ch], 0
0x140007c04  mov     rbx, [rsp+58h+arg_0]
0x140007c09  cmovz   ecx, edx
0x140007c0c  test    edi, ecx
0x140007c0e  mov     rdi, [rsp+58h+var_8]
0x140007c13  jnz     loc_140007D4F
0x140007c19  lea     rcx, [rsp+58h+var_28]; P
0x140007c1e  call    HsmpCleanupAttributionInformation
0x140007c23  add     rsp, 58h
0x140007c27  retn
0x140007c29  mov     rdx, [rcx+10h]
0x140007c2d  lea     r9, [rsp+58h+var_28]
0x140007c32  mov     [rsp+58h+arg_10], rsi
0x140007c37  call    HsmpFillOutAttributionInformation
0x140007c3c  lea     rdx, [rsp+58h+P]
0x140007c41  mov     [rsp+58h+arg_8], edi
0x140007c45  lea     rcx, [rsp+58h+var_28]
0x140007c4a  mov     [rsp+58h+P], 0
0x140007c53  call    HsmOsLocateProcessImageName
0x140007c58  test    eax, eax
0x140007c5a  js      loc_140007D2D
0x140007c60  mov     rcx, [rsp+58h+P]
0x140007c65  test    rcx, rcx
0x140007c68  jz      loc_140007D45
0x140007c6e  cmp     qword ptr [rcx+8], 0
0x140007c73  jz      loc_140007D32
0x140007c79  cmp     word ptr [rcx], 0
0x140007c7d  jz      loc_140007D32
0x140007c83  mov     edx, 100h
0x140007c88  mov     ecx, 40h ; '@'
0x140007c8d  mov     r8d, 62547348h
0x140007c93  call    cs:__imp_ExAllocatePool2
0x140007c9a  nop     dword ptr [rax+rax+00h]
0x140007c9f  mov     rsi, rax
0x140007ca2  test    rax, rax
0x140007ca5  jz      loc_140007D2D
0x140007cab  mov     rcx, [rsp+58h+P]
0x140007cb0  movzx   eax, word ptr [rcx]
0x140007cb3  lea     rdx, [rax-2]
0x140007cb7  add     rdx, [rcx+8]
0x140007cbb  mov     ecx, eax
0x140007cbd  test    ecx, ecx
0x140007cbf  jle     short loc_140007CD8
0x140007cc1  cmp     word ptr [rdx], 5Ch ; '\'
0x140007cc5  jz      short loc_140007CD0
0x140007cc7  sub     rdx, 2
0x140007ccb  sub     ecx, 2
0x140007cce  jmp     short loc_140007CBD
0x140007cd0  cmp     ecx, eax
0x140007cd2  jz      short loc_140007D19
0x140007cd4  add     rdx, 2
0x140007cd8  test    rdx, rdx
0x140007cdb  jz      short loc_140007D19
0x140007cdd  mov     [rsp+58h+var_38], rdx
0x140007ce2  lea     r9, __DEBUG
0x140007ce9  mov     edx, 80h; cchDest
0x140007cee  lea     r8, aSS; "%s\\%s"
0x140007cf5  mov     rcx, rsi; pszDest
0x140007cf8  call    RtlStringCchPrintfW
0x140007cfd  test    eax, eax
0x140007cff  js      short loc_140007D19
0x140007d01  lea     r8, [rsp+58h+arg_8]
0x140007d06  mov     rcx, rsi; SourceString
0x140007d09  lea     rdx, aBreakonopen; "BreakOnOpen"
0x140007d10  call    HsmpGetRegDword
0x140007d15  mov     edi, [rsp+58h+arg_8]
0x140007d19  mov     edx, 62547348h; Tag
0x140007d1e  mov     rcx, rsi; P
0x140007d21  call    cs:__imp_ExFreePoolWithTag
0x140007d28  nop     dword ptr [rax+rax+00h]
0x140007d2d  mov     rcx, [rsp+58h+P]; P
0x140007d32  test    rcx, rcx
0x140007d35  jz      short loc_140007D45
0x140007d37  xor     edx, edx; Tag
0x140007d39  call    cs:__imp_ExFreePoolWithTag
0x140007d40  nop     dword ptr [rax+rax+00h]
0x140007d45  mov     rsi, [rsp+58h+arg_10]
0x140007d4a  jmp     loc_140007BE7
0x140007d4f  int     3; Trap to Debugger
0x140007d50  jmp     loc_140007C19
```
