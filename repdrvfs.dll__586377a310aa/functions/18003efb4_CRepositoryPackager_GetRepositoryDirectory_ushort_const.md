# CRepositoryPackager::GetRepositoryDirectory(ushort * const)

- ea: `0x18003efb4`
- end: `0x18003f159`
- name: `?GetRepositoryDirectory@CRepositoryPackager@@AEAAJQEAG@Z`
- size: `421`
- prototype: `int(CRepositoryPackager *__hidden this, unsigned __int16 *const)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003ee5c`
- `0x18003f940`
- `0x18004025c`

## callees

- `0x1800012b8`
- `0x180024ca0`
- `0x18003efb4`
- `0x180043fa0`
- `0x180044170`
- `0x180044420`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18003f006`
- `wbemcomn!GetMemLogObject` at `0x18003f08f`
- `wbemcomn!GetMemLogObject` at `0x18003f0e1`
- `wbemcomn!GetMemLogObject` at `0x18003f006`
- `wbemcomn!GetMemLogObject` at `0x18003f08f`
- `wbemcomn!GetMemLogObject` at `0x18003f0e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003f014`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003f09d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003f0ef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003f014`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003f09d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003f0ef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003f0d7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003f0d7`

## string_xrefs

- `0x18003f05e`: `Repository Directory`

## pseudocode

```c
__int64 __fastcall CRepositoryPackager::GetRepositoryDirectory(
        CRepositoryPackager *this,
        unsigned __int16 *const a2,
        int a3)
{
  int v4; // r8d
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v6; // rcx
  __int64 v7; // rdx
  int Value; // ebx
  CMemoryLog *v9; // rax
  CMemoryLog *v10; // rax
  int v12; // [rsp+30h] [rbp-238h] BYREF
  __int64 v13; // [rsp+38h] [rbp-230h] BYREF
  WCHAR Src[264]; // [rsp+40h] [rbp-228h] BYREF

  v13 = 0;
  if ( (unsigned int)DLRegOpenKeyExW(
                       -2147483646,
                       (unsigned int)L"SOFTWARE\\Microsoft\\WBEM\\CIMOM",
                       a3,
                       131097,
                       (__int64)&v13) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217407);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749889LL;
    }
    v7 = 17;
LABEL_16:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids, 2147749889LL);
    return 2147749889LL;
  }
  v12 = 522;
  Value = DLRegQueryValueExW(v13, (unsigned int)L"Repository Directory", v4, 0, (__int64)Src, (__int64)&v12);
  DLRegCloseKey(v13);
  if ( Value )
  {
    v9 = GetMemLogObject();
    CMemoryLog::Write(v9, -2147217407);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749889LL;
    }
    v7 = 18;
    goto LABEL_16;
  }
  if ( !ExpandEnvironmentStringsW(Src, a2, 0x105u) )
  {
    v10 = GetMemLogObject();
    CMemoryLog::Write(v10, -2147217407);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749889LL;
    }
    v7 = 19;
    goto LABEL_16;
  }
  return 0;
}

