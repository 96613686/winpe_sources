# CreateSecureProcessEx

- ea: `0x18005ee68`
- end: `0x18005f1ca`
- name: `CreateSecureProcessEx`
- size: `866`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x18003c304`

## callees

- `0x180038970`
- `0x18005ee68`
- `0x180062310`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18005ef5d`
- `ntdll!RtlFreeHeap` at `0x18005ef5d`
- `ntdll!NtClose` at `0x18005ef72`
- `ntdll!NtClose` at `0x18005ef87`
- `ntdll!NtClose` at `0x18005ef72`
- `ntdll!NtClose` at `0x18005ef87`
- `ntdll!RtlInitUnicodeString` at `0x18005ef09`
- `ntdll!RtlInitUnicodeString` at `0x18005ef09`
- `ntdll!RtlCreateProcessParametersEx` at `0x18005f073`
- `ntdll!RtlCreateProcessParametersEx` at `0x18005f073`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18005efc7`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18005efc7`
- `ntdll!NtCreateUserProcess` at `0x18005f19b`
- `ntdll!NtCreateUserProcess` at `0x18005f19b`

## pseudocode

```c
__int64 __fastcall CreateSecureProcessEx(_WORD *a1, _WORD *a2, __int64 a3, __int64 a4, HANDLE *a5)
{
  __int64 v7; // rdi
  _WORD *v8; // rax
  __int64 v9; // rcx
  signed int v10; // ebx
  __int64 result; // rax
  _WORD *v12; // rax
  __int16 v13; // di
  struct _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // rbx
  char v15; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v16; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  __int128 v18; // [rsp+80h] [rbp-80h] BYREF
  __int64 v19; // [rsp+90h] [rbp-70h] BYREF
  int v20; // [rsp+A0h] [rbp-60h]
  _BYTE v21[4]; // [rsp+A4h] [rbp-5Ch] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE v23; // [rsp+B0h] [rbp-50h] BYREF
  char v24; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v25[2]; // [rsp+110h] [rbp+10h] BYREF
  char v26; // [rsp+120h] [rbp+20h]
  _QWORD v27[18]; // [rsp+170h] [rbp+70h] BYREF

  v15 = 2;
  v19 = 1;
  memset_0(v27, 0, 0x88u);
  v18 = 0;
  memset_0(v25, 0, 0x58u);
  v16 = 0;
  DestinationString = 0;
  memset_0(v21, 0, 0x64u);
  v20 = 104;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( a1 )
  {
    v7 = 0x7FFF;
    v8 = a1;
    v9 = 0x7FFF;
    while ( *v8 )
    {
      ++v8;
      if ( !--v9 )
        goto LABEL_5;
    }
    v10 = RtlDosPathNameToNtPathName_U_WithStatus(a1, &DestinationString, 0, 0);
    if ( v10 < 0 )
      goto LABEL_6;
    v18 = 0;
    if ( a2 )
    {
      v12 = a2;
      do
      {
        if ( !*v12 )
          break;
        ++v12;
        --v7;
      }
      while ( v7 );
      v10 = v7 == 0 ? 0xC000000D : 0;
      if ( !v7 )
        goto LABEL_6;
      v13 = 2 * v7;
      *((_QWORD *)&v18 + 1) = a2;
      LOWORD(v18) = -2 - v13;
      WORD1(v18) = -v13;
    }
    ProcessParameters = NtCurrentPeb()->ProcessParameters;
    result = RtlCreateProcessParametersEx(&v16, &DestinationString, 0, 0, &v18, 0, 0, 0, 0, 0, 1);
    if ( (int)result < 0 )
      return result;
    *(_DWORD *)(v16 + 1032) = ProcessParameters[1].Flags;
    memset_0(v25, 0, 0x58u);
    v25[0] = 88;
    v27[3] = &v24;
    v27[6] = DestinationString.Length;
    v27[7] = DestinationString.Buffer;
    v27[11] = &v19;
    v27[15] = &v15;
    v26 = 4;
    v27[1] = 65539;
    v27[2] = 16;
    v27[4] = 0;
    v27[5] = 131077;
    v27[8] = 0;
    v27[9] = 131090;
    v27[10] = 8;
    v27[12] = 0;
    v27[13] = 131080;
    v27[14] = 1;
    v27[16] = 0;
    v27[0] = 136;
    v10 = NtCreateUserProcess(&Handle, &v23, 0x2000000, 0x2000000, 0, 0, 256, 0, v16, v25, v27);
    if ( v10 >= 0 && a5 )
    {
      *a5 = Handle;
      Handle = 0;
    }
  }
  else
  {
LABEL_5:
    v10 = -1073741811;
  }
LABEL_6:
  if ( DestinationString.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  if ( Handle )
    NtClose(Handle);
  if ( v23 )
    NtClose(v23);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18005ee68  push    rbp
0x18005ee6a  push    rbx
0x18005ee6b  push    rsi
0x18005ee6c  push    rdi
0x18005ee6d  push    r12
0x18005ee6f  push    r13
0x18005ee71  push    r14
0x18005ee73  push    r15
0x18005ee75  lea     rbp, [rsp-118h]
0x18005ee7d  sub     rsp, 218h
0x18005ee84  mov     rax, cs:__security_cookie
0x18005ee8b  xor     rax, rsp
0x18005ee8e  mov     [rbp+150h+var_50], rax
0x18005ee95  mov     r14, [rbp+150h+arg_20]
0x18005ee9c  mov     r13d, 2
0x18005eea2  mov     rsi, rdx
0x18005eea5  mov     [rsp+250h+var_1F0], r13b
0x18005eeaa  mov     rbx, rcx
0x18005eead  xor     edx, edx; Val
0x18005eeaf  mov     r8d, 88h; Size
0x18005eeb5  lea     rcx, [rbp+150h+var_E0]; void *
0x18005eeb9  lea     r12d, [r13-1]
0x18005eebd  mov     [rbp+150h+var_1C0], r12
0x18005eec1  call    memset_0
0x18005eec6  xorps   xmm0, xmm0
0x18005eec9  lea     r8d, [r13+56h]; Size
0x18005eecd  xor     edx, edx; Val
0x18005eecf  lea     rcx, [rbp+150h+var_140]; void *
0x18005eed3  movups  [rbp+150h+var_1D0], xmm0
0x18005eed7  call    memset_0
0x18005eedc  xorps   xmm0, xmm0
0x18005eedf  lea     r8d, [r13+62h]; Size
0x18005eee3  xor     r15d, r15d
0x18005eee6  lea     rcx, [rbp+150h+var_1AC]; void *
0x18005eeea  xor     edx, edx; Val
0x18005eeec  mov     [rsp+250h+var_1E8], r15
0x18005eef1  movups  xmmword ptr [rsp+250h+DestinationString.Length], xmm0
0x18005eef6  call    memset_0
0x18005eefb  xor     edx, edx; SourceString
0x18005eefd  mov     [rbp+150h+var_1B0], 68h ; 'h'
0x18005ef04  lea     rcx, [rsp+250h+DestinationString]; DestinationString
0x18005ef09  call    cs:__imp_RtlInitUnicodeString
0x18005ef10  nop     dword ptr [rax+rax+00h]
0x18005ef15  test    rbx, rbx
0x18005ef18  jz      short loc_18005EF3D
0x18005ef1a  cmp     [rsp+250h+var_1F0], r15b
0x18005ef1f  jz      short loc_18005EF3D
0x18005ef21  mov     edi, 7FFFh
0x18005ef26  mov     rax, rbx
0x18005ef29  mov     ecx, edi
0x18005ef2b  cmp     [rax], r15w
0x18005ef2f  jz      loc_18005EFB9
0x18005ef35  add     rax, r13
0x18005ef38  sub     rcx, r12
0x18005ef3b  jnz     short loc_18005EF2B
0x18005ef3d  mov     ebx, 0C000000Dh
0x18005ef42  cmp     [rsp+250h+DestinationString.Buffer], r15
0x18005ef47  jz      short loc_18005EF69
0x18005ef49  mov     rcx, gs:60h
0x18005ef52  xor     edx, edx; Flags
0x18005ef54  mov     r8, [rsp+250h+DestinationString.Buffer]; P
0x18005ef59  mov     rcx, [rcx+30h]; HeapHandle
0x18005ef5d  call    cs:__imp_RtlFreeHeap
0x18005ef64  nop     dword ptr [rax+rax+00h]
0x18005ef69  mov     rcx, [rbp+150h+Handle]; Handle
0x18005ef6d  test    rcx, rcx
0x18005ef70  jz      short loc_18005EF7E
0x18005ef72  call    cs:__imp_NtClose
0x18005ef79  nop     dword ptr [rax+rax+00h]
0x18005ef7e  mov     rcx, [rbp+150h+var_1A0]; Handle
0x18005ef82  test    rcx, rcx
0x18005ef85  jz      short loc_18005EF93
0x18005ef87  call    cs:__imp_NtClose
0x18005ef8e  nop     dword ptr [rax+rax+00h]
0x18005ef93  mov     eax, ebx
0x18005ef95  mov     rcx, [rbp+150h+var_50]
0x18005ef9c  xor     rcx, rsp; StackCookie
0x18005ef9f  call    __security_check_cookie
0x18005efa4  add     rsp, 218h
0x18005efab  pop     r15
0x18005efad  pop     r14
0x18005efaf  pop     r13
0x18005efb1  pop     r12
0x18005efb3  pop     rdi
0x18005efb4  pop     rsi
0x18005efb5  pop     rbx
0x18005efb6  pop     rbp
0x18005efb7  retn
0x18005efb9  xor     r9d, r9d
0x18005efbc  lea     rdx, [rsp+250h+DestinationString]
0x18005efc1  xor     r8d, r8d
0x18005efc4  mov     rcx, rbx
0x18005efc7  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18005efce  nop     dword ptr [rax+rax+00h]
0x18005efd3  mov     ebx, eax
0x18005efd5  test    eax, eax
0x18005efd7  js      loc_18005EF42
0x18005efdd  xorps   xmm0, xmm0
0x18005efe0  movups  [rbp+150h+var_1D0], xmm0
0x18005efe4  test    rsi, rsi
0x18005efe7  jz      short loc_18005F02F
0x18005efe9  mov     rax, rsi
0x18005efec  cmp     [rax], r15w
0x18005eff0  jz      short loc_18005EFFA
0x18005eff2  add     rax, r13
0x18005eff5  sub     rdi, r12
0x18005eff8  jnz     short loc_18005EFEC
0x18005effa  mov     rax, rdi
0x18005effd  mov     ebx, 0C000000Dh
0x18005f002  neg     rax
0x18005f005  sbb     ecx, ecx
0x18005f007  not     ecx
0x18005f009  and     ebx, ecx
0x18005f00b  test    rdi, rdi
0x18005f00e  jz      loc_18005EF42
0x18005f014  add     di, di
0x18005f017  mov     qword ptr [rbp+150h+var_1D0+8], rsi
0x18005f01b  mov     eax, 0FFFEh
0x18005f020  sub     ax, di
0x18005f023  mov     word ptr [rbp+150h+var_1D0], ax
0x18005f027  add     ax, r13w
0x18005f02b  mov     word ptr [rbp+150h+var_1D0+2], ax
0x18005f02f  mov     rax, gs:60h
0x18005f038  lea     rdx, [rsp+250h+DestinationString]
0x18005f03d  mov     dword ptr [rsp+250h+var_200], r12d
0x18005f042  lea     rcx, [rsp+250h+var_1E8]
0x18005f047  mov     [rsp+250h+var_208], r15
0x18005f04c  xor     r9d, r9d
0x18005f04f  mov     [rsp+250h+var_210], r15
0x18005f054  xor     r8d, r8d
0x18005f057  mov     rbx, [rax+20h]
0x18005f05b  lea     rax, [rbp+150h+var_1D0]
0x18005f05f  mov     [rsp+250h+var_218], r15
0x18005f064  mov     [rsp+250h+var_220], r15
0x18005f069  mov     [rsp+250h+var_228], r15
0x18005f06e  mov     [rsp+250h+var_230], rax
0x18005f073  call    cs:__imp_RtlCreateProcessParametersEx
0x18005f07a  nop     dword ptr [rax+rax+00h]
0x18005f07f  test    eax, eax
0x18005f081  js      loc_18005EF95
0x18005f087  mov     ecx, [rbx+408h]
0x18005f08d  xor     edx, edx; Val
0x18005f08f  mov     rax, [rsp+250h+var_1E8]
0x18005f094  mov     ebx, 58h ; 'X'
0x18005f099  mov     r8d, ebx; Size
0x18005f09c  mov     [rax+408h], ecx
0x18005f0a2  lea     rcx, [rbp+150h+var_140]; void *
0x18005f0a6  call    memset_0
0x18005f0ab  lea     rax, [rbp+150h+var_198]
0x18005f0af  mov     [rbp+150h+var_140], rbx
0x18005f0b3  mov     [rbp+150h+var_C8], rax
0x18005f0ba  lea     rdx, [rbp+150h+var_1A0]
0x18005f0be  movzx   eax, [rsp+250h+DestinationString.Length]
0x18005f0c3  lea     rcx, [rbp+150h+Handle]
0x18005f0c7  mov     [rbp+150h+var_B0], rax
0x18005f0ce  mov     r8d, 2000000h
0x18005f0d4  mov     rax, [rsp+250h+DestinationString.Buffer]
0x18005f0d9  mov     r9d, r8d
0x18005f0dc  mov     [rbp+150h+var_A8], rax
0x18005f0e3  lea     rax, [rbp+150h+var_1C0]
0x18005f0e7  mov     [rbp+150h+var_88], rax
0x18005f0ee  lea     rax, [rsp+250h+var_1F0]
0x18005f0f3  mov     [rbp+150h+var_68], rax
0x18005f0fa  lea     rax, [rbp+150h+var_E0]
0x18005f0fe  mov     [rsp+250h+var_200], rax
0x18005f103  lea     rax, [rbp+150h+var_140]
0x18005f107  mov     [rsp+250h+var_208], rax
0x18005f10c  mov     rax, [rsp+250h+var_1E8]
0x18005f111  mov     [rsp+250h+var_210], rax
0x18005f116  mov     dword ptr [rsp+250h+var_218], r15d
0x18005f11b  mov     dword ptr [rsp+250h+var_220], 100h
0x18005f123  mov     [rsp+250h+var_228], r15
0x18005f128  mov     [rsp+250h+var_230], r15
0x18005f12d  mov     [rbp+150h+var_130], 4
0x18005f131  mov     [rbp+150h+var_D8], 10003h
0x18005f139  mov     [rbp+150h+var_D0], 10h
0x18005f144  mov     [rbp+150h+var_C0], r15
0x18005f14b  mov     [rbp+150h+var_B8], 20005h
0x18005f156  mov     [rbp+150h+var_A0], r15
0x18005f15d  mov     [rbp+150h+var_98], 20012h
0x18005f168  mov     [rbp+150h+var_90], 8
0x18005f173  mov     [rbp+150h+var_80], r15
0x18005f17a  mov     [rbp+150h+var_78], 20008h
0x18005f185  mov     [rbp+150h+var_70], r12
0x18005f18c  mov     [rbp+150h+var_60], r15
0x18005f193  mov     [rbp+150h+var_E0], 88h
0x18005f19b  call    cs:__imp_NtCreateUserProcess
0x18005f1a2  nop     dword ptr [rax+rax+00h]
0x18005f1a7  mov     ebx, eax
0x18005f1a9  test    eax, eax
0x18005f1ab  js      loc_18005EF42
0x18005f1b1  test    r14, r14
0x18005f1b4  jz      loc_18005EF42
0x18005f1ba  mov     rax, [rbp+150h+Handle]
0x18005f1be  mov     [r14], rax
0x18005f1c1  mov     [rbp+150h+Handle], r15
0x18005f1c5  jmp     loc_18005EF42
```
