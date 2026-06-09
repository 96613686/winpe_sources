# MRxSmbStartSMBCommand

- ea: `0x14004a590`
- end: `0x14004a747`
- name: `MRxSmbStartSMBCommand`
- size: `439`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _BYTE, _DWORD)`
- caller_count: `26`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002d870`
- `0x14002ddd0`
- `0x14002dee8`
- `0x14002ea60`
- `0x14002ec20`
- `0x140033fa8`
- `0x140034058`
- `0x140034470`
- `0x1400360f4`
- `0x1400361b0`
- `0x140036260`
- `0x14003630c`
- `0x14003652c`
- `0x140039b9c`
- `0x140039ee0`
- `0x14003a028`
- `0x14003a120`
- `0x14003a204`
- `0x14003a394`
- `0x14003a494`
- `0x14003b07c`
- `0x14003b4c8`
- `0x14003b980`
- `0x14003c230`
- `0x14003c2e8`
- `0x1400495b4`

## callees

- `0x140014194`
- `0x140046a50`
- `0x14004a590`

## pseudocode

```c
__int64 __fastcall MRxSmbStartSMBCommand(__int64 a1, int a2, char a3, int a4, __int64 a5, unsigned int a6)
{
  __int64 v7; // rsi
  int v10; // eax
  __int64 v11; // rcx
  unsigned int v12; // edx
  __int64 v13; // r8
  unsigned __int8 v14; // al
  unsigned __int16 v15; // cx
  __int64 v16; // rbp
  __int64 result; // rax
  __int64 v18; // rcx
  unsigned int v19; // esi
  unsigned int v20; // r14d
  _BYTE *i; // rcx

  v7 = *(_QWORD *)(a1 + 32);
  if ( *(_DWORD *)(a1 + 72) )
    goto LABEL_10;
  if ( a2 == 1 && *(_BYTE *)(a1 + 123) )
    MRxSmbSetInitialSMB(a1);
  v10 = *(unsigned __int8 *)(a1 + 121);
  *(_BYTE *)(a1 + 123) = 1;
  if ( v10 != 255 )
  {
    switch ( v10 )
    {
      case 36:
      case 45:
      case 46:
      case 47:
      case 115:
      case 117:
      case 162:
        break;
      default:
        goto LABEL_10;
    }
  }
  v11 = *(_QWORD *)(a1 + 80);
  v12 = HIWORD(a6);
  v13 = HIWORD(a6) + a4;
  if ( (unsigned __int64)(v11 + v13) >= *(_QWORD *)(a1 + 40) )
  {
LABEL_10:
    *(_BYTE *)(a1 + 122) = 1;
  }
  else if ( *(_QWORD *)(a1 + 48) && (unsigned int)(v13 + v11 - *(_DWORD *)(a1 + 32)) > 0x1104 )
  {
    *(_BYTE *)(a1 + 122) = 4;
  }
  else
  {
    v14 = *(_BYTE *)(a1 + 124);
    v15 = *(_WORD *)(a1 + 128);
    *(_BYTE *)(v7 + 9) = v14;
    *(_DWORD *)(a1 + 124) = v14;
    *(_DWORD *)(a1 + 128) = v15;
    *(_WORD *)(v7 + 10) = v15;
    v16 = *(_QWORD *)(a1 + 88);
    if ( !v16 )
    {
      *(_BYTE *)(v7 + 4) = a3;
LABEL_9:
      *(_QWORD *)(a1 + 88) = *(_QWORD *)(a1 + 80);
      result = 0;
      *(_BYTE *)(a1 + 121) = a3;
      *(_QWORD *)(a1 + 104) = 0;
      return result;
    }
    v18 = *(_QWORD *)(a1 + 80);
    if ( v18 + (unsigned __int64)v12 < *(_QWORD *)(a1 + 40) )
    {
      if ( v12 )
      {
        v19 = v12 - 1;
        v20 = a6 & (v12 - 1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_DLL(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, v13, v19 & (unsigned int)v18, v19, v20);
        }
        for ( i = *(_BYTE **)(a1 + 80); (v19 & (unsigned int)i) != (unsigned __int64)v20; i = *(_BYTE **)(a1 + 80) )
        {
          *i = 44;
          ++*(_QWORD *)(a1 + 80);
        }
      }
      *(_BYTE *)(v16 + 1) = a3;
      *(_BYTE *)(v16 + 2) = 0;
      *(_WORD *)(v16 + 3) = *(_WORD *)(a1 + 80) - *(_WORD *)(a1 + 32);
      goto LABEL_9;
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x14004a590  push    rbx
0x14004a592  push    rbp
0x14004a593  push    rsi
0x14004a594  push    rdi
0x14004a595  sub     rsp, 38h
0x14004a599  cmp     dword ptr [rcx+48h], 0
0x14004a59d  mov     ebp, r9d
0x14004a5a0  mov     rsi, [rcx+20h]
0x14004a5a4  movzx   edi, r8b
0x14004a5a8  mov     rbx, rcx
0x14004a5ab  jnz     def_14004A738; jumptable 000000014004A738 default case, cases 37-44,48-114,116,118-161
0x14004a5b1  cmp     edx, 1
0x14004a5b4  jz      loc_14004A6FD
0x14004a5ba  movzx   eax, byte ptr [rbx+79h]
0x14004a5be  mov     byte ptr [rbx+7Bh], 1
0x14004a5c2  cmp     eax, 0FFh
0x14004a5c7  jnz     loc_14004A711
0x14004a5cd  mov     r9d, [rsp+58h+arg_28]; jumptable 000000014004A738 cases 36,45-47,115,117,162
0x14004a5d5  mov     edx, r9d
0x14004a5d8  mov     rcx, [rbx+50h]
0x14004a5dc  shr     edx, 10h
0x14004a5df  lea     r8d, [rdx+rbp]
0x14004a5e3  mov     eax, r8d
0x14004a5e6  add     rax, rcx
0x14004a5e9  cmp     rax, [rbx+28h]
0x14004a5ed  jnb     short def_14004A738; jumptable 000000014004A738 default case, cases 37-44,48-114,116,118-161
0x14004a5ef  cmp     qword ptr [rbx+30h], 0
0x14004a5f4  jz      short loc_14004A608
0x14004a5f6  sub     ecx, [rbx+20h]
0x14004a5f9  add     ecx, r8d
0x14004a5fc  cmp     ecx, 1104h
0x14004a602  ja      loc_14004A73E
0x14004a608  movzx   eax, byte ptr [rbx+7Ch]
0x14004a60c  movzx   ecx, word ptr [rbx+80h]
0x14004a613  mov     [rsi+9], al
0x14004a616  movzx   eax, al
0x14004a619  mov     [rbx+7Ch], eax
0x14004a61c  movzx   eax, cx
0x14004a61f  mov     [rbx+80h], eax
0x14004a625  mov     [rsi+0Ah], cx
0x14004a629  mov     rbp, [rbx+58h]
0x14004a62d  test    rbp, rbp
0x14004a630  jnz     short loc_14004A661
0x14004a632  mov     [rsi+4], dil
0x14004a636  mov     rax, [rbx+50h]
0x14004a63a  mov     [rbx+58h], rax
0x14004a63e  xor     eax, eax
0x14004a640  mov     [rbx+79h], dil
0x14004a644  mov     qword ptr [rbx+68h], 0
0x14004a64c  add     rsp, 38h
0x14004a650  pop     rdi
0x14004a651  pop     rsi
0x14004a652  pop     rbp
0x14004a653  pop     rbx
0x14004a654  retn
0x14004a656  mov     byte ptr [rbx+7Ah], 1; jumptable 000000014004A738 default case, cases 37-44,48-114,116,118-161
0x14004a65a  mov     eax, 0C000000Dh
0x14004a65f  jmp     short loc_14004A64C
0x14004a661  mov     rcx, [rbx+50h]
0x14004a665  mov     eax, edx
0x14004a667  add     rax, rcx
0x14004a66a  cmp     rax, [rbx+28h]
0x14004a66e  jnb     short loc_14004A65A
0x14004a670  test    edx, edx
0x14004a672  jz      short loc_14004A6E4
0x14004a674  mov     [rsp+58h+arg_0], r14
0x14004a679  lea     esi, [rdx-1]
0x14004a67c  mov     r14d, esi
0x14004a67f  and     r14d, r9d
0x14004a682  mov     rdx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004a689  lea     rax, WPP_GLOBAL_Control
0x14004a690  cmp     rdx, rax
0x14004a693  jz      short loc_14004A6B5
0x14004a695  test    dword ptr [rdx+2Ch], 400h
0x14004a69c  jz      short loc_14004A6B5
0x14004a69e  and     ecx, esi
0x14004a6a0  mov     [rsp+58h+var_30], r14d
0x14004a6a5  mov     r9d, ecx
0x14004a6a8  mov     [rsp+58h+var_38], esi
0x14004a6ac  mov     rcx, [rdx+18h]
0x14004a6b0  call    WPP_SF_DLL
0x14004a6b5  mov     rcx, [rbx+50h]
0x14004a6b9  mov     edx, r14d
0x14004a6bc  mov     r14, [rsp+58h+arg_0]
0x14004a6c1  mov     eax, esi
0x14004a6c3  and     rax, rcx
0x14004a6c6  mov     r8d, esi
0x14004a6c9  cmp     rax, rdx
0x14004a6cc  jz      short loc_14004A6E4
0x14004a6ce  mov     byte ptr [rcx], 2Ch ; ','
0x14004a6d1  inc     qword ptr [rbx+50h]
0x14004a6d5  mov     rcx, [rbx+50h]
0x14004a6d9  mov     rax, rcx
0x14004a6dc  and     rax, r8
0x14004a6df  cmp     rax, rdx
0x14004a6e2  jnz     short loc_14004A6CE
0x14004a6e4  mov     [rbp+1], dil
0x14004a6e8  mov     byte ptr [rbp+2], 0
0x14004a6ec  movzx   ecx, word ptr [rbx+50h]
0x14004a6f0  sub     cx, [rbx+20h]
0x14004a6f4  mov     [rbp+3], cx
0x14004a6f8  jmp     loc_14004A636
0x14004a6fd  cmp     byte ptr [rcx+7Bh], 0
0x14004a701  jz      loc_14004A5BA
0x14004a707  call    MRxSmbSetInitialSMB
0x14004a70c  jmp     loc_14004A5BA
0x14004a711  add     eax, 0FFFFFFDCh; switch 127 cases
0x14004a714  cmp     eax, 7Eh
0x14004a717  ja      def_14004A738; jumptable 000000014004A738 default case, cases 37-44,48-114,116,118-161
0x14004a71d  lea     rdx, cs:140000000h
0x14004a724  cdqe
0x14004a726  movzx   eax, ds:(byte_14001B208 - 140000000h)[rdx+rax]
0x14004a72e  mov     ecx, ds:(jpt_14004A738 - 140000000h)[rdx+rax*4]
0x14004a735  add     rcx, rdx
0x14004a738  jmp     rcx; switch jump
0x14004a73e  mov     byte ptr [rbx+7Ah], 4
0x14004a742  jmp     loc_14004A65A
```
