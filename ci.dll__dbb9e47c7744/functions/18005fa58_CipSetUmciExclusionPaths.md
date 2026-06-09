# CipSetUmciExclusionPaths

- ea: `0x18005fa58`
- end: `0x18005fc5e`
- name: `CipSetUmciExclusionPaths`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18005e6d0`

## callees

- `0x18001c37c`
- `0x18002c080`
- `0x18002c380`
- `0x18005f358`
- `0x18005f3bc`
- `0x18005fa58`
- `0x1800d8abc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18005fbcc`
- `ntoskrnl!ExAllocatePool2` at `0x18005fbcc`

## string_xrefs

- `0x18005fa80`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\TRSData`
- `0x18005fa93`: `TestPath`

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
0x18005fa58  mov     [rsp-8+arg_10], rbx
0x18005fa5d  mov     [rsp-8+arg_18], rsi
0x18005fa62  push    rbp
0x18005fa63  push    rdi
0x18005fa64  push    r12
0x18005fa66  push    r14
0x18005fa68  push    r15
0x18005fa6a  lea     rbp, [rsp-37h]
0x18005fa6f  sub     rsp, 0A0h
0x18005fa76  xor     edi, edi
0x18005fa78  mov     [rbp+57h+var_80], 7C007Ah
0x18005fa80  lea     rax, aRegistryMachin_13; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18005fa87  mov     [rbp+57h+P], rdi
0x18005fa8b  mov     [rbp+57h+var_78], rax
0x18005fa8f  lea     rdx, [rbp+57h+arg_0]
0x18005fa93  lea     rax, aTestpath; "TestPath"
0x18005fa9a  mov     [rbp+57h+arg_0], edi
0x18005fa9d  mov     [rbp+57h+var_68], rax
0x18005faa1  lea     rcx, [rbp+57h+P]
0x18005faa5  xor     eax, eax
0x18005faa7  mov     [rbp+57h+var_70], 120010h
0x18005faae  mov     [rbp+57h+var_58+4], rax
0x18005fab2  mov     [rbp+57h+var_4C], eax
0x18005fab5  lea     rax, aTestframeworks; "TestFrameworks"
0x18005fabc  mov     [rbp+57h+var_40], rax
0x18005fac0  xor     eax, eax
0x18005fac2  mov     [rbp+57h+Src+4], rax
0x18005fac6  mov     [rbp+57h+var_24], eax
0x18005fac9  mov     [rbp+57h+var_60], 7
0x18005fad1  mov     dword ptr [rbp+57h+var_58], edi
0x18005fad4  mov     [rbp+57h+var_48], 1E001Ch
0x18005fadb  mov     [rbp+57h+var_38], 7
0x18005fae3  mov     dword ptr [rbp+57h+Src], edi
0x18005fae6  call    CipGetSbcpMergeListString
0x18005faeb  mov     rsi, [rbp+57h+P]
0x18005faef  mov     r15d, eax
0x18005faf2  test    eax, eax
0x18005faf4  js      short loc_18005FB29
0x18005faf6  test    rsi, rsi
0x18005faf9  jz      short loc_18005FB67
0x18005fafb  cmp     [rbp+57h+arg_0], edi
0x18005fafe  jz      short loc_18005FB67
0x18005fb00  mov     ebx, [rbp+57h+arg_0]
0x18005fb03  mov     r14, rsi
0x18005fb06  test    r14, r14
0x18005fb09  jz      short loc_18005FB29
0x18005fb0b  mov     cs:g_CiExclusionList, r14
0x18005fb12  mov     eax, 2
0x18005fb17  mov     cs:g_CiExclusionListCount, ebx
0x18005fb1d  mov     [rbp+57h+Src], rdi
0x18005fb21  sub     eax, 1
0x18005fb24  jnz     short loc_18005FB1D
0x18005fb26  mov     rsi, rdi
0x18005fb29  mov     edx, 2
0x18005fb2e  lea     rcx, [rbp+57h+var_70]
0x18005fb32  call    CipFreeRegistryParameters
0x18005fb37  test    rsi, rsi
0x18005fb3a  jz      short loc_18005FB47
0x18005fb3c  mov     edx, [rbp+57h+arg_0]
0x18005fb3f  mov     rcx, rsi; P
0x18005fb42  call    CipFreeUnicodeStringList
0x18005fb47  lea     r11, [rsp+0C0h+var_20]
0x18005fb4f  mov     eax, r15d
0x18005fb52  mov     rbx, [r11+40h]
0x18005fb56  mov     rsi, [r11+48h]
0x18005fb5a  mov     rsp, r11
0x18005fb5d  pop     r15
0x18005fb5f  pop     r14
0x18005fb61  pop     r12
0x18005fb63  pop     rdi
0x18005fb64  pop     rbp
0x18005fb65  retn
0x18005fb67  lea     r9, ProhibitedExclusions
0x18005fb6e  mov     [rsp+0C0h+var_A0], 8
0x18005fb76  mov     r8d, 2
0x18005fb7c  lea     rdx, [rbp+57h+var_70]
0x18005fb80  lea     rcx, [rbp+57h+var_80]
0x18005fb84  call    CipGetRegistryParameters
0x18005fb89  mov     r15d, eax
0x18005fb8c  test    eax, eax
0x18005fb8e  js      short loc_18005FB29
0x18005fb90  mov     r12, [rbp+57h+var_58]
0x18005fb94  mov     r14, [rbp+57h+Src]
0x18005fb98  mov     ebx, [rbp+57h+var_28]
0x18005fb9b  test    r12, r12
0x18005fb9e  jz      loc_18005FB06
0x18005fba4  mov     eax, [rbp+57h+var_50]
0x18005fba7  mov     dword ptr [rbp+57h+P], eax
0x18005fbaa  test    r14, r14
0x18005fbad  jz      loc_18005FC45
0x18005fbb3  add     eax, ebx
0x18005fbb5  mov     ecx, 102h
0x18005fbba  mov     edx, eax
0x18005fbbc  mov     r8d, 63734943h
0x18005fbc2  shl     rdx, 4
0x18005fbc6  mov     cs:g_CiExclusionListCount, eax
0x18005fbcc  call    cs:__imp_ExAllocatePool2
0x18005fbd3  nop     dword ptr [rax+rax+00h]
0x18005fbd8  mov     cs:g_CiExclusionList, rax
0x18005fbdf  test    rax, rax
0x18005fbe2  jnz     short loc_18005FBF5
0x18005fbe4  mov     r15d, 0C0000017h
0x18005fbea  mov     cs:g_CiExclusionListCount, edi
0x18005fbf0  jmp     loc_18005FB29
0x18005fbf5  mov     rdi, rbx
0x18005fbf8  mov     rdx, r14; Src
0x18005fbfb  shl     rdi, 4
0x18005fbff  mov     rcx, rax; void *
0x18005fc02  mov     r8, rdi; Size
0x18005fc05  call    memmove
0x18005fc0a  mov     ebx, dword ptr [rbp+57h+P]
0x18005fc0d  mov     rdx, r12; Src
0x18005fc10  mov     rcx, cs:g_CiExclusionList
0x18005fc17  shl     rbx, 4
0x18005fc1b  add     rcx, rdi; void *
0x18005fc1e  mov     r8, rbx; Size
0x18005fc21  call    memmove
0x18005fc26  mov     r8, rdi; Size
0x18005fc29  xor     edx, edx; Val
0x18005fc2b  mov     rcx, r14; void *
0x18005fc2e  call    memset
0x18005fc33  mov     r8, rbx; Size
0x18005fc36  xor     edx, edx; Val
0x18005fc38  mov     rcx, r12; void *
0x18005fc3b  call    memset
0x18005fc40  jmp     loc_18005FB29
0x18005fc45  mov     cs:g_CiExclusionList, r12
0x18005fc4c  mov     cs:g_CiExclusionListCount, eax
0x18005fc52  mov     [rbp+57h+var_58], rdi
0x18005fc56  mov     [rbp+57h+var_50], edi
0x18005fc59  jmp     loc_18005FB29
```
