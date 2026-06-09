# Resources::FormatSystemMessage(long)

- ea: `0x1800d7e5c`
- end: `0x1800d8031`
- name: `?FormatSystemMessage@Resources@@SAPEAVString@@J@Z`
- size: `469`
- prototype: `String *__fastcall(int errorid)`
- caller_count: `5`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180076b30`
- `0x1800a3ac0`
- `0x1800c4d60`
- `0x180113040`
- `0x18015f320`

## callees

- `0x180009490`
- `0x180009f88`
- `0x18000ae54`
- `0x18000d688`
- `0x18000d7d0`
- `0x18002addc`
- `0x180076b30`
- `0x18009f718`
- `0x1800a3e04`
- `0x1800d6770`
- `0x1800d7e5c`
- `0x1800d8038`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800d7ec2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800d7ec2`

## string_xrefs

- `0x1800d7edc`: `URLMON.DLL`
- `0x1800d7f5a`: `URLMON.DLL`
- `0x1800d7ef8`: `WININET.DLL`
- `0x1800d7f31`: `WINHTTP.DLL`

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
0x1800d7e5c  push    rbx
0x1800d7e5e  push    rsi
0x1800d7e5f  push    rdi
0x1800d7e60  sub     rsp, 40h
0x1800d7e64  mov     ebx, errorid
0x1800d7e66  mov     errorid, 1000h; cch
0x1800d7e6b  call    ??$new_array_ne@G@@YAPEAG_J@Z; new_array_ne<ushort>(__int64)
0x1800d7e70  mov     rsi, rax
0x1800d7e73  mov     [rsp+58h+buffer], rax
0x1800d7e78  xor     edi, edi
0x1800d7e7a  test    rax, rax
0x1800d7e7d  jnz     short loc_1800D7EA0
0x1800d7e7f  lea     rdx, ?s_cstrEmpty@String@@2V_CodebaseString@@B; p
0x1800d7e86  lea     rcx, [rsp+58h+result]; this
0x1800d7e8b  call    ??0?$_reference@VSchemaAnyAttribute@@@@QEAA@PEAVSchemaAnyAttribute@@@Z; _reference<SchemaAnyAttribute>::_reference<SchemaAnyAttribute>(SchemaAnyAttribute *)
0x1800d7e90  mov     rbx, [rax]
0x1800d7e93  mov     [rax], rdi
0x1800d7e96  lea     rcx, [rsp+58h+result]
0x1800d7e9b  jmp     loc_1800D8021
0x1800d7ea0  mov     [rsp+58h+Arguments], rdi; Arguments
0x1800d7ea5  mov     [rsp+58h+nSize], 1000h; nSize
0x1800d7ead  mov     [rsp+58h+lpBuffer], rsi; lpBuffer
0x1800d7eb2  mov     r9d, 400h; dwLanguageId
0x1800d7eb8  mov     r8d, ebx; dwMessageId
0x1800d7ebb  xor     edx, edx; lpSource
0x1800d7ebd  mov     errorid, 1000h; dwFlags
0x1800d7ec2  call    cs:__imp_FormatMessageW
0x1800d7ec8  mov     errorid, eax
0x1800d7eca  test    eax, eax
0x1800d7ecc  jnz     $done_0
0x1800d7ed2  mov     byte ptr [rsp+58h+lpBuffer], 1; pszModule
0x1800d7ed7  mov     r8, rsi; buffer
0x1800d7eda  mov     edx, ebx; errorid
0x1800d7edc  lea     rcx, aUrlmonDll; "URLMON.DLL"
0x1800d7ee3  call    ?SafeFormatMessage@Resources@@KAKPEBGKPEAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1800d7ee8  mov     errorid, eax
0x1800d7eea  test    eax, eax
0x1800d7eec  jnz     short $done_0
0x1800d7eee  mov     byte ptr [rsp+58h+lpBuffer], 1; pszModule
0x1800d7ef3  mov     r8, rsi; buffer
0x1800d7ef6  mov     edx, ebx; errorid
0x1800d7ef8  lea     rcx, aWininetDll; "WININET.DLL"
0x1800d7eff  call    ?SafeFormatMessage@Resources@@KAKPEBGKPEAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1800d7f04  mov     errorid, eax
0x1800d7f06  test    eax, eax
0x1800d7f08  jnz     short $done_0
0x1800d7f0a  mov     eax, ebx
0x1800d7f0c  and     eax, 1FFF0000h
0x1800d7f11  cmp     eax, 70000h
0x1800d7f16  jnz     short loc_1800D7F43
0x1800d7f18  movzx   eax, bx
0x1800d7f1b  sub     eax, 2EE1h
0x1800d7f20  cmp     eax, 0C0h
0x1800d7f25  ja      short loc_1800D7F43
0x1800d7f27  mov     byte ptr [rsp+58h+lpBuffer], 1; pszModule
0x1800d7f2c  mov     r8, rsi; buffer
0x1800d7f2f  mov     edx, ebx; errorid
0x1800d7f31  lea     rcx, aWinhttpDll; "WINHTTP.DLL"
0x1800d7f38  call    ?SafeFormatMessage@Resources@@KAKPEBGKPEAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1800d7f3d  mov     errorid, eax
0x1800d7f3f  test    eax, eax
0x1800d7f41  jnz     short $done_0
0x1800d7f43  lea     eax, [rbx+7FF40000h]
0x1800d7f49  cmp     eax, 3FFh
0x1800d7f4e  ja      short $done_0
0x1800d7f50  mov     byte ptr [rsp+58h+lpBuffer], dil; pszModule
0x1800d7f55  mov     r8, rsi; buffer
0x1800d7f58  mov     edx, ebx; errorid
0x1800d7f5a  lea     rcx, aUrlmonDll; "URLMON.DLL"
0x1800d7f61  call    ?SafeFormatMessage@Resources@@KAKPEBGKPEAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1800d7f66  mov     errorid, eax
0x1800d7f68  mov     [rsp+58h+num._p], rdi
0x1800d7f6d  mov     [rsp+58h+result._p], rdi
0x1800d7f72  test    errorid, errorid
0x1800d7f74  jz      short loc_1800D7F86
0x1800d7f76  mov     eax, errorid
0x1800d7f78  mov     [rsi+rax*2], di
0x1800d7f7c  mov     rcx, rsi; c
0x1800d7f7f  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800d7f84  jmp     short loc_1800D7FBB
0x1800d7f86  mov     errorid, ebx; c
0x1800d7f88  call    ?newString@String@@SAPEAV1@H@Z; String::newString(int)
0x1800d7f8d  mov     rbx, rax
0x1800d7f90  lea     rcx, [rsp+58h+num]; ppref
0x1800d7f95  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800d7f9a  mov     [rsp+58h+num._p], rbx
0x1800d7f9f  mov     qword ptr [rsp+58h+nSize], rdi; a4
0x1800d7fa4  mov     [rsp+58h+lpBuffer], rdi; a3
0x1800d7fa9  xor     r9d, r9d; a2
0x1800d7fac  mov     r8, rbx; a1
0x1800d7faf  mov     edx, 0C00CE30Ah; resid
0x1800d7fb4  xor     errorid, errorid; ppParams
0x1800d7fb6  call    ?formatMessage@Resources@@SAPEAVString@@PEAPEAV?$_array@V?$_reference@VString@@@@@@JPEAV2@111@Z; Resources::formatMessage(_array<_reference<String>> * *,long,String *,String *,String *,String *)
0x1800d7fbb  mov     rbx, rax
0x1800d7fbe  lea     rcx, [rsp+58h+result]; ppref
0x1800d7fc3  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800d7fc8  mov     [rsp+58h+result._p], rbx
0x1800d7fcd  jmp     short loc_1800D8005
0x1800d7fcf  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x1800d7fd4  cmp     [rsp+58h+num._p], 0
0x1800d7fda  jz      short loc_1800D7FE8
0x1800d7fdc  xor     edx, edx; pref
0x1800d7fde  lea     rcx, [rsp+58h+num]; ppref
0x1800d7fe3  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800d7fe8  lea     rdx, ?s_cstrEmpty@String@@2V_CodebaseString@@B; pref
0x1800d7fef  lea     rcx, [rsp+58h+result]; ppref
0x1800d7ff4  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800d7ff9  xor     edi, edi
0x1800d7ffb  mov     rsi, [rsp+58h+buffer]
0x1800d8000  mov     rbx, [rsp+58h+result._p]
0x1800d8005  mov     rcx, rsi; pv
0x1800d8008  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800d800d  mov     [rsp+58h+result._p], rdi
0x1800d8012  lea     rcx, [rsp+58h+result]; ppref
0x1800d8017  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800d801c  lea     rcx, [rsp+58h+num]; ppref
0x1800d8021  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800d8026  mov     rax, rbx
0x1800d8029  add     rsp, 40h
0x1800d802d  pop     rdi
0x1800d802e  pop     rsi
0x1800d802f  pop     rbx
0x1800d8030  retn
0x18017ee09  push    rbp
0x18017ee0b  sub     rsp, 40h
0x18017ee0f  mov     rbp, rdx
0x18017ee12  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z
0x18017ee17  nop
0x18017ee18  add     rsp, 40h
0x18017ee1c  pop     rbp
0x18017ee1d  retn
```
