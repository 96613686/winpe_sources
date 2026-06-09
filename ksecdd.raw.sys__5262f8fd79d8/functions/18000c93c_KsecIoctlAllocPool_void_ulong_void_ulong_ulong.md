# KsecIoctlAllocPool(void *,ulong,void *,ulong,ulong *)

- ea: `0x18000c93c`
- end: `0x18000cbae`
- name: `?KsecIoctlAllocPool@@YAJPEAXK0KPEAK@Z`
- size: `626`
- prototype: `int(void *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800053e0`

## callees

- `0x1800021bc`
- `0x180005718`
- `0x180007bd8`
- `0x18000b298`
- `0x18000c93c`
- `0x18000de6c`
- `0x18000e044`
- `0x18001f584`
- `0x18001f5c0`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000c9c1`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000c9c1`
- `ntoskrnl!ProbeForRead` at `0x18000c9e2`
- `ntoskrnl!ProbeForRead` at `0x18000c9e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000cad3`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000cb4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000cad3`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000cb4c`
- `ntoskrnl!ExAllocatePool2` at `0x18000ca21`
- `ntoskrnl!ExAllocatePool2` at `0x18000ca21`

## pseudocode

```c
__int64 __fastcall KsecIoctlAllocPool(void *a1, __int64 a2, void *a3, unsigned int a4, unsigned int *a5)
{
  __int64 v7; // r8
  unsigned __int8 *Pool2; // rax
  unsigned __int8 *v9; // rbx
  int inserted; // edi
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned __int8 *P; // [rsp+30h] [rbp-18h]
  __int64 ULong64FromUser; // [rsp+50h] [rbp+8h]

  if ( a1 && a3 && (_DWORD)a2 == 8 )
  {
    if ( a4 >= 8 )
    {
      if ( ((unsigned __int8)a1 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      ULong64FromUser = RtlReadULong64FromUser(a1, a2, (unsigned int)a2, a1);
      ProbeForRead(a3, 8u, 8u);
      if ( HIDWORD(ULong64FromUser) == -1 )
      {
        v7 = 1399157579;
      }
      else if ( HIDWORD(ULong64FromUser) >= 0xA )
      {
        v7 = 1516598091;
      }
      else
      {
        v7 = KsecPackageTags[HIDWORD(ULong64FromUser)];
      }
      Pool2 = (unsigned __int8 *)ExAllocatePool2(256, (unsigned int)ULong64FromUser, v7);
      v9 = Pool2;
      P = Pool2;
      if ( Pool2 )
      {
        inserted = KsecInsertValidAddress(Pool2, ULong64FromUser);
        if ( inserted >= 0 )
        {
          RtlWriteULong64ToUser(a3, v9);
          *a5 = 8;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0 )
          {
            WPP_SF_dqL(*((_QWORD *)WPP_GLOBAL_Control + 3), v11, v12, HIDWORD(ULong64FromUser), v9, ULong64FromUser, P);
          }
          return 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 14, &WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids);
          ExFreePoolWithTag(v9, 0);
          return (unsigned int)inserted;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_LL(*((_QWORD *)WPP_GLOBAL_Control + 3), 13, &WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids);
        return 3221225626LL;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          (unsigned int)(a2 + 4),
          &WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids);
      return 3221225507LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_qqL(*((_QWORD *)WPP_GLOBAL_Control + 3), 11, (unsigned int)a2, a1, a3, a2);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x18000c93c  mov     [rsp+arg_8], rbx
0x18000c941  mov     [rsp+arg_10], rsi
0x18000c946  push    rdi
0x18000c947  sub     rsp, 40h
0x18000c94b  mov     r10d, r9d
0x18000c94e  mov     rsi, r8
0x18000c951  mov     r8d, edx
0x18000c954  mov     r9, rcx
0x18000c957  mov     qword ptr [rsp+48h+arg_0], 0
0x18000c960  test    rcx, rcx
0x18000c963  jz      loc_18000CB66
0x18000c969  test    rsi, rsi
0x18000c96c  jz      loc_18000CB66
0x18000c972  cmp     edx, 8
0x18000c975  jnz     loc_18000CB66
0x18000c97b  cmp     r10d, edx
0x18000c97e  jnb     short loc_18000C9BB
0x18000c980  lea     rax, WPP_GLOBAL_Control
0x18000c987  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c98e  cmp     rcx, rax
0x18000c991  jz      short loc_18000C9B1
0x18000c993  mov     eax, [rcx+2Ch]
0x18000c996  test    al, 1
0x18000c998  jz      short loc_18000C9B1
0x18000c99a  lea     edx, [r8+4]
0x18000c99e  mov     r9d, r10d
0x18000c9a1  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x18000c9a8  mov     rcx, [rcx+18h]
0x18000c9ac  call    WPP_SF_D
0x18000c9b1  mov     eax, 0C0000023h
0x18000c9b6  jmp     loc_18000CB9D
0x18000c9bb  test    r9b, 3
0x18000c9bf  jz      short loc_18000C9CD
0x18000c9c1  call    cs:__imp_ExRaiseDatatypeMisalignment
0x18000c9c8  nop     dword ptr [rax+rax+00h]
0x18000c9cd  call    RtlReadULong64FromUser
0x18000c9d2  mov     qword ptr [rsp+48h+arg_0], rax
0x18000c9d7  mov     edx, 8; Length
0x18000c9dc  mov     r8d, edx; Alignment
0x18000c9df  mov     rcx, rsi; Address
0x18000c9e2  call    cs:__imp_ProbeForRead
0x18000c9e9  nop     dword ptr [rax+rax+00h]
0x18000c9ee  nop
0x18000c9ef  mov     eax, [rsp+54h]
0x18000c9f3  cmp     eax, 0FFFFFFFFh
0x18000c9f6  jnz     short loc_18000CA00
0x18000c9f8  mov     r8d, 5365734Bh
0x18000c9fe  jmp     short loc_18000CA18
0x18000ca00  cmp     eax, 0Ah
0x18000ca03  jnb     short loc_18000CA12
0x18000ca05  lea     r8, ?KsecPackageTags@@3PAKA; ulong near * KsecPackageTags
0x18000ca0c  mov     r8d, [r8+rax*4]
0x18000ca10  jmp     short loc_18000CA18
0x18000ca12  mov     r8d, 5A65734Bh
0x18000ca18  mov     edx, [rsp+48h+arg_0]
0x18000ca1c  mov     ecx, 100h
0x18000ca21  call    cs:__imp_ExAllocatePool2
0x18000ca28  nop     dword ptr [rax+rax+00h]
0x18000ca2d  mov     rbx, rax
0x18000ca30  mov     [rsp+48h+P], rax
0x18000ca35  test    rax, rax
0x18000ca38  jnz     short loc_18000CA7E
0x18000ca3a  lea     rax, WPP_GLOBAL_Control
0x18000ca41  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca48  cmp     rcx, rax
0x18000ca4b  jz      short loc_18000CA74
0x18000ca4d  mov     eax, [rcx+2Ch]
0x18000ca50  test    al, 1
0x18000ca52  jz      short loc_18000CA74
0x18000ca54  lea     edx, [rbx+0Dh]
0x18000ca57  mov     eax, [rsp+54h]
0x18000ca5b  mov     dword ptr [rsp+48h+var_28], eax
0x18000ca5f  mov     r9d, [rsp+48h+arg_0]
0x18000ca64  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x18000ca6b  mov     rcx, [rcx+18h]
0x18000ca6f  call    WPP_SF_LL
0x18000ca74  mov     eax, 0C000009Ah
0x18000ca79  jmp     loc_18000CB9D
0x18000ca7e  mov     r9d, [rsp+54h]
0x18000ca83  mov     r8d, 4
0x18000ca89  mov     edx, [rsp+48h+arg_0]; unsigned int
0x18000ca8d  mov     rcx, rbx; unsigned __int8 *
0x18000ca90  call    KsecInsertValidAddress
0x18000ca95  mov     edi, eax
0x18000ca97  test    eax, eax
0x18000ca99  jns     short loc_18000CAE6
0x18000ca9b  lea     rax, WPP_GLOBAL_Control
0x18000caa2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000caa9  cmp     rcx, rax
0x18000caac  jz      short loc_18000CACE
0x18000caae  mov     edx, [rcx+2Ch]
0x18000cab1  test    dl, 1
0x18000cab4  jz      short loc_18000CACE
0x18000cab6  mov     edx, 0Eh
0x18000cabb  mov     r9d, edi
0x18000cabe  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x18000cac5  mov     rcx, [rcx+18h]
0x18000cac9  call    WPP_SF_D
0x18000cace  xor     edx, edx; Tag
0x18000cad0  mov     rcx, rbx; P
0x18000cad3  call    cs:__imp_ExFreePoolWithTag
0x18000cada  nop     dword ptr [rax+rax+00h]
0x18000cadf  mov     eax, edi
0x18000cae1  jmp     loc_18000CB9D
0x18000cae6  mov     rdx, rbx
0x18000cae9  mov     rcx, rsi
0x18000caec  call    RtlWriteULong64ToUser
0x18000caf1  nop
0x18000caf2  mov     rax, [rsp+48h+arg_20]
0x18000caf7  mov     dword ptr [rax], 8
0x18000cafd  lea     rax, WPP_GLOBAL_Control
0x18000cb04  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb0b  cmp     rcx, rax
0x18000cb0e  jz      short loc_18000CB32
0x18000cb10  mov     eax, [rcx+2Ch]
0x18000cb13  test    al, 10h
0x18000cb15  jz      short loc_18000CB32
0x18000cb17  mov     eax, [rsp+48h+arg_0]
0x18000cb1b  mov     [rsp+48h+var_20], eax
0x18000cb1f  mov     [rsp+48h+var_28], rbx
0x18000cb24  mov     r9d, [rsp+54h]
0x18000cb29  mov     rcx, [rcx+18h]
0x18000cb2d  call    WPP_SF_dqL
0x18000cb32  xor     eax, eax
0x18000cb34  jmp     short loc_18000CB9D
0x18000cb36  mov     edx, 8
0x18000cb3b  mov     rcx, [rsp+48h+P]; unsigned __int8 *
0x18000cb40  call    KsecRemoveValidAddressCommon
0x18000cb45  xor     edx, edx; Tag
0x18000cb47  mov     rcx, [rsp+48h+P]; P
0x18000cb4c  call    cs:__imp_ExFreePoolWithTag
0x18000cb53  nop     dword ptr [rax+rax+00h]
0x18000cb58  mov     eax, 0C0000005h
0x18000cb5d  jmp     short loc_18000CB9D
0x18000cb5f  mov     eax, 0C0000005h
0x18000cb64  jmp     short loc_18000CB9D
0x18000cb66  lea     rax, WPP_GLOBAL_Control
0x18000cb6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb74  cmp     rcx, rax
0x18000cb77  jz      short loc_18000CB98
0x18000cb79  mov     eax, [rcx+2Ch]
0x18000cb7c  test    al, 1
0x18000cb7e  jz      short loc_18000CB98
0x18000cb80  mov     edx, 0Bh
0x18000cb85  mov     [rsp+48h+var_20], r8d
0x18000cb8a  mov     [rsp+48h+var_28], rsi
0x18000cb8f  mov     rcx, [rcx+18h]
0x18000cb93  call    WPP_SF_qqL
0x18000cb98  mov     eax, 0C000000Dh
0x18000cb9d  mov     rbx, [rsp+48h+arg_8]
0x18000cba2  mov     rsi, [rsp+48h+arg_10]
0x18000cba7  add     rsp, 40h
0x18000cbab  pop     rdi
0x18000cbac  retn
```
