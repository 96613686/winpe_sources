# CscEnpParseCommonExEa_1

- ea: `0x1400865b0`
- end: `0x14008669e`
- name: `CscEnpParseCommonExEa_1`
- size: `238`
- prototype: `__int64 __fastcall(const STRING *, __int64 *, unsigned __int16, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140011d18`
- `0x1400190ec`
- `0x1400865b0`

## import_xrefs

- `ntoskrnl!RtlEqualString` at `0x1400865f2`
- `ntoskrnl!RtlEqualString` at `0x1400865f2`

## string_xrefs

- `0x1400865c0`: `c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.CommonEx_1`

## pseudocode

```c
__int64 __fastcall CscEnpParseCommonExEa_1(const STRING *a1, __int64 *a2, unsigned __int16 a3, __int64 a4)
{
  unsigned int v4; // edi
  __int64 v6; // rax
  __int64 result; // rax
  STRING v9; // [rsp+30h] [rbp-18h] BYREF
  __int64 v10; // [rsp+68h] [rbp+20h] BYREF

  v4 = a3;
  v9.Buffer = "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.CommonEx_1";
  v6 = *(_QWORD *)(a4 + 8);
  *(_QWORD *)&v9.Length = 3407923;
  *(_DWORD *)(v6 + 380) = 0;
  if ( RtlEqualString(a1, &v9, 1u) )
  {
    if ( (_WORD)v4 == 176 )
    {
      v10 = *a2;
      result = CscEnpCheckEaVersion(&v10, 11534672);
      if ( (int)result >= 0 )
        *(_DWORD *)(*(_QWORD *)(a4 + 8) + 380LL) = *((_DWORD *)a2 + 2);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, v4, 96);
      }
      result = 0;
      if ( (_WORD)v4 )
        result = 3221225700LL;
      else
        *(_BYTE *)a4 |= 1u;
    }
  }
  else
  {
    result = 3221226528LL;
  }
  *(_DWORD *)(a4 + 16) = result;
  return result;
}

```

## disassembly

```asm
0x1400865b0  mov     r11, rsp
0x1400865b3  mov     [r11+8], rbx
0x1400865b7  mov     [r11+10h], rsi
0x1400865bb  push    rdi
0x1400865bc  sub     rsp, 40h
0x1400865c0  lea     rax, aC8a05bc03fa849_4; "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Cs"...
0x1400865c7  movzx   edi, r8w
0x1400865cb  mov     [r11-10h], rax
0x1400865cf  mov     rsi, rdx
0x1400865d2  mov     rax, [r9+8]
0x1400865d6  lea     rdx, [r11-18h]; String2
0x1400865da  mov     qword ptr [r11-18h], 340033h
0x1400865e2  mov     r8b, 1; CaseInSensitive
0x1400865e5  mov     rbx, r9
0x1400865e8  mov     dword ptr [rax+17Ch], 0
0x1400865f2  call    cs:__imp_RtlEqualString
0x1400865f9  nop     dword ptr [rax+rax+00h]
0x1400865fe  test    al, al
0x140086600  jz      short loc_140086648
0x140086602  mov     eax, 0B0h
0x140086607  cmp     di, ax
0x14008660a  jnz     short loc_14008664F
0x14008660c  mov     rax, [rsi]
0x14008660f  lea     rcx, [rsp+48h+arg_18]
0x140086614  mov     edx, 0B00150h
0x140086619  mov     [rsp+48h+arg_18], rax
0x14008661e  call    CscEnpCheckEaVersion
0x140086623  test    eax, eax
0x140086625  js      short loc_140086634
0x140086627  mov     rdx, [rbx+8]
0x14008662b  mov     ecx, [rsi+8]
0x14008662e  mov     [rdx+17Ch], ecx
0x140086634  mov     rsi, [rsp+48h+arg_8]
0x140086639  mov     [rbx+10h], eax
0x14008663c  mov     rbx, [rsp+48h+arg_0]
0x140086641  add     rsp, 40h
0x140086645  pop     rdi
0x140086646  retn
0x140086648  mov     eax, 0C0000420h
0x14008664d  jmp     short loc_140086634
0x14008664f  mov     rcx, cs:WPP_GLOBAL_Control
0x140086656  lea     rax, WPP_GLOBAL_Control
0x14008665d  cmp     rcx, rax
0x140086660  jz      short loc_14008668B
0x140086662  test    dword ptr [rcx+2Ch], 10000h
0x140086669  jz      short loc_14008668B
0x14008666b  mov     rcx, [rcx+18h]
0x14008666f  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x140086676  mov     r9d, edi
0x140086679  mov     [rsp+48h+var_28], 60h ; '`'
0x140086681  mov     edx, 2Ah ; '*'
0x140086686  call    WPP_SF_Dd
0x14008668b  xor     eax, eax
0x14008668d  cmp     ax, di
0x140086690  jnz     short loc_140086697
0x140086692  or      byte ptr [rbx], 1
0x140086695  jmp     short loc_140086634
0x140086697  mov     eax, 0C00000E4h
0x14008669c  jmp     short loc_140086634
```
