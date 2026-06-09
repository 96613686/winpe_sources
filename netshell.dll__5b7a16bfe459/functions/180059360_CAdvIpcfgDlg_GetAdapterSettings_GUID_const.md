# CAdvIpcfgDlg::GetAdapterSettings(_GUID const &)

- ea: `0x180059360`
- end: `0x1800594d5`
- name: `?GetAdapterSettings@CAdvIpcfgDlg@@AEAAJAEBU_GUID@@@Z`
- size: `373`
- prototype: `int(CAdvIpcfgDlg *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18005a72c`

## callees

- `0x18001e1e0`
- `0x180059360`
- `0x1800620f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800593d0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800593d0`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180059438`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180059438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800593dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800593dc`
- `ole32!CoTaskMemFree` at `0x18005938e`
- `ole32!CoTaskMemFree` at `0x18005946b`
- `ole32!CoTaskMemFree` at `0x18005938e`
- `ole32!CoTaskMemFree` at `0x18005946b`
- `ole32!StringFromGUID2` at `0x1800593ba`
- `ole32!StringFromGUID2` at `0x1800593ba`
- `ole32!CoTaskMemRealloc` at `0x180059415`
- `ole32!CoTaskMemRealloc` at `0x180059415`

## pseudocode

```c
__int64 __fastcall CAdvIpcfgDlg::GetAdapterSettings(LPVOID *this, const struct _GUID *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  signed int i; // eax
  IP_ADAPTER_ADDRESSES_LH *v7; // rax
  const char **v8; // rbx
  unsigned int v9; // esi
  bool v10; // sf
  __int64 result; // rax
  SIZE_T cb; // [rsp+30h] [rbp-98h] BYREF
  char Str1[40]; // [rsp+38h] [rbp-90h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-68h] BYREF

  CoTaskMemFree(this[11]);
  this[11] = 0;
  this[12] = 0;
  LODWORD(cb) = 0;
  StringFromGUID2(a2, sz, 39);
  if ( _o_wcstombs(Str1, sz, 39) == -1 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_14:
    CoTaskMemFree(this[11]);
    result = v5;
    this[11] = 0;
    this[12] = 0;
  }
  else
  {
    for ( i = GetAdaptersAddresses(0, 0xD6u, 0, (PIP_ADAPTER_ADDRESSES)this[11], (PULONG)&cb);
          ;
          i = GetAdaptersAddresses(0, 0xD6u, 0, v7, (PULONG)&cb) )
    {
      v5 = i;
      if ( !i )
        break;
      if ( i != 111 )
      {
        v10 = i < 0;
        if ( i > 0 )
        {
          v5 = (unsigned __int16)i | 0x80070000;
          v10 = 1;
        }
        if ( v10 )
          goto LABEL_14;
        break;
      }
      v7 = (IP_ADAPTER_ADDRESSES_LH *)CoTaskMemRealloc(this[11], (unsigned int)cb);
      this[11] = v7;
      if ( !v7 )
      {
        v5 = -2147024882;
        goto LABEL_14;
      }
    }
    v8 = (const char **)this[11];
    v9 = -2147024894;
    while ( v8 )
    {
      if ( !strncmp_0(Str1, v8[2], 0x27u) )
      {
        this[12] = v8;
        return 0;
      }
      v8 = (const char **)v8[1];
    }
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180059360  mov     [rsp+arg_10], rbx
0x180059365  mov     [rsp+arg_18], rsi
0x18005936a  push    rdi
0x18005936b  sub     rsp, 0C0h
0x180059372  mov     rax, cs:__security_cookie
0x180059379  xor     rax, rsp
0x18005937c  mov     [rsp+0C8h+var_18], rax
0x180059384  mov     rdi, rcx
0x180059387  mov     rbx, rdx
0x18005938a  mov     rcx, [rcx+58h]; pv
0x18005938e  call    cs:__imp_CoTaskMemFree
0x180059394  mov     r8d, 27h ; '''; cchMax
0x18005939a  mov     qword ptr [rdi+58h], 0
0x1800593a2  lea     rdx, [rsp+0C8h+sz]; lpsz
0x1800593a7  mov     qword ptr [rdi+60h], 0
0x1800593af  mov     rcx, rbx; rguid
0x1800593b2  mov     dword ptr [rsp+0C8h+cb], 0
0x1800593ba  call    cs:__imp_StringFromGUID2
0x1800593c0  mov     r8d, 27h ; '''
0x1800593c6  lea     rdx, [rsp+0C8h+sz]
0x1800593cb  lea     rcx, [rsp+0C8h+Str1]
0x1800593d0  call    cs:__imp__o_wcstombs
0x1800593d6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800593da  jnz     short loc_1800593F3
0x1800593dc  call    cs:__imp_GetLastError
0x1800593e2  mov     ebx, eax
0x1800593e4  test    eax, eax
0x1800593e6  jle     short loc_180059467
0x1800593e8  movzx   ebx, ax
0x1800593eb  or      ebx, 80070000h
0x1800593f1  jmp     short loc_180059467
0x1800593f3  mov     r9, [rdi+58h]
0x1800593f7  lea     rax, [rsp+0C8h+cb]
0x1800593fc  mov     [rsp+0C8h+SizePointer], rax
0x180059401  mov     esi, 0D6h
0x180059406  jmp     short loc_180059431
0x180059408  cmp     ebx, 6Fh ; 'o'
0x18005940b  jnz     short loc_180059456
0x18005940d  mov     edx, dword ptr [rsp+0C8h+cb]; cb
0x180059411  mov     rcx, [rdi+58h]; pv
0x180059415  call    cs:__imp_CoTaskMemRealloc
0x18005941b  mov     [rdi+58h], rax
0x18005941f  test    rax, rax
0x180059422  jz      short loc_18005944F
0x180059424  lea     rcx, [rsp+0C8h+cb]
0x180059429  mov     r9, rax; AdapterAddresses
0x18005942c  mov     [rsp+0C8h+SizePointer], rcx; SizePointer
0x180059431  xor     r8d, r8d; Reserved
0x180059434  mov     edx, esi; Flags
0x180059436  xor     ecx, ecx; Family
0x180059438  call    cs:__imp_GetAdaptersAddresses
0x18005943e  mov     ebx, eax
0x180059440  test    eax, eax
0x180059442  jnz     short loc_180059408
0x180059444  mov     rbx, [rdi+58h]
0x180059448  mov     esi, 80070002h
0x18005944d  jmp     short loc_1800594A1
0x18005944f  mov     ebx, 8007000Eh
0x180059454  jmp     short loc_180059467
0x180059456  test    ebx, ebx
0x180059458  jle     short loc_180059465
0x18005945a  movzx   ebx, bx
0x18005945d  or      ebx, 80070000h
0x180059463  test    ebx, ebx
0x180059465  jns     short loc_180059444
0x180059467  mov     rcx, [rdi+58h]; pv
0x18005946b  call    cs:__imp_CoTaskMemFree
0x180059471  mov     eax, ebx
0x180059473  mov     qword ptr [rdi+58h], 0
0x18005947b  mov     qword ptr [rdi+60h], 0
0x180059483  jmp     short loc_1800594B0
0x180059485  mov     rdx, [rbx+10h]; Str2
0x180059489  lea     rcx, [rsp+0C8h+Str1]; Str1
0x18005948e  mov     r8d, 27h ; '''; MaxCount
0x180059494  call    strncmp_0
0x180059499  test    eax, eax
0x18005949b  jz      short loc_1800594A8
0x18005949d  mov     rbx, [rbx+8]
0x1800594a1  test    rbx, rbx
0x1800594a4  jnz     short loc_180059485
0x1800594a6  jmp     short loc_1800594AE
0x1800594a8  mov     [rdi+60h], rbx
0x1800594ac  xor     esi, esi
0x1800594ae  mov     eax, esi
0x1800594b0  mov     rcx, [rsp+0C8h+var_18]
0x1800594b8  xor     rcx, rsp; StackCookie
0x1800594bb  call    __security_check_cookie
0x1800594c0  lea     r11, [rsp+0C8h+var_8]
0x1800594c8  mov     rbx, [r11+20h]
0x1800594cc  mov     rsi, [r11+28h]
0x1800594d0  mov     rsp, r11
0x1800594d3  pop     rdi
0x1800594d4  retn
```
