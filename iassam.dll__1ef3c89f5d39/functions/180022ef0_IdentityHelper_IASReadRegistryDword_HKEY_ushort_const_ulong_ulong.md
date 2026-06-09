# IdentityHelper::IASReadRegistryDword(HKEY__ * &,ushort const *,ulong,ulong *)

- ea: `0x180022ef0`
- end: `0x180023093`
- name: `?IASReadRegistryDword@IdentityHelper@@IEAAJAEAPEAUHKEY__@@PEBGKPEAK@Z`
- size: `419`
- prototype: `int(IdentityHelper *__hidden this, HKEY *, const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800235fc`

## callees

- `0x18001426c`
- `0x180022ef0`
- `0x180023b58`
- `0x1800254a0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180022f3a`
- `ADVAPI32!RegQueryValueExW` at `0x180022f3a`

## string_xrefs

- `0x180022fdb`: `The registry value %S does not exist. Using default %ld`
- `0x180022f71`: `Cannot read value %S.  error %ld`
- `0x180023050`: `Cannot read value %S.  Wrong type %ld. Size = %ld`

## pseudocode

```c
__int64 __fastcall IdentityHelper::IASReadRegistryDword(
        IdentityHelper *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int *a5)
{
  unsigned int *v5; // r14
  LSTATUS v8; // eax
  int v9; // ebx
  int v10; // r9d
  int v12; // r9d
  int v13; // edx
  int v14; // r8d
  int v15; // r9d
  DWORD v16[14]; // [rsp+40h] [rbp-38h] BYREF
  DWORD v17; // [rsp+80h] [rbp+8h] BYREF
  int v18; // [rsp+84h] [rbp+Ch]

  v18 = HIDWORD(this);
  v5 = a5;
  v17 = 4;
  v16[0] = 0;
  v8 = RegQueryValueExW(*a2, a3, 0, v16, (LPBYTE)a5, &v17);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 != 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Cannot read value %S.  error %ld");
        WPP_SF_sSl(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)&WPP_a4ca7ab9b7a63a7fb5f5b576ced31875_Traceguids,
          v10,
          (__int64)a3,
          v9);
      }
      if ( v9 > 0 )
        return (unsigned __int16)v9 | 0x80070000;
      return (unsigned int)v9;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("The registry value %S does not exist. Using default %ld");
      WPP_SF_sSl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_a4ca7ab9b7a63a7fb5f5b576ced31875_Traceguids,
        v12,
        (__int64)a3,
        a4);
    }
    *v5 = a4;
    return 0;
  }
  if ( v16[0] == 4 && v17 == 4 )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Cannot read value %S.  Wrong type %ld. Size = %ld");
    WPP_SF_sSll(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, v15, (__int64)a3, v16[0], v17);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180022ef0  mov     r11, rsp
0x180022ef3  mov     [r11+8], rcx
0x180022ef7  push    rbx
0x180022ef8  push    rsi
0x180022ef9  push    rdi
0x180022efa  push    r14
0x180022efc  sub     rsp, 58h
0x180022f00  mov     r14, [rsp+78h+arg_20]
0x180022f08  lea     rcx, [r11+8]
0x180022f0c  mov     rax, rdx
0x180022f0f  mov     [r11-50h], rcx
0x180022f13  mov     rdi, r8
0x180022f16  mov     dword ptr [r11+8], 4
0x180022f1e  mov     esi, r9d
0x180022f21  mov     [rsp+78h+var_38], 0
0x180022f29  lea     r9, [r11-38h]; lpType
0x180022f2d  mov     [r11-58h], r14
0x180022f31  mov     rcx, [rax]; hKey
0x180022f34  xor     r8d, r8d; lpReserved
0x180022f37  mov     rdx, rdi; lpValueName
0x180022f3a  call    cs:__imp_RegQueryValueExW
0x180022f40  mov     ebx, eax
0x180022f42  test    eax, eax
0x180022f44  jz      loc_180023016
0x180022f4a  cmp     eax, 2
0x180022f4d  jz      short loc_180022FB9
0x180022f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f56  lea     rax, WPP_GLOBAL_Control
0x180022f5d  cmp     rcx, rax
0x180022f60  jz      short loc_180022FA5
0x180022f62  cmp     byte ptr [rcx+19h], 2
0x180022f66  jb      short loc_180022FA5
0x180022f68  test    byte ptr [rcx+1Ch], 4
0x180022f6c  jz      short loc_180022FA5
0x180022f6e  mov     r8d, ebx
0x180022f71  lea     rcx, aCannotReadValu_1; "Cannot read value %S.  error %ld"
0x180022f78  mov     rdx, rdi
0x180022f7b  call    WppDbgPrint
0x180022f80  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f87  lea     r8, WPP_a4ca7ab9b7a63a7fb5f5b576ced31875_Traceguids
0x180022f8e  mov     edx, 0Ah
0x180022f93  mov     [rsp+78h+var_50], ebx
0x180022f97  mov     [rsp+78h+var_58], rdi
0x180022f9c  mov     rcx, [rcx+10h]
0x180022fa0  call    WPP_SF_sSl
0x180022fa5  test    ebx, ebx
0x180022fa7  jle     short loc_180022FB2
0x180022fa9  movzx   ebx, bx
0x180022fac  or      ebx, 80070000h
0x180022fb2  mov     eax, ebx
0x180022fb4  jmp     loc_180023089
0x180022fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180022fc0  lea     rax, WPP_GLOBAL_Control
0x180022fc7  cmp     rcx, rax
0x180022fca  jz      short loc_18002300F
0x180022fcc  cmp     byte ptr [rcx+19h], 4
0x180022fd0  jb      short loc_18002300F
0x180022fd2  test    byte ptr [rcx+1Ch], 4
0x180022fd6  jz      short loc_18002300F
0x180022fd8  mov     r8d, esi
0x180022fdb  lea     rcx, aTheRegistryVal; "The registry value %S does not exist. U"...
0x180022fe2  mov     rdx, rdi
0x180022fe5  call    WppDbgPrint
0x180022fea  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ff1  lea     r8, WPP_a4ca7ab9b7a63a7fb5f5b576ced31875_Traceguids
0x180022ff8  mov     edx, 0Bh
0x180022ffd  mov     [rsp+78h+var_50], esi
0x180023001  mov     [rsp+78h+var_58], rdi
0x180023006  mov     rcx, [rcx+10h]
0x18002300a  call    WPP_SF_sSl
0x18002300f  mov     [r14], esi
0x180023012  xor     eax, eax
0x180023014  jmp     short loc_180023089
0x180023016  mov     r8d, [rsp+78h+var_38]
0x18002301b  mov     r9d, [rsp+78h+arg_0]
0x180023023  cmp     r8d, 4
0x180023027  jnz     short loc_18002302E
0x180023029  cmp     r9d, r8d
0x18002302c  jz      short loc_180023012
0x18002302e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023035  lea     rax, WPP_GLOBAL_Control
0x18002303c  cmp     rcx, rax
0x18002303f  jz      short loc_180023084
0x180023041  cmp     byte ptr [rcx+19h], 2
0x180023045  jb      short loc_180023084
0x180023047  test    byte ptr [rcx+1Ch], 4
0x18002304b  jz      short loc_180023084
0x18002304d  mov     rdx, rdi
0x180023050  lea     rcx, aCannotReadValu_4; "Cannot read value %S.  Wrong type %ld. "...
0x180023057  call    WppDbgPrint
0x18002305c  mov     eax, [rsp+78h+arg_0]
0x180023063  mov     rcx, cs:WPP_GLOBAL_Control
0x18002306a  mov     [rsp+78h+var_48], eax
0x18002306e  mov     eax, [rsp+78h+var_38]
0x180023072  mov     [rsp+78h+var_50], eax
0x180023076  mov     rcx, [rcx+10h]
0x18002307a  mov     [rsp+78h+var_58], rdi
0x18002307f  call    WPP_SF_sSll
0x180023084  mov     eax, 80070057h
0x180023089  add     rsp, 58h
0x18002308d  pop     r14
0x18002308f  pop     rdi
0x180023090  pop     rsi
0x180023091  pop     rbx
0x180023092  retn
```
