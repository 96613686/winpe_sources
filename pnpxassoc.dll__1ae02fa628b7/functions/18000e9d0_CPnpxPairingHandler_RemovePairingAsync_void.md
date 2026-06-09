# CPnpxPairingHandler::RemovePairingAsync(void)

- ea: `0x18000e9d0`
- end: `0x18000ebbf`
- name: `?RemovePairingAsync@CPnpxPairingHandler@@UEAAJXZ`
- size: `495`
- prototype: `__int64 __fastcall(CPnpxPairingHandler *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callees

- `0x18000bce4`
- `0x18000bd30`
- `0x18000d2a8`
- `0x18000d7d8`
- `0x18000db10`
- `0x18000de14`
- `0x18000e104`
- `0x18000e9d0`
- `0x18000ebc8`
- `0x18000ed14`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CPnpxPairingHandler::RemovePairingAsync(CPnpxPairingHandler *this)
{
  unsigned int v2; // ebx
  int IsServiceDisabled; // edi
  int v4; // eax
  _QWORD *v5; // rcx
  BOOL v6; // eax
  struct IPairingCallback *PairingCallback; // rbx
  int v9; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v10; // [rsp+58h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
  v9 = 0;
  v10 = 0;
  v2 = CPnpxPairingHandler::SetState((char *)this - 8, 6, &v10);
  if ( v2 )
    goto LABEL_14;
  IsServiceDisabled = CPnpxPairingHandler::IsServiceDisabled((CPnpxPairingHandler *)((char *)this - 8), &v9);
  if ( IsServiceDisabled )
    goto LABEL_10;
  if ( !v9 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 11) + 56LL))(*((_QWORD *)this + 11), 0);
    IsServiceDisabled = v4;
    if ( v4 == -2147483638 )
    {
      CPnpxPairingHandler::SetState((char *)this - 8, 7, 0);
    }
    else if ( v4 )
    {
      if ( v4 == -2147024894 )
      {
        CPnpxPairingHandler::StampDevNodeAsNotPaired((CPnpxPairingHandler *)((char *)this - 8));
        v2 = -2147023728;
        goto LABEL_13;
      }
    }
    else
    {
      CPnpxPairingHandler::SetState((char *)this - 8, 0, 0);
      CPnpxPairingHandler::BeginCallback((CPnpxPairingHandler *)((char *)this - 8));
      PairingCallback = CPnpxPairingHandler::GetPairingCallback((CPnpxPairingHandler *)((char *)this - 8));
      if ( PairingCallback )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
        (*(void (__fastcall **)(struct IPairingCallback *, _QWORD, _QWORD))(*(_QWORD *)PairingCallback + 88LL))(
          PairingCallback,
          0,
          0);
        (*(void (__fastcall **)(struct IPairingCallback *))(*(_QWORD *)PairingCallback + 16LL))(PairingCallback);
      }
      else
      {
        IsServiceDisabled = -2147467259;
      }
      CPnpxPairingHandler::EndCallback((CPnpxPairingHandler *)((char *)this - 8));
    }
LABEL_10:
    v2 = 0;
    if ( IsServiceDisabled != -2147483638 )
      v2 = IsServiceDisabled;
    if ( !v2 )
    {
      v5 = WPP_GLOBAL_Control;
      v6 = *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
      v2 = 0;
      goto LABEL_15;
    }
    goto LABEL_13;
  }
  v2 = -1882193913;
LABEL_13:
  CPnpxPairingHandler::SetState((char *)this - 8, v10, 0);
LABEL_14:
  v5 = WPP_GLOBAL_Control;
  v6 = *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
LABEL_15:
  if ( v5 != &WPP_GLOBAL_Control && v6 )
    WPP_SF_sqd(v5[2], 31, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
  return v2;
}

```

## disassembly

