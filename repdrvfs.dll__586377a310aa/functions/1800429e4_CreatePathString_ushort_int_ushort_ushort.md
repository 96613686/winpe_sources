# CreatePathString(ushort *,int,ushort *,ushort *)

- ea: `0x1800429e4`
- end: `0x180042b52`
- name: `?CreatePathString@@YAJPEAGH00@Z`
- size: `366`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180042d64`
- `0x18004330c`

## callees

- `0x1800012f4`
- `0x180013880`
- `0x180013f90`
- `0x1800429e4`
- `0x180044420`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180042a23`
- `wbemcomn!GetMemLogObject` at `0x180042a91`
- `wbemcomn!GetMemLogObject` at `0x180042ade`
- `wbemcomn!GetMemLogObject` at `0x180042a23`
- `wbemcomn!GetMemLogObject` at `0x180042a91`
- `wbemcomn!GetMemLogObject` at `0x180042ade`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042a2e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042a9c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042ae9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042a2e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042a9c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042ae9`

## string_xrefs

- `0x180042a64`: `SOFTWARE\Classes\CLSID\`
- `0x180042a70`: `SOFTWARE\Classes\CLSID\`

## pseudocode

```c
__int64 __fastcall CreatePathString(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3, unsigned __int16 *a4)
{
  int v4; // esi
  int v5; // edi
  unsigned __int16 *v6; // r10
  CMemoryLog *v7; // rax
  CVarObjHeap *v8; // rcx
  int v9; // edx
  unsigned __int16 *v10; // r10
  unsigned __int64 v11; // r11
  CMemoryLog *v12; // rax
  CMemoryLog *MemLogObject; // rax
  unsigned __int16 v15[128]; // [rsp+30h] [rbp-118h] BYREF

  v4 = (int)a3;
  v5 = StringCchCopyW(v15, 0x80u, a3);
  if ( v5 >= 0 )
  {
    v5 = StringCchCopyW(v6, 0x100u, L"SOFTWARE\\Classes\\CLSID\\");
    if ( v5 >= 0 )
    {
      v5 = StringCchCatW(v10, v11, v15);
      if ( v5 < 0 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v5);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 12;
          goto LABEL_16;
        }
      }
    }
    else
    {
      v12 = GetMemLogObject();
      CMemoryLog::Write(v12, v5);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 11;
        goto LABEL_16;
      }
    }
  }
  else
  {
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, v5);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 10;
LABEL_16:
      WPP_SF_SS(
        *((_QWORD *)v8 + 2),
        v9,
        (unsigned int)WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids,
        v4,
        (__int64)L"SOFTWARE\\Classes\\CLSID\\");
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800429e4  mov     [rsp+arg_8], rbx
0x1800429e9  mov     [rsp+arg_18], rsi
0x1800429ee  push    rdi
0x1800429ef  sub     rsp, 140h
0x1800429f6  mov     rax, cs:__security_cookie
0x1800429fd  xor     rax, rsp
0x180042a00  mov     [rsp+148h+var_18], rax
0x180042a08  mov     r10, rcx
0x180042a0b  mov     edx, 80h; unsigned __int64
0x180042a10  lea     rcx, [rsp+148h+var_118]; unsigned __int16 *
0x180042a15  mov     rsi, r8
0x180042a18  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180042a1d  mov     edi, eax
0x180042a1f  test    eax, eax
0x180042a21  jns     short loc_180042A70
0x180042a23  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042a29  mov     rcx, rax
0x180042a2c  mov     edx, edi
0x180042a2e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042a34  mov     rcx, cs:WPP_GLOBAL_Control
0x180042a3b  lea     rdx, WPP_GLOBAL_Control
0x180042a42  cmp     rcx, rdx
0x180042a45  jz      loc_180042B2B
0x180042a4b  test    byte ptr [rcx+1Ch], 1
0x180042a4f  jz      loc_180042B2B
0x180042a55  cmp     byte ptr [rcx+19h], 2
0x180042a59  jb      loc_180042B2B
0x180042a5f  mov     edx, 0Ah
0x180042a64  lea     rbx, aSoftwareClasse_0; "SOFTWARE\\Classes\\CLSID\\"
0x180042a6b  jmp     loc_180042B13
0x180042a70  lea     rbx, aSoftwareClasse_0; "SOFTWARE\\Classes\\CLSID\\"
0x180042a77  mov     r11d, 100h
0x180042a7d  mov     r8, rbx; unsigned __int16 *
0x180042a80  mov     edx, r11d; unsigned __int64
0x180042a83  mov     rcx, r10; unsigned __int16 *
0x180042a86  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180042a8b  mov     edi, eax
0x180042a8d  test    eax, eax
0x180042a8f  jns     short loc_180042AC8
0x180042a91  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042a97  mov     rcx, rax
0x180042a9a  mov     edx, edi
0x180042a9c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042aa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180042aa9  lea     rdx, WPP_GLOBAL_Control
0x180042ab0  cmp     rcx, rdx
0x180042ab3  jz      short loc_180042B2B
0x180042ab5  test    byte ptr [rcx+1Ch], 1
0x180042ab9  jz      short loc_180042B2B
0x180042abb  cmp     byte ptr [rcx+19h], 2
0x180042abf  jb      short loc_180042B2B
0x180042ac1  mov     edx, 0Bh
0x180042ac6  jmp     short loc_180042B13
0x180042ac8  lea     r8, [rsp+148h+var_118]; unsigned __int16 *
0x180042acd  mov     rdx, r11; unsigned __int64
0x180042ad0  mov     rcx, r10; unsigned __int16 *
0x180042ad3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180042ad8  mov     edi, eax
0x180042ada  test    eax, eax
0x180042adc  jns     short loc_180042B2B
0x180042ade  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042ae4  mov     rcx, rax
0x180042ae7  mov     edx, edi
0x180042ae9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042aef  mov     rcx, cs:WPP_GLOBAL_Control
0x180042af6  lea     rdx, WPP_GLOBAL_Control
0x180042afd  cmp     rcx, rdx
0x180042b00  jz      short loc_180042B2B
0x180042b02  test    byte ptr [rcx+1Ch], 1
0x180042b06  jz      short loc_180042B2B
0x180042b08  cmp     byte ptr [rcx+19h], 2
0x180042b0c  jb      short loc_180042B2B
0x180042b0e  mov     edx, 0Ch
0x180042b13  mov     rcx, [rcx+10h]
0x180042b17  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x180042b1e  mov     r9, rsi
0x180042b21  mov     [rsp+148h+var_128], rbx
0x180042b26  call    WPP_SF_SS
0x180042b2b  mov     eax, edi
0x180042b2d  mov     rcx, [rsp+148h+var_18]
0x180042b35  xor     rcx, rsp; StackCookie
0x180042b38  call    __security_check_cookie
0x180042b3d  lea     r11, [rsp+148h+var_8]
0x180042b45  mov     rbx, [r11+18h]
0x180042b49  mov     rsi, [r11+28h]
0x180042b4d  mov     rsp, r11
0x180042b50  pop     rdi
0x180042b51  retn
```
