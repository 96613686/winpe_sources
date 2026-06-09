# Ncsi::Proxy::Detector::InitializeWinHttp(bool,void * &)

- ea: `0x18002af04`
- end: `0x18002b071`
- name: `?InitializeWinHttp@Detector@Proxy@Ncsi@@SAK_NAEAPEAX@Z`
- size: `365`
- prototype: `unsigned int __fastcall(bool, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800305b0`

## callees

- `0x180010200`
- `0x180011a58`
- `0x18002af04`
- `0x180047240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b010`
- `WINHTTP!WinHttpOpen` at `0x18002af6e`
- `WINHTTP!WinHttpOpen` at `0x18002af6e`
- `WINHTTP!WinHttpResetAutoProxy` at `0x18002afc0`
- `WINHTTP!WinHttpResetAutoProxy` at `0x18002afc0`
- `WINHTTP!WinHttpSetOption` at `0x18002b006`
- `WINHTTP!WinHttpSetOption` at `0x18002b006`
- `WINHTTP!WinHttpCloseHandle` at `0x18002b04b`
- `WINHTTP!WinHttpCloseHandle` at `0x18002b04b`

## pseudocode

```c
__int64 __fastcall Ncsi::Proxy::Detector::InitializeWinHttp(char a1, void **a2)
{
  void *v4; // rax
  DWORD LastError; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdx
  void *v9; // rcx
  int Buffer; // [rsp+30h] [rbp-38h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 39, WPP_91746b660ee53f707ce4bf14fc97e3d9_Traceguids);
  }
  v4 = WinHttpOpen(c_userAgent, 0, 0, 0, 0);
  *a2 = v4;
  if ( v4 )
  {
    LastError = 0;
    if ( a1 && (LastError = WinHttpResetAutoProxy(v4, 0x30000u)) != 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
        || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_23;
      }
      v8 = 41;
    }
    else
    {
      v9 = *a2;
      Buffer = 1;
      if ( WinHttpSetOption(v9, 0x89u, &Buffer, 4u) )
        return LastError;
      LastError = GetLastError();
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
        || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      {
LABEL_23:
        WinHttpCloseHandle(*a2);
        *a2 = 0;
        return LastError;
      }
      v8 = 42;
    }
    WPP_SF_d(*(_QWORD *)(v7 + 16), v8, WPP_91746b660ee53f707ce4bf14fc97e3d9_Traceguids, LastError);
    goto LABEL_23;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 40, WPP_91746b660ee53f707ce4bf14fc97e3d9_Traceguids);
  }
  return 21;
}

```

## disassembly

