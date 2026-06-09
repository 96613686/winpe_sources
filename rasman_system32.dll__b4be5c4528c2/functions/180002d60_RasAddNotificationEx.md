# RasAddNotificationEx

- ea: `0x180002d60`
- end: `0x180002ee3`
- name: `RasAddNotificationEx`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180002d60`
- `0x1800030d0`
- `0x180021b14`
- `0x180022150`
- `0x1800273d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002dc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002dc0`

## pseudocode

```c
__int64 __fastcall RasAddNotificationEx(__int64 a1, const char *a2, const char *a3, __int128 *a4, int a5, __int64 a6)
{
  __int128 v6; // xmm0
  DWORD CurrentProcessId; // eax
  __int64 result; // rax
  unsigned int v12; // ebx
  PVOID *v13; // rcx
  const char *v14; // rdx
  const char *v15; // rax
  __int64 v16; // [rsp+30h] [rbp-78h]
  __int128 v17; // [rsp+40h] [rbp-68h] BYREF
  __int64 v18[2]; // [rsp+50h] [rbp-58h] BYREF

  v6 = *a4;
  *(_OWORD *)v18 = *a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v14 = a3;
    v15 = a2;
    if ( !a3 )
      v14 = L"<NULL>";
    if ( !a2 )
      v15 = L"<NULL>";
    WPP_SF_qSS_guid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v15, (__int64)v14, (__int64)v18, a5);
    v6 = *(_OWORD *)v18;
  }
  v17 = v6;
  CurrentProcessId = GetCurrentProcessId();
  LODWORD(v16) = a5;
  result = SubmitLocalRequest(0x8Bu, CurrentProcessId, a1, a2, a3, &v17, v16, a6);
  v12 = result;
  if ( !(_DWORD)result )
    goto LABEL_4;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      692,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      (unsigned int)result);
LABEL_4:
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x40) != 0 && *((_BYTE *)v13 + 25) >= 6u )
    WPP_SF_d(v13[2], 693, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180002d60  push    rbx
0x180002d62  push    rbp
0x180002d63  push    rsi
0x180002d64  push    rdi
0x180002d65  push    r14
0x180002d67  push    r15
0x180002d69  sub     rsp, 78h
0x180002d6d  mov     rax, cs:__security_cookie
0x180002d74  xor     rax, rsp
0x180002d77  mov     [rsp+0A8h+var_48], rax
0x180002d7c  movups  xmm0, xmmword ptr [r9]
0x180002d80  mov     r14, [rsp+0A8h+arg_28]
0x180002d88  mov     rdi, r8
0x180002d8b  mov     rbx, rdx
0x180002d8e  mov     rsi, rcx
0x180002d91  movaps  xmmword ptr [rsp+0A8h+var_58], xmm0
0x180002d96  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d9d  lea     r15, WPP_GLOBAL_Control
0x180002da4  mov     ebp, dword ptr [rsp+0A8h+arg_20]
0x180002dab  cmp     rcx, r15
0x180002dae  jz      short loc_180002DBA
0x180002db0  test    byte ptr [rcx+1Ch], 40h
0x180002db4  jnz     loc_180002E4F
0x180002dba  movdqa  [rsp+0A8h+var_68], xmm0
0x180002dc0  call    cs:__imp_GetCurrentProcessId
0x180002dc7  nop     dword ptr [rax+rax+00h]
0x180002dcc  mov     qword ptr [rsp+0A8h+var_70], r14
0x180002dd1  mov     ecx, 8Bh
0x180002dd6  mov     edx, eax
0x180002dd8  mov     dword ptr [rsp+0A8h+var_78], ebp
0x180002ddc  lea     rax, [rsp+0A8h+var_68]
0x180002de1  mov     r9, rbx
0x180002de4  mov     [rsp+0A8h+var_80], rax
0x180002de9  mov     r8, rsi
0x180002dec  mov     [rsp+0A8h+var_88], rdi
0x180002df1  call    SubmitLocalRequest
0x180002df6  mov     ebx, eax
0x180002df8  test    eax, eax
0x180002dfa  jnz     loc_180002EA2
0x180002e00  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e07  cmp     rcx, r15
0x180002e0a  jnz     short loc_180002E29
0x180002e0c  mov     eax, ebx
0x180002e0e  mov     rcx, [rsp+0A8h+var_48]
0x180002e13  xor     rcx, rsp; StackCookie
0x180002e16  call    __security_check_cookie
0x180002e1b  add     rsp, 78h
0x180002e1f  pop     r15
0x180002e21  pop     r14
0x180002e23  pop     rdi
0x180002e24  pop     rsi
0x180002e25  pop     rbp
0x180002e26  pop     rbx
0x180002e27  retn
0x180002e29  test    byte ptr [rcx+1Ch], 40h
0x180002e2d  jz      short loc_180002E0C
0x180002e2f  cmp     byte ptr [rcx+19h], 6
0x180002e33  jb      short loc_180002E0C
0x180002e35  mov     rcx, [rcx+10h]
0x180002e39  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180002e40  mov     edx, 2B5h
0x180002e45  mov     r9d, ebx
0x180002e48  call    WPP_SF_d
0x180002e4d  jmp     short loc_180002E0C
0x180002e4f  cmp     byte ptr [rcx+19h], 6
0x180002e53  jb      loc_180002DBA
0x180002e59  mov     rcx, [rcx+10h]; LoggerHandle
0x180002e5d  lea     r8, aNull_2; "<NULL>"
0x180002e64  test    rdi, rdi
0x180002e67  mov     dword ptr [rsp+0A8h+var_70], ebp; char
0x180002e6b  mov     rdx, rdi
0x180002e6e  mov     rax, rbx
0x180002e71  cmovz   rdx, r8
0x180002e75  mov     r9, rsi
0x180002e78  test    rbx, rbx
0x180002e7b  cmovz   rax, r8
0x180002e7f  lea     r8, [rsp+0A8h+var_58]
0x180002e84  mov     [rsp+0A8h+var_78], r8; __int64
0x180002e89  mov     [rsp+0A8h+var_80], rdx; __int64
0x180002e8e  mov     [rsp+0A8h+var_88], rax; __int64
0x180002e93  call    WPP_SF_qSS_guid_D
0x180002e98  movaps  xmm0, xmmword ptr [rsp+0A8h+var_58]
0x180002e9d  jmp     loc_180002DBA
0x180002ea2  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ea9  cmp     rcx, r15
0x180002eac  jz      loc_180002E0E
0x180002eb2  test    byte ptr [rcx+1Ch], 40h
0x180002eb6  jz      loc_180002E07
0x180002ebc  cmp     byte ptr [rcx+19h], 2
0x180002ec0  jb      loc_180002E07
0x180002ec6  mov     rcx, [rcx+10h]
0x180002eca  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180002ed1  mov     edx, 2B4h
0x180002ed6  mov     r9d, ebx
0x180002ed9  call    WPP_SF_d
0x180002ede  jmp     loc_180002E00
```
