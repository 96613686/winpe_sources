# CipSetUmciExclusionPaths

- ea: `0x18005f308`
- end: `0x18005f50e`
- name: `CipSetUmciExclusionPaths`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18005dfd0`

## callees

- `0x18001c49c`
- `0x18002c040`
- `0x18002c340`
- `0x18005ec0c`
- `0x18005ec70`
- `0x18005f308`
- `0x1800d7b8c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18005f47c`
- `ntoskrnl!ExAllocatePool2` at `0x18005f47c`

## string_xrefs

- `0x18005f330`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\TRSData`
- `0x18005f343`: `TestPath`

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
0x18005f308  mov     [rsp-8+arg_10], rbx
0x18005f30d  mov     [rsp-8+arg_18], rsi
0x18005f312  push    rbp
0x18005f313  push    rdi
0x18005f314  push    r12
0x18005f316  push    r14
0x18005f318  push    r15
0x18005f31a  lea     rbp, [rsp-37h]
0x18005f31f  sub     rsp, 0A0h
0x18005f326  xor     edi, edi
0x18005f328  mov     [rbp+57h+var_80], 7C007Ah
0x18005f330  lea     rax, aRegistryMachin_14; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18005f337  mov     [rbp+57h+P], rdi
0x18005f33b  mov     [rbp+57h+var_78], rax
0x18005f33f  lea     rdx, [rbp+57h+arg_0]
0x18005f343  lea     rax, aTestpath; "TestPath"
0x18005f34a  mov     [rbp+57h+arg_0], edi
0x18005f34d  mov     [rbp+57h+var_68], rax
0x18005f351  lea     rcx, [rbp+57h+P]
0x18005f355  xor     eax, eax
0x18005f357  mov     [rbp+57h+var_70], 120010h
0x18005f35e  mov     [rbp+57h+var_58+4], rax
0x18005f362  mov     [rbp+57h+var_4C], eax
0x18005f365  lea     rax, aTestframeworks; "TestFrameworks"
0x18005f36c  mov     [rbp+57h+var_40], rax
0x18005f370  xor     eax, eax
0x18005f372  mov     [rbp+57h+Src+4], rax
0x18005f376  mov     [rbp+57h+var_24], eax
0x18005f379  mov     [rbp+57h+var_60], 7
0x18005f381  mov     dword ptr [rbp+57h+var_58], edi
0x18005f384  mov     [rbp+57h+var_48], 1E001Ch
0x18005f38b  mov     [rbp+57h+var_38], 7
0x18005f393  mov     dword ptr [rbp+57h+Src], edi
0x18005f396  call    CipGetSbcpMergeListString
0x18005f39b  mov     rsi, [rbp+57h+P]
0x18005f39f  mov     r15d, eax
0x18005f3a2  test    eax, eax
0x18005f3a4  js      short loc_18005F3D9
0x18005f3a6  test    rsi, rsi
0x18005f3a9  jz      short loc_18005F417
0x18005f3ab  cmp     [rbp+57h+arg_0], edi
0x18005f3ae  jz      short loc_18005F417
0x18005f3b0  mov     ebx, [rbp+57h+arg_0]
0x18005f3b3  mov     r14, rsi
0x18005f3b6  test    r14, r14
0x18005f3b9  jz      short loc_18005F3D9
0x18005f3bb  mov     cs:g_CiExclusionList, r14
0x18005f3c2  mov     eax, 2
0x18005f3c7  mov     cs:g_CiExclusionListCount, ebx
0x18005f3cd  mov     [rbp+57h+Src], rdi
0x18005f3d1  sub     eax, 1
0x18005f3d4  jnz     short loc_18005F3CD
0x18005f3d6  mov     rsi, rdi
0x18005f3d9  mov     edx, 2
0x18005f3de  lea     rcx, [rbp+57h+var_70]
0x18005f3e2  call    CipFreeRegistryParameters
0x18005f3e7  test    rsi, rsi
0x18005f3ea  jz      short loc_18005F3F7
0x18005f3ec  mov     edx, [rbp+57h+arg_0]
0x18005f3ef  mov     rcx, rsi; P
0x18005f3f2  call    CipFreeUnicodeStringList
0x18005f3f7  lea     r11, [rsp+0C0h+var_20]
0x18005f3ff  mov     eax, r15d
0x18005f402  mov     rbx, [r11+40h]
0x18005f406  mov     rsi, [r11+48h]
0x18005f40a  mov     rsp, r11
0x18005f40d  pop     r15
0x18005f40f  pop     r14
0x18005f411  pop     r12
0x18005f413  pop     rdi
0x18005f414  pop     rbp
0x18005f415  retn
0x18005f417  lea     r9, ProhibitedExclusions
0x18005f41e  mov     [rsp+0C0h+var_A0], 8
0x18005f426  mov     r8d, 2
0x18005f42c  lea     rdx, [rbp+57h+var_70]
0x18005f430  lea     rcx, [rbp+57h+var_80]
0x18005f434  call    CipGetRegistryParameters
0x18005f439  mov     r15d, eax
0x18005f43c  test    eax, eax
0x18005f43e  js      short loc_18005F3D9
0x18005f440  mov     r12, [rbp+57h+var_58]
0x18005f444  mov     r14, [rbp+57h+Src]
0x18005f448  mov     ebx, [rbp+57h+var_28]
0x18005f44b  test    r12, r12
0x18005f44e  jz      loc_18005F3B6
0x18005f454  mov     eax, [rbp+57h+var_50]
0x18005f457  mov     dword ptr [rbp+57h+P], eax
0x18005f45a  test    r14, r14
0x18005f45d  jz      loc_18005F4F5
0x18005f463  add     eax, ebx
0x18005f465  mov     ecx, 102h
0x18005f46a  mov     edx, eax
0x18005f46c  mov     r8d, 63734943h
0x18005f472  shl     rdx, 4
0x18005f476  mov     cs:g_CiExclusionListCount, eax
0x18005f47c  call    cs:__imp_ExAllocatePool2
0x18005f483  nop     dword ptr [rax+rax+00h]
0x18005f488  mov     cs:g_CiExclusionList, rax
0x18005f48f  test    rax, rax
0x18005f492  jnz     short loc_18005F4A5
0x18005f494  mov     r15d, 0C0000017h
0x18005f49a  mov     cs:g_CiExclusionListCount, edi
0x18005f4a0  jmp     loc_18005F3D9
0x18005f4a5  mov     rdi, rbx
0x18005f4a8  mov     rdx, r14; Src
0x18005f4ab  shl     rdi, 4
0x18005f4af  mov     rcx, rax; void *
0x18005f4b2  mov     r8, rdi; Size
0x18005f4b5  call    memmove
0x18005f4ba  mov     ebx, dword ptr [rbp+57h+P]
0x18005f4bd  mov     rdx, r12; Src
0x18005f4c0  mov     rcx, cs:g_CiExclusionList
0x18005f4c7  shl     rbx, 4
0x18005f4cb  add     rcx, rdi; void *
0x18005f4ce  mov     r8, rbx; Size
0x18005f4d1  call    memmove
0x18005f4d6  mov     r8, rdi; Size
0x18005f4d9  xor     edx, edx; Val
0x18005f4db  mov     rcx, r14; void *
0x18005f4de  call    memset
0x18005f4e3  mov     r8, rbx; Size
0x18005f4e6  xor     edx, edx; Val
0x18005f4e8  mov     rcx, r12; void *
0x18005f4eb  call    memset
0x18005f4f0  jmp     loc_18005F3D9
0x18005f4f5  mov     cs:g_CiExclusionList, r12
0x18005f4fc  mov     cs:g_CiExclusionListCount, eax
0x18005f502  mov     [rbp+57h+var_58], rdi
0x18005f506  mov     [rbp+57h+var_50], edi
0x18005f509  jmp     loc_18005F3D9
```
