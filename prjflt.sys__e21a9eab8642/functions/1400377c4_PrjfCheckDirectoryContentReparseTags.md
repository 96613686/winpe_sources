# PrjfCheckDirectoryContentReparseTags

- ea: `0x1400377c4`
- end: `0x140037a48`
- name: `PrjfCheckDirectoryContentReparseTags`
- size: `644`
- prototype: `__int64 __fastcall(int, int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x14003d620`

## callees

- `0x14000d008`
- `0x14000d128`
- `0x1400377c4`
- `0x14003a4d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140037a1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037a1d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400378f0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14003790e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400378f0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14003790e`
- `ntoskrnl!ExAllocatePool2` at `0x140037823`
- `ntoskrnl!ExAllocatePool2` at `0x140037823`

## pseudocode

```c
__int64 __fastcall PrjfCheckDirectoryContentReparseTags(int a1, int a2, int *a3)
{
  int v6; // edx
  unsigned int *Pool2; // rsi
  int v8; // r8d
  unsigned int v9; // ebx
  int i; // eax
  int v11; // edx
  int v12; // r8d
  unsigned int *j; // rbx
  unsigned int v14; // ecx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rax
  UNICODE_STRING String1; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v20[2]; // [rsp+70h] [rbp-10h] BYREF
  char v21; // [rsp+C0h] [rbp+40h] BYREF

  *a3 = 0;
  v20[0] = 262146;
  v20[1] = L"*";
  String1 = 0;
  Pool2 = (unsigned int *)ExAllocatePool2(256, 0x10000, 1701071440);
  if ( Pool2 )
  {
    for ( i = PrjfEnumerateDirectory(a1, a2, 60, (unsigned int)v20, 0, 1, 0x10000, (__int64)Pool2, (__int64)&v21);
          ;
          i = PrjfEnumerateDirectory(a1, a2, 60, (unsigned int)v20, 0, 0, 0x10000, (__int64)Pool2, (__int64)&v21) )
    {
      v9 = i;
      if ( i < 0 )
        break;
      for ( j = Pool2; ; j = (unsigned int *)((char *)j + v17) )
      {
        String1.Buffer = (PWSTR)(j + 22);
        String1.Length = *((_WORD *)j + 30);
        String1.MaximumLength = String1.Length;
        if ( !RtlEqualUnicodeString(&String1, &stru_140015580, 1u)
          && !RtlEqualUnicodeString(&String1, &stru_140015570, 1u) )
        {
          v14 = j[17];
          v15 = *a3;
          if ( v14 )
          {
            if ( v14 == -1879048164 )
            {
              v16 = v15 | 2;
            }
            else if ( v14 == -1610612702 )
            {
              v16 = v15 | 4;
            }
            else
            {
              v16 = v15 | 8;
            }
          }
          else
          {
            v16 = v15 | 1;
          }
          *a3 = v16;
        }
        v17 = *j;
        if ( !(_DWORD)v17 )
          break;
      }
    }
    if ( i == -2147483642 )
    {
      v9 = 0;
    }
    else if ( (BYTE2(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = BYTE2(xmmword_14001A3D0) & 4;
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        530,
        v11,
        v12,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        18,
        176,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        140,
        i);
    }
    ExFreePoolWithTag(Pool2, 0x65644A50u);
  }
  else
  {
    if ( (BYTE2(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = BYTE2(xmmword_14001A3D0) & 4;
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        530,
        v6,
        v8,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        18,
        175,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        113);
    }
    return (unsigned int)-1073741670;
  }
  return v9;
}

```

## disassembly

