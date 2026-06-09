# EVENT_LOG::SidToUser(void *,ushort *,unsigned __int64)

- ea: `0x1800717e0`
- end: `0x180071984`
- name: `?SidToUser@EVENT_LOG@@SAJPEAXPEAG_K@Z`
- size: `420`
- prototype: `__int64 __fastcall(PSID Sid, LPWSTR lpBuffer, unsigned __int64)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180071484`
- `0x180071630`
- `0x1800b4f7c`
- `0x1800b5410`
- `0x1800b567c`
- `0x1800b5b34`
- `0x1800b6114`
- `0x1800b65dc`
- `0x1800b6b40`

## callees

- `0x1800717e0`
- `0x180099074`
- `0x18009e9c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007182a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800718f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007182a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800718f6`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180071824`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800718ec`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180071824`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800718ec`

## pseudocode

```c
__int64 __fastcall EVENT_LOG::SidToUser(PSID Sid, LPWSTR lpBuffer, __int64 a3)
{
  unsigned __int64 v5; // rdx
  DWORD LastError; // edi
  DWORD v8; // ebx
  __int64 v9; // rax
  enum _SID_NAME_USE peUse[6]; // [rsp+30h] [rbp-18h] BYREF
  DWORD cchName; // [rsp+60h] [rbp+18h] BYREF
  int v13; // [rsp+64h] [rbp+1Ch]
  DWORD cchReferencedDomainName; // [rsp+68h] [rbp+20h] BYREF

  v13 = HIDWORD(a3);
  *lpBuffer = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse[0] = 0;
  LookupAccountSidLocalW(Sid, 0, &cchName, 0, &cchReferencedDomainName, peUse);
  LastError = GetLastError();
  if ( LastError == 1332 )
    return EVENT_LOG::GetUnknownUserName(lpBuffer, v5);
  if ( LastError == 122 )
  {
    if ( cchReferencedDomainName + cchName <= 0xC8 )
    {
      cchName = 200 - cchReferencedDomainName;
      if ( LookupAccountSidLocalW(
             Sid,
             &lpBuffer[cchReferencedDomainName],
             &cchName,
             lpBuffer,
             &cchReferencedDomainName,
             peUse) )
      {
        v9 = -1;
        while ( lpBuffer[++v9] != 0 )
          ;
        lpBuffer[v9] = 92;
        return 0;
      }
      else
      {
        v8 = GetLastError();
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids, v8);
        if ( (int)v8 > 0 )
          return (unsigned __int16)v8 | 0x80070000;
        return v8;
      }
    }
    else
    {
      return 2147942522LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids, LastError);
    if ( (int)LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return LastError;
  }
}

```

## disassembly

