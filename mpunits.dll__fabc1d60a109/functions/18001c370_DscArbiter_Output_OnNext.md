# DscArbiter_Output_OnNext

- ea: `0x18001c370`
- end: `0x18001c534`
- name: `DscArbiter_Output_OnNext`
- size: `452`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001a794`
- `0x18001c370`
- `0x180043120`
- `0x180043c74`
- `0x18004484e`
- `0x180044880`
- `0x180045010`

## string_xrefs

- `0x18001c3cc`: `MSFT_DSCConfigurationOutputResult`
- `0x18001c3df`: `MSFT_DSCConfigurationOutputReboot`

## pseudocode

```c
__int64 __fastcall DscArbiter_Output_OnNext(__int64 a1, __int64 *a2)
{
  __int64 v2; // rsi
  __int64 v4; // rbx
  const wchar_t *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rcx
  unsigned __int16 *v9; // rdi
  __int64 v10; // rdx
  int v11; // ecx
  int v12; // eax
  int v14; // [rsp+40h] [rbp-58h] BYREF
  _OWORD v15[2]; // [rsp+48h] [rbp-50h] BYREF
  __int64 v16; // [rsp+68h] [rbp-30h]

  v2 = a1 + 152;
  v4 = a1 + 320;
  v6 = *(const wchar_t **)(*(_QWORD *)(*a2 + 8) + 8LL);
  RecursiveLock_Acquire(a1 + 320);
  if ( *(_QWORD *)(v2 + 160) == -1
    || wcscmp_0(v6, L"MSFT_DSCConfigurationOutputResult") && wcscmp_0(v6, L"MSFT_DSCConfigurationOutputReboot") )
  {
    goto LABEL_17;
  }
  v7 = *a2;
  v16 = 0;
  v14 = 0;
  memset(v15, 0, sizeof(v15));
  if ( !v7 )
    goto LABEL_17;
  if ( !*(_QWORD *)v7 )
    goto LABEL_17;
  if ( (*(unsigned int (__fastcall **)(__int64, const wchar_t *, _OWORD *, int *, _QWORD, _QWORD))(*(_QWORD *)v7 + 88LL))(
         v7,
         L"JobId",
         v15,
         &v14,
         0,
         0) )
  {
    goto LABEL_17;
  }
  v8 = *(_QWORD *)(v2 + 104);
  if ( !v8 )
    goto LABEL_17;
  if ( !*(_QWORD *)v8 )
    goto LABEL_17;
  v9 = *(unsigned __int16 **)&v15[0];
  if ( (*(unsigned int (__fastcall **)(__int64, const wchar_t *, _OWORD *, int *, _QWORD, _QWORD))(*(_QWORD *)v8 + 88LL))(
         v8,
         L"Guid",
         v15,
         &v14,
         0,
         0) )
  {
    goto LABEL_17;
  }
  v10 = *(_QWORD *)&v15[0] - (_QWORD)v9;
  do
  {
    v11 = *(unsigned __int16 *)((char *)v9 + v10);
    v12 = *v9 - v11;
    if ( v12 )
      break;
    ++v9;
  }
  while ( v11 );
  if ( !v12 )
  {
    if ( (__int64)--*(_QWORD *)(v4 + 8) <= 0 )
    {
      *(_DWORD *)(v4 + 16) = 0;
      ReadWriteLock_ReleaseWrite(v4);
    }
    Arbiter_CompleteExecution(v2);
  }
  else
  {
LABEL_17:
    if ( (__int64)--*(_QWORD *)(v4 + 8) <= 0 )
    {
      *(_DWORD *)(v4 + 16) = 0;
      ReadWriteLock_ReleaseWrite(v4);
    }
  }
  return ((__int64 (__fastcall *)(__int64, __int64 *))ObserverProtocol_PostNext_ThreadSafe)(a1, a2);
}

