# PrjfCreatePathTierNode

- ea: `0x140044794`
- end: `0x140044ae9`
- name: `PrjfCreatePathTierNode`
- size: `853`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140044cec`

## callees

- `0x14000d008`
- `0x14000d128`
- `0x14000d754`
- `0x14003775c`
- `0x140044794`
- `0x140044af0`
- `0x140044c20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140044ac4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044ad8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044ac4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044ad8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400449d9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400449d9`
- `ntoskrnl!ExAllocatePool2` at `0x1400447d0`
- `ntoskrnl!ExAllocatePool2` at `0x1400447d0`

## pseudocode

```c
__int64 __fastcall PrjfCreatePathTierNode(
        PCUNICODE_STRING SourceString,
        int a2,
        char a3,
        __int64 a4,
        int a5,
        WCHAR *a6,
        struct _UNICODE_STRING **a7)
{
  int v10; // edx
  struct _UNICODE_STRING *Pool2; // rbx
  __int64 v12; // r8
  __int64 v13; // r9
  int UnicodeString; // edi
  __int16 v15; // ax
  int v16; // edx
  int v17; // r8d
  PWSTR *p_Buffer; // rcx
  int v20; // edx
  int v21; // r8d
  PWSTR v22; // rcx
  PWSTR Buffer; // rcx
  _WORD v24[2]; // [rsp+60h] [rbp-58h] BYREF
  int v25; // [rsp+64h] [rbp-54h]
  __int64 v26; // [rsp+68h] [rbp-50h]

  *a7 = 0;
  Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(256, 64, 1835944528);
  if ( !Pool2 )
  {
    if ( (BYTE2(xmmword_14001A3D0) & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = BYTE2(xmmword_14001A3D0) & 0x10;
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        532,
        v10,
        v12,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        20,
        38,
        (__int64)&WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
        82);
    }
    return (unsigned int)-1073741670;
  }
  if ( (a2 & 1) != 0 && (a2 & 0x10) != 0 )
  {
    v15 = *(_WORD *)(a4 + 2);
    if ( v15 )
    {
      v25 = 0;
      v24[1] = v15;
      v24[0] = v15;
      v26 = a4 + 4;
      UnicodeString = -1073741811;
      if ( (BYTE2(xmmword_14001A3D0) & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = BYTE2(xmmword_14001A3D0) & 0x10;
        LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          532,
          v10,
          v12,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          20,
          39,
          (__int64)&WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
          108,
          13,
          (__int64)v24);
      }
      goto LABEL_17;
    }
    Pool2[2].Buffer = 0;
    *(_DWORD *)&Pool2[2].Length = 0;
  }
  else
  {
    Pool2[2].MaximumLength = SourceString->MaximumLength;
    UnicodeString = PrjfAllocateUnicodeString(1852197456, &Pool2[2], v12, v13);
    if ( UnicodeString < 0 )
    {
      if ( (BYTE2(xmmword_14001A3D0) & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = BYTE2(xmmword_14001A3D0) & 0x10;
        LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          532,
          v16,
          v17,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          20,
          40,
          (__int64)&WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
          124,
          UnicodeString);
      }
LABEL_17:
      if ( !a3 )
      {
LABEL_33:
        Buffer = Pool2[2].Buffer;
        if ( Buffer )
          ExFreePoolWithTag(Buffer, 0x6D6E4A50u);
        ExFreePoolWithTag(Pool2, 0x6D6E4A50u);
        return (unsigned int)UnicodeString;
      }
LABEL_31:
      v22 = Pool2[3].Buffer;
      if ( v22 )
        PrjfDeletePathTree(v22);
      goto LABEL_33;
    }
    RtlCopyUnicodeString(Pool2 + 2, SourceString);
  }
  *(_DWORD *)&Pool2->Length = a2;
  if ( a3 )
  {
    p_Buffer = &Pool2[3].Buffer;
    if ( (a2 & 0x10) != 0 )
    {
      *p_Buffer = a6;
    }
    else
    {
      UnicodeString = PrjfCreatePathTree(p_Buffer);
      if ( UnicodeString < 0 )
      {
        if ( (BYTE2(xmmword_14001A3D0) & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v20) = BYTE2(xmmword_14001A3D0) & 0x10;
          LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            532,
            v20,
            v21,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            20,
            41,
            (__int64)&WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
            152,
            UnicodeString);
        }
        goto LABEL_31;
      }
    }
  }
  if ( (a2 & 1) != 0 )
    *(_DWORD *)&Pool2[3].Length = a5;
  *a7 = Pool2;
  return 0;
}

