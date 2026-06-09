# LipsStateIkeFilterDelete

- ea: `0x180045808`
- end: `0x180045928`
- name: `LipsStateIkeFilterDelete`
- size: `288`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004482c`
- `0x180045c1c`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x180045808`
- `0x180045aac`
- `0x180048478`
- `0x180048570`
- `0x1800486b0`

## string_xrefs

- `0x180045906`: `LipsStateIkeFilterDelete`

## pseudocode

```c
__int64 __fastcall LipsStateIkeFilterDelete(__int64 a1, unsigned int a2)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx

  if ( !a1 || !a2 )
    return 0;
  v4 = LipsBfeTransactionBegin();
  if ( !v4 )
  {
    v4 = LipsStateIkeFilterEnum(a1, 0, a2, LipsStateIkeFilterDeleteCb);
    if ( v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_16;
      v6 = 24;
    }
    else
    {
      v4 = LipsBfeTransactionCommit();
      if ( !v4 )
        goto LABEL_17;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_16;
      v6 = 25;
    }
    WPP_SF_d(v5[2], v6, WPP_b2e62c343c9f3927bd54de5c93575086_Traceguids, v4);
LABEL_16:
    LipsBfeTransactionAbort();
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_b2e62c343c9f3927bd54de5c93575086_Traceguids, v4);
LABEL_17:
  LipsStateIkeFilterEnum(a1, 0, a2, LipsStateIkeFilterDestroyLegacyCb);
  if ( v4 )
    return LipsReportError(v4, (int)"LipsStateIkeFilterDelete");
  return 0;
}

```

## disassembly

```asm
0x180045808  mov     [rsp+arg_0], rbx
0x18004580d  mov     [rsp+arg_8], rsi
0x180045812  push    rdi
0x180045813  sub     rsp, 20h
0x180045817  mov     edi, edx
0x180045819  mov     rsi, rcx
0x18004581c  test    rcx, rcx
0x18004581f  jz      loc_180045916
0x180045825  test    edx, edx
0x180045827  jz      loc_180045916
0x18004582d  call    LipsBfeTransactionBegin
0x180045832  mov     ebx, eax
0x180045834  test    eax, eax
0x180045836  jz      short loc_180045873
0x180045838  mov     rcx, cs:WPP_GLOBAL_Control
0x18004583f  lea     rax, WPP_GLOBAL_Control
0x180045846  cmp     rcx, rax
0x180045849  jz      loc_1800458EE
0x18004584f  test    byte ptr [rcx+1Ch], 10h
0x180045853  jz      loc_1800458EE
0x180045859  mov     rcx, [rcx+10h]
0x18004585d  lea     r8, WPP_b2e62c343c9f3927bd54de5c93575086_Traceguids
0x180045864  mov     edx, 17h
0x180045869  mov     r9d, ebx
0x18004586c  call    WPP_SF_d
0x180045871  jmp     short loc_1800458EE
0x180045873  lea     r9, LipsStateIkeFilterDeleteCb
0x18004587a  mov     r8d, edi
0x18004587d  xor     edx, edx
0x18004587f  mov     rcx, rsi
0x180045882  call    LipsStateIkeFilterEnum
0x180045887  mov     ebx, eax
0x180045889  test    eax, eax
0x18004588b  jz      short loc_1800458AD
0x18004588d  mov     rcx, cs:WPP_GLOBAL_Control
0x180045894  lea     rax, WPP_GLOBAL_Control
0x18004589b  cmp     rcx, rax
0x18004589e  jz      short loc_1800458E9
0x1800458a0  test    byte ptr [rcx+1Ch], 10h
0x1800458a4  jz      short loc_1800458E9
0x1800458a6  mov     edx, 18h
0x1800458ab  jmp     short loc_1800458D6
0x1800458ad  call    LipsBfeTransactionCommit
0x1800458b2  mov     ebx, eax
0x1800458b4  test    eax, eax
0x1800458b6  jz      short loc_1800458EE
0x1800458b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800458bf  lea     rax, WPP_GLOBAL_Control
0x1800458c6  cmp     rcx, rax
0x1800458c9  jz      short loc_1800458E9
0x1800458cb  test    byte ptr [rcx+1Ch], 10h
0x1800458cf  jz      short loc_1800458E9
0x1800458d1  mov     edx, 19h
0x1800458d6  mov     rcx, [rcx+10h]
0x1800458da  lea     r8, WPP_b2e62c343c9f3927bd54de5c93575086_Traceguids
0x1800458e1  mov     r9d, ebx
0x1800458e4  call    WPP_SF_d
0x1800458e9  call    LipsBfeTransactionAbort
0x1800458ee  lea     r9, LipsStateIkeFilterDestroyLegacyCb
0x1800458f5  mov     r8d, edi
0x1800458f8  xor     edx, edx
0x1800458fa  mov     rcx, rsi
0x1800458fd  call    LipsStateIkeFilterEnum
0x180045902  test    ebx, ebx
0x180045904  jz      short loc_180045916
0x180045906  lea     rdx, aLipsstateikefi_5; "LipsStateIkeFilterDelete"
0x18004590d  mov     ecx, ebx
0x18004590f  call    LipsReportError
0x180045914  jmp     short loc_180045918
0x180045916  xor     eax, eax
0x180045918  mov     rbx, [rsp+28h+arg_0]
0x18004591d  mov     rsi, [rsp+28h+arg_8]
0x180045922  add     rsp, 20h
0x180045926  pop     rdi
0x180045927  retn
```
