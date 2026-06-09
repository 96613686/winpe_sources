# RasSrvServiceInitialize

- ea: `0x1800209f8`
- end: `0x180020b78`
- name: `RasSrvServiceInitialize`
- size: `384`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18001f460`
- `0x1800202e0`

## callees

- `0x180020098`
- `0x1800209f8`
- `0x1800263dc`
- `0x1800263f8`
- `0x1800264b4`
- `0x1800264fc`
- `0x180029d34`
- `0x180029f24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a7c`
- `MPRAPI!MprUpgradeRouterConfigHelper` at `0x180020af6`
- `MPRAPI!MprUpgradeRouterConfigHelper` at `0x180020af6`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180020a70`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180020a70`

## string_xrefs

- `0x180020a44`: `remoteaccess`

## pseudocode

```c
__int64 __fastcall RasSrvServiceInitialize(_DWORD *a1, __int64 a2, _DWORD *a3)
{
  __int64 result; // rax
  _DWORD *v7; // r14
  DWORD v8; // eax
  unsigned int *v9; // rbp
  DWORD LastError; // ebx
  int IsPendingState; // edi
  DWORD IsStarted; // eax
  __int64 v13; // rbx
  LPVOID lpMem; // [rsp+50h] [rbp+8h] BYREF

  result = (unsigned int)a1[3];
  lpMem = 0;
  if ( (_DWORD)result )
    return result;
  if ( *a1 )
    return 0;
  v7 = a1 + 1;
  if ( a1[1] )
    return 0;
  v8 = DialupOpenNamedService(aRemoteaccess, (__int64 *)&lpMem);
  v9 = (unsigned int *)lpMem;
  LastError = v8;
  if ( !v8 )
  {
    if ( !lpMem )
    {
      LastError = 87;
      goto LABEL_28;
    }
    if ( QueryServiceStatus(*((SC_HANDLE *)lpMem + 1), (LPSERVICE_STATUS)((char *)lpMem + 16)) )
    {
      IsPendingState = DialupIsPendingState(v9[5]);
    }
    else
    {
      IsPendingState = 0;
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_28;
    }
    if ( IsPendingState )
    {
      *a3 = 2;
      LastError = 1003;
    }
    else
    {
      IsStarted = SvcIsStarted(v9, v7);
      LastError = IsStarted;
      if ( IsStarted )
      {
        *a3 = 1;
      }
      else
      {
        if ( *v7 )
        {
          a1[2] = 1;
          goto LABEL_28;
        }
        if ( a2 )
        {
          v13 = *(_QWORD *)(a2 + 32);
          if ( v13 )
          {
            if ( *(_QWORD *)v13 )
            {
              MprUpgradeRouterConfigHelper();
              if ( !*(_DWORD *)(v13 + 48) )
              {
                protSetEnabling(0, 1);
                protSetRouterType(0, 1);
              }
              if ( !*(_DWORD *)(v13 + 52) )
              {
                protSetEnabling(0, 2);
                protSetRouterType(0, 2);
              }
            }
          }
        }
        IsStarted = RasSrvInitializeService();
        LastError = IsStarted;
        if ( !IsStarted )
        {
          *a1 = 1;
          *v7 = 1;
          goto LABEL_28;
        }
        *a3 = 1;
      }
      a1[3] = IsStarted;
    }
  }
LABEL_28:
  if ( v9 )
    SvcClose(v9);
  return LastError;
}

