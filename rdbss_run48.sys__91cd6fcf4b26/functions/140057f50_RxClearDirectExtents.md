# RxClearDirectExtents

- ea: `0x140057f50`
- end: `0x14005811c`
- name: `RxClearDirectExtents`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140057a80`

## callees

- `0x140015230`
- `0x140018480`
- `0x140057f50`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400580fb`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400580fb`
- `ntoskrnl!FsRtlIsExtentDangling` at `0x140057ff8`
- `ntoskrnl!FsRtlIsExtentDangling` at `0x140057ff8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058083`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058083`

## pseudocode

```c
void __fastcall RxClearDirectExtents(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rdi
  int v5; // ebx
  unsigned __int64 v6; // rsi
  __int64 v7; // r14
  unsigned __int64 IsExtentDangling; // rax
  PVOID v9; // r12
  int v10; // [rsp+90h] [rbp+8h]
  LARGE_INTEGER Interval; // [rsp+98h] [rbp+10h] BYREF
  PVOID P; // [rsp+A0h] [rbp+18h]

  if ( a1 == *(_QWORD *)(a2 + 720) )
  {
    P = *(PVOID *)(a2 + 712);
    if ( P )
    {
      *(_QWORD *)(a2 + 712) = 0;
      v10 = 0;
      Interval.QuadPart = -160000;
      while ( 1 )
      {
        v4 = *(_DWORD **)(a2 + 712);
        if ( !v4 )
          break;
        if ( *(_QWORD *)(a2 + 720) != a1 )
          break;
        v5 = 0;
        if ( !*v4 )
          break;
        while ( 1 )
        {
          v6 = *(_QWORD *)&v4[4 * v5 + 4];
          v7 = *(_QWORD *)&v4[4 * v5 + 6];
          IsExtentDangling = FsRtlIsExtentDangling(v6, v7, 0);
          if ( v6 <= IsExtentDangling && IsExtentDangling < v7 + v6 )
            break;
          if ( (unsigned int)++v5 >= *v4 )
            goto LABEL_10;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqqqqD(WPP_GLOBAL_Control->AttachedDevice, IsExtentDangling, WPP_GLOBAL_Control, a1);
        }
        KeDelayExecutionThread(0, 0, &Interval);
        ++v10;
      }
LABEL_10:
      v9 = P;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 21, &WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids, a1, a2);
      }
      ExFreePoolWithTag(v9, 0x734D7852u);
    }
    *(_QWORD *)(a2 + 720) = 0;
    *(_QWORD *)(a2 + 728) = 0;
  }
}

```

## disassembly

