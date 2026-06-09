# CscEnpParseCommonExEa

- ea: `0x140086450`
- end: `0x14008659c`
- name: `CscEnpParseCommonExEa`
- size: `332`
- prototype: `__int64 __fastcall(const STRING *, __int64 *, unsigned __int16, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140011d18`
- `0x1400190ec`
- `0x140086450`

## import_xrefs

- `ntoskrnl!RtlEqualString` at `0x140086480`
- `ntoskrnl!RtlEqualString` at `0x140086480`

## string_xrefs

- `0x140086460`: `c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.CommonEx`

## pseudocode

```c
__int64 __fastcall CscEnpParseCommonExEa(const STRING *a1, __int64 *a2, unsigned __int16 a3, __int64 a4)
{
  unsigned int v4; // edi
  int v7; // ecx
  __int128 v8; // xmm1
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rdx
  bool v13; // zf
  STRING String2; // [rsp+30h] [rbp-38h] BYREF
  __int128 v16; // [rsp+40h] [rbp-28h]
  __int64 v17; // [rsp+50h] [rbp-18h]
  __int64 v18; // [rsp+A8h] [rbp+40h] BYREF

  v4 = a3;
  String2.Buffer = "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.CommonEx";
  *(_QWORD *)&String2.Length = 3276849;
  if ( !RtlEqualString(a1, &String2, 1u) )
  {
    v7 = -1073740768;
    goto LABEL_13;
  }
  if ( (_WORD)v4 != 96 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, v4, 96);
    }
    if ( (_WORD)v4 )
      goto LABEL_15;
    v7 = 0;
LABEL_14:
    *(_BYTE *)a4 |= 1u;
    goto LABEL_13;
  }
  v18 = *a2;
  v7 = CscEnpCheckEaVersion(&v18, 6291616);
  if ( v7 < 0 )
    goto LABEL_13;
  v8 = *(_OWORD *)(a2 + 1);
  v9 = *(_QWORD *)(a4 + 8);
  v10 = a2[1];
  v17 = a2[3];
  v16 = v8;
  v11 = *(_QWORD *)(v9 + 8);
  v12 = v10 - *(_QWORD *)(v11 + 324);
  if ( !v12 )
    v12 = *((_QWORD *)&v16 + 1) - *(_QWORD *)(v11 + 332);
  if ( v12 )
    goto LABEL_14;
  if ( HIDWORD(v17) > *(_DWORD *)(v9 + 368) )
  {
LABEL_15:
    v7 = -1073741596;
    goto LABEL_13;
  }
  v13 = (v17 & 1) == 0;
  *(_DWORD *)(v9 + 384) = HIDWORD(v17);
  if ( !v13 )
    *(_DWORD *)(*(_QWORD *)(a4 + 8) + 192LL) |= 0x10u;
  if ( (v17 & 2) != 0 )
    *(_DWORD *)(*(_QWORD *)(a4 + 8) + 196LL) |= 0x10u;
LABEL_13:
  *(_DWORD *)(a4 + 16) = v7;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140086450  push    rbp
0x140086452  push    rbx
0x140086453  push    rsi
0x140086454  push    rdi
0x140086455  mov     rbp, rsp
0x140086458  sub     rsp, 68h
0x14008645c  movzx   edi, r8w
0x140086460  lea     rax, aC8a05bc03fa849_3; "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Cs"...
0x140086467  mov     rsi, rdx
0x14008646a  mov     [rbp+String2.Buffer], rax
0x14008646e  mov     r8b, 1; CaseInSensitive
0x140086471  mov     qword ptr [rbp+String2.Length], 320031h
0x140086479  lea     rdx, [rbp+String2]; String2
0x14008647d  mov     rbx, r9
0x140086480  call    cs:__imp_RtlEqualString
0x140086487  nop     dword ptr [rax+rax+00h]
0x14008648c  test    al, al
0x14008648e  jz      loc_140086528
0x140086494  mov     r8d, 60h ; '`'
0x14008649a  cmp     di, r8w
0x14008649e  jnz     loc_140086548
0x1400864a4  mov     rax, [rsi]
0x1400864a7  lea     rcx, [rbp+arg_18]
0x1400864ab  mov     edx, 6000A0h
0x1400864b0  mov     [rbp+arg_18], rax
0x1400864b4  call    CscEnpCheckEaVersion
0x1400864b9  mov     ecx, eax
0x1400864bb  test    eax, eax
0x1400864bd  js      short loc_14008652D
0x1400864bf  movups  xmm1, xmmword ptr [rsi+8]
0x1400864c3  mov     r8, [rbx+8]
0x1400864c7  movsd   xmm0, qword ptr [rsi+18h]
0x1400864cc  movq    rdx, xmm1
0x1400864d1  movsd   [rbp+var_18], xmm0
0x1400864d6  movups  [rbp+var_28], xmm1
0x1400864da  mov     r9, [r8+8]
0x1400864de  sub     rdx, [r9+144h]
0x1400864e5  jnz     short loc_1400864F2
0x1400864e7  mov     rdx, qword ptr [rbp+var_28+8]
0x1400864eb  sub     rdx, [r9+14Ch]
0x1400864f2  test    rdx, rdx
0x1400864f5  jnz     short loc_14008653C
0x1400864f7  mov     rax, [rbp+var_18]
0x1400864fb  shr     rax, 20h
0x1400864ff  cmp     eax, [r8+170h]
0x140086506  ja      short loc_140086541
0x140086508  test    byte ptr [rbp+var_18], 1
0x14008650c  mov     [r8+180h], eax
0x140086513  jnz     short loc_14008658C
0x140086515  test    byte ptr [rbp+var_18], 2
0x140086519  jz      short loc_14008652D
0x14008651b  mov     rax, [rbx+8]
0x14008651f  or      dword ptr [rax+0C4h], 10h
0x140086526  jmp     short loc_14008652D
0x140086528  mov     ecx, 0C0000420h
0x14008652d  mov     [rbx+10h], ecx
0x140086530  mov     eax, ecx
0x140086532  add     rsp, 68h
0x140086536  pop     rdi
0x140086537  pop     rsi
0x140086538  pop     rbx
0x140086539  pop     rbp
0x14008653a  retn
0x14008653c  or      byte ptr [rbx], 1
0x14008653f  jmp     short loc_14008652D
0x140086541  mov     ecx, 0C00000E4h
0x140086546  jmp     short loc_14008652D
0x140086548  mov     rcx, cs:WPP_GLOBAL_Control
0x14008654f  lea     rax, WPP_GLOBAL_Control
0x140086556  cmp     rcx, rax
0x140086559  jz      short loc_140086581
0x14008655b  test    dword ptr [rcx+2Ch], 10000h
0x140086562  jz      short loc_140086581
0x140086564  mov     rcx, [rcx+18h]
0x140086568  mov     r9d, edi
0x14008656b  mov     [rsp+68h+var_48], r8d
0x140086570  mov     edx, 2Bh ; '+'
0x140086575  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x14008657c  call    WPP_SF_Dd
0x140086581  xor     eax, eax
0x140086583  cmp     ax, di
0x140086586  jnz     short loc_140086541
0x140086588  xor     ecx, ecx
0x14008658a  jmp     short loc_14008653C
0x14008658c  mov     rax, [rbx+8]
0x140086590  or      dword ptr [rax+0C0h], 10h
0x140086597  jmp     loc_140086515
```
