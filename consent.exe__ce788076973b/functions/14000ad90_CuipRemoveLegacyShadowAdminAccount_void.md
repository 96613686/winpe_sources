# CuipRemoveLegacyShadowAdminAccount(void *)

- ea: `0x14000ad90`
- end: `0x14000af0c`
- name: `?CuipRemoveLegacyShadowAdminAccount@@YAXPEAX@Z`
- size: `380`
- prototype: `void __fastcall(HANDLE hToken)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d690`

## callees

- `0x14000ad90`
- `0x140010ad3`
- `0x140014ab8`
- `0x14001e050`

## import_xrefs

- `msvcrt!wcsrchr` at `0x14000ae45`
- `msvcrt!wcsrchr` at `0x14000ae45`
- `msvcrt!wcsncpy_s` at `0x14000ae9d`
- `msvcrt!wcsncpy_s` at `0x14000ae9d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14000adf0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14000adf0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000ae15`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000ae20`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000ae15`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000ae20`
- `SspiCli!GetUserNameExW` at `0x14000ae0b`
- `SspiCli!GetUserNameExW` at `0x14000ae0b`
- `samcli!NetUserDel` at `0x14000aed2`
- `samcli!NetUserDel` at `0x14000aed2`
- `samcli!NetUserGetInfo` at `0x14000aeb5`
- `samcli!NetUserGetInfo` at `0x14000aeb5`
- `netutils!NetApiBufferFree` at `0x14000aee2`
- `netutils!NetApiBufferFree` at `0x14000aee2`

## pseudocode

```c
void __fastcall CuipRemoveLegacyShadowAdminAccount(HANDLE hToken)
{
  wchar_t *v2; // rax
  WCHAR *v3; // rbx
  unsigned __int64 v4; // rax
  rsize_t v5; // r9
  ULONG nSize; // [rsp+20h] [rbp-E0h] BYREF
  LPBYTE bufptr; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t Source[8]; // [rsp+30h] [rbp-D0h] BYREF
  int v9; // [rsp+40h] [rbp-C0h]
  WCHAR NameBuffer[520]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(NameBuffer, 0, 0x404u);
  nSize = 514;
  v9 = 0;
  *(_OWORD *)Source = 0;
  bufptr = 0;
  if ( ImpersonateLoggedOnUser(hToken) )
  {
    if ( GetUserNameExW(NameSamCompatible, NameBuffer, &nSize) )
    {
      RevertToSelf();
      if ( !(unsigned int)CuipGetShadowAdminAccountSuffix(NameBuffer, Source) )
      {
        v2 = wcsrchr(NameBuffer, 0x5Cu);
        if ( v2 )
          v3 = v2 + 1;
        else
          v3 = NameBuffer;
        v4 = -1;
        v5 = -1;
        do
          ++v5;
        while ( Source[v5] );
        do
          ++v4;
        while ( v3[v4] );
        if ( v4 > 20 - v5 )
          v4 = 20 - v5;
        if ( !wcsncpy_s(&v3[v4], 21 - v4, Source, v5)
          && !NetUserGetInfo(0, v3, 1u, &bufptr)
          && (*((_DWORD *)bufptr + 10) & 0x4000) != 0 )
        {
          NetUserDel(0, v3);
        }
      }
    }
    else
    {
      RevertToSelf();
    }
  }
  if ( bufptr )
    NetApiBufferFree(bufptr);
}