```

## disassembly

```asm
0x1800209f8  mov     r11, rsp
0x1800209fb  mov     [r11+10h], rbx
0x1800209ff  mov     [r11+18h], rbp
0x180020a03  push    rsi
0x180020a04  push    rdi
0x180020a05  push    r13
0x180020a07  push    r14
0x180020a09  push    r15
0x180020a0b  sub     rsp, 20h
0x180020a0f  mov     eax, [rcx+0Ch]
0x180020a12  mov     r15, r8
0x180020a15  mov     qword ptr [r11+8], 0
0x180020a1d  mov     r13, rdx
0x180020a20  mov     rsi, rcx
0x180020a23  test    eax, eax
0x180020a25  jnz     loc_180020B61
0x180020a2b  cmp     [rcx], eax
0x180020a2d  jnz     loc_180020B5F
0x180020a33  lea     r14, [rcx+4]
0x180020a37  cmp     [r14], eax
0x180020a3a  jnz     loc_180020B5F
0x180020a40  lea     rdx, [r11+8]
0x180020a44  lea     rcx, aRemoteaccess; "remoteaccess"
0x180020a4b  call    DialupOpenNamedService
0x180020a50  mov     rbp, [rsp+48h+lpMem]
0x180020a55  mov     ebx, eax
0x180020a57  test    eax, eax
0x180020a59  jnz     loc_180020B4E
0x180020a5f  test    rbp, rbp
0x180020a62  jz      loc_180020B49
0x180020a68  mov     rcx, [rbp+8]; hService
0x180020a6c  lea     rdx, [rbp+10h]; lpServiceStatus
0x180020a70  call    cs:__imp_QueryServiceStatus
0x180020a76  test    eax, eax
0x180020a78  jnz     short loc_180020A8D
0x180020a7a  xor     edi, edi
0x180020a7c  call    cs:__imp_GetLastError
0x180020a82  mov     ebx, eax
0x180020a84  test    eax, eax
0x180020a86  jz      short loc_180020A97
0x180020a88  jmp     loc_180020B4E
0x180020a8d  mov     ecx, [rbp+14h]
0x180020a90  call    DialupIsPendingState
0x180020a95  mov     edi, eax
0x180020a97  test    edi, edi
0x180020a99  jz      short loc_180020AAC
0x180020a9b  mov     dword ptr [r15], 2
0x180020aa2  mov     ebx, 3EBh
0x180020aa7  jmp     loc_180020B4E
0x180020aac  mov     rdx, r14
0x180020aaf  mov     rcx, rbp
0x180020ab2  call    SvcIsStarted
0x180020ab7  mov     ebx, eax
0x180020ab9  test    eax, eax
0x180020abb  jz      short loc_180020ACC
0x180020abd  mov     dword ptr [r15], 1
0x180020ac4  mov     [rsi+0Ch], eax
0x180020ac7  jmp     loc_180020B4E
0x180020acc  cmp     dword ptr [r14], 0
0x180020ad0  jz      short loc_180020ADB
0x180020ad2  mov     dword ptr [rsi+8], 1
0x180020ad9  jmp     short loc_180020B4E
0x180020adb  mov     edi, 1
0x180020ae0  test    r13, r13
0x180020ae3  jz      short loc_180020B32
0x180020ae5  mov     rbx, [r13+20h]
0x180020ae9  test    rbx, rbx
0x180020aec  jz      short loc_180020B32
0x180020aee  mov     rcx, [rbx]
0x180020af1  test    rcx, rcx
0x180020af4  jz      short loc_180020B32
0x180020af6  call    cs:__imp_MprUpgradeRouterConfigHelper
0x180020afc  cmp     dword ptr [rbx+30h], 0
0x180020b00  jnz     short loc_180020B14
0x180020b02  mov     edx, edi
0x180020b04  xor     ecx, ecx
0x180020b06  call    protSetEnabling
0x180020b0b  mov     edx, edi
0x180020b0d  xor     ecx, ecx
0x180020b0f  call    protSetRouterType
0x180020b14  cmp     dword ptr [rbx+34h], 0
0x180020b18  jnz     short loc_180020B32
0x180020b1a  mov     edx, 2
0x180020b1f  xor     ecx, ecx
0x180020b21  call    protSetEnabling
0x180020b26  mov     edx, 2
0x180020b2b  xor     ecx, ecx
0x180020b2d  call    protSetRouterType
0x180020b32  call    RasSrvInitializeService
0x180020b37  mov     ebx, eax
0x180020b39  test    eax, eax
0x180020b3b  jz      short loc_180020B42
0x180020b3d  mov     [r15], edi
0x180020b40  jmp     short loc_180020AC4
0x180020b42  mov     [rsi], edi
0x180020b44  mov     [r14], edi
0x180020b47  jmp     short loc_180020B4E
0x180020b49  mov     ebx, 57h ; 'W'
0x180020b4e  test    rbp, rbp
0x180020b51  jz      short loc_180020B5B
0x180020b53  mov     rcx, rbp; lpMem
0x180020b56  call    SvcClose
0x180020b5b  mov     eax, ebx
0x180020b5d  jmp     short loc_180020B61
0x180020b5f  xor     eax, eax
0x180020b61  mov     rbx, [rsp+48h+arg_8]
0x180020b66  mov     rbp, [rsp+48h+arg_10]
0x180020b6b  add     rsp, 20h
0x180020b6f  pop     r15
0x180020b71  pop     r14
0x180020b73  pop     r13
0x180020b75  pop     rdi
0x180020b76  pop     rsi
0x180020b77  retn
```
