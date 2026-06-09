# DfscRmSetReferralType

- ea: `0x140011494`
- end: `0x1400115ad`
- name: `DfscRmSetReferralType`
- size: `281`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001b230`

## callees

- `0x140004718`
- `0x140004f74`
- `0x140006380`
- `0x140011494`
- `0x14001ef20`
- `0x140028680`

## string_xrefs

- `0x14001151e`: `LINK_REF`

## pseudocode

```c
__int64 __fastcall DfscRmSetReferralType(__int64 a1, int a2, int a3)
{
  int inited; // edi
  int v7; // r8d
  int v8; // r9d
  const wchar_t *v9; // rax
  struct _UNICODE_STRING v11[9]; // [rsp+30h] [rbp-98h] BYREF

  memset(v11, 0, 0x60u);
  *(_DWORD *)(a1 + 8) = -1;
  inited = DfscInitDfsPath((unsigned __int16 *)(a1 + 144), v11);
  if ( inited >= 0 )
  {
    if ( v11[2].Length )
    {
      *(_DWORD *)(a1 + 8) = 2;
    }
    else
    {
      *(_DWORD *)(a1 + 8) = 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        v9 = L"LINK_REF";
        if ( a2 != 2 )
          v9 = L"ROOT_REF";
        WPP_SF_SS(WPP_GLOBAL_Control->AttachedDevice, (unsigned int)L"ROOT_REF", v7, v8, (__int64)v9);
      }
      if ( a2 != 1 )
        inited = -1073741634;
      if ( a3 && (unsigned __int8)DfscIsSpecialShare(&v11[1]) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
        {
          WPP_SF_Zq(
            WPP_GLOBAL_Control->AttachedDevice,
            24,
            (unsigned int)WPP_55706db06074317498eaf8c01331c814_Traceguids,
            (unsigned int)v11,
            a1);
        }
        *(struct _UNICODE_STRING *)(a1 + 128) = v11[0];
      }
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140011494  push    rbx
0x140011496  push    rbp
0x140011497  push    rsi
0x140011498  push    rdi
0x140011499  push    r12
0x14001149b  push    r14
0x14001149d  sub     rsp, 98h
0x1400114a4  mov     esi, edx
0x1400114a6  mov     ebp, r8d
0x1400114a9  xor     edx, edx; Val
0x1400114ab  mov     rbx, rcx
0x1400114ae  lea     rcx, [rsp+0C8h+var_98]; void *
0x1400114b3  lea     r8d, [rdx+60h]; Size
0x1400114b7  call    memset
0x1400114bc  lea     rcx, [rbx+90h]
0x1400114c3  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x1400114ca  lea     rdx, [rsp+0C8h+var_98]
0x1400114cf  call    DfscInitDfsPath
0x1400114d4  xor     r14d, r14d
0x1400114d7  mov     edi, eax
0x1400114d9  test    eax, eax
0x1400114db  js      loc_14001159A
0x1400114e1  cmp     [rsp+0C8h+var_78], r14w
0x1400114e7  jnz     loc_140011593
0x1400114ed  mov     dword ptr [rbx+8], 1
0x1400114f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400114fb  lea     r12, WPP_GLOBAL_Control
0x140011502  cmp     rcx, r12
0x140011505  jz      short loc_140011533
0x140011507  test    dword ptr [rcx+2Ch], 400000h
0x14001150e  jz      short loc_140011533
0x140011510  mov     rcx, [rcx+18h]
0x140011514  lea     rdx, aRootRef; "ROOT_REF"
0x14001151b  cmp     esi, 2
0x14001151e  lea     rax, aLinkRef; "LINK_REF"
0x140011525  cmovnz  rax, rdx
0x140011529  mov     [rsp+0C8h+var_A8], rax
0x14001152e  call    WPP_SF_SS
0x140011533  cmp     esi, 1
0x140011536  mov     eax, 0C00000BEh
0x14001153b  cmovnz  edi, eax
0x14001153e  test    ebp, ebp
0x140011540  jz      short loc_14001159A
0x140011542  lea     rcx, [rsp+0C8h+var_88]
0x140011547  call    DfscIsSpecialShare
0x14001154c  test    al, al
0x14001154e  jz      short loc_14001159A
0x140011550  mov     rcx, cs:WPP_GLOBAL_Control
0x140011557  cmp     rcx, r12
0x14001155a  jz      short loc_140011584
0x14001155c  test    dword ptr [rcx+2Ch], 400000h
0x140011563  jz      short loc_140011584
0x140011565  mov     rcx, [rcx+18h]
0x140011569  lea     r9, [rsp+0C8h+var_98]
0x14001156e  mov     edx, 18h
0x140011573  mov     [rsp+0C8h+var_A8], rbx
0x140011578  lea     r8, WPP_55706db06074317498eaf8c01331c814_Traceguids
0x14001157f  call    WPP_SF_Zq
0x140011584  movaps  xmm0, [rsp+0C8h+var_98]
0x140011589  movdqu  xmmword ptr [rbx+80h], xmm0
0x140011591  jmp     short loc_14001159A
0x140011593  mov     dword ptr [rbx+8], 2
0x14001159a  mov     eax, edi
0x14001159c  add     rsp, 98h
0x1400115a3  pop     r14
0x1400115a5  pop     r12
0x1400115a7  pop     rdi
0x1400115a8  pop     rsi
0x1400115a9  pop     rbp
0x1400115aa  pop     rbx
0x1400115ab  retn
```
