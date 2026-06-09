# CscEnpParseCommonEa

- ea: `0x1400803a0`
- end: `0x140080558`
- name: `CscEnpParseCommonEa`
- size: `440`
- prototype: `__int64 __fastcall(const STRING *, __int64 *, unsigned __int16, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140011d18`
- `0x1400190ec`
- `0x1400803a0`

## import_xrefs

- `ntoskrnl!RtlEqualString` at `0x1400803d6`
- `ntoskrnl!RtlEqualString` at `0x1400803d6`

## string_xrefs

- `0x1400803b3`: `c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.Common`

## pseudocode

```c
__int64 __fastcall CscEnpParseCommonEa(const STRING *a1, __int64 *a2, unsigned __int16 a3, __int64 a4)
{
  unsigned int v4; // esi
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // r9d
  __int64 v10; // rcx
  __int64 v11; // rdx
  STRING String2; // [rsp+30h] [rbp-18h] BYREF
  __int64 v13; // [rsp+68h] [rbp+20h] BYREF

  v4 = a3;
  String2.Buffer = "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.Common";
  *(_QWORD *)&String2.Length = 3145775;
  if ( RtlEqualString(a1, &String2, 1u) )
  {
    if ( (_WORD)v4 == 152 )
    {
      v13 = *a2;
      result = CscEnpCheckEaVersion(&v13, 9961600);
      if ( (int)result < 0 )
      {
LABEL_6:
        *(_DWORD *)(a4 + 16) = result;
        return result;
      }
      v8 = *(_QWORD *)(a4 + 8);
      v9 = *((_DWORD *)a2 + 24);
      v10 = a2[11];
      if ( ((*(_BYTE *)(v8 + 336) ^ *((_BYTE *)a2 + 96)) & 0x10) == 0 )
      {
        *(_OWORD *)(v8 + 192) = *(_OWORD *)(a2 + 1);
        *(_OWORD *)(v8 + 208) = *(_OWORD *)(a2 + 3);
        *(_OWORD *)(v8 + 224) = *(_OWORD *)(a2 + 5);
        *(_OWORD *)(v8 + 240) = *(_OWORD *)(a2 + 7);
        *(_OWORD *)(v8 + 256) = *(_OWORD *)(a2 + 9);
        *(_DWORD *)(*(_QWORD *)(a4 + 8) + 336LL) = v9;
        *(_QWORD *)(*(_QWORD *)(a4 + 8) + 288LL) = v10;
        *(_WORD *)(*(_QWORD *)(a4 + 8) + 388LL) = *((_WORD *)a2 + 52);
        *(_WORD *)(*(_QWORD *)(a4 + 8) + 400LL) = *((_WORD *)a2 + 53);
        *(_OWORD *)(*(_QWORD *)(a4 + 8) + 352LL) = *(_OWORD *)(a2 + 17);
        v11 = *(_QWORD *)(a4 + 8);
        *(_QWORD *)(v11 + 368) = *(__int64 *)((char *)a2 + 124);
        *(_DWORD *)(v11 + 376) = *((_DWORD *)a2 + 33);
        goto LABEL_6;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, v4, 152);
    }
    result = 3221225700LL;
    *(_DWORD *)(a4 + 16) = -1073741596;
  }
  else
  {
    result = 3221226528LL;
    *(_DWORD *)(a4 + 16) = -1073740768;
  }
  return result;
}

```

## disassembly

