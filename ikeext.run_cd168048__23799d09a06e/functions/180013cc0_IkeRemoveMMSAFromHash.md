# IkeRemoveMMSAFromHash

- ea: `0x180013cc0`
- end: `0x180013f4c`
- name: `IkeRemoveMMSAFromHash`
- size: `652`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000b940`

## callees

- `0x1800061ec`
- `0x180008310`
- `0x180008388`
- `0x180013cc0`
- `0x18001afe0`
- `0x18004aa3c`
- `0x180050850`
- `0x180068f5c`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180013ee8`
- `ntdll!RtlRemoveEntryHashTable` at `0x180013ee8`
- `ntdll!RtlLookupEntryHashTable` at `0x180013d97`
- `ntdll!RtlLookupEntryHashTable` at `0x180013d97`
- `ntdll!RtlGetNextEntryHashTable` at `0x180013e05`
- `ntdll!RtlGetNextEntryHashTable` at `0x180013e9e`
- `ntdll!RtlGetNextEntryHashTable` at `0x180013e05`
- `ntdll!RtlGetNextEntryHashTable` at `0x180013e9e`

## string_xrefs

- `0x180013cee`: `IkeRemoveMMSAFromHash`
- `0x180013ebb`: `IkeRemoveMMSAFromHash`
- `0x180013f0c`: `IkeRemoveMMSAFromHash`
- `0x180013f18`: `IkeRemoveMMSAFromHash`

## pseudocode

```c
__int64 __fastcall IkeRemoveMMSAFromHash(__int64 a1, __int64 *a2)
{
  int v3; // esi
  __int64 v4; // r12
  __int64 i; // rax
  __int64 v6; // rdx
  __int64 v7; // r11
  __int64 NextEntryHashTable; // rax
  __int64 *v9; // r13
  __int64 v10; // rbp
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rbx
  unsigned int v15; // [rsp+20h] [rbp-78h] BYREF
  __int64 v16; // [rsp+28h] [rbp-70h] BYREF
  __int64 *v17; // [rsp+30h] [rbp-68h]
  __int128 v18; // [rsp+38h] [rbp-60h] BYREF
  __int64 v19; // [rsp+48h] [rbp-50h]

  v17 = a2;
  v3 = 1;
  v19 = 0;
  v4 = 0;
  v18 = 0;
  TraceLogHelper("IkeRemoveMMSAFromHash", 1);
  while ( 1 )
  {
    v12 = 0;
    TraceLogHelper("IkeLookupMMSA", 1);
    if ( v3 )
    {
      v16 = 0;
      v15 = 0;
      if ( a1 != -680 )
        _mm_lfence();
      IkeAddrGetAddrBytes(a1 + 436, &v16, &v15);
      if ( v16 )
      {
        for ( i = 0; (unsigned int)i < v15; v7 = v6 + 37 * v7 )
        {
          v6 = *(unsigned __int8 *)(i + v16);
          i = (unsigned int)(i + 1);
        }
      }
      if ( !v7 )
        v7 = -1;
      NextEntryHashTable = RtlLookupEntryHashTable(&gIkeExtGlobals[54].LockCount, v7, &v18);
      v3 = 0;
    }
    else
    {
      NextEntryHashTable = RtlGetNextEntryHashTable(&gIkeExtGlobals[54].LockCount, &v18);
    }
    v9 = v17;
    while ( 1 )
    {
      v10 = NextEntryHashTable;
      if ( !NextEntryHashTable )
        break;
      if ( (unsigned int)IkeFullMMMatch(a1 + 680, a1 + 688, a1 + 376, *(_QWORD *)(NextEntryHashTable + 24)) )
      {
        v12 = *(_QWORD *)(v10 + 24);
        v4 = v10;
        break;
      }
      NextEntryHashTable = RtlGetNextEntryHashTable(&gIkeExtGlobals[54].LockCount, &v18);
    }
    TraceLogHelper("IkeLookupMMSA", 0);
    if ( v12 == a1 )
      break;
    if ( !v12 )
    {
      v13 = WfpReportSysErrorAsWinError(v11, "IkeRemoveMMSAFromHash", 1168, 1);
      goto LABEL_24;
    }
  }
  v13 = 0;
  RtlRemoveEntryHashTable(&gIkeExtGlobals[54].LockCount, v4, 0);
  if ( v9 )
    *v9 = v4;
  WfpRestructureHashtable(&gIkeExtGlobals[54].LockCount);
LABEL_24:
  TraceLogHelper("IkeRemoveMMSAFromHash", 0);
  return IkeReturnError(v13, "IkeRemoveMMSAFromHash");
}

```

