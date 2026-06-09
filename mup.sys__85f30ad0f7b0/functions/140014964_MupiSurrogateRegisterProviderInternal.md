# MupiSurrogateRegisterProviderInternal

- ea: `0x140014964`
- end: `0x140014bae`
- name: `MupiSurrogateRegisterProviderInternal`
- size: `586`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, int, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140014380`
- `0x1400143b0`

## callees

- `0x140002b18`
- `0x140002c28`
- `0x140003f80`
- `0x140014790`
- `0x1400147c4`
- `0x140014864`
- `0x140014908`
- `0x140014964`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140014ac2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140014ac2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140014a51`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140014a51`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014ace`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014ace`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400149cf`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400149cf`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140014b6f`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140014b6f`

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
0x140014964  push    rbx
0x140014966  push    rbp
0x140014967  push    rsi
0x140014968  push    rdi
0x140014969  push    r12
0x14001496b  push    r14
0x14001496d  sub     rsp, 48h
0x140014971  mov     rsi, r8
0x140014974  mov     ebp, edx
0x140014976  mov     r14, rcx
0x140014979  mov     rcx, cs:WPP_GLOBAL_Control
0x140014980  lea     r12, WPP_GLOBAL_Control
0x140014987  cmp     rcx, r12
0x14001498a  jz      short loc_1400149AD
0x14001498c  test    dword ptr [rcx+2Ch], 2000000h
0x140014993  jz      short loc_1400149AD
0x140014995  mov     rcx, [rcx+18h]
0x140014999  lea     r8, WPP_0fb1d46681b331a7af1167046103ae69_Traceguids
0x1400149a0  mov     edx, 0Bh
0x1400149a5  mov     r9, r14
0x1400149a8  call    WPP_SF_Z
0x1400149ad  call    MupiAcquireSurrogateListLockExclusive
0x1400149b2  mov     rbx, cs:qword_14000A588
0x1400149b9  lea     rax, qword_14000A588
0x1400149c0  cmp     rbx, rax
0x1400149c3  jz      short loc_140014A0C
0x1400149c5  lea     rdx, [rbx+20h]; String2
0x1400149c9  mov     r8b, 1; CaseInSensitive
0x1400149cc  mov     rcx, r14; String1
0x1400149cf  call    cs:__imp_RtlEqualUnicodeString
0x1400149d6  nop     dword ptr [rax+rax+00h]
0x1400149db  test    al, al
0x1400149dd  jz      short loc_1400149E4
0x1400149df  cmp     ebp, [rbx+10h]
0x1400149e2  jz      short loc_1400149F6
0x1400149e4  lea     eax, [rbp-1]
0x1400149e7  cmp     eax, 1
0x1400149ea  ja      short loc_1400149F1
0x1400149ec  cmp     ebp, [rbx+10h]
0x1400149ef  jz      short loc_1400149F6
0x1400149f1  mov     rbx, [rbx]
0x1400149f4  jmp     short loc_1400149B9
0x1400149f6  mov     rax, 0FFFFFFFFFFFFFFF8h
0x1400149fd  add     rax, rbx
0x140014a00  jz      short loc_140014A0C
0x140014a02  mov     edi, 0C0000010h
0x140014a07  jmp     loc_140014AB9
0x140014a0c  movzx   ecx, word ptr [r14]
0x140014a10  call    MupiAllocSurrogateProvider
0x140014a15  mov     rbx, rax
0x140014a18  test    rax, rax
0x140014a1b  jnz     short loc_140014A27
0x140014a1d  mov     edi, 0C000009Ah
0x140014a22  jmp     loc_140014ABB
0x140014a27  mov     [rax+18h], ebp
0x140014a2a  lea     rdi, [rbx+28h]
0x140014a2e  movzx   eax, word ptr [rsi+2]
0x140014a32  mov     rdx, r14; SourceString
0x140014a35  mov     [rbx+1Ch], ax
0x140014a39  mov     rcx, rdi; DestinationString
0x140014a3c  xor     eax, eax
0x140014a3e  mov     [rdi], ax
0x140014a41  movzx   eax, word ptr [r14]
0x140014a45  mov     [rbx+2Ah], ax
0x140014a49  lea     rax, [rbx+78h]
0x140014a4d  mov     [rbx+30h], rax
0x140014a51  call    cs:__imp_RtlCopyUnicodeString
0x140014a58  nop     dword ptr [rax+rax+00h]
0x140014a5d  movzx   ecx, byte ptr [rbx+1Dh]
0x140014a61  sub     ecx, 1
0x140014a64  jz      loc_140014B4F
0x140014a6a  cmp     ecx, 1
0x140014a6d  jz      loc_140014B20
0x140014a73  mov     edi, 0C00000E5h
0x140014a78  mov     rcx, cs:WPP_GLOBAL_Control
0x140014a7f  cmp     rcx, r12
0x140014a82  jz      short loc_140014AB1
0x140014a84  test    dword ptr [rcx+2Ch], 2000000h
0x140014a8b  jz      short loc_140014AB1
0x140014a8d  movzx   eax, byte ptr [rsi+2]
0x140014a91  mov     r9, r14
0x140014a94  movzx   edx, byte ptr [rsi+3]
0x140014a98  mov     rcx, [rcx+18h]
0x140014a9c  mov     [rsp+78h+var_48], 0C00000E5h
0x140014aa4  mov     dword ptr [rsp+78h+var_50], eax
0x140014aa8  mov     dword ptr [rsp+78h+var_58], edx
0x140014aac  call    WPP_SF_ZddD
0x140014ab1  mov     rcx, rbx; P
0x140014ab4  call    MupiFreeSurrogateProvider
0x140014ab9  xor     ebx, ebx
0x140014abb  lea     rcx, stru_14000A5A0; Resource
0x140014ac2  call    cs:__imp_ExReleaseResourceLite
0x140014ac9  nop     dword ptr [rax+rax+00h]
0x140014ace  call    cs:__imp_KeLeaveCriticalRegion
0x140014ad5  nop     dword ptr [rax+rax+00h]
0x140014ada  mov     rcx, cs:WPP_GLOBAL_Control
0x140014ae1  cmp     rcx, r12
0x140014ae4  jz      short loc_140014B10
0x140014ae6  test    dword ptr [rcx+2Ch], 2000000h
0x140014aed  jz      short loc_140014B10
0x140014aef  mov     rcx, [rcx+18h]
0x140014af3  lea     r8, WPP_0fb1d46681b331a7af1167046103ae69_Traceguids
0x140014afa  mov     edx, 0Dh
0x140014aff  mov     dword ptr [rsp+78h+var_50], edi
0x140014b03  mov     r9, r14
0x140014b06  mov     [rsp+78h+var_58], rbx
0x140014b0b  call    WPP_SF_ZqD
0x140014b10  mov     eax, edi
0x140014b12  add     rsp, 48h
0x140014b16  pop     r14
0x140014b18  pop     r12
0x140014b1a  pop     rdi
0x140014b1b  pop     rsi
0x140014b1c  pop     rbp
0x140014b1d  pop     rbx
0x140014b1e  retn
0x140014b20  mov     rax, [rsi+8]
0x140014b24  mov     [rbx+48h], rax
0x140014b28  mov     rax, [rsi+10h]
0x140014b2c  mov     [rbx+50h], rax
0x140014b30  mov     eax, [rsi+18h]
0x140014b33  and     eax, 7
0x140014b36  mov     [rbx+6Ch], eax
0x140014b39  mov     eax, 201h
0x140014b3e  cmp     [rsi+2], ax
0x140014b42  jb      short loc_140014B5F
0x140014b44  mov     eax, [rsi+1Ch]
0x140014b47  and     eax, 1
0x140014b4a  mov     [rbx+70h], eax
0x140014b4d  jmp     short loc_140014B5F
0x140014b4f  mov     rax, [rsi+8]
0x140014b53  mov     [rbx+48h], rax
0x140014b57  mov     rax, [rsi+10h]
0x140014b5b  mov     [rbx+50h], rax
0x140014b5f  lea     r9, [rbx+38h]; DeviceObject
0x140014b63  mov     edx, 20h ; ' '; DesiredAccess
0x140014b68  lea     r8, [rbx+40h]; FileObject
0x140014b6c  mov     rcx, rdi; ObjectName
0x140014b6f  call    cs:__imp_IoGetDeviceObjectPointer
0x140014b76  nop     dword ptr [rax+rax+00h]
0x140014b7b  mov     edi, eax
0x140014b7d  test    eax, eax
0x140014b7f  jnz     loc_140014AB1
0x140014b85  mov     eax, [rbx+18h]
0x140014b88  dec     eax
0x140014b8a  mov     dword ptr [rbx+20h], 2
0x140014b91  test    eax, 0FFFFFFFDh
0x140014b96  jnz     short loc_140014B9F
0x140014b98  lock inc cs:MupiCachingAndGenericSurrogateCount
0x140014b9f  mov     rcx, rbx
0x140014ba2  call    MupiAddSurrogateToList
0x140014ba7  xor     edi, edi
0x140014ba9  jmp     loc_140014ABB
```
