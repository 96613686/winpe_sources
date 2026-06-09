# CScrubCheckpoint::WriteCheckpoint(_UNICODE_STRING const *)

- ea: `0x180017a80`
- end: `0x180017c99`
- name: `?WriteCheckpoint@CScrubCheckpoint@@QEAAJPEBU_UNICODE_STRING@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(CScrubCheckpoint *__hidden this, const struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18000fbc0`
- `0x1800273d8`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x180017a80`
- `0x180017ca0`
- `0x18001860c`
- `0x1800189c8`
- `0x1800375e2`

## string_xrefs

- `0x180017abb`: `CScrubCheckpoint::WriteCheckpoint`

## pseudocode

```c
__int64 __fastcall CScrubCheckpoint::WriteCheckpoint(CScrubCheckpoint *this, const struct _UNICODE_STRING *a2)
{
  __int64 v4; // r9
  int v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rdx
  const char *v9; // [rsp+A0h] [rbp-38h] BYREF
  int v10; // [rsp+A8h] [rbp-30h]

  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v9 = "CScrubCheckpoint::WriteCheckpoint";
  ++*(_WORD *)(v4 + 8);
  *(_QWORD *)(v4 + 16) = "CScrubCheckpoint::WriteCheckpoint";
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubCheckpoint::WriteCheckpoint");
  }
  if ( a2 )
  {
    v5 = CScrubCheckpoint::_EnsureCheckpointDataLength(this, a2->Length);
    v10 = v5;
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          &WPP_50cd40487cfb379966d33e670ff2d168_Traceguids,
          (unsigned int)v5);
      }
      goto LABEL_17;
    }
    memcpy_0((void *)(*((_QWORD *)this + 5) + 288LL), a2->Buffer, a2->Length);
    *(_WORD *)(*((_QWORD *)this + 5) + 280LL) = a2->Length;
  }
  *(_DWORD *)(*((_QWORD *)this + 5) + 4LL) |= 1u;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v7 = (_QWORD *)*((_QWORD *)this + 5);
    WPP_SF_ZZiiiiiiiIIIII(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (__int64)a2,
      v7[2],
      v7[3],
      v7[4],
      v7[10],
      v7[11],
      v7[12],
      v7[13],
      v7[5],
      v7[6],
      v7[7],
      v7[8],
      v7[9]);
  }
  v6 = CScrubCheckpoint::_WriteCheckpointInternal(this, 0);
  v10 = v6;
LABEL_17:
  CHResultImp::~CHResultImp((CHResultImp *)&v9);
  return v6;
}

