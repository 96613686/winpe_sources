# InterfaceRecord::Dump(BookKeepingXml &)

- ea: `0x18000fdcc`
- end: `0x18000ff6f`
- name: `?Dump@InterfaceRecord@@QEBAJAEAVBookKeepingXml@@@Z`
- size: `419`
- prototype: `int(InterfaceRecord *__hidden this, struct BookKeepingXml *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18000f18c`

## callees

- `0x18000b980`
- `0x18000be1c`
- `0x18000bf80`
- `0x18000c60c`
- `0x18000caf0`
- `0x18000cbfc`
- `0x18000cfbc`
- `0x18000ecd8`
- `0x18000fdcc`
- `0x18001b550`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall InterfaceRecord::Dump(InterfaceRecord *this, struct BookKeepingXml *a2)
{
  __int64 v2; // rdi
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // ebx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  unsigned int v11; // ebp
  unsigned __int16 v13[24]; // [rsp+30h] [rbp-58h] BYREF

  v2 = *((_QWORD *)this + 1);
  v5 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
  StringCchPrintfW(v13, 0x18u, L"%p", v2);
  v6 = BookKeepingXml::OpenRecord(a2, 5, v5, v13);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = BookKeepingXml::AddProperty(a2, 49, *((unsigned int *)this + 4));
    v7 = v8;
    if ( v8 >= 0 )
    {
      v9 = BookKeepingXml::AddProperty(a2, 48, *((_QWORD *)this + 3));
      v7 = v9;
      if ( v9 < 0
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          12,
          (unsigned int)WPP_f3bba9684d7438edd2d7e3175dacda09_Traceguids,
          *((_QWORD *)this + 3),
          v9);
      }
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_dd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        11,
        WPP_f3bba9684d7438edd2d7e3175dacda09_Traceguids,
        *((unsigned int *)this + 4),
        v8);
    }
    v10 = BookKeepingXml::CloseRecord(a2);
    v11 = v10;
    if ( v10 < 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_qd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        13,
        WPP_f3bba9684d7438edd2d7e3175dacda09_Traceguids,
        *((_QWORD *)this + 1),
        v10);
    if ( v7 >= 0 )
      return v11;
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    WPP_SF_qd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      10,
      WPP_f3bba9684d7438edd2d7e3175dacda09_Traceguids,
      *((_QWORD *)this + 1),
      v6);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000fdcc  mov     [rsp+arg_10], rbx
