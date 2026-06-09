# MupiSurrogateRegisterProviderInternal

- ea: `0x140014914`
- end: `0x140014b5e`
- name: `MupiSurrogateRegisterProviderInternal`
- size: `586`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140014330`
- `0x140014360`

## callees

- `0x140002b18`
- `0x140002c28`
- `0x140003f80`
- `0x140014740`
- `0x140014774`
- `0x140014814`
- `0x1400148b8`
- `0x140014914`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140014a72`
- `ntoskrnl!ExReleaseResourceLite` at `0x140014a72`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140014a01`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140014a01`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014a7e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014a7e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001497f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001497f`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140014b1f`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140014b1f`

## pseudocode

```c
__int64 __fastcall MupiSurrogateRegisterProviderInternal(PCUNICODE_STRING SourceString, int a2, __int64 a3)
{
  __int64 i; // rbx
  unsigned int DeviceObjectPointer; // edi
  __int64 v8; // rax
  __int64 v9; // rbx
  int v10; // r8d
  int v12; // eax
  __int64 v13; // [rsp+28h] [rbp-50h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_0fb1d46681b331a7af1167046103ae69_Traceguids, SourceString);
  }
  MupiAcquireSurrogateListLockExclusive();
  for ( i = qword_14000A588; ; i = *(_QWORD *)i )
  {
    if ( (__int64 *)i == &qword_14000A588 )
      goto LABEL_13;
    if ( RtlEqualUnicodeString(SourceString, (PCUNICODE_STRING)(i + 32), 1u) && a2 == *(_DWORD *)(i + 16)
      || (unsigned int)(a2 - 1) <= 1 && a2 == *(_DWORD *)(i + 16) )
    {
      break;
    }
  }
  if ( i != 8 )
  {
    DeviceObjectPointer = -1073741808;
LABEL_21:
    LOBYTE(v9) = 0;
    goto LABEL_22;
  }
LABEL_13:
  v8 = MupiAllocSurrogateProvider(SourceString->Length);
  v9 = v8;
  if ( !v8 )
  {
    DeviceObjectPointer = -1073741670;
    goto LABEL_22;
  }
  *(_DWORD *)(v8 + 24) = a2;
  *(_WORD *)(v8 + 28) = *(_WORD *)(a3 + 2);
  *(_WORD *)(v8 + 40) = 0;
  *(_WORD *)(v8 + 42) = SourceString->Length;
  *(_QWORD *)(v8 + 48) = v8 + 120;
  RtlCopyUnicodeString((PUNICODE_STRING)(v8 + 40), SourceString);
  if ( *(_BYTE *)(v9 + 29) == 1 )
  {
    *(_QWORD *)(v9 + 72) = *(_QWORD *)(a3 + 8);
    *(_QWORD *)(v9 + 80) = *(_QWORD *)(a3 + 16);
  }
  else
  {
    if ( *(_BYTE *)(v9 + 29) != 2 )
    {
      DeviceObjectPointer = -1073741595;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
      {
        WPP_SF_ZddD(
          WPP_GLOBAL_Control->AttachedDevice,
          *(unsigned __int8 *)(a3 + 3),
          v10,
          (_DWORD)SourceString,
          *(_BYTE *)(a3 + 3),
          *(_BYTE *)(a3 + 2),
          229);
      }
      goto LABEL_20;
    }
    *(_QWORD *)(v9 + 72) = *(_QWORD *)(a3 + 8);
    *(_QWORD *)(v9 + 80) = *(_QWORD *)(a3 + 16);
    *(_DWORD *)(v9 + 108) = *(_DWORD *)(a3 + 24) & 7;
    if ( *(_WORD *)(a3 + 2) >= 0x201u )
      *(_DWORD *)(v9 + 112) = *(_DWORD *)(a3 + 28) & 1;
  }
  DeviceObjectPointer = IoGetDeviceObjectPointer(
                          (PUNICODE_STRING)(v9 + 40),
                          0x20u,
                          (PFILE_OBJECT *)(v9 + 64),
                          (PDEVICE_OBJECT *)(v9 + 56));
  if ( DeviceObjectPointer )
  {
LABEL_20:
    MupiFreeSurrogateProvider((PVOID)v9);
    goto LABEL_21;
  }
  v12 = *(_DWORD *)(v9 + 24) - 1;
  *(_DWORD *)(v9 + 32) = 2;
  if ( (v12 & 0xFFFFFFFD) == 0 )
    _InterlockedIncrement(&MupiCachingAndGenericSurrogateCount);
  MupiAddSurrogateToList(v9);
  DeviceObjectPointer = 0;
