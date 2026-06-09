# NlpResyncDpapiForLogon(_LUID *,DpapiResyncType)

- ea: `0x18000cf88`
- end: `0x18000d1aa`
- name: `?NlpResyncDpapiForLogon@@YAXPEAU_LUID@@W4DpapiResyncType@@@Z`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b3b0`

## callees

- `0x18000cf88`
- `0x18002ee7c`
- `0x18002f014`
- `0x18002fb50`
- `0x180040bac`
- `0x18006d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d176`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0c3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d098`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d098`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d185`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d185`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d16c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d16c`
- `LSASRV!LsaICryptProtectData` at `0x18000d12d`
- `LSASRV!LsaICryptProtectData` at `0x18000d12d`

## pseudocode

```c
int __fastcall NlpResyncDpapiForLogon(_DWORD *a1, unsigned int a2, __int64 a3)
{
  int v3; // esi
  _UNKNOWN **v5; // rax
  int v6; // ebx
  int v7; // r8d
  DWORD LastError; // eax
  HANDLE Token; // [rsp+50h] [rbp+7h] BYREF
  _QWORD v11[2]; // [rsp+58h] [rbp+Fh] BYREF
  HLOCAL hMem[2]; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v13; // [rsp+78h] [rbp+2Fh] BYREF

  v3 = 0;
  v13 = 0;
  v11[0] = 917516;
  Token = 0;
  v11[1] = L"Resync";
  *(_OWORD *)hMem = 0;
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      v5 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        LODWORD(v5) = WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        54,
                        WPP_905305d962583d6f838b30057de84013_Traceguids,
                        a2);
      goto LABEL_20;
    }
    v6 = 0x4000000;
  }
  else
  {
    v6 = 8;
  }
  v7 = ((__int64 (__fastcall *)(_DWORD *, HANDLE *, __int64, _QWORD))LsaFunctions->OpenTokenByLogonId)(
         a1,
         &Token,
         a3,
         a2);
  if ( v7 >= 0 )
  {
    if ( SetThreadToken(0, Token) )
    {
      v3 = 1;
      LODWORD(v5) = LsaICryptProtectData(&v13, 8, v11, 0, 0, 0, 0, v6, &hMem[1], hMem);
      if ( !(_BYTE)v5 )
      {
        v5 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          LODWORD(v5) = WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          57,
                          WPP_905305d962583d6f838b30057de84013_Traceguids);
      }
    }
    else
    {
      v5 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        LODWORD(v5) = WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        56,
                        WPP_905305d962583d6f838b30057de84013_Traceguids,
                        LastError);
      }
    }
  }
  else
  {
    v5 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      LODWORD(v5) = WPP_SF_DDd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      55,
                      WPP_905305d962583d6f838b30057de84013_Traceguids,
                      (unsigned int)a1[1],
                      *a1,
                      v7);
  }
LABEL_20:
  if ( hMem[1] )
    LODWORD(v5) = (unsigned int)LocalFree(hMem[1]);
  if ( v3 )
    LODWORD(v5) = RevertToSelf();
  if ( Token )
    LODWORD(v5) = CloseHandle(Token);
  return (int)v5;
}

```

## disassembly