```

## disassembly

```asm
0x18001c370  mov     [rsp+arg_10], rbx
0x18001c375  mov     [rsp+arg_18], rbp
0x18001c37a  push    rsi
0x18001c37b  push    rdi
0x18001c37c  push    r14
0x18001c37e  sub     rsp, 80h
0x18001c385  mov     rax, cs:__security_cookie
0x18001c38c  xor     rax, rsp
0x18001c38f  mov     [rsp+98h+var_28], rax
0x18001c394  mov     rax, [rdx]
0x18001c397  lea     rsi, [rcx+98h]
0x18001c39e  mov     rbp, rcx
0x18001c3a1  lea     rbx, [rsi+0A8h]
0x18001c3a8  mov     r14, rdx
0x18001c3ab  mov     rcx, [rax+8]
0x18001c3af  mov     rdi, [rcx+8]
0x18001c3b3  mov     rcx, rbx
0x18001c3b6  call    RecursiveLock_Acquire
0x18001c3bb  mov     rax, [rsi+0A0h]
0x18001c3c2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c3c6  jz      loc_18001C4DF
0x18001c3cc  lea     rdx, aMsftDscconfigu_3; "MSFT_DSCConfigurationOutputResult"
0x18001c3d3  mov     rcx, rdi; String1
0x18001c3d6  call    wcscmp_0
0x18001c3db  test    eax, eax
0x18001c3dd  jz      short loc_18001C3F6
0x18001c3df  lea     rdx, aMsftDscconfigu; "MSFT_DSCConfigurationOutputReboot"
0x18001c3e6  mov     rcx, rdi; String1
0x18001c3e9  call    wcscmp_0
0x18001c3ee  test    eax, eax
0x18001c3f0  jnz     loc_18001C4DF
0x18001c3f6  mov     rcx, [r14]
0x18001c3f9  xor     eax, eax
0x18001c3fb  mov     [rsp+98h+var_30], rax
0x18001c400  xorps   xmm0, xmm0
0x18001c403  mov     [rsp+98h+var_58], eax
0x18001c407  movups  [rsp+98h+var_50], xmm0
0x18001c40c  movups  [rsp+98h+var_40], xmm0
0x18001c411  test    rcx, rcx
0x18001c414  jz      loc_18001C4DF
0x18001c41a  mov     rax, [rcx]
0x18001c41d  test    rax, rax
0x18001c420  jz      loc_18001C4DF
0x18001c426  mov     rax, [rax+58h]
0x18001c42a  lea     r9, [rsp+98h+var_58]
0x18001c42f  mov     [rsp+98h+var_70], 0
0x18001c438  lea     r8, [rsp+98h+var_50]
0x18001c43d  lea     rdx, aJobid_0; "JobId"
0x18001c444  mov     [rsp+98h+var_78], 0
0x18001c44d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c452  test    eax, eax
0x18001c454  jnz     loc_18001C4DF
0x18001c45a  mov     rcx, [rsi+68h]
0x18001c45e  test    rcx, rcx
0x18001c461  jz      short loc_18001C4DF
0x18001c463  mov     rax, [rcx]
0x18001c466  test    rax, rax
0x18001c469  jz      short loc_18001C4DF
0x18001c46b  mov     rax, [rax+58h]
0x18001c46f  lea     r9, [rsp+98h+var_58]
0x18001c474  mov     rdi, qword ptr [rsp+98h+var_50]
0x18001c479  lea     r8, [rsp+98h+var_50]
0x18001c47e  mov     [rsp+98h+var_70], 0
0x18001c487  lea     rdx, aGuid; "Guid"
0x18001c48e  mov     [rsp+98h+var_78], 0
0x18001c497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c49c  test    eax, eax
0x18001c49e  jnz     short loc_18001C4DF
0x18001c4a0  mov     rdx, qword ptr [rsp+98h+var_50]
0x18001c4a5  sub     rdx, rdi
0x18001c4a8  movzx   eax, word ptr [rdi]
0x18001c4ab  movzx   ecx, word ptr [rdi+rdx]
0x18001c4af  sub     eax, ecx
0x18001c4b1  jnz     short loc_18001C4BB
0x18001c4b3  add     rdi, 2
0x18001c4b7  test    ecx, ecx
0x18001c4b9  jnz     short loc_18001C4A8
0x18001c4bb  test    eax, eax
0x18001c4bd  jnz     short loc_18001C4DF
0x18001c4bf  dec     qword ptr [rbx+8]
0x18001c4c3  cmp     qword ptr [rbx+8], 0
0x18001c4c8  jg      short loc_18001C4D5
0x18001c4ca  mov     rcx, rbx
0x18001c4cd  mov     [rbx+10h], eax
0x18001c4d0  call    ReadWriteLock_ReleaseWrite
0x18001c4d5  mov     rcx, rsi
0x18001c4d8  call    Arbiter_CompleteExecution
0x18001c4dd  jmp     short loc_18001C4F9
0x18001c4df  dec     qword ptr [rbx+8]
0x18001c4e3  cmp     qword ptr [rbx+8], 0
0x18001c4e8  jg      short loc_18001C4F9
0x18001c4ea  mov     rcx, rbx
0x18001c4ed  mov     dword ptr [rbx+10h], 0
0x18001c4f4  call    ReadWriteLock_ReleaseWrite
0x18001c4f9  mov     rax, cs:off_180047BB0
0x18001c500  mov     rdx, r14
0x18001c503  mov     rcx, rbp
0x18001c506  mov     rax, [rax+28h]
0x18001c50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c50f  mov     rcx, [rsp+98h+var_28]
0x18001c514  xor     rcx, rsp; StackCookie
0x18001c517  call    __security_check_cookie
0x18001c51c  lea     r11, [rsp+98h+var_18]
0x18001c524  mov     rbx, [r11+30h]
0x18001c528  mov     rbp, [r11+38h]
0x18001c52c  mov     rsp, r11
0x18001c52f  pop     r14
0x18001c531  pop     rdi
0x18001c532  pop     rsi
0x18001c533  retn
```
