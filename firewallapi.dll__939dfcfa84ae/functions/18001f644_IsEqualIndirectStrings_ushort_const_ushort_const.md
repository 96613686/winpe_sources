# IsEqualIndirectStrings(ushort const *,ushort const *)

- ea: `0x18001f644`
- end: `0x18001f76a`
- name: `?IsEqualIndirectStrings@@YAHPEBG0@Z`
- size: `294`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f528`
- `0x180032e5c`

## callees

- `0x18001f644`
- `0x1800294b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f70c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f70c`
- `fwbase!FwBaseFree` at `0x18001f730`
- `fwbase!FwBaseFree` at `0x18001f741`
- `fwbase!FwBaseFree` at `0x18001f730`
- `fwbase!FwBaseFree` at `0x18001f741`
- `fwbase!FwResolveIndirectString` at `0x18001f6b3`
- `fwbase!FwResolveIndirectString` at `0x18001f6de`
- `fwbase!FwResolveIndirectString` at `0x18001f6b3`
- `fwbase!FwResolveIndirectString` at `0x18001f6de`
- `fwbase!FwReportReturnError` at `0x18001f6a0`
- `fwbase!FwReportReturnError` at `0x18001f6a0`
- `fwbase!FwStringCopy` at `0x18001f687`
- `fwbase!FwStringCopy` at `0x18001f6c9`
- `fwbase!FwStringCopy` at `0x18001f687`
- `fwbase!FwStringCopy` at `0x18001f6c9`

## pseudocode

```c
_BOOL8 __fastcall IsEqualIndirectStrings(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  BOOL v2; // edi
  const unsigned __int16 *v3; // rbx
  const unsigned __int16 *v4; // rsi
  int v5; // eax
  int v6; // ebp
  int v7; // eax
  const unsigned __int16 *v9; // [rsp+20h] [rbp-38h] BYREF
  const unsigned __int16 *v10; // [rsp+28h] [rbp-30h] BYREF

  v2 = 0;
  v3 = a2;
  v9 = 0;
  v4 = a1;
  v10 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v5 = FwStringCopy(a1, &v9);
      if ( v5 < 0 || (v6 = FwResolveIndirectString(&v9), v5 = FwStringCopy(v3, &v10), v5 < 0) )
      {
        FwReportReturnError("IsEqualIndirectStrings", (unsigned int)v5);
      }
      else
      {
        v7 = FwResolveIndirectString(&v10);
        if ( v6 >= 0 && v7 >= 0 )
        {
          v3 = v10;
          v4 = v9;
        }
        LOBYTE(v2) = (unsigned int)_o__wcsicmp(v4, v3) == 0;
      }
    }
  }
  else
  {
    v2 = a2 == 0;
  }
  FwBaseFree(v9);
  FwBaseFree(v10);
  return v2;
}

```

## disassembly

```asm
0x18001f644  mov     r11, rsp
0x18001f647  mov     [r11+18h], rbx
0x18001f64b  push    rbp
0x18001f64c  push    rsi
0x18001f64d  push    rdi
0x18001f64e  sub     rsp, 40h
0x18001f652  mov     rax, cs:__security_cookie
0x18001f659  xor     rax, rsp
0x18001f65c  mov     [rsp+58h+var_28], rax
0x18001f661  xor     edi, edi
0x18001f663  mov     rbx, rdx
0x18001f666  mov     [r11-38h], rdi
0x18001f66a  mov     rsi, rcx
0x18001f66d  mov     [r11-30h], rdi
0x18001f671  test    rcx, rcx
0x18001f674  jz      loc_18001F720
0x18001f67a  test    rdx, rdx
0x18001f67d  jz      loc_18001F72B
0x18001f683  lea     rdx, [r11-38h]
0x18001f687  call    cs:__imp_FwStringCopy
0x18001f68e  nop     dword ptr [rax+rax+00h]
0x18001f693  test    eax, eax
0x18001f695  jns     short loc_18001F6AE
0x18001f697  mov     edx, eax
0x18001f699  lea     rcx, aIsequalindirec; "IsEqualIndirectStrings"
0x18001f6a0  call    cs:__imp_FwReportReturnError
0x18001f6a7  nop     dword ptr [rax+rax+00h]
0x18001f6ac  jmp     short loc_18001F72B
0x18001f6ae  lea     rcx, [rsp+58h+var_38]
0x18001f6b3  call    cs:__imp_FwResolveIndirectString
0x18001f6ba  nop     dword ptr [rax+rax+00h]
0x18001f6bf  lea     rdx, [rsp+58h+var_30]
0x18001f6c4  mov     rcx, rbx
0x18001f6c7  mov     ebp, eax
0x18001f6c9  call    cs:__imp_FwStringCopy
0x18001f6d0  nop     dword ptr [rax+rax+00h]
0x18001f6d5  test    eax, eax
0x18001f6d7  js      short loc_18001F697
0x18001f6d9  lea     rcx, [rsp+58h+var_30]
0x18001f6de  call    cs:__imp_FwResolveIndirectString
0x18001f6e5  nop     dword ptr [rax+rax+00h]
0x18001f6ea  test    ebp, ebp
0x18001f6ec  js      short loc_18001F706
0x18001f6ee  test    eax, eax
0x18001f6f0  js      short loc_18001F6F9
0x18001f6f2  mov     rbx, [rsp+58h+var_30]
0x18001f6f7  jmp     short loc_18001F701
0x18001f6f9  test    ebp, ebp
0x18001f6fb  js      short loc_18001F706
0x18001f6fd  test    eax, eax
0x18001f6ff  js      short loc_18001F706
0x18001f701  mov     rsi, [rsp+58h+var_38]
0x18001f706  mov     rdx, rbx
0x18001f709  mov     rcx, rsi
0x18001f70c  call    cs:__imp__o__wcsicmp
0x18001f713  nop     dword ptr [rax+rax+00h]
0x18001f718  test    eax, eax
0x18001f71a  setz    dil
0x18001f71e  jmp     short loc_18001F72B
0x18001f720  test    rbx, rbx
0x18001f723  mov     eax, 1
0x18001f728  cmovz   edi, eax
0x18001f72b  mov     rcx, [rsp+58h+var_38]
0x18001f730  call    cs:__imp_FwBaseFree
0x18001f737  nop     dword ptr [rax+rax+00h]
0x18001f73c  mov     rcx, [rsp+58h+var_30]
0x18001f741  call    cs:__imp_FwBaseFree
0x18001f748  nop     dword ptr [rax+rax+00h]
0x18001f74d  mov     eax, edi
0x18001f74f  mov     rcx, [rsp+58h+var_28]
0x18001f754  xor     rcx, rsp; StackCookie
0x18001f757  call    __security_check_cookie
0x18001f75c  mov     rbx, [rsp+58h+arg_10]
0x18001f761  add     rsp, 40h
0x18001f765  pop     rdi
0x18001f766  pop     rsi
0x18001f767  pop     rbp
0x18001f768  retn
```