```

## disassembly

```asm
0x18003efb4  mov     [rsp+arg_0], rbx
0x18003efb9  push    rdi
0x18003efba  sub     rsp, 260h
0x18003efc1  mov     rax, cs:__security_cookie
0x18003efc8  xor     rax, rsp
0x18003efcb  mov     [rsp+268h+var_18], rax
0x18003efd3  mov     rdi, rdx
0x18003efd6  mov     [rsp+268h+var_230], 0
0x18003efdf  lea     rax, [rsp+268h+var_230]
0x18003efe4  mov     r9d, 20019h
0x18003efea  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WBEM\\CIMOM"
0x18003eff1  mov     [rsp+268h+var_248], rax
0x18003eff6  mov     rcx, 0FFFFFFFF80000002h
0x18003effd  call    DLRegOpenKeyExW
0x18003f002  test    eax, eax
0x18003f004  jz      short loc_18003F04F
0x18003f006  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003f00c  mov     rcx, rax
0x18003f00f  mov     edx, 80041001h
0x18003f014  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003f01a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f021  lea     rax, WPP_GLOBAL_Control
0x18003f028  cmp     rcx, rax
0x18003f02b  jz      loc_18003F12F
0x18003f031  test    byte ptr [rcx+1Ch], 1
0x18003f035  jz      loc_18003F12F
0x18003f03b  cmp     byte ptr [rcx+19h], 2
0x18003f03f  jb      loc_18003F12F
0x18003f045  mov     edx, 11h
0x18003f04a  jmp     loc_18003F119
0x18003f04f  mov     rcx, [rsp+268h+var_230]
0x18003f054  lea     rax, [rsp+268h+var_238]
0x18003f059  mov     [rsp+268h+var_240], rax
0x18003f05e  lea     rdx, aRepositoryDire; "Repository Directory"
0x18003f065  lea     rax, [rsp+268h+Src]
0x18003f06a  mov     [rsp+268h+var_238], 20Ah
0x18003f072  xor     r9d, r9d
0x18003f075  mov     [rsp+268h+var_248], rax
0x18003f07a  call    DLRegQueryValueExW
0x18003f07f  mov     rcx, [rsp+268h+var_230]
0x18003f084  mov     ebx, eax
0x18003f086  call    DLRegCloseKey
0x18003f08b  test    ebx, ebx
0x18003f08d  jz      short loc_18003F0C9
0x18003f08f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003f095  mov     rcx, rax
0x18003f098  mov     edx, 80041001h
0x18003f09d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003f0a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f0aa  lea     rax, WPP_GLOBAL_Control
0x18003f0b1  cmp     rcx, rax
0x18003f0b4  jz      short loc_18003F12F
0x18003f0b6  test    byte ptr [rcx+1Ch], 1
0x18003f0ba  jz      short loc_18003F12F
0x18003f0bc  cmp     byte ptr [rcx+19h], 2
0x18003f0c0  jb      short loc_18003F12F
0x18003f0c2  mov     edx, 12h
0x18003f0c7  jmp     short loc_18003F119
0x18003f0c9  mov     r8d, 105h; nSize
0x18003f0cf  lea     rcx, [rsp+268h+Src]; lpSrc
0x18003f0d4  mov     rdx, rdi; lpDst
0x18003f0d7  call    cs:__imp_ExpandEnvironmentStringsW
0x18003f0dd  test    eax, eax
0x18003f0df  jnz     short loc_18003F136
0x18003f0e1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003f0e7  mov     rcx, rax
0x18003f0ea  mov     edx, 80041001h
0x18003f0ef  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003f0f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f0fc  lea     rax, WPP_GLOBAL_Control
0x18003f103  cmp     rcx, rax
0x18003f106  jz      short loc_18003F12F
0x18003f108  test    byte ptr [rcx+1Ch], 1
0x18003f10c  jz      short loc_18003F12F
0x18003f10e  cmp     byte ptr [rcx+19h], 2
0x18003f112  jb      short loc_18003F12F
0x18003f114  mov     edx, 13h
0x18003f119  mov     rcx, [rcx+10h]
0x18003f11d  lea     r8, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids
0x18003f124  mov     r9d, 80041001h
0x18003f12a  call    WPP_SF_d
0x18003f12f  mov     eax, 80041001h
0x18003f134  jmp     short loc_18003F138
0x18003f136  xor     eax, eax
0x18003f138  mov     rcx, [rsp+268h+var_18]
0x18003f140  xor     rcx, rsp; StackCookie
0x18003f143  call    __security_check_cookie
0x18003f148  mov     rbx, [rsp+268h+arg_0]
0x18003f150  add     rsp, 260h
0x18003f157  pop     rdi
0x18003f158  retn
```
