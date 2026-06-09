# PADeleteMMPolicy

- ea: `0x1800277f8`
- end: `0x1800278da`
- name: `PADeleteMMPolicy`
- size: `226`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002b8d0`
- `0x18002d8c4`

## callees

- `0x18000e510`
- `0x18001a860`
- `0x18001cc18`
- `0x180027408`
- `0x1800277f8`
- `0x1800278e0`
- `0x18004d090`

## pseudocode

```c
__int64 __fastcall PADeleteMMPolicy(__int128 *a1)
{
  __int128 v1; // xmm0
  __int64 result; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rdi
  unsigned int v6; // ebx
  unsigned int v7; // eax
  __int128 v8; // [rsp+20h] [rbp-38h] BYREF
  __int128 v9; // [rsp+30h] [rbp-28h] BYREF

  v1 = *a1;
  v9 = *a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_30a2a25fe4c032b6b42c56c6e7b9adea_Traceguids, &v9);
    v1 = v9;
  }
  v8 = v1;
  result = FindMMPolicyState(&v8);
  v5 = result;
  if ( result )
  {
    v6 = 0;
    if ( *(_DWORD *)(result + 24) && (v7 = DeleteMMPolicy(v4, v3, *(_WORD **)(result + 16)), (v6 = v7) != 0) )
    {
      *(_DWORD *)(v5 + 28) = v7;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_30a2a25fe4c032b6b42c56c6e7b9adea_Traceguids, v7);
    }
    else
    {
      PADeleteMMPolicyState(v5);
    }
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x1800277f8  mov     [rsp+arg_8], rbx
0x1800277fd  mov     [rsp+arg_10], rsi
0x180027802  push    rdi
0x180027803  sub     rsp, 50h
0x180027807  mov     rax, cs:__security_cookie
0x18002780e  xor     rax, rsp
0x180027811  mov     [rsp+58h+var_18], rax
0x180027816  movaps  xmm0, xmmword ptr [rcx]
0x180027819  movaps  [rsp+58h+var_28], xmm0
0x18002781e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027825  lea     rsi, WPP_GLOBAL_Control
0x18002782c  cmp     rcx, rsi
0x18002782f  jz      short loc_180027856
0x180027831  test    byte ptr [rcx+1Ch], 4
0x180027835  jz      short loc_180027856
0x180027837  mov     rcx, [rcx+10h]
0x18002783b  lea     r9, [rsp+58h+var_28]
0x180027840  mov     edx, 18h
0x180027845  lea     r8, WPP_30a2a25fe4c032b6b42c56c6e7b9adea_Traceguids
0x18002784c  call    WPP_SF__guid_
0x180027851  movaps  xmm0, [rsp+58h+var_28]
0x180027856  lea     rcx, [rsp+58h+var_38]
0x18002785b  movdqa  [rsp+58h+var_38], xmm0
0x180027861  call    FindMMPolicyState
0x180027866  mov     rdi, rax
0x180027869  test    rax, rax
0x18002786c  jz      short loc_1800278BD
0x18002786e  xor     ebx, ebx
0x180027870  cmp     [rax+18h], ebx
0x180027873  jz      short loc_1800278B3
0x180027875  mov     r8, [rax+10h]
0x180027879  call    DeleteMMPolicy
0x18002787e  mov     ebx, eax
0x180027880  test    eax, eax
0x180027882  jz      short loc_1800278B3
0x180027884  mov     [rdi+1Ch], eax
0x180027887  mov     rcx, cs:WPP_GLOBAL_Control
0x18002788e  cmp     rcx, rsi
0x180027891  jz      short loc_1800278BB
0x180027893  test    byte ptr [rcx+1Ch], 10h
0x180027897  jz      short loc_1800278BB
0x180027899  mov     rcx, [rcx+10h]
0x18002789d  lea     r8, WPP_30a2a25fe4c032b6b42c56c6e7b9adea_Traceguids
0x1800278a4  mov     edx, 19h
0x1800278a9  mov     r9d, eax
0x1800278ac  call    WPP_SF_d
0x1800278b1  jmp     short loc_1800278BB
0x1800278b3  mov     rcx, rdi
0x1800278b6  call    PADeleteMMPolicyState
0x1800278bb  mov     eax, ebx
0x1800278bd  mov     rcx, [rsp+58h+var_18]
0x1800278c2  xor     rcx, rsp; StackCookie
0x1800278c5  call    __security_check_cookie
0x1800278ca  mov     rbx, [rsp+58h+arg_8]
0x1800278cf  mov     rsi, [rsp+58h+arg_10]
0x1800278d4  add     rsp, 50h
0x1800278d8  pop     rdi
0x1800278d9  retn
```