```asm
0x18000e9d0  mov     [rsp+arg_10], rbx
0x18000e9d5  mov     [rsp+arg_18], rbp
0x18000e9da  push    rsi
0x18000e9db  push    rdi
0x18000e9dc  push    r12
0x18000e9de  sub     rsp, 30h
0x18000e9e2  mov     rbp, rcx
0x18000e9e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9ec  lea     r12, WPP_GLOBAL_Control
0x18000e9f3  cmp     rcx, r12
0x18000e9f6  jz      short loc_18000EA1C
0x18000e9f8  cmp     byte ptr [rcx+19h], 4
0x18000e9fc  jb      short loc_18000EA1C
0x18000e9fe  mov     rcx, [rcx+10h]
0x18000ea02  lea     rax, [rbp-8]
0x18000ea06  mov     edx, 1Dh
0x18000ea0b  mov     [rsp+48h+var_28], rax
0x18000ea10  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000ea17  call    WPP_SF_sq
0x18000ea1c  lea     rsi, [rbp-8]
0x18000ea20  mov     [rsp+48h+arg_0], 0
0x18000ea28  mov     rcx, rsi
0x18000ea2b  mov     [rsp+48h+arg_8], 0
0x18000ea33  lea     r8, [rsp+48h+arg_8]
0x18000ea38  mov     edx, 6
0x18000ea3d  call    ?SetState@CPnpxPairingHandler@@IEAAJW4_PAIRING_STATE@@PEAW42@@Z; CPnpxPairingHandler::SetState(_PAIRING_STATE,_PAIRING_STATE *)
0x18000ea42  mov     ebx, eax
0x18000ea44  test    eax, eax
0x18000ea46  jnz     short loc_18000EAB4
0x18000ea48  lea     rdx, [rsp+48h+arg_0]; int *
0x18000ea4d  mov     rcx, rsi; this
0x18000ea50  call    ?IsServiceDisabled@CPnpxPairingHandler@@IEAAJPEAH@Z; CPnpxPairingHandler::IsServiceDisabled(int *)
0x18000ea55  mov     edi, eax
0x18000ea57  test    eax, eax
0x18000ea59  jnz     short loc_18000EA92
0x18000ea5b  cmp     [rsp+48h+arg_0], eax
0x18000ea5f  jz      short loc_18000EA68
0x18000ea61  mov     ebx, 8FD00007h
0x18000ea66  jmp     short loc_18000EAA5
0x18000ea68  mov     rcx, [rbp+58h]
0x18000ea6c  xor     edx, edx
0x18000ea6e  mov     rax, [rcx]
0x18000ea71  mov     rax, [rax+38h]
0x18000ea75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea7a  mov     edi, eax
0x18000ea7c  cmp     eax, 8000000Ah
0x18000ea81  jnz     short loc_18000EB00
0x18000ea83  xor     r8d, r8d
0x18000ea86  mov     rcx, rsi
0x18000ea89  lea     edx, [r8+7]
0x18000ea8d  call    ?SetState@CPnpxPairingHandler@@IEAAJW4_PAIRING_STATE@@PEAW42@@Z; CPnpxPairingHandler::SetState(_PAIRING_STATE,_PAIRING_STATE *)
0x18000ea92  xor     ebx, ebx
0x18000ea94  cmp     edi, 8000000Ah
0x18000ea9a  cmovnz  ebx, edi
0x18000ea9d  test    ebx, ebx
0x18000ea9f  jz      loc_18000EBA8
0x18000eaa5  mov     edx, [rsp+48h+arg_8]
0x18000eaa9  xor     r8d, r8d
0x18000eaac  mov     rcx, rsi
0x18000eaaf  call    ?SetState@CPnpxPairingHandler@@IEAAJW4_PAIRING_STATE@@PEAW42@@Z; CPnpxPairingHandler::SetState(_PAIRING_STATE,_PAIRING_STATE *)
0x18000eab4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eabb  xor     eax, eax
0x18000eabd  cmp     byte ptr [rcx+19h], 2
0x18000eac1  setnb   al
0x18000eac4  cmp     rcx, r12
0x18000eac7  jz      short loc_18000EAEB
0x18000eac9  test    eax, eax
0x18000eacb  jz      short loc_18000EAEB
0x18000eacd  mov     rcx, [rcx+10h]
0x18000ead1  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000ead8  mov     edx, 1Fh
0x18000eadd  mov     [rsp+48h+var_20], ebx
0x18000eae1  mov     [rsp+48h+var_28], rsi
0x18000eae6  call    WPP_SF_sqd
0x18000eaeb  mov     rbp, [rsp+48h+arg_18]
0x18000eaf0  mov     eax, ebx
0x18000eaf2  mov     rbx, [rsp+48h+arg_10]
0x18000eaf7  add     rsp, 30h
0x18000eafb  pop     r12
0x18000eafd  pop     rdi
0x18000eafe  pop     rsi
0x18000eaff  retn
0x18000eb00  test    eax, eax
0x18000eb02  jnz     loc_18000EB8B
0x18000eb08  xor     r8d, r8d
0x18000eb0b  xor     edx, edx
0x18000eb0d  mov     rcx, rsi
0x18000eb10  call    ?SetState@CPnpxPairingHandler@@IEAAJW4_PAIRING_STATE@@PEAW42@@Z; CPnpxPairingHandler::SetState(_PAIRING_STATE,_PAIRING_STATE *)
0x18000eb15  mov     rcx, rsi; this
0x18000eb18  call    ?BeginCallback@CPnpxPairingHandler@@IEAAXXZ; CPnpxPairingHandler::BeginCallback(void)
0x18000eb1d  mov     rcx, rsi; this
0x18000eb20  call    ?GetPairingCallback@CPnpxPairingHandler@@IEAAPEAUIPairingCallback@@XZ; CPnpxPairingHandler::GetPairingCallback(void)
0x18000eb25  mov     rbx, rax
0x18000eb28  test    rax, rax
0x18000eb2b  jz      short loc_18000EB79
0x18000eb2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb34  cmp     rcx, r12
0x18000eb37  jz      short loc_18000EB54
0x18000eb39  cmp     byte ptr [rcx+19h], 4
0x18000eb3d  jb      short loc_18000EB54
0x18000eb3f  mov     rcx, [rcx+10h]
0x18000eb43  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000eb4a  mov     edx, 1Eh
0x18000eb4f  call    WPP_SF_s
0x18000eb54  mov     rax, [rbx]
0x18000eb57  xor     r8d, r8d
0x18000eb5a  xor     edx, edx
0x18000eb5c  mov     rcx, rbx
0x18000eb5f  mov     rax, [rax+58h]
0x18000eb63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb68  mov     rax, [rbx]
0x18000eb6b  mov     rcx, rbx
0x18000eb6e  mov     rax, [rax+10h]
0x18000eb72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb77  jmp     short loc_18000EB7E
0x18000eb79  mov     edi, 80004005h
0x18000eb7e  mov     rcx, rsi; this
0x18000eb81  call    ?EndCallback@CPnpxPairingHandler@@IEAAXXZ; CPnpxPairingHandler::EndCallback(void)
0x18000eb86  jmp     loc_18000EA92
0x18000eb8b  cmp     eax, 80070002h
0x18000eb90  jnz     loc_18000EA92
0x18000eb96  mov     rcx, rsi; this
0x18000eb99  call    ?StampDevNodeAsNotPaired@CPnpxPairingHandler@@IEAAJXZ; CPnpxPairingHandler::StampDevNodeAsNotPaired(void)
0x18000eb9e  mov     ebx, 80070490h
0x18000eba3  jmp     loc_18000EAA5
0x18000eba8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebaf  xor     eax, eax
0x18000ebb1  cmp     byte ptr [rcx+19h], 4
0x18000ebb5  setnb   al
0x18000ebb8  xor     ebx, ebx
0x18000ebba  jmp     loc_18000EAC4
```
