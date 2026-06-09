# CFileRecord::Commit(void)

- ea: `0x180007c08`
- end: `0x180007d55`
- name: `?Commit@CFileRecord@@QEAAJXZ`
- size: `333`
- prototype: `__int64 __fastcall(__int64 **this)`
- caller_count: `9`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c450`
- `0x18000cafc`
- `0x18000d4f4`
- `0x180010de8`
- `0x180013e14`
- `0x180016da0`
- `0x180017290`
- `0x18001cb74`
- `0x18001eaf0`

## callees

- `0x180007c08`
- `0x180007ecc`
- `0x180008244`
- `0x180009258`
- `0x18000935c`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CFileRecord::Commit(__int64 **this)
{
  _DWORD *v2; // rsi
  __int64 *v3; // rcx
  __int64 v4; // rax
  int v5; // edx
  int v6; // r9d
  int v7; // r10d
  __int64 *v8; // r11
  __int64 v9; // r8
  int v10; // eax
  unsigned int v11; // edi
  int v13; // eax

  v2 = this + 2;
  v3 = *this;
  v4 = *v3;
  v5 = *((_DWORD *)this + 16);
  v6 = *((_DWORD *)this + 15);
  v7 = *((_DWORD *)this + 14);
  v8 = this[6];
  v9 = *((unsigned __int16 *)this + 20);
  if ( *v2 != -1 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *, _QWORD, _WORD, __int64 *, int, int, int))(v4 + 144))(
            v3,
            (unsigned int)*v2,
            this[3],
            (unsigned __int16)v9,
            *((_WORD *)this + 21),
            v8,
            v7,
            v6,
            v5);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids,
          (unsigned int)*v2,
          v10);
      return v11;
    }
    CCatalogStatistics::DecrementFileRecordCount(this[1], *((unsigned __int16 *)this + 36));
LABEL_7:
    CCatalogStatistics::IncrementFileRecordCount(this[1], *((unsigned __int16 *)this + 20));
    *((_WORD *)this + 36) = *((_WORD *)this + 20);
    *((_DWORD *)this + 19) = 0;
    return v11;
  }
  v13 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64, _QWORD, __int64 *, int, int, int, _DWORD *))(v4 + 136))(
          v3,
          this[3],
          v9,
          *((unsigned __int16 *)this + 21),
          v8,
          v7,
          v6,
          v5,
          v2);
  v11 = v13;
  if ( v13 >= 0 )
    goto LABEL_7;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids,
      (unsigned int)this[3],
      v13);
  return v11;
}

```

## disassembly

```asm
0x180007c08  mov     [rsp+arg_0], rbx
0x180007c0d  mov     [rsp+arg_8], rsi
0x180007c12  push    rdi
0x180007c13  sub     rsp, 50h
0x180007c17  mov     rbx, rcx
0x180007c1a  lea     rsi, [rcx+10h]
0x180007c1e  mov     rcx, [rcx]
0x180007c21  mov     rax, [rcx]
0x180007c24  mov     edx, [rbx+40h]
0x180007c27  mov     r9d, [rbx+3Ch]
0x180007c2b  mov     r10d, [rbx+38h]
0x180007c2f  mov     r11, [rbx+30h]
0x180007c33  movzx   edi, word ptr [rbx+2Ah]
0x180007c37  movzx   r8d, word ptr [rbx+28h]
0x180007c3c  cmp     dword ptr [rsi], 0FFFFFFFFh
0x180007c3f  jz      loc_180007CEB
0x180007c45  mov     dword ptr [rsp+58h+var_18], edx
0x180007c49  mov     [rsp+58h+var_20], r9d
0x180007c4e  mov     [rsp+58h+var_28], r10d
0x180007c53  mov     [rsp+58h+var_30], r11
0x180007c58  mov     word ptr [rsp+58h+var_38], di
0x180007c5d  movzx   r9d, r8w
0x180007c61  mov     r8, [rbx+18h]
0x180007c65  mov     edx, [rsi]
0x180007c67  mov     rax, [rax+90h]
0x180007c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c73  mov     edi, eax
0x180007c75  test    eax, eax
0x180007c77  jns     short loc_180007CB0
0x180007c79  lea     rdx, WPP_GLOBAL_Control
0x180007c80  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c87  cmp     rcx, rdx
0x180007c8a  jz      short loc_180007CD9
0x180007c8c  test    byte ptr [rcx+1Ch], 1
0x180007c90  jz      short loc_180007CD9
0x180007c92  mov     edx, 0Fh
0x180007c97  mov     dword ptr [rsp+58h+var_38], eax
0x180007c9b  mov     r9d, [rsi]
0x180007c9e  lea     r8, WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids
0x180007ca5  mov     rcx, [rcx+10h]
0x180007ca9  call    WPP_SF_dd
0x180007cae  jmp     short loc_180007CD9
0x180007cb0  movzx   edx, word ptr [rbx+48h]
0x180007cb4  mov     rcx, [rbx+8]
0x180007cb8  call    ?DecrementFileRecordCount@CCatalogStatistics@@QEAAXW4FhFileState@@@Z; CCatalogStatistics::DecrementFileRecordCount(FhFileState)
0x180007cbd  movzx   edx, word ptr [rbx+28h]
0x180007cc1  mov     rcx, [rbx+8]
0x180007cc5  call    ?IncrementFileRecordCount@CCatalogStatistics@@QEAAXW4FhFileState@@@Z; CCatalogStatistics::IncrementFileRecordCount(FhFileState)
0x180007cca  movzx   eax, word ptr [rbx+28h]
0x180007cce  mov     [rbx+48h], ax
0x180007cd2  mov     dword ptr [rbx+4Ch], 0
0x180007cd9  mov     eax, edi
0x180007cdb  mov     rbx, [rsp+58h+arg_0]
0x180007ce0  mov     rsi, [rsp+58h+arg_8]
0x180007ce5  add     rsp, 50h
0x180007ce9  pop     rdi
0x180007cea  retn
0x180007ceb  mov     [rsp+58h+var_18], rsi
0x180007cf0  mov     [rsp+58h+var_20], edx
0x180007cf4  mov     [rsp+58h+var_28], r9d
0x180007cf9  mov     dword ptr [rsp+58h+var_30], r10d
0x180007cfe  mov     [rsp+58h+var_38], r11
0x180007d03  movzx   r9d, di
0x180007d07  mov     rdx, [rbx+18h]
0x180007d0b  mov     rax, [rax+88h]
0x180007d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d17  mov     edi, eax
0x180007d19  test    eax, eax
0x180007d1b  jns     short loc_180007CBD
0x180007d1d  lea     rdx, WPP_GLOBAL_Control
0x180007d24  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d2b  cmp     rcx, rdx
0x180007d2e  jz      short loc_180007CD9
0x180007d30  test    byte ptr [rcx+1Ch], 1
0x180007d34  jz      short loc_180007CD9
0x180007d36  mov     edx, 10h
0x180007d3b  mov     dword ptr [rsp+58h+var_38], eax
0x180007d3f  mov     r9, [rbx+18h]
0x180007d43  lea     r8, WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids
0x180007d4a  mov     rcx, [rcx+10h]
0x180007d4e  call    WPP_SF_Sd
0x180007d53  jmp     short loc_180007CD9
```
