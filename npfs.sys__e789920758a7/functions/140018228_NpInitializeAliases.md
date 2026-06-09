# NpInitializeAliases

- ea: `0x140018228`
- end: `0x140018416`
- name: `NpInitializeAliases`
- size: `494`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140018080`

## callees

- `0x140002240`
- `0x140018228`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400182aa`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140018344`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400182aa`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140018344`
- `ntoskrnl!_wcsicmp` at `0x1400183d0`
- `ntoskrnl!_wcsicmp` at `0x1400183d0`
- `ntoskrnl!ExAllocatePool2` at `0x1400182e4`
- `ntoskrnl!ExAllocatePool2` at `0x1400182e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001835f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001835f`

## pseudocode

```c
__int64 NpInitializeAliases()
{
  int v0; // ecx
  __int64 result; // rax
  char *Pool2; // rax
  char *v3; // rdi
  int v4; // ebx
  unsigned int v5; // r15d
  unsigned __int16 v6; // r14
  __int64 *v7; // rsi
  __int64 i; // rbx
  int v9; // [rsp+30h] [rbp-79h] BYREF
  __int64 v10; // [rsp+34h] [rbp-75h]
  int v11; // [rsp+3Ch] [rbp-6Dh]
  _BYTE v12[24]; // [rsp+40h] [rbp-69h] BYREF
  _QWORD v13[20]; // [rsp+60h] [rbp-49h] BYREF

  memset(v12, 0, 21);
  v9 = 1;
  memset(v13, 0, 0x70u);
  LODWORD(v13[1]) = 16;
  v13[0] = NpReadAlias;
  LODWORD(v13[4]) = 0;
  v10 = 0;
  v11 = 0;
  v0 = RtlQueryRegistryValuesEx(2147483649LL, L"Npfs\\Aliases", v13, &v9, 0);
  if ( v0 >= 0 )
  {
    if ( (_DWORD)v10 )
    {
      Pool2 = (char *)ExAllocatePool2(64, (unsigned int)v10, 1936093262);
      NpAliases = Pool2;
      if ( !Pool2 )
        return 3221225626LL;
      *(_QWORD *)&v12[8] = Pool2;
      v3 = &Pool2[16 * v11];
      LOBYTE(v9) = 0;
      *(_QWORD *)v12 = v3;
      *(_QWORD *)&v12[16] = &v3[32 * HIDWORD(v10)];
      v4 = RtlQueryRegistryValuesEx(2147483649LL, L"Npfs\\Aliases", v13, &v9, 0);
      if ( v4 < 0 )
      {
        ExFreePoolWithTag(NpAliases, 0);
        result = (unsigned int)v4;
        NpAliases = 0;
        return result;
      }
      if ( HIDWORD(v10) )
      {
        v5 = 0;
        do
        {
          v6 = *((_WORD *)v3 + 8);
          if ( (unsigned __int16)(v6 - 10) > 8u )
            v7 = &NpAliasList;
          else
            v7 = &NpAliasListByLength[((unsigned __int64)*((unsigned __int16 *)v3 + 8) - 10) >> 1];
          for ( i = *v7;
                i
             && *(_WORD *)(i + 16) <= v6
             && (*(_WORD *)(i + 16) < v6 || _wcsicmp(*((const wchar_t **)v3 + 3), *(const wchar_t **)(i + 24)) >= 0);
                i = *(_QWORD *)i )
          {
            v7 = (__int64 *)i;
          }
          ++v5;
          *(_QWORD *)v3 = *v7;
          *v7 = (__int64)v3;
          v3 += 32;
        }
        while ( v5 < HIDWORD(v10) );
      }
    }
    return 0;
  }
  else
  {
    result = 0;
    if ( v0 != -1073741772 )
      return (unsigned int)v0;
  }
  return result;
}

