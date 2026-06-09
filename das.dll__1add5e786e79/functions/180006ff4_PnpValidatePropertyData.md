# _PnpValidatePropertyData

- ea: `0x180006ff4`
- end: `0x1800072e6`
- name: `_PnpValidatePropertyData`
- size: `754`
- prototype: `__int64 __fastcall(LPCWSTR StringSecurityDescriptor, ULONG SecurityDescriptorLength)`
- caller_count: `7`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005a70`
- `0x180005c5c`
- `0x180006320`
- `0x180006440`
- `0x1800068a0`
- `0x180013be0`
- `0x180017210`

## callees

- `0x180006ff4`
- `0x18001ebc0`
- `0x18001f964`
- `0x18001fc00`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x1800071b8`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800071b8`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800071a6`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800071a6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180007140`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000723c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180007140`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000723c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007152`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000724e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007152`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000724e`

## pseudocode

```c
__int64 __fastcall PnpValidatePropertyData(_BYTE *StringSecurityDescriptor, ULONG SecurityDescriptorLength, int a3)
{
  unsigned __int64 v3; // rdi
  unsigned int v5; // ebx
  unsigned int v6; // r14d
  int BaseTypeSize; // eax
  unsigned int v8; // r8d
  int v9; // r9d
  int v10; // r11d
  unsigned int v11; // r10d
  bool v12; // zf
  unsigned __int64 v13; // r15
  int v14; // r10d
  bool v15; // zf
  unsigned __int64 v16; // r13
  unsigned __int64 v17; // rdi
  int v18; // edx
  unsigned int v19; // edi
  int v20; // ecx
  unsigned int v21; // ecx
  _QWORD v23[3]; // [rsp+20h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+98h] [rbp+60h] BYREF

  v3 = SecurityDescriptorLength;
  v23[0] = 0;
  SecurityDescriptor = 0;
  if ( (a3 & 0xFFFF0000) != 0 )
    return (unsigned int)-1073741811;
  v6 = a3 & 0xFFF;
  if ( v6 > 0x19 )
    return (unsigned int)-1073741811;
  BaseTypeSize = GetBaseTypeSize(a3 & 0xFFF);
  v9 = v8 & 0xF000;
  v10 = 0x2000;
  if ( !BaseTypeSize )
    goto LABEL_11;
  if ( v9 == 4096 )
  {
    if ( v6 < 2 || !(unsigned __int8)IsFixedSizeType(v8) || (unsigned int)v3 < v11 )
      return (unsigned int)-1073741811;
    v12 = (unsigned int)v3 % v11 == 0;
  }
  else if ( v9 == 0x2000 )
  {
    v12 = ((v6 - 18) & 0xFFFFFFFD) == 0;
  }
  else
  {
    if ( (v8 & 0xF000) != 0 )
      return (unsigned int)-1073741811;
    if ( !(unsigned __int8)IsFixedSizeType(v8) )
      goto LABEL_11;
    v12 = (_DWORD)v3 == v14;
  }
  if ( !v12 )
    return (unsigned int)-1073741811;
LABEL_11:
  v5 = 0;
  if ( v6 < 2 )
  {
    v21 = 0;
    if ( (_DWORD)v3 )
      return (unsigned int)-1073741811;
    return v21;
  }
  else
  {
    switch ( v6 )
    {
      case 0x10u:
        if ( StringSecurityDescriptor )
        {
          v19 = (unsigned int)v3 >> 3;
          v20 = 0;
          if ( !v19 )
            return v5;
          while ( *(__int64 *)&StringSecurityDescriptor[8 * v20] >= 0 )
          {
            if ( ++v20 >= v19 )
              return v5;
          }
        }
        return (unsigned int)-1073741811;
      case 0x11u:
        if ( StringSecurityDescriptor )
        {
          v18 = 0;
          if ( !(_DWORD)v3 )
            return v5;
          while ( StringSecurityDescriptor[v18] == 0xFF || StringSecurityDescriptor[v18] == 0 )
          {
            if ( ++v18 >= (unsigned int)v3 )
              return v5;
          }
        }
        return (unsigned int)-1073741811;
      case 0x12u:
        goto LABEL_19;
      case 0x13u:
        if ( StringSecurityDescriptor )
        {
          SecurityDescriptor = StringSecurityDescriptor;
          if ( RtlValidRelativeSecurityDescriptor(StringSecurityDescriptor, v3, 0) )
          {
            v15 = RtlLengthSecurityDescriptor(SecurityDescriptor) == (_DWORD)v3;
LABEL_46:
            if ( v15 )
              return v5;
          }
        }
        return (unsigned int)-1073741811;
      case 0x14u:
      case 0x19u:
LABEL_19:
        if ( StringSecurityDescriptor && (unsigned int)v3 >= 2 )
        {
          v13 = v3;
          if ( (v9 & v10) == 0 )
          {
            if ( (int)RtlUnalignedStringCbLengthW(StringSecurityDescriptor, v3, v23) >= 0
              && (unsigned __int64)(v23[0] + 2LL) <= 0xFFFE
              && v23[0] + 2LL == v3 )
            {
              if ( v6 != 20 )
                return v5;
              if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                     (LPCWSTR)StringSecurityDescriptor,
                     1u,
                     &SecurityDescriptor,
                     0) )
              {
                LocalFree(SecurityDescriptor);
                return v5;
              }
            }
            return (unsigned int)-1073741811;
          }
          v16 = 0;
          do
          {
            v5 = 0;
            if ( !*(_WORD *)StringSecurityDescriptor )
              break;
            if ( (int)RtlUnalignedStringCbLengthW(StringSecurityDescriptor, v13 - v16, v23) < 0 )
              return (unsigned int)-1073741811;
            if ( (v23[0] & 1) != 0 )
              return (unsigned int)-1073741811;
            v17 = v23[0] + 2LL;
            v23[0] = v17;
            if ( v17 > 0xFFFE )
              return (unsigned int)-1073741811;
            v16 += v17;
            if ( v16 > v13 )
              return (unsigned int)-1073741811;
            if ( v6 == 20 )
            {
              if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
                      (LPCWSTR)StringSecurityDescriptor,
                      1u,
                      &SecurityDescriptor,
                      0) )
                return (unsigned int)-1073741811;
              LocalFree(SecurityDescriptor);
            }
            StringSecurityDescriptor += 2 * (v17 >> 1);
          }
          while ( v16 + 2 <= v13 );
          v15 = v16 + 2 == v13;
          goto LABEL_46;
        }
        return (unsigned int)-1073741811;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180006ff4  push    rbp