```asm
0x140057f50  mov     rax, rsp
0x140057f53  push    rbp
0x140057f54  push    r15
0x140057f56  sub     rsp, 78h
0x140057f5a  mov     rbp, rdx
0x140057f5d  mov     r15, rcx
0x140057f60  cmp     rcx, [rdx+2D0h]
0x140057f67  jnz     loc_1400580A7
0x140057f6d  mov     [rax-28h], r12
0x140057f71  mov     r12, [rdx+2C8h]
0x140057f78  mov     [rax-30h], r13
0x140057f7c  xor     r13d, r13d
0x140057f7f  mov     [rsp+88h+P], r12
0x140057f87  test    r12, r12
0x140057f8a  jz      loc_14005808F
0x140057f90  mov     [rax+20h], rbx
0x140057f94  lea     r12, WPP_GLOBAL_Control
0x140057f9b  mov     [rax-18h], rsi
0x140057f9f  mov     [rax+10h], r13
0x140057fa3  mov     [rax-20h], rdi
0x140057fa7  mov     [rdx+2C8h], r13
0x140057fae  mov     [rax-38h], r14
0x140057fb2  mov     [rsp+88h+arg_0], r13d
0x140057fba  mov     qword ptr [rax+10h], 0FFFFFFFFFFFD8F00h
0x140057fc2  mov     rdi, [rbp+2C8h]
0x140057fc9  test    rdi, rdi
0x140057fcc  jz      short loc_14005801F
0x140057fce  cmp     [rbp+2D0h], r15
0x140057fd5  jnz     short loc_14005801F
0x140057fd7  mov     ebx, r13d
0x140057fda  cmp     [rdi], ebx
0x140057fdc  jbe     short loc_14005801F
0x140057fde  xchg    ax, ax
0x140057fe0  mov     eax, ebx
0x140057fe2  xor     r8d, r8d
0x140057fe5  add     rax, rax
0x140057fe8  mov     rsi, [rdi+rax*8+10h]
0x140057fed  mov     r14, [rdi+rax*8+18h]
0x140057ff2  mov     rcx, rsi
0x140057ff5  mov     rdx, r14
0x140057ff8  call    cs:__imp_FsRtlIsExtentDangling
0x140057fff  nop     dword ptr [rax+rax+00h]
0x140058004  mov     rdx, rax
0x140058007  cmp     rsi, rax
0x14005800a  ja      short loc_140058019
0x14005800c  lea     rcx, [r14+rsi]
0x140058010  cmp     rax, rcx
0x140058013  jb      loc_1400580B0
0x140058019  inc     ebx
0x14005801b  cmp     ebx, [rdi]
0x14005801d  jb      short loc_140057FE0
0x14005801f  mov     rcx, cs:WPP_GLOBAL_Control
0x140058026  lea     rax, WPP_GLOBAL_Control
0x14005802d  mov     r14, [rsp+88h+var_38]
0x140058032  mov     rdi, [rsp+88h+var_20]
0x140058037  mov     rsi, [rsp+88h+var_18]
0x14005803c  mov     rbx, [rsp+88h+arg_18]
0x140058044  mov     r12, [rsp+88h+P]
0x14005804c  cmp     rcx, rax
0x14005804f  jz      short loc_14005807B
0x140058051  mov     eax, [rcx+2Ch]
0x140058054  test    al, 8
0x140058056  jz      short loc_14005807B
0x140058058  cmp     byte ptr [rcx+29h], 2
0x14005805c  jb      short loc_14005807B
0x14005805e  mov     rcx, [rcx+18h]
0x140058062  lea     r8, WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids
0x140058069  mov     edx, 15h
0x14005806e  mov     [rsp+88h+var_68], rbp
0x140058073  mov     r9, r15
0x140058076  call    WPP_SF_qq
0x14005807b  mov     edx, 734D7852h; Tag
0x140058080  mov     rcx, r12; P
0x140058083  call    cs:__imp_ExFreePoolWithTag
0x14005808a  nop     dword ptr [rax+rax+00h]
0x14005808f  mov     r12, [rsp+88h+var_28]
0x140058094  mov     [rbp+2D0h], r13
0x14005809b  mov     [rbp+2D8h], r13
0x1400580a2  mov     r13, [rsp+88h+var_30]
0x1400580a7  add     rsp, 78h
0x1400580ab  pop     r15
0x1400580ad  pop     rbp
0x1400580ae  retn
0x1400580b0  mov     r8, cs:WPP_GLOBAL_Control
0x1400580b7  cmp     r8, r12
0x1400580ba  jz      short loc_1400580EF
0x1400580bc  mov     eax, [r8+2Ch]
0x1400580c0  test    al, 8
0x1400580c2  jz      short loc_1400580EF
0x1400580c4  cmp     byte ptr [r8+29h], 2
0x1400580c9  jb      short loc_1400580EF
0x1400580cb  mov     [rsp+88h+var_48], ebx
0x1400580cf  mov     r9, r15
0x1400580d2  mov     [rsp+88h+var_50], rcx
0x1400580d7  mov     rcx, [r8+18h]
0x1400580db  mov     [rsp+88h+var_58], rsi
0x1400580e0  mov     [rsp+88h+var_60], rdx
0x1400580e5  mov     [rsp+88h+var_68], rbp
0x1400580ea  call    WPP_SF_qqqqqD
0x1400580ef  lea     r8, [rsp+88h+Interval]; Interval
0x1400580f7  xor     edx, edx; Alertable
0x1400580f9  xor     ecx, ecx; WaitMode
0x1400580fb  call    cs:__imp_KeDelayExecutionThread
0x140058102  nop     dword ptr [rax+rax+00h]
0x140058107  mov     eax, [rsp+88h+arg_0]
0x14005810e  inc     eax
0x140058110  mov     [rsp+88h+arg_0], eax
0x140058117  jmp     loc_140057FC2
```