0x18000fdd1  push    rbp
0x18000fdd2  push    rsi
0x18000fdd3  push    rdi
0x18000fdd4  sub     rsp, 70h
0x18000fdd8  mov     rax, cs:__security_cookie
0x18000fddf  xor     rax, rsp
0x18000fde2  mov     [rsp+88h+var_28], rax
0x18000fde7  mov     rdi, [rcx+8]
0x18000fdeb  mov     rsi, rcx
0x18000fdee  mov     rcx, [rcx]
0x18000fdf1  mov     rbp, rdx
0x18000fdf4  mov     rax, [rcx]
0x18000fdf7  mov     rax, [rax+10h]
0x18000fdfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe00  mov     r9, rdi
0x18000fe03  lea     r8, aP; "%p"
0x18000fe0a  mov     edx, 18h; unsigned __int64
0x18000fe0f  lea     rcx, [rsp+88h+var_58]; unsigned __int16 *
0x18000fe14  mov     ebx, eax
0x18000fe16  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fe1b  lea     r9, [rsp+88h+var_58]
0x18000fe20  mov     r8d, ebx
0x18000fe23  mov     edx, 5
0x18000fe28  mov     rcx, rbp
0x18000fe2b  call    ?OpenRecord@BookKeepingXml@@QEAAJW4_XmlNameId@1@HPEBG@Z; BookKeepingXml::OpenRecord(BookKeepingXml::_XmlNameId,int,ushort const *)
0x18000fe30  mov     ebx, eax
0x18000fe32  test    eax, eax
0x18000fe34  jns     short loc_18000FE79
0x18000fe36  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe3d  lea     rdi, WPP_GLOBAL_Control
0x18000fe44  cmp     rcx, rdi
0x18000fe47  jz      loc_18000FF50
0x18000fe4d  cmp     byte ptr [rcx+19h], 2
0x18000fe51  jb      loc_18000FF50
0x18000fe57  mov     r9, [rsi+8]
0x18000fe5b  lea     r8, WPP_f3bba9684d7438edd2d7e3175dacda09_Traceguids
0x18000fe62  mov     rcx, [rcx+10h]
0x18000fe66  mov     edx, 0Ah
0x18000fe6b  mov     [rsp+88h+var_68], eax
0x18000fe6f  call    WPP_SF_qd
0x18000fe74  jmp     loc_18000FF50
0x18000fe79  mov     r8d, [rsi+10h]
0x18000fe7d  mov     edx, 31h ; '1'
0x18000fe82  mov     rcx, rbp
0x18000fe85  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@J@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,long)
0x18000fe8a  lea     rdi, WPP_GLOBAL_Control
0x18000fe91  mov     ebx, eax
0x18000fe93  test    eax, eax
0x18000fe95  jns     short loc_18000FEC8
0x18000fe97  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe9e  cmp     rcx, rdi
0x18000fea1  jz      short loc_18000FF0E
0x18000fea3  cmp     byte ptr [rcx+19h], 2
0x18000fea7  jb      short loc_18000FF0E
0x18000fea9  mov     r9d, [rsi+10h]
0x18000fead  lea     r8, WPP_f3bba9684d7438edd2d7e3175dacda09_Traceguids
0x18000feb4  mov     rcx, [rcx+10h]
0x18000feb8  mov     edx, 0Bh
0x18000febd  mov     [rsp+88h+var_68], eax
0x18000fec1  call    WPP_SF_dd
0x18000fec6  jmp     short loc_18000FF0E
0x18000fec8  mov     r8, [rsi+18h]
0x18000fecc  mov     edx, 30h ; '0'
0x18000fed1  mov     rcx, rbp
0x18000fed4  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x18000fed9  mov     ebx, eax
0x18000fedb  test    eax, eax
0x18000fedd  jns     short loc_18000FF0E
0x18000fedf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fee6  cmp     rcx, rdi
0x18000fee9  jz      short loc_18000FF0E
0x18000feeb  cmp     byte ptr [rcx+19h], 2
0x18000feef  jb      short loc_18000FF0E
0x18000fef1  mov     r9, [rsi+18h]
0x18000fef5  lea     r8, WPP_f3bba9684d7438edd2d7e3175dacda09_Traceguids
0x18000fefc  mov     rcx, [rcx+10h]
0x18000ff00  mov     edx, 0Ch
0x18000ff05  mov     [rsp+88h+var_68], eax
0x18000ff09  call    WPP_SF_Sd
0x18000ff0e  mov     rcx, rbp; this
0x18000ff11  call    ?CloseRecord@BookKeepingXml@@QEAAJXZ; BookKeepingXml::CloseRecord(void)
0x18000ff16  mov     ebp, eax
0x18000ff18  test    eax, eax
0x18000ff1a  jns     short loc_18000FF4B
0x18000ff1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff23  cmp     rcx, rdi
0x18000ff26  jz      short loc_18000FF4B
0x18000ff28  cmp     byte ptr [rcx+19h], 2
0x18000ff2c  jb      short loc_18000FF4B
0x18000ff2e  mov     r9, [rsi+8]
0x18000ff32  lea     r8, WPP_f3bba9684d7438edd2d7e3175dacda09_Traceguids
0x18000ff39  mov     rcx, [rcx+10h]
0x18000ff3d  mov     edx, 0Dh
0x18000ff42  mov     [rsp+88h+var_68], eax
0x18000ff46  call    WPP_SF_qd
0x18000ff4b  test    ebx, ebx
0x18000ff4d  cmovns  ebx, ebp
0x18000ff50  mov     eax, ebx
0x18000ff52  mov     rcx, [rsp+88h+var_28]
0x18000ff57  xor     rcx, rsp; StackCookie
0x18000ff5a  call    __security_check_cookie
0x18000ff5f  mov     rbx, [rsp+88h+arg_10]
0x18000ff67  add     rsp, 70h
0x18000ff6b  pop     rdi
0x18000ff6c  pop     rsi
0x18000ff6d  pop     rbp
0x18000ff6e  retn
```
