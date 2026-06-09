# CertPropAssociateSmartCardUserWithCertificateCallback

- ea: `0x1800093c0`
- end: `0x180009549`
- name: `CertPropAssociateSmartCardUserWithCertificateCallback`
- size: `393`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004600`
- `0x1800093c0`
- `0x180009550`
- `0x1800096e8`
- `0x180018bb4`
- `0x180018cb8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800093fe`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800093fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009441`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009498`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009533`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009498`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009533`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009524`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009524`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800093e7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800093e7`

## pseudocode

```c
void __fastcall CertPropAssociateSmartCardUserWithCertificateCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WORK Work)
{
  int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdi
  char LastError; // al
  int v8; // eax
  __int64 v9; // rcx
  char v10; // di
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  LPWSTR *v14; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v15[4]; // [rsp+38h] [rbp-20h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+10h] BYREF
  LPWSTR v17; // [rsp+78h] [rbp+20h] BYREF

  StringSid = 0;
  v4 = 0;
  if ( ConvertSidToStringSidW(*((PSID *)Context + 75), &StringSid) )
  {
    if ( SetThreadToken(0, *((HANDLE *)Context + 52)) )
    {
      v17 = (LPWSTR)*((_QWORD *)Context + 64);
      v4 = 1;
      v14 = &v17;
      if ( !(unsigned int)errcntrctlib::WinApiErrorContract__lambda_a10f23bf905ed032478f824c7550b3ba___(&v14) )
      {
        RevertToSelf();
        v14 = (LPWSTR *)*((_QWORD *)Context + 52);
        v4 = 0;
        v17 = StringSid;
        v15[0] = &v17;
        v15[1] = &v14;
        v8 = errcntrctlib::WinApiErrorContract__lambda_ddfb173e8f53b73a738df8ebe301e581___(v15);
        v10 = v8;
        if ( v8 )
        {
          WppTraceIndent(v9, 2);
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
          {
            WPP_SF_sSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, v13, (__int64)StringSid, v10);
          }
        }
      }
    }
    else
    {
      WppTraceIndent(v5, 2);
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
      {
        v6 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        LastError = GetLastError();
        WPP_SF_sD(v6, 49, (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids, WPP_pszIndent, LastError);
      }
    }
  }
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( v4 )
    RevertToSelf();
}

```

## disassembly

```asm
0x1800093c0  mov     [rsp+arg_0], rbx
0x1800093c5  mov     [rsp+arg_10], rsi
0x1800093ca  push    rdi
0x1800093cb  sub     rsp, 50h
0x1800093cf  mov     rdi, rdx
0x1800093d2  xor     esi, esi
0x1800093d4  lea     rdx, [rsp+58h+StringSid]; StringSid
0x1800093d9  mov     [rsp+58h+StringSid], rsi
0x1800093de  mov     ebx, esi
0x1800093e0  mov     rcx, [rdi+258h]; Sid
0x1800093e7  call    cs:__imp_ConvertSidToStringSidW
0x1800093ed  test    eax, eax
0x1800093ef  jz      loc_18000951A
0x1800093f5  mov     rdx, [rdi+1A0h]; Token
0x1800093fc  xor     ecx, ecx; Thread
0x1800093fe  call    cs:__imp_SetThreadToken
0x180009404  test    eax, eax
0x180009406  jnz     short loc_18000946B
0x180009408  mov     edx, 2
0x18000940d  call    WppTraceIndent
0x180009412  mov     rdi, cs:WPP_GLOBAL_Control
0x180009419  lea     rax, WPP_GLOBAL_Control
0x180009420  cmp     rdi, rax
0x180009423  jz      loc_18000951A
0x180009429  test    byte ptr [rdi+1Ch], 1
0x18000942d  jz      loc_18000951A
0x180009433  cmp     byte ptr [rdi+19h], 3
0x180009437  jb      loc_18000951A
0x18000943d  mov     rdi, [rdi+10h]
0x180009441  call    cs:__imp_GetLastError
0x180009447  mov     r9, cs:WPP_pszIndent
0x18000944e  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180009455  mov     edx, 31h ; '1'
0x18000945a  mov     dword ptr [rsp+58h+var_38], eax
0x18000945e  mov     rcx, rdi
0x180009461  call    WPP_SF_sD
0x180009466  jmp     loc_18000951A
0x18000946b  mov     rax, [rdi+200h]
0x180009472  lea     rcx, [rsp+58h+var_28]
0x180009477  mov     [rsp+58h+arg_18], rax
0x18000947c  mov     ebx, 1
0x180009481  lea     rax, [rsp+58h+arg_18]
0x180009486  mov     [rsp+58h+var_28], rax
0x18000948b  call    errcntrctlib__WinApiErrorContract__lambda_a10f23bf905ed032478f824c7550b3ba___
0x180009490  test    eax, eax
0x180009492  jnz     loc_18000951A
0x180009498  call    cs:__imp_RevertToSelf
0x18000949e  mov     rax, [rdi+1A0h]
0x1800094a5  lea     rcx, [rsp+58h+var_20]
0x1800094aa  mov     [rsp+58h+var_28], rax
0x1800094af  mov     ebx, esi
0x1800094b1  mov     rax, [rsp+58h+StringSid]
0x1800094b6  mov     [rsp+58h+arg_18], rax
0x1800094bb  lea     rax, [rsp+58h+arg_18]
0x1800094c0  mov     [rsp+58h+var_20], rax
0x1800094c5  lea     rax, [rsp+58h+var_28]
0x1800094ca  mov     [rsp+58h+var_18], rax
0x1800094cf  call    errcntrctlib__WinApiErrorContract__lambda_ddfb173e8f53b73a738df8ebe301e581___
0x1800094d4  mov     edi, eax
0x1800094d6  test    eax, eax
0x1800094d8  jz      short loc_18000951A
0x1800094da  mov     edx, 2
0x1800094df  call    WppTraceIndent
0x1800094e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094eb  lea     rax, WPP_GLOBAL_Control
0x1800094f2  cmp     rcx, rax
0x1800094f5  jz      short loc_18000951A
0x1800094f7  test    byte ptr [rcx+1Ch], 1
0x1800094fb  jz      short loc_18000951A
0x1800094fd  cmp     byte ptr [rcx+19h], 3
0x180009501  jb      short loc_18000951A
0x180009503  mov     rax, [rsp+58h+StringSid]
0x180009508  mov     rcx, [rcx+10h]
0x18000950c  mov     [rsp+58h+var_30], edi
0x180009510  mov     [rsp+58h+var_38], rax
0x180009515  call    WPP_SF_sSD
0x18000951a  mov     rcx, [rsp+58h+StringSid]; hMem
0x18000951f  test    rcx, rcx
0x180009522  jz      short loc_18000952F
0x180009524  call    cs:__imp_LocalFree
0x18000952a  mov     [rsp+58h+StringSid], rsi
0x18000952f  test    ebx, ebx
0x180009531  jz      short loc_180009539
0x180009533  call    cs:__imp_RevertToSelf
0x180009539  mov     rbx, [rsp+58h+arg_0]
0x18000953e  mov     rsi, [rsp+58h+arg_10]
0x180009543  add     rsp, 50h
0x180009547  pop     rdi
0x180009548  retn
```