## disassembly

```asm
0x180013cc0  mov     [rsp+arg_10], rbx
0x180013cc5  push    rbp
0x180013cc6  push    rsi
0x180013cc7  push    rdi
0x180013cc8  push    r12
0x180013cca  push    r13
0x180013ccc  push    r14
0x180013cce  push    r15
0x180013cd0  sub     rsp, 60h
0x180013cd4  mov     rax, cs:__security_cookie
0x180013cdb  xor     rax, rsp
0x180013cde  mov     [rsp+98h+var_48], rax
0x180013ce3  mov     [rsp+98h+var_68], rdx
0x180013ce8  mov     rdi, rcx
0x180013ceb  xorps   xmm0, xmm0
0x180013cee  lea     rcx, aIkeremovemmsaf_2; "IkeRemoveMMSAFromHash"
0x180013cf5  xor     eax, eax
0x180013cf7  mov     esi, 1
0x180013cfc  mov     edx, esi
0x180013cfe  mov     [rsp+98h+var_50], rax
0x180013d03  xor     r12d, r12d
0x180013d06  movups  [rsp+98h+var_60], xmm0
0x180013d0b  call    TraceLogHelper
0x180013d10  lea     r14, [rdi+2A8h]
0x180013d17  jmp     loc_180013DD0
0x180013d1c  mov     r9d, [rsp+98h+var_78]
0x180013d21  xor     eax, eax
0x180013d23  test    r9d, r9d
0x180013d26  jz      short loc_180013D7A
0x180013d28  nop     dword ptr [rax+rax+00000000h]
0x180013d30  movzx   edx, byte ptr [rax+r8]
0x180013d35  inc     eax
0x180013d37  imul    r11, 25h ; '%'
0x180013d3b  add     r11, rdx
0x180013d3e  cmp     eax, r9d
0x180013d41  jb      short loc_180013D30
0x180013d43  jmp     short loc_180013D7A
0x180013d45  xor     r11d, r11d
0x180013d48  mov     [rsp+98h+var_70], rbx
0x180013d4d  mov     [rsp+98h+var_78], ebx
0x180013d51  test    r14, r14
0x180013d54  jnz     loc_180013E0D
0x180013d5a  lea     rcx, [rdi+1B4h]
0x180013d61  lea     r8, [rsp+98h+var_78]
0x180013d66  lea     rdx, [rsp+98h+var_70]
0x180013d6b  call    IkeAddrGetAddrBytes
0x180013d70  mov     r8, [rsp+98h+var_70]
0x180013d75  test    r8, r8
0x180013d78  jnz     short loc_180013D1C
0x180013d7a  mov     rcx, cs:gIkeExtGlobals
0x180013d81  lea     r8, [rsp+98h+var_60]
0x180013d86  add     rcx, 878h
0x180013d8d  test    r11, r11
0x180013d90  cmovz   r11, r13
0x180013d94  mov     rdx, r11
0x180013d97  call    cs:__imp_RtlLookupEntryHashTable
0x180013d9d  xor     esi, esi
0x180013d9f  mov     r13, [rsp+98h+var_68]
0x180013da4  mov     rbp, rax
0x180013da7  test    rax, rax
0x180013daa  jnz     loc_180013E6D
0x180013db0  xor     edx, edx
0x180013db2  lea     rcx, aIkelookupmmsa; "IkeLookupMMSA"
0x180013db9  call    TraceLogHelper
0x180013dbe  cmp     rbx, rdi
0x180013dc1  jz      loc_180013ED2
0x180013dc7  test    rbx, rbx
0x180013dca  jz      loc_180013EB5
0x180013dd0  mov     edx, 1
0x180013dd5  lea     rcx, aIkelookupmmsa; "IkeLookupMMSA"
0x180013ddc  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180013de3  xor     ebx, ebx
0x180013de5  call    TraceLogHelper
0x180013dea  test    esi, esi
0x180013dec  jnz     loc_180013D45
0x180013df2  mov     rcx, cs:gIkeExtGlobals
0x180013df9  lea     rdx, [rsp+98h+var_60]
0x180013dfe  add     rcx, 878h
0x180013e05  call    cs:__imp_RtlGetNextEntryHashTable
0x180013e0b  jmp     short loc_180013D9F
0x180013e0d  lfence
0x180013e10  movzx   eax, byte ptr [r14]
0x180013e14  imul    rcx, rax, 25h ; '%'
0x180013e18  movzx   eax, byte ptr [r14+1]
0x180013e1d  add     rcx, rax
0x180013e20  movzx   eax, byte ptr [r14+2]
0x180013e25  imul    rdx, rcx, 25h ; '%'
0x180013e29  add     rdx, rax
0x180013e2c  movzx   eax, byte ptr [r14+3]
0x180013e31  imul    rcx, rdx, 25h ; '%'
0x180013e35  add     rcx, rax
0x180013e38  movzx   eax, byte ptr [r14+4]
0x180013e3d  imul    rdx, rcx, 25h ; '%'
0x180013e41  add     rdx, rax
0x180013e44  movzx   eax, byte ptr [r14+5]
0x180013e49  imul    rcx, rdx, 25h ; '%'
0x180013e4d  add     rcx, rax
0x180013e50  movzx   eax, byte ptr [r14+6]
0x180013e55  imul    rdx, rcx, 25h ; '%'
0x180013e59  add     rdx, rax
0x180013e5c  movzx   eax, byte ptr [r14+7]
0x180013e61  imul    r11, rdx, 25h ; '%'
0x180013e65  add     r11, rax
0x180013e68  jmp     loc_180013D5A
0x180013e6d  mov     r9, [rbp+18h]
0x180013e71  lea     rdx, [rdi+2B0h]
0x180013e78  lea     r8, [rdi+178h]
0x180013e7f  mov     rcx, r14
0x180013e82  call    IkeFullMMMatch
0x180013e87  test    eax, eax
0x180013e89  jnz     short loc_180013EA9
0x180013e8b  mov     rcx, cs:gIkeExtGlobals
0x180013e92  lea     rdx, [rsp+98h+var_60]
0x180013e97  add     rcx, 878h
0x180013e9e  call    cs:__imp_RtlGetNextEntryHashTable
0x180013ea4  jmp     loc_180013DA4
0x180013ea9  mov     rbx, [rbp+18h]
0x180013ead  mov     r12, rbp
0x180013eb0  jmp     loc_180013DB0
0x180013eb5  mov     r9d, 1
0x180013ebb  lea     rdx, aIkeremovemmsaf_2; "IkeRemoveMMSAFromHash"
0x180013ec2  mov     r8d, 490h
0x180013ec8  call    WfpReportSysErrorAsWinError
0x180013ecd  mov     rbx, rax
0x180013ed0  jmp     short loc_180013F0A
0x180013ed2  mov     rcx, cs:gIkeExtGlobals
0x180013ed9  xor     r8d, r8d
0x180013edc  add     rcx, 878h
0x180013ee3  mov     rdx, r12
0x180013ee6  xor     ebx, ebx
0x180013ee8  call    cs:__imp_RtlRemoveEntryHashTable
0x180013eee  test    r13, r13
0x180013ef1  jz      short loc_180013EF7
0x180013ef3  mov     [r13+0], r12
0x180013ef7  mov     rcx, cs:gIkeExtGlobals
0x180013efe  add     rcx, 878h
0x180013f05  call    WfpRestructureHashtable
0x180013f0a  xor     edx, edx
0x180013f0c  lea     rcx, aIkeremovemmsaf_2; "IkeRemoveMMSAFromHash"
0x180013f13  call    TraceLogHelper
0x180013f18  lea     rdx, aIkeremovemmsaf_2; "IkeRemoveMMSAFromHash"
0x180013f1f  mov     rcx, rbx
0x180013f22  call    IkeReturnError
0x180013f27  mov     rcx, [rsp+98h+var_48]
0x180013f2c  xor     rcx, rsp; StackCookie
0x180013f2f  call    __security_check_cookie
0x180013f34  mov     rbx, [rsp+98h+arg_10]
0x180013f3c  add     rsp, 60h
0x180013f40  pop     r15
0x180013f42  pop     r14
0x180013f44  pop     r13
0x180013f46  pop     r12
0x180013f48  pop     rdi
0x180013f49  pop     rsi
0x180013f4a  pop     rbp
0x180013f4b  retn
```