```

## disassembly

```asm
0x140018228  push    rbp
0x14001822a  push    rbx
0x14001822b  push    rsi
0x14001822c  push    rdi
0x14001822d  push    r13
0x14001822f  push    r14
0x140018231  push    r15
0x140018233  lea     rbp, [rsp-27h]
0x140018238  sub     rsp, 0D0h
0x14001823f  xor     eax, eax
0x140018241  lea     rcx, [rbp+57h+var_A0]; void *
0x140018245  xorps   xmm0, xmm0
0x140018248  xor     edx, edx; Val
0x14001824a  movups  [rbp+57h+var_C0], xmm0
0x14001824e  mov     qword ptr [rbp+57h+var_C0+0Dh], rax
0x140018252  lea     r8d, [rax+70h]; Size
0x140018256  movups  [rbp+57h+var_D0], xmm0
0x14001825a  call    memset
0x14001825f  lea     rax, NpReadAlias
0x140018266  mov     [rbp+57h+var_98], 10h
0x14001826d  mov     ebx, 80000001h
0x140018272  mov     [rbp+57h+var_A0], rax
0x140018276  mov     ecx, ebx
0x140018278  mov     [rbp+57h+var_80], 0
0x14001827f  lea     r9, [rbp+57h+var_D0]
0x140018283  mov     byte ptr [rbp+57h+var_D0], 1
0x140018287  lea     r8, [rbp+57h+var_A0]
0x14001828b  mov     qword ptr [rbp+57h+var_D0+4], 0
0x140018293  lea     rdx, aNpfsAliases; "Npfs\\Aliases"
0x14001829a  mov     dword ptr [rbp+57h+var_D0+0Ch], 0
0x1400182a1  mov     [rsp+100h+var_E0], 0
0x1400182aa  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400182b1  nop     dword ptr [rax+rax+00h]
0x1400182b6  mov     ecx, eax
0x1400182b8  test    eax, eax
0x1400182ba  jns     short loc_1400182CC
0x1400182bc  xor     eax, eax
0x1400182be  cmp     ecx, 0C0000034h
0x1400182c4  cmovnz  eax, ecx
0x1400182c7  jmp     loc_140018403
0x1400182cc  mov     eax, dword ptr [rbp+57h+var_D0+4]
0x1400182cf  test    eax, eax
0x1400182d1  jz      loc_140018401
0x1400182d7  mov     edx, eax
0x1400182d9  mov     ecx, 40h ; '@'
0x1400182de  mov     r8d, 7366704Eh
0x1400182e4  call    cs:__imp_ExAllocatePool2
0x1400182eb  nop     dword ptr [rax+rax+00h]
0x1400182f0  mov     cs:NpAliases, rax
0x1400182f7  test    rax, rax
0x1400182fa  jnz     short loc_140018306
0x1400182fc  mov     eax, 0C000009Ah
0x140018301  jmp     loc_140018403
0x140018306  mov     edi, dword ptr [rbp+57h+var_D0+0Ch]
0x140018309  lea     r9, [rbp+57h+var_D0]
0x14001830d  mov     qword ptr [rbp+57h+var_C0+8], rax
0x140018311  lea     r8, [rbp+57h+var_A0]
0x140018315  shl     rdi, 4
0x140018319  lea     rdx, aNpfsAliases; "Npfs\\Aliases"
0x140018320  add     rdi, rax
0x140018323  mov     byte ptr [rbp+57h+var_D0], 0
0x140018327  mov     eax, dword ptr [rbp+57h+var_D0+8]
0x14001832a  mov     ecx, ebx
0x14001832c  shl     rax, 5
0x140018330  add     rax, rdi
0x140018333  mov     qword ptr [rbp+57h+var_C0], rdi
0x140018337  mov     [rbp+57h+var_B0], rax
0x14001833b  mov     [rsp+100h+var_E0], 0
0x140018344  call    cs:__imp_RtlQueryRegistryValuesEx
0x14001834b  nop     dword ptr [rax+rax+00h]
0x140018350  mov     ebx, eax
0x140018352  test    eax, eax
0x140018354  jns     short loc_14001837D
0x140018356  mov     rcx, cs:NpAliases; P
0x14001835d  xor     edx, edx; Tag
0x14001835f  call    cs:__imp_ExFreePoolWithTag
0x140018366  nop     dword ptr [rax+rax+00h]
0x14001836b  mov     eax, ebx
0x14001836d  mov     cs:NpAliases, 0
0x140018378  jmp     loc_140018403
0x14001837d  cmp     dword ptr [rbp+57h+var_D0+8], 0
0x140018381  jbe     short loc_140018401
0x140018383  xor     r15d, r15d
0x140018386  lea     r13d, [r15+0Ah]
0x14001838a  movzx   r14d, word ptr [rdi+10h]
0x14001838f  movzx   eax, r14w
0x140018393  sub     ax, r13w
0x140018397  cmp     ax, 8
0x14001839b  ja      short loc_1400183B3
0x14001839d  mov     eax, r14d
0x1400183a0  lea     rcx, NpAliasListByLength
0x1400183a7  sub     rax, r13
0x1400183aa  shr     rax, 1
0x1400183ad  lea     rsi, [rcx+rax*8]
0x1400183b1  jmp     short loc_1400183BA
0x1400183b3  lea     rsi, NpAliasList
0x1400183ba  mov     rbx, [rsi]
0x1400183bd  jmp     short loc_1400183E6
0x1400183bf  cmp     [rbx+10h], r14w
0x1400183c4  ja      short loc_1400183EB
0x1400183c6  jb      short loc_1400183E0
0x1400183c8  mov     rdx, [rbx+18h]; Str2
0x1400183cc  mov     rcx, [rdi+18h]; Str1
0x1400183d0  call    cs:__imp__wcsicmp
0x1400183d7  nop     dword ptr [rax+rax+00h]
0x1400183dc  test    eax, eax
0x1400183de  js      short loc_1400183EB
0x1400183e0  mov     rsi, rbx
0x1400183e3  mov     rbx, [rbx]
0x1400183e6  test    rbx, rbx
0x1400183e9  jnz     short loc_1400183BF
0x1400183eb  mov     rax, [rsi]
0x1400183ee  inc     r15d
0x1400183f1  mov     [rdi], rax
0x1400183f4  mov     [rsi], rdi
0x1400183f7  add     rdi, 20h ; ' '
0x1400183fb  cmp     r15d, dword ptr [rbp+57h+var_D0+8]
0x1400183ff  jb      short loc_14001838A
0x140018401  xor     eax, eax
0x140018403  add     rsp, 0D0h
0x14001840a  pop     r15
0x14001840c  pop     r14
0x14001840e  pop     r13
0x140018410  pop     rdi
0x140018411  pop     rsi
0x140018412  pop     rbx
0x140018413  pop     rbp
0x140018414  retn
```