```asm
0x1400803a0  mov     [rsp+arg_0], rbx
0x1400803a5  mov     [rsp+arg_8], rsi
0x1400803aa  push    rdi
0x1400803ab  sub     rsp, 40h
0x1400803af  movzx   esi, r8w
0x1400803b3  lea     rax, aC8a05bc03fa849; "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Cs"...
0x1400803ba  mov     rdi, rdx
0x1400803bd  mov     [rsp+48h+String2.Buffer], rax
0x1400803c2  mov     r8b, 1; CaseInSensitive
0x1400803c5  mov     qword ptr [rsp+48h+String2.Length], 30002Fh
0x1400803ce  lea     rdx, [rsp+48h+String2]; String2
0x1400803d3  mov     rbx, r9
0x1400803d6  call    cs:__imp_RtlEqualString
0x1400803dd  nop     dword ptr [rax+rax+00h]
0x1400803e2  test    al, al
0x1400803e4  jz      loc_1400804EB
0x1400803ea  mov     r8d, 98h
0x1400803f0  cmp     si, r8w
0x1400803f4  jnz     loc_140080504
0x1400803fa  mov     rax, [rdi]
0x1400803fd  lea     rcx, [rsp+48h+arg_18]
0x140080402  mov     edx, 980080h
0x140080407  mov     [rsp+48h+arg_18], rax
0x14008040c  call    CscEnpCheckEaVersion
0x140080411  test    eax, eax
0x140080413  js      loc_1400804D7
0x140080419  mov     r8, [rbx+8]
0x14008041d  mov     r9d, [rdi+60h]
0x140080421  mov     edx, r9d
0x140080424  mov     rcx, [rdi+58h]
0x140080428  xor     edx, [r8+150h]
0x14008042f  test    dl, 10h
0x140080432  jnz     loc_140080517
0x140080438  movups  xmm0, xmmword ptr [rdi+8]
0x14008043c  movups  xmmword ptr [r8+0C0h], xmm0
0x140080444  movups  xmm1, xmmword ptr [rdi+18h]
0x140080448  movups  xmmword ptr [r8+0D0h], xmm1
0x140080450  movups  xmm0, xmmword ptr [rdi+28h]
0x140080454  movups  xmmword ptr [r8+0E0h], xmm0
0x14008045c  movups  xmm1, xmmword ptr [rdi+38h]
0x140080460  movups  xmmword ptr [r8+0F0h], xmm1
0x140080468  movups  xmm0, xmmword ptr [rdi+48h]
0x14008046c  movups  xmmword ptr [r8+100h], xmm0
0x140080474  mov     rdx, [rbx+8]
0x140080478  mov     [rdx+150h], r9d
0x14008047f  mov     rdx, [rbx+8]
0x140080483  mov     [rdx+120h], rcx
0x14008048a  movzx   ecx, word ptr [rdi+68h]
0x14008048e  mov     rdx, [rbx+8]
0x140080492  mov     [rdx+184h], cx
0x140080499  mov     rdx, [rbx+8]
0x14008049d  movzx   ecx, word ptr [rdi+6Ah]
0x1400804a1  mov     [rdx+190h], cx
0x1400804a8  mov     rcx, [rbx+8]
0x1400804ac  movups  xmm0, xmmword ptr [rdi+88h]
0x1400804b3  movups  xmmword ptr [rcx+160h], xmm0
0x1400804ba  mov     rdx, [rbx+8]
0x1400804be  movsd   xmm0, qword ptr [rdi+7Ch]
0x1400804c3  movsd   qword ptr [rdx+170h], xmm0
0x1400804cb  mov     ecx, [rdi+84h]
0x1400804d1  mov     [rdx+178h], ecx
0x1400804d7  mov     [rbx+10h], eax
0x1400804da  mov     rbx, [rsp+48h+arg_0]
0x1400804df  mov     rsi, [rsp+48h+arg_8]
0x1400804e4  add     rsp, 40h
0x1400804e8  pop     rdi
0x1400804e9  retn
0x1400804eb  mov     eax, 0C0000420h
0x1400804f0  mov     [rbx+10h], eax
0x1400804f3  mov     rbx, [rsp+48h+arg_0]
0x1400804f8  mov     rsi, [rsp+48h+arg_8]
0x1400804fd  add     rsp, 40h
0x140080501  pop     rdi
0x140080502  retn
0x140080504  mov     rcx, cs:WPP_GLOBAL_Control
0x14008050b  lea     rax, WPP_GLOBAL_Control
0x140080512  cmp     rcx, rax
0x140080515  jnz     short loc_140080530
0x140080517  mov     rsi, [rsp+48h+arg_8]
0x14008051c  mov     eax, 0C00000E4h
0x140080521  mov     [rbx+10h], eax
0x140080524  mov     rbx, [rsp+48h+arg_0]
0x140080529  add     rsp, 40h
0x14008052d  pop     rdi
0x14008052e  retn
0x140080530  test    dword ptr [rcx+2Ch], 10000h
0x140080537  jz      short loc_140080517
0x140080539  mov     rcx, [rcx+18h]
0x14008053d  mov     r9d, esi
0x140080540  mov     [rsp+48h+var_28], r8d
0x140080545  mov     edx, 29h ; ')'
0x14008054a  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x140080551  call    WPP_SF_Dd
0x140080556  jmp     short loc_140080517
```
