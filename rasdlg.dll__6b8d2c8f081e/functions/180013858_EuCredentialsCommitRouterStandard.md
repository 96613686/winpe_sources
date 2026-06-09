# EuCredentialsCommitRouterStandard

- ea: `0x180013858`
- end: `0x1800139a9`
- name: `EuCredentialsCommitRouterStandard`
- size: `337`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012b78`

## callees

- `0x180013858`
- `0x18003bea0`
- `0x18003c860`
- `0x18003d184`
- `0x18004e010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x180013892`
- `rtutils!TracePrintfExA` at `0x180013973`
- `rtutils!TracePrintfExA` at `0x180013892`
- `rtutils!TracePrintfExA` at `0x180013973`

## string_xrefs

- `0x180013886`: `EuCredentialsCommitRouterStandard`
- `0x180013905`: `EuCredComRouterStandard: MprAdminInterfaceGetHandle error %d`
- `0x180013967`: `EuCredComRouterStndrd: MprAdminInterfaceSetCredentials error %d`

## pseudocode

```c
__int64 __fastcall EuCredentialsCommitRouterStandard(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rsi
  unsigned int v4; // ebx
  unsigned int v5; // eax
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  v7 = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "EuCredentialsCommitRouterStandard");
  result = ((__int64 (__fastcall *)(_QWORD, __int64 *))g_pMprAdminServerConnect)(*(_QWORD *)(a1 + 48), &v6);
  if ( !(_DWORD)result )
  {
    v3 = StrDup(*(STRSAFE_LPCWSTR *)(*(_QWORD *)(a1 + 872) + 8LL));
    if ( v3 )
    {
      v5 = ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD))g_pMprAdminInterfaceGetHandle)(v6, v3, &v7, 0);
      v4 = v5;
      if ( v5 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "EuCredComRouterStandard: MprAdminInterfaceGetHandle error %d", v5);
      }
      else
      {
        EncodePasswordW(*(__int16 **)(a1 + 928));
        v4 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD, _QWORD))g_pMprAdminInterfaceSetCredentials)(
               *(_QWORD *)(a1 + 48),
               v3,
               *(_QWORD *)(a1 + 912),
               *(_QWORD *)(a1 + 920),
               *(_QWORD *)(a1 + 928));
        EncodePasswordW(*(__int16 **)(a1 + 928));
        if ( v4 && g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "EuCredComRouterStndrd: MprAdminInterfaceSetCredentials error %d", v4);
      }
      Free0(v3);
    }
    else
    {
      v4 = 8;
    }
    if ( v6 )
      ((void (*)(void))g_pMprAdminServerDisconnect)();
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180013858  mov     rax, rsp
0x18001385b  mov     [rax+18h], rbx
0x18001385f  mov     [rax+20h], rsi
0x180013863  push    rdi
0x180013864  sub     rsp, 30h
0x180013868  mov     rdi, rcx
0x18001386b  mov     qword ptr [rax+8], 0
0x180013873  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180013879  mov     qword ptr [rax+10h], 0
0x180013881  cmp     ecx, 0FFFFFFFFh
0x180013884  jz      short loc_180013898
0x180013886  lea     r8, aEucredentialsc_1; "EuCredentialsCommitRouterStandard"
0x18001388d  mov     edx, 0Ch; dwFlags
0x180013892  call    cs:__imp_TracePrintfExA
0x180013898  mov     rcx, [rdi+30h]
0x18001389c  lea     rdx, [rsp+38h+arg_0]
0x1800138a1  mov     rax, cs:g_pMprAdminServerConnect
0x1800138a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138ad  test    eax, eax
0x1800138af  jnz     loc_180013999
0x1800138b5  mov     rcx, [rdi+368h]
0x1800138bc  mov     rcx, [rcx+8]; pszSrc
0x1800138c0  call    StrDup
0x1800138c5  mov     rsi, rax
0x1800138c8  test    rax, rax
0x1800138cb  jnz     short loc_1800138D5
0x1800138cd  lea     ebx, [rax+8]
0x1800138d0  jmp     loc_180013981
0x1800138d5  mov     rcx, [rsp+38h+arg_0]
0x1800138da  lea     r8, [rsp+38h+arg_8]
0x1800138df  mov     rax, cs:g_pMprAdminInterfaceGetHandle
0x1800138e6  xor     r9d, r9d
0x1800138e9  mov     rdx, rsi
0x1800138ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138f1  mov     ebx, eax
0x1800138f3  test    eax, eax
0x1800138f5  jz      short loc_18001390E
0x1800138f7  mov     ecx, cs:g_dwTraceId
0x1800138fd  cmp     ecx, 0FFFFFFFFh
0x180013900  jz      short loc_180013979
0x180013902  mov     r9d, eax
0x180013905  lea     r8, aEucredcomroute_2; "EuCredComRouterStandard: MprAdminInterf"...
0x18001390c  jmp     short loc_18001396E
0x18001390e  mov     rcx, [rdi+3A0h]
0x180013915  call    EncodePasswordW
0x18001391a  mov     rcx, [rdi+3A0h]
0x180013921  mov     rdx, rsi
0x180013924  mov     r9, [rdi+398h]
0x18001392b  mov     r8, [rdi+390h]
0x180013932  mov     rax, cs:g_pMprAdminInterfaceSetCredentials
0x180013939  mov     [rsp+38h+var_18], rcx
0x18001393e  mov     rcx, [rdi+30h]
0x180013942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013947  mov     rcx, [rdi+3A0h]
0x18001394e  mov     ebx, eax
0x180013950  call    EncodePasswordW
0x180013955  test    ebx, ebx
0x180013957  jz      short loc_180013979
0x180013959  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001395f  cmp     ecx, 0FFFFFFFFh
0x180013962  jz      short loc_180013979
0x180013964  mov     r9d, ebx
0x180013967  lea     r8, aEucredcomroute_3; "EuCredComRouterStndrd: MprAdminInterfac"...
0x18001396e  mov     edx, 0Ch; dwFlags
0x180013973  call    cs:__imp_TracePrintfExA
0x180013979  mov     rcx, rsi
0x18001397c  call    Free0
0x180013981  mov     rcx, [rsp+38h+arg_0]
0x180013986  test    rcx, rcx
0x180013989  jz      short loc_180013997
0x18001398b  mov     rax, cs:g_pMprAdminServerDisconnect
0x180013992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013997  mov     eax, ebx
0x180013999  mov     rbx, [rsp+38h+arg_10]
0x18001399e  mov     rsi, [rsp+38h+arg_18]
0x1800139a3  add     rsp, 30h
0x1800139a7  pop     rdi
0x1800139a8  retn
```
