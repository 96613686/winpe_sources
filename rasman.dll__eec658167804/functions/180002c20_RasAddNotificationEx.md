# RasAddNotificationEx

- ea: `0x180002c20`
- end: `0x180002d9c`
- name: `RasAddNotificationEx`
- size: `380`
- prototype: `__int64 __fastcall(__int64, const char *, const char *, __int128 *, int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180002c20`
- `0x180002f80`
- `0x180021000`
- `0x1800215e8`
- `0x180026400`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002c80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002c80`

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
0x180002c20  push    rbx
0x180002c22  push    rbp
0x180002c23  push    rsi
0x180002c24  push    rdi
0x180002c25  push    r14
0x180002c27  push    r15
0x180002c29  sub     rsp, 78h
0x180002c2d  mov     rax, cs:__security_cookie
0x180002c34  xor     rax, rsp
0x180002c37  mov     [rsp+0A8h+var_48], rax
0x180002c3c  movups  xmm0, xmmword ptr [r9]
0x180002c40  mov     r14, [rsp+0A8h+arg_28]
0x180002c48  mov     rdi, r8
0x180002c4b  mov     rbx, rdx
0x180002c4e  mov     rsi, rcx
0x180002c51  movaps  xmmword ptr [rsp+0A8h+var_58], xmm0
0x180002c56  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c5d  lea     r15, WPP_GLOBAL_Control
0x180002c64  mov     ebp, dword ptr [rsp+0A8h+arg_20]
0x180002c6b  cmp     rcx, r15
0x180002c6e  jz      short loc_180002C7A
0x180002c70  test    byte ptr [rcx+1Ch], 40h
0x180002c74  jnz     loc_180002D08
0x180002c7a  movdqa  [rsp+0A8h+var_68], xmm0
0x180002c80  call    cs:__imp_GetCurrentProcessId
0x180002c86  mov     qword ptr [rsp+0A8h+var_70], r14
0x180002c8b  mov     ecx, 8Bh
0x180002c90  mov     edx, eax
0x180002c92  mov     dword ptr [rsp+0A8h+var_78], ebp
0x180002c96  lea     rax, [rsp+0A8h+var_68]
0x180002c9b  mov     r9, rbx
0x180002c9e  mov     [rsp+0A8h+var_80], rax
0x180002ca3  mov     r8, rsi
0x180002ca6  mov     [rsp+0A8h+var_88], rdi
0x180002cab  call    SubmitLocalRequest
0x180002cb0  mov     ebx, eax
0x180002cb2  test    eax, eax
0x180002cb4  jnz     loc_180002D5B
0x180002cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cc1  cmp     rcx, r15
0x180002cc4  jnz     short loc_180002CE2
0x180002cc6  mov     eax, ebx
0x180002cc8  mov     rcx, [rsp+0A8h+var_48]
0x180002ccd  xor     rcx, rsp; StackCookie
0x180002cd0  call    __security_check_cookie
0x180002cd5  add     rsp, 78h
0x180002cd9  pop     r15
0x180002cdb  pop     r14
0x180002cdd  pop     rdi
0x180002cde  pop     rsi
0x180002cdf  pop     rbp
0x180002ce0  pop     rbx
0x180002ce1  retn
0x180002ce2  test    byte ptr [rcx+1Ch], 40h
0x180002ce6  jz      short loc_180002CC6
0x180002ce8  cmp     byte ptr [rcx+19h], 6
0x180002cec  jb      short loc_180002CC6
0x180002cee  mov     rcx, [rcx+10h]
0x180002cf2  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180002cf9  mov     edx, 2B5h
0x180002cfe  mov     r9d, ebx
0x180002d01  call    WPP_SF_d
0x180002d06  jmp     short loc_180002CC6
0x180002d08  cmp     byte ptr [rcx+19h], 6
0x180002d0c  jb      loc_180002C7A
0x180002d12  mov     rcx, [rcx+10h]; LoggerHandle
0x180002d16  lea     r8, aNull_2; "<NULL>"
0x180002d1d  test    rdi, rdi
0x180002d20  mov     dword ptr [rsp+0A8h+var_70], ebp; char
0x180002d24  mov     rdx, rdi
0x180002d27  mov     rax, rbx
0x180002d2a  cmovz   rdx, r8
0x180002d2e  mov     r9, rsi
0x180002d31  test    rbx, rbx
0x180002d34  cmovz   rax, r8
0x180002d38  lea     r8, [rsp+0A8h+var_58]
0x180002d3d  mov     [rsp+0A8h+var_78], r8; __int64
0x180002d42  mov     [rsp+0A8h+var_80], rdx; __int64
0x180002d47  mov     [rsp+0A8h+var_88], rax; __int64
0x180002d4c  call    WPP_SF_qSS_guid_D
0x180002d51  movaps  xmm0, xmmword ptr [rsp+0A8h+var_58]
0x180002d56  jmp     loc_180002C7A
0x180002d5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d62  cmp     rcx, r15
0x180002d65  jz      loc_180002CC8
0x180002d6b  test    byte ptr [rcx+1Ch], 40h
0x180002d6f  jz      loc_180002CC1
0x180002d75  cmp     byte ptr [rcx+19h], 2
0x180002d79  jb      loc_180002CC1
0x180002d7f  mov     rcx, [rcx+10h]
0x180002d83  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180002d8a  mov     edx, 2B4h
0x180002d8f  mov     r9d, ebx
0x180002d92  call    WPP_SF_d
0x180002d97  jmp     loc_180002CBA
```
