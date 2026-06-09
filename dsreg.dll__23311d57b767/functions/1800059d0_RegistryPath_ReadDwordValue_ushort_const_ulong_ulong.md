# RegistryPath::ReadDwordValue(ushort const *,ulong *,ulong)

- ea: `0x1800059d0`
- end: `0x180005b90`
- name: `?ReadDwordValue@RegistryPath@@QEBAKPEBGPEAKK@Z`
- size: `448`
- prototype: `unsigned int(RegistryPath *__hidden this, const unsigned __int16 *, unsigned int *, unsigned int)`
- caller_count: `9`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180004218`
- `0x180037444`
- `0x18003c828`
- `0x18003f0e4`
- `0x18005f2c4`
- `0x18005f7fc`
- `0x18009ea50`
- `0x18009ec3c`
- `0x1800b31f4`

## callees

- `0x1800059d0`
- `0x180005ba0`
- `0x180006450`
- `0x1800065d0`
- `0x1800084f4`
- `0x180008530`
- `0x18008cf68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005a61`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005a61`

## string_xrefs

- `0x180005a95`: `RegReadDwordValue`
- `0x180005b0a`: `RegReadDwordValue`
- `0x180005b54`: `RegReadDwordValue`
- `0x180005af0`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x180005a7a`: `%s: The registry key value "%s@%s" does not exist. Using default value %lu. Error code: 0x%08x.`
- `0x180005ae9`: `RegistryPath::ReadDwordValue`
- `0x180005b5b`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x180005ae0`: `%s: The registry key value "%s@%s" is not of type DWORD. Using default value %lu. Error code: 0x%08x.`

## pseudocode

```c
LSTATUS __fastcall RegistryPath::ReadDwordValue(
        RegistryPath *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int a4)
{
  const unsigned __int16 *v7; // r14
  HKEY v8; // rax
  LSTATUS ValueW; // eax
  LSTATUS v10; // ebx
  int v11; // eax
  wchar_t *v12; // rcx
  const wchar_t *v13; // r9
  int v15; // eax
  const wchar_t *v16; // r9
  const unsigned __int16 *v17; // rax
  HKEY v18; // r10
  unsigned int *v19; // [rsp+20h] [rbp-48h]
  __int64 v20; // [rsp+28h] [rbp-40h]
  unsigned int v21; // [rsp+40h] [rbp-28h] BYREF
  DWORD v22[9]; // [rsp+44h] [rbp-24h] BYREF
  DWORD v23; // [rsp+70h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 4) && (v7 = *(const unsigned __int16 **)this) != 0 && *v7 )
  {
    v8 = (HKEY)*((_QWORD *)this + 5);
    if ( v8 )
    {
      v23 = 0;
      v21 = a4;
      v22[0] = 4;
      if ( !a3 )
      {
        Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadDwordValue", L"pData");
        return 87;
      }
      ValueW = RegGetValueW(v8, 0, a2, 0xFFFFu, &v23, &v21, v22);
      v10 = ValueW;
      if ( ValueW == 2 )
      {
        v11 = IsEmptyString(a2);
        LODWORD(v20) = 2;
        v12 = (wchar_t *)L"%s: The registry key value \"%s@%s\" does not exist. Using default value %lu. Error code: 0x%08x.";
      }
      else
      {
        if ( ValueW != 234 )
        {
          if ( ValueW )
          {
            Logger::WriteRegistryFailureEvent(ValueW, L"RegGetValueW", v7, a2);
            v15 = IsEmptyString(a2);
            LODWORD(v19) = v10;
            v16 = L"(default)";
            if ( !v15 )
              v16 = a2;
            Logger::TraceWarning(
              (wchar_t *)L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
              L"RegReadDwordValue",
              v7,
              v16,
              v19);
            goto LABEL_11;
          }
          if ( v23 == 4 )
          {
LABEL_11:
            *a3 = v21;
            return v10;
          }
        }
        v11 = IsEmptyString(a2);
        LODWORD(v20) = v10;
        v12 = (wchar_t *)L"%s: The registry key value \"%s@%s\" is not of type DWORD. Using default value %lu. Error code: 0x%08x.";
      }
      LODWORD(v19) = a4;
      v13 = L"(default)";
      if ( !v11 )
        v13 = a2;
      Logger::TraceWarning(v12, L"RegReadDwordValue", v7, v13, v19, v20);
      v10 = 0;
      goto LABEL_11;
    }
    v17 = RegistryPath::SubPath(this);
    return RegReadDwordValue(v18, v17, a2, v7, a3, a4);
  }
  else
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::ReadDwordValue");
    return 87;
  }
}

```

## disassembly

