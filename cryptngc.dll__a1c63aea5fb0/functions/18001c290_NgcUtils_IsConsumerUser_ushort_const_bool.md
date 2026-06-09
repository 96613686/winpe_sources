# NgcUtils::IsConsumerUser(ushort const *,bool *)

- ea: `0x18001c290`
- end: `0x18001c3bf`
- name: `?IsConsumerUser@NgcUtils@@YAJPEBGPEA_N@Z`
- size: `303`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c218`

## callees

- `0x1800158e0`
- `0x180018430`
- `0x18001c290`
- `0x18002494c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c345`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c345`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001c2da`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001c2da`

## pseudocode

```c
__int64 __fastcall NgcUtils::IsConsumerUser(const WCHAR *this, unsigned __int16 *a2, bool *a3)
{
  BOOL v4; // ebx
  enum NgcUserAccountType *v5; // r8
  signed int LastError; // ebx
  HLOCAL v7; // rcx
  int UserAccountType; // eax
  HLOCAL *p_hMem; // [rsp+30h] [rbp-20h] BYREF
  PSID Sid; // [rsp+38h] [rbp-18h] BYREF
  char v12; // [rsp+40h] [rbp-10h]
  int v13; // [rsp+60h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+20h] BYREF

  if ( !this || !a2 )
    return 2147942487LL;
  *(_BYTE *)a2 = 1;
  p_hMem = &hMem;
  hMem = 0;
  Sid = 0;
  v12 = 1;
  v4 = ConvertStringSidToSidW(this, &Sid);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( v4 )
  {
    v13 = 0;
    UserAccountType = NgcUtils::GetUserAccountType((NgcUtils *)hMem, &v13, v5);
    LastError = UserAccountType;
    if ( UserAccountType >= 0 )
    {
      *(_BYTE *)a2 = (unsigned int)(v13 - 1) <= 1;
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      v13 = UserAccountType;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)byte_180063743,
        0,
        0,
        (__int64)&v13);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v13 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)&word_180063716,
        0,
        0,
        (__int64)&v13);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  v7 = hMem;
  hMem = 0;
  if ( v7 )
    LocalFree(v7);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001c290  mov     [rsp-8+arg_8], rbx
0x18001c295  mov     [rsp-8+arg_18], rdi
0x18001c29a  push    rbp
0x18001c29b  mov     rbp, rsp
0x18001c29e  sub     rsp, 50h
0x18001c2a2  mov     rdi, rdx
0x18001c2a5  test    rcx, rcx
0x18001c2a8  jz      loc_18001C3AA
0x18001c2ae  test    rdx, rdx
0x18001c2b1  jz      loc_18001C3AA
0x18001c2b7  mov     byte ptr [rdx], 1
0x18001c2ba  lea     rax, [rbp+hMem]
0x18001c2be  lea     rdx, [rbp+Sid]; Sid
0x18001c2c2  mov     [rbp+var_20], rax
0x18001c2c6  mov     [rbp+hMem], 0
0x18001c2ce  mov     [rbp+Sid], 0
0x18001c2d6  mov     [rbp+var_10], 1
0x18001c2da  call    cs:__imp_ConvertStringSidToSidW
0x18001c2e0  lea     rcx, [rbp+var_20]
0x18001c2e4  mov     ebx, eax
0x18001c2e6  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001c2eb  test    ebx, ebx
0x18001c2ed  jnz     short loc_18001C34F
0x18001c2ef  call    cs:__imp_GetLastError
0x18001c2f5  mov     ebx, eax
0x18001c2f7  mov     eax, cs:dword_18006E000
0x18001c2fd  cmp     eax, 2
0x18001c300  jbe     short loc_18001C327
0x18001c302  lea     rax, [rbp+arg_0]
0x18001c306  mov     [rbp+arg_0], ebx
0x18001c309  xor     r9d, r9d
0x18001c30c  mov     [rsp+50h+var_30], rax
0x18001c311  xor     r8d, r8d
0x18001c314  lea     rdx, word_180063716
0x18001c31b  lea     rcx, dword_18006E000
0x18001c322  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001c327  test    ebx, ebx
0x18001c329  jle     short loc_18001C334
0x18001c32b  movzx   ebx, bx
0x18001c32e  or      ebx, 80070000h
0x18001c334  mov     rcx, [rbp+hMem]; hMem
0x18001c338  mov     [rbp+hMem], 0
0x18001c340  test    rcx, rcx
0x18001c343  jz      short loc_18001C34B
0x18001c345  call    cs:__imp_LocalFree
0x18001c34b  mov     eax, ebx
0x18001c34d  jmp     short loc_18001C3AF
0x18001c34f  mov     rcx, [rbp+hMem]; this
0x18001c353  lea     rdx, [rbp+arg_0]; void *
0x18001c357  mov     [rbp+arg_0], 0
0x18001c35e  call    ?GetUserAccountType@NgcUtils@@YAJPEAXPEAW4NgcUserAccountType@@@Z; NgcUtils::GetUserAccountType(void *,NgcUserAccountType *)
0x18001c363  mov     ebx, eax
0x18001c365  test    eax, eax
0x18001c367  jns     short loc_18001C39B
0x18001c369  mov     ecx, cs:dword_18006E000
0x18001c36f  cmp     ecx, 2
0x18001c372  jbe     short loc_18001C334
0x18001c374  mov     [rbp+arg_0], eax
0x18001c377  lea     rdx, byte_180063743
0x18001c37e  lea     rax, [rbp+arg_0]
0x18001c382  xor     r9d, r9d
0x18001c385  xor     r8d, r8d
0x18001c388  mov     [rsp+50h+var_30], rax
0x18001c38d  lea     rcx, dword_18006E000
0x18001c394  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001c399  jmp     short loc_18001C334
0x18001c39b  mov     eax, [rbp+arg_0]
0x18001c39e  dec     eax
0x18001c3a0  cmp     eax, 1
0x18001c3a3  setbe   al
0x18001c3a6  mov     [rdi], al
0x18001c3a8  jmp     short loc_18001C334
0x18001c3aa  mov     eax, 80070057h
0x18001c3af  mov     rbx, [rsp+50h+arg_8]
0x18001c3b4  mov     rdi, [rsp+50h+arg_18]
0x18001c3b9  add     rsp, 50h
0x18001c3bd  pop     rbp
0x18001c3be  retn
```