0x180006ff6  push    rbx
0x180006ff7  push    rsi
0x180006ff8  push    rdi
0x180006ff9  push    r12
0x180006ffb  push    r13
0x180006ffd  push    r14
0x180006fff  push    r15
0x180007001  mov     rbp, rsp
0x180007004  sub     rsp, 38h
0x180007008  xor     r12d, r12d
0x18000700b  mov     edi, edx
0x18000700d  mov     [rbp+var_18], r12
0x180007011  mov     rsi, rcx
0x180007014  mov     [rbp+SecurityDescriptor], r12
0x180007018  test    r8d, 0FFFF0000h
0x18000701f  jz      short loc_18000702B
0x180007021  mov     ebx, 0C000000Dh
0x180007026  jmp     loc_1800072D3
0x18000702b  mov     r14d, r8d
0x18000702e  and     r14d, 0FFFh
0x180007035  cmp     r14d, 19h
0x180007039  ja      short loc_180007021
0x18000703b  mov     ecx, r14d
0x18000703e  call    _GetBaseTypeSize
0x180007043  mov     r9d, r8d
0x180007046  mov     r10d, eax
0x180007049  and     r9d, 0F000h
0x180007050  mov     r11d, 2000h
0x180007056  test    eax, eax
0x180007058  jz      short loc_180007090
0x18000705a  cmp     r9d, 1000h
0x180007061  jnz     loc_18000715D
0x180007067  mov     eax, r14d
0x18000706a  test    r14d, r14d
0x18000706d  jz      short loc_180007021
0x18000706f  cmp     eax, 1
0x180007072  jz      short loc_180007021
0x180007074  mov     ecx, r8d
0x180007077  call    _IsFixedSizeType
0x18000707c  test    al, al
0x18000707e  jz      short loc_180007021
0x180007080  cmp     edi, r10d
0x180007083  jb      short loc_180007021
0x180007085  xor     edx, edx
0x180007087  mov     eax, edi
0x180007089  div     r10d
0x18000708c  test    edx, edx
0x18000708e  jnz     short loc_180007021
0x180007090  mov     ebx, r12d
0x180007093  mov     eax, r14d
0x180007096  test    r14d, r14d
0x180007099  jz      loc_1800072C5
0x18000709f  sub     eax, 1
0x1800070a2  jz      loc_1800072C5
0x1800070a8  sub     eax, 0Fh
0x1800070ab  jz      loc_18000729E
0x1800070b1  sub     eax, 1
0x1800070b4  jz      loc_180007276
0x1800070ba  sub     eax, 1
0x1800070bd  jz      short loc_1800070D6
0x1800070bf  sub     eax, 1
0x1800070c2  jz      loc_180007191
0x1800070c8  sub     eax, 1
0x1800070cb  jz      short loc_1800070D6
0x1800070cd  cmp     eax, 5
0x1800070d0  jnz     loc_1800072D3
0x1800070d6  test    rsi, rsi
0x1800070d9  jz      loc_180007021
0x1800070df  cmp     edi, 2
0x1800070e2  jb      loc_180007021
0x1800070e8  mov     r15, rdi
0x1800070eb  test    r11d, r9d
0x1800070ee  jnz     loc_1800071C5
0x1800070f4  lea     r8, [rbp+var_18]
0x1800070f8  mov     rdx, rdi
0x1800070fb  mov     rcx, rsi
0x1800070fe  call    RtlUnalignedStringCbLengthW
0x180007103  test    eax, eax
0x180007105  js      loc_180007021
0x18000710b  mov     rax, [rbp+var_18]
0x18000710f  add     rax, 2
0x180007113  cmp     rax, 0FFFEh
0x180007119  ja      loc_180007021
0x18000711f  cmp     rax, rdi
0x180007122  jnz     loc_180007021
0x180007128  cmp     r14d, 14h
0x18000712c  jnz     loc_1800072D3
0x180007132  xor     r9d, r9d; SecurityDescriptorSize
0x180007135  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180007139  lea     edx, [r14-13h]; StringSDRevision
0x18000713d  mov     rcx, rsi; StringSecurityDescriptor
0x180007140  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180007146  test    eax, eax
0x180007148  jz      loc_180007021
0x18000714e  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180007152  call    cs:__imp_LocalFree
0x180007158  jmp     loc_1800072D3
0x18000715d  cmp     r9d, r11d
0x180007160  jnz     short loc_180007170
0x180007162  lea     eax, [r14-12h]
0x180007166  test    eax, 0FFFFFFFDh
0x18000716b  jmp     loc_18000708E
0x180007170  test    r9d, r9d
0x180007173  jnz     loc_180007021
0x180007179  mov     ecx, r8d
0x18000717c  call    _IsFixedSizeType
0x180007181  test    al, al
0x180007183  jz      loc_180007090
0x180007189  cmp     edi, r10d
0x18000718c  jmp     loc_18000708E
0x180007191  test    rsi, rsi
0x180007194  jz      loc_180007021
0x18000719a  xor     r8d, r8d; RequiredInformation
0x18000719d  mov     [rbp+SecurityDescriptor], rsi
0x1800071a1  mov     edx, edi; SecurityDescriptorLength
0x1800071a3  mov     rcx, rsi; SecurityDescriptorInput
0x1800071a6  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1800071ac  test    al, al
0x1800071ae  jz      loc_180007021
0x1800071b4  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800071b8  call    cs:__imp_RtlLengthSecurityDescriptor
0x1800071be  cmp     eax, edi
0x1800071c0  jmp     loc_18000726F
0x1800071c5  mov     r13, r12
0x1800071c8  cmp     r15, 2
0x1800071cc  jb      loc_180007268
0x1800071d2  mov     ebx, r12d
0x1800071d5  cmp     [rsi], r12w
0x1800071d9  jz      loc_180007268
0x1800071df  mov     rdx, r15
0x1800071e2  lea     r8, [rbp+var_18]
0x1800071e6  sub     rdx, r13
0x1800071e9  mov     rcx, rsi
0x1800071ec  call    RtlUnalignedStringCbLengthW
0x1800071f1  test    eax, eax
0x1800071f3  js      loc_180007021
0x1800071f9  mov     rdi, [rbp+var_18]
0x1800071fd  test    dil, 1
0x180007201  jnz     loc_180007021
0x180007207  add     rdi, 2
0x18000720b  mov     [rbp+var_18], rdi
0x18000720f  cmp     rdi, 0FFFEh
0x180007216  ja      loc_180007021
0x18000721c  add     r13, rdi
0x18000721f  cmp     r13, r15
0x180007222  ja      loc_180007021
0x180007228  cmp     r14d, 14h
0x18000722c  jnz     short loc_180007254
0x18000722e  xor     r9d, r9d; SecurityDescriptorSize
0x180007231  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180007235  lea     edx, [r14-13h]; StringSDRevision
0x180007239  mov     rcx, rsi; StringSecurityDescriptor
0x18000723c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180007242  test    eax, eax
0x180007244  jz      loc_180007021
0x18000724a  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18000724e  call    cs:__imp_LocalFree
0x180007254  shr     rdi, 1
0x180007257  lea     rax, [r13+2]
0x18000725b  lea     rsi, [rsi+rdi*2]
0x18000725f  cmp     rax, r15
0x180007262  jbe     loc_1800071D2
0x180007268  lea     rax, [r13+2]
0x18000726c  cmp     rax, r15
0x18000726f  jz      short loc_1800072D3
0x180007271  jmp     loc_180007021
0x180007276  test    rsi, rsi
0x180007279  jz      loc_180007021
0x18000727f  mov     edx, r12d
0x180007282  test    edi, edi
0x180007284  jz      short loc_1800072D3
0x180007286  mov     eax, edx
0x180007288  mov     cl, [rax+rsi]
0x18000728b  inc     cl
0x18000728d  cmp     cl, 1
0x180007290  ja      loc_180007021
0x180007296  inc     edx
0x180007298  cmp     edx, edi
0x18000729a  jb      short loc_180007286
0x18000729c  jmp     short loc_1800072D3
0x18000729e  test    rsi, rsi
0x1800072a1  jz      loc_180007021
0x1800072a7  shr     edi, 3
0x1800072aa  mov     ecx, r12d
0x1800072ad  test    edi, edi
0x1800072af  jz      short loc_1800072D3
0x1800072b1  mov     eax, ecx
0x1800072b3  cmp     [rsi+rax*8], r12
0x1800072b7  jl      loc_180007021
0x1800072bd  inc     ecx
0x1800072bf  cmp     ecx, edi
0x1800072c1  jb      short loc_1800072B1
0x1800072c3  jmp     short loc_1800072D3
0x1800072c5  mov     ecx, ebx
0x1800072c7  test    edi, edi
0x1800072c9  mov     ebx, 0C000000Dh
0x1800072ce  cmovnz  ecx, ebx
0x1800072d1  mov     ebx, ecx
0x1800072d3  mov     eax, ebx
0x1800072d5  add     rsp, 38h
0x1800072d9  pop     r15
0x1800072db  pop     r14
0x1800072dd  pop     r13
0x1800072df  pop     r12
0x1800072e1  pop     rdi
0x1800072e2  pop     rsi
0x1800072e3  pop     rbx
0x1800072e4  pop     rbp
0x1800072e5  retn
```