```asm
0x1800717e0  mov     r11, rsp
0x1800717e3  mov     [r11+8], rbx
0x1800717e7  mov     [r11+10h], rsi
0x1800717eb  mov     [r11+18h], r8
0x1800717ef  push    rdi
0x1800717f0  sub     rsp, 40h
0x1800717f4  xor     eax, eax
0x1800717f6  lea     r8, [r11+18h]; cchName
0x1800717fa  mov     [rdx], ax
0x1800717fd  mov     rbx, rdx
0x180071800  mov     [rsp+48h+cchName], eax
0x180071804  xor     r9d, r9d; ReferencedDomainName
0x180071807  mov     [rsp+48h+arg_18], eax
0x18007180b  xor     edx, edx; Name
0x18007180d  mov     [rsp+48h+var_18], eax
0x180071811  mov     rsi, rcx
0x180071814  lea     rax, [r11-18h]
0x180071818  mov     [r11-20h], rax
0x18007181c  lea     rax, [r11+20h]
0x180071820  mov     [r11-28h], rax
0x180071824  call    cs:__imp_LookupAccountSidLocalW
0x18007182a  call    cs:__imp_GetLastError
0x180071830  mov     edi, eax
0x180071832  cmp     eax, 534h
0x180071837  jnz     short loc_180071851
0x180071839  mov     rcx, rbx; lpBuffer
0x18007183c  call    ?GetUnknownUserName@EVENT_LOG@@SAJPEAG_K@Z; EVENT_LOG::GetUnknownUserName(ushort *,unsigned __int64)
0x180071841  mov     rbx, [rsp+48h+arg_0]
0x180071846  mov     rsi, [rsp+48h+arg_8]
0x18007184b  add     rsp, 40h
0x18007184f  pop     rdi
0x180071850  retn
0x180071851  cmp     edi, 7Ah ; 'z'
0x180071854  jz      short loc_1800718A6
0x180071856  mov     rcx, cs:WPP_GLOBAL_Control
0x18007185d  lea     rax, WPP_GLOBAL_Control
0x180071864  cmp     rcx, rax
0x180071867  jz      short loc_180071887
0x180071869  test    byte ptr [rcx+1Ch], 4
0x18007186d  jz      short loc_180071887
0x18007186f  mov     rcx, [rcx+10h]
0x180071873  lea     r8, WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids
0x18007187a  mov     edx, 11h
0x18007187f  mov     r9d, edi
0x180071882  call    WPP_SF_d
0x180071887  test    edi, edi
0x180071889  jle     short loc_180071894
0x18007188b  movzx   edi, di
0x18007188e  or      edi, 80070000h
0x180071894  mov     eax, edi
0x180071896  mov     rbx, [rsp+48h+arg_0]
0x18007189b  mov     rsi, [rsp+48h+arg_8]
0x1800718a0  add     rsp, 40h
0x1800718a4  pop     rdi
0x1800718a5  retn
0x1800718a6  mov     edx, [rsp+48h+arg_18]
0x1800718aa  mov     eax, 0C8h
0x1800718af  mov     ecx, [rsp+48h+cchName]
0x1800718b3  add     ecx, edx
0x1800718b5  cmp     ecx, eax
0x1800718b7  jbe     short loc_1800718C3
0x1800718b9  mov     eax, 8007007Ah
0x1800718be  jmp     loc_180071974
0x1800718c3  sub     eax, edx
0x1800718c5  lea     r8, [rsp+48h+cchName]; cchName
0x1800718ca  mov     [rsp+48h+cchName], eax
0x1800718ce  lea     rdx, [rbx+rdx*2]; Name
0x1800718d2  lea     rax, [rsp+48h+var_18]
0x1800718d7  mov     r9, rbx; ReferencedDomainName
0x1800718da  mov     [rsp+48h+peUse], rax; peUse
0x1800718df  mov     rcx, rsi; Sid
0x1800718e2  lea     rax, [rsp+48h+arg_18]
0x1800718e7  mov     [rsp+48h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800718ec  call    cs:__imp_LookupAccountSidLocalW
0x1800718f2  test    eax, eax
0x1800718f4  jnz     short loc_18007194E
0x1800718f6  call    cs:__imp_GetLastError
0x1800718fc  mov     ebx, eax
0x1800718fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180071905  lea     rax, WPP_GLOBAL_Control
0x18007190c  cmp     rcx, rax
0x18007190f  jz      short loc_18007192F
0x180071911  test    byte ptr [rcx+1Ch], 4
0x180071915  jz      short loc_18007192F
0x180071917  mov     rcx, [rcx+10h]
0x18007191b  lea     r8, WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids
0x180071922  mov     edx, 12h
0x180071927  mov     r9d, ebx
0x18007192a  call    WPP_SF_d
0x18007192f  test    ebx, ebx
0x180071931  jle     short loc_18007193C
0x180071933  movzx   ebx, bx
0x180071936  or      ebx, 80070000h
0x18007193c  mov     eax, ebx
0x18007193e  mov     rbx, [rsp+48h+arg_0]
0x180071943  mov     rsi, [rsp+48h+arg_8]
0x180071948  add     rsp, 40h
0x18007194c  pop     rdi
0x18007194d  retn
0x18007194e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180071955  nop     word ptr [rax+rax+00000000h]
0x180071960  cmp     word ptr [rbx+rax*2+2], 0
0x180071966  lea     rax, [rax+1]
0x18007196a  jnz     short loc_180071960
0x18007196c  mov     word ptr [rbx+rax*2], 5Ch ; '\'
0x180071972  xor     eax, eax
0x180071974  mov     rbx, [rsp+48h+arg_0]
0x180071979  mov     rsi, [rsp+48h+arg_8]
0x18007197e  add     rsp, 40h
0x180071982  pop     rdi
0x180071983  retn
```
