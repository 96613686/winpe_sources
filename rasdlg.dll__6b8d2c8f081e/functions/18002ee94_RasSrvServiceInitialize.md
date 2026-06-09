# RasSrvServiceInitialize

- ea: `0x18002ee94`
- end: `0x18002f014`
- name: `RasSrvServiceInitialize`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18002e75c`

## callees

- `0x18002e370`
- `0x18002ee94`
- `0x1800345bc`
- `0x1800345d8`
- `0x180034694`
- `0x1800346dc`
- `0x180037e48`
- `0x180038038`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ef18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ef18`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002ef0c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002ef0c`
- `MPRAPI!MprUpgradeRouterConfigHelper` at `0x18002ef92`
- `MPRAPI!MprUpgradeRouterConfigHelper` at `0x18002ef92`

## string_xrefs

- `0x18002eee0`: `remoteaccess`

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
  v8 = DialupOpenNamedService(aRemoteaccess_0, (__int64 *)&lpMem);
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
0x18002ee94  mov     r11, rsp
0x18002ee97  mov     [r11+10h], rbx
0x18002ee9b  mov     [r11+18h], rbp
0x18002ee9f  push    rsi
0x18002eea0  push    rdi
0x18002eea1  push    r13
0x18002eea3  push    r14
0x18002eea5  push    r15
0x18002eea7  sub     rsp, 20h
0x18002eeab  mov     eax, [rcx+0Ch]
0x18002eeae  mov     r15, r8
0x18002eeb1  mov     qword ptr [r11+8], 0
0x18002eeb9  mov     r13, rdx
0x18002eebc  mov     rsi, rcx
0x18002eebf  test    eax, eax
0x18002eec1  jnz     loc_18002EFFD
0x18002eec7  cmp     [rcx], eax
0x18002eec9  jnz     loc_18002EFFB
0x18002eecf  lea     r14, [rcx+4]
0x18002eed3  cmp     [r14], eax
0x18002eed6  jnz     loc_18002EFFB
0x18002eedc  lea     rdx, [r11+8]
0x18002eee0  lea     rcx, aRemoteaccess_0; "remoteaccess"
0x18002eee7  call    DialupOpenNamedService
0x18002eeec  mov     rbp, [rsp+48h+lpMem]
0x18002eef1  mov     ebx, eax
0x18002eef3  test    eax, eax
0x18002eef5  jnz     loc_18002EFEA
0x18002eefb  test    rbp, rbp
0x18002eefe  jz      loc_18002EFE5
0x18002ef04  mov     rcx, [rbp+8]; hService
0x18002ef08  lea     rdx, [rbp+10h]; lpServiceStatus
0x18002ef0c  call    cs:__imp_QueryServiceStatus
0x18002ef12  test    eax, eax
0x18002ef14  jnz     short loc_18002EF29
0x18002ef16  xor     edi, edi
0x18002ef18  call    cs:__imp_GetLastError
0x18002ef1e  mov     ebx, eax
0x18002ef20  test    eax, eax
0x18002ef22  jz      short loc_18002EF33
0x18002ef24  jmp     loc_18002EFEA
0x18002ef29  mov     ecx, [rbp+14h]
0x18002ef2c  call    DialupIsPendingState
0x18002ef31  mov     edi, eax
0x18002ef33  test    edi, edi
0x18002ef35  jz      short loc_18002EF48
0x18002ef37  mov     dword ptr [r15], 2
0x18002ef3e  mov     ebx, 3EBh
0x18002ef43  jmp     loc_18002EFEA
0x18002ef48  mov     rdx, r14
0x18002ef4b  mov     rcx, rbp
0x18002ef4e  call    SvcIsStarted
0x18002ef53  mov     ebx, eax
0x18002ef55  test    eax, eax
0x18002ef57  jz      short loc_18002EF68
0x18002ef59  mov     dword ptr [r15], 1
0x18002ef60  mov     [rsi+0Ch], eax
0x18002ef63  jmp     loc_18002EFEA
0x18002ef68  cmp     dword ptr [r14], 0
0x18002ef6c  jz      short loc_18002EF77
0x18002ef6e  mov     dword ptr [rsi+8], 1
0x18002ef75  jmp     short loc_18002EFEA
0x18002ef77  mov     edi, 1
0x18002ef7c  test    r13, r13
0x18002ef7f  jz      short loc_18002EFCE
0x18002ef81  mov     rbx, [r13+20h]
0x18002ef85  test    rbx, rbx
0x18002ef88  jz      short loc_18002EFCE
0x18002ef8a  mov     rcx, [rbx]
0x18002ef8d  test    rcx, rcx
0x18002ef90  jz      short loc_18002EFCE
0x18002ef92  call    cs:__imp_MprUpgradeRouterConfigHelper
0x18002ef98  cmp     dword ptr [rbx+30h], 0
0x18002ef9c  jnz     short loc_18002EFB0
0x18002ef9e  mov     edx, edi
0x18002efa0  xor     ecx, ecx
0x18002efa2  call    protSetEnabling
0x18002efa7  mov     edx, edi
0x18002efa9  xor     ecx, ecx
0x18002efab  call    protSetRouterType
0x18002efb0  cmp     dword ptr [rbx+34h], 0
0x18002efb4  jnz     short loc_18002EFCE
0x18002efb6  mov     edx, 2
0x18002efbb  xor     ecx, ecx
0x18002efbd  call    protSetEnabling
0x18002efc2  mov     edx, 2
0x18002efc7  xor     ecx, ecx
0x18002efc9  call    protSetRouterType
0x18002efce  call    RasSrvInitializeService
0x18002efd3  mov     ebx, eax
0x18002efd5  test    eax, eax
0x18002efd7  jz      short loc_18002EFDE
0x18002efd9  mov     [r15], edi
0x18002efdc  jmp     short loc_18002EF60
0x18002efde  mov     [rsi], edi
0x18002efe0  mov     [r14], edi
0x18002efe3  jmp     short loc_18002EFEA
0x18002efe5  mov     ebx, 57h ; 'W'
0x18002efea  test    rbp, rbp
0x18002efed  jz      short loc_18002EFF7
0x18002efef  mov     rcx, rbp; lpMem
0x18002eff2  call    SvcClose
0x18002eff7  mov     eax, ebx
0x18002eff9  jmp     short loc_18002EFFD
0x18002effb  xor     eax, eax
0x18002effd  mov     rbx, [rsp+48h+arg_8]
0x18002f002  mov     rbp, [rsp+48h+arg_10]
0x18002f007  add     rsp, 20h
0x18002f00b  pop     r15
0x18002f00d  pop     r14
0x18002f00f  pop     r13
0x18002f011  pop     rdi
0x18002f012  pop     rsi
0x18002f013  retn
```