```asm
0x1400377c4  mov     [rsp-28h+arg_0], rbx
0x1400377c9  mov     [rsp-28h+arg_8], rsi
0x1400377ce  push    rbp
0x1400377cf  push    rdi
0x1400377d0  push    r13
0x1400377d2  push    r14
0x1400377d4  push    r15
0x1400377d6  mov     rbp, rsp
0x1400377d9  sub     rsp, 80h
0x1400377e0  mov     rdi, r8
0x1400377e3  mov     dword ptr [r8], 0
0x1400377ea  mov     r14, rdx
0x1400377ed  mov     [rbp+var_10], 40002h
0x1400377f5  mov     r15, rcx
0x1400377f8  lea     rax, asc_140015960; "*"
0x1400377ff  xorps   xmm0, xmm0
0x140037802  mov     [rbp+var_8], rax
0x140037806  mov     ebx, 2
0x14003780b  mov     edx, 10000h
0x140037810  mov     ecx, 100h
0x140037815  mov     r8d, 65644A50h
0x14003781b  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14003781f  lea     r13d, [rbx+2]
0x140037823  call    cs:__imp_ExAllocatePool2
0x14003782a  nop     dword ptr [rax+rax+00h]
0x14003782f  mov     rsi, rax
0x140037832  test    rax, rax
0x140037835  jnz     short loc_1400378AB
0x140037837  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x14003783d  lea     rax, WPP_RECORDER_INITIALIZED
0x140037844  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003784b  setnz   r8b
0x14003784f  and     dl, r13b
0x140037852  jnz     short loc_140037859
0x140037854  test    r8b, r8b
0x140037857  jz      short loc_1400378A1
0x140037859  mov     r9, cs:WPP_GLOBAL_Control
0x140037860  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140037867  mov     [rsp+80h+var_38], 1D71h
0x14003786f  mov     ecx, 212h
0x140037874  mov     [rsp+80h+var_40], rax
0x140037879  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140037880  mov     [rsp+80h+var_48], rax
0x140037885  mov     r9, [r9+40h]
0x140037889  mov     word ptr [rsp+80h+var_50], 0AFh
0x140037890  mov     [rsp+80h+var_58], 12h
0x140037898  mov     byte ptr [rsp+80h+var_60], bl
0x14003789c  call    WPP_RECORDER_AND_TRACE_SF_sD
0x1400378a1  mov     ebx, 0C000009Ah
0x1400378a6  jmp     loc_140037A29
0x1400378ab  lea     rax, [rbp+arg_10]
0x1400378af  mov     [rsp+80h+var_40], rax
0x1400378b4  mov     [rsp+80h+var_48], rsi
0x1400378b9  mov     [rsp+80h+var_50], 10000h
0x1400378c1  mov     byte ptr [rsp+80h+var_58], 1
0x1400378c6  jmp     loc_140037974
0x1400378cb  mov     rbx, rsi
0x1400378ce  lea     rax, [rbx+58h]
0x1400378d2  mov     r8b, 1; CaseInSensitive
0x1400378d5  mov     [rbp+String1.Buffer], rax
0x1400378d9  lea     rdx, stru_140015580; String2
0x1400378e0  movzx   eax, word ptr [rbx+3Ch]
0x1400378e4  lea     rcx, [rbp+String1]; String1
0x1400378e8  mov     [rbp+String1.Length], ax
0x1400378ec  mov     [rbp+String1.MaximumLength], ax
0x1400378f0  call    cs:__imp_RtlEqualUnicodeString
0x1400378f7  nop     dword ptr [rax+rax+00h]
0x1400378fc  test    al, al
0x1400378fe  jnz     short loc_14003794B
0x140037900  mov     r8b, 1; CaseInSensitive
0x140037903  lea     rdx, stru_140015570; String2
0x14003790a  lea     rcx, [rbp+String1]; String1
0x14003790e  call    cs:__imp_RtlEqualUnicodeString
0x140037915  nop     dword ptr [rax+rax+00h]
0x14003791a  test    al, al
0x14003791c  jnz     short loc_14003794B
0x14003791e  mov     ecx, [rbx+44h]
0x140037921  mov     eax, [rdi]
0x140037923  test    ecx, ecx
0x140037925  jnz     short loc_14003792C
0x140037927  or      eax, 1
0x14003792a  jmp     short loc_140037949
0x14003792c  cmp     ecx, 9000001Ch
0x140037932  jnz     short loc_140037939
0x140037934  or      eax, 2
0x140037937  jmp     short loc_140037949
0x140037939  cmp     ecx, 0A0000022h
0x14003793f  jnz     short loc_140037946
0x140037941  or      eax, r13d
0x140037944  jmp     short loc_140037949
0x140037946  or      eax, 8
0x140037949  mov     [rdi], eax
0x14003794b  mov     eax, [rbx]
0x14003794d  test    eax, eax
0x14003794f  jz      short loc_140037959
0x140037951  add     rbx, rax
0x140037954  jmp     loc_1400378CE
0x140037959  lea     rax, [rbp+arg_10]
0x14003795d  mov     [rsp+80h+var_40], rax
0x140037962  mov     [rsp+80h+var_48], rsi
0x140037967  mov     [rsp+80h+var_50], 10000h
0x14003796f  mov     byte ptr [rsp+80h+var_58], 0
0x140037974  lea     r9, [rbp+var_10]
0x140037978  mov     [rsp+80h+var_60], 0
0x140037980  mov     r8d, 3Ch ; '<'
0x140037986  mov     rdx, r14
0x140037989  mov     rcx, r15
0x14003798c  call    PrjfEnumerateDirectory
0x140037991  mov     ebx, eax
0x140037993  test    eax, eax
0x140037995  jns     loc_1400378CB
0x14003799b  cmp     eax, 80000006h
0x1400379a0  jnz     short loc_1400379A6
0x1400379a2  xor     ebx, ebx
0x1400379a4  jmp     short loc_140037A15
0x1400379a6  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x1400379ac  lea     rax, WPP_RECORDER_INITIALIZED
0x1400379b3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400379ba  setnz   r8b
0x1400379be  and     dl, r13b
0x1400379c1  jnz     short loc_1400379C8
0x1400379c3  test    r8b, r8b
0x1400379c6  jz      short loc_140037A15
0x1400379c8  mov     r9, cs:WPP_GLOBAL_Control
0x1400379cf  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400379d6  mov     [rsp+80h+var_30], ebx
0x1400379da  mov     ecx, 212h
0x1400379df  mov     [rsp+80h+var_38], 1D8Ch
0x1400379e7  mov     [rsp+80h+var_40], rax
0x1400379ec  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x1400379f3  mov     r9, [r9+40h]
0x1400379f7  mov     [rsp+80h+var_48], rax
0x1400379fc  mov     word ptr [rsp+80h+var_50], 0B0h
0x140037a03  mov     [rsp+80h+var_58], 12h
0x140037a0b  mov     byte ptr [rsp+80h+var_60], 2
0x140037a10  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140037a15  mov     edx, 65644A50h; Tag
0x140037a1a  mov     rcx, rsi; P
0x140037a1d  call    cs:__imp_ExFreePoolWithTag
0x140037a24  nop     dword ptr [rax+rax+00h]
0x140037a29  lea     r11, [rsp+80h+var_s0]
0x140037a31  mov     eax, ebx
0x140037a33  mov     rbx, [r11+30h]
0x140037a37  mov     rsi, [r11+38h]
0x140037a3b  mov     rsp, r11
0x140037a3e  pop     r15
0x140037a40  pop     r14
0x140037a42  pop     r13
0x140037a44  pop     rdi
0x140037a45  pop     rbp
0x140037a46  retn
```
