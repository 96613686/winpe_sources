# Dfdll::CShortcutFile::GetDefinitionIdentityFromShortcutFile(ushort const *,Dfdll::CString &)

- ea: `0x18000c954`
- end: `0x18000ca31`
- name: `?GetDefinitionIdentityFromShortcutFile@CShortcutFile@Dfdll@@SAJPEBGAEAVCString@2@@Z`
- size: `221`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Dfdll::CString *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180010d18`

## callees

- `0x180002604`
- `0x180003e88`
- `0x180008c6c`
- `0x18000c954`
- `0x18001179c`

## pseudocode

```c
__int64 __fastcall Dfdll::CShortcutFile::GetDefinitionIdentityFromShortcutFile(
        const unsigned __int16 *a1,
        struct Dfdll::CString *a2)
{
  int UnicodeFormattedTextFile; // ebx
  void **v5; // [rsp+20h] [rbp-39h] BYREF
  _QWORD v6[3]; // [rsp+28h] [rbp-31h] BYREF
  int v7; // [rsp+40h] [rbp-19h]
  int v8; // [rsp+48h] [rbp-11h]
  _QWORD v9[3]; // [rsp+50h] [rbp-9h] BYREF
  int v10; // [rsp+68h] [rbp+Fh]
  int v11; // [rsp+70h] [rbp+17h]
  _QWORD v12[2]; // [rsp+78h] [rbp+1Fh] BYREF
  unsigned __int16 *v13; // [rsp+88h] [rbp+2Fh]
  int v14; // [rsp+90h] [rbp+37h]
  int v15; // [rsp+98h] [rbp+3Fh]
  int v16; // [rsp+A0h] [rbp+47h]

  v5 = &Dfdll::CShortcutFile::`vftable';
  v6[0] = &Dfdll::CString::`vftable';
  v6[2] = 0;
  v7 = 0;
  v6[1] = &Dfdll::CBuffer<unsigned short>::`vftable';
  v8 = 0;
  v9[0] = &Dfdll::CString::`vftable';
  v9[2] = 0;
  v10 = 0;
  v9[1] = &Dfdll::CBuffer<unsigned short>::`vftable';
  v11 = 0;
  v12[0] = &Dfdll::CString::`vftable';
  v13 = 0;
  v14 = 0;
  v12[1] = &Dfdll::CBuffer<unsigned short>::`vftable';
  v15 = 0;
  v16 = 0;
  UnicodeFormattedTextFile = Dfdll::CFile::ReadUnicodeFormattedTextFile(a1, (struct Dfdll::CString *)v6, 0x10000u);
  if ( UnicodeFormattedTextFile >= 0 )
  {
    UnicodeFormattedTextFile = Dfdll::CString::Split(
                                 (Dfdll::CString *)v6,
                                 Dfdll::Constants::Strings::PoundSign,
                                 (struct Dfdll::CString *)v9,
                                 (struct Dfdll::CString *)v12);
    if ( UnicodeFormattedTextFile >= 0 )
    {
      UnicodeFormattedTextFile = Dfdll::CString::Assign(a2, v13);
      if ( UnicodeFormattedTextFile >= 0 )
        UnicodeFormattedTextFile = 0;
    }
  }
  Dfdll::CShortcutFile::~CShortcutFile((Dfdll::CShortcutFile *)&v5);
  return (unsigned int)UnicodeFormattedTextFile;
}

```

## disassembly

```asm
0x18000c954  mov     [rsp-8+arg_0], rbx
0x18000c959  mov     [rsp-8+arg_8], rdi
0x18000c95e  push    rbp
0x18000c95f  lea     rbp, [rsp-57h]
0x18000c964  sub     rsp, 0B0h
0x18000c96b  mov     rdi, rdx
0x18000c96e  lea     rax, ??_7CShortcutFile@Dfdll@@6B@; const Dfdll::CShortcutFile::`vftable'
0x18000c975  mov     [rbp+57h+var_90], rax
0x18000c979  lea     rdx, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x18000c980  mov     [rbp+57h+var_88], rdx
0x18000c984  and     [rbp+57h+var_78], 0
0x18000c989  and     [rbp+57h+var_70], 0
0x18000c98d  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18000c994  mov     [rbp+57h+var_80], rax
0x18000c998  and     [rbp+57h+var_68], 0
0x18000c99c  mov     [rbp+57h+var_60], rdx
0x18000c9a0  and     [rbp+57h+var_50], 0
0x18000c9a5  and     [rbp+57h+var_48], 0
0x18000c9a9  mov     [rbp+57h+var_58], rax
0x18000c9ad  and     [rbp+57h+var_40], 0
0x18000c9b1  mov     [rbp+57h+var_38], rdx
0x18000c9b5  and     [rbp+57h+var_28], 0
0x18000c9ba  and     [rbp+57h+var_20], 0
0x18000c9be  mov     [rbp+57h+var_30], rax
0x18000c9c2  and     [rbp+57h+var_18], 0
0x18000c9c6  and     [rbp+57h+var_10], 0
0x18000c9ca  mov     r8d, 10000h; unsigned int
0x18000c9d0  lea     rdx, [rbp+57h+var_88]; struct Dfdll::CString *
0x18000c9d4  call    ?ReadUnicodeFormattedTextFile@CFile@Dfdll@@SAJPEBGAEAVCString@2@I@Z; Dfdll::CFile::ReadUnicodeFormattedTextFile(ushort const *,Dfdll::CString &,uint)
0x18000c9d9  mov     ebx, eax
0x18000c9db  test    eax, eax
0x18000c9dd  js      short loc_18000CA11
0x18000c9df  lea     r9, [rbp+57h+var_38]; struct Dfdll::CString *
0x18000c9e3  lea     r8, [rbp+57h+var_60]; struct Dfdll::CString *
0x18000c9e7  mov     rdx, cs:?PoundSign@Strings@Constants@Dfdll@@3QEAGEA; unsigned __int16 *
0x18000c9ee  lea     rcx, [rbp+57h+var_88]; this
0x18000c9f2  call    ?Split@CString@Dfdll@@QEAAJPEBGAEAV12@1@Z; Dfdll::CString::Split(ushort const *,Dfdll::CString &,Dfdll::CString &)
0x18000c9f7  mov     ebx, eax
0x18000c9f9  test    eax, eax
0x18000c9fb  js      short loc_18000CA11
0x18000c9fd  mov     rdx, [rbp+57h+var_28]; unsigned __int16 *
0x18000ca01  mov     rcx, rdi; this
0x18000ca04  call    ?Assign@CString@Dfdll@@QEAAJPEBG@Z; Dfdll::CString::Assign(ushort const *)
0x18000ca09  mov     ebx, eax
0x18000ca0b  test    eax, eax
0x18000ca0d  js      short loc_18000CA11
0x18000ca0f  xor     ebx, ebx
0x18000ca11  lea     rcx, [rbp+57h+var_90]; this
0x18000ca15  call    ??1CShortcutFile@Dfdll@@UEAA@XZ; Dfdll::CShortcutFile::~CShortcutFile(void)
0x18000ca1a  mov     eax, ebx
0x18000ca1c  lea     r11, [rsp+0B0h+var_s0]
0x18000ca24  mov     rbx, [r11+10h]
0x18000ca28  mov     rdi, [r11+18h]
0x18000ca2c  mov     rsp, r11
0x18000ca2f  pop     rbp
0x18000ca30  retn
```
