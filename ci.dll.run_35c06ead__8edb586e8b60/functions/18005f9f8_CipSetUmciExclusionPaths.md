# CipSetUmciExclusionPaths

- ea: `0x18005f9f8`
- end: `0x18005fbfe`
- name: `CipSetUmciExclusionPaths`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18005e670`

## callees

- `0x18001c3dc`
- `0x18002c200`
- `0x18002c500`
- `0x18005f2f8`
- `0x18005f35c`
- `0x18005f9f8`
- `0x1800d8acc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18005fb6c`
- `ntoskrnl!ExAllocatePool2` at `0x18005fb6c`

## string_xrefs

- `0x18005fa20`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\TRSData`
- `0x18005fa33`: `TestPath`

## pseudocode

```c
__int64 CipSetUmciExclusionPaths()
{
  int SbcpMergeListString; // eax
  PVOID v1; // rsi
  int RegistryParameters; // r15d
  __int64 v3; // rbx
  PVOID v4; // r14
  int v5; // eax
  void *v7; // r12
  void *Pool2; // rax
  size_t v9; // rdi
  size_t v10; // rbx
  struct _UNICODE_STRING v11; // [rsp+40h] [rbp-29h] BYREF
  int v12; // [rsp+50h] [rbp-19h] BYREF
  const wchar_t *v13; // [rsp+58h] [rbp-11h]
  __int64 v14; // [rsp+60h] [rbp-9h]
  _BYTE v15[12]; // [rsp+68h] [rbp-1h] BYREF
  int v16; // [rsp+74h] [rbp+Bh]
  int v17; // [rsp+78h] [rbp+Fh]
  const wchar_t *v18; // [rsp+80h] [rbp+17h]
  __int64 v19; // [rsp+88h] [rbp+1Fh]
  _BYTE Src[12]; // [rsp+90h] [rbp+27h] BYREF
  int v21; // [rsp+9Ch] [rbp+33h]
  int v22; // [rsp+D0h] [rbp+67h] BYREF
  PVOID P; // [rsp+D8h] [rbp+6Fh] BYREF

  *(_QWORD *)&v11.Length = 8126586;
  P = 0;
  v11.Buffer = L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\TRSData";
  v22 = 0;
  v13 = L"TestPath";
  v12 = 1179664;
  v16 = 0;
  v18 = L"TestFrameworks";
  v21 = 0;
  v14 = 7;
  memset(v15, 0, sizeof(v15));
  v17 = 1966108;
  v19 = 7;
  memset(Src, 0, sizeof(Src));
  SbcpMergeListString = CipGetSbcpMergeListString(&P, &v22);
  v1 = P;
  RegistryParameters = SbcpMergeListString;
  if ( SbcpMergeListString >= 0 )
  {
    if ( P && v22 )
    {
      LODWORD(v3) = v22;
      v4 = P;
    }
    else
    {
      RegistryParameters = CipGetRegistryParameters(&v11, (__int64)&v12, 2u, (__int64)&ProhibitedExclusions, 8);
      if ( RegistryParameters < 0 )
        goto LABEL_9;
      v7 = *(void **)v15;
      v4 = *(PVOID *)Src;
      v3 = *(unsigned int *)&Src[8];
      if ( *(_QWORD *)v15 )
      {
        LODWORD(P) = *(_DWORD *)&v15[8];
        if ( *(_QWORD *)Src )
        {
          g_CiExclusionListCount = *(_DWORD *)&Src[8] + *(_DWORD *)&v15[8];
          Pool2 = (void *)ExAllocatePool2(
                            258,
                            16LL * (unsigned int)(*(_DWORD *)&Src[8] + *(_DWORD *)&v15[8]),
                            1668499779);
          g_CiExclusionList = (__int64)Pool2;
          if ( Pool2 )
          {
            v9 = 16 * v3;
            memmove(Pool2, v4, 16 * v3);
            v10 = 16LL * (unsigned int)P;
            memmove((void *)(v9 + g_CiExclusionList), v7, v10);
            memset(v4, 0, v9);
            memset(v7, 0, v10);
          }
          else
          {
            RegistryParameters = -1073741801;
            g_CiExclusionListCount = 0;
          }
        }
        else
        {
          g_CiExclusionList = *(_QWORD *)v15;
          g_CiExclusionListCount = *(_DWORD *)&v15[8];
          memset(v15, 0, sizeof(v15));
        }
        goto LABEL_9;
      }
    }
    if ( v4 )
    {
      g_CiExclusionList = (__int64)v4;
      v5 = 2;
      g_CiExclusionListCount = v3;
      do
      {
        *(_QWORD *)Src = 0;
        --v5;
      }
      while ( v5 );
      v1 = 0;
    }
  }
LABEL_9:
  CipFreeRegistryParameters(&v12, 2);
  if ( v1 )
    CipFreeUnicodeStringList(v1);
  return (unsigned int)RegistryParameters;
}

```