```

## disassembly

```asm
0x14000ad90  mov     [rsp-8+arg_8], rbx
0x14000ad95  mov     [rsp-8+arg_10], rdi
0x14000ad9a  push    rbp
0x14000ad9b  lea     rbp, [rsp-370h]
0x14000ada3  sub     rsp, 470h
0x14000adaa  mov     rax, cs:__security_cookie
0x14000adb1  xor     rax, rsp
0x14000adb4  mov     [rbp+370h+var_10], rax
0x14000adbb  mov     rbx, rcx
0x14000adbe  xor     edx, edx; Val
0x14000adc0  lea     rcx, [rsp+470h+NameBuffer]; void *
0x14000adc5  mov     r8d, 404h; Size
0x14000adcb  call    memset_0
0x14000add0  xorps   xmm0, xmm0
0x14000add3  mov     [rsp+470h+nSize], 202h
0x14000addb  xor     eax, eax
0x14000addd  xor     edi, edi
0x14000addf  mov     rcx, rbx; hToken
0x14000ade2  mov     [rsp+470h+var_430], eax
0x14000ade6  movups  xmmword ptr [rsp+470h+Source], xmm0
0x14000adeb  mov     [rsp+470h+bufptr], rdi
0x14000adf0  call    cs:__imp_ImpersonateLoggedOnUser
0x14000adf6  test    eax, eax
0x14000adf8  jz      loc_14000AED8
0x14000adfe  lea     r8, [rsp+470h+nSize]; nSize
0x14000ae03  lea     rdx, [rsp+470h+NameBuffer]; lpNameBuffer
0x14000ae08  lea     ecx, [rdi+2]; NameFormat
0x14000ae0b  call    cs:__imp_GetUserNameExW
0x14000ae11  test    al, al
0x14000ae13  jnz     short loc_14000AE20
0x14000ae15  call    cs:__imp_RevertToSelf
0x14000ae1b  jmp     loc_14000AED8
0x14000ae20  call    cs:__imp_RevertToSelf
0x14000ae26  lea     rdx, [rsp+470h+Source]; Destination
0x14000ae2b  lea     rcx, [rsp+470h+NameBuffer]; lpAccountName
0x14000ae30  call    ?CuipGetShadowAdminAccountSuffix@@YAKPEBGPEAG@Z; CuipGetShadowAdminAccountSuffix(ushort const *,ushort *)
0x14000ae35  test    eax, eax
0x14000ae37  jnz     loc_14000AED8
0x14000ae3d  lea     edx, [rax+5Ch]; Ch
0x14000ae40  lea     rcx, [rsp+470h+NameBuffer]; Str
0x14000ae45  call    cs:__imp_wcsrchr
0x14000ae4b  mov     rbx, rax
0x14000ae4e  test    rax, rax
0x14000ae51  jnz     short loc_14000AE5A
0x14000ae53  lea     rbx, [rsp+470h+NameBuffer]
0x14000ae58  jmp     short loc_14000AE5E
0x14000ae5a  add     rbx, 2
0x14000ae5e  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000ae62  lea     rcx, [rsp+470h+Source]
0x14000ae67  mov     r9, rax
0x14000ae6a  inc     r9; MaxCount
0x14000ae6d  cmp     [rcx+r9*2], di
0x14000ae72  jnz     short loc_14000AE6A
0x14000ae74  mov     ecx, 14h
0x14000ae79  sub     rcx, r9
0x14000ae7c  inc     rax
0x14000ae7f  cmp     [rbx+rax*2], di
0x14000ae83  jnz     short loc_14000AE7C
0x14000ae85  cmp     rax, rcx
0x14000ae88  lea     r8, [rsp+470h+Source]; Source
0x14000ae8d  mov     edx, 15h
0x14000ae92  cmova   rax, rcx
0x14000ae96  sub     rdx, rax; SizeInWords
0x14000ae99  lea     rcx, [rbx+rax*2]; Destination
0x14000ae9d  call    cs:__imp_wcsncpy_s
0x14000aea3  test    eax, eax
0x14000aea5  jnz     short loc_14000AED8
0x14000aea7  lea     r9, [rsp+470h+bufptr]; bufptr
0x14000aeac  mov     rdx, rbx; username
0x14000aeaf  lea     r8d, [rax+1]; level
0x14000aeb3  xor     ecx, ecx; servername
0x14000aeb5  call    cs:__imp_NetUserGetInfo
0x14000aebb  test    eax, eax
0x14000aebd  jnz     short loc_14000AED8
0x14000aebf  mov     rax, [rsp+470h+bufptr]
0x14000aec4  test    dword ptr [rax+28h], 4000h
0x14000aecb  jz      short loc_14000AED8
0x14000aecd  mov     rdx, rbx; username
0x14000aed0  xor     ecx, ecx; servername
0x14000aed2  call    cs:__imp_NetUserDel
0x14000aed8  mov     rcx, [rsp+470h+bufptr]; Buffer
0x14000aedd  test    rcx, rcx
0x14000aee0  jz      short loc_14000AEE8
0x14000aee2  call    cs:__imp_NetApiBufferFree
0x14000aee8  mov     rcx, [rbp+370h+var_10]
0x14000aeef  xor     rcx, rsp; StackCookie
0x14000aef2  call    __security_check_cookie
0x14000aef7  lea     r11, [rsp+470h+var_s0]
0x14000aeff  mov     rbx, [r11+18h]
0x14000af03  mov     rdi, [r11+20h]
0x14000af07  mov     rsp, r11
0x14000af0a  pop     rbp
0x14000af0b  retn
```