```asm
0x18002af04  push    rbx
0x18002af06  push    rsi
0x18002af07  push    rdi
0x18002af08  push    r15
0x18002af0a  sub     rsp, 48h
0x18002af0e  mov     rax, cs:__security_cookie
0x18002af15  xor     rax, rsp
0x18002af18  mov     [rsp+68h+var_30], rax
0x18002af1d  mov     rdi, rdx
0x18002af20  mov     sil, cl
0x18002af23  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af2a  lea     r15, WPP_GLOBAL_Control
0x18002af31  cmp     rcx, r15
0x18002af34  jz      short loc_18002AF57
0x18002af36  test    byte ptr [rcx+1Ch], 10h
0x18002af3a  jz      short loc_18002AF57
0x18002af3c  cmp     byte ptr [rcx+19h], 5
0x18002af40  jb      short loc_18002AF57
0x18002af42  mov     rcx, [rcx+10h]
0x18002af46  lea     r8, WPP_91746b660ee53f707ce4bf14fc97e3d9_Traceguids
0x18002af4d  mov     edx, 27h ; '''
0x18002af52  call    WPP_SF_
0x18002af57  mov     rcx, cs:?c_userAgent@@3V?$basic_zstring_view@G@wil@@B; pszAgentW
0x18002af5e  xor     r9d, r9d; pszProxyBypassW
0x18002af61  xor     r8d, r8d; pszProxyW
0x18002af64  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18002af6c  xor     edx, edx; dwAccessType
0x18002af6e  call    cs:__imp_WinHttpOpen
0x18002af74  mov     [rdi], rax
0x18002af77  test    rax, rax
0x18002af7a  jnz     short loc_18002AFB1
0x18002af7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af83  cmp     rcx, r15
0x18002af86  jz      short loc_18002AFA7
0x18002af88  test    byte ptr [rcx+1Ch], 10h
0x18002af8c  jz      short loc_18002AFA7
0x18002af8e  cmp     byte ptr [rcx+19h], 2
0x18002af92  jb      short loc_18002AFA7
0x18002af94  mov     rcx, [rcx+10h]
0x18002af98  lea     edx, [rax+28h]
0x18002af9b  lea     r8, WPP_91746b660ee53f707ce4bf14fc97e3d9_Traceguids
0x18002afa2  call    WPP_SF_
0x18002afa7  mov     eax, 15h
0x18002afac  jmp     loc_18002B05A
0x18002afb1  xor     ebx, ebx
0x18002afb3  test    sil, sil
0x18002afb6  jz      short loc_18002AFEB
0x18002afb8  mov     edx, 30000h; dwFlags
0x18002afbd  mov     rcx, rax; hSession
0x18002afc0  call    cs:__imp_WinHttpResetAutoProxy
0x18002afc6  mov     ebx, eax
0x18002afc8  test    eax, eax
0x18002afca  jz      short loc_18002AFEB
0x18002afcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002afd3  cmp     rcx, r15
0x18002afd6  jz      short loc_18002B048
0x18002afd8  test    byte ptr [rcx+1Ch], 10h
0x18002afdc  jz      short loc_18002B048
0x18002afde  cmp     byte ptr [rcx+19h], 2
0x18002afe2  jb      short loc_18002B048
0x18002afe4  mov     edx, 29h ; ')'
0x18002afe9  jmp     short loc_18002B035
0x18002afeb  mov     rcx, [rdi]; hInternet
0x18002afee  lea     r8, [rsp+68h+Buffer]; lpBuffer
0x18002aff3  mov     r9d, 4; dwBufferLength
0x18002aff9  mov     [rsp+68h+Buffer], 1
0x18002b001  mov     edx, 89h; dwOption
0x18002b006  call    cs:__imp_WinHttpSetOption
0x18002b00c  test    eax, eax
0x18002b00e  jnz     short loc_18002B058
0x18002b010  call    cs:__imp_GetLastError
0x18002b016  mov     ebx, eax
0x18002b018  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b01f  cmp     rcx, r15
0x18002b022  jz      short loc_18002B048
0x18002b024  test    byte ptr [rcx+1Ch], 10h
0x18002b028  jz      short loc_18002B048
0x18002b02a  cmp     byte ptr [rcx+19h], 2
0x18002b02e  jb      short loc_18002B048
0x18002b030  mov     edx, 2Ah ; '*'
0x18002b035  mov     rcx, [rcx+10h]
0x18002b039  lea     r8, WPP_91746b660ee53f707ce4bf14fc97e3d9_Traceguids
0x18002b040  mov     r9d, ebx
0x18002b043  call    WPP_SF_d
0x18002b048  mov     rcx, [rdi]; hInternet
0x18002b04b  call    cs:__imp_WinHttpCloseHandle
0x18002b051  mov     qword ptr [rdi], 0
0x18002b058  mov     eax, ebx
0x18002b05a  mov     rcx, [rsp+68h+var_30]
0x18002b05f  xor     rcx, rsp; StackCookie
0x18002b062  call    __security_check_cookie
0x18002b067  add     rsp, 48h
0x18002b06b  pop     r15
0x18002b06d  pop     rdi
0x18002b06e  pop     rsi
0x18002b06f  pop     rbx
0x18002b070  retn
```