```asm
0x1800059d0  mov     r11, rsp
0x1800059d3  mov     [r11+10h], rbx
0x1800059d7  mov     [r11+18h], rbp
0x1800059db  push    rsi
0x1800059dc  push    rdi
0x1800059dd  push    r14
0x1800059df  sub     rsp, 50h
0x1800059e3  mov     r10, [rcx+20h]
0x1800059e7  mov     esi, r9d
0x1800059ea  mov     rdi, r8
0x1800059ed  mov     rbp, rdx
0x1800059f0  test    r10, r10
0x1800059f3  jz      loc_180005AE9
0x1800059f9  mov     r14, [rcx]
0x1800059fc  test    r14, r14
0x1800059ff  jz      loc_180005AE9
0x180005a05  cmp     word ptr [r14], 0
0x180005a0a  jz      loc_180005AE9
0x180005a10  mov     rax, [rcx+28h]
0x180005a14  test    rax, rax
0x180005a17  jz      loc_180005B6C
0x180005a1d  mov     [rsp+68h+arg_0], 0
0x180005a25  mov     [rsp+68h+var_28], r9d
0x180005a2a  mov     [rsp+68h+var_24], 4
0x180005a32  test    r8, r8
0x180005a35  jz      loc_180005B03
0x180005a3b  lea     rcx, [r11-24h]
0x180005a3f  mov     r8, rdx; lpValue
0x180005a42  mov     [r11-38h], rcx
0x180005a46  mov     r9d, 0FFFFh; dwFlags
0x180005a4c  lea     rcx, [r11-28h]
0x180005a50  xor     edx, edx; lpSubKey
0x180005a52  mov     [r11-40h], rcx
0x180005a56  lea     rcx, [r11+8]
0x180005a5a  mov     [r11-48h], rcx
0x180005a5e  mov     rcx, rax; hkey
0x180005a61  call    cs:__imp_RegGetValueW
0x180005a67  mov     ebx, eax
0x180005a69  cmp     eax, 2
0x180005a6c  jnz     short loc_180005AC1
0x180005a6e  mov     rcx, rbp; unsigned __int16 *
0x180005a71  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180005a76  mov     dword ptr [rsp+68h+var_40], ebx
0x180005a7a  lea     rcx, aSTheRegistryKe_3; "%s: The registry key value \"%s@%s\" do"...
0x180005a81  test    eax, eax
0x180005a83  mov     dword ptr [rsp+68h+var_48], esi
0x180005a87  lea     r9, aDefault; "(default)"
0x180005a8e  mov     r8, r14
0x180005a91  cmovz   r9, rbp
0x180005a95  lea     rdx, aRegreaddwordva; "RegReadDwordValue"
0x180005a9c  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180005aa1  xor     ebx, ebx
0x180005aa3  mov     ecx, [rsp+68h+var_28]
0x180005aa7  mov     [rdi], ecx
0x180005aa9  mov     eax, ebx
0x180005aab  mov     rbx, [rsp+68h+arg_8]
0x180005ab0  mov     rbp, [rsp+68h+arg_10]
0x180005ab8  add     rsp, 50h
0x180005abc  pop     r14
0x180005abe  pop     rdi
0x180005abf  pop     rsi
0x180005ac0  retn
0x180005ac1  cmp     ebx, 0EAh
0x180005ac7  jz      short loc_180005AD4
0x180005ac9  test    ebx, ebx
0x180005acb  jnz     short loc_180005B24
0x180005acd  cmp     [rsp+68h+arg_0], 4
0x180005ad2  jz      short loc_180005AA3
0x180005ad4  mov     rcx, rbp; unsigned __int16 *
0x180005ad7  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180005adc  mov     dword ptr [rsp+68h+var_40], ebx
0x180005ae0  lea     rcx, aSTheRegistryKe_10; "%s: The registry key value \"%s@%s\" is"...
0x180005ae7  jmp     short loc_180005A81
0x180005ae9  lea     rdx, aRegistrypathRe_5; "RegistryPath::ReadDwordValue"
0x180005af0  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x180005af7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180005afc  mov     eax, 57h ; 'W'
0x180005b01  jmp     short loc_180005AAB
0x180005b03  lea     r8, aPdata; "pData"
0x180005b0a  lea     rdx, aRegreaddwordva; "RegReadDwordValue"
0x180005b11  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180005b18  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180005b1d  mov     ebx, 57h ; 'W'
0x180005b22  jmp     short loc_180005AA9
0x180005b24  mov     r9, rbp; unsigned __int16 *
0x180005b27  lea     rdx, aReggetvaluew; "RegGetValueW"
0x180005b2e  mov     r8, r14; unsigned __int16 *
0x180005b31  mov     ecx, ebx; unsigned int
0x180005b33  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x180005b38  mov     rcx, rbp; unsigned __int16 *
0x180005b3b  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180005b40  test    eax, eax
0x180005b42  mov     dword ptr [rsp+68h+var_48], ebx
0x180005b46  lea     r9, aDefault; "(default)"
0x180005b4d  mov     r8, r14
0x180005b50  cmovz   r9, rbp
0x180005b54  lea     rdx, aRegreaddwordva; "RegReadDwordValue"
0x180005b5b  lea     rcx, aSCannotReadReg_0; "%s: Cannot read registry key value \"%s"...
0x180005b62  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180005b67  jmp     loc_180005AA3
0x180005b6c  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x180005b71  mov     rdx, rax; unsigned __int16 *
0x180005b74  mov     dword ptr [rsp+68h+var_40], esi; unsigned int
0x180005b78  mov     r9, r14; unsigned __int16 *
0x180005b7b  mov     [rsp+68h+var_48], rdi; unsigned int *
0x180005b80  mov     r8, rbp; unsigned __int16 *
0x180005b83  mov     rcx, r10; HKEY
0x180005b86  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x180005b8b  jmp     loc_180005AAB
```