```

## disassembly

```asm
0x180017a80  mov     r11, rsp
0x180017a83  push    rbx
0x180017a84  push    rbp
0x180017a85  push    rsi
0x180017a86  push    rdi
0x180017a87  push    r14
0x180017a89  sub     rsp, 0B0h
0x180017a90  mov     r8d, cs:_tls_index
0x180017a97  mov     rsi, rdx
0x180017a9a  mov     rax, gs:58h
0x180017aa3  mov     rdi, rcx
0x180017aa6  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180017aad  mov     ebp, 1
0x180017ab2  mov     edx, 8
0x180017ab7  mov     r9, [rax+r8*8]
0x180017abb  lea     r8, aCscrubcheckpoi_6; "CScrubCheckpoint::WriteCheckpoint"
0x180017ac2  mov     eax, 10h
0x180017ac7  mov     [r11-38h], r8
0x180017acb  add     [rdx+r9], bp
0x180017ad0  movzx   edx, word ptr [rdx+r9]
0x180017ad5  mov     [rax+r9], r8
0x180017ad9  cmp     dx, cx
0x180017adc  movzx   eax, cx
0x180017adf  cmovb   ax, dx
0x180017ae3  cmovb   cx, dx
0x180017ae7  mov     [r11-48h], ax
0x180017aec  xor     eax, eax
0x180017aee  mov     [r11-44h], eax
0x180017af2  mov     rax, cs:off_180047060; "                                       "...
0x180017af9  mov     [r11-40h], rax
0x180017afd  mov     [r11-46h], cx
0x180017b02  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b09  lea     r14, WPP_GLOBAL_Control
0x180017b10  cmp     rcx, r14
0x180017b13  jz      short loc_180017B36
0x180017b15  test    [rcx+1Ch], bpl
0x180017b19  jz      short loc_180017B36
0x180017b1b  cmp     byte ptr [rcx+19h], 5
0x180017b1f  jb      short loc_180017B36
0x180017b21  mov     rcx, [rcx+10h]; LoggerHandle
0x180017b25  lea     edx, [rbp+0Ch]
0x180017b28  lea     r9, [r11-48h]
0x180017b2c  mov     [rsp+0D8h+var_B8], r8; __int64
0x180017b31  call    WPP_SF_aZs
0x180017b36  test    rsi, rsi
0x180017b39  jz      short loc_180017BBA
0x180017b3b  movzx   edx, word ptr [rsi]; unsigned __int16
0x180017b3e  mov     rcx, rdi; this
0x180017b41  call    ?_EnsureCheckpointDataLength@CScrubCheckpoint@@AEAAJG@Z; CScrubCheckpoint::_EnsureCheckpointDataLength(ushort)
0x180017b46  mov     [rsp+0D8h+var_30], eax
0x180017b4d  mov     ebx, eax
0x180017b4f  test    eax, eax
0x180017b51  jns     short loc_180017B94
0x180017b53  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b5a  cmp     rcx, r14
0x180017b5d  jz      loc_180017C7C
0x180017b63  test    [rcx+1Ch], bpl
0x180017b67  jz      loc_180017C7C
0x180017b6d  cmp     byte ptr [rcx+19h], 2
0x180017b71  jb      loc_180017C7C
0x180017b77  mov     rcx, [rcx+10h]
0x180017b7b  lea     r8, WPP_50cd40487cfb379966d33e670ff2d168_Traceguids
0x180017b82  mov     edx, 18h
0x180017b87  mov     r9d, eax
0x180017b8a  call    WPP_SF_d
0x180017b8f  jmp     loc_180017C7C
0x180017b94  mov     rcx, [rdi+28h]
0x180017b98  movzx   r8d, word ptr [rsi]; Size
0x180017b9c  add     rcx, 120h; void *
0x180017ba3  mov     rdx, [rsi+8]; Src
0x180017ba7  call    memcpy_0
0x180017bac  mov     rcx, [rdi+28h]
0x180017bb0  movzx   eax, word ptr [rsi]
0x180017bb3  mov     [rcx+118h], ax
0x180017bba  mov     rax, [rdi+28h]
0x180017bbe  or      [rax+4], ebp
0x180017bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180017bc8  cmp     rcx, r14
0x180017bcb  jz      loc_180017C69
0x180017bd1  test    [rcx+1Ch], bpl
0x180017bd5  jz      loc_180017C69
0x180017bdb  cmp     byte ptr [rcx+19h], 4
0x180017bdf  jb      loc_180017C69
0x180017be5  mov     rdx, [rdi+28h]
0x180017be9  mov     r9, [rdi]
0x180017bec  mov     rcx, [rcx+10h]; LoggerHandle
0x180017bf0  mov     rax, [rdx+48h]
0x180017bf4  mov     qword ptr [rsp+0D8h+var_58], rax; char
0x180017bfc  mov     rax, [rdx+40h]
0x180017c00  mov     qword ptr [rsp+0D8h+var_60], rax; char
0x180017c05  mov     rax, [rdx+38h]
0x180017c09  mov     qword ptr [rsp+0D8h+var_68], rax; char
0x180017c0e  mov     rax, [rdx+30h]
0x180017c12  mov     qword ptr [rsp+0D8h+var_70], rax; char
0x180017c17  mov     rax, [rdx+28h]
0x180017c1b  mov     qword ptr [rsp+0D8h+var_78], rax; char
0x180017c20  mov     rax, [rdx+68h]
0x180017c24  mov     qword ptr [rsp+0D8h+var_80], rax; char
0x180017c29  mov     rax, [rdx+60h]
0x180017c2d  mov     qword ptr [rsp+0D8h+var_88], rax; char
0x180017c32  mov     rax, [rdx+58h]
0x180017c36  mov     qword ptr [rsp+0D8h+var_90], rax; char
0x180017c3b  mov     rax, [rdx+50h]
0x180017c3f  mov     qword ptr [rsp+0D8h+var_98], rax; char
0x180017c44  mov     rax, [rdx+20h]
0x180017c48  mov     qword ptr [rsp+0D8h+var_A0], rax; char
0x180017c4d  mov     rax, [rdx+18h]
0x180017c51  mov     qword ptr [rsp+0D8h+var_A8], rax; char
0x180017c56  mov     rax, [rdx+10h]
0x180017c5a  mov     qword ptr [rsp+0D8h+var_B0], rax; char
0x180017c5f  mov     [rsp+0D8h+var_B8], rsi; __int64
0x180017c64  call    WPP_SF_ZZiiiiiiiIIIII
0x180017c69  xor     edx, edx; unsigned int
0x180017c6b  mov     rcx, rdi; this
0x180017c6e  call    ?_WriteCheckpointInternal@CScrubCheckpoint@@AEAAJK@Z; CScrubCheckpoint::_WriteCheckpointInternal(ulong)
0x180017c73  mov     ebx, eax
0x180017c75  mov     [rsp+0D8h+var_30], eax
0x180017c7c  lea     rcx, [rsp+0D8h+var_38]; this
0x180017c84  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180017c89  mov     eax, ebx
0x180017c8b  add     rsp, 0B0h
0x180017c92  pop     r14
0x180017c94  pop     rdi
0x180017c95  pop     rsi
0x180017c96  pop     rbp
0x180017c97  pop     rbx
0x180017c98  retn
```
