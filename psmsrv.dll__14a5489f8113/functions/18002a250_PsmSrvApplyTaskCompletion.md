# PsmSrvApplyTaskCompletion

- ea: `0x18002a250`
- end: `0x18002a382`
- name: `PsmSrvApplyTaskCompletion`
- size: `306`
- prototype: `NTSTATUS __fastcall(__int64, void *, unsigned int, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18001b7e0`
- `0x180022640`
- `0x180023ae8`
- `0x18002a250`

## import_xrefs

- `ntdll!NtQueryObject` at `0x18002a2e9`
- `ntdll!NtQueryObject` at `0x18002a2e9`
- `ntdll!NtDuplicateObject` at `0x18002a2c4`
- `ntdll!NtDuplicateObject` at `0x18002a2c4`
- `ntdll!NtClose` at `0x18002a342`
- `ntdll!NtClose` at `0x18002a342`

## pseudocode

```c
NTSTATUS __fastcall PsmSrvApplyTaskCompletion(__int64 a1, void *a2, unsigned int a3, char a4)
{
  NTSTATUS result; // eax
  NTSTATUS Object; // ebx
  __int64 v9; // r9
  void *TargetHandle; // [rsp+40h] [rbp-68h] BYREF
  _OWORD ObjectInformation[3]; // [rsp+48h] [rbp-60h] BYREF
  __int64 v12; // [rsp+78h] [rbp-30h]

  v12 = 0;
  TargetHandle = 0;
  memset(ObjectInformation, 0, sizeof(ObjectInformation));
  if ( !a3 )
    return -1073741583;
  result = NtDuplicateObject(*(HANDLE *)(a1 + 16), a2, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &TargetHandle, 0, 0, 2u);
  if ( result >= 0 )
  {
    Object = NtQueryObject(TargetHandle, ObjectBasicInformation, ObjectInformation, 0x38u, 0);
    if ( Object >= 0 )
    {
      v9 = DWORD1(ObjectInformation[0]);
      if ( (DWORD1(ObjectInformation[0]) & 0x101000) == 0x101000 )
      {
        LOBYTE(v9) = a4;
        return PsmpApplyTaskCompletion(a1, TargetHandle, a3, v9);
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids,
          DWORD1(ObjectInformation[0]),
          1052672);
      Object = -1073741790;
    }
    NtClose(TargetHandle);
    return Object;
  }
  return result;
}

```

## disassembly

```asm
0x18002a250  mov     [rsp+arg_18], rbx
0x18002a255  push    rbp
0x18002a256  push    rsi
0x18002a257  push    rdi
0x18002a258  sub     rsp, 90h
0x18002a25f  mov     rax, cs:__security_cookie
0x18002a266  xor     rax, rsp
0x18002a269  mov     [rsp+0A8h+var_28], rax
0x18002a271  xor     eax, eax
0x18002a273  xorps   xmm0, xmm0
0x18002a276  mov     [rsp+0A8h+var_30], rax
0x18002a27b  mov     bpl, r9b
0x18002a27e  mov     [rsp+0A8h+TargetHandle], rax
0x18002a283  mov     esi, r8d
0x18002a286  mov     rdi, rcx
0x18002a289  movups  [rsp+0A8h+ObjectInformation], xmm0
0x18002a28e  movups  [rsp+0A8h+var_50], xmm0
0x18002a293  movups  [rsp+0A8h+var_40], xmm0
0x18002a298  test    r8d, r8d
0x18002a29b  jnz     short loc_18002A2A7
0x18002a29d  mov     eax, 0C00000F1h
0x18002a2a2  jmp     loc_18002A34A
0x18002a2a7  mov     rcx, [rcx+10h]; SourceProcessHandle
0x18002a2ab  lea     r9, [rsp+0A8h+TargetHandle]; TargetHandle
0x18002a2b0  mov     [rsp+0A8h+Options], 2; Options
0x18002a2b8  or      r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x18002a2bc  mov     [rsp+0A8h+HandleAttributes], eax; HandleAttributes
0x18002a2c0  mov     [rsp+0A8h+DesiredAccess], eax; DesiredAccess
0x18002a2c4  call    cs:__imp_NtDuplicateObject
0x18002a2ca  test    eax, eax
0x18002a2cc  js      short loc_18002A34A
0x18002a2ce  mov     rcx, [rsp+0A8h+TargetHandle]; Handle
0x18002a2d3  lea     r8, [rsp+0A8h+ObjectInformation]; ObjectInformation
0x18002a2d8  mov     r9d, 38h ; '8'; ObjectInformationLength
0x18002a2de  mov     qword ptr [rsp+0A8h+DesiredAccess], 0; ReturnLength
0x18002a2e7  xor     edx, edx; ObjectInformationClass
0x18002a2e9  call    cs:__imp_NtQueryObject
0x18002a2ef  mov     ebx, eax
0x18002a2f1  test    eax, eax
0x18002a2f3  js      short loc_18002A33D
0x18002a2f5  mov     r9d, dword ptr [rsp+0A8h+ObjectInformation+4]
0x18002a2fa  mov     r8d, 101000h
0x18002a300  mov     eax, r9d
0x18002a303  and     eax, r8d
0x18002a306  cmp     eax, r8d
0x18002a309  jz      short loc_18002A36D
0x18002a30b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a312  test    byte ptr [rcx+1Ch], 10h
0x18002a316  jz      short loc_18002A338
0x18002a318  cmp     byte ptr [rcx+19h], 2
0x18002a31c  jb      short loc_18002A338
0x18002a31e  mov     rcx, [rcx+10h]
0x18002a322  mov     edx, 0Ch
0x18002a327  mov     [rsp+0A8h+DesiredAccess], r8d
0x18002a32c  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002a333  call    WPP_SF_Dd
0x18002a338  mov     ebx, 0C0000022h
0x18002a33d  mov     rcx, [rsp+0A8h+TargetHandle]; Handle
0x18002a342  call    cs:__imp_NtClose
0x18002a348  mov     eax, ebx
0x18002a34a  mov     rcx, [rsp+0A8h+var_28]
0x18002a352  xor     rcx, rsp; StackCookie
0x18002a355  call    __security_check_cookie
0x18002a35a  mov     rbx, [rsp+0A8h+arg_18]
0x18002a362  add     rsp, 90h
0x18002a369  pop     rdi
0x18002a36a  pop     rsi
0x18002a36b  pop     rbp
0x18002a36c  retn
0x18002a36d  mov     rdx, [rsp+0A8h+TargetHandle]
0x18002a372  mov     r9b, bpl
0x18002a375  mov     r8d, esi
0x18002a378  mov     rcx, rdi
0x18002a37b  call    PsmpApplyTaskCompletion
0x18002a380  jmp     short loc_18002A34A
```