## disassembly

```asm
0x18005f9f8  mov     [rsp-8+arg_10], rbx
0x18005f9fd  mov     [rsp-8+arg_18], rsi
0x18005fa02  push    rbp
0x18005fa03  push    rdi
0x18005fa04  push    r12
0x18005fa06  push    r14
0x18005fa08  push    r15
0x18005fa0a  lea     rbp, [rsp-37h]
0x18005fa0f  sub     rsp, 0A0h
0x18005fa16  xor     edi, edi
0x18005fa18  mov     [rbp+57h+var_80], 7C007Ah
0x18005fa20  lea     rax, aRegistryMachin_13; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18005fa27  mov     [rbp+57h+P], rdi
0x18005fa2b  mov     [rbp+57h+var_78], rax
0x18005fa2f  lea     rdx, [rbp+57h+arg_0]
0x18005fa33  lea     rax, aTestpath; "TestPath"
0x18005fa3a  mov     [rbp+57h+arg_0], edi
0x18005fa3d  mov     [rbp+57h+var_68], rax
0x18005fa41  lea     rcx, [rbp+57h+P]
0x18005fa45  xor     eax, eax
0x18005fa47  mov     [rbp+57h+var_70], 120010h
0x18005fa4e  mov     [rbp+57h+var_58+4], rax
0x18005fa52  mov     [rbp+57h+var_4C], eax
0x18005fa55  lea     rax, aTestframeworks; "TestFrameworks"
0x18005fa5c  mov     [rbp+57h+var_40], rax
0x18005fa60  xor     eax, eax
0x18005fa62  mov     [rbp+57h+Src+4], rax
0x18005fa66  mov     [rbp+57h+var_24], eax
0x18005fa69  mov     [rbp+57h+var_60], 7
0x18005fa71  mov     dword ptr [rbp+57h+var_58], edi
0x18005fa74  mov     [rbp+57h+var_48], 1E001Ch
0x18005fa7b  mov     [rbp+57h+var_38], 7
0x18005fa83  mov     dword ptr [rbp+57h+Src], edi
0x18005fa86  call    CipGetSbcpMergeListString
0x18005fa8b  mov     rsi, [rbp+57h+P]
0x18005fa8f  mov     r15d, eax
0x18005fa92  test    eax, eax
0x18005fa94  js      short loc_18005FAC9
0x18005fa96  test    rsi, rsi
0x18005fa99  jz      short loc_18005FB07
0x18005fa9b  cmp     [rbp+57h+arg_0], edi
0x18005fa9e  jz      short loc_18005FB07
0x18005faa0  mov     ebx, [rbp+57h+arg_0]
0x18005faa3  mov     r14, rsi
0x18005faa6  test    r14, r14
0x18005faa9  jz      short loc_18005FAC9
0x18005faab  mov     cs:g_CiExclusionList, r14
0x18005fab2  mov     eax, 2
0x18005fab7  mov     cs:g_CiExclusionListCount, ebx
0x18005fabd  mov     [rbp+57h+Src], rdi
0x18005fac1  sub     eax, 1
0x18005fac4  jnz     short loc_18005FABD
0x18005fac6  mov     rsi, rdi
0x18005fac9  mov     edx, 2
0x18005face  lea     rcx, [rbp+57h+var_70]
0x18005fad2  call    CipFreeRegistryParameters
0x18005fad7  test    rsi, rsi
0x18005fada  jz      short loc_18005FAE7
0x18005fadc  mov     edx, [rbp+57h+arg_0]
0x18005fadf  mov     rcx, rsi; P
0x18005fae2  call    CipFreeUnicodeStringList
0x18005fae7  lea     r11, [rsp+0C0h+var_20]
0x18005faef  mov     eax, r15d
0x18005faf2  mov     rbx, [r11+40h]
0x18005faf6  mov     rsi, [r11+48h]
0x18005fafa  mov     rsp, r11
0x18005fafd  pop     r15
0x18005faff  pop     r14
0x18005fb01  pop     r12
0x18005fb03  pop     rdi
0x18005fb04  pop     rbp
0x18005fb05  retn
0x18005fb07  lea     r9, ProhibitedExclusions
0x18005fb0e  mov     [rsp+0C0h+var_A0], 8
0x18005fb16  mov     r8d, 2
0x18005fb1c  lea     rdx, [rbp+57h+var_70]
0x18005fb20  lea     rcx, [rbp+57h+var_80]
0x18005fb24  call    CipGetRegistryParameters
0x18005fb29  mov     r15d, eax
0x18005fb2c  test    eax, eax
0x18005fb2e  js      short loc_18005FAC9
0x18005fb30  mov     r12, [rbp+57h+var_58]
0x18005fb34  mov     r14, [rbp+57h+Src]
0x18005fb38  mov     ebx, [rbp+57h+var_28]
0x18005fb3b  test    r12, r12
0x18005fb3e  jz      loc_18005FAA6
0x18005fb44  mov     eax, [rbp+57h+var_50]
0x18005fb47  mov     dword ptr [rbp+57h+P], eax
0x18005fb4a  test    r14, r14
0x18005fb4d  jz      loc_18005FBE5
0x18005fb53  add     eax, ebx
0x18005fb55  mov     ecx, 102h
0x18005fb5a  mov     edx, eax
0x18005fb5c  mov     r8d, 63734943h
0x18005fb62  shl     rdx, 4
0x18005fb66  mov     cs:g_CiExclusionListCount, eax
0x18005fb6c  call    cs:__imp_ExAllocatePool2
0x18005fb73  nop     dword ptr [rax+rax+00h]
0x18005fb78  mov     cs:g_CiExclusionList, rax
0x18005fb7f  test    rax, rax
0x18005fb82  jnz     short loc_18005FB95
0x18005fb84  mov     r15d, 0C0000017h
0x18005fb8a  mov     cs:g_CiExclusionListCount, edi
0x18005fb90  jmp     loc_18005FAC9
0x18005fb95  mov     rdi, rbx
0x18005fb98  mov     rdx, r14; Src
0x18005fb9b  shl     rdi, 4
0x18005fb9f  mov     rcx, rax; void *
0x18005fba2  mov     r8, rdi; Size
0x18005fba5  call    memmove
0x18005fbaa  mov     ebx, dword ptr [rbp+57h+P]
0x18005fbad  mov     rdx, r12; Src
0x18005fbb0  mov     rcx, cs:g_CiExclusionList
0x18005fbb7  shl     rbx, 4
0x18005fbbb  add     rcx, rdi; void *
0x18005fbbe  mov     r8, rbx; Size
0x18005fbc1  call    memmove
0x18005fbc6  mov     r8, rdi; Size
0x18005fbc9  xor     edx, edx; Val
0x18005fbcb  mov     rcx, r14; void *
0x18005fbce  call    memset
0x18005fbd3  mov     r8, rbx; Size
0x18005fbd6  xor     edx, edx; Val
0x18005fbd8  mov     rcx, r12; void *
0x18005fbdb  call    memset
0x18005fbe0  jmp     loc_18005FAC9
0x18005fbe5  mov     cs:g_CiExclusionList, r12
0x18005fbec  mov     cs:g_CiExclusionListCount, eax
0x18005fbf2  mov     [rbp+57h+var_58], rdi
0x18005fbf6  mov     [rbp+57h+var_50], edi
0x18005fbf9  jmp     loc_18005FAC9
```
