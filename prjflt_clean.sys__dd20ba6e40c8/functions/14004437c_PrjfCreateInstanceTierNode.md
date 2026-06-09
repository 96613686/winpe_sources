# PrjfCreateInstanceTierNode

- ea: `0x14004437c`
- end: `0x140044501`
- name: `PrjfCreateInstanceTierNode`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140044cec`

## callees

- `0x14000d008`
- `0x14000d128`
- `0x14004437c`
- `0x140044af0`
- `0x140044c20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400444db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400444db`
- `ntoskrnl!ExAllocatePool2` at `0x1400443a8`
- `ntoskrnl!ExAllocatePool2` at `0x1400443a8`

## pseudocode

```c
__int64 __fastcall PrjfCreateInstanceTierNode(__int64 a1, _QWORD *a2)
{
  _QWORD *Pool2; // rax
  int v5; // edx
  int v6; // r8d
  _QWORD *v7; // rbx
  int PathTree; // edi
  int v9; // edx
  int v10; // r8d
  void *v11; // rcx

  *a2 = 0;
  Pool2 = (_QWORD *)ExAllocatePool2(256, 24, 1835944528);
  v7 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = a1;
    Pool2[1] = 0;
    Pool2[2] = 0;
    PathTree = PrjfCreatePathTree(Pool2 + 1);
    if ( PathTree >= 0 )
    {
      *a2 = v7;
      return 0;
    }
    else
    {
      if ( (BYTE2(xmmword_14001A3D0) & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = BYTE2(xmmword_14001A3D0) & 0x10;
        LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          532,
          v9,
          v10,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          20,
          36,
          (__int64)&WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
          39,
          PathTree);
      }
      v11 = (void *)v7[1];
      if ( v11 )
        PrjfDeletePathTree(v11);
      ExFreePoolWithTag(v7, 0x6D6E4A50u);
    }
  }
  else
  {
    if ( (BYTE2(xmmword_14001A3D0) & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = BYTE2(xmmword_14001A3D0) & 0x10;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        532,
        v5,
        v6,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        20,
        35,
        (__int64)&WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
        18);
    }
    return (unsigned int)-1073741670;
  }
  return (unsigned int)PathTree;
}

```

## disassembly

```asm
0x14004437c  mov     [rsp+arg_0], rbx
0x140044381  mov     [rsp+arg_8], rsi
0x140044386  push    rdi
0x140044387  sub     rsp, 60h
0x14004438b  mov     rsi, rdx
0x14004438e  mov     qword ptr [rdx], 0
0x140044395  mov     rdi, rcx
0x140044398  mov     edx, 18h
0x14004439d  mov     ecx, 100h
0x1400443a2  mov     r8d, 6D6E4A50h
0x1400443a8  call    cs:__imp_ExAllocatePool2
0x1400443af  nop     dword ptr [rax+rax+00h]
0x1400443b4  mov     rbx, rax
0x1400443b7  test    rax, rax
0x1400443ba  jnz     short loc_140044431
0x1400443bc  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x1400443c2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400443c9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400443d0  setnz   r8b
0x1400443d4  and     dl, 10h
0x1400443d7  jnz     short loc_1400443DE
0x1400443d9  test    r8b, r8b
0x1400443dc  jz      short loc_140044427
0x1400443de  mov     r9, cs:WPP_GLOBAL_Control
0x1400443e5  lea     rax, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400443ec  mov     [rsp+68h+var_20], 412h
0x1400443f4  mov     ecx, 214h
0x1400443f9  mov     [rsp+68h+var_28], rax
0x1400443fe  lea     rax, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x140044405  mov     [rsp+68h+var_30], rax
0x14004440a  mov     r9, [r9+40h]
0x14004440e  mov     [rsp+68h+var_38], 23h ; '#'
0x140044415  mov     [rsp+68h+var_40], 14h
0x14004441d  mov     [rsp+68h+var_48], 2
0x140044422  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140044427  mov     edi, 0C000009Ah
0x14004442c  jmp     loc_1400444EE
0x140044431  lea     rcx, [rax+8]
0x140044435  mov     [rax], rdi
0x140044438  mov     qword ptr [rcx], 0
0x14004443f  mov     qword ptr [rax+10h], 0
0x140044447  call    PrjfCreatePathTree
0x14004444c  mov     edi, eax
0x14004444e  test    eax, eax
0x140044450  jns     loc_1400444E9
0x140044456  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x14004445c  lea     rax, WPP_RECORDER_INITIALIZED
0x140044463  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004446a  setnz   r8b
0x14004446e  and     dl, 10h
0x140044471  jnz     short loc_140044478
0x140044473  test    r8b, r8b
0x140044476  jz      short loc_1400444C5
0x140044478  mov     r9, cs:WPP_GLOBAL_Control
0x14004447f  lea     rax, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140044486  mov     [rsp+68h+var_18], edi
0x14004448a  mov     ecx, 214h
0x14004448f  mov     [rsp+68h+var_20], 427h
0x140044497  mov     [rsp+68h+var_28], rax
0x14004449c  lea     rax, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x1400444a3  mov     r9, [r9+40h]
0x1400444a7  mov     [rsp+68h+var_30], rax
0x1400444ac  mov     [rsp+68h+var_38], 24h ; '$'
0x1400444b3  mov     [rsp+68h+var_40], 14h
0x1400444bb  mov     [rsp+68h+var_48], 2
0x1400444c0  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400444c5  mov     rcx, [rbx+8]; P
0x1400444c9  test    rcx, rcx
0x1400444cc  jz      short loc_1400444D3
0x1400444ce  call    PrjfDeletePathTree
0x1400444d3  mov     edx, 6D6E4A50h; Tag
0x1400444d8  mov     rcx, rbx; P
0x1400444db  call    cs:__imp_ExFreePoolWithTag
0x1400444e2  nop     dword ptr [rax+rax+00h]
0x1400444e7  jmp     short loc_1400444EE
0x1400444e9  mov     [rsi], rbx
0x1400444ec  xor     edi, edi
0x1400444ee  mov     rbx, [rsp+68h+arg_0]
0x1400444f3  mov     eax, edi
0x1400444f5  mov     rsi, [rsp+68h+arg_8]
0x1400444fa  add     rsp, 60h
0x1400444fe  pop     rdi
0x1400444ff  retn
```
