# CSnapinThread::Dump(BookKeepingXml &)

- ea: `0x18000fc44`
- end: `0x18000fdc5`
- name: `?Dump@CSnapinThread@@QEBAJAEAVBookKeepingXml@@@Z`
- size: `385`
- prototype: `int(CSnapinThread *__hidden this, struct BookKeepingXml *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000f02c`

## callees

- `0x18000b980`
- `0x18000bdb8`
- `0x18000bf80`
- `0x18000c60c`
- `0x18000caf0`
- `0x18000fc44`
- `0x18000ffcc`
- `0x18001b550`

## import_xrefs

- `msvcrt!_itow` at `0x18000fc78`
- `msvcrt!_itow` at `0x18000fc78`

## pseudocode

```c
__int64 __fastcall CSnapinThread::Dump(CSnapinThread *this, struct BookKeepingXml *a2)
{
  unsigned int v2; // ebx
  int v5; // eax
  __int64 v6; // r8
  int v7; // ebx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 v11; // rdx
  const wchar_t *v12; // r8
  int v13; // eax
  __int64 v14; // r8
  unsigned int v15; // ebp
  wchar_t Buffer[32]; // [rsp+30h] [rbp-68h] BYREF

  v2 = *(_DWORD *)this;
  _itow(*((_DWORD *)this + 2), Buffer, 10);
  v5 = BookKeepingXml::OpenRecord(a2, 6, v2, Buffer);
  v7 = v5;
  if ( v5 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_Ld(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, v6, *((unsigned int *)this + 2), v5);
    return (unsigned int)v7;
  }
  v8 = BookKeepingXml::AddProperty(a2, 45, *((unsigned int *)this + 1));
  v7 = v8;
  if ( v8 >= 0 )
  {
    v12 = L"true";
    if ( (*((_BYTE *)this + 12) & 1) == 0 )
      v12 = L"false";
    v8 = BookKeepingXml::AddProperty(a2, 47, v12);
    v7 = v8;
    if ( v8 >= 0 )
      goto LABEL_16;
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_16;
    v10 = *((unsigned int *)this + 3);
    v11 = 16;
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_16;
    v10 = *((unsigned int *)this + 1);
    v11 = 15;
  }
  WPP_SF_dd(*(_QWORD *)(v9 + 16), v11, WPP_f3bba9684d7438edd2d7e3175dacda09_Traceguids, v10, v8);
LABEL_16:
  v13 = BookKeepingXml::CloseRecord(a2);
  v15 = v13;
  if ( v13 < 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    WPP_SF_Ld(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, v14, *((unsigned int *)this + 2), v13);
  if ( v7 >= 0 )
    return v15;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000fc44  mov     [rsp+arg_10], rbx
0x18000fc49  push    rbp
0x18000fc4a  push    rsi
0x18000fc4b  push    rdi
0x18000fc4c  sub     rsp, 80h
0x18000fc53  mov     rax, cs:__security_cookie
0x18000fc5a  xor     rax, rsp
0x18000fc5d  mov     [rsp+98h+var_28], rax
0x18000fc62  mov     ebx, [rcx]
0x18000fc64  mov     rbp, rdx
0x18000fc67  mov     rsi, rcx
0x18000fc6a  lea     rdx, [rsp+98h+Buffer]; Buffer
0x18000fc6f  mov     ecx, [rcx+8]; Value
0x18000fc72  mov     r8d, 0Ah; Radix
0x18000fc78  call    cs:__imp__itow
0x18000fc7e  lea     r9, [rsp+98h+Buffer]
0x18000fc83  mov     r8d, ebx
0x18000fc86  mov     edx, 6
0x18000fc8b  mov     rcx, rbp
0x18000fc8e  call    ?OpenRecord@BookKeepingXml@@QEAAJW4_XmlNameId@1@HPEBG@Z; BookKeepingXml::OpenRecord(BookKeepingXml::_XmlNameId,int,ushort const *)
0x18000fc93  mov     ebx, eax
0x18000fc95  test    eax, eax
0x18000fc97  jns     short loc_18000FCD5
0x18000fc99  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fca0  lea     rdi, WPP_GLOBAL_Control
0x18000fca7  cmp     rcx, rdi
0x18000fcaa  jz      loc_18000FDA3
0x18000fcb0  cmp     byte ptr [rcx+19h], 2
0x18000fcb4  jb      loc_18000FDA3
0x18000fcba  mov     r9d, [rsi+8]
0x18000fcbe  mov     edx, 0Eh
0x18000fcc3  mov     rcx, [rcx+10h]
0x18000fcc7  mov     [rsp+98h+var_78], eax
0x18000fccb  call    WPP_SF_Ld
0x18000fcd0  jmp     loc_18000FDA3
0x18000fcd5  mov     r8d, [rsi+4]
0x18000fcd9  mov     edx, 2Dh ; '-'
0x18000fcde  mov     rcx, rbp
0x18000fce1  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@H@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,int)
0x18000fce6  lea     rdi, WPP_GLOBAL_Control
0x18000fced  mov     ebx, eax
0x18000fcef  test    eax, eax
0x18000fcf1  jns     short loc_18000FD10
0x18000fcf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcfa  cmp     rcx, rdi
0x18000fcfd  jz      short loc_18000FD68
0x18000fcff  cmp     byte ptr [rcx+19h], 2
0x18000fd03  jb      short loc_18000FD68
0x18000fd05  mov     r9d, [rsi+4]
0x18000fd09  mov     edx, 0Fh
0x18000fd0e  jmp     short loc_18000FD54
0x18000fd10  test    byte ptr [rsi+0Ch], 1
0x18000fd14  lea     rax, aFalse; "false"
0x18000fd1b  lea     r8, aTrue; "true"
0x18000fd22  mov     edx, 2Fh ; '/'
0x18000fd27  cmovz   r8, rax
0x18000fd2b  mov     rcx, rbp
0x18000fd2e  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x18000fd33  mov     ebx, eax
0x18000fd35  test    eax, eax
0x18000fd37  jns     short loc_18000FD68
0x18000fd39  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd40  cmp     rcx, rdi
0x18000fd43  jz      short loc_18000FD68
0x18000fd45  cmp     byte ptr [rcx+19h], 2
0x18000fd49  jb      short loc_18000FD68
0x18000fd4b  mov     r9d, [rsi+0Ch]
0x18000fd4f  mov     edx, 10h
0x18000fd54  mov     rcx, [rcx+10h]
0x18000fd58  lea     r8, WPP_f3bba9684d7438edd2d7e3175dacda09_Traceguids
0x18000fd5f  mov     [rsp+98h+var_78], eax
0x18000fd63  call    WPP_SF_dd
0x18000fd68  mov     rcx, rbp; this
0x18000fd6b  call    ?CloseRecord@BookKeepingXml@@QEAAJXZ; BookKeepingXml::CloseRecord(void)
0x18000fd70  mov     ebp, eax
0x18000fd72  test    eax, eax
0x18000fd74  jns     short loc_18000FD9E
0x18000fd76  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd7d  cmp     rcx, rdi
0x18000fd80  jz      short loc_18000FD9E
0x18000fd82  cmp     byte ptr [rcx+19h], 2
0x18000fd86  jb      short loc_18000FD9E
0x18000fd88  mov     r9d, [rsi+8]
0x18000fd8c  mov     edx, 11h
0x18000fd91  mov     rcx, [rcx+10h]
0x18000fd95  mov     [rsp+98h+var_78], eax
0x18000fd99  call    WPP_SF_Ld
0x18000fd9e  test    ebx, ebx
0x18000fda0  cmovns  ebx, ebp
0x18000fda3  mov     eax, ebx
0x18000fda5  mov     rcx, [rsp+98h+var_28]
0x18000fdaa  xor     rcx, rsp; StackCookie
0x18000fdad  call    __security_check_cookie
0x18000fdb2  mov     rbx, [rsp+98h+arg_10]
0x18000fdba  add     rsp, 80h
0x18000fdc1  pop     rdi
0x18000fdc2  pop     rsi
0x18000fdc3  pop     rbp
0x18000fdc4  retn
```
