# RegistryPropertyBag::StringProperty::Write(HKEY__ *)

- ea: `0x180056fcc`
- end: `0x18005709f`
- name: `?Write@StringProperty@RegistryPropertyBag@@MEAAJPEAUHKEY__@@@Z`
- size: `211`
- prototype: `int(RegistryPropertyBag::StringProperty *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180055dd0`

## callees

- `0x180055448`
- `0x180055470`
- `0x180056fcc`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x18005701a`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18005701a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005704d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005704d`

## pseudocode

```c
__int64 __fastcall RegistryPropertyBag::StringProperty::Write(RegistryPropertyBag::StringProperty *this, HKEY a2)
{
  int v4; // eax
  const BYTE *lpData; // rax
  UINT cbData; // [rsp+28h] [rbp-10h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids);
  v4 = 0;
  if ( *((_BYTE *)this + 8) )
  {
    cbData = SysStringByteLen(*((BSTR *)this + 2)) + 2;
    lpData = (const BYTE *)&dword_1800684AC;
    if ( *((_QWORD *)this + 2) )
      lpData = (const BYTE *)*((_QWORD *)this + 2);
    v4 = RegSetValueExW(a2, *((LPCWSTR *)this + 4), 0, 1u, lpData, cbData);
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
  }
  *((_DWORD *)this + 7) = v4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids,
      (unsigned int)v4);
  return *((unsigned int *)this + 7);
}

```

## disassembly

```asm
0x180056fcc  mov     [rsp+arg_0], rbx
0x180056fd1  mov     [rsp+arg_8], rsi
0x180056fd6  push    rdi
0x180056fd7  sub     rsp, 30h
0x180056fdb  mov     rdi, rdx
0x180056fde  mov     rbx, rcx
0x180056fe1  mov     rcx, cs:WPP_GLOBAL_Control
0x180056fe8  lea     rsi, WPP_GLOBAL_Control
0x180056fef  cmp     rcx, rsi
0x180056ff2  jz      short loc_18005700F
0x180056ff4  test    byte ptr [rcx+1Ch], 10h
0x180056ff8  jz      short loc_18005700F
0x180056ffa  mov     rcx, [rcx+10h]
0x180056ffe  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x180057005  mov     edx, 0Eh
0x18005700a  call    WPP_SF_
0x18005700f  xor     eax, eax
0x180057011  cmp     [rbx+8], al
0x180057014  jz      short loc_18005705F
0x180057016  mov     rcx, [rbx+10h]; bstr
0x18005701a  call    cs:__imp_SysStringByteLen
0x180057020  cmp     qword ptr [rbx+10h], 0
0x180057025  mov     r9d, 1; dwType
0x18005702b  mov     rdx, [rbx+20h]; lpValueName
0x18005702f  lea     ecx, [rax+2]
0x180057032  mov     [rsp+38h+cbData], ecx; cbData
0x180057036  lea     rax, dword_1800684AC
0x18005703d  cmovnz  rax, [rbx+10h]
0x180057042  mov     rcx, rdi; hKey
0x180057045  xor     r8d, r8d; Reserved
0x180057048  mov     [rsp+38h+lpData], rax; lpData
0x18005704d  call    cs:__imp_RegSetValueExW
0x180057053  test    eax, eax
0x180057055  jle     short loc_18005705F
0x180057057  movzx   eax, ax
0x18005705a  or      eax, 80070000h
0x18005705f  mov     [rbx+1Ch], eax
0x180057062  mov     rcx, cs:WPP_GLOBAL_Control
0x180057069  cmp     rcx, rsi
0x18005706c  jz      short loc_18005708C
0x18005706e  test    byte ptr [rcx+1Ch], 10h
0x180057072  jz      short loc_18005708C
0x180057074  mov     rcx, [rcx+10h]
0x180057078  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x18005707f  mov     edx, 0Fh
0x180057084  mov     r9d, eax
0x180057087  call    WPP_SF_d
0x18005708c  mov     eax, [rbx+1Ch]
0x18005708f  mov     rbx, [rsp+38h+arg_0]
0x180057094  mov     rsi, [rsp+38h+arg_8]
0x180057099  add     rsp, 30h
0x18005709d  pop     rdi
0x18005709e  retn
```