LABEL_22:
  ExReleaseResourceLite(&stru_14000A5A0);
  KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    LODWORD(v13) = DeviceObjectPointer;
    WPP_SF_ZqD(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      (unsigned int)WPP_0fb1d46681b331a7af1167046103ae69_Traceguids,
      (_DWORD)SourceString,
      v9,
      v13);
  }
  return DeviceObjectPointer;
}

```

## disassembly

```asm
0x140014914  push    rbx
0x140014916  push    rbp
0x140014917  push    rsi
0x140014918  push    rdi
0x140014919  push    r12
0x14001491b  push    r14
0x14001491d  sub     rsp, 48h
0x140014921  mov     rsi, r8
0x140014924  mov     ebp, edx
0x140014926  mov     r14, rcx
0x140014929  mov     rcx, cs:WPP_GLOBAL_Control
0x140014930  lea     r12, WPP_GLOBAL_Control
0x140014937  cmp     rcx, r12
0x14001493a  jz      short loc_14001495D
0x14001493c  test    dword ptr [rcx+2Ch], 2000000h
0x140014943  jz      short loc_14001495D
0x140014945  mov     rcx, [rcx+18h]
0x140014949  lea     r8, WPP_0fb1d46681b331a7af1167046103ae69_Traceguids
0x140014950  mov     edx, 0Bh
0x140014955  mov     r9, r14
0x140014958  call    WPP_SF_Z
0x14001495d  call    MupiAcquireSurrogateListLockExclusive
0x140014962  mov     rbx, cs:qword_14000A588
0x140014969  lea     rax, qword_14000A588
0x140014970  cmp     rbx, rax
0x140014973  jz      short loc_1400149BC
0x140014975  lea     rdx, [rbx+20h]; String2
0x140014979  mov     r8b, 1; CaseInSensitive
0x14001497c  mov     rcx, r14; String1
0x14001497f  call    cs:__imp_RtlEqualUnicodeString
0x140014986  nop     dword ptr [rax+rax+00h]
0x14001498b  test    al, al
0x14001498d  jz      short loc_140014994
0x14001498f  cmp     ebp, [rbx+10h]
0x140014992  jz      short loc_1400149A6
0x140014994  lea     eax, [rbp-1]
0x140014997  cmp     eax, 1
0x14001499a  ja      short loc_1400149A1
0x14001499c  cmp     ebp, [rbx+10h]
0x14001499f  jz      short loc_1400149A6
0x1400149a1  mov     rbx, [rbx]
0x1400149a4  jmp     short loc_140014969
0x1400149a6  mov     rax, 0FFFFFFFFFFFFFFF8h
0x1400149ad  add     rax, rbx
0x1400149b0  jz      short loc_1400149BC
0x1400149b2  mov     edi, 0C0000010h
0x1400149b7  jmp     loc_140014A69
0x1400149bc  movzx   ecx, word ptr [r14]
0x1400149c0  call    MupiAllocSurrogateProvider
0x1400149c5  mov     rbx, rax
0x1400149c8  test    rax, rax
0x1400149cb  jnz     short loc_1400149D7
0x1400149cd  mov     edi, 0C000009Ah
0x1400149d2  jmp     loc_140014A6B
0x1400149d7  mov     [rax+18h], ebp
0x1400149da  lea     rdi, [rbx+28h]
0x1400149de  movzx   eax, word ptr [rsi+2]
0x1400149e2  mov     rdx, r14; SourceString
0x1400149e5  mov     [rbx+1Ch], ax
0x1400149e9  mov     rcx, rdi; DestinationString
0x1400149ec  xor     eax, eax
0x1400149ee  mov     [rdi], ax
0x1400149f1  movzx   eax, word ptr [r14]
0x1400149f5  mov     [rbx+2Ah], ax
0x1400149f9  lea     rax, [rbx+78h]
0x1400149fd  mov     [rbx+30h], rax
0x140014a01  call    cs:__imp_RtlCopyUnicodeString
0x140014a08  nop     dword ptr [rax+rax+00h]
0x140014a0d  movzx   ecx, byte ptr [rbx+1Dh]
0x140014a11  sub     ecx, 1
0x140014a14  jz      loc_140014AFF
0x140014a1a  cmp     ecx, 1
0x140014a1d  jz      loc_140014AD0
0x140014a23  mov     edi, 0C00000E5h
0x140014a28  mov     rcx, cs:WPP_GLOBAL_Control
0x140014a2f  cmp     rcx, r12
0x140014a32  jz      short loc_140014A61
0x140014a34  test    dword ptr [rcx+2Ch], 2000000h
0x140014a3b  jz      short loc_140014A61
0x140014a3d  movzx   eax, byte ptr [rsi+2]
0x140014a41  mov     r9, r14
0x140014a44  movzx   edx, byte ptr [rsi+3]
0x140014a48  mov     rcx, [rcx+18h]
0x140014a4c  mov     [rsp+78h+var_48], 0C00000E5h
0x140014a54  mov     dword ptr [rsp+78h+var_50], eax
0x140014a58  mov     dword ptr [rsp+78h+var_58], edx
0x140014a5c  call    WPP_SF_ZddD
0x140014a61  mov     rcx, rbx; P
0x140014a64  call    MupiFreeSurrogateProvider
0x140014a69  xor     ebx, ebx
0x140014a6b  lea     rcx, stru_14000A5A0; Resource
0x140014a72  call    cs:__imp_ExReleaseResourceLite
0x140014a79  nop     dword ptr [rax+rax+00h]
0x140014a7e  call    cs:__imp_KeLeaveCriticalRegion
0x140014a85  nop     dword ptr [rax+rax+00h]
0x140014a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140014a91  cmp     rcx, r12
0x140014a94  jz      short loc_140014AC0
0x140014a96  test    dword ptr [rcx+2Ch], 2000000h
0x140014a9d  jz      short loc_140014AC0
0x140014a9f  mov     rcx, [rcx+18h]
0x140014aa3  lea     r8, WPP_0fb1d46681b331a7af1167046103ae69_Traceguids
0x140014aaa  mov     edx, 0Dh
0x140014aaf  mov     dword ptr [rsp+78h+var_50], edi
0x140014ab3  mov     r9, r14
0x140014ab6  mov     [rsp+78h+var_58], rbx
0x140014abb  call    WPP_SF_ZqD
0x140014ac0  mov     eax, edi
0x140014ac2  add     rsp, 48h
0x140014ac6  pop     r14
0x140014ac8  pop     r12
0x140014aca  pop     rdi
0x140014acb  pop     rsi
0x140014acc  pop     rbp
0x140014acd  pop     rbx
0x140014ace  retn
0x140014ad0  mov     rax, [rsi+8]
0x140014ad4  mov     [rbx+48h], rax
0x140014ad8  mov     rax, [rsi+10h]
0x140014adc  mov     [rbx+50h], rax
0x140014ae0  mov     eax, [rsi+18h]
0x140014ae3  and     eax, 7
0x140014ae6  mov     [rbx+6Ch], eax
0x140014ae9  mov     eax, 201h
0x140014aee  cmp     [rsi+2], ax
0x140014af2  jb      short loc_140014B0F
0x140014af4  mov     eax, [rsi+1Ch]
0x140014af7  and     eax, 1
0x140014afa  mov     [rbx+70h], eax
0x140014afd  jmp     short loc_140014B0F
0x140014aff  mov     rax, [rsi+8]
0x140014b03  mov     [rbx+48h], rax
0x140014b07  mov     rax, [rsi+10h]
0x140014b0b  mov     [rbx+50h], rax
0x140014b0f  lea     r9, [rbx+38h]; DeviceObject
0x140014b13  mov     edx, 20h ; ' '; DesiredAccess
0x140014b18  lea     r8, [rbx+40h]; FileObject
0x140014b1c  mov     rcx, rdi; ObjectName
0x140014b1f  call    cs:__imp_IoGetDeviceObjectPointer
0x140014b26  nop     dword ptr [rax+rax+00h]
0x140014b2b  mov     edi, eax
0x140014b2d  test    eax, eax
0x140014b2f  jnz     loc_140014A61
0x140014b35  mov     eax, [rbx+18h]
0x140014b38  dec     eax
0x140014b3a  mov     dword ptr [rbx+20h], 2
0x140014b41  test    eax, 0FFFFFFFDh
0x140014b46  jnz     short loc_140014B4F
0x140014b48  lock inc cs:MupiCachingAndGenericSurrogateCount
0x140014b4f  mov     rcx, rbx
0x140014b52  call    MupiAddSurrogateToList
0x140014b57  xor     edi, edi
0x140014b59  jmp     loc_140014A6B
```
