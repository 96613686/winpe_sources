# Resources::FormatSystemMessage(long)

- ea: `0x1800d9bbc`
- end: `0x1800d9d98`
- name: `?FormatSystemMessage@Resources@@SAPEAVString@@J@Z`
- size: `476`
- prototype: `String *__fastcall(int errorid)`
- caller_count: `5`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180089e10`
- `0x1800a3a00`
- `0x1800c65ec`
- `0x180115830`
- `0x180162cd0`

## callees

- `0x180015a80`
- `0x180016588`
- `0x180017480`
- `0x180019cd0`
- `0x180019e20`
- `0x18002a370`
- `0x180089e10`
- `0x18009fefc`
- `0x1800a3c08`
- `0x1800d8454`
- `0x1800d9bbc`
- `0x1800d9da0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800d9c22`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800d9c22`

## string_xrefs

- `0x1800d9c42`: `URLMON.DLL`
- `0x1800d9cc0`: `URLMON.DLL`
- `0x1800d9c5e`: `WININET.DLL`
- `0x1800d9c97`: `WINHTTP.DLL`

## pseudocode

```c
String *__fastcall Resources::FormatSystemMessage(DWORD errorid)
{
  wchar_t *lpBuffer; // rax
  wchar_t *v3; // rsi
  String **v4; // rax
  String *v5; // rbx
  _reference<String> *p_num; // rcx
  int v7; // ecx
  unsigned int v8; // r9d
  unsigned int v9; // r9d
  unsigned int v10; // r9d
  String *v11; // rax
  String *v12; // rbx
  _reference<String> result; // [rsp+68h] [rbp+10h] BYREF
  _reference<String> num; // [rsp+70h] [rbp+18h] BYREF
  wchar_t *buffer; // [rsp+78h] [rbp+20h]

  lpBuffer = new_array_ne<unsigned short>(4096);
  v3 = lpBuffer;
  buffer = lpBuffer;
  if ( lpBuffer )
  {
    v7 = FormatMessageW(0x1000u, 0, errorid, 0x400u, lpBuffer, 0x1000u, 0);
    if ( !v7 )
    {
      v7 = Resources::SafeFormatMessage(L"URLMON.DLL", errorid, v3, v8, 1);
      if ( !v7 )
      {
        v7 = Resources::SafeFormatMessage(L"WININET.DLL", errorid, v3, v9, 1);
        if ( !v7
          && ((errorid & 0x1FFF0000) != 0x70000
           || (unsigned int)(unsigned __int16)errorid - 12001 > 0xC0
           || (v7 = Resources::SafeFormatMessage(L"WINHTTP.DLL", errorid, v3, v10, 1)) == 0)
          && errorid + 2146697216 <= 0x3FF )
        {
          v7 = Resources::SafeFormatMessage(L"URLMON.DLL", errorid, v3, v10, 0);
        }
      }
    }
    num._p = 0;
    result._p = 0;
    if ( v7 )
    {
      v3[v7] = 0;
      v11 = String::newString(v3);
    }
    else
    {
      v12 = String::newString(errorid);
      release(&num._p);
      num._p = v12;
      v11 = Resources::formatMessage(0, -1072897270, v12, 0, 0, 0);
    }
    v5 = v11;
    release(&result._p);
    result._p = v5;
    MemFree(v3);
    result._p = 0;
    release(&result._p);
    p_num = &num;
  }
  else
  {
    _reference<SchemaAnyAttribute>::_reference<SchemaAnyAttribute>(
      (_reference<IInternetSecurityManager> *)&result,
      (IInternetSecurityManager *)&String::s_cstrEmpty);
    v5 = *v4;
    *v4 = 0;
    p_num = &result;
  }
  release(&p_num->_p);
  return v5;
}

```

## disassembly

