# CreateNewDriveLetterName

- ea: `0x14000acd8`
- end: `0x14000ade8`
- name: `CreateNewDriveLetterName`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140014fc0`

## callees

- `0x140001ae0`
- `0x14000acd8`
- `0x14000adf0`
- `0x14000ccb4`
- `0x140018af0`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ad56`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ad74`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ad56`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000ad74`

## pseudocode

```c
__int64 __fastcall CreateNewDriveLetterName(__int64 a1)
{
  int BootDriveLetter; // ebx
  _BYTE *v3; // rsi
  unsigned __int8 v4; // dl
  __int64 v5; // r8
  unsigned __int8 v6; // si

  BootDriveLetter = 0;
  if ( (*(_DWORD *)(a1 + 120) & 0x100) != 0 )
  {
    v3 = (_BYTE *)(a1 + 128);
    BootDriveLetter = MountMgrQueryBootDriveLetter((_BYTE *)(a1 + 128));
    if ( BootDriveLetter < 0 )
    {
      *v3 = 0;
      BootDriveLetter = 0;
    }
  }
  v4 = *(_BYTE *)(a1 + 128);
  if ( v4 == 0xFF )
  {
    CreateNoDriveLetterEntry(*(unsigned __int16 **)(a1 + 96));
  }
  else
  {
    v6 = 65;
    if ( (unsigned __int8)(v4 - 65) > 0x19u )
    {
      *(_BYTE *)(a1 + 128) = 0;
    }
    else
    {
      BootDriveLetter = CreateNewDriveLetterHelper(a1, v4);
      if ( BootDriveLetter >= 0 )
        goto LABEL_14;
    }
    if ( !RtlPrefixUnicodeString(&String1, (PCUNICODE_STRING)(a1 + 80), 1u) )
      v6 = (RtlPrefixUnicodeString(&stru_140007030, (PCUNICODE_STRING)(a1 + 80), 1u) != 0) + 67;
    do
    {
      BootDriveLetter = CreateNewDriveLetterHelper(a1, v6);
      if ( BootDriveLetter >= 0 )
        break;
      ++v6;
    }
    while ( v6 <= 0x5Au );
  }
LABEL_14:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 85, v5, (unsigned int)BootDriveLetter);
  }
  return (unsigned int)BootDriveLetter;
}

```

## disassembly

```asm
0x14000acd8  mov     [rsp+arg_0], rbx
0x14000acdd  mov     [rsp+arg_8], rsi
0x14000ace2  push    rdi
0x14000ace3  sub     rsp, 20h
0x14000ace7  xor     ebx, ebx
0x14000ace9  mov     rdi, rcx
0x14000acec  test    dword ptr [rcx+78h], 100h
0x14000acf3  jz      short loc_14000AD0F
0x14000acf5  lea     rsi, [rcx+80h]
0x14000acfc  mov     rcx, rsi
0x14000acff  call    MountMgrQueryBootDriveLetter
0x14000ad04  mov     ebx, eax
0x14000ad06  test    eax, eax
0x14000ad08  jns     short loc_14000AD0F
0x14000ad0a  mov     byte ptr [rsi], 0
0x14000ad0d  xor     ebx, ebx
0x14000ad0f  mov     dl, [rdi+80h]
0x14000ad15  cmp     dl, 0FFh
0x14000ad18  jnz     short loc_14000AD25
0x14000ad1a  mov     rcx, [rdi+60h]
0x14000ad1e  call    CreateNoDriveLetterEntry
0x14000ad23  jmp     short loc_14000ADA4
0x14000ad25  mov     al, dl
0x14000ad27  mov     sil, 41h ; 'A'
0x14000ad2a  sub     al, sil
0x14000ad2d  cmp     al, 19h
0x14000ad2f  ja      short loc_14000AD41
0x14000ad31  mov     rcx, rdi
0x14000ad34  call    CreateNewDriveLetterHelper
0x14000ad39  mov     ebx, eax
0x14000ad3b  test    eax, eax
0x14000ad3d  jns     short loc_14000ADA4
0x14000ad3f  jmp     short loc_14000AD48
0x14000ad41  mov     byte ptr [rdi+80h], 0
0x14000ad48  mov     r8b, 1; CaseInSensitive
0x14000ad4b  lea     rdx, [rdi+50h]; String2
0x14000ad4f  lea     rcx, String1; String1
0x14000ad56  call    cs:__imp_RtlPrefixUnicodeString
0x14000ad5d  nop     dword ptr [rax+rax+00h]
0x14000ad62  test    al, al
0x14000ad64  jnz     short loc_14000AD8A
0x14000ad66  mov     r8b, 1; CaseInSensitive
0x14000ad69  lea     rdx, [rdi+50h]; String2
0x14000ad6d  lea     rcx, stru_140007030; String1
0x14000ad74  call    cs:__imp_RtlPrefixUnicodeString
0x14000ad7b  nop     dword ptr [rax+rax+00h]
0x14000ad80  test    al, al
0x14000ad82  setnz   sil
0x14000ad86  add     sil, 43h ; 'C'
0x14000ad8a  mov     dl, sil
0x14000ad8d  mov     rcx, rdi
0x14000ad90  call    CreateNewDriveLetterHelper
0x14000ad95  mov     ebx, eax
0x14000ad97  test    eax, eax
0x14000ad99  jns     short loc_14000ADA4
0x14000ad9b  inc     sil
0x14000ad9e  cmp     sil, 5Ah ; 'Z'
0x14000ada2  jbe     short loc_14000AD8A
0x14000ada4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000adab  lea     rax, WPP_GLOBAL_Control
0x14000adb2  cmp     rcx, rax
0x14000adb5  jz      short loc_14000ADD5
0x14000adb7  mov     eax, [rcx+2Ch]
0x14000adba  test    al, 1
0x14000adbc  jz      short loc_14000ADD5
0x14000adbe  cmp     byte ptr [rcx+29h], 2
0x14000adc2  jb      short loc_14000ADD5
0x14000adc4  mov     rcx, [rcx+18h]
0x14000adc8  mov     edx, 55h ; 'U'
0x14000adcd  mov     r9d, ebx
0x14000add0  call    WPP_SF_L
0x14000add5  mov     rsi, [rsp+28h+arg_8]
0x14000adda  mov     eax, ebx
0x14000addc  mov     rbx, [rsp+28h+arg_0]
0x14000ade1  add     rsp, 20h
0x14000ade5  pop     rdi
0x14000ade6  retn
```