```

## disassembly

```asm
0x140044794  mov     [rsp+arg_10], r8b
0x140044799  push    rbx
0x14004479a  push    rbp
0x14004479b  push    rsi
0x14004479c  push    rdi
0x14004479d  push    r12
0x14004479f  push    r13
0x1400447a1  push    r14
0x1400447a3  push    r15
0x1400447a5  sub     rsp, 78h
0x1400447a9  mov     r12, [rsp+0B8h+arg_30]
0x1400447b1  xor     r15d, r15d
0x1400447b4  mov     r14d, edx
0x1400447b7  mov     r13, rcx
0x1400447ba  mov     ecx, 100h
0x1400447bf  mov     r8d, 6D6E4A50h
0x1400447c5  mov     rdi, r9
0x1400447c8  lea     edx, [r15+40h]
0x1400447cc  mov     [r12], r15
0x1400447d0  call    cs:__imp_ExAllocatePool2
0x1400447d7  nop     dword ptr [rax+rax+00h]
0x1400447dc  mov     rbx, rax
0x1400447df  test    rax, rax
0x1400447e2  jnz     short loc_140044859
0x1400447e4  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x1400447ea  lea     rax, WPP_RECORDER_INITIALIZED
0x1400447f1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400447f8  setnz   r8b
0x1400447fc  and     dl, 10h
0x1400447ff  jnz     short loc_140044806
0x140044801  test    r8b, r8b
0x140044804  jz      short loc_14004484F
0x140044806  mov     r9, cs:WPP_GLOBAL_Control
0x14004480d  lea     rax, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140044814  mov     [rsp+0B8h+var_70], 652h
0x14004481c  mov     ecx, 214h
0x140044821  mov     [rsp+0B8h+var_78], rax
0x140044826  lea     rax, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x14004482d  mov     [rsp+0B8h+var_80], rax
0x140044832  mov     r9, [r9+40h]
0x140044836  mov     [rsp+0B8h+var_88], 26h ; '&'
0x14004483d  mov     [rsp+0B8h+var_90], 14h
0x140044845  mov     [rsp+0B8h+var_98], 2
0x14004484a  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14004484f  mov     edi, 0C000009Ah
0x140044854  jmp     loc_140044A1A
0x140044859  mov     esi, r14d
0x14004485c  mov     ebp, r14d
0x14004485f  and     esi, 10h
0x140044862  and     ebp, 1
0x140044865  jz      loc_14004492F
0x14004486b  test    esi, esi
0x14004486d  jz      loc_14004492F
0x140044873  movzx   eax, word ptr [rdi+2]
0x140044877  test    ax, ax
0x14004487a  jz      loc_140044922
0x140044880  xorps   xmm0, xmm0
0x140044883  movups  [rsp+0B8h+var_58], xmm0
0x140044888  mov     word ptr [rsp+0B8h+var_58+2], ax
0x14004488d  mov     word ptr [rsp+0B8h+var_58], ax
0x140044892  lea     rax, [rdi+4]
0x140044896  mov     qword ptr [rsp+0B8h+var_58+8], rax
0x14004489b  mov     edi, 0C000000Dh
0x1400448a0  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x1400448a6  lea     rax, WPP_RECORDER_INITIALIZED
0x1400448ad  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400448b4  setnz   r8b
0x1400448b8  and     dl, 10h
0x1400448bb  jnz     short loc_1400448C6
0x1400448bd  test    r8b, r8b
0x1400448c0  jz      loc_1400449BF
0x1400448c6  mov     r9, cs:WPP_GLOBAL_Control
0x1400448cd  lea     rax, [rsp+0B8h+var_58]
0x1400448d2  mov     [rsp+0B8h+var_60], rax
0x1400448d7  mov     ecx, 214h
0x1400448dc  mov     [rsp+0B8h+var_68], edi
0x1400448e0  lea     rax, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400448e7  mov     [rsp+0B8h+var_70], 66Ch
0x1400448ef  mov     r9, [r9+40h]
0x1400448f3  mov     [rsp+0B8h+var_78], rax
0x1400448f8  lea     rax, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x1400448ff  mov     [rsp+0B8h+var_80], rax
0x140044904  mov     [rsp+0B8h+var_88], 27h ; '''
0x14004490b  mov     [rsp+0B8h+var_90], 14h
0x140044913  mov     [rsp+0B8h+var_98], 2
0x140044918  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x14004491d  jmp     loc_1400449BF
0x140044922  mov     [rbx+28h], r15
0x140044926  mov     [rbx+20h], r15d
0x14004492a  jmp     loc_1400449E5
0x14004492f  movzx   eax, word ptr [r13+2]
0x140044934  lea     rdx, [rbx+20h]
0x140044938  mov     ecx, 6E664A50h
0x14004493d  mov     [rbx+22h], ax
0x140044941  call    PrjfAllocateUnicodeString
0x140044946  mov     edi, eax
0x140044948  test    eax, eax
0x14004494a  jns     loc_1400449D2
0x140044950  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140044956  lea     rax, WPP_RECORDER_INITIALIZED
0x14004495d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140044964  setnz   r8b
0x140044968  and     dl, 10h
0x14004496b  jnz     short loc_140044972
0x14004496d  test    r8b, r8b
0x140044970  jz      short loc_1400449BF
0x140044972  mov     r9, cs:WPP_GLOBAL_Control
0x140044979  lea     rax, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140044980  mov     [rsp+0B8h+var_68], edi
0x140044984  mov     ecx, 214h
0x140044989  mov     [rsp+0B8h+var_70], 67Ch
0x140044991  mov     [rsp+0B8h+var_78], rax
0x140044996  lea     rax, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x14004499d  mov     r9, [r9+40h]
0x1400449a1  mov     [rsp+0B8h+var_80], rax
0x1400449a6  mov     [rsp+0B8h+var_88], 28h ; '('
0x1400449ad  mov     [rsp+0B8h+var_90], 14h
0x1400449b5  mov     [rsp+0B8h+var_98], 2
0x1400449ba  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400449bf  cmp     [rsp+0B8h+arg_10], r15b
0x1400449c7  jz      loc_140044AB6
0x1400449cd  jmp     loc_140044AA8
0x1400449d2  mov     rdx, r13; SourceString
0x1400449d5  lea     rcx, [rbx+20h]; DestinationString
0x1400449d9  call    cs:__imp_RtlCopyUnicodeString
0x1400449e0  nop     dword ptr [rax+rax+00h]
0x1400449e5  mov     [rbx], r14d
0x1400449e8  cmp     [rsp+0B8h+arg_10], r15b
0x1400449f0  jz      short loc_140044A05
0x1400449f2  lea     rcx, [rbx+38h]
0x1400449f6  test    esi, esi
0x1400449f8  jz      short loc_140044A2E
0x1400449fa  mov     rax, [rsp+0B8h+arg_28]
0x140044a02  mov     [rcx], rax
0x140044a05  test    ebp, ebp
0x140044a07  jz      short loc_140044A13
0x140044a09  mov     eax, [rsp+0B8h+arg_20]
0x140044a10  mov     [rbx+30h], eax
0x140044a13  mov     [r12], rbx
0x140044a17  mov     edi, r15d
0x140044a1a  mov     eax, edi
0x140044a1c  add     rsp, 78h
0x140044a20  pop     r15
0x140044a22  pop     r14
0x140044a24  pop     r13
0x140044a26  pop     r12
0x140044a28  pop     rdi
0x140044a29  pop     rsi
0x140044a2a  pop     rbp
0x140044a2b  pop     rbx
0x140044a2c  retn
0x140044a2e  call    PrjfCreatePathTree
0x140044a33  mov     edi, eax
0x140044a35  test    eax, eax
0x140044a37  jns     short loc_140044A05
0x140044a39  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140044a3f  lea     rax, WPP_RECORDER_INITIALIZED
0x140044a46  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140044a4d  setnz   r8b
0x140044a51  and     dl, 10h
0x140044a54  jnz     short loc_140044A5B
0x140044a56  test    r8b, r8b
0x140044a59  jz      short loc_140044AA8
0x140044a5b  mov     r9, cs:WPP_GLOBAL_Control
0x140044a62  lea     rax, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140044a69  mov     [rsp+0B8h+var_68], edi
0x140044a6d  mov     ecx, 214h
0x140044a72  mov     [rsp+0B8h+var_70], 698h
0x140044a7a  mov     [rsp+0B8h+var_78], rax
0x140044a7f  lea     rax, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x140044a86  mov     r9, [r9+40h]
0x140044a8a  mov     [rsp+0B8h+var_80], rax
0x140044a8f  mov     [rsp+0B8h+var_88], 29h ; ')'
0x140044a96  mov     [rsp+0B8h+var_90], 14h
0x140044a9e  mov     [rsp+0B8h+var_98], 2
0x140044aa3  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140044aa8  mov     rcx, [rbx+38h]; P
0x140044aac  test    rcx, rcx
0x140044aaf  jz      short loc_140044AB6
0x140044ab1  call    PrjfDeletePathTree
0x140044ab6  mov     rcx, [rbx+28h]; P
0x140044aba  test    rcx, rcx
0x140044abd  jz      short loc_140044AD0
0x140044abf  mov     edx, 6D6E4A50h; Tag
0x140044ac4  call    cs:__imp_ExFreePoolWithTag
0x140044acb  nop     dword ptr [rax+rax+00h]
0x140044ad0  mov     edx, 6D6E4A50h; Tag
0x140044ad5  mov     rcx, rbx; P
0x140044ad8  call    cs:__imp_ExFreePoolWithTag
0x140044adf  nop     dword ptr [rax+rax+00h]
0x140044ae4  jmp     loc_140044A1A
```