```asm
0x1800d9bbc  push    rbx
0x1800d9bbe  push    rsi
0x1800d9bbf  push    rdi
0x1800d9bc0  sub     rsp, 40h
0x1800d9bc4  mov     ebx, errorid
0x1800d9bc6  mov     errorid, 1000h; cch
0x1800d9bcb  call    ??$new_array_ne@G@@YAPEAG_J@Z; new_array_ne<ushort>(__int64)
0x1800d9bd0  mov     rsi, rax
0x1800d9bd3  mov     [rsp+58h+buffer], rax
0x1800d9bd8  xor     edi, edi
0x1800d9bda  test    rax, rax
0x1800d9bdd  jnz     short loc_1800D9C00
0x1800d9bdf  lea     rdx, ?s_cstrEmpty@String@@2V_CodebaseString@@B; p
0x1800d9be6  lea     rcx, [rsp+58h+result]; this
0x1800d9beb  call    ??0?$_reference@VSchemaAnyAttribute@@@@QEAA@PEAVSchemaAnyAttribute@@@Z; _reference<SchemaAnyAttribute>::_reference<SchemaAnyAttribute>(SchemaAnyAttribute *)
0x1800d9bf0  mov     rbx, [rax]
0x1800d9bf3  mov     [rax], rdi
0x1800d9bf6  lea     rcx, [rsp+58h+result]
0x1800d9bfb  jmp     loc_1800D9D87
0x1800d9c00  mov     [rsp+58h+Arguments], rdi; Arguments
0x1800d9c05  mov     [rsp+58h+nSize], 1000h; nSize
0x1800d9c0d  mov     [rsp+58h+lpBuffer], rsi; lpBuffer
0x1800d9c12  mov     r9d, 400h; dwLanguageId
0x1800d9c18  mov     r8d, ebx; dwMessageId
0x1800d9c1b  xor     edx, edx; lpSource
0x1800d9c1d  mov     errorid, 1000h; dwFlags
0x1800d9c22  call    cs:__imp_FormatMessageW
0x1800d9c29  nop     dword ptr [rax+rax+00h]
0x1800d9c2e  mov     errorid, eax
0x1800d9c30  test    eax, eax
0x1800d9c32  jnz     $done_0
0x1800d9c38  mov     byte ptr [rsp+58h+lpBuffer], 1; pszModule
0x1800d9c3d  mov     r8, rsi; buffer
0x1800d9c40  mov     edx, ebx; errorid
0x1800d9c42  lea     rcx, aUrlmonDll; "URLMON.DLL"
0x1800d9c49  call    ?SafeFormatMessage@Resources@@KAKPEBGKPEAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1800d9c4e  mov     errorid, eax
0x1800d9c50  test    eax, eax
0x1800d9c52  jnz     short $done_0
0x1800d9c54  mov     byte ptr [rsp+58h+lpBuffer], 1; pszModule
0x1800d9c59  mov     r8, rsi; buffer
0x1800d9c5c  mov     edx, ebx; errorid
0x1800d9c5e  lea     rcx, aWininetDll; "WININET.DLL"
0x1800d9c65  call    ?SafeFormatMessage@Resources@@KAKPEBGKPEAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1800d9c6a  mov     errorid, eax
0x1800d9c6c  test    eax, eax
0x1800d9c6e  jnz     short $done_0
0x1800d9c70  mov     eax, ebx
0x1800d9c72  and     eax, 1FFF0000h
0x1800d9c77  cmp     eax, 70000h
0x1800d9c7c  jnz     short loc_1800D9CA9
0x1800d9c7e  movzx   eax, bx
0x1800d9c81  sub     eax, 2EE1h
0x1800d9c86  cmp     eax, 0C0h
0x1800d9c8b  ja      short loc_1800D9CA9
0x1800d9c8d  mov     byte ptr [rsp+58h+lpBuffer], 1; pszModule
0x1800d9c92  mov     r8, rsi; buffer
0x1800d9c95  mov     edx, ebx; errorid
0x1800d9c97  lea     rcx, aWinhttpDll; "WINHTTP.DLL"
0x1800d9c9e  call    ?SafeFormatMessage@Resources@@KAKPEBGKPEAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1800d9ca3  mov     errorid, eax
0x1800d9ca5  test    eax, eax
0x1800d9ca7  jnz     short $done_0
0x1800d9ca9  lea     eax, [rbx+7FF40000h]
0x1800d9caf  cmp     eax, 3FFh
0x1800d9cb4  ja      short $done_0
0x1800d9cb6  mov     byte ptr [rsp+58h+lpBuffer], dil; pszModule
0x1800d9cbb  mov     r8, rsi; buffer
0x1800d9cbe  mov     edx, ebx; errorid
0x1800d9cc0  lea     rcx, aUrlmonDll; "URLMON.DLL"
0x1800d9cc7  call    ?SafeFormatMessage@Resources@@KAKPEBGKPEAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1800d9ccc  mov     errorid, eax
0x1800d9cce  mov     [rsp+58h+num._p], rdi
0x1800d9cd3  mov     [rsp+58h+result._p], rdi
0x1800d9cd8  test    errorid, errorid
0x1800d9cda  jz      short loc_1800D9CEC
0x1800d9cdc  mov     eax, errorid
0x1800d9cde  mov     [rsi+rax*2], di
0x1800d9ce2  mov     rcx, rsi; c
0x1800d9ce5  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800d9cea  jmp     short loc_1800D9D21
0x1800d9cec  mov     errorid, ebx; c
0x1800d9cee  call    ?newString@String@@SAPEAV1@H@Z; String::newString(int)
0x1800d9cf3  mov     rbx, rax
0x1800d9cf6  lea     rcx, [rsp+58h+num]; ppref
0x1800d9cfb  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800d9d00  mov     [rsp+58h+num._p], rbx
0x1800d9d05  mov     qword ptr [rsp+58h+nSize], rdi; a4
0x1800d9d0a  mov     [rsp+58h+lpBuffer], rdi; a3
0x1800d9d0f  xor     r9d, r9d; a2
0x1800d9d12  mov     r8, rbx; a1
0x1800d9d15  mov     edx, 0C00CE30Ah; resid
0x1800d9d1a  xor     errorid, errorid; ppParams
0x1800d9d1c  call    ?formatMessage@Resources@@SAPEAVString@@PEAPEAV?$_array@V?$_reference@VString@@@@@@JPEAV2@111@Z; Resources::formatMessage(_array<_reference<String>> * *,long,String *,String *,String *,String *)
0x1800d9d21  mov     rbx, rax
0x1800d9d24  lea     rcx, [rsp+58h+result]; ppref
0x1800d9d29  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800d9d2e  mov     [rsp+58h+result._p], rbx
0x1800d9d33  jmp     short loc_1800D9D6B
0x1800d9d35  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x1800d9d3a  cmp     [rsp+58h+num._p], 0
0x1800d9d40  jz      short loc_1800D9D4E
0x1800d9d42  xor     edx, edx; pref
0x1800d9d44  lea     rcx, [rsp+58h+num]; ppref
0x1800d9d49  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800d9d4e  lea     rdx, ?s_cstrEmpty@String@@2V_CodebaseString@@B; pref
0x1800d9d55  lea     rcx, [rsp+58h+result]; ppref
0x1800d9d5a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800d9d5f  xor     edi, edi
0x1800d9d61  mov     rsi, [rsp+58h+buffer]
0x1800d9d66  mov     rbx, [rsp+58h+result._p]
0x1800d9d6b  mov     rcx, rsi; pv
0x1800d9d6e  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800d9d73  mov     [rsp+58h+result._p], rdi
0x1800d9d78  lea     rcx, [rsp+58h+result]; ppref
0x1800d9d7d  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800d9d82  lea     rcx, [rsp+58h+num]; ppref
0x1800d9d87  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800d9d8c  mov     rax, rbx
0x1800d9d8f  add     rsp, 40h
0x1800d9d93  pop     rdi
0x1800d9d94  pop     rsi
0x1800d9d95  pop     rbx
0x1800d9d96  retn
0x180182ac7  push    rbp
0x180182ac9  sub     rsp, 40h
0x180182acd  mov     rbp, rdx
0x180182ad0  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z
0x180182ad5  nop
0x180182ad6  add     rsp, 40h
0x180182ada  pop     rbp
0x180182adb  retn
```