```asm
0x18000cf88  mov     [rsp-8+arg_10], rbx
0x18000cf8d  push    rbp
0x18000cf8e  push    rsi
0x18000cf8f  push    rdi
0x18000cf90  lea     rbp, [rsp-47h]
0x18000cf95  sub     rsp, 90h
0x18000cf9c  mov     rax, cs:__security_cookie
0x18000cfa3  xor     rax, rsp
0x18000cfa6  mov     [rbp+57h+var_20], rax
0x18000cfaa  xor     esi, esi
0x18000cfac  mov     [rbp+57h+var_28], 0
0x18000cfb4  mov     [rbp+57h+var_48], 0E000Ch
0x18000cfbc  xorps   xmm0, xmm0
0x18000cfbf  mov     [rbp+57h+Token], 0
0x18000cfc7  lea     rax, aResync; "Resync"
0x18000cfce  mov     [rbp+57h+var_40], rax
0x18000cfd2  mov     r9d, edx
0x18000cfd5  mov     rdi, rcx
0x18000cfd8  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x18000cfdc  test    edx, edx
0x18000cfde  jz      short loc_18000D025
0x18000cfe0  cmp     edx, 1
0x18000cfe3  jz      short loc_18000D01E
0x18000cfe5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfec  lea     rax, WPP_GLOBAL_Control
0x18000cff3  cmp     rcx, rax
0x18000cff6  jz      loc_18000D163
0x18000cffc  test    byte ptr [rcx+1Ch], 1
0x18000d000  jz      loc_18000D163
0x18000d006  mov     rcx, [rcx+10h]
0x18000d00a  lea     edx, [rsi+36h]
0x18000d00d  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x18000d014  call    WPP_SF_d
0x18000d019  jmp     loc_18000D163
0x18000d01e  mov     ebx, 4000000h
0x18000d023  jmp     short loc_18000D02A
0x18000d025  mov     ebx, 8
0x18000d02a  mov     rax, cs:LsaFunctions
0x18000d031  lea     rdx, [rbp+57h+Token]
0x18000d035  mov     rax, [rax+170h]
0x18000d03c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d041  mov     r8d, eax
0x18000d044  test    eax, eax
0x18000d046  jns     short loc_18000D092
0x18000d048  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d04f  lea     rax, WPP_GLOBAL_Control
0x18000d056  cmp     rcx, rax
0x18000d059  jz      loc_18000D163
0x18000d05f  test    byte ptr [rcx+1Ch], 1
0x18000d063  jz      loc_18000D163
0x18000d069  mov     eax, [rdi]
0x18000d06b  mov     edx, 37h ; '7'
0x18000d070  mov     r9d, [rdi+4]
0x18000d074  mov     rcx, [rcx+10h]
0x18000d078  mov     dword ptr [rsp+0A0h+var_78], r8d
0x18000d07d  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x18000d084  mov     [rsp+0A0h+var_80], eax
0x18000d088  call    WPP_SF_DDd
0x18000d08d  jmp     loc_18000D163
0x18000d092  mov     rdx, [rbp+57h+Token]; Token
0x18000d096  xor     ecx, ecx; Thread
0x18000d098  call    cs:__imp_SetThreadToken
0x18000d09e  test    eax, eax
0x18000d0a0  jnz     short loc_18000D0EA
0x18000d0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0a9  lea     rax, WPP_GLOBAL_Control
0x18000d0b0  cmp     rcx, rax
0x18000d0b3  jz      loc_18000D163
0x18000d0b9  test    byte ptr [rcx+1Ch], 1
0x18000d0bd  jz      loc_18000D163
0x18000d0c3  call    cs:__imp_GetLastError
0x18000d0c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0d0  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x18000d0d7  mov     edx, 38h ; '8'
0x18000d0dc  mov     r9d, eax
0x18000d0df  mov     rcx, [rcx+10h]
0x18000d0e3  call    WPP_SF_d
0x18000d0e8  jmp     short loc_18000D163
0x18000d0ea  lea     rax, [rbp+57h+hMem]
0x18000d0ee  mov     esi, 1
0x18000d0f3  mov     [rsp+0A0h+var_58], rax
0x18000d0f8  lea     r8, [rbp+57h+var_48]
0x18000d0fc  lea     rax, [rbp+57h+hMem+8]
0x18000d100  xor     r9d, r9d
0x18000d103  mov     [rsp+0A0h+var_60], rax
0x18000d108  lea     rcx, [rbp+57h+var_28]
0x18000d10c  mov     [rsp+0A0h+var_68], ebx
0x18000d110  lea     edx, [rsi+7]
0x18000d113  mov     [rsp+0A0h+var_70], 0
0x18000d11c  mov     [rsp+0A0h+var_78], 0
0x18000d125  mov     [rsp+0A0h+var_80], 0
0x18000d12d  call    cs:__imp_LsaICryptProtectData
0x18000d133  test    al, al
0x18000d135  jnz     short loc_18000D163
0x18000d137  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d13e  lea     rax, WPP_GLOBAL_Control
0x18000d145  cmp     rcx, rax
0x18000d148  jz      short loc_18000D163
0x18000d14a  test    byte ptr [rcx+1Ch], 2
0x18000d14e  jz      short loc_18000D163
0x18000d150  mov     rcx, [rcx+10h]
0x18000d154  lea     edx, [rsi+38h]
0x18000d157  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x18000d15e  call    WPP_SF_
0x18000d163  mov     rcx, [rbp+57h+hMem+8]; hMem
0x18000d167  test    rcx, rcx
0x18000d16a  jz      short loc_18000D172
0x18000d16c  call    cs:__imp_LocalFree
0x18000d172  test    esi, esi
0x18000d174  jz      short loc_18000D17C
0x18000d176  call    cs:__imp_RevertToSelf
0x18000d17c  mov     rcx, [rbp+57h+Token]; hObject
0x18000d180  test    rcx, rcx
0x18000d183  jz      short loc_18000D18B
0x18000d185  call    cs:__imp_CloseHandle
0x18000d18b  mov     rcx, [rbp+57h+var_20]
0x18000d18f  xor     rcx, rsp; StackCookie
0x18000d192  call    __security_check_cookie
0x18000d197  mov     rbx, [rsp+0A0h+arg_10]
0x18000d19f  add     rsp, 90h
0x18000d1a6  pop     rdi
0x18000d1a7  pop     rsi
0x18000d1a8  pop     rbp
0x18000d1a9  retn
```
